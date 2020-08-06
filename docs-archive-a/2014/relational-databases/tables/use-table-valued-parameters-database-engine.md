---
title: Использование параметров, возвращающих табличные значения (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- DECLARE
- CREATE TYPE
helpviewer_keywords:
- table-valued parameters
- table-valued parameters, about table-valued parameters
- parameters [SQL Server], table-valued
- TVP See table-valued parameters
ms.assetid: 5e95a382-1e01-4c74-81f5-055612c2ad99
author: stevestein
ms.author: sstein
ms.openlocfilehash: fa7013fddc6b2ce12ad9ad0f9fcb511d93915e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664080"
---
# <a name="use-table-valued-parameters-database-engine"></a><span data-ttu-id="5572f-102">Использование параметров, возвращающих табличные значения (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="5572f-102">Use Table-Valued Parameters (Database Engine)</span></span>
  <span data-ttu-id="5572f-103">Возвращающие табличные значения параметры объявляются с помощью определяемых пользователем табличных типов.</span><span class="sxs-lookup"><span data-stu-id="5572f-103">Table-valued parameters are declared by using user-defined table types.</span></span> <span data-ttu-id="5572f-104">Возвращающие табличные значения параметры можно использовать, чтобы отправить несколько строк данных в инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] или в процедуру, например хранимую процедуру или функцию, не создавая при этом временной таблицы или большого количества параметров.</span><span class="sxs-lookup"><span data-stu-id="5572f-104">You can use table-valued parameters to send multiple rows of data to a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a routine, such as a stored procedure or function, without creating a temporary table or many parameters.</span></span>  
  
 <span data-ttu-id="5572f-105">Возвращающие табличные значения параметры похожи на массивы параметров в OLE DB и ODBC, но они обеспечивают большую гибкость и больше интегрированы с [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5572f-105">Table-valued parameters are like parameter arrays in OLE DB and ODBC, but offer more flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5572f-106">Преимуществом возвращающих табличные значения параметров также является возможность участия в операциях, основанных на наборах.</span><span class="sxs-lookup"><span data-stu-id="5572f-106">Table-valued parameters also have the benefit of being able to participate in set-based operations.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="5572f-107">передает возвращающие табличные значения параметры подпрограммам по ссылке, чтобы избежать создания копий входных данных.</span><span class="sxs-lookup"><span data-stu-id="5572f-107">passes table-valued parameters to routines by reference to avoid making a copy of the input data.</span></span> <span data-ttu-id="5572f-108">Можно создавать и выполнять процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)] с возвращающими табличные значения параметрами и вызывать их из кода [!INCLUDE[tsql](../../includes/tsql-md.md)], управляемых и собственных клиентов на любом управляемом языке.</span><span class="sxs-lookup"><span data-stu-id="5572f-108">You can create and execute [!INCLUDE[tsql](../../includes/tsql-md.md)] routines with table-valued parameters, and call them from [!INCLUDE[tsql](../../includes/tsql-md.md)] code, managed and native clients in any managed language.</span></span>  
  
 <span data-ttu-id="5572f-109">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="5572f-109">**In This Topic:**</span></span>  
  
 [<span data-ttu-id="5572f-110">Преимущества</span><span class="sxs-lookup"><span data-stu-id="5572f-110">Benefits</span></span>](#Benefits)  
  
 [<span data-ttu-id="5572f-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="5572f-111">Restrictions</span></span>](#Restrictions)  
  
 [<span data-ttu-id="5572f-112">Возвращающие табличные значения параметры и Операции BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="5572f-112">Table-Valued Parameters vs. BULK INSERT Operations</span></span>](#BulkInsert)  
  
 [<span data-ttu-id="5572f-113">Пример</span><span class="sxs-lookup"><span data-stu-id="5572f-113">Example</span></span>](#Example)  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="5572f-114">Преимущества</span><span class="sxs-lookup"><span data-stu-id="5572f-114">Benefits</span></span>  
 <span data-ttu-id="5572f-115">Область действия возвращающего табличное значение параметра такая же, как и у других параметров, — хранимая процедура, функция или динамический текст [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5572f-115">A table-valued parameter is scoped to the stored procedure, function, or dynamic [!INCLUDE[tsql](../../includes/tsql-md.md)] text, exactly like other parameters.</span></span> <span data-ttu-id="5572f-116">Аналогично область действия у переменной типа table точно такая же, как и у любой другой переменной, созданной с помощью инструкции DECLARE.</span><span class="sxs-lookup"><span data-stu-id="5572f-116">Similarly, a variable of table type has scope like any other local variable that is created by using a DECLARE statement.</span></span> <span data-ttu-id="5572f-117">Возвращающие табличные значения переменные можно объявлять в динамических инструкциях [!INCLUDE[tsql](../../includes/tsql-md.md)], а затем передавать эти переменные как возвращающие табличные значения параметры хранимым процедурам и функциям.</span><span class="sxs-lookup"><span data-stu-id="5572f-117">You can declare table-valued variables within dynamic [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and pass these variables as table-valued parameters to stored procedures and functions.</span></span>  
  
 <span data-ttu-id="5572f-118">Возвращающие табличные значения параметры обеспечивают большую гибкость и в некоторых случаях более высокую производительность, чем временные таблицы или другие методы передачи списка параметров.</span><span class="sxs-lookup"><span data-stu-id="5572f-118">Table-valued parameters offer more flexibility and in some cases better performance than temporary tables or other ways to pass a list of parameters.</span></span> <span data-ttu-id="5572f-119">Возвращающие табличные значения параметры имеют следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="5572f-119">Table-valued parameters offer the following benefits:</span></span>  
  
-   <span data-ttu-id="5572f-120">Не запрашивают блокировки для первичного заполнения данными от клиента.</span><span class="sxs-lookup"><span data-stu-id="5572f-120">Do not acquire locks for the initial population of data from a client.</span></span>  
  
-   <span data-ttu-id="5572f-121">Предоставляют простую модель программирования.</span><span class="sxs-lookup"><span data-stu-id="5572f-121">Provide a simple programming model.</span></span>  
  
-   <span data-ttu-id="5572f-122">Позволяют включать в одиночную процедуру сложную бизнес-логику.</span><span class="sxs-lookup"><span data-stu-id="5572f-122">Enable you to include complex business logic in a single routine.</span></span>  
  
-   <span data-ttu-id="5572f-123">Сокращают количество циклов приема-передачи с сервером.</span><span class="sxs-lookup"><span data-stu-id="5572f-123">Reduce round trips to the server.</span></span>  
  
-   <span data-ttu-id="5572f-124">Могут иметь структуру таблицы с другим количеством элементов.</span><span class="sxs-lookup"><span data-stu-id="5572f-124">Can have a table structure of different cardinality.</span></span>  
  
-   <span data-ttu-id="5572f-125">Строго типизированы.</span><span class="sxs-lookup"><span data-stu-id="5572f-125">Are strongly typed.</span></span>  
  
-   <span data-ttu-id="5572f-126">Позволяют клиенту указать порядок сортировки и уникальные ключи.</span><span class="sxs-lookup"><span data-stu-id="5572f-126">Enable the client to specify sort order and unique keys.</span></span>  
  
-   <span data-ttu-id="5572f-127">Кэшируются как временная таблица при использовании в хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="5572f-127">Are cached like a temp table when used in a stored procedure.</span></span> <span data-ttu-id="5572f-128">Начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], возвращающие табличное значение параметры также кэшируется для параметризированных запросов.</span><span class="sxs-lookup"><span data-stu-id="5572f-128">Starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], table-valued parameters are also cached for parameterized queries.</span></span>  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5572f-129">Ограничения</span><span class="sxs-lookup"><span data-stu-id="5572f-129">Restrictions</span></span>  
 <span data-ttu-id="5572f-130">Возвращающие табличные значения параметры имеют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="5572f-130">Table-valued parameters have the following restrictions:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5572f-131">не ведет статистику столбцов возвращающих табличные значения параметров.</span><span class="sxs-lookup"><span data-stu-id="5572f-131">does not maintain statistics on columns of table-valued parameters.</span></span>  
  
-   <span data-ttu-id="5572f-132">Возвращающие табличные значения параметры должны передаваться процедурам [!INCLUDE[tsql](../../includes/tsql-md.md)] как входные параметры типа READONLY.</span><span class="sxs-lookup"><span data-stu-id="5572f-132">Table-valued parameters must be passed as input READONLY parameters to [!INCLUDE[tsql](../../includes/tsql-md.md)] routines.</span></span> <span data-ttu-id="5572f-133">Над возвращающими табличные значения параметрами, находящимися в теле процедуры, нельзя выполнять операции DML, такие как UPDATE, DELETE или INSERT.</span><span class="sxs-lookup"><span data-stu-id="5572f-133">You cannot perform DML operations such as UPDATE, DELETE, or INSERT on a table-valued parameter in the body of a routine.</span></span>  
  
-   <span data-ttu-id="5572f-134">Возвращающий табличное значение параметр не может быть использован в качестве цели для инструкции SELECT INTO или INSERT EXEC.</span><span class="sxs-lookup"><span data-stu-id="5572f-134">You cannot use a table-valued parameter as target of a SELECT INTO or INSERT EXEC statement.</span></span> <span data-ttu-id="5572f-135">Возвращающий табличное значение параметр может присутствовать в предложении FROM инструкции SELECT INTO, в строке или хранимой процедуре INSERT EXEC.</span><span class="sxs-lookup"><span data-stu-id="5572f-135">A table-valued parameter can be in the FROM clause of SELECT INTO or in the INSERT EXEC string or stored procedure.</span></span>  
  
##  <a name="table-valued-parameters-vs-bulk-insert-operations"></a><a name="BulkInsert"></a><span data-ttu-id="5572f-136">Возвращающие табличные значения параметры и операции BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="5572f-136">Table-Valued Parameters vs. BULK INSERT Operations</span></span>  
 <span data-ttu-id="5572f-137">Использование возвращающих табличные значения параметров похоже на другие способы использования переменных, основанных на наборах. Однако применение возвращающих табличные значения параметров при работе с большими наборами данных часто позволяет добиться увеличения производительности.</span><span class="sxs-lookup"><span data-stu-id="5572f-137">Using table-valued parameters is comparable to other ways of using set-based variables; however, using table-valued parameters frequently can be faster for large data sets.</span></span> <span data-ttu-id="5572f-138">По сравнению с массовыми операциями, имеющими большие начальные затраты, возвращающие табличные значения параметры показывают хорошую производительность при вставке менее 1000 строк.</span><span class="sxs-lookup"><span data-stu-id="5572f-138">Compared to bulk operations that have a greater startup cost than table-valued parameters, table-valued parameters perform well for inserting less than 1000 rows.</span></span>  
  
 <span data-ttu-id="5572f-139">Возвращающие табличные значения параметры, используемые повторно, могут использовать кэширование временных таблиц.</span><span class="sxs-lookup"><span data-stu-id="5572f-139">Table-valued parameters that are reused benefit from temporary table caching.</span></span> <span data-ttu-id="5572f-140">Это кэширование таблиц позволяет обеспечить лучшую масштабируемость, чем в эквивалентных операциях BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="5572f-140">This table caching enables better scalability than equivalent BULK INSERT operations.</span></span> <span data-ttu-id="5572f-141">С помощью маленьких операций вставки строк можно добиться небольшого увеличения производительности, применяя списки параметров или пакетные инструкции вместо операций BULK INSERT или возвращающих табличные значения параметров.</span><span class="sxs-lookup"><span data-stu-id="5572f-141">By using small row-insert operations a small performance benefit might be gained by using parameter lists or batched statements instead of BULK INSERT operations or table-valued parameters.</span></span> <span data-ttu-id="5572f-142">Однако эти методы сложнее программировать, а производительность быстро падает при увеличении количества строк.</span><span class="sxs-lookup"><span data-stu-id="5572f-142">However, these methods are less convenient to program, and performance decreases quickly as rows increase.</span></span>  
  
 <span data-ttu-id="5572f-143">Возвращающие табличные значения параметры работают также хорошо или даже лучше, чем эквивалентная реализация массива параметров.</span><span class="sxs-lookup"><span data-stu-id="5572f-143">Table-valued parameters perform equally well or better than an equivalent parameter array implementation.</span></span>  
  
##  <a name="example"></a><a name="Example"></a> <span data-ttu-id="5572f-144">Пример</span><span class="sxs-lookup"><span data-stu-id="5572f-144">Example</span></span>  
 <span data-ttu-id="5572f-145">В следующем примере используется язык [!INCLUDE[tsql](../../includes/tsql-md.md)] и показывается, как создать тип возвращающего табличное значение параметра, объявить ссылающуюся на него переменную, заполнить список параметров, а затем передать значения хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="5572f-145">The following example uses [!INCLUDE[tsql](../../includes/tsql-md.md)] and shows you how to create a table-valued parameter type, declare a variable to reference it, fill the parameter list, and then pass the values to a stored procedure.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
/* Create a table type. */  
CREATE TYPE LocationTableType AS TABLE   
( LocationName VARCHAR(50)  
, CostRate INT );  
GO  
  
/* Create a procedure to receive data for the table-valued parameter. */  
CREATE PROCEDURE dbo. usp_InsertProductionLocation  
    @TVP LocationTableType READONLY  
    AS   
    SET NOCOUNT ON  
    INSERT INTO AdventureWorks2012.Production.Location  
           (Name  
           ,CostRate  
           ,Availability  
           ,ModifiedDate)  
        SELECT *, 0, GETDATE()  
        FROM  @TVP;  
        GO  
  
/* Declare a variable that references the type. */  
DECLARE @LocationTVP AS LocationTableType;  
  
/* Add data to the table variable. */  
INSERT INTO @LocationTVP (LocationName, CostRate)  
    SELECT Name, 0.00  
    FROM AdventureWorks2012.Person.StateProvince;  
  
/* Pass the table variable data to a stored procedure. */  
EXEC usp_InsertProductionLocation @LocationTVP;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="5572f-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="5572f-146">See Also</span></span>  
 <span data-ttu-id="5572f-147">[CREATE TYPE (Transact-SQL)](/sql/t-sql/statements/create-type-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5572f-147">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) </span></span>  
 <span data-ttu-id="5572f-148">[DECLARE @local_variable (Transact-SQL)](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5572f-148">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="5572f-149">[sys. types &#40;&#41;Transact-SQL](/sql/relational-databases/system-catalog-views/sys-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5572f-149">[sys.types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-types-transact-sql) </span></span>  
 <span data-ttu-id="5572f-150">[sys. parameters &#40;&#41;Transact-SQL](/sql/relational-databases/system-catalog-views/sys-parameters-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5572f-150">[sys.parameters &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameters-transact-sql) </span></span>  
 <span data-ttu-id="5572f-151">[sys. parameter_type_usages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameter-type-usages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5572f-151">[sys.parameter_type_usages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameter-type-usages-transact-sql) </span></span>  
 <span data-ttu-id="5572f-152">[CREATE PROCEDURE (Transact-SQL)](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5572f-152">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 [<span data-ttu-id="5572f-153">CREATE FUNCTION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5572f-153">CREATE FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-function-transact-sql)  
  
  
