---
title: SQL Server, объект Plan Cache | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Plan Cache object
- SQLServer:Plan Cache
ms.assetid: 225e2b02-8d2f-4f29-9eba-f5847c36ea99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 002cbe261c531c18bdbb2170da9694cc8abde89d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729405"
---
# <a name="sql-server-plan-cache-object"></a><span data-ttu-id="6b764-102">SQL Server, объект Plan Cache</span><span class="sxs-lookup"><span data-stu-id="6b764-102">SQL Server, Plan Cache Object</span></span>
  <span data-ttu-id="6b764-103">Объект **Plan Cache** содержит счетчики, отслеживающие объем памяти, используемый [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для хранения таких объектов, как хранимые процедуры, нерегламентированные и подготовленные инструкции языка [!INCLUDE[tsql](../../includes/tsql-md.md)] и триггеры.</span><span class="sxs-lookup"><span data-stu-id="6b764-103">The **Plan Cache** object provides counters to monitor how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses memory to store objects such as stored procedures, ad hoc and prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, and triggers.</span></span> <span data-ttu-id="6b764-104">Параллельно можно отслеживать несколько экземпляров объекта **Plan Cache** , причем в каждом экземпляре могут отслеживаться различные типы плана.</span><span class="sxs-lookup"><span data-stu-id="6b764-104">Multiple instances of the **Plan Cache** object can be monitored at the same time, with each instance representing a different type of plan to monitor.</span></span>  
  
 <span data-ttu-id="6b764-105">В приведенной ниже таблице описываются счетчики **SQLServer:Plan Cache**.</span><span class="sxs-lookup"><span data-stu-id="6b764-105">This table describes are the **SQLServer:Plan Cache**counters.</span></span>  
  
|<span data-ttu-id="6b764-106">Счетчики объекта Plan Cache</span><span class="sxs-lookup"><span data-stu-id="6b764-106">SQL Server Plan Cache counters</span></span>|<span data-ttu-id="6b764-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6b764-107">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="6b764-108">**Коэффициент попадания в кэш**</span><span class="sxs-lookup"><span data-stu-id="6b764-108">**Cache Hit Ratio**</span></span>|<span data-ttu-id="6b764-109">Соотношение между числом попаданий в кэш и числом уточняющих запросов.</span><span class="sxs-lookup"><span data-stu-id="6b764-109">Ratio between cache hits and lookups.</span></span>|  
|<span data-ttu-id="6b764-110">**Счетчик объектов кэша**</span><span class="sxs-lookup"><span data-stu-id="6b764-110">**Cache Object Counts**</span></span>|<span data-ttu-id="6b764-111">Количество объектов в кэше.</span><span class="sxs-lookup"><span data-stu-id="6b764-111">Number of cache objects in the cache.</span></span>|  
|<span data-ttu-id="6b764-112">**Страницы кэша**</span><span class="sxs-lookup"><span data-stu-id="6b764-112">**Cache Pages**</span></span>|<span data-ttu-id="6b764-113">Количество 8-килобайтных страниц, занимаемых объектами кэша.</span><span class="sxs-lookup"><span data-stu-id="6b764-113">Number of 8-kilobyte (KB) pages used by cache objects.</span></span>|  
|<span data-ttu-id="6b764-114">**Используемых объектов кэша**</span><span class="sxs-lookup"><span data-stu-id="6b764-114">**Cache Objects in use**</span></span>|<span data-ttu-id="6b764-115">Количество используемых объектов кэша.</span><span class="sxs-lookup"><span data-stu-id="6b764-115">Number of cache objects in use.</span></span>|  
  
 <span data-ttu-id="6b764-116">Каждый из счетчиков объекта содержит следующие экземпляры.</span><span class="sxs-lookup"><span data-stu-id="6b764-116">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="6b764-117">Экземпляр объекта Plan Cache</span><span class="sxs-lookup"><span data-stu-id="6b764-117">Plan Cache instance</span></span>|<span data-ttu-id="6b764-118">Описание</span><span class="sxs-lookup"><span data-stu-id="6b764-118">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="6b764-119">**_Total**</span><span class="sxs-lookup"><span data-stu-id="6b764-119">**_Total**</span></span>|<span data-ttu-id="6b764-120">Сведения обо всех типах экземпляров кэша.</span><span class="sxs-lookup"><span data-stu-id="6b764-120">Information for all types of cache instances.</span></span>|  
|<span data-ttu-id="6b764-121">**Sql Plans**</span><span class="sxs-lookup"><span data-stu-id="6b764-121">**Sql Plans**</span></span>|<span data-ttu-id="6b764-122">Планы запросов, формируемые нерегламентированным запросом [!INCLUDE[tsql](../../includes/tsql-md.md)] , включая автоматически параметризованные запросы, либо инструкциями языка [!INCLUDE[tsql](../../includes/tsql-md.md)] , использующими процедуры **sp_prepare** или **sp_cursorprepare**.</span><span class="sxs-lookup"><span data-stu-id="6b764-122">Query plans produced from an ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] query, including auto-parameterized queries, or from [!INCLUDE[tsql](../../includes/tsql-md.md)] statements prepared using **sp_prepare** or **sp_cursorprepare**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6b764-123">кэширует планы нерегламентированных инструкций языка [!INCLUDE[tsql](../../includes/tsql-md.md)] для повторного использования при последующем выполнении идентичных инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b764-123">caches the plans for ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for later reuse if the identical [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is later executed.</span></span> <span data-ttu-id="6b764-124">Запросы, параметризованные пользователем (даже в случае, если они не были подготовлены явно) также отображаются в виде подготовленных планов SQL.</span><span class="sxs-lookup"><span data-stu-id="6b764-124">User-parameterized queries (even if not explicitly prepared) are also monitored as Prepared SQL Plans.</span></span>|  
|<span data-ttu-id="6b764-125">**Object Plans**</span><span class="sxs-lookup"><span data-stu-id="6b764-125">**Object Plans**</span></span>|<span data-ttu-id="6b764-126">Планы запроса, формируемые при создании хранимых процедур, функций и триггеров.</span><span class="sxs-lookup"><span data-stu-id="6b764-126">Query plans generated by creating a stored procedure, function, or trigger.</span></span>|  
|<span data-ttu-id="6b764-127">**Bound Trees**</span><span class="sxs-lookup"><span data-stu-id="6b764-127">**Bound Trees**</span></span>|<span data-ttu-id="6b764-128">Нормализованные деревья для представлений, правил, вычисляемых столбцов и проверочных ограничений.</span><span class="sxs-lookup"><span data-stu-id="6b764-128">Normalized trees for views, rules, computed columns, and check constraints.</span></span>|  
|<span data-ttu-id="6b764-129">**Расширенные хранимые процедуры**</span><span class="sxs-lookup"><span data-stu-id="6b764-129">**Extended Stored Procedures**</span></span>|<span data-ttu-id="6b764-130">Сведения из каталога о расширенных хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="6b764-130">Catalog information for extended stores procedures.</span></span>|  
|<span data-ttu-id="6b764-131">**Временные таблицы и переменные таблиц**</span><span class="sxs-lookup"><span data-stu-id="6b764-131">**Temporary Tables & Table Variables**</span></span>|<span data-ttu-id="6b764-132">Сведения из кэша, относящиеся к временным таблицам и табличным переменным.</span><span class="sxs-lookup"><span data-stu-id="6b764-132">Cache information related to temporary tables and table variables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b764-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="6b764-133">See Also</span></span>  
 <span data-ttu-id="6b764-134">[Параметры конфигурации сервера «Server Memory»](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="6b764-134">[Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="6b764-135">[SQL Server, объект Buffer Manager](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="6b764-135">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="6b764-136">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="6b764-136">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
