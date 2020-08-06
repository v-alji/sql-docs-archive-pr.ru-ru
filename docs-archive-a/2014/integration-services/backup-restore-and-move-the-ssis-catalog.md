---
title: Резервное копирование, восстановление и перемещение каталога служб SSIS | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: bf806aef-8556-48ab-aed5-e95de9a2204e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9de552ddd54168f516f42d9988302561616fd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658375"
---
# <a name="backup-restore-and-move-the-ssis-catalog"></a><span data-ttu-id="7bda0-102">Резервное копирование, восстановление и перемещение каталога служб SSIS</span><span class="sxs-lookup"><span data-stu-id="7bda0-102">Backup, Restore, and Move the SSIS Catalog</span></span>
  [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] <span data-ttu-id="7bda0-103">включена база данных SSISDB.</span><span class="sxs-lookup"><span data-stu-id="7bda0-103">includes the SSISDB database.</span></span> <span data-ttu-id="7bda0-104">Создайте запрос представления в базе данных SSISDB для просмотра объектов, настроек и рабочих данных, которые хранятся в каталоге **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="7bda0-104">You query views in the SSISDB database to inspect objects, settings, and operational data that are stored in the **SSISDB** catalog.</span></span> <span data-ttu-id="7bda0-105">Этот раздел содержит инструкции для выполнения резервного копирования и восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="7bda0-105">This topic provides instructions for backing up and restoring the database.</span></span>  
  
 <span data-ttu-id="7bda0-106">В каталоге **SSISDB** хранятся пакеты, которые развернуты на сервере [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bda0-106">The **SSISDB** catalog stores the packages that you've deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="7bda0-107">Дополнительные сведения о каталоге см. в разделе [Каталог служб SSIS](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="7bda0-107">For more information about the catalog, see [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
##  <a name="to-back-up-the-ssis-database"></a><a name="backup"></a> <span data-ttu-id="7bda0-108">Создание резервной копии базы данных служб SSIS</span><span class="sxs-lookup"><span data-stu-id="7bda0-108">To Back up the SSIS Database</span></span>  
  
1.  <span data-ttu-id="7bda0-109">Откройте среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] и установите соединение с экземпляром [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bda0-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="7bda0-110">Создайте резервную копию главного ключа для базы данных SSISDB с помощью инструкции BACKUP MASTER KEY Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="7bda0-110">Back up the master key for the SSISDB database, by using the BACKUP MASTER KEY Transact-SQL statement.</span></span> <span data-ttu-id="7bda0-111">Ключ хранится в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="7bda0-111">The key is stored in a file that you specify.</span></span> <span data-ttu-id="7bda0-112">Используйте пароль для шифрования главного ключа базы данных в файле.</span><span class="sxs-lookup"><span data-stu-id="7bda0-112">Use a password to encrypt the master key in the file.</span></span>  
  
     <span data-ttu-id="7bda0-113">Дополнительные сведения об инструкции см. в разделе [BACKUP MASTER KEY (Transact-SQL)](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7bda0-113">For more information about the statement, see [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
     <span data-ttu-id="7bda0-114">В следующем примере главный ключ экспортируется в файл `c:\temp directory\RCTestInstKey` .</span><span class="sxs-lookup"><span data-stu-id="7bda0-114">In the following example, the master key is exported to the `c:\temp directory\RCTestInstKey` file.</span></span> <span data-ttu-id="7bda0-115">Пароль `LS2Setup!` используется для шифрования главного ключа.</span><span class="sxs-lookup"><span data-stu-id="7bda0-115">The `LS2Setup!` password is used to encrypt the master key.</span></span>  
  
    ```  
    backup master key to file = 'c:\temp\RCTestInstKey'  
           encryption by password = 'LS2Setup!'  
  
    ```  
  
3.  <span data-ttu-id="7bda0-116">Выполните резервное копирование базы данных SSISDB с помощью диалогового окна **Создание резервной копии базы данных** в [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bda0-116">Back up the SSISDB database by using the **Backup Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="7bda0-117">Дополнительные сведения см. в разделе [Как создать резервную копию базы данных (среда SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=231812).</span><span class="sxs-lookup"><span data-stu-id="7bda0-117">For more information, see [How to: Back Up a Database (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=231812).</span></span>  
  
4.  <span data-ttu-id="7bda0-118">Создайте скрипт CREATE LOGIN для ## MS_SSISServerCleanupJobLogin ##, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7bda0-118">Generate the CREATE LOGIN script for ##MS_SSISServerCleanupJobLogin##, by doing the following.</span></span> <span data-ttu-id="7bda0-119">Дополнительные сведения см. в разделе [CREATE LOGIN (Transact-SQL)](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7bda0-119">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
    1.  <span data-ttu-id="7bda0-120">В обозревателе объектов среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]разверните узел **Безопасность** , а затем узел **Имена входа** .</span><span class="sxs-lookup"><span data-stu-id="7bda0-120">In Object Explorer in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Security** node and then expand the **Logins** node.</span></span>  
  
    2.  <span data-ttu-id="7bda0-121">Щелкните правой кнопкой мыши **##MS_SSISServerCleanupJobLogin##** и выберите **Внести в скрипт имена входа как** > **СОЗДАТЬ в** > **В новом окне редактора запросов**.</span><span class="sxs-lookup"><span data-stu-id="7bda0-121">Right-click **##MS_SSISServerCleanupJobLogin##**, and then click **Script Login as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
5.  <span data-ttu-id="7bda0-122">Если планируется восстановление базы данных SSISDB из копии на экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , где каталог SSISDB еще не создан, создайте скрипт CREATE PROCEDURE для sp_ssis_startup следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7bda0-122">If you will be restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, generate the CREATE PROCEDURE script for sp_ssis_startup, by doing the following.</span></span> <span data-ttu-id="7bda0-123">Дополнительные сведения см. в статье [CREATE PROCEDURE (Transact-SQL)](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7bda0-123">For more information, see [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span>  
  
    1.  <span data-ttu-id="7bda0-124">В обозревателе объектов разверните узел **базы данных** , а затем узел **системные базы данных**  >  **главные**  >  **Программируемые**  >  **хранимые процедуры** .</span><span class="sxs-lookup"><span data-stu-id="7bda0-124">In Object Explorer, expand the **Databases** node and then expand the **System Databases** > **master** > **Programmability** > **Stored Procedures** node.</span></span>  
  
    2.  <span data-ttu-id="7bda0-125">Щелкните правой кнопкой мыши **dbo.sp_ssis_startup**и выберите **Внести в скрипт хранимые процедуры как** > **СОЗДАТЬ в** > **В новом окне редактора запросов**.</span><span class="sxs-lookup"><span data-stu-id="7bda0-125">Right click **dbo.sp_ssis_startup**, and then click **Script Stored Procedure as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
6.  <span data-ttu-id="7bda0-126">Убедитесь, что агент SQL Server запущен.</span><span class="sxs-lookup"><span data-stu-id="7bda0-126">Confirm that SQL Server Agent has been started</span></span>  
  
7.  <span data-ttu-id="7bda0-127">Если планируется восстановление базы данных SSISDB из копии на экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , где каталог SSISDB еще не создан, создайте скрипт для задания обслуживания сервера SSIS следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7bda0-127">If you will be restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, generate a script for the SSIS Server Maintenance Job by doing the following.</span></span> <span data-ttu-id="7bda0-128">Скрипт создается в агенте [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] автоматически при создании каталога SSISDB.</span><span class="sxs-lookup"><span data-stu-id="7bda0-128">The script is created in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent automatically when the SSISDB catalog is created.</span></span> <span data-ttu-id="7bda0-129">Задание помогает очистить журналы операции с вышедшим сроком сохранения и удалить старые версии проектов.</span><span class="sxs-lookup"><span data-stu-id="7bda0-129">The job helps clean up cleanup operation logs outside the retention window and remove older versions of projects.</span></span>  
  
    1.  <span data-ttu-id="7bda0-130">В обозревателе объектов разверните узел **Агент SQL Server** , а затем узел **Задания** .</span><span class="sxs-lookup"><span data-stu-id="7bda0-130">In Object Explorer, expand the **SQL Server Agent** node and then expand the **Jobs** node.</span></span>  
  
    2.  <span data-ttu-id="7bda0-131">Щелкните правой кнопкой мыши задание обслуживания сервера SSIS, а затем выберите создать **Скрипт**  >  **для задания в**  >  **новом окне редактора запросов**.</span><span class="sxs-lookup"><span data-stu-id="7bda0-131">Right click SSIS Server Maintenance Job, and then click **Script Job as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
### <a name="to-restore-the-ssis-database"></a><span data-ttu-id="7bda0-132">Восстановление базы данных служб SSIS</span><span class="sxs-lookup"><span data-stu-id="7bda0-132">To Restore the SSIS Database</span></span>  
  
1.  <span data-ttu-id="7bda0-133">Если база данных SSISDB восстанавливается из копии в экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], где каталог SSISDB никогда не создавался, включите среду CLR с помощью хранимой процедуры sp_configure.</span><span class="sxs-lookup"><span data-stu-id="7bda0-133">If you are restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, enable common language runtime (clr) by running the sp_configure stored procedure.</span></span> <span data-ttu-id="7bda0-134">Дополнительные сведения см. в разделах [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) и [Параметр clr enabled](https://go.microsoft.com/fwlink/?LinkId=231855).</span><span class="sxs-lookup"><span data-stu-id="7bda0-134">For more information, see [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) and [clr enabled Option](https://go.microsoft.com/fwlink/?LinkId=231855).</span></span>  
  
    ```  
    use master   
           sp_configure 'clr enabled', 1  
           reconfigure  
  
    ```  
  
2.  <span data-ttu-id="7bda0-135">Если база данных SSISDB восстанавливается из копии на экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , где каталог SSISDB никогда не создавался, создайте асимметричный ключ и имя входа из асимметричного ключа и предоставьте разрешение UNSAFE для имени входа.</span><span class="sxs-lookup"><span data-stu-id="7bda0-135">If you are restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, create the asymmetric key and the login from the asymmetric key, and grant UNSAFE permission to the login.</span></span>  
  
    ```  
    Create Asymmetric key MS_SQLEnableSystemAssemblyLoadingKey  
           FROM Executable File = 'C:\Program Files\Microsoft SQL Server\110\DTS\Binn\Microsoft.SqlServer.IntegrationServices.Server.dll'  
  
    ```  
  
     [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="7bda0-136">требуют предоставления разрешения UNSAFE для имени входа, поскольку имени входа необходим дополнительный доступ к ресурсам, на которые существуют ограничения, например API-интерфейс Microsoft Win32.</span><span class="sxs-lookup"><span data-stu-id="7bda0-136">CLR stored procedures require UNSAFE permissions to be granted to the login because the login requires additional access to restricted resources, such as the Microsoft Win32 API.</span></span> <span data-ttu-id="7bda0-137">Дополнительные сведения о коде разрешения UNSAFE см. в разделе [Creating an Assembly](../relational-databases/clr-integration/assemblies/creating-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="7bda0-137">For more information about the UNSAFE code permission, see [Creating an Assembly](../relational-databases/clr-integration/assemblies/creating-an-assembly.md).</span></span>  
  
    ```  
    Create Login MS_SQLEnableSystemAssemblyLoadingUser  
           FROM Asymmetric key MS_SQLEnableSystemAssemblyLoadingKey   
  
           Grant unsafe Assembly to MS_SQLEnableSystemAssemblyLoadingUser  
  
    ```  
  
3.  <span data-ttu-id="7bda0-138">Восстановите базу данных SSISDB из резервной копии с помощью диалогового окна **Восстановление базы данных** в [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bda0-138">Restore the SSISDB database from the backup by using the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="7bda0-139">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="7bda0-139">For more information, see the following topics.</span></span>  
  
    -   [<span data-ttu-id="7bda0-140">Восстановление базы данных (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="7bda0-140">Restore Database &#40;General Page&#41;</span></span>](general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="7bda0-141">Восстановление базы данных (страница "Файлы")</span><span class="sxs-lookup"><span data-stu-id="7bda0-141">Restore Database &#40;Files Page&#41;</span></span>](../relational-databases/backup-restore/restore-database-files-page.md)  
  
    -   [<span data-ttu-id="7bda0-142">Восстановление базы данных (страница "Параметры")</span><span class="sxs-lookup"><span data-stu-id="7bda0-142">Restore Database &#40;Options Page&#41;</span></span>](../relational-databases/backup-restore/restore-database-options-page.md)  
  
4.  <span data-ttu-id="7bda0-143">Выполните скрипт, созданный в разделе [Создание резервной копии базы данных служб SSIS](#backup) для ##MS_SSISServerCleanupJobLogin##, sp_ssis_startup и заданий по обслуживанию служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="7bda0-143">Execute the scripts that you created in the [To Back up the SSIS Database](#backup) for ##MS_SSISServerCleanupJobLogin##, sp_ssis_startup, and SSIS Server Maintenance Job.</span></span> <span data-ttu-id="7bda0-144">Убедитесь, что агент SQL Server запущен.</span><span class="sxs-lookup"><span data-stu-id="7bda0-144">Confirm that SQL Server Agent has been started.</span></span>  
  
5.  <span data-ttu-id="7bda0-145">Выполните следующую инструкцию для установки автоматического выполнения процедуры sp_ssis_startup.</span><span class="sxs-lookup"><span data-stu-id="7bda0-145">Run the following statement to set the sp_ssis_startup prodecure for autoexecution.</span></span> <span data-ttu-id="7bda0-146">Дополнительные сведения см. в разделе [sp_procoption (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7bda0-146">For more information, see [sp_procoption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql).</span></span>  
  
    ```  
    EXEC sp_procoption N'sp_ssis_startup','startup','on'  
    ```  
  
6.  <span data-ttu-id="7bda0-147">Сопоставьте пользователя SSISDB ##MS_SSISServerCleanupJobUser## (база данных SSISDB) с ##MS_SSISServerCleanupJobLogin## с помощью диалогового окна **Свойства имени входа** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bda0-147">Map the SSISDB user ##MS_SSISServerCleanupJobUser## (SSISDB database) to ##MS_SSISServerCleanupJobLogin##, by using the **Login Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
7.  <span data-ttu-id="7bda0-148">Восстановите главный ключ с помощью одного из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="7bda0-148">Restore the master key by using one of the following methods.</span></span> <span data-ttu-id="7bda0-149">Дополнительные сведения о шифровании см. в разделе [Encryption Hierarchy](../relational-databases/security/encryption/encryption-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="7bda0-149">For more information about encryption, see [Encryption Hierarchy](../relational-databases/security/encryption/encryption-hierarchy.md).</span></span>  
  
    -   <span data-ttu-id="7bda0-150">**Метод 1**</span><span class="sxs-lookup"><span data-stu-id="7bda0-150">**Method 1**</span></span>  
  
         <span data-ttu-id="7bda0-151">Используйте этот метод при наличии резервной копии главного ключа базы данных и пароля, используемого для шифрования этого ключа.</span><span class="sxs-lookup"><span data-stu-id="7bda0-151">Use this method if you've already performed a backup of the database master key, and you have the password used to encrypt the master key.</span></span>  
  
        ```  
               Restore master key from file = 'c:\temp\RCTestInstKey'  
               Decryption by password = 'LS2Setup!' -- 'Password used to encrypt the master key during SSISDB backup'  
               Encryption by password = 'LS3Setup!' -- 'New Password'  
               Force  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="7bda0-152">Убедитесь, что учетная запись службы [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] имеет разрешения на чтение файла резервной копии ключа.</span><span class="sxs-lookup"><span data-stu-id="7bda0-152">Confirm that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service account has permissions to read the backup key file.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="7bda0-153">Если главный ключ базы данных еще не зашифрован главным ключом сервера, то в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] отобразится следующее предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="7bda0-153">You will see the following warning message displayed in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] if the database master key has not yet been encrypted by the service master key.</span></span> <span data-ttu-id="7bda0-154">Пропустите это предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="7bda0-154">Ignore the warning message.</span></span>  
        >   
        >  <span data-ttu-id="7bda0-155">**Не удается расшифровать текущий главный ключ. Ошибка пропущена, так как задан параметр FORCE.**</span><span class="sxs-lookup"><span data-stu-id="7bda0-155">**The current master key cannot be decrypted. The error was ignored because the FORCE option was specified.**</span></span>  
        >   
        >  <span data-ttu-id="7bda0-156">Аргумент FORCE указывает, что следует продолжить процесс восстановления, даже если текущий главный ключ базы данных закрыт.</span><span class="sxs-lookup"><span data-stu-id="7bda0-156">The FORCE argument specifies that the restore process should continue even if the current database master key is not open.</span></span> <span data-ttu-id="7bda0-157">Для каталога SSISDB это сообщение будет отображаться, поскольку главный ключ базы данных не является открытым в экземпляре, где осуществляется восстановление базы данных.</span><span class="sxs-lookup"><span data-stu-id="7bda0-157">For the SSISDB catalog, because the database master key has not been opened on the instance where you are restoring the database, you will see this message.</span></span>  
  
    -   <span data-ttu-id="7bda0-158">**Метод 2.**</span><span class="sxs-lookup"><span data-stu-id="7bda0-158">**Method 2**</span></span>  
  
         <span data-ttu-id="7bda0-159">Этот метод следует использовать при наличии исходного пароля, который использовался для создания SSISDB.</span><span class="sxs-lookup"><span data-stu-id="7bda0-159">Use this method if you have the original password that was used to create SSISDB.</span></span>  
  
        ```  
        open master key decryption by password = 'LS1Setup!' --'Password used when creating SSISDB'  
               Alter Master Key Add encryption by Service Master Key  
        ```  
  
8.  <span data-ttu-id="7bda0-160">Определите, совместимы ли схема каталога SSISDB и двоичные файлы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] (сборка ISServerExec и SQLCLR), запустив [catalog.check_schema_version](/sql/integration-services/system-stored-procedures/catalog-check-schema-version).</span><span class="sxs-lookup"><span data-stu-id="7bda0-160">Determine whether the SSISDB catalog schema and the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] binaries (ISServerExec and SQLCLR assembly) are compatible, by running [catalog.check_schema_version](/sql/integration-services/system-stored-procedures/catalog-check-schema-version).</span></span>  
  
9. <span data-ttu-id="7bda0-161">Для подтверждения того, что база данных SSISDB успешно восстановлена, выполните такие операции с каталогом SSISDB, как запуск пакетов, развернутых на сервере [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bda0-161">To confirm that the SSISDB database has been restored successfully, perform operations against the SSISDB catalog such as running packages that have been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="7bda0-162">Дополнительные сведения см. разделе [Выполнение пакета на сервере служб SSIS с использованием среды SQL Server Management Studio](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="7bda0-162">For more information, see [Run a Package on the SSIS Server Using SQL Server Management Studio](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md).</span></span>  
  
### <a name="to-move-the-ssis-database"></a><span data-ttu-id="7bda0-163">Перемещение базы данных служб SSIS</span><span class="sxs-lookup"><span data-stu-id="7bda0-163">To Move the SSIS Database</span></span>  
  
-   <span data-ttu-id="7bda0-164">Следуйте инструкциям по перемещению пользовательских баз данных.</span><span class="sxs-lookup"><span data-stu-id="7bda0-164">Follow the instructions for moving user databases.</span></span> <span data-ttu-id="7bda0-165">Дополнительные сведения см. в статье [Move User Databases](../relational-databases/databases/move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7bda0-165">For more information, see [Move User Databases](../relational-databases/databases/move-user-databases.md).</span></span>  
  
     <span data-ttu-id="7bda0-166">Обязательно создайте резервную копию главного ключа базы данных SSISDB и защитите файл резервной копии.</span><span class="sxs-lookup"><span data-stu-id="7bda0-166">Ensure that you back up the master key for the SSISDB database and protect the backup file.</span></span> <span data-ttu-id="7bda0-167">Дополнительные сведения см. в статье [Создание резервной копии каталога SSISDB](#backup).</span><span class="sxs-lookup"><span data-stu-id="7bda0-167">For more information, see [To Back up the SSIS Database](#backup).</span></span>  
  
     <span data-ttu-id="7bda0-168">Убедитесь, что соответствующие объекты служб Integration Services (SSIS) созданы в новом экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , где каталог SSISDB еще не был создан.</span><span class="sxs-lookup"><span data-stu-id="7bda0-168">Ensure that the Integration Services (SSIS) relevant objects are created in the new [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog has not yet been created.</span></span>  
  
  
