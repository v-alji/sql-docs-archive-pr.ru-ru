---
title: Создание диаграмм, предупреждений, журналов и отчетов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- System Monitor [SQL Server], charts and reports
- charts [SQL Server]
- reports [SQL Server]
- reports [SQL Server], creating
- Windows System Monitor [SQL Server], charts and reports
- logs [SQL Server], System Monitor
- System Monitor [SQL Server], logs
- Windows System Monitor [SQL Server], logs
ms.assetid: c9162b37-e5dc-43d1-a3aa-1e9ebc69fecc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3a0c95c3f483a8af3e3e68d9c5c7d3caf44350d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739752"
---
# <a name="create-charts-alerts-logs-and-reports"></a><span data-ttu-id="72994-102">Создание диаграмм, предупреждений, журналов и отчетов</span><span class="sxs-lookup"><span data-stu-id="72994-102">Create Charts, Alerts, Logs, and Reports</span></span>
  <span data-ttu-id="72994-103">Для контроля экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]системный монитор позволяет создавать диаграммы, предупреждения, журналы и отчеты.</span><span class="sxs-lookup"><span data-stu-id="72994-103">System Monitor lets you create charts, alerts, logs, and reports to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="charts"></a><span data-ttu-id="72994-104">Диаграммы</span><span class="sxs-lookup"><span data-stu-id="72994-104">Charts</span></span>  
 <span data-ttu-id="72994-105">Диаграммы позволяют контролировать производительность выбранных объектов и состояние счетчиков, например загрузку ЦП или дисковый ввод-вывод.</span><span class="sxs-lookup"><span data-stu-id="72994-105">Charts can monitor the current performance of selected objects and counters; for example, the CPU usage or disk I/O.</span></span> <span data-ttu-id="72994-106">К диаграмме можно добавить различные сочетания объектов и счетчиков системного монитора.</span><span class="sxs-lookup"><span data-stu-id="72994-106">You can add to a chart various combinations of System Monitor objects and counters.</span></span> <span data-ttu-id="72994-107">К диаграмме также можно добавить объекты и счетчики [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="72994-107">You also can add [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows objects and counters to a chart.</span></span>  
  
 <span data-ttu-id="72994-108">Каждая диаграмма представляет подмножество контролируемых данных.</span><span class="sxs-lookup"><span data-stu-id="72994-108">Each chart represents a subset of information you want to monitor.</span></span> <span data-ttu-id="72994-109">Например, одна диаграмма может отслеживать статистику использования памяти, а вторая — статистику операций дискового ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="72994-109">For example, one chart can track memory usage statistics and a second chart can track disk I/O statistics.</span></span>  
  
 <span data-ttu-id="72994-110">Диаграммы полезно использовать при выполнении следующих задач.</span><span class="sxs-lookup"><span data-stu-id="72994-110">Using a chart can be useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="72994-111">Исследование причин медленной или неэффективной работы компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="72994-111">Investigating why a computer or application is slow or inefficient.</span></span>  
  
-   <span data-ttu-id="72994-112">Постоянный контроль различных систем для обнаружения периодических проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="72994-112">Continually monitoring systems to find intermittent performance problems.</span></span>  
  
-   <span data-ttu-id="72994-113">Определение момента, когда требуется увеличить емкость.</span><span class="sxs-lookup"><span data-stu-id="72994-113">Discovering why you need to increase capacity.</span></span>  
  
-   <span data-ttu-id="72994-114">Отображение тренда в виде линии диаграммы.</span><span class="sxs-lookup"><span data-stu-id="72994-114">Displaying a trend as a line chart.</span></span>  
  
-   <span data-ttu-id="72994-115">Отображение сравнительных данных в виде гистограммы.</span><span class="sxs-lookup"><span data-stu-id="72994-115">Displaying a comparison as a histogram chart.</span></span>  
  
 <span data-ttu-id="72994-116">Диаграммы полезно использовать для кратковременного контроля показателей локального или удаленного компьютера в реальном времени (например, контроля возникновения определенных событий).</span><span class="sxs-lookup"><span data-stu-id="72994-116">Charts are useful for short-term, real-time monitoring of a local or remote computer (for example, when you want to monitor an event as it occurs).</span></span>  
  
## <a name="alerts"></a><span data-ttu-id="72994-117">видны узлы</span><span class="sxs-lookup"><span data-stu-id="72994-117">Alerts</span></span>  
 <span data-ttu-id="72994-118">При помощи предупреждений системный монитор отслеживает определенные события и уведомляет выбранным способом.</span><span class="sxs-lookup"><span data-stu-id="72994-118">Using alerts, System Monitor tracks specific events and notifies you of these events as requested.</span></span> <span data-ttu-id="72994-119">В журнал предупреждений можно записывать текущее состояние выбранных счетчиков производительности и экземпляров объектов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72994-119">An alert log can monitor the current performance of selected counters and instances for objects in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="72994-120">Когда счетчик превышает заданное значение, в журнал записываются соответствующие дата и время.</span><span class="sxs-lookup"><span data-stu-id="72994-120">When a counter exceeds a given value, the log records the date and time of the event.</span></span> <span data-ttu-id="72994-121">Предупреждения о событиях можно передавать по сети.</span><span class="sxs-lookup"><span data-stu-id="72994-121">An event can also generate a network alert.</span></span> <span data-ttu-id="72994-122">Кроме того, можно указать программу, которую необходимо запускать при первом или каждом возникновении события.</span><span class="sxs-lookup"><span data-stu-id="72994-122">You can have a specified program run the first time or every time an event occurs.</span></span> <span data-ttu-id="72994-123">Например, можно передать по сети сообщение всем системным администраторам о том, что экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не хватает пространства на диске.</span><span class="sxs-lookup"><span data-stu-id="72994-123">For example, an alert can send a network message to all system administrators that the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is getting low on disk space.</span></span>  
  
## <a name="logs"></a><span data-ttu-id="72994-124">Журналы</span><span class="sxs-lookup"><span data-stu-id="72994-124">Logs</span></span>  
 <span data-ttu-id="72994-125">Журналы позволяют записывать сведения о текущей активности выбранных объектов и компьютеров для последующего просмотра и анализа.</span><span class="sxs-lookup"><span data-stu-id="72994-125">Logs allow you to record information on the current activity of selected objects and computers for later viewing and analysis.</span></span> <span data-ttu-id="72994-126">В один файл журнала можно записывать данные нескольких систем.</span><span class="sxs-lookup"><span data-stu-id="72994-126">You can collect data from multiple systems into a single log file.</span></span> <span data-ttu-id="72994-127">Например, можно создать различные журналы для сбора сведений о производительности выбранных объектов на разных компьютерах для последующего анализа.</span><span class="sxs-lookup"><span data-stu-id="72994-127">For example, you can create different logs to accumulate information about the performance of selected objects on various computers for future analysis.</span></span> <span data-ttu-id="72994-128">Журнал с выбранными настройками можно сохранить в отдельном файле и использовать его для создания других журналов, которые должны содержать аналогичные сведения.</span><span class="sxs-lookup"><span data-stu-id="72994-128">You can save these selections under a file name and reuse them when you want to create another log of similar information for comparison.</span></span>  
  
 <span data-ttu-id="72994-129">Файлы журнала предоставляют сведения для устранения неполадок и планирования.</span><span class="sxs-lookup"><span data-stu-id="72994-129">Log files provide a wealth of information for troubleshooting or planning.</span></span> <span data-ttu-id="72994-130">В отличие от диаграмм, предупреждений и отчетов, которые предоставляют сведения о текущей активности, файлы журнала позволяют отслеживать состояние счетчиков за длительное время.</span><span class="sxs-lookup"><span data-stu-id="72994-130">Whereas charts, alerts, and reports on current activity provide instant feedback, log files enable you to track counters over a long period of time.</span></span> <span data-ttu-id="72994-131">Таким образом, они позволяют более тщательно контролировать и изучать сведения о производительности системы.</span><span class="sxs-lookup"><span data-stu-id="72994-131">Thus, you can examine information more thoroughly and document system performance.</span></span>  
  
## <a name="reports"></a><span data-ttu-id="72994-132">Отчеты</span><span class="sxs-lookup"><span data-stu-id="72994-132">Reports</span></span>  
 <span data-ttu-id="72994-133">Отчеты позволяют посмотреть состояние постоянно меняющегося счетчика и значения экземпляров выбранных объектов.</span><span class="sxs-lookup"><span data-stu-id="72994-133">Reports allow you to display constantly changing counter and instance values for selected objects.</span></span> <span data-ttu-id="72994-134">Значения отображаются для каждого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="72994-134">Values appear in columns for each instance.</span></span> <span data-ttu-id="72994-135">Можно настроить период отчета, напечатать моментальные снимки и экспортировать данные.</span><span class="sxs-lookup"><span data-stu-id="72994-135">You can adjust report intervals, print snapshots, and export data.</span></span> <span data-ttu-id="72994-136">Используйте отчеты, если требуются необработанные данные.</span><span class="sxs-lookup"><span data-stu-id="72994-136">Use reports when you need to display the raw numbers.</span></span>  
  
 <span data-ttu-id="72994-137">Дополнительные сведения о создании диаграмм, предупреждений, журналов и отчетов и об объектах и счетчиках Windows см. в документации по Windows.</span><span class="sxs-lookup"><span data-stu-id="72994-137">For more information about creating charts, alerts, logs, and reports, or about Windows objects and counters, see the Windows documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72994-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="72994-138">See Also</span></span>  
 [<span data-ttu-id="72994-139">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="72994-139">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
