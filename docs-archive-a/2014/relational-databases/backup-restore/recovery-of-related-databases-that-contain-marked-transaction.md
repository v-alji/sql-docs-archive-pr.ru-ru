---
title: Восстановление связанных баз данных, которые содержат помеченную транзакцию | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction logs [SQL Server], marks
- STOPBEFOREMARK option [RESTORE statement]
- STOPATMARK option [RESTORE statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
- recovery [SQL Server], databases
- restoring [SQL Server], point in time
- transactions [SQL Server], recovering to a mark
- database recovery [SQL Server]
- marked transactions [SQL Server], restoring
- database restores [SQL Server], point in time
ms.assetid: 77a0d9c0-978a-4891-8b0d-a4256c81c3f8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b968322f92c7a135adb5fd0733b5774e7562bc39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736437"
---
# <a name="recovery-of-related--databases-that-contain-marked-transaction"></a><span data-ttu-id="fe38c-102">Восстановление связанных баз данных, которые содержат помеченную транзакцию</span><span class="sxs-lookup"><span data-stu-id="fe38c-102">Recovery of Related  Databases That Contain Marked Transaction</span></span>
  <span data-ttu-id="fe38c-103">Этот раздел относится только к базам данных, содержащим помеченные транзакции и использующим полную модель восстановления или модель восстановления с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="fe38c-103">This topic is relevant only for databases that contain marked transactions and that use the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="fe38c-104">Дополнительные сведения о требованиях к восстановлению до указанной точки восстановления см. в статье [Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="fe38c-104">For information about the requirements for restoring to a specific recovery point, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fe38c-105">поддерживает вставку именованных меток в журнал транзакций, чтобы обеспечить возможность восстановления до определенной метки.</span><span class="sxs-lookup"><span data-stu-id="fe38c-105">supports inserting named marks into the transaction log to allow recovery to that specific mark.</span></span> <span data-ttu-id="fe38c-106">Метки журнала являются специальным средством транзакции и вставляются только в случае, если связанная с ними транзакция зафиксирована.</span><span class="sxs-lookup"><span data-stu-id="fe38c-106">Log marks are transaction specific and are inserted only if their associated transaction commits.</span></span> <span data-ttu-id="fe38c-107">В итоге, метки могут быть привязаны к конкретной работе, и можно выполнить восстановление до точки, которая включает или не включает эту работу.</span><span class="sxs-lookup"><span data-stu-id="fe38c-107">As a result, marks can be tied to specific work, and you can recover to a point that includes or excludes this work.</span></span>  
  
 <span data-ttu-id="fe38c-108">Перед вставкой именованных меток в журнал транзакций следует учесть следующее.</span><span class="sxs-lookup"><span data-stu-id="fe38c-108">Before you insert named marks into the transaction log, consider the following:</span></span>  
  
-   <span data-ttu-id="fe38c-109">Метки транзакций занимают место в журнале, поэтому их следует использовать только для транзакций, играющих важную роль в стратегии восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="fe38c-109">Because transaction marks consume log space, use them only for transactions that play a significant role in the database recovery strategy.</span></span>  
  
-   <span data-ttu-id="fe38c-110">После фиксации помеченной транзакции в таблицу [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) базы данных **msdb**вставляется строка.</span><span class="sxs-lookup"><span data-stu-id="fe38c-110">After a marked transaction commits, a row is inserted in the [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) table in **msdb**.</span></span>  
  
-   <span data-ttu-id="fe38c-111">Если в помеченной транзакции задействованы несколько баз данных на одном сервере баз данных или на разных серверах, то метки должны записываться в журналах всех задействованных баз данных.</span><span class="sxs-lookup"><span data-stu-id="fe38c-111">If a marked transaction spans multiple databases on the same database server or on different servers, the marks must be recorded in the logs of all the affected databases.</span></span> <span data-ttu-id="fe38c-112">Дополнительные сведения см. в статье [Использование помеченных транзакций для согласованного восстановления связанных баз данных (модель полного восстановления)](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="fe38c-112">For more information, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fe38c-113">Дополнительные сведения о том, как пометить транзакции, см. в статье [Использование помеченных транзакций для согласованного восстановления связанных баз данных (модель полного восстановления)](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="fe38c-113">For information about how to mark transactions, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
## <a name="transact-sql-syntax-for-inserting-named-marks-into-a-transaction-log"></a><span data-ttu-id="fe38c-114">Синтаксис языка Transact-SQL для вставки именованных меток в журнал транзакций</span><span class="sxs-lookup"><span data-stu-id="fe38c-114">Transact-SQL Syntax for Inserting Named Marks into a Transaction Log</span></span>  
 <span data-ttu-id="fe38c-115">Чтобы вставлять метки в журналы транзакций, используйте инструкцию [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) и предложение WITH MARK [*описание*].</span><span class="sxs-lookup"><span data-stu-id="fe38c-115">To insert marks into the transaction logs, use the [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) statement and the WITH MARK [*description*] clause.</span></span> <span data-ttu-id="fe38c-116">Имя метки совпадает с именем транзакции.</span><span class="sxs-lookup"><span data-stu-id="fe38c-116">The mark is named the same as the transaction.</span></span> <span data-ttu-id="fe38c-117">Необязательное *описание* представляет собой текстовое описание, а не имя метки.</span><span class="sxs-lookup"><span data-stu-id="fe38c-117">The optional *description* is a textual description of the mark, not the mark name.</span></span> <span data-ttu-id="fe38c-118">Например, именем транзакции и метки, которые созданы следующей инструкцией `BEGIN TRANSACTION` , будет `Tx1`.</span><span class="sxs-lookup"><span data-stu-id="fe38c-118">For example, the name of both the transaction and the mark that is created in the following `BEGIN TRANSACTION` statement is `Tx1`:</span></span>  
  
```wmimof  
BEGIN TRANSACTION Tx1 WITH MARK 'not the mark name, just a description'    
```  
  
 <span data-ttu-id="fe38c-119">В журнале транзакций записывается имя метки (имя транзакции), описание, база данных, пользователь, данные `datetime` и регистрационный номер транзакции в журнале (LSN).</span><span class="sxs-lookup"><span data-stu-id="fe38c-119">The transaction log records the mark name (transaction name), description, database, user, `datetime` information, and the log sequence number (LSN).</span></span> <span data-ttu-id="fe38c-120">Данные `datetime` используются с именем метки, чтобы уникально идентифицировать метку.</span><span class="sxs-lookup"><span data-stu-id="fe38c-120">The `datetime` information is used with the mark name to uniquely identify the mark.</span></span>  
  
 <span data-ttu-id="fe38c-121">Дополнительные сведения о вставке метки в транзакцию, которая охватывает несколько баз данных, см. в статье [Использование помеченных транзакций для согласованного восстановления связанных баз данных (модель полного восстановления)](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="fe38c-121">For information about how to insert a mark into a transaction that spans multiple databases, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
## <a name="transact-sql-syntax-for-recovering-to-a-mark"></a><span data-ttu-id="fe38c-122">Синтаксис языка Transact-SQL для восстановления до метки</span><span class="sxs-lookup"><span data-stu-id="fe38c-122">Transact-SQL Syntax for Recovering to a Mark</span></span>  
 <span data-ttu-id="fe38c-123">Отметив помеченную транзакцию с помощью инструкции[RESTORE LOG](/sql/t-sql/statements/restore-statements-transact-sql), можно использовать одно из следующих предложений, чтобы остановиться на метке или перед ней.</span><span class="sxs-lookup"><span data-stu-id="fe38c-123">When you target a marked transaction by using a[RESTORE LOG](/sql/t-sql/statements/restore-statements-transact-sql)statement, you can use one the following clauses to stop at or immediately before the mark:</span></span>  
  
-   <span data-ttu-id="fe38c-124">Используйте предложение WITH STOPATMARK = **' *`<mark_name>`* '** , чтобы указать, что помеченная транзакция является точкой восстановления.</span><span class="sxs-lookup"><span data-stu-id="fe38c-124">Use the WITH STOPATMARK = **'*`<mark_name>`*'** clause to specify that the marked transaction is the recovery point.</span></span>  
  
     <span data-ttu-id="fe38c-125">С помощью предложения STOPATMARK выполняется накат к метке, при этом помеченная транзакция включается в накат.</span><span class="sxs-lookup"><span data-stu-id="fe38c-125">STOPATMARK rolls forward to the mark and includes the marked transaction in the roll forward.</span></span>  
  
-   <span data-ttu-id="fe38c-126">Используйте предложение WITH STOPBEFOREMARK = **' *`<mark_name>`* '** , чтобы указать, что запись журнала, которая находится непосредственно перед меткой, является точкой восстановления.</span><span class="sxs-lookup"><span data-stu-id="fe38c-126">Use the WITH STOPBEFOREMARK = **'*`<mark_name>`*'** clause to specify that the log record that is immediately before the mark is the recovery point.</span></span>  
  
     <span data-ttu-id="fe38c-127">С помощью предложения STOPBEFOREMARK выполняется накат к метке, при этом помеченная транзакция не включается в накат.</span><span class="sxs-lookup"><span data-stu-id="fe38c-127">STOPBEFOREMARK rolls forward to the mark and excludes marked the transaction from the roll forward.</span></span>  
  
 <span data-ttu-id="fe38c-128">В обоих вариантах, с предложением STOPATMARK и с предложением STOPBEFOREMARK, поддерживается необязательное предложение AFTER *datetime* .</span><span class="sxs-lookup"><span data-stu-id="fe38c-128">The STOPATMARK and STOPBEFOREMARK options both support an optional AFTER *datetime* clause.</span></span> <span data-ttu-id="fe38c-129">При использовании *datetime* уникальность имен меток необязательна.</span><span class="sxs-lookup"><span data-stu-id="fe38c-129">When *datetime* is used, mark names do not have to be unique.</span></span>  
  
 <span data-ttu-id="fe38c-130">Если предложение AFTER *datetime* опущено, накат останавливается на первой метке с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="fe38c-130">If AFTER *datetime* is omitted, roll forward stops at the first mark that has the specified name.</span></span> <span data-ttu-id="fe38c-131">Если предложение AFTER *datetime* указано, накат останавливается на первой метке с указанным именем точно в *datetime*или сразу после.</span><span class="sxs-lookup"><span data-stu-id="fe38c-131">If AFTER *datetime* is specified, roll forward stops at the first mark that has the specified name, exactly at or after *datetime*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fe38c-132">Как и во всех случаях операций восстановления на момент времени, восстановление к метке запрещено, когда в базе данных совершаются операции с массовым протоколированием.</span><span class="sxs-lookup"><span data-stu-id="fe38c-132">As in all point-in-time restore operations, recovering to a mark is disallowed when the database is undergoing operations that are bulk-logged.</span></span>  
  
 <span data-ttu-id="fe38c-133">**Восстановление до помеченной транзакции**</span><span class="sxs-lookup"><span data-stu-id="fe38c-133">**To restore to a marked transaction**</span></span>  
  
 [<span data-ttu-id="fe38c-134">Восстановление базы данных до помеченной транзакции (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="fe38c-134">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
 [<span data-ttu-id="fe38c-135">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fe38c-135">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
### <a name="preparing-the-log-backups"></a><span data-ttu-id="fe38c-136">Подготовка резервных копий журнала</span><span class="sxs-lookup"><span data-stu-id="fe38c-136">Preparing the Log Backups</span></span>  
 <span data-ttu-id="fe38c-137">Например, подходящей стратегией резервного копирования для этих связанных баз данных будет следующая.</span><span class="sxs-lookup"><span data-stu-id="fe38c-137">For this example, an appropriate backup strategy for these related databases would be the following:</span></span>  
  
1.  <span data-ttu-id="fe38c-138">Использование модели полного восстановления для обеих баз данных.</span><span class="sxs-lookup"><span data-stu-id="fe38c-138">Use the full recovery model for both databases.</span></span>  
  
2.  <span data-ttu-id="fe38c-139">Создание полной резервной копии каждой базы данных.</span><span class="sxs-lookup"><span data-stu-id="fe38c-139">Create a full backup of each database.</span></span>  
  
     <span data-ttu-id="fe38c-140">Отдельное или одновременное резервное копирование баз данных.</span><span class="sxs-lookup"><span data-stu-id="fe38c-140">The databases can be backed up sequentially or simultaneously.</span></span>  
  
3.  <span data-ttu-id="fe38c-141">Перед созданием резервной копии журнала транзакций необходимо отметить транзакцию, выполняющуюся во всех базах данных.</span><span class="sxs-lookup"><span data-stu-id="fe38c-141">Before backing up the transaction log, mark a transaction that executes in all databases.</span></span> <span data-ttu-id="fe38c-142">Дополнительные сведения о создании помеченных транзакций см. в статье [Использование помеченных транзакций для согласованного восстановления связанных баз данных (модель полного восстановления)](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="fe38c-142">For information about how to create the marked transactions, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
4.  <span data-ttu-id="fe38c-143">Резервное копирование журнала транзакции в каждой базе данных.</span><span class="sxs-lookup"><span data-stu-id="fe38c-143">Back up the transaction log on each database.</span></span>  
  
### <a name="recovering-the-database-to-a-marked-transaction"></a><span data-ttu-id="fe38c-144">Восстановление базы данных до помеченной транзакции</span><span class="sxs-lookup"><span data-stu-id="fe38c-144">Recovering the Database to a Marked Transaction</span></span>  
 <span data-ttu-id="fe38c-145">**Восстановление резервной копии**</span><span class="sxs-lookup"><span data-stu-id="fe38c-145">**To restore the backup**</span></span>  
  
1.  <span data-ttu-id="fe38c-146">При необходимости создайте [резервные копии заключительного фрагмента журнала](tail-log-backups-sql-server.md) неповрежденных баз данных, если возможно.</span><span class="sxs-lookup"><span data-stu-id="fe38c-146">Create [tail-log backups](tail-log-backups-sql-server.md) of the undamaged databases, if possible.</span></span>  
  
2.  <span data-ttu-id="fe38c-147">Восстановите последнюю полную резервную копию каждой базы данных.</span><span class="sxs-lookup"><span data-stu-id="fe38c-147">Restore the most recent full database backup of each database.</span></span>  
  
3.  <span data-ttu-id="fe38c-148">Идентифицируйте недавно помеченные транзакции, доступные во всех резервных копиях журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="fe38c-148">Identify the most recent marked transaction that is available in all of the transaction log backups.</span></span> <span data-ttu-id="fe38c-149">Данные сведения хранятся в таблице **logmarkhistory** в базе данных **msdb** на каждом сервере.</span><span class="sxs-lookup"><span data-stu-id="fe38c-149">This information is stored in the **logmarkhistory** table in the **msdb** database on each server.</span></span>  
  
4.  <span data-ttu-id="fe38c-150">Идентифицируйте резервные копии журналов для всех связанных баз данных, содержащих данную отметку.</span><span class="sxs-lookup"><span data-stu-id="fe38c-150">Identify the log backups for all related databases that contain this mark.</span></span>  
  
5.  <span data-ttu-id="fe38c-151">Восстановите каждую резервную копию журнала, остановившись на помеченной транзакции.</span><span class="sxs-lookup"><span data-stu-id="fe38c-151">Restore each log backup, stopping at the marked transaction.</span></span>  
  
6.  <span data-ttu-id="fe38c-152">Восстановите каждую базу данных.</span><span class="sxs-lookup"><span data-stu-id="fe38c-152">Recover each database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe38c-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="fe38c-153">See Also</span></span>  
 <span data-ttu-id="fe38c-154">[BEGIN TRANSACTION (Transact-SQL)](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fe38c-154">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span></span>  
 <span data-ttu-id="fe38c-155">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fe38c-155">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="fe38c-156">[Применение резервных копий журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fe38c-156">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="fe38c-157">[Использование помеченных транзакций для согласованного восстановления связанных баз данных (модель полного восстановления)](use-marked-transactions-to-recover-related-databases-consistently.md) </span><span class="sxs-lookup"><span data-stu-id="fe38c-157">[Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) </span></span>  
 <span data-ttu-id="fe38c-158">[Обзор процессов восстановления (SQL Server)](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fe38c-158">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="fe38c-159">[Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="fe38c-159">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="fe38c-160">Планирование и выполнение последовательностей восстановления (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="fe38c-160">Plan and Perform Restore Sequences &#40;Full Recovery Model&#41;</span></span>](plan-and-perform-restore-sequences-full-recovery-model.md)  
  
  
