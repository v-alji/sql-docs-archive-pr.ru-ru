---
title: Управление семантическим поиском и наблюдение за ним | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], managing
- semantic search [SQL Server], monitoring
ms.assetid: eb5c3b29-da70-42aa-aa97-7d35a3f1eb98
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 16e3af1d37f177dfe6d4e0cb090e7b8b0a4988d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733762"
---
# <a name="manage-and-monitor-semantic-search"></a><span data-ttu-id="4e476-102">Управление и наблюдение за семантическим поиском</span><span class="sxs-lookup"><span data-stu-id="4e476-102">Manage and Monitor Semantic Search</span></span>
  <span data-ttu-id="4e476-103">Описывается процесс семантического индексирования и задачи, связанные с наблюдением за индексами и управлением ими.</span><span class="sxs-lookup"><span data-stu-id="4e476-103">Describes the process of semantic indexing and the tasks related to managing and monitoring the indexes.</span></span>  
  
##  <a name="how-to-check-the-status-of-semantic-indexing"></a><a name="HowToMonitorStatus"></a><span data-ttu-id="4e476-104">Как проверить состояние семантического индексирования</span><span class="sxs-lookup"><span data-stu-id="4e476-104">How To: Check the Status of Semantic Indexing</span></span>  
 <span data-ttu-id="4e476-105">**Завершен ли первый этап семантического индексирования?**</span><span class="sxs-lookup"><span data-stu-id="4e476-105">**Is the first phase of semantic indexing complete?**</span></span>  
 <span data-ttu-id="4e476-106">Запросите динамическое административное представление [sys.dm_fts_index_population (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) и проверьте столбцы **status** и **status_description**.</span><span class="sxs-lookup"><span data-stu-id="4e476-106">Query the dynamic management view, [sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql), and check the **status** and **status_description** columns.</span></span>  
  
 <span data-ttu-id="4e476-107">Первый этап индексирования включает заполнение полнотекстового индекса ключевых слов и семантического индекса ключевых фраз, а также извлечение данных о подобии документов.</span><span class="sxs-lookup"><span data-stu-id="4e476-107">The first phase of indexing includes the population of the full-text keyword index and the semantic key phrase index, as well as the extraction of document similarity data.</span></span>  
  
```sql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_fts_index_population WHERE table_id = OBJECT_ID('table_name')  
GO  
```  
  
 <span data-ttu-id="4e476-108">**Завершен ли второй этап семантического индексирования?**</span><span class="sxs-lookup"><span data-stu-id="4e476-108">**Is the second phase of semantic indexing complete?**</span></span>  
 <span data-ttu-id="4e476-109">Запросите динамическое административное представление [sys.dm_fts_semantic_similarity_population (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql) и проверьте столбцы **status** и **status_description**.</span><span class="sxs-lookup"><span data-stu-id="4e476-109">Query the dynamic management view, [sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql), and check the **status** and **status_description** columns..</span></span>  
  
 <span data-ttu-id="4e476-110">Второй этап индексирования включает заполнение семантического индекса подобия документов.</span><span class="sxs-lookup"><span data-stu-id="4e476-110">The second phase of indexing includes the population of the semantic document similarity index.</span></span>  
  
```wql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_fts_semantic_similarity_population WHERE table_id = OBJECT_ID('table_name')  
GO  
```  
  
##  <a name="how-to-check-the-size-of-the-semantic-indexes"></a><a name="HowToCheckSize"></a><span data-ttu-id="4e476-111">Как проверить размер семантических индексов</span><span class="sxs-lookup"><span data-stu-id="4e476-111">How To: Check the Size of the Semantic Indexes</span></span>  
 <span data-ttu-id="4e476-112">**Каков логический размер семантического индекса ключевых фраз или семантического индекса подобия документов?**</span><span class="sxs-lookup"><span data-stu-id="4e476-112">**What is the logical size of a semantic key phrase index or a semantic document similarity index?**</span></span>  
 <span data-ttu-id="4e476-113">Запросите динамическое административное представление [sys.dm_db_fts_index_physical_stats (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4e476-113">Query the dynamic management view, [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="4e476-114">Логический размер отображается в количестве страниц индекса.</span><span class="sxs-lookup"><span data-stu-id="4e476-114">The logical size is displayed in number of index pages.</span></span>  
  
```sql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_db_fts_index_physical_stats WHERE object_id = OBJECT_ID('table_name')  
GO  
```  
  
 <span data-ttu-id="4e476-115">**Каков общий размер полнотекстового и семантического индексов для полнотекстового каталога?**</span><span class="sxs-lookup"><span data-stu-id="4e476-115">**What is the total size of the full-text and semantic indexes for a full-text catalog?**</span></span>  
 <span data-ttu-id="4e476-116">Запросите свойство **IndexSize** функции метаданных [FULLTEXTCATALOGPROPERTY (Transact-SQL)](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4e476-116">Query the **IndexSize** property of the [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) metadata function.</span></span>  
  
```sql  
SELECT FULLTEXTCATALOGPROPERTY('catalog_name', 'IndexSize')  
GO  
```  
  
 <span data-ttu-id="4e476-117">**Сколько элементов проиндексированы в полнотекстовом и семантическом индексах для полнотекстового каталога?**</span><span class="sxs-lookup"><span data-stu-id="4e476-117">**How many items are indexed in the full-text and semantic indexes for a full-text catalog?**</span></span>  
 <span data-ttu-id="4e476-118">Запросите свойство **ItemCount** функции метаданных [FULLTEXTCATALOGPROPERTY (Transact-SQL)](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4e476-118">Query the **ItemCount** property of the [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) metadata function.</span></span>  
  
```sql  
SELECT FULLTEXTCATALOGPROPERTY('catalog_name', 'ItemCount')  
GO  
```  
  
##  <a name="how-to-force-the-population-of-the-semantic-indexes"></a><a name="HowToForcePopulation"></a><span data-ttu-id="4e476-119">Как принудительно выполнить заполнение семантических индексов</span><span class="sxs-lookup"><span data-stu-id="4e476-119">How To: Force the Population of the Semantic Indexes</span></span>  
 <span data-ttu-id="4e476-120">Можно принудительно выполнить заполнение полнотекстового и семантического индексов с помощью предложений START/STOP/PAUSE или RESUME POPULATION с таким же синтаксисом и поведением, как описано для полнотекстовых индексов.</span><span class="sxs-lookup"><span data-stu-id="4e476-120">You can force the population of full-text and semantic indexes by using the START/STOP/PAUSE or RESUME POPULATION clause with the same syntax and behavior that is described for full-text indexes.</span></span> <span data-ttu-id="4e476-121">Дополнительные сведения см. в разделах [ALTER FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/alter-fulltext-index-transact-sql) и [Заполнение полнотекстовых индексов](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="4e476-121">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) and [Populate Full-Text Indexes](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="4e476-122">Поскольку семантическое индексирование зависит от полнотекстового индексирования, семантические индексы заполняются только после заполнения связанных полнотекстовых индексов.</span><span class="sxs-lookup"><span data-stu-id="4e476-122">Since semantic indexing is dependent on full-text indexing, semantic indexes are only populated when the associated full-text indexes are populated.</span></span>  
  
 <span data-ttu-id="4e476-123">**Пример. Запуск полного заполнения полнотекстового и семантического индексов**</span><span class="sxs-lookup"><span data-stu-id="4e476-123">**Example: Start a full population of full-text and semantic indexes**</span></span>  
  
 <span data-ttu-id="4e476-124">В следующем примере запускается заполнение полнотекстового и семантического индексов путем изменения существующего полнотекстового индекса таблицы **Production.Document** в образце базы данных AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="4e476-124">The following example starts full population of both full-text and semantic indexes by altering an existing full-text index on the **Production.Document** table in the AdventureWorks2012 sample database.</span></span>  
  
```vb  
USE AdventureWorks2012  
GO  
  
ALTER FULLTEXT INDEX ON Production.Document  
    START FULL POPULATION  
GO  
```  
  
##  <a name="how-to-disable-or-re-enable-semantic-indexing"></a><a name="HowToDisableIndexing"></a><span data-ttu-id="4e476-125">Как отключить или повторно включить семантическое индексирование</span><span class="sxs-lookup"><span data-stu-id="4e476-125">How To: Disable or Re-enable Semantic Indexing</span></span>  
 <span data-ttu-id="4e476-126">Можно включить или отключить полнотекстовое или семантическое индексирование с помощью предложений ENABLE/DISABLE с таким же синтаксисом и поведением, как описано для полнотекстовых индексов.</span><span class="sxs-lookup"><span data-stu-id="4e476-126">You can enable or disable full-text or semantic indexing by using the ENABLE/DISABLE clause with the same syntax and behavior that is described for full-text indexes.</span></span> <span data-ttu-id="4e476-127">Дополнительные сведения см. в статье [ALTER FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4e476-127">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="4e476-128">Если семантическое индексирование отключено и приостановлено, запросы к семантическим данным продолжают успешно выполняться и возвращать ранее проиндексированные данные.</span><span class="sxs-lookup"><span data-stu-id="4e476-128">When semantic indexing is disabled and suspended, queries over semantic data continue to work successfully and to return previously indexed data.</span></span> <span data-ttu-id="4e476-129">Такое поведение не согласуется с поведением полнотекстового поиска.</span><span class="sxs-lookup"><span data-stu-id="4e476-129">This behavior is not consistent with the behavior of Full-Text Search.</span></span>  
  
```sql  
-- To disable semantic indexing on a table  
USE database_name  
GO  
  
ALTER FULLTEXT INDEX ON table_name DISABLE  
GO  
  
-- To re-enable semantic indexing on a table  
USE database_name  
GO  
  
ALTER FULLTEXT INDEX ON table_name ENABLE  
GO  
```  
  
##  <a name="phases-of-semantic-indexing"></a><a name="SemanticIndexing"></a><span data-ttu-id="4e476-130">Фазы семантического индексирования</span><span class="sxs-lookup"><span data-stu-id="4e476-130">Phases of Semantic Indexing</span></span>  
 <span data-ttu-id="4e476-131">Для семантического поиска индексируются два типа данных для каждого столбца, по которому он включен.</span><span class="sxs-lookup"><span data-stu-id="4e476-131">Semantic Search indexes two kinds of data for each column on which it is enabled:</span></span>  
  
1.  <span data-ttu-id="4e476-132">**Ключевые фразы**</span><span class="sxs-lookup"><span data-stu-id="4e476-132">**Key phrases**</span></span>  
  
2.  <span data-ttu-id="4e476-133">**Подобие документов**</span><span class="sxs-lookup"><span data-stu-id="4e476-133">**Document similarity**</span></span>  
  
 <span data-ttu-id="4e476-134">Семантическое индексирование выполняется в два этапа совместно с полнотекстовым индексированием.</span><span class="sxs-lookup"><span data-stu-id="4e476-134">Semantic indexing occurs in two phases, in conjunction with full-text indexing:</span></span>  
  
1.  <span data-ttu-id="4e476-135">**Этап 1**.</span><span class="sxs-lookup"><span data-stu-id="4e476-135">**Phase 1**.</span></span> <span data-ttu-id="4e476-136">Полнотекстовый индекс ключевых слов и семантический индекс ключевых фраз заполняются параллельно и одновременно.</span><span class="sxs-lookup"><span data-stu-id="4e476-136">The full-text keyword index and the semantic key phrase index are populated in parallel at the same time.</span></span> <span data-ttu-id="4e476-137">Одновременно извлекаются данные, необходимые для индексирования подобия документов.</span><span class="sxs-lookup"><span data-stu-id="4e476-137">The data required to index document similarity is also extracted at this time.</span></span>  
  
2.  <span data-ttu-id="4e476-138">**Этап 2**.</span><span class="sxs-lookup"><span data-stu-id="4e476-138">**Phase 2**.</span></span> <span data-ttu-id="4e476-139">Затем заполняется семантический индекс подобия документов.</span><span class="sxs-lookup"><span data-stu-id="4e476-139">The semantic document similarity index is then populated.</span></span> <span data-ttu-id="4e476-140">Этот индекс зависит от обоих индексов, заполненных на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="4e476-140">This index depends on both indexes that were populated in the preceding phase.</span></span>  
  
##  <a name="BestPracticeUnderstand"></a>   
##  <a name="problem-semantic-indexes-are-not-populated"></a><a name="ProblemNotPopulated"></a><span data-ttu-id="4e476-141">Проблема. семантические индексы не заполнены</span><span class="sxs-lookup"><span data-stu-id="4e476-141">Problem: Semantic Indexes Are Not Populated</span></span>  
 <span data-ttu-id="4e476-142">**Заполнены ли связанные полнотекстовые индексы?**</span><span class="sxs-lookup"><span data-stu-id="4e476-142">**Are the associated full-text indexes populated?**</span></span>  
 <span data-ttu-id="4e476-143">Поскольку семантическое индексирование зависит от полнотекстового индексирования, семантические индексы заполняются только после заполнения связанных полнотекстовых индексов.</span><span class="sxs-lookup"><span data-stu-id="4e476-143">Since semantic indexing is dependent on full-text indexing, semantic indexes are only populated when the associated full-text indexes are populated.</span></span>  
  
 <span data-ttu-id="4e476-144">**Правильно ли установлены и настроены компоненты полнотекстового поиска и семантического поиска?**</span><span class="sxs-lookup"><span data-stu-id="4e476-144">**Are full-text search and semantic search properly installed and configured?**</span></span>  
 <span data-ttu-id="4e476-145">Дополнительные сведения см. в разделе [Установка и настройка семантического поиска](install-and-configure-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="4e476-145">For more information, see [Install and Configure Semantic Search](install-and-configure-semantic-search.md).</span></span>  
  
 <span data-ttu-id="4e476-146">**Не находится ли служба FDHOST в состоянии «недоступна» и нет ли других проблем, которые могли бы вызвать сбой полнотекстового индексирования?**</span><span class="sxs-lookup"><span data-stu-id="4e476-146">**Is the FDHOST service not available, or is there another condition that would cause full-text indexing to fail?**</span></span>  
 <span data-ttu-id="4e476-147">Дополнительные сведения см. в разделе [Устранение неполадок полнотекстового индексирования](troubleshoot-full-text-indexing.md).</span><span class="sxs-lookup"><span data-stu-id="4e476-147">For more information, see [Troubleshoot Full-Text Indexing](troubleshoot-full-text-indexing.md).</span></span>  
  
  
