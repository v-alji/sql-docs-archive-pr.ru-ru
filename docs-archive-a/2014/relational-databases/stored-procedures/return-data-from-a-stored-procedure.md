---
title: Возврат данных из хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], returning data
- returning data from stored procedure
ms.assetid: 7a428ffe-cd87-4f42-b3f1-d26aa8312bf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 472ca5cf27f7e7ea2b18daa961c19faadcf2251f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669371"
---
# <a name="return-data-from-a-stored-procedure"></a><span data-ttu-id="13b29-102">Возврат данных из хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="13b29-102">Return Data from a Stored Procedure</span></span>
  <span data-ttu-id="13b29-103">Существует два способа возврата результирующих наборов или данных из процедуры вызывающей программе: параметры вывода и коды возврата.</span><span class="sxs-lookup"><span data-stu-id="13b29-103">There are two ways of returning result sets or data from a procedure to a calling program: output parameters and return codes.</span></span> <span data-ttu-id="13b29-104">В этом разделе приводятся сведения по обоим способам.</span><span class="sxs-lookup"><span data-stu-id="13b29-104">This topic provides information on both approaches.</span></span>  
  
## <a name="returning-data-using-an-output-parameter"></a><span data-ttu-id="13b29-105">Возврат данных с помощью выходного параметра</span><span class="sxs-lookup"><span data-stu-id="13b29-105">Returning Data Using an Output Parameter</span></span>  
 <span data-ttu-id="13b29-106">Процедура может возвращать текущее значение параметра в вызываемой программе при завершении работы при указании ключевого слова OUTPUT для параметра в определении процедуры.</span><span class="sxs-lookup"><span data-stu-id="13b29-106">If you specify the OUTPUT keyword for a parameter in the procedure definition, the procedure can return the current value of the parameter to the calling program when the procedure exits.</span></span> <span data-ttu-id="13b29-107">Чтобы сохранить значение параметра в переменной, которая может быть использована в вызываемой программе, при выполнении процедуры вызываемая программа должна использовать ключевое слово OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="13b29-107">To save the value of the parameter in a variable that can be used in the calling program, the calling program must use the OUTPUT keyword when executing the procedure.</span></span> <span data-ttu-id="13b29-108">Дополнительные сведения о том, какие типы данных могут использоваться в качестве выходных параметров, см. в разделе [CREATE PROCEDURE (Transact-SQL)](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="13b29-108">For more information about what data types can be used as output parameters, see [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span>  
  
### <a name="examples-of-output-parameter"></a><span data-ttu-id="13b29-109">Примеры выходного параметра</span><span class="sxs-lookup"><span data-stu-id="13b29-109">Examples of Output Parameter</span></span>  
 <span data-ttu-id="13b29-110">Следующий пример представляет процедуру с входным и выходным параметрами.</span><span class="sxs-lookup"><span data-stu-id="13b29-110">The following example shows a procedure with an input and an output parameter.</span></span> <span data-ttu-id="13b29-111">Параметр `@SalesPerson` получает входное значение, указанное вызывающей программой.</span><span class="sxs-lookup"><span data-stu-id="13b29-111">The `@SalesPerson` parameter would receive an input value specified by the calling program.</span></span> <span data-ttu-id="13b29-112">Инструкция SELECT использует значение, переданное входному параметру для получения верного значения `SalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="13b29-112">The SELECT statement uses the value passed into the input parameter to obtain the correct `SalesYTD` value.</span></span> <span data-ttu-id="13b29-113">Инструкция SELECT также присваивает это значение выходному параметру `@SalesYTD` , который возвращает значение вызывающей программе при завершении процедуры.</span><span class="sxs-lookup"><span data-stu-id="13b29-113">The SELECT statement also assigns the value to the `@SalesYTD` output parameter, which returns the value to the calling program when the procedure exits.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetEmployeeSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.uspGetEmployeeSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetEmployeeSalesYTD  
@SalesPerson nvarchar(50),  
@SalesYTD money OUTPUT  
AS    
  
    SET NOCOUNT ON;  
    SELECT @SalesYTD = SalesYTD  
    FROM Sales.SalesPerson AS sp  
    JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
    WHERE LastName = @SalesPerson;  
RETURN  
GO  
  
```  
  
 <span data-ttu-id="13b29-114">В следующем примере вызывается процедура, которая была создана в первом примере и сохраняет выходное значение, возвращенное вызванной процедурой в переменной `@SalesYTD` , являющейся локальной в вызывающей программе.</span><span class="sxs-lookup"><span data-stu-id="13b29-114">The following example calls the procedure created in the first example and saves the output value returned from the called procedure in the `@SalesYTD` variable, which is local to the calling program.</span></span>  
  
```  
-- Declare the variable to receive the output value of the procedure.  
DECLARE @SalesYTDBySalesPerson money;  
-- Execute the procedure specifying a last name for the input parameter  
-- and saving the output value in the variable @SalesYTDBySalesPerson  
EXECUTE Sales.uspGetEmployeeSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDBySalesPerson OUTPUT;  
-- Display the value returned by the procedure.  
PRINT 'Year-to-date sales for this employee is ' +   
    convert(varchar(10),@SalesYTDBySalesPerson);  
GO  
  
```  
  
 <span data-ttu-id="13b29-115">Входные значения также могут быть указаны для параметров OUTPUT при выполнении процедуры.</span><span class="sxs-lookup"><span data-stu-id="13b29-115">Input values can also be specified for OUTPUT parameters when the procedure is executed.</span></span> <span data-ttu-id="13b29-116">Это позволяет хранимой процедуре получать значение из вызываемой программы, изменять его или выполнять операции с этим значением, а затем возвращать новое значение вызываемой программе.</span><span class="sxs-lookup"><span data-stu-id="13b29-116">This allows the procedure to receive a value from the calling program, change or perform operations with the value, and then return the new value to the calling program.</span></span> <span data-ttu-id="13b29-117">В предыдущем примере переменной `@SalesYTDBySalesPerson` может быть присвоено значение прежде, чем программа вызовет процедуру `Sales.uspGetEmployeeSalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="13b29-117">In the previous example, the `@SalesYTDBySalesPerson` variable can be assigned a value before the program calls the `Sales.uspGetEmployeeSalesYTD` procedure.</span></span> <span data-ttu-id="13b29-118">Эта инструкция передает значение переменной `@SalesYTDBySalesPerson` выходному параметру `@SalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="13b29-118">The execute statement would pass the `@SalesYTDBySalesPerson` variable value into the `@SalesYTD` OUTPUT parameter.</span></span> <span data-ttu-id="13b29-119">Далее в тексте процедуры значение можно использовать для вычислений, формирующих новое значение.</span><span class="sxs-lookup"><span data-stu-id="13b29-119">Then in the procedure body, the value could be used for calculations that generate a new value.</span></span> <span data-ttu-id="13b29-120">Новое значение передается обратно из процедуры через выходной параметр, обновляя значение в переменной `@SalesYTDBySalesPerson` при завершении процедуры.</span><span class="sxs-lookup"><span data-stu-id="13b29-120">The new value would be passed back out of the procedure through the OUTPUT parameter, updating the value in the `@SalesYTDBySalesPerson` variable when the procedure exits.</span></span> <span data-ttu-id="13b29-121">Часто это называется «возможностью передачи по ссылке».</span><span class="sxs-lookup"><span data-stu-id="13b29-121">This is often referred to as "pass-by-reference capability."</span></span>  
  
 <span data-ttu-id="13b29-122">Если при вызове процедуры указано ключевое слово OUTPUT для параметра, а параметр не определен при помощи OUTPUT в определении процедуры, выдается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="13b29-122">If you specify OUTPUT for a parameter when you call a procedure and that parameter is not defined by using OUTPUT in the procedure definition, you get an error message.</span></span> <span data-ttu-id="13b29-123">Однако процедуру можно выполнить с выходными параметрами, не указывая OUTPUT при выполнении процедуры.</span><span class="sxs-lookup"><span data-stu-id="13b29-123">However, you can execute a procedure with output parameters and not specify OUTPUT when executing the procedure.</span></span> <span data-ttu-id="13b29-124">Сообщение об ошибке не будет выдаваться, но нельзя будет использовать выходное значение в вызываемой программе.</span><span class="sxs-lookup"><span data-stu-id="13b29-124">No error is returned, but you cannot use the output value in the calling program.</span></span>  
  
### <a name="using-the-cursor-data-type-in-output-parameters"></a><span data-ttu-id="13b29-125">Использование типа данных Cursor в выходных параметрах</span><span class="sxs-lookup"><span data-stu-id="13b29-125">Using the Cursor Data Type in OUTPUT Parameters</span></span>  
 [!INCLUDE[tsql](../../../includes/tsql-md.md)]<span data-ttu-id="13b29-126">процедуры могут использовать `cursor` тип данных только для выходных параметров.</span><span class="sxs-lookup"><span data-stu-id="13b29-126">procedures can use the `cursor` data type only for OUTPUT parameters.</span></span> <span data-ttu-id="13b29-127">Если `cursor` для параметра указан тип данных, для этого параметра в определении процедуры должны быть указаны как ключевые, так и выходные.</span><span class="sxs-lookup"><span data-stu-id="13b29-127">If the `cursor` data type is specified for a parameter, both the VARYING and OUTPUT keywords must be specified for that parameter in the procedure definition.</span></span> <span data-ttu-id="13b29-128">Параметр может быть задан только как OUTPUT, но если в объявлении параметра указано ключевое слово "РАЗНОе", тип данных должен быть, `cursor` а также должно быть указано ключевое слово OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="13b29-128">A parameter can be specified as only OUTPUT but if the VARYING keyword is specified in the parameter declaration, the data type must be `cursor` and the OUTPUT keyword must also be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13b29-129">Тип данных `cursor` не может быть связан с переменными приложения через интерфейсы API баз данных, таких как OLE DB, ODBC, ADO и DB-Library.</span><span class="sxs-lookup"><span data-stu-id="13b29-129">The `cursor` data type cannot be bound to application variables through the database APIs such as OLE DB, ODBC, ADO, and DB-Library.</span></span> <span data-ttu-id="13b29-130">Поскольку выходные параметры должны быть привязаны прежде, чем приложение сможет выполнить хранимую процедуру, хранимые процедуры с выходными параметрами типа `cursor` не могут быть вызваны из функций API базы данных.</span><span class="sxs-lookup"><span data-stu-id="13b29-130">Because OUTPUT parameters must be bound before an application can execute a procedure, procedures with `cursor` OUTPUT parameters cannot be called from the database APIs.</span></span> <span data-ttu-id="13b29-131">Эти процедуры могут быть вызваны из пакетов на языке [!INCLUDE[tsql](../../../includes/tsql-md.md)], процедур или триггеров, только если выходная переменная типа `cursor` присвоена локальной переменной языка [!INCLUDE[tsql](../../../includes/tsql-md.md)] типа `cursor`.</span><span class="sxs-lookup"><span data-stu-id="13b29-131">These procedures can be called from [!INCLUDE[tsql](../../../includes/tsql-md.md)] batches, procedures, or triggers only when the `cursor` OUTPUT variable is assigned to a [!INCLUDE[tsql](../../../includes/tsql-md.md)] local `cursor` variable.</span></span>  
  
### <a name="rules-for-cursor-output-parameters"></a><span data-ttu-id="13b29-132">Правила для выходных параметров курсора</span><span class="sxs-lookup"><span data-stu-id="13b29-132">Rules for Cursor Output Parameters</span></span>  
 <span data-ttu-id="13b29-133">Следующие правила относятся к выходным параметрам типа `cursor` при выполнении процедуры:</span><span class="sxs-lookup"><span data-stu-id="13b29-133">The following rules pertain to `cursor` output parameters when the procedure is executed:</span></span>  
  
-   <span data-ttu-id="13b29-134">Для курсора последовательного доступа в результирующий набор курсора будут возвращены только строки с текущей позиции курсора до конца курсора. Текущая позиция курсора определяется при окончании выполнения процедуры. Например:</span><span class="sxs-lookup"><span data-stu-id="13b29-134">For a forward-only cursor, the rows returned in the cursor's result set are only those rows at and beyond the position of the cursor at the conclusion of the procedure execution, for example:</span></span>  
  
    -   <span data-ttu-id="13b29-135">Непрокручиваемый курсор открыт в процедуре на результирующем наборе по имени RS из 100 строк.</span><span class="sxs-lookup"><span data-stu-id="13b29-135">A nonscrollable cursor is opened in a procedure on a result set named RS of 100 rows.</span></span>  
  
    -   <span data-ttu-id="13b29-136">Процедура выбирает первые 5 строк результирующего набора RS.</span><span class="sxs-lookup"><span data-stu-id="13b29-136">The procedure fetches the first 5 rows of result set RS.</span></span>  
  
    -   <span data-ttu-id="13b29-137">Процедура возвращает результат участнику.</span><span class="sxs-lookup"><span data-stu-id="13b29-137">The procedure returns to its caller.</span></span>  
  
    -   <span data-ttu-id="13b29-138">Результирующий набор RS, возвращенный участнику, состоит из строк с 6 по 100 из набора RS, и курсор в участнике позиционирован перед первой строкой RS.</span><span class="sxs-lookup"><span data-stu-id="13b29-138">The result set RS returned to the caller consists of rows from 6 through 100 of RS, and the cursor in the caller is positioned before the first row of RS.</span></span>  
  
-   <span data-ttu-id="13b29-139">Для курсора последовательного доступа, если курсор позиционирован перед первой строкой после завершения хранимой процедуры, весь результирующий набор будет возвращен к вызывающему пакету, процедуре или триггеру.</span><span class="sxs-lookup"><span data-stu-id="13b29-139">For a forward-only cursor, if the cursor is positioned before the first row when the procedure exits, the entire result set is returned to the calling batch, procedure, or trigger.</span></span> <span data-ttu-id="13b29-140">После возврата позиция курсора будет установлена перед первой строкой.</span><span class="sxs-lookup"><span data-stu-id="13b29-140">When returned, the cursor position is set before the first row.</span></span>  
  
-   <span data-ttu-id="13b29-141">Для курсора последовательного доступа, если курсор позиционирован за концом последней строки после завершения хранимой процедуры, вызывающему пакету, процедуре или триггеру будет возвращен пустой результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="13b29-141">For a forward-only cursor, if the cursor is positioned beyond the end of the last row when the procedure exits, an empty result set is returned to the calling batch, procedure, or trigger.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="13b29-142">Пустой результирующий набор отличается от значения NULL.</span><span class="sxs-lookup"><span data-stu-id="13b29-142">An empty result set is not the same as a null value.</span></span>  
  
-   <span data-ttu-id="13b29-143">Для прокручиваемого курсора все строки в результирующем наборе будут возвращены к вызывающему пакету, процедуре или триггеру после выполнения процедуры.</span><span class="sxs-lookup"><span data-stu-id="13b29-143">For a scrollable cursor, all the rows in the result set are returned to the calling batch, procedure, or trigger when the procedure exits.</span></span> <span data-ttu-id="13b29-144">При возврате позиция курсора остается в позиции последней выборки, выполненной в процедуре.</span><span class="sxs-lookup"><span data-stu-id="13b29-144">When returned, the cursor position is left at the position of the last fetch executed in the procedure.</span></span>  
  
-   <span data-ttu-id="13b29-145">Для любого типа курсора, если курсор закрыт, вызывающему пакету, процедуре или триггеру будет возвращено значение NULL.</span><span class="sxs-lookup"><span data-stu-id="13b29-145">For any type of cursor, if the cursor is closed, then a null value is passed back to the calling batch, procedure, or trigger.</span></span> <span data-ttu-id="13b29-146">Это же произойдет в случае, если курсор присвоен параметру, но этот курсор никогда не открывался.</span><span class="sxs-lookup"><span data-stu-id="13b29-146">This will also be the case if a cursor is assigned to a parameter, but that cursor is never opened.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="13b29-147">Закрытое состояние имеет значение только во время возврата.</span><span class="sxs-lookup"><span data-stu-id="13b29-147">The closed state matters only at return time.</span></span> <span data-ttu-id="13b29-148">Например, можно при выполнении процедуры закрыть курсор, снова открыть его позже в процедуре и возвратить этот результирующий набор курсора в вызывающий пакет, процедуру или триггер.</span><span class="sxs-lookup"><span data-stu-id="13b29-148">For example, it is valid to close a cursor part of the way through the procedure, to open it again later in the procedure, and return that cursor's result set to the calling batch, procedure, or trigger.</span></span>  
  
### <a name="examples-of-cursor-output-parameters"></a><span data-ttu-id="13b29-149">Примеры выходных параметров курсора</span><span class="sxs-lookup"><span data-stu-id="13b29-149">Examples of Cursor Output Parameters</span></span>  
 <span data-ttu-id="13b29-150">В следующем примере создается процедура, которая указывает выходной параметр `@currency` _ `cursor` с использованием `cursor` типа данных.</span><span class="sxs-lookup"><span data-stu-id="13b29-150">In the following example, a procedure is created that specified an output parameter, `@currency`_`cursor` using the `cursor` data type.</span></span> <span data-ttu-id="13b29-151">Процедура затем будет вызвана из пакета.</span><span class="sxs-lookup"><span data-stu-id="13b29-151">The procedure is then called in a batch.</span></span>  
  
 <span data-ttu-id="13b29-152">Сначала создайте процедуру, которая объявляет и затем открывает курсор в таблице Currency.</span><span class="sxs-lookup"><span data-stu-id="13b29-152">First, create the procedure that declares and then opens a cursor on the Currency table.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'dbo.uspCurrencyCursor', 'P' ) IS NOT NULL  
    DROP PROCEDURE dbo.uspCurrencyCursor;  
GO  
CREATE PROCEDURE dbo.uspCurrencyCursor   
    @CurrencyCursor CURSOR VARYING OUTPUT  
AS  
    SET NOCOUNT ON;  
    SET @CurrencyCursor = CURSOR  
    FORWARD_ONLY STATIC FOR  
      SELECT CurrencyCode, Name  
      FROM Sales.Currency;  
    OPEN @CurrencyCursor;  
GO  
  
```  
  
 <span data-ttu-id="13b29-153">Затем выполните пакет, который объявляет локальную переменную курсора, выполняет процедуру, присваивающую курсор локальной переменной, и затем выбирает строки из курсора.</span><span class="sxs-lookup"><span data-stu-id="13b29-153">Next, execute a batch that declares a local cursor variable, executes the procedure to assign the cursor to the local variable, and then fetches the rows from the cursor.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @MyCursor CURSOR;  
EXEC dbo.uspCurrencyCursor @CurrencyCursor = @MyCursor OUTPUT;  
WHILE (@@FETCH_STATUS = 0)  
BEGIN;  
     FETCH NEXT FROM @MyCursor;  
END;  
CLOSE @MyCursor;  
DEALLOCATE @MyCursor;  
GO  
  
```  
  
## <a name="returning-data-using-a-return-code"></a><span data-ttu-id="13b29-154">Возврат данных с использованием кода возврата</span><span class="sxs-lookup"><span data-stu-id="13b29-154">Returning Data Using a Return Code</span></span>  
 <span data-ttu-id="13b29-155">Процедура может возвращать целочисленное значение, называемое кодом возврата, чтобы указать состояние выполнения процедуры.</span><span class="sxs-lookup"><span data-stu-id="13b29-155">A procedure can return an integer value called a return code to indicate the execution status of a procedure.</span></span> <span data-ttu-id="13b29-156">Код возврата для процедуры указывается при помощи инструкции RETURN.</span><span class="sxs-lookup"><span data-stu-id="13b29-156">You specify the return code for a procedure using the RETURN statement.</span></span> <span data-ttu-id="13b29-157">Как и выходные параметры, при выполнении процедуры код возврата необходимо сохранить в переменной, чтобы использовать это значение в вызывающей программе.</span><span class="sxs-lookup"><span data-stu-id="13b29-157">As with OUTPUT parameters, you must save the return code in a variable when the procedure is executed in order to use the return code value in the calling program.</span></span> <span data-ttu-id="13b29-158">Например, переменная присваивания `@result` типа данных `int` используется для хранения кода возврата из процедуры `my_proc` , например:</span><span class="sxs-lookup"><span data-stu-id="13b29-158">For example, the assignment variable `@result` of data type `int` is used to store the return code from the procedure `my_proc`, such as:</span></span>  
  
```  
DECLARE @result int;  
EXECUTE @result = my_proc;  
```  
  
 <span data-ttu-id="13b29-159">Коды возврата часто применяются в блоках управления потоком процедур для присвоения кода возврата каждой из возможных ошибок.</span><span class="sxs-lookup"><span data-stu-id="13b29-159">Return codes are commonly used in control-of-flow blocks within procedures to set the return code value for each possible error situation.</span></span> <span data-ttu-id="13b29-160">Чтобы выяснить, произошла ли во время выполнения инструкции ошибка, запустите функцию @@ERROR после инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13b29-160">You can use the @@ERROR function after a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement to detect whether an error occurred during the execution of the statement.</span></span>  
  
### <a name="examples-of-return-codes"></a><span data-ttu-id="13b29-161">Примеры кодов возврата</span><span class="sxs-lookup"><span data-stu-id="13b29-161">Examples of Return Codes</span></span>  
 <span data-ttu-id="13b29-162">В следующем примере показана процедура `usp_GetSalesYTD` с обработкой ошибок, устанавливающей специальные значения кода возврата для различных ошибок.</span><span class="sxs-lookup"><span data-stu-id="13b29-162">The following example shows the `usp_GetSalesYTD` procedure with error handling that sets special return code values for various errors.</span></span> <span data-ttu-id="13b29-163">В следующей таблице показано целое число, которое назначается процедурой каждой возможной ошибке, и соответствующее значение каждого числа.</span><span class="sxs-lookup"><span data-stu-id="13b29-163">The following table shows the integer value that is assigned by the procedure to each possible error, and the corresponding meaning for each value.</span></span>  
  
|<span data-ttu-id="13b29-164">Значения кодов возврата</span><span class="sxs-lookup"><span data-stu-id="13b29-164">Return code value</span></span>|<span data-ttu-id="13b29-165">Значение</span><span class="sxs-lookup"><span data-stu-id="13b29-165">Meaning</span></span>|  
|-----------------------|-------------|  
|<span data-ttu-id="13b29-166">0</span><span class="sxs-lookup"><span data-stu-id="13b29-166">0</span></span>|<span data-ttu-id="13b29-167">Выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="13b29-167">Successful execution.</span></span>|  
|<span data-ttu-id="13b29-168">1</span><span class="sxs-lookup"><span data-stu-id="13b29-168">1</span></span>|<span data-ttu-id="13b29-169">Требуемое значение параметра не указано.</span><span class="sxs-lookup"><span data-stu-id="13b29-169">Required parameter value is not specified.</span></span>|  
|<span data-ttu-id="13b29-170">2</span><span class="sxs-lookup"><span data-stu-id="13b29-170">2</span></span>|<span data-ttu-id="13b29-171">Требуемое значение параметра не допустимо.</span><span class="sxs-lookup"><span data-stu-id="13b29-171">Specified parameter value is not valid.</span></span>|  
|<span data-ttu-id="13b29-172">3</span><span class="sxs-lookup"><span data-stu-id="13b29-172">3</span></span>|<span data-ttu-id="13b29-173">Произошла ошибка при получении значения продаж.</span><span class="sxs-lookup"><span data-stu-id="13b29-173">Error has occurred getting sales value.</span></span>|  
|<span data-ttu-id="13b29-174">4</span><span class="sxs-lookup"><span data-stu-id="13b29-174">4</span></span>|<span data-ttu-id="13b29-175">Найдено значение NULL для продаж данного менеджера.</span><span class="sxs-lookup"><span data-stu-id="13b29-175">NULL sales value found for the salesperson.</span></span>|  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.usp_GetSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.usp_GetSalesYTD;  
GO  
CREATE PROCEDURE Sales.usp_GetSalesYTD  
@SalesPerson nvarchar(50) = NULL,  -- NULL default value  
@SalesYTD money = NULL OUTPUT  
AS    
  
-- Validate the @SalesPerson parameter.  
IF @SalesPerson IS NULL  
   BEGIN  
       PRINT 'ERROR: You must specify a last name for the sales person.'  
       RETURN(1)  
   END  
ELSE  
   BEGIN  
   -- Make sure the value is valid.  
   IF (SELECT COUNT(*) FROM HumanResources.vEmployee  
          WHERE LastName = @SalesPerson) = 0  
      RETURN(2)  
   END  
-- Get the sales for the specified name and   
-- assign it to the output parameter.  
SELECT @SalesYTD = SalesYTD   
FROM Sales.SalesPerson AS sp  
JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
WHERE LastName = @SalesPerson;  
-- Check for SQL Server errors.  
IF @@ERROR <> 0   
   BEGIN  
      RETURN(3)  
   END  
ELSE  
   BEGIN  
   -- Check to see if the ytd_sales value is NULL.  
     IF @SalesYTD IS NULL  
       RETURN(4)   
     ELSE  
      -- SUCCESS!!  
        RETURN(0)  
   END  
-- Run the stored procedure without specifying an input value.  
EXEC Sales.usp_GetSalesYTD;  
GO  
-- Run the stored procedure with an input value.  
DECLARE @SalesYTDForSalesPerson money, @ret_code int;  
-- Execute the procedure specifying a last name for the input parameter  
-- and saving the output value in the variable @SalesYTD  
EXECUTE Sales.usp_GetSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDForSalesPerson OUTPUT;  
PRINT N'Year-to-date sales for this employee is ' +  
    CONVERT(varchar(10), @SalesYTDForSalesPerson);  
  
```  
  
 <span data-ttu-id="13b29-176">Следующий пример создает программу обработки кодов возврата, которые возвращаются процедурой `usp_GetSalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="13b29-176">The following example creates a program to handle the return codes that are returned from the `usp_GetSalesYTD` procedure.</span></span>  
  
```  
-- Declare the variables to receive the output value and return code   
-- of the procedure.  
DECLARE @SalesYTDForSalesPerson money, @ret_code int;  
  
-- Execute the procedure with a title_id value  
-- and save the output value and return code in variables.  
EXECUTE @ret_code = Sales.usp_GetSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDForSalesPerson OUTPUT;  
--  Check the return codes.  
IF @ret_code = 0  
BEGIN  
   PRINT 'Procedure executed successfully'  
   -- Display the value returned by the procedure.  
   PRINT 'Year-to-date sales for this employee is ' + CONVERT(varchar(10),@SalesYTDForSalesPerson)  
END  
ELSE IF @ret_code = 1  
   PRINT 'ERROR: You must specify a last name for the sales person.'  
ELSE IF @ret_code = 2   
   PRINT 'EERROR: You must enter a valid last name for the sales person.'  
ELSE IF @ret_code = 3  
   PRINT 'ERROR: An error occurred getting sales value.'  
ELSE IF @ret_code = 4  
   PRINT 'ERROR: No sales recorded for this employee.'     
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="13b29-177">См. также:</span><span class="sxs-lookup"><span data-stu-id="13b29-177">See Also</span></span>  
 <span data-ttu-id="13b29-178">[DECLARE @local_variable (Transact-SQL)](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="13b29-178">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="13b29-179">[PRINT (Transact-SQL)](/sql/t-sql/language-elements/print-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="13b29-179">[PRINT &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/print-transact-sql) </span></span>  
 <span data-ttu-id="13b29-180">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="13b29-180">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="13b29-181">[Курсоры](../cursors.md) </span><span class="sxs-lookup"><span data-stu-id="13b29-181">[Cursors](../cursors.md) </span></span>  
 <span data-ttu-id="13b29-182">[RETURN (Transact-SQL)](/sql/t-sql/language-elements/return-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="13b29-182">[RETURN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/return-transact-sql) </span></span>  
 [<span data-ttu-id="13b29-183">@@ERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="13b29-183">@@ERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/error-transact-sql)  
  
  
