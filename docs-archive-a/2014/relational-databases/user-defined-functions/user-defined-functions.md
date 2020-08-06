---
title: Определяемые пользователем функции | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- user-defined functions [SQL Server], components
- user-defined functions [SQL Server], about user-defined functions
ms.assetid: d7ddafab-f5a6-44b0-81d5-ba96425aada4
author: rothja
ms.author: jroth
ms.openlocfilehash: c7e4b1a77f2fe5a13e21d8b3fe59e37931669b30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654104"
---
# <a name="user-defined-functions"></a><span data-ttu-id="af615-102">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="af615-102">User-Defined Functions</span></span>
  <span data-ttu-id="af615-103">Аналогично функциям в языках программирования,  определяемые пользователем функции [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] представляют собой подпрограммы, которые принимают параметры, выполняют действие, например, сложные вычисления, и возвращают результат этого действия в виде значения.</span><span class="sxs-lookup"><span data-stu-id="af615-103">Like functions in programming languages, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined functions are routines that accept parameters, perform an action, such as a complex calculation, and return the result of that action as a value.</span></span> <span data-ttu-id="af615-104">Возвращаемое значение может быть либо единичным скалярным значением, либо результирующим набором.</span><span class="sxs-lookup"><span data-stu-id="af615-104">The return value can either be a single scalar value or a result set.</span></span>  
  
 <span data-ttu-id="af615-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="af615-105">**In This Topic**</span></span>  
  
 [<span data-ttu-id="af615-106">Преимущества определяемых пользователем функций</span><span class="sxs-lookup"><span data-stu-id="af615-106">User-defined Function Benefits</span></span>](#Benefits)  
  
 [<span data-ttu-id="af615-107">Типы функций</span><span class="sxs-lookup"><span data-stu-id="af615-107">Types of Functions</span></span>](#FunctionTypes)  
  
 [<span data-ttu-id="af615-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="af615-108">Guidelines</span></span>](#Guidelines)  
  
 [<span data-ttu-id="af615-109">Допустимые инструкции в функции</span><span class="sxs-lookup"><span data-stu-id="af615-109">Valid Statements in a Function</span></span>](#ValidStatements)  
  
 [<span data-ttu-id="af615-110">Привязанные к схеме функции</span><span class="sxs-lookup"><span data-stu-id="af615-110">Schema Bound Functions</span></span>](#SchemaBound)  
  
 [<span data-ttu-id="af615-111">Указание параметров</span><span class="sxs-lookup"><span data-stu-id="af615-111">Specifying Parameters</span></span>](#Parameters)  
  
 [<span data-ttu-id="af615-112">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="af615-112">Related Tasks</span></span>](#Tasks)  
  
##  <a name="user-defined-function-benefits"></a><a name="Benefits"></a><span data-ttu-id="af615-113">Преимущества определяемых пользователем функций</span><span class="sxs-lookup"><span data-stu-id="af615-113">User-defined Function Benefits</span></span>  
 <span data-ttu-id="af615-114">Определяемые пользователем функции [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предоставляют следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="af615-114">The benefits of using user-defined functions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are:</span></span>  
  
-   <span data-ttu-id="af615-115">Делают возможным модульное программирование.</span><span class="sxs-lookup"><span data-stu-id="af615-115">They allow modular programming.</span></span>  
  
     <span data-ttu-id="af615-116">Можно, однажды создав функцию, сохранить ее в базе данных, а затем любое число раз вызывать из своей программы.</span><span class="sxs-lookup"><span data-stu-id="af615-116">You can create the function once, store it in the database, and call it any number of times in your program.</span></span> <span data-ttu-id="af615-117">Определяемые пользователем функции могут быть изменены независимо от исходного кода программы.</span><span class="sxs-lookup"><span data-stu-id="af615-117">User-defined functions can be modified independently of the program source code.</span></span>  
  
-   <span data-ttu-id="af615-118">Позволяют ускорить выполнение.</span><span class="sxs-lookup"><span data-stu-id="af615-118">They allow faster execution.</span></span>  
  
     <span data-ttu-id="af615-119">Как и хранимые процедуры, определяемые пользователем функции [!INCLUDE[tsql](../../includes/tsql-md.md)] снижают стоимость компиляции кода [!INCLUDE[tsql](../../includes/tsql-md.md)], кэшируя и повторно используя планы выполнения.</span><span class="sxs-lookup"><span data-stu-id="af615-119">Similar to stored procedures, [!INCLUDE[tsql](../../includes/tsql-md.md)] user-defined functions reduce the compilation cost of [!INCLUDE[tsql](../../includes/tsql-md.md)] code by caching the plans and reusing them for repeated executions.</span></span> <span data-ttu-id="af615-120">Это означает, что для определяемых пользователем функций нет необходимости выполнять повторный синтаксический анализ и оптимизацию при каждом вызове, что значительно ускоряет их выполнение.</span><span class="sxs-lookup"><span data-stu-id="af615-120">This means the user-defined function does not need to be reparsed and reoptimized with each use resulting in much faster execution times.</span></span>  
  
     <span data-ttu-id="af615-121">Функции CLR дают значительное преимущество в производительности по сравнению с функциями [!INCLUDE[tsql](../../includes/tsql-md.md)] для вычислительных задач, работы со строками и бизнес-логикой.</span><span class="sxs-lookup"><span data-stu-id="af615-121">CLR functions offer significant performance advantage over [!INCLUDE[tsql](../../includes/tsql-md.md)] functions for computational tasks, string manipulation, and business logic.</span></span> <span data-ttu-id="af615-122">Функции [!INCLUDE[tsql](../../includes/tsql-md.md)] лучше подходят для логики с интенсивным доступом к данным.</span><span class="sxs-lookup"><span data-stu-id="af615-122">[!INCLUDE[tsql](../../includes/tsql-md.md)] functions are better suited for data-access intensive logic.</span></span>  
  
-   <span data-ttu-id="af615-123">Позволяют уменьшить сетевой трафик.</span><span class="sxs-lookup"><span data-stu-id="af615-123">They can reduce network traffic.</span></span>  
  
     <span data-ttu-id="af615-124">Операция, которая фильтрует данные на основе какого-нибудь сложного ограничения и не может быть выражена одним скалярным выражением, может быть реализована в виде функции.</span><span class="sxs-lookup"><span data-stu-id="af615-124">An operation that filters data based on some complex constraint that cannot be expressed in a single scalar expression can be expressed as a function.</span></span> <span data-ttu-id="af615-125">Ее можно вызвать из предложения WHERE, чтобы уменьшить число строк, возвращаемых клиенту.</span><span class="sxs-lookup"><span data-stu-id="af615-125">The function can then invoked in the WHERE clause to reduce the number or rows sent to the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af615-126">Определяемые пользователем функции [!INCLUDE[tsql](../../includes/tsql-md.md)] в запросах могут выполняться только как один поток (план последовательного выполнения).</span><span class="sxs-lookup"><span data-stu-id="af615-126">[!INCLUDE[tsql](../../includes/tsql-md.md)] user-defined functions in queries can only be executed on a single thread (serial execution plan).</span></span>  
  
##  <a name="types-of-functions"></a><a name="FunctionTypes"></a><span data-ttu-id="af615-127">Типы функций</span><span class="sxs-lookup"><span data-stu-id="af615-127">Types of Functions</span></span>  
 <span data-ttu-id="af615-128">Скалярная функция</span><span class="sxs-lookup"><span data-stu-id="af615-128">Scalar Function</span></span>  
 <span data-ttu-id="af615-129">Пользовательские скалярные функции возвращают одно значение типа данных, заданного в предложении RETURNS.</span><span class="sxs-lookup"><span data-stu-id="af615-129">User-defined scalar functions return a single data value of the type defined in the RETURNS clause.</span></span> <span data-ttu-id="af615-130">Встроенная скалярная функция не имеет тела, скалярное значение является результатом одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="af615-130">For an inline scalar function, there is no function body; the scalar value is the result of a single statement.</span></span> <span data-ttu-id="af615-131">Скалярная функция из нескольких инструкций имеет текст, ограниченное блоком BEGIN...END, и содержит последовательность инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] , возвращающих одно значение.</span><span class="sxs-lookup"><span data-stu-id="af615-131">For a multistatement scalar function, the function body, defined in a BEGIN...END block, contains a series of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that return the single value.</span></span> <span data-ttu-id="af615-132">Такие функции могут возвращать любые типы данных, кроме `text`, `ntext`, `image`, `cursor` и `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="af615-132">The return type can be any data type except `text`, `ntext`, `image`, `cursor`, and `timestamp`.</span></span>  
  
 <span data-ttu-id="af615-133">Функции с табличными значениями</span><span class="sxs-lookup"><span data-stu-id="af615-133">Table-Valued Functions</span></span>  
 <span data-ttu-id="af615-134">Определяемые пользователем функции с табличным значением возвращают значение типа `table`.</span><span class="sxs-lookup"><span data-stu-id="af615-134">User-defined table-valued functions return a `table` data type.</span></span> <span data-ttu-id="af615-135">Встроенная функция с табличным значением не имеет текста, таблица является результирующим набором одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="af615-135">For an inline table-valued function, there is no function body; the table is the result set of a single SELECT statement.</span></span>  
  
 <span data-ttu-id="af615-136">Системные функции</span><span class="sxs-lookup"><span data-stu-id="af615-136">System Functions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="af615-137">предоставляет множество системных функций для выполнения различных операций.</span><span class="sxs-lookup"><span data-stu-id="af615-137">provides many system functions that you can use to perform a variety of operations.</span></span> <span data-ttu-id="af615-138">Их нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="af615-138">They cannot be modified.</span></span> <span data-ttu-id="af615-139">Дополнительные сведения см. в разделах [Встроенные функции (Transact-SQL)](/sql/t-sql/functions/functions), [Системные хранимые функции (Transact-SQL)](/sql/relational-databases/system-functions/system-functions-for-transact-sql) и [Динамические административные представления и функции (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/system-dynamic-management-views).</span><span class="sxs-lookup"><span data-stu-id="af615-139">For more information, see [Built-in Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/functions), [System Stored Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/system-functions-for-transact-sql), and [Dynamic Management Views and Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/system-dynamic-management-views).</span></span>  
  
##  <a name="guidelines"></a><a name="Guidelines"></a> <span data-ttu-id="af615-140">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="af615-140">Guidelines</span></span>  
 <span data-ttu-id="af615-141">Ошибки [!INCLUDE[tsql](../../includes/tsql-md.md)], которые вызывают отмену инструкции и продолжение выполнения со следующей инструкции в модуле (например в триггере или хранимой процедуре), внутри функций обрабатываются иначе.</span><span class="sxs-lookup"><span data-stu-id="af615-141">[!INCLUDE[tsql](../../includes/tsql-md.md)] errors that cause a statement to be canceled and continue with the next statement in the module (such as triggers or stored procedures) are treated differently inside a function.</span></span> <span data-ttu-id="af615-142">В функциях такие ошибки вызывают остановку выполнения функции.</span><span class="sxs-lookup"><span data-stu-id="af615-142">In functions, such errors cause the execution of the function to stop.</span></span> <span data-ttu-id="af615-143">Это вызывает отмену инструкции, вызвавшей функцию.</span><span class="sxs-lookup"><span data-stu-id="af615-143">This in turn causes the statement that invoked the function to be canceled.</span></span>  
  
 <span data-ttu-id="af615-144">Инструкции в блоке BEGIN...END не могут иметь каких-либо побочных эффектов.</span><span class="sxs-lookup"><span data-stu-id="af615-144">The statements in a BEGIN...END block cannot have any side effects.</span></span> <span data-ttu-id="af615-145">Побочными эффектами функций называются любые постоянные изменения состояния ресурса, область которого лежит за пределами функции, например изменение таблицы базы данных.</span><span class="sxs-lookup"><span data-stu-id="af615-145">Function side effects are any permanent changes to the state of a resource that has a scope outside the function such as a modification to a database table.</span></span> <span data-ttu-id="af615-146">Инструкции внутри функции могут изменять только локальные по отношению к этой функции объекты, например локальные курсоры или переменные.</span><span class="sxs-lookup"><span data-stu-id="af615-146">The only changes that can be made by the statements in the function are changes to objects local to the function, such as local cursors or variables.</span></span> <span data-ttu-id="af615-147">Изменения таблиц баз данных, операции с курсорами, не являющимися локальными для данной функции, отправка электронной почты, попытка изменения каталога, формирование результирующего набора, возвращаемого пользователю — это примеры действий, выполнение которых внутри функции невозможно.</span><span class="sxs-lookup"><span data-stu-id="af615-147">Modifications to database tables, operations on cursors that are not local to the function, sending e-mail, attempting a catalog modification, and generating a result set that is returned to the user are examples of actions that cannot be performed in a function.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af615-148">Если инструкция CREATE FUNCTION создает побочные эффекты в отношении ресурсов, которые не существуют во время применения инструкции CREATE FUNCTION, то [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняет эту инструкцию.</span><span class="sxs-lookup"><span data-stu-id="af615-148">If a CREATE FUNCTION statement produces side effects against resources that do not exist when the CREATE FUNCTION statement is issued, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes the statement.</span></span> <span data-ttu-id="af615-149">Однако [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не выполняет эту функцию при ее вызове.</span><span class="sxs-lookup"><span data-stu-id="af615-149">However, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not execute the function when it is invoked.</span></span>  
  
 <span data-ttu-id="af615-150">Число раз, когда указанная в запросе функция будет фактически выполнена, может различаться для разных планов выполнения, построенных оптимизатором.</span><span class="sxs-lookup"><span data-stu-id="af615-150">The number of times that a function specified in a query is actually executed can vary between execution plans built by the optimizer.</span></span> <span data-ttu-id="af615-151">Примером является функция, вызываемая вложенным запросом в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="af615-151">An example is a function invoked by a subquery in a WHERE clause.</span></span> <span data-ttu-id="af615-152">Число раз, когда вложенный запрос и его функция будут выполнены, может различаться для разных путей доступа, выбираемых оптимизатором.</span><span class="sxs-lookup"><span data-stu-id="af615-152">The number of times the subquery and its function is executed can vary with different access paths chosen by the optimizer.</span></span>  
  
##  <a name="valid-statements-in-a-function"></a><a name="ValidStatements"></a><span data-ttu-id="af615-153">Допустимые инструкции в функции</span><span class="sxs-lookup"><span data-stu-id="af615-153">Valid Statements in a Function</span></span>  
 <span data-ttu-id="af615-154">К типам инструкций, допустимым внутри функций, относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="af615-154">The types of statements that are valid in a function include:</span></span>  
  
-   <span data-ttu-id="af615-155">Инструкции DECLARE, используемые для определения переменных и курсоров, локальных для данной функции.</span><span class="sxs-lookup"><span data-stu-id="af615-155">DECLARE statements can be used to define data variables and cursors that are local to the function.</span></span>  
  
-   <span data-ttu-id="af615-156">Присвоение значений объектам, локальным для данной функции, например присвоение значений скалярным и табличным локальным переменным с помощью инструкции SET.</span><span class="sxs-lookup"><span data-stu-id="af615-156">Assignments of values to objects local to the function, such as using SET to assign values to scalar and table local variables.</span></span>  
  
-   <span data-ttu-id="af615-157">Операции над курсорами, обращающиеся к локальным курсорам и выполняющие их объявление, открытие, закрытие и освобождение внутри функции.</span><span class="sxs-lookup"><span data-stu-id="af615-157">Cursor operations that reference local cursors that are declared, opened, closed, and deallocated in the function.</span></span> <span data-ttu-id="af615-158">Инструкции FETCH, возвращающие данные клиенту, запрещены.</span><span class="sxs-lookup"><span data-stu-id="af615-158">FETCH statements that return data to the client are not allowed.</span></span> <span data-ttu-id="af615-159">Разрешены только инструкции FETCH, присваивающие значения локальным переменным с помощью предложения INTO.</span><span class="sxs-lookup"><span data-stu-id="af615-159">Only FETCH statements that assign values to local variables using the INTO clause are allowed.</span></span>  
  
-   <span data-ttu-id="af615-160">Инструкции управления потоком, за исключением инструкций TRY...CATCH.</span><span class="sxs-lookup"><span data-stu-id="af615-160">Control-of-flow statements except TRY...CATCH statements.</span></span>  
  
-   <span data-ttu-id="af615-161">Инструкции SELECT, содержащие списки выборки с выражениями, присваивающими значения переменным, локальным для данной функции.</span><span class="sxs-lookup"><span data-stu-id="af615-161">SELECT statements containing select lists with expressions that assign values to variables that are local to the function.</span></span>  
  
-   <span data-ttu-id="af615-162">Инструкции UPDATE, INSERT и DELETE, изменяющие табличные переменные, локальные для функции.</span><span class="sxs-lookup"><span data-stu-id="af615-162">UPDATE, INSERT, and DELETE statements modifying table variables that are local to the function.</span></span>  
  
-   <span data-ttu-id="af615-163">Инструкции EXECUTE, вызывающие расширенную хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="af615-163">EXECUTE statements calling an extended stored procedure.</span></span>  
  
### <a name="built-in-system-functions"></a><span data-ttu-id="af615-164">Встроенные системные функции</span><span class="sxs-lookup"><span data-stu-id="af615-164">Built-in System Functions</span></span>  
 <span data-ttu-id="af615-165">Следующие недетерминированные встроенные функции могут быть использованы в определяемых пользователем функциях языка Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="af615-165">The following nondeterministic built-in functions can be used in Transact-SQL user-defined functions.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af615-166">CURRENT_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="af615-166">CURRENT_TIMESTAMP</span></span>|<span data-ttu-id="af615-167">@@MAX_CONNECTIONS</span><span class="sxs-lookup"><span data-stu-id="af615-167">@@MAX_CONNECTIONS</span></span>|  
|<span data-ttu-id="af615-168">GET_TRANSMISSION_STATUS</span><span class="sxs-lookup"><span data-stu-id="af615-168">GET_TRANSMISSION_STATUS</span></span>|<span data-ttu-id="af615-169">@@PACK_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="af615-169">@@PACK_RECEIVED</span></span>|  
|<span data-ttu-id="af615-170">GETDATE</span><span class="sxs-lookup"><span data-stu-id="af615-170">GETDATE</span></span>|<span data-ttu-id="af615-171">@@PACK_SENT</span><span class="sxs-lookup"><span data-stu-id="af615-171">@@PACK_SENT</span></span>|  
|<span data-ttu-id="af615-172">GETUTCDATE</span><span class="sxs-lookup"><span data-stu-id="af615-172">GETUTCDATE</span></span>|<span data-ttu-id="af615-173">@@PACKET_ERRORS</span><span class="sxs-lookup"><span data-stu-id="af615-173">@@PACKET_ERRORS</span></span>|  
|<span data-ttu-id="af615-174">@@CONNECTIONS</span><span class="sxs-lookup"><span data-stu-id="af615-174">@@CONNECTIONS</span></span>|<span data-ttu-id="af615-175">@@TIMETICKS</span><span class="sxs-lookup"><span data-stu-id="af615-175">@@TIMETICKS</span></span>|  
|<span data-ttu-id="af615-176">@@CPU_BUSY</span><span class="sxs-lookup"><span data-stu-id="af615-176">@@CPU_BUSY</span></span>|<span data-ttu-id="af615-177">@@TOTAL_ERRORS</span><span class="sxs-lookup"><span data-stu-id="af615-177">@@TOTAL_ERRORS</span></span>|  
|<span data-ttu-id="af615-178">@@DBTS</span><span class="sxs-lookup"><span data-stu-id="af615-178">@@DBTS</span></span>|<span data-ttu-id="af615-179">@@TOTAL_READ</span><span class="sxs-lookup"><span data-stu-id="af615-179">@@TOTAL_READ</span></span>|  
|<span data-ttu-id="af615-180">@@IDLE</span><span class="sxs-lookup"><span data-stu-id="af615-180">@@IDLE</span></span>|<span data-ttu-id="af615-181">@@TOTAL_WRITE</span><span class="sxs-lookup"><span data-stu-id="af615-181">@@TOTAL_WRITE</span></span>|  
|<span data-ttu-id="af615-182">@@IO_BUSY</span><span class="sxs-lookup"><span data-stu-id="af615-182">@@IO_BUSY</span></span>||  
  
 <span data-ttu-id="af615-183">Следующие недетерминированные встроенные функции в определяемых пользователем функциях на языке Transact-SQL использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="af615-183">The following nondeterministic built-in functions cannot be used in Transact-SQL user-defined functions.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af615-184">NEWID</span><span class="sxs-lookup"><span data-stu-id="af615-184">NEWID</span></span>|<span data-ttu-id="af615-185">RAND</span><span class="sxs-lookup"><span data-stu-id="af615-185">RAND</span></span>|  
|<span data-ttu-id="af615-186">NEWSEQUENTIALID</span><span class="sxs-lookup"><span data-stu-id="af615-186">NEWSEQUENTIALID</span></span>|<span data-ttu-id="af615-187">TEXTPTR</span><span class="sxs-lookup"><span data-stu-id="af615-187">TEXTPTR</span></span>|  
  
 <span data-ttu-id="af615-188">Список детерминированных и недетерминированных встроенных системных функций см. в разделе [Детерминированные и недетерминированные функции](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span><span class="sxs-lookup"><span data-stu-id="af615-188">For a list of deterministic and nondeterministic built-in system functions, see [Deterministic and Nondeterministic Functions](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span></span>  
  
##  <a name="schema-bound-functions"></a><a name="SchemaBound"></a><span data-ttu-id="af615-189">Функции, привязанные к схеме</span><span class="sxs-lookup"><span data-stu-id="af615-189">Schema-Bound Functions</span></span>  
 <span data-ttu-id="af615-190">Инструкция CREATE FUNCTION поддерживает предложение SCHEMABINDING, позволяющее привязать функцию к схеме каких-либо объектов, на которые она ссылается, например таблиц, представлений и других пользовательских функций.</span><span class="sxs-lookup"><span data-stu-id="af615-190">CREATE FUNCTION supports a SCHEMABINDING clause that binds the function to the schema of any objects it references, such as tables, views, and other user-defined functions.</span></span> <span data-ttu-id="af615-191">Попытка изменения или удаления любого объекта, к которому обращается привязанная к схеме функция, приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="af615-191">An attempt to alter or drop any object referenced by a schema-bound function fails.</span></span>  
  
 <span data-ttu-id="af615-192">Перед указанием предложения SCHEMABINDING в инструкции CREATE FUNCTION нужно соблюсти следующие условия.</span><span class="sxs-lookup"><span data-stu-id="af615-192">These conditions must be met before you can specify SCHEMABINDING in CREATE FUNCTION:</span></span>  
  
-   <span data-ttu-id="af615-193">Все представления и пользовательские функции, к которым обращается функция, должны быть привязаны к схеме.</span><span class="sxs-lookup"><span data-stu-id="af615-193">All views and user-defined functions referenced by the function must be schema-bound.</span></span>  
  
-   <span data-ttu-id="af615-194">Все объекты, к которым обращается функция, должны находиться в той же базе данных, что и функция.</span><span class="sxs-lookup"><span data-stu-id="af615-194">All objects referenced by the function must be in the same database as the function.</span></span> <span data-ttu-id="af615-195">Обращение к объектам должно производиться по однокомпонентным либо двухкомпонентным именам.</span><span class="sxs-lookup"><span data-stu-id="af615-195">The objects must be referenced using either one-part or two-part names.</span></span>  
  
-   <span data-ttu-id="af615-196">Для всех объектов (таблиц, представлений и пользовательских функций), к которым обращается функция, должно быть получено разрешение REFERENCES.</span><span class="sxs-lookup"><span data-stu-id="af615-196">You must have REFERENCES permission on all objects (tables, views, and user-defined functions) referenced in the function.</span></span>  
  
 <span data-ttu-id="af615-197">Для удаления привязки к схеме можно использовать инструкцию ALTER FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="af615-197">You can use ALTER FUNCTION to remove the schema binding.</span></span> <span data-ttu-id="af615-198">В инструкции ALTER FUNCTION следует переопределить функцию без указания предложения WITH SCHEMABINDING.</span><span class="sxs-lookup"><span data-stu-id="af615-198">The ALTER FUNCTION statement should redefine the function without specifying WITH SCHEMABINDING.</span></span>  
  
##  <a name="specifying-parameters"></a><a name="Parameters"></a><span data-ttu-id="af615-199">Указание параметров</span><span class="sxs-lookup"><span data-stu-id="af615-199">Specifying Parameters</span></span>  
 <span data-ttu-id="af615-200">Пользовательская функция может принимать 0 или более входных параметров и возвращать либо скалярное, либо табличное значение.</span><span class="sxs-lookup"><span data-stu-id="af615-200">A user-defined function takes zero or more input parameters and returns either a scalar value or a table.</span></span> <span data-ttu-id="af615-201">Максимальное число входных параметров для функции равно 1024.</span><span class="sxs-lookup"><span data-stu-id="af615-201">A function can have a maximum of 1024 input parameters.</span></span> <span data-ttu-id="af615-202">Если для параметра функции установлено значение по умолчанию, необходимо указать ключевое слово DEFAULT при вызове функции, чтобы получить установленное по умолчанию значение.</span><span class="sxs-lookup"><span data-stu-id="af615-202">When a parameter of the function has a default value, the keyword DEFAULT must be specified when calling the function to get the default value.</span></span> <span data-ttu-id="af615-203">Это поведение отличается от использования параметров со значениями по умолчанию в пользовательских хранимых процедурах, в которых пропущенный параметр также принимает значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="af615-203">This behavior is different from parameters with default values in user-defined stored procedures in which omitting the parameter also implies the default value.</span></span> <span data-ttu-id="af615-204">В определяемых пользователями функциях не поддерживаются выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="af615-204">User-defined functions do not support output parameters.</span></span>  
  
##  <a name="related-tasks"></a><a name="Tasks"></a> <span data-ttu-id="af615-205">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="af615-205">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af615-206">**Описание задачи**</span><span class="sxs-lookup"><span data-stu-id="af615-206">**Task Description**</span></span>|<span data-ttu-id="af615-207">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="af615-207">**Topic**</span></span>|  
|<span data-ttu-id="af615-208">Описывает, как создать определяемую пользователем функцию Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="af615-208">Describes how to create a Transact-SQL user-defined function.</span></span>|[<span data-ttu-id="af615-209">Создание определяемых пользователем функций (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="af615-209">Create User-defined Functions &#40;Database Engine&#41;</span></span>](../user-defined-functions/create-user-defined-functions-database-engine.md)|  
|<span data-ttu-id="af615-210">Описывает, как создать функции CLR.</span><span class="sxs-lookup"><span data-stu-id="af615-210">Describes how create a CLR function.</span></span>|[<span data-ttu-id="af615-211">Создание функций CLR</span><span class="sxs-lookup"><span data-stu-id="af615-211">Create CLR Functions</span></span>](../user-defined-functions/create-clr-functions.md)|  
|<span data-ttu-id="af615-212">Описывает, как создать определяемую пользователем агрегатную функцию.</span><span class="sxs-lookup"><span data-stu-id="af615-212">Describes how to create a user-defined aggregate function</span></span>|[<span data-ttu-id="af615-213">Создание пользовательских агрегатных функций</span><span class="sxs-lookup"><span data-stu-id="af615-213">Create User-defined Aggregates</span></span>](../user-defined-functions/create-user-defined-aggregates.md)|  
|<span data-ttu-id="af615-214">Описывает, как изменить определяемую пользователем функцию Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="af615-214">Describes how to modify a Transact-SQL user-defined function.</span></span>|[<span data-ttu-id="af615-215">Изменение пользовательских функций</span><span class="sxs-lookup"><span data-stu-id="af615-215">Modify User-defined Functions</span></span>](../user-defined-functions/user-defined-functions.md)|  
|<span data-ttu-id="af615-216">Описывает, как удалить определяемую пользователем функцию.</span><span class="sxs-lookup"><span data-stu-id="af615-216">Describes how to delete a user-defined function.</span></span>|[<span data-ttu-id="af615-217">Удаление пользовательских функций</span><span class="sxs-lookup"><span data-stu-id="af615-217">Delete User-defined Functions</span></span>](../user-defined-functions/delete-user-defined-functions.md)|  
|<span data-ttu-id="af615-218">Описывает, как создать определяемую пользователем функцию выполнения.</span><span class="sxs-lookup"><span data-stu-id="af615-218">Describes how to execute a user-defined function.</span></span>|[<span data-ttu-id="af615-219">Выполнение пользовательских функций</span><span class="sxs-lookup"><span data-stu-id="af615-219">Execute User-defined Functions</span></span>](../user-defined-functions/execute-user-defined-functions.md)|  
|<span data-ttu-id="af615-220">Описывает, как переименовать определяемую пользователем функцию</span><span class="sxs-lookup"><span data-stu-id="af615-220">Describes how to rename a user-defined function</span></span>|[<span data-ttu-id="af615-221">Переименование пользовательских функций</span><span class="sxs-lookup"><span data-stu-id="af615-221">Rename User-defined Functions</span></span>](../user-defined-functions/rename-user-defined-functions.md)|  
|<span data-ttu-id="af615-222">Описывает, как просмотреть определяемую пользователем функцию.</span><span class="sxs-lookup"><span data-stu-id="af615-222">Describes how to view the definition of a user-defined function.</span></span>|[<span data-ttu-id="af615-223">Просмотр пользовательских функций</span><span class="sxs-lookup"><span data-stu-id="af615-223">View User-defined Functions</span></span>](view-user-defined-functions.md)|  
  
  