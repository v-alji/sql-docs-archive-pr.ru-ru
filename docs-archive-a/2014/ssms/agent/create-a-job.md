---
title: Создание задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], creating
- SQL Server Agent jobs, creating
ms.assetid: b35af2b6-6594-40d1-9861-4d5dd906048c
author: stevestein
ms.author: sstein
ms.openlocfilehash: de74f032924fbb0b6643bd8f3d482481ffb1f983
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654734"
---
# <a name="create-a-job"></a><span data-ttu-id="fb54a-102">Создание задания</span><span class="sxs-lookup"><span data-stu-id="fb54a-102">Create a Job</span></span>
  <span data-ttu-id="fb54a-103">В этом разделе описывается создание задания агента SQL Server в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющих объектов SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="fb54a-103">This topic describes how to create a SQL Server Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="fb54a-104">Чтобы добавить шаги заданий, расписаний, предупреждений и уведомлений, которые можно отправить операторам, см. ссылки на разделы руководства.</span><span class="sxs-lookup"><span data-stu-id="fb54a-104">To add job steps, schedules, alerts, and notifications that can be sent to operators, see the links to topics in the See Also section.</span></span>  
  
-   <span data-ttu-id="fb54a-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="fb54a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fb54a-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="fb54a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="fb54a-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="fb54a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fb54a-108">**Для создания задания используется**</span><span class="sxs-lookup"><span data-stu-id="fb54a-108">**To create a job, using:**</span></span>  
  
     <span data-ttu-id="fb54a-109">[SQL Server Management Studio](#SSMSProcedure),</span><span class="sxs-lookup"><span data-stu-id="fb54a-109">[SQL Server Management Studio](#SSMSProcedure),</span></span>  
  
     [<span data-ttu-id="fb54a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb54a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="fb54a-111">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb54a-111">SQL Server Management Objects</span></span>](#SMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fb54a-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="fb54a-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fb54a-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="fb54a-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="fb54a-114">Чтобы создать задание, пользователь должен быть членом одной из предопределенных ролей базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="fb54a-114">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="fb54a-115">Задание может быть изменено его владельцем или членом роли **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="fb54a-115">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="fb54a-116">Дополнительные сведения о предопределенных ролях базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Предопределенные роли базы данных агента SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fb54a-116">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
-   <span data-ttu-id="fb54a-117">Назначение задания другому имени входа не гарантирует того, что новый владелец обладает достаточными разрешениями для успешного запуска задания.</span><span class="sxs-lookup"><span data-stu-id="fb54a-117">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
-   <span data-ttu-id="fb54a-118">Локальные задания кэшируются локальным агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ,</span><span class="sxs-lookup"><span data-stu-id="fb54a-118">Local jobs are cached by the local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="fb54a-119">поэтому внесение в задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] любых изменений неявно вызывает его повторное кэширование.</span><span class="sxs-lookup"><span data-stu-id="fb54a-119">Therefore, any modifications implicitly force [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to re-cache the job.</span></span> <span data-ttu-id="fb54a-120">Поскольку агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не помещает задание в кэш до вызова процедуры **sp_add_jobserver** , эффективнее вызывать процедуру **sp_add_jobserver** последней.</span><span class="sxs-lookup"><span data-stu-id="fb54a-120">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent does not cache the job until **sp_add_jobserver** is called, it is more efficient to call **sp_add_jobserver** last.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fb54a-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="fb54a-121">Security</span></span>  
  
-   <span data-ttu-id="fb54a-122">Чтобы изменить владельца задания, необходимо быть системным администратором.</span><span class="sxs-lookup"><span data-stu-id="fb54a-122">You must be a system administrator to change the owner of a job.</span></span>  
  
-   <span data-ttu-id="fb54a-123">Из соображений безопасности изменять определение задания может только его владелец или член роли **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="fb54a-123">For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job.</span></span> <span data-ttu-id="fb54a-124">Только члены предопределенной роли сервера **sysadmin** могут предоставлять права владения заданием другим пользователям, а также могут запускать любое задание, независимо от того, кто является его владельцем.</span><span class="sxs-lookup"><span data-stu-id="fb54a-124">Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fb54a-125">Если задать в качестве нового владельца задания пользователя, не являющегося членом предопределенной роли сервера **sysadmin** , а задание выполняет шаги, которым требуются учетные записи-посредники (например, выполнение пакета служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] ), убедитесь в том, что пользователь имеет доступ к этой учетной записи-посреднику, в противном случае задание завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="fb54a-125">If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fb54a-126">Permissions</span><span class="sxs-lookup"><span data-stu-id="fb54a-126">Permissions</span></span>  
 <span data-ttu-id="fb54a-127">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="fb54a-127">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fb54a-128">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fb54a-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="fb54a-129">Создание задания агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb54a-129">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="fb54a-130">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, на котором нужно создать задание агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fb54a-130">In the **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent job.</span></span>  
  
2.  <span data-ttu-id="fb54a-131">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="fb54a-131">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="fb54a-132">Щелкните правой кнопкой мыши папку **Задания** и выберите пункт **Создать задание…**.</span><span class="sxs-lookup"><span data-stu-id="fb54a-132">Right-click the **Jobs** folder and select **New Job...**.</span></span>  
  
4.  <span data-ttu-id="fb54a-133">На странице **Общие** в диалоговом окне **Создание задания** измените общие свойства задания.</span><span class="sxs-lookup"><span data-stu-id="fb54a-133">In the **New Job** dialog box, on the **General** page, modify the general properties of the job.</span></span> <span data-ttu-id="fb54a-134">Дополнительные сведения о параметрах, доступных на этой странице, см. в разделе [Свойства задания и создание задания &#40;Общие страницы&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span><span class="sxs-lookup"><span data-stu-id="fb54a-134">For more information on the available options on this page, see [Job Properties and New Job &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span></span>  
  
5.  <span data-ttu-id="fb54a-135">На странице **Действия** задайте шаги задания.</span><span class="sxs-lookup"><span data-stu-id="fb54a-135">On the **Steps** page, organize the job steps.</span></span> <span data-ttu-id="fb54a-136">Дополнительные сведения о параметрах, доступных на этой странице, см [. в разделе Свойства задания: страница "Создание задания &#40;шаги"&#41;](job-properties-new-job-steps-page.md)</span><span class="sxs-lookup"><span data-stu-id="fb54a-136">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](job-properties-new-job-steps-page.md)</span></span>  
  
6.  <span data-ttu-id="fb54a-137">На странице **Расписания** задайте расписания для задания.</span><span class="sxs-lookup"><span data-stu-id="fb54a-137">On the **Schedules** page, organize schedules for the job.</span></span> <span data-ttu-id="fb54a-138">Дополнительные сведения о параметрах, доступных на этой странице, см [. в разделе Свойства задания: создание задания &#40;расписания&#41;](job-properties-new-job-schedules-page.md)</span><span class="sxs-lookup"><span data-stu-id="fb54a-138">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md)</span></span>  
  
7.  <span data-ttu-id="fb54a-139">На странице **Предупреждения** задайте предупреждения для задания.</span><span class="sxs-lookup"><span data-stu-id="fb54a-139">On the **Alerts** page, organize the alerts for the job.</span></span> <span data-ttu-id="fb54a-140">Дополнительные сведения о параметрах, доступных на этой странице, см [. в разделе Свойства задания: создание &#40;оповещений о задании&#41;](job-properties-new-job-alerts-page.md)</span><span class="sxs-lookup"><span data-stu-id="fb54a-140">For more information on the available options on this page, see [Job Properties: New Job &#40;Alerts Page&#41;](job-properties-new-job-alerts-page.md)</span></span>  
  
8.  <span data-ttu-id="fb54a-141">На странице **Уведомления** задайте действия, которые должен выполнять агент [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] после завершения задания.</span><span class="sxs-lookup"><span data-stu-id="fb54a-141">On the **Notifications** page, set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span> <span data-ttu-id="fb54a-142">Дополнительные сведения о параметрах, доступных на этой странице, см. в разделе [Свойства задания: создание &#40;уведомлений&#41;странице "сведения о ](job-properties-new-job-notifications-page.md)задании".</span><span class="sxs-lookup"><span data-stu-id="fb54a-142">For more information on the available options on this page, see [Job Properties: New Job &#40;Notifications Page&#41;](job-properties-new-job-notifications-page.md).</span></span>  
  
9. <span data-ttu-id="fb54a-143">Страница **Цели** используется для управления целевыми серверами в задании.</span><span class="sxs-lookup"><span data-stu-id="fb54a-143">On the **Targets** page, manage the target servers for the job.</span></span> <span data-ttu-id="fb54a-144">Дополнительные сведения о параметрах, доступных на этой странице, см. в разделе [Свойства задания: страница создание &#40;целевые объекты задания&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="fb54a-144">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
10. <span data-ttu-id="fb54a-145">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fb54a-145">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fb54a-146">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb54a-146">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="fb54a-147">Создание задания агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb54a-147">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="fb54a-148">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb54a-148">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fb54a-149">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="fb54a-149">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fb54a-150">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="fb54a-150">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_job  
        @job_name = N'Weekly Sales Data Backup' ;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
    USE msdb ;  
    GO  
    EXEC sp_attach_schedule  
       @job_name = N'Weekly Sales Data Backup',  
       @schedule_name = N'RunOnce';  
    GO  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Data Backup';  
    GO  
    ```  
  
 <span data-ttu-id="fb54a-151">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="fb54a-151">For more information, see:</span></span>  
  
-   [<span data-ttu-id="fb54a-152">sp_add_job (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fb54a-152">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="fb54a-153">sp_add_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fb54a-153">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="fb54a-154">sp_add_schedule (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fb54a-154">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="fb54a-155">sp_attach_schedule (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fb54a-155">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="fb54a-156">sp_add_jobserver &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fb54a-156">sp_add_jobserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMOProcedure"></a><span data-ttu-id="fb54a-157">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb54a-157">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="fb54a-158">**Создание задания агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="fb54a-158">**To create a SQL Server Agent job**</span></span>  
  
 <span data-ttu-id="fb54a-159">Вызовите метод `Create` класса `Job` на языке программирования по своему выбору (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="fb54a-159">Call the `Create` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="fb54a-160">Пример кода см. в разделе [Планирование автоматических административных задач в агенте SQL Server](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="fb54a-160">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
  
##  <a name="SSMSProc2"></a>  
