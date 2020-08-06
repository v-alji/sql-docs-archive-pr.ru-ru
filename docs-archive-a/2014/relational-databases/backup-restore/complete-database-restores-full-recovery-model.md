---
title: Полное восстановление базы данных (модель полного восстановления) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- complete database restores
- database restores [SQL Server], complete database
- restoring databases [SQL Server], complete database
- restoring [SQL Server], database
- full recovery model [SQL Server], performing restores
- log backups [SQL Server[
ms.assetid: 5b4c471c-b972-498e-aba9-92cf7a0ea881
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea6ec9f196acd0a64a0b785024bd6426cd6a5381
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668943"
---
# <a name="complete-database-restores-full-recovery-model"></a><span data-ttu-id="482c6-102">Выполнение полного восстановления базы данных (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="482c6-102">Complete Database Restores (Full Recovery Model)</span></span>
  <span data-ttu-id="482c6-103">Задача полного восстановления — восстановить базу данных целиком.</span><span class="sxs-lookup"><span data-stu-id="482c6-103">In a complete database restore, the goal is to restore the whole database.</span></span> <span data-ttu-id="482c6-104">В период восстановления база данных находится вне сети.</span><span class="sxs-lookup"><span data-stu-id="482c6-104">The whole database is offline for the duration of the restore.</span></span> <span data-ttu-id="482c6-105">Прежде чем какая-либо часть базы данных перейдет в режим «в сети», все данные восстанавливаются до точки согласования, в которой все части базы данных находятся в одном и том же моменте времени и в которой нет незафиксированных транзакций.</span><span class="sxs-lookup"><span data-stu-id="482c6-105">Before any part of the database can come online, all data is recovered to a consistent point in which all parts of the database are at the same point in time and no uncommitted transactions exist.</span></span>  
  
 <span data-ttu-id="482c6-106">При работе в режиме модели полного восстановления после восстановления резервных копий данных необходимо восстановить все последующие резервные копии журнала транзакций, а затем саму базу данных.</span><span class="sxs-lookup"><span data-stu-id="482c6-106">Under the full recovery model, after you restore your data backup or backups, you must restore all subsequent transaction log backups and then recover the database.</span></span> <span data-ttu-id="482c6-107">Базу данных можно восстановить до определенной *точки восстановления* в одной из этих резервных копий журналов.</span><span class="sxs-lookup"><span data-stu-id="482c6-107">You can restore a database to a specific *recovery point* within one of these log backups.</span></span> <span data-ttu-id="482c6-108">Этой точкой восстановления может быть заданная дата и время, помеченная транзакция или регистрационный номер транзакции в журнале (LSN).</span><span class="sxs-lookup"><span data-stu-id="482c6-108">The recovery point can be a specific date and time, a marked transaction, or a log sequence number (LSN).</span></span>  
  
 <span data-ttu-id="482c6-109">При восстановлении базы данных, в особенности при использовании модели полного восстановления или модели восстановления с неполным протоколированием, следует использовать одну последовательность восстановления.</span><span class="sxs-lookup"><span data-stu-id="482c6-109">When restoring a database, particularly under the full recovery model or bulk-logged recovery model, you should use a single restore sequence.</span></span> <span data-ttu-id="482c6-110">*Последовательность восстановления* состоит из одной или нескольких операций восстановления, которые выполняют перемещение данных в одном или нескольких этапах восстановления.</span><span class="sxs-lookup"><span data-stu-id="482c6-110">A *restore sequence* consists of one or more restore operations that move data through one or more of the phases of restore.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="482c6-111">Не рекомендуется подключать или восстанавливать базы данных, полученные из неизвестных или ненадежных источников.</span><span class="sxs-lookup"><span data-stu-id="482c6-111">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="482c6-112">В этих базах данных может содержаться вредоносный код, вызывающий выполнение непредусмотренных инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] или появление ошибок путем изменения схемы или физической структуры базы данных.</span><span class="sxs-lookup"><span data-stu-id="482c6-112">These databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="482c6-113">Перед тем как использовать базу данных, полученную из неизвестного или ненадежного источника, выполните на тестовом сервере инструкцию [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) для этой базы данных, а также изучите исходный код в базе данных, например хранимые процедуры и другой пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="482c6-113">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
 <span data-ttu-id="482c6-114">**В этом разделе.**</span><span class="sxs-lookup"><span data-stu-id="482c6-114">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="482c6-115">Восстановление базы данных до точки сбоя</span><span class="sxs-lookup"><span data-stu-id="482c6-115">Restoring a Database to the Point of Failure</span></span>](#PointOfFailure)  
  
-   [<span data-ttu-id="482c6-116">Восстановление базы данных до точки в резервной копии журнала</span><span class="sxs-lookup"><span data-stu-id="482c6-116">Restoring a Database to a Point Within a Log Backup</span></span>](#PointWithinBackup)  
  
-   [<span data-ttu-id="482c6-117">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="482c6-117">Related Tasks</span></span>](#RelatedTasks)  
  
> [!NOTE]  
>  <span data-ttu-id="482c6-118">Сведения о поддержке резервных копий более ранних версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]см. в подразделе "Поддержка совместимости" раздела [RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="482c6-118">For information about support for backups from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the "Compatibility Support" section of [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="restoring-a-database-to-the-point-of-failure"></a><a name="PointOfFailure"></a> <span data-ttu-id="482c6-119">Восстановление базы данных до точки сбоя</span><span class="sxs-lookup"><span data-stu-id="482c6-119">Restoring a Database to the Point of Failure</span></span>  
 <span data-ttu-id="482c6-120">Обычно восстановление базы данных до точки сбоя включает следующие основные шаги:</span><span class="sxs-lookup"><span data-stu-id="482c6-120">Typically, recovering a database to the point of failure involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="482c6-121">Произведите резервное копирование активного журнала транзакций (также известного как заключительный фрагмент журнала).</span><span class="sxs-lookup"><span data-stu-id="482c6-121">Back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="482c6-122">На этом шаге создается резервная копия заключительного фрагмента журнала.</span><span class="sxs-lookup"><span data-stu-id="482c6-122">This creates a tail-log backup.</span></span> <span data-ttu-id="482c6-123">Если активный журнал транзакций недоступен, все транзакции этой части журнала будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="482c6-123">If the active transaction log is unavailable, all transactions in that part of the log are lost.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="482c6-124">При использовании модели восстановления с неполным протоколированием для создания резервной копии для журнала, содержащего операции с неполным протоколированием, требуется доступ ко всем файлам базы данных.</span><span class="sxs-lookup"><span data-stu-id="482c6-124">Under the bulk-logged recovery model, backing up any log that contains bulk-logged operations requires access to all data files in the database.</span></span> <span data-ttu-id="482c6-125">Если файлы данных недоступны, резервное копирование журнала транзакций невозможно.</span><span class="sxs-lookup"><span data-stu-id="482c6-125">If the data files cannot be accessed, the transaction log cannot be backed up.</span></span> <span data-ttu-id="482c6-126">В этом случае необходимо вручную внести все изменения, произошедшие с момента последнего резервного копирования журнала.</span><span class="sxs-lookup"><span data-stu-id="482c6-126">In that case, you have to manually redo all changes that were made since the most recent log backup.</span></span>  
  
     <span data-ttu-id="482c6-127">Дополнительные сведения см. в статье [Резервные копии заключительного фрагмента журнала (SQL Server)](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="482c6-127">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="482c6-128">Восстановите самую последнюю полную резервную копию базы данных без восстановления самой базы данных (RESTORE DATABASE *имя_базы_данных* FROM *устройство_резервного_копирования* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="482c6-128">Restore the most recent full database backup without recovering the database (RESTORE DATABASE *database_name* FROM *backup_device* WITH NORECOVERY).</span></span>  
  
3.  <span data-ttu-id="482c6-129">Если существуют разностные резервные копии, восстановите самую последнюю из них без восстановления базы данных (RESTORE DATABASE *имя_базы_данных* FROM *устройство_разностного_резервного_копирования* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="482c6-129">If differential backups exist, restore the most recent one without recovering the database (RESTORE DATABASE *database_name* FROM *differential_backup_device* WITH NORECOVERY).</span></span>  
  
     <span data-ttu-id="482c6-130">При восстановлении последней разностной резервной копии уменьшается число подлежащих восстановлению резервных копий журнала.</span><span class="sxs-lookup"><span data-stu-id="482c6-130">Restoring the most recent differential backup reduces the number of log backups that must be restored.</span></span>  
  
4.  <span data-ttu-id="482c6-131">Начиная с первой резервной копии журнала транзакций, созданной после только что восстановленной резервной копии, последовательно восстановите журналы с параметром NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="482c6-131">Starting with the first transaction log backup that was created after the backup you just restored, restore the logs in sequence with NORECOVERY.</span></span>  
  
5.  <span data-ttu-id="482c6-132">Восстановите базу данных (RESTORE DATABASE *имя_базы_данных* WITH RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="482c6-132">Recover the database (RESTORE DATABASE *database_name* WITH RECOVERY).</span></span> <span data-ttu-id="482c6-133">Этот шаг можно объединить с восстановлением последней резервной копии журнала.</span><span class="sxs-lookup"><span data-stu-id="482c6-133">Alternatively, this step can be combined with restoring the last log backup.</span></span>  
  
 <span data-ttu-id="482c6-134">На следующем рисунке показана эта последовательность восстановления.</span><span class="sxs-lookup"><span data-stu-id="482c6-134">The following illustration shows this restore sequence.</span></span> <span data-ttu-id="482c6-135">После сбоя (1) создается резервная копия заключительного фрагмента журнала (2).</span><span class="sxs-lookup"><span data-stu-id="482c6-135">After a failure occurs (1), a tail-log backup is created (2).</span></span> <span data-ttu-id="482c6-136">Затем база данных восстанавливается до точки сбоя.</span><span class="sxs-lookup"><span data-stu-id="482c6-136">Next, the database is restored to the point of the failure.</span></span> <span data-ttu-id="482c6-137">Это включает восстановление резервной копии базы данных, последующей разностной резервной копии и всех резервных копий журналов, сохраненных после разностной резервной копии, в том числе резервной копии заключительного фрагмента журнала.</span><span class="sxs-lookup"><span data-stu-id="482c6-137">This involves restoring a database backup, a subsequent differential backup, and every log backup taken after the differential backup, including the tail-log backup.</span></span>  
  
 <span data-ttu-id="482c6-138">![Полное восстановление базы данных на момент сбоя](../../database-engine/media/bnrr-rmfull1-db-failure-pt.gif "Полное восстановление базы данных на момент сбоя")</span><span class="sxs-lookup"><span data-stu-id="482c6-138">![Complete database restore to the time of a failure](../../database-engine/media/bnrr-rmfull1-db-failure-pt.gif "Complete database restore to the time of a failure")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="482c6-139">Если база данных восстанавливается на другой экземпляр сервера, см. раздел [Копирование баз данных путем создания и восстановления резервных копий](../databases/copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="482c6-139">When you restore a database backup onto a different server instance, see [Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md).</span></span>  
  
###  <a name="basic-transact-sql-restore-syntax"></a><a name="TsqlSyntax"></a> <span data-ttu-id="482c6-140">Базовый синтаксис инструкции Transact-SQL RESTORE</span><span class="sxs-lookup"><span data-stu-id="482c6-140">Basic Transact-SQL RESTORE Syntax</span></span>  
 <span data-ttu-id="482c6-141">Базовый синтаксис инструкции [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] для последовательности восстановления в предыдущей иллюстрации выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="482c6-141">The basic [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] syntax for the restore sequence in the preceding illustration is as follows:</span></span>  
  
1.  <span data-ttu-id="482c6-142">RESTORE DATABASE *база_данных* FROM *full database backup* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="482c6-142">RESTORE DATABASE *database* FROM *full database backup* WITH NORECOVERY;</span></span>  
  
2.  <span data-ttu-id="482c6-143">RESTORE DATABASE *база_данных* FROM *полная_разностная_резервная_копия* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="482c6-143">RESTORE DATABASE *database* FROM *full_differential_backup* WITH NORECOVERY;</span></span>  
  
3.  <span data-ttu-id="482c6-144">RESTORE LOG *база_данных* FROM *резервная_копия_журнала* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="482c6-144">RESTORE LOG *database* FROM *log_backup* WITH NORECOVERY;</span></span>  
  
     <span data-ttu-id="482c6-145">Повторите шаг по восстановлению журнала из резервной копии для каждой резервной копии журнала.</span><span class="sxs-lookup"><span data-stu-id="482c6-145">Repeat this restore-log step for each additional log backup.</span></span>  
  
4.  <span data-ttu-id="482c6-146">RESTORE DATABASE *база_данных* WITH RECOVERY;</span><span class="sxs-lookup"><span data-stu-id="482c6-146">RESTORE DATABASE *database* WITH RECOVERY;</span></span>  
  
###  <a name="example-recovering-to-the-point-of-failure-transact-sql"></a><a name="ExampleToPoFTsql"></a> <span data-ttu-id="482c6-147">Пример. Восстановление до точки сбоя (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="482c6-147">Example: Recovering to the Point of Failure (Transact-SQL)</span></span>  
 <span data-ttu-id="482c6-148">В следующем примере [!INCLUDE[tsql](../../includes/tsql-md.md)] показаны важные параметры в последовательности восстановления для восстановления базы данных до точки сбоя.</span><span class="sxs-lookup"><span data-stu-id="482c6-148">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] example shows the essential options in a restore sequence that restores the database to the point of failure.</span></span> <span data-ttu-id="482c6-149">На этом шаге создается резервная копия заключительного фрагмента журнала базы данных.</span><span class="sxs-lookup"><span data-stu-id="482c6-149">The example creates a tail-log backup of the database.</span></span> <span data-ttu-id="482c6-150">Далее в примере восстанавливается полная резервная копия базы данных и резервная копия журнала, а затем восстанавливается резервная копия заключительного фрагмента журнала.</span><span class="sxs-lookup"><span data-stu-id="482c6-150">Next, the example restores a full database backup and log backup and then restores the tail-log backup.</span></span> <span data-ttu-id="482c6-151">В этом примере показан отдельный последний шаг восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="482c6-151">The example recovers the database in a separate, final step.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="482c6-152">В примере используется резервная копия базы данных и резервная копия журнала, созданные в подразделе "Использование резервных копий при модели полного восстановления" раздела [Полные резервные копии баз данных (SQL Server)](full-database-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="482c6-152">This example uses a database backup and log backup that is created in the "Using Database Backups Under the Full Recovery Model" section in [Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md).</span></span> <span data-ttu-id="482c6-153">До создания резервной копии базы данных образец базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] был настроен на использование модели полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="482c6-153">Before the database backup, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database was set to use the full recovery model.</span></span>  
  
```  
USE master;  
--Create tail-log backup.  
BACKUP LOG AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'    
   WITH NORECOVERY;   
GO  
--Restore the full database backup (from backup set 1).  
RESTORE DATABASE AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'   
  WITH FILE=1,   
    NORECOVERY;  
  
--Restore the regular log backup (from backup set 2).  
RESTORE LOG AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'   
  WITH FILE=2,   
    NORECOVERY;  
  
--Restore the tail-log backup (from backup set 3).  
RESTORE LOG AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'  
  WITH FILE=3,   
    NORECOVERY;  
GO  
--recover the database:  
RESTORE DATABASE AdventureWorks2012 WITH RECOVERY;  
GO  
```  
  
##  <a name="restoring-a-database-to-a-point-within-a-log-backup"></a><a name="PointWithinBackup"></a> <span data-ttu-id="482c6-154">Восстановление базы данных на момент времени в пределах резервной копии журнала</span><span class="sxs-lookup"><span data-stu-id="482c6-154">Restoring a Database to a Point Within a Log Backup</span></span>  
 <span data-ttu-id="482c6-155">При работе в режиме полного восстановления можно провести полное восстановление базы данных до состояния на момент времени, до помеченной транзакции или до номера LSN в резервной копии журнала.</span><span class="sxs-lookup"><span data-stu-id="482c6-155">Under the full recovery model, a complete database restore can usually be recovered to a point of time, a marked transaction, or an LSN within a log backup.</span></span> <span data-ttu-id="482c6-156">Однако в модели восстановления с неполным протоколированием, если в резервной копии журнала содержатся изменения с неполным протоколированием, восстановление до момента времени невозможно.</span><span class="sxs-lookup"><span data-stu-id="482c6-156">However, under the bulk-logged recovery model, if the log backup contains bulk-logged changes, point-in-time recovery is not possible.</span></span>  
  
### <a name="sample-point-in-time-restore-scenarios"></a><span data-ttu-id="482c6-157">Образцы сценариев восстановления на определенный момент времени</span><span class="sxs-lookup"><span data-stu-id="482c6-157">Sample Point-in-Time Restore Scenarios</span></span>  
 <span data-ttu-id="482c6-158">В следующем примере предполагается использование критически важной системы баз данных, в которой полная резервная копия баз данных создается ежедневно в полночь, разностная резервная копия — каждый час, с понедельника до субботы. Резервные копии журнала создаются каждые 10 минут в течение дня.</span><span class="sxs-lookup"><span data-stu-id="482c6-158">The following example assumes a mission-critical database system for which a full database backup is created daily at midnight, a differential database backup is created on the hour, Monday through Saturday, and transaction log backups are created every 10 minutes throughout the day.</span></span> <span data-ttu-id="482c6-159">Чтобы восстановить базу данных до ее состояния на 05:19</span><span class="sxs-lookup"><span data-stu-id="482c6-159">To restore the database to the state is was in at 5:19 A.M.</span></span> <span data-ttu-id="482c6-160">среды, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="482c6-160">Wednesday, do the following:</span></span>  
  
1.  <span data-ttu-id="482c6-161">Восстановить полную резервную копию базы данных, полученную в полночь вторника.</span><span class="sxs-lookup"><span data-stu-id="482c6-161">Restore the full database backup that was created Tuesday at midnight.</span></span>  
  
2.  <span data-ttu-id="482c6-162">Восстановление разностной резервной копии базы данных, созданной в 5:00</span><span class="sxs-lookup"><span data-stu-id="482c6-162">Restore the differential database backup that was created at 5:00 A.M.</span></span> <span data-ttu-id="482c6-163">в среду.</span><span class="sxs-lookup"><span data-stu-id="482c6-163">on Wednesday.</span></span>  
  
3.  <span data-ttu-id="482c6-164">Применение резервной копии журнала транзакций, созданной в 5:10</span><span class="sxs-lookup"><span data-stu-id="482c6-164">Apply the transaction log backup that was created at 5:10 A.M.</span></span> <span data-ttu-id="482c6-165">в среду.</span><span class="sxs-lookup"><span data-stu-id="482c6-165">on Wednesday.</span></span>  
  
4.  <span data-ttu-id="482c6-166">Применение резервной копии журнала транзакций, созданной в 5:20</span><span class="sxs-lookup"><span data-stu-id="482c6-166">Apply the transaction log backup that was created 5:20 A.M.</span></span> <span data-ttu-id="482c6-167">в среду, с указанием того, что процесс восстановления относится лишь к происшедшим до 5:19 транзакциям.</span><span class="sxs-lookup"><span data-stu-id="482c6-167">on Wednesday, specifying that the recovery process applies only to transactions that occurred before 5:19 A.M.</span></span>  
  
 <span data-ttu-id="482c6-168">В случае если нужно восстановить базу данных до ее состояния на 03:04</span><span class="sxs-lookup"><span data-stu-id="482c6-168">Alternatively, if the database needs to be restored to its state at 3:04 A.M.</span></span> <span data-ttu-id="482c6-169">четверга, но разностная резервная копия базы данных, созданная в 3:00</span><span class="sxs-lookup"><span data-stu-id="482c6-169">Thursday, but the differential database backup that was created at 3:00 A.M.</span></span> <span data-ttu-id="482c6-170">четверга недоступна, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="482c6-170">Thursday is unavailable, do the following:</span></span>  
  
1.  <span data-ttu-id="482c6-171">Восстановить резервную копию базы данных, полученную в полночь в среду.</span><span class="sxs-lookup"><span data-stu-id="482c6-171">Restore the database backup that was created Wednesday at midnight.</span></span>  
  
2.  <span data-ttu-id="482c6-172">Восстановление разностной резервной копии базы данных, созданной в 2:00</span><span class="sxs-lookup"><span data-stu-id="482c6-172">Restore the differential database backup that was created at 2:00 A.M.</span></span> <span data-ttu-id="482c6-173">в четверг.</span><span class="sxs-lookup"><span data-stu-id="482c6-173">on Thursday.</span></span>  
  
3.  <span data-ttu-id="482c6-174">Применение всех резервных копий журнала транзакций, созданных за время от 2:10</span><span class="sxs-lookup"><span data-stu-id="482c6-174">Apply all the transaction log backups created from 2:10 A.M.</span></span> <span data-ttu-id="482c6-175">до 3:00</span><span class="sxs-lookup"><span data-stu-id="482c6-175">to 3:00 A.M.</span></span> <span data-ttu-id="482c6-176">в четверг.</span><span class="sxs-lookup"><span data-stu-id="482c6-176">on Thursday.</span></span>  
  
4.  <span data-ttu-id="482c6-177">Применение резервной копии журнала транзакций, созданной в 3:10</span><span class="sxs-lookup"><span data-stu-id="482c6-177">Apply the transaction log backup that was created at 3:10 A.M.</span></span> <span data-ttu-id="482c6-178">в четверг с остановкой процесса восстановления на момент 3:04.</span><span class="sxs-lookup"><span data-stu-id="482c6-178">on Thursday, stopping the recovery process at 3:04 A.M.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="482c6-179">Пример восстановления на определенный момент времени см. в разделе [Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="482c6-179">For an example of a point-in-time restore, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="482c6-180">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="482c6-180">Related Tasks</span></span>  
 <span data-ttu-id="482c6-181">**Восстановление полной резервной копии базы данных**</span><span class="sxs-lookup"><span data-stu-id="482c6-181">**To restore a full database backup**</span></span>  
  
-   [<span data-ttu-id="482c6-182">Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="482c6-182">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="482c6-183">Восстановление базы данных в новом расположении (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="482c6-183">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
 <span data-ttu-id="482c6-184">**Восстановление разностной резервной копии базы данных**</span><span class="sxs-lookup"><span data-stu-id="482c6-184">**To restore a differential database backup**</span></span>  
  
-   [<span data-ttu-id="482c6-185">Восстановление разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="482c6-185">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](restore-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="482c6-186">**Восстановление резервной копии журнала транзакций**</span><span class="sxs-lookup"><span data-stu-id="482c6-186">**To restore a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="482c6-187">Восстановление резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="482c6-187">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
 <span data-ttu-id="482c6-188">**Восстановление резервной копии с помощью управляющих объектов SQL Server (SMO)**</span><span class="sxs-lookup"><span data-stu-id="482c6-188">**To restore a backup by using SQL Server Management Objects (SMO)**</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  
 <span data-ttu-id="482c6-189">**Восстановление базы данных до точки в резервной копии журнала**</span><span class="sxs-lookup"><span data-stu-id="482c6-189">**To restore a database to a point within a log backup**</span></span>  
  
-   [<span data-ttu-id="482c6-190">Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="482c6-190">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="482c6-191">Восстановление связанных баз данных, которые содержат помеченную транзакцию</span><span class="sxs-lookup"><span data-stu-id="482c6-191">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
-   [<span data-ttu-id="482c6-192">Восстановление до номера LSN (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="482c6-192">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="482c6-193">См. также:</span><span class="sxs-lookup"><span data-stu-id="482c6-193">See Also</span></span>  
 <span data-ttu-id="482c6-194">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="482c6-194">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="482c6-195">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="482c6-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="482c6-196">[Применение резервных копий журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="482c6-196">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="482c6-197">[sp_addumpdevice (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="482c6-197">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="482c6-198">[Полные резервные копии баз данных (SQL Server)](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="482c6-198">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="482c6-199">[Разностные резервные копии (SQL Server)](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="482c6-199">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="482c6-200">[Общие сведения о резервном копировании (SQL Server)](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="482c6-200">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="482c6-201">Обзор процессов восстановления (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="482c6-201">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
  
  
