---
title: Конфигурация SQL Server Profiler воспроизведения (дополнительные параметры воспроизведения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.generaloptions.advanced.f1
helpviewer_keywords:
- Replay Configuration dialog box
ms.assetid: b4eb34f7-3af6-4a44-ba7e-2b8430ec3cd7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 95070d8defb5b7778859ce470aaa8cfc85955ba6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736692"
---
# <a name="sql-server-profiler---replay-configuration-advanced-replay-options"></a><span data-ttu-id="a329c-102">Приложение SQL Server Profiler — Конфигурация воспроизведения (дополнительные параметры воспроизведения)</span><span class="sxs-lookup"><span data-stu-id="a329c-102">SQL Server Profiler - Replay Configuration (Advanced Replay Options)</span></span>
  <span data-ttu-id="a329c-103">В диалоговом окне **Конфигурация воспроизведения** используйте вкладку **Дополнительные параметры воспроизведения** для задания способа воспроизведения файла трассировки.</span><span class="sxs-lookup"><span data-stu-id="a329c-103">In the **Replay Configuration** dialog box, use the **Advanced Replay Options** tab to specify how to replay a trace file.</span></span>  
  
 <span data-ttu-id="a329c-104">Для просмотра этого окна используйте приложение [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] для открытия файла трассировки или таблицы, содержащей события, предназначенные для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="a329c-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace file or table that contains the appropriate events for replay.</span></span> <span data-ttu-id="a329c-105">Дополнительные сведения см. в разделе [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a329c-105">For more information, see [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span></span> <span data-ttu-id="a329c-106">После открытия файла трассировки или таблицы в меню **Воспроизвести** выберите команду **Запустить**, соединитесь с экземпляром SQL Server, содержащим необходимую трассировку, и перейдите на вкладку **Дополнительные параметры воспроизведения** .</span><span class="sxs-lookup"><span data-stu-id="a329c-106">While the trace file or table is open, on the **Replay** menu, click **Start**, connect to the instance of SQL Server where you want to replay the trace, and then click the **Advanced Replay Options** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a329c-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="a329c-107">Options</span></span>  
 <span data-ttu-id="a329c-108">**Воспроизвести системные SPID**</span><span class="sxs-lookup"><span data-stu-id="a329c-108">**Replay system SPIDs**</span></span>  
 <span data-ttu-id="a329c-109">Указывает, воспроизводит ли приложение [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] идентификаторы системных процессов (SPID).</span><span class="sxs-lookup"><span data-stu-id="a329c-109">Specifies whether [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] replays system process identifiers (SPIDs).</span></span>  
  
 <span data-ttu-id="a329c-110">**Воспроизвести только один SPID**</span><span class="sxs-lookup"><span data-stu-id="a329c-110">**Replay one SPID only**</span></span>  
 <span data-ttu-id="a329c-111">Воспроизводится только деятельность в файле трассировки источника, относящемся к выбранному SPID.</span><span class="sxs-lookup"><span data-stu-id="a329c-111">Replays only the activity in the source trace file that is related to the selected SPID.</span></span>  
  
 <span data-ttu-id="a329c-112">**SPID для воспроизведения**</span><span class="sxs-lookup"><span data-stu-id="a329c-112">**SPID to replay**</span></span>  
 <span data-ttu-id="a329c-113">Задает SPID для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="a329c-113">Specify which SPID to replay.</span></span>  
  
 <span data-ttu-id="a329c-114">**Ограничить воспроизведение по дате и времени**</span><span class="sxs-lookup"><span data-stu-id="a329c-114">**Limit replay by date and time**</span></span>  
 <span data-ttu-id="a329c-115">Установите для воспроизведения только части файла трассировки источника.</span><span class="sxs-lookup"><span data-stu-id="a329c-115">Check to replay only a portion of the source trace file.</span></span>  
  
 <span data-ttu-id="a329c-116">**Время начала**</span><span class="sxs-lookup"><span data-stu-id="a329c-116">**Start time**</span></span>  
 <span data-ttu-id="a329c-117">Дата и время из файла трассировки источника, когда должно начаться воспроизведение.</span><span class="sxs-lookup"><span data-stu-id="a329c-117">Date and time in the source trace file where the replay should start.</span></span>  
  
 <span data-ttu-id="a329c-118">**Время окончания**</span><span class="sxs-lookup"><span data-stu-id="a329c-118">**End time**</span></span>  
 <span data-ttu-id="a329c-119">Дата и время из файла трассировки источника, когда должно завершиться воспроизведение.</span><span class="sxs-lookup"><span data-stu-id="a329c-119">Date and time in the source trace file where the replay should stop.</span></span>  
  
 <span data-ttu-id="a329c-120">**Интервал ожидания монитора исправности (сек)**</span><span class="sxs-lookup"><span data-stu-id="a329c-120">**Health monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="a329c-121">Задает интервал ожидания воспроизведения в секундах.</span><span class="sxs-lookup"><span data-stu-id="a329c-121">Specify the wait interval to replay in seconds.</span></span> <span data-ttu-id="a329c-122">По умолчанию — 3 600 секунд (1 час).</span><span class="sxs-lookup"><span data-stu-id="a329c-122">Default is 3600 seconds (1 hour).</span></span> <span data-ttu-id="a329c-123">Эта установка влияет на количество времени, предоставляемое для выполнения процесса, по истечении которого монитор исправности прерывает процесс.</span><span class="sxs-lookup"><span data-stu-id="a329c-123">This setting affects the amount of time a process is allowed to run before being terminated by the health monitor.</span></span>  
  
 <span data-ttu-id="a329c-124">**Интервал опроса монитора исправности (сек)**</span><span class="sxs-lookup"><span data-stu-id="a329c-124">**Health monitor poll interval (sec)**</span></span>  
 <span data-ttu-id="a329c-125">Задайте интервал опроса монитора исправности во время воспроизведения в секундах.</span><span class="sxs-lookup"><span data-stu-id="a329c-125">Specify the health monitor poll interval during replay in seconds.</span></span> <span data-ttu-id="a329c-126">По умолчанию — 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="a329c-126">Default is 60 seconds.</span></span> <span data-ttu-id="a329c-127">Это значение дает возможность пользователю определить, как часто монитор исправности выполняет опрос кандидатов на завершение.</span><span class="sxs-lookup"><span data-stu-id="a329c-127">This value allows the user to configure how often the health monitor polls for candidates for termination.</span></span>  
  
 <span data-ttu-id="a329c-128">**Включить монитор заблокированных процессов SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a329c-128">**Enable SQL Server blocked processes monitor**</span></span>  
 <span data-ttu-id="a329c-129">Включает процесс, который ищет блокированные или блокирующие процессы.</span><span class="sxs-lookup"><span data-stu-id="a329c-129">Enables a process that searches for blocked or blocking processes.</span></span>  
  
 <span data-ttu-id="a329c-130">**Интервал ожидания монитора заблокированных процессов (сек)**</span><span class="sxs-lookup"><span data-stu-id="a329c-130">**Blocked processes monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="a329c-131">Устанавливает, как часто монитор заблокированных процессов ищет заблокированные или блокирующие процессы.</span><span class="sxs-lookup"><span data-stu-id="a329c-131">Configures how often the blocked processes monitor searches for blocked or blocking processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a329c-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="a329c-132">See Also</span></span>  
 <span data-ttu-id="a329c-133">[Воспроизведение таблицы трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="a329c-133">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="a329c-134">[Воспроизведение файла трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="a329c-134">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="a329c-135">Воспроизведение трассировок</span><span class="sxs-lookup"><span data-stu-id="a329c-135">Replay Traces</span></span>](../tools/sql-server-profiler/replay-traces.md)  
  
  
