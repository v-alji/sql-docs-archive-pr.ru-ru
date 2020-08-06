---
title: Транзакции между контейнерами | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5d84b51a-ec17-4c5c-b80e-9e994fc8ae80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28437f0903459616a574e713c0f138e8bb459870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664469"
---
# <a name="cross-container-transactions"></a><span data-ttu-id="1ee33-102">Транзакции между контейнерами</span><span class="sxs-lookup"><span data-stu-id="1ee33-102">Cross-Container Transactions</span></span>
  <span data-ttu-id="1ee33-103">Транзакции между контейнерами представляют собой неявные или явные пользовательские транзакции, включающие вызовы хранимых процедур, скомпилированных в собственном коде, или операции над оптимизированными для памяти таблицами.</span><span class="sxs-lookup"><span data-stu-id="1ee33-103">Cross-container transactions are either implicit or explicit user transactions that include calls to natively-compiled stored procedures or operations on memory-optimized tables.</span></span>  
  
 <span data-ttu-id="1ee33-104">В [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] вызовы хранимых процедур не инициируют транзакцию.</span><span class="sxs-lookup"><span data-stu-id="1ee33-104">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], calls to stored procedures do not initiate a transaction.</span></span> <span data-ttu-id="1ee33-105">Выполнение хранимых процедур, скомпилированных в собственном коде, в режиме автоматической фиксации (не в контексте пользовательской транзакции) не считается транзакциями между контейнерами.</span><span class="sxs-lookup"><span data-stu-id="1ee33-105">Executions of natively compiled procedures in autocommit mode (not in the context of a user transaction) are not considered cross-container transactions.</span></span>  
  
 <span data-ttu-id="1ee33-106">Любой интерпретируемый запрос, который ссылается на оптимизированные для памяти таблицы, считается частью транзакции между контейнерами, как при выполнении из явных или неявных транзакций, так и в режиме автоматической фиксации.</span><span class="sxs-lookup"><span data-stu-id="1ee33-106">Any interpreted query that references memory-optimized tables is considered a part of a cross-container transaction, whether executed from an explicit or implicit transaction or in auto-commit mode.</span></span>  
  
##  <a name="isolation-of-individual-operations"></a><a name="isolation"></a><span data-ttu-id="1ee33-107">Изоляция отдельных операций</span><span class="sxs-lookup"><span data-stu-id="1ee33-107">Isolation of Individual Operations</span></span>  
 <span data-ttu-id="1ee33-108">Каждая транзакция [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] имеет уровень изоляции.</span><span class="sxs-lookup"><span data-stu-id="1ee33-108">Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] transaction has an isolation level.</span></span> <span data-ttu-id="1ee33-109">Уровень изоляции по умолчанию — READ COMMITTED.</span><span class="sxs-lookup"><span data-stu-id="1ee33-109">The default isolation level is Read Committed.</span></span> <span data-ttu-id="1ee33-110">Чтобы использовать другой уровень изоляции, можно задать уровень изоляции с помощью [инструкции SET TRANSACTION изоляцией &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1ee33-110">To use a different isolation level, you can set the isolation level using [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
 <span data-ttu-id="1ee33-111">Часто приходится выполнять операции над оптимизированными для памяти таблицами с другим уровнем изоляции, чем операции над дисковыми таблицами.</span><span class="sxs-lookup"><span data-stu-id="1ee33-111">It is often necessary to perform operations on memory-optimized tables at a different isolation level than operations on disk-based tables.</span></span> <span data-ttu-id="1ee33-112">В транзакции можно задать другой уровень изоляции для коллекции инструкций или отдельной операции считывания.</span><span class="sxs-lookup"><span data-stu-id="1ee33-112">In a transaction, it is possible to set a different isolation level for a collection of statements or for an individual read operation.</span></span>  
  
### <a name="specifying-the-isolation-level-of-individual-operations"></a><span data-ttu-id="1ee33-113">Задание уровня изоляции отдельных операций</span><span class="sxs-lookup"><span data-stu-id="1ee33-113">Specifying the Isolation Level of Individual Operations</span></span>  
 <span data-ttu-id="1ee33-114">Чтобы задать другой уровень изоляции для набора инструкций в транзакции, можно использовать `SET TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="1ee33-114">To set a different isolation level for a set of statements in a transaction, you can use `SET TRANSACTION ISOLATION LEVEL`.</span></span> <span data-ttu-id="1ee33-115">В следующем примере транзакции по умолчанию используется уровень изоляции SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="1ee33-115">The following example of a transaction uses the serializable isolation level as default.</span></span> <span data-ttu-id="1ee33-116">Операции вставки и выбора над t3, t2 и t1 выполняются при использовании уровня изоляции REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="1ee33-116">The insert and select operations on t3, t2, and t1 are executed under repeatable read isolation.</span></span>  
  
```sql  
set transaction isolation level serializable  
go  
  
begin transaction  
 ......  
  set transaction isolation level repeatable read  
  
  insert t3 select * from t1 join t2 on t1.id=t2.id  
  
  set transaction isolation level serializable  
 ......  
commit  
```  
  
 <span data-ttu-id="1ee33-117">Чтобы задать уровень изоляции для отдельных операций чтения, отличный от назначаемого транзакции по умолчанию, можно использовать табличное указание (например, SERIALIZABLE).</span><span class="sxs-lookup"><span data-stu-id="1ee33-117">To set an isolation level for individual read operations that is different from the transaction default, you can use a table hint (for example, serializable).</span></span> <span data-ttu-id="1ee33-118">Каждый выбор соответствует операции считывания, а каждое обновление и каждое удаление соответствуют чтению, поскольку строку всегда необходимо прочитать, прежде чем ее можно будет обновить или удалить.</span><span class="sxs-lookup"><span data-stu-id="1ee33-118">Every select corresponds to a read operation and every update and every delete corresponds to a read, because the row always needs to be read before it can be updated or deleted.</span></span> <span data-ttu-id="1ee33-119">Операции вставки не имеют уровня изоляции, поскольку запись всегда изолирована в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ee33-119">Insert operations do not have an isolation level, because writes are always isolated in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1ee33-120">В следующем примере уровень изоляции по умолчанию для транзакций — READ COMMITTED, но доступ к таблице t1 происходит в режиме изоляции SERIALIZABLE, а к таблице t2 — в режиме изоляции SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="1ee33-120">In the following example, the default isolation level for the transaction is read committed, but table t1 is accessed under serializable and t2 under snapshot isolation.</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
 ......  
  
  insert t3 select * from t1 (serializable) join t2 (snapshot) on t1.id=t2.id  
  
  ......  
commit  
```  
  
### <a name="isolation-semantics-for-individual-operations"></a><span data-ttu-id="1ee33-121">Семантика изоляции для отдельных операций</span><span class="sxs-lookup"><span data-stu-id="1ee33-121">Isolation Semantics for Individual Operations</span></span>  
 <span data-ttu-id="1ee33-122">Cериализуемая транзакция T выполняется в полной изоляции.</span><span class="sxs-lookup"><span data-stu-id="1ee33-122">A serializable transaction T is executed in complete isolation.</span></span> <span data-ttu-id="1ee33-123">То есть как бы каждая другая транзакция зафиксирована перед запуском T или запущена после фиксации T.</span><span class="sxs-lookup"><span data-stu-id="1ee33-123">It is as if every other transaction has either committed before T started, or is started after T committed.</span></span> <span data-ttu-id="1ee33-124">Ситуация становится более сложной, если различные операции в транзакции имеют разные уровни изоляции.</span><span class="sxs-lookup"><span data-stu-id="1ee33-124">It becomes more complex when different operations in a transaction have different isolation levels.</span></span>  
  
 <span data-ttu-id="1ee33-125">Общая семантика уровней изоляции транзакций в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , а также влияние на блокировку, объясняется в описании [инструкции SET TRANSACTION изоляцией Level &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1ee33-125">The general semantics of the transaction isolation levels in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], along with the implications on locking, is explained in [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
 <span data-ttu-id="1ee33-126">Для транзакций между контейнерами, где различные операции могут иметь различные уровни изоляции, необходимо понимать семантику изоляции отдельных операций чтения.</span><span class="sxs-lookup"><span data-stu-id="1ee33-126">For cross-container transactions where different operations may have different isolation levels, you need to understand the semantics of isolation of individual read operations.</span></span> <span data-ttu-id="1ee33-127">Операции записи всегда изолированы.</span><span class="sxs-lookup"><span data-stu-id="1ee33-127">Write operations are always isolated.</span></span> <span data-ttu-id="1ee33-128">Записи в разных транзакциях не могут повлиять друг на друга.</span><span class="sxs-lookup"><span data-stu-id="1ee33-128">Writes in different transactions cannot impact each other.</span></span>  
  
 <span data-ttu-id="1ee33-129">Операция считывания данных возвращает несколько строк, удовлетворяющих условию фильтра.</span><span class="sxs-lookup"><span data-stu-id="1ee33-129">A data read operation returns a number of rows that satisfy a filter condition.</span></span>  
  
 <span data-ttu-id="1ee33-130">Операции чтения выполняются как часть транзакции T. уровни изоляции для операций чтения могут быть понятны с точки зрения,</span><span class="sxs-lookup"><span data-stu-id="1ee33-130">Reads are performed as part of a transaction T. Isolation levels for read operations can be understood in terms of,</span></span>  
  
 <span data-ttu-id="1ee33-131">Состояние фиксации</span><span class="sxs-lookup"><span data-stu-id="1ee33-131">Commit Status</span></span>  
 <span data-ttu-id="1ee33-132">Состояние фиксации указывает, гарантирована ли фиксация считывания данных.</span><span class="sxs-lookup"><span data-stu-id="1ee33-132">Commit status refers to whether the data read is guaranteed to be committed.</span></span>  
  
 <span data-ttu-id="1ee33-133">Согласованность (транзакций)</span><span class="sxs-lookup"><span data-stu-id="1ee33-133">(Transactional) Consistency</span></span>  
 <span data-ttu-id="1ee33-134">Согласованность транзакций для набора операция чтения показывает, гарантировано ли, что чтение версий строк будет включать обновления из точно такого же набора транзакций.</span><span class="sxs-lookup"><span data-stu-id="1ee33-134">Transactional consistency for a set of reads refers to whether the row versions read are all guaranteed to include updates from precisely the same set of transactions.</span></span>  
  
 <span data-ttu-id="1ee33-135">Гарантии стабильности система дает транзакции T относительно считывания данных.</span><span class="sxs-lookup"><span data-stu-id="1ee33-135">Stability guarantees the system gives to transaction T about the data read.</span></span>  
 <span data-ttu-id="1ee33-136">Стабильность определяет, являются ли операции чтения транзакций повторяемыми.</span><span class="sxs-lookup"><span data-stu-id="1ee33-136">Stability refers to whether the transaction's reads are repeatable.</span></span> <span data-ttu-id="1ee33-137">То есть, если операции чтения повторяются, возвратят ли они одни и те же строки и версии строк?</span><span class="sxs-lookup"><span data-stu-id="1ee33-137">That is, if the reads were repeated would they return the same rows and row versions?</span></span>  
  
 <span data-ttu-id="1ee33-138">Некоторые гарантии относятся ко времени логического завершения транзакции.</span><span class="sxs-lookup"><span data-stu-id="1ee33-138">Certain guarantees refer to the logical end time of the transaction.</span></span> <span data-ttu-id="1ee33-139">В целом время логического завершения — это время фиксации транзакции в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1ee33-139">In general, the logical end time is the time the transaction is committed to the database.</span></span> <span data-ttu-id="1ee33-140">Если транзакция выполняет доступ к оптимизируемым для памяти таблицам, то время логического завершения технически представляет собой начало этапа проверки.</span><span class="sxs-lookup"><span data-stu-id="1ee33-140">If memory-optimized tables are accessed by the transaction, the logical end time is technically the beginning of the validation phase.</span></span> <span data-ttu-id="1ee33-141">(Дополнительные сведения см. в статье обсуждение времени существования транзакций в [транзакциях в таблицах, оптимизированных для памяти](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="1ee33-141">(For more information, see the transaction lifetime discussion in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="1ee33-142">Независимо от уровня изоляции транзакция (T) всегда видит свои собственные обновления.</span><span class="sxs-lookup"><span data-stu-id="1ee33-142">Regardless of isolation level, a transaction (T) always sees its own updates:</span></span>  
  
 <span data-ttu-id="1ee33-143">READ UNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="1ee33-143">READ UNCOMMITTED</span></span>  
 <span data-ttu-id="1ee33-144">Чтение данных не может быть зафиксировано, согласовано или стабильно.</span><span class="sxs-lookup"><span data-stu-id="1ee33-144">The data read may neither be committed, consistent, or stable.</span></span> <span data-ttu-id="1ee33-145">Однако оно содержит операции записи, выполненные ранее транзакцией T.</span><span class="sxs-lookup"><span data-stu-id="1ee33-145">However, it will include earlier write operations done by T.</span></span>  
  
 <span data-ttu-id="1ee33-146">READ COMMITTED</span><span class="sxs-lookup"><span data-stu-id="1ee33-146">READ COMMITTED</span></span>  
 <span data-ttu-id="1ee33-147">Считывание данных будет зафиксировано.</span><span class="sxs-lookup"><span data-stu-id="1ee33-147">The data read will be committed.</span></span>  
  
 <span data-ttu-id="1ee33-148">SNAPSHOT</span><span class="sxs-lookup"><span data-stu-id="1ee33-148">SNAPSHOT</span></span>  
 <span data-ttu-id="1ee33-149">Все операции считывания, выполняемые транзакцией T в режиме изоляции SNAPSHOT, имеют то же время логического чтения, которое представляет собой начало транзакции.</span><span class="sxs-lookup"><span data-stu-id="1ee33-149">All read operations performed by T under snapshot isolation have the same logical read time, which is the beginning of the transaction.</span></span> <span data-ttu-id="1ee33-150">Считывание данных гарантированно фиксируется и согласовано для времени логического чтения.</span><span class="sxs-lookup"><span data-stu-id="1ee33-150">The data read is guaranteed to be committed and consistent as of the logical read time.</span></span> <span data-ttu-id="1ee33-151">Повтор чтения во время первоначального чтения гарантированно возвращает тот же результат.</span><span class="sxs-lookup"><span data-stu-id="1ee33-151">Repeating a read as of the original read time is guaranteed to return the same result.</span></span>  
  
 <span data-ttu-id="1ee33-152">REPEATABLE READ</span><span class="sxs-lookup"><span data-stu-id="1ee33-152">REPEATABLE READ</span></span>  
 <span data-ttu-id="1ee33-153">Считывание данных гарантированно фиксируется и стабильно до времени логического завершения транзакции.</span><span class="sxs-lookup"><span data-stu-id="1ee33-153">The data read is guaranteed to be committed and stable up to the logical end time of the transaction.</span></span>  
  
 <span data-ttu-id="1ee33-154">SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="1ee33-154">SERIALIZABLE</span></span>  
 <span data-ttu-id="1ee33-155">Все гарантии возможности ПОВТОРЯЕМого чтения и фантомного исключения, а также согласованность транзакций в отношении всех сериализуемых операций чтения, выполняемых T. фантомное исключение означает, что операция просмотра может возвращать только дополнительные строки, записанные T, но не строки, записанные другими транзакциями.</span><span class="sxs-lookup"><span data-stu-id="1ee33-155">All guarantees of REPEATABLE READ plus phantom avoidance and transactional consistency with respect to all serializable read operations performed by T. Phantom avoidance means that the scan operation can only return additional rows that were written by T, but no rows that were written by other transactions.</span></span>  
  
 <span data-ttu-id="1ee33-156">Рассмотрим следующую транзакцию:</span><span class="sxs-lookup"><span data-stu-id="1ee33-156">Consider the following transaction,</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
  -- remove all rows from t3; the related read operation is performed under read committed   
  -- isolation, as this is the default for the transaction  
  delete from t3  
  
  -- copy the contents from t1 to t3; the read on t1 is performed under the serializable   
  -- isolation level  
  insert t3 select * from t1 (serializable)  
  
  -- compare t3 and t1; note: the result set may not be empty, as rows may have been added   
  -- by other transaction before this select, due to the read committed isolation level  
  select * from t3 except t1  
  
  -- compare t1 and t3; note: the result set is empty, as no rows have been added to t1   
  -- since its contents were copied to t1, due to the serializable isolation level  
  select * from t1 except t3  
commit  
```  
  
 <span data-ttu-id="1ee33-157">Эта транзакция удаляет все строки из t3 в режиме изоляции READ COMMITTED, копирует все строки от t1 до t3 в режиме изоляции SERIALIZABLE, а затем сравнивает t1 и t3.</span><span class="sxs-lookup"><span data-stu-id="1ee33-157">This transaction deletes all rows from t3 under read committed isolation, copies all rows from t1 to t3 under serializable isolation, and then compares t1 and t3.</span></span> <span data-ttu-id="1ee33-158">Некоторые строки [не в t1] могут быть добавлены к t3, поскольку таблица стала пустой.</span><span class="sxs-lookup"><span data-stu-id="1ee33-158">Some rows [not in t1] may have been added to t3 since the table was emptied.</span></span> <span data-ttu-id="1ee33-159">Строки не были добавлены к t1, так как копия была сериализуемая.</span><span class="sxs-lookup"><span data-stu-id="1ee33-159">No rows were added to t1 as the copy was serializable.</span></span>  
  
 <span data-ttu-id="1ee33-160">Несмотря на то, что чтение из T1 в конце транзакции выполняется по синтаксическим операциям чтения, оно эффективно сериализуется, так как в транзакции в режиме сериализуемой изоляции было выполнено такое же считывание. возможности сериализации гарантирует, что если операция чтения выполняется в любой более поздней точке транзакции, возвращаются те же строки.</span><span class="sxs-lookup"><span data-stu-id="1ee33-160">Although the read from t1 at the end of the transaction is syntactically read committed, it is effectively serializable, because the same read was performed earlier in the transaction under serializable isolation: serializability guarantees that if the read is performed at any later point in the transaction, the same rows are returned.</span></span>  
  
## <a name="cross-container-transactions-and-isolation-levels"></a><span data-ttu-id="1ee33-161">Транзакции между контейнерами и уровни изоляции</span><span class="sxs-lookup"><span data-stu-id="1ee33-161">Cross-Container Transactions and Isolation Levels</span></span>  
 <span data-ttu-id="1ee33-162">Транзакции между контейнерами могут рассматриваться как две стороны: дисковая сторона (для операций с таблицами на диске) и оптимизированная для памяти сторона (для операций с оптимизированными для памяти таблицами).</span><span class="sxs-lookup"><span data-stu-id="1ee33-162">A cross-container transaction can be seen as having two sides: a disk-based side (for operations on disk-based tables) and a memory-optimized side (for operations on memory-optimized tables).</span></span> <span data-ttu-id="1ee33-163">Уровни изоляции этих двух сторон могут быть различными.</span><span class="sxs-lookup"><span data-stu-id="1ee33-163">These two sides may have different isolation levels.</span></span> <span data-ttu-id="1ee33-164">В действительности отдельные операции чтения с каждой стороны могут иметь различные уровни изоляции.</span><span class="sxs-lookup"><span data-stu-id="1ee33-164">In fact, individual read operations on each side may have different isolation levels.</span></span>  
  
 <span data-ttu-id="1ee33-165">Дисковая сторона данной транзакции T достигает определенного уровня изоляции X, если выполняется одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="1ee33-165">The disk-based side of a given transaction T reaches a certain isolation level X if one of the following conditions is met:</span></span>  
  
-   <span data-ttu-id="1ee33-166">Он начинается с X. То есть сеанс по умолчанию имел значение X, так как вы выполнили `SET TRANSACTION ISOLATION LEVEL` или это значение [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1ee33-166">It starts in X. That is, the session default was X, either because you executed `SET TRANSACTION ISOLATION LEVEL`, or it is the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] default.</span></span>  
  
-   <span data-ttu-id="1ee33-167">Во время транзакции уровень изоляции по умолчанию изменяется на X с помощью `SET TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="1ee33-167">During the transaction, the default isolation level is changed to X using `SET TRANSACTION ISOLATION LEVEL`.</span></span>  
  
-   <span data-ttu-id="1ee33-168">Операция считывания в дисковой таблице выполняется на уровне изоляции X с использованием синтаксиса `WITH (X)`.</span><span class="sxs-lookup"><span data-stu-id="1ee33-168">A read operation on a disk-based table is executed under isolation level X, using the syntax `WITH (X)`.</span></span>  
  
 <span data-ttu-id="1ee33-169">Сторона оптимизированной для памяти T достигает уровня изоляции Y, если во время выполнения T любая операция считывания в таблице, оптимизированной для памяти, или любая хранимая процедура, скомпилированная в собственном коде, выполняется с уровнем изоляции Y.</span><span class="sxs-lookup"><span data-stu-id="1ee33-169">The memory-optimized side of T reaches an isolation level Y if during execution of T, any read operation on a memory-optimized table or any natively compiled stored procedure is executed under isolation level Y.</span></span>  
  
 <span data-ttu-id="1ee33-170">В качестве примера рассмотрим следующую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="1ee33-170">Consider the following transaction as an example.</span></span> <span data-ttu-id="1ee33-171">В данном случае t1 и t2 — дисковые таблицы, а t3 и t4 — оптимизированные для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="1ee33-171">Here, t1 and t2 are disk-based tables and t3 and t4 are memory-optimized tables.</span></span>  
  
 <span data-ttu-id="1ee33-172">Дисковая сторона транзакции достигает уровня изоляции READ COMMITTED, поскольку запускается на данном уровне.</span><span class="sxs-lookup"><span data-stu-id="1ee33-172">The disk-based side of the transaction reaches the isolation level read committed, because it starts in that level.</span></span> <span data-ttu-id="1ee33-173">Дисковая сторона также достигает уровня изоляции REPEATABLE READ, так как первая операция чтения выполняется на этом уровне изоляции.</span><span class="sxs-lookup"><span data-stu-id="1ee33-173">The disk-based side also reaches repeatable read, because the first read operation is executed under that isolation level.</span></span> <span data-ttu-id="1ee33-174">Удаление в конце транзакции выполняется с уровнем изоляции READ COMMITTED, поэтому не вызывает перехода на новый уровень изоляции.</span><span class="sxs-lookup"><span data-stu-id="1ee33-174">The delete at the end of the transaction is executed under read committed isolation level, and so does not introduce a new isolation level.</span></span>  
  
 <span data-ttu-id="1ee33-175">Часть транзакции, оптимизированной для памяти, может достигать одного из двух уровней: Если condition1 имеет значение true, то достигается сериализуемый, а если значение false, то оптимизированная для памяти часть достигает только изоляции моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="1ee33-175">The memory-optimized side of the transaction can reach one of two levels: if condition1 is true, it reaches serializable, while if it is false, the memory-optimized side reaches only snapshot isolation.</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
  select * from t1 (repeatableread)  
  
  if condition1 begin  
    insert t3 select * from t4 (serializable)  
  end  
  else begin  
    insert t3 select * from t4 (snapshot)  
  end  
  
  delete from t1  
commit  
```  
  
### <a name="supported-isolation-levels-for-cross-container-transactions"></a><span data-ttu-id="1ee33-176">Поддерживаемые уровни изоляции для транзакций между контейнерами</span><span class="sxs-lookup"><span data-stu-id="1ee33-176">Supported Isolation Levels for Cross-Container Transactions</span></span>  
 <span data-ttu-id="1ee33-177">Существуют ограничения на уровни изоляции, используемые с операциями над оптимизированными для памяти таблицами в транзакциях между контейнерами.</span><span class="sxs-lookup"><span data-stu-id="1ee33-177">There are limitations on the isolation levels used with operations on memory-optimized tables in cross-container transactions.</span></span>  
  
 <span data-ttu-id="1ee33-178">Оптимизированные для памяти таблицы поддерживают уровни изоляции SNAPSHOT, REPEATABLE READ и SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="1ee33-178">Memory-optimized tables support the isolation levels SNAPSHOT, REPEATABLE READ, and SERIALIZABLE.</span></span> <span data-ttu-id="1ee33-179">Для транзакций с автоматической фиксацией оптимизированные для памяти таблицы поддерживают уровень изоляции READ COMMITTED.</span><span class="sxs-lookup"><span data-stu-id="1ee33-179">For autocommit transactions, memory-optimized tables support the isolation level READ COMMITTED.</span></span>  
  
 <span data-ttu-id="1ee33-180">Поддерживаются следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="1ee33-180">The following scenarios are supported:</span></span>  
  
-   <span data-ttu-id="1ee33-181">Транзакции между контейнерами READ UNCOMMITTED, READ COMMITTED и READ_COMMITTED_SNAPSHOT могут получить доступ к оптимизированным для памяти таблицам в режиме изоляции SNAPSHOT, REPEATABLE READ и SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="1ee33-181">READ UNCOMMITTED, READ COMMITTED, and READ_COMMITTED_SNAPSHOT cross-container transactions can access memory-optimized tables under SNAPSHOT, REPEATABLE READ, and SERIALIZABLE isolation.</span></span> <span data-ttu-id="1ee33-182">Гарантия READ COMMITTED действует для транзакции; все строки, считанные транзакцией, были зафиксированы в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1ee33-182">The READ COMMITTED guarantee holds for the transaction; all rows read by the transaction have been committed to the database.</span></span>  
  
-   <span data-ttu-id="1ee33-183">Транзакции REPEATABLE READ и SERIALIZABLE могут получить доступ к оптимизированным для памяти таблицам в режиме изоляции SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="1ee33-183">REPEATABLE READ and SERIALIZABLE transactions can access memory-optimized tables under SNAPSHOT isolation.</span></span>  
  
## <a name="read-only-cross-container-transactions"></a><span data-ttu-id="1ee33-184">Транзакции между контейнерами только для чтения</span><span class="sxs-lookup"><span data-stu-id="1ee33-184">Read-only Cross-Container Transactions</span></span>  
 <span data-ttu-id="1ee33-185">Большинство транзакции только для чтения в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] откатываются в момент фиксации.</span><span class="sxs-lookup"><span data-stu-id="1ee33-185">Most read-only transactions in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] are rolled back at commit time.</span></span> <span data-ttu-id="1ee33-186">Поскольку отсутствуют изменения, которые будут зафиксированы в базе данных, система просто освобождает ресурсы, используемые транзакцией.</span><span class="sxs-lookup"><span data-stu-id="1ee33-186">Because there are no changes to commit to the database, the system simply frees the resources used by the transaction.</span></span> <span data-ttu-id="1ee33-187">Для дисковых транзакций только для чтения все блокировки, сделанные транзакцией, снимаются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="1ee33-187">For read-only disk-based transactions, all locks taken by the transaction are released at this time.</span></span> <span data-ttu-id="1ee33-188">Оптимизированные для памяти транзакции только для чтения, которые занимают одну скомпилированную в собственном коде хранимую процедуру, не проверяются.</span><span class="sxs-lookup"><span data-stu-id="1ee33-188">For read-only memory-optimized transactions that span a single natively compiled procedure execution, no validation is performed.</span></span>  
  
 <span data-ttu-id="1ee33-189">Транзакции только для чтения между контейнерами в режиме автоматической фиксации просто откатываются в конце транзакции.</span><span class="sxs-lookup"><span data-stu-id="1ee33-189">Cross-container, read-only transactions in autocommit mode are simply rolled back at the end of the transaction.</span></span> <span data-ttu-id="1ee33-190">Проверка не произведена.</span><span class="sxs-lookup"><span data-stu-id="1ee33-190">No validation is performed.</span></span>  
  
 <span data-ttu-id="1ee33-191">Явные или неявные транзакции только для чтения между контейнерами выполняют проверку в момент фиксации, если транзакция обращается к таблицам с оптимизацией для памяти в уровне изоляции REPEATABLE READ или SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="1ee33-191">Explicit or implicit cross-container, read-only transactions perform validation at commit time if the transaction accesses memory-optimized tables under REPEATABLE READ or SERIALIZABLE isolation.</span></span> <span data-ttu-id="1ee33-192">Дополнительные сведения о проверке см. в разделе об обнаружении конфликтов, проверке и проверке зависимостей фиксации в [транзакциях в таблицах, оптимизированных для памяти](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="1ee33-192">For details about validation see the section on Conflict Detection, Validation, and Commit Dependency Checks in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee33-193">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ee33-193">See Also</span></span>  
 <span data-ttu-id="1ee33-194">[Основные сведения о транзакциях в таблицах, оптимизированных для памяти](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="1ee33-194">[Understanding Transactions on Memory-Optimized Tables](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="1ee33-195">[Рекомендации по уровню изоляции транзакций с таблицами, оптимизированными для памяти](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="1ee33-195">[Guidelines for Transaction Isolation Levels with Memory-Optimized Tables](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="1ee33-196">Рекомендации для логики повторного выполнения транзакций для таблиц, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="1ee33-196">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>](../../2014/database-engine/guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
  
