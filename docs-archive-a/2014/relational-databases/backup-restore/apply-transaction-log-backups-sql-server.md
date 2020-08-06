---
title: Использование резервных копий журнала транзакций (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring [SQL Server], log backups
- transaction log backups [SQL Server], applying backups
- online restores [SQL Server], log backups
- transaction log backups [SQL Server], quantity needed for restore sequence
- backups [SQL Server], log backups
ms.assetid: 9b12be51-5469-46f9-8e86-e938e10aa3a1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 54c91106f8ca6f15539b4103220860143882c3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658855"
---
# <a name="apply-transaction-log-backups-sql-server"></a><span data-ttu-id="5413a-102">Применение резервных копий журналов транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5413a-102">Apply Transaction Log Backups (SQL Server)</span></span>
  <span data-ttu-id="5413a-103">Этот раздел относится только к модели полного восстановления и модели восстановления с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="5413a-103">The topic is relevant only for the full recovery model or bulk-logged recovery model.</span></span>  
  
 <span data-ttu-id="5413a-104">В этом разделе описано применение резервных копий журнала транзакции в процессе восстановления базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5413a-104">This topic describes applying transaction log backups as part of restoring a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="5413a-105">**В этом разделе.**</span><span class="sxs-lookup"><span data-stu-id="5413a-105">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="5413a-106">Требования к восстановлению резервных копий журналов транзакций</span><span class="sxs-lookup"><span data-stu-id="5413a-106">Requirements for Restoring Transaction Log Backups</span></span>](#Requirements)  
  
-   [<span data-ttu-id="5413a-107">Журналы восстановления и транзакций</span><span class="sxs-lookup"><span data-stu-id="5413a-107">Recovery and Transaction Logs</span></span>](#RecoveryAndTlogs)  
  
-   [<span data-ttu-id="5413a-108">Использование резервных копий журнала для восстановления до точки сбоя</span><span class="sxs-lookup"><span data-stu-id="5413a-108">Using Log Backups to Restore to the Point of Failure</span></span>](#PITrestore)  
  
-   [<span data-ttu-id="5413a-109">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="5413a-109">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="requirements-for-restoring-transaction-log-backups"></a><a name="Requirements"></a><span data-ttu-id="5413a-110">Требования к восстановлению резервных копий журналов транзакций</span><span class="sxs-lookup"><span data-stu-id="5413a-110">Requirements for Restoring Transaction Log Backups</span></span>  
 <span data-ttu-id="5413a-111">Для применения резервной копии журнала транзакций необходимо выполнить следующие требования.</span><span class="sxs-lookup"><span data-stu-id="5413a-111">To apply a transaction log backup, the following requirements must be met:</span></span>  
  
-   <span data-ttu-id="5413a-112">**Достаточное количество резервных копий журналов для последовательности восстановления:** Чтобы провести полную последовательность восстановления, в резервных копиях журнала должно быть достаточно записей.</span><span class="sxs-lookup"><span data-stu-id="5413a-112">**Enough Log Backups for a Restore Sequence :** You must have enough log records backed up to complete a restore sequence.</span></span> <span data-ttu-id="5413a-113">Необходимые резервные копии журнала, включая при необходимости [резервные копии конца журнала](tail-log-backups-sql-server.md) , должны быть доступны перед запуском последовательности восстановления.</span><span class="sxs-lookup"><span data-stu-id="5413a-113">The necessary log backups, including the [tail-log backup](tail-log-backups-sql-server.md) where required, must be available before the start of the restore sequence.</span></span>  
  
-   <span data-ttu-id="5413a-114">**Правильный порядок восстановления:**  Сначала необходимо восстановить предыдущую полную или разностную резервную копию базы данных.</span><span class="sxs-lookup"><span data-stu-id="5413a-114">**Correct restore order:**  The immediately previous full database backup or differential database backup must be restored first.</span></span> <span data-ttu-id="5413a-115">После этого в хронологическом порядке необходимо восстановить все журналы транзакций, созданные после указанной полной или разностной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="5413a-115">Then, all transaction logs that are created after that full or differential database backup must be restored in chronological order.</span></span> <span data-ttu-id="5413a-116">Если резервная копия журнала транзакций в этой цепочке журналов утрачена или повреждена, то восстановить можно только журналы транзакций до отсутствующего журнала.</span><span class="sxs-lookup"><span data-stu-id="5413a-116">If a transaction log backup in this log chain is lost or damaged, you can restore only transaction logs before the missing transaction log.</span></span>  
  
-   <span data-ttu-id="5413a-117">**База данных еще не восстановлена:**  Базу данных нельзя восстановить до тех пор, пока не будет применен последний журнал транзакций.</span><span class="sxs-lookup"><span data-stu-id="5413a-117">**Database not yet recovered:**  The database cannot be recovered until after the final transaction log has been applied.</span></span> <span data-ttu-id="5413a-118">Если база данных восстанавливается после восстановления одной из промежуточных резервных копий журнала транзакций, расположенной перед концом цепочки журналов, базу данных после этой точки можно восстановить без перезапуска всей последовательности восстановления, начинающейся с полной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="5413a-118">If you recover the database after restoring one of the intermediate transaction log backups, that before the end of the log chain, you cannot restore the database past that point without restarting the complete restore sequence, starting with the full database backup.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="5413a-119">Лучше всего восстановить все резервные журналы (RESTORE LOG *имя_базы_данных* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="5413a-119">A best practice is to restore all the log backups (RESTORE LOG *database_name* WITH NORECOVERY).</span></span> <span data-ttu-id="5413a-120">После восстановления последней резервной копии журнала восстановите базу данных отдельной операцией (RESTORE DATABASE *имя_базы_данных* WITH RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="5413a-120">Then, after restoring the last log backup, recover the database in a separate operation (RESTORE DATABASE *database_name* WITH RECOVERY).</span></span>  
  
##  <a name="recovery-and-transaction-logs"></a><a name="RecoveryAndTlogs"></a><span data-ttu-id="5413a-121">Журналы восстановления и транзакций</span><span class="sxs-lookup"><span data-stu-id="5413a-121">Recovery and Transaction Logs</span></span>  
 <span data-ttu-id="5413a-122">По завершении операции восстановления и восстановления базы данных будет произведен откат всех незавершенных транзакций.</span><span class="sxs-lookup"><span data-stu-id="5413a-122">When you finish the restore operation and recover the database, recovery rolls back all incomplete transactions.</span></span> <span data-ttu-id="5413a-123">Этот шаг называется *стадией отката*.</span><span class="sxs-lookup"><span data-stu-id="5413a-123">This is known as the *undo phase*.</span></span> <span data-ttu-id="5413a-124">Откат требуется для восстановления целостности базы данных.</span><span class="sxs-lookup"><span data-stu-id="5413a-124">Rolling back is required to restore the integrity of the database.</span></span> <span data-ttu-id="5413a-125">После отката база данных включается в режим «в сети», и больше никакие резервные копии журнала транзакций не могут быть применены.</span><span class="sxs-lookup"><span data-stu-id="5413a-125">After rollback, the database goes online, and no more transaction log backups can be applied to the database.</span></span>  
  
 <span data-ttu-id="5413a-126">Например, серия резервных копий журнала транзакций содержит долго выполняющуюся транзакцию.</span><span class="sxs-lookup"><span data-stu-id="5413a-126">For example, a series of transaction log backups contain a long-running transaction.</span></span> <span data-ttu-id="5413a-127">Начало транзакции записано в первой резервной копии журнала транзакций, а конец транзакции записан во второй резервной копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="5413a-127">The start of the transaction is recorded in the first transaction log backup, but the end of the transaction is recorded in the second transaction log backup.</span></span> <span data-ttu-id="5413a-128">В первой резервной копии журнала транзакций нет записи об операции фиксации или отката.</span><span class="sxs-lookup"><span data-stu-id="5413a-128">There is no record of a commit or rollback operation in the first transaction log backup.</span></span> <span data-ttu-id="5413a-129">Если операция восстановления запускается при применении первой резервной копии журнала транзакций, то долго выполняющаяся транзакция рассматривается как незавершенная, а изменения в данных, записанные в первой резервной копии журнала транзакций, будут отменены.</span><span class="sxs-lookup"><span data-stu-id="5413a-129">If a recovery operation runs when the first transaction log backup is applied, the long-running transaction is treated as incomplete, and data modifications recorded in the first transaction log backup for the transaction are rolled back.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5413a-130">не позволяет применять вторую резервную копию журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="5413a-130">does not allow for the second transaction log backup to be applied after this point.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5413a-131">В некоторых обстоятельствах при восстановлении журнала можно явно добавить файл.</span><span class="sxs-lookup"><span data-stu-id="5413a-131">In some circumstances, you can explicitly add a file during log restore.</span></span>  
  
##  <a name="using-log-backups-to-restore-to-the-point-of-failure"></a><a name="PITrestore"></a><span data-ttu-id="5413a-132">Использование резервных копий журналов для восстановления до точки сбоя</span><span class="sxs-lookup"><span data-stu-id="5413a-132">Using Log Backups to Restore to the Point of Failure</span></span>  
 <span data-ttu-id="5413a-133">Предполагается такая последовательность событий.</span><span class="sxs-lookup"><span data-stu-id="5413a-133">Assume the following sequence of events.</span></span>  
  
|<span data-ttu-id="5413a-134">Time</span><span class="sxs-lookup"><span data-stu-id="5413a-134">Time</span></span>|<span data-ttu-id="5413a-135">Событие</span><span class="sxs-lookup"><span data-stu-id="5413a-135">Event</span></span>|  
|----------|-----------|  
|<span data-ttu-id="5413a-136">8:00</span><span class="sxs-lookup"><span data-stu-id="5413a-136">8:00 A.M.</span></span>|<span data-ttu-id="5413a-137">Создание резервной копии базы данных для создания полной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="5413a-137">Back up database to create a full database backup.</span></span>|  
|<span data-ttu-id="5413a-138">Полдень</span><span class="sxs-lookup"><span data-stu-id="5413a-138">Noon</span></span>|<span data-ttu-id="5413a-139">Резервное копирование журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="5413a-139">Back up transaction log.</span></span>|  
|<span data-ttu-id="5413a-140">16:00</span><span class="sxs-lookup"><span data-stu-id="5413a-140">4:00 P.M.</span></span>|<span data-ttu-id="5413a-141">Резервное копирование журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="5413a-141">Back up transaction log.</span></span>|  
|<span data-ttu-id="5413a-142">18:00</span><span class="sxs-lookup"><span data-stu-id="5413a-142">6:00 P.M.</span></span>|<span data-ttu-id="5413a-143">Создание резервной копии базы данных для создания полной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="5413a-143">Back up database to create a full database backup.</span></span>|  
|<span data-ttu-id="5413a-144">20:00</span><span class="sxs-lookup"><span data-stu-id="5413a-144">8:00 P.M.</span></span>|<span data-ttu-id="5413a-145">Резервное копирование журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="5413a-145">Back up transaction log.</span></span>|  
|<span data-ttu-id="5413a-146">21:45</span><span class="sxs-lookup"><span data-stu-id="5413a-146">9:45 P.M.</span></span>|<span data-ttu-id="5413a-147">Произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="5413a-147">Failure occurs.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="5413a-148">Объяснение этого примера последовательности резервных копий см. в разделе [Резервные копии журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5413a-148">For an explanation of this example sequence of backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="5413a-149">Чтобы восстановить базу данных до ее состояния в 21:45</span><span class="sxs-lookup"><span data-stu-id="5413a-149">To restore the database to its state at 9:45 P.M.</span></span> <span data-ttu-id="5413a-150">(точка сбоя), может быть использована любая из следующих альтернативных процедур.</span><span class="sxs-lookup"><span data-stu-id="5413a-150">(the point of failure), either of the following alternative procedures can be used:</span></span>  
  
 <span data-ttu-id="5413a-151">**Вариант 1. Восстановление базы данных с помощью последней полной резервной копии базы данных**</span><span class="sxs-lookup"><span data-stu-id="5413a-151">**Alternative 1: Restore the database by using the most recent full database backup**</span></span>  
  
1.  <span data-ttu-id="5413a-152">Создайте резервную копию заключительного фрагмента активного журнала транзакций на момент точки сбоя.</span><span class="sxs-lookup"><span data-stu-id="5413a-152">Create a tail-log backup of the currently active transaction log as of the point of failure.</span></span>  
  
2.  <span data-ttu-id="5413a-153">Не восстанавливайте полную резервную копию базы данных,</span><span class="sxs-lookup"><span data-stu-id="5413a-153">Do not restore the 8:00 A.M.</span></span> <span data-ttu-id="5413a-154">резервной копии базы данных от 18:00.</span><span class="sxs-lookup"><span data-stu-id="5413a-154">full database backup.</span></span> <span data-ttu-id="5413a-155">Вместо этого восстановите последнюю полную резервную копию, созданную в 18:00:00</span><span class="sxs-lookup"><span data-stu-id="5413a-155">Instead, restore the more recent 6:00 P.M.</span></span> <span data-ttu-id="5413a-156">а затем примените резервную копию журнала</span><span class="sxs-lookup"><span data-stu-id="5413a-156">full database backup, and then apply the 8:00 P.M.</span></span> <span data-ttu-id="5413a-157">и резервную копию заключительного фрагмента журнала, созданные в 20:00:00.</span><span class="sxs-lookup"><span data-stu-id="5413a-157">log backup and the tail-log backup.</span></span>  
  
 <span data-ttu-id="5413a-158">**Вариант 2. Восстановление базы данных с использованием более ранней полной резервной копии базы данных**</span><span class="sxs-lookup"><span data-stu-id="5413a-158">**Alternative 2: Restore the database by using an earlier full database backup**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5413a-159">Этот вариант можно использовать в том случае, если проблема не позволяет воспользоваться полной</span><span class="sxs-lookup"><span data-stu-id="5413a-159">This alternative process is useful if a problem prevents you from using the 6:00 P.M.</span></span> <span data-ttu-id="5413a-160">резервной копии базы данных от 18:00.</span><span class="sxs-lookup"><span data-stu-id="5413a-160">full database backup.</span></span> <span data-ttu-id="5413a-161">Этот процесс занимает больше времени, чем восстановление полной</span><span class="sxs-lookup"><span data-stu-id="5413a-161">This process takes longer than restoring from the 6:00 P.M.</span></span> <span data-ttu-id="5413a-162">резервной копии базы данных от 18:00.</span><span class="sxs-lookup"><span data-stu-id="5413a-162">full database backup.</span></span>  
  
1.  <span data-ttu-id="5413a-163">Создайте резервную копию заключительного фрагмента активного журнала транзакций на момент точки сбоя.</span><span class="sxs-lookup"><span data-stu-id="5413a-163">Create a tail-log backup of the currently active transaction log as of the point of failure.</span></span>  
  
2.  <span data-ttu-id="5413a-164">Восстановите полную резервную копию</span><span class="sxs-lookup"><span data-stu-id="5413a-164">Restore the 8:00 A.M.</span></span> <span data-ttu-id="5413a-165">базы данных от 8:00, а затем последовательно восстановите все четыре резервные копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="5413a-165">full database backup, and then restore all four transaction log backups in sequence.</span></span> <span data-ttu-id="5413a-166">Это позволяет произвести накат всех завершенных транзакций вплоть до 21:45.</span><span class="sxs-lookup"><span data-stu-id="5413a-166">This rolls forward all completed transactions up to 9:45 P.M.</span></span>  
  
     <span data-ttu-id="5413a-167">Этот вариант указывает на избыточную безопасность, предлагаемую цепочкой резервных копий журнала транзакций в серии полных резервных копий базы данных.</span><span class="sxs-lookup"><span data-stu-id="5413a-167">This alternative points out the redundant security offered by maintaining a chain of transaction log backups across a series of full database backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5413a-168">В некоторых случаях журналы транзакций могут также использоваться для восстановления базы данных на определенный момент времени.</span><span class="sxs-lookup"><span data-stu-id="5413a-168">In some cases, you can also use transaction logs to restore a database to a specific point in time.</span></span> <span data-ttu-id="5413a-169">Дополнительные сведения см. в разделе [Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="5413a-169">For more information, [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5413a-170">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="5413a-170">Related Tasks</span></span>  
 <span data-ttu-id="5413a-171">**Использование резервной копии журнала транзакций**</span><span class="sxs-lookup"><span data-stu-id="5413a-171">**To apply a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="5413a-172">Восстановление резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5413a-172">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
 <span data-ttu-id="5413a-173">**Восстановление до нужной точки восстановления**</span><span class="sxs-lookup"><span data-stu-id="5413a-173">**To restore to your recovery point**</span></span>  
  
-   [<span data-ttu-id="5413a-174">Восстановление базы данных до точки сбоя в модели полного восстановления (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5413a-174">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="5413a-175">Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="5413a-175">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   <span data-ttu-id="5413a-176"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="5413a-176"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  
-   [<span data-ttu-id="5413a-177">Восстановление связанных баз данных, которые содержат помеченную транзакцию</span><span class="sxs-lookup"><span data-stu-id="5413a-177">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
-   [<span data-ttu-id="5413a-178">Восстановление до номера LSN (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5413a-178">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
 <span data-ttu-id="5413a-179">**Восстановление базы данных после восстановления резервных копий с параметром WITH NORECOVERY**</span><span class="sxs-lookup"><span data-stu-id="5413a-179">**To recover a database after restoring backups using WITH NORECOVERY**</span></span>  
  
-   [<span data-ttu-id="5413a-180">Восстановление базы данных без восстановления данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5413a-180">Recover a Database Without Restoring Data &#40;Transact-SQL&#41;</span></span>](recover-a-database-without-restoring-data-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="5413a-181">См. также:</span><span class="sxs-lookup"><span data-stu-id="5413a-181">See Also</span></span>  
 [<span data-ttu-id="5413a-182">Журнал транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5413a-182">The Transaction Log &#40;SQL Server&#41;</span></span>](../logs/the-transaction-log-sql-server.md)  
  
  
