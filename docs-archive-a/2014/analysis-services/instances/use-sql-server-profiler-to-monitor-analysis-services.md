---
title: Использование SQL Server Profiler для отслеживания Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- performance [Analysis Services], SQL Server Profiler
- Profiler [SQL Server Profiler], Analysis Services
ms.assetid: 8b77dafc-4584-4e93-8ad7-299304391bfd
author: minewiskan
ms.author: owend
ms.openlocfilehash: e144c1d858670f8a46b164ffc9885e6e082c4b0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656675"
---
# <a name="use-sql-server-profiler-to-monitor-analysis-services"></a><span data-ttu-id="61906-102">Use SQL Server Profiler to Monitor Analysis Services</span><span class="sxs-lookup"><span data-stu-id="61906-102">Use SQL Server Profiler to Monitor Analysis Services</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="61906-103">отслеживает события обработки ядра, например начало пакета или транзакции, и фиксирует данные об этих событиях, тем самым давая возможность осуществлять мониторинг операций серверов и баз данных (например, пользовательские операции запросов и входа в систему).</span><span class="sxs-lookup"><span data-stu-id="61906-103">tracks engine process events, such as the start of a batch or a transaction, and it captures data about those events, thus enabling you to monitor server and database activity (for example, user queries or login activity).</span></span> <span data-ttu-id="61906-104">Можно фиксировать данные приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или файл для дальнейшего анализа, а также можно воспроизводить зафиксированные события в том же или в другом экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , чтобы точно определить, что произошло.</span><span class="sxs-lookup"><span data-stu-id="61906-104">You can capture [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] data to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or a file for later analysis, and you can also replay the events captured on the same or another [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance to see exactly what happened.</span></span> <span data-ttu-id="61906-105">Можно воспроизводить события в режиме реального времени или в пошаговом режиме.</span><span class="sxs-lookup"><span data-stu-id="61906-105">You can replay events in real time or on a step-by-step basis.</span></span> <span data-ttu-id="61906-106">Также очень полезно запускать события трассировки вместе со счетчиками приложения «Производительность» на одном и том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="61906-106">It is also very useful to run the trace events along with the Performance counters on the same machine.</span></span> <span data-ttu-id="61906-107">Приложение SQL Profiler может определять корреляцию между ними на основе времени и отображать их совместно на одной временной шкале.</span><span class="sxs-lookup"><span data-stu-id="61906-107">The profiler can correlate these two based on time and display them together along a single timeline.</span></span> <span data-ttu-id="61906-108">События трассировки предоставят подробные сведения, в то время как счетчики приложения «Производительность» дадут общее представление.</span><span class="sxs-lookup"><span data-stu-id="61906-108">Trace events will give you more details while Performance counters give you an aggregate view.</span></span> <span data-ttu-id="61906-109">Дополнительные сведения о создании и запуске трассировок см. в разделе [Создание трассировки приложения Profiler для воспроизведения (службы Analysis Services)](create-profiler-traces-for-replay-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="61906-109">For information about how to create and run traces, see [Create Profiler Traces for Replay &#40;Analysis Services&#41;](create-profiler-traces-for-replay-analysis-services.md).</span></span>  
  
 <span data-ttu-id="61906-110">В следующей таблице описаны подразделы, содержащиеся в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="61906-110">The following table describes the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61906-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="61906-111">In This Section</span></span>  
  
|<span data-ttu-id="61906-112">Раздел</span><span class="sxs-lookup"><span data-stu-id="61906-112">Topic</span></span>|<span data-ttu-id="61906-113">Описание</span><span class="sxs-lookup"><span data-stu-id="61906-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="61906-114">Введение в мониторинг служб Analysis Services при помощи приложения SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="61906-114">Introduction to Monitoring Analysis Services with SQL Server Profiler</span></span>](introduction-to-monitoring-analysis-services-with-sql-server-profiler.md)|<span data-ttu-id="61906-115">Содержит описание использования приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] для мониторинга экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61906-115">Describes how to use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to monitor an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>|  
|[<span data-ttu-id="61906-116">Создание трассировки приложения Profiler для воспроизведения (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="61906-116">Create Profiler Traces for Replay &#40;Analysis Services&#41;</span></span>](create-profiler-traces-for-replay-analysis-services.md)|<span data-ttu-id="61906-117">Содержит требования к созданию трассировки для воспроизведения с помощью приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61906-117">Describes the requirements for creating a trace for replay by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="61906-118">События трассировки служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="61906-118">Analysis Services Trace Events</span></span>](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events)|<span data-ttu-id="61906-119">Содержит описание классов событий служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61906-119">Describes [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] event classes.</span></span> <span data-ttu-id="61906-120">Эти классы событий соответствуют действиям, формируемым службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , и используются для воспроизведения трассировок.</span><span class="sxs-lookup"><span data-stu-id="61906-120">These event classes map to actions generated by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and are used for trace replays.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61906-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="61906-121">See Also</span></span>  
 [<span data-ttu-id="61906-122">Наблюдение за экземпляром служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="61906-122">Monitor an Analysis Services Instance</span></span>](monitor-an-analysis-services-instance.md)  
  
  
