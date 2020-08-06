---
title: Воспроизвести таблицу трассировки (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 6a0ad817-3d8d-4495-889d-c66a7ef9e8bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: f3c26858fa852686bc3d9ccf4a26d47e04852647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733386"
---
# <a name="replay-a-trace-table-sql-server-profiler"></a><span data-ttu-id="e527f-102">воспроизвести таблицу трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="e527f-102">Replay a Trace Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="e527f-103">Воспроизведением называется возможность открывать сохраненную трассировку и снова ее воспроизводить.</span><span class="sxs-lookup"><span data-stu-id="e527f-103">Replay is the ability to open a saved trace and replay it again.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="e527f-104">содержит в себе многопоточный модуль воспроизведения, который имитирует соединения пользователей и проверку подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e527f-104">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="e527f-105">Воспроизведение хорошо помогает при диагностике ошибок приложений и процессов.</span><span class="sxs-lookup"><span data-stu-id="e527f-105">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="e527f-106">Отыскав и исправив ошибку, запустите трассировку, обнаружившую эту ошибку, в отношении исправленной версии приложения или процесса.</span><span class="sxs-lookup"><span data-stu-id="e527f-106">When you identify the problem and implement corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="e527f-107">а затем, после воспроизведения исходной трассировки, сравнить результаты.</span><span class="sxs-lookup"><span data-stu-id="e527f-107">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="e527f-108">Чтобы воспроизведение было возможным, необходимо помимо классов событий, отобранных для отслеживания, фиксировать и специальные классы событий.</span><span class="sxs-lookup"><span data-stu-id="e527f-108">In addition to any other event classes you want to monitor, specific event classes must be captured to enable replay.</span></span> <span data-ttu-id="e527f-109">Эти события фиксируются по умолчанию при использовании шаблона трассировки **TSQL_Replay** .</span><span class="sxs-lookup"><span data-stu-id="e527f-109">These events are captured by default if you use the **TSQL_Replay** trace template.</span></span> <span data-ttu-id="e527f-110">Дополнительные сведения см. в разделе [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e527f-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
### <a name="to-replay-a-trace-table"></a><span data-ttu-id="e527f-111">Воспроизведение таблицы трассировки</span><span class="sxs-lookup"><span data-stu-id="e527f-111">To replay a trace table</span></span>  
  
1.  <span data-ttu-id="e527f-112">Откройте таблицу трассировки, которая содержит классы событий, необходимые для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="e527f-112">Open a trace table that contains the event classes necessary for replay.</span></span>  
  
2.  <span data-ttu-id="e527f-113">В меню **Воспроизведение** выберите **Начать**и установите соединение с экземпляром сервера, на котором требуется воспроизвести трассировку.</span><span class="sxs-lookup"><span data-stu-id="e527f-113">On the **Replay** menu, click **Start**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="e527f-114">В диалоговом окне **Настройка воспроизведения** на вкладке **Основные параметры воспроизведения** укажите **Сервер воспроизведения**.</span><span class="sxs-lookup"><span data-stu-id="e527f-114">In the **Replay Configuration** dialog box, on the **Basic Replay Options** tab, specify **Replay server**.</span></span> <span data-ttu-id="e527f-115">Нажмите кнопку **Изменить** , чтобы изменить сервер, который отображается в диалоговом окне **Сервер воспроизведения** .</span><span class="sxs-lookup"><span data-stu-id="e527f-115">Click **Change** to change the server that is displayed in the **Replay server** box.</span></span>  
  
4.  <span data-ttu-id="e527f-116">По желанию можно выбрать одно из следующих мест назначения, где можно сохранить воспроизведение:</span><span class="sxs-lookup"><span data-stu-id="e527f-116">Optionally, select one of the following destinations in which to save the replay:</span></span>  
  
    -   <span data-ttu-id="e527f-117">**Сохранить в файл** , что указывает на файл, в котором должно быть сохранено воспроизведение.</span><span class="sxs-lookup"><span data-stu-id="e527f-117">**Save to file,** which specifies a file in which to save the replay.</span></span>  
  
    -   <span data-ttu-id="e527f-118">**Сохранить в таблицу**позволяет указать таблицу базы данных, в которую будут записаны результаты воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="e527f-118">**Save to table**, which specifies a database table in which to save the replay.</span></span>  
  
5.  <span data-ttu-id="e527f-119">Выберите либо **Воспроизвести события в порядке трассировки**, либо **Воспроизвести события, используя несколько потоков**.</span><span class="sxs-lookup"><span data-stu-id="e527f-119">Choose either **Replay the events in the order they were traced**or **Replay events using multiple threads**.</span></span> <span data-ttu-id="e527f-120">В нижеследующей таблице объясняются различия между этими параметрами.</span><span class="sxs-lookup"><span data-stu-id="e527f-120">The following table explains the difference between these settings.</span></span>  
  
    |<span data-ttu-id="e527f-121">Параметр</span><span class="sxs-lookup"><span data-stu-id="e527f-121">Option</span></span>|<span data-ttu-id="e527f-122">Description</span><span class="sxs-lookup"><span data-stu-id="e527f-122">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="e527f-123">**Воспроизвести события в порядке трассировки**</span><span class="sxs-lookup"><span data-stu-id="e527f-123">**Replay events in the order they were traced**</span></span>|<span data-ttu-id="e527f-124">Воспроизводит события в том порядке, в котором они были записаны.</span><span class="sxs-lookup"><span data-stu-id="e527f-124">Replays events in the order they were recorded.</span></span> <span data-ttu-id="e527f-125">Выбор этого параметра включает возможность отладки.</span><span class="sxs-lookup"><span data-stu-id="e527f-125">This option enables debugging.</span></span>|  
    |<span data-ttu-id="e527f-126">**Воспроизвести события, используя несколько потоков**</span><span class="sxs-lookup"><span data-stu-id="e527f-126">**Replay events using multiple threads**</span></span>|<span data-ttu-id="e527f-127">В этом варианте используются несколько потоков для воспроизведения каждого события независимо от последовательности.</span><span class="sxs-lookup"><span data-stu-id="e527f-127">This option uses multiple threads to replay each event regardless of the sequence.</span></span> <span data-ttu-id="e527f-128">Выбор этого параметра способствует оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="e527f-128">This option optimizes performance.</span></span>|  
  
6.  <span data-ttu-id="e527f-129">Чтобы проследить за ходом воспроизведения, выберите **Отобразить результаты воспроизведения** .</span><span class="sxs-lookup"><span data-stu-id="e527f-129">Select **Display replay results** to view the replay as it occurs.</span></span>  
  
7.  <span data-ttu-id="e527f-130">При необходимости выберите вкладку **Дополнительные параметры воспроизведения**, чтобы задать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e527f-130">Optionally, click the **Advanced Replay Options**tab to specify the following options:</span></span>  
  
    -   <span data-ttu-id="e527f-131">Чтобы воспроизвести все идентификаторы серверных процессов (SPID), выберите **Воспроизвести системные SPID**.</span><span class="sxs-lookup"><span data-stu-id="e527f-131">To replay all server process IDs (SPIDs), select **Replay system SPIDs**.</span></span>  
  
    -   <span data-ttu-id="e527f-132">Чтобы ограничить воспроизведение процессами, принадлежащими конкретному SPID, выберите **Воспроизвести только один SPID**.</span><span class="sxs-lookup"><span data-stu-id="e527f-132">To limit the replay to processes belonging to a specific SPID, select **Replay one SPID only**.</span></span> <span data-ttu-id="e527f-133">В поле **SPID для воспроизведения**введите SPID.</span><span class="sxs-lookup"><span data-stu-id="e527f-133">In the **SPID to replay**box, type the SPID.</span></span>  
  
    -   <span data-ttu-id="e527f-134">чтобы воспроизвести события за определенный период времени, выберите **Предел воспроизведения по дате и времени**.</span><span class="sxs-lookup"><span data-stu-id="e527f-134">To replay events that occurred during a specific time period, select **Limit replay by date and time**.</span></span> <span data-ttu-id="e527f-135">Выберите дату и время для параметров **Время запуска**и **Время окончания**, чтобы указать период для включения в воспроизведение.</span><span class="sxs-lookup"><span data-stu-id="e527f-135">Select a date and time for the **Start time**and **End time**to specify the time period to include in the replay.</span></span>  
  
    -   <span data-ttu-id="e527f-136">чтобы указать, как сервер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен управлять процессами во время воспроизведения, настройте **Параметры монитора исправности**.</span><span class="sxs-lookup"><span data-stu-id="e527f-136">To control how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] manages processes during replay, configure **Health Monitor Options**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e527f-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="e527f-137">See Also</span></span>  
 <span data-ttu-id="e527f-138">[Разрешения, необходимые для запуска приложения SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e527f-138">[Permissions Required to Run SQL Server Profiler](sql-server-profiler.md) </span></span>  
 <span data-ttu-id="e527f-139">[Воспроизведение трассировок](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="e527f-139">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="e527f-140">[Открытие таблицы трассировки (приложение SQL Server Profiler)](open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e527f-140">[Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="e527f-141">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="e527f-141">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
