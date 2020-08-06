---
title: Атомарные блоки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 40e0e749-260c-4cfc-a848-444d30c09d85
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ca8f5b4d767ef0fe836cd260f8d12dd5b40c75d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655719"
---
# <a name="atomic-blocks"></a><span data-ttu-id="93674-102">Блоки ATOMIC</span><span class="sxs-lookup"><span data-stu-id="93674-102">Atomic Blocks</span></span>
  <span data-ttu-id="93674-103">`BEGIN ATOMIC` — часть стандарта ANSI SQL.</span><span class="sxs-lookup"><span data-stu-id="93674-103">`BEGIN ATOMIC` is part of the ANSI SQL standard.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="93674-104">поддерживает блоки ATOMIC только на высшем уровне хранимых процедур, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="93674-104">supports atomic blocks only at the top-level of natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="93674-105">Каждая хранимая процедура, скомпилированная в собственном коде, содержит только один блок инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93674-105">Every natively compiled stored procedure contains exactly one block of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="93674-106">Это блок ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="93674-106">This is an ATOMIC block.</span></span>  
  
-   <span data-ttu-id="93674-107">Интерпретированные хранимые процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)] , скомпилированные не в собственном коде, и нерегламентированные пакеты не поддерживают блоки ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="93674-107">Non-native, interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and ad hoc batches do not support atomic blocks.</span></span>  
  
 <span data-ttu-id="93674-108">Блоки ATOMIC выполняются (атомарным образом) в рамках транзакции.</span><span class="sxs-lookup"><span data-stu-id="93674-108">Atomic blocks are executed (atomically) within the transaction.</span></span> <span data-ttu-id="93674-109">Либо все инструкции в блоке выполняются успешно, либо весь блок будет подвергнут откату до точки сохранения, созданной в начале блока.</span><span class="sxs-lookup"><span data-stu-id="93674-109">Either all statements in the block succeed or the entire block will be rolled back to the savepoint that was created at the start of the block.</span></span> <span data-ttu-id="93674-110">Кроме того, параметры сеанса фиксируются для блока ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="93674-110">In addition, the session settings are fixed for the atomic block.</span></span> <span data-ttu-id="93674-111">Выполнение того же блока ATOMIC в сеансах с различными параметрами приведет к тому же поведению независимо от параметров текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="93674-111">Executing the same atomic block in sessions with different settings will result in the same behavior, independent of the settings of the current session.</span></span>  
  
## <a name="transactions-and-error-handling"></a><span data-ttu-id="93674-112">Транзакции и обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="93674-112">Transactions and Error Handling</span></span>  
 <span data-ttu-id="93674-113">Если транзакция уже существует в сеансе (поскольку пакет выполнил инструкцию `BEGIN TRANSACTION` и транзакция остается активной), то при запуске блока ATOMIC создается точка сохранения в транзакции.</span><span class="sxs-lookup"><span data-stu-id="93674-113">If a transaction already exists on a session (because a batch executed a `BEGIN TRANSACTION` statement and the transaction remains active), then starting an atomic block will create a savepoint in the transaction.</span></span> <span data-ttu-id="93674-114">Если блок выходит без исключения, точка сохранения, которая была создана для блока, фиксируется, но транзакция не будет фиксироваться до тех пор, пока не будет зафиксирована транзакция на уровне сеанса.</span><span class="sxs-lookup"><span data-stu-id="93674-114">If the block exits without an exception, the savepoint that was created for the block commits, but the transaction will not commit until the transaction at the session level commits.</span></span> <span data-ttu-id="93674-115">Если блок вызывает исключение, то результаты блока подвергаются откату, но транзакция на уровне сеанса продолжается, если исключение не приводит к ошибке транзакции.</span><span class="sxs-lookup"><span data-stu-id="93674-115">If the block throws an exception, the effects of the block are rolled back but the transaction at the session level will proceed, unless the exception is transaction-dooming.</span></span> <span data-ttu-id="93674-116">Например, конфликт записи приводит к ошибке транзакции, но не к ошибке приведения типов.</span><span class="sxs-lookup"><span data-stu-id="93674-116">For example a write conflict is transaction-dooming, but not a type casting error.</span></span>  
  
 <span data-ttu-id="93674-117">Если отсутствуют активные транзакции в сеансе, то `BEGIN ATOMIC` запускает новую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="93674-117">If there is no active transaction on a session, `BEGIN ATOMIC` will start a new transaction.</span></span> <span data-ttu-id="93674-118">Если вне блока не возникло исключение, то транзакция будет зафиксирована в конце блока.</span><span class="sxs-lookup"><span data-stu-id="93674-118">If no exception is thrown outside the scope of the block, the transaction will be committed at the end of the block.</span></span> <span data-ttu-id="93674-119">Если блок вызывает исключение (то есть исключение не обрабатывается и не перехватывается внутри блока), то будет произведен откат этой транзакции.</span><span class="sxs-lookup"><span data-stu-id="93674-119">If the block throws an exception (that is, the exception is not caught and handled within the block), the transaction will be rolled back.</span></span> <span data-ttu-id="93674-120">Для транзакций, которые охватывают один блок ATOMIC (одна хранимая процедура, скомпилированная в собственном коде), нет необходимости записывать явные инструкции `BEGIN TRANSACTION` и `COMMIT` или `ROLLBACK`.</span><span class="sxs-lookup"><span data-stu-id="93674-120">For transactions that span a single atomic block (a single natively compiled stored procedure), you do not need to write explicit `BEGIN TRANSACTION` and `COMMIT` or `ROLLBACK` statements.</span></span>  
  
 <span data-ttu-id="93674-121">Все хранимые процедуры, скомпилированные в собственном коде, поддерживают конструкции `TRY`, `CATCH` и `THROW` для обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="93674-121">Natively compiled stored procedures support the `TRY`, `CATCH`, and `THROW` constructs for error handling.</span></span> <span data-ttu-id="93674-122">Тип `RAISERROR` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="93674-122">`RAISERROR` is not supported.</span></span>  
  
 <span data-ttu-id="93674-123">Следующий пример иллюстрирует работу функции обработки ошибок с блоками ATOMIC и хранимыми процедурами, скомпилированными в собственном коде:</span><span class="sxs-lookup"><span data-stu-id="93674-123">The following example illustrates the error handling behavior with atomic blocks and natively compiled stored procedures:</span></span>  
  
```sql  
-- sample table  
CREATE TABLE dbo.t1 (  
  c1 int not null primary key nonclustered  
)  
WITH (MEMORY_OPTIMIZED=ON)  
GO  
  
-- sample proc that inserts 2 rows  
CREATE PROCEDURE dbo.usp_t1 @v1 bigint not null, @v2 bigint not null  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS  
BEGIN ATOMIC  
WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english', DELAYED_DURABILITY = ON)  
  
  INSERT dbo.t1 VALUES (@v1)  
  INSERT dbo.t1 VALUES (@v2)  
  
END  
GO  
  
-- insert two rows  
EXEC dbo.usp_t1 1, 2  
GO  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify the rows 1 and 2 were committed  
SELECT c1 FROM dbo.t1  
GO  
  
-- execute proc with arithmetic overflow  
EXEC dbo.usp_t1 3, 4444444444444  
GO  
-- expected error message:  
-- Msg 8115, Level 16, State 0, Procedure usp_t1  
-- Arithmetic overflow error converting bigint to data type int.  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify rows 3 was not committed; usp_t1 has been rolled back  
SELECT c1 FROM dbo.t1  
GO  
  
-- start a new transaction  
BEGIN TRANSACTION  
  -- insert rows 3 and 4  
  EXEC dbo.usp_t1 3, 4  
  
  -- verify there is still an active transaction  
  SELECT @@TRANCOUNT  
  
  -- verify the rows 3 and 4 were inserted  
  SELECT c1 FROM dbo.t1 WITH (SNAPSHOT)   
  ORDER BY c1  
  
  -- catch the arithmetic overflow error  
  BEGIN TRY  
    EXEC dbo.usp_t1 5, 4444444444444  
  END TRY  
  BEGIN CATCH  
    PRINT N'Error occurred: ' + error_message()  
  END CATCH  
  
  -- verify there is still an active transaction  
  SELECT @@TRANCOUNT  
  
  -- verify rows 3 and 4 are still in the table, and row 5 has not been inserted  
  SELECT c1 FROM dbo.t1 WITH (SNAPSHOT)   
  ORDER BY c1  
  
COMMIT  
GO  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify rows 3 and 4 has been committed  
SELECT c1 FROM dbo.t1  
ORDER BY c1  
GO  
```  
  
 <span data-ttu-id="93674-124">Следующие сообщения об ошибке, относящиеся к таблицам с оптимизацией для памяти, указывают на неудачу транзакции.</span><span class="sxs-lookup"><span data-stu-id="93674-124">The following error messages specific to memory-optimized tables are transaction dooming.</span></span> <span data-ttu-id="93674-125">Если они встречаются в атомарном блок, это приведет к тому, что транзакция будет прервана: 10772, 41301, 41302, 41305, 41325, 41332 и 41333.</span><span class="sxs-lookup"><span data-stu-id="93674-125">If they occur in the scope of an atomic block, they will cause the transaction to abort: 10772, 41301, 41302, 41305, 41325, 41332, and 41333.</span></span>  
  
## <a name="session-settings"></a><span data-ttu-id="93674-126">Параметры сеанса</span><span class="sxs-lookup"><span data-stu-id="93674-126">Session Settings</span></span>  
 <span data-ttu-id="93674-127">Параметры сеанса в блоках ATOMIC фиксируются, если выполнена компиляция хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="93674-127">The session settings in atomic blocks are fixed when the stored procedure is compiled.</span></span> <span data-ttu-id="93674-128">Некоторые параметры могут быть заданы с помощью `BEGIN ATOMIC`, тогда как другие параметры всегда фиксируются в одно и то же значение.</span><span class="sxs-lookup"><span data-stu-id="93674-128">Some settings can be specified with `BEGIN ATOMIC` while other settings are always fixed to the same value.</span></span>  
  
 <span data-ttu-id="93674-129">Требуются следующие параметры с `BEGIN ATOMIC`.</span><span class="sxs-lookup"><span data-stu-id="93674-129">The following options are required with `BEGIN ATOMIC`:</span></span>  
  
|<span data-ttu-id="93674-130">Обязательный параметр</span><span class="sxs-lookup"><span data-stu-id="93674-130">Required Setting</span></span>|<span data-ttu-id="93674-131">Описание</span><span class="sxs-lookup"><span data-stu-id="93674-131">Description</span></span>|  
|----------------------|-----------------|  
|`TRANSACTION ISOLATION LEVEL`|<span data-ttu-id="93674-132">Поддерживаются значения `SNAPSHOT`, `REPEATABLEREAD` и `SERIALIZABLE`.</span><span class="sxs-lookup"><span data-stu-id="93674-132">Supported values are `SNAPSHOT`, `REPEATABLEREAD`, and `SERIALIZABLE`.</span></span>|  
|`LANGUAGE`|<span data-ttu-id="93674-133">Определяет форматы даты и времени и системных сообщений.</span><span class="sxs-lookup"><span data-stu-id="93674-133">Determines date and time formats and system messages.</span></span> <span data-ttu-id="93674-134">Все языки и псевдонимы в [sys.syslanguages & #40; Transact-SQL & #41;](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql)поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="93674-134">All languages and aliases in [sys.syslanguages &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) are supported.</span></span>|  
  
 <span data-ttu-id="93674-135">Следующие параметры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="93674-135">The following settings are optional:</span></span>  
  
|<span data-ttu-id="93674-136">Необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="93674-136">Optional Setting</span></span>|<span data-ttu-id="93674-137">Описание</span><span class="sxs-lookup"><span data-stu-id="93674-137">Description</span></span>|  
|----------------------|-----------------|  
|`DATEFORMAT`|<span data-ttu-id="93674-138">Поддерживаются все форматы даты, отличные от [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93674-138">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date formats are supported.</span></span> <span data-ttu-id="93674-139">Если он указан, параметр `DATEFORMAT` переопределяет формат даты по умолчанию, связанный с объектом `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="93674-139">When specified, `DATEFORMAT` overrides the default date format associated with `LANGUAGE`.</span></span>|  
|`DATEFIRST`|<span data-ttu-id="93674-140">Если он указан, параметр `DATEFIRST` переопределяет значение по умолчанию, связанное с `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="93674-140">When specified, `DATEFIRST` overrides the default associated with `LANGUAGE`.</span></span>|  
|`DELAYED_DURABILITY`|<span data-ttu-id="93674-141">Поддерживаемые значения: `OFF` и `ON`.</span><span class="sxs-lookup"><span data-stu-id="93674-141">Supported values are `OFF` and `ON`.</span></span><br /><br /> <span data-ttu-id="93674-142">Фиксации транзакций [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут быть полностью устойчивыми (вариант по умолчанию) или отложенно устойчивыми. Дополнительные сведения см. в статье [Управление устойчивостью транзакций](../logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="93674-142">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transaction commits can be either fully durable, the default, or delayed durable.For more information, see [Control Transaction Durability](../logs/control-transaction-durability.md).</span></span>|  
  
 <span data-ttu-id="93674-143">Следующие параметры SET имеют одно и то же значение по умолчанию для всех блоков ATOMIC во всех хранимых процедурах, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="93674-143">The following SET options have the same system default value for all atomic blocks in all natively compiled stored procedures:</span></span>  
  
|<span data-ttu-id="93674-144">Установленный параметр</span><span class="sxs-lookup"><span data-stu-id="93674-144">Set Option</span></span>|<span data-ttu-id="93674-145">Системные значения по умолчанию для блоков ATOMIC</span><span class="sxs-lookup"><span data-stu-id="93674-145">System Default for Atomic Blocks</span></span>|  
|----------------|--------------------------------------|  
|<span data-ttu-id="93674-146">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="93674-146">ANSI_NULLS</span></span>|<span data-ttu-id="93674-147">ON</span><span class="sxs-lookup"><span data-stu-id="93674-147">ON</span></span>|  
|<span data-ttu-id="93674-148">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="93674-148">ANSI_PADDING</span></span>|<span data-ttu-id="93674-149">ON</span><span class="sxs-lookup"><span data-stu-id="93674-149">ON</span></span>|  
|<span data-ttu-id="93674-150">ANSI_WARNING</span><span class="sxs-lookup"><span data-stu-id="93674-150">ANSI_WARNING</span></span>|<span data-ttu-id="93674-151">ON</span><span class="sxs-lookup"><span data-stu-id="93674-151">ON</span></span>|  
|<span data-ttu-id="93674-152">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="93674-152">ARITHABORT</span></span>|<span data-ttu-id="93674-153">ON</span><span class="sxs-lookup"><span data-stu-id="93674-153">ON</span></span>|  
|<span data-ttu-id="93674-154">ARITHIGNORE</span><span class="sxs-lookup"><span data-stu-id="93674-154">ARITHIGNORE</span></span>|<span data-ttu-id="93674-155">OFF</span><span class="sxs-lookup"><span data-stu-id="93674-155">OFF</span></span>|  
|<span data-ttu-id="93674-156">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="93674-156">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="93674-157">ON</span><span class="sxs-lookup"><span data-stu-id="93674-157">ON</span></span>|  
|<span data-ttu-id="93674-158">IDENTITY_INSERT</span><span class="sxs-lookup"><span data-stu-id="93674-158">IDENTITY_INSERT</span></span>|<span data-ttu-id="93674-159">OFF</span><span class="sxs-lookup"><span data-stu-id="93674-159">OFF</span></span>|  
|<span data-ttu-id="93674-160">NOCOUNT</span><span class="sxs-lookup"><span data-stu-id="93674-160">NOCOUNT</span></span>|<span data-ttu-id="93674-161">ON</span><span class="sxs-lookup"><span data-stu-id="93674-161">ON</span></span>|  
|<span data-ttu-id="93674-162">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="93674-162">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="93674-163">OFF</span><span class="sxs-lookup"><span data-stu-id="93674-163">OFF</span></span>|  
|<span data-ttu-id="93674-164">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="93674-164">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="93674-165">ON</span><span class="sxs-lookup"><span data-stu-id="93674-165">ON</span></span>|  
|<span data-ttu-id="93674-166">ROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="93674-166">ROWCOUNT</span></span>|<span data-ttu-id="93674-167">0</span><span class="sxs-lookup"><span data-stu-id="93674-167">0</span></span>|  
|<span data-ttu-id="93674-168">TEXTSIZE</span><span class="sxs-lookup"><span data-stu-id="93674-168">TEXTSIZE</span></span>|<span data-ttu-id="93674-169">0</span><span class="sxs-lookup"><span data-stu-id="93674-169">0</span></span>|  
|<span data-ttu-id="93674-170">XACT_ABORT</span><span class="sxs-lookup"><span data-stu-id="93674-170">XACT_ABORT</span></span>|<span data-ttu-id="93674-171">OFF</span><span class="sxs-lookup"><span data-stu-id="93674-171">OFF</span></span><br /><br /> <span data-ttu-id="93674-172">Неперехваченные исключения приводят к откату блока ATOMIC, но не вызывают прерывание транзакции, если ошибка не критична для транзакции.</span><span class="sxs-lookup"><span data-stu-id="93674-172">Uncaught exceptions cause the atomic block to roll back, but not cause the transaction to abort unless the error is transaction dooming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93674-173">См. также:</span><span class="sxs-lookup"><span data-stu-id="93674-173">See Also</span></span>  
 [<span data-ttu-id="93674-174">Скомпилированные в собственном коде хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="93674-174">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
