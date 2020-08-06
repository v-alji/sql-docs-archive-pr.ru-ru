---
title: Устранение неполадок при переполнении журнала транзакций (ошибка SQL Server 9002) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], full
- troubleshooting [SQL Server], full transaction log
- 9002 (Database Engine error)
- transaction logs [SQL Server], truncation
- backing up transaction logs [SQL Server], full logs
- transaction logs [SQL Server], full log
- full transaction logs [SQL Server]
ms.assetid: 0f23aa84-475d-40df-bed3-c923f8c1b520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d03e259bd0aff8fce02558dbe08efb56748493c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655149"
---
# <a name="troubleshoot-a-full-transaction-log-sql-server-error-9002"></a><span data-ttu-id="cfce7-102">Устранение неполадок при переполнении журнала транзакций (ошибка SQL Server 9002)</span><span class="sxs-lookup"><span data-stu-id="cfce7-102">Troubleshoot a Full Transaction Log (SQL Server Error 9002)</span></span>
  <span data-ttu-id="cfce7-103">В этом разделе описаны возможные действия при переполнении журнала транзакций, а также советы о том, как его избежать.</span><span class="sxs-lookup"><span data-stu-id="cfce7-103">This topic discusses possible responses to a full transaction log and suggests how to avoid it in the future.</span></span> <span data-ttu-id="cfce7-104">Когда журнал транзакций переполняется, в компоненте [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] происходит ошибка 9002.</span><span class="sxs-lookup"><span data-stu-id="cfce7-104">When the transaction log becomes full, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] issues a 9002 error.</span></span> <span data-ttu-id="cfce7-105">Журнал может заполниться, когда база данных работает в режиме «в сети» или находится в процессе восстановления.</span><span class="sxs-lookup"><span data-stu-id="cfce7-105">The log can fill when the database is online or in recovery.</span></span> <span data-ttu-id="cfce7-106">Если журнал переполняется при подключенной базе данных, она не отключается, но переходит в режим только для чтения.</span><span class="sxs-lookup"><span data-stu-id="cfce7-106">If the log fills while the database is online, the database remains online but can only be read, not updated.</span></span> <span data-ttu-id="cfce7-107">Если журнал заполняется, когда база данных находится в процессе восстановления, компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] помечает базу данных как RESOURCE PENDING.</span><span class="sxs-lookup"><span data-stu-id="cfce7-107">If the log fills during recovery, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] marks the database as RESOURCE PENDING.</span></span> <span data-ttu-id="cfce7-108">В любом случае необходимо вмешательство пользователя, чтобы сделать журнал транзакций доступным.</span><span class="sxs-lookup"><span data-stu-id="cfce7-108">In either case, user action is required to make log space available.</span></span>  
  
## <a name="responding-to-a-full-transaction-log"></a><span data-ttu-id="cfce7-109">Действия при переполнении журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="cfce7-109">Responding to a Full Transaction Log</span></span>  
 <span data-ttu-id="cfce7-110">Ответные действия при переполнении журнала транзакций частично зависят от условий, которые вызвали переполнение журнала.</span><span class="sxs-lookup"><span data-stu-id="cfce7-110">The appropriate response to a full transaction log depends partly on what condition or conditions caused the log to fill.</span></span> <span data-ttu-id="cfce7-111">Чтобы определить, что препятствует усечению журнала транзакций в конкретном случае, используйте столбцы **log_reuse_wait** и **log_reuse_wait_desc** представления каталога **sys.database**.</span><span class="sxs-lookup"><span data-stu-id="cfce7-111">To discover what is preventing log truncation in a given case, use the **log_reuse_wait** and **log_reuse_wait_desc** columns of the **sys.database** catalog view.</span></span> <span data-ttu-id="cfce7-112">Дополнительные сведения см. в разделе [sys.databases (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cfce7-112">For more information, see [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span> <span data-ttu-id="cfce7-113">Описание причин, которые могут задержать усечение журнала, см. в разделе [Журнал транзакций (SQL Server)](the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cfce7-113">For descriptions of factors that can delay log truncation, see [The Transaction Log &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cfce7-114">Если при возникновении ошибки 9002 база данных находилась в состоянии восстановления, то после устранения проблемы восстановите базу данных с помощью инструкции ALTER DATABASE *имя_базы_данных* SET ONLINE.</span><span class="sxs-lookup"><span data-stu-id="cfce7-114">If the database was in recovery when the 9002 error occurred, after resolving the problem, recover the database by using ALTER DATABASE *database_name* SET ONLINE.</span></span>  
  
 <span data-ttu-id="cfce7-115">При переполнении журнала транзакций предусмотрены следующие ответные действия:</span><span class="sxs-lookup"><span data-stu-id="cfce7-115">Alternatives for responding to a full transaction log include:</span></span>  
  
-   <span data-ttu-id="cfce7-116">создание резервной копии журнала;</span><span class="sxs-lookup"><span data-stu-id="cfce7-116">Backing up the log.</span></span>  
  
-   <span data-ttu-id="cfce7-117">освобождение места на диске, чтобы журнал мог автоматически расти;</span><span class="sxs-lookup"><span data-stu-id="cfce7-117">Freeing disk space so that the log can automatically grow.</span></span>  
  
-   <span data-ttu-id="cfce7-118">перемещение файла журнала на диск с достаточным объемом свободного места;</span><span class="sxs-lookup"><span data-stu-id="cfce7-118">Moving the log file to a disk drive with sufficient space.</span></span>  
  
-   <span data-ttu-id="cfce7-119">увеличение размера файла журнала;</span><span class="sxs-lookup"><span data-stu-id="cfce7-119">Increasing the size of a log file.</span></span>  
  
-   <span data-ttu-id="cfce7-120">добавление файла журнала на другой диск;</span><span class="sxs-lookup"><span data-stu-id="cfce7-120">Adding a log file on a different disk.</span></span>  
  
-   <span data-ttu-id="cfce7-121">завершение или уничтожение длительной транзакции.</span><span class="sxs-lookup"><span data-stu-id="cfce7-121">Completing or killing a long-running transaction.</span></span>  
  
 <span data-ttu-id="cfce7-122">Эти возможности описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="cfce7-122">These alternatives are discussed in the following sections.</span></span> <span data-ttu-id="cfce7-123">Выберите ответное действие, наиболее подходящее в конкретной ситуации.</span><span class="sxs-lookup"><span data-stu-id="cfce7-123">Choose a response that fits your situation best.</span></span>  
  
### <a name="backing-up-the-log"></a><span data-ttu-id="cfce7-124">Создание резервной копии журнала</span><span class="sxs-lookup"><span data-stu-id="cfce7-124">Backing up the Log</span></span>  
 <span data-ttu-id="cfce7-125">Для полных моделей восстановления и моделей с неполным протоколированием резервное копирование может предотвратить усечение журнала транзакций, если оно не было сделано недавно.</span><span class="sxs-lookup"><span data-stu-id="cfce7-125">Under the full recovery model or bulk-logged recovery model, if the transaction log has not been backed up recently, backup might be what is preventing log truncation.</span></span> <span data-ttu-id="cfce7-126">Если резервная копия журнала создается в первый раз, необходимо сделать вторую резервную копию журнала, чтобы разрешить компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] усечение журнала до точки последнего резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="cfce7-126">If the log has never been backed up, you must create two log backups to permit the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to truncate the log to the point of the last backup.</span></span> <span data-ttu-id="cfce7-127">Усечение журнала освобождает пространство для новых записей журнала.</span><span class="sxs-lookup"><span data-stu-id="cfce7-127">Truncating the log frees space for new log records.</span></span> <span data-ttu-id="cfce7-128">Чтобы избежать повторного переполнения журнала, следует чаще выполнять резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="cfce7-128">To keep the log from filling up again, take log backups frequently.</span></span>  
  
 <span data-ttu-id="cfce7-129">**Создание резервной копии журнала транзакций**</span><span class="sxs-lookup"><span data-stu-id="cfce7-129">**To create a transaction log backup**</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cfce7-130">Если база данных повреждена, см. раздел [Резервные копии заключительного фрагмента журнала (SQL Server)](../backup-restore/tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cfce7-130">If the database is damaged, see [Tail-Log Backups &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="cfce7-131">Создание резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="cfce7-131">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-a-transaction-log-sql-server.md)  
  
-   <span data-ttu-id="cfce7-132"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="cfce7-132"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
### <a name="freeing-disk-space"></a><span data-ttu-id="cfce7-133">Освободите место на диске</span><span class="sxs-lookup"><span data-stu-id="cfce7-133">Freeing Disk Space</span></span>  
 <span data-ttu-id="cfce7-134">Возможно, следует освободить место на диске, где находится файл журнала транзакций для базы данных. Для этого можно удалить или переместить другие файлы.</span><span class="sxs-lookup"><span data-stu-id="cfce7-134">You might be able to free disk space on the disk drive that contains the transaction log file for the database by deleting or moving other files.</span></span> <span data-ttu-id="cfce7-135">Освобожденное место на диске позволит системе восстановления автоматически увеличить размер файла журнала.</span><span class="sxs-lookup"><span data-stu-id="cfce7-135">The freed disk space allows the recovery system to enlarge the log file automatically.</span></span>  
  
### <a name="moving-the-log-file-to-a-different-disk"></a><span data-ttu-id="cfce7-136">Перемещение файла журнала на другой диск</span><span class="sxs-lookup"><span data-stu-id="cfce7-136">Moving the Log File to a Different Disk</span></span>  
 <span data-ttu-id="cfce7-137">Если на текущем диске невозможно освободить достаточное количество места, следует переместить файл на другой диск, где места достаточно.</span><span class="sxs-lookup"><span data-stu-id="cfce7-137">If you cannot free enough disk space on the drive that currently contains the log file, consider moving the file to another drive with sufficient space.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cfce7-138">Файлы журнала ни в коем случае не следует размещать в файловых системах со сжатием.</span><span class="sxs-lookup"><span data-stu-id="cfce7-138">Log files should never be placed on compressed file systems.</span></span>  
  
 <span data-ttu-id="cfce7-139">**Перемещение файла журнала**</span><span class="sxs-lookup"><span data-stu-id="cfce7-139">**To move a log file**</span></span>  
  
-   [<span data-ttu-id="cfce7-140">Перемещение файлов базы данных</span><span class="sxs-lookup"><span data-stu-id="cfce7-140">Move Database Files</span></span>](../databases/move-database-files.md)  
  
### <a name="increasing-the-size-of-a-log-file"></a><span data-ttu-id="cfce7-141">Увеличение размера файла журнала</span><span class="sxs-lookup"><span data-stu-id="cfce7-141">Increasing the Size of a Log File</span></span>  
 <span data-ttu-id="cfce7-142">Если на диске, на котором находится журнал, доступно свободное место, можно увеличить размер файла журнала.</span><span class="sxs-lookup"><span data-stu-id="cfce7-142">If space is available on the log disk, you can increase the size of the log file.</span></span> <span data-ttu-id="cfce7-143">Максимальный объем файлов журнала составляет 2 терабайта (ТБ) на файл журнала.</span><span class="sxs-lookup"><span data-stu-id="cfce7-143">The maximum size for log files is two terabytes (TB) per log file.</span></span>  
  
 <span data-ttu-id="cfce7-144">**Увеличение размера файла**</span><span class="sxs-lookup"><span data-stu-id="cfce7-144">**To increase the file size**</span></span>  
  
 <span data-ttu-id="cfce7-145">Если автоувеличение отключено, база данных находится в режиме «в сети» и на диске достаточно свободного места, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="cfce7-145">If autogrow is disabled, the database is online, and sufficient space is available on the disk, either:</span></span>  
  
-   <span data-ttu-id="cfce7-146">Вручную увеличьте размер файла для получения одного шага роста размера файла.</span><span class="sxs-lookup"><span data-stu-id="cfce7-146">Manually increase the file size to produce a single growth increment.</span></span>  
  
-   <span data-ttu-id="cfce7-147">Включить свойство автоматического увеличения при помощи инструкции ALTER DATABASE, чтобы установить отличное от нуля значение шага роста для параметра FILEGROWTH.</span><span class="sxs-lookup"><span data-stu-id="cfce7-147">Turn on autogrow by using the ALTER DATABASE statement to set a non-zero growth increment for the FILEGROWTH option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfce7-148">В любом случае, если достигнут текущий предел размера файла, увеличьте значение MAXSIZE.</span><span class="sxs-lookup"><span data-stu-id="cfce7-148">In either case, if the current size limit has been reached, increase the MAXSIZE value.</span></span>  
  
### <a name="adding-a-log-file-on-a-different-disk"></a><span data-ttu-id="cfce7-149">Добавление файла журнала на другой диск</span><span class="sxs-lookup"><span data-stu-id="cfce7-149">Adding a Log File on a Different Disk</span></span>  
 <span data-ttu-id="cfce7-150">Добавьте новый файл журнала базы данных на другом диске, где достаточно места, с помощью инструкции ALTER DATABASE <имя_базы_данных> ADD LOG FILE.</span><span class="sxs-lookup"><span data-stu-id="cfce7-150">Add a new log file to the database on a different disk that has sufficient space by using ALTER DATABASE <database_name> ADD LOG FILE.</span></span>  
  
 <span data-ttu-id="cfce7-151">**Добавление файла журнала**</span><span class="sxs-lookup"><span data-stu-id="cfce7-151">**To add a log file**</span></span>  
  
-   [<span data-ttu-id="cfce7-152">Добавление файлов данных или журналов в базу данных</span><span class="sxs-lookup"><span data-stu-id="cfce7-152">Add Data or Log Files to a Database</span></span>](../databases/add-data-or-log-files-to-a-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="cfce7-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="cfce7-153">See Also</span></span>  
 <span data-ttu-id="cfce7-154">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfce7-154">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="cfce7-155">[Управление размером файла журнала транзакций](manage-the-size-of-the-transaction-log-file.md) </span><span class="sxs-lookup"><span data-stu-id="cfce7-155">[Manage the Size of the Transaction Log File](manage-the-size-of-the-transaction-log-file.md) </span></span>  
 <span data-ttu-id="cfce7-156">[Резервные копии журналов транзакций (SQL Server)](../backup-restore/transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cfce7-156">[Transaction Log Backups &#40;SQL Server&#41;](../backup-restore/transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="cfce7-157">sp_add_log_file_recover_suspect_db (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cfce7-157">sp_add_log_file_recover_suspect_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-log-file-recover-suspect-db-transact-sql)  
  
  
