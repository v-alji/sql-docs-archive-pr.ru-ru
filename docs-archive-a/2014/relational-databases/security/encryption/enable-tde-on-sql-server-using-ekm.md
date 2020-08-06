---
title: Включение TDE с помощью расширенного управления ключами | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], TDE using an EKM
- TDE, EKM how to
- EKM, TDE how to
- Transparent Data Encryption, using EKM
ms.assetid: b892e7a7-95bd-4903-bf54-55ce08e225af
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: e659c5ff0245fdb17192b845eafc60badf5e295e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750608"
---
# <a name="enable-tde-using-ekm"></a><span data-ttu-id="083f3-102">Включение прозрачного шифрования данных с использованием расширенного управления ключами</span><span class="sxs-lookup"><span data-stu-id="083f3-102">Enable TDE Using EKM</span></span>
  <span data-ttu-id="083f3-103">В этом разделе описано, как включить прозрачное шифрование данных (TDE) в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] , чтобы защитить ключ шифрования базы данных с помощью асимметричного ключа, хранящегося на модуле расширенного управления ключами (EKM) при помощи [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="083f3-103">This topic describes how to enable transparent data encryption (TDE) in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] to protect a database encryption key by using an asymmetric key stored in an extensible key management (EKM) module with [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="083f3-104">При использовании TDE хранилище всей базы данных шифруется с помощью симметричного ключа, который называется ключом шифрования базы данных.</span><span class="sxs-lookup"><span data-stu-id="083f3-104">TDE encrypts the storage of an entire database by using a symmetric key called the database encryption key.</span></span> <span data-ttu-id="083f3-105">Ключ шифрования базы данных можно также защитить с помощью сертификата, защищенного главным ключом базы данных master.</span><span class="sxs-lookup"><span data-stu-id="083f3-105">The database encryption key can also be protected using a certificate which is protected by the database master key of the master database.</span></span> <span data-ttu-id="083f3-106">Дополнительные сведения о защите ключа шифрования базы данных с помощью главного ключа базы данных см. в разделе [Прозрачное шифрование данных (TDE)](transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="083f3-106">For more information about protecting the database encryption key by using the database master key, see [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span></span> <span data-ttu-id="083f3-107">Дополнительные сведения о настройке прозрачного шифрования данных при выполнении [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в виртуальной машине Azure см. в разделе [Расширенное управление ключами с помощью хранилища ключей Azure (SQL Server)](extensible-key-management-using-azure-key-vault-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="083f3-107">For information about configuring TDE when [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is running on an Azure VM, see [Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;](extensible-key-management-using-azure-key-vault-sql-server.md).</span></span>  
  
 <span data-ttu-id="083f3-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="083f3-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="083f3-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="083f3-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="083f3-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="083f3-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="083f3-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="083f3-111">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="083f3-112">Включение использования расширенного управления ключами для TDE при помощи Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="083f3-112">To enable TDE using EKM, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="083f3-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="083f3-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="083f3-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="083f3-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="083f3-115">Для создания ключа шифрования базы данных и шифрования в базе данных необходимо быть привилегированным пользователем (например, системным администратором).</span><span class="sxs-lookup"><span data-stu-id="083f3-115">You must be a high privileged user (such as a system administrator) to create a database encryption key and encrypt a database.</span></span> <span data-ttu-id="083f3-116">Этот пользователь должен также проходить проверку подлинности в модуле расширенного управления ключами.</span><span class="sxs-lookup"><span data-stu-id="083f3-116">That user must be able to be authenticated by the EKM module.</span></span>  
  
-   <span data-ttu-id="083f3-117">При запуске компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] он должен открыть базу данных.</span><span class="sxs-lookup"><span data-stu-id="083f3-117">Upon start up the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must open the database.</span></span> <span data-ttu-id="083f3-118">Чтобы это сделать, необходимо создать учетные данные, которые будут проверяться по расширенному управлению ключами, и добавить их к имени входа, основанном на асимметричном ключе.</span><span class="sxs-lookup"><span data-stu-id="083f3-118">To do this, you should create a credential that will be authenticated by the EKM, and add it to a login that is based on an asymmetric key.</span></span> <span data-ttu-id="083f3-119">Пользователи не смогут войти в систему с этим именем входа, но компонент [!INCLUDE[ssDE](../../../includes/ssde-md.md)] сможет пройти проверку подлинности на устройстве расширенного управления ключами.</span><span class="sxs-lookup"><span data-stu-id="083f3-119">Users cannot login using that login, but the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] will be able to authenticate itself with the EKM device.</span></span>  
  
-   <span data-ttu-id="083f3-120">Если асимметричный ключ, хранящийся в поставщике расширенного управления ключами, утерян, то [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]не сможет открыть базу данных.</span><span class="sxs-lookup"><span data-stu-id="083f3-120">If the asymmetric key stored in the EKM module is lost, the database will not be able to be opened by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="083f3-121">Если поставщик расширенного управления ключами позволяет создать резервную копию асимметричного ключа, необходимо создать его резервную копию и хранить ее в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="083f3-121">If the EKM provider lets you back up the asymmetric key, you should create a back up and store it in a secure location.</span></span>  
  
-   <span data-ttu-id="083f3-122">Параметры и настройки, которые требуются поставщиком расширенного управления ключами, могут отличаться от приведенного ниже примера кода.</span><span class="sxs-lookup"><span data-stu-id="083f3-122">The options and parameters required by your EKM provider can differ from what is provided in the code example below.</span></span> <span data-ttu-id="083f3-123">Дополнительные сведения см. в документации поставщика расширенного управления ключами.</span><span class="sxs-lookup"><span data-stu-id="083f3-123">For more information, see your EKM provider.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="083f3-124">безопасность</span><span class="sxs-lookup"><span data-stu-id="083f3-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="083f3-125">Permissions</span><span class="sxs-lookup"><span data-stu-id="083f3-125">Permissions</span></span>  
 <span data-ttu-id="083f3-126">В этом разделе используются следующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="083f3-126">This topic uses the following permissions:</span></span>  
  
-   <span data-ttu-id="083f3-127">Для изменения параметра конфигурации и выполнения инструкции RECONFIGURE должно быть предоставлено разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="083f3-127">To change a configuration option and run the RECONFIGURE statement, you must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="083f3-128">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="083f3-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
-   <span data-ttu-id="083f3-129">Требуется разрешение ALTER ANY CREDENTIAL.</span><span class="sxs-lookup"><span data-stu-id="083f3-129">Requires ALTER ANY CREDENTIAL permission.</span></span>  
  
-   <span data-ttu-id="083f3-130">Необходимо разрешение ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="083f3-130">Requires ALTER ANY LOGIN permission.</span></span>  
  
-   <span data-ttu-id="083f3-131">Требуется разрешение CREATE ASYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="083f3-131">Requires CREATE ASYMMETRIC KEY permission.</span></span>  
  
-   <span data-ttu-id="083f3-132">Требуется разрешение CONTROL в базе данных для ее шифрования.</span><span class="sxs-lookup"><span data-stu-id="083f3-132">Requires CONTROL permission on the database to encrypt the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="083f3-133">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="083f3-133">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-tde-using-ekm"></a><span data-ttu-id="083f3-134">Включение TDE с расширенным управлением ключами</span><span class="sxs-lookup"><span data-stu-id="083f3-134">To enable TDE using EKM</span></span>  
  
1.  <span data-ttu-id="083f3-135">Скопируйте файлы поставщика расширенного управления ключами в соответствующую папку на компьютере [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="083f3-135">Copy the files supplied by the EKM provider to an appropriate location on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="083f3-136">В этом примере используется папка **C:\EKM** .</span><span class="sxs-lookup"><span data-stu-id="083f3-136">In this example, we use the **C:\EKM** folder.</span></span>  
  
2.  <span data-ttu-id="083f3-137">Установите на компьютер сертификаты в соответствии с требованиями поставщика расширенного управления ключами.</span><span class="sxs-lookup"><span data-stu-id="083f3-137">Install certificates to the computer as required by your EKM provider.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="083f3-138">не поддерживает поставщик расширенного управления ключами.</span><span class="sxs-lookup"><span data-stu-id="083f3-138">does not supply an EKM provider.</span></span> <span data-ttu-id="083f3-139">Каждый поставщик расширенного управления ключами может иметь разные процедуры установки, настройки и авторизации пользователей.</span><span class="sxs-lookup"><span data-stu-id="083f3-139">Each EKM provider can have different procedures for installing, configuring and authorizing users.</span></span>  <span data-ttu-id="083f3-140">Проконсультируйтесь с документацией поставщика расширенного управления ключами, чтобы завершить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="083f3-140">Consult your EKM provider documentation to complete this step.</span></span>  
  
3.  <span data-ttu-id="083f3-141">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="083f3-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
4.  <span data-ttu-id="083f3-142">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="083f3-142">On the Standard bar, click **New Query**.</span></span>  
  
5.  <span data-ttu-id="083f3-143">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="083f3-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Enable advanced options.  
    sp_configure 'show advanced options', 1 ;  
    GO  
    RECONFIGURE ;  
    GO  
    -- Enable EKM provider  
    sp_configure 'EKM provider enabled', 1 ;  
    GO  
    RECONFIGURE ;  
    GO  
    -- Create a cryptographic provider, which we have chosen to call "EKM_Prov," based on an EKM provider  
  
    CREATE CRYPTOGRAPHIC PROVIDER EKM_Prov   
    FROM FILE = 'C:\EKM_Files\KeyProvFile.dll' ;  
    GO  
  
    -- Create a credential that will be used by system administrators.  
    CREATE CREDENTIAL sa_ekm_tde_cred   
    WITH IDENTITY = 'Identity1',   
    SECRET = 'q*gtev$0u#D1v'   
    FOR CRYPTOGRAPHIC PROVIDER EKM_Prov ;  
    GO  
  
    -- Add the credential to a high privileged user such as your   
    -- own domain login in the format [DOMAIN\login].  
    ALTER LOGIN Contoso\Mary  
    ADD CREDENTIAL sa_ekm_tde_cred ;  
    GO  
    -- create an asymmetric key stored inside the EKM provider  
    USE master ;  
    GO  
    CREATE ASYMMETRIC KEY ekm_login_key   
    FROM PROVIDER [EKM_Prov]  
    WITH ALGORITHM = RSA_512,  
    PROVIDER_KEY_NAME = 'SQL_Server_Key' ;  
    GO  
  
    -- Create a credential that will be used by the Database Engine.  
    CREATE CREDENTIAL ekm_tde_cred   
    WITH IDENTITY = 'Identity2'   
    , SECRET = 'jeksi84&sLksi01@s'   
    FOR CRYPTOGRAPHIC PROVIDER EKM_Prov ;  
  
    -- Add a login used by TDE, and add the new credential to the login.  
    CREATE LOGIN EKM_Login   
    FROM ASYMMETRIC KEY ekm_login_key ;  
    GO  
    ALTER LOGIN EKM_Login   
    ADD CREDENTIAL ekm_tde_cred ;  
    GO  
  
    -- Create the database encryption key that will be used for TDE.  
    USE AdventureWorks2012 ;  
    GO  
    CREATE DATABASE ENCRYPTION KEY  
    WITH ALGORITHM  = AES_128  
    ENCRYPTION BY SERVER ASYMMETRIC KEY ekm_login_key ;  
    GO  
  
    -- Alter the database to enable transparent data encryption.  
    ALTER DATABASE AdventureWorks2012   
    SET ENCRYPTION ON ;  
    GO  
    ```  
  
 <span data-ttu-id="083f3-144">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="083f3-144">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="083f3-145">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="083f3-145">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
-   [<span data-ttu-id="083f3-146">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="083f3-146">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-cryptographic-provider-transact-sql)  
  
-   [<span data-ttu-id="083f3-147">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="083f3-147">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)  
  
-   [<span data-ttu-id="083f3-148">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="083f3-148">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)  
  
-   [<span data-ttu-id="083f3-149">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="083f3-149">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
-   [<span data-ttu-id="083f3-150">CREATE DATABASE ENCRYPTION KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="083f3-150">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)  
  
-   [<span data-ttu-id="083f3-151">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="083f3-151">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)  
  
-   [<span data-ttu-id="083f3-152">ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="083f3-152">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
-   [<span data-ttu-id="083f3-153">Расширенное управление ключами с помощью хранилища ключей Azure (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="083f3-153">Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;</span></span>](extensible-key-management-using-azure-key-vault-sql-server.md)  
  
-   [<span data-ttu-id="083f3-154">Прозрачное шифрование данных в Базе данных SQL Azure</span><span class="sxs-lookup"><span data-stu-id="083f3-154">Transparent Data Encryption with Azure SQL Database</span></span>](../../../database-engine/transparent-data-encryption-with-azure-sql-database.md)  
  
  
