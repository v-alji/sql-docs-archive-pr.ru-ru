---
title: SQL Server:Buffer Node | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Buffer Node
- Buffer Node object
ms.assetid: fd3f9f0f-7c38-4cfd-a0c5-ee93dd52d9a5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 14659e4c1191e2260bccdbcd612f510770913629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667034"
---
# <a name="sql-serverbuffer-node"></a><span data-ttu-id="f6abb-102">SQL Server:Buffer Node</span><span class="sxs-lookup"><span data-stu-id="f6abb-102">SQL Server:Buffer Node</span></span>
  <span data-ttu-id="f6abb-103">Объект **узел буфера** предоставляет счетчики, которые дополняют счетчики, предоставляемые объектом **диспетчер буферов** .</span><span class="sxs-lookup"><span data-stu-id="f6abb-103">The **Buffer Node** object provides counters that complement counters provided by the **Buffer Manager** object.</span></span> <span data-ttu-id="f6abb-104">Это позволяет контролировать распределение страницы буферного пула [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для каждого узла неоднородного доступа к памяти (NUMA).</span><span class="sxs-lookup"><span data-stu-id="f6abb-104">It allows you to monitor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] buffer pool page distribution for each non-uniform memory access (NUMA) node.</span></span> <span data-ttu-id="f6abb-105">Для каждого используемого узла неоднородного доступа к памяти (NUMA) существует экземпляр объекта **узел буфера** .</span><span class="sxs-lookup"><span data-stu-id="f6abb-105">There is an instance of the **Buffer Node** object for each NUMA node in use.</span></span> <span data-ttu-id="f6abb-106">В архитектуре, отличной от NUMA, существует единственный экземпляр объекта **узел буфера** .</span><span class="sxs-lookup"><span data-stu-id="f6abb-106">On non-NUMA architecture, there will be a single instance of the **Buffer Node** object.</span></span>  
  
## <a name="buffer-node-performance-objects"></a><span data-ttu-id="f6abb-107">Объекты производительности узла буфера</span><span class="sxs-lookup"><span data-stu-id="f6abb-107">Buffer Node Performance Objects</span></span>  
 <span data-ttu-id="f6abb-108">Объекты производительности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **узла буфера** описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f6abb-108">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Buffer Node** performance objects.</span></span>  
  
|<span data-ttu-id="f6abb-109">Счетчики узла буфера SQL Server</span><span class="sxs-lookup"><span data-stu-id="f6abb-109">SQL Server Buffer Node counters</span></span>|<span data-ttu-id="f6abb-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f6abb-110">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="f6abb-111">**Страниц базы данных**</span><span class="sxs-lookup"><span data-stu-id="f6abb-111">**Database pages**</span></span>|<span data-ttu-id="f6abb-112">Указывает число страниц с содержимым базы данных в буферном пуле этого узла.</span><span class="sxs-lookup"><span data-stu-id="f6abb-112">Indicates the number of pages in the buffer pool on this node with database content.</span></span>|  
|<span data-ttu-id="f6abb-113">**Ожидаемый срок жизни страницы**</span><span class="sxs-lookup"><span data-stu-id="f6abb-113">**Page life expectancy**</span></span>|<span data-ttu-id="f6abb-114">Указывает минимальное количество секунд, в течение которых страница остается в буферном пуле этого узла без ссылок на нее.</span><span class="sxs-lookup"><span data-stu-id="f6abb-114">Indicates the minimum number of seconds a page will stay in the buffer pool on this node without references.</span></span>|  
|<span data-ttu-id="f6abb-115">**Поисков страниц на локальном узле/с**</span><span class="sxs-lookup"><span data-stu-id="f6abb-115">**Local Node page lookups/sec**</span></span>|<span data-ttu-id="f6abb-116">Указывает число запросов поиска с этого узла, которые были удовлетворены с этого узла.</span><span class="sxs-lookup"><span data-stu-id="f6abb-116">Indicates the number of lookup requests from this node which were satisfied from this node.</span></span>|  
|<span data-ttu-id="f6abb-117">**Поисков страниц на удаленных узлах/с**</span><span class="sxs-lookup"><span data-stu-id="f6abb-117">**Remote Note page lookups/sec**</span></span>|<span data-ttu-id="f6abb-118">Указывает число запросов поиска с этого узла, которые были удовлетворены с других узлов.</span><span class="sxs-lookup"><span data-stu-id="f6abb-118">Indicates the number of lookup requests from this node which were satisfied from other nodes.</span></span>|  
  
 <span data-ttu-id="f6abb-119">Если SQL Server выполняется на оборудовании, отличном от NUMA, то счетчики объектов **узел буфера** и **диспетчер буферов** должны иметь одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="f6abb-119">If SQL Server is running on non-NUMA hardware, the counters of **Buffer Node** and **Buffer Manager** objects should match.</span></span>  
  
 <span data-ttu-id="f6abb-120">На оборудовании NUMA суммы соответствующих счетчиков всех **узлов буфера** должны соответствовать своим дополнениям **диспетчера буферов**.</span><span class="sxs-lookup"><span data-stu-id="f6abb-120">On NUMA hardware, sums of respective counters of all **Buffer Nodes** should match their counterparts of **Buffer Manager**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6abb-121">Значения и суммы счетчиков могут точно не совпадать по причине динамической природы счетчиков и точности отбора значений.</span><span class="sxs-lookup"><span data-stu-id="f6abb-121">The counter values and sums may not match precisely due to the dynamic nature of the counters and the sampling accuracy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6abb-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="f6abb-122">See Also</span></span>  
 <span data-ttu-id="f6abb-123">[SQL Server, объект Buffer Manager](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="f6abb-123">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 <span data-ttu-id="f6abb-124">[Параметры конфигурации сервера «Server Memory»](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="f6abb-124">[Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="f6abb-125">[Наблюдение за использованием ресурсов (системный монитор)](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f6abb-125">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 [<span data-ttu-id="f6abb-126">sys.dm_os_performance_counters (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f6abb-126">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  
