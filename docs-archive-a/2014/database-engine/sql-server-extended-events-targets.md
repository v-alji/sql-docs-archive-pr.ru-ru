---
title: SQL Server мишеней расширенных событий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events]
- extended events [SQL Server], targets
ms.assetid: e281684c-40d1-4cf9-a0d4-7ea1ecffa384
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 010b7cc29543f266b77aaf180c50173ef9f70346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655324"
---
# <a name="sql-server-extended-events-targets"></a><span data-ttu-id="bd62c-102">SQL Server Extended Events Targets</span><span class="sxs-lookup"><span data-stu-id="bd62c-102">SQL Server Extended Events Targets</span></span>
  <span data-ttu-id="bd62c-103">Целями расширенных событий [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] являются потребители события.</span><span class="sxs-lookup"><span data-stu-id="bd62c-103">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events targets are event consumers.</span></span> <span data-ttu-id="bd62c-104">Цели могут записывать события в файл, хранить данные событий в буфере памяти и cобирать статистические данные о событиях.</span><span class="sxs-lookup"><span data-stu-id="bd62c-104">Targets can write to a file, store event data in a memory buffer, or aggregate event data.</span></span> <span data-ttu-id="bd62c-105">Цели могут обрабатывать данные в синхронном или асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="bd62c-105">Targets can process data synchronously or asynchronously.</span></span>  
  
 <span data-ttu-id="bd62c-106">Структура расширенных событий гарантирует, что цели получают события единственный раз за сеанс.</span><span class="sxs-lookup"><span data-stu-id="bd62c-106">The Extended Events design ensures that targets are guaranteed to receive events once and only once per session.</span></span>  
  
 <span data-ttu-id="bd62c-107">Расширенные события предоставляют следующие цели, которые можно использовать в сеансах расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="bd62c-107">Extended Events provide the following targets that you can use for an Extended Events session:</span></span>  
  
-   [<span data-ttu-id="bd62c-108">Счетчик событий</span><span class="sxs-lookup"><span data-stu-id="bd62c-108">Event counter</span></span>](../../2014/database-engine/event-counter-target.md)  
  
     <span data-ttu-id="bd62c-109">Подсчитывает все события, происходящие в ходе сеанса расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="bd62c-109">Counts all specified events that occur during an Extended Events session.</span></span> <span data-ttu-id="bd62c-110">Эта цель используется для получения сведений о характеристиках рабочей нагрузки без затрат на сбор всех событий.</span><span class="sxs-lookup"><span data-stu-id="bd62c-110">Use to obtain information about workload characteristics without adding the overhead of full event collection.</span></span> <span data-ttu-id="bd62c-111">Это синхронная цель.</span><span class="sxs-lookup"><span data-stu-id="bd62c-111">This is a synchronous target.</span></span>  
  
-   [<span data-ttu-id="bd62c-112">Файл событий</span><span class="sxs-lookup"><span data-stu-id="bd62c-112">Event file</span></span>](../../2014/database-engine/event-file-target.md)  
  
     <span data-ttu-id="bd62c-113">Используется для записи выходных данных сеанса событий из полных буферов памяти на диск.</span><span class="sxs-lookup"><span data-stu-id="bd62c-113">Use to write event session output from complete memory buffers to disk.</span></span> <span data-ttu-id="bd62c-114">Это асинхронная цель.</span><span class="sxs-lookup"><span data-stu-id="bd62c-114">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="bd62c-115">Попарное разбиение событий</span><span class="sxs-lookup"><span data-stu-id="bd62c-115">Event pairing</span></span>](../../2014/database-engine/event-pairing-target.md)  
  
     <span data-ttu-id="bd62c-116">Многие типы событий происходят попарно, например получение и снятие блокировки.</span><span class="sxs-lookup"><span data-stu-id="bd62c-116">Many kinds of events occur in pairs, such as lock acquires and lock releases.</span></span> <span data-ttu-id="bd62c-117">Эта цель позволяет определить, что указанное парное событие не произошло в правильной последовательности.</span><span class="sxs-lookup"><span data-stu-id="bd62c-117">Use to determine when a specified paired event does not occur in a matched set.</span></span> <span data-ttu-id="bd62c-118">Это асинхронная цель.</span><span class="sxs-lookup"><span data-stu-id="bd62c-118">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="bd62c-119">Трассировка событий Windows (ETW)</span><span class="sxs-lookup"><span data-stu-id="bd62c-119">Event Tracing for Windows (ETW)</span></span>](../relational-databases/extended-events/event-tracing-for-windows-target.md)  
  
     <span data-ttu-id="bd62c-120">Предназначена для сопоставления событий [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] с данными событий Windows или данными событий приложений.</span><span class="sxs-lookup"><span data-stu-id="bd62c-120">Use to correlate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events with Windows operating system or application event data.</span></span> <span data-ttu-id="bd62c-121">Это синхронная цель.</span><span class="sxs-lookup"><span data-stu-id="bd62c-121">This is a synchronous target.</span></span>  
  
-   [<span data-ttu-id="bd62c-122">Гистограмма</span><span class="sxs-lookup"><span data-stu-id="bd62c-122">Histogram</span></span>](../../2014/database-engine/histogram-target.md)  
  
     <span data-ttu-id="bd62c-123">Используется для подсчета количества указанных событий на основании указанного действия или столбца события.</span><span class="sxs-lookup"><span data-stu-id="bd62c-123">Use to count the number of times that a specified event occurs, based on a specified event column or action.</span></span> <span data-ttu-id="bd62c-124">Это асинхронная цель.</span><span class="sxs-lookup"><span data-stu-id="bd62c-124">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="bd62c-125">Кольцевой буфер</span><span class="sxs-lookup"><span data-stu-id="bd62c-125">Ring buffer</span></span>](../../2014/database-engine/ring-buffer-target.md)  
  
     <span data-ttu-id="bd62c-126">Используется для хранения данных о событиях в памяти по принципу очереди (FIFO) или по принципу FIFO для каждого события.</span><span class="sxs-lookup"><span data-stu-id="bd62c-126">Use to hold the event data in memory on a first-in first-out (FIFO) basis, or on a per-event FIFO basis.</span></span> <span data-ttu-id="bd62c-127">Это асинхронная цель.</span><span class="sxs-lookup"><span data-stu-id="bd62c-127">This is an asynchronous target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd62c-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd62c-128">See Also</span></span>  
 <span data-ttu-id="bd62c-129">[Расширенные события](../relational-databases/extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="bd62c-129">[Extended Events](../relational-databases/extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="bd62c-130">[SQL Server пакетов расширенных событий](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span><span class="sxs-lookup"><span data-stu-id="bd62c-130">[SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span></span>  
 <span data-ttu-id="bd62c-131">[Сеансы расширенных событий SQL Server](../relational-databases/extended-events/sql-server-extended-events-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="bd62c-131">[SQL Server Extended Events Sessions](../relational-databases/extended-events/sql-server-extended-events-sessions.md) </span></span>  
 [<span data-ttu-id="bd62c-132">Подсистема расширенных событий SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd62c-132">SQL Server Extended Events Engine</span></span>](../relational-databases/extended-events/sql-server-extended-events-engine.md)  
  
  
