---
title: Свойства базы данных (страница "Хранилище запросов") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql13.swb.databaseproperties.querystore.f1
ms.assetid: da47d75e-291a-4305-acef-4b0aaf5215da
author: stevestein
ms.author: sstein
ms.openlocfilehash: bab0d9b697e9ad9ec4b27f320d26b9b9edb5944e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734125"
---
# <a name="database-properties-query-store-page"></a><span data-ttu-id="2dc25-102">Свойства базы данных (страница хранилища запросов)</span><span class="sxs-lookup"><span data-stu-id="2dc25-102">Database Properties (Query Store Page)</span></span>
  <span data-ttu-id="2dc25-103">Откройте эту страницу из основной базы данных и используйте ее для настройки и изменения свойств хранилища запросов базы данных.</span><span class="sxs-lookup"><span data-stu-id="2dc25-103">Access this page from the principal database, and use it to configure and to modify the properties of the database query store.</span></span> <span data-ttu-id="2dc25-104">Эти параметры можно также настроить с помощью [параметров ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="2dc25-104">These options can also be configure by using the [ALTER DATABASE SET options](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span> <span data-ttu-id="2dc25-105">Дополнительные сведения о хранилище запросов см. в разделе [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span><span class="sxs-lookup"><span data-stu-id="2dc25-105">For information about the query store, see [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span></span>  
  
||  
|-|  
|<span data-ttu-id="2dc25-106">**Применимо к**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2dc25-106">**Applies to**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].</span></span>|  
  
## <a name="options"></a><span data-ttu-id="2dc25-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="2dc25-107">Options</span></span>  
 <span data-ttu-id="2dc25-108">Включить</span><span class="sxs-lookup"><span data-stu-id="2dc25-108">Enable</span></span>  
 <span data-ttu-id="2dc25-109">Включает и отключает хранилище запросов.</span><span class="sxs-lookup"><span data-stu-id="2dc25-109">Enables and disables the query store.</span></span>  
  
 <span data-ttu-id="2dc25-110">Режим работы</span><span class="sxs-lookup"><span data-stu-id="2dc25-110">Operation Mode</span></span>  
 <span data-ttu-id="2dc25-111">Допустимые значения: READ_ONLY и READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="2dc25-111">Valid values are READ_ONLY and READ_WRITE.</span></span> <span data-ttu-id="2dc25-112">В режиме READ_WRITE хранилище запросов собирает и сохраняет план запросов и статистические данные о выполнении.</span><span class="sxs-lookup"><span data-stu-id="2dc25-112">In READ_WRITE mode, the query store collects and persists query plan and runtime execution statistics information.</span></span> <span data-ttu-id="2dc25-113">В режиме READ_ONLY можно считывать данные из хранилища запросов, но новые сведения не добавляется.</span><span class="sxs-lookup"><span data-stu-id="2dc25-113">In READ_ONLY mode, information can be read from the query store, but new information is not added.</span></span> <span data-ttu-id="2dc25-114">Если выделенное свободное место в хранилище запросов будет исчерпано, хранилище переключится в режим работы READ_ONLY.</span><span class="sxs-lookup"><span data-stu-id="2dc25-114">If the maximum allocated space of the query store has been exhausted, the query store will change its operation mode to READ_ONLY.</span></span>  
  
 <span data-ttu-id="2dc25-115">Режим работы (фактический)</span><span class="sxs-lookup"><span data-stu-id="2dc25-115">Operation Mode (Actual)</span></span>  
 <span data-ttu-id="2dc25-116">Получает фактический режим работы хранилища запросов.</span><span class="sxs-lookup"><span data-stu-id="2dc25-116">Gets the actual operation mode of the query store.</span></span>  
  
 <span data-ttu-id="2dc25-117">Режим работы (запрошенный)</span><span class="sxs-lookup"><span data-stu-id="2dc25-117">Operation Mode (Requested)</span></span>  
 <span data-ttu-id="2dc25-118">Получает и задает нужный режим работы хранилища запросов.</span><span class="sxs-lookup"><span data-stu-id="2dc25-118">Gets and sets the desired operation mode of the query store.</span></span>  
  
 <span data-ttu-id="2dc25-119">Интервал сброса данных (в минутах)</span><span class="sxs-lookup"><span data-stu-id="2dc25-119">Data Flush Interval (Minutes)</span></span>  
 <span data-ttu-id="2dc25-120">Определяет частоту, с которой данные, записанные в хранилище запросов, сохраняются на диск.</span><span class="sxs-lookup"><span data-stu-id="2dc25-120">Determines the frequency at which data written to the query store is persisted to disk.</span></span> <span data-ttu-id="2dc25-121">Для оптимизации производительности данные, собранные хранилищем запросов, асинхронно записываются на диск.</span><span class="sxs-lookup"><span data-stu-id="2dc25-121">To optimize for performance, data collected by the query store is asynchronously written to the disk.</span></span> <span data-ttu-id="2dc25-122">Настраивается частота, с которой происходит эта асинхронная передача.</span><span class="sxs-lookup"><span data-stu-id="2dc25-122">The frequency at which this asynchronous transfer occurs is configured.</span></span>  
  
 <span data-ttu-id="2dc25-123">Интервал сбора статистики</span><span class="sxs-lookup"><span data-stu-id="2dc25-123">Statistics Collection Interval</span></span>  
 <span data-ttu-id="2dc25-124">Получает и задает значение интервала сборка статистики.</span><span class="sxs-lookup"><span data-stu-id="2dc25-124">Gets and sets the statistics collection interval value.</span></span>  
  
 <span data-ttu-id="2dc25-125">Максимальный размер (Мбайт)</span><span class="sxs-lookup"><span data-stu-id="2dc25-125">Max Size (MB)</span></span>  
 <span data-ttu-id="2dc25-126">Получает и задает свободное место, выделенное для хранилища запросов.</span><span class="sxs-lookup"><span data-stu-id="2dc25-126">Gets and sets the total space allocated to the query store.</span></span>  
  
 <span data-ttu-id="2dc25-127">Пороговое значение устаревших запросов (в днях)</span><span class="sxs-lookup"><span data-stu-id="2dc25-127">Stale Query Threshold (Days)</span></span>  
 <span data-ttu-id="2dc25-128">Получает и задает пороговое значение устаревшего запроса.</span><span class="sxs-lookup"><span data-stu-id="2dc25-128">Gets and sets the stale query threshold.</span></span> <span data-ttu-id="2dc25-129">Настройте аргумент STALE_QUERY_THRESHOLD_DAYS, чтобы указать длительность хранения данных в хранилище запросов в днях.</span><span class="sxs-lookup"><span data-stu-id="2dc25-129">Configure the STALE_QUERY_THRESHOLD_DAYS argument to specify the number of days to retain data in the query store.</span></span>  
  
 <span data-ttu-id="2dc25-130">Очистка данных запроса</span><span class="sxs-lookup"><span data-stu-id="2dc25-130">Purge Query Data</span></span>  
 <span data-ttu-id="2dc25-131">Удаляет содержимое хранилища запросов.</span><span class="sxs-lookup"><span data-stu-id="2dc25-131">Removes the contents of the query store.</span></span>  
  
 <span data-ttu-id="2dc25-132">Круговые диаграммы</span><span class="sxs-lookup"><span data-stu-id="2dc25-132">Pie Charts</span></span>  
 <span data-ttu-id="2dc25-133">На схеме слева показано общее использование файлов базы данных на диске и часть файла, в которой содержатся данные хранилища запросов.</span><span class="sxs-lookup"><span data-stu-id="2dc25-133">The left chart shows the total database file consumption on the disk, and the portion of the file which is filled with the query store data.</span></span>  
  
 <span data-ttu-id="2dc25-134">На схеме справа показана часть квоты хранилища запросов, которая сейчас занята.</span><span class="sxs-lookup"><span data-stu-id="2dc25-134">The right chart shows the portion of the query store quota which is currently used up.</span></span> <span data-ttu-id="2dc25-135">Обратите внимание, что на левой схеме квота не показана.</span><span class="sxs-lookup"><span data-stu-id="2dc25-135">Note that the quota is not shown in the left chart.</span></span> <span data-ttu-id="2dc25-136">Квота может превышать текущий размер базы данных.</span><span class="sxs-lookup"><span data-stu-id="2dc25-136">The quota may exceed the current size of the database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dc25-137">Remarks</span><span class="sxs-lookup"><span data-stu-id="2dc25-137">Remarks</span></span>  
 <span data-ttu-id="2dc25-138">Хранилище запросов предоставляет DBA подробные сведения о выборе и производительности плана запросов.</span><span class="sxs-lookup"><span data-stu-id="2dc25-138">The query store feature provides DBAs with insight on query plan choice and performance.</span></span> <span data-ttu-id="2dc25-139">Оно упрощает устранение неполадок с производительностью, позволяя быстро находить разницу в производительности, вызванную изменениями в планах запросов.</span><span class="sxs-lookup"><span data-stu-id="2dc25-139">It simplifies performance troubleshooting by enabling you to quickly find performance differences caused by changes in query plans.</span></span> <span data-ttu-id="2dc25-140">Функция автоматически записывает журнал запросов, планы и статистику выполнения и сохраняет их для просмотра.</span><span class="sxs-lookup"><span data-stu-id="2dc25-140">The feature automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.</span></span> <span data-ttu-id="2dc25-141">Она разделяет данные по временным окнам, позволяя просмотреть шаблоны использования и понять, когда изменения плана запросов произошли на сервере.</span><span class="sxs-lookup"><span data-stu-id="2dc25-141">It separates data by time windows, allowing you to see database usage patterns and understand when query plan changes happened on the server.</span></span> <span data-ttu-id="2dc25-142">Хранилище запросов можно настроить на странице свойств базы данных хранилища запросов или с помощью параметра [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="2dc25-142">The query store can be configured by using this query store database property page, or by using the [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) option.</span></span> <span data-ttu-id="2dc25-143">Сведения в хранилище запросов представлены в диалоговом окне [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2dc25-143">The query store presents information by using a [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] dialog box.</span></span> <span data-ttu-id="2dc25-144">Дополнительные сведения о хранилище запросов см. в разделе [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span><span class="sxs-lookup"><span data-stu-id="2dc25-144">For more information about query store, see [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dc25-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="2dc25-145">See Also</span></span>  
 <span data-ttu-id="2dc25-146">[Query Store Stored Procedures (Transact-SQL)](/sql/relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql)  (Хранимые процедуры хранилища запросов (Transact-SQL))</span><span class="sxs-lookup"><span data-stu-id="2dc25-146">[Query Store Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="2dc25-147">Представления каталога хранилища запросов (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2dc25-147">Query Store Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/query-store-catalog-views-transact-sql)  
  
  
