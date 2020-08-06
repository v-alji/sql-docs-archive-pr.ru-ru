---
title: Восстановление базы данных без восстановления данных (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring [SQL Server], recovery-only
- recovery-only scenario [SQL Server]
- restoring databases [SQL Server], recovery-only
- recovery [SQL Server], recovery-only
- database recovery [SQL Server]
- database restores [SQL Server], recovery-only
- recovery [SQL Server], without restoring data
ms.assetid: 7e8fa620-315d-4e10-a718-23fa5171c09e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 04e4f78e51adb803bb65530c0b3b903aa7f76419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666695"
---
# <a name="recover-a-database-without-restoring-data-transact-sql"></a><span data-ttu-id="0a9ba-102">Восстановление базы данных без восстановления данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0a9ba-102">Recover a Database Without Restoring Data (Transact-SQL)</span></span>
  <span data-ttu-id="0a9ba-103">Обычно все данные в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] восстанавливаются перед восстановлением базы данных.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-103">Usually, all of the data in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is restored before the database is recovered.</span></span> <span data-ttu-id="0a9ba-104">Однако операция восстановления может восстановить базу данных без использования резервной копии, например, при восстановлении согласованных с базой данных файлов, доступных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-104">However, a restore operation can recover a database without actually restoring a backup; for example, when recovering a read-only file that is consistent with the database.</span></span> <span data-ttu-id="0a9ba-105">Это называется *восстановлением только по журналу транзакций*.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-105">This is referred to as a *recovery-only restore*.</span></span> <span data-ttu-id="0a9ba-106">Восстановление только по журналу транзакций выполняется в тех случаях, когда данные уже согласованы с базой данных и остается только сделать их доступными.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-106">When offline data is already consistent with the database and needs only to be made available, a recovery-only restore operation completes the recovery of the database and bring the data online.</span></span>  
  
 <span data-ttu-id="0a9ba-107">Восстановление только по журналу транзакций может выполняться для одного или нескольких файлов или файловых групп базы данных.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-107">A recovery-only restore can occur for a whole database or for one or more a files or filegroups.</span></span>  
  
## <a name="recovery-only-database-restore"></a><span data-ttu-id="0a9ba-108">Восстановление базы данных только по журналу транзакций</span><span class="sxs-lookup"><span data-stu-id="0a9ba-108">Recovery-Only Database Restore</span></span>  
 <span data-ttu-id="0a9ba-109">Восстановление базы данных только по журналу транзакций может применяться в следующей ситуации.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-109">A recovery-only database restore can be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="0a9ba-110">При восстановлении из последней резервной копии в последовательности восстановления база данных, которую в настоящее время нужно перевести в оперативный режим, не была восстановлена по журналу.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-110">You did not recover the database when restoring the last backup in a restore sequence, and you now want to recover the database to bring it online.</span></span>  
  
-   <span data-ttu-id="0a9ba-111">База данных находится в режиме ожидания, поэтому необходимо сделать ее доступной для обновлений без применения еще одной резервной копии журналов.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-111">The database is in standby mode, and you want to make the database updatable without applying another log backup.</span></span>  
  
 <span data-ttu-id="0a9ba-112">Синтаксис инструкции [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) для восстановления базы данных только по журналу транзакций:</span><span class="sxs-lookup"><span data-stu-id="0a9ba-112">The [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for a recovery-only database restore is as follows:</span></span>  
  
 <span data-ttu-id="0a9ba-113">RESTORE DATABASE *имя_базы_данных* WITH RECOVERY</span><span class="sxs-lookup"><span data-stu-id="0a9ba-113">RESTORE DATABASE *database_name* WITH RECOVERY</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a9ba-114">Предложение FROM **=** \<*backup_device>\* не используется для восстановления базы данных только по журналу транзакций, поскольку резервная копия не требуется.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-114">The FROM **=** \<*backup_device>\* clause is not used for recovery-only restores because no backup is necessary.</span></span>  
  
 <span data-ttu-id="0a9ba-115">**Пример**</span><span class="sxs-lookup"><span data-stu-id="0a9ba-115">**Example**</span></span>  
  
 <span data-ttu-id="0a9ba-116">В следующем примере выполняется восстановление базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] в ходе операции восстановления без восстановления данных.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-116">The following example recovers the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database in a restore operation without restoring data.</span></span>  
  
```  
-- Restore database using WITH RECOVERY.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY  
```  
  
## <a name="recovery-only-file-restore"></a><span data-ttu-id="0a9ba-117">Восстановление файлов только по журналу транзакций</span><span class="sxs-lookup"><span data-stu-id="0a9ba-117">Recovery-Only File Restore</span></span>  
 <span data-ttu-id="0a9ba-118">Восстановление файлов только по журналу транзакций может применяться в следующей ситуации.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-118">A recovery-only file restore can be useful in the following situation:</span></span>  
  
 <span data-ttu-id="0a9ba-119">База данных поэтапно восстановлена из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-119">A database is restored piecemeal.</span></span> <span data-ttu-id="0a9ba-120">После восстановления первичной файловой группы один или несколько еще не восстановленных файлов согласованы с новым состоянием базы данных, потому что, например, в течение некоторого времени они были доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-120">After restore of the primary filegroup is complete, one or more of the unrestored files are consistent with the new database state, perhaps because it has been read-only for some time.</span></span> <span data-ttu-id="0a9ba-121">Эти файлы достаточно восстановить по журналу транзакций. Копировать данные не нужно.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-121">These files only have to be recovered; data copying is unnecessary.</span></span>  
  
 <span data-ttu-id="0a9ba-122">Операция восстановления только по журналу транзакций переводит файловую группу «вне сети» в режим «в сети», при этом не выполняется ни копирование, ни повтор, ни стадия отката.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-122">A recovery-only restore operation brings the data in the offline filegroup online; no data-copy, redo, or undo phase occurs.</span></span> <span data-ttu-id="0a9ba-123">Сведения об этапах восстановления см. в статье [Обзор процессов восстановления (SQL Server)](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0a9ba-123">For information about the phases of restore, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
 <span data-ttu-id="0a9ba-124">Синтаксис инструкции [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) для восстановления файлов только по журналу транзакций:</span><span class="sxs-lookup"><span data-stu-id="0a9ba-124">The [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for a recovery-only file restore is:</span></span>  
  
 <span data-ttu-id="0a9ba-125">Восстановление базы данных *database_name* {файл **=** _logical_file_name_ | ФАЙЛовая группа **=** _logical_filegroup_name_ } [ **,**... *n* ] с восстановлением</span><span class="sxs-lookup"><span data-stu-id="0a9ba-125">RESTORE DATABASE *database_name* { FILE **=**_logical_file_name_ | FILEGROUP **=**_logical_filegroup_name_ }[ **,**...*n* ] WITH RECOVERY</span></span>  
  
 <span data-ttu-id="0a9ba-126">**Пример**</span><span class="sxs-lookup"><span data-stu-id="0a9ba-126">**Example**</span></span>  
  
 <span data-ttu-id="0a9ba-127">В следующем примере показано восстановление по журналу транзакций для файлов вторичной файловой группы `SalesGroup2`в базе данных `Sales` .</span><span class="sxs-lookup"><span data-stu-id="0a9ba-127">The following example illustrates a recovery-only file restore of the files in a secondary filegroup, `SalesGroup2`, in the `Sales` database.</span></span> <span data-ttu-id="0a9ba-128">Первичная файловая группа уже восстановлена в качестве первого шага поэтапного восстановления, поэтому группа `SalesGroup2` согласована с первичной файловой группой.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-128">The primary filegroup has already been restored as the initial step of a piecemeal restore, and `SalesGroup2` is consistent with the restored primary filegroup.</span></span> <span data-ttu-id="0a9ba-129">Восстановление файловой группы и ее перевод в режим «в сети» требует только одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="0a9ba-129">Recovering this filegroup and bringing it online requires only a single statement.</span></span>  
  
```  
RESTORE DATABASE Sales FILEGROUP=SalesGroup2 WITH RECOVERY;  
```  
  
## <a name="examples-of-completing-a-piecemeal-restore-scenario-with-a-recovery-only-restore"></a><span data-ttu-id="0a9ba-130">Примеры завершения сценария поэтапного восстановления восстановлением только по журналу транзакций</span><span class="sxs-lookup"><span data-stu-id="0a9ba-130">Examples of Completing a Piecemeal Restore Scenario with a Recovery-Only Restore</span></span>  
 <span data-ttu-id="0a9ba-131">**Простая модель восстановления**</span><span class="sxs-lookup"><span data-stu-id="0a9ba-131">**Simple recovery model**</span></span>  
  
-   [<span data-ttu-id="0a9ba-132">Пример. Поэтапное восстановление базы данных &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="0a9ba-132">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="0a9ba-133">Пример. Поэтапное восстановление отдельных файловых групп &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="0a9ba-133">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
 <span data-ttu-id="0a9ba-134">**Модель полного восстановления**</span><span class="sxs-lookup"><span data-stu-id="0a9ba-134">**Full recovery model**</span></span>  
  
-   [<span data-ttu-id="0a9ba-135">Пример. Поэтапное восстановление базы данных &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="0a9ba-135">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="0a9ba-136">Пример. Поэтапное восстановление только некоторых файловых групп &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="0a9ba-136">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  
## <a name="see-also"></a><span data-ttu-id="0a9ba-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="0a9ba-137">See Also</span></span>  
 <span data-ttu-id="0a9ba-138">[Восстановление в сети (SQL Server)](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0a9ba-138">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="0a9ba-139">[Поэтапное восстановление (SQL Server)](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0a9ba-139">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="0a9ba-140">[Восстановление файлов (простая модель восстановления)](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="0a9ba-140">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="0a9ba-141">[Восстановления файлов (модель полного восстановления)](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="0a9ba-141">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="0a9ba-142">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0a9ba-142">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
