---
title: Воспроизведение в точке останова (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- breakpoints [SQL Server]
- traces [SQL Server], replaying
ms.assetid: 3caf751e-df3b-40c7-b5e8-4490ae178e0c
author: stevestein
ms.author: sstein
ms.openlocfilehash: f33b6862847b042a2613d8c2aa035dd5805493ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737235"
---
# <a name="replay-to-a-breakpoint-sql-server-profiler"></a><span data-ttu-id="424ca-102">воспроизвести нагрузку до точки останова (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="424ca-102">Replay to a Breakpoint (SQL Server Profiler)</span></span>
  <span data-ttu-id="424ca-103">В этом подразделе описывается, как создавать точки останова в файле или таблице трассировки, воспроизводимой в приложении [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="424ca-103">This topic describes how to set breakpoints in a trace file or table that you want to replay by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="424ca-104">Определение точек останова перед запуском воспроизведения трассировки позволяет останавливать ее по определенным событиям.</span><span class="sxs-lookup"><span data-stu-id="424ca-104">Setting breakpoints in a trace file or table before you start to replay the trace, enables you to pause replay of the trace at specific events.</span></span> <span data-ttu-id="424ca-105">Точки останова позволяют отлаживать воспроизведение трассировки, разбивая длинный скрипт трассировки на короткие сегменты, которые могут быть подвергнуты последовательному анализу.</span><span class="sxs-lookup"><span data-stu-id="424ca-105">Using breakpoints while replaying a trace supports debugging because you can break the replay of long trace scripts into short segments that can be analyzed incrementally.</span></span>  
  
### <a name="to-replay-to-a-breakpoint"></a><span data-ttu-id="424ca-106">Воспроизведение до точки останова</span><span class="sxs-lookup"><span data-stu-id="424ca-106">To replay to a breakpoint</span></span>  
  
1.  <span data-ttu-id="424ca-107">Откройте файл трассировки или таблицу трассировки, которые необходимо воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="424ca-107">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="424ca-108">Дополнительные сведения см. в статье [Открыть файл трассировки (приложение SQL Server Profiler)](open-a-trace-file-sql-server-profiler.md) или в помощник по настройке ядра СУБД [Открыть таблицу трассировки (приложение SQL Server Profiler)](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="424ca-108">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="424ca-109">Убедитесь, что открытый файл трассировки или открытая таблица содержат классы событий, которые необходимо воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="424ca-109">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="424ca-110">Дополнительные сведения см. в разделе [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="424ca-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="424ca-111">В окне трассировки щелкните событие, по которому устанавливается точка останова.</span><span class="sxs-lookup"><span data-stu-id="424ca-111">In the trace window, click an event that you want to use as a breakpoint.</span></span> <span data-ttu-id="424ca-112">Точку останова можно назначить одним из следующих трех способов:</span><span class="sxs-lookup"><span data-stu-id="424ca-112">Use one of the following three methods to set a breakpoint:</span></span>  
  
    -   <span data-ttu-id="424ca-113">Нажмите клавишу F9.</span><span class="sxs-lookup"><span data-stu-id="424ca-113">Press F9.</span></span>  
  
    -   <span data-ttu-id="424ca-114">В меню **Воспроизведение** выбрав пункт **Переключить точку останова**.</span><span class="sxs-lookup"><span data-stu-id="424ca-114">On the **Replay** menu, click **Toggle Breakpoint**.</span></span>  
  
    -   <span data-ttu-id="424ca-115">Щелкнув событие правой кнопкой мыши, а затем выбрав пункт **Переключить точку останова**.</span><span class="sxs-lookup"><span data-stu-id="424ca-115">Right-click the event, and then click **Toggle Breakpoint**.</span></span>  
  
     <span data-ttu-id="424ca-116">Справа от выбранного события трассировки появляется красный маркер, указывающий на наличие точки останова.</span><span class="sxs-lookup"><span data-stu-id="424ca-116">A red bullet appears next to the selected trace event, indicating that it is the trace breakpoint.</span></span>  
  
     <span data-ttu-id="424ca-117">Повторите этот шаг для установки нескольких точек останова.</span><span class="sxs-lookup"><span data-stu-id="424ca-117">Repeat this step to set several breakpoints.</span></span>  
  
3.  <span data-ttu-id="424ca-118">В меню **Воспроизведение** выберите **Начать**и подключитесь к серверу, на котором будет воспроизводиться трассировка.</span><span class="sxs-lookup"><span data-stu-id="424ca-118">On the **Replay** menu, click **Start**, and connect to the server where you want to replay the trace.</span></span>  
  
4.  <span data-ttu-id="424ca-119">В диалоговом окне **Конфигурация воспроизведения** проверьте настройки и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="424ca-119">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
     <span data-ttu-id="424ca-120">Воспроизведение начинается, приостанавливаясь при достижении точки останова.</span><span class="sxs-lookup"><span data-stu-id="424ca-120">The replay starts, pausing when the breakpoint is reached.</span></span>  
  
5.  <span data-ttu-id="424ca-121">Нажмите F5 для возобновления воспроизведения до следующей точки останова.</span><span class="sxs-lookup"><span data-stu-id="424ca-121">Press F5 to resume the replay and proceed to the next breakpoint.</span></span>  
  
6.  <span data-ttu-id="424ca-122">Повторяйте шаг 5 до завершения трассировки.</span><span class="sxs-lookup"><span data-stu-id="424ca-122">Repeat Step 5 through the end of the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="424ca-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="424ca-123">See Also</span></span>  
 <span data-ttu-id="424ca-124">[Воспроизвести нагрузку до курсора (приложение SQL Server Profiler)](replay-to-a-cursor-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="424ca-124">[Replay to a Cursor &#40;SQL Server Profiler&#41;](replay-to-a-cursor-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="424ca-125">[Воспроизведение трассировок](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="424ca-125">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="424ca-126">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="424ca-126">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
