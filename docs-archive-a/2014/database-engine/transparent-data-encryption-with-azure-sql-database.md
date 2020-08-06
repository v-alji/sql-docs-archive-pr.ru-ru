---
title: Прозрачное шифрование данных в базе данных SQL Azure | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- TDE, SQL Database
- Transparent Data Encryption, SQL Database
- encryption (SQL Database) TDE
ms.assetid: 0bf7e8ff-1416-4923-9c4c-49341e208c62
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6af7c52741b85a2733b93c2b1ed8c03a14dd6343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664459"
---
# <a name="transparent-data-encryption-with-azure-sql-database"></a><span data-ttu-id="380c3-102">Прозрачное шифрование данных в Базе данных SQL Azure</span><span class="sxs-lookup"><span data-stu-id="380c3-102">Transparent Data Encryption with Azure SQL Database</span></span>
  <span data-ttu-id="380c3-103">Прозрачное шифрование данных [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] (предварительная версия) защищает от угроз вредоносных действий, в реальном времени выполняя шифрование и расшифровку неактивных файлов базы данных, связанных резервных копий и журнала транзакций. При этом способ использования не меняется.</span><span class="sxs-lookup"><span data-stu-id="380c3-103">[!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] transparent data encryption (preview) helps protect against the threat of malicious activity by performing real-time encryption and decryption of the database, associated backups, and transaction log files at rest without requiring changes to the application.</span></span>

 <span data-ttu-id="380c3-104">При использовании TDE хранилище всей базы данных шифруется с помощью симметричного ключа, который называется ключом шифрования базы данных.</span><span class="sxs-lookup"><span data-stu-id="380c3-104">TDE encrypts the storage of an entire database by using a symmetric key called the database encryption key.</span></span> <span data-ttu-id="380c3-105">В [!INCLUDE[ssSDS](../includes/sssds-md.md)] для защиты ключа шифрования базы данных используется встроенный сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="380c3-105">In [!INCLUDE[ssSDS](../includes/sssds-md.md)] the database encryption key is protected by a built-in server certificate.</span></span> <span data-ttu-id="380c3-106">Встроенный сертификат сервера уникален для каждого сервера [!INCLUDE[ssSDS](../includes/sssds-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="380c3-106">The built-in server certificate is unique for each [!INCLUDE[ssSDS](../includes/sssds-md.md)] server.</span></span> <span data-ttu-id="380c3-107">Если база данных находится в отношении GeoDR, на каждом сервере для защиты используется разный ключ.</span><span class="sxs-lookup"><span data-stu-id="380c3-107">If a database is in a GeoDR relationship, it is protected by a different key on each server.</span></span> <span data-ttu-id="380c3-108">Если две базы данных подключены к одному серверу, используется один встроенный сертификат.</span><span class="sxs-lookup"><span data-stu-id="380c3-108">If 2 databases are connected to the same server, they share the same built-in certificate.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="380c3-109">автоматически меняет эти сертификаты каждые 90 дней.</span><span class="sxs-lookup"><span data-stu-id="380c3-109">automatically rotates these certificates at least every 90 days.</span></span> <span data-ttu-id="380c3-110">Общее описание прозрачного шифрования данных см. в разделе [Прозрачное шифрование данных (TDE)](../relational-databases/security/encryption/transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="380c3-110">For a general description of TDE, see [Transparent Data Encryption &#40;TDE&#41;](../relational-databases/security/encryption/transparent-data-encryption.md).</span></span>

 [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] <span data-ttu-id="380c3-111">не поддерживает интеграцию хранилища ключей Azure с TDE.</span><span class="sxs-lookup"><span data-stu-id="380c3-111">does not support Azure Key Vault integration with TDE.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="380c3-112">, запущенный на виртуальной машине Azure, может использовать асимметричный ключ из хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="380c3-112">running on an Azure virtual machine can use an asymmetric key from the Key Vault.</span></span> <span data-ttu-id="380c3-113">Дополнительные сведения см. в разделе [Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault](../relational-databases/security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md#ExampleA).</span><span class="sxs-lookup"><span data-stu-id="380c3-113">For more information, see [Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault](../relational-databases/security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md#ExampleA).</span></span>

||
|-|
|<span data-ttu-id="380c3-114">Область **применения**: [!INCLUDE[sqldbesa](../includes/sqldbesa-md.md)] ([Предварительная версия в некоторых регионах](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span><span class="sxs-lookup"><span data-stu-id="380c3-114">**Applies to**: [!INCLUDE[sqldbesa](../includes/sqldbesa-md.md)] ([Preview in some regions](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="380c3-115">В настоящий момент это предварительная версия функции.</span><span class="sxs-lookup"><span data-stu-id="380c3-115">This is currently a preview feature.</span></span> <span data-ttu-id="380c3-116">Я признаю и соглашаюсь, что в отношении использования в моих базах данных прозрачного шифрования данных [!INCLUDE[ssSDS](../includes/sssds-md.md)] действуют условия предварительной версии, приведенные в моем лицензионном соглашении (например, Соглашении Enterprise, соглашении для Microsoft Azure или соглашении Microsoft Online Subscription), а также [дополнительные условия использования предварительных версий Microsoft Azure](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span><span class="sxs-lookup"><span data-stu-id="380c3-116">I acknowledge and agree that implementation of [!INCLUDE[ssSDS](../includes/sssds-md.md)] transparent data encryption in my database(s) is subject to the preview terms in my license agreement (e.g. the Enterprise Agreement, Microsoft Azure Agreement, or Microsoft Online Subscription Agreement), as well as any applicable [Supplemental Terms of Use for Microsoft Azure Preview](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span></span>

 <span data-ttu-id="380c3-117">Просмотр состояния TDE применяется даже в подмножестве географических регионов, в которых сообщается, что версия семейства V12 [!INCLUDE[ssSDS](../includes/sssds-md.md)] теперь общедоступна.</span><span class="sxs-lookup"><span data-stu-id="380c3-117">The preview of status of TDE applies even in the subset of geographic regions where version family V12 of [!INCLUDE[ssSDS](../includes/sssds-md.md)] is announced as now being in general availability status.</span></span> <span data-ttu-id="380c3-118">Прозрачное шифрование данных для [!INCLUDE[ssSDS](../includes/sssds-md.md)] не используется в рабочих базах данных до тех пор, пока [!INCLUDE[msCoName](../includes/msconame-md.md)] не объявит, что функция TDE становится общедоступной.</span><span class="sxs-lookup"><span data-stu-id="380c3-118">TDE for [!INCLUDE[ssSDS](../includes/sssds-md.md)] is not intended for use in production databases until [!INCLUDE[msCoName](../includes/msconame-md.md)] announces that TDE is promoted from preview to GA.</span></span> <span data-ttu-id="380c3-119">Дополнительные сведения о [!INCLUDE[ssSDS](../includes/sssds-md.md)] V12 можно найти в разделе [Новые возможности версии 12 базы данных SQL](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/).</span><span class="sxs-lookup"><span data-stu-id="380c3-119">For more information about [!INCLUDE[ssSDS](../includes/sssds-md.md)] V12, see [What's new in Azure SQL Database](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/).</span></span>

##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="380c3-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="380c3-120">Permissions</span></span>
 <span data-ttu-id="380c3-121">Чтобы подписаться на предварительную версию и настроить TDE через портал Azure с помощью REST API или PowerShell, необходимо подключиться в качестве владельца, участника или диспетчера безопасности SQL Azure.</span><span class="sxs-lookup"><span data-stu-id="380c3-121">To sign up for the preview and to configure TDE through the Azure portal, by using the REST API, or by using PowerShell, you must be connected as the Azure Owner, Contributor, or SQL Security Manager.</span></span>

 <span data-ttu-id="380c3-122">Чтобы настроить TDE с помощью [!INCLUDE[tsql](../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="380c3-122">To configure TDE by using [!INCLUDE[tsql](../includes/tsql-md.md)] requires the following:</span></span>

-   <span data-ttu-id="380c3-123">Нужен доступ к предварительной версии TDE.</span><span class="sxs-lookup"><span data-stu-id="380c3-123">You must be already signed up for the TDE preview.</span></span>

-   <span data-ttu-id="380c3-124">Чтобы создать ключ шифрования базы данных, нужны права администратора [!INCLUDE[ssSDS](../includes/sssds-md.md)] или роль **dbmanager** в базе данных master и разрешение **CONTROL** .</span><span class="sxs-lookup"><span data-stu-id="380c3-124">To create the database encryption key you must be a [!INCLUDE[ssSDS](../includes/sssds-md.md)] administrator or you must be a member of the **dbmanager** role in the master database and have the **CONTROL** permission on the database.</span></span>

-   <span data-ttu-id="380c3-125">Чтобы выполнить инструкцию ALTER DATABASE с параметром SET, нужна только роль **dbmanager** .</span><span class="sxs-lookup"><span data-stu-id="380c3-125">To execute the ALTER DATABASE statement with the SET option only requires membership in the **dbmanager** role.</span></span>

##  <a name="sign-up-for-the-preview-of-tde-and-enable-tde-on-a-database"></a><a name="Preview"></a><span data-ttu-id="380c3-126">Зарегистрируйтесь для использования предварительной версии TDE и включите TDE в базе данных</span><span class="sxs-lookup"><span data-stu-id="380c3-126">Sign Up for the Preview of TDE and Enable TDE on a Database</span></span>

1.  <span data-ttu-id="380c3-127">Посетите портал Azure по адресу [https://portal.azure.com](https://portal.azure.com) и войдите с помощью учетной записи администратора или участника Azure.</span><span class="sxs-lookup"><span data-stu-id="380c3-127">Visit the Azure Portal at [https://portal.azure.com](https://portal.azure.com) and sign-in with your Azure Administrator or Contributor account.</span></span>

2.  <span data-ttu-id="380c3-128">В области слева нажмите кнопку **ОБЗОР** и выберите **Базы данных SQL**.</span><span class="sxs-lookup"><span data-stu-id="380c3-128">On the left banner, click to **BROWSE**, and then click **SQL databases**.</span></span>

3.  <span data-ttu-id="380c3-129">Выбрав пункт **Базы данных SQL** в области слева, выберите свою пользовательскую базу данных.</span><span class="sxs-lookup"><span data-stu-id="380c3-129">With **SQL databases** selected in the left pane, click your user database.</span></span>

4.  <span data-ttu-id="380c3-130">В колонке базы данных щелкните **Все параметры**.</span><span class="sxs-lookup"><span data-stu-id="380c3-130">In the database blade, click **All settings**.</span></span>

5.  <span data-ttu-id="380c3-131">В колонке **Параметры** выберите **Прозрачное шифрование данных (предварительная версия)** , чтобы открыть колонку **Прозрачное шифрование данных ПРЕДВАРИТЕЛЬНАЯ ВЕРСИЯ** .</span><span class="sxs-lookup"><span data-stu-id="380c3-131">In the **Settings** blade, click **Transparent data encryption (preview)** part to open the **Transparent data encryption PREVIEW** blade.</span></span> <span data-ttu-id="380c3-132">Если вы еще не подписались на предварительную версию TDE, параметры шифрования данных будут неактивны.</span><span class="sxs-lookup"><span data-stu-id="380c3-132">If you have not already signed up for the TDE preview, the data encryption settings will be disabled until you complete signup.</span></span>

6.  <span data-ttu-id="380c3-133">Щелкните **УСЛОВИЯ ПРЕДВАРИТЕЛЬНОЙ ВЕРСИИ**.</span><span class="sxs-lookup"><span data-stu-id="380c3-133">Click **PREVIEW TERMS**.</span></span>

7.  <span data-ttu-id="380c3-134">Ознакомьтесь с условиями предварительной версии и, если вы согласны с условиями, установите флажок **прозрачные енкриптионпревиев термины данных** и нажмите кнопку **ОК** в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="380c3-134">Read the terms of the preview, and if you agree to the terms, select the **Transparent Data encryptionPreview terms** check box, and then click **OK** near the bottom of the page.</span></span> <span data-ttu-id="380c3-135">Возврат в колонку **Енкриптионпревиев данных** , где теперь должна быть включена кнопка **шифрования данных** .</span><span class="sxs-lookup"><span data-stu-id="380c3-135">Returning to the **Data encryptionPREVIEW** blade, where the **Data encryption** button should now be enabled.</span></span>

8.  <span data-ttu-id="380c3-136">В колонке **Шифрование данных ПРЕДВАРИТЕЛЬНАЯ ВЕРСИЯ** переместите кнопку **Шифрование данных** в положение **ВКЛ**и нажмите кнопку **Сохранить** вверху страницы.</span><span class="sxs-lookup"><span data-stu-id="380c3-136">In the **Data encryption PREVIEW** blade, move the **Data encryption** button to **On**, and then click **Save** (at the top of the page) to apply the setting.</span></span> <span data-ttu-id="380c3-137">В разделе **Состояние шифрования** будет отображаться приблизительный ход прозрачного шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="380c3-137">The **Encryption status** will approximate the progress of the transparent data encryption.</span></span>

     <span data-ttu-id="380c3-138">![SQLDB_TDE_TermsNewUI](../../2014/database-engine/media/sqldb-tde-termsnewui.png "SQLDB_TDE_TermsNewUI")</span><span class="sxs-lookup"><span data-stu-id="380c3-138">![SQLDB_TDE_TermsNewUI](../../2014/database-engine/media/sqldb-tde-termsnewui.png "SQLDB_TDE_TermsNewUI")</span></span>

     <span data-ttu-id="380c3-139">Кроме того, отслеживать ход шифрования можно, подключившись к [!INCLUDE[ssSDS](../includes/sssds-md.md)] с помощью инструмента запросов, например [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , в качестве пользователя базы данных с разрешением **VIEW DATABASE STATE** .</span><span class="sxs-lookup"><span data-stu-id="380c3-139">You can also monitor the progress of encryption by connecting to [!INCLUDE[ssSDS](../includes/sssds-md.md)] using a query tool such as [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] as a database user with the **VIEW DATABASE STATE** permission.</span></span> <span data-ttu-id="380c3-140">Запросите `encryption_state` Столбец представления [sys. dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="380c3-140">Query the `encryption_state` column of the [sys.dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) view.</span></span>

##  <a name="enabling-tde-on-sssds-by-using-transact-sql"></a><a name="Encrypt"></a><span data-ttu-id="380c3-141">Включение TDE в с [!INCLUDE[ssSDS](../includes/sssds-md.md)] помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="380c3-141">Enabling TDE on [!INCLUDE[ssSDS](../includes/sssds-md.md)] by Using Transact-SQL</span></span>
 <span data-ttu-id="380c3-142">Далее предполагается, что вы уже подписались на предварительную версию.</span><span class="sxs-lookup"><span data-stu-id="380c3-142">The following steps, assume you have already signed up for the preview.</span></span>

###  <a name="TsqlProcedure"></a>

1.  <span data-ttu-id="380c3-143">Подключитесь к базе данных, используя учетные данные администратора или участника роли **dbmanager** в базе данных master.</span><span class="sxs-lookup"><span data-stu-id="380c3-143">Connect to the database using a login that is an administrator or a member of the **dbmanager** role in the master database.</span></span>

2.  <span data-ttu-id="380c3-144">Выполните следующие инструкции, чтобы создать ключ шифрования и зашифровать базу данных.</span><span class="sxs-lookup"><span data-stu-id="380c3-144">Execute the following statements to create a database encryption key and encrypt the database.</span></span>

    ```sql
    -- Create the database encryption key that will be used for TDE.
    CREATE DATABASE ENCRYPTION KEY 
    WITH ALGORITHM = AES_256 
    ENCRYPTION BY SERVER CERTIFICATE ##MS_TdeCertificate##;

    -- Enable encryption
    ALTER DATABASE [AdventureWorks] SET ENCRYPTION ON;
    GO
    ```

3.  <span data-ttu-id="380c3-145">Чтобы отслеживать ход выполнения шифрования в [!INCLUDE[ssSDS](../includes/sssds-md.md)] , пользователи базы данных с разрешением **Просмотр состояния базы данных** могут запрашивать `encryption_state` столбец представления [sys. dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="380c3-145">To monitor the progress of encryption on [!INCLUDE[ssSDS](../includes/sssds-md.md)], database users with the **VIEW DATABASE STATE** permission can query the `encryption_state` column of the [sys.dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) view.</span></span>

## <a name="enabling-tde-on-sql-database-by-using-powershell"></a><span data-ttu-id="380c3-146">Включение TDE в Базе данных SQL с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="380c3-146">Enabling TDE on SQL Database by Using PowerShell</span></span>
 <span data-ttu-id="380c3-147">Включить и отключить TDE можно с помощью следующих команд Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="380c3-147">Using the Azure PowerShell you can run the following command to turn TDE on/off.</span></span> <span data-ttu-id="380c3-148">Перед выполнением команды подключите свою учетную запись к окну PS.</span><span class="sxs-lookup"><span data-stu-id="380c3-148">You do have to connect your account to the PS window before running the command.</span></span> <span data-ttu-id="380c3-149">Далее предполагается, что вы уже подписались на предварительную версию.</span><span class="sxs-lookup"><span data-stu-id="380c3-149">The following steps, assume you have already signed up for the preview.</span></span> <span data-ttu-id="380c3-150">Дополнительные сведения о PowerShell см. в разделе [Установка и настройка Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span><span class="sxs-lookup"><span data-stu-id="380c3-150">For additional information about PowerShell, see [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span>

1.  <span data-ttu-id="380c3-151">Чтобы включить TDE и просмотреть состояние шифрования:</span><span class="sxs-lookup"><span data-stu-id="380c3-151">To enable TDE, return the TDE status, and view the encryption activity.</span></span>

    ```powershell
    Switch-AzureMode -Name AzureResourceManager
    Set-AzureSqlDatabaseTransparentDataEncryption -ServerName "myserver" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "database1" -State "Enabled"

    Get-AzureSqlDatabaseTransparentDataEncryption -ServerName "myserver" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "database1"
    Get-AzureSqlDatabaseTransparentDataEncryptionActivity -ServerName "myserver" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "database1"
    ```

2.  <span data-ttu-id="380c3-152">Чтобы отключить TDE:</span><span class="sxs-lookup"><span data-stu-id="380c3-152">To disable TDE:</span></span>

    ```powershell
    Set-AzureSqlDatabaseTransparentDataEncryption -ServerName "myserver" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "database1" -State "Disabled"
    Switch-AzureMode -Name AzureServiceManagement
    ```

##  <a name="decrypting-a-tde-protected-database-on-sssds"></a><a name="Decrypt"></a><span data-ttu-id="380c3-153">Расшифровка защищенной базы данных TDE на[!INCLUDE[ssSDS](../includes/sssds-md.md)]</span><span class="sxs-lookup"><span data-stu-id="380c3-153">Decrypting a TDE Protected Database on [!INCLUDE[ssSDS](../includes/sssds-md.md)]</span></span>

#### <a name="to-disable-tde-by-using-the-azure-portal"></a><span data-ttu-id="380c3-154">Отключение TDE с помощью портала Azure</span><span class="sxs-lookup"><span data-stu-id="380c3-154">To Disable TDE by Using the Azure Portal</span></span>

1.  <span data-ttu-id="380c3-155">Посетите портал Azure по адресу [https://portal.azure.com](https://portal.azure.com) и войдите с помощью учетной записи администратора или участника Azure.</span><span class="sxs-lookup"><span data-stu-id="380c3-155">Visit the Azure Portal at [https://portal.azure.com](https://portal.azure.com) and sign-in with your Azure Administrator or Contributor account.</span></span>

2.  <span data-ttu-id="380c3-156">В области слева нажмите кнопку **ОБЗОР** и выберите **Базы данных SQL**.</span><span class="sxs-lookup"><span data-stu-id="380c3-156">On the left banner, click to **BROWSE**, and then click **SQL databases**.</span></span>

3.  <span data-ttu-id="380c3-157">Выбрав пункт **Базы данных SQL** в области слева, выберите свою пользовательскую базу данных.</span><span class="sxs-lookup"><span data-stu-id="380c3-157">With **SQL databases** selected in the left pane, click your user database.</span></span>

4.  <span data-ttu-id="380c3-158">В колонке базы данных щелкните **Все параметры**.</span><span class="sxs-lookup"><span data-stu-id="380c3-158">In the database blade, click **All settings**.</span></span>

5.  <span data-ttu-id="380c3-159">В колонке **Параметры** выберите **Прозрачное шифрование данных (предварительная версия)** , чтобы открыть колонку **Прозрачное шифрование данных ПРЕДВАРИТЕЛЬНАЯ ВЕРСИЯ** .</span><span class="sxs-lookup"><span data-stu-id="380c3-159">In the **Settings** blade, click **Transparent data encryption (preview)** part to open the **Transparent data encryption PREVIEW** blade.</span></span>

6.  <span data-ttu-id="380c3-160">В колонке **Прозрачное шифрование данных ПРЕДВАРИТЕЛЬНАЯ ВЕРСИЯ** переместите кнопку **Шифрование данных** в положение **ВЫКЛ**и нажмите кнопку **Сохранить** вверху страницы.</span><span class="sxs-lookup"><span data-stu-id="380c3-160">In the **Transparent data encryption PREVIEW** blade, move the **Data encryption** button to **Off**, and then click **Save** (at the top of the page) to apply the setting.</span></span> <span data-ttu-id="380c3-161">В разделе **Состояние шифрования** будет отображаться приблизительный ход прозрачной расшифровки данных.</span><span class="sxs-lookup"><span data-stu-id="380c3-161">The **Encryption status** will approximate the progress of the transparent data decryption.</span></span>

     <span data-ttu-id="380c3-162">Кроме того, отслеживать ход расшифровки можно, подключившись к [!INCLUDE[ssSDS](../includes/sssds-md.md)] с помощью инструмента запросов, например [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] , в качестве пользователя базы данных с разрешением **VIEW DATABASE STATE** .</span><span class="sxs-lookup"><span data-stu-id="380c3-162">You can also monitor the progress of decryption by connecting to [!INCLUDE[ssSDS](../includes/sssds-md.md)] using a query tool such as [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] as a database user with the **VIEW DATABASE STATE** permission.</span></span> <span data-ttu-id="380c3-163">Запросите `encryption_state` Столбец представления [sys. dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="380c3-163">Query the `encryption_state` column of the [sys.dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql)view.</span></span>

#### <a name="to-disable-tde-by-using-transact-sql"></a><span data-ttu-id="380c3-164">Отключение TDE с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="380c3-164">To Disable TDE by Using Transact-SQL</span></span>

1.  <span data-ttu-id="380c3-165">Подключитесь к базе данных, используя учетные данные администратора или участника роли **dbmanager** в базе данных master.</span><span class="sxs-lookup"><span data-stu-id="380c3-165">Connect to the database using a login that is an administrator or a member of the **dbmanager** role in the master database.</span></span>

2.  <span data-ttu-id="380c3-166">Выполните следующие инструкции, чтобы расшифровать базу данных.</span><span class="sxs-lookup"><span data-stu-id="380c3-166">Execute the following statements to decrypt the database.</span></span>

    ```sql
    -- Enable encryption
    ALTER DATABASE [AdventureWorks] SET ENCRYPTION OFF;
    GO
    ```

3.  <span data-ttu-id="380c3-167">Чтобы отслеживать ход выполнения шифрования в [!INCLUDE[ssSDS](../includes/sssds-md.md)] , пользователи базы данных с разрешением **Просмотр состояния базы данных** могут запрашивать `encryption_state` столбец представления [sys. dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="380c3-167">To monitor the progress of encryption on [!INCLUDE[ssSDS](../includes/sssds-md.md)], database users with the **VIEW DATABASE STATE** permission can query the `encryption_state` column of the [sys.dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) view.</span></span>

##  <a name="working-with-tde-protected-databases-on-sssds"></a><a name="Working"></a><span data-ttu-id="380c3-168">Работа с защищенными базами данных TDE в[!INCLUDE[ssSDS](../includes/sssds-md.md)]</span><span class="sxs-lookup"><span data-stu-id="380c3-168">Working with TDE Protected Databases on [!INCLUDE[ssSDS](../includes/sssds-md.md)]</span></span>
 <span data-ttu-id="380c3-169">Расшифровывать базы данных для работы в Azure не нужно.</span><span class="sxs-lookup"><span data-stu-id="380c3-169">You do not need to decrypt databases for operations within Azure.</span></span> <span data-ttu-id="380c3-170">Параметры TDE базы данных-источника прозрачно наследуются целевым объектом.</span><span class="sxs-lookup"><span data-stu-id="380c3-170">The TDE settings on the source database or primary database are transparently inherited on the target.</span></span> <span data-ttu-id="380c3-171">Сюда входят операции, связанные с:</span><span class="sxs-lookup"><span data-stu-id="380c3-171">This includes operations involving:</span></span>

-   <span data-ttu-id="380c3-172">геовосстановлением;</span><span class="sxs-lookup"><span data-stu-id="380c3-172">Geo-Restore</span></span>

-   <span data-ttu-id="380c3-173">самостоятельным восстановлением до точки во времени;</span><span class="sxs-lookup"><span data-stu-id="380c3-173">Self-Service Point in Time Restore</span></span>

-   <span data-ttu-id="380c3-174">восстановлением удаленной базы данных;</span><span class="sxs-lookup"><span data-stu-id="380c3-174">Restore a Deleted Database</span></span>

-   <span data-ttu-id="380c3-175">активной георепликацией;</span><span class="sxs-lookup"><span data-stu-id="380c3-175">Active Geo_Replication</span></span>

-   <span data-ttu-id="380c3-176">созданием копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="380c3-176">Creating a Database Copy</span></span>

##  <a name="moving-a-tde-protected-database-on-using-bacpac-files"></a><a name="Moving"></a><span data-ttu-id="380c3-177">Перемещение базы данных, защищенной TDE, в среде с помощью. BACPAC-файлы</span><span class="sxs-lookup"><span data-stu-id="380c3-177">Moving a TDE Protected Database on using .Bacpac Files</span></span>
 <span data-ttu-id="380c3-178">При экспорте базы данных с защитой TDE с помощью функции экспорта на портале [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] или в мастере импорта и экспорта [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ее содержимое не шифруется.</span><span class="sxs-lookup"><span data-stu-id="380c3-178">When exporting a TDE protected database using the Export Database function in the [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] Portal or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard, the content of the database is not encrypted.</span></span> <span data-ttu-id="380c3-179">Содержимое хранится в незашифрованных файлах .bacpac.</span><span class="sxs-lookup"><span data-stu-id="380c3-179">The content is stored in .bacpac files which are not encrypted.</span></span>  <span data-ttu-id="380c3-180">Не забудьте защитить файлы .bacpac соответствующим образом и включить TDE после завершения импорта новой базы данных.</span><span class="sxs-lookup"><span data-stu-id="380c3-180">Be sure to protect the .bacpac files appropriately and enable TDE once import of the new database is completed.</span></span>

## <a name="related-sql-server-topic"></a><span data-ttu-id="380c3-181">Связанный раздел по SQL Server</span><span class="sxs-lookup"><span data-stu-id="380c3-181">Related SQL Server Topic</span></span>
 [<span data-ttu-id="380c3-182">Включение TDE с помощью расширенного управления ключами</span><span class="sxs-lookup"><span data-stu-id="380c3-182">Enable TDE Using EKM</span></span>](../relational-databases/security/encryption/enable-tde-on-sql-server-using-ekm.md)

## <a name="see-also"></a><span data-ttu-id="380c3-183">См. также:</span><span class="sxs-lookup"><span data-stu-id="380c3-183">See Also</span></span>
 <span data-ttu-id="380c3-184">[Прозрачное шифрование данных &#40;TDE&#41;](../relational-databases/security/encryption/transparent-data-encryption.md) [Создание учетных данных &#40;transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [CREATE асимметричный ключ &#40;TRANSACT-](/sql/t-sql/statements/create-asymmetric-key-transact-sql) SQL&#41;[Создание ключа шифрования базы данных &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-encryption-key-transact-sql) [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) [инструкции ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)</span><span class="sxs-lookup"><span data-stu-id="380c3-184">[Transparent Data Encryption &#40;TDE&#41;](../relational-databases/security/encryption/transparent-data-encryption.md) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-encryption-key-transact-sql) [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)</span></span>
