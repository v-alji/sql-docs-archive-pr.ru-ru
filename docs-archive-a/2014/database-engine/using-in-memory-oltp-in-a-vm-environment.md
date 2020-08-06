---
title: Использование выполняющейся в памяти OLTP в среде виртуальной машины | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 27ec7eb3-3a24-41db-aa65-2f206514c6f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83cf785fbcd2df9449d61e328e3bf8e374a6656d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732006"
---
# <a name="using-in-memory-oltp-in-a-vm-environment"></a><span data-ttu-id="24fba-102">Использование In-Memory OLTP в среде ВМ</span><span class="sxs-lookup"><span data-stu-id="24fba-102">Using In-Memory OLTP in a VM Environment</span></span>
  <span data-ttu-id="24fba-103">Виртуализация серверов позволяет не только снизить расходы на приобретение и эксплуатацию, но и добиться большей эффективности ИТ-процессов благодаря оптимизации подготовки, обслуживания, доступности и операций резервного копирования или восстановления приложений.</span><span class="sxs-lookup"><span data-stu-id="24fba-103">Server virtualization can help you lower IT capital and operational costs and attain greater IT efficiency with improved application provisioning, maintenance, availability, and backup/recovery processes.</span></span> <span data-ttu-id="24fba-104">В результате недавних успехов в развитии технологий стало проще консолидировать сложные рабочие нагрузки базы данных с применением виртуализации.</span><span class="sxs-lookup"><span data-stu-id="24fba-104">With recent technological advances, complex database workloads can be more readily consolidated using virtualization.</span></span> <span data-ttu-id="24fba-105">В этой статье приведены рекомендации по использованию [!INCLUDE[hek_1](../includes/hek-1-md.md)] в виртуализированной среде.</span><span class="sxs-lookup"><span data-stu-id="24fba-105">This topic covers best practices for using [!INCLUDE[hek_1](../includes/hek-1-md.md)] in a virtualized environment.</span></span>  
  
##  <a name="memory-pre-allocation"></a><a name="bkmk_memoryPreAllocation"></a><span data-ttu-id="24fba-106">Предварительное выделение памяти</span><span class="sxs-lookup"><span data-stu-id="24fba-106">Memory pre-allocation</span></span>  
 <span data-ttu-id="24fba-107">В виртуальной среде важными факторами для памяти являются более высокая производительность и расширенная поддержка.</span><span class="sxs-lookup"><span data-stu-id="24fba-107">For memory in a virtualized environment, better performance and enhanced support are essential considerations.</span></span> <span data-ttu-id="24fba-108">Необходимо иметь возможность как быстро выделять память виртуальным машинам в зависимости от их требований (пиковые и низкие нагрузки), так и исключить бесполезные траты памяти.</span><span class="sxs-lookup"><span data-stu-id="24fba-108">You must be able to both quickly allocate memory to virtual machines depending on their requirements (peak and off-peak loads) and ensure that the memory is not wasted.</span></span> <span data-ttu-id="24fba-109">Компонент Hyper-V Dynamic Memory делает выделение памяти между виртуальными машинами, выполняемыми на узле, и управление ею более гибким.</span><span class="sxs-lookup"><span data-stu-id="24fba-109">The Hyper-V Dynamic Memory feature increases agility in how the memory is allocated and managed between virtual machines running on a host.</span></span>  
  
 <span data-ttu-id="24fba-110">Некоторые рекомендации по виртуализации и управлению [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] необходимо изменить при виртуализации базы данных с таблицами, оптимизированными для памяти.</span><span class="sxs-lookup"><span data-stu-id="24fba-110">Some best practices for virtualizing and managing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] need to be modified when virtualizing a database with memory-optimized tables.</span></span> <span data-ttu-id="24fba-111">При отсутствии оптимизированных для памяти таблиц есть две рекомендации.</span><span class="sxs-lookup"><span data-stu-id="24fba-111">Without memory-optimized tables, two of the best practices are:</span></span>  
  
-   <span data-ttu-id="24fba-112">При использовании MIN_SERVER_MEMORY рекомендуется назначать только необходимое количество памяти, чтобы достаточно памяти осталось для других процессов (во избежание подкачки).</span><span class="sxs-lookup"><span data-stu-id="24fba-112">If you use MIN_SERVER_MEMORY, it is better to assign only the amount of memory that is required so sufficient memory remains for other processes (thereby avoiding paging).</span></span>  
  
-   <span data-ttu-id="24fba-113">Не назначайте слишком высокого значения предварительного выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="24fba-113">Do not set the memory pre-allocation value too high.</span></span> <span data-ttu-id="24fba-114">В противном случае другие процессы могут не получить достаточной памяти к тому времени, когда она им потребуется, а это приведет к подкачке памяти.</span><span class="sxs-lookup"><span data-stu-id="24fba-114">Otherwise, other processes may not get sufficient memory at the time when they require it, and this can result in memory paging.</span></span>  
  
 <span data-ttu-id="24fba-115">Если следовать указанным выше рекомендациям, когда в базе данных есть оптимизированные для памяти таблицы, может выясниться, что попытка восстановить базу данных приводит к остановке базы данных в состоянии "Ожидание восстановления", даже если доступно достаточно памяти для восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="24fba-115">If you follow the above practices for a database with memory-optimized tables, an attempt to restore and recover a database could result in the database being in a "Recovery Pending" state, even if you have sufficient memory to recover the database.</span></span> <span data-ttu-id="24fba-116">Причина в том, что при запуске [!INCLUDE[hek_2](../includes/hek-2-md.md)] передает данные в память активнее, чем механизм выделения динамической памяти выделяет память базе данных.</span><span class="sxs-lookup"><span data-stu-id="24fba-116">The reason for this is that, when starting up, [!INCLUDE[hek_2](../includes/hek-2-md.md)] brings data into memory more aggressively than dynamic memory allocation allocates memory to the database.</span></span>  
  
 <span data-ttu-id="24fba-117">**Способы устранения:**</span><span class="sxs-lookup"><span data-stu-id="24fba-117">**Resolution**</span></span>  
  
 <span data-ttu-id="24fba-118">Чтобы смягчить этот эффект, заранее выделите достаточную память, чтобы восстановить или перезапустить базу данных, а не минимальное значение, в расчете на то, что динамическая память выделит дополнительную память при необходимости.</span><span class="sxs-lookup"><span data-stu-id="24fba-118">To mitigate this, pre-allocate sufficient memory to the database to recover or restart the database, not a minimum value relying on dynamic memory to provide the additional memory when needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24fba-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="24fba-119">See Also</span></span>  
 [<span data-ttu-id="24fba-120">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="24fba-120">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
