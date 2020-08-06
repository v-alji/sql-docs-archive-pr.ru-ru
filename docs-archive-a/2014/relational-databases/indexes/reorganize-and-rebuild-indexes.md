---
title: Реорганизация и перестроение индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.fragmentation.f1
- sql12.swb.index.reorg.f1
- sql12.swb.index.rebuild.f1
helpviewer_keywords:
- large object defragmenting
- indexes [SQL Server], reorganizing
- index reorganization [SQL Server]
- reorganizing indexes
- defragmenting large object data types
- index fragmentation [SQL Server]
- index rebuilding [SQL Server]
- rebuilding indexes
- indexes [SQL Server], rebuilding
- defragmenting indexes
- nonclustered indexes [SQL Server], defragmenting
- fragmentation [SQL Server]
- index defragmenting [SQL Server]
- LOB data [SQL Server], defragmenting
- clustered indexes, defragmenting
ms.assetid: a28c684a-c4e9-4b24-a7ae-e248808b31e9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c00f2128bb4c54064511ffff9e8929c9faf4d59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739965"
---
# <a name="reorganize-and-rebuild-indexes"></a><span data-ttu-id="7bf87-102">Реорганизация и перестроение индексов</span><span class="sxs-lookup"><span data-stu-id="7bf87-102">Reorganize and Rebuild Indexes</span></span>
  <span data-ttu-id="7bf87-103">В этом разделе описывается реорганизация или перестроение фрагментированного индекса в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bf87-103">This topic describes how to reorganize or rebuild a fragmented index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7bf87-104">Компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] автоматически поддерживает состояние индексов при выполнении операций вставки, обновления или удаления в отношении базовых данных.</span><span class="sxs-lookup"><span data-stu-id="7bf87-104">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatically maintains indexes whenever insert, update, or delete operations are made to the underlying data.</span></span> <span data-ttu-id="7bf87-105">Со временем эти изменения могут привести к тому, что данные в индексе окажутся разбросанными по базе данных (фрагментированными).</span><span class="sxs-lookup"><span data-stu-id="7bf87-105">Over time these modifications can cause the information in the index to become scattered in the database (fragmented).</span></span> <span data-ttu-id="7bf87-106">Фрагментация имеет место в тех случаях, когда в индексах содержатся страницы, для которых логический порядок, основанный на значении ключа, не совпадает с физическим порядком в файле данных.</span><span class="sxs-lookup"><span data-stu-id="7bf87-106">Fragmentation exists when indexes have pages in which the logical ordering, based on the key value, does not match the physical ordering inside the data file.</span></span> <span data-ttu-id="7bf87-107">Значительно фрагментированные индексы могут серьезно снижать производительность запросов и служить причиной замедления откликов приложения.</span><span class="sxs-lookup"><span data-stu-id="7bf87-107">Heavily fragmented indexes can degrade query performance and cause your application to respond slowly.</span></span>  
  
 <span data-ttu-id="7bf87-108">Можно устранить фрагментацию путем реорганизации или перестроения индекса.</span><span class="sxs-lookup"><span data-stu-id="7bf87-108">You can remedy index fragmentation by reorganizing or rebuilding an index.</span></span> <span data-ttu-id="7bf87-109">Для секционированных индексов, построенных на основе схемы секционирования, можно использовать любой из этих методов для всего индекса или отдельной его секции.</span><span class="sxs-lookup"><span data-stu-id="7bf87-109">For partitioned indexes built on a partition scheme, you can use either of these methods on a complete index or a single partition of an index.</span></span> <span data-ttu-id="7bf87-110">При перестроении старый индекс удаляется, и создается новый.</span><span class="sxs-lookup"><span data-stu-id="7bf87-110">Rebuilding an index drops and re-creates the index.</span></span> <span data-ttu-id="7bf87-111">Таким образом, устраняется фрагментация, восстанавливается место на диске путем сжатия страниц с учетом указанного или существующего коэффициента заполнения, переупорядочиваются индексные строки в последовательных страницах.</span><span class="sxs-lookup"><span data-stu-id="7bf87-111">This removes fragmentation, reclaims disk space by compacting the pages based on the specified or existing fill factor setting, and reorders the index rows in contiguous pages.</span></span> <span data-ttu-id="7bf87-112">Если указывается ключевое слово ALL, то все индексы для таблицы удаляются и перестраиваются в одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="7bf87-112">When ALL is specified, all indexes on the table are dropped and rebuilt in a single transaction.</span></span> <span data-ttu-id="7bf87-113">Для реорганизации индекса требуется минимальный объем системных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7bf87-113">Reorganizing an index uses minimal system resources.</span></span> <span data-ttu-id="7bf87-114">При реорганизации концевой уровень кластеризованных и некластеризованных индексов на таблицах и представлениях дефрагментируется путем физической реорганизации страниц конечного уровня, в результате чего они выстраиваются в соответствии с логическим порядком конечных узлов (слева направо).</span><span class="sxs-lookup"><span data-stu-id="7bf87-114">It defragments the leaf level of clustered and nonclustered indexes on tables and views by physically reordering the leaf-level pages to match the logical, left to right, order of the leaf nodes.</span></span> <span data-ttu-id="7bf87-115">Кроме того, реорганизация сжимает страницы индекса.</span><span class="sxs-lookup"><span data-stu-id="7bf87-115">Reorganizing also compacts the index pages.</span></span> <span data-ttu-id="7bf87-116">Их сжатие производится в соответствии с текущим значением коэффициента заполнения.</span><span class="sxs-lookup"><span data-stu-id="7bf87-116">Compaction is based on the existing fill factor value.</span></span>  
  
 <span data-ttu-id="7bf87-117">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="7bf87-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7bf87-118">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="7bf87-118">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7bf87-119">Выявление фрагментации</span><span class="sxs-lookup"><span data-stu-id="7bf87-119">Detecting Fragmentation</span></span>](#Fragmentation)  
  
     [<span data-ttu-id="7bf87-120">Ограничения</span><span class="sxs-lookup"><span data-stu-id="7bf87-120">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7bf87-121">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7bf87-121">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7bf87-122">**Для проверки фрагментации индекса используется:**</span><span class="sxs-lookup"><span data-stu-id="7bf87-122">**To check the fragmentation of an index, using:**</span></span>  
  
     [<span data-ttu-id="7bf87-123">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7bf87-123">SQL Server Management Studio</span></span>](#SSMSProcedureFrag)  
  
     [<span data-ttu-id="7bf87-124">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7bf87-124">Transact-SQL</span></span>](#TsqlProcedureFrag)  
  
-   <span data-ttu-id="7bf87-125">**Для реорганизации или перестроения индекса используется:**</span><span class="sxs-lookup"><span data-stu-id="7bf87-125">**To reorganize or rebuild an index, using:**</span></span>  
  
     [<span data-ttu-id="7bf87-126">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7bf87-126">SQL Server Management Studio</span></span>](#SSMSProcedureReorg)  
  
     [<span data-ttu-id="7bf87-127">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7bf87-127">Transact-SQL</span></span>](#TsqlProcedureReorg)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7bf87-128">Перед началом</span><span class="sxs-lookup"><span data-stu-id="7bf87-128">Before You Begin</span></span>  
  
###  <a name="detecting-fragmentation"></a><a name="Fragmentation"></a><span data-ttu-id="7bf87-129">Обнаружение фрагментации</span><span class="sxs-lookup"><span data-stu-id="7bf87-129">Detecting Fragmentation</span></span>  
 <span data-ttu-id="7bf87-130">Первым шагом в определении, какой метод дефрагментации следует использовать, будет анализ индекса на предмет степени фрагментации.</span><span class="sxs-lookup"><span data-stu-id="7bf87-130">The first step in deciding which defragmentation method to use is to analyze the index to determine the degree of fragmentation.</span></span> <span data-ttu-id="7bf87-131">Системная функция [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql)позволяет выявить фрагментацию конкретного индекса, всех индексов в таблице или индексированном представлении, всех индексов в базе данных или всех индексов во всех базах данных.</span><span class="sxs-lookup"><span data-stu-id="7bf87-131">By using the system function [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql), you can detect fragmentation in a specific index, all indexes on a table or indexed view, all indexes in a database, or all indexes in all databases.</span></span> <span data-ttu-id="7bf87-132">Для секционированных индексов **sys.dm_db_index_physical_stats** также предоставляет сведения о фрагментации каждой секции.</span><span class="sxs-lookup"><span data-stu-id="7bf87-132">For partitioned indexes, **sys.dm_db_index_physical_stats** also provides fragmentation information for each partition.</span></span>  
  
 <span data-ttu-id="7bf87-133">Результирующий набор, возвращаемый функцией **sys.dm_db_index_physical_stats** , включает следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="7bf87-133">The result set returned by the **sys.dm_db_index_physical_stats** function includes the following columns.</span></span>  
  
|<span data-ttu-id="7bf87-134">Столбец</span><span class="sxs-lookup"><span data-stu-id="7bf87-134">Column</span></span>|<span data-ttu-id="7bf87-135">Описание</span><span class="sxs-lookup"><span data-stu-id="7bf87-135">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7bf87-136">**avg_fragmentation_in_percent**</span><span class="sxs-lookup"><span data-stu-id="7bf87-136">**avg_fragmentation_in_percent**</span></span>|<span data-ttu-id="7bf87-137">Процентная доля логической фрагментации (неупорядоченные страницы в индексе).</span><span class="sxs-lookup"><span data-stu-id="7bf87-137">The percent of logical fragmentation (out-of-order pages in the index).</span></span>|  
|<span data-ttu-id="7bf87-138">**fragment_count**</span><span class="sxs-lookup"><span data-stu-id="7bf87-138">**fragment_count**</span></span>|<span data-ttu-id="7bf87-139">Число фрагментов (физически последовательные конечные страницы) в индексе.</span><span class="sxs-lookup"><span data-stu-id="7bf87-139">The number of fragments (physically consecutive leaf pages) in the index.</span></span>|  
|<span data-ttu-id="7bf87-140">**avg_fragment_size_in_pages**</span><span class="sxs-lookup"><span data-stu-id="7bf87-140">**avg_fragment_size_in_pages**</span></span>|<span data-ttu-id="7bf87-141">Среднее число страниц в одном фрагменте индекса.</span><span class="sxs-lookup"><span data-stu-id="7bf87-141">Average number of pages in one fragment in an index.</span></span>|  
  
 <span data-ttu-id="7bf87-142">Выяснив степень фрагментации, используйте нижеследующую таблицу для определения наиболее подходящего метода устранения фрагментации.</span><span class="sxs-lookup"><span data-stu-id="7bf87-142">After the degree of fragmentation is known, use the following table to determine the best method to correct the fragmentation.</span></span>  
  
|<span data-ttu-id="7bf87-143">Значение**avg_fragmentation_in_percent**</span><span class="sxs-lookup"><span data-stu-id="7bf87-143">**avg_fragmentation_in_percent** value</span></span>|<span data-ttu-id="7bf87-144">Корректирующая инструкция</span><span class="sxs-lookup"><span data-stu-id="7bf87-144">Corrective statement</span></span>|  
|-----------------------------------------------|--------------------------|  
|<span data-ttu-id="7bf87-145">> 5% и \< = 30%</span><span class="sxs-lookup"><span data-stu-id="7bf87-145">> 5% and \< = 30%</span></span>|<span data-ttu-id="7bf87-146">ALTER INDEX REORGANIZE</span><span class="sxs-lookup"><span data-stu-id="7bf87-146">ALTER INDEX REORGANIZE</span></span>|  
|<span data-ttu-id="7bf87-147">> 30%</span><span class="sxs-lookup"><span data-stu-id="7bf87-147">> 30%</span></span>|<span data-ttu-id="7bf87-148">ALTER INDEX REBUILD WITH (ONLINE = ON) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7bf87-148">ALTER INDEX REBUILD WITH (ONLINE = ON) <sup>1</sup></span></span>|

<span data-ttu-id="7bf87-149"><sup>1</sup> Индекс может быть перестроен как в режиме "в сети", так и в режиме "вне сети".</span><span class="sxs-lookup"><span data-stu-id="7bf87-149"><sup>1</sup> Rebuilding an index can be executed online or offline.</span></span> <span data-ttu-id="7bf87-150">Реорганизация индекса всегда выполняется в режиме "в сети".</span><span class="sxs-lookup"><span data-stu-id="7bf87-150">Reorganizing an index is always executed online.</span></span> <span data-ttu-id="7bf87-151">Чтобы добиться доступности, подобной варианту с реорганизацией, следует перестраивать индексы в режиме "в сети".</span><span class="sxs-lookup"><span data-stu-id="7bf87-151">To achieve availability similar to the reorganize option, you should rebuild indexes online.</span></span>  
  
> [!TIP]
> <span data-ttu-id="7bf87-152">Эти значения дают примерное представление об определении точки, в которой необходимо переключаться между `ALTER INDEX REORGANIZE` и `ALTER INDEX REBUILD`.</span><span class="sxs-lookup"><span data-stu-id="7bf87-152">These values provide a rough guideline for determining the point at which you should switch between `ALTER INDEX REORGANIZE` and `ALTER INDEX REBUILD`.</span></span> <span data-ttu-id="7bf87-153">Однако фактические значения могут различаться в каждом конкретном случае.</span><span class="sxs-lookup"><span data-stu-id="7bf87-153">However, the actual values may vary from case to case.</span></span> <span data-ttu-id="7bf87-154">Важно определить наилучшее пороговое значение для используемой среды экспериментальным путем.</span><span class="sxs-lookup"><span data-stu-id="7bf87-154">It is important that you experiment to determine the best threshold for your environment.</span></span> <span data-ttu-id="7bf87-155">Например, если индекс используется преимущественно для операций сканирования, устранение фрагментации позволяет повысить производительность при их выполнении.</span><span class="sxs-lookup"><span data-stu-id="7bf87-155">For example, if a given index is used mainly for scan operations, removing fragmentation can improve performance of these operations.</span></span> <span data-ttu-id="7bf87-156">Выигрыш в производительности не так заметен в случае с индексами, которые используются в первую очередь для операций поиска.</span><span class="sxs-lookup"><span data-stu-id="7bf87-156">The performance benefit is less noticeable for indexes that are used primarily for seek operations.</span></span> <span data-ttu-id="7bf87-157">Аналогичным образом устранение фрагментации в куче (таблице без кластеризованного индекса) особенно полезно для операций сканирования некластеризованного индекса, но мало влияет на операции поиска.</span><span class="sxs-lookup"><span data-stu-id="7bf87-157">Similarly, removing fragmentation in a heap (a table with no clustered index) is especially useful for nonclustered index scan operations, but has little effect in lookup operations.</span></span>

<span data-ttu-id="7bf87-158">При очень низких уровнях фрагментации (менее 5 %) эти команды, как правило, использоваться не должны, так как выгода от дефрагментации столь низкого уровня почти всегда в достаточной степени компенсируется за счет реорганизации или перестроения индекса.</span><span class="sxs-lookup"><span data-stu-id="7bf87-158">Very low levels of fragmentation (less than 5 percent) should typically not be addressed by either of these commands, because the benefit from removing such a small amount of fragmentation is almost always vastly outweighed by the cost of reorganizing or rebuilding the index.</span></span> 

> [!NOTE]
> <span data-ttu-id="7bf87-159">Перестроение или реорганизация малых индексов часто не приводит к уменьшению фрагментации.</span><span class="sxs-lookup"><span data-stu-id="7bf87-159">Rebuilding or reorganizing small indexes often does not reduce fragmentation.</span></span> <span data-ttu-id="7bf87-160">Страницы индексов малого размера хранятся в смешанных экстентах.</span><span class="sxs-lookup"><span data-stu-id="7bf87-160">The pages of small indexes are sometimes stored on mixed extents.</span></span> <span data-ttu-id="7bf87-161">Смешанные экстенты могут находиться в общем пользовании у восьми объектов, поэтому фрагментацию в малом индексе нельзя уменьшить путем его реорганизации или перестроения.</span><span class="sxs-lookup"><span data-stu-id="7bf87-161">Mixed extents are shared by up to eight objects, so the fragmentation in a small index might not be reduced after reorganizing or rebuilding it.</span></span>

### <a name="index-defragmentation-considerations"></a><span data-ttu-id="7bf87-162">Рекомендации по дефрагментации индексов</span><span class="sxs-lookup"><span data-stu-id="7bf87-162">Index defragmentation considerations</span></span>
<span data-ttu-id="7bf87-163">При определенных условиях перестроение кластеризованного индекса автоматически приводит к перестроению всех некластеризованных индексов, на которые ссылается ключ кластеризации, если физические или логические идентификаторы в записях некластеризованного индекса должны изменяться.</span><span class="sxs-lookup"><span data-stu-id="7bf87-163">Under certain conditions, rebuilding a clustered index will automatically rebuild any nonclustered index that reference the clustering key, if the physical or logical identifiers contained in the nonclustered index records needs to change.</span></span>

<span data-ttu-id="7bf87-164">Автоматическое перестроение всех некластеризованных индексов в таблице происходит в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="7bf87-164">Scenarios that force all nonclustered indexes to be automatically rebuilt on a table:</span></span>

-  <span data-ttu-id="7bf87-165">создание кластеризованного индекса для таблицы;</span><span class="sxs-lookup"><span data-stu-id="7bf87-165">Creating a clustered index on a table</span></span>
-  <span data-ttu-id="7bf87-166">удаление кластеризованного индекса, в результате которого таблица сохраняется как куча;</span><span class="sxs-lookup"><span data-stu-id="7bf87-166">Removing a clustered index, causing the table to be stored as a heap</span></span>
-  <span data-ttu-id="7bf87-167">включение столбцов в ключ кластеризации или исключение столбцов из него.</span><span class="sxs-lookup"><span data-stu-id="7bf87-167">Changing the clustering key to include or exclude columns</span></span>

<span data-ttu-id="7bf87-168">Автоматическое перестроение всех некластеризованных индексов в таблице не требуется в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="7bf87-168">Scenarios that do not require all nonclustered indexes to be automatically rebuilt on a table:</span></span>

-  <span data-ttu-id="7bf87-169">перестроение уникального кластеризованного индекса;</span><span class="sxs-lookup"><span data-stu-id="7bf87-169">Rebuilding a unique clustered index</span></span>
-  <span data-ttu-id="7bf87-170">перестроение не уникального кластеризованного индекса;</span><span class="sxs-lookup"><span data-stu-id="7bf87-170">Rebuilding a non-unique clustered index</span></span>
-  <span data-ttu-id="7bf87-171">изменение схемы индекса, например применение схемы секционирования к кластеризованному индексу или перемещение кластеризованного индекса в другую файловую группу.</span><span class="sxs-lookup"><span data-stu-id="7bf87-171">Changing the index schema, such as applying a partitioning scheme to a clustered index or moving the clustered index to a different filegroup</span></span>
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7bf87-172">Ограничения</span><span class="sxs-lookup"><span data-stu-id="7bf87-172">Limitations and Restrictions</span></span>  
  
<span data-ttu-id="7bf87-173">Перестроение индексов с более чем 128 экстентами осуществляется в два этапа: логическое и физическое перестроение.</span><span class="sxs-lookup"><span data-stu-id="7bf87-173">Indexes with more than 128 extents are rebuilt in two separate phases: logical and physical.</span></span> <span data-ttu-id="7bf87-174">На этапе логического перестроения существующие единицы распределения, используемые индексом, помечаются для освобождения, строки данных копируются и сортируются, а затем перемещаются в новые единицы распределения, созданные для хранения перестроенного индекса.</span><span class="sxs-lookup"><span data-stu-id="7bf87-174">In the logical phase, the existing allocation units used by the index are marked for deallocation, the data rows are copied and sorted, then moved to new allocation units created to store the rebuilt index.</span></span> <span data-ttu-id="7bf87-175">На этапе физического перестроения единицы распределения, ранее помеченные для освобождения, физически удаляются посредством выполняемых в фоновом режиме коротких транзакций, и многочисленные блокировки для этого не требуются.</span><span class="sxs-lookup"><span data-stu-id="7bf87-175">In the physical phase, the allocation units previously marked for deallocation are physically dropped in short transactions that happen in the background, and do not require many locks.</span></span> <span data-ttu-id="7bf87-176">Дополнительные сведения об экстентах см. в разделе [Руководство по архитектуре страниц и экстентов](https://docs.microsoft.com/sql/relational-databases/pages-and-extents-architecture-guide).</span><span class="sxs-lookup"><span data-stu-id="7bf87-176">For more information about extents, refer to the [Pages and Extents Architecture Guide](https://docs.microsoft.com/sql/relational-databases/pages-and-extents-architecture-guide).</span></span>

<span data-ttu-id="7bf87-177">Инструкция `ALTER INDEX REORGANIZE` требует, чтобы в файле данных, где содержится индекс, было свободное пространство, потому что операция может выделять временные рабочие страницы только в том же файле (а не в другом файле файловой группы, к примеру).</span><span class="sxs-lookup"><span data-stu-id="7bf87-177">The `ALTER INDEX REORGANIZE` statement requires the data file containing the index to have space available, because the operation can only allocate temporary work pages on the same file, not another file within the filegroup.</span></span> <span data-ttu-id="7bf87-178">Поэтому у пользователя все равно может возникнуть ошибка 1105, даже если в файловой группе есть свободные страницы: `Could not allocate space for object '###' in database '###' because the '###' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.`</span><span class="sxs-lookup"><span data-stu-id="7bf87-178">So although the filegroup might have free pages available, the user can still encounter error 1105: `Could not allocate space for object '###' in database '###' because the '###' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.`</span></span>

<span data-ttu-id="7bf87-179">Создание и перестройка невыровненных индексов для таблицы, количество секций в которой превышает 1000, возможны, но не рекомендуются.</span><span class="sxs-lookup"><span data-stu-id="7bf87-179">Creating and rebuilding non-aligned indexes on a table with more than 1,000 partitions is possible, but is not recommended.</span></span> <span data-ttu-id="7bf87-180">Это может привести к снижению производительности или чрезмерному потреблению памяти во время таких операций.</span><span class="sxs-lookup"><span data-stu-id="7bf87-180">Doing so may cause degraded performance or excessive memory consumption during these operations.</span></span>

<span data-ttu-id="7bf87-181">Индекс нельзя реорганизовать или перестроить, если файловая группа, в которой он расположен, находится в автономном режиме или предназначена только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7bf87-181">An index cannot be reorganized or rebuilt if the filegroup in which it is located is offline or set to read-only.</span></span> <span data-ttu-id="7bf87-182">Если указывается ключевое слово `ALL`, а один индекс или несколько расположены в файловой группе, которая находится в автономном режиме или предназначена только для чтения, то выполнить инструкцию не удастся.</span><span class="sxs-lookup"><span data-stu-id="7bf87-182">When the keyword `ALL` is specified and one or more indexes are in an offline or read-only filegroup, the statement fails.</span></span>
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7bf87-183">безопасность</span><span class="sxs-lookup"><span data-stu-id="7bf87-183">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7bf87-184">Permissions</span><span class="sxs-lookup"><span data-stu-id="7bf87-184">Permissions</span></span>  
 <span data-ttu-id="7bf87-185">Необходимо разрешение `ALTER` для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="7bf87-185">Requires `ALTER` permission on the table or view.</span></span> <span data-ttu-id="7bf87-186">Пользователь должен быть членом предопределенной роли сервера **sysadmin** или предопределенных ролей базы данных **db_ddladmin** и **db_owner**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-186">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedureFrag"></a> <span data-ttu-id="7bf87-187">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7bf87-187">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-check-the-fragmentation-of-an-index"></a><span data-ttu-id="7bf87-188">Проверка фрагментации индекса</span><span class="sxs-lookup"><span data-stu-id="7bf87-188">To check the fragmentation of an index</span></span>  
  
1.  <span data-ttu-id="7bf87-189">В обозревателе объектов разверните базу данных, содержащую таблицу, в которой необходимо проверить фрагментацию индекса.</span><span class="sxs-lookup"><span data-stu-id="7bf87-189">In Object Explorer, Expand the database that contains the table on which you want to check an index's fragmentation.</span></span>  
  
2.  <span data-ttu-id="7bf87-190">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-190">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="7bf87-191">Разверните таблицу, в которой нужно проверить фрагментацию индекса.</span><span class="sxs-lookup"><span data-stu-id="7bf87-191">Expand the table on which you want to check an index's fragmentation.</span></span>  
  
4.  <span data-ttu-id="7bf87-192">Разверните папку **Индексы**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-192">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="7bf87-193">Щелкните правой кнопкой мыши индекс, для которого нужно проверить фрагментацию, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-193">Right-click the index of which you want to check the fragmentation and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="7bf87-194">В разделе **Выбор страницы**выберите пункт **Фрагментация**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-194">Under **Select a page**, select **Fragmentation**.</span></span>  
  
     <span data-ttu-id="7bf87-195">На странице **Фрагментация** доступны следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="7bf87-195">The following information is available on the **Fragmentation** page:</span></span>  
  
     <span data-ttu-id="7bf87-196">**Заполненность страниц**</span><span class="sxs-lookup"><span data-stu-id="7bf87-196">**Page fullness**</span></span>  
     <span data-ttu-id="7bf87-197">Отображает среднее заполнение страниц индекса, в процентах.</span><span class="sxs-lookup"><span data-stu-id="7bf87-197">Indicates average fullness of the index pages, as a percentage.</span></span> <span data-ttu-id="7bf87-198">100 % означает, что страницы индекса полностью заполнены.</span><span class="sxs-lookup"><span data-stu-id="7bf87-198">100% means the index pages are completely full.</span></span> <span data-ttu-id="7bf87-199">50 % означает, что каждая страница индекса заполнена в среднем наполовину.</span><span class="sxs-lookup"><span data-stu-id="7bf87-199">50% means that, on average, each index page is half full.</span></span>  
  
     <span data-ttu-id="7bf87-200">**Общая фрагментация**</span><span class="sxs-lookup"><span data-stu-id="7bf87-200">**Total fragmentation**</span></span>  
     <span data-ttu-id="7bf87-201">Процент логической фрагментации.</span><span class="sxs-lookup"><span data-stu-id="7bf87-201">The logical fragmentation percentage.</span></span> <span data-ttu-id="7bf87-202">Отображает количество страниц индекса, хранимых не в порядке.</span><span class="sxs-lookup"><span data-stu-id="7bf87-202">This indicates the number of pages in an index that are not stored in order.</span></span>  
  
     <span data-ttu-id="7bf87-203">**Средний размер строки**</span><span class="sxs-lookup"><span data-stu-id="7bf87-203">**Average row size**</span></span>  
     <span data-ttu-id="7bf87-204">Средний размер строки конечного уровня.</span><span class="sxs-lookup"><span data-stu-id="7bf87-204">The average size of a leaf level row.</span></span>  
  
     <span data-ttu-id="7bf87-205">**Depth**</span><span class="sxs-lookup"><span data-stu-id="7bf87-205">**Depth**</span></span>  
     <span data-ttu-id="7bf87-206">Количество уровней индекса, включая конечный уровень.</span><span class="sxs-lookup"><span data-stu-id="7bf87-206">The number of levels in the index, including the leaf level.</span></span>  
  
     <span data-ttu-id="7bf87-207">**Перенаправленные записи**</span><span class="sxs-lookup"><span data-stu-id="7bf87-207">**Forwarded records**</span></span>  
     <span data-ttu-id="7bf87-208">Количество записей в куче, содержащих указатели на данные в других местах.</span><span class="sxs-lookup"><span data-stu-id="7bf87-208">The number of records in a heap that have forward pointers to another data location.</span></span> <span data-ttu-id="7bf87-209">(Такое состояние возникает во время обновления, когда не хватает места для сохранения новой строки в исходном расположении.)</span><span class="sxs-lookup"><span data-stu-id="7bf87-209">(This state occurs during an update, when there is not enough room to store the new row in the original location.)</span></span>  
  
     <span data-ttu-id="7bf87-210">**Фантомные строки**</span><span class="sxs-lookup"><span data-stu-id="7bf87-210">**Ghost rows**</span></span>  
     <span data-ttu-id="7bf87-211">Количество строк, помеченных как удаленных, но еще фактически не удаленных.</span><span class="sxs-lookup"><span data-stu-id="7bf87-211">The number of rows that are marked as deleted but not yet removed.</span></span> <span data-ttu-id="7bf87-212">Эти строки будут удалены потоком очистки, когда сервер будет не загружен.</span><span class="sxs-lookup"><span data-stu-id="7bf87-212">These rows will be removed by a clean-up thread, when the server is not busy.</span></span> <span data-ttu-id="7bf87-213">Это значение не включает в себя строки, сохраняемые из-за ожидающей выполнения транзакции изоляции моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="7bf87-213">This value does not include rows that are being retained due to an outstanding snapshot isolation transaction.</span></span>  
  
     <span data-ttu-id="7bf87-214">**Тип индекса**</span><span class="sxs-lookup"><span data-stu-id="7bf87-214">**Index type**</span></span>  
     <span data-ttu-id="7bf87-215">Тип индекса.</span><span class="sxs-lookup"><span data-stu-id="7bf87-215">The type of index.</span></span> <span data-ttu-id="7bf87-216">Возможными значениями являются **Кластеризованный индекс**, **Некластеризованный индекс**и **Первичный XML**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-216">Possible values are **Clustered index**, **Nonclustered index**, and **Primary XML**.</span></span> <span data-ttu-id="7bf87-217">Таблицы могут также сохраняться в виде кучи (без индексов), однако после этого данная страница «Свойства индекса» не может быть открыта.</span><span class="sxs-lookup"><span data-stu-id="7bf87-217">Tables can also be stored as a heap (without indexes), but then this Index Properties page cannot be opened.</span></span>  
  
     <span data-ttu-id="7bf87-218">**Строки конечного уровня**</span><span class="sxs-lookup"><span data-stu-id="7bf87-218">**Leaf-level rows**</span></span>  
     <span data-ttu-id="7bf87-219">Количество строк конечного уровня.</span><span class="sxs-lookup"><span data-stu-id="7bf87-219">The number of leaf level rows.</span></span>  
  
     <span data-ttu-id="7bf87-220">**Максимальный размер строки**</span><span class="sxs-lookup"><span data-stu-id="7bf87-220">**Maximum row size**</span></span>  
     <span data-ttu-id="7bf87-221">Максимальный размер строки конечного уровня.</span><span class="sxs-lookup"><span data-stu-id="7bf87-221">The maximum leaf-level row size.</span></span>  
  
     <span data-ttu-id="7bf87-222">**Минимальный размер строки**</span><span class="sxs-lookup"><span data-stu-id="7bf87-222">**Minimum row size**</span></span>  
     <span data-ttu-id="7bf87-223">Минимальный размер строки конечного уровня.</span><span class="sxs-lookup"><span data-stu-id="7bf87-223">The minimum leaf-level row size.</span></span>  
  
     <span data-ttu-id="7bf87-224">**Страницы**</span><span class="sxs-lookup"><span data-stu-id="7bf87-224">**Pages**</span></span>  
     <span data-ttu-id="7bf87-225">Общее число страниц данных.</span><span class="sxs-lookup"><span data-stu-id="7bf87-225">The total number of data pages.</span></span>  
  
     <span data-ttu-id="7bf87-226">**Partition ID**</span><span class="sxs-lookup"><span data-stu-id="7bf87-226">**Partition ID**</span></span>  
     <span data-ttu-id="7bf87-227">Идентификатор секции сбалансированного дерева, содержащего индекс.</span><span class="sxs-lookup"><span data-stu-id="7bf87-227">The partition ID of the b-tree containing the index.</span></span>  
  
     <span data-ttu-id="7bf87-228">**Фантомные строки версии**</span><span class="sxs-lookup"><span data-stu-id="7bf87-228">**Version ghost rows**</span></span>  
     <span data-ttu-id="7bf87-229">Количество фантомных записей, которые сохраняются в памяти из-за незавершенной транзакции изоляции моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="7bf87-229">The number of ghost records that are being retained due to an outstanding snapshot isolation transaction.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedureFrag"></a> <span data-ttu-id="7bf87-230">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7bf87-230">Using Transact-SQL</span></span>  
  
#### <a name="to-check-the-fragmentation-of-an-index"></a><span data-ttu-id="7bf87-231">Проверка фрагментации индекса</span><span class="sxs-lookup"><span data-stu-id="7bf87-231">To check the fragmentation of an index</span></span>  
  
1.  <span data-ttu-id="7bf87-232">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bf87-232">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7bf87-233">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-233">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7bf87-234">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-234">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find the average fragmentation percentage of all indexes  
    -- in the HumanResources.Employee table.   
    SELECT a.index_id, name, avg_fragmentation_in_percent  
    FROM sys.dm_db_index_physical_stats (DB_ID(N'AdventureWorks2012'), OBJECT_ID(N'HumanResources.Employee'), NULL, NULL, NULL) AS a  
        JOIN sys.indexes AS b ON a.object_id = b.object_id AND a.index_id = b.index_id;   
    GO  
    ```  
  
     <span data-ttu-id="7bf87-235">Эта инструкция должна возвратить результирующий набор, подобный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="7bf87-235">The statement above might return a result set similar to the following.</span></span>  
  
    ```  
    index_id    name                                                  avg_fragmentation_in_percent  
    ----------- ----------------------------------------------------- ----------------------------  
    1           PK_Employee_BusinessEntityID                          0  
    2           IX_Employee_OrganizationalNode                        0  
    3           IX_Employee_OrganizationalLevel_OrganizationalNode    0  
    5           AK_Employee_LoginID                                   66.6666666666667  
    6           AK_Employee_NationalIDNumber                          50  
    7           AK_Employee_rowguid                                   0  
  
    (6 row(s) affected)  
    ```  
  
 <span data-ttu-id="7bf87-236">Дополнительные сведения см. в разделе [sys. dm_db_index_physical_stats &#40;&#41;Transact-SQL ](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7bf87-236">For more information, see  [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedureReorg"></a> <span data-ttu-id="7bf87-237">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7bf87-237">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-reorganize-or-rebuild-an-index"></a><span data-ttu-id="7bf87-238">Реорганизация или перестроение индекса</span><span class="sxs-lookup"><span data-stu-id="7bf87-238">To reorganize or rebuild an index</span></span>  
  
1.  <span data-ttu-id="7bf87-239">В обозревателе объектов разверните базу данных, содержащую таблицу, в которой необходимо реорганизовать индекс.</span><span class="sxs-lookup"><span data-stu-id="7bf87-239">In Object Explorer, Expand the database that contains the table on which you want to reorganize an index.</span></span>  
  
2.  <span data-ttu-id="7bf87-240">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-240">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="7bf87-241">Разверните таблицу, в которой нужно реорганизовать индекс.</span><span class="sxs-lookup"><span data-stu-id="7bf87-241">Expand the table on which you want to reorganize an index.</span></span>  
  
4.  <span data-ttu-id="7bf87-242">Разверните папку **Индексы**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-242">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="7bf87-243">Щелкните правой кнопкой мыши индекс, который требуется реорганизовать, и выберите пункт **Реорганизовать**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-243">Right-click the index you want to reorganize and select **Reorganize**.</span></span>  
  
6.  <span data-ttu-id="7bf87-244">В диалоговом окне **Реорганизация индексов** убедитесь, что нужный индекс приведен в сетке **Индексы для реорганизации** , и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-244">In the **Reorganize Indexes** dialog box, verify that the correct index is in the **Indexes to be reorganized** grid and click **OK**.</span></span>  
  
7.  <span data-ttu-id="7bf87-245">Установите флажок **Сжать данные в столбцах больших объектов** , чтобы указать, что также сжимаются все страницы, содержащие данные больших объектов.</span><span class="sxs-lookup"><span data-stu-id="7bf87-245">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
8.  <span data-ttu-id="7bf87-246">Нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="7bf87-246">Click **OK.**</span></span>  
  
#### <a name="to-reorganize-all-indexes-in-a-table"></a><span data-ttu-id="7bf87-247">Реорганизация всех индексов в таблице</span><span class="sxs-lookup"><span data-stu-id="7bf87-247">To reorganize all indexes in a table</span></span>  
  
1.  <span data-ttu-id="7bf87-248">В обозревателе объектов разверните базу данных, содержащую таблицу, в которой необходимо реорганизовать индексы.</span><span class="sxs-lookup"><span data-stu-id="7bf87-248">In Object Explorer, Expand the database that contains the table on which you want to reorganize the indexes.</span></span>  
  
2.  <span data-ttu-id="7bf87-249">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-249">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="7bf87-250">Разверните таблицу, в которой нужно реорганизовать индексы.</span><span class="sxs-lookup"><span data-stu-id="7bf87-250">Expand the table on which you want to reorganize the indexes.</span></span>  
  
4.  <span data-ttu-id="7bf87-251">Щелкните правой кнопкой мыши папку **Индексы** и выберите команду **Реорганизовать все**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-251">Right-click the **Indexes** folder and select **Reorganize All**.</span></span>  
  
5.  <span data-ttu-id="7bf87-252">В диалоговом окне **Реорганизация индексов** убедитесь, что нужные индексы приведены в сетке **Индексы для реорганизации**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-252">In the **Reorganize Indexes** dialog box, verify that the correct indexes are in the **Indexes to be reorganized**.</span></span> <span data-ttu-id="7bf87-253">Для удаления индекса из сетки **Индексы для реорганизации** выделите индекс и нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="7bf87-253">To remove an index from the **Indexes to be reorganized** grid, select the index and then press the Delete key.</span></span>  
  
6.  <span data-ttu-id="7bf87-254">Установите флажок **Сжать данные в столбцах больших объектов** , чтобы указать, что также сжимаются все страницы, содержащие данные больших объектов.</span><span class="sxs-lookup"><span data-stu-id="7bf87-254">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
7.  <span data-ttu-id="7bf87-255">Нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="7bf87-255">Click **OK.**</span></span>  
  
#### <a name="to-rebuild-an-index"></a><span data-ttu-id="7bf87-256">Перестроение индекса</span><span class="sxs-lookup"><span data-stu-id="7bf87-256">To rebuild an index</span></span>  
  
1.  <span data-ttu-id="7bf87-257">В обозревателе объектов разверните базу данных, содержащую таблицу, в которой необходимо реорганизовать индекс.</span><span class="sxs-lookup"><span data-stu-id="7bf87-257">In Object Explorer, Expand the database that contains the table on which you want to reorganize an index.</span></span>  
  
2.  <span data-ttu-id="7bf87-258">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-258">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="7bf87-259">Разверните таблицу, в которой нужно реорганизовать индекс.</span><span class="sxs-lookup"><span data-stu-id="7bf87-259">Expand the table on which you want to reorganize an index.</span></span>  
  
4.  <span data-ttu-id="7bf87-260">Разверните папку **Индексы**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-260">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="7bf87-261">Щелкните правой кнопкой мыши индекс, который требуется реорганизовать, и выберите пункт **Реорганизовать**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-261">Right-click the index you want to reorganize and select **Reorganize**.</span></span>  
  
6.  <span data-ttu-id="7bf87-262">В диалоговом окне **Перестроение индексов** убедитесь, что нужный индекс приведен в сетке **Индексы для перестроения**, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-262">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to be rebuilt** grid and click **OK**.</span></span>  
  
7.  <span data-ttu-id="7bf87-263">Установите флажок **Сжать данные в столбцах больших объектов** , чтобы указать, что также сжимаются все страницы, содержащие данные больших объектов.</span><span class="sxs-lookup"><span data-stu-id="7bf87-263">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
8.  <span data-ttu-id="7bf87-264">Нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="7bf87-264">Click **OK.**</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedureReorg"></a> <span data-ttu-id="7bf87-265">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7bf87-265">Using Transact-SQL</span></span>  
  
#### <a name="to-reorganize-a-defragmented-index"></a><span data-ttu-id="7bf87-266">Реорганизация дефрагментированного индекса</span><span class="sxs-lookup"><span data-stu-id="7bf87-266">To reorganize a defragmented index</span></span>  
  
1.  <span data-ttu-id="7bf87-267">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bf87-267">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7bf87-268">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-268">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7bf87-269">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-269">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Reorganize the IX_Employee_OrganizationalLevel_OrganizationalNode index on the HumanResources.Employee table.   
  
    ALTER INDEX IX_Employee_OrganizationalLevel_OrganizationalNode ON HumanResources.Employee  
    REORGANIZE ;   
    GO  
    ```  
  
#### <a name="to-reorganize-all-indexes-in-a-table"></a><span data-ttu-id="7bf87-270">Реорганизация всех индексов в таблице</span><span class="sxs-lookup"><span data-stu-id="7bf87-270">To reorganize all indexes in a table</span></span>  
  
1.  <span data-ttu-id="7bf87-271">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bf87-271">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7bf87-272">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-272">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7bf87-273">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-273">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Reorganize all indexes on the HumanResources.Employee table.  
    ALTER INDEX ALL ON HumanResources.Employee  
    REORGANIZE ;   
    GO  
    ```  
  
#### <a name="to-rebuild-a-defragmented-index"></a><span data-ttu-id="7bf87-274">Перестроение дефрагментированного индекса</span><span class="sxs-lookup"><span data-stu-id="7bf87-274">To rebuild a defragmented index</span></span>  
  
1.  <span data-ttu-id="7bf87-275">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bf87-275">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7bf87-276">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-276">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7bf87-277">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-277">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7bf87-278">В этом примере перестраивается один индекс в таблице `Employee` .</span><span class="sxs-lookup"><span data-stu-id="7bf87-278">The example rebuilds a single index on the `Employee` table.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex1](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex1)]  
  
#### <a name="to-rebuild-all-indexes-in-a-table"></a><span data-ttu-id="7bf87-279">Перестроение всех индексов в таблице</span><span class="sxs-lookup"><span data-stu-id="7bf87-279">To rebuild all indexes in a table</span></span>  
  
1.  <span data-ttu-id="7bf87-280">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bf87-280">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7bf87-281">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7bf87-281">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7bf87-282">Скопируйте следующий пример в запрос. В примере указывается ключевое слово `ALL`.</span><span class="sxs-lookup"><span data-stu-id="7bf87-282">Copy and paste the following example into the query The example specifies the keyword `ALL`.</span></span> <span data-ttu-id="7bf87-283">Тем самым выполняется перестроение всех индексов, связанных с таблицей.</span><span class="sxs-lookup"><span data-stu-id="7bf87-283">This rebuilds all indexes associated with the table.</span></span> <span data-ttu-id="7bf87-284">Указываются три параметра.</span><span class="sxs-lookup"><span data-stu-id="7bf87-284">Three options are specified.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex2](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex2)]  
  
 <span data-ttu-id="7bf87-285">Дополнительные сведения см. в разделе [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7bf87-285">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf87-286">См. также:</span><span class="sxs-lookup"><span data-stu-id="7bf87-286">See Also</span></span>  
 [<span data-ttu-id="7bf87-287">Рекомендации по дефрагментации индексов Microsoft SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="7bf87-287">Microsoft SQL Server 2000 Index Defragmentation Best Practices</span></span>](https://technet.microsoft.com/library/cc966523.aspx)  
  
  
