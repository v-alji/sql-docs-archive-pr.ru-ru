---
title: Объект статистики ожидания (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Wait Statistics object
- SQLServer:Wait Statistics
ms.assetid: cb7f917d-4291-4115-9b78-ee7692ebbb2d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5cfd2f1309cb118896ff7951b7f82feb38de60e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729389"
---
# <a name="sql-server-wait-statistics-object"></a><span data-ttu-id="ebdc0-102">SQL Server, объект Wait Statistics</span><span class="sxs-lookup"><span data-stu-id="ebdc0-102">SQL Server, Wait Statistics Object</span></span>
  <span data-ttu-id="ebdc0-103">Объект производительности **SQLServer:Wait Statistics** содержит счетчики производительности, сообщающие сведения о состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-103">The **SQLServer:Wait Statistics** performance object contains performance counters that report information about wait status.</span></span>  
  
 <span data-ttu-id="ebdc0-104">В таблице ниже перечислены счетчики, содержащиеся в объекте статистики ожидания.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-104">The table below lists the counters that the Wait Statistics object contains.</span></span>  
  
|<span data-ttu-id="ebdc0-105">SQL Server, счетчики статистики ожидания</span><span class="sxs-lookup"><span data-stu-id="ebdc0-105">SQL Server Wait Statistics counters</span></span>|<span data-ttu-id="ebdc0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ebdc0-106">Description</span></span>|  
|-----------------------------------------|-----------------|  
|<span data-ttu-id="ebdc0-107">**Ожиданий блокировок**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-107">**Lock waits**</span></span>|<span data-ttu-id="ebdc0-108">Статистика процессов, ожидающих в состоянии блокировки.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-108">Statistics for processes waiting on a lock.</span></span>|  
|<span data-ttu-id="ebdc0-109">**Ожиданий буфера журнала**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-109">**Log buffer waits**</span></span>|<span data-ttu-id="ebdc0-110">Статистика процессов, ожидающих освобождения буфера журнала.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-110">Statistics for processes waiting for log buffer to be available.</span></span>|  
|<span data-ttu-id="ebdc0-111">**Ожиданий записи в журнал**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-111">**Log write waits**</span></span>|<span data-ttu-id="ebdc0-112">Статистика процессов, ожидающих записи в буфер журнала.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-112">Statistics for processes waiting for log buffer to be written.</span></span>|  
|<span data-ttu-id="ebdc0-113">**Ожиданий в очереди на выделение памяти**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-113">**Memory grant queue waits**</span></span>|<span data-ttu-id="ebdc0-114">Статистика процессов, ожидающих предоставления памяти.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-114">Statistics for processes waiting for memory grant to become available.</span></span>|  
|<span data-ttu-id="ebdc0-115">**Ожиданий сетевых операций ввода-вывода**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-115">**Network IO waits**</span></span>|<span data-ttu-id="ebdc0-116">Статистика, относящаяся к сетевому вводу-выводу.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-116">Statistics relevant to wait on network I/O.</span></span>|  
|<span data-ttu-id="ebdc0-117">**Ожиданий кратковременной блокировки объектов, отличных от страниц**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-117">**Non-Page latch waits**</span></span>|<span data-ttu-id="ebdc0-118">Статистика, относящаяся к не страничным кратковременным блокировкам.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-118">Statistics relevant to non-page latches.</span></span>|  
|<span data-ttu-id="ebdc0-119">**Число ожиданий кратковременной блокировки операций ввода-вывода страниц**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-119">**Page IO latch waits**</span></span>|<span data-ttu-id="ebdc0-120">Статистика, относящаяся к кратковременным блокировкам страничного ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-120">Statistics relevant to page I/O latches.</span></span>|  
|<span data-ttu-id="ebdc0-121">**Ожиданий кратковременной блокировки страниц**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-121">**Page latch waits**</span></span>|<span data-ttu-id="ebdc0-122">Статистика, относящаяся к страничным кратковременным блокировкам, исключая кратковременные блокировки ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-122">Statistics relevant to page latches, not including I/O latches.</span></span>|  
|<span data-ttu-id="ebdc0-123">**Ожиданий поточно-ориентированных объектов памяти**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-123">**Thread-safe memory objects waits**</span></span>|<span data-ttu-id="ebdc0-124">Статистика процессов, ожидающих поточно-ориентированного выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-124">Statistics for processes waiting on thread-safe memory allocators.</span></span>|  
|<span data-ttu-id="ebdc0-125">**Ожиданий владения транзакцией**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-125">**Transaction ownership waits**</span></span>|<span data-ttu-id="ebdc0-126">Статистика, относящаяся к процессам, синхронизирующим доступ к транзакции.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-126">Statistics relevant to processes synchronizing access to transaction.</span></span>|  
|<span data-ttu-id="ebdc0-127">**Ожиданий исполнителя**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-127">**Wait for the worker**</span></span>|<span data-ttu-id="ebdc0-128">Статистика, относящаяся к процессам, ожидающим освобождения рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-128">Statistics relevant to processes waiting for worker to become available.</span></span>|  
|<span data-ttu-id="ebdc0-129">**Ожиданий синхронизации рабочего пространства**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-129">**Workspace synchronization waits**</span></span>|<span data-ttu-id="ebdc0-130">Статистика, относящаяся к процессам, синхронизирующим доступ к рабочему пространству.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-130">Statistics relevant to processes synchronizing access to workspace.</span></span>|  
  
 <span data-ttu-id="ebdc0-131">Каждый из счетчиков объекта содержит следующие экземпляры.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-131">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="ebdc0-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="ebdc0-132">Item</span></span>|<span data-ttu-id="ebdc0-133">Описание</span><span class="sxs-lookup"><span data-stu-id="ebdc0-133">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="ebdc0-134">**Среднее время ожидания блокировки (мс)**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-134">**Average wait time (ms)**</span></span>|<span data-ttu-id="ebdc0-135">Среднее время для выбранного типа ожидания.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-135">Average time for the selected type of wait.</span></span>|  
|<span data-ttu-id="ebdc0-136">**Совокупное время ожидания (мс) в секунду**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-136">**Cumulative wait time (ms) per second**</span></span>|<span data-ttu-id="ebdc0-137">Общее время ожидания в секунду для выбранного типа ожидания.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-137">Aggregated wait time per second, for the selected type of wait.</span></span>|  
|<span data-ttu-id="ebdc0-138">**Выполняющиеся сеансы ожидания**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-138">**Waits in progress**</span></span>|<span data-ttu-id="ebdc0-139">Количество ожидающих в данный момент процессов для определенного типа ожидания.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-139">Number of processes currently waiting on the following type.</span></span>|  
|<span data-ttu-id="ebdc0-140">**Начатые сеансы ожидания (в секунду)**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-140">**Waits started per second**</span></span>|<span data-ttu-id="ebdc0-141">Число ожиданий, запущенных за одну секунду, для выбранного типа ожидания.</span><span class="sxs-lookup"><span data-stu-id="ebdc0-141">Number of waits started per second of the selected type of wait.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ebdc0-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="ebdc0-142">See Also</span></span>  
 [<span data-ttu-id="ebdc0-143">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="ebdc0-143">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
