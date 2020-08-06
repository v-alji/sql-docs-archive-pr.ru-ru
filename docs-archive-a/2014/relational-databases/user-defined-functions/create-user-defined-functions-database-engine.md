---
title: Создание пользовательских функций (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- SCHEMABINDING clause
- schema-bound functions [SQL Server]
- user-defined functions [SQL Server], creating
- CREATE FUNCTION statement
- valid statements [SQL Server]
ms.assetid: f0d5dd10-73fd-4e05-9177-07f56552bdf7
author: rothja
ms.author: jroth
ms.openlocfilehash: 790fa1b969f933890e050311173fcde3f12c37ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668128"
---
# <a name="create-user-defined-functions-database-engine"></a><span data-ttu-id="ad558-102">Создание определяемых пользователем функций (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="ad558-102">Create User-defined Functions (Database Engine)</span></span>
  <span data-ttu-id="ad558-103">В этом разделе описывается создание определяемой пользователем функции в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad558-103">This topic describes how to create a user-defined function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ad558-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="ad558-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ad558-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="ad558-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ad558-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ad558-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ad558-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ad558-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ad558-108">**Создание определяемой пользователем функции:**</span><span class="sxs-lookup"><span data-stu-id="ad558-108">**To create a user-defined function:**</span></span>  
  
     [<span data-ttu-id="ad558-109">Создание скалярной функции</span><span class="sxs-lookup"><span data-stu-id="ad558-109">Create a Scalar Function</span></span>](#Scalar)  
  
     [<span data-ttu-id="ad558-110">Создание функции, возвращающей табличное значение</span><span class="sxs-lookup"><span data-stu-id="ad558-110">Create a Table-valued Function</span></span>](#TVF)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ad558-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ad558-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ad558-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ad558-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ad558-113">Определяемые пользователем функции не могут выполнять действия, изменяющие состояние базы данных.</span><span class="sxs-lookup"><span data-stu-id="ad558-113">User-defined functions cannot be used to perform actions that modify the database state.</span></span>  
  
-   <span data-ttu-id="ad558-114">Определяемые пользователем функции не могут содержать предложение OUTPUT INTO, целью которого является таблица.</span><span class="sxs-lookup"><span data-stu-id="ad558-114">User-defined functions cannot contain an OUTPUT INTO clause that has a table as its target.</span></span>  
  
-   <span data-ttu-id="ad558-115">Определяемые пользователем функции не могут возвращать несколько результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="ad558-115">User-defined functions can not return multiple result sets.</span></span> <span data-ttu-id="ad558-116">Используйте хранимую процедуру, если нужно возвращать несколько результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="ad558-116">Use a stored procedure if you need to return multiple result sets.</span></span>  
  
-   <span data-ttu-id="ad558-117">Обработка ошибок в функциях, определяемых пользователем, ограниченна.</span><span class="sxs-lookup"><span data-stu-id="ad558-117">Error handling is restricted in a user-defined function.</span></span> <span data-ttu-id="ad558-118">Определяемая пользователем функция не поддерживает TRY... CATCH @ERROR или RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="ad558-118">A UDF does not support TRY...CATCH, @ERROR or RAISERROR.</span></span>  
  
-   <span data-ttu-id="ad558-119">Определяемые пользователем функции не могут вызывать хранимую процедуру, но могут вызывать расширенную хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="ad558-119">User-defined functions cannot call a stored procedure, but can call an extended stored procedure.</span></span>  
  
-   <span data-ttu-id="ad558-120">Определяемые пользователем функции не могут использовать динамический SQL и временные таблицы.</span><span class="sxs-lookup"><span data-stu-id="ad558-120">User-defined functions cannot make use of dynamic SQL or temp tables.</span></span> <span data-ttu-id="ad558-121">Табличные переменные разрешены к использованию.</span><span class="sxs-lookup"><span data-stu-id="ad558-121">Table variables are allowed.</span></span>  
  
-   <span data-ttu-id="ad558-122">Инструкцию SET нельзя использовать в определяемых пользователем функциях.</span><span class="sxs-lookup"><span data-stu-id="ad558-122">SET statements are not allowed in a user-defined function.</span></span>  
  
-   <span data-ttu-id="ad558-123">Предложение FOR XML не допускается к использованию.</span><span class="sxs-lookup"><span data-stu-id="ad558-123">The FOR XML clause is not allowed</span></span>  
  
-   <span data-ttu-id="ad558-124">Определяемые пользователем функции могут быть вложенными, то есть из одной функции может быть вызвана другая.</span><span class="sxs-lookup"><span data-stu-id="ad558-124">User-defined functions can be nested; that is, one user-defined function can call another.</span></span> <span data-ttu-id="ad558-125">Уровень вложенности увеличивается на единицу каждый раз, когда начинается выполнение вызванной функции и уменьшается на единицу, когда ее выполнение завершается.</span><span class="sxs-lookup"><span data-stu-id="ad558-125">The nesting level is incremented when the called function starts execution, and decremented when the called function finishes execution.</span></span> <span data-ttu-id="ad558-126">Вложенность определяемых пользователем функций не может превышать 32 уровней.</span><span class="sxs-lookup"><span data-stu-id="ad558-126">User-defined functions can be nested up to 32 levels.</span></span> <span data-ttu-id="ad558-127">Превышение максимального уровня вложенности приводит к ошибке выполнения для всей цепочки вызываемых функций.</span><span class="sxs-lookup"><span data-stu-id="ad558-127">Exceeding the maximum levels of nesting causes the whole calling function chain to fail.</span></span> <span data-ttu-id="ad558-128">Каждый вызов управляемого кода из определяемой пользователем функции Transact-SQL считается одним уровнем вложенности из 32 возможных.</span><span class="sxs-lookup"><span data-stu-id="ad558-128">Any reference to managed code from a Transact-SQL user-defined function counts as one level against the 32-level nesting limit.</span></span> <span data-ttu-id="ad558-129">Методы, вызываемые из управляемого кода, под это ограничение не подпадают.</span><span class="sxs-lookup"><span data-stu-id="ad558-129">Methods invoked from within managed code do not count against this limit.</span></span>  
  
-   <span data-ttu-id="ad558-130">Следующие инструкции компонента Service Broker не могут быть включены в определение определяемой пользователем функции Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="ad558-130">The following Service Broker statements cannot be included in the definition of a Transact-SQL user-defined function:</span></span>  
  
    -   <span data-ttu-id="ad558-131">BEGIN DIALOG CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="ad558-131">BEGIN DIALOG CONVERSATION</span></span>  
  
    -   <span data-ttu-id="ad558-132">END CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="ad558-132">END CONVERSATION</span></span>  
  
    -   <span data-ttu-id="ad558-133">GET CONVERSATION GROUP</span><span class="sxs-lookup"><span data-stu-id="ad558-133">GET CONVERSATION GROUP</span></span>  
  
    -   <span data-ttu-id="ad558-134">MOVE CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="ad558-134">MOVE CONVERSATION</span></span>  
  
    -   <span data-ttu-id="ad558-135">RECEIVE</span><span class="sxs-lookup"><span data-stu-id="ad558-135">RECEIVE</span></span>  
  
    -   <span data-ttu-id="ad558-136">SEND</span><span class="sxs-lookup"><span data-stu-id="ad558-136">SEND</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ad558-137">безопасность</span><span class="sxs-lookup"><span data-stu-id="ad558-137">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ad558-138">Permissions</span><span class="sxs-lookup"><span data-stu-id="ad558-138">Permissions</span></span>  
 <span data-ttu-id="ad558-139">Требуется разрешение CREATE FUNCTION на базу данных и разрешение ALTER на схему, в которой создается функция.</span><span class="sxs-lookup"><span data-stu-id="ad558-139">Requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.</span></span> <span data-ttu-id="ad558-140">Если в функции указан определяемый пользователем тип, требуется разрешение EXECUTE на этот тип.</span><span class="sxs-lookup"><span data-stu-id="ad558-140">If the function specifies a user-defined type, requires EXECUTE permission on the type.</span></span>  
  
##  <a name="scalar-functions"></a><a name="Scalar"></a><span data-ttu-id="ad558-141">Скалярные функции</span><span class="sxs-lookup"><span data-stu-id="ad558-141">Scalar Functions</span></span>  
 <span data-ttu-id="ad558-142">В следующем примере создается скалярная функция из нескольких инструкций в базе данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad558-142">The following example creates a multistatement scalar function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="ad558-143">Функция имеет один входной параметр `ProductID`и возвращает одно значение — количество указанного товара на складе.</span><span class="sxs-lookup"><span data-stu-id="ad558-143">The function takes one input value, a `ProductID`, and returns a single data value, the aggregated quantity of the specified product in inventory.</span></span>  
  
```  
IF OBJECT_ID (N'dbo.ufnGetInventoryStock', N'FN') IS NOT NULL  
    DROP FUNCTION ufnGetInventoryStock;  
GO  
CREATE FUNCTION dbo.ufnGetInventoryStock(@ProductID int)  
RETURNS int   
AS   
-- Returns the stock level for the product.  
BEGIN  
    DECLARE @ret int;  
    SELECT @ret = SUM(p.Quantity)   
    FROM Production.ProductInventory p   
    WHERE p.ProductID = @ProductID   
        AND p.LocationID = '6';  
     IF (@ret IS NULL)   
        SET @ret = 0;  
    RETURN @ret;  
END;  
GO  
  
```  
  
 <span data-ttu-id="ad558-144">В следующем примере функция `ufnGetInventoryStock` используется для получения сведений о количестве товаров с идентификаторами `ProductModelID` от 75 до 80.</span><span class="sxs-lookup"><span data-stu-id="ad558-144">The following example uses the `ufnGetInventoryStock` function to return the current inventory quantity for products that have a `ProductModelID` between 75 and 80.</span></span>  
  
```  
SELECT ProductModelID, Name, dbo.ufnGetInventoryStock(ProductID)AS CurrentSupply  
FROM Production.Product  
WHERE ProductModelID BETWEEN 75 and 80;  
  
```  
  
##  <a name="table-valued-functions"></a><a name="TVF"></a><span data-ttu-id="ad558-145">Функции с табличным значением</span><span class="sxs-lookup"><span data-stu-id="ad558-145">Table-Valued Functions</span></span>  
 <span data-ttu-id="ad558-146">Результатом следующего примера является встроенная функция, создающая табличное значение в базе данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad558-146">The following example creates an inline table-valued function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="ad558-147">Функция имеет один входной параметр — идентификатор клиента (магазина) — и возвращает столбцы `ProductID`, `Name`и столбец `YTD Total` со сведениями о продажах продукта за текущий год.</span><span class="sxs-lookup"><span data-stu-id="ad558-147">The function takes one input parameter, a customer (store) ID, and returns the columns `ProductID`, `Name`, and the aggregate of year-to-date sales as `YTD Total` for each product sold to the store.</span></span>  
  
```  
IF OBJECT_ID (N'Sales.ufn_SalesByStore', N'IF') IS NOT NULL  
    DROP FUNCTION Sales.ufn_SalesByStore;  
GO  
CREATE FUNCTION Sales.ufn_SalesByStore (@storeid int)  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT P.ProductID, P.Name, SUM(SD.LineTotal) AS 'Total'  
    FROM Production.Product AS P   
    JOIN Sales.SalesOrderDetail AS SD ON SD.ProductID = P.ProductID  
    JOIN Sales.SalesOrderHeader AS SH ON SH.SalesOrderID = SD.SalesOrderID  
    JOIN Sales.Customer AS C ON SH.CustomerID = C.CustomerID  
    WHERE C.StoreID = @storeid  
    GROUP BY P.ProductID, P.Name  
);  
  
```  
  
 <span data-ttu-id="ad558-148">В следующем примере функция вызывается с идентификатором 602.</span><span class="sxs-lookup"><span data-stu-id="ad558-148">The following example invokes the function and specifies customer ID 602.</span></span>  
  
```  
SELECT * FROM Sales.ufn_SalesByStore (602);  
  
```  
  
 <span data-ttu-id="ad558-149">В следующем примере создается функция с табличным значением в базе данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad558-149">The following example creates a table-valued function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="ad558-150">Функция имеет один входной параметр `EmployeeID` и возвращает список всех сотрудников, которые напрямую или косвенно отчитываются перед заданным сотрудником.</span><span class="sxs-lookup"><span data-stu-id="ad558-150">The function takes a single input parameter, an `EmployeeID` and returns a list of all the employees who report to the specified employee directly or indirectly.</span></span> <span data-ttu-id="ad558-151">Затем функция вызывается с указанием идентификатора сотрудника 109.</span><span class="sxs-lookup"><span data-stu-id="ad558-151">The function is then invoked specifying employee ID 109.</span></span>  
  
```  
IF OBJECT_ID (N'dbo.ufn_FindReports', N'TF') IS NOT NULL  
    DROP FUNCTION dbo.ufn_FindReports;  
GO  
CREATE FUNCTION dbo.ufn_FindReports (@InEmpID INTEGER)  
RETURNS @retFindReports TABLE   
(  
    EmployeeID int primary key NOT NULL,  
    FirstName nvarchar(255) NOT NULL,  
    LastName nvarchar(255) NOT NULL,  
    JobTitle nvarchar(50) NOT NULL,  
    RecursionLevel int NOT NULL  
)  
--Returns a result set that lists all the employees who report to the   
--specific employee directly or indirectly.*/  
AS  
BEGIN  
WITH EMP_cte(EmployeeID, OrganizationNode, FirstName, LastName, JobTitle, RecursionLevel) -- CTE name and columns  
    AS (  
        SELECT e.BusinessEntityID, e.OrganizationNode, p.FirstName, p.LastName, e.JobTitle, 0 -- Get the initial list of Employees for Manager n  
        FROM HumanResources.Employee e   
INNER JOIN Person.Person p   
ON p.BusinessEntityID = e.BusinessEntityID  
        WHERE e.BusinessEntityID = @InEmpID  
        UNION ALL  
        SELECT e.BusinessEntityID, e.OrganizationNode, p.FirstName, p.LastName, e.JobTitle, RecursionLevel + 1 -- Join recursive member to anchor  
        FROM HumanResources.Employee e   
            INNER JOIN EMP_cte  
            ON e.OrganizationNode.GetAncestor(1) = EMP_cte.OrganizationNode  
INNER JOIN Person.Person p   
ON p.BusinessEntityID = e.BusinessEntityID  
        )  
-- copy the required columns to the result of the function   
   INSERT @retFindReports  
   SELECT EmployeeID, FirstName, LastName, JobTitle, RecursionLevel  
   FROM EMP_cte   
   RETURN  
END;  
GO  
-- Example invocation  
SELECT EmployeeID, FirstName, LastName, JobTitle, RecursionLevel  
FROM dbo.ufn_FindReports(1);  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad558-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="ad558-152">See Also</span></span>  
 <span data-ttu-id="ad558-153">[Определяемые пользователем функции](user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="ad558-153">[User-Defined Functions](user-defined-functions.md) </span></span>  
 [<span data-ttu-id="ad558-154">CREATE FUNCTION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ad558-154">CREATE FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-function-transact-sql)  
  
  
