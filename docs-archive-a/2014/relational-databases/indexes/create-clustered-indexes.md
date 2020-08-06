---
title: Создание кластеризованных индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], clustered indexes
- clustered indexes, creating
- clustered indexes, PRIMARY KEY constraint
- clustered indexes, UNIQUE constraint
- indexes [SQL Server], clustered
ms.assetid: 47148383-c2c7-4f08-a9e4-7016bf2d1d13
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 567ff9a01bd93323149168b9e3aa0f34d78aee39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658711"
---
# <a name="create-clustered-indexes"></a><span data-ttu-id="32f19-102">Создание кластеризованных индексов</span><span class="sxs-lookup"><span data-stu-id="32f19-102">Create Clustered Indexes</span></span>
  <span data-ttu-id="32f19-103">Кластеризованные индексы для таблиц в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно создать с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32f19-103">You can create clustered indexes on tables in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="32f19-104">За некоторыми исключениями, каждая таблица должна иметь кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="32f19-104">With few exceptions, every table should have a clustered index.</span></span> <span data-ttu-id="32f19-105">Кроме того, что кластеризованный индекс повышает производительность запросов, его можно перестраивать или переорганизовывать по запросу, управляя фрагментацией таблицы.</span><span class="sxs-lookup"><span data-stu-id="32f19-105">Besides improving query performance, a clustered index can be rebuilt or reorganized on demand to control table fragmentation.</span></span> <span data-ttu-id="32f19-106">Кластеризованный индекс может быть также создан для представления.</span><span class="sxs-lookup"><span data-stu-id="32f19-106">A clustered index can also be created on a view.</span></span> <span data-ttu-id="32f19-107">(Кластеризованные индексы определены в разделе [Описания кластеризованных и некластеризованных индексов](clustered-and-nonclustered-indexes-described.md).)</span><span class="sxs-lookup"><span data-stu-id="32f19-107">(Clustered indexes are defined in the topic [Clustered and Nonclustered Indexes Described](clustered-and-nonclustered-indexes-described.md).)</span></span>  
  
 <span data-ttu-id="32f19-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="32f19-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="32f19-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="32f19-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="32f19-110">Стандартные реализации</span><span class="sxs-lookup"><span data-stu-id="32f19-110">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="32f19-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="32f19-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="32f19-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="32f19-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="32f19-113">**Для создания кластеризованного индекса для таблицы используется:**</span><span class="sxs-lookup"><span data-stu-id="32f19-113">**To create a clustered index on a table, using:**</span></span>  
  
     [<span data-ttu-id="32f19-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="32f19-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="32f19-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="32f19-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="32f19-116">Перед началом</span><span class="sxs-lookup"><span data-stu-id="32f19-116">Before You Begin</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="32f19-117">Стандартные реализации</span><span class="sxs-lookup"><span data-stu-id="32f19-117">Typical Implementations</span></span>  
 <span data-ttu-id="32f19-118">Кластеризованные индексы реализуются следующими методами.</span><span class="sxs-lookup"><span data-stu-id="32f19-118">Clustered indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="32f19-119">**Ограничениями PRIMARY KEY и UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="32f19-119">**PRIMARY KEY and UNIQUE constraints**</span></span>  
  
     <span data-ttu-id="32f19-120">Если кластеризованный индекс в таблице еще не создан, а уникальный некластеризованный индекс еще не указан, то при создании ограничения PRIMARY KEY в одном или нескольких столбцах автоматически создается уникальный кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="32f19-120">When you create a PRIMARY KEY constraint, a unique clustered index on the column or columns is automatically created if a clustered index on the table does not already exist and you do not specify a unique nonclustered index.</span></span> <span data-ttu-id="32f19-121">В первичном ключевом столбце недопустимы значения NULL.</span><span class="sxs-lookup"><span data-stu-id="32f19-121">The primary key column cannot allow NULL values.</span></span>  
  
     <span data-ttu-id="32f19-122">При создании ограничения UNIQUE создается уникальный некластеризованный индекс. Он нужен, чтобы принудительно применять ограничение UNIQUE по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="32f19-122">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="32f19-123">Если кластеризованный индекс в таблице еще не создан, то можно указать уникальный кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="32f19-123">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span>  
  
     <span data-ttu-id="32f19-124">Индексу, создаваемому в составе ограничения, автоматически присваивается то же имя, что и имя ограничения.</span><span class="sxs-lookup"><span data-stu-id="32f19-124">An index created as part of the constraint is automatically given the same name as the constraint name.</span></span> <span data-ttu-id="32f19-125">Дополнительные сведения см. в разделах [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md) и [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="32f19-125">For more information, see [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md) and [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
-   <span data-ttu-id="32f19-126">**Индекс, не зависящий от ограничения**</span><span class="sxs-lookup"><span data-stu-id="32f19-126">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="32f19-127">Можно создать кластеризованный индекс в столбце, отличном от первичного ключевого столбца, если задано ограничение некластеризованного первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="32f19-127">You can create a clustered index on a column other than primary key column if a nonclustered primary key constraint was specified.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="32f19-128">Ограничения</span><span class="sxs-lookup"><span data-stu-id="32f19-128">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="32f19-129">При создании кластеризованного индекса в соответствующих файлах и файловых группах требуется столько места на диске, сколько суммарно занимают старые (исходные) и новые (целевые) структуры.</span><span class="sxs-lookup"><span data-stu-id="32f19-129">When a clustered index structure is created, disk space for both the old (source) and new (target) structures is required in their respective files and filegroups.</span></span> <span data-ttu-id="32f19-130">Старая структура не освобождается до тех пор, пока не зафиксирована вся транзакция создания индекса.</span><span class="sxs-lookup"><span data-stu-id="32f19-130">The old structure is not deallocated until the complete transaction commits.</span></span> <span data-ttu-id="32f19-131">Кроме того, для сортировки может временно потребоваться дополнительное место на диске.</span><span class="sxs-lookup"><span data-stu-id="32f19-131">Additional temporary disk space for sorting may also be required.</span></span> <span data-ttu-id="32f19-132">Дополнительные сведения см. в статье [Disk Space Requirements for Index DDL Operations](disk-space-requirements-for-index-ddl-operations.md).</span><span class="sxs-lookup"><span data-stu-id="32f19-132">For more information, see [Disk Space Requirements for Index DDL Operations](disk-space-requirements-for-index-ddl-operations.md).</span></span>  
  
-   <span data-ttu-id="32f19-133">Если кластеризованный индекс создается в куче с несколькими существующими некластеризованными индексами, все некластеризованные индексы необходимо перестроить, чтобы они содержали значение ключа кластеризации, а не идентификатор строки (RID).</span><span class="sxs-lookup"><span data-stu-id="32f19-133">If a clustered index is created on a heap with several existing nonclustered indexes, all the nonclustered indexes must be rebuilt so that they contain the clustering key value instead of the row identifier (RID).</span></span> <span data-ttu-id="32f19-134">Точно так же, если кластеризованный индекс удаляется из таблицы с несколькими некластеризованными индексами, некластеризованные индексы перестраиваются в ходе операции DROP.</span><span class="sxs-lookup"><span data-stu-id="32f19-134">Similarly, if a clustered index is dropped on a table that has several nonclustered indexes, the nonclustered indexes are all rebuilt as part of the DROP operation.</span></span> <span data-ttu-id="32f19-135">Для больших таблиц это может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="32f19-135">This may take significant time on large tables.</span></span>  
  
     <span data-ttu-id="32f19-136">Предпочтительный способ построения индекса в больших таблицах — это начать с кластеризованного индекса, а затем построить некластеризованные.</span><span class="sxs-lookup"><span data-stu-id="32f19-136">The preferred way to build indexes on large tables is to start with the clustered index and then build any nonclustered indexes.</span></span> <span data-ttu-id="32f19-137">При создании индексов для существующих таблиц рассмотрите целесообразность присвоения параметру ONLINE значения ON.</span><span class="sxs-lookup"><span data-stu-id="32f19-137">Consider setting the ONLINE option to ON when you create indexes on existing tables.</span></span> <span data-ttu-id="32f19-138">В этом случае длительные блокировки таблиц удерживаться не будут.</span><span class="sxs-lookup"><span data-stu-id="32f19-138">When set to ON, long-term table locks are not held.</span></span> <span data-ttu-id="32f19-139">Это позволит продолжить выполнение запросов или обновление базовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="32f19-139">This enables queries or updates to the underlying table to continue.</span></span> <span data-ttu-id="32f19-140">Дополнительные сведения см. в статье [Выполнение операции с индексами в сети](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="32f19-140">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
-   <span data-ttu-id="32f19-141">Ключ кластеризованного индекса не может включать в себя столбцы `varchar`, для которых существуют данные в единице распределения ROW_OVERFLOW_DATA.</span><span class="sxs-lookup"><span data-stu-id="32f19-141">The index key of a clustered index cannot contain `varchar` columns that have existing data in the ROW_OVERFLOW_DATA allocation unit.</span></span> <span data-ttu-id="32f19-142">Если кластеризованный индекс создается для столбца типа `varchar` и существующие данные располагаются в единице распределения IN_ROW_DATA, то все последующие операции вставки или обновления для данного столбца, выталкивающие данные за пределы строки, будут завершаться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="32f19-142">If a clustered index is created on a `varchar` column and the existing data is in the IN_ROW_DATA allocation unit, subsequent insert or update actions on the column that would push the data off-row will fail.</span></span> <span data-ttu-id="32f19-143">Для получения сведений о таблицах, которые могут содержать превышающие размер страницы данные строки, используется функция динамического управления [sys.dm_db_index_physical_stats (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="32f19-143">To obtain information about tables that might contain row-overflow data, use the [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql) dynamic management function.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="32f19-144">безопасность</span><span class="sxs-lookup"><span data-stu-id="32f19-144">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="32f19-145">Permissions</span><span class="sxs-lookup"><span data-stu-id="32f19-145">Permissions</span></span>  
 <span data-ttu-id="32f19-146">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="32f19-146">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="32f19-147">Пользователь должен быть членом предопределенной роли сервера **sysadmin** или предопределенных ролей базы данных **db_ddladmin** и **db_owner**.</span><span class="sxs-lookup"><span data-stu-id="32f19-147">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="32f19-148">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="32f19-148">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-clustered-index-by-using-object-explorer"></a><span data-ttu-id="32f19-149">Создание кластеризованного индекса в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="32f19-149">To create a clustered index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="32f19-150">В обозревателе объектов разверните таблицу, в которой необходимо создать кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="32f19-150">In Object Explorer, expand the table on which you want to create a clustered index.</span></span>  
  
2.  <span data-ttu-id="32f19-151">Щелкните правой кнопкой мыши папку **Индексы**, наведите указатель на пункт **Создать индекс** и выберите пункт **Кластеризованный индекс**.</span><span class="sxs-lookup"><span data-stu-id="32f19-151">Right-click the **Indexes** folder, point to **New Index**, and select **Clustered Index...**.</span></span>  
  
3.  <span data-ttu-id="32f19-152">В диалоговом окне **Создание индекса** на странице **Общие** введите имя нового индекса в поле **Имя индекса** .</span><span class="sxs-lookup"><span data-stu-id="32f19-152">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
4.  <span data-ttu-id="32f19-153">В разделе **Ключевые столбцы индекса** щелкните **Добавить…** .</span><span class="sxs-lookup"><span data-stu-id="32f19-153">Under **Index key columns**, click **Add...**.</span></span>  
  
5.  <span data-ttu-id="32f19-154">В диалоговом окне **Выбор столбцов из**_table_name_ установите флажок для столбца таблицы, который будет добавлен в кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="32f19-154">In the **Select Columns from**_table_name_ dialog box, select the check box of the table column to be added to the clustered index.</span></span>  
  
6.  <span data-ttu-id="32f19-155">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="32f19-155">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="32f19-156">В диалоговом окне **Создание индекса** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="32f19-156">In the **New Index** dialog box, click **OK**.</span></span>  
  
#### <a name="to-create-a-clustered-index-by-using-the-table-designer"></a><span data-ttu-id="32f19-157">Создание кластеризованного индекса с помощью конструктора таблиц</span><span class="sxs-lookup"><span data-stu-id="32f19-157">To create a clustered index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="32f19-158">В обозревателе объектов разверните базу данных, в которой необходимо создать таблицу с кластеризованным индексом.</span><span class="sxs-lookup"><span data-stu-id="32f19-158">In Object Explorer, expand the database on which you want to create a table with a clustered index.</span></span>  
  
2.  <span data-ttu-id="32f19-159">Щелкните правой кнопкой мыши папку **Таблицы** и выберите команду **Создать таблицу...** .</span><span class="sxs-lookup"><span data-stu-id="32f19-159">Right-click the **Tables** folder and click **New Table...**.</span></span>  
  
3.  <span data-ttu-id="32f19-160">Создайте новую таблицу обычным способом.</span><span class="sxs-lookup"><span data-stu-id="32f19-160">Create a new table as you normally would.</span></span> <span data-ttu-id="32f19-161">Дополнительные сведения см. в статье [Создание таблиц (компонент Database Engine)](../tables/create-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="32f19-161">For more information, see [Create Tables &#40;Database Engine&#41;](../tables/create-tables-database-engine.md).</span></span>  
  
4.  <span data-ttu-id="32f19-162">Щелкните правой кнопкой мыши созданную таблицу и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="32f19-162">Right-click the new table created above and click **Design**.</span></span>  
  
5.  <span data-ttu-id="32f19-163">В меню **Конструктор таблиц** выберите пункт **Индексы и ключи**.</span><span class="sxs-lookup"><span data-stu-id="32f19-163">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
6.  <span data-ttu-id="32f19-164">В диалоговом окне **Индексы и ключи** нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="32f19-164">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
7.  <span data-ttu-id="32f19-165">Выберите новый индекс в текстовом поле **Выбранный первичный/уникальный ключ или индекс** .</span><span class="sxs-lookup"><span data-stu-id="32f19-165">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
8.  <span data-ttu-id="32f19-166">Выберите в сетке **Создать как кластеризованный**и из раскрывающегося списка справа от свойства выберите **Да** .</span><span class="sxs-lookup"><span data-stu-id="32f19-166">In the grid, select **Create as Clustered**, and choose **Yes** from the drop-down list to the right of the property.</span></span>  
  
9. <span data-ttu-id="32f19-167">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="32f19-167">Click **Close**.</span></span>  
  
10. <span data-ttu-id="32f19-168">В меню **Файл** выберите пункт **Сохранить**_имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="32f19-168">On the **File** menu, click **Save**_table_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="32f19-169">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="32f19-169">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-clustered-index"></a><span data-ttu-id="32f19-170">Создание кластеризованного индекса</span><span class="sxs-lookup"><span data-stu-id="32f19-170">To create a clustered index</span></span>  
  
1.  <span data-ttu-id="32f19-171">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32f19-171">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="32f19-172">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="32f19-172">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="32f19-173">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="32f19-173">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Create a new table with three columns.  
    CREATE TABLE dbo.TestTable  
        (TestCol1 int NOT NULL,  
         TestCol2 nchar(10) NULL,  
         TestCol3 nvarchar(50) NULL);  
    GO  
    -- Create a clustered index called IX_TestTable_TestCol1  
    -- on the dbo.TestTable table using the TestCol1 column.  
    CREATE CLUSTERED INDEX IX_TestTable_TestCol1   
        ON dbo.TestTable (TestCol1);   
    GO  
    ```  
  
 <span data-ttu-id="32f19-174">Дополнительные сведения см. в разделе [CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="32f19-174">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f19-175">См. также:</span><span class="sxs-lookup"><span data-stu-id="32f19-175">See Also</span></span>  
 <span data-ttu-id="32f19-176">[Создание первичных ключей](../tables/create-primary-keys.md) </span><span class="sxs-lookup"><span data-stu-id="32f19-176">[Create Primary Keys](../tables/create-primary-keys.md) </span></span>  
 [<span data-ttu-id="32f19-177">Создание ограничений уникальности</span><span class="sxs-lookup"><span data-stu-id="32f19-177">Create Unique Constraints</span></span>](../tables/create-unique-constraints.md)  
  
  
