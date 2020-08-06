---
title: Настройка управляемого резервного копирования SQL Server в Azure | Документация Майкрософт
ms.custom: ''
ms.date: 08/04/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 68ebb53e-d5ad-4622-af68-1e150b94516e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b9e3b86fde91028106263310aad8a1952fc041a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667741"
---
# <a name="setting-up-sql-server-managed-backup-to-azure"></a><span data-ttu-id="f6c78-102">Настройка управляемого резервного копирования SQL Server в Azure</span><span class="sxs-lookup"><span data-stu-id="f6c78-102">Setting up SQL Server Managed Backup to Azure</span></span>
  <span data-ttu-id="f6c78-103">В этот раздел входят два учебника:</span><span class="sxs-lookup"><span data-stu-id="f6c78-103">This topic includes two tutorials:</span></span>  
  
 <span data-ttu-id="f6c78-104">Настройка [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] на уровне базы данных, включение уведомлений по электронной почте и мониторинг резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f6c78-104">Set up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the database level, enable email notification, and monitor backup activity.</span></span>  
  
 <span data-ttu-id="f6c78-105">Настройка [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] на уровне экземпляра, включение уведомлений по электронной почте и мониторинг резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f6c78-105">Setting up  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the instance level, enable email notification, and monitor backup activity.</span></span>  
  
 <span data-ttu-id="f6c78-106">Руководство по настройке [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] групп доступности см. в статье [Настройка SQL Server управляемого резервного копирования в Microsoft Azure для групп доступности](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="f6c78-106">For a tutorial on setting up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for Availability Groups, see [Setting up SQL Server Managed Backup to Microsoft Azure for Availability Groups](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
## <a name="setting-up-ss_smartbackup"></a><span data-ttu-id="f6c78-107">Настройка [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6c78-107">Setting Up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]</span></span>  
  
### <a name="enable-and-configure-ss_smartbackup-for-a-database"></a><span data-ttu-id="f6c78-108">Включение и настройка [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] для базы данных</span><span class="sxs-lookup"><span data-stu-id="f6c78-108">Enable and Configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a Database</span></span>  
 <span data-ttu-id="f6c78-109">В этом учебнике приведены необходимые шаги по включению и настройке [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] для базы данных (TestDB), затем приведены шаги по включению контроля работоспособности [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6c78-109">This tutorial describes the steps necessary to enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a database (TestDB), followed by steps to enable monitoring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] health status.</span></span>  
  
 <span data-ttu-id="f6c78-110">**Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="f6c78-110">**Permissions:**</span></span>  
  
-   <span data-ttu-id="f6c78-111">Требуется членство в **db_backupoperator** роли базы данных с разрешениями **ALTER ANY CREDENTIAL** и `EXECUTE` разрешения на хранимую процедуру **sp_delete_backuphistory**.</span><span class="sxs-lookup"><span data-stu-id="f6c78-111">Requires membership in **db_backupoperator** database role, with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on **sp_delete_backuphistory**stored procedure.</span></span>  
  
-   <span data-ttu-id="f6c78-112">Требуются разрешения **SELECT** на функцию **smart_admin. fn_get_current_xevent_settings**.</span><span class="sxs-lookup"><span data-stu-id="f6c78-112">Requires **SELECT** permissions on the **smart_admin.fn_get_current_xevent_settings**function.</span></span>  
  
-   <span data-ttu-id="f6c78-113">Требуются `EXECUTE` разрешения на хранимую процедуру **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="f6c78-113">Requires `EXECUTE` permissions on the **smart_admin.sp_get_backup_diagnostics** stored procedure.</span></span> <span data-ttu-id="f6c78-114">Кроме того, необходимы разрешения `VIEW SERVER STATE`, так как процедура автоматически вызывает другие системные объекты, которым требуется это разрешение.</span><span class="sxs-lookup"><span data-stu-id="f6c78-114">In addition, it requires `VIEW SERVER STATE` permissions as it internally calls other system objects that require this permission.</span></span>  
  
-   <span data-ttu-id="f6c78-115">Требуются `EXECUTE` разрешения для `smart_admin.sp_set_instance_backup` `smart_admin.sp_backup_master_switch` хранимых процедур и.</span><span class="sxs-lookup"><span data-stu-id="f6c78-115">Requires `EXECUTE` permissions on the `smart_admin.sp_set_instance_backup` and `smart_admin.sp_backup_master_switch` stored procedures.</span></span>  


1.  <span data-ttu-id="f6c78-116">**Создайте учетную запись хранения Microsoft Azure:** Резервные копии хранятся в службе хранилища Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="f6c78-116">**Create a Microsoft Azure storage account:** The backups are stored in the Microsoft Azure storage service.</span></span> <span data-ttu-id="f6c78-117">Необходимо сначала создать учетную запись хранения Microsoft Azure, если у вас еще нет учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f6c78-117">You must first create a Microsoft Azure storage account, if you do not already have an account.</span></span>
    - <span data-ttu-id="f6c78-118">SQL Server 2014 использует страничные большие двоичные объекты, которые отличаются от блочных и добавочных BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="f6c78-118">SQL Server 2014 uses page blobs, which are different than block and append blobs.</span></span> <span data-ttu-id="f6c78-119">Поэтому необходимо создать учетную запись общего назначения, а не учетную запись BLOB-объекта.</span><span class="sxs-lookup"><span data-stu-id="f6c78-119">Therefore you must create a general purpose account, and not a blob account.</span></span> <span data-ttu-id="f6c78-120">Дополнительные сведения см. в статье [Об учетных записях хранения Azure](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span><span class="sxs-lookup"><span data-stu-id="f6c78-120">For more information, see [About Azure storage accounts](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span></span>
    - <span data-ttu-id="f6c78-121">Запишите имя учетной записи хранения и ключи доступа.</span><span class="sxs-lookup"><span data-stu-id="f6c78-121">Make a note of the storage account name, and the access keys.</span></span> <span data-ttu-id="f6c78-122">Имя учетной записи хранения и сведения о ключе доступа используются для создания учетных данных SQL.</span><span class="sxs-lookup"><span data-stu-id="f6c78-122">The storage account name and access key information is used to create a SQL Credential.</span></span> <span data-ttu-id="f6c78-123">Учетные данные SQL используются для проверки подлинности учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="f6c78-123">The SQL Credential is used to authenticate to the storage account.</span></span>  
 
2.  <span data-ttu-id="f6c78-124">**Создайте учетные данные SQL:** Создайте учетные данные SQL, используя имя учетной записи хранения в качестве удостоверения и ключ доступа к хранилищу в качестве пароля.</span><span class="sxs-lookup"><span data-stu-id="f6c78-124">**Create a SQL Credential:** Create a SQL Credential using the name of the storage account as the Identity and the storage access key as the password.</span></span>  
  
3.  <span data-ttu-id="f6c78-125">**Убедитесь, что служба Агент SQL Server запущена и работает:**  Запустите агент SQL Server, если он в данный момент не запущен.</span><span class="sxs-lookup"><span data-stu-id="f6c78-125">**Ensure SQL Server Agent service is Started and Running:**  Start SQL Server Agent if it is not currently running.</span></span>  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="f6c78-126">требует, чтобы агент SQL Server был запущен на экземпляре.</span><span class="sxs-lookup"><span data-stu-id="f6c78-126">requires SQL Server Agent to be running on the instance to perform backup operations.</span></span>  <span data-ttu-id="f6c78-127">Можно установить автоматический запуск агента SQL Server, чтобы обеспечить регулярное выполнение операций резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f6c78-127">You may want to set SQL Server Agent to run automatically to make sure that backup operations can occur regularly.</span></span>  
  
4.  <span data-ttu-id="f6c78-128">**Определение срока хранения.** Определите период хранения файлов резервной копии.</span><span class="sxs-lookup"><span data-stu-id="f6c78-128">**Determine the retention period:** Determine the retention period for the backup files.</span></span> <span data-ttu-id="f6c78-129">Срок хранения указывается в днях и может принимать значение от 1 до 30.</span><span class="sxs-lookup"><span data-stu-id="f6c78-129">The retention period is specified in days and can range from 1 to 30.</span></span>  
  
5.  <span data-ttu-id="f6c78-130">**Включить и настроить [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** запуск SQL Server Management Studio и подключение к экземпляру, где установлена база данных.</span><span class="sxs-lookup"><span data-stu-id="f6c78-130">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Start SQL Server Management Studio and connect to the instance where the database is installed.</span></span> <span data-ttu-id="f6c78-131">В окне запроса выполните приведенную ниже инструкцию, предварительно задав нужные значения имени базы данных, учетных данных SQL, срока хранения и параметров шифрования.</span><span class="sxs-lookup"><span data-stu-id="f6c78-131">From the query window run the following statement after you modify the values for the database name, SQL Credential, retention period, and encryption options per your requirements:</span></span>  
  
     <span data-ttu-id="f6c78-132">Дополнительные сведения о создании сертификата для шифрования см. в разделе Создание **резервной копии сертификата** статьи [Создание зашифрованного резервного копирования](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="f6c78-132">For more information on creating a certificate for encryption, see the **Create a Backup Certificate** step in [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
    ```  
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='TestDB'   
                    ,@retention_days=30   
                    ,@credential_name='MyCredential'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
                    ,@enable_backup=1;  
    GO  
  
    ```  
  
     [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="f6c78-133">включено на указанной базе данных.</span><span class="sxs-lookup"><span data-stu-id="f6c78-133">is now enabled on the database you specified.</span></span> <span data-ttu-id="f6c78-134">Может потребоваться до 15 минут, прежде чем начнут выполняться операции резервного копирования для базы данных.</span><span class="sxs-lookup"><span data-stu-id="f6c78-134">It may take up to 15 minutes for the backup operations on the database to start to run.</span></span>  
  
6.  <span data-ttu-id="f6c78-135">**Просмотр конфигурации расширенных событий по умолчанию.** Просмотрите параметры расширенных событий, выполнив приведенную ниже инструкцию Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="f6c78-135">**Review Extended Event Default Configuration:** Review the Extended Event settings by running the following transact-SQL statement.</span></span>  
  
    ```  
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     <span data-ttu-id="f6c78-136">Обратите внимание, что события каналов Admin, Operational и Analytical включены по умолчанию и их нельзя отключить.</span><span class="sxs-lookup"><span data-stu-id="f6c78-136">You should see that Admin, Operational, and Analytical channel events are enabled by default and cannot be disabled.</span></span> <span data-ttu-id="f6c78-137">Этого должно быть достаточно для наблюдения за событиями, требующими ручного вмешательства.</span><span class="sxs-lookup"><span data-stu-id="f6c78-137">This should be sufficient to monitor the events that require manual intervention.</span></span>  <span data-ttu-id="f6c78-138">Можно включить события отладки, но каналы отладки содержат информационные и отладочные события, которые [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] использует для обнаружения и устранения проблем.</span><span class="sxs-lookup"><span data-stu-id="f6c78-138">You can enable debug events, but the debug channels include informational and debug events that [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] uses to detect issues and solve them.</span></span> <span data-ttu-id="f6c78-139">Дополнительные сведения см. [в статье мониторинг SQL Server управляемого резервного копирования для Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="f6c78-139">For more information, see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
7.  <span data-ttu-id="f6c78-140">**Включите и настройте уведомление о состоянии работоспособности.** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] имеет хранимую процедуру, создающую задание агента для отправки по электронной почте уведомлений об ошибках или предупреждений, которые могут требовать внимания пользователя.</span><span class="sxs-lookup"><span data-stu-id="f6c78-140">**Enable and Configure Notification for Health Status:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] has a stored procedure that creates an agent job to send out e-mail notifications of errors or warnings that may require attention.</span></span> <span data-ttu-id="f6c78-141">Приведенные ниже шаги описывают процесс включения и настройки уведомлений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="f6c78-141">The following steps describe the process to enable and configure e-mail notifications:</span></span>  
  
    1.  <span data-ttu-id="f6c78-142">Настройте компонент Database Mail, если он еще не включен на экземпляре.</span><span class="sxs-lookup"><span data-stu-id="f6c78-142">Setup Database Mail if it is not already enabled on the instance.</span></span> <span data-ttu-id="f6c78-143">Дополнительные сведения см. в разделе [Configure Database Mail](../database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="f6c78-143">For more information, see [Configure Database Mail](../database-mail/configure-database-mail.md).</span></span>  
  
    2.  <span data-ttu-id="f6c78-144">Настройте уведомления агента SQL Server для использования компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="f6c78-144">Configure SQL Server Agent Notification to use Database Mail.</span></span> <span data-ttu-id="f6c78-145">Дополнительные сведения см. в статье [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="f6c78-145">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
    3.  <span data-ttu-id="f6c78-146">**Включите уведомления по электронной почте для получения ошибок и предупреждений, связанных с резервными копиями**. В окне запроса выполните следующие инструкции Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="f6c78-146">**Enable e-mail notifications to receive backup errors and warnings:** From the query window, run the following Transact-SQL statements:</span></span>  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email1;email2>'  
  
        ```  
  
         <span data-ttu-id="f6c78-147">Дополнительные сведения и полный пример скрипта см. [в разделе Monitor SQL Server управляемое резервное копирование в Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="f6c78-147">For more information, and a full sample script see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
8.  <span data-ttu-id="f6c78-148">**Просмотрите файлы резервных копий в учетной записи хранения Microsoft Azure.** Подключитесь к учетной записи хранения из SQL Server Management Studio либо с помощью портала управления Azure.</span><span class="sxs-lookup"><span data-stu-id="f6c78-148">**View backup files in the Microsoft Azure Storage Account:** Connect to the storage account from SQL Server Management Studio or the Azure Management Portal.</span></span> <span data-ttu-id="f6c78-149">Вы увидите контейнер экземпляра SQL Server, в котором размещается база данных, настроенная на использование [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6c78-149">You will see a container for the instance of SQL Server that hosts the database you configured to use [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="f6c78-150">Кроме того, можно настроить базу данных и резервное копирование журналов за 15 минут либо включить [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] для базы данных.</span><span class="sxs-lookup"><span data-stu-id="f6c78-150">You may also see a database and a log backup within 15 minutes of enabling [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the database.</span></span>  
  
9. <span data-ttu-id="f6c78-151">**Мониторинг состояния работоспособности**.  Можно вести мониторинг с помощью настроенных ранее уведомлений по электронной почте либо активно просматривать события в журнале.</span><span class="sxs-lookup"><span data-stu-id="f6c78-151">**Monitor the Health Status:**  You can monitor through e-mail notifications you configured previously, or actively monitor the events logged.</span></span> <span data-ttu-id="f6c78-152">Ниже приведены примеры инструкций Transact-SQL, которые используются для просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="f6c78-152">The following are some example Transact-SQL Statements used to view the events:</span></span>  
  
    ```  
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'  
  
    ```  
  
    ```  
    -- to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 <span data-ttu-id="f6c78-153">Шаги, описанные в этом разделе, специально предназначены для первой настройки [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f6c78-153">The steps described in this section are specifically for configuring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the first time on the database.</span></span> <span data-ttu-id="f6c78-154">Существующие конфигурации можно изменить с помощью той же системной хранимой процедуры **smart_admin. sp_set_db_backup** и укажите новые значения.</span><span class="sxs-lookup"><span data-stu-id="f6c78-154">You can modify the existing configurations using the same system stored procedure **smart_admin.sp_set_db_backup** and provide the new values.</span></span> <span data-ttu-id="f6c78-155">Дополнительные сведения см. [в разделе SQL Server управляемое резервное копирование в Microsoft Azure параметры хранения и хранения](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f6c78-155">For more information, see [SQL Server Managed Backup to Microsoft Azure - Retention and Storage Settings](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).</span></span>  
  
### <a name="enable-ss_smartbackup-for-the-instance-with-default-settings"></a><span data-ttu-id="f6c78-156">Включите [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] для экземпляра с параметрами по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f6c78-156">Enable [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the Instance with Default Settings</span></span>  
 <span data-ttu-id="f6c78-157">В этом руководстве описываются шаги по включению и настройке [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] для экземпляра «myInstance» \\ .</span><span class="sxs-lookup"><span data-stu-id="f6c78-157">This tutorial describes the steps to enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the instance, 'MyInstance',\\.</span></span> <span data-ttu-id="f6c78-158">В него входят шаги для включения мониторинга состояния работоспособности [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6c78-158">It includes steps to enable monitoring the [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] health status.</span></span>  
  
 <span data-ttu-id="f6c78-159">**Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="f6c78-159">**Permissions:**</span></span>  
  
-   <span data-ttu-id="f6c78-160">Требуется членство в **db_backupoperator** роли базы данных с разрешениями **ALTER ANY CREDENTIAL** и `EXECUTE` разрешения на хранимую процедуру **sp_delete_backuphistory**.</span><span class="sxs-lookup"><span data-stu-id="f6c78-160">Requires membership in **db_backupoperator** database role, with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on **sp_delete_backuphistory**stored procedure.</span></span>  
  
-   <span data-ttu-id="f6c78-161">Требуются разрешения **SELECT** на функцию **smart_admin. fn_get_current_xevent_settings**.</span><span class="sxs-lookup"><span data-stu-id="f6c78-161">Requires **SELECT** permissions on the **smart_admin.fn_get_current_xevent_settings**function.</span></span>  
  
-   <span data-ttu-id="f6c78-162">Требуются `EXECUTE` разрешения на хранимую процедуру **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="f6c78-162">Requires `EXECUTE` permissions on the **smart_admin.sp_get_backup_diagnostics** stored procedure.</span></span> <span data-ttu-id="f6c78-163">Кроме того, необходимы разрешения `VIEW SERVER STATE`, так как процедура автоматически вызывает другие системные объекты, которым требуется это разрешение.</span><span class="sxs-lookup"><span data-stu-id="f6c78-163">In addition, it requires `VIEW SERVER STATE` permissions as it internally calls other system objects that require this permission.</span></span>  


1.  <span data-ttu-id="f6c78-164">**Создайте учетную запись хранения Microsoft Azure:** Резервные копии хранятся в службе хранилища Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="f6c78-164">**Create a Microsoft Azure storage account:** The backups are stored in the Microsoft Azure storage service.</span></span> <span data-ttu-id="f6c78-165">Необходимо сначала создать учетную запись хранения Microsoft Azure, если у вас еще нет учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f6c78-165">You must first create a Microsoft Azure storage account, if you do not already have an account.</span></span>
    - <span data-ttu-id="f6c78-166">SQL Server 2014 использует страничные большие двоичные объекты, которые отличаются от блочных и добавочных BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="f6c78-166">SQL Server 2014 uses page blobs, which are different than block and append blobs.</span></span> <span data-ttu-id="f6c78-167">Поэтому необходимо создать учетную запись общего назначения, а не учетную запись BLOB-объекта.</span><span class="sxs-lookup"><span data-stu-id="f6c78-167">Therefore you must create a general purpose account, and not a blob account.</span></span> <span data-ttu-id="f6c78-168">Дополнительные сведения см. в статье [Об учетных записях хранения Azure](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span><span class="sxs-lookup"><span data-stu-id="f6c78-168">For more information, see [About Azure storage accounts](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span></span>
    - <span data-ttu-id="f6c78-169">Запишите имя учетной записи хранения и ключи доступа.</span><span class="sxs-lookup"><span data-stu-id="f6c78-169">Make a note of the storage account name, and the access keys.</span></span> <span data-ttu-id="f6c78-170">Имя учетной записи хранения и сведения о ключе доступа используются для создания учетных данных SQL.</span><span class="sxs-lookup"><span data-stu-id="f6c78-170">The storage account name and access key information is used to create a SQL Credential.</span></span> <span data-ttu-id="f6c78-171">Учетные данные SQL используются для проверки подлинности учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="f6c78-171">The SQL Credential is used to authenticate to the storage account.</span></span>  
  
2.  <span data-ttu-id="f6c78-172">**Создайте учетные данные SQL:** Создайте учетные данные SQL, используя имя учетной записи хранения в качестве удостоверения и ключ доступа к хранилищу в качестве пароля.</span><span class="sxs-lookup"><span data-stu-id="f6c78-172">**Create a SQL Credential:** Create a SQL Credential using the name of the storage account as the Identity and the storage access key as the password.</span></span>  
  
3.  <span data-ttu-id="f6c78-173">**Убедитесь в том, что служба агента SQL Server запущена и работает.** Запустите агент SQL Server, если он не запущен.</span><span class="sxs-lookup"><span data-stu-id="f6c78-173">**Ensure SQL Server Agent service is Started and Running:** Start SQL Server Agent if it is not currently running.</span></span> [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="f6c78-174">требует, чтобы агент SQL Server был запущен на экземпляре.</span><span class="sxs-lookup"><span data-stu-id="f6c78-174">requires SQL Server Agent to be running on the instance to perform backup operations.</span></span>  <span data-ttu-id="f6c78-175">Можно установить автоматический запуск агента SQL Server, чтобы обеспечить регулярное выполнение операций резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f6c78-175">You may want to set SQL Server Agent to run automatically to make sure that backup operations can occur regularly.</span></span>  
  
4.  <span data-ttu-id="f6c78-176">**Определение срока хранения.** Определите период хранения файлов резервной копии.</span><span class="sxs-lookup"><span data-stu-id="f6c78-176">**Determine the retention period:** Determine the retention period for the backup files.</span></span> <span data-ttu-id="f6c78-177">Срок хранения указывается в днях и может принимать значение от 1 до 30.</span><span class="sxs-lookup"><span data-stu-id="f6c78-177">The retention period is specified in days and can range from 1 to 30.</span></span> <span data-ttu-id="f6c78-178">После включения [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] на уровне экземпляра с параметрами по умолчанию все новые базы данных, созданные позднее, будут наследовать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="f6c78-178">Once [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] is enabled at the instance level with the defaults all new databases created thereafter will inherit the settings.</span></span> <span data-ttu-id="f6c78-179">Поддерживаются только базы данных, для которых установлена полная модель восстановления или модель восстановления с неполным протоколированием. Эти базы данных будут настраиваться автоматически.</span><span class="sxs-lookup"><span data-stu-id="f6c78-179">Only databases that are set to full or bulk-logged recovery models are supported and will be configured automatically.</span></span> <span data-ttu-id="f6c78-180">Можно отключить [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] для конкретной базы данных в любое время, если настройка [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] не требуется.</span><span class="sxs-lookup"><span data-stu-id="f6c78-180">You may disable [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a specific database at any time if you  do not want [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configured.</span></span> <span data-ttu-id="f6c78-181">Кроме того, можно изменить конфигурацию для отдельной базы данных, настроив [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] на уровне базы данных.</span><span class="sxs-lookup"><span data-stu-id="f6c78-181">You can also change the configuration for a specific database by configuring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the database level.</span></span>  
  
5.  <span data-ttu-id="f6c78-182">**Включить и настроить [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** запуск SQL Server Management Studio и подключение к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f6c78-182">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Start SQL Server Management Studio and connect to the instance of SQL Server.</span></span> <span data-ttu-id="f6c78-183">В окне запроса выполните приведенную ниже инструкцию, предварительно задав нужные значения имени базы данных, учетных данных SQL, срока хранения и параметров шифрования.</span><span class="sxs-lookup"><span data-stu-id="f6c78-183">From the query window run the following statement after you modify the values for the database name, SQL Credential, retention period, and the encryption options per your requirements:</span></span>  
  
     <span data-ttu-id="f6c78-184">Дополнительные сведения о создании сертификата для шифрования см. в разделе Создание **резервной копии сертификата** статьи [Создание зашифрованного резервного копирования](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="f6c78-184">For more information on creating a certificate for encryption, see the **Create a Backup Certificate** step in [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
    ```  
    Use msdb;  
    Go  
       EXEC smart_admin.sp_set_instance_backup  
                     @enable_backup=1  
                    ,@retention_days=30   
                    ,@credential_name='sqlbackuptoURL'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert';  
    GO  
  
    ```  
  
     [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="f6c78-185">теперь включен на экземпляре.</span><span class="sxs-lookup"><span data-stu-id="f6c78-185">is now enabled on the instance.</span></span>  
  
6.  <span data-ttu-id="f6c78-186">Проверьте параметры конфигурации, запустив следующую инструкцию Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="f6c78-186">Verify the configuration settings by running the following Transact-SQL statement:</span></span>  
  
    ```  
    Use msdb;  
    GO  
    SELECT * FROM smart_admin.fn_backup_instance_config ();  
  
    ```  
  
7.  <span data-ttu-id="f6c78-187">Создайте новую базу данных на экземпляре.</span><span class="sxs-lookup"><span data-stu-id="f6c78-187">Create a new database on the instance.</span></span> <span data-ttu-id="f6c78-188">Запустите следующую инструкцию Transact-SQL, чтобы просмотреть параметры конфигурации [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] для базы данных:</span><span class="sxs-lookup"><span data-stu-id="f6c78-188">Run the following Transact-SQL statement to view the [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configuration settings for the database:</span></span>  
  
    ```  
    Use msdb  
    GO  
    SELECT * FROM smart_admin.fn_backup_db_config('NewDB')  
    ```  
  
     <span data-ttu-id="f6c78-189">Может потребоваться до 15 минут, прежде чем параметры отобразятся и начнут выполняться операции резервного копирования для базы данных.</span><span class="sxs-lookup"><span data-stu-id="f6c78-189">It may take up to 15 minutes for the settings to show and backup operations on the database to start to run.</span></span>  
  
8.  <span data-ttu-id="f6c78-190">**Включите и настройте уведомление о состоянии работоспособности.** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] имеет хранимую процедуру, создающую задание агента для отправки по электронной почте уведомлений об ошибках или предупреждений, которые могут требовать внимания пользователя.</span><span class="sxs-lookup"><span data-stu-id="f6c78-190">**Enable and Configure Notification for Health Status:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] has a stored procedure that creates an agent job to send out e-mail notifications of errors or warnings that may require attention.</span></span>  <span data-ttu-id="f6c78-191">Чтобы получать такие уведомления, необходимо включить запуск хранимой процедуры, которая создает задание агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f6c78-191">To receive such notifications, you must enable run the stored procedure which creates a SQL Server Agent Job.</span></span> <span data-ttu-id="f6c78-192">Приведенные ниже шаги описывают процесс включения и настройки уведомлений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="f6c78-192">The following steps describe the process to enable and configure e-mail notifications:</span></span>  
  
    1.  <span data-ttu-id="f6c78-193">Настройте компонент Database Mail, если он еще не включен на экземпляре.</span><span class="sxs-lookup"><span data-stu-id="f6c78-193">Setup Database Mail if it is not already enabled on the instance.</span></span> <span data-ttu-id="f6c78-194">Дополнительные сведения см. в разделе [Configure Database Mail](../database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="f6c78-194">For more information, see [Configure Database Mail](../database-mail/configure-database-mail.md).</span></span>  
  
    2.  <span data-ttu-id="f6c78-195">Настройте уведомления агента SQL Server для использования компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="f6c78-195">Configure SQL Server Agent Notification to use Database Mail.</span></span> <span data-ttu-id="f6c78-196">Дополнительные сведения см. в статье [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="f6c78-196">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
    3.  <span data-ttu-id="f6c78-197">**Включите уведомления по электронной почте для получения ошибок и предупреждений, связанных с резервными копиями**. В окне запроса выполните следующие инструкции Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="f6c78-197">**Enable e-mail notifications to receive backup errors and warnings:** From the query window, run the following Transact-SQL statements:</span></span>  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email address>'  
  
        ```  
  
         <span data-ttu-id="f6c78-198">Дополнительные сведения о мониторинге и полный пример скрипта см. в разделе [monitor SQL Server управляемое резервное копирование в Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="f6c78-198">For more information about how to monitor, and a full sample script see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
9. <span data-ttu-id="f6c78-199">**Просмотрите файлы резервных копий в учетной записи хранения Microsoft Azure.** Подключитесь к учетной записи хранения из SQL Server Management Studio либо с помощью портала управления Azure.</span><span class="sxs-lookup"><span data-stu-id="f6c78-199">**View backup files in the Microsoft Azure Storage Account:** Connect to the storage account from SQL Server Management Studio or the Azure Management Portal.</span></span> <span data-ttu-id="f6c78-200">Вы увидите контейнер экземпляра SQL Server, в котором размещается база данных, настроенная на использование [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6c78-200">You will see a container for the instance of SQL Server that hosts the database you configured to use [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="f6c78-201">Кроме того, вы увидите базу данных и резервную копию журнала в течение 15 минут после создания новой базы данных.</span><span class="sxs-lookup"><span data-stu-id="f6c78-201">You may also see a database and a log backup within 15 minutes of creating a new database.</span></span>  
  
10. <span data-ttu-id="f6c78-202">**Мониторинг состояния работоспособности**.  Можно вести мониторинг с помощью настроенных ранее уведомлений по электронной почте либо активно просматривать события в журнале.</span><span class="sxs-lookup"><span data-stu-id="f6c78-202">**Monitor the Health Status:**  You can monitor through e-mail notifications you configured previously, or actively monitor the events logged.</span></span> <span data-ttu-id="f6c78-203">Ниже приведены примеры инструкций Transact-SQL, которые используются для просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="f6c78-203">The following are some example Transact-SQL Statements used to view the events:</span></span>  
  
    ```  
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'  
  
    ```  
  
    ```  
    --  to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 <span data-ttu-id="f6c78-204">Параметры [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] по умолчанию могут переопределяться для конкретной базы данных путем специальной настройки параметров на уровне базы данных.</span><span class="sxs-lookup"><span data-stu-id="f6c78-204">[!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] default settings can be overridden for a specific database by configuring the settings specifically at the database level.</span></span> <span data-ttu-id="f6c78-205">Кроме того, можно временно приостанавливать службу [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] и возобновлять ее выполнение.</span><span class="sxs-lookup"><span data-stu-id="f6c78-205">You can also pause and resume [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] service temporarily.</span></span> <span data-ttu-id="f6c78-206">Дополнительные сведения см. [в разделе SQL Server управляемое резервное копирование в Microsoft Azure-параметры хранения и хранения](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md) .</span><span class="sxs-lookup"><span data-stu-id="f6c78-206">For more information, see [SQL Server Managed Backup to Microsoft Azure - Retention and Storage Settings](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md)</span></span>  
  
  
