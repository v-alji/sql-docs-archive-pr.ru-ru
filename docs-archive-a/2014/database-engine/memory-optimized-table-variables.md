---
title: Оптимизированные для памяти табличные переменные | Документация Майкрософт
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: bd102e95-53e2-4da6-9b8b-0e4f02d286d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: bec720c53c257240ee92274a6391ebc3f17faa25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665098"
---
# <a name="memory-optimized-table-variables"></a><span data-ttu-id="273ea-102">Переменные оптимизированной для памяти таблицы</span><span class="sxs-lookup"><span data-stu-id="273ea-102">Memory-Optimized Table Variables</span></span>
  <span data-ttu-id="273ea-103">Помимо оптимизированных для памяти таблиц (которые повышают эффективность доступа к данным) и скомпилированных в собственном коде хранимых процедур (которые повышают эффективность обработки запросов и выполнения бизнес-логики) [!INCLUDE[hek_2](../includes/hek-2-md.md)] также использует третий тип объекта: оптимизированный для памяти табличный тип.</span><span class="sxs-lookup"><span data-stu-id="273ea-103">In addition to memory-optimized tables (for efficient data access) and natively compiled stored procedures (for efficient query processing and business logic execution) [!INCLUDE[hek_2](../includes/hek-2-md.md)] introduces a third kind of object: the memory-optimized table type.</span></span> <span data-ttu-id="273ea-104">Табличная переменная, созданная с использованием оптимизированного для памяти табличного типа, является оптимизированной для памяти табличной переменной.</span><span class="sxs-lookup"><span data-stu-id="273ea-104">A table variable created using a memory-optimized table type is a memory-optimized table variable.</span></span>  
  
 <span data-ttu-id="273ea-105">Оптимизированные для памяти табличные переменные обеспечивают следующие преимущества, если сравнивать их с дисковыми табличными переменными.</span><span class="sxs-lookup"><span data-stu-id="273ea-105">Memory-optimized table variables offer the following advantages when compared to disk-based table variables:</span></span>  
  
-   <span data-ttu-id="273ea-106">Переменные хранятся только в памяти.</span><span class="sxs-lookup"><span data-stu-id="273ea-106">The variables are only stored in memory.</span></span> <span data-ttu-id="273ea-107">Доступ к данным более эффективен, поскольку оптимизированный для памяти табличный тип использует такой же алгоритм и структуры данных, что и оптимизированные для памяти таблицы, особенно когда переменные используются в скомпилированных в собственном коде хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="273ea-107">Data access is more efficient because memory-optimized table type use the same memory-optimized algorithm and data structures used for memory-optimized tables, especially when the variables are used in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="273ea-108">С оптимизированными для памяти табличными переменными tempdb не используется.</span><span class="sxs-lookup"><span data-stu-id="273ea-108">With memory-optimized table variables, there is no tempdb utilization.</span></span> <span data-ttu-id="273ea-109">Табличные переменные не хранятся в базе данных tempdb и не потребляют ее ресурсы.</span><span class="sxs-lookup"><span data-stu-id="273ea-109">Table variables are not stored in tempdb and do not use any resources in tempdb.</span></span>  
  
 <span data-ttu-id="273ea-110">Типичные сценарии использования оптимизированных для памяти табличных переменных.</span><span class="sxs-lookup"><span data-stu-id="273ea-110">The typical usage scenarios for memory-optimized table variables are:</span></span>  
  
-   <span data-ttu-id="273ea-111">Хранение промежуточных результатов и создание единого результирующего набора для нескольких запросов в скомпилированных в собственном коде хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="273ea-111">Storing intermediate results and creating single result sets based on multiple queries in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="273ea-112">Передача параметров с табличными значениями в скомпилированные в собственном коде и интерпретируемые хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="273ea-112">Passing table-valued parameters into natively compiled stored procedures and interpreted stored procedures.</span></span>  
  
-   <span data-ttu-id="273ea-113">Замена находящихся на диске табличных переменных и в некоторых случаях таблиц #temp, которые являются локальными по отношению к хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="273ea-113">Replacing disk-based table variables, and in some cases #temp tables that are local to a stored procedure.</span></span> <span data-ttu-id="273ea-114">Это особенно полезно, если база данных tempdb часто используется в системе.</span><span class="sxs-lookup"><span data-stu-id="273ea-114">This is particularly useful if there is a lot of tempdb contention in the system.</span></span>  
  
-   <span data-ttu-id="273ea-115">Табличные переменные могут использоваться для имитации курсоров из скомпилированных в собственном коде хранимых процедур, что может помочь обойти ограничения контактной зоны в скомпилированных в собственном коде хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="273ea-115">Table variables can be used to simulate cursors in natively compiled stored procedures, which can help you work around surface area limitations in natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="273ea-116">Как и оптимизированные для памяти таблицы, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] создает библиотеку DLL для каждого оптимизированного для памяти табличного типа.</span><span class="sxs-lookup"><span data-stu-id="273ea-116">Like memory-optimized tables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] generates a DLL for each memory-optimized table type.</span></span> <span data-ttu-id="273ea-117">(Компиляция вызывается при создании оптимизированного для памяти табличного типа, а не при использовании для создания оптимизированных для памяти табличных переменных.) Эта библиотека DLL включает функции для доступа к индексам и получения данных из табличных переменных.</span><span class="sxs-lookup"><span data-stu-id="273ea-117">(Compilation is invoked when the memory-optimized table type is created and not when used to create memory-optimized table variables.) This DLL includes the functions for accessing indexes and retrieving data from the table variables.</span></span> <span data-ttu-id="273ea-118">При объявлении оптимизированной для памяти табличной переменной на основе табличного типа создается экземпляр структур таблицы и индекса, соответствующий табличному типу в пользовательском сеансе.</span><span class="sxs-lookup"><span data-stu-id="273ea-118">When a memory-optimized table variable is declared based on the table type, an instance of the table and index structures corresponding to the table type is created in the user session.</span></span> <span data-ttu-id="273ea-119">После этого табличную переменную можно использовать таким же образом, как и записанные на диск табличные переменные.</span><span class="sxs-lookup"><span data-stu-id="273ea-119">The table variable can then be used in the same way as disk-based table variables.</span></span> <span data-ttu-id="273ea-120">Можно вставлять, обновлять и удалять строки в табличной переменной, а также использовать переменные в запросах [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="273ea-120">You can insert, update, and delete rows in the table variable, and you can use the variables in [!INCLUDE[tsql](../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="273ea-121">Кроме того, можно передавать переменные, скомпилированные в собственном коде, и интерпретированные хранимые процедуры в качестве параметров с табличными значениями (TVP).</span><span class="sxs-lookup"><span data-stu-id="273ea-121">You can also pass the variables into natively compiled and interpreted stored procedures, as table-valued parameters (TVP).</span></span>  
  
 <span data-ttu-id="273ea-122">В следующем примере показан оптимизированный для памяти табличный тип из образца выполняющейся в памяти OLTP на основе AdventureWorks ([пример SQL Server 2014 в памяти OLTP](https://msftdbprodsamples.codeplex.com/releases/view/114491)).</span><span class="sxs-lookup"><span data-stu-id="273ea-122">The following sample shows a memory-optimized table type from the AdventureWorks-based In-Memory OLTP sample ([SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491)).</span></span>  
  
```sql
CREATE TYPE Sales.SalesOrderDetailType_inmem
   AS TABLE
(
   OrderQty         smallint   NOT NULL,
   ProductID        int        NOT NULL,

   SpecialOfferID   int        NOT NULL
      INDEX  IX_SpecialOfferID  NONCLUSTERED,

   LocalID          int        NOT NULL,

   INDEX IX_ProductID HASH (ProductID)
      WITH ( BUCKET_COUNT = 8 )
)
WITH ( MEMORY_OPTIMIZED = ON );
```  
  
 <span data-ttu-id="273ea-123">Пример показывает, что синтаксис оптимизированных для памяти табличных типов похож на дисковые табличные типы, за исключением следующих случаев.</span><span class="sxs-lookup"><span data-stu-id="273ea-123">The sample shows that the syntax of memory-optimized table types is similar to disk-based table types, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="273ea-124">`MEMORY_OPTIMIZED=ON` указывает, что табличный тип является оптимизированным для памяти.</span><span class="sxs-lookup"><span data-stu-id="273ea-124">`MEMORY_OPTIMIZED=ON` indicates that the table type is memory-optimized.</span></span>  
  
-   <span data-ttu-id="273ea-125">Тип должен иметь по крайней мере один индекс.</span><span class="sxs-lookup"><span data-stu-id="273ea-125">The type must have at least one index.</span></span> <span data-ttu-id="273ea-126">Как и в случае с оптимизированными для памяти таблицами, можно использовать хэш-индексы и некластеризованные индексы.</span><span class="sxs-lookup"><span data-stu-id="273ea-126">As with memory-optimized tables, you can use hash and nonclustered indexes.</span></span>  
  
     <span data-ttu-id="273ea-127">Для хэш-индекса число контейнеров должно быть примерно в два раза больше числа ожидаемых уникальных ключей индекса.</span><span class="sxs-lookup"><span data-stu-id="273ea-127">For a hash index, the bucket count should be about one to two times the number of expected unique index keys.</span></span> <span data-ttu-id="273ea-128">Дополнительные сведения см. в разделе [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="273ea-128">For more information, see [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="273ea-129">Тип данных и ограничения для оптимизированных для памяти таблиц также применяются к оптимизированным для памяти табличным типам.</span><span class="sxs-lookup"><span data-stu-id="273ea-129">The data type and constraint restrictions on memory-optimized tables also apply to memory-optimized table types.</span></span> <span data-ttu-id="273ea-130">Например, ограничения по умолчанию в [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] поддерживаются, а ограничения CHECK — нет.</span><span class="sxs-lookup"><span data-stu-id="273ea-130">For example, in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] default constraints are supported, but check constraints are not.</span></span>  
  
 <span data-ttu-id="273ea-131">Как и оптимизированные для памяти таблицы, оптимизированные для памяти табличные</span><span class="sxs-lookup"><span data-stu-id="273ea-131">Like memory-optimized tables, memory-optimized table variables,</span></span>  
  
-   <span data-ttu-id="273ea-132">Не поддерживают параллельные планы.</span><span class="sxs-lookup"><span data-stu-id="273ea-132">Do not support parallel plans.</span></span>  
  
-   <span data-ttu-id="273ea-133">Должна помещаться в памяти и не использует дисковые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="273ea-133">Must fit in memory and do not use disk resources.</span></span>  
  
 <span data-ttu-id="273ea-134">Записанные на диск табличные переменные существуют в tempdb.</span><span class="sxs-lookup"><span data-stu-id="273ea-134">Disk-based table variables exist in tempdb.</span></span> <span data-ttu-id="273ea-135">Оптимизированные для памяти табличные переменные существуют в пользовательской базе данных, однако они не используют хранение и не восстанавливаются.</span><span class="sxs-lookup"><span data-stu-id="273ea-135">Memory-optimized table variables exist in the user database (but they do not consume storage and are not recovered).</span></span>  
  
 <span data-ttu-id="273ea-136">Нельзя создать переменную оптимизированной для памяти таблицы с помощью встроенного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="273ea-136">You cannot create a memory-optimized table variable using in-line syntax.</span></span> <span data-ttu-id="273ea-137">В отличие от дисковых табличных переменных сначала необходимо создать тип.</span><span class="sxs-lookup"><span data-stu-id="273ea-137">Unlike disk-based table variables, you must create a type first.</span></span>  
  
## <a name="table-valued-parameters"></a><span data-ttu-id="273ea-138">Параметры, возвращающие табличные значения</span><span class="sxs-lookup"><span data-stu-id="273ea-138">Table-Valued Parameters</span></span>  
 <span data-ttu-id="273ea-139">В следующем примере скрипта объявляется табличная переменная в качестве оптимизированного для памяти табличного типа `Sales.SalesOrderDetailType_inmem`, выполняется вставка трех строк в переменную и передача переменной в качестве возвращающего табличное значение параметра в `Sales.usp_InsertSalesOrder_inmem`.</span><span class="sxs-lookup"><span data-stu-id="273ea-139">The following sample script shows the declaration of a table variable as the memory-optimized table type `Sales.SalesOrderDetailType_inmem`, the insert of three rows into the variable, and passing the variable as a TVP into `Sales.usp_InsertSalesOrder_inmem`.</span></span>  
  
```sql  
DECLARE @od Sales.SalesOrderDetailType_inmem,  
  @SalesOrderID uniqueidentifier,  
  @DueDate datetime2 = SYSDATETIME()  
  
INSERT @od (LocalID, ProductID, OrderQty, SpecialOfferID) VALUES  
  (1, 888, 2, 1),  
  (2, 450, 13, 1),  
  (3, 841, 1, 1)  
  
EXEC Sales.usp_InsertSalesOrder_inmem  
  @SalesOrderID = @SalesOrderID,  
  @DueDate = @DueDate,  
 @OnlineOrderFlag = 1,  
  @SalesOrderDetails = @od  
```  
  
 <span data-ttu-id="273ea-140">Оптимизированные для памяти табличные типы можно использовать в качестве параметров с табличными значениями хранимых процедур; клиенты могут обращаться к ним по ссылке так же, как и к записанным на диск табличным типам и TVP.</span><span class="sxs-lookup"><span data-stu-id="273ea-140">Memory-optimized table types can be used as the type for stored procedure table-valued parameters (TVPs) and can be referenced by clients exactly the same as disk-based table types and TVPs.</span></span> <span data-ttu-id="273ea-141">Таким образом, вызов хранимых процедур с оптимизированными для памяти, возвращающими табличное значение параметрами и компилируемых в собственном коде хранимых процедур работает так же, как и вызов интерпретируемых хранимых процедур с записанными на диск, возвращающими табличное значение параметрами.</span><span class="sxs-lookup"><span data-stu-id="273ea-141">Therefore, the invocation of stored procedures with memory-optimized TVPs, and natively compiled stored procedures works exactly the same as the invocation of interpreted stored procedures with disk-based TVPs.</span></span>  
  
## <a name="temp-table-replacement"></a><span data-ttu-id="273ea-142">Замена таблицы #temp</span><span class="sxs-lookup"><span data-stu-id="273ea-142">#temp Table Replacement</span></span>  
 <span data-ttu-id="273ea-143">В следующем примере показаны оптимизированные для памяти табличные типы и табличные переменные в качестве замены таблиц #temp, которые являются локальными по отношению к хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="273ea-143">The following sample shows memory-optimized table types and table variables as a replacement for #temp tables that are local to a stored procedure.</span></span>  
  
```sql  
-- Using SQL procedure and temp table  
CREATE TABLE #tempTable (c INT NOT NULL PRIMARY KEY NONCLUSTERED)  
  
CREATE PROCEDURE sqlProc  
AS  
BEGIN  
  TRUNCATE TABLE #tempTable  
  
  INSERT #tempTable VALUES (1)  
  INSERT #tempTable VALUES (2)  
  INSERT #tempTable VALUES (3)  
  SELECT * FROM #tempTable  
END  
GO  
  
-- Using natively compiled stored procedure and table variable  
CREATE TYPE TT AS TABLE (c INT NOT NULL PRIMARY KEY NONCLUSTERED)  
GO  
  
CREATE PROCEDURE NCSPProc  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
  DECLARE @tableVariable TT  
  INSERT @tableVariable VALUES (1)  
  INSERT @tableVariable VALUES (2)  
  INSERT @tableVariable VALUES (3)  
  SELECT c FROM @tableVariable  
END  
GO  
```  
  
## <a name="creating-a-single-result-set"></a><span data-ttu-id="273ea-144">Создание одного результирующего набора</span><span class="sxs-lookup"><span data-stu-id="273ea-144">Creating a Single Result Set</span></span>  
 <span data-ttu-id="273ea-145">В следующем примере показано, как сохранить промежуточные результаты и создать единый результирующий набор для нескольких запросов в компилируемых в собственном коде хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="273ea-145">The following sample shows how to store intermediate results and create single result sets based on multiple queries in natively compiled stored procedures.</span></span> <span data-ttu-id="273ea-146">В примере вычисляется соединение `SELECT c1 FROM dbo.t1 UNION SELECT c1 FROM dbo.t2`.</span><span class="sxs-lookup"><span data-stu-id="273ea-146">The sample is computing the union `SELECT c1 FROM dbo.t1 UNION SELECT c1 FROM dbo.t2`.</span></span>  
  
```sql  
CREATE DATABASE hk  
GO  
ALTER DATABASE hk ADD FILEGROUP hk_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE hk ADD FILE( NAME = 'hk_mod' , FILENAME = 'c:\data\hk_mod') TO FILEGROUP hk_mod;  
  
USE hk  
GO  
  
CREATE TYPE tab1 AS TABLE (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON)  
  
CREATE TABLE dbo.t1 (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
CREATE TABLE dbo.t2 (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
  
INSERT INTO dbo.t1 VALUES (1), (2)  
INSERT INTO dbo.t2 VALUES (3), (4)  
GO  
  
CREATE PROCEDURE dbo.p1  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
  AS  
  BEGIN ATOMIC WITH ( TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english' )  
  
    DECLARE @t dbo.tab1  
    INSERT @t (c1)  
    SELECT c1 FROM dbo.t1;  
  
    INSERT @t (c1)  
    SELECT c1 FROM dbo.t2;  
  
    SELECT c1 FROM @t;  
  END  
GO  
  
EXEC dbo.p1  
GO  
```  
  
## <a name="memory-consumption-for-table-variables"></a><span data-ttu-id="273ea-147">Потребление памяти для табличных переменных</span><span class="sxs-lookup"><span data-stu-id="273ea-147">Memory Consumption for Table Variables</span></span>  
 <span data-ttu-id="273ea-148">Потребление памяти для табличных переменных такое же, как для таблиц, оптимизированных для памяти, за исключением некластеризованных индексов.</span><span class="sxs-lookup"><span data-stu-id="273ea-148">Memory consumption for table variables is similar to memory-optimized tables, with the exception of nonclustered indexes.</span></span> <span data-ttu-id="273ea-149">При вставке большого количества строк в переменные таблиц, оптимизированных для памяти, с некластеризованными индексами, если ключи индексов при этом большие, переменные этих таблиц занимают непропорционально большое количество памяти.</span><span class="sxs-lookup"><span data-stu-id="273ea-149">If you insert a lot of rows into memory-optimized table variables with nonclustered indexes and if the index keys are large, these table variables will use a disproportionate amount of memory.</span></span> <span data-ttu-id="273ea-150">Некластеризованные индексы для больших табличных переменных требуют пропорционально больше памяти, необходимой при одинаковом количестве строк, вставляемых в таблицу (больше памяти для страниц индекса), чем некластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="273ea-150">Nonclustered indexes on large table variables require proportionately more memory than a nonclustered index would require for the same number of rows inserted into a table (more memory in the index pages).</span></span>  
  
 <span data-ttu-id="273ea-151">Память для табличных переменных состоит из пула ресурсов регулятора ресурсов базы данных.</span><span class="sxs-lookup"><span data-stu-id="273ea-151">Memory for table variables comes from the database's Resource Governor resource pool.</span></span>  
  
 <span data-ttu-id="273ea-152">В отличие от оптимизированных для памяти таблиц, память, потребляемая табличными переменными (включая удаленные строки), освобождается, когда табличная переменная покидает область действия.</span><span class="sxs-lookup"><span data-stu-id="273ea-152">Unlike memory-optimized tables, the memory consumed (including deleted rows) by table variables is freed when the table variable goes out of scope.</span></span>  
  
 <span data-ttu-id="273ea-153">Память учитывается как часть одного потребителя памяти PGPOOL базы данных.</span><span class="sxs-lookup"><span data-stu-id="273ea-153">Memory is accounted for as part of the single PGPOOL memory consumer of the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="273ea-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="273ea-154">See Also</span></span>  
 [<span data-ttu-id="273ea-155">Поддержка Transact-SQL для выполняющейся в памяти OLTP</span><span class="sxs-lookup"><span data-stu-id="273ea-155">Transact-SQL Support for In-Memory OLTP</span></span>](../relational-databases/in-memory-oltp/transact-sql-support-for-in-memory-oltp.md)  
  
  
