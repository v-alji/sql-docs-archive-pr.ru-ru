---
title: Конфигурация SQL Server Profiler воспроизведения (основные параметры воспроизведения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.generaloptions.f1
helpviewer_keywords:
- Replay Configuration dialog box
ms.assetid: 85a1dec6-9bbc-477a-86c5-b463db9ebb31
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cbf433c3108294909d91f7860136c0755b39b46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736686"
---
# <a name="sql-server-profiler---replay-configuration-basic-replay-options"></a><span data-ttu-id="93670-102">Приложение SQL Server Profiler — конфигурация воспроизведения (базовые параметры воспроизведения)</span><span class="sxs-lookup"><span data-stu-id="93670-102">SQL Server Profiler - Replay Configuration (Basic Replay Options)</span></span>
  <span data-ttu-id="93670-103">В диалоговом окне **Конфигурация воспроизведения** страница **Основные параметры воспроизведения** используется для указания способа воспроизведения файла или таблицы трассировки.</span><span class="sxs-lookup"><span data-stu-id="93670-103">In the **Replay Configuration** dialog box, use the **Basic Replay Options** page to specify how to replay a trace file or table.</span></span>  
  
 <span data-ttu-id="93670-104">Для просмотра этого окна используйте приложение [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] для открытия файла трассировки или таблицы, содержащей события, предназначенные для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="93670-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace file or table that contains the appropriate events for replay.</span></span> <span data-ttu-id="93670-105">Дополнительные сведения см. в разделе [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93670-105">For more information, see [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span></span> <span data-ttu-id="93670-106">Когда файл или таблица трассировки открыты, в меню **Воспроизведение** щелкните **Начать**, a затем подключитесь к экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , на котором необходимо воспроизвести трассировку.</span><span class="sxs-lookup"><span data-stu-id="93670-106">While the trace file or table is open, on the **Replay** menu, click **Start**, and then connect to the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] where you want to replay the trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="93670-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="93670-107">Options</span></span>  
 <span data-ttu-id="93670-108">**Сервер воспроизведения**</span><span class="sxs-lookup"><span data-stu-id="93670-108">**Replay server**</span></span>  
 <span data-ttu-id="93670-109">Отображает экземпляр сервера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для подключения с целью воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="93670-109">Displays the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to connect to for the replay.</span></span>  
  
 <span data-ttu-id="93670-110">**Изменить...**</span><span class="sxs-lookup"><span data-stu-id="93670-110">**Change...**</span></span>  
 <span data-ttu-id="93670-111">Запускает диалоговое окно **Соединение с сервером** для подключения к другому серверу.</span><span class="sxs-lookup"><span data-stu-id="93670-111">Launches the **Connect to Server** dialog box to connect to another server.</span></span>  
  
 <span data-ttu-id="93670-112">**Сохранить в файл**</span><span class="sxs-lookup"><span data-stu-id="93670-112">**Save to file**</span></span>  
 <span data-ttu-id="93670-113">Сохраняет результаты воспроизведения в файл.</span><span class="sxs-lookup"><span data-stu-id="93670-113">Save the replay results to a file.</span></span> [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="93670-114">отображает стандартное диалоговое окно, в котором можно указать место для сохранения файла.</span><span class="sxs-lookup"><span data-stu-id="93670-114">displays the standard file dialog, where you can specify the location to save the file.</span></span>  
  
 <span data-ttu-id="93670-115">**Сохранить в таблицу**</span><span class="sxs-lookup"><span data-stu-id="93670-115">**Save to table**</span></span>  
 <span data-ttu-id="93670-116">Сохраняет результаты воспроизведения в таблицу.</span><span class="sxs-lookup"><span data-stu-id="93670-116">Save the replay results to a table.</span></span> [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="93670-117">отображает диалоговое окно выбора таблицы, в котором можно указать место для сохранения таблицы.</span><span class="sxs-lookup"><span data-stu-id="93670-117">displays the table selection dialog, where you can specify the location to save the table.</span></span>  
  
 <span data-ttu-id="93670-118">**Число потоков воспроизведения**</span><span class="sxs-lookup"><span data-stu-id="93670-118">**Number of replay threads**</span></span>  
 <span data-ttu-id="93670-119">Задайте число потоков воспроизведения, используемых одновременно.</span><span class="sxs-lookup"><span data-stu-id="93670-119">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="93670-120">Чем больше это число, тем больше ресурсов потребляется при воспроизведении, но при этом воспроизведение ускоряется и возрастает его параллельность.</span><span class="sxs-lookup"><span data-stu-id="93670-120">A higher number consumes more resources during replay, but replay is faster and more concurrent.</span></span>  
  
 <span data-ttu-id="93670-121">**Воспроизвести события в порядке трассировки**</span><span class="sxs-lookup"><span data-stu-id="93670-121">**Replay events in the order they were traced**</span></span>  
 <span data-ttu-id="93670-122">Позволяет воспроизвести события последовательно.</span><span class="sxs-lookup"><span data-stu-id="93670-122">Replay events sequentially.</span></span> <span data-ttu-id="93670-123">Используйте этот параметр, если трассировка воспроизводится с целью отладки.</span><span class="sxs-lookup"><span data-stu-id="93670-123">Use this option if you are replaying a trace for debugging.</span></span>  
  
 <span data-ttu-id="93670-124">**Воспроизвести события, используя несколько потоков**</span><span class="sxs-lookup"><span data-stu-id="93670-124">**Replay events using multiple threads**</span></span>  
 <span data-ttu-id="93670-125">Позволяет воспроизвести события параллельно.</span><span class="sxs-lookup"><span data-stu-id="93670-125">Replay events concurrently.</span></span> <span data-ttu-id="93670-126">Этот параметр позволяет воспроизводить события быстрее, чем в последовательном режиме, но при этом отключается возможность отладки.</span><span class="sxs-lookup"><span data-stu-id="93670-126">This option is faster than replaying events sequentially, but disables debugging.</span></span> <span data-ttu-id="93670-127">События упорядочиваются по их системным идентификаторам процессов (SPID).</span><span class="sxs-lookup"><span data-stu-id="93670-127">The events are ordered within their system process identifiers (SPID).</span></span>  
  
 <span data-ttu-id="93670-128">**Отобразить результаты воспроизведения**</span><span class="sxs-lookup"><span data-stu-id="93670-128">**Display replay results**</span></span>  
 <span data-ttu-id="93670-129">Отображает результаты воспроизведения в приложении [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93670-129">Display replay results in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93670-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="93670-130">See Also</span></span>  
 <span data-ttu-id="93670-131">[Воспроизведение таблицы трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="93670-131">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="93670-132">[Воспроизведение файла трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="93670-132">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="93670-133">Воспроизведение трассировок</span><span class="sxs-lookup"><span data-stu-id="93670-133">Replay Traces</span></span>](../tools/sql-server-profiler/replay-traces.md)  
  
  
