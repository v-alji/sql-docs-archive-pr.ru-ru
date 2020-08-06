---
title: Параметры воспроизведения (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
- health monitor [SQL Server]
- Replay Configuration dialog box
ms.assetid: 58761a25-a84f-4a90-9c61-97700bc5ad9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 695a1431145813f0a7829626a380e510d0e602e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737241"
---
# <a name="replay-options-sql-server-profiler"></a><span data-ttu-id="2ee56-102">Параметры воспроизведения (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="2ee56-102">Replay Options (SQL Server Profiler)</span></span>
  <span data-ttu-id="2ee56-103">Перед воспроизведением захваченной трассировки с помощью приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]задайте параметры воспроизведения в диалоговом окне **Конфигурация воспроизведения** .</span><span class="sxs-lookup"><span data-stu-id="2ee56-103">Before replaying a captured trace with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], specify replay options in the **Replay Configuration** dialog box.</span></span> <span data-ttu-id="2ee56-104">Чтобы открыть его, откройте файл трассировки воспроизведения в приложении [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]и в меню **Воспроизведение** выберите **Запуск**.</span><span class="sxs-lookup"><span data-stu-id="2ee56-104">To launch this dialog box, open the replay trace file or table in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], and on the **Replay** menu, click **Start**.</span></span> <span data-ttu-id="2ee56-105">Сведения о разрешениях, необходимых для воспроизведения трассировки, см. в разделе [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="2ee56-105">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
 <span data-ttu-id="2ee56-106">В этом разделе приводится описание параметров, которые задаются в диалоговом окне **Конфигурация воспроизведения** .</span><span class="sxs-lookup"><span data-stu-id="2ee56-106">This topic describes the options specified with the **Replay Configuration** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ee56-107">Для воспроизведения ресурсоемких приложений OLTP (с множеством одновременных активных соединений или высокой пропускной способностью) рекомендуется пользоваться программой распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="2ee56-107">We recommend using the Distributed Replay Utility for replaying an intensive OLTP application (with many active concurrent connections or high throughput).</span></span> <span data-ttu-id="2ee56-108">Программа распределенного воспроизведения воспроизводит данные трассировки с нескольких компьютеров и лучше имитирует важную рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="2ee56-108">The Distributed Replay Utility can replay trace data from multiple computers, better simulating a mission-critical workload.</span></span> <span data-ttu-id="2ee56-109">Дополнительные сведения см. в статье [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="2ee56-109">For more information, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
## <a name="basic-replay-options"></a><span data-ttu-id="2ee56-110">Основные параметры воспроизведения</span><span class="sxs-lookup"><span data-stu-id="2ee56-110">Basic Replay Options</span></span>  
 <span data-ttu-id="2ee56-111">**Сервер воспроизведения**</span><span class="sxs-lookup"><span data-stu-id="2ee56-111">**Replay server**</span></span>  
 <span data-ttu-id="2ee56-112">Сервер — имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , на котором будет воспроизведена трассировка.</span><span class="sxs-lookup"><span data-stu-id="2ee56-112">The server is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] against which you want to replay the trace.</span></span> <span data-ttu-id="2ee56-113">Сервер должен отвечать требованиям воспроизведения, описанным в разделе [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ee56-113">The server must adhere to the replay requirements described in [Replay Requirements](replay-requirements.md)."</span></span>  
  
 <span data-ttu-id="2ee56-114">**Сохранить в файл**</span><span class="sxs-lookup"><span data-stu-id="2ee56-114">**Save to file**</span></span>  
 <span data-ttu-id="2ee56-115">Выходной файл, куда будут записываться результаты воспроизведения трассировки для дальнейшего просмотра.</span><span class="sxs-lookup"><span data-stu-id="2ee56-115">The output file where the result of replaying the trace is written for later viewing.</span></span> <span data-ttu-id="2ee56-116">По умолчанию приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] отображает только результаты трассировки, воспроизводящейся на экране.</span><span class="sxs-lookup"><span data-stu-id="2ee56-116">By default, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] displays only the results of replaying the trace on the screen.</span></span>  
  
 <span data-ttu-id="2ee56-117">**Сохранить в таблицу**</span><span class="sxs-lookup"><span data-stu-id="2ee56-117">**Save to table**</span></span>  
 <span data-ttu-id="2ee56-118">Таблица базы данных, куда будут записываться результаты воспроизведения трассировки для дальнейшего просмотра.</span><span class="sxs-lookup"><span data-stu-id="2ee56-118">The database table where the result of replaying the trace is written for later viewing.</span></span>  
  
 <span data-ttu-id="2ee56-119">**Число потоков воспроизведения**</span><span class="sxs-lookup"><span data-stu-id="2ee56-119">**Number of replay threads**</span></span>  
 <span data-ttu-id="2ee56-120">Задайте число потоков воспроизведения, используемых одновременно.</span><span class="sxs-lookup"><span data-stu-id="2ee56-120">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="2ee56-121">Большее число потребует больших ресурсов во время воспроизведения, но само воспроизведение будет выполняться быстрее.</span><span class="sxs-lookup"><span data-stu-id="2ee56-121">A higher number consumes more resources during replay, but replay is faster.</span></span> <span data-ttu-id="2ee56-122">При многопоточном воспроизведении порядок возникновения событий поддерживается неполностью.</span><span class="sxs-lookup"><span data-stu-id="2ee56-122">Event ordering is not fully maintained when multiple threads are used.</span></span>  
  
 <span data-ttu-id="2ee56-123">**Воспроизвести события в порядке трассировки**</span><span class="sxs-lookup"><span data-stu-id="2ee56-123">**Replay events in the order they were traced**</span></span>  
 <span data-ttu-id="2ee56-124">Позволяет использовать методы отладки, например пошаговое прохождение каждой трассировки.</span><span class="sxs-lookup"><span data-stu-id="2ee56-124">Allows you to use debugging methods such as stepping through each trace.</span></span> <span data-ttu-id="2ee56-125">Если этот флажок не установлен, воспроизведение не гарантирует, что события будут воспроизведены в порядке их захвата.</span><span class="sxs-lookup"><span data-stu-id="2ee56-125">If this option is not selected, replay does not guarantee that events are replayed in an order that is consistent with the order in which events were originally captured.</span></span>  
  
 <span data-ttu-id="2ee56-126">**Воспроизвести события, используя несколько потоков**</span><span class="sxs-lookup"><span data-stu-id="2ee56-126">**Replay events using multiple threads**</span></span>  
 <span data-ttu-id="2ee56-127">Улучшает производительность и отключает отладку.</span><span class="sxs-lookup"><span data-stu-id="2ee56-127">Optimizes performance and disables debugging.</span></span> <span data-ttu-id="2ee56-128">События воспроизводятся в порядке, в котором они были записаны для определенного идентификатора процесса сервера (SPID), но упорядочение идентификаторов SPID не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="2ee56-128">Events are replayed in the order they were recorded for a particular server process ID (SPID), but ordering of SPIDs is not guaranteed.</span></span>  
  
 <span data-ttu-id="2ee56-129">**Отобразить результаты воспроизведения**</span><span class="sxs-lookup"><span data-stu-id="2ee56-129">**Display replay results**</span></span>  
 <span data-ttu-id="2ee56-130">Отобразить результаты воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="2ee56-130">Display the results of the replay.</span></span> <span data-ttu-id="2ee56-131">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ee56-131">This is the default option.</span></span> <span data-ttu-id="2ee56-132">Если воспроизводимая трассировка очень велика, этот флажок можно снять, чтобы сэкономить место на диске.</span><span class="sxs-lookup"><span data-stu-id="2ee56-132">If the trace you are replaying is very large, you may want to disable this to save disk space.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ee56-133">Для достижения наилучшей производительности рекомендуется воспроизводить события с помощью нескольких потоков и не отображать результаты воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="2ee56-133">For best replay performance, we recommend that you select to replay events using multiple threads, and do not select to display the replay results.</span></span>  
  
## <a name="advanced-replay-options"></a><span data-ttu-id="2ee56-134">Дополнительные параметры воспроизведения</span><span class="sxs-lookup"><span data-stu-id="2ee56-134">Advanced Replay Options</span></span>  
 <span data-ttu-id="2ee56-135">**Воспроизвести системные SPID**</span><span class="sxs-lookup"><span data-stu-id="2ee56-135">**Replay system SPIDs**</span></span>  
 <span data-ttu-id="2ee56-136">Воспроизвести все системные SPID.</span><span class="sxs-lookup"><span data-stu-id="2ee56-136">Replay all SPIDs.</span></span> <span data-ttu-id="2ee56-137">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ee56-137">This is the default option.</span></span>  
  
 <span data-ttu-id="2ee56-138">**Воспроизвести только один SPID**</span><span class="sxs-lookup"><span data-stu-id="2ee56-138">**Replay one SPID only**</span></span>  
 <span data-ttu-id="2ee56-139">Воспроизвести SPID, выбранный из списка.</span><span class="sxs-lookup"><span data-stu-id="2ee56-139">Replays the SPID number you choose from the list.</span></span>  
  
 <span data-ttu-id="2ee56-140">**Ограничить воспроизведение по дате и времени**</span><span class="sxs-lookup"><span data-stu-id="2ee56-140">**Limit replay by date and time**</span></span>  
 <span data-ttu-id="2ee56-141">Воспроизвести трассировку от указанного **Времени начала** до **Времени окончания**.</span><span class="sxs-lookup"><span data-stu-id="2ee56-141">Replays the trace for the specified **Start time** and **End time**.</span></span>  
  
 <span data-ttu-id="2ee56-142">**Интервал ожидания монитора исправности**</span><span class="sxs-lookup"><span data-stu-id="2ee56-142">**Health monitor wait interval**</span></span>  
 <span data-ttu-id="2ee56-143">Определяет количество времени, в течение которого процесс может выполняться, до того момента, как монитор исправности прекратит его.</span><span class="sxs-lookup"><span data-stu-id="2ee56-143">Sets the amount of time a process is allowed to run before the health monitor terminates it.</span></span>  
  
 <span data-ttu-id="2ee56-144">**Интервал опроса монитора исправности**</span><span class="sxs-lookup"><span data-stu-id="2ee56-144">**Health monitor poll interval**</span></span>  
 <span data-ttu-id="2ee56-145">Как часто монитор исправности будет опрашивать кандидаты на прекращение.</span><span class="sxs-lookup"><span data-stu-id="2ee56-145">Sets how often the health monitor polls candidates for termination.</span></span>  
  
 <span data-ttu-id="2ee56-146">**Включить монитор заблокированных процессов SQL Server**</span><span class="sxs-lookup"><span data-stu-id="2ee56-146">**Enable SQL Server blocked processes monitor**</span></span>  
 <span data-ttu-id="2ee56-147">Как часто монитор заблокированных процессов будет искать заблокированные или блокирующие процессы.</span><span class="sxs-lookup"><span data-stu-id="2ee56-147">Sets how often the blocked processes monitor searches for blocked or blocking processes.</span></span>  
  
## <a name="about-the-health-monitor"></a><span data-ttu-id="2ee56-148">О мониторе исправности</span><span class="sxs-lookup"><span data-stu-id="2ee56-148">About the Health Monitor</span></span>  
 <span data-ttu-id="2ee56-149">Монитор исправности — это поток приложения, который контролирует имитируемые процессы воспроизведения трассировки и завершает их, если во время воспроизведения они блокируются.</span><span class="sxs-lookup"><span data-stu-id="2ee56-149">The health monitor is an application thread that monitors the simulated processes involved in replaying a trace, and ends those processes that are blocked within the replay.</span></span> <span data-ttu-id="2ee56-150">На вкладке **Дополнительные параметры воспроизведения** диалогового окна **Конфигурация воспроизведения** можно указать, как долго (в секундах) монитор исправности будет ждать перед прекращением заблокированного процесса (**Интервал ожидания монитора исправности**).</span><span class="sxs-lookup"><span data-stu-id="2ee56-150">In the **Advanced Replay Options** tab of the **Replay Configuration** dialog box, you can specify how long the health monitor should wait in seconds before ending a blocked process (**Health monitor wait interval**).</span></span> <span data-ttu-id="2ee56-151">Если задать этому параметру значение 0, монитор исправности никогда не будет прекращать имитируемые процессы воспроизведения трассировки.</span><span class="sxs-lookup"><span data-stu-id="2ee56-151">If you set this interval to 0, the health monitor never ends simulated blocking processes in the replaying trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee56-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="2ee56-152">See Also</span></span>  
 <span data-ttu-id="2ee56-153">[Воспроизведение трассировок](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="2ee56-153">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="2ee56-154">[Требования к воспроизведению](replay-requirements.md) </span><span class="sxs-lookup"><span data-stu-id="2ee56-154">[Replay Requirements](replay-requirements.md) </span></span>  
 [<span data-ttu-id="2ee56-155">Вопросы воспроизведения трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="2ee56-155">Considerations for Replaying Traces &#40;SQL Server Profiler&#41;</span></span>](considerations-for-replaying-traces-sql-server-profiler.md)  
  
  
