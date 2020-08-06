---
title: Перекомпиляция хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- sp_recompile
- WITH RECOMPILE clause
- recompiling stored procedures
- stored procedures [SQL Server], recompiling
ms.assetid: b90deb27-0099-4fe7-ba60-726af78f7c18
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2a9bc0e1d4baecb7f4c66b83b57081ed3131123d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669375"
---
# <a name="recompile-a-stored-procedure"></a><span data-ttu-id="838b7-102">Перекомпиляция хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="838b7-102">Recompile a Stored Procedure</span></span>
  <span data-ttu-id="838b7-103">В этом разделе описывается, как перекомпилировать хранимую процедуру в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="838b7-103">This topic describes how to recompile a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="838b7-104">Это можно сделать тремя способами: `WITH RECOMPILE` параметр в определении процедуры или при вызове процедуры, `RECOMPILE` Указание запроса для отдельных инструкций или использование `sp_recompile` системной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="838b7-104">There are three ways to do this: `WITH RECOMPILE` option in the procedure definition or when the procedure is called, the `RECOMPILE` query hint on individual statements, or by using the `sp_recompile` system stored procedure.</span></span> <span data-ttu-id="838b7-105">В этом разделе описывается использование параметра WITH RECOMPILE при создании определения процедуры и выполнении существующей процедуры.</span><span class="sxs-lookup"><span data-stu-id="838b7-105">This topic describes using the WITH RECOMPILE option when creating a procedure definition and executing an existing procedure.</span></span> <span data-ttu-id="838b7-106">Также описывается использование системной хранимой процедуры sp_recompile для перекомпиляции существующей процедуры.</span><span class="sxs-lookup"><span data-stu-id="838b7-106">It also describes using the sp_recompile system stored procedure to recompile an existing procedure.</span></span>  
  
 <span data-ttu-id="838b7-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="838b7-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="838b7-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="838b7-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="838b7-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="838b7-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="838b7-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="838b7-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="838b7-111">**Для перекомпиляции хранимой процедуры используется:**</span><span class="sxs-lookup"><span data-stu-id="838b7-111">**To recompile a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="838b7-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="838b7-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="838b7-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="838b7-113">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="838b7-114">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="838b7-114">Recommendations</span></span>  
  
-   <span data-ttu-id="838b7-115">Когда процедура компилируется впервые или повторно, выполняется оптимизация плана запроса процедуры для текущего состояния базы данных и ее объектов.</span><span class="sxs-lookup"><span data-stu-id="838b7-115">When a procedure is compiled for the first time or recompiled, the procedure's query plan is optimized for the current state of the database and its objects.</span></span> <span data-ttu-id="838b7-116">Если данные или структура базы данных подвергаются значительным изменениям, то при перекомпиляции процедуры ее план запроса обновляется и оптимизируется в соответствии с этими изменениями.</span><span class="sxs-lookup"><span data-stu-id="838b7-116">If a database undergoes significant changes to its data or structure, recompiling a procedure updates and optimizes the procedure's query plan for those changes.</span></span> <span data-ttu-id="838b7-117">Это может повысить производительность обработки процедуры.</span><span class="sxs-lookup"><span data-stu-id="838b7-117">This can improve the procedure's processing performance.</span></span>  
  
-   <span data-ttu-id="838b7-118">Иногда необходимо принудительно выполнить перекомпиляцию процедуры, а иногда это выполняется автоматически.</span><span class="sxs-lookup"><span data-stu-id="838b7-118">There are times when procedure recompilation must be forced and other times when it occurs automatically.</span></span> <span data-ttu-id="838b7-119">Автоматическая перекомпиляция выполняется при каждом перезапуске [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="838b7-119">Automatic recompiling occurs whenever [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is restarted.</span></span> <span data-ttu-id="838b7-120">Она также проводится, если в базовой таблице, на которую ссылается процедура, происходят изменения физической структуры.</span><span class="sxs-lookup"><span data-stu-id="838b7-120">It also occurs if an underlying table referenced by the procedure has undergone physical design changes.</span></span>  
  
-   <span data-ttu-id="838b7-121">Другая причина для принудительного перекомпилирования процедуры — это нейтрализация пробного сохранения параметров при компиляции процедуры.</span><span class="sxs-lookup"><span data-stu-id="838b7-121">Another reason to force a procedure to recompile is to counteract the "parameter sniffing" behavior of procedure compilation.</span></span> <span data-ttu-id="838b7-122">Когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняет процедуры, значения всех используемых при компиляции параметров включаются в формируемый план запроса.</span><span class="sxs-lookup"><span data-stu-id="838b7-122">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes procedures, any parameter values that are used by the procedure when it compiles are included as part of generating the query plan.</span></span> <span data-ttu-id="838b7-123">Если эти значения типичны для последующих вызовов процедуры, то компиляция и выполнение хранимой процедуры с этим планом запроса происходит быстрее.</span><span class="sxs-lookup"><span data-stu-id="838b7-123">If these values represent the typical ones with which the procedure is subsequently called, then the procedure benefits from the query plan every time that it compiles and executes.</span></span> <span data-ttu-id="838b7-124">Если значения параметров для процедуры часто оказываются нетипичными, то принудительная перекомпиляция процедуры и создание нового плана на основе других значений параметров может повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="838b7-124">If parameter values on the procedure are frequently atypical, forcing a recompile of the procedure and a new plan based on different parameter values can improve performance.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="838b7-125">обладает возможностью перекомпиляции процедур на уровне инструкций.</span><span class="sxs-lookup"><span data-stu-id="838b7-125">features statement-level recompilation of procedures.</span></span> <span data-ttu-id="838b7-126">Во время перекомпиляции хранимой процедуры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] заново компилирует только вызвавшую этот процесс инструкцию, а не всю процедуру.</span><span class="sxs-lookup"><span data-stu-id="838b7-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recompiles stored procedures, only the statement that caused the recompilation is compiled, instead of the complete procedure.</span></span>  
  
-   <span data-ttu-id="838b7-127">Если некоторые запросы в процедуре регулярно используют нетипичные или временные значения, то можно повысить производительность процедуры, используя указание запроса RECOMPILE в таких запросах.</span><span class="sxs-lookup"><span data-stu-id="838b7-127">If certain queries in a procedure regularly use atypical or temporary values, procedure performance can be improved by using the RECOMPILE query hint inside those queries.</span></span> <span data-ttu-id="838b7-128">Поскольку перекомпиляцию будут проходить только запросы, использующие это указание, а не вся процедура, то повторная компиляция [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]будет работать на уровне инструкций.</span><span class="sxs-lookup"><span data-stu-id="838b7-128">Since only the queries using the query hint will be recompiled instead of the complete procedure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]'s statement-level recompilation behavior is mimicked.</span></span> <span data-ttu-id="838b7-129">Однако, помимо использования текущих значений параметров процедуры, указание запроса RECOMPILE при компиляции инструкции также использует значения локальных переменных в хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="838b7-129">But in addition to using the procedure's current parameter values, the RECOMPILE query hint also uses the values of any local variables inside the stored procedure when you compile the statement.</span></span> <span data-ttu-id="838b7-130">Дополнительные сведения см. в разделе [Указания запросов (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span><span class="sxs-lookup"><span data-stu-id="838b7-130">For more information, see [Query Hint (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="838b7-131">безопасность</span><span class="sxs-lookup"><span data-stu-id="838b7-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="838b7-132">Permissions</span><span class="sxs-lookup"><span data-stu-id="838b7-132">Permissions</span></span>  
 <span data-ttu-id="838b7-133">`WITH RECOMPILE`Функцию</span><span class="sxs-lookup"><span data-stu-id="838b7-133">`WITH RECOMPILE` Option</span></span>  
 <span data-ttu-id="838b7-134">Если этот параметр используется при создании определения процедуры, то необходимо разрешение CREATE PROCEDURE в базе данных и разрешение ALTER на схему, в которой создается процедура.</span><span class="sxs-lookup"><span data-stu-id="838b7-134">If this option is used when the procedure definition is created, it requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
 <span data-ttu-id="838b7-135">Если этот параметр используется в инструкции EXECUTE, требуются разрешения EXECUTE на процедуру.</span><span class="sxs-lookup"><span data-stu-id="838b7-135">If this option is used in an EXECUTE statement, it requires EXECUTE permissions on the procedure.</span></span> <span data-ttu-id="838b7-136">Разрешения на саму инструкцию EXECUTE не требуются, однако требуются разрешения на выполнение процедуры, упоминаемой в инструкции EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="838b7-136">Permissions are not required on the EXECUTE statement itself but execute permissions are required on the procedure referenced in the EXECUTE statement.</span></span> <span data-ttu-id="838b7-137">Дополнительные сведения см. в разделе [EXECUTE (Transact-SQL)](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="838b7-137">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
 <span data-ttu-id="838b7-138">`RECOMPILE`Указание запроса</span><span class="sxs-lookup"><span data-stu-id="838b7-138">`RECOMPILE` Query Hint</span></span>  
 <span data-ttu-id="838b7-139">Эта возможность используется при создании процедуры, и указание включается в инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] в процедуре.</span><span class="sxs-lookup"><span data-stu-id="838b7-139">This feature is used when the procedure is created and the hint is included in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the procedure.</span></span> <span data-ttu-id="838b7-140">Таким образом, требуется разрешение CREATE PROCEDURE в базе данных и разрешение ALTER на схему, в которой создается процедура.</span><span class="sxs-lookup"><span data-stu-id="838b7-140">Therefore, it requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
 <span data-ttu-id="838b7-141">`sp_recompile`Системная хранимая процедура</span><span class="sxs-lookup"><span data-stu-id="838b7-141">`sp_recompile` System Stored Procedure</span></span>  
 <span data-ttu-id="838b7-142">Необходимо разрешение ALTER на указанную процедуру.</span><span class="sxs-lookup"><span data-stu-id="838b7-142">Requires ALTER permission on the specified procedure.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="838b7-143">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="838b7-143">Using Transact-SQL</span></span>  
  
#### <a name="to-recompile-a-stored-procedure-by-using-the-with-recompile-option"></a><span data-ttu-id="838b7-144">Перекомпиляция хранимой процедуры с использованием параметра WITH RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="838b7-144">To recompile a stored procedure by using the WITH RECOMPILE option</span></span>  
  
1.  <span data-ttu-id="838b7-145">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="838b7-145">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="838b7-146">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="838b7-146">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="838b7-147">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="838b7-147">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="838b7-148">В этом примере создается определение процедуры.</span><span class="sxs-lookup"><span data-stu-id="838b7-148">This example creates the procedure definition.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'dbo.uspProductByVendor', 'P' ) IS NOT NULL   
    DROP PROCEDURE dbo.uspProductByVendor;  
GO  
CREATE PROCEDURE dbo.uspProductByVendor @Name varchar(30) = '%'  
WITH RECOMPILE  
AS  
    SET NOCOUNT ON;  
    SELECT v.Name AS 'Vendor name', p.Name AS 'Product name'  
    FROM Purchasing.Vendor AS v   
    JOIN Purchasing.ProductVendor AS pv   
      ON v.BusinessEntityID = pv.BusinessEntityID   
    JOIN Production.Product AS p   
      ON pv.ProductID = p.ProductID  
    WHERE v.Name LIKE @Name;  
  
```  
  
#### <a name="to-recompile-a-stored-procedure-by-using-the-with-recompile-option"></a><span data-ttu-id="838b7-149">Перекомпиляция хранимой процедуры с использованием параметра WITH RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="838b7-149">To recompile a stored procedure by using the WITH RECOMPILE option</span></span>  
  
1.  <span data-ttu-id="838b7-150">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="838b7-150">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="838b7-151">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="838b7-151">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="838b7-152">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="838b7-152">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="838b7-153">В этом примере создается простая процедура, возвращающая из представления всех сотрудников (с указанием имени и фамилии), их должности и названия отделов.</span><span class="sxs-lookup"><span data-stu-id="838b7-153">This example creates a simple procedure that returns all employees (first and last names supplied), their job titles, and their department names from a view.</span></span>  
  
     <span data-ttu-id="838b7-154">Затем скопируйте второй пример кода в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="838b7-154">And then copy and paste the second code example into the query window and click **Execute**.</span></span> <span data-ttu-id="838b7-155">Процедура будет выполнена с повторной компиляцией плана запроса.</span><span class="sxs-lookup"><span data-stu-id="838b7-155">This executes the procedure and recompiles the procedure's query plan.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXECUTE HumanResources.uspGetAllEmployees WITH RECOMPILE;  
GO  
  
```  
  
#### <a name="to-recompile-a-stored-procedure-by-using-sp_recompile"></a><span data-ttu-id="838b7-156">Перекомпиляция хранимой процедуры с использованием процедуры sp_recompile</span><span class="sxs-lookup"><span data-stu-id="838b7-156">To recompile a stored procedure by using sp_recompile</span></span>  
  
1.  <span data-ttu-id="838b7-157">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="838b7-157">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="838b7-158">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="838b7-158">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="838b7-159">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="838b7-159">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="838b7-160">В этом примере создается простая процедура, возвращающая из представления всех сотрудников (с указанием имени и фамилии), их должности и названия отделов.</span><span class="sxs-lookup"><span data-stu-id="838b7-160">This example creates a simple procedure that returns all employees (first and last names supplied), their job titles, and their department names from a view.</span></span>  
  
     <span data-ttu-id="838b7-161">Затем скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="838b7-161">Then, copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="838b7-162">Процедура не будет выполнена, но будет помечена для повторной компиляции, и при следующем выполнении процедуры ее план запроса будет обновлен.</span><span class="sxs-lookup"><span data-stu-id="838b7-162">This does not execute the procedure but it does mark the procedure to be recompiled so that its query plan is updated the next time that the procedure is executed.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_recompile N'HumanResources.uspGetAllEmployees';  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="838b7-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="838b7-163">See Also</span></span>  
 <span data-ttu-id="838b7-164">[Создание хранимой процедуры](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="838b7-164">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="838b7-165">[Изменение хранимой процедуры](../stored-procedures/modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="838b7-165">[Modify a Stored Procedure](../stored-procedures/modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="838b7-166">[Изменение имени хранимой процедуры](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="838b7-166">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="838b7-167">[Просмотр определения хранимой процедуры](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="838b7-167">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="838b7-168">[Просмотр зависимостей хранимой процедуры](view-the-dependencies-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="838b7-168">[View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="838b7-169">DROP PROCEDURE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="838b7-169">DROP PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-procedure-transact-sql)  
  
  
