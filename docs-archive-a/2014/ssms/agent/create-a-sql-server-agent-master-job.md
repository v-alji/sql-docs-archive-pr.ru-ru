---
title: Создание задания агента главного сервера SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 04/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], master jobs
- jobs [SQL Server Agent], creating
- master SQL Server Agent job [SQL Server]
ms.assetid: c12ab23f-d7ee-43a5-8cd2-0a9121292bcd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8a6503caec3f153878e360ee29ce09a5c099ade5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732250"
---
# <a name="create-a-sql-server-agent-master-job"></a><span data-ttu-id="2a1d1-102">Создание задания агента главного сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="2a1d1-102">Create a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="2a1d1-103">В этом разделе описывается создание [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] задания главного агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a1d1-103">This topic describes how to create a master [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2a1d1-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2a1d1-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2a1d1-105">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2a1d1-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2a1d1-106">Изменения задания агента главного сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должны распространяться на все связанные целевые серверы.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-106">Changes to master [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs must be propagated to all involved target servers.</span></span> <span data-ttu-id="2a1d1-107">Так как целевые серверы изначально не загружают задание, пока не указаны их цели, [!INCLUDE[msCoName](../../includes/msconame-md.md)] рекомендует завершить все шаги и расписания индивидуального задания перед указанием каких-либо целевых серверов.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-107">Because target servers do not initially download a job until those targets are specified, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you complete all job steps and job schedules for a particular job before you specify any target servers.</span></span> <span data-ttu-id="2a1d1-108">Иначе необходимо будет вручную запросить повторное скачивание измененного задания целевыми серверами либо с помощью хранимой процедуры **sp_post_msx_operation** , либо путем изменения задания в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a1d1-108">Otherwise, you must manual request that the target servers download the modified job again, either by executing the **sp_post_msx_operation** stored procedure or modifying the job using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2a1d1-109">Дополнительные сведения см. в разделе [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) или [Изменение задания](modify-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="2a1d1-109">For more information, see [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) or [Modify a Job](modify-a-job.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2a1d1-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="2a1d1-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2a1d1-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="2a1d1-111">Permissions</span></span>  
 <span data-ttu-id="2a1d1-112">Распределенные задания, имеющие связанные с учетной записью-посредником шаги, выполняются в контексте учетной записи-посредника на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-112">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="2a1d1-113">Убедитесь в том, что выполняются нижеприведенные условия, либо в том, что шаги заданий, связанные с учетной записью-посредником, не будут загружаться с главного сервера на целевой:</span><span class="sxs-lookup"><span data-stu-id="2a1d1-113">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="2a1d1-114">В подразделе реестра **\ HKEY_LOCAL_MACHINE \софтваре\микрософт\микрософт SQL Server \\ < *instance_name*> \SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) установлено значение 1 (true).</span><span class="sxs-lookup"><span data-stu-id="2a1d1-114">The registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="2a1d1-115">По умолчанию для него задается значение 0 (false).</span><span class="sxs-lookup"><span data-stu-id="2a1d1-115">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="2a1d1-116">На целевом сервере есть учетная запись-посредник. Ее имя совпадает с именем учетной записи-посредника на главном сервере, под которой выполняется шаг задания.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-116">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="2a1d1-117">Если шаги задания, использующие учетную запись-посредник, завершаются с ошибками при скачивании с главного сервера на целевой, то в столбце **error_message** в таблице **sysdownloadlist** базы данных **msdb** появятся следующие сообщения об ошибках:</span><span class="sxs-lookup"><span data-stu-id="2a1d1-117">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="2a1d1-118">«Для этого шага задания необходима учетная запись-посредник, однако проверка совпадения учетной записи-посредника на целевом сервере отключена.»</span><span class="sxs-lookup"><span data-stu-id="2a1d1-118">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span> <span data-ttu-id="2a1d1-119">Чтобы устранить эту ошибку, задайте для раздела реестра **AllowDownloadedJobsToMatchProxyName** значение 1.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-119">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="2a1d1-120">«Учетная запись-посредник не найдена.»</span><span class="sxs-lookup"><span data-stu-id="2a1d1-120">"Proxy not found."</span></span> <span data-ttu-id="2a1d1-121">Чтобы устранить эту ошибку, убедитесь, что на целевом сервере есть учетная запись-посредник, имя которой совпадает с именем посреднической учетной записи на главном сервере, под которой выполняется шаг задания.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-121">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2a1d1-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2a1d1-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-master-sql-server-agent-job"></a><span data-ttu-id="2a1d1-123">Создание задания агента главного сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="2a1d1-123">To create a master SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="2a1d1-124">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, на котором нужно создать задание агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-124">In the **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent job.</span></span>  
  
2.  <span data-ttu-id="2a1d1-125">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="2a1d1-126">Щелкните правой кнопкой мыши папку **Задания** и выберите пункт **Создать задание…**.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-126">Right-click the **Jobs** folder and select **New Job...**.</span></span>  
  
4.  <span data-ttu-id="2a1d1-127">На странице **Общие** в диалоговом окне **Создание задания** измените общие свойства задания.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-127">In the **New Job** dialog box, on the **General** page, modify the general properties of the job.</span></span> <span data-ttu-id="2a1d1-128">Дополнительные сведения о параметрах, доступных на этой странице, см. в разделе [Свойства задания и создание задания &#40;Общие страницы&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span><span class="sxs-lookup"><span data-stu-id="2a1d1-128">For more information on the available options on this page, see [Job Properties and New Job &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span></span>  
  
5.  <span data-ttu-id="2a1d1-129">На странице **Действия** задайте шаги задания.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-129">On the **Steps** page, organize the job steps.</span></span> <span data-ttu-id="2a1d1-130">Дополнительные сведения о параметрах, доступных на этой странице, см [. в разделе Свойства задания: страница "Создание задания &#40;шаги"&#41;](job-properties-new-job-steps-page.md)</span><span class="sxs-lookup"><span data-stu-id="2a1d1-130">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](job-properties-new-job-steps-page.md)</span></span>  
  
6.  <span data-ttu-id="2a1d1-131">На странице **Расписания** задайте расписания для задания.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-131">On the **Schedules** page, organize schedules for the job.</span></span> <span data-ttu-id="2a1d1-132">Дополнительные сведения о параметрах, доступных на этой странице, см [. в разделе Свойства задания: создание задания &#40;расписания&#41;](job-properties-new-job-schedules-page.md)</span><span class="sxs-lookup"><span data-stu-id="2a1d1-132">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md)</span></span>  
  
7.  <span data-ttu-id="2a1d1-133">На странице **Предупреждения** задайте предупреждения для задания.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-133">On the **Alerts** page, organize the alerts for the job.</span></span> <span data-ttu-id="2a1d1-134">Дополнительные сведения о параметрах, доступных на этой странице, см [. в разделе Свойства задания: создание &#40;оповещений о задании&#41;](job-properties-new-job-alerts-page.md)</span><span class="sxs-lookup"><span data-stu-id="2a1d1-134">For more information on the available options on this page, see [Job Properties: New Job &#40;Alerts Page&#41;](job-properties-new-job-alerts-page.md)</span></span>  
  
8.  <span data-ttu-id="2a1d1-135">На странице **Уведомления** задайте действия, которые должен выполнять агент [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] после завершения задания.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-135">On the **Notifications** page, set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span> <span data-ttu-id="2a1d1-136">Дополнительные сведения о параметрах, доступных на этой странице, см. в разделе [Свойства задания: создание &#40;уведомлений&#41;странице "сведения о ](job-properties-new-job-notifications-page.md)задании".</span><span class="sxs-lookup"><span data-stu-id="2a1d1-136">For more information on the available options on this page, see [Job Properties: New Job &#40;Notifications Page&#41;](job-properties-new-job-notifications-page.md).</span></span>  
  
9. <span data-ttu-id="2a1d1-137">Страница **Цели** используется для управления целевыми серверами в задании.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-137">On the **Targets** page, manage the target servers for the job.</span></span> <span data-ttu-id="2a1d1-138">Дополнительные сведения о параметрах, доступных на этой странице, см. в разделе [Свойства задания: страница создание &#40;целевые объекты задания&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="2a1d1-138">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
10. <span data-ttu-id="2a1d1-139">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-139">When finished, click **OK**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2a1d1-140">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2a1d1-140">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-master-sql-server-agent-job"></a><span data-ttu-id="2a1d1-141">Создание задания агента главного сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="2a1d1-141">To create a master SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="2a1d1-142">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a1d1-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2a1d1-143">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2a1d1-144">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2a1d1-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- Adds a new job executed by the SQLServerAgent service called 'Weekly Sales Data Backup'  
    EXEC dbo.sp_add_job  
        @job_name = N'Weekly Sales Data Backup' ;  
    GO  
    -- Adds a step (operation) to the 'Weekly Sales Data Backup' job.  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    -- Creates a schedule called RunOnce  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
    USE msdb ;  
    GO  
    -- Sets the 'RunOnce' schedule to the "Weekly Sales Data Backup' Job  
    EXEC sp_attach_schedule  
       @job_name = N'Weekly Sales Data Backup',  
       @schedule_name = N'RunOnce';  
    GO  
    -- assigns the multiserver job Weekly Sales Backups to the server SEATTLE2  
    -- assumes that SEATTLE2 is registered as a target server for the current instance.  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Data Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="2a1d1-145">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="2a1d1-145">For more information, see:</span></span>  
  
-   [<span data-ttu-id="2a1d1-146">sp_add_job (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2a1d1-146">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="2a1d1-147">sp_add_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2a1d1-147">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="2a1d1-148">sp_add_schedule (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2a1d1-148">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="2a1d1-149">sp_attach_schedule (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2a1d1-149">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="2a1d1-150">sp_add_jobserver &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2a1d1-150">sp_add_jobserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  

  
  
