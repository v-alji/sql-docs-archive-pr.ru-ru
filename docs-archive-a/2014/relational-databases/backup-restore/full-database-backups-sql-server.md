---
title: Полные резервные копии баз данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- backups [SQL Server], database
- backing up databases [SQL Server], full backups
- estimating database backup size
- backing up [SQL Server], size of backup
- database backups [SQL Server], full backups
- size [SQL Server], backups
- database backups [SQL Server], about backing up databases
ms.assetid: 4d933d19-8d21-4aa1-8153-d230cb3a3f99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ee871b6cabbe6c2b2cb4f444fd1e2d42d711dfbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731758"
---
# <a name="full-database-backups-sql-server"></a><span data-ttu-id="1b302-102">Полные резервные копии баз данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1b302-102">Full Database Backups (SQL Server)</span></span>
  <span data-ttu-id="1b302-103">При полном резервном копировании создается резервная копия всей базы данных целиком.</span><span class="sxs-lookup"><span data-stu-id="1b302-103">A full database backup backs up the whole database.</span></span> <span data-ttu-id="1b302-104">В нее входит часть журнала транзакций, что позволяет восстановить полную базу данных из полной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="1b302-104">This includes part of the transaction log so that the full database can be recovered after a full database backup is restored.</span></span> <span data-ttu-id="1b302-105">Полные резервные копии базы данных отображают состояние базы данных на момент завершения резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="1b302-105">Full database backups represent the database at the time the backup finished.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="1b302-106">Однако по мере увеличения размера базы данных полное резервное копирование занимает больше времени и требует больше пространства для хранения.</span><span class="sxs-lookup"><span data-stu-id="1b302-106">As a database increases in size full database backups take more time to finish and require more storage space.</span></span> <span data-ttu-id="1b302-107">Поэтому для больших баз данных может потребоваться, кроме полных резервных копий, создавать также и *разностные резервные копии баз данных*.</span><span class="sxs-lookup"><span data-stu-id="1b302-107">Therefore, for a large database, you might want to supplement a full database backup with a series of *differential database backups*.</span></span> <span data-ttu-id="1b302-108">Дополнительные сведения см. в разделе [Разностные резервные копии (SQL Server)](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1b302-108">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1b302-109">Для резервной копии базы данных свойству TRUSTWORTHY присваивается значение OFF.</span><span class="sxs-lookup"><span data-stu-id="1b302-109">TRUSTWORTHY is set to OFF on a database backup.</span></span> <span data-ttu-id="1b302-110">Дополнительные сведения о том, как задать для параметра TRUSTWORTHY значение ON, см. в разделе [Параметры ALTER DATABASE SET (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="1b302-110">For information about how to set TRUSTWORTHY to ON, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="1b302-111">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="1b302-111">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="1b302-112">Резервные копии баз данных при простой модели восстановления</span><span class="sxs-lookup"><span data-stu-id="1b302-112">Database Backups Under the Simple Recovery Model</span></span>](#DbBuRMs)  
  
-   [<span data-ttu-id="1b302-113">Резервные копии баз данных при модели полного восстановления</span><span class="sxs-lookup"><span data-stu-id="1b302-113">Database Backups Under the Full Recovery Model</span></span>](#DbBuRMf)  
  
-   [<span data-ttu-id="1b302-114">Восстановление базы данных с помощью полной резервной копии</span><span class="sxs-lookup"><span data-stu-id="1b302-114">Use a Full Database Backup to Restore the Database</span></span>](#RestoreDbBu)  
  
-   [<span data-ttu-id="1b302-115">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="1b302-115">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="database-backups-under-the-simple-recovery-model"></a><a name="DbBuRMs"></a> <span data-ttu-id="1b302-116">Резервные копии баз данных при простой модели восстановления</span><span class="sxs-lookup"><span data-stu-id="1b302-116">Database Backups Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="1b302-117">При использовании простой модели восстановления после создания каждой резервной копии база данных уязвима для потенциальной потери данных в случае аварийной ситуации.</span><span class="sxs-lookup"><span data-stu-id="1b302-117">Under the simple recovery model, after each backup, the database is exposed to potential work loss if a disaster were to occur.</span></span> <span data-ttu-id="1b302-118">Потенциальные потери работы растут с каждым внесенным изменением до следующего создания резервной копии, после чего объем потенциальных потерь работы снова уменьшается до нуля и начинается новый цикл.</span><span class="sxs-lookup"><span data-stu-id="1b302-118">The work-loss exposure increases with each update until the next backup, when the work-loss exposure returns to zero and a new cycle of work-loss exposure starts.</span></span> <span data-ttu-id="1b302-119">Потенциальные потери работы становятся тем больше, чем больше времени прошло со времени создания последней резервной копии.</span><span class="sxs-lookup"><span data-stu-id="1b302-119">Work-loss exposure increases over time between backups.</span></span> <span data-ttu-id="1b302-120">На следующем рисунке показана вероятность потери данных при использовании стратегии резервного копирования, в которой применяются только полные резервные копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="1b302-120">The following illustration shows the work-loss exposure for a backup strategy that uses only full database backups.</span></span>  
  
 <span data-ttu-id="1b302-121">![Показывает риск потери результатов работы в промежутках между созданием резервных копий базы данных](../../database-engine/media/bnr-rmsimple-1-fulldb-backups.gif "Показывает риск потери результатов работы в промежутках между созданием резервных копий базы данных")</span><span class="sxs-lookup"><span data-stu-id="1b302-121">![Shows work-loss exposure between database backups](../../database-engine/media/bnr-rmsimple-1-fulldb-backups.gif "Shows work-loss exposure between database backups")</span></span>  
  
### <a name="example--tsql"></a><span data-ttu-id="1b302-122">Пример ([!INCLUDE[tsql](../../../includes/tsql-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="1b302-122">Example ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span></span>  
 <span data-ttu-id="1b302-123">В следующем примере показано, как создать полную резервную копию базы данных с помощью предложения WITH FORMAT, чтобы перезаписать все существующие резервные копии и создать новый набор носителей.</span><span class="sxs-lookup"><span data-stu-id="1b302-123">The following example shows how to create a full database backup by using WITH FORMAT to overwrite any existing backups and create a new media set.</span></span>  
  
```  
-- Back up the AdventureWorks2012 database to new media set.  
BACKUP DATABASE AdventureWorks2012  
    TO DISK = 'Z:\SQLServerBackups\AdventureWorksSimpleRM.bak'   
    WITH FORMAT;  
GO  
```  
  
##  <a name="database-backups-under-the-full-recovery-model"></a><a name="DbBuRMf"></a> <span data-ttu-id="1b302-124">Резервные копии баз данных при модели полного восстановления</span><span class="sxs-lookup"><span data-stu-id="1b302-124">Database Backups Under the Full Recovery Model</span></span>  
 <span data-ttu-id="1b302-125">Для баз данных, в которых используются полная модель восстановления и модель восстановления с неполным протоколированием, создание резервных копий баз данных необходимо, но недостаточно для нормальной работы.</span><span class="sxs-lookup"><span data-stu-id="1b302-125">For databases that use full and bulk-logged recovery, database backups are necessary but not sufficient.</span></span> <span data-ttu-id="1b302-126">Требуется также создание резервных копий журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="1b302-126">Transaction log backups are also required.</span></span> <span data-ttu-id="1b302-127">На следующем рисунке показан минимальный вариант полной стратегии резервного копирования, доступный при использовании модели полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="1b302-127">The following illustration shows the least complex backup strategy that is possible under the full recovery model.</span></span>  
  
 <span data-ttu-id="1b302-128">![Последовательность полных резервных копий базы данных и резервных копий журналов](../../database-engine/media/bnr-rmfull-1-fulldb-log-backups.gif "Последовательность полных резервных копий базы данных и резервных копий журналов")</span><span class="sxs-lookup"><span data-stu-id="1b302-128">![Series of full database backups and log backups](../../database-engine/media/bnr-rmfull-1-fulldb-log-backups.gif "Series of full database backups and log backups")</span></span>  
  
 <span data-ttu-id="1b302-129">Сведения о том, как создавать резервные копии журналов, см. в разделе [Резервные копии журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1b302-129">For information about how to create log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
### <a name="example--tsql"></a><span data-ttu-id="1b302-130">Пример ([!INCLUDE[tsql](../../../includes/tsql-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="1b302-130">Example ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span></span>  
 <span data-ttu-id="1b302-131">В следующем примере показано, как создать полную резервную копию базы данных с помощью предложения WITH FORMAT, чтобы перезаписать все существующие резервные копии и создать новый набор носителей.</span><span class="sxs-lookup"><span data-stu-id="1b302-131">The following example shows how to create a full database backup by using WITH FORMAT to overwrite any existing backups and create a new media set.</span></span> <span data-ttu-id="1b302-132">Затем в примере производится резервное копирование журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="1b302-132">Then, the example backs up the transaction log.</span></span> <span data-ttu-id="1b302-133">В реальной ситуации, возможно, придется создать ряд обычных резервных копий журнала.</span><span class="sxs-lookup"><span data-stu-id="1b302-133">In a real-life situation, you would have to perform a series of regular log backups.</span></span> <span data-ttu-id="1b302-134">В этом примере образец базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] должен быть переключен на модель полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="1b302-134">For this example, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database is set to use the full recovery model.</span></span>  
  
```  
USE master;  
ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
GO  
-- Back up the AdventureWorks2012 database to new media set (backup set 1).  
BACKUP DATABASE AdventureWorks2012  
  TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012FullRM.bak'   
  WITH FORMAT;  
GO  
--Create a routine log backup (backup set 2).  
BACKUP LOG AdventureWorks2012 TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012FullRM.bak';  
GO  
```  
  
##  <a name="use-a-full-database-backup-to-restore-the-database"></a><a name="RestoreDbBu"></a> <span data-ttu-id="1b302-135">Восстановление базы данных с помощью полной резервной копии</span><span class="sxs-lookup"><span data-stu-id="1b302-135">Use a Full Database Backup to Restore the Database</span></span>  
 <span data-ttu-id="1b302-136">Из полной резервной копии базы данных путем ее восстановления можно за один этап восстановить всю базу данных в любом местоположении.</span><span class="sxs-lookup"><span data-stu-id="1b302-136">You can re-create a whole database in one step by restoring the database from a full database backup to any location.</span></span> <span data-ttu-id="1b302-137">В резервную копию включается достаточная часть журнала транзакций, чтобы можно было восстановить базу данных в состоянии на момент окончания резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="1b302-137">Enough of the transaction log is included in the backup to let you recover the database to the time when the backup finished.</span></span> <span data-ttu-id="1b302-138">Восстановленная база данных соответствует состоянию исходной базы данных на момент окончания резервного копирования, за вычетом незавершенных транзакций.</span><span class="sxs-lookup"><span data-stu-id="1b302-138">The restored database matches the state of the original database when the database backup finished, minus any uncommitted transactions.</span></span> <span data-ttu-id="1b302-139">Согласно модели полного восстановления затем следует выполнить восстановление всех последующих резервных копий журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="1b302-139">Under the full recovery model, you should then restore all subsequent transaction log backups.</span></span> <span data-ttu-id="1b302-140">После восстановления базы данных выполняется откат незавершенных транзакций.</span><span class="sxs-lookup"><span data-stu-id="1b302-140">When the database is recovered, uncommitted transactions are rolled back.</span></span>  
  
 <span data-ttu-id="1b302-141">Дополнительные сведения см. в разделе [Выполнение полного восстановления базы данных (простая модель восстановления)](complete-database-restores-simple-recovery-model.md) или [Выполнение полного восстановления базы данных (модель полного восстановления)](complete-database-restores-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="1b302-141">For more information, see [Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) or [Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1b302-142">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="1b302-142">Related Tasks</span></span>  
 <span data-ttu-id="1b302-143">**Создание полной резервной копии базы данных**</span><span class="sxs-lookup"><span data-stu-id="1b302-143">**To create a full database backup**</span></span>  
  
-   [<span data-ttu-id="1b302-144">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1b302-144">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   <span data-ttu-id="1b302-145"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="1b302-145"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
 <span data-ttu-id="1b302-146">**Расписание заданий резервного копирования**</span><span class="sxs-lookup"><span data-stu-id="1b302-146">**To schedule backup jobs**</span></span>  
  
 [<span data-ttu-id="1b302-147">Использование мастера планов обслуживания</span><span class="sxs-lookup"><span data-stu-id="1b302-147">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="1b302-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b302-148">See Also</span></span>  
 <span data-ttu-id="1b302-149">[Резервное копирование и восстановление баз данных SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="1b302-149">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="1b302-150">[Общие сведения о резервном копировании (SQL Server)](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1b302-150">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="1b302-151">Создание и восстановление резервных копий баз данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1b302-151">Backup and Restore of Analysis Services Databases</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases)  
  
  
