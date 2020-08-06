---
title: Устранение распространенных проблем с производительностью с помощью хэш-индексов, оптимизированных для памяти | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 1954a997-7585-4713-81fd-76d429b8d095
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3cef98571edd7736bc45ba8caf17451007a74cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728670"
---
# <a name="troubleshooting-common-performance-problems-with-memory-optimized-hash-indexes"></a><span data-ttu-id="2fed3-102">Диагностика общих проблем с производительностью хэш-индексов оптимизированными для памяти таблиц</span><span class="sxs-lookup"><span data-stu-id="2fed3-102">Troubleshooting Common Performance Problems with Memory-Optimized Hash Indexes</span></span>
  <span data-ttu-id="2fed3-103">В этом разделе рассматривается устранение неполадок и обходные пути для распространенных проблем с хэш-индексами.</span><span class="sxs-lookup"><span data-stu-id="2fed3-103">This topic will focus on troubleshooting and working around common issues with hash indexes.</span></span>  
  
## <a name="search-requires-a-subset-of-hash-index-key-columns"></a><span data-ttu-id="2fed3-104">Поиску требуется подмножество ключевых столбцов хэш-индекса</span><span class="sxs-lookup"><span data-stu-id="2fed3-104">Search Requires a Subset of Hash Index Key Columns</span></span>  
 <span data-ttu-id="2fed3-105">**Вопрос.** Хэш-индексы должны иметь значения для всех ключевых столбцов индекса, чтобы вычислить хэш-значение, а также указать соответствующие строки в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="2fed3-105">**Issue:** Hash indexes require values for all index key columns in order to compute the hash value, and locate the corresponding rows in the hash table.</span></span> <span data-ttu-id="2fed3-106">Поэтому если запрос включает предикаты равенства только для подмножества ключей индекса в предложении WHERE, то [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] не может использовать поиск по индексу для нахождения строк, соответствующих предикатам в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="2fed3-106">Therefore, if a query includes equality predicates for only a subset of the index keys in the WHERE clause, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot use an index seek to locate the rows corresponding to the predicates in the WHERE clause.</span></span>  
  
 <span data-ttu-id="2fed3-107">Наоборот, упорядоченные индексы, так же как дисковые некластеризованные индексы и оптимизированные для памяти некластеризованные индексы, поддерживают поиск по индексу для подмножества ключевых столбцов индекса, если такие столбцы находятся в первых столбцах в индексе.</span><span class="sxs-lookup"><span data-stu-id="2fed3-107">In contrast, ordered indexes like the disk-based nonclustered indexes and the memory-optimized nonclustered indexes support index seek on a subset of the index key columns, as long as they are the leading columns in the index.</span></span>  
  
 <span data-ttu-id="2fed3-108">**Симптом:** Это приводит к снижению производительности, так как [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для выполнения полного сканирования таблицы требуется выполнить полное сканирование таблиц, а не поиск по индексу, что обычно является более быстрой операцией.</span><span class="sxs-lookup"><span data-stu-id="2fed3-108">**Symptom:** This results in a performance degradation, as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] needs to execute full table scans rather than an index seek, which is typically a faster operation.</span></span>  
  
 <span data-ttu-id="2fed3-109">**Устранение неполадок.** Помимо снижения производительности, проверка планов запросов покажет проверку, а не поиск по индексу.</span><span class="sxs-lookup"><span data-stu-id="2fed3-109">**How to troubleshoot:** Besides the performance degradation, inspection of the query plans will show a scan instead of an index seek.</span></span> <span data-ttu-id="2fed3-110">Если запрос простой, проверка текста запроса и определения индекса также покажет, требуется ли поиску подмножество ключевых столбцов индекса.</span><span class="sxs-lookup"><span data-stu-id="2fed3-110">If the query is fairly simple, inspection of the query text and index definition will also show whether the search requires a subset of the index key columns.</span></span>  
  
 <span data-ttu-id="2fed3-111">Рассмотрим следующую таблицу и запрос.</span><span class="sxs-lookup"><span data-stu-id="2fed3-111">Consider the following table and query:</span></span>  
  
```sql  
CREATE TABLE [dbo].[od]  
(  
     o_id INT NOT NULL,  
     od_id INT NOT NULL,  
     p_id INT NOT NULL,  
     CONSTRAINT PK_od PRIMARY KEY NONCLUSTERED HASH (o_id, od_id) WITH (BUCKET_COUNT = 10000)  
)  
WITH (MEMORY_OPTIMIZED = ON)  
  
 SELECT p_id  
 FROM dbo.od  
 WHERE o_id=1  
```  
  
 <span data-ttu-id="2fed3-112">Таблица содержит хэш-индекс для двух столбцов (o_id, od_id), в то время как в запросе есть предикат равенства для (o_id).</span><span class="sxs-lookup"><span data-stu-id="2fed3-112">The table has a hash index on the two columns (o_id, od_id), while the query has an equality predicate on (o_id).</span></span> <span data-ttu-id="2fed3-113">Так как запрос имеет предикаты равенства только для подмножества ключевых столбцов индекса, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] не сможет выполнить поиск по индексу с помощью PK_od, вместо этого [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] вынужденно вернется к полному просмотру индекса.</span><span class="sxs-lookup"><span data-stu-id="2fed3-113">As the query has equality predicates on only a subset of the index key columns, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot perform an index seek operation using PK_od; instead, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has to revert to a full index scan.</span></span>  
  
 <span data-ttu-id="2fed3-114">**Обходные пути:** Существует несколько возможных обходных путей.</span><span class="sxs-lookup"><span data-stu-id="2fed3-114">**Workarounds:** There are a number of possible workarounds.</span></span> <span data-ttu-id="2fed3-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="2fed3-115">For example:</span></span>  
  
-   <span data-ttu-id="2fed3-116">Создайте заново индекс некластеризованного типа вместо некластеризованного хэша.</span><span class="sxs-lookup"><span data-stu-id="2fed3-116">Recreate the index as type nonclustered instead of nonclustered hash.</span></span> <span data-ttu-id="2fed3-117">Оптимизированный для памяти некластеризованный индекс упорядочен, поэтому [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] сможет выполнить поиск по индексу в тех ключевых столбцах индекса, которые находятся в начале.</span><span class="sxs-lookup"><span data-stu-id="2fed3-117">The memory-optimized nonclustered index is ordered, and thus [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can perform an index seek on the leading index key columns.</span></span> <span data-ttu-id="2fed3-118">Результирующее определение первичного ключа в этом примере будет следующим: `constraint PK_od primary key nonclustered`.</span><span class="sxs-lookup"><span data-stu-id="2fed3-118">The resulting primary key definition for the example would be `constraint PK_od primary key nonclustered`.</span></span>  
  
-   <span data-ttu-id="2fed3-119">Измените текущий ключ индекса так, чтобы он соответствовал столбцам в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="2fed3-119">Change the current index key to match the columns in the WHERE clause.</span></span>  
  
-   <span data-ttu-id="2fed3-120">Добавьте новый хэш-индекс, который совпадает со столбцами в предложении WHERE запроса.</span><span class="sxs-lookup"><span data-stu-id="2fed3-120">Add a new hash index that matches with the columns in the WHERE clause of the query.</span></span> <span data-ttu-id="2fed3-121">В данном случае определение результирующей таблицы будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2fed3-121">In the example, the resulting table definition would look at follows:</span></span>  
  
    ```sql  
    CREATE TABLE dbo.od  
     ( o_id INT NOT NULL,  
     od_id INT NOT NULL,  
     p_id INT NOT NULL,  
  
     CONSTRAINT PK_od PRIMARY KEY   
     NONCLUSTERED HASH (o_id,od_id) WITH (BUCKET_COUNT=10000),  
  
     INDEX ix_o_id NONCLUSTERED HASH (o_id) WITH (BUCKET_COUNT=10000)  
  
     ) WITH (MEMORY_OPTIMIZED=ON)  
    ```  
  
 <span data-ttu-id="2fed3-122">Обратите внимание, что оптимизированный для памяти хэш-индекс не работает оптимально при наличии большого количества повторяющихся строк для заданного значения ключа индекса. в этом примере, если число уникальных значений для столбца o_id намного меньше, чем количество строк в таблице, не было бы оптимальным добавлять индекс в (o_id). Вместо этого лучшим решением будет изменение типа индекса PK_od от hash к некластеризованному.</span><span class="sxs-lookup"><span data-stu-id="2fed3-122">Note that a memory-optimized hash index does not perform optimally if there are a lot of duplicate rows for a given index key value: in the example, if the number of unique values for the column o_id is much smaller than the number of rows in the table, it would not be optimal to add an index on (o_id); instead, changing the type of the index PK_od from hash to nonclustered would be the better solution.</span></span> <span data-ttu-id="2fed3-123">Дополнительные сведения см. в разделе [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="2fed3-123">For more information, see [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fed3-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="2fed3-124">See Also</span></span>  
 [<span data-ttu-id="2fed3-125">Индексы для оптимизированных для памяти таблиц</span><span class="sxs-lookup"><span data-stu-id="2fed3-125">Indexes on Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
