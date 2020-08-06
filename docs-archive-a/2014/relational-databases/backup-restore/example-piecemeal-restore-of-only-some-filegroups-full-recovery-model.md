---
title: Пример. Поэтапное восстановление некоторых файловых групп (модель полного восстановления) | Документация Майкрософт
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
ms.assetid: bced4b54-e819-472b-b784-c72e14e72a0b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b3cb1a5ea33a5016c99fdf1f5a7f4e892c045b59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751216"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-full-recovery-model"></a><span data-ttu-id="5b0f6-102">Пример поэтапного восстановления некоторых файловых групп (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="5b0f6-102">Example: Piecemeal Restore of Only Some Filegroups (Full Recovery Model)</span></span>
  <span data-ttu-id="5b0f6-103">Сведения в этом разделе относятся только к базам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , использующим полную модель восстановления, которые содержат несколько файлов или файловых групп.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="5b0f6-104">В последовательности поэтапного восстановления база данных восстанавливается за несколько шагов на уровне файловой группы, начиная с первичной и всех вторичных файловых групп, доступных для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-104">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, starting with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="5b0f6-105">В этом примере база данных `adb`, которая использует модель полного восстановления, содержит три файловые группы.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-105">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="5b0f6-106">Файловая группа `A` доступна для записи и для чтения, файловые группы `B` и `C` доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-106">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="5b0f6-107">Изначально все файловые группы находятся в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-107">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="5b0f6-108">Первичная файловая группа и файловая группа `B` базы данных `adb` , вероятно, повреждены.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-108">The primary and filegroup `B` of database `adb` appear to be damaged.</span></span> <span data-ttu-id="5b0f6-109">Первичная файловая группа достаточно мала и может быть быстро восстановлена.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-109">The primary filegroup is fairly small and can be restored quickly.</span></span> <span data-ttu-id="5b0f6-110">Администратор базы данных решает восстановить обе группы с помощью последовательности поэтапного восстановления.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-110">The database administrator decides to restore them by using a piecemeal restore sequence.</span></span> <span data-ttu-id="5b0f6-111">Сначала восстанавливается первичная файловая группа и связанные с ней журналы транзакций, при этом восстанавливается база данных.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-111">First, the primary filegroup and the subsequent transaction logs are restored the database is recovered.</span></span>  
  
 <span data-ttu-id="5b0f6-112">Неизменившиеся файловые группы `A` и `C` содержат важные данные.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-112">The intact filegroups `A` and `C` contain critical data.</span></span> <span data-ttu-id="5b0f6-113">Поэтому они будут восстановлены следующим образом и переведены в режим «в сети» как можно быстрее.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-113">Therefore, they will be recovered next to bring them online as quickly as possible.</span></span> <span data-ttu-id="5b0f6-114">Наконец, восстанавливается поврежденная вторичная файловая группа `B`.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-114">Finally, the damaged secondary filegroup, `B`, is restored and recovered.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="5b0f6-115">Последовательности восстановления</span><span class="sxs-lookup"><span data-stu-id="5b0f6-115">Restore Sequences:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b0f6-116">Синтаксис последовательности восстановления в сети тот же самый, что и в случае последовательности восстановления вне сети.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-116">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="5b0f6-117">Создайте резервную копию заключительного фрагмента журнала базы данных `adb`.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-117">Create a tail log backup of database `adb`.</span></span> <span data-ttu-id="5b0f6-118">Этот этап важен, чтобы привести неповрежденные файловые группы `A` и `C` в соответствие с точкой восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-118">This step is essential to make the intact filegroups `A` and `C` current with the recovery point of the database.</span></span>  
  
    ```  
    BACKUP LOG adb TO tailLogBackup WITH NORECOVERY  
    ```  
  
2.  <span data-ttu-id="5b0f6-119">Произведите частичное восстановление первичной файловой группы.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-119">Partial restore of the primary filegroup.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='Primary' FROM backup   
    WITH PARTIAL, NORECOVERY  
    RESTORE LOG adb FROM backup1 WITH NORECOVERY  
    RESTORE LOG adb FROM backup2 WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="5b0f6-120">В этот момент первичная группа файлов переходит в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="5b0f6-120">At this point the primary is online.</span></span> <span data-ttu-id="5b0f6-121">Файлы в файловых группах `A`, `B`и `C` ожидают восстановления и поэтому находятся в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="5b0f6-121">Files in filegroups `A`, `B`, and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
3.  <span data-ttu-id="5b0f6-122">Восстановление файлов `A` и `C`в сети.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-122">Online restore of filegroups `A` and `C`.</span></span>  
  
     <span data-ttu-id="5b0f6-123">Так как данные этих файловых групп не повреждены, их не нужно восстанавливать из резервной копии, но их нужно перевести в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="5b0f6-123">Because their data is undamaged, these filegroups do not have to be restored from a backup, but they do have to be recovered to bring them online.</span></span>  
  
     <span data-ttu-id="5b0f6-124">Администратор базы данных сразу же восстанавливает файловые группы `A` и `C` .</span><span class="sxs-lookup"><span data-stu-id="5b0f6-124">The database administrator recovers `A` and `C` immediately.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='A', FILEGROUP='C' WITH RECOVERY  
    ```  
  
     <span data-ttu-id="5b0f6-125">На этом этапе первичная файловая группа и файловые группы `A` и `C` находятся в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-125">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="5b0f6-126">Файлы в файловой группе `B` ожидают восстановления, при этом она находится в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="5b0f6-126">Files in filegroup `B` remain recovery pending, with the filegroup offline.</span></span>  
  
4.  <span data-ttu-id="5b0f6-127">Восстановление файловой группы `B`«в сети».</span><span class="sxs-lookup"><span data-stu-id="5b0f6-127">Online restore of filegroup `B`.</span></span>  
  
     <span data-ttu-id="5b0f6-128">Файлы в файловой группе `B` могут быть восстановлены позже в любое время.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-128">Files in filegroup `B` are restored any time thereafter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b0f6-129">После того как файловая группа `B` становится доступной только для чтения, используется ее резервная копия, что исключает необходимость выполнения наката.</span><span class="sxs-lookup"><span data-stu-id="5b0f6-129">The backup of filegroup `B` was taken after the filegroup became read-only; therefore, these files do not have to be rolled forward.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="5b0f6-130">Теперь все файловые группы находятся в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="5b0f6-130">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="5b0f6-131">Дополнительные примеры</span><span class="sxs-lookup"><span data-stu-id="5b0f6-131">Additional Examples</span></span>  
  
-   [<span data-ttu-id="5b0f6-132">Пример. Поэтапное восстановление базы данных &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="5b0f6-132">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="5b0f6-133">Пример. Поэтапное восстановление отдельных файловых групп &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="5b0f6-133">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="5b0f6-134">Пример. Оперативное восстановление доступного только для чтения файла &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="5b0f6-134">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="5b0f6-135">Пример. Поэтапное восстановление базы данных &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="5b0f6-135">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="5b0f6-136">Пример. Оперативное восстановление файла, доступного для чтения и записи &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="5b0f6-136">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="5b0f6-137">Пример. Оперативное восстановление файла, доступного только для чтения &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="5b0f6-137">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="5b0f6-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="5b0f6-138">See Also</span></span>  
 <span data-ttu-id="5b0f6-139">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5b0f6-139">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="5b0f6-140">[Восстановление в сети (SQL Server)](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5b0f6-140">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="5b0f6-141">[Применение резервных копий журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5b0f6-141">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="5b0f6-142">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5b0f6-142">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="5b0f6-143">Поэтапное восстановление (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5b0f6-143">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
