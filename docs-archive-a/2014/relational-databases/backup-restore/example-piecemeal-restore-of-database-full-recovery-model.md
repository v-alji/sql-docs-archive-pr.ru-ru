---
title: Пример. Поэтапное восстановление базы данных (модель полного восстановления) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- piecemeal restores [SQL Server], full recovery model
- restore sequences [SQL Server], piecemeal
ms.assetid: 0a84892d-2f7a-4e77-b2d0-d68b95595210
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5cfccccdbdc0c4fb3b189ee0a9fa3aeaf426578b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735374"
---
# <a name="example-piecemeal-restore-of-database-full-recovery-model"></a><span data-ttu-id="646c2-102">Пример поэтапного восстановления базы данных (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="646c2-102">Example: Piecemeal Restore of Database (Full Recovery Model)</span></span>
  <span data-ttu-id="646c2-103">При поэтапной последовательности восстановления база данных восстанавливается в течение нескольких этапов на уровне файловой группы, начиная с первичной и всех вторичных файловых групп, доступных для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="646c2-103">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, beginning with the primary and all read-write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="646c2-104">В данном примере база данных `adb` восстанавливается после сбоя на новом компьютере.</span><span class="sxs-lookup"><span data-stu-id="646c2-104">In this example, database `adb` is restored to a new computer after a disaster.</span></span> <span data-ttu-id="646c2-105">Используется полная модель восстановления базы данных, поэтому перед началом восстановления необходимо сделать резервную копию заключительного фрагмента журнала базы данных.</span><span class="sxs-lookup"><span data-stu-id="646c2-105">The database is using the full recovery model; therefore, before the restore starts, a tail-log backup must be taken of the database.</span></span> <span data-ttu-id="646c2-106">До сбоя все файловые группы работали в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="646c2-106">Before the disaster, all the filegroups are online.</span></span> <span data-ttu-id="646c2-107">Файловая группа `B` доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="646c2-107">Filegroup `B` is read-only.</span></span> <span data-ttu-id="646c2-108">Необходимо восстановить все вторичные файловые группы, но они восстанавливаются в порядке важности: `A` (наивысшая), `C`и `B`.</span><span class="sxs-lookup"><span data-stu-id="646c2-108">All of the secondary filegroups must be restored, but they are restored in order of importance: `A` (highest), `C`, and lastly `B`.</span></span> <span data-ttu-id="646c2-109">В этом примере существует четыре резервные копии журнала, включая резервную копию заключительного фрагмента журнала.</span><span class="sxs-lookup"><span data-stu-id="646c2-109">In this example, there are four log backups, including the tail-log backup.</span></span>  
  
## <a name="tail-log-backup"></a><span data-ttu-id="646c2-110">Резервная копия заключительного фрагмента журнала</span><span class="sxs-lookup"><span data-stu-id="646c2-110">Tail-Log Backup</span></span>  
 <span data-ttu-id="646c2-111">Перед тем как восстановить базу данных из копии, администратор этой базы данных должен создать резервную копию заключительного фрагмента журнала.</span><span class="sxs-lookup"><span data-stu-id="646c2-111">Before restoring the database, the database administrator must back up the tail of the log.</span></span> <span data-ttu-id="646c2-112">Поскольку база данных повреждена, для создания резервной копии заключительного фрагмента журнала требуется применение параметра NO_TRUNCATE:</span><span class="sxs-lookup"><span data-stu-id="646c2-112">Because the database is damaged, creating the tail-log backup requires using the NO_TRUNCATE option:</span></span>  
  
```  
BACKUP LOG adb TO tailLogBackup WITH NORECOVERY, NO_TRUNCATE  
```  
  
 <span data-ttu-id="646c2-113">Резервная копия заключительного фрагмента журнала — это последняя резервная копия, используемая в следующих последовательностях восстановления.</span><span class="sxs-lookup"><span data-stu-id="646c2-113">The tail-log backup is the last backup that is applied in the following restore sequences.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="646c2-114">Последовательности восстановления</span><span class="sxs-lookup"><span data-stu-id="646c2-114">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="646c2-115">Синтаксис последовательности восстановления в сети тот же самый, что и в случае последовательности восстановления вне сети.</span><span class="sxs-lookup"><span data-stu-id="646c2-115">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="646c2-116">Частичное восстановление первичной и вторичной файловой группы `A`:</span><span class="sxs-lookup"><span data-stu-id="646c2-116">Partial restore of the primary and secondary filegroup `A`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
       WITH PARTIAL, NORECOVERY  
    RESTORE DATABASE adb FILEGROUP='A' FROM backup2   
       WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM backup4 WITH NORECOVERY  
    RESTORE LOG adb FROM backup5 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
2.  <span data-ttu-id="646c2-117">Восстановление файловой группы `C`«в сети».</span><span class="sxs-lookup"><span data-stu-id="646c2-117">Online restore of filegroup `C`.</span></span>  
  
     <span data-ttu-id="646c2-118">На этом этапе первичная файловая группа и вторичная файловая группа `A` находятся в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="646c2-118">At this point, the primary filegroup and secondary filegroup `A` are online.</span></span> <span data-ttu-id="646c2-119">Все файлы в файловых группах `B` и `C` ожидают восстановления, а сами файловые группы находятся в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="646c2-119">All the files in filegroups `B` and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
     <span data-ttu-id="646c2-120">Сообщения от последней инструкции `RESTORE LOG` в шаге 1 указывают, что откат транзакций, задействовавших файловую группу `C` , был отложен из-за недоступности этой файловой группы.</span><span class="sxs-lookup"><span data-stu-id="646c2-120">Messages from the last `RESTORE LOG` statement in step 1 indicate that rollback of transactions that involve filegroup `C` was deferred, because this filegroup is not available.</span></span> <span data-ttu-id="646c2-121">Нормальная работа может продолжаться, но этими транзакциями удерживаются блокировки, поэтому до завершения отката усечение журнала выполнено не будет.</span><span class="sxs-lookup"><span data-stu-id="646c2-121">Regular operations can continue, but locks are held by these transactions and log truncation will not occur until the rollback can complete.</span></span>  
  
     <span data-ttu-id="646c2-122">Во второй последовательности восстановления администратор базы данных восстанавливает файловую группу `C`:</span><span class="sxs-lookup"><span data-stu-id="646c2-122">In the second restore sequence, the database administrator restores filegroup `C`:</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' FROM backup2a WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM backup4 WITH NORECOVERY  
    RESTORE LOG adb FROM backup5 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="646c2-123">На этом этапе первичная файловая группа и файловые группы `A` и `C` находятся в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="646c2-123">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="646c2-124">Файлы в файловой группе `B` ожидают восстановления, при этом она находится в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="646c2-124">Files in filegroup `B` remain recovery pending, with the filegroup offline.</span></span> <span data-ttu-id="646c2-125">Отложенные транзакции разрешены, и выполняется усечение журнала.</span><span class="sxs-lookup"><span data-stu-id="646c2-125">Deferred transactions have been resolved, and log truncation occurs.</span></span>  
  
3.  <span data-ttu-id="646c2-126">Восстановление файловой группы `B`«в сети».</span><span class="sxs-lookup"><span data-stu-id="646c2-126">Online restore of filegroup `B`.</span></span>  
  
     <span data-ttu-id="646c2-127">В третьей последовательности восстановления администратор базы данных восстанавливает файловую группу `B`.</span><span class="sxs-lookup"><span data-stu-id="646c2-127">In the third restore sequence, the database administrator restores filegroup `B`.</span></span> <span data-ttu-id="646c2-128">После того как файловая группа `B` стала доступна только для чтения, используется ее резервная копия, чтобы не нужно было осуществлять накат во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="646c2-128">The backup of filegroup `B` was taken after the filegroup became read-only; therefore, it does not have to be rolled forward during recovery.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup2b WITH RECOVERY  
    ```  
  
     <span data-ttu-id="646c2-129">Теперь все файловые группы находятся в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="646c2-129">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="646c2-130">Дополнительные примеры</span><span class="sxs-lookup"><span data-stu-id="646c2-130">Additional Examples</span></span>  
  
-   [<span data-ttu-id="646c2-131">Пример. Поэтапное восстановление базы данных &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="646c2-131">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="646c2-132">Пример. Поэтапное восстановление отдельных файловых групп &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="646c2-132">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="646c2-133">Пример. Оперативное восстановление доступного только для чтения файла &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="646c2-133">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="646c2-134">Пример. Поэтапное восстановление только некоторых файловых групп &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="646c2-134">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="646c2-135">Пример. Оперативное восстановление файла, доступного для чтения и записи &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="646c2-135">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="646c2-136">Пример. Оперативное восстановление файла, доступного только для чтения &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="646c2-136">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="646c2-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="646c2-137">See Also</span></span>  
 <span data-ttu-id="646c2-138">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="646c2-138">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="646c2-139">[Восстановление в сети (SQL Server)](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="646c2-139">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="646c2-140">[Применение резервных копий журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="646c2-140">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="646c2-141">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="646c2-141">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="646c2-142">Поэтапное восстановление (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="646c2-142">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
