---
title: Указание параметров | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- parameters [SQL Server], stored procedures
- stored procedures [SQL Server], parameters
- output parameters [SQL Server]
- input parameters [SQL Server]
ms.assetid: 902314fe-5f9c-4d0d-a0b7-27e67c9c70ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: d93a04281839c4db26cbab16ac166af3cdb7c9a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669370"
---
# <a name="specify-parameters"></a><span data-ttu-id="68a9a-102">Указание параметров</span><span class="sxs-lookup"><span data-stu-id="68a9a-102">Specify Parameters</span></span>
  <span data-ttu-id="68a9a-103">Путем указания параметров процедуры вызывающие программы могут передавать значения в тело процедуры.</span><span class="sxs-lookup"><span data-stu-id="68a9a-103">By specifying procedure parameters, calling programs are able to pass values into the body of the procedure.</span></span> <span data-ttu-id="68a9a-104">Эти значения могут использоваться для разных целей во время исполнения процедуры.</span><span class="sxs-lookup"><span data-stu-id="68a9a-104">Those values can be used for a variety of purposes during procedure execution.</span></span> <span data-ttu-id="68a9a-105">Параметры процедуры могут также возвращать значения вызывающей программе, если параметр помечен признаком OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="68a9a-105">Procedure parameters can also return values to the calling program if the parameter is marked as an OUTPUT parameter.</span></span>  
  
 <span data-ttu-id="68a9a-106">Хранимая процедура может иметь не более 2100 параметров, каждый из которых имеет имя, тип данных и направление.</span><span class="sxs-lookup"><span data-stu-id="68a9a-106">A procedure can have a maximum of 2100 parameters; each assigned a name, data type, and direction.</span></span> <span data-ttu-id="68a9a-107">При необходимости параметрам можно задавать значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="68a9a-107">Optionally, parameters can be assigned default values.</span></span>  
  
 <span data-ttu-id="68a9a-108">В следующем разделе содержатся сведения о передаче значений параметрам и о том, как каждый из атрибутов параметров используется во время вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="68a9a-108">The following section provides information about passing values into parameters and about how each of the parameter attributes is used during a procedure call.</span></span>  
  
## <a name="passing-values-into-parameters"></a><span data-ttu-id="68a9a-109">Передача значений в параметры</span><span class="sxs-lookup"><span data-stu-id="68a9a-109">Passing Values into Parameters</span></span>  
 <span data-ttu-id="68a9a-110">Значения параметра, переданные при вызове процедуры, должны быть константами или переменными. Имя функции не может быть значением параметра.</span><span class="sxs-lookup"><span data-stu-id="68a9a-110">The parameter values supplied with a procedure call must be constants or a variable; a function name cannot be used as a parameter value.</span></span> <span data-ttu-id="68a9a-111">Переменные могут быть пользовательскими или системными, например \@\@spid.</span><span class="sxs-lookup"><span data-stu-id="68a9a-111">Variables can be user-defined or system variables such as \@\@spid.</span></span>  
  
 <span data-ttu-id="68a9a-112">В следующих примерах демонстрируется передача значений параметров процедуре `uspGetWhereUsedProductID`.</span><span class="sxs-lookup"><span data-stu-id="68a9a-112">The following examples demonstrate passing parameter values to the procedure `uspGetWhereUsedProductID`.</span></span> <span data-ttu-id="68a9a-113">В них показано, как передать в качестве параметров константы и переменные, а также как использовать переменную для передачи значения функции.</span><span class="sxs-lookup"><span data-stu-id="68a9a-113">They illustrate how to pass parameters as constants and variables and also how to use a variable to pass the value of a function.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
-- Passing values as constants.  
EXEC dbo.uspGetWhereUsedProductID 819, '20050225';  
GO  
-- Passing values as variables.  
DECLARE @ProductID int, @CheckDate datetime;  
SET @ProductID = 819;  
SET @CheckDate = '20050225';  
EXEC dbo.uspGetWhereUsedProductID @ProductID, @CheckDate;  
GO  
-- Try to use a function as a parameter value.  
-- This produces an error message.  
EXEC dbo.uspGetWhereUsedProductID 819, GETDATE();  
GO  
-- Passing the function value as a variable.  
DECLARE @CheckDate datetime;  
SET @CheckDate = GETDATE();  
EXEC dbo.uspGetWhereUsedProductID 819, @CheckDate;  
GO  
```  
  
## <a name="specifying-parameter-names"></a><span data-ttu-id="68a9a-114">Указание имен параметров</span><span class="sxs-lookup"><span data-stu-id="68a9a-114">Specifying Parameter Names</span></span>  
 <span data-ttu-id="68a9a-115">При создании процедуры и объявлении имени параметра, последнее должно начинаться с единичного символа \@ и быть уникальным для всей процедуры.</span><span class="sxs-lookup"><span data-stu-id="68a9a-115">When creating a procedure and declaring a parameter name, the parameter name must begin with a single \@ character and must be unique in the scope of the procedure.</span></span>  
  
 <span data-ttu-id="68a9a-116">Явные имена параметров и задание значений каждому параметру в процедуре позволяет передавать параметры в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="68a9a-116">Explicitly naming the parameters and assigning the appropriate values to each parameter in a procedure call allows the parameters to be supplied in any order.</span></span> <span data-ttu-id="68a9a-117">Например, если в процедуре **my_proc** ожидается три параметра с именами **\@first**, **\@second** и **\@third**, передаваемые в процедуру значения могут быть присвоены параметрам следующим образом: `EXECUTE my_proc @second = 2, @first = 1, @third = 3;`.</span><span class="sxs-lookup"><span data-stu-id="68a9a-117">For example, if the procedure **my_proc** expects three parameters named **\@first**, **\@second**, and **\@third**, the values passed to the procedure can be assigned to the parameter names, such as: `EXECUTE my_proc @second = 2, @first = 1, @third = 3;`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68a9a-118">При указании одного значения параметра в формате **\@parameter =** _value_ необходимо точно так же предоставить все последующие параметры.</span><span class="sxs-lookup"><span data-stu-id="68a9a-118">If one parameter value is supplied in the form **\@parameter =**_value_, all subsequent parameters must be supplied in this manner.</span></span> <span data-ttu-id="68a9a-119">Если значения параметра передаются не в формате **\@parameter =** _value_, значения должны передаваться в том порядке (слева направо), в котором они перечислены в инструкции CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="68a9a-119">If the parameter values are not passed in the form **\@parameter =**_value_, the values must be supplied in the identical order (left to right) as the parameters are listed in the CREATE PROCEDURE statement.</span></span>  
> 
> [!WARNING]
>  <span data-ttu-id="68a9a-120">Передача параметров в формате **\@parameter =** _value_ с ошибками приведет к возникновению ошибки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и невозможности выполнения процедуры.</span><span class="sxs-lookup"><span data-stu-id="68a9a-120">Any parameter passed in the form **\@parameter =**_value_ with the parameter misspelled, will cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to generate an error and prevent procedure execution.</span></span>  
  
## <a name="specifying-parameter-data-types"></a><span data-ttu-id="68a9a-121">Указание типов данных параметров</span><span class="sxs-lookup"><span data-stu-id="68a9a-121">Specifying Parameter Data Types</span></span>  
 <span data-ttu-id="68a9a-122">Параметры должны быть определены с типом данных в момент объявления в инструкции CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="68a9a-122">Parameters must be defined with a data type when they are declared in a CREATE PROCEDURE statement.</span></span> <span data-ttu-id="68a9a-123">Тип данных параметра определяет тип и диапазон допустимых значений параметра при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="68a9a-123">The data type of a parameter determines the type and range of values that are accepted for the parameter when the procedure is called.</span></span> <span data-ttu-id="68a9a-124">Например, параметр типа `tinyint` может принимать только численные значения в диапазоне от 0 до 255 в момент передачи этому параметру.</span><span class="sxs-lookup"><span data-stu-id="68a9a-124">For example, if you define a parameter with a `tinyint` data type, only numeric values ranging from 0 to 255 are accepted when passed into that parameter.</span></span> <span data-ttu-id="68a9a-125">При попытке выполнить процедуру со значением, не совместимым с типом данных, происходит ошибка.</span><span class="sxs-lookup"><span data-stu-id="68a9a-125">An error is returned if a procedure is executed with a value incompatible with the data type.</span></span>  
  
## <a name="specifying-parameter-default-values"></a><span data-ttu-id="68a9a-126">Указание значений параметра по умолчанию</span><span class="sxs-lookup"><span data-stu-id="68a9a-126">Specifying Parameter Default Values</span></span>  
 <span data-ttu-id="68a9a-127">Параметр считается необязательным, если он имеет значение по умолчанию при объявлении.</span><span class="sxs-lookup"><span data-stu-id="68a9a-127">A parameter is considered optional if the parameter has a default value specified when it is declared.</span></span> <span data-ttu-id="68a9a-128">Нет необходимости указывать значение необязательного параметра при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="68a9a-128">It is not necessary to provide a value for an optional parameter in a procedure call.</span></span>  
  
 <span data-ttu-id="68a9a-129">Значение параметра по умолчанию используется, когда:</span><span class="sxs-lookup"><span data-stu-id="68a9a-129">The default value of a parameter is used when:</span></span>  
  
-   <span data-ttu-id="68a9a-130">не указано значение для параметра при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="68a9a-130">No value for the parameter is specified in the procedure call.</span></span>  
  
-   <span data-ttu-id="68a9a-131">в качестве значения при вызове процедуры указывается ключевое слово DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="68a9a-131">The DEFAULT keyword is specified as the value in the procedure call.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68a9a-132">Если значением по умолчанию является символьная строка, включающая в себя знаки пробела или пунктуации, либо содержащая первым элементом число, например 6ххх, то ее следует заключить в одинарные прямые кавычки.</span><span class="sxs-lookup"><span data-stu-id="68a9a-132">If the default value is a character string that contains embedded blanks or punctuation, or if it starts with a number (for example, 6xxx), it must be enclosed in single, straight quotation marks.</span></span>  
  
 <span data-ttu-id="68a9a-133">Если значение по умолчанию указать нельзя, укажите NULL.</span><span class="sxs-lookup"><span data-stu-id="68a9a-133">If no value can be specified appropriately as a default for the parameter, specify NULL as the default.</span></span> <span data-ttu-id="68a9a-134">Желательно, чтобы процедура возвращала сообщение, если она выполняется без значения для параметра.</span><span class="sxs-lookup"><span data-stu-id="68a9a-134">It is a good idea to have the procedure return a customized message if the procedure is executed without a value for the parameter.</span></span>  
  
 <span data-ttu-id="68a9a-135">В следующем примере создается процедура `usp_GetSalesYTD` с единственным входным параметром `@SalesPerson`.</span><span class="sxs-lookup"><span data-stu-id="68a9a-135">The following example creates the `usp_GetSalesYTD` procedure with one input parameter, `@SalesPerson`.</span></span> <span data-ttu-id="68a9a-136">В качестве значения по умолчанию параметру присваивается значение NULL, которое используется в инструкциях обработки ошибок для выдачи сообщения, если процедура выполняется с неопределенным параметром `@SalesPerson` .</span><span class="sxs-lookup"><span data-stu-id="68a9a-136">NULL is assigned as the default value for the parameter and is used in error handling statements to return a custom error message for cases when the procedure is executed without a value for the `@SalesPerson` parameter.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.uspGetSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetSalesYTD  
@SalesPerson nvarchar(50) = NULL  -- NULL default value  
AS   
    SET NOCOUNT ON;   
  
-- Validate the @SalesPerson parameter.  
IF @SalesPerson IS NULL  
BEGIN  
   PRINT 'ERROR: You must specify the last name of the sales person.'  
   RETURN  
END  
-- Get the sales for the specified sales person and   
-- assign it to the output parameter.  
SELECT SalesYTD  
FROM Sales.SalesPerson AS sp  
JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
WHERE LastName = @SalesPerson;  
RETURN  
GO  
  
```  
  
 <span data-ttu-id="68a9a-137">Следующий пример выполняет процедуру.</span><span class="sxs-lookup"><span data-stu-id="68a9a-137">The following example executes the procedure.</span></span> <span data-ttu-id="68a9a-138">Первая инструкция выполняет процедуру без указания входного значения.</span><span class="sxs-lookup"><span data-stu-id="68a9a-138">The first statement executes the procedure without specifying an input value.</span></span> <span data-ttu-id="68a9a-139">В результате чего инструкции обработки ошибок процедуры возвращают пользовательское сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="68a9a-139">This causes the error handling statements in the procedure to return the custom error message.</span></span> <span data-ttu-id="68a9a-140">Вторая инструкция задает входное значение и возвращает ожидаемый результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="68a9a-140">The second statement supplies an input value and returns the expected result set.</span></span>  
  
```  
-- Run the procedure without specifying an input value.  
EXEC Sales.usp_GetSalesYTD;  
GO  
-- Run the procedure with an input value.  
EXEC Sales.usp_GetSalesYTD N'Blythe';  
GO  
```  
  
 <span data-ttu-id="68a9a-141">Хотя разрешается опустить параметры, для которых предоставлены значения по умолчанию, можно лишь подвергнуть усечению список параметров.</span><span class="sxs-lookup"><span data-stu-id="68a9a-141">Although parameters for which defaults have been supplied can be omitted, the list of parameters can only be truncated.</span></span> <span data-ttu-id="68a9a-142">Например, если у процедуры пять параметров, можно опустить как четвертый, так и пятый параметр.</span><span class="sxs-lookup"><span data-stu-id="68a9a-142">For example, if a procedure has five parameters, both the fourth and the fifth parameters can be omitted.</span></span> <span data-ttu-id="68a9a-143">При этом нельзя пропустить четвертый параметр, если включен пятый, если только параметры не передаются в формате **\@parameter =** _value_.</span><span class="sxs-lookup"><span data-stu-id="68a9a-143">However the fourth parameter cannot be skipped as long as the fifth parameter is included, unless the parameters are supplied in the form **\@parameter =**_value_.</span></span>  
  
## <a name="specifying-parameter-direction"></a><span data-ttu-id="68a9a-144">Указание направления параметров</span><span class="sxs-lookup"><span data-stu-id="68a9a-144">Specifying Parameter Direction</span></span>  
 <span data-ttu-id="68a9a-145">Параметр может быть как входным, когда значение передается в тело процедуры, так и выходным, возвращаемым процедурой вызывающей программе.</span><span class="sxs-lookup"><span data-stu-id="68a9a-145">The direction of a parameter is either input, a value is passed into the body of the procedure, or output, the procedure returns a value to the calling program.</span></span> <span data-ttu-id="68a9a-146">По умолчанию параметр определен как входной.</span><span class="sxs-lookup"><span data-stu-id="68a9a-146">The default is an input parameter.</span></span>  
  
 <span data-ttu-id="68a9a-147">Для указания выходного параметра в определении процедуры необходимо указать ключевое слово OUTPUT в инструкции CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="68a9a-147">To specify an output parameter, the OUTPUT keyword must be specified in the definition of the parameter in the CREATE PROCEDURE statement.</span></span> <span data-ttu-id="68a9a-148">Процедура, завершая свою работу, возвращает текущее значение выходного параметра в вызывающую программу.</span><span class="sxs-lookup"><span data-stu-id="68a9a-148">The procedure returns the current value of the output parameter to the calling program when the procedure exits.</span></span> <span data-ttu-id="68a9a-149">При выполнении процедуры вызывающая программа также должна использовать ключевое слово OUTPUT для сохранения значения параметра в переменной, которое затем может быть использовано в вызывающей программе.</span><span class="sxs-lookup"><span data-stu-id="68a9a-149">The calling program must also use the OUTPUT keyword when executing the procedure to save the parameter's value in a variable that can be used in the calling program.</span></span>  
  
 <span data-ttu-id="68a9a-150">В следующем примере создается процедура `Production.usp`_`GetList` , которая возвращает список продуктов, стоимость которых не превышает заданного значения.</span><span class="sxs-lookup"><span data-stu-id="68a9a-150">The following example creates the `Production.usp`_`GetList` procedure, which returns a list of products that have prices that do not exceed a specified amount.</span></span> <span data-ttu-id="68a9a-151">На данном примере демонстрируется использование нескольких инструкций SELECT и нескольких параметров OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="68a9a-151">The example shows using multiple SELECT statements and multiple OUTPUT parameters.</span></span> <span data-ttu-id="68a9a-152">Параметры OUTPUT позволяют внешней процедуре, пакету или нескольким инструкциям [!INCLUDE[tsql](../../includes/tsql-md.md)] осуществлять доступ к набору значений во время выполнения процедуры.</span><span class="sxs-lookup"><span data-stu-id="68a9a-152">OUTPUT parameters allow an external procedure, a batch, or more than one [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to access a value set during the procedure execution.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'Production.uspGetList', 'P' ) IS NOT NULL   
    DROP PROCEDURE Production.uspGetList;  
GO  
CREATE PROCEDURE Production.uspGetList @Product varchar(40)   
    , @MaxPrice money   
    , @ComparePrice money OUTPUT  
    , @ListPrice money OUT  
AS  
    SET NOCOUNT ON;  
    SELECT p.[Name] AS Product, p.ListPrice AS 'List Price'  
    FROM Production.Product AS p  
    JOIN Production.ProductSubcategory AS s   
      ON p.ProductSubcategoryID = s.ProductSubcategoryID  
    WHERE s.[Name] LIKE @Product AND p.ListPrice < @MaxPrice;  
-- Populate the output variable @ListPprice.  
SET @ListPrice = (SELECT MAX(p.ListPrice)  
        FROM Production.Product AS p  
        JOIN  Production.ProductSubcategory AS s   
          ON p.ProductSubcategoryID = s.ProductSubcategoryID  
        WHERE s.[Name] LIKE @Product AND p.ListPrice < @MaxPrice);  
-- Populate the output variable @compareprice.  
SET @ComparePrice = @MaxPrice;  
GO  
  
```  
  
 <span data-ttu-id="68a9a-153">Процедура `usp_GetList` возвращает из базы данных [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] список товаров (велосипедов) стоимостью менее $ 700.</span><span class="sxs-lookup"><span data-stu-id="68a9a-153">Execute `usp_GetList` to return a list of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] products (Bikes) that cost less than $700.</span></span> <span data-ttu-id="68a9a-154">Параметры **\@cost** и **\@compareprices** инструкции OUTPUT используются в языке управления потоком для вывода информации в окне **Сообщения**.</span><span class="sxs-lookup"><span data-stu-id="68a9a-154">The OUTPUT parameters **\@cost** and **\@compareprices** are used with control-of-flow language to return a message in the **Messages** window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68a9a-155">Переменная OUTPUT должна быть определена во время создания процедуры, а также в ходе использования переменной.</span><span class="sxs-lookup"><span data-stu-id="68a9a-155">The OUTPUT variable must be defined during the procedure creation and also during the use of the variable.</span></span> <span data-ttu-id="68a9a-156">Имена параметра и переменной не должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="68a9a-156">The parameter name and variable name do not have to match.</span></span> <span data-ttu-id="68a9a-157">При этом тип данных и положение параметра должны быть одинаковыми (если только не используется **\@listprice=** _переменная_).</span><span class="sxs-lookup"><span data-stu-id="68a9a-157">However, the data type and parameter positioning must match (unless **\@listprice=** _variable_ is used).</span></span>  
  
```  
DECLARE @ComparePrice money, @Cost money ;  
EXECUTE Production.uspGetList '%Bikes%', 700,   
    @ComparePrice OUT,   
    @Cost OUTPUT  
IF @Cost <= @ComparePrice   
BEGIN  
    PRINT 'These products can be purchased for less than   
    $'+RTRIM(CAST(@ComparePrice AS varchar(20)))+'.'  
END  
ELSE  
    PRINT 'The prices for all products in this category exceed   
    $'+ RTRIM(CAST(@ComparePrice AS varchar(20)))+'.';  
  
```  
  
 <span data-ttu-id="68a9a-158">Частичный результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="68a9a-158">Here is the partial result set:</span></span>  
  
```  
Product                                            List Price  
-------------------------------------------------- ------------------  
Road-750 Black, 58                                 539.99  
Mountain-500 Silver, 40                            564.99  
Mountain-500 Silver, 42                            564.99  
...  
Road-750 Black, 48                                 539.99  
Road-750 Black, 52                                 539.99  
  
(14 row(s) affected)  
  
These items can be purchased for less than $700.00.  
```  
  
## <a name="see-also"></a><span data-ttu-id="68a9a-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="68a9a-159">See Also</span></span>  
 [<span data-ttu-id="68a9a-160">CREATE PROCEDURE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="68a9a-160">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
