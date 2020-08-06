---
title: Определение узких мест | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- resource bottlenecks [SQL Server]
- database monitoring [SQL Server], bottlenecks
- performance [SQL Server], bottlenecks
- tuning databases [SQL Server], bottlenecks
- monitoring server performance [SQL Server], bottlenecks
- monitoring performance [SQL Server], bottlenecks
- database performance [SQL Server], bottlenecks
- server performance [SQL Server], bottlenecks
- bottlenecks [SQL Server]
- identifying bottlenecks [SQL Server]
ms.assetid: db079e65-ee80-4105-aec9-f8230d0d6635
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e941b3f4a1185177cef007eb6a02a71ae1adece7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729382"
---
# <a name="identify-bottlenecks"></a><span data-ttu-id="5c940-102">Выявление узких мест</span><span class="sxs-lookup"><span data-stu-id="5c940-102">Identify Bottlenecks</span></span>
  <span data-ttu-id="5c940-103">Одновременный доступ к общим ресурсам может привести к появлению узких мест.</span><span class="sxs-lookup"><span data-stu-id="5c940-103">Simultaneous access to shared resources causes bottlenecks.</span></span> <span data-ttu-id="5c940-104">Узкие места присутствуют в любой программной системе, и избежать их появления нельзя.</span><span class="sxs-lookup"><span data-stu-id="5c940-104">In general, bottlenecks are present in every software system and are inevitable.</span></span> <span data-ttu-id="5c940-105">Однако чрезмерная нагрузка на общие ресурсы повышает время отклика, и поэтому ее необходимо выявить и выполнить настройку.</span><span class="sxs-lookup"><span data-stu-id="5c940-105">However, excessive demands on shared resources cause poor response time and must be identified and tuned.</span></span>  
  
 <span data-ttu-id="5c940-106">Причины появления узких мест:</span><span class="sxs-lookup"><span data-stu-id="5c940-106">Causes of bottlenecks include:</span></span>  
  
-   <span data-ttu-id="5c940-107">недостаточность ресурсов, требуется обновление или наращивание компонентов;</span><span class="sxs-lookup"><span data-stu-id="5c940-107">Insufficient resources, requiring additional or upgraded components.</span></span>  
  
-   <span data-ttu-id="5c940-108">однотипные ресурсы, рабочая нагрузка на которые не распределена должным образом (например, монопольное использование диска);</span><span class="sxs-lookup"><span data-stu-id="5c940-108">Resources of the same type among which workloads are not distributed evenly; for example, one disk is being monopolized.</span></span>  
  
-   <span data-ttu-id="5c940-109">неисправность ресурса;</span><span class="sxs-lookup"><span data-stu-id="5c940-109">Malfunctioning resources.</span></span>  
  
-   <span data-ttu-id="5c940-110">ресурс неправильно настроен.</span><span class="sxs-lookup"><span data-stu-id="5c940-110">Incorrectly configured resources.</span></span>  
  
## <a name="analyzing-bottlenecks"></a><span data-ttu-id="5c940-111">Анализ узких мест</span><span class="sxs-lookup"><span data-stu-id="5c940-111">Analyzing Bottlenecks</span></span>  
 <span data-ttu-id="5c940-112">Чрезмерная продолжительность различных событий служит признаком узких мест, которые нуждаются в дополнительной настройке.</span><span class="sxs-lookup"><span data-stu-id="5c940-112">Excessive durations for various events are indicators of bottlenecks that can be tuned.</span></span>  
  
 <span data-ttu-id="5c940-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="5c940-113">For example:</span></span>  
  
-   <span data-ttu-id="5c940-114">какой-либо компонент препятствует завершению загрузки данного компонента, таким образом повышая общую длительность загрузки;</span><span class="sxs-lookup"><span data-stu-id="5c940-114">Some other component may prevent the load from reaching this component thereby increasing the time to complete the load.</span></span>  
  
-   <span data-ttu-id="5c940-115">запросы от клиентов могут выполняться дольше из-за загруженности сети.</span><span class="sxs-lookup"><span data-stu-id="5c940-115">Client requests may take longer due to network congestion.</span></span>  
  
 <span data-ttu-id="5c940-116">Ниже приведены пять основных областей, на которые следует обратить внимание при выявлении узких мест.</span><span class="sxs-lookup"><span data-stu-id="5c940-116">Following are five key areas to monitor when tracking server performance to identify bottlenecks.</span></span>  
  
|<span data-ttu-id="5c940-117">Возможная область появления узких мест</span><span class="sxs-lookup"><span data-stu-id="5c940-117">Possible bottleneck area</span></span>|<span data-ttu-id="5c940-118">Влияние на сервер</span><span class="sxs-lookup"><span data-stu-id="5c940-118">Effects on the server</span></span>|  
|------------------------------|---------------------------|  
|<span data-ttu-id="5c940-119">Использование памяти</span><span class="sxs-lookup"><span data-stu-id="5c940-119">Memory usage</span></span>|<span data-ttu-id="5c940-120">Недостаток памяти, выделенной или доступной Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , значительно снижает производительность.</span><span class="sxs-lookup"><span data-stu-id="5c940-120">Insufficient memory allocated or available to Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] degrades performance.</span></span> <span data-ttu-id="5c940-121">Данные медленнее считываются с диска, чем непосредственно из кэша.</span><span class="sxs-lookup"><span data-stu-id="5c940-121">Data must be read from the disk rather than directly from the data cache.</span></span> <span data-ttu-id="5c940-122">Операционные системы Microsoft Windows выполняют чрезмерную выгрузку данных на диск и обратно в процессе обращения к различным страницам.</span><span class="sxs-lookup"><span data-stu-id="5c940-122">Microsoft Windows operating systems perform excessive paging by swapping data to and from the disk as the pages are needed.</span></span>|  
|<span data-ttu-id="5c940-123">загрузка ЦП;</span><span class="sxs-lookup"><span data-stu-id="5c940-123">CPU utilization</span></span>|<span data-ttu-id="5c940-124">Стабильно высокая загрузка ЦП может указывать на то, что следует оптимизировать запросы [!INCLUDE[tsql](../../includes/tsql-md.md)] , либо на необходимость модернизации ЦП.</span><span class="sxs-lookup"><span data-stu-id="5c940-124">A chronically high CPU utilization rate may indicate that [!INCLUDE[tsql](../../includes/tsql-md.md)] queries need to be tuned or that a CPU upgrade is needed.</span></span>|  
|<span data-ttu-id="5c940-125">Дисковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="5c940-125">Disk input/output (I/O)</span></span>|[!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="5c940-126">Чтобы снизить необходимость в операциях ввода-вывода, можно оптимизировать запросы (например, создав индексы).</span><span class="sxs-lookup"><span data-stu-id="5c940-126">queries can be tuned to reduce unnecessary I/O; for example, by employing indexes.</span></span>|  
|<span data-ttu-id="5c940-127">Соединения пользователей</span><span class="sxs-lookup"><span data-stu-id="5c940-127">User connections</span></span>|<span data-ttu-id="5c940-128">Слишком много пользователей, одновременно производящих доступ к серверу, могут вызвать снижение производительности.</span><span class="sxs-lookup"><span data-stu-id="5c940-128">Too many users may be accessing the server simultaneously causing performance degradation.</span></span>|  
|<span data-ttu-id="5c940-129">Блокирующие блокировки</span><span class="sxs-lookup"><span data-stu-id="5c940-129">Blocking locks</span></span>|<span data-ttu-id="5c940-130">Неверно разработанные приложения могут вызвать блокировки и затруднить параллелизм, а это повышает время отклика и снижает пропускную способность системы.</span><span class="sxs-lookup"><span data-stu-id="5c940-130">Incorrectly designed applications can cause locks and hamper concurrency, thus causing longer response times and lower transaction throughput rates.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c940-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c940-131">See Also</span></span>  
 <span data-ttu-id="5c940-132">[Мониторинг использования ЦП](../performance-monitor/monitor-cpu-usage.md) </span><span class="sxs-lookup"><span data-stu-id="5c940-132">[Monitor CPU Usage](../performance-monitor/monitor-cpu-usage.md) </span></span>  
 <span data-ttu-id="5c940-133">[Наблюдение за использованием диска](../performance-monitor/monitor-disk-usage.md) </span><span class="sxs-lookup"><span data-stu-id="5c940-133">[Monitor Disk Usage](../performance-monitor/monitor-disk-usage.md) </span></span>  
 <span data-ttu-id="5c940-134">[Наблюдение за использованием памяти](../performance-monitor/monitor-memory-usage.md) </span><span class="sxs-lookup"><span data-stu-id="5c940-134">[Monitor Memory Usage](../performance-monitor/monitor-memory-usage.md) </span></span>  
 <span data-ttu-id="5c940-135">[SQL Server, объект General Statistics](../performance-monitor/sql-server-general-statistics-object.md) </span><span class="sxs-lookup"><span data-stu-id="5c940-135">[SQL Server, General Statistics Object](../performance-monitor/sql-server-general-statistics-object.md) </span></span>  
 [<span data-ttu-id="5c940-136">SQL Server, объект Locks</span><span class="sxs-lookup"><span data-stu-id="5c940-136">SQL Server, Locks Object</span></span>](../performance-monitor/sql-server-locks-object.md)  
  
  
