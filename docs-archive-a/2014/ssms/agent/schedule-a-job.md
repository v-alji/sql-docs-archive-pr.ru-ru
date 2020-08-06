---
title: Планирование задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scheduling jobs [SQL Server]
- SQL Server Agent jobs, scheduling
- jobs [SQL Server Agent], scheduling
ms.assetid: f626390a-a3df-4970-b7a7-a0529e4a109c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1077766d6853ed7c029b8eefa76515c89ad861fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731325"
---
# <a name="schedule-a-job"></a><span data-ttu-id="e1737-102">Schedule a Job</span><span class="sxs-lookup"><span data-stu-id="e1737-102">Schedule a Job</span></span>
  <span data-ttu-id="e1737-103">В этом разделе описан процесс составления расписания задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1737-103">This topic describes how to schedule a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
-   <span data-ttu-id="e1737-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="e1737-104">**Before you begin:** ,</span></span>  
  
     [<span data-ttu-id="e1737-105">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e1737-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e1737-106">**Для планирования задания используется:**</span><span class="sxs-lookup"><span data-stu-id="e1737-106">**To schedule a job, using:**</span></span>  
  
     [<span data-ttu-id="e1737-107">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e1737-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="e1737-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e1737-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="e1737-109">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="e1737-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e1737-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="e1737-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e1737-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="e1737-111">Security</span></span>  
 <span data-ttu-id="e1737-112">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e1737-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e1737-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e1737-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-and-attach-a-schedule-to-a-job"></a><span data-ttu-id="e1737-114">Создание и присоединение расписания к заданию</span><span class="sxs-lookup"><span data-stu-id="e1737-114">To create and attach a schedule to a job</span></span>  
  
1.  <span data-ttu-id="e1737-115">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="e1737-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e1737-116">Разверните узел **Агент SQL Server**, **Задания**, правой кнопкой мыши щелкните задание, для которого составляется расписание, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e1737-116">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to schedule, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e1737-117">Выберите страницу **Расписания** , затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e1737-117">Select the **Schedules** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="e1737-118">В поле **Имя** введите имя нового расписания.</span><span class="sxs-lookup"><span data-stu-id="e1737-118">In the **Name** box, type a name for the new schedule.</span></span>  
  
5.  <span data-ttu-id="e1737-119">Если расписание не должно вступать в силу немедленно после его создания, сбросьте флажок **Включено** .</span><span class="sxs-lookup"><span data-stu-id="e1737-119">Clear the **Enabled** check box if you do not want the schedule to take effect immediately following its creation.</span></span>  
  
6.  <span data-ttu-id="e1737-120">Выберите одно из следующих значений для параметра **Тип расписания**:</span><span class="sxs-lookup"><span data-stu-id="e1737-120">For **Schedule Type**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="e1737-121">Для запуска задания во время запуска службы агента **выберите элемент** Запускать автоматически при запуске агента SQL Server [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1737-121">Click **Start automatically when SQL Server Agent starts** to start the job when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is started.</span></span>  
  
    -   <span data-ttu-id="e1737-122">Для запуска задания, когда процессоры переходят в бездействующее состояние, щелкните **Запускать при бездействии процессоров** .</span><span class="sxs-lookup"><span data-stu-id="e1737-122">Click **Start whenever the CPUs become idle** to start the job when the CPUs reach an idle condition.</span></span>  
  
    -   <span data-ttu-id="e1737-123">Если необходимо составить расписание для периодического выполнения, выберите **Повторяющееся задание** .</span><span class="sxs-lookup"><span data-stu-id="e1737-123">Click **Recurring** if you want a schedule to run repeatedly.</span></span> <span data-ttu-id="e1737-124">Затем в диалоговом окне заполните группы **Частота**, **Сколько раз в день**и **Продолжительность** .</span><span class="sxs-lookup"><span data-stu-id="e1737-124">To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.</span></span>  
  
    -   <span data-ttu-id="e1737-125">Если планируется однократное выполнение, выберите **Один раз** .</span><span class="sxs-lookup"><span data-stu-id="e1737-125">Click **One time** if you want the schedule to run only once.</span></span> <span data-ttu-id="e1737-126">Для установки расписания **Один раз** заполните в диалоговом окне группу **Однократное выполнение** .</span><span class="sxs-lookup"><span data-stu-id="e1737-126">To set the **One time** schedule, complete the **One-time occurrence** group on the dialog.</span></span>  
  
#### <a name="to-attach-a-schedule-to-a-job"></a><span data-ttu-id="e1737-127">Присоединение расписания к заданию</span><span class="sxs-lookup"><span data-stu-id="e1737-127">To attach a schedule to a job</span></span>  
  
1.  <span data-ttu-id="e1737-128">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="e1737-128">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e1737-129">Разверните узел **Агент SQL Server**, **Задания**, правой кнопкой мыши щелкните задание, для которого составляется расписание, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e1737-129">Expand **SQL Server Agent**, expand **Jobs**, right-click the job that you want to schedule, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e1737-130">Выберите страницу **Расписания** и нажмите кнопку **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="e1737-130">Select the **Schedules** page, and then click **Pick**.</span></span>  
  
4.  <span data-ttu-id="e1737-131">Выберите расписание, которое нужно присоединить, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e1737-131">Select the schedule that you want to attach, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="e1737-132">В диалоговом окне **Свойства задания** дважды щелкните присоединенное расписание.</span><span class="sxs-lookup"><span data-stu-id="e1737-132">In the **Job Properties** dialog box, double-click the attached schedule.</span></span>  
  
6.  <span data-ttu-id="e1737-133">Убедитесь, что значение **Дата начала** настроено правильно.</span><span class="sxs-lookup"><span data-stu-id="e1737-133">Verify that **Start date** is set correctly.</span></span> <span data-ttu-id="e1737-134">В противном случае установите дату начала расписания и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e1737-134">If it is not, set the date when you want for the schedule to start, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="e1737-135">В диалоговом окне **Свойства задания** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e1737-135">In the **Job Properties** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="e1737-136">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e1737-136">Using Transact-SQL</span></span>  
  
#### <a name="to-schedule-a-job"></a><span data-ttu-id="e1737-137">Планирование задания</span><span class="sxs-lookup"><span data-stu-id="e1737-137">To schedule a job</span></span>  
  
1.  <span data-ttu-id="e1737-138">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1737-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e1737-139">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="e1737-139">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e1737-140">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e1737-140">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
    -- creates a schedule named NightlyJobs.   
    -- Jobs that use this schedule execute every day when the time on the server is 01:00.   
    EXEC sp_add_schedule  
        @schedule_name = N'NightlyJobs' ,  
        @freq_type = 4,  
        @freq_interval = 1,  
        @active_start_time = 010000 ;  
    GO  
    -- attaches the schedule to the job BackupDatabase  
    EXEC sp_attach_schedule  
       @job_name = N'BackupDatabase',  
       @schedule_name = N'NightlyJobs' ;  
    GO  
    ```  
  
 <span data-ttu-id="e1737-141">Дополнительные сведения см. в статьях [sp_add_schedule &#40;Transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql) и [sp_attach_schedule &#40;transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e1737-141">For more information, see [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql) and [sp_attach_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="e1737-142">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="e1737-142">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="e1737-143">Воспользуйтесь классом `JobSchedule` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="e1737-143">Use the `JobSchedule` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="e1737-144">Дополнительные сведения см. в разделе[Управляющие объекты SQL Server](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="e1737-144">For more information, see[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
