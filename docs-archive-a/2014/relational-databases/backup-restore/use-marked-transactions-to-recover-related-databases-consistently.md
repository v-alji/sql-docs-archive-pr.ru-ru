---
title: Использование помеченных транзакций для согласованного восстановления связанных баз данных (модель полного восстановления) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction marks [SQL Server]
- marked transactions [SQL Server]
- database restores [SQL Server], inserting transaction marks for
- recovery [SQL Server], related databases
- restoring databases [SQL Server], related database recovery
- database restores [SQL Server], related databases
- marked transactions [SQL Server], creating
- BEGIN TRAN...WITH MARK statement
- two-phase commit
ms.assetid: 50a73574-1a69-448e-83dd-9abcc7cb7e1a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8dd368ad14f6e521fb8d504bdea774e3088c2522
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736422"
---
# <a name="use-marked-transactions-to-recover-related-databases-consistently-full-recovery-model"></a><span data-ttu-id="020a5-102">Использование помеченных транзакций для согласованного восстановления связанных баз данных (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="020a5-102">Use Marked Transactions to Recover Related Databases Consistently (Full Recovery Model)</span></span>
  <span data-ttu-id="020a5-103">Этот раздел относится только к тем базам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые используют модель полного восстановления или модель восстановления с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="020a5-103">This topic is relevant only for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="020a5-104">При выполнении связанных обновлений двух или более баз данных, *связанных баз данных*, можно использовать метки транзакции, чтобы возвратить их к логически непротиворечивой точке.</span><span class="sxs-lookup"><span data-stu-id="020a5-104">When you make related updates to two or more databases, *related databases*, you can use transaction marks to recover them to a logically consistent point.</span></span> <span data-ttu-id="020a5-105">Однако при восстановлении транзакция, совершенная после метки, используемой в качестве точки восстановления, теряется.</span><span class="sxs-lookup"><span data-stu-id="020a5-105">However, this recovery loses any transaction that is committed after the mark that was used as the recovery point.</span></span> <span data-ttu-id="020a5-106">Маркировка транзакций подходит только для проверки связанных баз данных или отмены недавно совершенной транзакции.</span><span class="sxs-lookup"><span data-stu-id="020a5-106">Marking transactions is suitable only when you are testing related databases or when you are willing to lose recently committed transactions.</span></span>  
  
 <span data-ttu-id="020a5-107">Обычно пометка связанных транзакций в каждой связанной базе данных устанавливает ряд общих точек восстановления в базе данных.</span><span class="sxs-lookup"><span data-stu-id="020a5-107">Routinely marking related transactions in every related database establishes a series of common recovery points in the databases.</span></span> <span data-ttu-id="020a5-108">Метки транзакции записываются в журнал транзакций и включаются в резервные копии журнала.</span><span class="sxs-lookup"><span data-stu-id="020a5-108">The transaction marks are recorded in the transaction log and included in log backups.</span></span> <span data-ttu-id="020a5-109">При возникновении аварийной ситуации можно восстановить каждую из баз данных к одной метке транзакции, чтобы возвратить их к соответствующей точке.</span><span class="sxs-lookup"><span data-stu-id="020a5-109">In the event of a disaster, you can restore each of the databases to the same transaction mark to recover them to a consistent point.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="020a5-110">Резервные копии журнала в различных базах данных могут быть созданы независимо друга от друга и могут не быть совместными.</span><span class="sxs-lookup"><span data-stu-id="020a5-110">Log backups on the different databases can be created independently of each other and do not have to be simultaneous.</span></span>  
  
 <span data-ttu-id="020a5-111">Восстановление связанных баз данных в следующих сценариях требует наличия помеченных транзакций в каждой связанной базе данных.</span><span class="sxs-lookup"><span data-stu-id="020a5-111">Recovering related databases in the following scenarios requires that you have already marked transactions in every related database:</span></span>  
  
-   <span data-ttu-id="020a5-112">Один или несколько журналов транзакций разрушены.</span><span class="sxs-lookup"><span data-stu-id="020a5-112">One or more transaction logs are destroyed.</span></span> <span data-ttu-id="020a5-113">Необходимо восстановить набор баз данных до согласованного состояния во время резервного копирования последнего журнала.</span><span class="sxs-lookup"><span data-stu-id="020a5-113">You have to restore the set of databases to a consistent state at the time of your last log backup.</span></span>  
  
-   <span data-ttu-id="020a5-114">Необходимо восстановить весь набор баз данных до взаимно стабильного состояния на более раннем этапе.</span><span class="sxs-lookup"><span data-stu-id="020a5-114">You have to restore the entire set of databases to a mutually consistent state at some earlier point in time.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="020a5-115">Восстановление связанных баз данных возможно только до помеченной транзакции, а не до определенного момента времени.</span><span class="sxs-lookup"><span data-stu-id="020a5-115">You can recover related databases only to a marked transaction, not to a specific point in time.</span></span>  
  
 <span data-ttu-id="020a5-116">Дополнительные сведения о создании помеченных транзакций см. в теме «Создание помеченных транзакций» далее в разделе.</span><span class="sxs-lookup"><span data-stu-id="020a5-116">For information about how to create marking transactions, see "Creating the Marked Transactions," later in this topic.</span></span>  
  
## <a name="typical-scenario-for-using-marked-transactions"></a><span data-ttu-id="020a5-117">Типичные сценарии для использования помеченных транзакций</span><span class="sxs-lookup"><span data-stu-id="020a5-117">Typical Scenario for Using Marked Transactions</span></span>  
 <span data-ttu-id="020a5-118">Типичные сценарии для использования помеченных транзакций включают следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="020a5-118">A typical scenario for using marked transactions includes the following steps:</span></span>  
  
1.  <span data-ttu-id="020a5-119">Создание полной или разностной резервной копии каждой связанной базы данных.</span><span class="sxs-lookup"><span data-stu-id="020a5-119">Create a full or differential database backup of each of the related databases.</span></span>  
  
2.  <span data-ttu-id="020a5-120">Пометка блока транзакций во всех базах данных.</span><span class="sxs-lookup"><span data-stu-id="020a5-120">Mark a transaction block in all the databases.</span></span>  
  
3.  <span data-ttu-id="020a5-121">Резервное копирование журнала транзакции во всех базах данных.</span><span class="sxs-lookup"><span data-stu-id="020a5-121">Back up the transaction log for all the databases.</span></span>  
  
4.  <span data-ttu-id="020a5-122">Восстановление резервных копий базы данных с ключевым словом WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="020a5-122">Restore database backups WITH NORECOVERY.</span></span>  
  
5.  <span data-ttu-id="020a5-123">Восстановление журналов с ключевым словом WITH STOPATMARK.</span><span class="sxs-lookup"><span data-stu-id="020a5-123">Restore logs WITH STOPATMARK.</span></span>  
  
## <a name="considerations-for-using-marked-transactions"></a><span data-ttu-id="020a5-124">Сведения об использовании помеченных транзакций</span><span class="sxs-lookup"><span data-stu-id="020a5-124">Considerations for Using Marked Transactions</span></span>  
 <span data-ttu-id="020a5-125">Перед вставкой именованных меток в журнал транзакций следует учесть следующее:</span><span class="sxs-lookup"><span data-stu-id="020a5-125">Before inserting named marks into the transaction log, consider the following:</span></span>  
  
-   <span data-ttu-id="020a5-126">Метки транзакций занимают место в журнале, поэтому их следует использовать только для транзакций, играющих важную роль в стратегии восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="020a5-126">Because transaction marks consume log space, use them only for transactions that play a significant role in the database recovery strategy.</span></span>  
  
-   <span data-ttu-id="020a5-127">После фиксации помеченной транзакции в таблицу [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) базы данных **msdb**вставляется строка.</span><span class="sxs-lookup"><span data-stu-id="020a5-127">After a marked transaction commits, a row is inserted in the [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) table in **msdb**.</span></span>  
  
-   <span data-ttu-id="020a5-128">Если в помеченной транзакции задействованы несколько баз данных на одном сервере баз данных или на разных серверах, то метки должны записываться в журналах всех задействованных баз данных.</span><span class="sxs-lookup"><span data-stu-id="020a5-128">If a marked transaction spans multiple databases on the same database server or on different servers, the marks must be recorded in the logs of all the affected databases.</span></span>  
  
## <a name="creating-the-marked-transactions"></a><span data-ttu-id="020a5-129">Создайте помеченные транзакции</span><span class="sxs-lookup"><span data-stu-id="020a5-129">Creating the Marked Transactions</span></span>  
 <span data-ttu-id="020a5-130">Чтобы создать помеченные транзакции, используйте инструкцию [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) и предложение WITH MARK [*description*].</span><span class="sxs-lookup"><span data-stu-id="020a5-130">To create a marked transaction, use the [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) statement and the WITH MARK [*description*] clause.</span></span> <span data-ttu-id="020a5-131">Необязательное *описание* представляет собой текстовое описание метки.</span><span class="sxs-lookup"><span data-stu-id="020a5-131">The optional *description* is a textual description of the mark.</span></span> <span data-ttu-id="020a5-132">Имя метки для транзакции указывается обязательно.</span><span class="sxs-lookup"><span data-stu-id="020a5-132">A mark name for the transaction is required.</span></span> <span data-ttu-id="020a5-133">Имя метки может быть использовано повторно.</span><span class="sxs-lookup"><span data-stu-id="020a5-133">A mark name can be reused.</span></span> <span data-ttu-id="020a5-134">В журнале транзакций записывается имя метки, описание, база данных, пользователь, данные datetime и порядковый номер транзакции в журнале (LSN).</span><span class="sxs-lookup"><span data-stu-id="020a5-134">The transaction log records the mark name, description, database, user, datetime information, and the log sequence number (LSN).</span></span> <span data-ttu-id="020a5-135">Данные datetime используются наряду с именем метки, чтобы уникально идентифицировать метку.</span><span class="sxs-lookup"><span data-stu-id="020a5-135">The datetime information is used along with the mark name to uniquely identify the mark.</span></span>  
  
 <span data-ttu-id="020a5-136">**Создание помеченных транзакций в наборе баз данных**</span><span class="sxs-lookup"><span data-stu-id="020a5-136">**To create marked transactions in a set of databases:**</span></span>  
  
1.  <span data-ttu-id="020a5-137">Дайте имя транзакции в инструкции BEGIN TRAN и используйте предложение WITH MARK.</span><span class="sxs-lookup"><span data-stu-id="020a5-137">Name the transaction in the BEGIN TRAN statement and use the WITH MARK clause</span></span>  
  
     <span data-ttu-id="020a5-138">Можно вложить инструкцию BEGIN TRAN *new_mark_name* WITH MARK в существующую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="020a5-138">You can nest the statement BEGIN TRAN *new_mark_name* WITH MARK within an existing transaction.</span></span> <span data-ttu-id="020a5-139">Значение параметра *new_mark_name* является помеченным именем для транзакции, даже если транзакция владеет им.</span><span class="sxs-lookup"><span data-stu-id="020a5-139">The value of *new_mark_name* is the mark name for the transaction, even if the transaction possesses a transaction name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="020a5-140">Если вызывается вторая вложенная инструкция BEGIN TRAN...WITH MARK, предыдущая инструкция пропускается, но в результате появляется предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="020a5-140">If you issue a second nested BEGIN TRAN...WITH MARK, that statement is skipped but causes a warning message.</span></span>  
  
2.  <span data-ttu-id="020a5-141">Выполните обновление всех баз данных в наборе.</span><span class="sxs-lookup"><span data-stu-id="020a5-141">Run an update against all of the databases in the set.</span></span>  
  
     <span data-ttu-id="020a5-142">Метка указанной транзакции добавлена в журналы транзакций только на экземпляре сервера, где выполнена инструкция BEGIN TRAN...WITH MARK.</span><span class="sxs-lookup"><span data-stu-id="020a5-142">The mark for a specific transaction is inserted into transaction logs only on the server instance where the BEGIN TRAN...WITH MARK statement is executed.</span></span> <span data-ttu-id="020a5-143">Метка транзакции размещается только в журнале транзакции каждой базы данных, обновленной помеченной транзакцией на данном экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="020a5-143">The transaction mark is placed in the transaction log of every database updated by the marked transaction on that server instance.</span></span> <span data-ttu-id="020a5-144">Если базы данных постоянно находятся на различных экземплярах сервера, идентичные метки должны быть созданы на каждом из них.</span><span class="sxs-lookup"><span data-stu-id="020a5-144">If the databases reside on different server instances, identical marks must be created on each of the server instances.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="020a5-145">Примеры</span><span class="sxs-lookup"><span data-stu-id="020a5-145">Examples</span></span>  
 <span data-ttu-id="020a5-146">В следующем примере журнал транзакций восстанавливается до метки в помеченной транзакции с именем `ListPriceUpdate`.</span><span class="sxs-lookup"><span data-stu-id="020a5-146">The following example restores the transaction log to the mark in the marked transaction named `ListPriceUpdate`.</span></span>  
  
```sql  
USE AdventureWorks  
GO  
BEGIN TRANSACTION ListPriceUpdate  
   WITH MARK 'UPDATE Product list prices';  
GO  
  
UPDATE Production.Product  
   SET ListPrice = ListPrice * 1.10  
   WHERE ProductNumber LIKE 'BK-%';  
GO  
  
COMMIT TRANSACTION ListPriceUpdate;  
GO  
  
-- Time passes. Regular database   
-- and log backups are taken.  
-- An error occurs in the database.  
USE master  
GO  
  
RESTORE DATABASE AdventureWorks  
FROM AdventureWorksBackups  
WITH FILE = 3, NORECOVERY;  
GO  
  
RESTORE LOG AdventureWorks  
   FROM AdventureWorksBackups   
   WITH FILE = 4,  
   RECOVERY,   
   STOPATMARK = 'ListPriceUpdate';  
```  
  
## <a name="forcing-a-mark-to-spread-to-other-servers"></a><span data-ttu-id="020a5-147">Форсирование отметки к распространению на другие сервера</span><span class="sxs-lookup"><span data-stu-id="020a5-147">Forcing a Mark to Spread to Other Servers</span></span>  
 <span data-ttu-id="020a5-148">В процессе распространения транзакции имя отметки транзакции не передается автоматически на другой сервер.</span><span class="sxs-lookup"><span data-stu-id="020a5-148">A transaction mark name is not automatically distributed to another server as the transaction spreads there.</span></span> <span data-ttu-id="020a5-149">Чтобы заставить отметку распространиться на другие сервера, хранимая процедура должна содержать инструкцию BEGIN TRAN *имя* WITH MARK.</span><span class="sxs-lookup"><span data-stu-id="020a5-149">To force the mark to spread to the other servers, a stored procedure must be written that contains a BEGIN TRAN *name* WITH MARK statement.</span></span> <span data-ttu-id="020a5-150">Эта хранимая процедура затем должна быть выполнена на удаленном сервере в области транзакции на исходном сервере.</span><span class="sxs-lookup"><span data-stu-id="020a5-150">That stored procedure must then be executed on the remote server under the scope of the transaction in the originating server.</span></span>  
  
 <span data-ttu-id="020a5-151">Например, рассмотрим секционированную базу данных, существующую в нескольких экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="020a5-151">For example, consider a partitioned database that exists on multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="020a5-152">В каждом экземпляре находится база данных под названием `coyote`.</span><span class="sxs-lookup"><span data-stu-id="020a5-152">On each instance is a database named `coyote`.</span></span> <span data-ttu-id="020a5-153">Во-первых, необходимо создать хранимую процедуру, например `sp_SetMark`, в каждой базе данных.</span><span class="sxs-lookup"><span data-stu-id="020a5-153">First, in every database, create a stored procedure, for example, `sp_SetMark`.</span></span>  
  
```sql  
CREATE PROCEDURE sp_SetMark  
@name nvarchar (128)  
AS  
BEGIN TRANSACTION @name WITH MARK  
UPDATE coyote.dbo.Marks SET one = 1  
COMMIT TRANSACTION;  
GO  
```  
  
 <span data-ttu-id="020a5-154">Затем необходимо создать хранимую процедуру `sp_MarkAll` , которая содержит транзакцию, размещающую отметку в каждой базе данных.</span><span class="sxs-lookup"><span data-stu-id="020a5-154">Next, create stored procedure `sp_MarkAll` containing a transaction that places a mark in every database.</span></span> <span data-ttu-id="020a5-155">`sp_MarkAll` может быть запущена из любого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="020a5-155">`sp_MarkAll` can be run from any of the instances.</span></span>  
  
```sql  
CREATE PROCEDURE sp_MarkAll  
@name nvarchar (128)  
AS  
BEGIN TRANSACTION  
EXEC instance0.coyote.dbo.sp_SetMark @name  
EXEC instance1.coyote.dbo.sp_SetMark @name  
EXEC instance2.coyote.dbo.sp_SetMark @name  
COMMIT TRANSACTION;  
GO  
```  
  
### <a name="two-phase-commit"></a><span data-ttu-id="020a5-156">двухфазная фиксация</span><span class="sxs-lookup"><span data-stu-id="020a5-156">Two-Phase Commit</span></span>  
 <span data-ttu-id="020a5-157">Фиксация распределенной транзакции состоит из двух фаз: подготовка и фиксация.</span><span class="sxs-lookup"><span data-stu-id="020a5-157">Committing a distributed transaction occurs in two phases: prepare and commit.</span></span> <span data-ttu-id="020a5-158">При фиксации помеченной транзакции запись журнала фиксации для каждой базы данных в помеченной транзакции размещается в журнале в том месте, где нет сомнительных транзакций.</span><span class="sxs-lookup"><span data-stu-id="020a5-158">When a marked transaction is committed, the commit log record for each database in the marked transaction is placed in the log at a point where there are no in-doubt transactions in any of the logs.</span></span> <span data-ttu-id="020a5-159">На данном этапе гарантируется, что не появятся транзакции, зафиксированные в одном журнале, но не зафиксированные в другом.</span><span class="sxs-lookup"><span data-stu-id="020a5-159">At this point, it is guaranteed that there are no transactions that appear as committed in one log, but not committed in another log.</span></span>  
  
 <span data-ttu-id="020a5-160">Следующие шаги выполняются во время фиксации помеченной транзакции.</span><span class="sxs-lookup"><span data-stu-id="020a5-160">The following steps accomplish this during the commit of a marked transaction:</span></span>  
  
1.  <span data-ttu-id="020a5-161">Фаза подготовки помеченной транзакции останавливает все новые подготовки и фиксации.</span><span class="sxs-lookup"><span data-stu-id="020a5-161">Prepare phase of a marking transaction stalls all new prepares and commits.</span></span>  
  
2.  <span data-ttu-id="020a5-162">Может продолжаться только фиксация уже подготовленных транзакций.</span><span class="sxs-lookup"><span data-stu-id="020a5-162">Only commits of already prepared transactions are allowed to continue.</span></span>  
  
3.  <span data-ttu-id="020a5-163">Пометка транзакции ожидает истощения всех подготовленных транзакций (с учетом времени ожидания).</span><span class="sxs-lookup"><span data-stu-id="020a5-163">Marking transaction then waits for all prepared transactions to drain (with time-out).</span></span>  
  
4.  <span data-ttu-id="020a5-164">Помеченная транзакция готова и зафиксирована.</span><span class="sxs-lookup"><span data-stu-id="020a5-164">Marked transaction is prepared and committed.</span></span>  
  
5.  <span data-ttu-id="020a5-165">Остановка новых подготовок и фиксаций удалена.</span><span class="sxs-lookup"><span data-stu-id="020a5-165">The stall of new prepares and commits is removed.</span></span>  
  
 <span data-ttu-id="020a5-166">Остановы, сформированные помеченными транзакциями, которые охватывают несколько баз данных, могут уменьшить производительность обработки транзакции сервера.</span><span class="sxs-lookup"><span data-stu-id="020a5-166">The stalls generated by marked transactions that span multiple databases can reduce the transaction processing performance of the server.</span></span>  
  
 <span data-ttu-id="020a5-167">Не рекомендуется запускать параллельно еще одну помеченную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="020a5-167">We recommend that you do not run concurrent marked transactions.</span></span> <span data-ttu-id="020a5-168">Маловероятно, но возможно, что произойдет взаимоблокировка фиксации распределенной помеченной транзакции с другими помеченными транзакциями, которые фиксируются в то же время.</span><span class="sxs-lookup"><span data-stu-id="020a5-168">It is rare but possible for the commit of a distributed marked transaction to deadlock with other distributed marked transactions that are committing at the same time.</span></span> <span data-ttu-id="020a5-169">Когда это произойдет, помечающая транзакция будет считаться жертвой взаимоблокировки и откатится назад.</span><span class="sxs-lookup"><span data-stu-id="020a5-169">When this happens, the marking transaction is chosen as the deadlock victim and is rolled back.</span></span> <span data-ttu-id="020a5-170">При возникновении данной ошибки приложение перезапустит помеченную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="020a5-170">When this error occurs, the application can retry the marked transaction.</span></span> <span data-ttu-id="020a5-171">Возможность взаимоблокировки увеличивается, если несколько помеченных транзакций пытаются зафиксироваться одновременно.</span><span class="sxs-lookup"><span data-stu-id="020a5-171">When multiple marked transactions try to commit concurrently, there is a higher probability of deadlock.</span></span>  
  
## <a name="recovering-to-a-marked-transaction"></a><span data-ttu-id="020a5-172">Восстановление до помеченной транзакции</span><span class="sxs-lookup"><span data-stu-id="020a5-172">Recovering to a Marked Transaction</span></span>  
 <span data-ttu-id="020a5-173">Дополнительные сведения о восстановлении базы данных, содержащей помеченные транзакции на определенной метке или перед ней, см. в разделе [Восстановление связанных баз данных, которые содержат помеченную транзакцию](recovery-of-related-databases-that-contain-marked-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="020a5-173">For information about how to recover a database that contains marked transactions to or just before a particular mark, see [Recovery of Related  Databases That Contain Marked Transaction](recovery-of-related-databases-that-contain-marked-transaction.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="020a5-174">См. также:</span><span class="sxs-lookup"><span data-stu-id="020a5-174">See Also</span></span>  
 <span data-ttu-id="020a5-175">[BEGIN DISTRIBUTED TRANSACTION (Transact-SQL)](/sql/t-sql/language-elements/begin-distributed-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="020a5-175">[BEGIN DISTRIBUTED TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-distributed-transaction-transact-sql) </span></span>  
 <span data-ttu-id="020a5-176">[Резервное копирование и восстановление системных баз данных (SQL Server)](back-up-and-restore-of-system-databases-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="020a5-176">[Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span></span>  
 <span data-ttu-id="020a5-177">[BEGIN TRANSACTION (Transact-SQL)](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="020a5-177">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span></span>  
 <span data-ttu-id="020a5-178">[Применение резервных копий журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="020a5-178">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="020a5-179">[Полные резервные копии баз данных (SQL Server)](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="020a5-179">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="020a5-180">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="020a5-180">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="020a5-181">Восстановление связанных баз данных, которые содержат помеченную транзакцию</span><span class="sxs-lookup"><span data-stu-id="020a5-181">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
  
