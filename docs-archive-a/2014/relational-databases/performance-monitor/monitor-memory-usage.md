---
title: Мониторинг использования памяти | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- tuning databases [SQL Server], memory
- monitoring server performance [SQL Server], memory usage
- isolating memory [SQL Server]
- paging rate [SQL Server]
- memory [SQL Server], monitoring usage
- monitoring [SQL Server], memory usage
- low-memory conditions
- database monitoring [SQL Server], memory usage
- available memory [SQL Server]
- page faults [SQL Server]
- monitoring performance [SQL Server], memory usage
- server performance [SQL Server], memory
ms.assetid: 1aee3933-a11c-4b87-91b7-32f5ea38c87f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1986d9576f9b067cad18f27d4febbf097ed52703
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739740"
---
# <a name="monitor-memory-usage"></a><span data-ttu-id="1094b-102">Наблюдение за использованием памяти</span><span class="sxs-lookup"><span data-stu-id="1094b-102">Monitor Memory Usage</span></span>
  <span data-ttu-id="1094b-103">Проводите периодический мониторинг экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для подтверждения того, что память используется в допустимых пределах.</span><span class="sxs-lookup"><span data-stu-id="1094b-103">Monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically to confirm that memory usage is within typical ranges.</span></span>  
  
 <span data-ttu-id="1094b-104">Для контроля условий нехватки памяти используйте следующие счетчики объектов.</span><span class="sxs-lookup"><span data-stu-id="1094b-104">To monitor for a low-memory condition, use the following object counters:</span></span>  
  
-   <span data-ttu-id="1094b-105">**Память: доступно байтов**</span><span class="sxs-lookup"><span data-stu-id="1094b-105">**Memory: Available Bytes**</span></span>  
  
-   <span data-ttu-id="1094b-106">**Память: страниц/с**</span><span class="sxs-lookup"><span data-stu-id="1094b-106">**Memory: Pages/sec**</span></span>  
  
 <span data-ttu-id="1094b-107">Счетчик **Доступно байтов** указывает на то, сколько байт памяти доступно на данный момент для использования процессами.</span><span class="sxs-lookup"><span data-stu-id="1094b-107">The **Available Bytes** counter indicates how many bytes of memory are currently available for use by processes.</span></span> <span data-ttu-id="1094b-108">Счетчик **Страниц/с** показывает число страниц, которые были или получены с диска из-за ошибок страниц физической памяти, или записаны на диск для освобождения пространства в рабочем множестве из-за ошибок страниц.</span><span class="sxs-lookup"><span data-stu-id="1094b-108">The **Pages/sec** counter indicates the number of pages that either were retrieved from disk due to hard page faults or written to disk to free space in the working set due to page faults.</span></span>  
  
 <span data-ttu-id="1094b-109">Малые значения счетчика **Доступно байтов** могут указывать на то, что существует общая нехватка памяти на компьютере или что приложение не освобождает память.</span><span class="sxs-lookup"><span data-stu-id="1094b-109">Low values for the **Available Bytes** counter can indicate that there is an overall shortage of memory on the computer or that an application is not releasing memory.</span></span> <span data-ttu-id="1094b-110">Большое значение счетчика **Страниц/с** может означать излишнюю подкачку.</span><span class="sxs-lookup"><span data-stu-id="1094b-110">A high rate for the **Pages/sec** counter could indicate excessive paging.</span></span> <span data-ttu-id="1094b-111">Наблюдение за счетчиком **Память: ошибок страниц/с** позволяет убедиться в том, что активность диска не вызвана трансляцией страниц.</span><span class="sxs-lookup"><span data-stu-id="1094b-111">Monitor the **Memory: Page Faults/sec** counter to make sure that the disk activity is not caused by paging.</span></span>  
  
 <span data-ttu-id="1094b-112">Низкий уровень подкачки (и редкие ошибки страниц) является нормальным, даже если у компьютера достаточно большое количество доступной памяти.</span><span class="sxs-lookup"><span data-stu-id="1094b-112">A low rate of paging (and hence page faults) is typical, even if the computer has plenty of available memory.</span></span> <span data-ttu-id="1094b-113">Диспетчер виртуальной памяти (VMM) Microsoft Windows берет страницы из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и других процессов по мере того, как он урезает размеры рабочих множеств этих процессов.</span><span class="sxs-lookup"><span data-stu-id="1094b-113">The Microsoft Windows Virtual Memory Manager (VMM) takes pages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and other processes as it trims the working-set sizes of those processes.</span></span> <span data-ttu-id="1094b-114">Деятельность VMM может привести к ошибкам страниц.</span><span class="sxs-lookup"><span data-stu-id="1094b-114">This VMM activity tends to cause page faults.</span></span> <span data-ttu-id="1094b-115">Чтобы определить, является ли [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или другой процесс причиной излишней подкачки, наблюдайте за счетчиком **Процесс: ошибок страниц/с** для экземпляра процесса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1094b-115">To determine whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or another process is the cause of excessive paging, monitor the **Process: Page Faults/sec** counter for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process instance.</span></span>  
  
 <span data-ttu-id="1094b-116">Дополнительные сведения об устранении проблемы излишней подкачки см. в документации по операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="1094b-116">For more information about resolving excessive paging, see the Windows operating system documentation.</span></span>  
  
## <a name="isolating-memory-used-by-sql-server"></a><span data-ttu-id="1094b-117">Изоляция памяти, используемой SQL Server</span><span class="sxs-lookup"><span data-stu-id="1094b-117">Isolating Memory Used by SQL Server</span></span>  
 <span data-ttu-id="1094b-118">По умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] изменяет свои требования к памяти динамически, исходя из доступных ресурсов системы.</span><span class="sxs-lookup"><span data-stu-id="1094b-118">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] changes its memory requirements dynamically, on the basis of available system resources.</span></span> <span data-ttu-id="1094b-119">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] нужно больше памяти, он производит запрос к операционной системе, чтобы определить, доступна ли свободная физическая память, и использует ее.</span><span class="sxs-lookup"><span data-stu-id="1094b-119">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] needs more memory, it queries the operating system to determine whether free physical memory is available and uses the available memory.</span></span> <span data-ttu-id="1094b-120">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не нуждается в памяти, выделенной для него, он освобождает ее для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1094b-120">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not need the memory currently allocated to it, it releases the memory to the operating system.</span></span> <span data-ttu-id="1094b-121">Однако можно отказаться от динамического использования памяти, задав значения параметрам конфигурации сервера **minservermemory**и **maxservermemory** .</span><span class="sxs-lookup"><span data-stu-id="1094b-121">However, you can override the option to dynamically use memory by using the **minservermemory**, and **maxservermemory** server configuration options.</span></span> <span data-ttu-id="1094b-122">Дополнительные сведения см. в разделе [Параметры памяти сервера](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="1094b-122">For more information, see [Server Memory Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span></span>  
  
 <span data-ttu-id="1094b-123">Для мониторинга объема памяти, используемого [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , наблюдайте за следующими счетчиками производительности.</span><span class="sxs-lookup"><span data-stu-id="1094b-123">To monitor the amount of memory that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses, examine the following performance counters:</span></span>  
  
-   <span data-ttu-id="1094b-124">**Процесс: рабочий набор**</span><span class="sxs-lookup"><span data-stu-id="1094b-124">**Process: Working Set**</span></span>  
  
-   <span data-ttu-id="1094b-125">**SQL Server: Buffer Manager: коэффициент попаданий в буферный кэш**</span><span class="sxs-lookup"><span data-stu-id="1094b-125">**SQL Server: Buffer Manager: Buffer Cache Hit Ratio**</span></span>  
  
-   <span data-ttu-id="1094b-126">**SQL Server: Buffer Manager: страниц базы данных**</span><span class="sxs-lookup"><span data-stu-id="1094b-126">**SQL Server: Buffer Manager: Database Pages**</span></span>  
  
-   <span data-ttu-id="1094b-127">**SQL Server: Memory Manager: общая память сервера (КБ)**</span><span class="sxs-lookup"><span data-stu-id="1094b-127">**SQL Server: Memory Manager: Total Server Memory (KB)**</span></span>  
  
 <span data-ttu-id="1094b-128">Счетчик **WorkingSet** отображает объем памяти, занятый процессом.</span><span class="sxs-lookup"><span data-stu-id="1094b-128">The **WorkingSet** counter shows the amount of memory that is used by a process.</span></span> <span data-ttu-id="1094b-129">Если это число постоянно меньше объема памяти, установленного параметрами сервера **min server memory** и **max server memory** , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настроен для использования слишком большого объема памяти.</span><span class="sxs-lookup"><span data-stu-id="1094b-129">If this number is consistently below the amount of memory that is set by the **min server memory** and **max server memory** server options, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use too much memory.</span></span>  
  
 <span data-ttu-id="1094b-130">Значения счетчика **Коэффициент попаданий в кэш буфера** зависят от конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="1094b-130">The **Buffer Cache Hit Ratio** counter is specific to an application.</span></span> <span data-ttu-id="1094b-131">Однако желательно значение коэффициента, равное 90 процентам или выше.</span><span class="sxs-lookup"><span data-stu-id="1094b-131">However, a rate of 90 percent or higher is desirable.</span></span> <span data-ttu-id="1094b-132">Добавляйте память, пока значение не будет постоянно больше 90 процентов.</span><span class="sxs-lookup"><span data-stu-id="1094b-132">Add more memory until the value is consistently greater than 90 percent.</span></span> <span data-ttu-id="1094b-133">Значение выше 90 процентов указывает на то, что более 90 процентов всех запрошенных данных были получены из кэша данных.</span><span class="sxs-lookup"><span data-stu-id="1094b-133">A value greater than 90 percent indicates that more than 90 percent of all requests for data were satisfied from the data cache.</span></span>  
  
 <span data-ttu-id="1094b-134">Если счетчик **TotalServerMemory (KB)** постоянно показывает высокие значения по сравнению с объемом физической памяти компьютера, это может означать, что требуется установить в компьютер больше памяти.</span><span class="sxs-lookup"><span data-stu-id="1094b-134">If the **TotalServerMemory (KB)** counter is consistently high compared to the amount of physical memory in the computer, it may indicate that more memory is required.</span></span>  
  
## <a name="determining-current-memory-allocation"></a><span data-ttu-id="1094b-135">Определение Текущего Распределения Памяти</span><span class="sxs-lookup"><span data-stu-id="1094b-135">Determining Current Memory Allocation</span></span>  
 <span data-ttu-id="1094b-136">Следующий запрос возвращает информацию о текущем распределении памяти.</span><span class="sxs-lookup"><span data-stu-id="1094b-136">The following query returns information about currently allocated memory.</span></span>  
  
```  
SELECT  
(physical_memory_in_use_kb/1024) AS Memory_usedby_Sqlserver_MB,  
(locked_page_allocations_kb/1024) AS Locked_pages_used_Sqlserver_MB,  
(total_virtual_address_space_kb/1024) AS Total_VAS_in_MB,  
process_physical_memory_low,  
process_virtual_memory_low  
FROM sys.dm_os_process_memory;  
```  
  
  
