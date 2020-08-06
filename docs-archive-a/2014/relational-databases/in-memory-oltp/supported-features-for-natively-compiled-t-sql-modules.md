---
title: Поддерживаемые конструкции в хранимых процедурах, скомпилированных в собственном виде | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 05515013-28b5-4ccf-9a54-ae861448945b
author: rothja
ms.author: jroth
ms.openlocfilehash: 65e6e794c5858a68c4b2a9b298513911b487cf52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668327"
---
# <a name="supported-constructs-in-natively-compiled-stored-procedures"></a><span data-ttu-id="9cc33-102">Поддерживаемые конструкции для хранимых процедур, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="9cc33-102">Supported Constructs in Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="9cc33-103">Этот раздел содержит список поддерживаемых функций для хранимых процедур, скомпилированных в собственном виде ([Создание процедуры &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql)):</span><span class="sxs-lookup"><span data-stu-id="9cc33-103">This topic contains a list of supported features for natively compiled stored procedures ([CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql)):</span></span>  
  
-   [<span data-ttu-id="9cc33-104">Возможности программирования в хранимых процедурах, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="9cc33-104">Programmability in Natively Compiled Stored Procedures</span></span>](#pncsp)  
  
-   [<span data-ttu-id="9cc33-105">Поддерживаемые операторы</span><span class="sxs-lookup"><span data-stu-id="9cc33-105">Supported Operators</span></span>](#so)  
  
-   [<span data-ttu-id="9cc33-106">Встроенные функции в хранимых процедурах, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="9cc33-106">Built-in Functions in Natively Compiled Stored Procedures</span></span>](#bfncsp)  
  
-   [<span data-ttu-id="9cc33-107">Контактная зона запросов в хранимых процедурах, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="9cc33-107">Query Surface Area in Natively Compiled Stored Procedures</span></span>](#qsancsp)  
  
-   [<span data-ttu-id="9cc33-108">Аудит</span><span class="sxs-lookup"><span data-stu-id="9cc33-108">Auditing</span></span>](#auditing)  
  
-   [<span data-ttu-id="9cc33-109">Таблица, запрос и указания по соединению</span><span class="sxs-lookup"><span data-stu-id="9cc33-109">Table, Query, and Join Hints</span></span>](#tqh)  
  
-   [<span data-ttu-id="9cc33-110">Ограничения на сортировку</span><span class="sxs-lookup"><span data-stu-id="9cc33-110">Limitations on Sorting</span></span>](#los)  
  
 <span data-ttu-id="9cc33-111">Сведения о типах данных, поддерживаемых в скомпилированных в собственном коде хранимых процедурах, см. в разделе [Supported Data Types](supported-data-types-for-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="9cc33-111">For information on data types supported in natively compiled stored procedures, see [Supported Data Types](supported-data-types-for-in-memory-oltp.md).</span></span>  
  
 <span data-ttu-id="9cc33-112">Полные сведения о неподдерживаемых конструкциях и о том, как обойти некоторые неподдерживаемые функции в хранимых процедурах, скомпилированных в собственном коде, см. в разделе [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9cc33-112">For complete information about unsupported constructs, and for information about how to work around some of the unsupported features in natively compiled stored procedures, see [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span></span> <span data-ttu-id="9cc33-113">Дополнительные сведения о неподдерживаемых компонентах см. в разделе [Конструкции языка Transact-SQL, неподдерживаемые в In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="9cc33-113">For more information about unsupported features, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
##  <a name="programmability-in-natively-compiled-stored-procedures"></a><a name="pncsp"></a><span data-ttu-id="9cc33-114">Программирование в хранимых процедурах, скомпилированных в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="9cc33-114">Programmability in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="9cc33-115">Поддерживаются следующие конструкции:</span><span class="sxs-lookup"><span data-stu-id="9cc33-115">The following are supported:</span></span>  
  
-   <span data-ttu-id="9cc33-116">BEGIN ATOMIC (на внешнем уровне хранимой процедуры), LANGUAGE, ISOLATION LEVEL, DATEFORMAT и DATEFIRST.</span><span class="sxs-lookup"><span data-stu-id="9cc33-116">BEGIN ATOMIC (at the outer level of the stored procedure), LANGUAGE, ISOLATION LEVEL, DATEFORMAT, and DATEFIRST.</span></span>  
  
-   <span data-ttu-id="9cc33-117">Объявление переменной как NULL или NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="9cc33-117">Declaring variables as NULL or NOT NULL.</span></span> <span data-ttu-id="9cc33-118">Если переменная объявлена как NOT NULL, то объявление должно иметь инициализатор.</span><span class="sxs-lookup"><span data-stu-id="9cc33-118">If a variable is declared as NOT NULL, the declaration must have an initializer.</span></span> <span data-ttu-id="9cc33-119">Если переменная не объявлена как NOT NULL, инициализатор не обязателен.</span><span class="sxs-lookup"><span data-stu-id="9cc33-119">If a variable is not declared as NOT NULL, an initializer is optional.</span></span>  
  
-   <span data-ttu-id="9cc33-120">IF и WHILE</span><span class="sxs-lookup"><span data-stu-id="9cc33-120">IF and WHILE</span></span>  
  
-   <span data-ttu-id="9cc33-121">INSERT/UPDATE/DELETE</span><span class="sxs-lookup"><span data-stu-id="9cc33-121">INSERT/UPDATE/DELETE</span></span>  
  
     <span data-ttu-id="9cc33-122">Вложенные запросы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="9cc33-122">Subqueries are not supported.</span></span> <span data-ttu-id="9cc33-123">В предложениях WHERE и HAVING предложения AND и BETWEEN поддерживаются; OR, NOT и IN не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="9cc33-123">In the WHERE or HAVING clause, AND and BETWEEN are supported; OR, NOT, and IN are not supported.</span></span>  
  
-   <span data-ttu-id="9cc33-124">Оптимизированные для памяти табличные типы и табличные переменные.</span><span class="sxs-lookup"><span data-stu-id="9cc33-124">Memory-optimized table types and table variables.</span></span>  
  
-   <span data-ttu-id="9cc33-125">RETURN</span><span class="sxs-lookup"><span data-stu-id="9cc33-125">RETURN</span></span>  
  
-   <span data-ttu-id="9cc33-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="9cc33-126">SELECT</span></span>  
  
-   <span data-ttu-id="9cc33-127">SET</span><span class="sxs-lookup"><span data-stu-id="9cc33-127">SET</span></span>  
  
-   <span data-ttu-id="9cc33-128">TRY/CATCH/THROW</span><span class="sxs-lookup"><span data-stu-id="9cc33-128">TRY/CATCH/THROW</span></span>  
  
     <span data-ttu-id="9cc33-129">Чтобы улучшить производительность, используйте один блок TRY/CATCH для всей хранимой процедуры, скомпилированной в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="9cc33-129">To optimize performance, use a single TRY/CATCH block for an entire natively compiled stored procedure.</span></span>  
  
##  <a name="supported-operators"></a><a name="so"></a> <span data-ttu-id="9cc33-130">Поддерживаемые операторы</span><span class="sxs-lookup"><span data-stu-id="9cc33-130">Supported Operators</span></span>  
 <span data-ttu-id="9cc33-131">Поддерживаются следующие операторы.</span><span class="sxs-lookup"><span data-stu-id="9cc33-131">The following operators are supported.</span></span>  
  
-   <span data-ttu-id="9cc33-132">[Операторы сравнения &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/comparison-operators-transact-sql) (например, >, \<, > = и <=) поддерживаются в условных выражениях (если, while).</span><span class="sxs-lookup"><span data-stu-id="9cc33-132">[Comparison Operators &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/comparison-operators-transact-sql) (for example, >, \<, >=, and <=) are supported in conditionals (IF, WHILE).</span></span>  
  
-   <span data-ttu-id="9cc33-133">Унарные операторы (+, -).</span><span class="sxs-lookup"><span data-stu-id="9cc33-133">Unary operators (+, -).</span></span>  
  
-   <span data-ttu-id="9cc33-134">Двоичные операторы (\*,/, +, -, % (остаток от деления)).</span><span class="sxs-lookup"><span data-stu-id="9cc33-134">Binary operators (\*, /, +, -, % (modulo)).</span></span>  
  
     <span data-ttu-id="9cc33-135">Оператор плюс (+) поддерживается как для чисел, так и в строках.</span><span class="sxs-lookup"><span data-stu-id="9cc33-135">The plus operator (+) is supported on both numbers and strings.</span></span>  
  
-   <span data-ttu-id="9cc33-136">Логические операторы (AND, OR, NOT).</span><span class="sxs-lookup"><span data-stu-id="9cc33-136">Logical operators (AND, OR, NOT).</span></span> <span data-ttu-id="9cc33-137">Операторы OR и NOT поддерживаются в инструкциях IF и WHILE, но не в предложениях WHERE или HAVING.</span><span class="sxs-lookup"><span data-stu-id="9cc33-137">OR and NOT are supported in IF and WHILE statements but not in WHERE or HAVING clauses.</span></span>  
  
-   <span data-ttu-id="9cc33-138">Битовые операторы ~, &, |, и ^</span><span class="sxs-lookup"><span data-stu-id="9cc33-138">Bitwise operators ~, &, |, and ^</span></span>  
  
##  <a name="built-in-functions-in-natively-compiled-stored-procedures"></a><a name="bfncsp"></a><span data-ttu-id="9cc33-139">Встроенные функции в хранимых процедурах, скомпилированных в собственном виде</span><span class="sxs-lookup"><span data-stu-id="9cc33-139">Built-in Functions in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="9cc33-140">Следующие функции поддерживаются в ограничениях по умолчанию для оптимизированных для памяти таблиц и в хранимых процедурах, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="9cc33-140">The following functions are supported in default constraints on memory-optimized tables and in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="9cc33-141">Математические функции: ACOS, ASIN, ATAN, ATN2, COS, COT, DEGREES, EXP, LOG, LOG10, PI, POWER, RADIANS, RAND, SIN, SQRT, SQUARE и TAN</span><span class="sxs-lookup"><span data-stu-id="9cc33-141">Math Functions: ACOS, ASIN, ATAN, ATN2, COS, COT, DEGREES, EXP, LOG, LOG10, PI, POWER, RADIANS, RAND, SIN, SQRT, SQUARE, and TAN</span></span>  
  
-   <span data-ttu-id="9cc33-142">Функции даты: CURRENT_TIMESTAMP, DATEADD, DATEDIFF, DATEFROMPARTS, DATEPART, DATETIME2FROMPARTS, DATETIMEFROMPARTS, DAY, EOMONTH, GETDATE, GETUTCDATE, MONTH, SMALLDATETIMEFROMPARTS, SYSDATETIME, SYSUTCDATETIME и YEAR.</span><span class="sxs-lookup"><span data-stu-id="9cc33-142">Date Functions: CURRENT_TIMESTAMP, DATEADD, DATEDIFF, DATEFROMPARTS, DATEPART, DATETIME2FROMPARTS, DATETIMEFROMPARTS, DAY, EOMONTH, GETDATE, GETUTCDATE, MONTH, SMALLDATETIMEFROMPARTS, SYSDATETIME, SYSUTCDATETIME, and YEAR.</span></span>  
  
-   <span data-ttu-id="9cc33-143">Строковые функции: LEN, LTRIM, RTRIM и SUBSTRING</span><span class="sxs-lookup"><span data-stu-id="9cc33-143">String Functions: LEN, LTRIM, RTRIM, and SUBSTRING</span></span>  
  
-   <span data-ttu-id="9cc33-144">Функция идентификации: SCOPE_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="9cc33-144">Identity Function: SCOPE_IDENTITY</span></span>  
  
-   <span data-ttu-id="9cc33-145">Функции для работы со значением NULL: ISNULL</span><span class="sxs-lookup"><span data-stu-id="9cc33-145">NULL functions: ISNULL</span></span>  
  
-   <span data-ttu-id="9cc33-146">Функции уникальных идентификаторов: NEWID и NEWSEQUENTIALID</span><span class="sxs-lookup"><span data-stu-id="9cc33-146">Uniqueidentifier functions: NEWID and NEWSEQUENTIALID</span></span>  
  
-   <span data-ttu-id="9cc33-147">Функции ошибок: ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY и ERROR_STATE</span><span class="sxs-lookup"><span data-stu-id="9cc33-147">Error Functions: ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY, and ERROR_STATE</span></span>  
  
-   <span data-ttu-id="9cc33-148">Преобразования: CAST и CONVERT.</span><span class="sxs-lookup"><span data-stu-id="9cc33-148">Conversions: CAST and CONVERT.</span></span> <span data-ttu-id="9cc33-149">Не поддерживаются преобразования между символьными строками в Юникоде и отличными от Юникода (n(var)char и (var)char).</span><span class="sxs-lookup"><span data-stu-id="9cc33-149">Conversions between Unicode and non-Unicode character strings (n(var)char and (var)char) are not supported.</span></span>  
  
-   <span data-ttu-id="9cc33-150">Системные функции: @@rowcount.</span><span class="sxs-lookup"><span data-stu-id="9cc33-150">System Functions: @@rowcount.</span></span> <span data-ttu-id="9cc33-151">Инструкции в хранимых процедурах, скомпилированных в собственном коде, обновляют @@rowcount, и вы можете использовать @@rowcount в таких процедурах для определения числа строк, затронутых последней инструкцией, выполненной в пределах этой хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="9cc33-151">Statements inside natively compiled stored procedures update @@rowcount and you can use @@rowcount in a natively compiled stored procedure to determine the number of rows affected by the last statement executed within that natively compiled stored procedure.</span></span> <span data-ttu-id="9cc33-152">Но @@rowcount сбрасывается до 0 в начале и в конце выполнения каждой хранимой процедуры, скомпилированной в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="9cc33-152">However, @@rowcount is reset to 0 at the start and at the end of the execution of a natively compiled stored procedure.</span></span>  
  
##  <a name="query-surface-area-in-natively-compiled-stored-procedures"></a><a name="qsancsp"></a><span data-ttu-id="9cc33-153">Контактная зона запроса в скомпилированных в собственном режиме хранимых процедурах</span><span class="sxs-lookup"><span data-stu-id="9cc33-153">Query Surface Area in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="9cc33-154">Поддерживаются следующие конструкции:</span><span class="sxs-lookup"><span data-stu-id="9cc33-154">The following are supported:</span></span>  
  
-   <span data-ttu-id="9cc33-155">BETWEEN</span><span class="sxs-lookup"><span data-stu-id="9cc33-155">BETWEEN</span></span>  
  
-   <span data-ttu-id="9cc33-156">Псевдонимы имен столбцов (с помощью синтаксиса AS или =).</span><span class="sxs-lookup"><span data-stu-id="9cc33-156">Column name aliases (using either AS or = syntax).</span></span>  
  
-   <span data-ttu-id="9cc33-157">CROSS JOIN и INNER JOIN поддерживаются только с запросами SELECT.</span><span class="sxs-lookup"><span data-stu-id="9cc33-157">CROSS JOIN and INNER JOIN, supported only with SELECT queries.</span></span>  
  
-   <span data-ttu-id="9cc33-158">Выражения поддерживаются в списке SELECT, [где &#40;предложение&#41;Transact-SQL](/sql/t-sql/queries/where-transact-sql) , если они используют поддерживаемый оператор.</span><span class="sxs-lookup"><span data-stu-id="9cc33-158">Expressions are supported in SELECT list and [WHERE &#40;Transact-SQL&#41;](/sql/t-sql/queries/where-transact-sql) clause if they use a supported operator.</span></span> <span data-ttu-id="9cc33-159">Список поддерживаемых в настоящее время операторов см. в разделе [Supported Operators](#so) .</span><span class="sxs-lookup"><span data-stu-id="9cc33-159">See [Supported Operators](#so) for the list of currently-supported operators.</span></span>  
  
-   <span data-ttu-id="9cc33-160">Предикат фильтра IS [NOT] NULL</span><span class="sxs-lookup"><span data-stu-id="9cc33-160">Filter predicate IS [NOT] NULL</span></span>  
  
-   <span data-ttu-id="9cc33-161">FROM \<memory optimized table></span><span class="sxs-lookup"><span data-stu-id="9cc33-161">FROM \<memory optimized table></span></span>  
  
-   <span data-ttu-id="9cc33-162">Поддерживается [группирование &#40;&#41;Transact-SQL](/sql/t-sql/queries/select-group-by-transact-sql) , а также агрегатные функции AVG, COUNT, COUNT_BIG, min, Max и Sum.</span><span class="sxs-lookup"><span data-stu-id="9cc33-162">[GROUP BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) is supported, along with the aggregate functions AVG, COUNT, COUNT_BIG, MIN, MAX, and SUM.</span></span> <span data-ttu-id="9cc33-163">Функции MIN и MAX не поддерживаются для типов nvarchar, char, varchar, varchar, varbinary и binary.</span><span class="sxs-lookup"><span data-stu-id="9cc33-163">MIN and MAX are not supported for types nvarchar, char, varchar, varchar, varbinary, and binary.</span></span> <span data-ttu-id="9cc33-164">[Предложение order by &#40;&#41;Transact-SQL](/sql/t-sql/queries/select-order-by-clause-transact-sql) поддерживается в инструкции [Group By &#40;transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) если выражение в списке ORDER BY отображается в списке Group By.</span><span class="sxs-lookup"><span data-stu-id="9cc33-164">[ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql) is supported with [GROUP BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) if an expression in the ORDER BY list appears verbatim in the GROUP BY list.</span></span> <span data-ttu-id="9cc33-165">Например, GROUP BY a + b ORDER BY a + b поддерживается; GROUP BY a, b ORDER BY a + b не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9cc33-165">For example, GROUP BY a + b ORDER BY a + b is supported, but GROUP BY a, b ORDER BY a + b is not.</span></span>  
  
-   <span data-ttu-id="9cc33-166">HAVING, с соблюдением тех же ограничений, как в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="9cc33-166">HAVING, subject to the same expression limitations as the WHERE clause.</span></span>  
  
-   <span data-ttu-id="9cc33-167">INSERT VALUES (по одной строке на каждую инструкцию) и SELECT INSERT</span><span class="sxs-lookup"><span data-stu-id="9cc33-167">INSERT VALUES (one row per statement) and INSERT SELECT</span></span>  
  
-   <span data-ttu-id="9cc33-168">УПОРЯДОЧИТЬ по <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9cc33-168">ORDER BY <sup>1</sup></span></span>  
  
-   <span data-ttu-id="9cc33-169">Предикаты без ссылки на столбец.</span><span class="sxs-lookup"><span data-stu-id="9cc33-169">Predicates not referencing a column.</span></span>  
  
-   <span data-ttu-id="9cc33-170">DELETE, SELECT и UPDATE</span><span class="sxs-lookup"><span data-stu-id="9cc33-170">SELECT, UPDATE, and DELETE</span></span>  
  
-   <span data-ttu-id="9cc33-171">ПЕРВЫЕ <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9cc33-171">TOP <sup>1</sup></span></span>  
  
-   <span data-ttu-id="9cc33-172">Присвоение переменных в списке предложения SELECT.</span><span class="sxs-lookup"><span data-stu-id="9cc33-172">Variable assignment in the SELECT list.</span></span>  
  
-   <span data-ttu-id="9cc33-173">ГДЕ... ПЕРЕТАСКИВАНИ</span><span class="sxs-lookup"><span data-stu-id="9cc33-173">WHERE ... AND</span></span>  
  
 <span data-ttu-id="9cc33-174"><sup>1</sup> ORDER BY и Top поддерживаются в хранимых процедурах, скомпилированных в собственном режиме, с некоторыми ограничениями.</span><span class="sxs-lookup"><span data-stu-id="9cc33-174"><sup>1</sup> ORDER BY and TOP are supported in natively compiled stored procedures, with some restrictions:</span></span>  
  
-   <span data-ttu-id="9cc33-175">Не поддерживается `DISTINCT` в предложениях `SELECT` и `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="9cc33-175">There is no support for `DISTINCT` in the `SELECT` or `ORDER BY` clause.</span></span>  
  
-   <span data-ttu-id="9cc33-176">Не поддерживаются `WITH TIES` и `PERCENT` в предложении `TOP`.</span><span class="sxs-lookup"><span data-stu-id="9cc33-176">There is no support for `WITH TIES` or `PERCENT` in the `TOP` clause.</span></span>  
  
-   <span data-ttu-id="9cc33-177">`TOP` совместно с `ORDER BY` не поддерживает более 8192 строк при использовании константы в предложении `TOP`.</span><span class="sxs-lookup"><span data-stu-id="9cc33-177">`TOP` combined with `ORDER BY` does not support more than 8,192 when using a constant in the `TOP` clause.</span></span> <span data-ttu-id="9cc33-178">Это ограничение может быть понижено в случае, если запрос содержит соединения или агрегатные функции.</span><span class="sxs-lookup"><span data-stu-id="9cc33-178">This limit may be lowered in case the query contains joins or aggregate functions.</span></span> <span data-ttu-id="9cc33-179">(Например, с одним соединением (двумя таблицами) ограничение составляет 4 096 строк.</span><span class="sxs-lookup"><span data-stu-id="9cc33-179">(For example, with one join (two tables), the limit is 4,096 rows.</span></span> <span data-ttu-id="9cc33-180">С двумя соединениями (тремя таблицами) ограничение равно 2 730 строкам.)</span><span class="sxs-lookup"><span data-stu-id="9cc33-180">With two joins (three tables), the limit is 2,730 rows.)</span></span>  
  
     <span data-ttu-id="9cc33-181">Результаты более 8 192 можно получить, сохраняя в переменной несколько строк.</span><span class="sxs-lookup"><span data-stu-id="9cc33-181">You can obtain results greater than 8,192 by storing the number of rows in a variable:</span></span>  
  
    ```sql  
    DECLARE @v INT = 9000  
    SELECT TOP (@v) ... FROM ... ORDER BY ...  
    ```  
  
 <span data-ttu-id="9cc33-182">Однако константа в предложении `TOP` обеспечивает лучшую производительность, чем при использовании переменной.</span><span class="sxs-lookup"><span data-stu-id="9cc33-182">However, a constant in the `TOP` clause results in better performance compared to using a variable.</span></span>  
  
 <span data-ttu-id="9cc33-183">Эти ограничения не применяются к интерпретированному доступу [!INCLUDE[tsql](../../includes/tsql-md.md)] к оптимизированным для памяти таблицам.</span><span class="sxs-lookup"><span data-stu-id="9cc33-183">These restrictions do not apply to interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] access on memory-optimized tables.</span></span>  
  
##  <a name="auditing"></a><a name="auditing"></a> <span data-ttu-id="9cc33-184">Аудит</span><span class="sxs-lookup"><span data-stu-id="9cc33-184">Auditing</span></span>  
 <span data-ttu-id="9cc33-185">Аудит на уровне процедуры поддерживается для хранимых процедур, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="9cc33-185">Procedure level auditing is supported in natively compiled stored procedures.</span></span> <span data-ttu-id="9cc33-186">Аудит уровня инструкций не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9cc33-186">Statement level auditing is not supported.</span></span>  
  
 <span data-ttu-id="9cc33-187">Дополнительные сведения об аудите см. в разделе [Создание спецификация аудита для сервера и базы данных](../security/auditing/create-a-server-audit-and-database-audit-specification.md).</span><span class="sxs-lookup"><span data-stu-id="9cc33-187">For more information about auditing, see [Create a Server Audit and Database Audit Specification](../security/auditing/create-a-server-audit-and-database-audit-specification.md).</span></span>  
  
##  <a name="table-query-and-join-hints"></a><a name="tqh"></a><span data-ttu-id="9cc33-188">Таблицы, запросы и указания по соединению</span><span class="sxs-lookup"><span data-stu-id="9cc33-188">Table, Query, and Join Hints</span></span>  
 <span data-ttu-id="9cc33-189">Поддерживаются следующие конструкции:</span><span class="sxs-lookup"><span data-stu-id="9cc33-189">The following are supported:</span></span>  
  
-   <span data-ttu-id="9cc33-190">Табличные указания INDEX, FORCESCAN и FORCESEEK в синтаксисе табличных указаний или в [предложении OPTION (Transact-SQL)](/sql/t-sql/queries/option-clause-transact-sql) запроса.</span><span class="sxs-lookup"><span data-stu-id="9cc33-190">INDEX, FORCESCAN, and FORCESEEK hints, either in table hints syntax or in [OPTION Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/option-clause-transact-sql) of the query.</span></span>  
  
-   <span data-ttu-id="9cc33-191">FORCE ORDER</span><span class="sxs-lookup"><span data-stu-id="9cc33-191">FORCE ORDER</span></span>  
  
-   <span data-ttu-id="9cc33-192">INNER LOOP JOIN</span><span class="sxs-lookup"><span data-stu-id="9cc33-192">INNER LOOP JOIN</span></span>  
  
-   <span data-ttu-id="9cc33-193">OPTIMIZE FOR</span><span class="sxs-lookup"><span data-stu-id="9cc33-193">OPTIMIZE FOR</span></span>  
  
 <span data-ttu-id="9cc33-194">Дополнительные сведения см. в разделе [указания &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9cc33-194">For more information, see [Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql).</span></span>  
  
##  <a name="limitations-on-sorting"></a><a name="los"></a> <span data-ttu-id="9cc33-195">Ограничения на сортировку</span><span class="sxs-lookup"><span data-stu-id="9cc33-195">Limitations on Sorting</span></span>  
 <span data-ttu-id="9cc33-196">В запросе с использованием [TOP (Transact-SQL)](/sql/t-sql/queries/top-transact-sql) и [предложения ORDER BY (Transact-SQL)](/sql/t-sql/queries/select-order-by-clause-transact-sql) можно сортировать более 8 000 строк.</span><span class="sxs-lookup"><span data-stu-id="9cc33-196">You can sort greater than 8,000 rows in a query that uses [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) and an [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span></span> <span data-ttu-id="9cc33-197">Без [предложения ORDER BY (Transact-SQL)](/sql/t-sql/queries/select-order-by-clause-transact-sql)[TOP (Transact-SQL)](/sql/t-sql/queries/top-transact-sql) позволяет сортировать не более 8 000 строк (меньше, если есть соединения).</span><span class="sxs-lookup"><span data-stu-id="9cc33-197">However, without [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) can sort up to 8,000 rows (fewer rows if there are joins).</span></span>  
  
 <span data-ttu-id="9cc33-198">Если в запросе используется как оператор [TOP (Transact-SQL)](/sql/t-sql/queries/top-transact-sql), так и [предложение ORDER BY (Transact-SQL)](/sql/t-sql/queries/select-order-by-clause-transact-sql), для оператора TOP можно указать не более 8192 строк.</span><span class="sxs-lookup"><span data-stu-id="9cc33-198">If your query uses both the [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) operator and an [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), you can specify up to 8192 rows for the TOP operator.</span></span> <span data-ttu-id="9cc33-199">Если указано больше 8192 строк, возникает следующее сообщение об ошибке: **Сообщение 41398, уровень 16, состояние 1, процедура *\<procedureName>* , строка *\<lineNumber>* . Оператор TOP может возвратить не более 8192 строк; запрошенное число: *\<number>* .**</span><span class="sxs-lookup"><span data-stu-id="9cc33-199">If you specify more than 8192 rows you get the error message: **Msg 41398, Level 16, State 1, Procedure *\<procedureName>*, Line *\<lineNumber>* The TOP operator can return a maximum of 8192 rows; *\<number>* was requested.**</span></span>  
  
 <span data-ttu-id="9cc33-200">Если отсутствует предложение TOP, то можно отсортировать любое количество строк с помощью предложения ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="9cc33-200">If you do not have a TOP clause, you can sort any number of rows with ORDER BY.</span></span>  
  
 <span data-ttu-id="9cc33-201">Если не используется предложение ORDER BY, то можно использовать любое целочисленное значение с оператором TOP.</span><span class="sxs-lookup"><span data-stu-id="9cc33-201">If you do not use an ORDER BY clause, you can use any integer value with the TOP operator.</span></span>  
  
 <span data-ttu-id="9cc33-202">Пример для оператора TOP с числом значений 8192: компиляция</span><span class="sxs-lookup"><span data-stu-id="9cc33-202">Example with TOP N = 8192: Compiles</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    SELECT TOP 8192 ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="9cc33-203">Пример для оператора TOP с числом значений > 8192: сбой компиляции.</span><span class="sxs-lookup"><span data-stu-id="9cc33-203">Example with TOP N > 8192: Fails to compile.</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    SELECT TOP 8193 ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="9cc33-204">Ограничение в 8192 строки применяется только к `TOP N` , где `N` является константой, как показано в предыдущих примерах.</span><span class="sxs-lookup"><span data-stu-id="9cc33-204">The 8192 row limitation only applies to `TOP N` where `N` is a constant, as in the preceding examples.</span></span>  <span data-ttu-id="9cc33-205">Если нужно, чтобы `N` было больше 8192, можно присвоить это значение переменной и использовать ее с оператором `TOP`.</span><span class="sxs-lookup"><span data-stu-id="9cc33-205">If you need `N` greater than 8192 you can assign the value to a variable and use that variable with `TOP`.</span></span>  
  
 <span data-ttu-id="9cc33-206">Пример использования переменной: компиляция</span><span class="sxs-lookup"><span data-stu-id="9cc33-206">Example using a variable: Compiles</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    DECLARE @v int = 8193   
    SELECT TOP (@v) ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="9cc33-207">**Ограничения возвращаемых строк:** Существует два варианта, когда возможно уменьшение числа строк, возвращаемых оператором TOP.</span><span class="sxs-lookup"><span data-stu-id="9cc33-207">**Limitations on rows returned:** There are two cases where that can potentially reduce the number of rows that can be returned by the TOP operator:</span></span>  
  
-   <span data-ttu-id="9cc33-208">Использование соединений в запросе.</span><span class="sxs-lookup"><span data-stu-id="9cc33-208">Using JOINs in the query.</span></span>  <span data-ttu-id="9cc33-209">Влияние соединений на ограничения зависит от плана запроса.</span><span class="sxs-lookup"><span data-stu-id="9cc33-209">The influence of JOINs on the limitation depends on the query plan.</span></span>  
  
-   <span data-ttu-id="9cc33-210">Использование агрегатных функций или ссылки на агрегатные функции в предложении ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="9cc33-210">Using aggregate functions or references to aggregate functions in the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="9cc33-211">Формула для вычисления наименьшего поддерживаемого значения N в предложении TOP N выглядит следующим образом: `N = floor ( 65536 / number_of_tables * 8 + total_size+of+aggs )`.</span><span class="sxs-lookup"><span data-stu-id="9cc33-211">The formula to calculate a worst case maximum supported N in TOP N is: `N = floor ( 65536 / number_of_tables * 8 + total_size+of+aggs )`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc33-212">См. также:</span><span class="sxs-lookup"><span data-stu-id="9cc33-212">See Also</span></span>  
 <span data-ttu-id="9cc33-213">[Скомпилированные в собственном коде хранимые процедуры](natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="9cc33-213">[Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="9cc33-214">Проблемы миграции, связанные с хранимыми процедурами, скомпилированными в собственном коде</span><span class="sxs-lookup"><span data-stu-id="9cc33-214">Migration Issues for Natively Compiled Stored Procedures</span></span>](migration-issues-for-natively-compiled-stored-procedures.md)  
  
  
