---
title: Рекомендации по логике повторных попыток для транзакций в таблицах, оптимизированных для памяти | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f2a35c37-4449-49ee-8bba-928028f1de66
author: stevestein
ms.author: sstein
ms.openlocfilehash: c9ffaccefb8d4e0a3044c4858a06029fd4350354
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732929"
---
# <a name="guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables"></a><span data-ttu-id="d60b5-102">Рекомендации для логики повторного выполнения транзакций для таблиц, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="d60b5-102">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>
  <span data-ttu-id="d60b5-103">Условия ошибки, возникающие с транзакциями, которые обращаются к оптимизированным для памяти таблицам.</span><span class="sxs-lookup"><span data-stu-id="d60b5-103">There are error conditions that occur with transactions that access memory-optimized tables.</span></span>  
  
-   41302. <span data-ttu-id="d60b5-104">Текущая транзакция попыталась обновить запись, которая была изменена после начала этой транзакции.</span><span class="sxs-lookup"><span data-stu-id="d60b5-104">The current transaction attempted to update a record that has been updated since the transaction started.</span></span>  
  
-   41305. <span data-ttu-id="d60b5-105">Текущей транзакции не удалось выполнить фиксацию из-за ошибки проверки уровня изоляции REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="d60b5-105">The current transaction failed to commit due to a repeatable read validation failure.</span></span>  
  
-   41325. <span data-ttu-id="d60b5-106">Текущей транзакции не удалось выполнить фиксацию из-за ошибки сериализуемой проверки.</span><span class="sxs-lookup"><span data-stu-id="d60b5-106">The current transaction failed to commit due to a serializable validation failure.</span></span>  
  
-   41301. <span data-ttu-id="d60b5-107">Предыдущая транзакция, от которой зависит текущая транзакция, прервана, текущая транзакция не может быть зафиксирована.</span><span class="sxs-lookup"><span data-stu-id="d60b5-107">A previous transaction that the current transaction took a dependency on has aborted, and the current transaction can no longer commit.</span></span>  
  
 <span data-ttu-id="d60b5-108">Частая причина этих ошибок — взаимодействие одновременно выполняющихся транзакций.</span><span class="sxs-lookup"><span data-stu-id="d60b5-108">A common cause of these errors is interference between concurrently executing transaction.</span></span> <span data-ttu-id="d60b5-109">Общее действие для исправления — повторное выполнение транзакции.</span><span class="sxs-lookup"><span data-stu-id="d60b5-109">The common corrective action is to retry the transaction.</span></span>  
  
 <span data-ttu-id="d60b5-110">Дополнительные сведения об этих условиях ошибки см. в разделе об обнаружении конфликтов, проверке и проверке зависимостей фиксации в [транзакциях в таблицах, оптимизированных для памяти](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d60b5-110">For more information about these error conditions, see the section on Conflict Detection, Validation, and Commit Dependency Checks in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="d60b5-111">Взаимоблокировки (код ошибки 1205) не могут возникнуть для оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="d60b5-111">Deadlocks (error code 1205) cannot occur for memory-optimized tables.</span></span> <span data-ttu-id="d60b5-112">Блокировки не используются для оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="d60b5-112">Locks are not used for memory-optimized tables.</span></span> <span data-ttu-id="d60b5-113">Но если приложение уже содержит логику повторных попыток для взаимоблокировок, ее можно расширить для поддержки новых кодов ошибок.</span><span class="sxs-lookup"><span data-stu-id="d60b5-113">However, if the application already contains retry logic for deadlocks, the existing logic could be extended to include the new error codes.</span></span>  
  
## <a name="considerations-for-retrying"></a><span data-ttu-id="d60b5-114">Рекомендации для повторных попыток</span><span class="sxs-lookup"><span data-stu-id="d60b5-114">Considerations for Retrying</span></span>  
 <span data-ttu-id="d60b5-115">Обычно в приложениях возникает конфликт между транзакциями и требуется реализовать логику устранения этих конфликтов.</span><span class="sxs-lookup"><span data-stu-id="d60b5-115">Applications will typically encounter conflicts between transactions and need to implement retry logic to resolve those conflicts.</span></span> <span data-ttu-id="d60b5-116">Количество обнаруженных конфликтов зависит от нескольких факторов.</span><span class="sxs-lookup"><span data-stu-id="d60b5-116">The number of conflicts encountered depends on a number of factors:</span></span>  
  
-   <span data-ttu-id="d60b5-117">Конфликты отдельных строк.</span><span class="sxs-lookup"><span data-stu-id="d60b5-117">Contention for individual rows.</span></span> <span data-ttu-id="d60b5-118">Возможность появления конфликтов растет с числом транзакций, которые пытаются обновить одну и ту же строку.</span><span class="sxs-lookup"><span data-stu-id="d60b5-118">The potential for conflicts increases as the number of transactions attempting to update the same row increases.</span></span>  
  
-   <span data-ttu-id="d60b5-119">Количество строк, считываемых транзакциями REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="d60b5-119">Number of rows read by REPEATABLE READ transactions.</span></span> <span data-ttu-id="d60b5-120">Чем больше строк считывается, тем выше вероятность того, что некоторые из них обновляются параллельными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="d60b5-120">The more rows read, the greater the chance that some of these rows are updated by concurrent transactions.</span></span> <span data-ttu-id="d60b5-121">Это приводит к ошибкам проверки операций чтения с возможностью повторения.</span><span class="sxs-lookup"><span data-stu-id="d60b5-121">This causes repeatable read validation failures.</span></span>  
  
-   <span data-ttu-id="d60b5-122">Размер диапазонов сканирования, используемых транзакциями SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="d60b5-122">Size of the scan ranges used by SERIALIZABLE transactions.</span></span> <span data-ttu-id="d60b5-123">Чем больше диапазон сканирования, тем выше вероятность того, что параллельные транзакции сформируют фантомные строки и вызовут ошибки проверки сериализации.</span><span class="sxs-lookup"><span data-stu-id="d60b5-123">The larger the scan ranges, the higher the chance that concurrent transactions will introduce phantom rows, causing serializable validation failures.</span></span>  
  
     <span data-ttu-id="d60b5-124">Приложению трудно избежать таких конфликтов, для этого нужна логика повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="d60b5-124">It is difficult for an application to avoid these conflicts, requiring retry logic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d60b5-125">Транзакциям для чтения и записи, которые обращаются к оптимизированным для памяти таблицам, требуется логика повторов.</span><span class="sxs-lookup"><span data-stu-id="d60b5-125">Read-write transactions that access memory-optimized tables require retry logic.</span></span>  
  
### <a name="considerations-for-read-only-transactions-and-natively-compiled-stored-procedures"></a><span data-ttu-id="d60b5-126">Рекомендации для транзакций только для чтения и скомпилированные в памяти хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="d60b5-126">Considerations for Read-Only Transactions and Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="d60b5-127">Транзакциям в режиме только для чтения, охватывающим выполнение одной скомпилированной в собственном коде хранимой процедуры, не требуется проверка транзакций REPEATABLE READ и SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="d60b5-127">Read-only transactions that span a single execution of a natively compiled stored procedure do not require validation for REPEATABLE READ and SERIALIZABLE transactions.</span></span> <span data-ttu-id="d60b5-128">Для транзакций только для чтения конфликты операций записи не возникают.</span><span class="sxs-lookup"><span data-stu-id="d60b5-128">Write conflicts cannot occur due to a transaction being read-only.</span></span>  
  
 <span data-ttu-id="d60b5-129">Однако по-прежнему могут возникать ошибки зависимости.</span><span class="sxs-lookup"><span data-stu-id="d60b5-129">However, dependency failures can still occur.</span></span> <span data-ttu-id="d60b5-130">Они реже, чем ошибки в результате конфликтов.</span><span class="sxs-lookup"><span data-stu-id="d60b5-130">Dependency failures are rarer than errors resulting from conflicts.</span></span> <span data-ttu-id="d60b5-131">Поэтому во многих случаях не требуется специфическая логика повторов для транзакций только для чтения, охватывающих одно выполнение скомпилированных в собственном коде хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="d60b5-131">Therefore, in many cases, specific retry logic is not required for read-only transactions that span single executions of natively compiled stored procedures.</span></span>  
  
### <a name="considerations-for-read-only-transactions-and-cross-container-transactions"></a><span data-ttu-id="d60b5-132">Рекомендации для транзакций только для чтения и транзакций между контейнерами</span><span class="sxs-lookup"><span data-stu-id="d60b5-132">Considerations for Read-Only Transactions and Cross-Container Transactions</span></span>  
 <span data-ttu-id="d60b5-133">Транзакции между контейнерами только для чтения, которые запускаются вне контекста хранимой процедуры, скомпилированной в собственном коде, не проверяют, осуществляется ли доступ к оптимизированным для памяти таблицам с уровнем изоляции SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="d60b5-133">Read-only cross-container transactions, which are transactions that are started outside the context of a natively compiled stored procedure, do not perform validation if the memory-optimized tables are all accessed under SNAPSHOT isolation.</span></span> <span data-ttu-id="d60b5-134">Однако при доступе к оптимизированным для памяти таблицам в изоляции REPEATABLE READ или SERIALIZABLE проверка выполняется в момент фиксации.</span><span class="sxs-lookup"><span data-stu-id="d60b5-134">However, when memory-optimized tables are accessed under REPEATABLE READ or SERIALIZABLE isolation, validation is performed at commit time.</span></span> <span data-ttu-id="d60b5-135">В этом случае может потребоваться логика повторов.</span><span class="sxs-lookup"><span data-stu-id="d60b5-135">In this case, retry logic may be required.</span></span>  
  
 <span data-ttu-id="d60b5-136">Дополнительные сведения см. в разделе о транзакциях между контейнерами в [уровнях изоляции транзакций](../../2014/database-engine/transaction-isolation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d60b5-136">For more information, see the section on Cross-Container Transactions in [Transaction Isolation Levels](../../2014/database-engine/transaction-isolation-levels.md).</span></span>  
  
## <a name="implementing-retry-logic"></a><span data-ttu-id="d60b5-137">Реализация логики повторов</span><span class="sxs-lookup"><span data-stu-id="d60b5-137">Implementing Retry Logic</span></span>  
 <span data-ttu-id="d60b5-138">Как и в случае с другими транзакциями, которые обращаются к таблицам, оптимизированным для памяти, следует принять во внимание логику повторов для обработки потенциальных неполадок, например записи конфликтов (код ошибки 41302) или ошибок зависимости (код ошибки 41301).</span><span class="sxs-lookup"><span data-stu-id="d60b5-138">As with all transactions that access memory-optimized tables, you need to consider retry logic to handle potential failures, such as write conflicts (error code 41302) or dependency failures (error code 41301).</span></span> <span data-ttu-id="d60b5-139">В большинстве приложений интенсивность отказов будет низкой, но все же необходимо обрабатывать ошибки, повторно выполняя транзакции.</span><span class="sxs-lookup"><span data-stu-id="d60b5-139">In most applications the failure rate will be low, but it is still necessary to handle failures by retrying the transaction.</span></span> <span data-ttu-id="d60b5-140">Два возможных метода реализации логики повторного выполнения:</span><span class="sxs-lookup"><span data-stu-id="d60b5-140">Two suggested ways of implementing retry logic are:</span></span>  
  
-   <span data-ttu-id="d60b5-141">Клиентские повторы попыток.</span><span class="sxs-lookup"><span data-stu-id="d60b5-141">Client-side retries.</span></span> <span data-ttu-id="d60b5-142">В общем случае повторения на стороне клиента — предпочтительный способ реализации логики повторов.</span><span class="sxs-lookup"><span data-stu-id="d60b5-142">Client-side retries is the preferred way to implement retry logic in the general case.</span></span> <span data-ttu-id="d60b5-143">Клиентское приложение перехватывает ошибку, сформированную транзакцией, и пытается повторить транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d60b5-143">The client application catches the error thrown by the transaction, and retries the transaction.</span></span> <span data-ttu-id="d60b5-144">Если существующее клиентское приложение содержит логику повтора попыток для обработки взаимоблокировок, приложение можно расширить с целью обработки новых ошибок.</span><span class="sxs-lookup"><span data-stu-id="d60b5-144">If an existing client application has retry logic to handle deadlocks, you can extend the application to handle the new error codes.</span></span>  
  
-   <span data-ttu-id="d60b5-145">Использование хранимой процедуры оболочки.</span><span class="sxs-lookup"><span data-stu-id="d60b5-145">Using a wrapper stored procedure.</span></span> <span data-ttu-id="d60b5-146">Клиент вызывает интерпретированную хранимую процедуру [!INCLUDE[tsql](../includes/tsql-md.md)], которая запускает скомпилированную в собственном коде хранимую процедуру или выполняет транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d60b5-146">The client calls an interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] stored procedure that calls the natively compiled stored procedure or executes the transaction.</span></span> <span data-ttu-id="d60b5-147">Затем в процедуре оболочки используется логика try/catch для обнаружения ошибок и повторения вызова процедуры при необходимости.</span><span class="sxs-lookup"><span data-stu-id="d60b5-147">The wrapper procedure then uses try/catch logic to catch the error and retry the procedure call if needed.</span></span> <span data-ttu-id="d60b5-148">Возможна ситуация, при которой результаты будут возвращены клиенту до возникновения ошибки и клиент не будет располагать информацией, чтобы отбросить их.</span><span class="sxs-lookup"><span data-stu-id="d60b5-148">It is possible that results are returned to the client before the failure, and the client would not know to discard them.</span></span> <span data-ttu-id="d60b5-149">Поэтому, чтобы обезопасить себя, лучше всего использовать этот метод только с изначально скомпилированными в собственном коде хранимыми процедурами, которые не возвращают клиенту никаких результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="d60b5-149">Therefore, to be safe, it is best to use this method only with natively compiled stored procedures that do not return any result sets to the client.</span></span>  
  
 <span data-ttu-id="d60b5-150">Логику повторов можно реализовать в [!INCLUDE[tsql](../includes/tsql-md.md)] или в коде приложения среднего уровня.</span><span class="sxs-lookup"><span data-stu-id="d60b5-150">The retry logic can be implemented either in [!INCLUDE[tsql](../includes/tsql-md.md)] or in the application code in the mid-tier.</span></span>  
  
 <span data-ttu-id="d60b5-151">Существуют две возможные причины, чтобы рассматривать возможность реализации логики повторов.</span><span class="sxs-lookup"><span data-stu-id="d60b5-151">Two possible reasons to consider the retry logic are:</span></span>  
  
-   <span data-ttu-id="d60b5-152">Клиентское приложение использует логику повторов для других кодов ошибок, например 1205, которую можно расширить.</span><span class="sxs-lookup"><span data-stu-id="d60b5-152">The client application has retry logic for other error codes, such as 1205, which you can extend.</span></span>  
  
-   <span data-ttu-id="d60b5-153">Конфликты происходят редко, и важно уменьшить сквозную задержку с помощью подготовленного выполнения.</span><span class="sxs-lookup"><span data-stu-id="d60b5-153">Conflicts are rare, and it is important to reduce end-to-end latency by using prepared execution.</span></span> <span data-ttu-id="d60b5-154">Дополнительные сведения о непосредственном запуске хранимых процедур, скомпилированных в собственном режиме, см. в разделе [хранимые процедуры, скомпилированные в собственном](../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md)виде.</span><span class="sxs-lookup"><span data-stu-id="d60b5-154">For more information about executing natively compiled stored procedures directly, see [Natively Compiled Stored Procedures](../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="d60b5-155">В следующем примере показана логика повторов в интерпретированной хранимой процедуре [!INCLUDE[tsql](../includes/tsql-md.md)], которая содержит вызов хранимой процедуры, скомпилированной в собственном коде, или транзакции между контейнерами.</span><span class="sxs-lookup"><span data-stu-id="d60b5-155">The following sample shows retry logic in an interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] stored procedure that contains a call either to a natively compiled stored procedure or to a cross-container transaction.</span></span>  
  
```sql  
CREATE PROCEDURE usp_my_procedure @param1 type1, @param2 type2, ...  
AS  
BEGIN  
  -- number of retries - tune based on the workload  
  DECLARE @retry INT = 10  
  
  WHILE (@retry > 0)  
  BEGIN  
    BEGIN TRY  
  
      -- exec usp_my_native_proc @param1, @param2, ...  
  
      --       or  
  
      -- BEGIN TRANSACTION  
      --   ...  
      -- COMMIT TRANSACTION  
  
      SET @retry = 0  
    END TRY  
    BEGIN CATCH  
      SET @retry -= 1  
  
      -- the error number for deadlocks (1205) does not need to be included for   
      -- transactions that do not access disk-based tables  
      IF (@retry > 0 AND error_number() in (41302, 41305, 41325, 41301, 1205))  
      BEGIN  
        -- these error conditions are transaction dooming - rollback the transaction  
        -- this is not needed if the transaction spans a single native proc execution  
        --   as the native proc will simply rollback when an error is thrown   
        IF XACT_STATE() = -1  
          ROLLBACK TRANSACTION  
  
        -- use a delay if there is a high rate of write conflicts (41302)  
        --   length of delay should depend on the typical duration of conflicting transactions  
        -- WAITFOR DELAY '00:00:00.001'  
      END  
      ELSE  
      BEGIN  
        -- insert custom error handling for other error conditions here  
  
        -- throw if this is not a qualifying error condition  
        ;THROW  
      END  
    END CATCH  
  END  
END  
```  
  
## <a name="see-also"></a><span data-ttu-id="d60b5-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="d60b5-156">See Also</span></span>  
 <span data-ttu-id="d60b5-157">[Основные сведения о транзакциях в таблицах, оптимизированных для памяти](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="d60b5-157">[Understanding Transactions on Memory-Optimized Tables](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="d60b5-158">[Транзакции в таблицах, оптимизированных для памяти](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="d60b5-158">[Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="d60b5-159">Рекомендации для уровней изоляции транзакций с таблицами, оптимизированными для памяти</span><span class="sxs-lookup"><span data-stu-id="d60b5-159">Guidelines for Transaction Isolation Levels with Memory-Optimized Tables</span></span>](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md)  
  
  
