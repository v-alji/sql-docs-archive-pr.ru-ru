---
title: Журнал резервных копий и сведения о заголовке резервной копии (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup headers [SQL Server]
- history tables [SQL Server]
- file restores [SQL Server], status information
- backup sets [SQL Server], status information
- listing backed up databases
- status information [SQL Server], backups
- backing up [SQL Server], viewing backup sets
- restoring [SQL Server], history tables
- restoring databases [SQL Server], status information
- backups [SQL Server], status information
- headers [SQL Server]
- media headers [SQL Server]
- backup history tables [SQL Server]
- viewing backup information
- restoring files [SQL Server], viewing backup information
- restoring databases [SQL Server], history tables
- displaying backup information
- restoring files [SQL Server], status information
- historical information [SQL Server], backups
- database restores [SQL Server], history tables
- restore history tables [SQL Server]
- listing backed up files
ms.assetid: 799b9934-0ec2-4f43-960b-5c9653f18374
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ff1e75cc88e51de75af32bcd9d48860be52d5861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752220"
---
# <a name="backup-history-and-header-information-sql-server"></a><span data-ttu-id="42d08-102">Журнал и сведения о заголовке резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42d08-102">Backup History and Header Information (SQL Server)</span></span>
  <span data-ttu-id="42d08-103">Полный журнал резервных копий и операций восстановления на экземпляре сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] хранится в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="42d08-103">A complete history of all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore operations on a server instance is stored in the **msdb** database.</span></span> <span data-ttu-id="42d08-104">В этом разделе рассказывается о таблицах журнала восстановления, а также об инструкциях [!INCLUDE[tsql](../../includes/tsql-md.md)] , которые используются для доступа к журналам резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="42d08-104">This topic introduces the backup and restore history tables and also the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are used to access backup history.</span></span> <span data-ttu-id="42d08-105">В этом разделе также обсуждается удобство составления списка файлов базы данных и журнала транзакций и использование данных в заголовке носителя в сравнении с использованием данных в заголовке резервной копии.</span><span class="sxs-lookup"><span data-stu-id="42d08-105">The topic also discusses when listing database and transaction log files is useful and when to use media-header information compared to when to use backup-header information.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="42d08-106">Чтобы снизить риск потери недавних изменений, следует чаще создавать резервные копии базы данных **msdb** и журнала.</span><span class="sxs-lookup"><span data-stu-id="42d08-106">To manage the risk of losing recent changes to your backup and restore history, back up **msdb** frequently.</span></span> <span data-ttu-id="42d08-107">Сведения о том, резервную копию какой системной базы данных нужно создать, см. в разделе [Резервное копирование и восстановление системных баз данных (SQL Server)](back-up-and-restore-of-system-databases-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="42d08-107">For information about which of the system databases you must back up, see [Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md).</span></span>  
  
 <span data-ttu-id="42d08-108">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="42d08-108">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="42d08-109">Таблицы журналов резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="42d08-109">Backup and Restore History Tables</span></span>](#BnRHistoryTables)  
  
-   [<span data-ttu-id="42d08-110">Инструкции Transact-SQL для доступа к журналу резервного копирования</span><span class="sxs-lookup"><span data-stu-id="42d08-110">Transact-SQL Statements for Accessing Backup History</span></span>](#TsqlStatementsForBackupHistory)  
  
-   [<span data-ttu-id="42d08-111">Файлы базы данных и журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="42d08-111">Database and Transaction Log Files</span></span>](#ListDbTlogFiles)  
  
-   [<span data-ttu-id="42d08-112">Данные в заголовке носителя</span><span class="sxs-lookup"><span data-stu-id="42d08-112">Media-Header Information</span></span>](#MediaHeader)  
  
-   [<span data-ttu-id="42d08-113">Данные в заголовке резервной копии</span><span class="sxs-lookup"><span data-stu-id="42d08-113">Backup-Header Information</span></span>](#BackupHeader)  
  
-   [<span data-ttu-id="42d08-114">Сравнение данных в заголовке носителя и в заголовке резервной копии</span><span class="sxs-lookup"><span data-stu-id="42d08-114">Comparison of Media-Header and Backup-Header Information</span></span>](#CompareMediaHeaderBackupHeader)  
  
-   [<span data-ttu-id="42d08-115">Проверки резервных копий</span><span class="sxs-lookup"><span data-stu-id="42d08-115">Backup Verification</span></span>](#Verification)  
  
-   [<span data-ttu-id="42d08-116">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="42d08-116">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="backup-and-restore-history-tables"></a><a name="BnRHistoryTables"></a> <span data-ttu-id="42d08-117">Таблицы журналов резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="42d08-117">Backup and Restore History Tables</span></span>  
 <span data-ttu-id="42d08-118">В этом разделе рассказывается о журнальных таблицах, в которых в системной базе данных **msdb** хранятся метаданные резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="42d08-118">This section introduces the history tables that store backup and restore metadata in the **msdb** system database.</span></span>  
  
|<span data-ttu-id="42d08-119">Таблица журнала</span><span class="sxs-lookup"><span data-stu-id="42d08-119">History table</span></span>|<span data-ttu-id="42d08-120">Описание</span><span class="sxs-lookup"><span data-stu-id="42d08-120">Description</span></span>|  
|-------------------|-----------------|  
|[<span data-ttu-id="42d08-121">backupfile;</span><span class="sxs-lookup"><span data-stu-id="42d08-121">backupfile</span></span>](/sql/relational-databases/system-tables/backupfile-transact-sql)|<span data-ttu-id="42d08-122">Содержит по одной строке для каждого файла данных или журнала, подвергаемого резервному копированию.</span><span class="sxs-lookup"><span data-stu-id="42d08-122">Contains one row for each data or log file that is backed up.</span></span>|  
|[<span data-ttu-id="42d08-123">backupfilegroup</span><span class="sxs-lookup"><span data-stu-id="42d08-123">backupfilegroup</span></span>](/sql/relational-databases/system-tables/backupfilegroup-transact-sql)|<span data-ttu-id="42d08-124">Содержит по одной строке для каждой файловой группы в резервном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="42d08-124">Contains a row for each filegroup in a backup set.</span></span>|  
|[<span data-ttu-id="42d08-125">backupmediafamily;</span><span class="sxs-lookup"><span data-stu-id="42d08-125">backupmediafamily</span></span>](/sql/relational-databases/system-tables/backupmediafamily-transact-sql)|<span data-ttu-id="42d08-126">Содержит по одной строке для каждого семейства носителей.</span><span class="sxs-lookup"><span data-stu-id="42d08-126">Contains one row for each media family.</span></span> <span data-ttu-id="42d08-127">Если семейство носителей хранится на зеркальном наборе носителей, семейство имеет отдельную строку для каждого зеркала в наборе носителей.</span><span class="sxs-lookup"><span data-stu-id="42d08-127">If a media family resides in a mirrored media set, the family has a separate row for each mirror in the media set.</span></span>|  
|[<span data-ttu-id="42d08-128">backupmediaset;</span><span class="sxs-lookup"><span data-stu-id="42d08-128">backupmediaset</span></span>](/sql/relational-databases/system-tables/backupmediaset-transact-sql)|<span data-ttu-id="42d08-129">Содержит по одной строке для каждого резервного набора носителей.</span><span class="sxs-lookup"><span data-stu-id="42d08-129">Contains one row for each backup media set.</span></span>|  
|[<span data-ttu-id="42d08-130">backupset;</span><span class="sxs-lookup"><span data-stu-id="42d08-130">backupset</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)|<span data-ttu-id="42d08-131">Содержит по одной строке для каждого резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="42d08-131">Contains a row for each backup set.</span></span>|  
|[<span data-ttu-id="42d08-132">restorefile;</span><span class="sxs-lookup"><span data-stu-id="42d08-132">restorefile</span></span>](/sql/relational-databases/system-tables/restorefile-transact-sql)|<span data-ttu-id="42d08-133">Содержит по одной строке для каждого восстановленного файла.</span><span class="sxs-lookup"><span data-stu-id="42d08-133">Contains one row for each restored file.</span></span> <span data-ttu-id="42d08-134">Это файлы, восстановленные неявно по имени файловой группы.</span><span class="sxs-lookup"><span data-stu-id="42d08-134">This includes files restored indirectly by filegroup name.</span></span>|  
|[<span data-ttu-id="42d08-135">restorefilegroup;</span><span class="sxs-lookup"><span data-stu-id="42d08-135">restorefilegroup</span></span>](/sql/relational-databases/system-tables/restorefilegroup-transact-sql)|<span data-ttu-id="42d08-136">Содержит по одной строке для каждой восстановленной файловой группы.</span><span class="sxs-lookup"><span data-stu-id="42d08-136">Contains one row for each restored filegroup.</span></span>|  
|[<span data-ttu-id="42d08-137">restorehistory.</span><span class="sxs-lookup"><span data-stu-id="42d08-137">restorehistory</span></span>](/sql/relational-databases/system-tables/restorehistory-transact-sql)|<span data-ttu-id="42d08-138">Содержит по одной строке для каждой операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="42d08-138">Contains one row for each restore operation.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="42d08-139">При восстановлении изменяются таблицы журналов резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="42d08-139">When a restore is performed, backup history tables and restore history tables are modified.</span></span>  
  
##  <a name="transact-sql-statements-for-accessing-backup-history"></a><a name="TsqlStatementsForBackupHistory"></a> <span data-ttu-id="42d08-140">Инструкции Transact-SQL для доступа к журналу резервного копирования</span><span class="sxs-lookup"><span data-stu-id="42d08-140">Transact-SQL Statements for Accessing Backup History</span></span>  
 <span data-ttu-id="42d08-141">Инструкции восстановления данных соответствуют сведениям, сохраненным в некоторых таблицах журналов резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="42d08-141">The restore information statements correspond with information stored in certain backup history tables.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="42d08-142">Инструкциям Transact-SQL RESTORE FILELISTONLY, RESTORE HEADERONLY, RESTORE LABELONLY и RESTORE VERIFYONLY требуется разрешение CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="42d08-142">The RESTORE FILELISTONLY, RESTORE HEADERONLY, RESTORE LABELONLY, and RESTORE VERIFYONLY Transact-SQL statements require CREATE DATABASE permission.</span></span> <span data-ttu-id="42d08-143">Тем самым обеспечивается более надежная защита файлов резервных копий и данных, чем в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="42d08-143">This requirement secures your backup files and protects your backup information more fully than in previous versions.</span></span> <span data-ttu-id="42d08-144">Дополнительные сведения об этом разрешении см. в разделе[ Разрешения базы данных GRANT (Transact-SQL)](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="42d08-144">For information about this permission, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
|<span data-ttu-id="42d08-145">Информационная инструкция</span><span class="sxs-lookup"><span data-stu-id="42d08-145">Information statement</span></span>|<span data-ttu-id="42d08-146">Таблица журнала резервного копирования</span><span class="sxs-lookup"><span data-stu-id="42d08-146">Backup history table</span></span>|<span data-ttu-id="42d08-147">Описание</span><span class="sxs-lookup"><span data-stu-id="42d08-147">Description</span></span>|  
|---------------------------|--------------------------|-----------------|  
|[<span data-ttu-id="42d08-148">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="42d08-148">RESTORE FILELISTONLY</span></span>](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)|[<span data-ttu-id="42d08-149">backupfile;</span><span class="sxs-lookup"><span data-stu-id="42d08-149">backupfile</span></span>](/sql/relational-databases/system-tables/backupfile-transact-sql)|<span data-ttu-id="42d08-150">Возвращает результирующий набор со списком файлов базы данных и журнала, которые содержит указанный резервный набор данных.</span><span class="sxs-lookup"><span data-stu-id="42d08-150">Returns a result set that has a list of the database and log files that are contained in the specified backup set.</span></span><br /><br /> <span data-ttu-id="42d08-151">Дополнительные сведения см. далее в разделе «Составление списка файлов базы данных и журналов транзакций».</span><span class="sxs-lookup"><span data-stu-id="42d08-151">For more information, see "Listing Database and Transaction Log Files," later in this topic.</span></span>|  
|[<span data-ttu-id="42d08-152">инструкция RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="42d08-152">RESTORE HEADERONLY</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)|[<span data-ttu-id="42d08-153">backupset;</span><span class="sxs-lookup"><span data-stu-id="42d08-153">backupset</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)|<span data-ttu-id="42d08-154">Извлекает все данные заголовка резервной копии для всех резервных наборов данных в определенном устройстве резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="42d08-154">Retrieves all the backup header information for all backup sets on a particular backup device.</span></span> <span data-ttu-id="42d08-155">Результатом выполнения RESTORE HEADERONLY является результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="42d08-155">The result from executing RESTORE HEADERONLY is a result set.</span></span><br /><br /> <span data-ttu-id="42d08-156">Дополнительные сведения см. далее в разделе «Просмотр данных заголовка резервной копии».</span><span class="sxs-lookup"><span data-stu-id="42d08-156">For more information, see "Viewing the Backup-Header Information," later in this topic.</span></span>|  
|[<span data-ttu-id="42d08-157">RESTORE LABELONLY</span><span class="sxs-lookup"><span data-stu-id="42d08-157">RESTORE LABELONLY</span></span>](/sql/t-sql/statements/restore-statements-labelonly-transact-sql)|[<span data-ttu-id="42d08-158">backupmediaset;</span><span class="sxs-lookup"><span data-stu-id="42d08-158">backupmediaset</span></span>](/sql/relational-databases/system-tables/backupmediaset-transact-sql)|<span data-ttu-id="42d08-159">Возвращает результирующий набор, который содержит сведения о резервном носителе в указанном устройстве резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="42d08-159">Returns a result set that contains information about the backup media on a specified backup device.</span></span><br /><br /> <span data-ttu-id="42d08-160">Дополнительные сведения см. далее в разделе «Просмотр данных заголовка носителя».</span><span class="sxs-lookup"><span data-stu-id="42d08-160">For more information, see "Viewing the Media-Header Information," later in this topic.</span></span>|  
  
##  <a name="database-and-transaction-log-files"></a><a name="ListDbTlogFiles"></a> <span data-ttu-id="42d08-161">Файлы базы данных и журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="42d08-161">Database and Transaction Log Files</span></span>  
 <span data-ttu-id="42d08-162">При подготовке списка файлов базы данных и журнала транзакций в резервной копии отображаются сведения о логическом имени, физическом имени, типе файла (база данных или журнал), членстве в файловой группе, размере файла (в байтах), максимально допустимом размере файла и заранее заданный рост файла (в байтах).</span><span class="sxs-lookup"><span data-stu-id="42d08-162">Information that is displayed when the database and transaction log files are listed in a backup includes the logical name, physical name, file type (database or log), filegroup membership, file size (in bytes), the maximum allowed file size, and the predefined file growth size (in bytes).</span></span> <span data-ttu-id="42d08-163">Эти сведения позволяют в следующих ситуациях определять имена файлов в резервной копии базы данных перед восстановлением.</span><span class="sxs-lookup"><span data-stu-id="42d08-163">This information is useful, in the following situations, to determine the names of the files in a database backup before you restore the database backup:</span></span>  
  
-   <span data-ttu-id="42d08-164">Был утрачен дисковый накопитель, который содержал один или несколько файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="42d08-164">You have lost a disk drive that contains one or more of the files for a database.</span></span>  
  
     <span data-ttu-id="42d08-165">По списку файлов в резервной копии базы данных можно определить затронутые файлы, затем восстановить эти файлы на другом диске при восстановлении всей базы данных или восстановить только эти файлы и применить любые резервные копии журналов транзакций, созданные со времени резервного копирования базы данных.</span><span class="sxs-lookup"><span data-stu-id="42d08-165">You can list the files in the database backup to determine which files were affected, and then restore those files onto a different drive when you restore the whole database; or restore just those files and apply any transaction log backups created since the database was backed up.</span></span>  
  
-   <span data-ttu-id="42d08-166">База данных из одного сервера восстанавливается на другом сервере, но на сервере отсутствуют структура каталогов и сопоставление носителей.</span><span class="sxs-lookup"><span data-stu-id="42d08-166">You are restoring a database from one server onto another server, but the directory structure and drive mapping does not exist on the server.</span></span>  
  
     <span data-ttu-id="42d08-167">Составление списка файлов в резервной копии позволяет определить затронутые файлы.</span><span class="sxs-lookup"><span data-stu-id="42d08-167">Listing the files in the backup let you determine which files are affected.</span></span> <span data-ttu-id="42d08-168">Например, резервная копия содержит файл, который нужно восстановить на диск E:, но на целевом сервере диск E: отсутствует. При восстановлении этот файл необходимо перенести в другое расположение, например на диск Z:.</span><span class="sxs-lookup"><span data-stu-id="42d08-168">For example, the backup contains a file that it has to restore to drive E, but the destination server does not have a drive E. The file must be relocated to another location, such as drive Z, when the file is restored.</span></span>  
  
##  <a name="media-header-information"></a><a name="MediaHeader"></a> <span data-ttu-id="42d08-169">Данные в заголовке носителя</span><span class="sxs-lookup"><span data-stu-id="42d08-169">Media-Header Information</span></span>  
 <span data-ttu-id="42d08-170">При просмотре данных в заголовке носителя отображаются сведения о самом носителе, а не о резервных копиях на нем.</span><span class="sxs-lookup"><span data-stu-id="42d08-170">Viewing the media header displays information about the media itself, instead of about the backups on the media.</span></span> <span data-ttu-id="42d08-171">К отображаемым сведениям из заголовка носителя относятся имя носителя, описание, имя программы, с помощью которой был создан заголовок носителя, а также дата записи заголовка носителя.</span><span class="sxs-lookup"><span data-stu-id="42d08-171">Media header information that is displayed includes the media name, description, name of the software that created the media header, and the date the media header was written.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42d08-172">Просмотр данных в заголовке носителя занимает мало времени.</span><span class="sxs-lookup"><span data-stu-id="42d08-172">Viewing the media header is quick.</span></span>  
  
 <span data-ttu-id="42d08-173">Дополнительные сведения см. далее в подразделе [Сравнение данных в заголовках носителя и резервной копии](#CompareMediaHeaderBackupHeader)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="42d08-173">For more information, see [Comparison of Media-Header and Backup-Header Information](#CompareMediaHeaderBackupHeader), later in this topic.</span></span>  
  
##  <a name="backup-header-information"></a><a name="BackupHeader"></a> <span data-ttu-id="42d08-174">Данные в заголовке резервной копии</span><span class="sxs-lookup"><span data-stu-id="42d08-174">Backup-Header Information</span></span>  
 <span data-ttu-id="42d08-175">В заголовке резервной копии отображаются сведения обо всех резервных наборах данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и отличных от[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на носителях.</span><span class="sxs-lookup"><span data-stu-id="42d08-175">Viewing the backup header displays information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup sets on the media.</span></span> <span data-ttu-id="42d08-176">К отображаемым сведениям относятся типы применяемых устройств резервного копирования, типы резервных копий (например: копия базы данных, транзакции, файла или разностная копия базы данных), дата-время начала и конца резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="42d08-176">Information that is displayed includes the types of backup devices that are used, the types of backup (for example, database, transaction, file, or differential database), and backup start and stop date/time information.</span></span> <span data-ttu-id="42d08-177">С помощью этих сведений можно определить, какой резервный набор данных на ленте подлежит восстановлению или какие резервные копии находятся на носителе.</span><span class="sxs-lookup"><span data-stu-id="42d08-177">This information is useful when you have to determine which backup set on the tape to restore, or the backups that are contained on the media.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42d08-178">Просмотр данных в заголовке носителя для магнитных лент большой емкости может занимать длительное время, так как для отображения информации обо всех резервных копиях на носителе необходимо просмотреть весь носитель.</span><span class="sxs-lookup"><span data-stu-id="42d08-178">Viewing backup header information can take a long time for high-capacity tapes, because the whole media must be scanned to display information about each backup on the media.</span></span>  
  
 <span data-ttu-id="42d08-179">Дополнительные сведения см. далее в подразделе [Сравнение данных в заголовках носителя и резервной копии](#CompareMediaHeaderBackupHeader)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="42d08-179">For more information, see [Comparison of Media-Header and Backup-Header Information](#CompareMediaHeaderBackupHeader), later in this topic.</span></span>  
  
### <a name="which-backup-set-to-restore"></a><span data-ttu-id="42d08-180">Резервные наборы, которые необходимо восстановить</span><span class="sxs-lookup"><span data-stu-id="42d08-180">Which Backup Set to Restore</span></span>  
 <span data-ttu-id="42d08-181">Сведения из заголовка резервной копии можно использовать для определения резервного набора данных, который будет использован в процессе восстановления.</span><span class="sxs-lookup"><span data-stu-id="42d08-181">You can use information in the backup header to identify which backup set to restore.</span></span> <span data-ttu-id="42d08-182">Компонент Database Engine нумерует каждый резервный набор данных на резервном носителе.</span><span class="sxs-lookup"><span data-stu-id="42d08-182">The Database Engine numbers each backup set on the backup media.</span></span> <span data-ttu-id="42d08-183">Это позволяет выявить резервный набор данных, подлежащий восстановлению, по его положению на носителе.</span><span class="sxs-lookup"><span data-stu-id="42d08-183">This lets you identify the backup set you want to restore by using its position on the media.</span></span> <span data-ttu-id="42d08-184">Например, на следующем носителе содержатся три резервных набора данных.</span><span class="sxs-lookup"><span data-stu-id="42d08-184">For example, the following media contains three backup sets.</span></span>  
  
 <span data-ttu-id="42d08-185">![Носитель данных резервных копий, содержащий резервные наборы данных SQL Server](../../database-engine/media/bnr-media-backup-sets.gif "Носитель данных резервных копий, содержащий резервные наборы данных SQL Server")</span><span class="sxs-lookup"><span data-stu-id="42d08-185">![Backup media containing SQL Server backup sets](../../database-engine/media/bnr-media-backup-sets.gif "Backup media containing SQL Server backup sets")</span></span>  
  
 <span data-ttu-id="42d08-186">Чтобы восстановить определенный резервный набор данных, укажите номер позиции резервного набора данных, который нужно восстановить.</span><span class="sxs-lookup"><span data-stu-id="42d08-186">To restore a specific backup set, specify the position number of the backup set you want to restore.</span></span> <span data-ttu-id="42d08-187">Например, чтобы восстановить второй резервный набор данных, следует указать «2» в качестве номера резервного набора данных, подлежащего восстановлению.</span><span class="sxs-lookup"><span data-stu-id="42d08-187">For example, to restore the second backup set, specify 2 as the backup set to restore.</span></span>  
  
##  <a name="comparison-of-media-header-and-backup-header-information"></a><a name="CompareMediaHeaderBackupHeader"></a> <span data-ttu-id="42d08-188">Сравнение данных в заголовке носителя и в заголовке резервной копии</span><span class="sxs-lookup"><span data-stu-id="42d08-188">Comparison of Media-Header and Backup-Header Information</span></span>  
 <span data-ttu-id="42d08-189">На следующем рисунке показано отличие между просмотром данных в заголовке носителя и просмотром данных в заголовке резервной копии.</span><span class="sxs-lookup"><span data-stu-id="42d08-189">The following illustration provides an example of the differences between viewing backup-header and media-header information.</span></span> <span data-ttu-id="42d08-190">Получение заголовка носителя требует извлечения данных только с начала ленты.</span><span class="sxs-lookup"><span data-stu-id="42d08-190">Obtaining the media header requires retrieving information from only the start of the tape.</span></span> <span data-ttu-id="42d08-191">Получение заголовка резервной копии требует просмотра всей ленты в поисках заголовков всех резервных наборов данных.</span><span class="sxs-lookup"><span data-stu-id="42d08-191">Obtaining the backup header requires scanning the whole tape to look at the header of every backup set.</span></span>  
  
 <span data-ttu-id="42d08-192">![Набор носителей с тремя наборами резервных копий баз данных SQL Server](../../database-engine/media/bnr-media-label.gif "Набор носителей с тремя наборами резервных копий баз данных SQL Server")</span><span class="sxs-lookup"><span data-stu-id="42d08-192">![Media set containing three SQL Server backup sets](../../database-engine/media/bnr-media-label.gif "Media set containing three SQL Server backup sets")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42d08-193">При использовании наборов носителей с несколькими семействами носителей заголовок носителя и резервный набор данных записываются на все семейства носителей.</span><span class="sxs-lookup"><span data-stu-id="42d08-193">When you use media sets that have multiple media families, the media header and backup set are written to all media families.</span></span> <span data-ttu-id="42d08-194">Поэтому для этих учетных операций необходимо указать лишь одно семейство носителей.</span><span class="sxs-lookup"><span data-stu-id="42d08-194">Therefore, you only have to provide a single media family for these reporting operations.</span></span>  
  
 <span data-ttu-id="42d08-195">Дополнительные сведения о просмотре заголовка носителя см. выше в разделе «Просмотр данных заголовка носителя».</span><span class="sxs-lookup"><span data-stu-id="42d08-195">For information about how to view the media-header, see "Viewing the Media-Header Information," earlier in this topic.</span></span>  
  
 <span data-ttu-id="42d08-196">Дополнительные сведения о просмотре заголовка резервной копии для всех резервных наборов данных на устройстве резервного копирования см. далее в разделе «Просмотр данных заголовка резервной копии».</span><span class="sxs-lookup"><span data-stu-id="42d08-196">For information about how to view the backup header information for all backup sets on a backup device, see "Viewing the Backup-Header Information," earlier in this topic.</span></span>  
  
##  <a name="backup-verification"></a><a name="Verification"></a> <span data-ttu-id="42d08-197">Проверки резервных копий</span><span class="sxs-lookup"><span data-stu-id="42d08-197">Backup Verification</span></span>  
 <span data-ttu-id="42d08-198">Проверка резервных копий хотя и не обязательна, но полезна.</span><span class="sxs-lookup"><span data-stu-id="42d08-198">Although not required, verifying a backup is a useful practice.</span></span> <span data-ttu-id="42d08-199">С помощью проверки резервной копии можно проконтролировать ее физическую доступность, убедиться в том, что все файлы резервной копии могут быть прочитаны и восстановлены, и в том, что резервную копию можно восстановить в любой момент, когда это понадобится.</span><span class="sxs-lookup"><span data-stu-id="42d08-199">Verifying a backup checks that the backup is intact physically, to ensure that all the files in the backup are readable and can be restored, and that you can restore your backup in the event you need to use it.</span></span> <span data-ttu-id="42d08-200">Важно понимать, что проверка резервной копии не является проверкой структуры данных в данной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="42d08-200">It is important to understand that verifying a backup does not verify the structure of the data on the backup.</span></span> <span data-ttu-id="42d08-201">Однако если резервная копия была создана с использованием предложения WITH CHECKSUMS, проверка резервной копии с использованием предложения WITH CHECKSUMS может также дать полное представление о надежности данных в данной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="42d08-201">However, if the backup was created using WITH CHECKSUMS, verifying the backup using WITH CHECKSUMS can provide a good indication of the reliability of the data on the backup.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="42d08-202">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="42d08-202">Related Tasks</span></span>  
 <span data-ttu-id="42d08-203">**Удаление старых строк из таблиц журналов резервного копирования и восстановления**</span><span class="sxs-lookup"><span data-stu-id="42d08-203">**To delete old rows from backup and restore history tables**</span></span>  
  
-   [<span data-ttu-id="42d08-204">sp_delete_backuphistory (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42d08-204">sp_delete_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql)  
  
 <span data-ttu-id="42d08-205">**Удаление всех строк для заданной базы данных из таблиц журналов резервного копирования и восстановления**</span><span class="sxs-lookup"><span data-stu-id="42d08-205">**To delete all rows for a specific database from backup and restore history tables**</span></span>  
  
-   [<span data-ttu-id="42d08-206">sp_delete_database_backuphistory (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42d08-206">sp_delete_database_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-database-backuphistory-transact-sql)  
  
 <span data-ttu-id="42d08-207">**Просмотр файлов данных и журналов в резервном наборе данных**</span><span class="sxs-lookup"><span data-stu-id="42d08-207">**To view the data and log files in a backup set**</span></span>  
  
-   [<span data-ttu-id="42d08-208">RESTORE FILELISTONLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42d08-208">RESTORE FILELISTONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)  
  
-   <span data-ttu-id="42d08-209"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadFileList%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="42d08-209"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadFileList%2A> (SMO)</span></span>  
  
 <span data-ttu-id="42d08-210">**Просмотр данных в заголовке носителя**</span><span class="sxs-lookup"><span data-stu-id="42d08-210">**To view media header information**</span></span>  
  
-   [<span data-ttu-id="42d08-211">RESTORE LABELONLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42d08-211">RESTORE LABELONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-labelonly-transact-sql)  
  
-   [<span data-ttu-id="42d08-212">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42d08-212">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="42d08-213">Просмотр содержимого ленты или файла резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42d08-213">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   <span data-ttu-id="42d08-214"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadMediaHeader%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="42d08-214"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadMediaHeader%2A> (SMO)</span></span>  
  
 <span data-ttu-id="42d08-215">**Просмотр данных в заголовке резервной копии**</span><span class="sxs-lookup"><span data-stu-id="42d08-215">**To view backup header information**</span></span>  
  
-   [<span data-ttu-id="42d08-216">RESTORE HEADERONLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42d08-216">RESTORE HEADERONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
-   [<span data-ttu-id="42d08-217">Просмотр содержимого ленты или файла резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42d08-217">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="42d08-218">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42d08-218">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   <span data-ttu-id="42d08-219"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadBackupHeader%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="42d08-219"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadBackupHeader%2A> (SMO)</span></span>  
  
 <span data-ttu-id="42d08-220">**Удаление старых строк из таблиц журналов резервного копирования и восстановления**</span><span class="sxs-lookup"><span data-stu-id="42d08-220">**To delete old rows from backup and restore history tables**</span></span>  
  
-   [<span data-ttu-id="42d08-221">sp_delete_backuphistory (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42d08-221">sp_delete_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql)  
  
 <span data-ttu-id="42d08-222">**Удаление всех строк для заданной базы данных из таблиц журналов резервного копирования и восстановления**</span><span class="sxs-lookup"><span data-stu-id="42d08-222">**To delete all rows for a specific database from backup and restore history tables**</span></span>  
  
-   [<span data-ttu-id="42d08-223">sp_delete_database_backuphistory (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42d08-223">sp_delete_database_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-database-backuphistory-transact-sql)  
  
 <span data-ttu-id="42d08-224">**Просмотр данных в заголовке носителя**</span><span class="sxs-lookup"><span data-stu-id="42d08-224">**To view media header information**</span></span>  
  
-   [<span data-ttu-id="42d08-225">RESTORE LABELONLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42d08-225">RESTORE LABELONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-labelonly-transact-sql)  
  
-   [<span data-ttu-id="42d08-226">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42d08-226">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="42d08-227">Просмотр содержимого ленты или файла резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42d08-227">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   <span data-ttu-id="42d08-228"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadMediaHeader%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="42d08-228"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadMediaHeader%2A> (SMO)</span></span>  
  
 <span data-ttu-id="42d08-229">**Просмотр данных в заголовке резервной копии**</span><span class="sxs-lookup"><span data-stu-id="42d08-229">**To view backup header information**</span></span>  
  
-   [<span data-ttu-id="42d08-230">RESTORE HEADERONLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42d08-230">RESTORE HEADERONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
-   [<span data-ttu-id="42d08-231">Просмотр содержимого ленты или файла резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42d08-231">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="42d08-232">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42d08-232">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   <span data-ttu-id="42d08-233"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadBackupHeader%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="42d08-233"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadBackupHeader%2A> (SMO)</span></span>  
  
 <span data-ttu-id="42d08-234">**Просмотр файлов в резервном наборе данных**</span><span class="sxs-lookup"><span data-stu-id="42d08-234">**To view the files in a backup set**</span></span>  
  
-   [<span data-ttu-id="42d08-235">Просмотр файлов данных и журналов в резервном наборе данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42d08-235">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="42d08-236">RESTORE HEADERONLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42d08-236">RESTORE HEADERONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
 <span data-ttu-id="42d08-237">**Проверка резервной копии**</span><span class="sxs-lookup"><span data-stu-id="42d08-237">**To verify a backup**</span></span>  
  
-   [<span data-ttu-id="42d08-238">RESTORE VERIFYONLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42d08-238">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql)  
  
-   <span data-ttu-id="42d08-239"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlVerify%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="42d08-239"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlVerify%2A> (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42d08-240">См. также:</span><span class="sxs-lookup"><span data-stu-id="42d08-240">See Also</span></span>  
 <span data-ttu-id="42d08-241">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="42d08-241">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="42d08-242">[Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)](media-sets-media-families-and-backup-sets-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="42d08-242">[Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span></span>  
 <span data-ttu-id="42d08-243">[Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="42d08-243">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="42d08-244">[Зеркальные наборы носителей резервных копий (SQL Server)](mirrored-backup-media-sets-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="42d08-244">[Mirrored Backup Media Sets &#40;SQL Server&#41;](mirrored-backup-media-sets-sql-server.md) </span></span>  
 [<span data-ttu-id="42d08-245">Возможные ошибки носителей во время резервного копирования и восстановления (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42d08-245">Possible Media Errors During Backup and Restore &#40;SQL Server&#41;</span></span>](possible-media-errors-during-backup-and-restore-sql-server.md)  
  
  
