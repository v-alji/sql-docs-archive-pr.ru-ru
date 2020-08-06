---
title: Запуск трассировки | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, stopping traces
- pausing traces
- Profiler [SQL Server Profiler], stopping traces
- Profiler [SQL Server Profiler], starting traces
- traces [SQL Server], starting
- SQL Server Profiler, pausing traces
- traces [SQL Server], stopping
- Profiler [SQL Server Profiler], pausing traces
- traces [SQL Server], pausing
- SQL Server Profiler, starting traces
- stopping traces
- starting traces
ms.assetid: aeeb38eb-229a-4c8b-ad66-57e9ce45fb6a
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2b75519631269a1213077a4e295ac73fca1b950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734750"
---
# <a name="start-a-trace"></a><span data-ttu-id="c4e5d-102">Запуск трассировки</span><span class="sxs-lookup"><span data-stu-id="c4e5d-102">Start a Trace</span></span>
  <span data-ttu-id="c4e5d-103">После определения новой трассировки или создания шаблона при помощи приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]можно запускать, приостанавливать или останавливать сбор данных, используя новое определение трассировки или новый шаблон.</span><span class="sxs-lookup"><span data-stu-id="c4e5d-103">After you have defined a new trace or created a template by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can start, pause, or stop capturing data by using the new trace definition or template.</span></span>  
  
## <a name="starting-a-trace"></a><span data-ttu-id="c4e5d-104">Запуск трассировки</span><span class="sxs-lookup"><span data-stu-id="c4e5d-104">Starting a Trace</span></span>  
 <span data-ttu-id="c4e5d-105">Когда запускается трассировка, а определенным источником является экземпляр [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] или служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] создает очередь, служащую для временного хранения данных о зарегистрированных серверных событиях.</span><span class="sxs-lookup"><span data-stu-id="c4e5d-105">When you start a trace and the defined source is an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates a queue that provides a temporary holding place for captured server events.</span></span>  
  
 <span data-ttu-id="c4e5d-106">При обращении к инструменту трассировки SQL посредством приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] открывается новое окно трассировки (если ни одно такое окно еще не открыто) и немедленно выполняется регистрация данных.</span><span class="sxs-lookup"><span data-stu-id="c4e5d-106">When you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to access SQL Trace, a new trace window opens (if one is not already open) when a trace is started, and data is immediately captured.</span></span>  
  
 <span data-ttu-id="c4e5d-107">Если обращение следует к механизму трассировки SQL с использованием системных хранимых процедур [!INCLUDE[tsql](../../includes/tsql-md.md)] , трассировку нужно запускать каждый раз, когда экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] начинает регистрацию данных.</span><span class="sxs-lookup"><span data-stu-id="c4e5d-107">When you use [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to access SQL Trace, you must start a trace every time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts for data to be captured.</span></span> <span data-ttu-id="c4e5d-108">После запуска трассировки можно изменить только ее имя.</span><span class="sxs-lookup"><span data-stu-id="c4e5d-108">When a trace has been started, you can modify only the name of the trace.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4e5d-109">При работе с существующими трассировками можно просматривать свойства, но нельзя изменять их.</span><span class="sxs-lookup"><span data-stu-id="c4e5d-109">When working with existing traces, you can view the properties, but you cannot modify the properties.</span></span> <span data-ttu-id="c4e5d-110">Чтобы изменить свойства, необходимо остановить или приостановить трассировку.</span><span class="sxs-lookup"><span data-stu-id="c4e5d-110">To modify the properties, stop or pause the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e5d-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="c4e5d-111">See Also</span></span>  
 <span data-ttu-id="c4e5d-112">[Автоматический запуск трассировки после подключения к серверу &#40;SQL Server Profiler&#41;](start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c4e5d-112">[Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;](start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c4e5d-113">[Приостановка SQL Server Profiler &#40;трассировки&#41;](pause-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c4e5d-113">[Pause a Trace &#40;SQL Server Profiler&#41;](pause-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c4e5d-114">[Завершение SQL Server Profiler &#40;трассировки&#41;](stop-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c4e5d-114">[Stop a Trace &#40;SQL Server Profiler&#41;](stop-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c4e5d-115">[Очистка окна трассировки &#40;SQL Server Profiler&#41;](clear-a-trace-window-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c4e5d-115">[Clear a Trace Window &#40;SQL Server Profiler&#41;](clear-a-trace-window-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="c4e5d-116">Проведение трассировки после паузы или остановки (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="c4e5d-116">Run a Trace After It Has Been Paused or Stopped &#40;SQL Server Profiler&#41;</span></span>](run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
  
