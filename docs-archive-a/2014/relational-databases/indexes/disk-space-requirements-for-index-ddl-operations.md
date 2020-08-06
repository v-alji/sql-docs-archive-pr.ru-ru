---
title: Требования к месту на диске для DDL-операций индекса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- disk space [SQL Server], indexes
- index disk space [SQL Server]
- space [SQL Server], indexes
- indexes [SQL Server], disk space requirements
- temporary disk space [SQL Server]
ms.assetid: 35930826-c870-44c1-a966-a6a4638f62ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4ac25fc1555d6b6cfd8ee97b50d261cf5788f587
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668326"
---
# <a name="disk-space-requirements-for-index-ddl-operations"></a><span data-ttu-id="c6875-102">Disk Space Requirements for Index DDL Operations</span><span class="sxs-lookup"><span data-stu-id="c6875-102">Disk Space Requirements for Index DDL Operations</span></span>
  <span data-ttu-id="c6875-103">Наличие свободного места на диске имеет особое значение при создании, перестроении или удалении индексов.</span><span class="sxs-lookup"><span data-stu-id="c6875-103">Disk space is an important consideration when you create, rebuild, or drop indexes.</span></span> <span data-ttu-id="c6875-104">Недостаток места на диске может понизить производительность и даже вызвать ошибку операции с индексом.</span><span class="sxs-lookup"><span data-stu-id="c6875-104">Inadequate disk space can degrade performance or even cause the index operation to fail.</span></span> <span data-ttu-id="c6875-105">В этом разделе приведены общие сведения о том, как определить объем места на диске, необходимый для DDL-операций индекса.</span><span class="sxs-lookup"><span data-stu-id="c6875-105">This topic provides general information that can help you determine the amount of disk space required for index data definition language (DDL) operations.</span></span>  
  
## <a name="index-operations-that-require-no-additional-disk-space"></a><span data-ttu-id="c6875-106">Операции с индексами, для которых не нужно дополнительное место на диске</span><span class="sxs-lookup"><span data-stu-id="c6875-106">Index Operations That Require No Additional Disk Space</span></span>  
 <span data-ttu-id="c6875-107">Дополнительное место на диске не требуется для следующих операций с индексами.</span><span class="sxs-lookup"><span data-stu-id="c6875-107">The following index operations require no additional disk space:</span></span>  
  
-   <span data-ttu-id="c6875-108">ALTER INDEX REORGANIZE (однако необходимо место для журнала).</span><span class="sxs-lookup"><span data-stu-id="c6875-108">ALTER INDEX REORGANIZE; however, log space is required.</span></span>  
  
-   <span data-ttu-id="c6875-109">DROP INDEX (при удалении некластеризованного индекса).</span><span class="sxs-lookup"><span data-stu-id="c6875-109">DROP INDEX when you are dropping a nonclustered index.</span></span>  
  
-   <span data-ttu-id="c6875-110">DROP INDEX (при удалении вне сети кластеризованного индекса без предложения MOVE TO и в отсутствие некластеризованных индексов).</span><span class="sxs-lookup"><span data-stu-id="c6875-110">DROP INDEX when you are dropping a clustered index offline without specifying the MOVE TO clause and nonclustered indexes do not exist.</span></span>  
  
-   <span data-ttu-id="c6875-111">CREATE TABLE (PRIMARY KEY или ограничение UNIQUE).</span><span class="sxs-lookup"><span data-stu-id="c6875-111">CREATE TABLE (PRIMARY KEY or UNIQUE constraints)</span></span>  
  
## <a name="index-operations-that-require-additional-disk-space"></a><span data-ttu-id="c6875-112">Операции с индексами, требующие дополнительного места на диске.</span><span class="sxs-lookup"><span data-stu-id="c6875-112">Index Operations That Require Additional Disk Space</span></span>  
 <span data-ttu-id="c6875-113">Все остальные DDL-операции индекса требуют дополнительного временного места на диске на время операции, а также постоянного пространства для хранения новых структур индекса.</span><span class="sxs-lookup"><span data-stu-id="c6875-113">All other index DDL operations require additional temporary disk space to use during the operation, and permanent disk space to store the new index structure or structures.</span></span>  
  
 <span data-ttu-id="c6875-114">При создании новой структуры индекса место на диске требуется как для старой (исходной), так и для новой (целевой) структуры в соответствующих файлах и файловых группах.</span><span class="sxs-lookup"><span data-stu-id="c6875-114">When a new index structure is created, disk space for both the old (source) and new (target) structures is required in their appropriate files and filegroups.</span></span> <span data-ttu-id="c6875-115">Место, занимаемое старой структурой, не освобождается до тех пор, пока транзакция создания индекса не будет зафиксирована.</span><span class="sxs-lookup"><span data-stu-id="c6875-115">The old structure is not deallocated until the index creation transaction commits.</span></span>  
  
 <span data-ttu-id="c6875-116">Следующие DDL-операции индекса, создающие новые структуры индексов, требуют дополнительного места на диске:</span><span class="sxs-lookup"><span data-stu-id="c6875-116">The following index DDL operations create new index structures and require additional disk space:</span></span>  
  
-   <span data-ttu-id="c6875-117">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="c6875-117">CREATE INDEX</span></span>  
  
-   <span data-ttu-id="c6875-118">CREATE INDEX WITH DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="c6875-118">CREATE INDEX WITH DROP_EXISTING</span></span>  
  
-   <span data-ttu-id="c6875-119">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="c6875-119">ALTER INDEX REBUILD</span></span>  
  
-   <span data-ttu-id="c6875-120">ALTER TABLE ADD CONSTRAINT (PRIMARY KEY или ограничение UNIQUE)</span><span class="sxs-lookup"><span data-stu-id="c6875-120">ALTER TABLE ADD CONSTRAINT (PRIMARY KEY or UNIQUE)</span></span>  
  
-   <span data-ttu-id="c6875-121">ALTER TABLE DROP CONSTRAINT (ограничение PRIMARY KEY или UNIQUE) если ограничение основано на кластеризованном индексе;</span><span class="sxs-lookup"><span data-stu-id="c6875-121">ALTER TABLE DROP CONSTRAINT (PRIMARY KEY or UNIQUE) when the constraint is based on a clustered index</span></span>  
  
-   <span data-ttu-id="c6875-122">DROP INDEX MOVE TO (применяется только к кластеризованным индексам).</span><span class="sxs-lookup"><span data-stu-id="c6875-122">DROP INDEX MOVE TO (Applies only to clustered indexes.)</span></span>  
  
## <a name="temporary-disk-space-for-sorting"></a><span data-ttu-id="c6875-123">Временное место на диске для сортировки</span><span class="sxs-lookup"><span data-stu-id="c6875-123">Temporary Disk Space for Sorting</span></span>  
 <span data-ttu-id="c6875-124">Помимо места на диске, необходимого для исходной и целевой структур, требуется также временное место для сортировки. Оно не понадобится только в том случае, если оптимизатор запросов найдет план выполнения, не требующий сортировки.</span><span class="sxs-lookup"><span data-stu-id="c6875-124">Besides the disk space required for the source and target structures, temporary disk space is required for sorting, unless the query optimizer finds an execution plan that does not require sorting.</span></span>  
  
 <span data-ttu-id="c6875-125">Если сортировка необходима, то она выполняется для каждого нового индекса.</span><span class="sxs-lookup"><span data-stu-id="c6875-125">If sorting is required, sorting occurs one new index at a time.</span></span> <span data-ttu-id="c6875-126">Например, при перестройке кластеризованного индекса и связанных с ним некластеризованных индексов в рамках одной инструкции индексы сортируются один за другим.</span><span class="sxs-lookup"><span data-stu-id="c6875-126">For example, when you rebuild a clustered index and associated nonclustered indexes within a single statement, the indexes are sorted one after the other.</span></span> <span data-ttu-id="c6875-127">Следовательно, для сортировки необходимо по крайней мере столько дополнительного временного места на диске, сколько занимает самый большой индекс в операции.</span><span class="sxs-lookup"><span data-stu-id="c6875-127">Therefore, the additional temporary disk space that is required for sorting only has to be as large as the largest index in the operation.</span></span> <span data-ttu-id="c6875-128">Такой индекс почти всегда оказывается кластеризованным.</span><span class="sxs-lookup"><span data-stu-id="c6875-128">This is almost always the clustered index.</span></span>  
  
 <span data-ttu-id="c6875-129">Если параметр SORT_IN_TEMPDB имеет значение ON, то наибольший индекс должен помещаться в базе данных **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="c6875-129">If the SORT_IN_TEMPDB option is set to ON, the largest index must fit into **tempdb**.</span></span> <span data-ttu-id="c6875-130">Несмотря на то, что этот параметр увеличивает количество временного места на диске, используемого при создании индекса, он может сократить время создания индекса, если база данных **tempdb** и пользовательская база данных находятся на разных наборах дисков.</span><span class="sxs-lookup"><span data-stu-id="c6875-130">Although this option increases the amount of temporary disk space that is used to create an index, it may reduce the time that is required to create an index when **tempdb** is on a set of disks different from the user database.</span></span>  
  
 <span data-ttu-id="c6875-131">Если параметр SORT_IN_TEMPDB имеет значение OFF (по умолчанию), то каждый индекс, включая секционированные, сортируется в собственном месте назначения на диске; необходимо только место для новых структур индексов.</span><span class="sxs-lookup"><span data-stu-id="c6875-131">If SORT_IN_TEMPDB is set to OFF (the default) each index, including partitioned indexes, is sorted in its destination disk space; and only the disk space for the new index structures is required.</span></span>  
  
 <span data-ttu-id="c6875-132">Пример вычисления места на диске см. в разделе [Index Disk Space Example](index-disk-space-example.md).</span><span class="sxs-lookup"><span data-stu-id="c6875-132">For an example of calculating disk space, see [Index Disk Space Example](index-disk-space-example.md).</span></span>  
  
## <a name="temporary-disk-space-for-online-index-operations"></a><span data-ttu-id="c6875-133">Временное место на диске для действий с индексами в режиме в сети</span><span class="sxs-lookup"><span data-stu-id="c6875-133">Temporary Disk Space for Online Index Operations</span></span>  
 <span data-ttu-id="c6875-134">При выполнении действий с индексами в режиме в сети необходимо дополнительное временное место на диске.</span><span class="sxs-lookup"><span data-stu-id="c6875-134">When you perform index operations online, additional temporary disk space is required.</span></span>  
  
 <span data-ttu-id="c6875-135">При создании, перестройке или удалении вне сети кластеризованного индекса создается временный некластеризованный индекс для сопоставления старых закладок с новыми.</span><span class="sxs-lookup"><span data-stu-id="c6875-135">If a clustered index is created, rebuilt, or dropped online, a temporary nonclustered index is created to map old bookmarks to new bookmarks.</span></span> <span data-ttu-id="c6875-136">Если параметр SORT_IN_TEMPDB имеет значение ON, то этот временный индекс создается в базе данных **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="c6875-136">If the SORT_IN_TEMPDB option is set to ON, this temporary index is created in **tempdb**.</span></span> <span data-ttu-id="c6875-137">Если параметр SORT_IN_TEMPDB имеет значение OFF, то используется та же файловая группа или схема секционирования, что и для целевого индекса.</span><span class="sxs-lookup"><span data-stu-id="c6875-137">If SORT_IN_TEMPDB is set to OFF, the same filegroup or partition scheme as the target index is used.</span></span> <span data-ttu-id="c6875-138">Временный индекс сопоставления содержит одну запись для каждой строки таблицы, содержимое которой представляет собой объединенные старый и новый столбцы закладок, включая уникальные идентификаторы и идентификаторы записи, причем в этой таблице содержится только по одной копии каждого столбца, который используется в обеих закладках.</span><span class="sxs-lookup"><span data-stu-id="c6875-138">The temporary mapping index contains one record for each row in the table, and its contents is the union of the old and new bookmark columns, including uniqueifiers and record identifiers and including only a single copy of any column used in both bookmarks.</span></span> <span data-ttu-id="c6875-139">Дополнительные сведения об операциях с индексами в сети см. в статье [Выполнение операции с индексами в сети](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="c6875-139">For more information about online index operations, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6875-140">Для инструкций DROP INDEX нельзя задать параметр SORT_IN_TEMPDB.</span><span class="sxs-lookup"><span data-stu-id="c6875-140">The SORT_IN_TEMPDB option cannot be set for DROP INDEX statements.</span></span> <span data-ttu-id="c6875-141">Временный индекс сопоставления всегда создается в той же файловой группе или схеме секционирования, что и целевой индекс.</span><span class="sxs-lookup"><span data-stu-id="c6875-141">The temporary mapping index is always created in the same filegroup or partition scheme as the target index.</span></span>  
  
 <span data-ttu-id="c6875-142">Для действий с индексами в оперативном режиме применяется управление версиями строк, позволяющее изолировать действия с индексами от воздействия изменений, внесенных другими транзакциями.</span><span class="sxs-lookup"><span data-stu-id="c6875-142">Online index operations use row versioning to isolate the index operation from the effects of modifications made by other transactions.</span></span> <span data-ttu-id="c6875-143">Это исключает необходимость запрашивать общую блокировку уже считанных записей.</span><span class="sxs-lookup"><span data-stu-id="c6875-143">This avoids the need for requesting share locks on rows that have been read.</span></span> <span data-ttu-id="c6875-144">Для одновременных операций обновления и удаления, выполняемых пользователями во время операций с индексами в сети, требуется место в базе данных **tempdb**для сохранения записей версий.</span><span class="sxs-lookup"><span data-stu-id="c6875-144">Concurrent user update and delete operations during online index operations require space for version records in **tempdb**.</span></span> <span data-ttu-id="c6875-145">Дополнительные сведения см. в статье [Выполнение операции с индексами в сети](perform-index-operations-online.md) .</span><span class="sxs-lookup"><span data-stu-id="c6875-145">For more information, see [Perform Index Operations Online](perform-index-operations-online.md) .</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c6875-146">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="c6875-146">Related Tasks</span></span>  
 [<span data-ttu-id="c6875-147">Пример использования места на диске для индекса</span><span class="sxs-lookup"><span data-stu-id="c6875-147">Index Disk Space Example</span></span>](index-disk-space-example.md)  
  
 [<span data-ttu-id="c6875-148">Место на диске журнала транзакций для операций обработки индекса</span><span class="sxs-lookup"><span data-stu-id="c6875-148">Transaction Log Disk Space for Index Operations</span></span>](transaction-log-disk-space-for-index-operations.md)  
  
 [<span data-ttu-id="c6875-149">Оценка размера таблицы</span><span class="sxs-lookup"><span data-stu-id="c6875-149">Estimate the Size of a Table</span></span>](../databases/estimate-the-size-of-a-table.md)  
  
 [<span data-ttu-id="c6875-150">Оценка размера кластеризованного индекса</span><span class="sxs-lookup"><span data-stu-id="c6875-150">Estimate the Size of a Clustered Index</span></span>](../databases/estimate-the-size-of-a-clustered-index.md)  
  
 [<span data-ttu-id="c6875-151">Оценка размера некластеризованного индекса</span><span class="sxs-lookup"><span data-stu-id="c6875-151">Estimate the Size of a Nonclustered Index</span></span>](../databases/estimate-the-size-of-a-nonclustered-index.md)  
  
 [<span data-ttu-id="c6875-152">Оценка размера кучи</span><span class="sxs-lookup"><span data-stu-id="c6875-152">Estimate the Size of a Heap</span></span>](../databases/estimate-the-size-of-a-heap.md)  
  
## <a name="related-content"></a><span data-ttu-id="c6875-153">См. также</span><span class="sxs-lookup"><span data-stu-id="c6875-153">Related Content</span></span>  
 [<span data-ttu-id="c6875-154">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c6875-154">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
 [<span data-ttu-id="c6875-155">ALTER INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c6875-155">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
 [<span data-ttu-id="c6875-156">DROP INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c6875-156">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 [<span data-ttu-id="c6875-157">Указание коэффициента заполнения для индекса</span><span class="sxs-lookup"><span data-stu-id="c6875-157">Specify Fill Factor for an Index</span></span>](specify-fill-factor-for-an-index.md)  
  
 [<span data-ttu-id="c6875-158">Реорганизация и перестроение индексов</span><span class="sxs-lookup"><span data-stu-id="c6875-158">Reorganize and Rebuild Indexes</span></span>](indexes.md)  
  
  
