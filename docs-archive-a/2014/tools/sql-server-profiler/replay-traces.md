---
title: Воспроизвести трассировки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, replaying traces
- Run to Cursor option
- Toggle Breakpoint option
- traces [SQL Server], replaying
- replaying traces
- playback engine [SQL Server Profiler]
- events [SQL Server], replaying traces
- Profiler [SQL Server Profiler], replaying traces
ms.assetid: da958d3c-7f3e-44c9-aecc-8a9493bea7c0
author: stevestein
ms.author: sstein
ms.openlocfilehash: c485317d1343958f9c430b73d858130097d44d75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737229"
---
# <a name="replay-traces"></a><span data-ttu-id="77a4c-102">Воспроизведение трассировок</span><span class="sxs-lookup"><span data-stu-id="77a4c-102">Replay Traces</span></span>
  <span data-ttu-id="77a4c-103">Воспроизведением называется возможность повторить действие, захваченное в трассировке.</span><span class="sxs-lookup"><span data-stu-id="77a4c-103">Replay is the ability to reproduce activity that has been captured in a trace.</span></span> <span data-ttu-id="77a4c-104">После создания или редактирования трассировки ее можно сохранить в файл и позже воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="77a4c-104">When you create or edit a trace, you can save the trace to a file and replay it later.</span></span> <span data-ttu-id="77a4c-105">Приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] позволяет воспроизводить трассировку с одного компьютера.</span><span class="sxs-lookup"><span data-stu-id="77a4c-105">You can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to replay trace activity from a single computer.</span></span> <span data-ttu-id="77a4c-106">При высокой рабочей нагрузке используйте программу распределенного воспроизведения, которая позволяет воспроизводить данные трассировки с нескольких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="77a4c-106">For large workloads, use the Distributed Replay Utility to replay trace data from multiple computers.</span></span>  
  
 <span data-ttu-id="77a4c-107">В этом разделе описывается использование возможностей воспроизведения приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77a4c-107">This section describes how to use the replay features of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="77a4c-108">Дополнительные сведения о программе распределенного воспроизведения см. в разделе [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="77a4c-108">For more information about the Distributed Replay Utility, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="77a4c-109">содержит в себе многопоточный модуль воспроизведения, который имитирует соединения пользователей и проверку подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77a4c-109">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="77a4c-110">Воспроизведение хорошо помогает при диагностике ошибок приложений и процессов.</span><span class="sxs-lookup"><span data-stu-id="77a4c-110">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="77a4c-111">После изучения проблемы и внесения необходимых изменений можно снова запустить трассировку, которая обнаружила эту проблему, на исправленном приложении или процессе,</span><span class="sxs-lookup"><span data-stu-id="77a4c-111">When you have identified the problem and implemented corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="77a4c-112">а затем, после воспроизведения исходной трассировки, сравнить результаты.</span><span class="sxs-lookup"><span data-stu-id="77a4c-112">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="77a4c-113">Воспроизведение трассировки поддерживает отладку с использованием параметров **Точка останова** и **Выполнить до курсора** в меню **Воспроизведение** в [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77a4c-113">Trace replay supports debugging by using the **Toggle Breakpoint** and the **Run to Cursor** options on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Replay** menu.</span></span> <span data-ttu-id="77a4c-114">Эти команды особенно помогают при анализе длинных скриптов, позволяя разбить воспроизведение на короткие сегменты, которые могут быть последовательно проанализированы.</span><span class="sxs-lookup"><span data-stu-id="77a4c-114">These options especially improve the analysis of long scripts because they can break the replay of the trace into short segments so they can be analyzed incrementally.</span></span>  
  
 <span data-ttu-id="77a4c-115">Сведения о том, какие разрешения необходимы для воспроизведения трассировки, см. в статье [Разрешения, необходимые для запуска приложения SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="77a4c-115">For information about the permissions required to replay traces, see [Permissions Required to Run SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77a4c-116">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="77a4c-116">In This Section</span></span>  
  
|<span data-ttu-id="77a4c-117">Раздел</span><span class="sxs-lookup"><span data-stu-id="77a4c-117">Topic</span></span>|<span data-ttu-id="77a4c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="77a4c-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="77a4c-119">Требования к воспроизведению</span><span class="sxs-lookup"><span data-stu-id="77a4c-119">Replay Requirements</span></span>](replay-requirements.md)|<span data-ttu-id="77a4c-120">Описывает события, которые могут быть включены в определение трассировки для последующего воспроизведения в приложении [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77a4c-120">Describes the events that must be included in a trace definition so that it can be replayed with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="77a4c-121">Параметры воспроизведения (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="77a4c-121">Replay Options &#40;SQL Server Profiler&#41;</span></span>](replay-options-sql-server-profiler.md)|<span data-ttu-id="77a4c-122">Описывает параметры, устанавливаемые в диалоговом окне **Конфигурация воспроизведения** приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77a4c-122">Describes the options you can set in the **Replay Configuration** dialog box of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="77a4c-123">Вопросы воспроизведения трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="77a4c-123">Considerations for Replaying Traces &#40;SQL Server Profiler&#41;</span></span>](considerations-for-replaying-traces-sql-server-profiler.md)|<span data-ttu-id="77a4c-124">Описывает события трассировки, которые не могут быть воспроизведены в приложении [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , и влияние воспроизведения на производительность работы сервера.</span><span class="sxs-lookup"><span data-stu-id="77a4c-124">Describes trace events that can not be replayed with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and the effects on server performance of replaying traces.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77a4c-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="77a4c-125">See Also</span></span>  
 [<span data-ttu-id="77a4c-126">Распределенное воспроизведение SQL Server</span><span class="sxs-lookup"><span data-stu-id="77a4c-126">SQL Server Distributed Replay</span></span>](../distributed-replay/sql-server-distributed-replay.md)  
  
  
