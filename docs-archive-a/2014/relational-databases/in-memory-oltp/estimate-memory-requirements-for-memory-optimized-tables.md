---
title: Оценка требований к объему памяти для таблиц, оптимизированных для памяти | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5c5cc1fc-1fdf-4562-9443-272ad9ab5ba8
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5c5218a96d3650cbae22501ab2794b1b553996b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738393"
---
# <a name="estimate-memory-requirements-for-memory-optimized-tables"></a><span data-ttu-id="3524d-102">Оценка требований к объему памяти для таблиц, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="3524d-102">Estimate Memory Requirements for Memory-Optimized Tables</span></span>
  <span data-ttu-id="3524d-103">При создании новой [!INCLUDE[hek_2](../../includes/hek-2-md.md)] оптимизированной для памяти таблицы или переносе существующей дисковой таблицы в оптимизированную для памяти таблицу важно иметь разумную оценку потребностей в памяти для каждой таблицы, чтобы можно было подготавливать сервер с достаточным объемом памяти.</span><span class="sxs-lookup"><span data-stu-id="3524d-103">Whether you are creating a new [!INCLUDE[hek_2](../../includes/hek-2-md.md)] memory-optimized table or migrating an existing disk-based table to a memory-optimized table, it is important to have a reasonable estimate of each table's memory needs so you can provision the server with sufficient memory.</span></span> <span data-ttu-id="3524d-104">В этом разделе описывается, как определить объем памяти, необходимый для хранения данных в таблице, оптимизированной для памяти.</span><span class="sxs-lookup"><span data-stu-id="3524d-104">This section describes how to estimate the amount of memory that you need to hold data for a memory-optimized table.</span></span>  
  
 <span data-ttu-id="3524d-105">Если вы рассматриваете переход от дисковых таблиц к таблицам, оптимизированным для памяти, то перед продолжением чтения посмотрите в разделе [Определение, должна ли таблица или хранимая процедура быть перенесена в In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md) сведения о том, какие таблицы лучше всего подходят для миграции.</span><span class="sxs-lookup"><span data-stu-id="3524d-105">If you are contemplating migrating from disk-based tables to memory-optimized tables, before you proceed in this topic, see the topic [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md) for guidance on which tables are best to migrate.</span></span> <span data-ttu-id="3524d-106">Все разделы статьи [Миграция в In-Memory OLTP](migrating-to-in-memory-oltp.md) содержат руководство по миграции дисковых таблиц в оптимизированные для памяти.</span><span class="sxs-lookup"><span data-stu-id="3524d-106">All the topics under [Migrating to In-Memory OLTP](migrating-to-in-memory-oltp.md) provide guidance on migrating from disk-based to memory-optimized tables.</span></span>  
  
## <a name="sections-in-this-topic"></a><span data-ttu-id="3524d-107">Подразделы этого раздела</span><span class="sxs-lookup"><span data-stu-id="3524d-107">Sections in this topic</span></span>  
  
-   [<span data-ttu-id="3524d-108">Пример оптимизированной для памяти таблицы</span><span class="sxs-lookup"><span data-stu-id="3524d-108">Example memory-optimized table</span></span>](#bkmk_ExampleTable)  
  
-   [<span data-ttu-id="3524d-109">Память для таблицы</span><span class="sxs-lookup"><span data-stu-id="3524d-109">Memory for the table</span></span>](#bkmk_MemoryForTable)  
  
-   [<span data-ttu-id="3524d-110">Память для индексов</span><span class="sxs-lookup"><span data-stu-id="3524d-110">Memory for indexes</span></span>](#bkmk_IndexMeemory)  
  
-   [<span data-ttu-id="3524d-111">Память для управления версиями строк</span><span class="sxs-lookup"><span data-stu-id="3524d-111">Memory for row versioning</span></span>](#bkmk_MemoryForRowVersions)  
  
-   [<span data-ttu-id="3524d-112">Память для табличных переменных</span><span class="sxs-lookup"><span data-stu-id="3524d-112">Memory for table variables</span></span>](#bkmk_TableVariables)  
  
-   [<span data-ttu-id="3524d-113">Память под будущее увеличение</span><span class="sxs-lookup"><span data-stu-id="3524d-113">Memory for growth</span></span>](#bkmk_MemoryForGrowth)  
  
##  <a name="example-memory-optimized-table"></a><a name="bkmk_ExampleTable"></a> <span data-ttu-id="3524d-114">Пример оптимизированной для памяти таблицы</span><span class="sxs-lookup"><span data-stu-id="3524d-114">Example memory-optimized table</span></span>  
 <span data-ttu-id="3524d-115">Рассмотрим следующую схему таблицы, оптимизированной для памяти:</span><span class="sxs-lookup"><span data-stu-id="3524d-115">Consider the following memory-optimized table schema:</span></span>  
  
```sql  
  
CREATE TABLE t_hk (  
col1 int NOT NULL PRIMARY KEY NONCLUSTERED,  
col2 int NOT NULL INDEX t1c2_index   
     HASH WITH (bucket_count = 5000000),  
col3 int NOT NULL INDEX t1c3_index   
     HASH WITH (bucket_count = 5000000),  
col4 int NOT NULL INDEX t1c4_index   
     HASH WITH (bucket_count = 5000000),  
col5 int NOT NULL INDEX t1c5_index NONCLUSTERED,  
col6 char (50) NOT NULL,  
col7 char (50) NOT NULL,   
col8 char (30) NOT NULL,   
col9 char (50) NOT NULL  
     WITH (memory_optimized = on)  
GO  
  
```  
  
 <span data-ttu-id="3524d-116">С помощью этой схемы мы определим минимальный объем памяти, необходимый для оптимизированной для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="3524d-116">Using this schema we will determine the minimum memory needed for this memory-optimized table.</span></span>  
  
##  <a name="memory-for-the-table"></a><a name="bkmk_MemoryForTable"></a> <span data-ttu-id="3524d-117">Память для таблицы</span><span class="sxs-lookup"><span data-stu-id="3524d-117">Memory for the table</span></span>  
 <span data-ttu-id="3524d-118">Строка оптимизированной для памяти таблицы состоит из 3 частей:</span><span class="sxs-lookup"><span data-stu-id="3524d-118">A memory-optimized table row is comprised of three parts:</span></span>  
  
-   <span data-ttu-id="3524d-119">**Метки времени** </span><span class="sxs-lookup"><span data-stu-id="3524d-119">**Timestamps** </span></span>  
    <span data-ttu-id="3524d-120">Заголовок строки или метки времени = 24 байта.</span><span class="sxs-lookup"><span data-stu-id="3524d-120">Row header/timestamps = 24 bytes.</span></span>  
  
-   <span data-ttu-id="3524d-121">**Указатели индекса** </span><span class="sxs-lookup"><span data-stu-id="3524d-121">**Index pointers** </span></span>  
    <span data-ttu-id="3524d-122">Для каждого хэш-индекса в таблице каждая строка содержит 8-байтный адресный указатель на следующую строку в индексе.</span><span class="sxs-lookup"><span data-stu-id="3524d-122">For each hash index in the table, each row has an 8-byte address pointer to the next row in the index.</span></span>  <span data-ttu-id="3524d-123">Поскольку имеются 4 индекса, каждая строка выделит 32 байта для указателей индекса (указатель для каждого индекса занимает 8 байт).</span><span class="sxs-lookup"><span data-stu-id="3524d-123">Since there are 4 indexes, each row will allocate 32 bytes for index pointers (an 8 byte pointer for each index).</span></span>  
  
-   <span data-ttu-id="3524d-124">**Данные** </span><span class="sxs-lookup"><span data-stu-id="3524d-124">**Data** </span></span>  
    <span data-ttu-id="3524d-125">Размер данных в строке определяется путем суммирования размера типа данных для каждого столбца данных.</span><span class="sxs-lookup"><span data-stu-id="3524d-125">The size of the data portion of the row is determined by summing the type size for each data column.</span></span>  <span data-ttu-id="3524d-126">В нашей таблице имеется пять 4-байтных целых чисел, три 50-байтных символьных столбцов и один 30-байтный символьный столбец.</span><span class="sxs-lookup"><span data-stu-id="3524d-126">In our table we have five 4-byte integers, three 50-byte character columns, and one 30-byte character column.</span></span>  <span data-ttu-id="3524d-127">Поэтому часть данных в каждой строке — это 4 + 4 + 4 + 4 + 4 + 50 + 50 + 30 + 50 или 200 байт.</span><span class="sxs-lookup"><span data-stu-id="3524d-127">Therefore the data portion of each row is 4 + 4 + 4 + 4 + 4 + 50 + 50 + 30 + 50 or 200 bytes.</span></span>  
  
 <span data-ttu-id="3524d-128">Далее приведено вычисление размера для 5 миллионов строк в таблице, оптимизированной для памяти.</span><span class="sxs-lookup"><span data-stu-id="3524d-128">The following is a size computation for 5,000,000 (5 million) rows in a memory-optimized table.</span></span> <span data-ttu-id="3524d-129">Общий объем памяти, используемой строками данных, вычисляется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3524d-129">The total memory used by data rows is estimated as follows:</span></span>  
  
 <span data-ttu-id="3524d-130">**Память для строк таблицы**</span><span class="sxs-lookup"><span data-stu-id="3524d-130">**Memory for the table's rows**</span></span>  
  
 <span data-ttu-id="3524d-131">Из вышеуказанных вычислений, размер каждой строки в таблице, оптимизированной для памяти, будет 24 + 32 + 200 или 256 байт.</span><span class="sxs-lookup"><span data-stu-id="3524d-131">From the above calculations, the size of each row in the memory-optimized table is 24 + 32 + 200, or 256 bytes.</span></span>  <span data-ttu-id="3524d-132">Поскольку мы имеем 5 миллионов строк, таблица использует 5 000 000 \* 256 байт или 1 280 000 000 байт — примерно 1,28 ГБ.</span><span class="sxs-lookup"><span data-stu-id="3524d-132">Since we have 5 million rows, the table will consume 5,000,000 \* 256 bytes, or 1,280,000,000 bytes - approximately 1.28 GB.</span></span>  
  
##  <a name="memory-for-indexes"></a><a name="bkmk_IndexMeemory"></a> <span data-ttu-id="3524d-133">Память для индексов</span><span class="sxs-lookup"><span data-stu-id="3524d-133">Memory for indexes</span></span>  
 <span data-ttu-id="3524d-134">**Объем памяти для каждого хэш-индекса**</span><span class="sxs-lookup"><span data-stu-id="3524d-134">**Memory for each hash index**</span></span>  
  
 <span data-ttu-id="3524d-135">Каждый хэш-индекс — это хэш-массив, состоящий из 8-байтных указателей адреса.</span><span class="sxs-lookup"><span data-stu-id="3524d-135">Each hash index is a hash array of 8-byte address pointers.</span></span>  <span data-ttu-id="3524d-136">Размер массива лучше всего определяется количеством уникальных значений индекса в нем, то есть количество уникальных значений Col2 будет хорошей отправной точкой для подсчета размера массива t1c2_index.</span><span class="sxs-lookup"><span data-stu-id="3524d-136">The size of the array is best determined by the number of unique index values for that index - e.g., the number of unique Col2 values is a good starting point for the array size for the t1c2_index.</span></span> <span data-ttu-id="3524d-137">Слишком большой хэш-массив занимает много памяти.</span><span class="sxs-lookup"><span data-stu-id="3524d-137">A hash array that is too big wastes memory.</span></span>  <span data-ttu-id="3524d-138">Слишком маленький хэш-массив снижает производительность, поскольку будет слишком много конфликтов индексных значений, которые хэшируются в один и тот же индекс.</span><span class="sxs-lookup"><span data-stu-id="3524d-138">A hash array that is too small slows performance since there will be too many collisions by index values that hash to the same index.</span></span>  
  
 <span data-ttu-id="3524d-139">В хэш-индексах скорость поиска совпадений очень высока:</span><span class="sxs-lookup"><span data-stu-id="3524d-139">Hash indexes achieve very fast equality lookups such as:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE Col2 = 3  
  
```  
  
 <span data-ttu-id="3524d-140">Некластеризованные индексы будут быстрее при поиске диапазона, например:</span><span class="sxs-lookup"><span data-stu-id="3524d-140">Nonclustered indexes are faster for range lookups such as:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE Col2 >= 3  
  
```  
  
 <span data-ttu-id="3524d-141">При переносе дисковой таблицы можно использовать следующий критерий для определения количества уникальных значений в индексе t1c2_index.</span><span class="sxs-lookup"><span data-stu-id="3524d-141">If you are migrating a disk-based table you can use the following to determine the number of unique values for the index t1c2_index.</span></span>  
  
```sql  
  
SELECT COUNT(DISTINCT [Col2])  
  FROM t_hk  
  
```  
  
 <span data-ttu-id="3524d-142">При создании новой таблицы необходимо оценить размер массива или собрать данные путем теста еще до развертывания.</span><span class="sxs-lookup"><span data-stu-id="3524d-142">If you are creating a new table, you'll need to estimate the array size or gather data from your testing prior to deployment.</span></span>  
  
 <span data-ttu-id="3524d-143">Сведения о принципах работы хэш-индексов в оптимизированных для памяти таблицах [!INCLUDE[hek_2](../../includes/hek-2-md.md)] см. в разделе [Хэш-индексы](../../database-engine/hash-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="3524d-143">For information on how hash indexes work in [!INCLUDE[hek_2](../../includes/hek-2-md.md)] memory-optimized tables, see [Hash Indexes](../../database-engine/hash-indexes.md).</span></span>  
  
 <span data-ttu-id="3524d-144">**Примечание.** Невозможно изменить размер массива хэш-индекса на ходу.</span><span class="sxs-lookup"><span data-stu-id="3524d-144">**Note:** You cannot change the hash index array size on the fly.</span></span> <span data-ttu-id="3524d-145">Чтобы изменить размер массива хэш-индекса, нужно удалить таблицу, изменить значение bucket_count и повторно создать таблицу.</span><span class="sxs-lookup"><span data-stu-id="3524d-145">To change the hash index array size you must drop the table, change the bucket_count value and recreate the table.</span></span>  
  
 <span data-ttu-id="3524d-146">**Задание размера массива хэш-индекса**</span><span class="sxs-lookup"><span data-stu-id="3524d-146">**Setting the hash index array size**</span></span>  
  
 <span data-ttu-id="3524d-147">Размер хэш-массива задается `(bucket_count= <value>)` , где \<value> — это целочисленное значение больше нуля.</span><span class="sxs-lookup"><span data-stu-id="3524d-147">The hash array size is set by `(bucket_count= <value>)` where \<value> is an integer value greater than zero.</span></span> <span data-ttu-id="3524d-148">Если \<value> не является степенью 2, то фактическое значение bucket_count округляется вверх до следующего значения, являющегося степенью 2.</span><span class="sxs-lookup"><span data-stu-id="3524d-148">If \<value> is not a power of 2, the actual bucket_count is rounded up to the next closest power of 2.</span></span>  <span data-ttu-id="3524d-149">В нашем примере таблицы (bucket_count = 5000000), так как 5 000 000 не является степенью числа 2, фактическое число контейнеров округляется до 8 388 608 (2<sup>23</sup>).</span><span class="sxs-lookup"><span data-stu-id="3524d-149">In our example table, (bucket_count = 5000000), since 5,000,000 is not a power of 2, the actual bucket count rounds up to 8,388,608 (2<sup>23</sup>).</span></span>  <span data-ttu-id="3524d-150">Необходимо использовать это число, а не 5 000 000, при вычислении объема памяти, необходимого для хэш-массива.</span><span class="sxs-lookup"><span data-stu-id="3524d-150">You must use this number, not 5,000,000 when calculating memory needed by the hash array.</span></span>  
  
 <span data-ttu-id="3524d-151">Таким образом, в нашем примере для хэш-массива потребуется памяти:</span><span class="sxs-lookup"><span data-stu-id="3524d-151">Thus, in our example, the memory needed for each hash array is:</span></span>  
  
 <span data-ttu-id="3524d-152">8 388 608 \* 8 = 2<sup>23</sup> \* 8 = 2<sup>23</sup> \* 2<sup>3</sup> = 2<sup>26</sup> = 67 108 864 или приблизительно 64 МБ.</span><span class="sxs-lookup"><span data-stu-id="3524d-152">8,388,608 \* 8 = 2<sup>23</sup> \* 8 = 2<sup>23</sup> \* 2<sup>3</sup> = 2<sup>26</sup> = 67,108,864 or approximately 64 MB.</span></span>  
  
 <span data-ttu-id="3524d-153">Поскольку мы имеем 3 хэш-индекса, память, требуемая для хэш-индексов, — 64 МБ \* 3 = 192 МБ.</span><span class="sxs-lookup"><span data-stu-id="3524d-153">Since we have three hash indexes, the memory needed for the hash indexes is 3 \* 64MB = 192MB.</span></span>  
  
 <span data-ttu-id="3524d-154">**Память для некластеризованных индексов**</span><span class="sxs-lookup"><span data-stu-id="3524d-154">**Memory for nonclustered indexes**</span></span>  
  
 <span data-ttu-id="3524d-155">Некластеризованные индексы реализуются в виде B-деревьев, внутренние узлы которых содержат значения индекса и указатели на последующие узлы.</span><span class="sxs-lookup"><span data-stu-id="3524d-155">Nonclustered indexes are implemented as BTrees with the inner nodes containing the index value and pointers to subsequent nodes.</span></span>  <span data-ttu-id="3524d-156">Листовые узлы содержат значение индекса и указатель на строку таблицы в памяти.</span><span class="sxs-lookup"><span data-stu-id="3524d-156">Leaf nodes contain the index value and a pointer to the table row in memory.</span></span>  
  
 <span data-ttu-id="3524d-157">В отличие от хэш-индексов некластеризованные индексы не имеют фиксированного размера контейнера.</span><span class="sxs-lookup"><span data-stu-id="3524d-157">Unlike hash indexes, nonclustered indexes do not have a fixed bucket size.</span></span> <span data-ttu-id="3524d-158">Индекс динамически увеличивается и уменьшается вместе с данными.</span><span class="sxs-lookup"><span data-stu-id="3524d-158">The index grows and shrinks dynamically with the data.</span></span>  
  
 <span data-ttu-id="3524d-159">Объем памяти, требуемый для некластеризованных индексов, можно вычислить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3524d-159">Memory needed by nonclustered indexes can be computed as follows:</span></span>  
  
-   <span data-ttu-id="3524d-160">**Память, выделенная для неконечных узлов** </span><span class="sxs-lookup"><span data-stu-id="3524d-160">**Memory allocated to non-leaf nodes** </span></span>  
    <span data-ttu-id="3524d-161">В стандартной конфигурации объем памяти, выделенный для неконечных узлов, составляет небольшой процент от общей памяти, занятой индексом.</span><span class="sxs-lookup"><span data-stu-id="3524d-161">For a typical configuration, the memory allocated to non-leaf nodes is a small percentage of the overall memory taken by the index.</span></span> <span data-ttu-id="3524d-162">Это слишком мало, поэтому этот объем можно спокойно опустить.</span><span class="sxs-lookup"><span data-stu-id="3524d-162">This is so small it can safely be ignored.</span></span>  
  
-   <span data-ttu-id="3524d-163">**Память для конечных узлов** </span><span class="sxs-lookup"><span data-stu-id="3524d-163">**Memory for leaf nodes** </span></span>  
    <span data-ttu-id="3524d-164">Конечные узлы содержат по одной строке для каждого уникального ключа в таблице, и она указывает на строки данных с этим уникальным ключом.</span><span class="sxs-lookup"><span data-stu-id="3524d-164">The leaf nodes have one row for each unique key in the table that points to the data rows with that unique key.</span></span>  <span data-ttu-id="3524d-165">При наличии нескольких строк с одинаковым ключом (т. е. имеется неуникальный некластеризованный индекс) будет только одна строка в конечном узле индекса, указывающая на одну из строк, а другие строки будут связаны между собой.</span><span class="sxs-lookup"><span data-stu-id="3524d-165">If you have multiple rows with the same key (i.e., you have a non-unique nonclustered index), there is only one row in the index leaf node that points to one of the rows with the other rows linked to each other.</span></span>  <span data-ttu-id="3524d-166">Таким образом, общую память можно примерно вычислить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3524d-166">Thus, the total memory required can be approximated by:</span></span>   
    <span data-ttu-id="3524d-167">memoryForNonClusteredIndex = (pointerSize + sum(keyColumnDataTypeSizes)) \* rowsWithUniqueKeys</span><span class="sxs-lookup"><span data-stu-id="3524d-167">memoryForNonClusteredIndex = (pointerSize + sum(keyColumnDataTypeSizes)) \* rowsWithUniqueKeys</span></span>  
  
 <span data-ttu-id="3524d-168">Некластеризованные индексы лучше всего подходят для поиска по диапазону, как показано в следующем примере запроса:</span><span class="sxs-lookup"><span data-stu-id="3524d-168">Nonclustered indexes are best when used for range lookups, as exemplified by the following query:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE c2 > 5  
```  
  
##  <a name="memory-for-row-versioning"></a><a name="bkmk_MemoryForRowVersions"></a> <span data-ttu-id="3524d-169">Память для управления версиями строк</span><span class="sxs-lookup"><span data-stu-id="3524d-169">Memory for row versioning</span></span>  
 <span data-ttu-id="3524d-170">Чтобы избежать блокировок, модуль In-Memory OLTP использует оптимистический параллелизм при обновлении или удалении строк.</span><span class="sxs-lookup"><span data-stu-id="3524d-170">To avoid locks, In-Memory OLTP uses optimistic concurrency when updating or deleting rows.</span></span> <span data-ttu-id="3524d-171">Это означает, что при обновлении строки создается ее дополнительная версия.</span><span class="sxs-lookup"><span data-stu-id="3524d-171">This means that when a row is updated, an additional version of the row is created.</span></span> <span data-ttu-id="3524d-172">Система держит предыдущие версии до тех пор, пока все транзакции, которые теоретически могут использовать одну из версий, не завершатся.</span><span class="sxs-lookup"><span data-stu-id="3524d-172">The system keeps the previous versions available until all transactions that could possibly use the version have finished execution.</span></span> <span data-ttu-id="3524d-173">При удалении строки система действует точно так же, как и при обновлении, сохраняя версию до тех пор, пока она больше не понадобится.</span><span class="sxs-lookup"><span data-stu-id="3524d-173">When a row is deleted, the system acts in a similar way to an update, keeping the version available until it is no longer necessary.</span></span> <span data-ttu-id="3524d-174">Операции считывания и вставки не создают версии дополнительных строк.</span><span class="sxs-lookup"><span data-stu-id="3524d-174">Reads and inserts do not create additional row versions.</span></span>  
  
 <span data-ttu-id="3524d-175">Поскольку в любой момент в памяти может находиться некоторое количество дополнительных строк, ожидающих цикла сборки мусора для освобождения памяти, необходимо иметь достаточный объем памяти, чтобы учесть эти дополнительные строки.</span><span class="sxs-lookup"><span data-stu-id="3524d-175">Because there may be a number of additional rows in memory at any time waiting for the garbage collection cycle to release their memory, you must have sufficient memory to accommodate these additional rows.</span></span>  
  
 <span data-ttu-id="3524d-176">Число дополнительных строк может быть получено путем подсчета пикового количества обновлений и удалений строк в секунду, которое затем умножается на число секунд, которое занимает самая длинная транзакция (минимум 1 секунда).</span><span class="sxs-lookup"><span data-stu-id="3524d-176">The number of additional rows can be estimated by computing the peak number of row updates and deletions per second, then multiplying that by the number of seconds the longest transaction takes (minimum of 1).</span></span>  
  
 <span data-ttu-id="3524d-177">Затем это значение умножается на размер строки, что дает число байтов, необходимых для управления версиями строк.</span><span class="sxs-lookup"><span data-stu-id="3524d-177">That value is then multiplied by the row size to get the number of bytes you need for row versioning.</span></span>  
  
 `rowVersions = durationOfLongestTransactionInSeconds * peakNumberOfRowUpdatesOrDeletesPerSecond`  
  
 <span data-ttu-id="3524d-178">После этого потребности в памяти для устаревших строк оцениваются путем умножения количества устаревших строк на размер строки таблицы, оптимизированной для памяти (см. [таблицу](#bkmk_MemoryForTable) выше).</span><span class="sxs-lookup"><span data-stu-id="3524d-178">Memory needs for stale rows is then estimated by multiplying the number of stale rows by the size of a memory-optimized table row (see [Memory for the table](#bkmk_MemoryForTable) above).</span></span>  
  
 `memoryForRowVersions = rowVersions * rowSize`  
  
##  <a name="memory-for-table-variables"></a><a name="bkmk_TableVariables"></a> <span data-ttu-id="3524d-179">Память для табличных переменных</span><span class="sxs-lookup"><span data-stu-id="3524d-179">Memory for table variables</span></span>  
 <span data-ttu-id="3524d-180">Память, отведенная для табличных переменных, освобождается только в тех случаях, когда табличная переменная покидает область действия.</span><span class="sxs-lookup"><span data-stu-id="3524d-180">Memory used for a table variable is released only when the table variable goes out of scope.</span></span> <span data-ttu-id="3524d-181">Удаленные строки, включая строки, удаленные как часть обновления, из табличной переменной, не подвергаются сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="3524d-181">Deleted rows, including rows deleted as part of an update, from a table variable are not subject to garbage collection.</span></span> <span data-ttu-id="3524d-182">Ресурсы памяти не освобождаются до того момента, пока существует область табличных переменных.</span><span class="sxs-lookup"><span data-stu-id="3524d-182">No memory is released until the table variable exits scope.</span></span>  
  
 <span data-ttu-id="3524d-183">Табличные переменные, определенные в большом пакете SQL, в отличие от области действия процедур, используемых в нескольких транзакциях, могут потреблять большой объем памяти.</span><span class="sxs-lookup"><span data-stu-id="3524d-183">Table variables defined in a large SQL batch, as opposed to a procedure scope, which are used in many transactions, can consume a lot of memory.</span></span> <span data-ttu-id="3524d-184">Так как для них не применяется сборка мусора, удаленные строки в табличной переменной могут занимать большой объем памяти и, следовательно, могут снизить производительность, т. к. операции считывания должны сканировать эти удаленные строки.</span><span class="sxs-lookup"><span data-stu-id="3524d-184">Because they are not garbage collected, deleted rows in a table variable can consume a lot memory and degrade performance since read operations need to scan past the deleted rows.</span></span>  
  
##  <a name="memory-for-growth"></a><a name="bkmk_MemoryForGrowth"></a> <span data-ttu-id="3524d-185">Память под будущее увеличение</span><span class="sxs-lookup"><span data-stu-id="3524d-185">Memory for growth</span></span>  
 <span data-ttu-id="3524d-186">Указанные выше вычисления дают оценку потребного объема памяти для таблицы в том виде, в котором она существует в данный момент.</span><span class="sxs-lookup"><span data-stu-id="3524d-186">The above calculations estimate your memory needs for the table as it currently exists.</span></span> <span data-ttu-id="3524d-187">В дополнение к этому объему памяти необходимо оценить увеличение размера таблицы и предоставить достаточно памяти для ее будущего роста.</span><span class="sxs-lookup"><span data-stu-id="3524d-187">In addition to this memory, you need to estimate the growth of the table and provide sufficient memory to accommodate that growth.</span></span>  <span data-ttu-id="3524d-188">Например, если предполагается рост размера в 10 %, то следует умножить полученные ранее результаты на 1,1. Это и даст общую оценку объема памяти для таблицы.</span><span class="sxs-lookup"><span data-stu-id="3524d-188">For example, if you anticipate 10% growth then you need to multiple the results from above by 1.1 to get the total memory needed for your table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3524d-189">См. также:</span><span class="sxs-lookup"><span data-stu-id="3524d-189">See Also</span></span>  
 [<span data-ttu-id="3524d-190">Миграция в In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="3524d-190">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
