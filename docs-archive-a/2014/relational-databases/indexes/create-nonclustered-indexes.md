---
title: Создание некластеризованных индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], nonclustered indexes
- nonclustered indexes [SQL Server], creating
- nonclustered indexes [SQL Server], UNIQUE constraint
- indexes [SQL Server], nonclustered
- nonclustered indexes [SQL Server], PRIMARY KEY constraint
ms.assetid: 9402029a-1227-46c4-93aa-c2122eb1b943
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fae0c06b1f562dc3fc518a319df1787b3384c0cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749835"
---
# <a name="create-nonclustered-indexes"></a><span data-ttu-id="2d98e-102">Создание некластеризованных индексов</span><span class="sxs-lookup"><span data-stu-id="2d98e-102">Create Nonclustered Indexes</span></span>
  <span data-ttu-id="2d98e-103">Некластеризованные индексы в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно создать с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d98e-103">You can create nonclustered indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2d98e-104">Некластеризованный индекс — это структура индекса, отделенная от данных, хранящихся в таблице, и переупорядочивающая один или несколько выделенных столбцов.</span><span class="sxs-lookup"><span data-stu-id="2d98e-104">A nonclustered index is an index structure separate from the data stored in a table that reorders one or more selected columns.</span></span> <span data-ttu-id="2d98e-105">Некластеризованные индексы часто ускоряют поиск данных по сравнению с поиском в базовой таблице. Иногда на запросы можно ответить, используя только данные из некластеризованного индекса, либо некластеризованный индекс может указать компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] на нужные строки из базовой таблицы.</span><span class="sxs-lookup"><span data-stu-id="2d98e-105">Nonclustered indexes can often help you find data more quickly than searching the underlying table; queries can sometimes be answered entirely by the data in the nonclustered index, or the nonclustered index can point the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to the rows in the underlying table.</span></span> <span data-ttu-id="2d98e-106">Обычно некластеризованные индексы создаются с целью повышения производительности часто используемых запросов, не входящих в кластеризованный индекс, либо для поиска строк таблицы, не имеющей кластеризованного индекса (которая называется кучей).</span><span class="sxs-lookup"><span data-stu-id="2d98e-106">Generally, nonclustered indexes are created to improve the performance of frequently used queries not covered by the clustered index or to locate rows in a table without a clustered index (called a heap).</span></span> <span data-ttu-id="2d98e-107">Можно создать несколько некластеризованных индексов для таблицы или индексированного представления.</span><span class="sxs-lookup"><span data-stu-id="2d98e-107">You can create multiple nonclustered indexes on a table or indexed view.</span></span>  
  
 <span data-ttu-id="2d98e-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="2d98e-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2d98e-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2d98e-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2d98e-110">Типичные реализации</span><span class="sxs-lookup"><span data-stu-id="2d98e-110">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="2d98e-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2d98e-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2d98e-112">**Для создания некластеризованного индекса используется:**</span><span class="sxs-lookup"><span data-stu-id="2d98e-112">**To create a nonclustered index, using:**</span></span>  
  
     [<span data-ttu-id="2d98e-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d98e-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2d98e-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d98e-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2d98e-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2d98e-115">Before You Begin</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="2d98e-116">Стандартные реализации</span><span class="sxs-lookup"><span data-stu-id="2d98e-116">Typical Implementations</span></span>  
 <span data-ttu-id="2d98e-117">Некластеризованные индексы реализуются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2d98e-117">Nonclustered indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="2d98e-118">**Ограничения UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="2d98e-118">**UNIQUE constraints**</span></span>  
  
     <span data-ttu-id="2d98e-119">При создании ограничения UNIQUE создается уникальный некластеризованный индекс. Он нужен, чтобы принудительно применять ограничение UNIQUE по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2d98e-119">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="2d98e-120">Если кластеризованный индекс в таблице еще не создан, то можно указать уникальный кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="2d98e-120">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span> <span data-ttu-id="2d98e-121">Дополнительные сведения см. в статье [Ограничения уникальности и проверочные ограничения](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="2d98e-121">For more information, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
-   <span data-ttu-id="2d98e-122">**Индекс, не зависящий от ограничения**</span><span class="sxs-lookup"><span data-stu-id="2d98e-122">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="2d98e-123">По умолчанию некластеризованный индекс создается в том случае, если ранее не был задан кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="2d98e-123">By default, a nonclustered index is created if clustered is not specified.</span></span> <span data-ttu-id="2d98e-124">Для таблицы может быть создано не более 999 некластеризованных индексов.</span><span class="sxs-lookup"><span data-stu-id="2d98e-124">The maximum number of nonclustered indexes that can be created per table is 999.</span></span> <span data-ttu-id="2d98e-125">В это число входят любые индексы, созданные ограничениями PRIMARY KEY или UNIQUE, но не входят XML-индексы.</span><span class="sxs-lookup"><span data-stu-id="2d98e-125">This includes any indexes created by PRIMARY KEY or UNIQUE constraints, but does not include XML indexes.</span></span>  
  
-   <span data-ttu-id="2d98e-126">**Некластеризованный индекс в индексированном представлении**</span><span class="sxs-lookup"><span data-stu-id="2d98e-126">**Nonclustered index on an indexed view**</span></span>  
  
     <span data-ttu-id="2d98e-127">Некластеризованные индексы в представлении могут создаваться только после создания в нем уникального кластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="2d98e-127">After a unique clustered index has been created on a view, nonclustered indexes can be created.</span></span> <span data-ttu-id="2d98e-128">Дополнительные сведения см. в разделе [Создание индексированных представлений](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="2d98e-128">For more information, see [Create Indexed Views](../views/views.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2d98e-129">безопасность</span><span class="sxs-lookup"><span data-stu-id="2d98e-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2d98e-130">Permissions</span><span class="sxs-lookup"><span data-stu-id="2d98e-130">Permissions</span></span>  
 <span data-ttu-id="2d98e-131">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="2d98e-131">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="2d98e-132">Пользователь должен быть членом предопределенной роли сервера **sysadmin** или предопределенных ролей базы данных **db_ddladmin** и **db_owner**.</span><span class="sxs-lookup"><span data-stu-id="2d98e-132">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2d98e-133">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d98e-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-nonclustered-index-by-using-the-table-designer"></a><span data-ttu-id="2d98e-134">Создание некластеризованного индекса с помощью конструктора таблиц</span><span class="sxs-lookup"><span data-stu-id="2d98e-134">To create a nonclustered index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="2d98e-135">В обозревателе объектов разверните базу данных, содержащую таблицу, в которой необходимо создать некластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="2d98e-135">In Object Explorer, expand the database that contains the table on which you want to create a nonclustered index.</span></span>  
  
2.  <span data-ttu-id="2d98e-136">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="2d98e-136">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="2d98e-137">Щелкните правой кнопкой мыши таблицу, в которой нужно создать некластеризованный индекс, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="2d98e-137">Right-click the table on which you want to create a nonclustered index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="2d98e-138">В меню **Конструктор таблиц** выберите пункт **Индексы/Ключи**.</span><span class="sxs-lookup"><span data-stu-id="2d98e-138">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="2d98e-139">В диалоговом окне **Индексы и ключи** нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2d98e-139">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="2d98e-140">Выберите новый индекс в текстовом поле **Выбранный первичный/уникальный ключ или индекс** .</span><span class="sxs-lookup"><span data-stu-id="2d98e-140">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
7.  <span data-ttu-id="2d98e-141">Выберите в сетке элемент **Создать как кластеризованный**и в раскрывающемся списке справа от свойства выберите значение **Нет** .</span><span class="sxs-lookup"><span data-stu-id="2d98e-141">In the grid, select **Create as Clustered**, and choose **No** from the drop-down list to the right of the property.</span></span>  
  
8.  <span data-ttu-id="2d98e-142">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2d98e-142">Click **Close**.</span></span>  
  
9. <span data-ttu-id="2d98e-143">В меню **Файл** выберите пункт **Сохранить**_имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="2d98e-143">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="to-create-a-nonclustered-index-by-using-object-explorer"></a><span data-ttu-id="2d98e-144">Создание некластеризованного индекса в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="2d98e-144">To create a nonclustered index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="2d98e-145">В обозревателе объектов разверните базу данных, содержащую таблицу, в которой необходимо создать некластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="2d98e-145">In Object Explorer, expand the database that contains the table on which you want to create a nonclustered index.</span></span>  
  
2.  <span data-ttu-id="2d98e-146">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="2d98e-146">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="2d98e-147">Разверните таблицу, для которой необходимо создать некластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="2d98e-147">Expand the table on which you want to create a nonclustered index.</span></span>  
  
4.  <span data-ttu-id="2d98e-148">Щелкните правой кнопкой мыши папку **Индексы**, выберите **Создать индекс** и **Некластеризованный индекс...**</span><span class="sxs-lookup"><span data-stu-id="2d98e-148">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="2d98e-149">В диалоговом окне **Создание индекса** на странице **Общие** введите имя нового индекса в поле **Имя индекса** .</span><span class="sxs-lookup"><span data-stu-id="2d98e-149">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="2d98e-150">В разделе **Ключевые столбцы индекса** щелкните **Добавить…** .</span><span class="sxs-lookup"><span data-stu-id="2d98e-150">Under **Index key columns**, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="2d98e-151">В диалоговом окне **Выбор столбцов из**_table_name_ установите флажки для столбцов таблицы или столбцов, которые будут добавлены к некластеризованному индексу.</span><span class="sxs-lookup"><span data-stu-id="2d98e-151">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the nonclustered index.</span></span>  
  
8.  <span data-ttu-id="2d98e-152">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2d98e-152">Click **OK**.</span></span>  
  
9. <span data-ttu-id="2d98e-153">В диалоговом окне **Создание индекса** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2d98e-153">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2d98e-154">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d98e-154">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-nonclustered-index-on-a-table"></a><span data-ttu-id="2d98e-155">Создание некластеризованного индекса для таблицы</span><span class="sxs-lookup"><span data-stu-id="2d98e-155">To create a nonclustered index on a table</span></span>  
  
1.  <span data-ttu-id="2d98e-156">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d98e-156">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2d98e-157">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2d98e-157">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2d98e-158">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2d98e-158">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named IX_ProductVendor_VendorID and delete it if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
                WHERE name = N'IX_ProductVendor_VendorID')   
        DROP INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor;   
    GO  
    -- Create a nonclustered index called IX_ProductVendor_VendorID   
    -- on the Purchasing.ProductVendor table using the BusinessEntityID column.   
    CREATE NONCLUSTERED INDEX IX_ProductVendor_VendorID   
        ON Purchasing.ProductVendor (BusinessEntityID);   
    GO  
    ```  
  
 <span data-ttu-id="2d98e-159">Дополнительные сведения см. в разделе [CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2d98e-159">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
