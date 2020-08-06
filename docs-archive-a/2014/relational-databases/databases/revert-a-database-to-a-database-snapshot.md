---
title: Восстановление базы данных из моментального снимка | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], reverting to
- reverting databases
ms.assetid: 8f74dd31-c9ca-4537-8760-0c7648f0787d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1c78da3d7c559309c0563760e7062f01cf784648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658806"
---
# <a name="revert-a-database-to-a-database-snapshot"></a><span data-ttu-id="c0feb-102">Восстановление базы данных до состояния, сохраненного в моментальном снимке</span><span class="sxs-lookup"><span data-stu-id="c0feb-102">Revert a Database to a Database Snapshot</span></span>
  <span data-ttu-id="c0feb-103">При повреждении данных в базе данных в сети в некоторых случаях вместо восстановления базы данных из резервной копии будет уместно восстановить базу данных из моментального снимка базы данных, соответствующего времени, предшествующему повреждению.</span><span class="sxs-lookup"><span data-stu-id="c0feb-103">If data in an online database becomes damaged, in some cases, reverting the database to a database snapshot that predates the damage might be an appropriate alternative to restoring the database from a backup.</span></span> <span data-ttu-id="c0feb-104">Например, с помощью возврата базы данных можно устранить такую серьезную недавнюю ошибку пользователя, как удаление таблицы.</span><span class="sxs-lookup"><span data-stu-id="c0feb-104">For example, reverting a database might be useful for reverse a recent serious user error, such as a dropped table.</span></span> <span data-ttu-id="c0feb-105">Однако все изменения данных, внесенные после создания моментального снимка, будут утеряны.</span><span class="sxs-lookup"><span data-stu-id="c0feb-105">However, all changes made after the snapshot was created are lost.</span></span>  
  
-   <span data-ttu-id="c0feb-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c0feb-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c0feb-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c0feb-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c0feb-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c0feb-108">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="c0feb-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c0feb-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c0feb-110">**Восстановление базы данных из моментального снимка с помощью**:  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="c0feb-110">**To Revert a Database to a Database Snapshot, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c0feb-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c0feb-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c0feb-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c0feb-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c0feb-113">Возврат не поддерживается в следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="c0feb-113">Reverting is unsupported under the following conditions:</span></span>  
  
-   <span data-ttu-id="c0feb-114">У базы данных в текущее время должен быть один моментальный снимок, из которого необходимо возвратить состояние базы.</span><span class="sxs-lookup"><span data-stu-id="c0feb-114">The database must currently have only one database snapshot, to which you plan to revert.</span></span>  
  
-   <span data-ttu-id="c0feb-115">В базе данных имеются доступные только для чтения или сжатые файловые группы.</span><span class="sxs-lookup"><span data-stu-id="c0feb-115">Any read-only or compressed filegroups exist in the database.</span></span>  
  
-   <span data-ttu-id="c0feb-116">Какие-либо файлы находятся вне сети, хотя были в сети на момент создания снимка.</span><span class="sxs-lookup"><span data-stu-id="c0feb-116">Any files are now offline but were online when the snapshot was created.</span></span>  
  
 <span data-ttu-id="c0feb-117">Перед тем как выполнять возврат, нужно учитывать следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="c0feb-117">Before reverting a database, consider the following limitations:</span></span>  
  
-   <span data-ttu-id="c0feb-118">Возврат не предназначен для восстановления носителей.</span><span class="sxs-lookup"><span data-stu-id="c0feb-118">Reverting is not intended for media recovery.</span></span> <span data-ttu-id="c0feb-119">.</span><span class="sxs-lookup"><span data-stu-id="c0feb-119">.</span></span> <span data-ttu-id="c0feb-120">Моментальный снимок базы данных — это неполная копия файлов базы данных, поэтому в случае, если база данных или ее снимок будут повреждены, вероятно, возврат к снимку станет невозможным.</span><span class="sxs-lookup"><span data-stu-id="c0feb-120">A database snapshot is an incomplete copy of the database files, so if either the database or the database snapshot is corrupted, reverting from a snapshot is likely to be impossible.</span></span> <span data-ttu-id="c0feb-121">Кроме того, даже если возврат возможен, в случае повреждения он вряд ли устранит проблему.</span><span class="sxs-lookup"><span data-stu-id="c0feb-121">Furthermore, even when it is possible, reverting in the event of corruption is unlikely to correct the problem.</span></span> <span data-ttu-id="c0feb-122">Таким образом, создание регулярных резервных копий и тестирование плана восстановления абсолютно необходимы для защиты базы данных.</span><span class="sxs-lookup"><span data-stu-id="c0feb-122">Therefore, taking regular backups and testing your restore plan are essential to protect a database.</span></span> <span data-ttu-id="c0feb-123">Дополнительные сведения см. в разделе [Резервное копирование и восстановление баз данных SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="c0feb-123">For more information, see [Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0feb-124">Если необходима возможность восстановления базы данных-источника на момент времени, в который был создан моментальный снимок базы данных, используйте модель полного восстановления и реализуйте политику резервного копирования, позволяющую это сделать.</span><span class="sxs-lookup"><span data-stu-id="c0feb-124">If you need to be able to restore the source database to the point in time at which you created a database snapshot, use the full recovery model and implement a backup policy that enables you to do that.</span></span>  
  
-   <span data-ttu-id="c0feb-125">Исходная база данных-источник перезаписывается базой данных, к которой выполняется возврат, при этом любые изменения, внесенные в базу данных после создания моментального снимка, будут утеряны.</span><span class="sxs-lookup"><span data-stu-id="c0feb-125">The original source database is overwritten by the reverted database, so any updates to the database since the snapshot's creation are lost.</span></span>  
  
-   <span data-ttu-id="c0feb-126">Операция возврата также перезаписывает старый файл журнала и перестраивает журнал.</span><span class="sxs-lookup"><span data-stu-id="c0feb-126">The revert operation also overwrites the old log file and rebuilds the log.</span></span> <span data-ttu-id="c0feb-127">Поэтому выполнить повтор (накат) изменений возвращенной базы данных до момента ошибки пользователя будет невозможно.</span><span class="sxs-lookup"><span data-stu-id="c0feb-127">Consequently, you cannot roll the reverted database forward to the point of user error.</span></span> <span data-ttu-id="c0feb-128">Вследствие этого рекомендуется создать резервную копию журнала перед возвратом базы данных.</span><span class="sxs-lookup"><span data-stu-id="c0feb-128">Therefore, we recommend that you back up the log before reverting a database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0feb-129">Хотя первоначальный журнал невозможно восстановить для наката базы данных, данные из этого файла журнала могут понадобиться при реконструкции потерянных данных.</span><span class="sxs-lookup"><span data-stu-id="c0feb-129">Although you cannot restore the original log to roll forward the database, the information in the original log file can be useful for reconstructing lost data.</span></span>  
  
-   <span data-ttu-id="c0feb-130">При возврате разрывается цепочка резервных копий журналов.</span><span class="sxs-lookup"><span data-stu-id="c0feb-130">Reverting breaks the log backup chain.</span></span> <span data-ttu-id="c0feb-131">Следовательно, прежде чем можно будет выполнять резервное копирование журналов возвращенной базы данных, необходимо создать полную резервную копию базы данных или файлов.</span><span class="sxs-lookup"><span data-stu-id="c0feb-131">Therefore, before you can take log backups of the reverted database, you must first take a full database backup or file backup.</span></span> <span data-ttu-id="c0feb-132">Рекомендуется создать полную резервную копию базы данных.</span><span class="sxs-lookup"><span data-stu-id="c0feb-132">We recommend a full database backup.</span></span>  
  
-   <span data-ttu-id="c0feb-133">Во время операции возврата моментальный снимок и база данных-источник будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="c0feb-133">During a revert operation, both the snapshot and the source database are unavailable.</span></span> <span data-ttu-id="c0feb-134">База данных-источник и моментальный снимок помечаются как «Восстанавливается».</span><span class="sxs-lookup"><span data-stu-id="c0feb-134">The source database and snapshot are both marked "In restore."</span></span> <span data-ttu-id="c0feb-135">Если во время операции возврата произойдет ошибка, то при следующем запуске базы данных будет предпринята попытка завершить возврат.</span><span class="sxs-lookup"><span data-stu-id="c0feb-135">If an error occurs during the revert operation, when the database starts up again, the revert operation will try to finish reverting.</span></span>  
  
-   <span data-ttu-id="c0feb-136">Метаданные возвращенной базы данных совпадают с метаданными на момент снимка.</span><span class="sxs-lookup"><span data-stu-id="c0feb-136">The metadata of a reverted database is the same as the metadata at the time of the snapshot.</span></span>  
  
-   <span data-ttu-id="c0feb-137">Операция восстановления удаляет все полнотекстовые каталоги.</span><span class="sxs-lookup"><span data-stu-id="c0feb-137">Reverting drops all the full-text catalogs.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="c0feb-138">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c0feb-138">Prerequisites</span></span>  
 <span data-ttu-id="c0feb-139">Убедитесь, что исходная база данных и моментальный снимок базы данных удовлетворяют следующим предварительным требованиям.</span><span class="sxs-lookup"><span data-stu-id="c0feb-139">Ensure that the source database and database snapshot meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="c0feb-140">Убедитесь, что база данных не повреждена.</span><span class="sxs-lookup"><span data-stu-id="c0feb-140">Verify that the database has not become corrupted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0feb-141">Если база данных повреждена, ее необходимо восстановить из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="c0feb-141">If the database has been corrupted, you will need to restore it from backups.</span></span> <span data-ttu-id="c0feb-142">Дополнительные сведения см. в разделе [Выполнение полного восстановления базы данных (простая модель восстановления)](../backup-restore/complete-database-restores-simple-recovery-model.md) или [Выполнение полного восстановления базы данных (модель полного восстановления)](../backup-restore/complete-database-restores-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="c0feb-142">For more information, see [Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) or [Complete Database Restores &#40;Full Recovery Model&#41;](../backup-restore/complete-database-restores-full-recovery-model.md).</span></span>  
  
-   <span data-ttu-id="c0feb-143">Найдите последний моментальный снимок, созданный до ошибки.</span><span class="sxs-lookup"><span data-stu-id="c0feb-143">Identify a recent snapshot that was created before the error.</span></span> <span data-ttu-id="c0feb-144">Дополнительные сведения см. в разделе [Просмотр моментального снимка базы данных (SQL Server)](view-a-database-snapshot-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c0feb-144">For more information, see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span></span>  
  
-   <span data-ttu-id="c0feb-145">Удалите все прочие моментальные снимки, существующие в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c0feb-145">Drop any other snapshots that currently exist on the database.</span></span> <span data-ttu-id="c0feb-146">Дополнительные сведения см. в разделе [Удаление моментального снимка базы данных (Transact-SQL)](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c0feb-146">For more information, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c0feb-147">безопасность</span><span class="sxs-lookup"><span data-stu-id="c0feb-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c0feb-148">Permissions</span><span class="sxs-lookup"><span data-stu-id="c0feb-148">Permissions</span></span>  
 <span data-ttu-id="c0feb-149">Возвратить базу данных-источник к состоянию на момент создания моментального снимка базы данных может любой пользователь с разрешением RESTORE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="c0feb-149">Any user who has RESTORE DATABASE permissions on the source database can revert it to its state when a database snapshot was created.</span></span>  
  
##  <a name="how-to-revert-a-database-to-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c0feb-150">Как восстановить базу данных до моментального снимка базы данных (с использованием Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c0feb-150">How to Revert a Database to a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="c0feb-151">**Восстановление базы данных до состояния, сохраненного в моментальном снимке**</span><span class="sxs-lookup"><span data-stu-id="c0feb-151">**To revert a database to a database snapshot**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c0feb-152">Пример этой процедуры см. в подразделе [Примеры (Transact-SQL)](#TsqlExample)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c0feb-152">For an example of this procedure, see [Examples (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="c0feb-153">Выберите моментальный снимок базы данных, до которого ее необходимо восстановить.</span><span class="sxs-lookup"><span data-stu-id="c0feb-153">Identify the database snapshot to which you want to revert the database.</span></span> <span data-ttu-id="c0feb-154">Просмотреть моментальные снимки базы данных можно в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (см. раздел [Просмотр моментального снимка базы данных (SQL Server)](view-a-database-snapshot-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="c0feb-154">You can view the snapshots on a database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md)).</span></span> <span data-ttu-id="c0feb-155">Также базу данных-источник можно задать с помощью столбца **source_database_id** представления каталога [sys.databases (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="c0feb-155">Also, you can identify the source database of a view from the **source_database_id** column of the [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view.</span></span>  
  
2.  <span data-ttu-id="c0feb-156">Удалите другие моментальные снимки.</span><span class="sxs-lookup"><span data-stu-id="c0feb-156">Drop any other database snapshots.</span></span>  
  
     <span data-ttu-id="c0feb-157">Дополнительные сведения об удалении моментальных снимков см. в разделе [Удаление моментального снимка базы данных (Transact-SQL)](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c0feb-157">For information on dropping snapshots, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span> <span data-ttu-id="c0feb-158">Если база данных использует модель полного восстановления, перед тем как выполнять возврат, следует создать резервную копию журнала.</span><span class="sxs-lookup"><span data-stu-id="c0feb-158">If the database uses the full recovery model, before reverting, you should back up the log.</span></span> <span data-ttu-id="c0feb-159">Дополнительные сведения см. в разделе [Резервное копирование журнала транзакций (SQL Server)](../backup-restore/back-up-a-transaction-log-sql-server.md) или [Резервное копирование журнала транзакций при повреждении базы данных (SQL Server)](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c0feb-159">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) or [Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="c0feb-160">Выполните операцию восстановления.</span><span class="sxs-lookup"><span data-stu-id="c0feb-160">Perform the revert operation.</span></span>  
  
     <span data-ttu-id="c0feb-161">Чтобы выполнить операцию восстановления базы данных-источника, необходимо обладать разрешением RESTORE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="c0feb-161">A revert operation requires RESTORE DATABASE permissions on the source database.</span></span> <span data-ttu-id="c0feb-162">Чтобы восстановить базу данных, необходимо ввести следующую инструкцию Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="c0feb-162">To revert the database, use the following Transact-SQL statement:</span></span>  
  
     <span data-ttu-id="c0feb-163">RESTORE DATABASE *database_name* FROM DATABASE_SNAPSHOT **=** _database_snapshot_name_</span><span class="sxs-lookup"><span data-stu-id="c0feb-163">RESTORE DATABASE *database_name* FROM DATABASE_SNAPSHOT **=**_database_snapshot_name_</span></span>  
  
     <span data-ttu-id="c0feb-164">где *database_name* — это база данных-источник, а *database_snapshot_name* — имя моментального снимка, к состоянию на момент создания которого необходимо восстановить базу данных.</span><span class="sxs-lookup"><span data-stu-id="c0feb-164">Where *database_name* is the source database and *database_snapshot_name* is the name of the snapshot to which you want to revert the database.</span></span> <span data-ttu-id="c0feb-165">Обратите внимание, что в данной инструкции необходимо задавать имя моментального снимка, а не устройство резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="c0feb-165">Notice that in this statement, you must specify a snapshot name rather than a backup device.</span></span>  
  
     <span data-ttu-id="c0feb-166">Дополнительные сведения см. в разделе [RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql)невозможно.</span><span class="sxs-lookup"><span data-stu-id="c0feb-166">For more information, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0feb-167">В процессе выполнения операции восстановления моментальный снимок и база данных-источник являются недоступными.</span><span class="sxs-lookup"><span data-stu-id="c0feb-167">During the revert operation, both the snapshot and the source database are unavailable.</span></span> <span data-ttu-id="c0feb-168">База данных-источник и моментальный снимок помечаются как «Восстанавливаемый».</span><span class="sxs-lookup"><span data-stu-id="c0feb-168">The source database and snapshot are both marked as "In restore."</span></span> <span data-ttu-id="c0feb-169">В случае возникновения ошибки в процессе восстановления система попытается продолжить его при следующем запуске базы данных.</span><span class="sxs-lookup"><span data-stu-id="c0feb-169">If an error occurs during the revert operation, it will try to finish reverting when the database starts up again.</span></span>  
  
4.  <span data-ttu-id="c0feb-170">В случае смены владельца базы данных после создания ее моментального снимка, возможно, понадобится обновить соответствующую информацию после восстановления.</span><span class="sxs-lookup"><span data-stu-id="c0feb-170">If the database owner changed since creation of the database snapshot, you may want to update the database owner of the reverted database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0feb-171">После восстановления в базе данных сохраняются разрешения и настройки (например модель восстановления и сведения о владельце базы данных) моментального снимка базы данных.</span><span class="sxs-lookup"><span data-stu-id="c0feb-171">The reverted database retains the permissions and configuration (such as database owner and recovery model) of the database snapshot.</span></span>  
  
5.  <span data-ttu-id="c0feb-172">Запустите базу данных.</span><span class="sxs-lookup"><span data-stu-id="c0feb-172">Start the database.</span></span>  
  
6.  <span data-ttu-id="c0feb-173">Кроме того, можно создать резервную копию восстанавливаемой базы данных, особенно если в ней используется полная модель восстановления или модель восстановления с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="c0feb-173">Optionally, back up the reverted database, especially if it uses the full (or bulk-logged) recovery model.</span></span> <span data-ttu-id="c0feb-174">Сведения о резервном копировании базы данных см. в разделе [Создание полной резервной копии базы данных (SQL Server)](../backup-restore/create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c0feb-174">To back up a database, see [Create a Full Database Backup &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="c0feb-175">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c0feb-175">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="c0feb-176">В этом разделе содержатся примеры восстановления базы данных до состояния, соответствующего моментальному снимку.</span><span class="sxs-lookup"><span data-stu-id="c0feb-176">This section contains the following examples of reverting a database to a database snapshot:</span></span>  
  
-   <span data-ttu-id="c0feb-177">A.</span><span class="sxs-lookup"><span data-stu-id="c0feb-177">A.</span></span> [<span data-ttu-id="c0feb-178">Восстановление базы данных AdventureWorks к состоянию моментального снимка</span><span class="sxs-lookup"><span data-stu-id="c0feb-178">Reverting a snapshot on the AdventureWorks database</span></span>](#Reverting_AW)  
  
-   <span data-ttu-id="c0feb-179">Б.</span><span class="sxs-lookup"><span data-stu-id="c0feb-179">B.</span></span> [<span data-ttu-id="c0feb-180">Восстановление базы данных Sales к состоянию моментального снимка</span><span class="sxs-lookup"><span data-stu-id="c0feb-180">Reverting a snapshot on the Sales database</span></span>](#Reverting_Sales)  
  
####  <a name="a-reverting-a-snapshot-on-the-adventureworks-database"></a><a name="Reverting_AW"></a> <span data-ttu-id="c0feb-181">A.</span><span class="sxs-lookup"><span data-stu-id="c0feb-181">A.</span></span> <span data-ttu-id="c0feb-182">Восстановление базы данных AdventureWorks к состоянию моментального снимка</span><span class="sxs-lookup"><span data-stu-id="c0feb-182">Reverting a snapshot on the AdventureWorks database</span></span>  
 <span data-ttu-id="c0feb-183">В этом примере предполагается наличие единственного моментального снимка базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0feb-183">This example assumes that only one snapshot currently exists on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="c0feb-184">Пример создания снимка, к состоянию на момент создания которого необходимо восстановить базу данных, см. в разделе [Создание моментального снимка базы данных (Transact-SQL)](create-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c0feb-184">For the example that creates the snapshot to which the database is reverted here, see [Create a Database Snapshot &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span></span>  
  
```  
USE master;  
-- Reverting AdventureWorks to AdventureWorks_dbss1800  
RESTORE DATABASE AdventureWorks from   
DATABASE_SNAPSHOT = 'AdventureWorks_dbss1800';  
GO  
```  
  
####  <a name="b-reverting-a-snapshot-on-the-sales-database"></a><a name="Reverting_Sales"></a> <span data-ttu-id="c0feb-185">Б.</span><span class="sxs-lookup"><span data-stu-id="c0feb-185">B.</span></span> <span data-ttu-id="c0feb-186">Восстановление базы данных Sales к состоянию моментального снимка</span><span class="sxs-lookup"><span data-stu-id="c0feb-186">Reverting a snapshot on the Sales database</span></span>  
 <span data-ttu-id="c0feb-187">В этом примере предполагается, что в базе данных **Sales** имеется два моментальных снимка: **sales_snapshot0600** и **sales_snapshot1200**.</span><span class="sxs-lookup"><span data-stu-id="c0feb-187">This example assumes that two snapshots currently exist on the **Sales** database: **sales_snapshot0600** and **sales_snapshot1200**.</span></span> <span data-ttu-id="c0feb-188">В примере происходит удаление более раннего моментального снимка, и база данных восстанавливается до состояния более позднего моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="c0feb-188">The example deletes the older of the snapshots and reverts the database to the more recent snapshot.</span></span>  
  
 <span data-ttu-id="c0feb-189">Код программы создания образца базы данных и моментальных снимков для данного примера см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c0feb-189">For the code for creating the sample database and snapshots on which this example depends, see:</span></span>  
  
-   <span data-ttu-id="c0feb-190">Сведения о создании базы данных **Sales** и моментального снимка **sales_snapshot0600** см. в подразделах "Создание баз данных с файловыми группами" и "Создание моментального снимка базы данных" раздела [CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c0feb-190">For the **Sales** database and the **sales_snapshot0600** snapshot, see "Creating a database with filegroups" and "Creating a database snapshot" in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
-   <span data-ttu-id="c0feb-191">Сведения о создании базы данных **sales_snapshot1200** см. в подразделе "Создание моментального снимка базы данных Sales" в разделе [Создание моментального снимка базы данных (Transact-SQL)](create-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c0feb-191">For the **sales_snapshot1200** snapshot, see "Creating a snapshot on the Sales database" in [Create a Database Snapshot &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span></span>  
  
```  
--Test to see if sales_snapshot0600 exists and if it   
-- does, delete it.  
IF EXISTS (SELECT dbid FROM sys.databases  
    WHERE NAME='sales_snapshot0600')  
    DROP DATABASE SalesSnapshot0600;  
GO  
-- Reverting Sales to sales_snapshot1200  
USE master;  
RESTORE DATABASE Sales FROM DATABASE_SNAPSHOT = 'sales_snapshot1200';  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="c0feb-192">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="c0feb-192">Related Tasks</span></span>  
  
-   [<span data-ttu-id="c0feb-193">Создание моментального снимка базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c0feb-193">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="c0feb-194">Просмотр моментального снимка базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c0feb-194">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="c0feb-195">Удаление моментального снимка базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c0feb-195">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="c0feb-196">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0feb-196">See Also</span></span>  
 <span data-ttu-id="c0feb-197">[Моментальные снимки базы данных (SQL Server)](database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c0feb-197">[Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span></span>  
 <span data-ttu-id="c0feb-198">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0feb-198">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="c0feb-199">[sys.databases (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0feb-199">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="c0feb-200">Зеркальное отображение и моментальные снимки баз данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c0feb-200">Database Mirroring and Database Snapshots &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-and-database-snapshots-sql-server.md)  
  
  
