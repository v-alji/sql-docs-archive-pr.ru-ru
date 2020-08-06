---
title: Создание отфильтрованных индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- filtered indexes [SQL Server], about filtered indexes
- designing indexes [SQL Server], filtered
- filtered indexes [SQL Server]
- nonclustered indexes [SQL Server], filtered
- indexes [SQL Server], filtered
ms.assetid: 25e1fcc5-45d7-4c53-8c79-5493dfaa1c74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 77cf641ca84181496f26a995244029d0525ade63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749860"
---
# <a name="create-filtered-indexes"></a><span data-ttu-id="68488-102">Создание отфильтрованных индексов</span><span class="sxs-lookup"><span data-stu-id="68488-102">Create Filtered Indexes</span></span>
  <span data-ttu-id="68488-103">В этом разделе описывается создание фильтруемого индекса в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68488-103">This topic describes how to create a filtered index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="68488-104">Фильтруемый индекс — это оптимизированный некластеризованный индекс, особенно подходящий для запросов, осуществляющих выборку из хорошо определенного подмножества данных.</span><span class="sxs-lookup"><span data-stu-id="68488-104">A filtered index is an optimized nonclustered index especially suited to cover queries that select from a well-defined subset of data.</span></span> <span data-ttu-id="68488-105">Он использует предикат фильтра для индексирования части строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="68488-105">It uses a filter predicate to index a portion of rows in the table.</span></span> <span data-ttu-id="68488-106">Хорошо спроектированный фильтруемый индекс позволяет повысить производительность запросов, а также снизить затраты на обслуживание и хранение индексов по сравнению с полнотабличными индексами.</span><span class="sxs-lookup"><span data-stu-id="68488-106">A well-designed filtered index can improve query performance as well as reduce index maintenance and storage costs compared with full-table indexes.</span></span>  
  
 <span data-ttu-id="68488-107">Отфильтрованные индексы могут предоставить следующие преимущества по сравнению с индексами, построенными на всей таблице.</span><span class="sxs-lookup"><span data-stu-id="68488-107">Filtered indexes can provide the following advantages over full-table indexes:</span></span>  
  
-   <span data-ttu-id="68488-108">**Улучшение производительности запроса и качества плана**</span><span class="sxs-lookup"><span data-stu-id="68488-108">**Improved query performance and plan quality**</span></span>  
  
     <span data-ttu-id="68488-109">Хорошо спроектированный отфильтрованный индекс повышает производительность запроса и качество плана выполнения, поскольку он меньше, чем полнотабличный некластеризованный индекс, и содержит отфильтрованную статистику.</span><span class="sxs-lookup"><span data-stu-id="68488-109">A well-designed filtered index improves query performance and execution plan quality because it is smaller than a full-table nonclustered index and has filtered statistics.</span></span> <span data-ttu-id="68488-110">Отфильтрованная статистика точнее полнотабличной статистики, так как содержит только строки отфильтрованного индекса.</span><span class="sxs-lookup"><span data-stu-id="68488-110">The filtered statistics are more accurate than full-table statistics because they cover only the rows in the filtered index.</span></span>  
  
-   <span data-ttu-id="68488-111">**Снижение расходов на обслуживание индекса**</span><span class="sxs-lookup"><span data-stu-id="68488-111">**Reduced index maintenance costs**</span></span>  
  
     <span data-ttu-id="68488-112">Индекс обслуживается только в случае, если инструкции языка обработки данных (DML) затрагивают данные в индексе.</span><span class="sxs-lookup"><span data-stu-id="68488-112">An index is maintained only when data manipulation language (DML) statements affect the data in the index.</span></span> <span data-ttu-id="68488-113">Фильтруемый индекс уменьшает затраты на обслуживание индекса по сравнению с полнотабличным некластеризованным индексом, поскольку он меньше и обслуживается только при изменении данных в индексе.</span><span class="sxs-lookup"><span data-stu-id="68488-113">A filtered index reduces index maintenance costs compared with a full-table nonclustered index because it is smaller and is only maintained when the data in the index is changed.</span></span> <span data-ttu-id="68488-114">Возможно наличие большого числа фильтруемых индексов, особенно если они содержат редко изменяющиеся данные.</span><span class="sxs-lookup"><span data-stu-id="68488-114">It is possible to have a large number of filtered indexes, especially when they contain data that is changed infrequently.</span></span> <span data-ttu-id="68488-115">Аналогично, если фильтруемый индекс содержит только часто изменяемые данные, меньший размер индекса уменьшает затраты на обновление статистики.</span><span class="sxs-lookup"><span data-stu-id="68488-115">Similarly, if a filtered index contains only the frequently modified data, the smaller size of the index reduces the cost of updating the statistics.</span></span>  
  
-   <span data-ttu-id="68488-116">**Снижение затрат на хранение индекса**</span><span class="sxs-lookup"><span data-stu-id="68488-116">**Reduced index storage costs**</span></span>  
  
     <span data-ttu-id="68488-117">Создание отфильтрованного индекса может уменьшить место на диске для некластеризованных индексов, если нет необходимости в полнотабличном индексе.</span><span class="sxs-lookup"><span data-stu-id="68488-117">Creating a filtered index can reduce disk storage for nonclustered indexes when a full-table index is not necessary.</span></span> <span data-ttu-id="68488-118">Полнотабличный некластеризованный индекс можно заменить несколькими отфильтрованными индексами без значительного увеличения требований к хранилищу.</span><span class="sxs-lookup"><span data-stu-id="68488-118">You can replace a full-table nonclustered index with multiple filtered indexes without significantly increasing the storage requirements.</span></span>  
  
 <span data-ttu-id="68488-119">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="68488-119">**In This Topic**</span></span>  
  
-   <span data-ttu-id="68488-120">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="68488-120">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="68488-121">Вопросы проектирования</span><span class="sxs-lookup"><span data-stu-id="68488-121">Design Considerations</span></span>](#Design)  
  
     [<span data-ttu-id="68488-122">Ограничения</span><span class="sxs-lookup"><span data-stu-id="68488-122">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="68488-123">Безопасность</span><span class="sxs-lookup"><span data-stu-id="68488-123">Security</span></span>](#Security)  
  
-   <span data-ttu-id="68488-124">**Создание фильтруемого индекса с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="68488-124">**To create a filtered index, using:**</span></span>  
  
     [<span data-ttu-id="68488-125">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68488-125">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="68488-126">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="68488-126">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="68488-127">Перед началом</span><span class="sxs-lookup"><span data-stu-id="68488-127">Before You Begin</span></span>  
  
###  <a name="design-considerations"></a><a name="Design"></a> <span data-ttu-id="68488-128">Вопросы проектирования</span><span class="sxs-lookup"><span data-stu-id="68488-128">Design Considerations</span></span>  
  
-   <span data-ttu-id="68488-129">Если столбец содержит только небольшое число удовлетворяющих запросу значений, можно создать отфильтрованный индекс на этом подмножестве значений.</span><span class="sxs-lookup"><span data-stu-id="68488-129">When a column only has a small number of relevant values for queries, you can create a filtered index on the subset of values.</span></span> <span data-ttu-id="68488-130">Например, если столбец содержит в основном значения NULL, а запрос выбирает только из значений, отличных от NULL, можно создать отфильтрованный индекс для строк данных, отличных от NULL.</span><span class="sxs-lookup"><span data-stu-id="68488-130">For example, when the values in a column are mostly NULL and the query selects only from the non-NULL values, you can create a filtered index for the non-NULL data rows.</span></span> <span data-ttu-id="68488-131">В результате индекс уменьшится и затраты на его обслуживание будут значительно меньше, чем для полнотабличного некластеризованного индекса на тех же ключевых столбцах.</span><span class="sxs-lookup"><span data-stu-id="68488-131">The resulting index will be smaller and cost less to maintain than a full-table nonclustered index defined on the same key columns.</span></span>  
  
-   <span data-ttu-id="68488-132">Если таблица содержит строки с разнородными данными, можно создать отфильтрованный индекс для одной или более категорий данных.</span><span class="sxs-lookup"><span data-stu-id="68488-132">When a table has heterogeneous data rows, you can create a filtered index for one or more categories of data.</span></span> <span data-ttu-id="68488-133">Это может позволить повысить производительность запросов этих строк данных с помощью ограничения области запроса до определенной области таблицы.</span><span class="sxs-lookup"><span data-stu-id="68488-133">This can improve the performance of queries on these data rows by narrowing the focus of a query to a specific area of the table.</span></span> <span data-ttu-id="68488-134">В результате индекс уменьшится и затраты на его обслуживание будут значительно меньше, чем для полнотабличного некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="68488-134">Again, the resulting index will be smaller and cost less to maintain than a full-table nonclustered index.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="68488-135">Ограничения</span><span class="sxs-lookup"><span data-stu-id="68488-135">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="68488-136">Невозможно создать отфильтрованный индекс для представления.</span><span class="sxs-lookup"><span data-stu-id="68488-136">You cannot create a filtered index on a view.</span></span> <span data-ttu-id="68488-137">Однако оптимизатор запросов может извлечь выгоду из отфильтрованного индекса, определенного в таблице, на которую имеется ссылка в представлении.</span><span class="sxs-lookup"><span data-stu-id="68488-137">However, the query optimizer can benefit from a filtered index defined on a table that is referenced in a view.</span></span> <span data-ttu-id="68488-138">Оптимизатор запросов рассматривает отфильтрованный индекс для запроса, выбирающего данные из представления, если результат запроса будет корректен.</span><span class="sxs-lookup"><span data-stu-id="68488-138">The query optimizer considers a filtered index for a query that selects from a view if the query results will be correct.</span></span>  
  
-   <span data-ttu-id="68488-139">Отфильтрованные индексы имеют следующие преимущества по сравнению с индексированными представлениями.</span><span class="sxs-lookup"><span data-stu-id="68488-139">Filtered indexes have the following advantages over indexed views:</span></span>  
  
    -   <span data-ttu-id="68488-140">Снижение расходов на обслуживание индекса</span><span class="sxs-lookup"><span data-stu-id="68488-140">Reduced index maintenance costs.</span></span> <span data-ttu-id="68488-141">Например, для обновления отфильтрованного индекса обработчик запросов использует меньшее количество ресурсов ЦП, чем для индексированного представления.</span><span class="sxs-lookup"><span data-stu-id="68488-141">For example, the query processor uses fewer CPU resources to update a filtered index than an indexed view.</span></span>  
  
    -   <span data-ttu-id="68488-142">Повышение качества планов.</span><span class="sxs-lookup"><span data-stu-id="68488-142">Improved plan quality.</span></span> <span data-ttu-id="68488-143">Например, во время компиляции запроса оптимизатор запросов рассматривает использование отфильтрованного индекса в большем количестве ситуаций, чем для эквивалентного индексированного представления.</span><span class="sxs-lookup"><span data-stu-id="68488-143">For example, during query compilation, the query optimizer considers using a filtered index in more situations than the equivalent indexed view.</span></span>  
  
    -   <span data-ttu-id="68488-144">Перестроение индексов в сети.</span><span class="sxs-lookup"><span data-stu-id="68488-144">Online index rebuilds.</span></span> <span data-ttu-id="68488-145">Отфильтрованные индексы можно перестраивать, если они доступны для запросов.</span><span class="sxs-lookup"><span data-stu-id="68488-145">You can rebuild filtered indexes while they are available for queries.</span></span> <span data-ttu-id="68488-146">Для индексированных представлений перестроение индексов в сети не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="68488-146">Online index rebuilds are not supported for indexed views.</span></span> <span data-ttu-id="68488-147">Дополнительные сведения см. в описании параметра REBUILD для [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="68488-147">For more information, see the REBUILD option for [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
    -   <span data-ttu-id="68488-148">Неуникальные индексы.</span><span class="sxs-lookup"><span data-stu-id="68488-148">Non-unique indexes.</span></span> <span data-ttu-id="68488-149">Отфильтрованные индексы могут быть неуникальными, тогда как индексированные представления должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="68488-149">Filtered indexes can be non-unique, whereas indexed views must be unique.</span></span>  
  
-   <span data-ttu-id="68488-150">Отфильтрованные индексы определены в одной таблице и поддерживают только простые операторы сравнения.</span><span class="sxs-lookup"><span data-stu-id="68488-150">Filtered indexes are defined on one table and only support simple comparison operators.</span></span> <span data-ttu-id="68488-151">Если необходим критерий фильтра, который ссылается на множество таблиц или имеет сложную логику, нужно создать представление.</span><span class="sxs-lookup"><span data-stu-id="68488-151">If you need a filter expression that references multiple tables or has complex logic, you should create a view.</span></span>  
  
-   <span data-ttu-id="68488-152">Столбец в выражении отфильтрованного индекса не обязательно должен быть ключевым или включенным столбцом в определении отфильтрованного индекса, если выражение отфильтрованного индекса эквивалентно предикату запроса, а запрос не возвращает столбец с результатами запроса в выражение отфильтрованного индекса.</span><span class="sxs-lookup"><span data-stu-id="68488-152">A column in the filtered index expression does not need to be a key or included column in the filtered index definition if the filtered index expression is equivalent to the query predicate and the query does not return the column in the filtered index expression with the query results.</span></span>  
  
-   <span data-ttu-id="68488-153">Столбец в выражении отфильтрованного индекса должен быть ключевым или включенным столбцом в определении отфильтрованного индекса, если предикат запроса использует в сравнении столбец, который не эквивалентен выражению отфильтрованного индекса.</span><span class="sxs-lookup"><span data-stu-id="68488-153">A column in the filtered index expression should be a key or included column in the filtered index definition if the query predicate uses the column in a comparison that is not equivalent to the filtered index expression.</span></span>  
  
-   <span data-ttu-id="68488-154">Столбец в выражении отфильтрованного индекса должен быть ключевым или включенным столбцом в определении отфильтрованного индекса, если этот столбец содержится в результирующем наборе запроса.</span><span class="sxs-lookup"><span data-stu-id="68488-154">A column in the filtered index expression should be a key or included column in the filtered index definition if the column is in the query result set.</span></span>  
  
-   <span data-ttu-id="68488-155">Ключ кластеризованного индекса таблицы необязательно должен быть ключевым или включенным столбцом в определении отфильтрованного индекса.</span><span class="sxs-lookup"><span data-stu-id="68488-155">The clustered index key of the table does not need to be a key or included column in the filtered index definition.</span></span> <span data-ttu-id="68488-156">Ключ кластеризованного индекса автоматически включается во все некластеризованные индексы, в том числе отфильтрованные индексы.</span><span class="sxs-lookup"><span data-stu-id="68488-156">The clustered index key is automatically included in all nonclustered indexes, including filtered indexes.</span></span>  
  
-   <span data-ttu-id="68488-157">Если оператор сравнения определен в выражении отфильтрованного индекса результатов отфильтрованного индекса в неявном или явном преобразовании данных, произойдет ошибка, если преобразование выполняется в левой части оператора сравнения.</span><span class="sxs-lookup"><span data-stu-id="68488-157">If the comparison operator specified in the filtered index expression of the filtered index results in an implicit or explicit data conversion, an error will occur if the conversion occurs on the left side of a comparison operator.</span></span> <span data-ttu-id="68488-158">Решением является применение выражения отфильтрованного индекса с оператором преобразования данных (CAST или CONVERT) в правой части оператора сравнения.</span><span class="sxs-lookup"><span data-stu-id="68488-158">A solution is to write the filtered index expression with the data conversion operator (CAST or CONVERT) on the right side of the comparison operator.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="68488-159">безопасность</span><span class="sxs-lookup"><span data-stu-id="68488-159">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="68488-160">Permissions</span><span class="sxs-lookup"><span data-stu-id="68488-160">Permissions</span></span>  
 <span data-ttu-id="68488-161">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="68488-161">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="68488-162">Пользователь должен быть членом предопределенной роли сервера **sysadmin** или предопределенных ролей базы данных **db_ddladmin** и **db_owner**.</span><span class="sxs-lookup"><span data-stu-id="68488-162">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span> <span data-ttu-id="68488-163">Для изменения выражения отфильтрованного индекса используйте инструкцию CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="68488-163">To modify the filtered index expression, use CREATE INDEX WITH DROP_EXISTING.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="68488-164">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68488-164">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-filtered-index"></a><span data-ttu-id="68488-165">Создание фильтруемого индекса</span><span class="sxs-lookup"><span data-stu-id="68488-165">To create a filtered index</span></span>  
  
1.  <span data-ttu-id="68488-166">В обозревателе объектов щелкните знак «плюс», чтобы развернуть базу данных, содержащую таблицу, в которой необходимо создать отфильтрованный индекс.</span><span class="sxs-lookup"><span data-stu-id="68488-166">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to create a filtered index.</span></span>  
  
2.  <span data-ttu-id="68488-167">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="68488-167">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="68488-168">Щелкните знак «плюс», чтобы развернуть таблицу, в которой необходимо создать отфильтрованный индекс.</span><span class="sxs-lookup"><span data-stu-id="68488-168">Click the plus sign to expand the table on which you want to create a filtered index.</span></span>  
  
4.  <span data-ttu-id="68488-169">Щелкните правой кнопкой мыши папку **Индексы**, выберите **Создать индекс** и **Некластеризованный индекс...**</span><span class="sxs-lookup"><span data-stu-id="68488-169">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="68488-170">В диалоговом окне **Создание индекса** на странице **Общие** введите имя нового индекса в поле **Имя индекса** .</span><span class="sxs-lookup"><span data-stu-id="68488-170">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="68488-171">В разделе **Ключевые столбцы индекса** щелкните **Добавить…** .</span><span class="sxs-lookup"><span data-stu-id="68488-171">Under **Index key columns**, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="68488-172">В диалоговом окне **Выбор столбцов из**_table_name_ установите флажки для столбцов таблицы или столбцов, которые будут добавлены в уникальный индекс.</span><span class="sxs-lookup"><span data-stu-id="68488-172">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the unique index.</span></span>  
  
8.  <span data-ttu-id="68488-173">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="68488-173">Click **OK**.</span></span>  
  
9. <span data-ttu-id="68488-174">На странице **Фильтр** в поле **Критерий фильтра** введите выражение SQL, которое будет использоваться для создания фильтруемого индекса.</span><span class="sxs-lookup"><span data-stu-id="68488-174">On the **Filter** page, under **Filter Expression**, enter SQL expression that you'll use to create the filtered index.</span></span>  
  
10. <span data-ttu-id="68488-175">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="68488-175">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="68488-176">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="68488-176">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-filtered-index"></a><span data-ttu-id="68488-177">Создание фильтруемого индекса</span><span class="sxs-lookup"><span data-stu-id="68488-177">To create a filtered index</span></span>  
  
1.  <span data-ttu-id="68488-178">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68488-178">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="68488-179">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="68488-179">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="68488-180">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="68488-180">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Looks for an existing filtered index named "FIBillOfMaterialsWithEndDate"  
    -- and deletes it from the table Production.BillOfMaterials if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
        WHERE name = N'FIBillOfMaterialsWithEndDate'  
        AND object_id = OBJECT_ID (N'Production.BillOfMaterials'))  
    DROP INDEX FIBillOfMaterialsWithEndDate  
        ON Production.BillOfMaterials  
    GO  
    -- Creates a filtered index "FIBillOfMaterialsWithEndDate"  
    -- on the table Production.BillOfMaterials   
    -- using the columms ComponentID and StartDate.  
  
    CREATE NONCLUSTERED INDEX FIBillOfMaterialsWithEndDate  
        ON Production.BillOfMaterials (ComponentID, StartDate)  
        WHERE EndDate IS NOT NULL ;  
    GO  
    ```  
  
     <span data-ttu-id="68488-181">Фильтруемый индекс выше является действительным для следующего запроса.</span><span class="sxs-lookup"><span data-stu-id="68488-181">The filtered index above is valid for the following query.</span></span> <span data-ttu-id="68488-182">Можно отобразить план выполнения запроса для проверки того, использует ли оптимизатор запросов отфильтрованный индекс.</span><span class="sxs-lookup"><span data-stu-id="68488-182">You can display the query execution plan to determine if the query optimizer used the filtered index.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT ProductAssemblyID, ComponentID, StartDate   
    FROM Production.BillOfMaterials  
    WHERE EndDate IS NOT NULL   
        AND ComponentID = 5   
        AND StartDate > '01/01/2008' ;  
    GO  
    ```  
  
#### <a name="to-ensure-that-a-filtered-index-is-used-in-a-sql-query"></a><span data-ttu-id="68488-183">Обеспечение использования фильтруемого индекса в SQL-запросе</span><span class="sxs-lookup"><span data-stu-id="68488-183">To ensure that a filtered index is used in a SQL query</span></span>  
  
1.  <span data-ttu-id="68488-184">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68488-184">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="68488-185">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="68488-185">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="68488-186">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="68488-186">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT ComponentID, StartDate FROM Production.BillOfMaterials  
        WITH ( INDEX ( FIBillOfMaterialsWithEndDate ) )   
    WHERE EndDate IN ('20000825', '20000908', '20000918');   
    GO  
    ```  
  
 <span data-ttu-id="68488-187">Дополнительные сведения см. в статье [CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="68488-187">For more information, see  [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
