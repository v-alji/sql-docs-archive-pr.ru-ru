---
title: SQL Server Profiler — ограничение счетчиков производительности | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.performancecounterlimit.f1
helpviewer_keywords:
- Performance Counters List dialog box
ms.assetid: d10140ef-36c4-449c-b365-1cff1b2524e4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 27bda135abaf9d91b078e36a69a87098a734acbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736698"
---
# <a name="sql-server-profiler---performance-counters-limit"></a><span data-ttu-id="2115f-102">Приложение SQL Server Profiler — предел для счетчиков производительности</span><span class="sxs-lookup"><span data-stu-id="2115f-102">SQL Server Profiler - Performance Counters Limit</span></span>
  <span data-ttu-id="2115f-103">Используйте диалоговое окно «Предел для счетчиков производительности», чтобы ограничить сведения из файла журнала производительности системного монитора при сопоставлении ее с трассировкой приложения [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2115f-103">Use the Performance Counters Limit dialog box to limit the information from a System Monitor performance log file when correlating it with a [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace.</span></span> <span data-ttu-id="2115f-104">Можно использовать это диалоговое окно, чтобы выбрать счетчики, которые следует отобразить и использовать для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="2115f-104">You can use this dialog box to select counters that should be displayed and used for correlation.</span></span>  
  
 <span data-ttu-id="2115f-105">Диалоговое окно **Предел для счетчиков производительности** заполняется объектами производительности и счетчиками, которые содержатся в файле журнала производительности.</span><span class="sxs-lookup"><span data-stu-id="2115f-105">The **Performance Counters Limit** dialog box is populated with the performance objects and counters that the performance log file contains.</span></span>  
  
### <a name="to-select-performance-objects-and-counters-to-correlate-with-a-trace"></a><span data-ttu-id="2115f-106">Выбор объектов производительности и счетчиков для сопоставления с трассировкой</span><span class="sxs-lookup"><span data-stu-id="2115f-106">To select performance objects and counters to correlate with a trace</span></span>  
  
1.  <span data-ttu-id="2115f-107">Разверните объект производительности, чтобы увидеть, какие счетчики включены в файл журнала производительности.</span><span class="sxs-lookup"><span data-stu-id="2115f-107">Expand a performance object to see which counters are included in the performance log file.</span></span>  
  
2.  <span data-ttu-id="2115f-108">Установите флажки рядом со счетчиками, которые необходимо сопоставить с файлом трассировки приложения [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2115f-108">Check the counters that you want to correlate with the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace file.</span></span>  
  
     <span data-ttu-id="2115f-109">Если нужно выбрать все счетчики объекта производительности, установите пометку на флажке рядом с объектом производительности.</span><span class="sxs-lookup"><span data-stu-id="2115f-109">If you want to select all counters for a performance object, check the box that is adjacent to the performance object.</span></span> <span data-ttu-id="2115f-110">Пометив самый верхний узел, обозначающий компьютер, можно выбрать все объекты производительности и счетчики, содержащиеся в файле журнала производительности.</span><span class="sxs-lookup"><span data-stu-id="2115f-110">Checking the topmost node, which indicates the computer, selects all performance objects and counters contained in the performance log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2115f-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="2115f-111">See Also</span></span>  
 [<span data-ttu-id="2115f-112">Сопоставить трассировку с данными журнала производительности Windows (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="2115f-112">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../tools/sql-server-profiler/correlate-a-trace-with-windows-performance-log-data.md)  
  
  
