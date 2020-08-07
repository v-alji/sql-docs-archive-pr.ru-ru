---
title: Рекомендации по использованию индексов в таблицах, оптимизированных для памяти | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
helpviewer_keywords:
- hash indexes
ms.assetid: 16ef63a4-367a-46ac-917d-9eebc81ab29b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f00d643088634c918eb626917eae64a001ce3678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732917"
---
# <a name="guidelines-for-using-indexes-on-memory-optimized-tables"></a><span data-ttu-id="2c21d-102">Рекомендации по использованию индексов в таблицах, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="2c21d-102">Guidelines for Using Indexes on Memory-Optimized Tables</span></span>
  <span data-ttu-id="2c21d-103">Индексы используются для повышения эффективности доступа к данным в таблицах [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c21d-103">Indexes are used for efficiently accessing data in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="2c21d-104">Правильное указание индексов может серьезно улучшить производительность запросов.</span><span class="sxs-lookup"><span data-stu-id="2c21d-104">Specifying the right indexes can dramatically improve query performance.</span></span> <span data-ttu-id="2c21d-105">Рассмотрим в качестве примера следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="2c21d-105">Consider, for example, the query:</span></span>  
  
```sql  
SELECT c1, c2 FROM t WHERE c1 = 1;  
```  
  
 <span data-ttu-id="2c21d-106">При отсутствии индекса для столбца c1 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] будет сканировать всю таблицу t, а затем фильтровать строки, которые удовлетворяют условию c1=1.</span><span class="sxs-lookup"><span data-stu-id="2c21d-106">If there is no index on column c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will need to scan the entire table t, and then filter on the rows that satisfy the condition c1=1.</span></span> <span data-ttu-id="2c21d-107">Однако, если t имеет индекс для столбца c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] может напрямую выполнить поиск по значению 1 и получить нужные строки.</span><span class="sxs-lookup"><span data-stu-id="2c21d-107">However, if t has an index on column c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can seek directly on the value 1 and retrieve the rows.</span></span>  
  
 <span data-ttu-id="2c21d-108">Для поиска записей, имеющих определенное значение или диапазон значений, одного или нескольких столбцов в таблице [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] может использовать индекс для этих столбцов, который ускоряет поиск соответствующих записей.</span><span class="sxs-lookup"><span data-stu-id="2c21d-108">When searching for records that have a specific value, or range of values, for one or more columns in the table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can use an index on those columns to quickly locate the corresponding records.</span></span> <span data-ttu-id="2c21d-109">Использование индексов повышает производительность таблиц, хранимых на диске, и таблиц, оптимизированных для памяти.</span><span class="sxs-lookup"><span data-stu-id="2c21d-109">Both disk-based and memory-optimized tables benefit from indexes.</span></span> <span data-ttu-id="2c21d-110">Однако существуют некоторые отличия в структуре индекса, которые следует учитывать при работе с таблицами, оптимизированными для памяти.</span><span class="sxs-lookup"><span data-stu-id="2c21d-110">There are, however, certain differences between index structures that need to be considered when using memory-optimized tables.</span></span> <span data-ttu-id="2c21d-111">(Индексы в таблицах, оптимизированных для памяти, называются индексами, оптимизированными для памяти.) Ниже приведены некоторые ключевые отличия.</span><span class="sxs-lookup"><span data-stu-id="2c21d-111">(Indexes on memory-optimized tables are referred to as memory-optimized indexes.) Some of the key differences are:</span></span>  
  
-   <span data-ttu-id="2c21d-112">Оптимизированные для памяти индексы должны создаваться с помощью [CREATE TABLE &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c21d-112">Memory-optimized indexes must be created with [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span> <span data-ttu-id="2c21d-113">Дисковое индексы могут создаваться с помощью `CREATE TABLE` и `CREATE INDEX`.</span><span class="sxs-lookup"><span data-stu-id="2c21d-113">Disk-based indexes can be created with `CREATE TABLE` and `CREATE INDEX`.</span></span>  
  
-   <span data-ttu-id="2c21d-114">Индексы, оптимизированные для памяти, существуют только в памяти.</span><span class="sxs-lookup"><span data-stu-id="2c21d-114">Memory-optimized indexes exist only in memory.</span></span> <span data-ttu-id="2c21d-115">Структуры индексов не сохраняются на диск, а операции с индексами в сети не записываются в журнал транзакций.</span><span class="sxs-lookup"><span data-stu-id="2c21d-115">Index structures are not persisted to disk and index operations are not logged in the transaction log.</span></span> <span data-ttu-id="2c21d-116">Структура индекса создается в тот момент, когда в памяти создается таблица, оптимизированная для памяти, как при исполнении инструкции CREATE TABLE, так и при запуске базы данных.</span><span class="sxs-lookup"><span data-stu-id="2c21d-116">The index structure is created when the memory-optimized table is created in memory, both during CREATE TABLE and during database startup.</span></span>  
  
-   <span data-ttu-id="2c21d-117">Индексы, оптимизированные для памяти, являются универсальными по природе.</span><span class="sxs-lookup"><span data-stu-id="2c21d-117">Memory-optimized indexes are inherently covering.</span></span> <span data-ttu-id="2c21d-118">Это означает, что все столбцы включаются в индекс и для таблиц, оптимизированных для памяти, не требуется поиск по закладкам.</span><span class="sxs-lookup"><span data-stu-id="2c21d-118">Covering means that all columns are virtually included in the index and bookmark lookups are not needed for memory-optimized tables.</span></span> <span data-ttu-id="2c21d-119">Вместо ссылки на первичный ключ индексы, оптимизированные для памяти, просто включают указатель памяти на фактическую строку в структуре данных таблицы.</span><span class="sxs-lookup"><span data-stu-id="2c21d-119">Rather than a reference to the primary key, memory-optimized indexes simply contain a memory pointer to the actual row in the table data structure.</span></span>  
  
-   <span data-ttu-id="2c21d-120">Понятия фрагментации и коэффициента заполнения неприменимы к индексам, оптимизированным для памяти.</span><span class="sxs-lookup"><span data-stu-id="2c21d-120">Fragmentation and fillfactor do not apply to memory-optimized indexes.</span></span> <span data-ttu-id="2c21d-121">Для индекса, сохраняемого на диске, фрагментация означает, что страницы сбалансированного дерева записываются на диск без какого-либо порядка.</span><span class="sxs-lookup"><span data-stu-id="2c21d-121">In disk-based indexes, fragmentation refers to pages in the B-tree being written to disk out-of-order.</span></span> <span data-ttu-id="2c21d-122">Индексы, оптимизированные для памяти, не записываются на диск и не считываются с диска.</span><span class="sxs-lookup"><span data-stu-id="2c21d-122">Memory-optimized indexes are not written to or read from disk.</span></span> <span data-ttu-id="2c21d-123">Фактор заполнения в индексах со структурой в виде сбалансированного дерева, сохраняемых на диск, — это степень, до которой структура физической страницы заполняется данными.</span><span class="sxs-lookup"><span data-stu-id="2c21d-123">Fillfactor in disk-based B-tree indexes refers to the degree to which the physical page structures are filled with actual data.</span></span> <span data-ttu-id="2c21d-124">Структура индекса, оптимизированного для памяти, не имеет страниц фиксированного размера.</span><span class="sxs-lookup"><span data-stu-id="2c21d-124">The memory-optimized index structures do not have fixed-size pages.</span></span>  
  
 <span data-ttu-id="2c21d-125">Существует два типа индексов, оптимизированных для памяти:</span><span class="sxs-lookup"><span data-stu-id="2c21d-125">There are two types of memory-optimized indexes:</span></span>  
  
-   <span data-ttu-id="2c21d-126">Некластеризованные хэш-индексы, которые созданы для уточняющих запросов.</span><span class="sxs-lookup"><span data-stu-id="2c21d-126">Nonclustered hash indexes, which are made for point lookups.</span></span> <span data-ttu-id="2c21d-127">Дополнительные сведения о хэш-индексах см. в разделе [хэш-индексы](hash-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="2c21d-127">For more information about hash indexes, see [Hash Indexes](hash-indexes.md).</span></span>  
  
-   <span data-ttu-id="2c21d-128">Некластеризованные индексы, которые создаются для сканирования диапазона и упорядоченного сканирования.</span><span class="sxs-lookup"><span data-stu-id="2c21d-128">Nonclustered indexes, which are made for range scans and ordered scans.</span></span>  
  
 <span data-ttu-id="2c21d-129">При использовании хэш-индекса доступ к данным осуществляется через хэш-таблицу в памяти.</span><span class="sxs-lookup"><span data-stu-id="2c21d-129">With a hash index, data is accessed through an in-memory hash table.</span></span> <span data-ttu-id="2c21d-130">Хэш-индексы не имеют страниц и всегда имеют фиксированный размер.</span><span class="sxs-lookup"><span data-stu-id="2c21d-130">Hash indexes do not have pages and are always of a fixed size.</span></span> <span data-ttu-id="2c21d-131">Однако хэш-индекс может содержать пустые хэш-контейнеры, что приводит к незначительной потере свободного места.</span><span class="sxs-lookup"><span data-stu-id="2c21d-131">However, a hash index can have empty hash buckets, which result in limited wasted space.</span></span> <span data-ttu-id="2c21d-132">Значения, возвращаемые запросом, использующим хэш-индекс, не сортируются.</span><span class="sxs-lookup"><span data-stu-id="2c21d-132">The values returned from a query using a hash index are not sorted.</span></span> <span data-ttu-id="2c21d-133">Хэш-индексы оптимизированы для поиска по индексу в предикатах равенства, а также поддерживают полное сканирование индекса.</span><span class="sxs-lookup"><span data-stu-id="2c21d-133">Hash indexes are optimized for index seeks on equality predicates and also support full index scans.</span></span>  
  
 <span data-ttu-id="2c21d-134">Некластеризованные индексы (не хэш-индексы) поддерживают все, что поддерживают хэш-индексы, а также операции поиска в предикатах неравенства (больше или меньше) и порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="2c21d-134">Nonclustered indexes (not hash indexes) support everything that hash indexes supports plus seek operations on inequality predicates such as greater than or less than, as well as sort order.</span></span> <span data-ttu-id="2c21d-135">Строки можно получать по порядку, указанному при создании индекса.</span><span class="sxs-lookup"><span data-stu-id="2c21d-135">Rows can be retrieved according to the order specified with index creation.</span></span> <span data-ttu-id="2c21d-136">Если порядок сортировки индекса совпадает с порядком сортировки, необходимым для конкретного запроса, например если ключ индекса совпадает с предложением ORDER BY, нет необходимости сортировать строки в составе выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="2c21d-136">If the sort order of the index matches the sort order required for a particular query, for example if the index key matches the ORDER BY clause, there is no need to sort the rows as part of query execution.</span></span> <span data-ttu-id="2c21d-137">Оптимизированные для памяти некластеризованные индексы однонаправлены. Они не поддерживают извлечение строк в порядке сортировки, обратном порядку сортировки индекса.</span><span class="sxs-lookup"><span data-stu-id="2c21d-137">Memory-optimized nonclustered indexes are unidirectional; they do not support retrieving rows in a sort order that is the reverse of the sort order of the index.</span></span> <span data-ttu-id="2c21d-138">Например, для индекса, определенного как (c1 ASC), невозможно сканировать индекс в обратном порядке, как (c1 DESC).</span><span class="sxs-lookup"><span data-stu-id="2c21d-138">For example, for an index specified as (c1 ASC), it is not possible to scan the index in reverse order, as (c1 DESC).</span></span>  
  
 <span data-ttu-id="2c21d-139">Каждый индекс использует память.</span><span class="sxs-lookup"><span data-stu-id="2c21d-139">Each index consumes memory.</span></span> <span data-ttu-id="2c21d-140">Хэш-индексы используют фиксированный размер памяти, который зависит от числа контейнеров.</span><span class="sxs-lookup"><span data-stu-id="2c21d-140">Hash indexes consume a fixed amount of memory, which is a function of the bucket count.</span></span> <span data-ttu-id="2c21d-141">У некластеризованных индексов потребление памяти является функцией от числа строк и размера ключевых столбцов индекса с некоторыми дополнительными издержками в зависимости от рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="2c21d-141">For nonclustered indexes, memory consumption is a function of the row count and the size of the index key columns, with some additional overhead depending on the workload.</span></span> <span data-ttu-id="2c21d-142">Память для индексов, оптимизированных для памяти, — это дополнительная память, которая отделена от памяти, используемой для хранения строк в таблицах, оптимизированных для памяти.</span><span class="sxs-lookup"><span data-stu-id="2c21d-142">Memory for memory-optimized indexes is in addition to and separate from the memory used to store rows in memory-optimized tables.</span></span>  
  
 <span data-ttu-id="2c21d-143">Повторяющиеся ключевые значения всегда делят один и тот же хэш-контейнер. </span><span class="sxs-lookup"><span data-stu-id="2c21d-143">Duplicate key values always share the same hash bucket.</span></span> <span data-ttu-id="2c21d-144">Если хэш-индекс содержит много повторяющихся ключевых значений, итоговые длинные цепочки хэширования ухудшат производительность.  </span><span class="sxs-lookup"><span data-stu-id="2c21d-144">If a hash index contains many duplicate key values, the resulting long hash chains will harm performance.</span></span> <span data-ttu-id="2c21d-145">Конфликты хэша, которые происходят в любом хэш-индексе, в последующем снизит производительность в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="2c21d-145">Hash collisions, which occur in any hash index, will further reduce performance in this scenario.</span></span> <span data-ttu-id="2c21d-146">По этой причине если число ключей уникального индекса не превышает числа 100 строк, то можно уменьшить риск конфликтов хэша, так как число контейнеров значительно превышает (по крайней мере в восьми раза больше количества уникальных ключей индекса; см. раздел [Определение правильного числа контейнеров для хэш-индексов](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) ) или можно полностью исключить конфликты хэша с помощью некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="2c21d-146">For that reason, if the number of unique index keys is at least 100 times smaller than the row count, you can reduce the risk of hash collisions by making the bucket count much larger (at least eight times the number of unique index keys; see [Determining the Correct Bucket Count for Hash Indexes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) for more information) or you can eliminate hash collisions entirely by using a nonclustered index.</span></span>  
  
## <a name="determining-which-indexes-to-use-for-a-memory-optimized-table"></a><span data-ttu-id="2c21d-147">Какие индексы следует использовать для таблицы, оптимизированной для памяти</span><span class="sxs-lookup"><span data-stu-id="2c21d-147">Determining Which Indexes to Use for a Memory-Optimized Table</span></span>  
 <span data-ttu-id="2c21d-148">Каждая оптимизированная для памяти таблица должна содержать как минимум один индекс.</span><span class="sxs-lookup"><span data-stu-id="2c21d-148">Each memory-optimized table must have at least one index.</span></span> <span data-ttu-id="2c21d-149">Обратите внимание, что каждое ограничение PRIMARY KEY неявно создает индекс.</span><span class="sxs-lookup"><span data-stu-id="2c21d-149">Note that each PRIMARY KEY constraint implicitly creates an index.</span></span> <span data-ttu-id="2c21d-150">Поэтому, если таблица имеет первичный ключ, она имеет индекс.</span><span class="sxs-lookup"><span data-stu-id="2c21d-150">Therefore, if a table has a primary key, it has an index.</span></span> <span data-ttu-id="2c21d-151">Первичный ключ является обязательным для надежной таблицы, оптимизированной для памяти.</span><span class="sxs-lookup"><span data-stu-id="2c21d-151">A primary key is a requirement for a durable memory-optimized table.</span></span>  
  
 <span data-ttu-id="2c21d-152">При запросе оптимизированной для памяти таблицы производительность хэш-индексов выше, если предложение предиката содержит только предикаты равенства.</span><span class="sxs-lookup"><span data-stu-id="2c21d-152">When querying a memory-optimized table, hash indexes perform better when the predicate clause contains only equality predicates.</span></span> <span data-ttu-id="2c21d-153">Предикат должен содержать все столбцы в ключе хэш-индекса.</span><span class="sxs-lookup"><span data-stu-id="2c21d-153">The predicate must include all columns in the hash index key.</span></span> <span data-ttu-id="2c21d-154">Хэш-индекс вернется к сканированию данного предиката неравенства.</span><span class="sxs-lookup"><span data-stu-id="2c21d-154">A hash index will revert to a scan given an inequality predicate.</span></span>  
  
 <span data-ttu-id="2c21d-155">Столбец в таблице, оптимизированной для памяти, может быть частью хэш-индекса и некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="2c21d-155">A column in a memory-optimized table can be part of both a hash index and a nonclustered index.</span></span>  
  
 <span data-ttu-id="2c21d-156">При запросе оптимизированной для памяти таблицы с предикатами неравенства некластеризованные индексы работают лучше, чем некластеризованные хэш-индексы.</span><span class="sxs-lookup"><span data-stu-id="2c21d-156">When querying a memory-optimized table with inequality predicates, nonclustered indexes will perform better than nonclustered hash indexes.</span></span>  
  
 <span data-ttu-id="2c21d-157">Для хэш-индекса требуется ключ (для хэша) для поиска в индексе.</span><span class="sxs-lookup"><span data-stu-id="2c21d-157">The hash index requires a key (to hash) to seek into the index.</span></span> <span data-ttu-id="2c21d-158">Если ключ индекса состоит из двух столбцов, а вы предоставляете только первый столбец, у [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] не будет полного ключа для хэширования.</span><span class="sxs-lookup"><span data-stu-id="2c21d-158">If an index key consists of two columns and you only provide the first column, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not have a complete key to hash.</span></span> <span data-ttu-id="2c21d-159">Это приведет к получению плана запроса сканирования индекса.</span><span class="sxs-lookup"><span data-stu-id="2c21d-159">This will result in an index scan query plan.</span></span> <span data-ttu-id="2c21d-160">Столбцы, которые необходимо проиндексировать, определяются на практике.</span><span class="sxs-lookup"><span data-stu-id="2c21d-160">Usage determines which columns should be indexed.</span></span>  
  
 <span data-ttu-id="2c21d-161">Если в нескольких строках столбца в некластеризованном индексе содержится одинаковое значение (ключевые столбцы индекса содержат много повторяющихся значений), производительность при обновлении, вставке и удалении может снизиться.</span><span class="sxs-lookup"><span data-stu-id="2c21d-161">When a column in a nonclustered index has the same value in many rows (index key columns have a lot of duplicate values), performance can degrade for updates, inserts, and deletions.</span></span>  <span data-ttu-id="2c21d-162">Один из способов повышения производительности в этой ситуации — добавление еще одного столбца в некластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="2c21d-162">One way to improve performance in this situation is to add another column to the nonclustered index.</span></span>  
  
### <a name="operations-on-memory-optimized-and-disk-based-indexes"></a><span data-ttu-id="2c21d-163">Операции с индексами с оптимизацией для памяти, хранимыми на диске.</span><span class="sxs-lookup"><span data-stu-id="2c21d-163">Operations on memory-optimized and disk-based indexes.</span></span>  
  
|<span data-ttu-id="2c21d-164">Операция</span><span class="sxs-lookup"><span data-stu-id="2c21d-164">Operation</span></span>|<span data-ttu-id="2c21d-165">Некластеризованный хэш-индекс, оптимизированный для памяти</span><span class="sxs-lookup"><span data-stu-id="2c21d-165">Memory-optimized, nonclustered hash, index</span></span>|<span data-ttu-id="2c21d-166">Некластеризованный индекс, оптимизированный для памяти</span><span class="sxs-lookup"><span data-stu-id="2c21d-166">Memory-optimized nonclustered index</span></span>|<span data-ttu-id="2c21d-167">Сохраняемый на диске индекс</span><span class="sxs-lookup"><span data-stu-id="2c21d-167">Disk-based index</span></span>|  
|---------------|-------------------------------------------------|------------------------------------------|-----------------------|  
|<span data-ttu-id="2c21d-168">Сканирование индекса, получение всех строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="2c21d-168">Index Scan, retrieve all table rows.</span></span>|<span data-ttu-id="2c21d-169">Да</span><span class="sxs-lookup"><span data-stu-id="2c21d-169">Yes</span></span>|<span data-ttu-id="2c21d-170">Да</span><span class="sxs-lookup"><span data-stu-id="2c21d-170">Yes</span></span>|<span data-ttu-id="2c21d-171">Да</span><span class="sxs-lookup"><span data-stu-id="2c21d-171">Yes</span></span>|  
|<span data-ttu-id="2c21d-172">Поиск по индексу с использованием предиката равенства (=).</span><span class="sxs-lookup"><span data-stu-id="2c21d-172">Index seek on equality predicate(s) (=).</span></span>|<span data-ttu-id="2c21d-173">Да</span><span class="sxs-lookup"><span data-stu-id="2c21d-173">Yes</span></span><br /><br /> <span data-ttu-id="2c21d-174">(Требуется полный ключ.)</span><span class="sxs-lookup"><span data-stu-id="2c21d-174">(Full key required.)</span></span>|<span data-ttu-id="2c21d-175">Да <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2c21d-175">Yes <sup>1</sup></span></span>|<span data-ttu-id="2c21d-176">Да</span><span class="sxs-lookup"><span data-stu-id="2c21d-176">Yes</span></span>|  
|<span data-ttu-id="2c21d-177">Поиск по индексу в предикатах неравенства (>, <, \<=, > =, Between).</span><span class="sxs-lookup"><span data-stu-id="2c21d-177">Index seek on inequality predicates (>, <, \<=, >=, BETWEEN).</span></span>|<span data-ttu-id="2c21d-178">Нет (получается при сканировании индекса)</span><span class="sxs-lookup"><span data-stu-id="2c21d-178">No (results in an index scan)</span></span>|<span data-ttu-id="2c21d-179">Да <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2c21d-179">Yes <sup>1</sup></span></span>|<span data-ttu-id="2c21d-180">Да</span><span class="sxs-lookup"><span data-stu-id="2c21d-180">Yes</span></span>|  
|<span data-ttu-id="2c21d-181">Получение строк, соответствующих определению индекса, с сортировкой.</span><span class="sxs-lookup"><span data-stu-id="2c21d-181">Retrieve rows in a sort-order matching the index definition.</span></span>|<span data-ttu-id="2c21d-182">Нет</span><span class="sxs-lookup"><span data-stu-id="2c21d-182">No</span></span>|<span data-ttu-id="2c21d-183">Да</span><span class="sxs-lookup"><span data-stu-id="2c21d-183">Yes</span></span>|<span data-ttu-id="2c21d-184">Да</span><span class="sxs-lookup"><span data-stu-id="2c21d-184">Yes</span></span>|  
|<span data-ttu-id="2c21d-185">Получение строк, соответствующих обратному определению индекса, с сортировкой.</span><span class="sxs-lookup"><span data-stu-id="2c21d-185">Retrieve rows in a sort-order matching the reverse of the index definition.</span></span>|<span data-ttu-id="2c21d-186">Нет</span><span class="sxs-lookup"><span data-stu-id="2c21d-186">No</span></span>|<span data-ttu-id="2c21d-187">Нет</span><span class="sxs-lookup"><span data-stu-id="2c21d-187">No</span></span>|<span data-ttu-id="2c21d-188">Да</span><span class="sxs-lookup"><span data-stu-id="2c21d-188">Yes</span></span>|  
  
 <span data-ttu-id="2c21d-189">В таблице Да означает, что индекс может адекватно обслуживать запрос, а Нет означает, что индекс не может быть успешно использован для удовлетворения запроса. </span><span class="sxs-lookup"><span data-stu-id="2c21d-189">In the table, Yes means that the index can adequately service the request and No means that the index cannot be used successfully to satisfy the request.</span></span>  
  
 <span data-ttu-id="2c21d-190"><sup>1</sup> для некластеризованного индекса, оптимизированного для памяти, полный ключ не требуется для выполнения поиска по индексу.</span><span class="sxs-lookup"><span data-stu-id="2c21d-190"><sup>1</sup> For a nonclustered memory-optimized index, the full key is not required to perform an index seek.</span></span> <span data-ttu-id="2c21d-191">В зависимости от порядка столбцов ключа индекса сканирование будет выполнено, если значение столбца следует после отсутствующего столбца.</span><span class="sxs-lookup"><span data-stu-id="2c21d-191">Although, given the column order of the index key, a scan will occur if a value for a column comes after a missing column.</span></span>  
  
## <a name="index-count"></a><span data-ttu-id="2c21d-192">Счетчик индекса</span><span class="sxs-lookup"><span data-stu-id="2c21d-192">Index Count</span></span>  
 <span data-ttu-id="2c21d-193">Оптимизированные для памяти таблицы могут иметь до 8 индексов, включая индекс, создаваемый первичным ключом. </span><span class="sxs-lookup"><span data-stu-id="2c21d-193">A memory-optimized table can have up to 8 indexes, including the index created with the primary key.</span></span>  
  
 <span data-ttu-id="2c21d-194">При создании определенного числа индексов для таблицы, оптимизированной для памяти, следует иметь в виду следующее.</span><span class="sxs-lookup"><span data-stu-id="2c21d-194">Regarding the number of indexes created on a memory-optimized table, consider the following:</span></span>  
  
-   <span data-ttu-id="2c21d-195">Следует указать необходимые индексы во время создания таблицы.</span><span class="sxs-lookup"><span data-stu-id="2c21d-195">Specify the indexes you need when you create the table.</span></span> <span data-ttu-id="2c21d-196">Нельзя создать индекс для таблицы, оптимизированной для памяти, после создания таблицы.</span><span class="sxs-lookup"><span data-stu-id="2c21d-196">You cannot create an index for a memory-optimized table after the table is created.</span></span> <span data-ttu-id="2c21d-197">Если необходимо добавить индекс к таблице, оптимизированной для памяти, удалите и снова создайте таблицу.</span><span class="sxs-lookup"><span data-stu-id="2c21d-197">If you want to add an index to a memory-optimized table, drop and recreate that table.</span></span>  
  
-   <span data-ttu-id="2c21d-198">Не создавайте индекс, который будет использоваться редко.</span><span class="sxs-lookup"><span data-stu-id="2c21d-198">Do not create an index that you rarely use:</span></span>  
  
     <span data-ttu-id="2c21d-199">Сборка мусора работает лучше, если все индексы таблицы используются часто.</span><span class="sxs-lookup"><span data-stu-id="2c21d-199">Garbage collection works best if all indexes on the table are frequently used.</span></span> <span data-ttu-id="2c21d-200">Редко используемые индексы могут помешать системе сборки мусора работать оптимально для старых версий строк.</span><span class="sxs-lookup"><span data-stu-id="2c21d-200">Rarely-used indexes may cause the garbage collection system to not perform optimally for old row versions.</span></span>  
  
## <a name="creating-a-memory-optimized-index-code-samples"></a><span data-ttu-id="2c21d-201">Создание оптимизированного для памяти индекса: примеры кода</span><span class="sxs-lookup"><span data-stu-id="2c21d-201">Creating a Memory-Optimized Index: Code Samples</span></span>  
 <span data-ttu-id="2c21d-202">Хэш-индекс уровня столбца:</span><span class="sxs-lookup"><span data-stu-id="2c21d-202">Column level hash index:</span></span>  
  
```sql  
CREATE TABLE t1   
   (c1 INT NOT NULL INDEX idx HASH WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="2c21d-203">Хэш-индекс уровня таблицы:</span><span class="sxs-lookup"><span data-stu-id="2c21d-203">Table level hash index:</span></span>  
  
```sql  
CREATE TABLE t1_1   
   (c1 INT NOT NULL,   
   INDEX IDX HASH (c1) WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="2c21d-204">Хэш-индекс первичного ключа уровня столбца:</span><span class="sxs-lookup"><span data-stu-id="2c21d-204">Column level primary key hash index:</span></span>  
  
```sql  
CREATE TABLE t2   
   (c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="2c21d-205">Хэш-индекс первичного ключа уровня таблицы:</span><span class="sxs-lookup"><span data-stu-id="2c21d-205">Table level primary key hash index:</span></span>  
  
```sql  
CREATE TABLE t2_2   
   (c1 INT NOT NULL,   
   PRIMARY KEY NONCLUSTERED HASH (c1) WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="2c21d-206">Некластеризованный индекс на уровне столбцов:</span><span class="sxs-lookup"><span data-stu-id="2c21d-206">Column level nonclustered index:</span></span>  
  
```sql  
CREATE TABLE t3   
   (c1 INT NOT NULL INDEX ID)   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="2c21d-207">Некластеризованный индекс на уровне таблиц:</span><span class="sxs-lookup"><span data-stu-id="2c21d-207">Table level nonclustered  index:</span></span>  
  
```sql  
CREATE TABLE t3_3   
   (c1 INT NOT NULL,   
   INDEX IDX NONCLUSTERED (c1))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="2c21d-208">Некластеризованный индекс диапазона первичного ключа на уровне столбцов:</span><span class="sxs-lookup"><span data-stu-id="2c21d-208">Column level primary key nonclustered  index:</span></span>  
  
```sql  
CREATE TABLE t4   
   (c1 INT NOT NULL PRIMARY KEY NONCLUSTERED)   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="2c21d-209">Некластеризованный индекс первичного ключа на уровне таблиц:</span><span class="sxs-lookup"><span data-stu-id="2c21d-209">Table level primary key nonclustered index:</span></span>  
  
```sql  
CREATE TABLE t4_4   
   (c1 INT NOT NULL,   
   PRIMARY KEY NONCLUSTERED (c1))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="2c21d-210">Индекс с несколькими столбцами определен после определения столбцов:</span><span class="sxs-lookup"><span data-stu-id="2c21d-210">Multicolumn index defined after columns are defined:</span></span>  
  
```sql  
create table t (  
       a int not null constraint ta primary key nonclustered,  
       b int not null,  
       c int not null,  
       d int not null,  
       index idx_t_b_c_d nonclustered (b, c asc, d desc)  
) with (memory_optimized = on, durability = SCHEMA_AND_DATA)  
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c21d-211">См. также:</span><span class="sxs-lookup"><span data-stu-id="2c21d-211">See Also</span></span>  
 <span data-ttu-id="2c21d-212">[Индексы в таблицах, оптимизированных для памяти](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="2c21d-212">[Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="2c21d-213">[Определение правильного числа контейнеров для хэш-индексов](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="2c21d-213">[Determining the Correct Bucket Count for Hash Indexes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) </span></span>  
 [<span data-ttu-id="2c21d-214">Хэш-индексы</span><span class="sxs-lookup"><span data-stu-id="2c21d-214">Hash Indexes</span></span>](hash-indexes.md)  
  
  
