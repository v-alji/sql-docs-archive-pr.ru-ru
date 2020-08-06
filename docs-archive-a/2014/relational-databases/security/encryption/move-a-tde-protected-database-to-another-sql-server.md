---
title: Перемещение базы данных, защищаемой прозрачным шифрованием, в другой экземпляр SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, moving
- TDE, moving a database
ms.assetid: fb420903-df54-4016-bab6-49e6dfbdedc7
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 3b03b4d9ecf31e9953fd3e22cec5c51bbacc0c25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752067"
---
# <a name="move-a-tde-protected-database-to-another-sql-server"></a><span data-ttu-id="43d09-102">Переместить базу данных, защищаемую прозрачным шифрованием, в другой экземпляр SQL Server</span><span class="sxs-lookup"><span data-stu-id="43d09-102">Move a TDE Protected Database to Another SQL Server</span></span>
  <span data-ttu-id="43d09-103">В этом разделе описано, как защитить базу данных с применением прозрачного шифрования данных и переместить базу данных в другой экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43d09-103">This topic describes how to protect a database by using transparent data encryption (TDE), and then move the database to another instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="43d09-104">Функция прозрачного шифрования данных выполняет шифрование и дешифрование ввода-вывода в реальном времени для файлов данных и журналов.</span><span class="sxs-lookup"><span data-stu-id="43d09-104">TDE performs real-time I/O encryption and decryption of the data and log files.</span></span> <span data-ttu-id="43d09-105">При шифровании используется ключ шифрования базы данных (DEK), который хранится в загрузочной записи базы данных, где можно получить к нему доступ при восстановлении.</span><span class="sxs-lookup"><span data-stu-id="43d09-105">The encryption uses a database encryption key (DEK), which is stored in the database boot record for availability during recovery.</span></span> <span data-ttu-id="43d09-106">Ключ шифрования базы данных является симметричным ключом, защищенным сертификатом, который хранится в базе данных `master` на сервере, или асимметричным ключом, защищенным модулем расширенного управления ключами.</span><span class="sxs-lookup"><span data-stu-id="43d09-106">The DEK is a symmetric key secured by using a certificate stored in the `master` database of the server or an asymmetric key protected by an EKM module.</span></span>  
  
 <span data-ttu-id="43d09-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="43d09-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="43d09-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="43d09-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="43d09-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="43d09-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="43d09-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="43d09-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="43d09-111">**Создание базы данных, защищаемой с применением прозрачного шифрования данных с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="43d09-111">**To create a database protected by transparent data encryption, using:**</span></span>  
  
     [<span data-ttu-id="43d09-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43d09-112">SQL Server Management Studio</span></span>](#SSMSCreate)  
  
     [<span data-ttu-id="43d09-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43d09-113">Transact-SQL</span></span>](#TsqlCreate)  
  
-   <span data-ttu-id="43d09-114">**Перемещение базы данных с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="43d09-114">**To move a database, using:**</span></span>  
  
     [<span data-ttu-id="43d09-115">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43d09-115">SQL Server Management Studio</span></span>](#SSMSMove)  
  
     [<span data-ttu-id="43d09-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43d09-116">Transact-SQL</span></span>](#TsqlMove)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="43d09-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="43d09-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="43d09-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="43d09-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="43d09-119">В случае перемещения базы данных, защищаемой прозрачным шифрованием, также необходимо переместить сертификат или асимметричный ключ, который служит для открытия ключа шифрования базы данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-119">When moving a TDE protected database, you must also move the certificate or asymmetric key that is used to open the DEK.</span></span> <span data-ttu-id="43d09-120">Сертификат или асимметричный ключ должен быть установлен в `master` базе данных целевого сервера, чтобы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] иметь доступ к файлам базы данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-120">The certificate or asymmetric key must be installed in the `master` database of the destination server, so that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can access the database files.</span></span> <span data-ttu-id="43d09-121">Дополнительные сведения см. в статье [Прозрачное шифрование данных (TDE)](transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="43d09-121">For more information, see [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span></span>  
  
-   <span data-ttu-id="43d09-122">Для восстановления сертификата необходимо хранить копии файла сертификата и файла закрытого ключа.</span><span class="sxs-lookup"><span data-stu-id="43d09-122">You must retain copies of both the certificate file and the private key file in order to recover the certificate.</span></span> <span data-ttu-id="43d09-123">Пароль для закрытого ключа не обязательно должен совпадать с паролем главного ключа базы данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-123">The password for the private key does not have to be the same as the database master key password.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="43d09-124">хранит файлы, созданные здесь, в папке **C:\Program FILES\MICROSOFT SQL Server\MSSQL12. МССКЛСЕРВЕР\МССКЛ\ДАТА** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="43d09-124">stores the files created here in **C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA** by default.</span></span> <span data-ttu-id="43d09-125">В других системах имена и расположения файлов могут быть иными.</span><span class="sxs-lookup"><span data-stu-id="43d09-125">Your file names and locations might be different.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="43d09-126">безопасность</span><span class="sxs-lookup"><span data-stu-id="43d09-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="43d09-127">Permissions</span><span class="sxs-lookup"><span data-stu-id="43d09-127">Permissions</span></span>  
  
-   <span data-ttu-id="43d09-128">`CONTROL DATABASE` `master` Для создания главного ключа базы данных требуется разрешение в базе данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-128">Requires `CONTROL DATABASE` permission on the `master` database to create the database master key.</span></span>  
  
-   <span data-ttu-id="43d09-129">`CREATE CERTIFICATE` `master` Для создания сертификата, ЗАЩИЩАЮЩего DEK, требуется разрешение в базе данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-129">Requires `CREATE CERTIFICATE` permission on the `master` database to create the certificate that protects the DEK.</span></span>  
  
-   <span data-ttu-id="43d09-130">Требуется разрешение `CONTROL DATABASE` в зашифрованной базе данных и разрешение `VIEW DEFINITION` на сертификат или асимметричный ключ, используемый для шифрования ключа шифрования базы данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-130">Requires `CONTROL DATABASE` permission on the encrypted database and `VIEW DEFINITION` permission on the certificate or asymmetric key that is used to encrypt the database encryption key.</span></span>  
  
##  <a name="to-create-a-database-protected-by-transparent-data-encryption"></a><a name="SSMSProcedure"></a> <span data-ttu-id="43d09-131">Создание базы данных, защищаемой с применением прозрачного шифрования данных</span><span class="sxs-lookup"><span data-stu-id="43d09-131">To create a database protected by transparent data encryption</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSCreate"></a> <span data-ttu-id="43d09-132">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43d09-132">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="43d09-133">Создайте главный ключ базы данных и сертификат в `master` базе данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-133">Create a database master key and certificate in the `master` database.</span></span> <span data-ttu-id="43d09-134">Дополнительные сведения см. в статье **Использование Transact-SQL** ниже.</span><span class="sxs-lookup"><span data-stu-id="43d09-134">For more information, see **Using Transact-SQL** below.</span></span>  
  
2.  <span data-ttu-id="43d09-135">Создайте резервную копию сертификата сервера в `master` базе данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-135">Create a backup of the server certificate in the `master` database.</span></span> <span data-ttu-id="43d09-136">Дополнительные сведения см. в статье **Использование Transact-SQL** ниже.</span><span class="sxs-lookup"><span data-stu-id="43d09-136">For more information, see **Using Transact-SQL** below.</span></span>  
  
3.  <span data-ttu-id="43d09-137">В обозревателе объектов щелкните правой кнопкой мыши папку **Базы данных** и выберите **Создать базу данных**.</span><span class="sxs-lookup"><span data-stu-id="43d09-137">In Object Explorer, right-click the **Databases** folder and select **New Database**.</span></span>  
  
4.  <span data-ttu-id="43d09-138">В диалоговом окне **Создание базы данных** в поле **Имя базы данных** введите имя новой базы данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-138">In the **New Database** dialog box, in the **Database name** box, enter the name of the new database.</span></span>  
  
5.  <span data-ttu-id="43d09-139">В поле **Владелец** введите имя владельца новой базы данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-139">In the **Owner** box, enter the name of the new database's owner.</span></span> <span data-ttu-id="43d09-140">Также можно нажать кнопку с многоточием **(...)** , чтобы открыть диалоговое окно **Выбор владельца базы данных**.</span><span class="sxs-lookup"><span data-stu-id="43d09-140">Alternately, click the ellipsis **(...)** to open the **Select Database Owner** dialog box.</span></span> <span data-ttu-id="43d09-141">Дополнительные сведения о создании новой базы данных см. в разделе [Create a Database](../../databases/create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="43d09-141">For more information on creating a new database, see [Create a Database](../../databases/create-a-database.md).</span></span>  
  
6.  <span data-ttu-id="43d09-142">В обозревателе объектов щелкните значок «плюс», чтобы развернуть папку **Базы данных** .</span><span class="sxs-lookup"><span data-stu-id="43d09-142">In Object Explorer, click the plus sign to expand the **Databases** folder.</span></span>  
  
7.  <span data-ttu-id="43d09-143">Щелкните правой кнопкой мыши созданную базу данных, выберите **Задачи**, затем **Управление шифрованием базы данных**.</span><span class="sxs-lookup"><span data-stu-id="43d09-143">Right-click the database you created, point to **Tasks**, and select **Manage Database Encryption**.</span></span>  
  
     <span data-ttu-id="43d09-144">В диалоговом окне **Управление шифрованием базы данных** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="43d09-144">The following options are available on the **Manage Database Encryption** dialog box.</span></span>  
  
     <span data-ttu-id="43d09-145">**Алгоритм шифрования**</span><span class="sxs-lookup"><span data-stu-id="43d09-145">**Encryption Algorithm**</span></span>  
     <span data-ttu-id="43d09-146">Отображает или устанавливает алгоритм для шифрования базы данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-146">Displays or sets the algorithm to use for database encryption.</span></span> <span data-ttu-id="43d09-147">Алгоритм шифрования по умолчанию — `AES128`.</span><span class="sxs-lookup"><span data-stu-id="43d09-147">`AES128` is the default algorithm.</span></span> <span data-ttu-id="43d09-148">Это поле не может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="43d09-148">This field cannot be blank.</span></span> <span data-ttu-id="43d09-149">Дополнительные сведения об алгоритмах шифрования см. в разделе [Choose an Encryption Algorithm](choose-an-encryption-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="43d09-149">For more information on encryption algorithms, see [Choose an Encryption Algorithm](choose-an-encryption-algorithm.md).</span></span>  
  
     <span data-ttu-id="43d09-150">**Использовать сертификат сервера**</span><span class="sxs-lookup"><span data-stu-id="43d09-150">**Use server certificate**</span></span>  
     <span data-ttu-id="43d09-151">Задает шифрование с защитой сертификатом.</span><span class="sxs-lookup"><span data-stu-id="43d09-151">Sets the encryption to be secured by a certificate.</span></span> <span data-ttu-id="43d09-152">Выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="43d09-152">Select one from the list.</span></span> <span data-ttu-id="43d09-153">Если разрешение `VIEW DEFINITION` для сертификатов сервера отсутствует, этот список будет пустым.</span><span class="sxs-lookup"><span data-stu-id="43d09-153">If you do not have the `VIEW DEFINITION` permission on server certificates, this list will be empty.</span></span> <span data-ttu-id="43d09-154">Если выбран метод шифрования с сертификатом, это значение не может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="43d09-154">If a certificate method of encryption is selected, this value cannot be empty.</span></span> <span data-ttu-id="43d09-155">Дополнительные сведения о сертификатах см. в разделе [SQL Server Certificates and Asymmetric Keys](../sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="43d09-155">For more information about certificates, see [SQL Server Certificates and Asymmetric Keys](../sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
     <span data-ttu-id="43d09-156">**Использовать асимметричный ключ сервера**</span><span class="sxs-lookup"><span data-stu-id="43d09-156">**Use server asymmetric key**</span></span>  
     <span data-ttu-id="43d09-157">Задает шифрование с защитой асимметричным ключом.</span><span class="sxs-lookup"><span data-stu-id="43d09-157">Sets the encryption to be secured by an asymmetric key.</span></span> <span data-ttu-id="43d09-158">Отображаются только доступные асимметричные ключи.</span><span class="sxs-lookup"><span data-stu-id="43d09-158">Only available asymmetric keys are displayed.</span></span> <span data-ttu-id="43d09-159">Только асимметричный ключ, защищенный модулем расширенного управления ключами, позволяет шифровать базу данных с помощью прозрачного шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-159">Only an asymmetric key protected by an EKM module can encrypt a database using TDE.</span></span>  
  
     <span data-ttu-id="43d09-160">**Задать шифрование базы данных для**</span><span class="sxs-lookup"><span data-stu-id="43d09-160">**Set Database Encryption On**</span></span>  
     <span data-ttu-id="43d09-161">Переключает базу данных между включенным (флажок установлен) или выключенным (флажок снят) режимом прозрачного шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-161">Alters the database to turn on (checked) or turn off (unchecked) TDE.</span></span>  
  
8.  <span data-ttu-id="43d09-162">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="43d09-162">When finished, click **OK**.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlCreate"></a> <span data-ttu-id="43d09-163">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43d09-163">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="43d09-164">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43d09-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="43d09-165">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="43d09-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="43d09-166">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="43d09-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Create a database master key and a certificate in the master database.  
    USE master ;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1';  
    GO  
    CREATE CERTIFICATE TestSQLServerCert   
    WITH SUBJECT = 'Certificate to protect TDE key'  
    GO  
    -- Create a backup of the server certificate in the master database.  
    -- The following code stores the backup of the certificate and the private key file in the default data location for this instance of SQL Server   
    -- (C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA).  
  
    BACKUP CERTIFICATE TestSQLServerCert   
    TO FILE = 'TestSQLServerCert'  
    WITH PRIVATE KEY   
    (  
        FILE = 'SQLPrivateKeyFile',  
        ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1'  
    );  
    GO  
    -- Create a database to be protected by TDE.  
    CREATE DATABASE CustRecords ;  
    GO  
    -- Switch to the new database.  
    -- Create a database encryption key, that is protected by the server certificate in the master database.   
    -- Alter the new database to encrypt the database using TDE.  
    USE CustRecords;  
    GO  
    CREATE DATABASE ENCRYPTION KEY  
    WITH ALGORITHM = AES_128  
    ENCRYPTION BY SERVER CERTIFICATE TestSQLServerCert;  
    GO  
    ALTER DATABASE CustRecords  
    SET ENCRYPTION ON;  
    GO  
    ```  
  
 <span data-ttu-id="43d09-167">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="43d09-167">For more information, see:</span></span>  
  
-   [<span data-ttu-id="43d09-168">CREATE MASTER KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43d09-168">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="43d09-169">CREATE CERTIFICATE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43d09-169">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="43d09-170">BACKUP CERTIFICATE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43d09-170">BACKUP CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-certificate-transact-sql)  
  
-   [<span data-ttu-id="43d09-171">CREATE DATABASE (SQL Server Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43d09-171">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
-   [<span data-ttu-id="43d09-172">CREATE DATABASE ENCRYPTION KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43d09-172">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)  
  
-   [<span data-ttu-id="43d09-173">ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43d09-173">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
##  <a name="to-move-a-database"></a><a name="TsqlProcedure"></a><span data-ttu-id="43d09-174">Перемещение базы данных</span><span class="sxs-lookup"><span data-stu-id="43d09-174">To move a database</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSMove"></a> <span data-ttu-id="43d09-175">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43d09-175">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="43d09-176">В обозревателе объектов щелкните правой кнопкой мыши зашифрованную ранее базу данных, выберите **Задачи**, затем **Отсоединить…** .</span><span class="sxs-lookup"><span data-stu-id="43d09-176">In Object Explorer, right-click the database you encrypted above, point to **Tasks** and select **Detach...**.</span></span>  
  
     <span data-ttu-id="43d09-177">В диалоговом окне **Отсоединение базы данных** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="43d09-177">The following options are available in the **Detach Database** dialog box.</span></span>  
  
     <span data-ttu-id="43d09-178">**Базы данных для отсоединения**</span><span class="sxs-lookup"><span data-stu-id="43d09-178">**Databases to detach**</span></span>  
     <span data-ttu-id="43d09-179">Перечисляет базы данных для отсоединения.</span><span class="sxs-lookup"><span data-stu-id="43d09-179">Lists the databases to detach.</span></span>  
  
     <span data-ttu-id="43d09-180">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="43d09-180">**Database Name**</span></span>  
     <span data-ttu-id="43d09-181">Отображает имя базы данных для отсоединения.</span><span class="sxs-lookup"><span data-stu-id="43d09-181">Displays the name of the database to be detached.</span></span>  
  
     <span data-ttu-id="43d09-182">**Удалить соединения**</span><span class="sxs-lookup"><span data-stu-id="43d09-182">**Drop Connections**</span></span>  
     <span data-ttu-id="43d09-183">Завершить соединения с указанной базой данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-183">Disconnect connections to the specified database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43d09-184">Невозможно отсоединить базу данных с активными соединениями.</span><span class="sxs-lookup"><span data-stu-id="43d09-184">You cannot detach a database with active connections.</span></span>  
  
     <span data-ttu-id="43d09-185">**Обновить статистику**</span><span class="sxs-lookup"><span data-stu-id="43d09-185">**Update Statistics**</span></span>  
     <span data-ttu-id="43d09-186">По умолчанию операция отсоединения сохраняет устаревшую статистику оптимизации. Для ее обновления установите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="43d09-186">By default, the detach operation retains any out-of-date optimization statistics when detaching the database; to update the existing optimization statistics, click this check box.</span></span>  
  
     <span data-ttu-id="43d09-187">**Сохранять полнотекстовые каталоги**</span><span class="sxs-lookup"><span data-stu-id="43d09-187">**Keep Full-Text Catalogs**</span></span>  
     <span data-ttu-id="43d09-188">По умолчанию операция отсоединения сохраняет связанные с базой данных полнотекстовые каталоги.</span><span class="sxs-lookup"><span data-stu-id="43d09-188">By default, the detach operation keeps any full-text catalogs that are associated with the database.</span></span> <span data-ttu-id="43d09-189">Для удаления этих каталогов сбросьте флажок **Сохранять полнотекстовые каталоги** .</span><span class="sxs-lookup"><span data-stu-id="43d09-189">To remove them, clear the **Keep Full-Text Catalogs** check box.</span></span> <span data-ttu-id="43d09-190">Этот параметр доступен только при обновлении базы данных с версии [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43d09-190">This option appears only when you are upgrading a database from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="43d09-191">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="43d09-191">**Status**</span></span>  
     <span data-ttu-id="43d09-192">Отображает одно из следующих состояний: **Готово** или **Не готово**.</span><span class="sxs-lookup"><span data-stu-id="43d09-192">Displays one of the following states: **Ready** or **Not ready**.</span></span>  
  
     <span data-ttu-id="43d09-193">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="43d09-193">**Message**</span></span>  
     <span data-ttu-id="43d09-194">Столбец **Сообщение** может отображать сведения о базе данных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="43d09-194">The **Message** column may display information about the database, as follows:</span></span>  
  
    -   <span data-ttu-id="43d09-195">Если база данных участвует в репликации, то ее **Состояние** имеет значение **Не готово** , а в столбце **Сообщение** отображается строка **База данных реплицирована**.</span><span class="sxs-lookup"><span data-stu-id="43d09-195">When a database is involved with replication, the **Status** is **Not ready** and the **Message** column displays **Database replicated**.</span></span>  
  
    -   <span data-ttu-id="43d09-196">Если имеется одно или несколько активных соединений с базой данных, то ее **состояние** имеет значение **Не готово**, а в столбце **Сообщение** отображается **Активных соединений**: _<число_активных_соединений>_ , например: **Активных подключений: 1**.</span><span class="sxs-lookup"><span data-stu-id="43d09-196">When a database has one or more active connections, the **Status** is **Not ready** and the **Message** column displays _<number_of_active_connections>_**Active connection(s)** - for example: **1 Active connection(s)**.</span></span> <span data-ttu-id="43d09-197">Прежде чем можно будет отсоединить базу данных, необходимо отключить активные соединений, выбрав команду **Удалить соединения**.</span><span class="sxs-lookup"><span data-stu-id="43d09-197">Before you can detach the database, you need to disconnect any active connections by selecting **Drop Connections**.</span></span>  
  
     <span data-ttu-id="43d09-198">Чтобы получить сведения о сообщении, откройте монитор активности, щелкнув текст с гиперссылкой.</span><span class="sxs-lookup"><span data-stu-id="43d09-198">To obtain more information about a message, click the hyperlinked text to open Activity Monitor.</span></span>  
  
2.  <span data-ttu-id="43d09-199">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="43d09-199">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="43d09-200">В проводнике Windows переместите или скопируйте файлы базы данных с исходного сервера в то же расположение на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="43d09-200">Using Windows Explorer, move or copy the database files from the source server to the same location on the destination server.</span></span>  
  
4.  <span data-ttu-id="43d09-201">В проводнике Windows переместите или скопируйте резервную копию сертификата сервера и файла закрытого ключа с исходного сервера в то же расположение на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="43d09-201">Using Windows Explorer, move or copy the backup of the server certificate and the private key file from the source server to the same location on the destination server.</span></span>  
  
5.  <span data-ttu-id="43d09-202">Создайте главный ключ базы данных на целевом экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43d09-202">Create a database master key on the destination instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="43d09-203">Дополнительные сведения см. в статье **Использование Transact-SQL** ниже.</span><span class="sxs-lookup"><span data-stu-id="43d09-203">For more information, see **Using Transact-SQL** below.</span></span>  
  
6.  <span data-ttu-id="43d09-204">Повторно создайте сертификат сервера с помощью файла резервной копии исходного сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="43d09-204">Recreate the server certificate by using the original server certificate backup file.</span></span> <span data-ttu-id="43d09-205">Дополнительные сведения см. в статье **Использование Transact-SQL** ниже.</span><span class="sxs-lookup"><span data-stu-id="43d09-205">For more information, see **Using Transact-SQL** below.</span></span>  
  
7.  <span data-ttu-id="43d09-206">В обозревателе объектов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]щелкните правой кнопкой мыши папку **Базы данных** и выберите команду **Присоединить...** .</span><span class="sxs-lookup"><span data-stu-id="43d09-206">In Object Explorer in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], right-click the **Databases** folder and select **Attach...**.</span></span>  
  
8.  <span data-ttu-id="43d09-207">В диалоговом окне **Присоединение баз данных** в области **Базы данных для присоединения**нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="43d09-207">In the **Attach Databases** dialog box, under **Databases to attach**, click **Add**.</span></span>  
  
9. <span data-ttu-id="43d09-208">В диалоговом окне " **Размещение файлов базы данных —**_server_name_ " выберите файл базы данных, который нужно присоединить к новому серверу, и нажмите кнопку " **ОК**".</span><span class="sxs-lookup"><span data-stu-id="43d09-208">In the **Locate Database Files -**_server_name_ dialog box, select the database file to attach to the new server and click **OK**.</span></span>  
  
     <span data-ttu-id="43d09-209">В диалоговом окне **Присоединение базы данных** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="43d09-209">The following options are available in the **Attach Databases** dialog box.</span></span>  
  
     <span data-ttu-id="43d09-210">**Базы данных для присоединения**</span><span class="sxs-lookup"><span data-stu-id="43d09-210">**Databases to attach**</span></span>  
     <span data-ttu-id="43d09-211">Отобразятся сведения о выбранных базах данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-211">Displays information about the selected databases.</span></span>  
  
     \<no column header>  
     <span data-ttu-id="43d09-212">Отображается значок, указывающий на состояние операции присоединения.</span><span class="sxs-lookup"><span data-stu-id="43d09-212">Displays an icon indicating the status of the attach operation.</span></span> <span data-ttu-id="43d09-213">Возможные значки описываются в приводимом ниже описании **Состояние** .</span><span class="sxs-lookup"><span data-stu-id="43d09-213">The possible icons are described in the **Status** description, below).</span></span>  
  
     <span data-ttu-id="43d09-214">**Расположение файла MDF**</span><span class="sxs-lookup"><span data-stu-id="43d09-214">**MDF File Location**</span></span>  
     <span data-ttu-id="43d09-215">Отображается путь и имя выбранного MDF-файла.</span><span class="sxs-lookup"><span data-stu-id="43d09-215">Displays the path and file name of the selected MDF file.</span></span>  
  
     <span data-ttu-id="43d09-216">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="43d09-216">**Database Name**</span></span>  
     <span data-ttu-id="43d09-217">Отображается имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-217">Displays the name of the database.</span></span>  
  
     <span data-ttu-id="43d09-218">**Присоединить как**</span><span class="sxs-lookup"><span data-stu-id="43d09-218">**Attach As**</span></span>  
     <span data-ttu-id="43d09-219">Необязательный параметр, указывает другое имя, под которым присоединяется база данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-219">Optionally, specifies a different name for the database to attach as.</span></span>  
  
     <span data-ttu-id="43d09-220">**Владелец**</span><span class="sxs-lookup"><span data-stu-id="43d09-220">**Owner**</span></span>  
     <span data-ttu-id="43d09-221">Содержит раскрывающийся список возможных владельцев базы данных, из которого при необходимости можно выбрать другого владельца.</span><span class="sxs-lookup"><span data-stu-id="43d09-221">Provides a drop-down list of possible database owners from which you can optionally select a different owner.</span></span>  
  
     <span data-ttu-id="43d09-222">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="43d09-222">**Status**</span></span>  
     <span data-ttu-id="43d09-223">Отображается состояние базы данных в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="43d09-223">Displays the status of the database according to the following table.</span></span>  
  
    |<span data-ttu-id="43d09-224">Значок</span><span class="sxs-lookup"><span data-stu-id="43d09-224">Icon</span></span>|<span data-ttu-id="43d09-225">Текст состояния</span><span class="sxs-lookup"><span data-stu-id="43d09-225">Status text</span></span>|<span data-ttu-id="43d09-226">Описание</span><span class="sxs-lookup"><span data-stu-id="43d09-226">Description</span></span>|  
    |----------|-----------------|-----------------|  
    |<span data-ttu-id="43d09-227">(Нет значка)</span><span class="sxs-lookup"><span data-stu-id="43d09-227">(No icon)</span></span>|<span data-ttu-id="43d09-228">(Нет текста)</span><span class="sxs-lookup"><span data-stu-id="43d09-228">(No text)</span></span>|<span data-ttu-id="43d09-229">Операция присоединения не была запущена или находится в режиме ожидания для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="43d09-229">Attach operation has not been started or may be pending for this object.</span></span> <span data-ttu-id="43d09-230">Это состояние по умолчанию при открытии диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="43d09-230">This is the default when the dialog is opened.</span></span>|  
    |<span data-ttu-id="43d09-231">Зеленый, указывающий направо треугольник</span><span class="sxs-lookup"><span data-stu-id="43d09-231">Green, right-pointing triangle</span></span>|<span data-ttu-id="43d09-232">Выполняется</span><span class="sxs-lookup"><span data-stu-id="43d09-232">In progress</span></span>|<span data-ttu-id="43d09-233">Операция присоединения была запущена, но не завершена.</span><span class="sxs-lookup"><span data-stu-id="43d09-233">Attach operation has been started but it is not complete.</span></span>|  
    |<span data-ttu-id="43d09-234">Зеленый флажок</span><span class="sxs-lookup"><span data-stu-id="43d09-234">Green check mark</span></span>|<span data-ttu-id="43d09-235">Успешно</span><span class="sxs-lookup"><span data-stu-id="43d09-235">Success</span></span>|<span data-ttu-id="43d09-236">Объект успешно присоединен.</span><span class="sxs-lookup"><span data-stu-id="43d09-236">The object has been attached successfully.</span></span>|  
    |<span data-ttu-id="43d09-237">Красный кружок с белым крестом внутри</span><span class="sxs-lookup"><span data-stu-id="43d09-237">Red circle containing a white cross</span></span>|<span data-ttu-id="43d09-238">Error</span><span class="sxs-lookup"><span data-stu-id="43d09-238">Error</span></span>|<span data-ttu-id="43d09-239">При выполнении операции присоединения возникла ошибка, и операция не была успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="43d09-239">Attach operation encountered an error and did not complete successfully.</span></span>|  
    |<span data-ttu-id="43d09-240">Кружок с двумя черными квадратами (слева и справа) и двумя белыми квадратами (сверху и снизу)</span><span class="sxs-lookup"><span data-stu-id="43d09-240">Circle containing two black quadrants (on left and right) and two white quadrants (on top and bottom)</span></span>|<span data-ttu-id="43d09-241">Остановлена</span><span class="sxs-lookup"><span data-stu-id="43d09-241">Stopped</span></span>|<span data-ttu-id="43d09-242">Операция присоединения не была успешно завершена, т.к. пользователь остановил операцию.</span><span class="sxs-lookup"><span data-stu-id="43d09-242">Attach operation was not completed successfully because the user stopped the operation.</span></span>|  
    |<span data-ttu-id="43d09-243">Кружок, содержащий изогнутую стрелку, указывающую в направлении против часовой стрелки</span><span class="sxs-lookup"><span data-stu-id="43d09-243">Circle containing a curved arrow pointing counter-clockwise</span></span>|<span data-ttu-id="43d09-244">Выполнен откат</span><span class="sxs-lookup"><span data-stu-id="43d09-244">Rolled Back</span></span>|<span data-ttu-id="43d09-245">Операция присоединения была успешной, но был выполнен ее откат из-за ошибки, возникшей при вложении другого объекта.</span><span class="sxs-lookup"><span data-stu-id="43d09-245">Attach operation was successful but it has been rolled back due to an error during attachment of another object.</span></span>|  
  
     <span data-ttu-id="43d09-246">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="43d09-246">**Message**</span></span>  
     <span data-ttu-id="43d09-247">Отображается пустое сообщение или гиперссылка «Файл не найден».</span><span class="sxs-lookup"><span data-stu-id="43d09-247">Displays either a blank message or a "File not found" hyperlink.</span></span>  
  
     <span data-ttu-id="43d09-248">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="43d09-248">**Add**</span></span>  
     <span data-ttu-id="43d09-249">Найдите необходимые основные файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-249">Find the necessary main database files.</span></span> <span data-ttu-id="43d09-250">Если пользователь выбирает mdf-файл, необходимые сведения автоматически вводятся в соответствующие поля сетки **Базы данных для присоединения** .</span><span class="sxs-lookup"><span data-stu-id="43d09-250">When the user selects an .mdf file, applicable information is automatically filled in the respective fields of the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="43d09-251">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="43d09-251">**Remove**</span></span>  
     <span data-ttu-id="43d09-252">Удаляет выбранный файл из сетки **Базы данных для присоединения** .</span><span class="sxs-lookup"><span data-stu-id="43d09-252">Removes the selected file from the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="43d09-253">**Сведения о базе данных "** _<имя_базы_данных>_ **"**</span><span class="sxs-lookup"><span data-stu-id="43d09-253">**"** _<database_name>_ **" database details**</span></span>  
     <span data-ttu-id="43d09-254">Отображаются имена файлов, которые необходимо присоединить.</span><span class="sxs-lookup"><span data-stu-id="43d09-254">Displays the names of the files to be attached.</span></span> <span data-ttu-id="43d09-255">Чтобы проверить или изменить путь к файлу, нажмите кнопку **Обзор** ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="43d09-255">To verify or change the pathname of a file, click the **Browse** button (**...**).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43d09-256">Если файл не существует, в столбце **Сообщение** отображается сообщение «Не найден».</span><span class="sxs-lookup"><span data-stu-id="43d09-256">If a file does not exist, the **Message** column displays "Not found."</span></span> <span data-ttu-id="43d09-257">Если файл журнала не найден, то он существует в другом каталоге или был удален.</span><span class="sxs-lookup"><span data-stu-id="43d09-257">If a log file is not found, it exists in another directory or has been deleted.</span></span> <span data-ttu-id="43d09-258">Необходимо или обновить путь файла в сетке **Сведения о базе данных** таким образом, чтобы этот путь указывал на правильное расположение, или удалить файл журнала из сетки.</span><span class="sxs-lookup"><span data-stu-id="43d09-258">You need to either update the file path in the **database details** grid to point to the correct location or remove the log file from the grid.</span></span> <span data-ttu-id="43d09-259">Если MDF-файл не найден, необходимо обновить путь этого файла в сетке таким образом, чтобы этот путь указывал на правильное расположение.</span><span class="sxs-lookup"><span data-stu-id="43d09-259">If an .ndf data file is not found, you need to update its path in the grid to point to the correct location.</span></span>  
  
     <span data-ttu-id="43d09-260">**Имя исходного файла**</span><span class="sxs-lookup"><span data-stu-id="43d09-260">**Original File Name**</span></span>  
     <span data-ttu-id="43d09-261">Отображается имя присоединенного файла, принадлежащего базе данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-261">Displays the name of the attached file belonging to the database.</span></span>  
  
     <span data-ttu-id="43d09-262">**Тип файла**</span><span class="sxs-lookup"><span data-stu-id="43d09-262">**File Type**</span></span>  
     <span data-ttu-id="43d09-263">Указывается тип файла: **Данные** или **Журнал**.</span><span class="sxs-lookup"><span data-stu-id="43d09-263">Indicates the type of file, **Data** or **Log**.</span></span>  
  
     <span data-ttu-id="43d09-264">**Текущий путь к файлу**</span><span class="sxs-lookup"><span data-stu-id="43d09-264">**Current File Path**</span></span>  
     <span data-ttu-id="43d09-265">Отображается путь к выбранному файлу базы данных.</span><span class="sxs-lookup"><span data-stu-id="43d09-265">Displays the path to the selected database file.</span></span> <span data-ttu-id="43d09-266">Путь может быть изменен вручную.</span><span class="sxs-lookup"><span data-stu-id="43d09-266">The path can be edited manually.</span></span>  
  
     <span data-ttu-id="43d09-267">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="43d09-267">**Message**</span></span>  
     <span data-ttu-id="43d09-268">Отображается пустое сообщение или гиперссылка "**Файл не найден**".</span><span class="sxs-lookup"><span data-stu-id="43d09-268">Displays either a blank message or a "**File not found**" hyperlink.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlMove"></a> <span data-ttu-id="43d09-269">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43d09-269">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="43d09-270">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43d09-270">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="43d09-271">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="43d09-271">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="43d09-272">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="43d09-272">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Detach the TDE protected database from the source server.   
    USE master ;  
    GO  
    EXEC master.dbo.sp_detach_db @dbname = N'CustRecords';  
    GO  
    -- Move or copy the database files from the source server to the same location on the destination server.   
    -- Move or copy the backup of the server certificate and the private key file from the source server to the same location on the destination server.   
    -- Create a database master key on the destination instance of SQL Server.   
    USE master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1';  
    GO  
    -- Recreate the server certificate by using the original server certificate backup file.   
    -- The password must be the same as the password that was used when the backup was created.  
  
    CREATE CERTIFICATE TestSQLServerCert   
    FROM FILE = 'TestSQLServerCert'  
    WITH PRIVATE KEY   
    (  
        FILE = 'SQLPrivateKeyFile',  
        DECRYPTION BY PASSWORD = '*rt@40(FL&dasl1'  
    );  
    GO  
    -- Attach the database that is being moved.   
    -- The path of the database files must be the location where you have stored the database files.  
    CREATE DATABASE [CustRecords] ON   
    ( FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\CustRecords.mdf' ),  
    ( FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\CustRecords_log.LDF' )  
    FOR ATTACH ;  
    GO  
    ```  
  
 <span data-ttu-id="43d09-273">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="43d09-273">For more information, see:</span></span>  
  
-   [<span data-ttu-id="43d09-274">sp_detach_db (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43d09-274">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
-   [<span data-ttu-id="43d09-275">CREATE MASTER KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43d09-275">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="43d09-276">CREATE CERTIFICATE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43d09-276">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="43d09-277">CREATE DATABASE (SQL Server Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43d09-277">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="43d09-278">См. также:</span><span class="sxs-lookup"><span data-stu-id="43d09-278">See Also</span></span>  
 [<span data-ttu-id="43d09-279">Присоединение и отсоединение базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="43d09-279">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../../databases/database-detach-and-attach-sql-server.md)  
  
  
