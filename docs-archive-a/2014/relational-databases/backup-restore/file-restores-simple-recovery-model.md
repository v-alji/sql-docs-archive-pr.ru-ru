---
title: Восстановление файлов (простая модель восстановления) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- file restores [SQL Server]
- simple recovery model [SQL Server]
- restoring files [SQL Server], Transact-SQL restore sequence
- restoring files [SQL Server]
- Transact-SQL restore sequence
- restoring files [SQL Server], simple recovery model
- file restores [SQL Server], simple recovery model
- file restores [SQL Server], Transact-SQL restore sequence
ms.assetid: b6d07386-7c6f-4cc6-be32-93289adbd3d6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2ed48f48f531e727de5d6e1403ef47f5399f874d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731761"
---
# <a name="file-restores-simple-recovery-model"></a><span data-ttu-id="f073c-102">Восстановления файлов (простая модель восстановления)</span><span class="sxs-lookup"><span data-stu-id="f073c-102">File Restores (Simple Recovery Model)</span></span>
  <span data-ttu-id="f073c-103">Сведения в этом разделе относятся только к базам данных, использующим простую модель восстановления и содержащим хотя бы одну вторичную файловую группу только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f073c-103">This topic is relevant only for simple-model databases that contain at least one read-only secondary filegroup.</span></span>  
  
 <span data-ttu-id="f073c-104">Цель восстановления файлов — восстановить один или несколько поврежденных файлов, не восстанавливая всю базу данных.</span><span class="sxs-lookup"><span data-stu-id="f073c-104">In a file restore, the goal is to restore one or more damaged files without restoring the whole database.</span></span> <span data-ttu-id="f073c-105">В рамках простой модели восстановления резервные копии файлов и файловых групп поддерживаются только на файлах только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f073c-105">Under the simple recovery model, file backups are supported only for read-only files.</span></span> <span data-ttu-id="f073c-106">Первичная файловая группа и вторичные файловые группы, доступные как для чтения и записи, всегда восстанавливаются вместе из резервной копии базы данных или частичной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="f073c-106">The primary filegroup and read/write secondary filegroups are always restored together, by restoring a database or partial backup.</span></span>  
  
 <span data-ttu-id="f073c-107">Существуют следующие сценарии восстановления файлов.</span><span class="sxs-lookup"><span data-stu-id="f073c-107">The file-restore scenarios are as follows:</span></span>  
  
-   <span data-ttu-id="f073c-108">Восстановление файлов в режиме «вне сети»</span><span class="sxs-lookup"><span data-stu-id="f073c-108">Offline file restore</span></span>  
  
     <span data-ttu-id="f073c-109">При *автономном восстановлении файлов*база данных находится в режиме «вне сети», в то время как происходит восстановление поврежденных файлов или файловых групп.</span><span class="sxs-lookup"><span data-stu-id="f073c-109">In an *offline file restore*, the database is offline while damaged files or filegroups are restored.</span></span> <span data-ttu-id="f073c-110">В конце последовательности восстановления база данных переходит в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="f073c-110">At the end of the restore sequence, the database comes online.</span></span>  
  
     <span data-ttu-id="f073c-111">Автономное восстановление файлов поддерживают все выпуски [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f073c-111">All editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support offline file restore.</span></span>  
  
-   <span data-ttu-id="f073c-112">Восстановление файлов в сети</span><span class="sxs-lookup"><span data-stu-id="f073c-112">Online file restore</span></span>  
  
     <span data-ttu-id="f073c-113">При *оперативном восстановлении файлов*, если база данных во время восстановления находится в режиме «в сети», то остается в этом режиме в течение времени восстановления файлов.</span><span class="sxs-lookup"><span data-stu-id="f073c-113">In an *online file restore*, if database is online at restore time, it remains online during the file restore.</span></span> <span data-ttu-id="f073c-114">Однако каждая файловая группа, в которой восстанавливается файл, во время операции восстановления находится в состоянии «вне сети».</span><span class="sxs-lookup"><span data-stu-id="f073c-114">However, each filegroup in which a file is being restored is offline during the restore operation.</span></span> <span data-ttu-id="f073c-115">После восстановления всех файлов, входящих в файловую группу в режиме «вне сети», она автоматически переключается в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="f073c-115">After all the files in an offline filegroup are recovered, the filegroup is automatically brought online.</span></span>  
  
     <span data-ttu-id="f073c-116">Дополнительные сведения о поддержке оперативного восстановления страниц и файлов см. в разделе [Возможности, поддерживаемые различными выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="f073c-116">For information about support for online page and file restore, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="f073c-117">Дополнительные сведения об оперативном восстановлении см. в разделе [Оперативное восстановление (SQL Server)](online-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f073c-117">For more information about online restores, see [Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="f073c-118">Если желательно, чтобы база данных находилась в режиме "вне сети" для восстановления файлов, переведите ее в этот режим перед запуском последовательности восстановления, выполнив следующую инструкцию [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options): ALTER DATABASE *имя_базы_данных* SET OFFLINE.</span><span class="sxs-lookup"><span data-stu-id="f073c-118">If you want the database to be offline for a file restore, take the database offline before you start the restore sequence by executing the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement: ALTER DATABASE *database_name* SET OFFLINE.</span></span>  
  

  
##  <a name="overview-of-file-and-filegroup-restore-under-the-simple-recovery-model"></a><a name="Overview"></a> <span data-ttu-id="f073c-119">Общие сведения о восстановлении файлов и файловых групп в простой модели восстановления</span><span class="sxs-lookup"><span data-stu-id="f073c-119">Overview of File and Filegroup Restore Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="f073c-120">Сценарий восстановления файлов состоит из единой последовательности восстановления, в процессе которой производится копирование, накат транзакций и восстановление соответствующих данных.</span><span class="sxs-lookup"><span data-stu-id="f073c-120">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data as follows:</span></span>  
  
1.  <span data-ttu-id="f073c-121">Восстановите каждый поврежденный файл из последней резервной копии поврежденного файла.</span><span class="sxs-lookup"><span data-stu-id="f073c-121">Restore each damaged file from its most recent file backup.</span></span>  
  
2.  <span data-ttu-id="f073c-122">Восстановите базу данных и самую свежую разностную резервную копию файлов для каждого восстанавливаемого файла.</span><span class="sxs-lookup"><span data-stu-id="f073c-122">Restore the most recent differential file backup for each restored file and recover the database.</span></span>  
  
### <a name="transact-sql-steps-for-file-restore-sequence-simple-recovery-model"></a><span data-ttu-id="f073c-123">Шаги Transact-SQL для последовательности восстановления файлов (простая модель восстановления)</span><span class="sxs-lookup"><span data-stu-id="f073c-123">Transact-SQL Steps for File Restore Sequence (Simple Recovery Model)</span></span>  
 <span data-ttu-id="f073c-124">В этом разделе показаны основные параметры инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) для простой последовательности восстановления файлов.</span><span class="sxs-lookup"><span data-stu-id="f073c-124">This section shows the essential [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) options for a simple file-restore sequence.</span></span> <span data-ttu-id="f073c-125">Синтаксис и прочие подробности, несущественные для данной цели, опущены.</span><span class="sxs-lookup"><span data-stu-id="f073c-125">Syntax and details that are not relevant to this purpose are omitted.</span></span>  
  
 <span data-ttu-id="f073c-126">Последовательность восстановления содержит только две инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f073c-126">The restore sequence contains only two [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="f073c-127">Первая инструкция восстанавливает вторичный файл `A`, который восстанавливается с параметром WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="f073c-127">The first statement restores a secondary file, file `A`, which is restored using WITH NORECOVERY.</span></span> <span data-ttu-id="f073c-128">Вторая операция восстанавливает файлы `B` и `C` , которые восстанавливаются с другого устройства резервного копирования с параметром WITH RECOVERY:</span><span class="sxs-lookup"><span data-stu-id="f073c-128">The second operation restores two other files, `B` and `C` which are restored using WITH RECOVERY from a different backup device:</span></span>  
  
1.  <span data-ttu-id="f073c-129">RESTORE DATABASE *база_данных* FILE **=** _имя_файла_A_</span><span class="sxs-lookup"><span data-stu-id="f073c-129">RESTORE DATABASE *database* FILE **=**_name_of_file_A_</span></span>  
  
     <span data-ttu-id="f073c-130">FROM *резервная_копия_файла_A*</span><span class="sxs-lookup"><span data-stu-id="f073c-130">FROM *file_backup_of_file_A*</span></span>  
  
     <span data-ttu-id="f073c-131">WITH NORECOVERY **;**</span><span class="sxs-lookup"><span data-stu-id="f073c-131">WITH NORECOVERY **;**</span></span>  
  
2.  <span data-ttu-id="f073c-132">RESTORE DATABASE *база_данных* FILE **=** _имя_файла_Б_ **,** _имя_файла_В_</span><span class="sxs-lookup"><span data-stu-id="f073c-132">RESTORE DATABASE *database* FILE **=**_name_of_file_B_**,**_name_of_file_C_</span></span>  
  
     <span data-ttu-id="f073c-133">FROM *резервная_копия_файлов_Б_и_В*</span><span class="sxs-lookup"><span data-stu-id="f073c-133">FROM *file_backup_of_files_B_and_C*</span></span>  
  
     <span data-ttu-id="f073c-134">WITH RECOVERY **;**</span><span class="sxs-lookup"><span data-stu-id="f073c-134">WITH RECOVERY **;**</span></span>  
  
### <a name="examples"></a><span data-ttu-id="f073c-135">Примеры</span><span class="sxs-lookup"><span data-stu-id="f073c-135">Examples</span></span>  
  
-   [<span data-ttu-id="f073c-136">Пример. Оперативное восстановление доступного только для чтения файла &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="f073c-136">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="f073c-137">Пример. Автономное восстановление основной и еще одной файловой группы &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="f073c-137">Example: Offline Restore of Primary and One Other Filegroup &#40;Full Recovery Model&#41;</span></span>](example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model.md)  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f073c-138">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f073c-138">Related Tasks</span></span>  
 <span data-ttu-id="f073c-139">**Восстановление файлов и файловых групп**</span><span class="sxs-lookup"><span data-stu-id="f073c-139">**To restore files and filegroups**</span></span>  
  
-   [<span data-ttu-id="f073c-140">Восстановление файлов и файловых групп поверх существующих файлов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f073c-140">Restore Files and Filegroups over Existing Files &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-over-existing-files-sql-server.md)  
  
-   [<span data-ttu-id="f073c-141">Восстановление файлов и файловых групп (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f073c-141">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="f073c-142">Восстановление файлов и файловых групп (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f073c-142">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   <span data-ttu-id="f073c-143"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="f073c-143"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="f073c-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="f073c-144">See Also</span></span>  
 <span data-ttu-id="f073c-145">[Резервное копирование и восстановление: взаимодействие и совместимость &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f073c-145">[Backup and Restore: Interoperability and Coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="f073c-146">[Разностные резервные копии (SQL Server)](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f073c-146">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="f073c-147">[Полные резервные копии файлов (SQL Server)](full-file-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f073c-147">[Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span></span>  
 <span data-ttu-id="f073c-148">[Общие сведения о резервном копировании (SQL Server)](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f073c-148">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="f073c-149">[Обзор процессов восстановления (SQL Server)](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f073c-149">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="f073c-150">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f073c-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="f073c-151">[Выполнение полного восстановления базы данных (простая модель восстановления)](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="f073c-151">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="f073c-152">Поэтапное восстановление (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f073c-152">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
