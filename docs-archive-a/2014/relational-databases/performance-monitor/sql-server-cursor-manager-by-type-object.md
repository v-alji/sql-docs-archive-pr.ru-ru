---
title: SQL Server, объект Cursor Manager by Type | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Cursor Manager by Type object
- SQLServer:Cursor Manager by Type
ms.assetid: d67fbd8a-7554-4a16-96f1-d9ee857a95e3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7bee15aa2917f7b8890e6c1d3f26cc0e210208a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656359"
---
# <a name="sql-server-cursor-manager-by-type-object"></a><span data-ttu-id="8b5bd-102">SQL Server: объект Cursor Manager by Type</span><span class="sxs-lookup"><span data-stu-id="8b5bd-102">SQL Server, Cursor Manager by Type Object</span></span>
  <span data-ttu-id="8b5bd-103">Объект **SQLServer: диспетчер курсоров по типу** содержит счетчики для отслеживания курсоров с группировкой по типу.</span><span class="sxs-lookup"><span data-stu-id="8b5bd-103">The **SQLServer:Cursor Manager by Type** object provides counters to monitor cursors, grouped by type.</span></span>  
  
 <span data-ttu-id="8b5bd-104">Следующая таблица описывает счетчики SQL Server **диспетчер курсоров по типу** .</span><span class="sxs-lookup"><span data-stu-id="8b5bd-104">This table describes the SQL Server **Cursor Manager by Type** counters.</span></span>  
  
|<span data-ttu-id="8b5bd-105">Счетчики «Cursor Manager by Type»</span><span class="sxs-lookup"><span data-stu-id="8b5bd-105">Cursor Manager by Type counters</span></span>|<span data-ttu-id="8b5bd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8b5bd-106">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="8b5bd-107">**Активные курсоры**</span><span class="sxs-lookup"><span data-stu-id="8b5bd-107">**Active cursors**</span></span>|<span data-ttu-id="8b5bd-108">Число активных курсоров.</span><span class="sxs-lookup"><span data-stu-id="8b5bd-108">Number of active cursors.</span></span>|  
|<span data-ttu-id="8b5bd-109">**Коэффициент попадания в кэш**</span><span class="sxs-lookup"><span data-stu-id="8b5bd-109">**Cache Hit Ratio**</span></span>|<span data-ttu-id="8b5bd-110">Соотношение между числом попаданий в кэш и числом уточняющих запросов.</span><span class="sxs-lookup"><span data-stu-id="8b5bd-110">Ratio between cache hits and lookups.</span></span>|  
|<span data-ttu-id="8b5bd-111">**Счетчик кэшированных курсоров**</span><span class="sxs-lookup"><span data-stu-id="8b5bd-111">**Cached Cursor Counts**</span></span>|<span data-ttu-id="8b5bd-112">Число курсоров данного типа, находящихся в кэше.</span><span class="sxs-lookup"><span data-stu-id="8b5bd-112">Number of cursors of a given type in the cache.</span></span>|  
|<span data-ttu-id="8b5bd-113">**Число использований кэша курсоров/с**</span><span class="sxs-lookup"><span data-stu-id="8b5bd-113">**Cursor Cache Use Count/sec**</span></span>|<span data-ttu-id="8b5bd-114">Число использований курсоров каждого из типов.</span><span class="sxs-lookup"><span data-stu-id="8b5bd-114">Times each type of cached cursor has been used.</span></span>|  
|<span data-ttu-id="8b5bd-115">**Использование памяти курсорами**</span><span class="sxs-lookup"><span data-stu-id="8b5bd-115">**Cursor memory usage**</span></span>|<span data-ttu-id="8b5bd-116">Объем памяти (в килобайтах), занятый курсорами.</span><span class="sxs-lookup"><span data-stu-id="8b5bd-116">Amount of memory consumed by cursors in kilobytes (KB).</span></span>|  
|<span data-ttu-id="8b5bd-117">**Запрошенных курсоров/с**</span><span class="sxs-lookup"><span data-stu-id="8b5bd-117">**Cursor Requests/sec**</span></span>|<span data-ttu-id="8b5bd-118">Число запросов SQL на курсоры, полученных сервером.</span><span class="sxs-lookup"><span data-stu-id="8b5bd-118">Number of SQL cursor requests received by server.</span></span>|  
|<span data-ttu-id="8b5bd-119">**Использование рабочих таблиц курсора**</span><span class="sxs-lookup"><span data-stu-id="8b5bd-119">**Cursor worktable usage**</span></span>|<span data-ttu-id="8b5bd-120">Число рабочих таблиц, занятых курсорами.</span><span class="sxs-lookup"><span data-stu-id="8b5bd-120">Number of worktables used by cursors.</span></span>|  
|<span data-ttu-id="8b5bd-121">**Количество активных планов исполнения курсора**</span><span class="sxs-lookup"><span data-stu-id="8b5bd-121">**Number of active cursor plans**</span></span>|<span data-ttu-id="8b5bd-122">Число планов курсоров.</span><span class="sxs-lookup"><span data-stu-id="8b5bd-122">Number of cursor plans.</span></span>|  
  
 <span data-ttu-id="8b5bd-123">Каждый из счетчиков объекта содержит следующие экземпляры.</span><span class="sxs-lookup"><span data-stu-id="8b5bd-123">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="8b5bd-124">Экземпляр диспетчера курсоров</span><span class="sxs-lookup"><span data-stu-id="8b5bd-124">Cursor Manager instance</span></span>|<span data-ttu-id="8b5bd-125">Описание</span><span class="sxs-lookup"><span data-stu-id="8b5bd-125">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="8b5bd-126">**_Total**</span><span class="sxs-lookup"><span data-stu-id="8b5bd-126">**_Total**</span></span>|<span data-ttu-id="8b5bd-127">Сведения обо всех курсорах.</span><span class="sxs-lookup"><span data-stu-id="8b5bd-127">Information for all cursors.</span></span>|  
|<span data-ttu-id="8b5bd-128">**API Cursor**</span><span class="sxs-lookup"><span data-stu-id="8b5bd-128">**API Cursor**</span></span>|<span data-ttu-id="8b5bd-129">Только сведения об API курсора.</span><span class="sxs-lookup"><span data-stu-id="8b5bd-129">Only the API cursor information.</span></span>|  
|<span data-ttu-id="8b5bd-130">**TSQL Global Cursor**</span><span class="sxs-lookup"><span data-stu-id="8b5bd-130">**TSQL Global Cursor**</span></span>|<span data-ttu-id="8b5bd-131">Только сведения о глобальных курсорах [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8b5bd-131">Only the [!INCLUDE[tsql](../../includes/tsql-md.md)] global cursor information.</span></span>|  
|<span data-ttu-id="8b5bd-132">**TSQL Local Cursor**</span><span class="sxs-lookup"><span data-stu-id="8b5bd-132">**TSQL Local Cursor**</span></span>|<span data-ttu-id="8b5bd-133">Только сведения о локальных курсорах [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8b5bd-133">Only the [!INCLUDE[tsql](../../includes/tsql-md.md)] local cursor information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b5bd-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b5bd-134">See Also</span></span>  
 [<span data-ttu-id="8b5bd-135">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="8b5bd-135">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
