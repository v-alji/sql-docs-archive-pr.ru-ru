---
title: Наблюдение за использованием ресурсов (системный монитор) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server], resource usage
- System Monitor [SQL Server], about Windows System Monitor
- resource usage monitoring [SQL Server]
- System Monitor [SQL Server]
- counters [SQL Server], resource usage subjects
- performance counters [SQL Server], resource usage subjects
- Windows System Monitor [SQL Server], about Windows System Monitor
- monitoring [SQL Server], server resource usage
- monitoring resource usage [SQL Server]
- Windows System Monitor [SQL Server]
- database monitoring [SQL Server], resource usage
- database performance [SQL Server], resource usage
- tuning databases [SQL Server], resource usage
- server performance [SQL Server], resource usage
ms.assetid: f2993a28-0b81-46f2-aec0-6877fe990387
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d691091a41e3161c733902824bf439b6788cc4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668262"
---
# <a name="monitor-resource-usage-system-monitor"></a><span data-ttu-id="ad0cc-102">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="ad0cc-102">Monitor Resource Usage (System Monitor)</span></span>
  <span data-ttu-id="ad0cc-103">В состав серверной операционной системы Microsoft Windows входит графическое средство для измерения производительности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]— системный монитор.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-103">If you are running Microsoft Windows server operating system, use the System Monitor graphical tool to measure the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ad0cc-104">Он позволяет просматривать объекты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , счетчики производительности, а также поведения других объектов, таких как процессоры, память, кэш, потоки и процессы.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-104">You can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects, performance counters, and the behavior of other objects, such as processors, memory, cache, threads, and processes.</span></span> <span data-ttu-id="ad0cc-105">С каждым из этих объектов связан набор счетчиков, измеряющих степень использования устройства, длину очередей, задержки и другие показатели производительности и внутренней перегрузки.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-105">Each of these objects has an associated set of counters that measure device usage, queue lengths, delays, and other indicators of throughput and internal congestion.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ad0cc-106">Этот системный монитор заменяет системный монитор Windows NT 4.0.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-106">System Monitor replaced Performance Monitor after Windows NT 4.0.</span></span>  
  
## <a name="benefits-of-system-monitor"></a><span data-ttu-id="ad0cc-107">Преимущества системного монитора</span><span class="sxs-lookup"><span data-stu-id="ad0cc-107">Benefits of System Monitor</span></span>  
 <span data-ttu-id="ad0cc-108">Системный монитор может быть полезным для одновременного контроля счетчиков операционной системы Windows и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для определения корреляции между производительностью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и Windows.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-108">System Monitor can be useful to monitor Windows operating system and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] counters at the same time to determine any correlation between the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows.</span></span> <span data-ttu-id="ad0cc-109">Например, контроль счетчиков Windows для операций ввода-вывода на диске и одновременно счетчиков диспетчера буферов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может выявить закономерности всей системы.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-109">For example, monitoring the Windows disk input/output (I/O) counters and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Buffer Manager counters at the same time can reveal the behavior of the entire system.</span></span>  
  
 <span data-ttu-id="ad0cc-110">Системный монитор позволяет получить статистические данные о текущей активности и производительности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad0cc-110">System Monitor allows you to obtain statistics on current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activity and performance.</span></span> <span data-ttu-id="ad0cc-111">Применение системного монитора предоставляет следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-111">Using System Monitor, you can:</span></span>  
  
-   <span data-ttu-id="ad0cc-112">Просматривать данные одновременно на любом числе компьютеров.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-112">View data simultaneously from any number of computers.</span></span>  
  
-   <span data-ttu-id="ad0cc-113">Просматривать и изменять диаграммы, отражающие текущую активность, отображать значения счетчиков, обновляемых с частотой, которую определяет пользователь.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-113">View and change charts to reflect current activity, and show counter values that are updated at a frequency that the user defines.</span></span>  
  
-   <span data-ttu-id="ad0cc-114">Экспортировать данные из диаграмм, журналов, журналов предупреждений и отчетов в электронные таблицы или приложения баз данных для дальнейшей обработки и печати.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-114">Export data from charts, logs, alert logs, and reports to spreadsheet or database applications for further manipulation and printing.</span></span>  
  
-   <span data-ttu-id="ad0cc-115">Добавлять системные предупреждения, которые вносят событие в журнал предупреждений и уведомляют пользователей, формируя сетевые предупреждения.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-115">Add system alerts that list an event in the alert log and can notify you by issuing a network alert.</span></span>  
  
-   <span data-ttu-id="ad0cc-116">Запускать предопределенные приложения в первый раз или каждый раз, когда значение счетчика становится выше или ниже заданного значения.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-116">Run a predefined application the first time or every time a counter value goes over or under a user-defined value.</span></span>  
  
-   <span data-ttu-id="ad0cc-117">Создавать файлы журналов, содержащие данные о различных объектах в разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-117">Create log files that contain data about various objects from different computers.</span></span>  
  
-   <span data-ttu-id="ad0cc-118">Присоединять к одному файлу выбранные разделы из других файлов журналов для формирования долговременного архива.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-118">Append to one file selected sections from other existing log files to form a long-term archive.</span></span>  
  
-   <span data-ttu-id="ad0cc-119">Просматривать отчеты о текущей активности или создавать отчеты на основе данных существующих файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-119">View current-activity reports, or create reports from existing log files.</span></span>  
  
-   <span data-ttu-id="ad0cc-120">Сохранять отдельные диаграммы, предупреждения, журналы, параметры отчетов или данные для запуска всего рабочего пространства для повторного использования.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-120">Save individual chart, alert, log, or report settings, or the entire workspace setup for reuse.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ad0cc-121">В системах позднее Windows NT 4.0 системный монитор заменил монитор производительности.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-121">System Monitor replaced the Performance Monitor after Windows NT 4.0.</span></span> <span data-ttu-id="ad0cc-122">Для выполнения указанных задач можно использовать системный монитор или монитор производительности.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-122">You can use either the System Monitor or Performance Monitor to do these tasks.</span></span>  
  
## <a name="system-monitor-performance"></a><span data-ttu-id="ad0cc-123">Производительность системного монитора</span><span class="sxs-lookup"><span data-stu-id="ad0cc-123">System Monitor Performance</span></span>  
 <span data-ttu-id="ad0cc-124">При мониторинге [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и операционной системы Microsoft Windows для исследования вопросов, связанных с производительностью, первоначальные усилия должны быть сосредоточены на трех основных областях.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-124">When you monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the Microsoft Windows operating system to investigate performance-related issues, concentrate your initial efforts in three main areas:</span></span>  
  
-   <span data-ttu-id="ad0cc-125">Активность работы с диском</span><span class="sxs-lookup"><span data-stu-id="ad0cc-125">Disk activity</span></span>  
  
-   <span data-ttu-id="ad0cc-126">Использование процессора</span><span class="sxs-lookup"><span data-stu-id="ad0cc-126">Processor utilization</span></span>  
  
-   <span data-ttu-id="ad0cc-127">Использование памяти</span><span class="sxs-lookup"><span data-stu-id="ad0cc-127">Memory usage</span></span>  
  
 <span data-ttu-id="ad0cc-128">Контроль компьютера, в котором выполняется системный монитор, может слегка влиять на производительность компьютера.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-128">Monitoring a computer on which System Monitor is running can affect computer performance slightly.</span></span> <span data-ttu-id="ad0cc-129">Поэтому или регистрируйте данные системного монитора на другом диске (или компьютере), чтобы уменьшить воздействие процедуры контроля на контролируемый компьютер, или выполняйте системный монитор с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-129">Therefore, either log the System Monitor data to another disk (or computer) so that it reduces the effect on the computer being monitored, or run System Monitor from a remote computer.</span></span> <span data-ttu-id="ad0cc-130">Контролируйте только те счетчики, которые необходимы.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-130">Monitor only the counters in which you are interested.</span></span> <span data-ttu-id="ad0cc-131">При мониторинге слишком большого числа счетчиков в процессе мониторинга возникают дополнительные затраты ресурсов, что влияет на производительность того компьютера, за которым производится наблюдение.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-131">If you monitor too many counters, resource usage overhead is added to the monitoring process and affects the performance of the computer that is being monitored.</span></span>  
  
## <a name="system-monitor-tasks"></a><span data-ttu-id="ad0cc-132">Задачи системного монитора</span><span class="sxs-lookup"><span data-stu-id="ad0cc-132">System Monitor Tasks</span></span>  
  
|<span data-ttu-id="ad0cc-133">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="ad0cc-133">Task Description</span></span>|<span data-ttu-id="ad0cc-134">Раздел</span><span class="sxs-lookup"><span data-stu-id="ad0cc-134">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="ad0cc-135">Описываются случаи применения системного монитора и обсуждается снижение производительности при использовании системного монитора.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-135">Describes when to use System Monitor and discusses performance overhead when you use System Monitor.</span></span>|[<span data-ttu-id="ad0cc-136">Запуск системного монитора</span><span class="sxs-lookup"><span data-stu-id="ad0cc-136">Run System Monitor</span></span>](run-system-monitor.md)|  
|<span data-ttu-id="ad0cc-137">Описаны способы отслеживания счетчиков дискового пространства для определения активности диска и количества операций ввода-вывода, создаваемых компонентами SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-137">Describes how to monitor disk counters to determine disk activity and the amount of I/O generated by their SQL Server components.</span></span>|[<span data-ttu-id="ad0cc-138">Отслеживание использования диска</span><span class="sxs-lookup"><span data-stu-id="ad0cc-138">Monitor Disk Usage</span></span>](monitor-disk-usage.md)|  
|<span data-ttu-id="ad0cc-139">Описаны способы отслеживания экземпляра Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , чтобы определить, находятся ли уровни загрузки ЦП в стандартных диапазонах.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-139">Describes how to monitor an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to determine whether CPU usage rates are within normal ranges.</span></span>|[<span data-ttu-id="ad0cc-140">Отслеживание использования ЦП</span><span class="sxs-lookup"><span data-stu-id="ad0cc-140">Monitor CPU Usage</span></span>](monitor-cpu-usage.md)|  
|<span data-ttu-id="ad0cc-141">Описаны способы мониторинга экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для подтверждения того, что память используется в допустимых пределах.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-141">Describes how to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to confirm that memory usage is within typical ranges.</span></span>|[<span data-ttu-id="ad0cc-142">Отслеживание использования памяти</span><span class="sxs-lookup"><span data-stu-id="ad0cc-142">Monitor Memory Usage</span></span>](monitor-memory-usage.md)|  
|<span data-ttu-id="ad0cc-143">Описаны способы создания предупреждения, которое будет выводиться, когда счетчик системного монитора достигает порогового значения.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-143">Describes how to create an alert that is raised when a threshold value for a System Monitor counter has been reached.</span></span>|[<span data-ttu-id="ad0cc-144">Создание предупреждения для базы данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad0cc-144">Create a SQL Server Database Alert</span></span>](create-a-sql-server-database-alert.md)|  
|<span data-ttu-id="ad0cc-145">Описаны способы создания диаграмм, предупреждений, журналов и отчетов для отслеживания экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad0cc-145">Describes how to you create charts, alerts, logs, and reports to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[<span data-ttu-id="ad0cc-146">Создание диаграмм, предупреждений, журналов и отчетов</span><span class="sxs-lookup"><span data-stu-id="ad0cc-146">Create Charts, Alerts, Logs, and Reports</span></span>](create-charts-alerts-logs-and-reports.md)|  
|<span data-ttu-id="ad0cc-147">Приводится список объектов и счетчиков, используемых системным монитором для отслеживания деятельности на компьютерах, где установлены экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad0cc-147">Lists objects and counters that System Monitor uses to monitor activity in computers running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[<span data-ttu-id="ad0cc-148">Использование объектов SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad0cc-148">Use SQL Server Objects</span></span>](use-sql-server-objects.md)|  
|<span data-ttu-id="ad0cc-149">Приводится список объектов и счетчиков, используемых системным монитором для отслеживания действий OLTP в памяти.</span><span class="sxs-lookup"><span data-stu-id="ad0cc-149">Lists objects and counters that System Monitor uses to monitor In-Memory OLTP activity.</span></span>|[<span data-ttu-id="ad0cc-150">Счетчики производительности XTP &#40;в памяти OLTP&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0cc-150">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)|  
  
  
