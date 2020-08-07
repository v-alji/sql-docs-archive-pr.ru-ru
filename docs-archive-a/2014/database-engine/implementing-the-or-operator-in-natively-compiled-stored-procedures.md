---
title: Реализация оператора OR в скомпилированных в собственном итоге хранимых процедурах | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f2528e74-2b1c-48cb-861b-c4e57b51ac35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7ed762e062cbc6831eb46784ef71fc7889850676
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734450"
---
# <a name="implementing-the-or-operator-in-natively-compiled-stored-procedures"></a><span data-ttu-id="3b5cb-102">Реализация оператора OR в скомпилированных в собственном коде хранимых процедурах</span><span class="sxs-lookup"><span data-stu-id="3b5cb-102">Implementing the OR Operator in Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="3b5cb-103">Операторы OR не поддерживаются в предикатах запросов в скомпилированных в собственном коде хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-103">OR operators are not supported in query predicates in natively compiled stored procedures.</span></span> <span data-ttu-id="3b5cb-104">Так как операторы NOT также не поддерживаются в предикатах запросов в скомпилированных в собственном коде хранимых процедурах, использование операторов OR нельзя имитировать только с помощью эквивалентных логических операторов.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-104">Because NOT operators are also not supported in query predicates in natively compiled stored procedures, the effects of OR operators cannot be simulated through the use of equivalent logical operators alone.</span></span> <span data-ttu-id="3b5cb-105">Однако результаты выполнения оператора OR можно имитировать с помощью переменных оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-105">However, the effects of an OR operator may be simulated with memory-optimized table variables.</span></span>  
  
## <a name="or-operator-in-where-clause"></a><span data-ttu-id="3b5cb-106">Оператор OR в предложении WHERE</span><span class="sxs-lookup"><span data-stu-id="3b5cb-106">OR Operator in WHERE Clause</span></span>  
 <span data-ttu-id="3b5cb-107">Если в предложении WHERE имеется оператор OR, то для имитации его поведения можно использовать следующий подход.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-107">If you have an OR operator in a WHERE clause, you can use the following approach to simulate its behavior:</span></span>  
  
1.  <span data-ttu-id="3b5cb-108">Создайте переменную оптимизированной для памяти таблицы с соответствующей схемой.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-108">Create a memory-optimized table variable with the appropriate schema.</span></span> <span data-ttu-id="3b5cb-109">Для этого требуется стандартный тип оптимизированной для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-109">This requires a predefined memory-optimized table type.</span></span>  
  
2.  <span data-ttu-id="3b5cb-110">Начиная с оператора OR верхнего уровня, разделите предложение WHERE на две части в соответствии с предикатами, соединенными оператором OR.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-110">Starting with the top level OR operator, separate the WHERE clause into two parts according to the predicates joined by the OR operator.</span></span> <span data-ttu-id="3b5cb-111">При наличии в предложении WHERE нескольких операторов OR это необходимо будет сделать несколько раз.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-111">If you have more than one OR operator in a WHERE clause, you may need to do this more than once.</span></span> <span data-ttu-id="3b5cb-112">Повторяйте этот шаг до тех пор, пока операторов OR больше не останется.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-112">Repeat this step until no OR operators remain.</span></span> <span data-ttu-id="3b5cb-113">Например, предположим, что имеется следующий предикат:</span><span class="sxs-lookup"><span data-stu-id="3b5cb-113">For example, if you have the following predicate:</span></span>  
  
    ```  
    pred1 OR (pred2 AND (pred3 OR pred4)) OR (pred5 AND pred6)  
    ```  
  
     <span data-ttu-id="3b5cb-114">После выполнения этого шага у вас должны получиться следующие предикаты:</span><span class="sxs-lookup"><span data-stu-id="3b5cb-114">After this step, you should have the following predicates:</span></span>  
  
    ```  
    pred1  
    pred5 AND pred6  
    pred2 AND pred3  
    pred2 AND pred4  
    ```  
  
3.  <span data-ttu-id="3b5cb-115">Выполните запрос с каждой из двух частей, образованных в шаге 2 в качестве предиката.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-115">Execute a query with each of the two parts found in Step 2 as the predicate.</span></span> <span data-ttu-id="3b5cb-116">Введите результат выполнения каждого запроса в переменную оптимизированной для памяти таблицы, созданной на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-116">Insert the result for each query into the memory-optimized table variable created in Step 1.</span></span>  
  
4.  <span data-ttu-id="3b5cb-117">При необходимости удалите повторения из переменной оптимизированной для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-117">If necessary, remove duplicates from the memory-optimized table variable.</span></span>  
  
5.  <span data-ttu-id="3b5cb-118">Используйте содержимое переменной оптимизированной для памяти таблицы в качестве результата запроса.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-118">Use the content of the memory-optimized table variable as the result from the query.</span></span>  
  
 <span data-ttu-id="3b5cb-119">В следующем образце используются таблицы из базы данных AdventureWorks2012, которые были обновлены для [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b5cb-119">The following sample uses tables from the AdventureWorks2012 database that were updated for [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="3b5cb-120">Чтобы скачать файлы для этого образца, перейдите по следующей странице [базы данных AdventureWorks — 2012, 2008R2 и 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span><span class="sxs-lookup"><span data-stu-id="3b5cb-120">To download the files for this sample, goto [AdventureWorks Databases - 2012, 2008R2 and 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span></span> <span data-ttu-id="3b5cb-121">Чтобы применить [!INCLUDE[hek_2](../includes/hek-2-md.md)] пример кода к AdventureWorks2012, перейдите на [пример SQL Server 2014 in-Memory OLTP](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="3b5cb-121">To apply [!INCLUDE[hek_2](../includes/hek-2-md.md)] code sample to AdventureWorks2012, go to [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="3b5cb-122">Добавьте в базу данных следующую хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-122">Add the following stored procedure to the database.</span></span> <span data-ttu-id="3b5cb-123">Мы преобразуем эту хранимую процедуру так, чтобы она компилировалась в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-123">We will convert this stored procedure to use native compilation.</span></span>  
  
```  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesOrderDetail_ondisk  
  @SalesOrderId int = 0, @SalesOrderDetailId int = 0,   
  @CarrierTrackingNumber nvarchar(25) = N'', @ProductId int = 0,   
  @minUnitPrice money = 0, @maxUnitPrice money = 0  
AS BEGIN  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_ondisk s  
  WHERE  s.SalesOrderId = @SalesOrderId  
      OR s.SalesOrderDetailId = @SalesOrderDetailId  
      OR s.CarrierTrackingNumber = @CarrierTrackingNumber  
      OR s.ProductID = @ProductId  
      OR (s.UnitPrice > @minUnitPrice AND s.UnitPrice < @maxUnitPrice)  
END  
GO  
```  
  
 <span data-ttu-id="3b5cb-124">После преобразования схема таблицы и хранимой процедуры будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-124">After conversion, the table and stored procedure schema is as follows,</span></span>  
  
```  
CREATE TYPE Sales.fuzzySearchSalesOrderDetailType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  ModifiedDate datetime2(7) not null  
  INDEX ix_fuzzySearchSalesOrderDetailType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE TYPE Sales.fuzzySearchSalesOrderDetailTempType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  recordcount int not null  
  INDEX ix_fuzzySearchSalesOrderDetailTempType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesOrderDetail_inmem  
  @SalesOrderId int = 0, @SalesOrderDetailId int = 0,   
  @CarrierTrackingNumber nvarchar(25) = N'', @ProductId int = 0,   
  @minUnitPrice money = 0, @maxUnitPrice money = 0  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'ENGLISH')  
  
  DECLARE @retValue Sales.fuzzySearchSalesOrderDetailType  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.SalesOrderId = @SalesOrderId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.SalesOrderDetailId = @SalesOrderDetailId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.CarrierTrackingNumber COLLATE Latin1_General_BIN2 = @CarrierTrackingNumber COLLATE Latin1_General_BIN2   
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.ProductID = @ProductId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE (s.UnitPrice > @minUnitPrice AND s.UnitPrice < @maxUnitPrice)  
  
  -- After the above statements, there will be duplicates inside @retValue  
  -- Delete the duplicates from @retValue  
  DECLARE @duplicates Sales.fuzzySearchSalesOrderDetailTempType  
  
  INSERT INTO @duplicates (SalesOrderId, SalesOrderDetailId, recordcount)   
  SELECT SalesOrderId, SalesOrderDetailId, COUNT(*) AS recordCount  
  FROM @retValue  
  GROUP BY SalesOrderId, SalesOrderDetailId  
  
  -- Now we have one row per pair  
  -- clear and rebuild the result set  
  DELETE FROM @retValue  
  
  INSERT INTO @retValue  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN @duplicates d ON s.SalesOrderId = d.SalesOrderId AND s.SalesOrderDetailId = d.SalesOrderDetailId  
  
  -- After this every pair of (SalesOrderId, SalesOrderDetailId) in @retValue should be unique.  
  SELECT SalesorderId, SalesOrderDetailId, ModifiedDate FROM @retValue  
END  
GO  
```  
  
## <a name="or-operator-in-join-condition"></a><span data-ttu-id="3b5cb-125">Оператор OR в условии JOIN</span><span class="sxs-lookup"><span data-stu-id="3b5cb-125">OR Operator in JOIN Condition</span></span>  
 <span data-ttu-id="3b5cb-126">Если в условии JOIN инструкции SELECT есть оператор OR, то для имитации его работы можно использовать следующий подход.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-126">If you have an OR operator in a JOIN condition of a SELECT statement, you may use the following approach to simulate its behavior.</span></span> <span data-ttu-id="3b5cb-127">Если в условии JOIN есть несколько операторов OR или имеется несколько условий JOIN с операторами OR, выполнить это действие нужно будет несколько раз.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-127">If you have more than one OR operator in a JOIN condition or you have multiple JOIN condition with OR operators, you may need to do this more than once.</span></span>  
  
 <span data-ttu-id="3b5cb-128">При наличии условий OUTER JOIN этот способ можно использовать в сочетании со способом для условий OUTER JOIN.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-128">If you have OUTER JOIN conditions, you may combine this workaround with the workaround for OUTER JOIN conditions.</span></span>  
  
1.  <span data-ttu-id="3b5cb-129">Создайте переменную оптимизированной для памяти таблицы с соответствующей схемой.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-129">Create a memory-optimized table variable with the appropriate schema.</span></span> <span data-ttu-id="3b5cb-130">Для этого требуется стандартный тип оптимизированной для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-130">This requires a predefined memory-optimized table type.</span></span>  
  
2.  <span data-ttu-id="3b5cb-131">Разделите предикат из условия JOIN на две части в соответствии с предикатами, объединяемыми оператором OR.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-131">Separate the predicate in the JOIN condition into two parts according to the predicates joined by the OR operator.</span></span> <span data-ttu-id="3b5cb-132">При наличии нескольких условий JOIN сделать это необходимо будет для каждого условия JOIN, а затем создать набор сочетаний получившихся фрагментов.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-132">If you have multiple JOIN conditions, you may need to do this for each JOIN condition and then create a set of combinations of the resulting fragments.</span></span> <span data-ttu-id="3b5cb-133">Например, если есть три условия JOIN с одним оператором OR в каждом из них, количество предикатов может составить 2x2x2=8.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-133">For example, if you have three JOIN conditions with one OR operator in each JOIN condition, you may have 2x2x2=8 predicates.</span></span>  
  
3.  <span data-ttu-id="3b5cb-134">Для каждого предиката, полученного на шаге 2, создайте запрос, который будет вставлять результат его выполнения в переменную оптимизированной для памяти таблицы, созданной на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-134">For each predicate produced by Step 2, create a query that will insert its result into the memory-optimized table variable created in Step 1.</span></span>  
  
4.  <span data-ttu-id="3b5cb-135">При необходимости удалите повторения из переменной оптимизированной для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-135">If necessary, remove duplicates from the memory-optimized table variable.</span></span>  
  
5.  <span data-ttu-id="3b5cb-136">Используйте содержимое переменной оптимизированной для памяти таблицы в качестве результата запроса.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-136">Use the content of the memory-optimized table variable as the result from the query.</span></span>  
  
 <span data-ttu-id="3b5cb-137">В следующем образце используются таблицы из базы данных AdventureWorks2012, которые были обновлены для [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b5cb-137">The following sample uses tables from the AdventureWorks2012 database that were updated for [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="3b5cb-138">Чтобы скачать файлы для этого образца, перейдите по следующей странице [базы данных AdventureWorks — 2012, 2008R2 и 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span><span class="sxs-lookup"><span data-stu-id="3b5cb-138">To download the files for this sample, goto [AdventureWorks Databases - 2012, 2008R2 and 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span></span> <span data-ttu-id="3b5cb-139">Чтобы применить [!INCLUDE[hek_2](../includes/hek-2-md.md)] пример кода к AdventureWorks2012, перейдите на [пример SQL Server 2014 in-Memory OLTP](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="3b5cb-139">To apply [!INCLUDE[hek_2](../includes/hek-2-md.md)] code sample to AdventureWorks2012, go to [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="3b5cb-140">Добавьте в базу данных следующую хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-140">Add the following stored procedure to the database.</span></span> <span data-ttu-id="3b5cb-141">Мы преобразуем эту хранимую процедуру так, чтобы она компилировалась в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-141">We will convert this stored procedure to use native compilation.</span></span> <span data-ttu-id="3b5cb-142">В этом образце используются условия INNER JOIN.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-142">This sample uses INNER JOIN conditions.</span></span>  
  
```  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesSpecialOffers_ondisk  
  @SpecialOfferId int  
AS BEGIN  
  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_ondisk s  
  JOIN Sales.SpecialOffer_onDisk offer   
    ON s.SpecialOfferID = offer.SpecialOfferID   
    OR s.ProductID IN (SELECT ProductId FROM Sales.SpecialOfferProduct sop WHERE sop.SpecialOfferID = @SpecialOfferId)  
END  
```  
  
 <span data-ttu-id="3b5cb-143">После преобразования схема таблицы и хранимой процедуры будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-143">After conversion, the table and stored procedure schema is as follows,</span></span>  
  
```  
CREATE TYPE Sales.fuzzySearchSalesSpecialOffers_Type AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  SpecialOfferId int not null,  
  ModifiedDate datetime2(7) not null  
  INDEX ix_fuzzySearchSalesSpecialOffers_Type NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE TYPE Sales.fuzzySearchSalesSpecialOffers_TempType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  SpecialOfferId int not null,  
  recordcount int null  
  INDEX ix_fuzzySearchSalesSpecialOffers_TempType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesSpecialOffers_inmem  
  @SpecialOfferId int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'ENGLISH')  
  
  DECLARE @retValue Sales.FuzzySearchSalesSpecialOffers_Type  
  
  -- Find all special offers matching the conditions  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, SpecialOfferid, ModifiedDate)  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN Sales.SpecialOffer_inmem offer   
    ON s.SpecialOfferID = offer.SpecialOfferID  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, SpecialOfferid, ModifiedDate)  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN Sales.SpecialOfferProduct_inmem sop   
    ON sop.SpecialOfferId = @SpecialOfferId AND s.ProductID = sop.ProductId  
  
  -- Now we need to remove the duplicates from @matchingSpecialOffers  
  DECLARE @duplicates Sales.fuzzySearchSalesSpecialOffers_TempType  
  
  INSERT INTO @duplicates (SalesOrderId, SalesOrderDetailId, SpecialOfferid, recordcount)  
  SELECT SalesOrderId, SalesOrderDetailId, SpecialOfferId, COUNT(*)   
  FROM @retValue  
  GROUP BY SalesOrderId, SalesOrderDetailId, SpecialOfferId  
  
  -- now there should be no duplicates within @duplicate  
  -- use @duplicate for join.  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN @duplicates offer   
    ON    s.SalesOrderId = offer.SalesOrderId   
      AND s.SalesOrderDetailId = offer.SalesOrderDetailID   
      AND s.SpecialOfferId = offer.SpecialOfferId  
END  
GO  
```  
  
## <a name="side-effects"></a><span data-ttu-id="3b5cb-144">Побочные эффекты</span><span class="sxs-lookup"><span data-stu-id="3b5cb-144">Side Effects</span></span>  
 <span data-ttu-id="3b5cb-145">При наличии в предложении WHERE или условии JOIN нескольких операторов OR количество запросов, которые необходимо выполнить для имитации поведения, может увеличиваться экспоненциально.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-145">If you have more than one OR operator in the WHERE clause or JOIN condition, the number of queries you need to execute to simulate the behavior may increase exponentially.</span></span> <span data-ttu-id="3b5cb-146">Из-за этого выполнение запросов может замедлиться или же может увеличиться объем используемой памяти из-за необходимости использовать переменные оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="3b5cb-146">This may slow down query performance and may increase memory usage due to the need to use memory-optimized table variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b5cb-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="3b5cb-147">See Also</span></span>  
 [<span data-ttu-id="3b5cb-148">Проблемы миграции, связанные с хранимыми процедурами, скомпилированными в собственном коде</span><span class="sxs-lookup"><span data-stu-id="3b5cb-148">Migration Issues for Natively Compiled Stored Procedures</span></span>](../relational-databases/in-memory-oltp/migration-issues-for-natively-compiled-stored-procedures.md)  
  
