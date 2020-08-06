---
title: Пример. Поэтапное восстановление некоторых файловых групп (простая модель восстановления) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], simple recovery model
- restore sequences [SQL Server], piecemeal
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: d7ad026c-5355-4308-9560-0dc843940d4f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8254ac96a269b6fb433759e5a649bf9df1b7feac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751215"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model"></a><span data-ttu-id="9ce80-102">Пример поэтапного восстановления некоторых файловых групп (простая модель восстановления)</span><span class="sxs-lookup"><span data-stu-id="9ce80-102">Example: Piecemeal Restore of Only Some Filegroups (Simple Recovery Model)</span></span>
  <span data-ttu-id="9ce80-103">Данный раздел относится только к базам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые содержат доступные только для чтения файловые группы в простой модели восстановления.</span><span class="sxs-lookup"><span data-stu-id="9ce80-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the simple recovery model that contain a read-only filegroup.</span></span>  
  
 <span data-ttu-id="9ce80-104">При поэтапной последовательности восстановления база данных восстанавливается в течение нескольких этапов на уровне файловой группы, начиная с первичной, и всех вторичных файловых групп, доступных для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="9ce80-104">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, beginning with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="9ce80-105">В этом примере база данных с именем `adb`, которая использует простую модель восстановления, содержит три файловые группы.</span><span class="sxs-lookup"><span data-stu-id="9ce80-105">In this example, a database named `adb`, which uses the simple recovery model, contains three filegroups.</span></span> <span data-ttu-id="9ce80-106">Файловая группа `A` доступна для записи и для чтения, файловые группы `B` и `C` доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="9ce80-106">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="9ce80-107">Изначально все файловые группы находятся в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="9ce80-107">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="9ce80-108">Первичная группа и файловая группа `B` базы данных `adb` повреждены, поэтому администратор базы данных решает восстановить их с помощью последовательности поэтапного восстановления.</span><span class="sxs-lookup"><span data-stu-id="9ce80-108">The primary and filegroup `B` of database `adb` appear to be damaged; therefore, the database administrator decides to restore them by using a piecemeal restore sequence.</span></span> <span data-ttu-id="9ce80-109">При использовании простой модели восстановления все файловые группы, доступные для чтения и записи, должны быть восстановлены из той же частичной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="9ce80-109">Under the simple recovery model, all read/write filegroups must be restored from the same partial backup.</span></span> <span data-ttu-id="9ce80-110">Хотя файловая группа `A` не повреждена, но для обеспечения согласованности данных она должна быть восстановлена вместе с первичной файловой группой (база данных будет восстановлена в том виде, который она имела к концу последнего частичного резервного копирования).</span><span class="sxs-lookup"><span data-stu-id="9ce80-110">Although filegroup `A` is intact, it must be restored with the primary filegroup to make sure that they are consistent (the database will be restored to the point in time defined by the end of the last partial backup).</span></span> <span data-ttu-id="9ce80-111">Файловая группа `C` не повреждена, но она должна быть восстановлена для перевода ее в режим в сети.</span><span class="sxs-lookup"><span data-stu-id="9ce80-111">Filegroup `C` is intact, but it must be recovered to bring it online.</span></span> <span data-ttu-id="9ce80-112">Файловая группа `B`, даже если она повреждена, содержит меньше важных данных, чем файловая группа `C`, поэтому `B` будет восстановлена в последнюю очередь.</span><span class="sxs-lookup"><span data-stu-id="9ce80-112">Filegroup `B`, although damaged, contains less critical data than Filegroup `C`; therefore, `B` will be restored last.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="9ce80-113">Последовательности восстановления</span><span class="sxs-lookup"><span data-stu-id="9ce80-113">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ce80-114">Синтаксис последовательности восстановления в сети тот же самый, что и в случае последовательности восстановления вне сети.</span><span class="sxs-lookup"><span data-stu-id="9ce80-114">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="9ce80-115">Частичное восстановление первичной группы и файловой группы `A` из частичной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="9ce80-115">Partial restore of the primary and filegroup `A` from a partial backup.</span></span>  
  
    ```  
    RESTORE DATABASE adb READ_WRITE_FILEGROUPS FROM partial_backup   
    WITH PARTIAL, RECOVERY  
    ```  
  
     <span data-ttu-id="9ce80-116">На этом этапе первичная файловая группа и файловая группа `A` работают в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="9ce80-116">At this point the primary filegroup and filegroup `A` are online.</span></span> <span data-ttu-id="9ce80-117">Файлы в файловых группах `B` и `C` ожидают восстановления, поэтому находятся в режиме вне сети.</span><span class="sxs-lookup"><span data-stu-id="9ce80-117">Files in filegroups `B` and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
2.  <span data-ttu-id="9ce80-118">Восстановление файловой группы `C`в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="9ce80-118">Online recovery of filegroup `C`.</span></span>  
  
     <span data-ttu-id="9ce80-119">Файловая группа `C` согласована, потому что восстановленная выше резервная копия была сделана после того, как эту группу `C` перевели в режим только для чтения, несмотря на то, что в результате восстановления произошел откат базы данных на более ранний момент времени.</span><span class="sxs-lookup"><span data-stu-id="9ce80-119">Filegroup `C` is consistent because the partial backup that was restored above was taken after filegroup `C` became read-only, although the database was taken back in time by the restore.</span></span> <span data-ttu-id="9ce80-120">Администратор базы данных восстанавливает файловую группу `C`, не восстанавливая ее из копии, чтобы перевести в режим в сети.</span><span class="sxs-lookup"><span data-stu-id="9ce80-120">The database administrator recovers the filegroup `C`, without restoring it, to bring it online.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' WITH RECOVERY  
    ```  
  
     <span data-ttu-id="9ce80-121">На этом этапе первичная файловая группа и файловые группы `A` и `C` находятся в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="9ce80-121">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="9ce80-122">Файлы в файловой группе filegroup B ожидают восстановления, при этом она находится в режиме вне сети.</span><span class="sxs-lookup"><span data-stu-id="9ce80-122">Files in filegroupB remain recovery pending, with the filegroup offline.</span></span>  
  
3.  <span data-ttu-id="9ce80-123">Восстановление в сети файловой группы `B.`</span><span class="sxs-lookup"><span data-stu-id="9ce80-123">Online restore of filegroup `B.`</span></span>  
  
     <span data-ttu-id="9ce80-124">Файлы файловой группы `B` должны быть восстановлены из копий.</span><span class="sxs-lookup"><span data-stu-id="9ce80-124">Files in filegroup `B` must be restored.</span></span> <span data-ttu-id="9ce80-125">Администратор восстанавливает резервную копию файловой группы `B` , полученную после того, как группа `B` стала доступна только для чтения, но до выполнения частичного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="9ce80-125">The database administrator restores the backup of filegroup `B` taken after filegroup `B` became read-only and before the partial backup.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup   
    WITH RECOVERY  
    ```  
  
     <span data-ttu-id="9ce80-126">Теперь все файловые группы находятся в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="9ce80-126">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="9ce80-127">Дополнительные примеры</span><span class="sxs-lookup"><span data-stu-id="9ce80-127">Additional Examples</span></span>  
  
-   [<span data-ttu-id="9ce80-128">Пример. Поэтапное восстановление базы данных &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="9ce80-128">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="9ce80-129">Пример. Оперативное восстановление доступного только для чтения файла &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="9ce80-129">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="9ce80-130">Пример. Поэтапное восстановление базы данных &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="9ce80-130">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="9ce80-131">Пример. Поэтапное восстановление только некоторых файловых групп &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="9ce80-131">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="9ce80-132">Пример. Оперативное восстановление файла, доступного для чтения и записи &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="9ce80-132">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="9ce80-133">Пример. Оперативное восстановление файла, доступного только для чтения &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="9ce80-133">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="9ce80-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ce80-134">See Also</span></span>  
 <span data-ttu-id="9ce80-135">[Восстановление в сети (SQL Server)](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9ce80-135">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="9ce80-136">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9ce80-136">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="9ce80-137">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9ce80-137">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="9ce80-138">Поэтапное восстановление (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9ce80-138">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
