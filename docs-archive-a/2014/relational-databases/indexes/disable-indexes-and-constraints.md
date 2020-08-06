---
title: Отключение индексов и ограничений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.disableindexes.f1
helpviewer_keywords:
- disabled indexes [SQL Server], index operations
- nonclustered indexes [SQL Server], disabling
- disabled indexes [SQL Server], guidelines
- clustered indexes, disabling
- constraints [SQL Server], disabling
- disabled indexes [SQL Server], viewing
- FOREIGN KEY constraints, disabling
- statistical information [SQL Server], indexes
- index disabling [SQL Server]
- indexed views [SQL Server], disabled indexes
ms.assetid: 2198f1af-fa44-47e9-92df-f4fde322ba18
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 40f9de4108be4defeb2353a9e7835c289641a819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749823"
---
# <a name="disable-indexes-and-constraints"></a><span data-ttu-id="78e51-102">Отключение индексов и ограничений</span><span class="sxs-lookup"><span data-stu-id="78e51-102">Disable Indexes and Constraints</span></span>
  <span data-ttu-id="78e51-103">В этом разделе описывается отключение индекса или ограничений в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78e51-103">This topic describes how to disable an index or constraints in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="78e51-104">Отключение индексов предотвращает доступ пользователя к индексам в случае использования кластеризованных индексов к данным базовой таблицы.</span><span class="sxs-lookup"><span data-stu-id="78e51-104">Disabling an index prevents user access to the index, and for clustered indexes to the underlying table data.</span></span> <span data-ttu-id="78e51-105">Определение индекса остается в метаданных, и статистики индекса сохраняются на некластеризованных индексах.</span><span class="sxs-lookup"><span data-stu-id="78e51-105">The index definition remains in metadata, and index statistics are kept on nonclustered indexes.</span></span> <span data-ttu-id="78e51-106">Данные индекса при отключении некластеризованных или кластеризованных индексов в представлении удаляются физически.</span><span class="sxs-lookup"><span data-stu-id="78e51-106">Disabling a nonclustered or clustered index on a view physically deletes the index data.</span></span> <span data-ttu-id="78e51-107">Отключение кластеризованного индекса в таблице позволяет предотвратить доступ к данным; данные остаются в таблице, но являются недоступными для операций языка обработки данных DML до удаления или перестроения индекса.</span><span class="sxs-lookup"><span data-stu-id="78e51-107">Disabling a clustered index on a table prevents access to the data; the data still remains in the table, but is unavailable for data manipulation language (DML) operations until the index is dropped or rebuilt.</span></span>  
  
 <span data-ttu-id="78e51-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="78e51-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="78e51-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="78e51-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="78e51-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="78e51-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="78e51-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="78e51-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="78e51-112">**Отключение индекса с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="78e51-112">**To disable an index, using:**</span></span>  
  
     [<span data-ttu-id="78e51-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78e51-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="78e51-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78e51-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="78e51-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="78e51-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="78e51-116">Ограничения</span><span class="sxs-lookup"><span data-stu-id="78e51-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="78e51-117">При отключении индекса он не обслуживается.</span><span class="sxs-lookup"><span data-stu-id="78e51-117">The index is not maintained while it is disabled.</span></span>  
  
-   <span data-ttu-id="78e51-118">Оптимизатор запросов не учитывает отключенные индексы при создании планов выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="78e51-118">The query optimizer does not consider the disabled index when creating query execution plans.</span></span> <span data-ttu-id="78e51-119">Запросы, ссылающиеся на отключенные индексы с помощью табличного указания, также завершаются сбоем.</span><span class="sxs-lookup"><span data-stu-id="78e51-119">Also, queries that reference the disabled index with a table hint fail.</span></span>  
  
-   <span data-ttu-id="78e51-120">Нельзя создавать индекс с именем, которое идентично имени существующего отключенного индекса.</span><span class="sxs-lookup"><span data-stu-id="78e51-120">You cannot create an index that uses the same name as an existing disabled index.</span></span>  
  
-   <span data-ttu-id="78e51-121">Отключенный индекс может быть удален.</span><span class="sxs-lookup"><span data-stu-id="78e51-121">A disabled index can be dropped.</span></span>  
  
-   <span data-ttu-id="78e51-122">При отключении уникального индекса также отключаются ограничения PRIMARY KEY, UNIQUE и все ограничения FOREIGN KEY, ссылающиеся на индексированные столбцы из других таблиц.</span><span class="sxs-lookup"><span data-stu-id="78e51-122">When disabling a unique index, the PRIMARY KEY or UNIQUE constraint and all FOREIGN KEY constraints that reference the indexed columns from other tables are also disabled.</span></span> <span data-ttu-id="78e51-123">При отключении кластеризованного индекса также отключаются все входящие и исходящие ограничения FOREIGN KEY для базовой таблицы.</span><span class="sxs-lookup"><span data-stu-id="78e51-123">When disabling a clustered index, all incoming and outgoing FOREIGN KEY constraints on the underlying table are also disabled.</span></span> <span data-ttu-id="78e51-124">При отключении индекса в предупреждающем сообщении приводятся имена ограничений.</span><span class="sxs-lookup"><span data-stu-id="78e51-124">The constraint names are listed in a warning message when the index is disabled.</span></span> <span data-ttu-id="78e51-125">После перестроения индекса необходимо вручную включить все ограничения с помощью инструкции ALTER TABLE CHECK CONSTRAINT.</span><span class="sxs-lookup"><span data-stu-id="78e51-125">After rebuilding the index, all constraints must be manually enabled by using the ALTER TABLE CHECK CONSTRAINT statement.</span></span>  
  
-   <span data-ttu-id="78e51-126">Некластеризованные индексы автоматически отключаются при отключении связанных с ними кластеризованных индексов.</span><span class="sxs-lookup"><span data-stu-id="78e51-126">Nonclustered indexes are automatically disabled when the associated clustered index is disabled.</span></span> <span data-ttu-id="78e51-127">Они не могут быть включены до тех пор, пока не будет включен кластеризованный индекс таблицы или представления или пока не будет удален кластеризованный индекс таблицы.</span><span class="sxs-lookup"><span data-stu-id="78e51-127">They cannot be enabled until either the clustered index on the table or view is enabled or the clustered index on the table is dropped.</span></span> <span data-ttu-id="78e51-128">Некластеризованные индексы должны быть явно включены в том случае, если кластеризованные индексы не были включены ранее с помощью инструкции ALTER TABLE CHECK CONSTRAINT.</span><span class="sxs-lookup"><span data-stu-id="78e51-128">Nonclustered indexes must be explicitly enabled, unless the clustered index was enabled by using the ALTER INDEX ALL REBUILD statement.</span></span>  
  
-   <span data-ttu-id="78e51-129">Инструкция ALTER INDEX ALL REBUILD перестраивает и включает все отключенные индексы таблицы, за исключением индексов представления.</span><span class="sxs-lookup"><span data-stu-id="78e51-129">The ALTER INDEX ALL REBUILD statement rebuilds and enables all disabled indexes on the table, except for disabled indexes on views.</span></span> <span data-ttu-id="78e51-130">Для включения индексов представлений используется отдельная инструкция ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="78e51-130">Indexes on views must be enabled in a separate ALTER INDEX ALL REBUILD statement.</span></span>  
  
-   <span data-ttu-id="78e51-131">При отключении кластеризованного индекса в таблице также отключаются все кластеризованные и некластеризованные индексы в представлениях, которые ссылаются на эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="78e51-131">Disabling a clustered index on a table also disables all clustered and nonclustered indexes on views that reference that table.</span></span> <span data-ttu-id="78e51-132">Указанные индексы должны быть перестроены, так же как и индексы ссылочной таблицы.</span><span class="sxs-lookup"><span data-stu-id="78e51-132">These indexes must be rebuilt just as those on the referenced table.</span></span>  
  
-   <span data-ttu-id="78e51-133">Доступ к строкам данных отключенного кластеризованного индекса не может быть осуществлен, за исключением удаления или перестроения кластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="78e51-133">The data rows of the disabled clustered index cannot be accessed except to drop or rebuild the clustered index.</span></span>  
  
-   <span data-ttu-id="78e51-134">Перестройка отключенных некластеризованных индексов в режиме в сети возможна, если таблица не содержит отключенные кластеризованные индексы.</span><span class="sxs-lookup"><span data-stu-id="78e51-134">You can rebuild a disabled nonclustered index online when the table does not have a disabled clustered index.</span></span> <span data-ttu-id="78e51-135">Однако при использовании инструкций ALTER INDEX REBUILD и CREATE INDEX WITH DROP_EXISTING отключенные кластеризованные индексы могут быть перестроены только в режиме вне сети.</span><span class="sxs-lookup"><span data-stu-id="78e51-135">However, you must always rebuild a disabled clustered index offline if you use either the ALTER INDEX REBUILD or CREATE INDEX WITH DROP_EXISTING statement.</span></span> <span data-ttu-id="78e51-136">Дополнительные сведения об операциях с индексами в сети см. в статье [Выполнение операции с индексами в сети](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="78e51-136">For more information about online index operations, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
-   <span data-ttu-id="78e51-137">Инструкция CREATE STATISTICS не может применяться к таблицам, содержащим отключенные кластеризованные индексы.</span><span class="sxs-lookup"><span data-stu-id="78e51-137">The CREATE STATISTICS statement cannot be successfully executed on a table that has a disabled clustered index.</span></span>  
  
-   <span data-ttu-id="78e51-138">Параметр базы данных AUTO_CREATE_STATISTICS создает новые статистики для столбцов с отключенными индексами при выполнении следующих условий:</span><span class="sxs-lookup"><span data-stu-id="78e51-138">The AUTO_CREATE_STATISTICS database option creates new statistics on a column when the index is disabled and the following conditions exist:</span></span>  
  
    -   <span data-ttu-id="78e51-139">Параметр AUTO_CREATE_STATISTICS установлен в значение ON</span><span class="sxs-lookup"><span data-stu-id="78e51-139">AUTO_CREATE_STATISTICS is set to ON</span></span>  
  
    -   <span data-ttu-id="78e51-140">Для данного столбца не существует статистик.</span><span class="sxs-lookup"><span data-stu-id="78e51-140">There are no existing statistics for the column.</span></span>  
  
    -   <span data-ttu-id="78e51-141">Статистики необходимы при оптимизации запросов.</span><span class="sxs-lookup"><span data-stu-id="78e51-141">Statistics are required during query optimization.</span></span>  
  
-   <span data-ttu-id="78e51-142">Если кластеризованные индексы отключены, то [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) не может вернуть сведения о базовой таблице. Вместо этого результатом выполнения этой инструкции будет сообщение об отключенном кластеризованном индексе.</span><span class="sxs-lookup"><span data-stu-id="78e51-142">If a clustered index is disabled, [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) cannot return information about the underlying table; instead, the statement reports that the clustered index is disabled.</span></span> <span data-ttu-id="78e51-143">[Инструкция DBCC INDEXDEFRAG](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql) не может быть использована для дефрагментации отключенного индекса. В этом случае она возвращает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="78e51-143">[DBCC INDEXDEFRAG](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql) cannot be used to defragment a disabled index; the statement fails with an error message.</span></span> <span data-ttu-id="78e51-144">Инструкция [DBCC DBREINDEX](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) может быть использована для перестроения отключенного индекса.</span><span class="sxs-lookup"><span data-stu-id="78e51-144">You can use [DBCC DBREINDEX](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) to rebuild a disabled index.</span></span>  
  
-   <span data-ttu-id="78e51-145">При создании нового кластеризованного индекса включаются ранее отключенные некластеризованные индексы.</span><span class="sxs-lookup"><span data-stu-id="78e51-145">Creating a new clustered index enables previously disabled nonclustered indexes.</span></span> <span data-ttu-id="78e51-146">Дополнительные сведения см. в статье [Enable Indexes and Constraints](enable-indexes-and-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="78e51-146">For more information, see [Enable Indexes and Constraints](enable-indexes-and-constraints.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="78e51-147">безопасность</span><span class="sxs-lookup"><span data-stu-id="78e51-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="78e51-148">Permissions</span><span class="sxs-lookup"><span data-stu-id="78e51-148">Permissions</span></span>  
 <span data-ttu-id="78e51-149">Для выполнения ALTER INDEX необходимо иметь как минимум разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="78e51-149">To execute ALTER INDEX, at a minimum, ALTER permission on the table or view is required.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="78e51-150">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78e51-150">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-an-index"></a><span data-ttu-id="78e51-151">Отключение индекса</span><span class="sxs-lookup"><span data-stu-id="78e51-151">To disable an index</span></span>  
  
1.  <span data-ttu-id="78e51-152">В обозревателе объектов щелкните знак «плюс», чтобы развернуть базу данных, содержащую таблицу, в которой необходимо отключить индекс.</span><span class="sxs-lookup"><span data-stu-id="78e51-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to disable an index.</span></span>  
  
2.  <span data-ttu-id="78e51-153">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="78e51-153">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="78e51-154">Щелкните знак «плюс», чтобы развернуть таблицу, в которой необходимо отключить индекс.</span><span class="sxs-lookup"><span data-stu-id="78e51-154">Click the plus sign to expand the table on which you want to disable an index.</span></span>  
  
4.  <span data-ttu-id="78e51-155">Чтобы развернуть папку **Индексы** , щелкните знак «плюс» (+).</span><span class="sxs-lookup"><span data-stu-id="78e51-155">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="78e51-156">Щелкните правой кнопкой мыши индекс, который необходимо отключить, и выберите пункт **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="78e51-156">Right-click the index you want to disable and select **Disable**.</span></span>  
  
6.  <span data-ttu-id="78e51-157">В диалоговом окне **Отключение индексов** убедитесь, что нужный индекс указан в сетке **Индексы для отключения** , и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="78e51-157">In the **Disable Indexes** dialog box, verify that the correct index is in the **Indexes to disable** grid and click **OK**.</span></span>  
  
#### <a name="to-disable-all-indexes-on-a-table"></a><span data-ttu-id="78e51-158">Отключение всех индексов таблицы</span><span class="sxs-lookup"><span data-stu-id="78e51-158">To disable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="78e51-159">В обозревателе объектов щелкните знак «плюс», чтобы развернуть базу данных, содержащую таблицу, в которой необходимо отключить индексы.</span><span class="sxs-lookup"><span data-stu-id="78e51-159">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to disable the indexes.</span></span>  
  
2.  <span data-ttu-id="78e51-160">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="78e51-160">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="78e51-161">Щелкните знак «плюс», чтобы развернуть таблицу, в которой необходимо отключить индексы.</span><span class="sxs-lookup"><span data-stu-id="78e51-161">Click the plus sign to expand the table on which you want to disable the indexes.</span></span>  
  
4.  <span data-ttu-id="78e51-162">Щелкните правой кнопкой мыши папку **Индексы** и выберите **Отключить все**.</span><span class="sxs-lookup"><span data-stu-id="78e51-162">Right-click the **Indexes** folder and select **Disable All**.</span></span>  
  
5.  <span data-ttu-id="78e51-163">В диалоговом окне **Отключение индексов** убедитесь, что нужные индексы указаны в сетке **Индексы для отключения** , и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="78e51-163">In the **Disable Indexes** dialog box, verify that the correct indexes are in the **Indexes to disable** grid and click **OK**.</span></span> <span data-ttu-id="78e51-164">Для удаления индекса из сетки **Индексы для отключения** выберите индекс и нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="78e51-164">To remove an index from the **Indexes to disable** grid, select the index and then press the Delete key.</span></span>  
  
 <span data-ttu-id="78e51-165">В диалоговом окне **Отключить индексы** доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="78e51-165">The following information is available in the **Disable Indexes** dialog box:</span></span>  
  
 <span data-ttu-id="78e51-166">**Index Name**</span><span class="sxs-lookup"><span data-stu-id="78e51-166">**Index Name**</span></span>  
 <span data-ttu-id="78e51-167">Отображает имя индекса.</span><span class="sxs-lookup"><span data-stu-id="78e51-167">Displays the name of the index.</span></span> <span data-ttu-id="78e51-168">В ходе выполнения в этом столбце также отображается значок, представляющий состояние.</span><span class="sxs-lookup"><span data-stu-id="78e51-168">During execution, this column also displays an icon representing the status.</span></span>  
  
 <span data-ttu-id="78e51-169">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="78e51-169">**Table Name**</span></span>  
 <span data-ttu-id="78e51-170">Отображает имя таблицы или представления, для которых был создан индекс.</span><span class="sxs-lookup"><span data-stu-id="78e51-170">Displays the name of the table or view that the index was created on.</span></span>  
  
 <span data-ttu-id="78e51-171">**Тип индекса**</span><span class="sxs-lookup"><span data-stu-id="78e51-171">**Index Type**</span></span>  
 <span data-ttu-id="78e51-172">Отображает тип индекса: **кластеризованный**, **некластеризованный**, **пространственный**или **XML**.</span><span class="sxs-lookup"><span data-stu-id="78e51-172">Displays the type of the index: **Clustered**, **Nonclustered**, **Spatial**, or **XML**.</span></span>  
  
 <span data-ttu-id="78e51-173">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="78e51-173">**Status**</span></span>  
 <span data-ttu-id="78e51-174">Отображает состояние операции отключения.</span><span class="sxs-lookup"><span data-stu-id="78e51-174">Displays the status of the disable operation.</span></span> <span data-ttu-id="78e51-175">Возможные значения после выполнения.</span><span class="sxs-lookup"><span data-stu-id="78e51-175">Possible values after execution are:</span></span>  
  
-   <span data-ttu-id="78e51-176">Пусто</span><span class="sxs-lookup"><span data-stu-id="78e51-176">Blank</span></span>  
  
     <span data-ttu-id="78e51-177">**Состояние** до выполнения является пустым.</span><span class="sxs-lookup"><span data-stu-id="78e51-177">Prior to execution **Status** is blank.</span></span>  
  
-   <span data-ttu-id="78e51-178">**Выполняется**</span><span class="sxs-lookup"><span data-stu-id="78e51-178">**In progress**</span></span>  
  
     <span data-ttu-id="78e51-179">Отключение индексов было начато, но еще не завершено.</span><span class="sxs-lookup"><span data-stu-id="78e51-179">Disabling of the indexes has been started but is not complete.</span></span>  
  
-   <span data-ttu-id="78e51-180">**Успешно**</span><span class="sxs-lookup"><span data-stu-id="78e51-180">**Success**</span></span>  
  
     <span data-ttu-id="78e51-181">Операция отключения успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="78e51-181">The disable operation completed successfully.</span></span>  
  
-   <span data-ttu-id="78e51-182">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="78e51-182">**Error**</span></span>  
  
     <span data-ttu-id="78e51-183">При отключении индекса возникла ошибка, и операция отключения не была успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="78e51-183">An error was encountered during the index disable operation, and the operation did not complete successfully.</span></span>  
  
-   <span data-ttu-id="78e51-184">**Остановлено**</span><span class="sxs-lookup"><span data-stu-id="78e51-184">**Stopped**</span></span>  
  
     <span data-ttu-id="78e51-185">Отключение индекса не было завершено успешно, поскольку пользователь остановил операцию.</span><span class="sxs-lookup"><span data-stu-id="78e51-185">The disable of the index was not completed successfully because the user stopped the operation.</span></span>  
  
 <span data-ttu-id="78e51-186">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="78e51-186">**Message**</span></span>  
 <span data-ttu-id="78e51-187">Предоставляет текст сообщений об ошибках в ходе операции отключения.</span><span class="sxs-lookup"><span data-stu-id="78e51-187">Provides the text of error messages during the disable operation.</span></span> <span data-ttu-id="78e51-188">Во время выполнения ошибки отображаются в виде гиперссылок.</span><span class="sxs-lookup"><span data-stu-id="78e51-188">During execution, errors appear as hyperlinks.</span></span> <span data-ttu-id="78e51-189">Текст гиперссылок описывает тело ошибки.</span><span class="sxs-lookup"><span data-stu-id="78e51-189">The text of the hyperlinks describes the body of the error.</span></span> <span data-ttu-id="78e51-190">Столбец **Сообщение** редко имеет ширину, достаточную для прочтения всего текстового сообщения.</span><span class="sxs-lookup"><span data-stu-id="78e51-190">The **Message** column is rarely wide enough to read the full message text.</span></span> <span data-ttu-id="78e51-191">Есть два способа получить полный текст.</span><span class="sxs-lookup"><span data-stu-id="78e51-191">There are two ways to get the full text:</span></span>  
  
-   <span data-ttu-id="78e51-192">Переместите указатель мыши на ячейку сообщения для вызова подсказки, содержащей текст ошибки.</span><span class="sxs-lookup"><span data-stu-id="78e51-192">Move the mouse pointer over the message cell to display a ToolTip with the error text.</span></span>  
  
-   <span data-ttu-id="78e51-193">Щелкните гиперссылку, чтобы вызвать диалоговое окно, отображающее полный текст сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="78e51-193">Click the hyperlink to display a dialog box displaying the full error.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="78e51-194">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78e51-194">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-an-index"></a><span data-ttu-id="78e51-195">Отключение индекса</span><span class="sxs-lookup"><span data-stu-id="78e51-195">To disable an index</span></span>  
  
1.  <span data-ttu-id="78e51-196">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78e51-196">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="78e51-197">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="78e51-197">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="78e51-198">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="78e51-198">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- disables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    DISABLE;  
    ```  
  
#### <a name="to-disable-all-indexes-on-a-table"></a><span data-ttu-id="78e51-199">Отключение всех индексов таблицы</span><span class="sxs-lookup"><span data-stu-id="78e51-199">To disable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="78e51-200">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78e51-200">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="78e51-201">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="78e51-201">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="78e51-202">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="78e51-202">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Disables all indexes on the HumanResources.Employee table.  
    ALTER INDEX ALL ON HumanResources.Employee  
    DISABLE;  
    ```  
  
 <span data-ttu-id="78e51-203">Дополнительные сведения см. в разделе [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="78e51-203">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
