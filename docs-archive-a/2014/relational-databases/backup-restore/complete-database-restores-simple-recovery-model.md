---
title: Выполнение полного восстановления базы данных (простая модель восстановления) | Документация Майкрософт
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
- simple recovery model [SQL Server]
- restoring [SQL Server], database
ms.assetid: 49828927-1727-4d1d-9ef5-3de43f68c026
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67eee8d7d6f44c9ff83795bf2a8bd612309bf0a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668940"
---
# <a name="complete-database-restores-simple-recovery-model"></a><span data-ttu-id="34d2a-102">Выполнение полного восстановления базы данных (Простая модель восстановления)</span><span class="sxs-lookup"><span data-stu-id="34d2a-102">Complete Database Restores (Simple Recovery Model)</span></span>
  <span data-ttu-id="34d2a-103">Задача полного восстановления — восстановить базу данных целиком.</span><span class="sxs-lookup"><span data-stu-id="34d2a-103">In a complete database restore, the goal is to restore the whole database.</span></span> <span data-ttu-id="34d2a-104">В период восстановления база данных находится вне сети.</span><span class="sxs-lookup"><span data-stu-id="34d2a-104">The whole database is offline for the duration of the restore.</span></span> <span data-ttu-id="34d2a-105">Прежде чем какая-либо часть базы данных перейдет в режим «в сети», все данные восстанавливаются до точки согласования, в которой все части базы данных находятся в одном и том же моменте времени и в которой нет незафиксированных транзакций.</span><span class="sxs-lookup"><span data-stu-id="34d2a-105">Before any part of the database can come online, all data is recovered to a consistent point in which all parts of the database are at the same point in time and no uncommitted transactions exist.</span></span>  
  
 <span data-ttu-id="34d2a-106">При использовании простой модели восстановления база данных не может быть восстановлена к определенному моменту времени внутри заданной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="34d2a-106">Under the simple recovery model, the database cannot be restored to a specific point in time within a specific backup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="34d2a-107">Не рекомендуется подключать или восстанавливать базы данных, полученные из неизвестных или ненадежных источников.</span><span class="sxs-lookup"><span data-stu-id="34d2a-107">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="34d2a-108">В этих базах данных может содержаться вредоносный код, вызывающий выполнение непредусмотренных инструкций [!INCLUDE[tsql](../../../includes/tsql-md.md)] или появление ошибок путем изменения схемы или физической структуры базы данных.</span><span class="sxs-lookup"><span data-stu-id="34d2a-108">These databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="34d2a-109">Перед тем как использовать базу данных, полученную из неизвестного или ненадежного источника, выполните на тестовом сервере инструкцию [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) для этой базы данных, а также изучите исходный код в базе данных, например хранимые процедуры и другой пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="34d2a-109">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  

  
> [!NOTE]  
>  <span data-ttu-id="34d2a-110">Сведения о поддержке резервных копий более ранних версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]см. в подразделе "Поддержка совместимости" раздела [RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="34d2a-110">For information about support for backups from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the "Compatibility Support" section of [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="overview-of-database-restore-under-the-simple-recovery-model"></a><a name="Overview"></a> <span data-ttu-id="34d2a-111">Общие сведения о восстановлении баз данных в рамках простой модели восстановления</span><span class="sxs-lookup"><span data-stu-id="34d2a-111">Overview of Database Restore Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="34d2a-112">Полное восстановление базы данных при использовании простой модели восстановления состоит из одной или двух инструкций [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , в зависимости от того, нужно ли выполнять восстановление разностной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="34d2a-112">A full database restore under the simple recovery model involves one or two [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statements, depending on whether you want to restore a differential database backup.</span></span> <span data-ttu-id="34d2a-113">При использовании только полной резервной копии базы данных просто восстановите последнюю резервную копию, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="34d2a-113">If you are using only a full database backup, just restore the most recent backup, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="34d2a-114">![Восстановление только полной резервной копии базы данных](../../database-engine/media/bnrr-rmsimple1-fulldbbu.gif "Восстановление только полной резервной копии базы данных")</span><span class="sxs-lookup"><span data-stu-id="34d2a-114">![Restoring only a full database backup](../../database-engine/media/bnrr-rmsimple1-fulldbbu.gif "Restoring only a full database backup")</span></span>  
  
 <span data-ttu-id="34d2a-115">Если используется также восстановление разностной резервной копии базы данных, восстановите самую последнюю полную резервную копию базы данных без восстановления самой базы данных, а затем восстановите самую последнюю разностную резервную копию базы данных и восстановите саму базу данных.</span><span class="sxs-lookup"><span data-stu-id="34d2a-115">If you are also using a differential database backup, restore the most recent full database backup without recovering the database, and then restore the most recent differential database backup and recover the database.</span></span> <span data-ttu-id="34d2a-116">На следующем рисунке показан этот процесс.</span><span class="sxs-lookup"><span data-stu-id="34d2a-116">The following illustration shows this process.</span></span>  
  
 <span data-ttu-id="34d2a-117">![Восстановление полной и разностной резервных копий базы данных](../../database-engine/media/bnrr-rmsimple2-diffdbbu.gif "Восстановление полной и разностной резервных копий базы данных")</span><span class="sxs-lookup"><span data-stu-id="34d2a-117">![Restoring full and differential database backups](../../database-engine/media/bnrr-rmsimple2-diffdbbu.gif "Restoring full and differential database backups")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34d2a-118">Если база данных восстанавливается на другой экземпляр сервера, см. раздел [Копирование баз данных путем создания и восстановления резервных копий](../databases/copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="34d2a-118">If you plan to restore a database backup onto a different server instance, see [Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md).</span></span>  
  
###  <a name="basic-transact-sql-restore-syntax"></a><a name="TsqlSyntax"></a> <span data-ttu-id="34d2a-119">Базовый синтаксис инструкции Transact-SQL RESTORE</span><span class="sxs-lookup"><span data-stu-id="34d2a-119">Basic Transact-SQL RESTORE Syntax</span></span>  
 <span data-ttu-id="34d2a-120">Базовый синтаксис инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) для восстановления полной резервной копии базы данных выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="34d2a-120">The basic [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for restoring a full database backup is:</span></span>  
  
 <span data-ttu-id="34d2a-121">RESTORE DATABASE *имя_базы_данных* FROM *устройство_резервного_копирования* [ WITH NORECOVERY ]</span><span class="sxs-lookup"><span data-stu-id="34d2a-121">RESTORE DATABASE *database_name* FROM *backup_device* [ WITH NORECOVERY ]</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34d2a-122">Если планируется также восстановление разностной резервной копии базы данных, используйте параметр WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="34d2a-122">Use WITH NORECOVERY if you plan to also restore a differential database backup.</span></span>  
  
 <span data-ttu-id="34d2a-123">Базовый синтаксис инструкции [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) восстановления из резервной копии базы данных:</span><span class="sxs-lookup"><span data-stu-id="34d2a-123">The basic [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for restoring a database backup is:</span></span>  
  
 <span data-ttu-id="34d2a-124">RESTORE DATABASE *имя_базы_данных* FROM *устройство_резервного_копирования* WITH RECOVERY</span><span class="sxs-lookup"><span data-stu-id="34d2a-124">RESTORE DATABASE *database_name* FROM *backup_device* WITH RECOVERY</span></span>  
  
###  <a name="example-transact-sql"></a><a name="Example"></a> <span data-ttu-id="34d2a-125">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="34d2a-125">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="34d2a-126">В следующем примере сначала показано, как использовать инструкцию [BACKUP](/sql/t-sql/statements/backup-transact-sql) , чтобы создать полную резервную копию базы данных и разностную резервную копию базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34d2a-126">The following example first shows how to use the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement to create a full database backup and a differential database backup of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="34d2a-127">Затем в примере восстанавливаются резервные копии в последовательности восстановления.</span><span class="sxs-lookup"><span data-stu-id="34d2a-127">The example then restores these backups in sequence.</span></span> <span data-ttu-id="34d2a-128">База данных восстанавливается к состоянию на момент создания разностной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="34d2a-128">The database is restored to its state as of the time that the differential database backup finished.</span></span>  
  
 <span data-ttu-id="34d2a-129">В  примере показаны критически важные параметры в последовательности восстановления для полного восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="34d2a-129">The example shows the critical options in a restore sequence for the complete database restore scenario.</span></span> <span data-ttu-id="34d2a-130">*Последовательность восстановления* состоит из одной или нескольких операций восстановления, которые выполняют перемещение данных в одном или нескольких этапах восстановления.</span><span class="sxs-lookup"><span data-stu-id="34d2a-130">A *restore sequence* consists of one or more restore operations that move data through one or more of the phases of restore.</span></span> <span data-ttu-id="34d2a-131">Синтаксис и прочие подробности, несущественные для данной цели, опущены.</span><span class="sxs-lookup"><span data-stu-id="34d2a-131">Syntax and details that are not relevant to this purpose are omitted.</span></span> <span data-ttu-id="34d2a-132">При восстановлении базы данных рекомендуется явно указать параметр RECOVERY, несмотря на то, что он подразумевается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34d2a-132">When you recover a database, we recommend explicitly specifying the RECOVERY option for clarity, even though it is the default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34d2a-133">Пример начинается с инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) , которая устанавливает модель восстановления `SIMPLE`.</span><span class="sxs-lookup"><span data-stu-id="34d2a-133">The example starts with an [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement that sets the recovery model to `SIMPLE`.</span></span>  
  
```  
USE master;  
--Make sure the database is using the simple recovery model.  
ALTER DATABASE AdventureWorks2012 SET RECOVERY SIMPLE;  
GO  
-- Back up the full AdventureWorks2012 database.  
BACKUP DATABASE AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
  WITH FORMAT;  
GO  
--Create a differential database backup.  
BACKUP DATABASE AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'  
   WITH DIFFERENTIAL;  
GO  
--Restore the full database backup (from backup set 1).  
RESTORE DATABASE AdventureWorks2012   
FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
   WITH FILE=1, NORECOVERY;  
--Restore the differential backup (from backup set 2).  
RESTORE DATABASE AdventureWorks2012   
FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
   WITH FILE=2, RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="34d2a-134">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="34d2a-134">Related Tasks</span></span>  
 <span data-ttu-id="34d2a-135">**Восстановление полной резервной копии базы данных**</span><span class="sxs-lookup"><span data-stu-id="34d2a-135">**To restore a full database backup**</span></span>  
  
-   [<span data-ttu-id="34d2a-136">Восстановление резервной копии базы данных в простой модели восстановления (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="34d2a-136">Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md)  
  
-   [<span data-ttu-id="34d2a-137">Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="34d2a-137">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="34d2a-138">Восстановление базы данных в новом расположении (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="34d2a-138">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
 <span data-ttu-id="34d2a-139">**Восстановление разностной резервной копии базы данных**</span><span class="sxs-lookup"><span data-stu-id="34d2a-139">**To restore a differential database backup**</span></span>  
  
-   [<span data-ttu-id="34d2a-140">Восстановление разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="34d2a-140">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](restore-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="34d2a-141">**Восстановление резервной копии с помощью управляющих объектов SQL Server (SMO)**</span><span class="sxs-lookup"><span data-stu-id="34d2a-141">**To restore a backup by using SQL Server Management Objects (SMO)**</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  

  
## <a name="see-also"></a><span data-ttu-id="34d2a-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="34d2a-142">See Also</span></span>  
 <span data-ttu-id="34d2a-143">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34d2a-143">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="34d2a-144">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34d2a-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="34d2a-145">[sp_addumpdevice (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34d2a-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="34d2a-146">[Полные резервные копии баз данных (SQL Server)](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34d2a-146">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="34d2a-147">[Разностные резервные копии (SQL Server)](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34d2a-147">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="34d2a-148">[Общие сведения о резервном копировании (SQL Server)](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34d2a-148">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="34d2a-149">Обзор процессов восстановления (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="34d2a-149">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
  
  
