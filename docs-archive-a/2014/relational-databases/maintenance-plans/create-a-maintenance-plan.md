---
title: Создание плана обслуживания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- maintenance plans [SQL Server], creating
ms.assetid: a945cb65-ba7a-42f4-bbd9-6ec675745523
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3df0c1cd06427deb051a9c4214d03084b44c6f9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666579"
---
# <a name="create-a-maintenance-plan"></a><span data-ttu-id="d03b0-102">Создание плана обслуживания</span><span class="sxs-lookup"><span data-stu-id="d03b0-102">Create a Maintenance Plan</span></span>
  <span data-ttu-id="d03b0-103">В этом разделе описывается создание плана обслуживания одного или нескольких серверов в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d03b0-103">This topic describes how to create a single server or multiserver maintenance plan in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d03b0-104">В среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]можно создавать планы обслуживания двумя способами: с помощью мастера планов обслуживания или рабочей области конструирования.</span><span class="sxs-lookup"><span data-stu-id="d03b0-104">Using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], you can create these maintenance plans in one of two ways: by either using the Maintenance Plan Wizard or the design surface.</span></span> <span data-ttu-id="d03b0-105">Мастер лучше подходит для создания простых планов обслуживания, а конструктор позволяет использовать расширенные возможности рабочего процесса с потоком операций.</span><span class="sxs-lookup"><span data-stu-id="d03b0-105">The Wizard is best for creating basic maintenance plans, while creating a plan using the design surface allows you to utilize enhanced workflow.</span></span>  
  
 <span data-ttu-id="d03b0-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="d03b0-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d03b0-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="d03b0-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d03b0-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d03b0-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d03b0-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="d03b0-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d03b0-110">**Для создания плана обслуживания используется:**</span><span class="sxs-lookup"><span data-stu-id="d03b0-110">**To create a maintenance plan, using:**</span></span>  
  
     [<span data-ttu-id="d03b0-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d03b0-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d03b0-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d03b0-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d03b0-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="d03b0-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d03b0-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d03b0-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="d03b0-115">Для создания многосерверного плана обслуживания необходимо настроить многосерверную среду, содержащую один главный сервер и один или несколько целевых серверов.</span><span class="sxs-lookup"><span data-stu-id="d03b0-115">To create a multiserver maintenance plan, a multiserver environment containing one master server and one or more target servers must be configured.</span></span> <span data-ttu-id="d03b0-116">План многосерверного обслуживания необходимо создать и хранить на главном сервере.</span><span class="sxs-lookup"><span data-stu-id="d03b0-116">Multiserver maintenance plans must be created and maintained on the master server.</span></span> <span data-ttu-id="d03b0-117">На целевых серверах эти планы можно просматривать, но нельзя хранить.</span><span class="sxs-lookup"><span data-stu-id="d03b0-117">These plans can be viewed, but not maintained, on target servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d03b0-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="d03b0-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d03b0-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="d03b0-119">Permissions</span></span>  
 <span data-ttu-id="d03b0-120">Для создания планов обслуживания и работы с ними пользователь должен быть членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="d03b0-120">To create or manage Maintenance Plans, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d03b0-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d03b0-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-maintenance-plan-using-the-maintenance-plan-wizard"></a><span data-ttu-id="d03b0-122">Создание плана обслуживания с помощью мастера планов обслуживания</span><span class="sxs-lookup"><span data-stu-id="d03b0-122">To create a maintenance plan using the Maintenance Plan Wizard</span></span>  
  
1.  <span data-ttu-id="d03b0-123">В обозревателе объектов щелкните знак «плюс», чтобы развернуть сервер, где нужно создать план обслуживания.</span><span class="sxs-lookup"><span data-stu-id="d03b0-123">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="d03b0-124">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="d03b0-124">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="d03b0-125">Щелкните правой кнопкой мыши папку **Планы обслуживания** и выберите пункт **Мастер планов обслуживания**.</span><span class="sxs-lookup"><span data-stu-id="d03b0-125">Right-click the **Maintenance Plans** folder and select **Maintenance Plan Wizard**.</span></span>  
  
4.  <span data-ttu-id="d03b0-126">Выполните предлагаемые мастером шаги, чтобы создать план обслуживания.</span><span class="sxs-lookup"><span data-stu-id="d03b0-126">Follow the steps of the wizard to create a maintenance plan.</span></span> <span data-ttu-id="d03b0-127">Дополнительные сведения см. в статье [Use the Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d03b0-127">For more information, see [Use the Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md).</span></span>  
  
#### <a name="to-create-a-maintenance-plan-using-the-design-surface"></a><span data-ttu-id="d03b0-128">Создание планов обслуживания при помощи области конструктора</span><span class="sxs-lookup"><span data-stu-id="d03b0-128">To create a maintenance plan using the design surface</span></span>  
  
1.  <span data-ttu-id="d03b0-129">В обозревателе объектов щелкните знак «плюс», чтобы развернуть сервер, где нужно создать план обслуживания.</span><span class="sxs-lookup"><span data-stu-id="d03b0-129">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="d03b0-130">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="d03b0-130">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="d03b0-131">Щелкните правой кнопкой мыши папку **Планы обслуживания** и выберите команду **Создать план обслуживания**.</span><span class="sxs-lookup"><span data-stu-id="d03b0-131">Right-click the **Maintenance Plans** folder and select **New Maintenance Plan**.</span></span>  
  
4.  <span data-ttu-id="d03b0-132">Создайте план обслуживания, выполнив действия, описанные в разделе [Создание планов обслуживания (область конструктора планов обслуживания)](create-a-maintenance-plan-maintenance-plan-design-surface.md).</span><span class="sxs-lookup"><span data-stu-id="d03b0-132">Create a maintenance plan following the steps in [Create a Maintenance Plan &#40;Maintenance Plan Design Surface&#41;](create-a-maintenance-plan-maintenance-plan-design-surface.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d03b0-133">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d03b0-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-maintenance-plan"></a><span data-ttu-id="d03b0-134">Создание плана обслуживания</span><span class="sxs-lookup"><span data-stu-id="d03b0-134">To create a maintenance plan</span></span>  
  
1.  <span data-ttu-id="d03b0-135">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d03b0-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d03b0-136">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="d03b0-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d03b0-137">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="d03b0-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    --  Adds a new job, executed by the SQL Server Agent service, called "HistoryCleanupTask_1".  
    EXEC dbo.sp_add_job  
       @job_name = N'HistoryCleanupTask_1',   
       @enabled = 1,   
       @description = N'Clean up old task history' ;   
    GO  
    -- Adds a job step for reorganizing all of the indexes in the HumanResources.Employee table to the HistoryCleanupTask_1 job.   
    EXEC dbo.sp_add_jobstep  
        @job_name = N'HistoryCleanupTask_1',   
        @step_name = N'Reorganize all indexes on HumanResources.Employee table',   
        @subsystem = N'TSQL',   
        @command = N'USE AdventureWorks2012  
    GO  
    ALTER INDEX AK_Employee_LoginID ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX AK_Employee_NationalIDNumber ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX AK_Employee_rowguid ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX IX_Employee_OrganizationNode ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX PK_Employee_BusinessEntityID ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    ',   
        @retry_attempts = 5,   
        @retry_interval = 5 ;   
    GO  
    -- Creates a schedule named RunOnce that executes every day when the time on the server is 23:00.   
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',   
        @freq_type = 4,   
        @freq_interval = 1,   
        @active_start_time = 233000 ;   
    GO  
    -- Attaches the RunOnce schedule to the job HistoryCleanupTask_1.   
    EXEC sp_attach_schedule  
       @job_name = N'HistoryCleanupTask_1'  
       @schedule_name = N'RunOnce' ;   
    GO  
  
    ```  
  
 <span data-ttu-id="d03b0-138">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="d03b0-138">For more information, see:</span></span>  
  
-   [<span data-ttu-id="d03b0-139">sp_add_job (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d03b0-139">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="d03b0-140">sp_add_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d03b0-140">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="d03b0-141">sp_add_schedule (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d03b0-141">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="d03b0-142">sp_attach_schedule (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d03b0-142">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
  
