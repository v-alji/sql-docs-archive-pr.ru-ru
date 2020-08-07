---
title: Сопоставление трассировки с журналом производительности Windows | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- correlating trace with log data
- logs [SQL Server], traces
- Profiler [SQL Server Profiler], correlating trace with log data
- traces [SQL Server], logs
- SQL Server Profiler, correlating trace with log data
ms.assetid: 1e4412c8-d27c-4aae-9b35-214128d1d00a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 879441c948f0ad04b971159a37ec0dcec90e3ada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727601"
---
# <a name="correlate-a-trace-with-windows-performance-log-data"></a><span data-ttu-id="9b6a5-102">Сопоставление трассировки с журналом производительности Windows</span><span class="sxs-lookup"><span data-stu-id="9b6a5-102">Correlate a Trace with Windows Performance Log Data</span></span>
  <span data-ttu-id="9b6a5-103">С помощью приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]можно открыть журнал производительности Microsoft Windows, выбрать счетчики, которые нужно сопоставить с трассировкой, и отобразить выбранные счетчики производительности рядом с трассировкой в графическом пользовательском интерфейсе приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b6a5-103">Using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can open a Microsoft Windows performance log, choose the counters you want to correlate with a trace, and display the selected performance counters alongside the trace in the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] graphical user interface.</span></span> <span data-ttu-id="9b6a5-104">При выборе события в окне трассировки вертикальная красная линия на панели окна системного монитора в приложении [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] показывает данные журнала производительности, которые сопоставлены выбранному событию трассировки.</span><span class="sxs-lookup"><span data-stu-id="9b6a5-104">When you select an event in the trace window, a vertical red bar in the System Monitor data window pane of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] indicates the performance log data that correlates with the selected trace event.</span></span>  
  
 <span data-ttu-id="9b6a5-105">Чтобы сопоставить трассировку со счетчиками производительности, откройте файл трассировки или таблицу, содержащую столбцы данных **StartTime** и **EndTime**, а затем щелкните элемент **Импорт данных производительности** в меню [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]Файл**в**.</span><span class="sxs-lookup"><span data-stu-id="9b6a5-105">To correlate a trace with performance counters, open a trace file or table that contains the **StartTime** and **EndTime** data columns, and then click **Import Performance Data** on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **File** menu.</span></span> <span data-ttu-id="9b6a5-106">Потом можно открыть журнал производительности и выбрать объекты системного монитора и счетчики, которые сопоставляются с трассировкой.</span><span class="sxs-lookup"><span data-stu-id="9b6a5-106">You can then open a performance log, and select the System Monitor objects and counters that you want to correlate with the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b6a5-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b6a5-107">See Also</span></span>  
 [<span data-ttu-id="9b6a5-108">Сопоставить трассировку с данными журнала производительности Windows (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="9b6a5-108">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](correlate-a-trace-with-windows-performance-log-data.md)  
  
  
