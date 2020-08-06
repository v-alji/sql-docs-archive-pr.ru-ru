---
title: Создание и присоединение расписаний к заданиям | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server]
- scheduling jobs [SQL Server]
- jobs [SQL Server], scheduling
- CPU [SQL Server], idle conditions
- automatic job processing
- SQL Server Agent jobs, scheduling
- idle time [SQL Server]
ms.assetid: 079c2984-0052-4a37-a2b8-4ece56e6b6b5
author: stevestein
ms.author: sstein
ms.openlocfilehash: ced47013b6552725e6350b113a3722b066016a6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731381"
---
# <a name="create-and-attach-schedules-to-jobs"></a><span data-ttu-id="232ee-102">Создание и присоединение расписаний к заданиям</span><span class="sxs-lookup"><span data-stu-id="232ee-102">Create and Attach Schedules to Jobs</span></span>
  <span data-ttu-id="232ee-103">Планирование заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предполагает определение условия или условий, при которых выполнение задания должно начаться без вмешательства пользователя.</span><span class="sxs-lookup"><span data-stu-id="232ee-103">Scheduling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs means defining the condition or conditions that cause the job to begin running without user interaction.</span></span> <span data-ttu-id="232ee-104">Можно запланировать автоматическое выполнение задания, создав новое расписание для задания или присоединив к нему существующее расписание.</span><span class="sxs-lookup"><span data-stu-id="232ee-104">You can schedule a job to run automatically by creating a new schedule for the job, or by attaching an existing schedule to the job.</span></span>  
  
 <span data-ttu-id="232ee-105">Существуют следующие два способа создания расписания.</span><span class="sxs-lookup"><span data-stu-id="232ee-105">There are two ways to create a schedule:</span></span>  
  
-   <span data-ttu-id="232ee-106">Создание расписания во время создания задания.</span><span class="sxs-lookup"><span data-stu-id="232ee-106">Create the schedule while you are creating a job.</span></span>  
  
-   <span data-ttu-id="232ee-107">Создание расписания в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="232ee-107">Create the schedule in Object Explorer.</span></span>  
  
 <span data-ttu-id="232ee-108">После создания расписания его можно присоединить к нескольким заданиям, даже если оно было создано для конкретного задания.</span><span class="sxs-lookup"><span data-stu-id="232ee-108">After a schedule has been created, you can attach that schedule to multiple jobs, even if the schedule was created for a specific job.</span></span> <span data-ttu-id="232ee-109">Можно также отсоединять расписания от заданий.</span><span class="sxs-lookup"><span data-stu-id="232ee-109">You can also detach schedules from jobs.</span></span>  
  
 <span data-ttu-id="232ee-110">Расписание может быть основано на времени или на событии.</span><span class="sxs-lookup"><span data-stu-id="232ee-110">A schedule can be based upon time or an event.</span></span> <span data-ttu-id="232ee-111">Например, можно спланировать выполнение задания при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="232ee-111">For example, you can schedule a job to run at the following times:</span></span>  
  
-   <span data-ttu-id="232ee-112">при каждом запуске агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)];</span><span class="sxs-lookup"><span data-stu-id="232ee-112">Whenever [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts.</span></span>  
  
-   <span data-ttu-id="232ee-113">каждый раз, когда использование ЦП компьютера будет достигать уровня, который определен как уровень простоя;</span><span class="sxs-lookup"><span data-stu-id="232ee-113">Whenever CPU utilization of the computer is at a level you have defined as idle.</span></span>  
  
-   <span data-ttu-id="232ee-114">однажды, в указанные дату и время;</span><span class="sxs-lookup"><span data-stu-id="232ee-114">One time, at a specific date and time.</span></span>  
  
-   <span data-ttu-id="232ee-115">Для повторяющегося расписания.</span><span class="sxs-lookup"><span data-stu-id="232ee-115">On a recurring schedule.</span></span>  
  
 <span data-ttu-id="232ee-116">В качестве альтернативы расписаниям заданий можно также создать предупреждение, отвечающее на событие выполнением задания.</span><span class="sxs-lookup"><span data-stu-id="232ee-116">As an alternative to job schedules, you can also create an alert that responds to an event by running a job.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="232ee-117">Только один экземпляр задания может выполняться в один момент времени.</span><span class="sxs-lookup"><span data-stu-id="232ee-117">Only one instance of the job can be run at a time.</span></span> <span data-ttu-id="232ee-118">При попытке вручную запустить выполнение задания в то время, как оно выполняется по расписанию, агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ответит на требование отказом.</span><span class="sxs-lookup"><span data-stu-id="232ee-118">If you try to run a job manually while it is running as scheduled, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent refuses the request.</span></span>  
  
 <span data-ttu-id="232ee-119">Чтобы запретить выполнение запланированного задания, необходимо выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="232ee-119">To prevent a scheduled job from running, you must do one of the following:</span></span>  
  
-   <span data-ttu-id="232ee-120">отключить расписание;</span><span class="sxs-lookup"><span data-stu-id="232ee-120">Disable the schedule.</span></span>  
  
-   <span data-ttu-id="232ee-121">отключить задание;</span><span class="sxs-lookup"><span data-stu-id="232ee-121">Disable the job.</span></span>  
  
-   <span data-ttu-id="232ee-122">отсоединить расписание от задания;</span><span class="sxs-lookup"><span data-stu-id="232ee-122">Detach the schedule from the job.</span></span>  
  
-   <span data-ttu-id="232ee-123">остановить службу агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="232ee-123">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
-   <span data-ttu-id="232ee-124">удалить расписание.</span><span class="sxs-lookup"><span data-stu-id="232ee-124">Delete the schedule.</span></span>  
  
 <span data-ttu-id="232ee-125">Если расписание не включено, задание все равно может выполняться в ответ на предупреждение или при запуске пользователем вручную.</span><span class="sxs-lookup"><span data-stu-id="232ee-125">If the schedule is not enabled, the job can still run in response to an alert or when a user runs the job manually.</span></span> <span data-ttu-id="232ee-126">Когда расписание заданий не включено, оно выключено для всех заданий, использующих это расписание.</span><span class="sxs-lookup"><span data-stu-id="232ee-126">When a job schedule is not enabled, the schedule is not enabled for any job that uses the schedule.</span></span>  
  
 <span data-ttu-id="232ee-127">Необходимо явно повторно включить расписание, которое было отключено.</span><span class="sxs-lookup"><span data-stu-id="232ee-127">You must explicitly re-enable a schedule that has been disabled.</span></span> <span data-ttu-id="232ee-128">Изменение расписания не приводит к его автоматическому повторному включению.</span><span class="sxs-lookup"><span data-stu-id="232ee-128">Editing the schedule does not automatically re-enable the schedule.</span></span>  
  
## <a name="scheduling-start-dates"></a><span data-ttu-id="232ee-129">Планирование даты начала</span><span class="sxs-lookup"><span data-stu-id="232ee-129">Scheduling Start Dates</span></span>  
 <span data-ttu-id="232ee-130">Дата начала расписания должна быть больше или равна 19900101.</span><span class="sxs-lookup"><span data-stu-id="232ee-130">The start date of a schedule must be greater than or equal to 19900101.</span></span>  
  
 <span data-ttu-id="232ee-131">При присоединении расписания к заданию необходимо проверить дату выполнения, которую расписание будет использовать для первого запуска задания.</span><span class="sxs-lookup"><span data-stu-id="232ee-131">When you are attaching a schedule to a job, you should review the start date that the schedule uses to run the job for the first time.</span></span> <span data-ttu-id="232ee-132">Дата выполнения зависит от дня и времени присоединения расписания к заданию.</span><span class="sxs-lookup"><span data-stu-id="232ee-132">The start date depends upon the day and time when you attach the schedule to the job.</span></span> <span data-ttu-id="232ee-133">Например, можно создать расписание, которое выполняется каждый второй понедельник в 8:00.</span><span class="sxs-lookup"><span data-stu-id="232ee-133">For example, you create a schedule that runs every other Monday at 8:00 A.M.</span></span> <span data-ttu-id="232ee-134">Если задание создается в 10:00.</span><span class="sxs-lookup"><span data-stu-id="232ee-134">If you create a job at 10:00 A.M.</span></span> <span data-ttu-id="232ee-135">в понедельник 3 марта 2008 г., то начальной датой расписания будет понедельник 17 марта 2008 г.</span><span class="sxs-lookup"><span data-stu-id="232ee-135">on Monday, March 3, 2008, the schedule start date is Monday, March 17, 2008.</span></span> <span data-ttu-id="232ee-136">Если во вторник 4 марта 2008 г. создается другое задание, начальной датой расписания будет понедельник 10 марта 2008 г.</span><span class="sxs-lookup"><span data-stu-id="232ee-136">If you create another job on Tuesday, March 4, 2008, the schedule start date is Monday, March 10, 2008.</span></span>  
  
 <span data-ttu-id="232ee-137">Начальную дату расписания можно изменить после его присоединения к заданию.</span><span class="sxs-lookup"><span data-stu-id="232ee-137">You can change the schedule start date after you attach the schedule to a job.</span></span>  
  
## <a name="cpu-idle-schedules"></a><span data-ttu-id="232ee-138">Расписания простоя ЦП</span><span class="sxs-lookup"><span data-stu-id="232ee-138">CPU Idle Schedules</span></span>  
 <span data-ttu-id="232ee-139">Для максимально эффективного использования ресурсов ЦП можно определить условие простоя ЦП для агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="232ee-139">To maximize CPU resources, you can define a CPU idle condition for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="232ee-140">Агент использует настройку условий простоя ЦП, чтобы определить наиболее подходящее время для выполнения заданий.</span><span class="sxs-lookup"><span data-stu-id="232ee-140">Agent uses the CPU idle condition setting to determine the best time to run jobs.</span></span> <span data-ttu-id="232ee-141">Например, можно спланировать задание для перестройки индексов во время простоя ЦП и периодов невысокой загрузки.</span><span class="sxs-lookup"><span data-stu-id="232ee-141">For example, you can schedule a job to rebuild indexes during CPU idle time and slow production periods.</span></span>  
  
 <span data-ttu-id="232ee-142">Прежде чем определить задания для выполнения во время простоя ЦП, определите загрузку ЦП во время нормальной обработки.</span><span class="sxs-lookup"><span data-stu-id="232ee-142">Before you define jobs to run during CPU idle time, determine the load on the CPU during normal processing.</span></span> <span data-ttu-id="232ee-143">Чтобы сделать это, используйте приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] или системный монитор для контроля над рабочей нагрузкой сервера и сбора статистики.</span><span class="sxs-lookup"><span data-stu-id="232ee-143">To do this, use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor to monitor server traffic and collect statistics.</span></span> <span data-ttu-id="232ee-144">Затем можно использовать собранные сведения, чтобы установить процентную долю и продолжительность времени простоя ЦП.</span><span class="sxs-lookup"><span data-stu-id="232ee-144">You can then use the information you gather to set the CPU idle time percentage and duration.</span></span>  
  
 <span data-ttu-id="232ee-145">Определите условие простоя ЦП как процентную долю, ниже которой использование ЦП должно оставаться в течение указанного времени.</span><span class="sxs-lookup"><span data-stu-id="232ee-145">Define the CPU idle condition as a percentage below which CPU usage must remain for a specified time.</span></span> <span data-ttu-id="232ee-146">Затем установите количество времени.</span><span class="sxs-lookup"><span data-stu-id="232ee-146">Next, set the amount of time.</span></span> <span data-ttu-id="232ee-147">Когда использование ЦП окажется ниже указанной процентной доли в течение указанного количества времени, агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] запускает выполнение всех заданий, имеющих расписание для времени простоя ЦП.</span><span class="sxs-lookup"><span data-stu-id="232ee-147">When the CPU usage is below the specified percentage for the specified amount of time, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts all jobs that have a CPU idle time schedule.</span></span> <span data-ttu-id="232ee-148">Дополнительные сведения об использовании [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] или мониторе производительности для мониторинга использования ЦП см. в разделе [мониторинг использования ЦП](../../relational-databases/performance-monitor/monitor-cpu-usage.md).</span><span class="sxs-lookup"><span data-stu-id="232ee-148">For more information on using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor to monitor CPU usage, see [Monitor CPU Usage](../../relational-databases/performance-monitor/monitor-cpu-usage.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="232ee-149">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="232ee-149">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="232ee-150">**Описание**</span><span class="sxs-lookup"><span data-stu-id="232ee-150">**Description**</span></span>|<span data-ttu-id="232ee-151">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="232ee-151">**Topic**</span></span>|  
|<span data-ttu-id="232ee-152">Описывает создание расписания для задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="232ee-152">Describes how to create a schedule for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="232ee-153">Создание расписания</span><span class="sxs-lookup"><span data-stu-id="232ee-153">Create a Schedule</span></span>](create-a-schedule.md)|  
|<span data-ttu-id="232ee-154">Описывает планирование задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="232ee-154">Describes how to schedule a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="232ee-155">Планирование задания</span><span class="sxs-lookup"><span data-stu-id="232ee-155">Schedule a Job</span></span>](schedule-a-job.md)|  
|<span data-ttu-id="232ee-156">Описывает задание условия простоя ЦП для сервера.</span><span class="sxs-lookup"><span data-stu-id="232ee-156">Explains how to define the CPU idle condition for your server.</span></span>|[<span data-ttu-id="232ee-157">Установка времени и длительности простоя ЦП (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="232ee-157">Set CPU Idle Time and Duration &#40;SQL Server Management Studio&#41;</span></span>](set-cpu-idle-time-and-duration-sql-server-management-studio.md)|  
  
## <a name="see-also"></a><span data-ttu-id="232ee-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="232ee-158">See Also</span></span>  
 <span data-ttu-id="232ee-159">[sp_help_jobschedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobschedule-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="232ee-159">[sp_help_jobschedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobschedule-transact-sql) </span></span>  
 [<span data-ttu-id="232ee-160">dbo.sysжобсчедулес &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="232ee-160">dbo.sysjobschedules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysjobschedules-transact-sql)  
  
  
