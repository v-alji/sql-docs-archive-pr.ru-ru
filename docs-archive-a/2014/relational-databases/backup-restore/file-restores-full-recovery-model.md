---
title: Восстановление файлов (модель полного восстановления) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- file restores [SQL Server]
- full recovery model [SQL Server], performing restores
- restoring files [SQL Server], Transact-SQL restore sequence
- restoring files [SQL Server]
- file restores [SQL Server], full recovery model
- restoring files [SQL Server], full recovery model
- Transact-SQL restore sequence
- file restores [SQL Server], Transact-SQL restore sequence
ms.assetid: d2236a2a-4cf1-4c3f-b542-f73f6096e15c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 488515ec900867f13d33580402e36a3f98747bb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731762"
---
# <a name="file-restores-full-recovery-model"></a><span data-ttu-id="5b203-102">Файлы из резервных копий (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="5b203-102">File Restores (Full Recovery Model)</span></span>
  <span data-ttu-id="5b203-103">Сведения этого раздела относятся только к тем базам данных, которые содержат несколько файловых групп в модели полного восстановления или модели восстановления с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="5b203-103">This topic is relevant only for databases that contain multiple files or filegroups under the full or bulk-load recovery model.</span></span>  
  
 <span data-ttu-id="5b203-104">Цель восстановления файлов — восстановить один или несколько поврежденных файлов, не восстанавливая всю базу данных.</span><span class="sxs-lookup"><span data-stu-id="5b203-104">In a file restore, the goal is to restore one or more damaged files without restoring the whole database.</span></span> <span data-ttu-id="5b203-105">Сценарий восстановления файлов состоит из одной последовательности восстановления, которая копирует данные, выполняет накат и восстанавливает соответствующие данные.</span><span class="sxs-lookup"><span data-stu-id="5b203-105">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data</span></span>  
  
 <span data-ttu-id="5b203-106">Если восстанавливаемая файловая группа предназначена для чтения и записи, то после восстановления последних данных или разностной резервной копии необходимо применение резервных копий журналов.</span><span class="sxs-lookup"><span data-stu-id="5b203-106">If the filegroup that is being restored is read/write, an unbroken chain of log backups must be applied after the last data or differential backup is restored.</span></span> <span data-ttu-id="5b203-107">При этом производится накат файловой группы до текущих активных записей журнальных файлов.</span><span class="sxs-lookup"><span data-stu-id="5b203-107">This brings the filegroup forward to the log records in the current active log records in the log file.</span></span> <span data-ttu-id="5b203-108">Точка восстановления обычно рядом с концом журнала, но это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="5b203-108">The recovery point is typically near the end of log, but not necessarily.</span></span>  
  
 <span data-ttu-id="5b203-109">Если файловая группа доступна только для чтения, применение резервных копий журналов не нужно, и поэтому оно будет пропущено.</span><span class="sxs-lookup"><span data-stu-id="5b203-109">If the filegroup that is being restored is read-only, usually applying log backups is unnecessary and is skipped.</span></span> <span data-ttu-id="5b203-110">Если резервирование проводилось после того, как файл был переведен в режим только для чтения, то эта копия является последней для восстановления.</span><span class="sxs-lookup"><span data-stu-id="5b203-110">If the backup was taken after the file became read-only, that is the last backup to restore.</span></span> <span data-ttu-id="5b203-111">Накат вперед заканчивается в целевой момент.</span><span class="sxs-lookup"><span data-stu-id="5b203-111">Roll forward stops at the target point.</span></span>  
  
 <span data-ttu-id="5b203-112">Существуют следующие сценарии восстановления файлов.</span><span class="sxs-lookup"><span data-stu-id="5b203-112">The file-restore scenarios are as follows:</span></span>  
  
-   <span data-ttu-id="5b203-113">Восстановление файлов в режиме «вне сети»</span><span class="sxs-lookup"><span data-stu-id="5b203-113">Offline file restore</span></span>  
  
     <span data-ttu-id="5b203-114">При *автономном восстановлении файлов*база данных находится в режиме «вне сети», в то время как происходит восстановление поврежденных файлов или файловых групп.</span><span class="sxs-lookup"><span data-stu-id="5b203-114">In an *offline file restore*, the database is offline while damaged files or filegroups are restored.</span></span> <span data-ttu-id="5b203-115">В конце последовательности восстановления база данных переходит в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="5b203-115">At the end of the restore sequence, the database comes online.</span></span>  
  
     <span data-ttu-id="5b203-116">Автономное восстановление файлов поддерживают все выпуски [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b203-116">All editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support offline file restore.</span></span>  
  
-   <span data-ttu-id="5b203-117">Восстановление файлов в сети</span><span class="sxs-lookup"><span data-stu-id="5b203-117">Online file restore</span></span>  
  
     <span data-ttu-id="5b203-118">При *оперативном восстановлении файлов*, если база данных во время восстановления находится в режиме «в сети», то остается в этом режиме в течение времени восстановления файлов.</span><span class="sxs-lookup"><span data-stu-id="5b203-118">In an *online file restore*, if database is online at restore time, it remains online during the file restore.</span></span> <span data-ttu-id="5b203-119">Однако каждая файловая группа, в которой восстанавливается файл, во время операции восстановления находится в состоянии «вне сети».</span><span class="sxs-lookup"><span data-stu-id="5b203-119">However, each filegroup in which a file is being restored is offline during the restore operation.</span></span> <span data-ttu-id="5b203-120">После восстановления всех файлов, входящих в файловую группу в режиме «вне сети», она автоматически переключается в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="5b203-120">After all the files in an offline filegroup are recovered, the filegroup is automatically brought online.</span></span>  
  
     <span data-ttu-id="5b203-121">Дополнительные сведения о поддержке оперативного восстановления страниц и файлов см. в разделе [Возможности, поддерживаемые различными выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="5b203-121">For information about support for online page and file restore, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="5b203-122">Дополнительные сведения об оперативном восстановлении см. в разделе [Оперативное восстановление (SQL Server)](online-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5b203-122">For more information about online restores, see [Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="5b203-123">Если желательно, чтобы база данных находилась в режиме "вне сети" для восстановления файлов, переведите ее в этот режим перед запуском последовательности восстановления, выполнив следующую инструкцию [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options): ALTER DATABASE *имя_базы_данных* SET OFFLINE.</span><span class="sxs-lookup"><span data-stu-id="5b203-123">If you want the database to be offline for a file restore, take the database offline before you start the restore sequence by executing the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement: ALTER DATABASE *database_name* SET OFFLINE.</span></span>  
  
  
  
##  <a name="restoring-damaged-files-from-file-backups"></a><a name="Overview"></a> <span data-ttu-id="5b203-124">Восстановление поврежденных файлов из резервных копий файлов</span><span class="sxs-lookup"><span data-stu-id="5b203-124">Restoring Damaged Files from File Backups</span></span>  
  
1.  <span data-ttu-id="5b203-125">Перед восстановлением одного или нескольких поврежденных файлов попробуйте создать [резервную копию заключительного фрагмента журнала](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5b203-125">Before restoring one or more damaged files, attempt to create a [tail-log backup](tail-log-backups-sql-server.md).</span></span>  
  
     <span data-ttu-id="5b203-126">Если журнал был поврежден, то невозможно создать резервную копию заключительного фрагмента журнала и приходится восстанавливать всю базу данных.</span><span class="sxs-lookup"><span data-stu-id="5b203-126">If the log has been damaged, a tail-log backup cannot be created, and you must restore the whole database.</span></span>  
  
     <span data-ttu-id="5b203-127">Сведения о создании резервной копии журналов транзакций см. в разделе [Резервные копии журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5b203-127">For information about how to back up a transaction log, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5b203-128">Для восстановления файлов вне сети необходимо всегда снимать резервную копию заключительного фрагмента журнала перед восстановлением резервной копии файлов.</span><span class="sxs-lookup"><span data-stu-id="5b203-128">For an offline file restore, you must always take a tail-log backup before the file restore.</span></span> <span data-ttu-id="5b203-129">Для восстановления файлов вне сети необходимо всегда снимать резервную копию журнала перед восстановлением резервной копии файлов.</span><span class="sxs-lookup"><span data-stu-id="5b203-129">For an online file restore, you must always take the log backup after the file restore.</span></span> <span data-ttu-id="5b203-130">Это необходимо из-за того, что файл должен быть восстановлен в состояние, согласованное с оставшейся частью базы данных.</span><span class="sxs-lookup"><span data-stu-id="5b203-130">This log backup is necessary to allow for the file to be recovered to a state consistent with the rest of the database.</span></span>  
  
2.  <span data-ttu-id="5b203-131">Восстановите каждый поврежденный файл из самой последней резервной копии этого файла.</span><span class="sxs-lookup"><span data-stu-id="5b203-131">Restore each damaged file from the most recent file backup of that file.</span></span>  
  
3.  <span data-ttu-id="5b203-132">Восстановите самую последнюю разностную резервную копию файлов, если она существует, для каждого восстановленного файла.</span><span class="sxs-lookup"><span data-stu-id="5b203-132">Restore the most recent differential file backup, if any, for each restored file.</span></span>  
  
4.  <span data-ttu-id="5b203-133">Восстановите резервные копии журнала транзакций в последовательности, начиная с резервной копии, покрывающей самый старый из восстановленных файлов, и заканчивая резервной копией заключительного фрагмента журнала, созданной на этапе 1.</span><span class="sxs-lookup"><span data-stu-id="5b203-133">Restore transaction log backups in sequence, starting with the backup that covers the oldest of the restored files and ending with the tail-log backup created in step 1.</span></span>  
  
     <span data-ttu-id="5b203-134">Необходимо восстановить резервные копии журналов транзакций, созданные после резервных копий файлов, для приведения базы данных в согласованное состояние.</span><span class="sxs-lookup"><span data-stu-id="5b203-134">You must restore the transaction log backups that were created after the file backups to bring the database to a consistent state.</span></span> <span data-ttu-id="5b203-135">Накат резервных копий журналов транзакций может производиться быстро, поскольку применяются только изменения для восстановленных файлов.</span><span class="sxs-lookup"><span data-stu-id="5b203-135">The transaction log backups can be rolled forward quickly, because only the changes that apply to the restored files are applied.</span></span> <span data-ttu-id="5b203-136">Восстановление отдельных файлов может привести к лучшим результатам, чем восстановление всей базы данных целиком, так как в последнем случае неповрежденные файлы не будут скопированы и будут откачены назад.</span><span class="sxs-lookup"><span data-stu-id="5b203-136">Restoring individual files can be better than restoring the whole database, because undamaged files are not copied and then rolled forward.</span></span> <span data-ttu-id="5b203-137">Однако вся цепочка резервных копий журналов должна быть читаема.</span><span class="sxs-lookup"><span data-stu-id="5b203-137">However, the whole chain of log backups still has to be read.</span></span>  
  
5.  <span data-ttu-id="5b203-138">Восстановите базу данных по журналам транзакций.</span><span class="sxs-lookup"><span data-stu-id="5b203-138">Recover the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b203-139">Резервные копии файлов могут использоваться для восстановления базы данных на более ранний момент времени.</span><span class="sxs-lookup"><span data-stu-id="5b203-139">File backups can be used to restore the database to an earlier point in time.</span></span> <span data-ttu-id="5b203-140">Для этого необходимо восстановить полный набор резервных копий файлов, затем восстановить резервные копии журналов транзакций в последовательности до достижения нужной точки, следующей за концом самой последней восстановленной резервной копии файла.</span><span class="sxs-lookup"><span data-stu-id="5b203-140">To do this, you must restore a complete set of file backups, and then restore transaction log backups in sequence to reach a target point that is after the end of the most recent restored file backup.</span></span> <span data-ttu-id="5b203-141">Дополнительные сведения о восстановлении на данный момент времени см. в разделе [Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="5b203-141">For more information about point-in-time recovery, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
## <a name="transact-sql-restore-sequence-for-an-offline-file-restore-full-recovery-model"></a><span data-ttu-id="5b203-142">Последовательность восстановления Transact-SQL для восстановления файлов вне сети (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="5b203-142">Transact-SQL Restore Sequence for an Offline File Restore (Full Recovery Model)</span></span>  
 <span data-ttu-id="5b203-143">Сценарий восстановления файлов состоит из одной последовательности восстановления, которая копирует данные, выполняет накат и восстанавливает соответствующие данные.</span><span class="sxs-lookup"><span data-stu-id="5b203-143">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data.</span></span>  
  
 <span data-ttu-id="5b203-144">В этом разделе показаны основные параметры инструкции [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) для последовательности восстановления файлов.</span><span class="sxs-lookup"><span data-stu-id="5b203-144">This section shows the essential [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) options for a file-restore sequence.</span></span> <span data-ttu-id="5b203-145">Синтаксис и прочие подробности, несущественные для данной цели, опущены.</span><span class="sxs-lookup"><span data-stu-id="5b203-145">Syntax and details that are not relevant to this purpose are omitted.</span></span>  
  
 <span data-ttu-id="5b203-146">Пример показывает автономное восстановление вторичных файлов `A` и `B`с параметром WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="5b203-146">The following sample restore sequence shows an offline restore of two secondary files, `A` and `B`, using WITH NORECOVERY.</span></span> <span data-ttu-id="5b203-147">Далее используются две резервные копий журналов с параметром NORECOVERY, затем резервная копия заключительного фрагмента журнала и выполняется восстановление с параметром WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="5b203-147">Next, two log backups are applied with NORECOVERY, followed with the tail-log backup, and this is restored using WITH RECOVERY.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b203-148">Следующая простая последовательность восстановления начинается с перевода файла в состояние «вне сети», после чего создается резервная копия заключительного фрагмента журнала.</span><span class="sxs-lookup"><span data-stu-id="5b203-148">The following sample restore sequence starts by taking the file offline and then creates a tail-log backup.</span></span>  
  
```  
--Take the file offline.  
ALTER DATABASE database_name MODIFY FILE SET OFFLINE;  
-- Back up the currently active transaction log.  
BACKUP LOG database_name  
   TO <tail_log_backup>  
   WITH NORECOVERY;  
GO   
-- Restore the files.  
RESTORE DATABASE database_name FILE=name   
   FROM <file_backup_of_file_A>   
   WITH NORECOVERY;  
RESTORE DATABASE database_name FILE=<name> ......  
   FROM <file_backup_of_file_B>   
   WITH NORECOVERY;  
-- Restore the log backups.  
RESTORE LOG database_name FROM <log_backup>   
   WITH NORECOVERY;  
RESTORE LOG database_name FROM <log_backup>   
   WITH NORECOVERY;  
RESTORE LOG database_name FROM <tail_log_backup>   
   WITH RECOVERY;  
```  
  
## <a name="examples"></a><span data-ttu-id="5b203-149">Примеры</span><span class="sxs-lookup"><span data-stu-id="5b203-149">Examples</span></span>  
  
-   [<span data-ttu-id="5b203-150">Пример. Оперативное восстановление файла, доступного для чтения и записи &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="5b203-150">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="5b203-151">Пример. Оперативное восстановление файла, доступного только для чтения &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="5b203-151">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="5b203-152">Пример. Автономное восстановление основной и еще одной файловой группы &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="5b203-152">Example: Offline Restore of Primary and One Other Filegroup &#40;Full Recovery Model&#41;</span></span>](example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5b203-153">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="5b203-153">Related Tasks</span></span>  
 <span data-ttu-id="5b203-154">**Восстановление файлов и файловых групп**</span><span class="sxs-lookup"><span data-stu-id="5b203-154">**To restore files and filegroups**</span></span>  
  
-   [<span data-ttu-id="5b203-155">Восстановление файлов в новое место (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5b203-155">Restore Files to a New Location &#40;SQL Server&#41;</span></span>](restore-files-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="5b203-156">Восстановление файлов и файловых групп (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5b203-156">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   <span data-ttu-id="5b203-157"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="5b203-157"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="5b203-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="5b203-158">See Also</span></span>  
 <span data-ttu-id="5b203-159">[Резервное копирование и восстановление: взаимодействие и совместимость &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5b203-159">[Backup and Restore: Interoperability and Coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="5b203-160">[Разностные резервные копии (SQL Server)](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5b203-160">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="5b203-161">[Полные резервные копии файлов (SQL Server)](full-file-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5b203-161">[Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span></span>  
 <span data-ttu-id="5b203-162">[Общие сведения о резервном копировании (SQL Server)](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5b203-162">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="5b203-163">[Обзор процессов восстановления (SQL Server)](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5b203-163">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="5b203-164">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5b203-164">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="5b203-165">[Выполнение полного восстановления базы данных (простая модель восстановления)](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="5b203-165">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="5b203-166">Поэтапное восстановление (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5b203-166">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
