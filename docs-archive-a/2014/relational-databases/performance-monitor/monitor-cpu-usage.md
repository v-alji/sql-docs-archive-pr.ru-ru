---
title: Мониторинг использования ЦП | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server], CPU usage
- tuning databases [SQL Server], CPU usage
- processors [SQL Server], monitoring usage
- database performance [SQL Server], CPU usage
- monitoring CPU usage [SQL Server]
- server performance [SQL Server], CPU usage
- database monitoring [SQL Server], CPU usage
- monitoring [SQL Server], CPU usage
- processors [SQL Server]
- CPU [SQL Server], monitoring
- monitoring server performance [SQL Server], CPU usage
ms.assetid: 2a02a3b6-07b2-4ad0-8a24-670414d19812
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f08d49348fd25593f27a87f2b0123f7ce43e35b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739749"
---
# <a name="monitor-cpu-usage"></a><span data-ttu-id="655c4-102">Мониторинг использования ЦП</span><span class="sxs-lookup"><span data-stu-id="655c4-102">Monitor CPU Usage</span></span>
  <span data-ttu-id="655c4-103">Периодически контролируйте экземпляр Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , чтобы определить, находятся ли уровни загрузки ЦП в стандартных диапазонах.</span><span class="sxs-lookup"><span data-stu-id="655c4-103">Monitor an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically to determine whether CPU usage rates are within normal ranges.</span></span> <span data-ttu-id="655c4-104">Постоянный высокий уровень использования ЦП может указывать на необходимость обновления ЦП или на необходимость добавления нескольких процессоров.</span><span class="sxs-lookup"><span data-stu-id="655c4-104">A continually high rate of CPU usage may indicate the need to upgrade the CPU or add multiple processors.</span></span> <span data-ttu-id="655c4-105">Кроме того, высокий уровень использования ЦП может указывать на плохо настроенное или плохо разработанное приложение.</span><span class="sxs-lookup"><span data-stu-id="655c4-105">Alternatively, a high CPU usage rate may indicate a poorly tuned or designed application.</span></span> <span data-ttu-id="655c4-106">Оптимизация работы приложения может снизить уровень загрузки ЦП.</span><span class="sxs-lookup"><span data-stu-id="655c4-106">Optimizing the application can lower CPU utilization.</span></span>  
  
 <span data-ttu-id="655c4-107">Эффективным способом определения уровня загрузки ЦП является использование счетчика **Процессор: % загруженности процессора** в служебной программе «Системный монитор».</span><span class="sxs-lookup"><span data-stu-id="655c4-107">An efficient way to determine CPU usage is to use the **Processor:% Processor Time** counter in System Monitor.</span></span> <span data-ttu-id="655c4-108">Этот счетчик отслеживает время, которое ЦП тратит на выполнение потока во время работы.</span><span class="sxs-lookup"><span data-stu-id="655c4-108">This counter monitors the amount of time the CPU spends executing a thread that is not idle.</span></span> <span data-ttu-id="655c4-109">Постоянный уровень загрузки ЦП в диапазоне от 80 до 90 % может указывать на необходимость обновления ЦП или на необходимость добавления нескольких процессоров.</span><span class="sxs-lookup"><span data-stu-id="655c4-109">A consistent state of 80 percent to 90 percent may indicate the need to upgrade your CPU or add more processors.</span></span> <span data-ttu-id="655c4-110">При работе с многопроцессорными системами следите за отдельным экземпляром упомянутого счетчика для каждого процессора.</span><span class="sxs-lookup"><span data-stu-id="655c4-110">For multiprocessor systems, monitor a separate instance of this counter for each processor.</span></span> <span data-ttu-id="655c4-111">Это значение представляет суммарное процессорное время указанного процессора.</span><span class="sxs-lookup"><span data-stu-id="655c4-111">This value represents the sum of processor time on a specific processor.</span></span> <span data-ttu-id="655c4-112">Чтобы определить среднее для всех процессоров, воспользуйтесь вместо этого счетчиком **Система: % общего процессорного времени** .</span><span class="sxs-lookup"><span data-stu-id="655c4-112">To determine the average for all processors, use the **System: %Total Processor Time** counter instead.</span></span>  
  
 <span data-ttu-id="655c4-113">Дополнительно можно контролировать следующие счетчики:</span><span class="sxs-lookup"><span data-stu-id="655c4-113">Optionally, you can also monitor the following counters to monitor processor usage:</span></span>  
  
-   <span data-ttu-id="655c4-114">**Процессор: % работы в привилегированном режиме**</span><span class="sxs-lookup"><span data-stu-id="655c4-114">**Processor: % Privileged Time**</span></span>  
  
     <span data-ttu-id="655c4-115">Соответствует проценту процессорного времени, затраченного на выполнение команд ядра операционной системы Microsoft Windows, таких как обработка запросов ввода-вывода [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="655c4-115">Corresponds to the percentage of time the processor spends on execution of Microsoft Windows kernel commands, such as processing of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] I/O requests.</span></span> <span data-ttu-id="655c4-116">Если значение этого счетчика постоянно высокое, в то время как счетчики для объекта **Физический диск** также имеют высокие значения, то необходимо рассмотреть вопрос об установке более быстрой и более эффективной дисковой подсистемы.</span><span class="sxs-lookup"><span data-stu-id="655c4-116">If this counter is consistently high when the **Physical Disk** counters are high, consider installing a faster or more efficient disk subsystem.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="655c4-117">На обработку запросов от различных контроллеров дисков и самих дисковых накопителей ядром операционной системы тратится различное количество времени.</span><span class="sxs-lookup"><span data-stu-id="655c4-117">Different disk controllers and drivers use different amounts of kernel processing time.</span></span> <span data-ttu-id="655c4-118">Эффективные контроллеры и дисковые накопители используют меньше привилегированного времени, оставляя больше времени для обработки запросов пользовательских приложений, увеличивая общую пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="655c4-118">Efficient controllers and drivers use less privileged time, leaving more processing time available for user applications, increasing overall throughput.</span></span>  
  
-   <span data-ttu-id="655c4-119">**Процессор: % работы в пользовательском режиме**</span><span class="sxs-lookup"><span data-stu-id="655c4-119">**Processor: %User Time**</span></span>  
  
     <span data-ttu-id="655c4-120">Соответствует проценту времени работы процессора, которое он затрачивает на выполнение пользовательских приложений, например [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="655c4-120">Corresponds to the percentage of time that the processor spends on executing user processes such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="655c4-121">**Система: Длина очереди процессора**.</span><span class="sxs-lookup"><span data-stu-id="655c4-121">**System: Processor Queue Length**</span></span>  
  
     <span data-ttu-id="655c4-122">Соответствует количеству потоков, ожидающих обработки процессором.</span><span class="sxs-lookup"><span data-stu-id="655c4-122">Corresponds to the number of threads waiting for processor time.</span></span> <span data-ttu-id="655c4-123">Если потокам некоторого процесса требуется больше циклов процессора, чем это возможно, значит, узким местом системы является процессор.</span><span class="sxs-lookup"><span data-stu-id="655c4-123">A processor bottleneck develops when threads of a process require more processor cycles than are available.</span></span> <span data-ttu-id="655c4-124">Если количество процессов, требующих обработки процессором, велико, необходимо установить более быстрый процессор.</span><span class="sxs-lookup"><span data-stu-id="655c4-124">If more than a few processes attempt to utilize the processor's time, you might need to install a faster processor.</span></span> <span data-ttu-id="655c4-125">Или, в многопроцессорной системе, необходимо добавить еще один процессор.</span><span class="sxs-lookup"><span data-stu-id="655c4-125">Or, if you have a multiprocessor system, you could add a processor.</span></span>  
  
 <span data-ttu-id="655c4-126">При оценке использования процессора необходимо принять во внимание тип работы, выполняемой экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="655c4-126">When you examine processor usage, consider the type of work that the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs.</span></span> <span data-ttu-id="655c4-127">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняет много вычислений, таких как запросы на обработку статистических выражений или запросы к рабочей области, не требующие дисковых операций ввода-вывода, то может быть использовано 100 % процессорного времени.</span><span class="sxs-lookup"><span data-stu-id="655c4-127">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs many calculations, such as queries involving aggregates or memory-bound queries that require no disk I/O, 100 percent of the processor's time can be used.</span></span> <span data-ttu-id="655c4-128">Если это приводит к снижению производительности других приложений, попробуйте изменить рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="655c4-128">If this causes the performance of other applications to suffer, try changing the workload.</span></span> <span data-ttu-id="655c4-129">Например, выделите компьютер целиком для работы только экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="655c4-129">For example, dedicate the computer to running the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="655c4-130">Уровни загрузки ЦП около 100 % при обработке многочисленных запросов клиентов могут указывать на то, что процессы стоят в очереди, ожидая обработки процессором, который является узким местом системы.</span><span class="sxs-lookup"><span data-stu-id="655c4-130">Usage rates around 100 percent, where many client requests are being processed, may indicate that processes are queuing up, waiting for processor time, and causing a bottleneck.</span></span> <span data-ttu-id="655c4-131">Данная проблема может быть решена установкой более быстрых процессоров.</span><span class="sxs-lookup"><span data-stu-id="655c4-131">Resolve the problem by adding faster processors.</span></span>  
  
  
