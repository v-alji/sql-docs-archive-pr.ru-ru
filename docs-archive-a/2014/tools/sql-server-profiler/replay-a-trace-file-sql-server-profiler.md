---
title: Воспроизвести файл трассировки (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 9e361275-c8fd-4499-8389-242cf8e27415
author: stevestein
ms.author: sstein
ms.openlocfilehash: d3a9f007b9b6d2b46be43abdb10db286a75c33fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737244"
---
# <a name="replay-a-trace-file-sql-server-profiler"></a><span data-ttu-id="8c885-102">воспроизвести файл трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="8c885-102">Replay a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="8c885-103">Воспроизведением называется возможность открывать сохраненную трассировку и снова ее воспроизводить.</span><span class="sxs-lookup"><span data-stu-id="8c885-103">Replay is the ability to open a saved trace and replay it again.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="8c885-104">содержит в себе многопоточный модуль воспроизведения, который имитирует соединения пользователей и проверку подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8c885-104">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="8c885-105">Воспроизведение хорошо помогает при диагностике ошибок приложений и процессов.</span><span class="sxs-lookup"><span data-stu-id="8c885-105">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="8c885-106">Отыскав и исправив ошибку, запустите трассировку, обнаружившую эту ошибку, в отношении исправленной версии приложения или процесса.</span><span class="sxs-lookup"><span data-stu-id="8c885-106">When you identify the problem and implement corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="8c885-107">а затем, после воспроизведения исходной трассировки, сравнить результаты.</span><span class="sxs-lookup"><span data-stu-id="8c885-107">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="8c885-108">Чтобы воспроизведение было возможным, необходимо помимо классов событий, отобранных для отслеживания, фиксировать и специальные классы событий.</span><span class="sxs-lookup"><span data-stu-id="8c885-108">In addition to any other event classes you want to monitor, specific event classes must be captured to enable replay.</span></span> <span data-ttu-id="8c885-109">Эти события фиксируются по умолчанию при использовании шаблона трассировки **TSQL_Replay** .</span><span class="sxs-lookup"><span data-stu-id="8c885-109">These events are captured by default if you use the **TSQL_Replay** trace template.</span></span> <span data-ttu-id="8c885-110">Дополнительные сведения см. в разделе [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c885-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
### <a name="to-replay-a-trace-file"></a><span data-ttu-id="8c885-111">Воспроизведение файла трассировки</span><span class="sxs-lookup"><span data-stu-id="8c885-111">To replay a trace file</span></span>  
  
1.  <span data-ttu-id="8c885-112">В меню **Файл** выберите **Открыть**, а затем выберите пункт **Файл трассировки**.</span><span class="sxs-lookup"><span data-stu-id="8c885-112">On the **File** menu, point to **Open**, and then click **Trace File**.</span></span> <span data-ttu-id="8c885-113">Выберите файл трассировки, содержащий классы событий, необходимые для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="8c885-113">Select a trace file that contains the event classes necessary for replay.</span></span>  
  
2.  <span data-ttu-id="8c885-114">В меню **Воспроизведение** выберите **Начать**и установите соединение с экземпляром сервера, на котором требуется воспроизвести трассировку.</span><span class="sxs-lookup"><span data-stu-id="8c885-114">On the **Replay** menu, click **Start**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="8c885-115">В диалоговом окне **Конфигурация воспроизведения** на вкладке **Основные параметры воспроизведения** укажите **Сервер воспроизведения**.</span><span class="sxs-lookup"><span data-stu-id="8c885-115">In the **Replay Configuration** dialog box, on the **Basic Replay Options** tab, specify the **Replay server**.</span></span> <span data-ttu-id="8c885-116">Нажмите кнопку **Изменить** , чтобы сменить сервер, отображаемый в поле **Сервер воспроизведения** .</span><span class="sxs-lookup"><span data-stu-id="8c885-116">Click **Change** to change the server displayed in the **Replay server** box.</span></span>  
  
4.  <span data-ttu-id="8c885-117">По желанию можно выбрать одно из следующих мест назначения, где можно сохранить воспроизведение:</span><span class="sxs-lookup"><span data-stu-id="8c885-117">Optionally, select one of the following destinations in which to save the replay:</span></span>  
  
    -   <span data-ttu-id="8c885-118">**Сохранить в файл**, что указывает на файл, в котором должно быть сохранено воспроизведение.</span><span class="sxs-lookup"><span data-stu-id="8c885-118">**Save to file**, which specifies a file in which to save the replay.</span></span>  
  
    -   <span data-ttu-id="8c885-119">**Сохранить в таблицу**позволяет указать таблицу базы данных, в которую будут записаны результаты воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="8c885-119">**Save to table**, which specifies a database table in which to save the replay.</span></span>  
  
5.  <span data-ttu-id="8c885-120">Выберите либо **Воспроизвести события в порядке трассировки**, либо **Воспроизвести события, используя несколько потоков**.</span><span class="sxs-lookup"><span data-stu-id="8c885-120">Choose either **Replay the events in the order they were traced**or **Replay events using multiple threads**.</span></span> <span data-ttu-id="8c885-121">В нижеследующей таблице объясняются различия между этими параметрами.</span><span class="sxs-lookup"><span data-stu-id="8c885-121">The following table explains the difference between these settings.</span></span>  
  
    |<span data-ttu-id="8c885-122">Параметр</span><span class="sxs-lookup"><span data-stu-id="8c885-122">Option</span></span>|<span data-ttu-id="8c885-123">Description</span><span class="sxs-lookup"><span data-stu-id="8c885-123">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="8c885-124">**Воспроизвести события в порядке трассировки**</span><span class="sxs-lookup"><span data-stu-id="8c885-124">**Replay events in the order they were traced**</span></span>|<span data-ttu-id="8c885-125">Воспроизводит события в том порядке, в котором они были записаны.</span><span class="sxs-lookup"><span data-stu-id="8c885-125">Replays events in the order they were recorded.</span></span> <span data-ttu-id="8c885-126">Выбор этого параметра включает возможность отладки.</span><span class="sxs-lookup"><span data-stu-id="8c885-126">This option enables debugging.</span></span>|  
    |<span data-ttu-id="8c885-127">**Воспроизвести события, используя несколько потоков**</span><span class="sxs-lookup"><span data-stu-id="8c885-127">**Replay events using multiple threads**</span></span>|<span data-ttu-id="8c885-128">В этом варианте используются несколько потоков для воспроизведения каждого события независимо от последовательности.</span><span class="sxs-lookup"><span data-stu-id="8c885-128">This option uses multiple threads to replay each event regardless of the sequence.</span></span> <span data-ttu-id="8c885-129">Выбор этого параметра способствует оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="8c885-129">This option optimizes performance.</span></span>|  
  
6.  <span data-ttu-id="8c885-130">Чтобы проследить за ходом воспроизведения, выберите **Отобразить результаты воспроизведения** .</span><span class="sxs-lookup"><span data-stu-id="8c885-130">Select **Display replay results** to view the replay as it occurs.</span></span>  
  
7.  <span data-ttu-id="8c885-131">При необходимости выберите вкладку **Дополнительные параметры воспроизведения**, чтобы настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8c885-131">Optionally click the **Advanced Replay Options**tab to configure the following options:</span></span>  
  
    -   <span data-ttu-id="8c885-132">Чтобы воспроизвести все идентификаторы серверных процессов (SPID), выберите **Воспроизвести системные SPID**.</span><span class="sxs-lookup"><span data-stu-id="8c885-132">To replay all server process IDs (SPIDs), select **Replay system SPIDs**.</span></span>  
  
    -   <span data-ttu-id="8c885-133">Чтобы ограничить воспроизведение процессами, принадлежащими конкретному SPID, выберите **Воспроизвести только один SPID**.</span><span class="sxs-lookup"><span data-stu-id="8c885-133">To limit the replay to processes belonging to a specific SPID, select **Replay one SPID only**.</span></span> <span data-ttu-id="8c885-134">В поле **SPID для воспроизведения** введите SPID.</span><span class="sxs-lookup"><span data-stu-id="8c885-134">In the **SPID to replay** box, type the SPID.</span></span>  
  
    -   <span data-ttu-id="8c885-135">Чтобы воспроизвести события, имевшие место в течение определенного временного периода, выберите **Ограничить воспроизведение по дате и времени**.</span><span class="sxs-lookup"><span data-stu-id="8c885-135">To replay events that occurred during a specific time period, select **Limit the replay by date and time**.</span></span> <span data-ttu-id="8c885-136">Выберите дату и время для параметров **Время запуска**и **Время окончания**, чтобы указать период для включения в воспроизведение.</span><span class="sxs-lookup"><span data-stu-id="8c885-136">Select a date and time for the **Start time**and **End time**to specify the time period to include in the replay.</span></span>  
  
    -   <span data-ttu-id="8c885-137">Чтобы контролировать, как SQL Server управляет процессами в ходе воспроизведения, настройте **Параметры монитора исправности**.</span><span class="sxs-lookup"><span data-stu-id="8c885-137">To control how SQL Server manages processes during replay, configure **Health Monitor Options**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c885-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="8c885-138">See Also</span></span>  
 <span data-ttu-id="8c885-139">[Разрешения, необходимые для запуска приложения SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="8c885-139">[Permissions Required to Run SQL Server Profiler](sql-server-profiler.md) </span></span>  
 <span data-ttu-id="8c885-140">[Воспроизведение трассировок](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="8c885-140">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="8c885-141">[Открытие файла трассировки (приложение SQL Server Profiler)](open-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="8c885-141">[Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="8c885-142">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8c885-142">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
