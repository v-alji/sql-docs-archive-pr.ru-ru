---
title: Создание индексов с включенными столбцами | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index size [SQL Server]
- index keys [SQL Server]
- index columns [SQL Server]
- size [SQL Server], indexes
- key columns [SQL Server]
- included columns
- nonclustered indexes [SQL Server], included columns
- designing indexes [SQL Server], included columns
- nonkey columns
ms.assetid: d198648d-fea5-416d-9f30-f9d4aebbf4ec
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e5a464f9791ea635236069555647229bf1f0d79e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749848"
---
# <a name="create-indexes-with-included-columns"></a><span data-ttu-id="0c2d6-102">Создание индексов с включенными столбцами</span><span class="sxs-lookup"><span data-stu-id="0c2d6-102">Create Indexes with Included Columns</span></span>
  <span data-ttu-id="0c2d6-103">В этой теме описывается добавление невключенных или неключевых столбцов, чтобы расширить функциональные возможности некластеризованных индексов в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c2d6-103">This topic describes how to add included (or nonkey) columns to extend the functionality of nonclustered indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0c2d6-104">Добавление неключевых столбцов позволяет создавать некластеризованные индексы, покрывающие больше запросов.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-104">By including nonkey columns, you can create nonclustered indexes that cover more queries.</span></span> <span data-ttu-id="0c2d6-105">Это обусловлено следующими преимуществами неключевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-105">This is because the nonkey columns have the following benefits:</span></span>  
  
-   <span data-ttu-id="0c2d6-106">Они могут содержать типы данных, не разрешенные для ключевых столбцов индекса.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-106">They can be data types not allowed as index key columns.</span></span>  
  
-   <span data-ttu-id="0c2d6-107">Они не учитываются компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)] при расчете числа ключевых столбцов индекса и размера ключа индекса.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-107">They are not considered by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] when calculating the number of index key columns or index key size.</span></span>  
  
 <span data-ttu-id="0c2d6-108">Индекс с неключевыми столбцами может значительно повысить производительность запроса, когда все столбцы запроса включены в индекс как ключевые или неключевые.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-108">An index with nonkey columns can significantly improve query performance when all columns in the query are included in the index either as key or nonkey columns.</span></span> <span data-ttu-id="0c2d6-109">Производительность повышается благодаря тому, что оптимизатор запросов может найти все значения столбцов в этом индексе; при этом нет обращения к данным таблиц или кластеризованных индексов, что приводит к меньшему количеству дисковых операций ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-109">Performance gains are achieved because the query optimizer can locate all the column values within the index; table or clustered index data is not accessed resulting in fewer disk I/O operations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c2d6-110">Если индекс содержит все столбцы, на которых в запросе имеются ссылки, это обычно называется *покрытием запроса*.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-110">When an index contains all the columns referenced by a query it is typically referred to as *covering the query*.</span></span>  
  
 <span data-ttu-id="0c2d6-111">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="0c2d6-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0c2d6-112">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="0c2d6-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0c2d6-113">Рекомендации по проектированию</span><span class="sxs-lookup"><span data-stu-id="0c2d6-113">Design Recommendations</span></span>](#DesignRecs)  
  
     [<span data-ttu-id="0c2d6-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0c2d6-114">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0c2d6-115">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0c2d6-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0c2d6-116">**Создание индекса с неключевыми столбцами с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="0c2d6-116">**To create an index with nonkey columns, using:**</span></span>  
  
     [<span data-ttu-id="0c2d6-117">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c2d6-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0c2d6-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0c2d6-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0c2d6-119">Перед началом</span><span class="sxs-lookup"><span data-stu-id="0c2d6-119">Before You Begin</span></span>  
  
###  <a name="design-recommendations"></a><a name="DesignRecs"></a> <span data-ttu-id="0c2d6-120">Рекомендации по проектированию</span><span class="sxs-lookup"><span data-stu-id="0c2d6-120">Design Recommendations</span></span>  
  
-   <span data-ttu-id="0c2d6-121">Переопределите некластеризованные индексы с большим размером ключа индекса, чтобы только столбцы, используемые для поиска и уточняющего запроса, были ключевыми.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-121">Redesign nonclustered indexes with a large index key size so that only columns used for searching and lookups are key columns.</span></span> <span data-ttu-id="0c2d6-122">Все остальные столбцы, покрывающие запрос, сделайте неключевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-122">Make all other columns that cover the query into nonkey columns.</span></span> <span data-ttu-id="0c2d6-123">Таким образом, в наличии будут все столбцы, покрывающие запрос, но сам ключ индекса будет небольшим и эффективным.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-123">In this way, you will have all columns needed to cover the query, but the index key itself is small and efficient.</span></span>  
  
-   <span data-ttu-id="0c2d6-124">Включите неключевые столбцы в некластеризованный индекс, чтобы избежать превышения текущих ограничений на размер индекса (16 ключевых столбцов) и размер ключа индекса (900 байт).</span><span class="sxs-lookup"><span data-stu-id="0c2d6-124">Include nonkey columns in a nonclustered index to avoid exceeding the current index size limitations of a maximum of 16 key columns and a maximum index key size of 900 bytes.</span></span> <span data-ttu-id="0c2d6-125">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] не учитывает неключевые столбцы при расчете количества ключевых столбцов индекса и размера ключа индекса.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-125">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not consider nonkey columns when calculating the number of index key columns or index key size.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0c2d6-126">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0c2d6-126">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="0c2d6-127">Неключевые столбцы можно задавать только для некластеризованных индексов.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-127">Nonkey columns can only be defined on nonclustered indexes.</span></span>  
  
-   <span data-ttu-id="0c2d6-128">Все типы данных, за исключением `text`, `ntext`, и `image` могут использоваться как неключевые столбцы.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-128">All data types except `text`, `ntext`, and `image` can be used as nonkey columns.</span></span>  
  
-   <span data-ttu-id="0c2d6-129">Вычисляемые столбцы, являющиеся детерминированными, в том числе точными или неточными, могут быть неключевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-129">Computed columns that are deterministic and either precise or imprecise can be nonkey columns.</span></span> <span data-ttu-id="0c2d6-130">Дополнительные сведения см. в разделе [Индексы вычисляемых столбцов](indexes-on-computed-columns.md).</span><span class="sxs-lookup"><span data-stu-id="0c2d6-130">For more information, see [Indexes on Computed Columns](indexes-on-computed-columns.md).</span></span>  
  
-   <span data-ttu-id="0c2d6-131">Вычисляемые столбцы, полученные на основе типов данных `image`, `ntext` и `text`, могут быть неключевыми столбцами, если тип данных этого вычисляемого столбца допустим в качестве неключевого индексного столбца.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-131">Computed columns derived from `image`, `ntext`, and `text` data types can be nonkey columns as long as the computed column data type is allowed as a nonkey index column.</span></span>  
  
-   <span data-ttu-id="0c2d6-132">Неключевые столбцы можно удалить из таблицы только после удаления из этой таблицы индекса.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-132">Nonkey columns cannot be dropped from a table unless that table's index is dropped first.</span></span>  
  
-   <span data-ttu-id="0c2d6-133">Неключевые столбцы нельзя изменять, за исключением следующих операций:</span><span class="sxs-lookup"><span data-stu-id="0c2d6-133">Nonkey columns cannot be changed, except to do the following:</span></span>  
  
    -   <span data-ttu-id="0c2d6-134">изменение поведения столбца в отношении значения NULL с NOT NULL на NULL;</span><span class="sxs-lookup"><span data-stu-id="0c2d6-134">Change the nullability of the column from NOT NULL to NULL.</span></span>  
  
    -   <span data-ttu-id="0c2d6-135">Увеличение длины столбцов типов `varchar`, `nvarchar` и `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-135">Increase the length of `varchar`, `nvarchar`, or `varbinary` columns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0c2d6-136">безопасность</span><span class="sxs-lookup"><span data-stu-id="0c2d6-136">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0c2d6-137">Permissions</span><span class="sxs-lookup"><span data-stu-id="0c2d6-137">Permissions</span></span>  
 <span data-ttu-id="0c2d6-138">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-138">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="0c2d6-139">Пользователь должен быть членом предопределенной роли сервера **sysadmin** или предопределенных ролей базы данных **db_ddladmin** и **db_owner**.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-139">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0c2d6-140">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c2d6-140">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-index-with-nonkey-columns"></a><span data-ttu-id="0c2d6-141">Создание индекса с неключевыми столбцами</span><span class="sxs-lookup"><span data-stu-id="0c2d6-141">To create an index with nonkey columns</span></span>  
  
1.  <span data-ttu-id="0c2d6-142">В обозревателе объектов щелкните знак «плюс», чтобы развернуть базу данных, содержащую таблицу, в которой необходимо создать индекс с неключевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-142">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to create an index with nonkey columns.</span></span>  
  
2.  <span data-ttu-id="0c2d6-143">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="0c2d6-143">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="0c2d6-144">Щелкните знак «плюс», чтобы развернуть таблицу, в которой необходимо создать индекс с неключевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-144">Click the plus sign to expand the table on which you want to create an index with nonkey columns.</span></span>  
  
4.  <span data-ttu-id="0c2d6-145">Щелкните правой кнопкой мыши папку **Индексы**, выберите **Создать индекс** и **Некластеризованный индекс...**</span><span class="sxs-lookup"><span data-stu-id="0c2d6-145">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="0c2d6-146">В диалоговом окне **Создание индекса** на странице **Общие** введите имя нового индекса в поле **Имя индекса** .</span><span class="sxs-lookup"><span data-stu-id="0c2d6-146">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="0c2d6-147">На вкладке **Ключевые столбцы индекса** нажмите кнопку **Добавить…** .</span><span class="sxs-lookup"><span data-stu-id="0c2d6-147">Under the **Index key columns** tab, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="0c2d6-148">В диалоговом окне **Выбор столбцов из**_table_name_ установите флажки для столбцов таблицы или столбцов, которые будут добавлены в индекс.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-148">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the index.</span></span>  
  
8.  <span data-ttu-id="0c2d6-149">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-149">Click **OK**.</span></span>  
  
9. <span data-ttu-id="0c2d6-150">На вкладке **Включенные столбцы** нажмите кнопку **Добавить…** .</span><span class="sxs-lookup"><span data-stu-id="0c2d6-150">Under the **Included columns** tab, click **Add...**.</span></span>  
  
10. <span data-ttu-id="0c2d6-151">В диалоговом окне **Выбор столбцов из**_table_name_ установите флажки для столбцов таблицы, которые будут добавлены в индекс в качестве неключевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-151">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the index as nonkey columns.</span></span>  
  
11. <span data-ttu-id="0c2d6-152">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-152">Click **OK**.</span></span>  
  
12. <span data-ttu-id="0c2d6-153">В диалоговом окне **Создание индекса** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-153">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0c2d6-154">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0c2d6-154">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-index-with-nonkey-columns"></a><span data-ttu-id="0c2d6-155">Создание индекса с неключевыми столбцами</span><span class="sxs-lookup"><span data-stu-id="0c2d6-155">To create an index with nonkey columns</span></span>  
  
1.  <span data-ttu-id="0c2d6-156">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c2d6-156">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0c2d6-157">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-157">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0c2d6-158">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="0c2d6-158">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates a nonclustered index on the Person.Address table with four included (nonkey) columns.   
    -- index key column is PostalCode and the nonkey columns are  
    -- AddressLine1, AddressLine2, City, and StateProvinceID.  
    CREATE NONCLUSTERED INDEX IX_Address_PostalCode  
    ON Person.Address (PostalCode)  
    INCLUDE (AddressLine1, AddressLine2, City, StateProvinceID);  
    GO  
    ```  
  
 <span data-ttu-id="0c2d6-159">Дополнительные сведения см. в разделе [CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0c2d6-159">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
