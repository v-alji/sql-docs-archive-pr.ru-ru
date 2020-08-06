---
title: Пример. Оперативное восстановление файла для чтения и записи (модель полного восстановления) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- online restores [SQL Server], full recovery model
- restore sequences [SQL Server], online
ms.assetid: 0dbeda81-1464-44ba-9011-914900096368
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5b99a3d97644c2a5f104173457f30fc5b3fd7188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655785"
---
# <a name="example-online-restore-of-a-read-write-file-full-recovery-model"></a><span data-ttu-id="d7090-102">Пример Оперативное восстановление доступного для чтения и записи файла (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="d7090-102">Example: Online Restore of a Read-Write File (Full Recovery Model)</span></span>
  <span data-ttu-id="d7090-103">Сведения в этом разделе относятся только к базам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , использующим полную модель восстановления, которые содержат несколько файлов или файловых групп.</span><span class="sxs-lookup"><span data-stu-id="d7090-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="d7090-104">В этом примере база данных `adb`, которая использует модель полного восстановления, содержит три файловые группы.</span><span class="sxs-lookup"><span data-stu-id="d7090-104">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="d7090-105">Файловая группа `A` доступна для записи и для чтения, файловые группы `B` и `C` доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="d7090-105">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="d7090-106">Изначально все файловые группы находятся в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="d7090-106">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="d7090-107">Файл `a1` в файловой группе `A` , похоже, поврежден, и администратор базы данных решает восстановить его при сохранении базы данных в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="d7090-107">File `a1` in filegroup `A` appears to be damaged, and the database administrator decides to restore it while the database remains online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7090-108">При простой модели восстановления восстановление доступных для чтения и записи данных «в сети» не разрешено.</span><span class="sxs-lookup"><span data-stu-id="d7090-108">Under the simple recovery model, online restore of read/write data is not allowed.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="d7090-109">Последовательности восстановления</span><span class="sxs-lookup"><span data-stu-id="d7090-109">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7090-110">Синтаксис последовательности восстановления в сети тот же самый, что и в случае последовательности восстановления вне сети.</span><span class="sxs-lookup"><span data-stu-id="d7090-110">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="d7090-111">Восстановление файла `a1`в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="d7090-111">Online restore of file `a1`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILE='a1' FROM backup   
    WITH NORECOVERY;  
    ```  
  
     <span data-ttu-id="d7090-112">На данном этапе файл a1 находится в состоянии восстановления (RESTORING), а файловая группа A — в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="d7090-112">At this point, file a1 is in the RESTORING state, and filegroup A is offline.</span></span>  
  
2.  <span data-ttu-id="d7090-113">После восстановления файла администратор базы данных выполняет новое резервное копирование журнала, чтобы удостовериться, что момент перехода файла в режим «вне сети» перехвачен.</span><span class="sxs-lookup"><span data-stu-id="d7090-113">After restoring the file, the database administrator takes a new log backup to make sure that the point at which the file went offline is captured.</span></span>  
  
    ```  
    BACKUP LOG adb TO log_backup3;   
    ```  
  
3.  <span data-ttu-id="d7090-114">Восстановление резервных копий журналов «в сети».</span><span class="sxs-lookup"><span data-stu-id="d7090-114">Online restore of log backups.</span></span>  
  
     <span data-ttu-id="d7090-115">Администратор производит восстановление всех резервных копий журналов, созданных со времени создания резервной копии восстановленного файла до последней резервной копии журнала (*log_backup3*, сделанной в шаге 2).</span><span class="sxs-lookup"><span data-stu-id="d7090-115">The administrator restores all the log backups taken since the restored file backup, ending with the latest log backup (*log_backup3*, taken in step 2).</span></span> <span data-ttu-id="d7090-116">База данных будет восстановлена после восстановления последней резервной копии.</span><span class="sxs-lookup"><span data-stu-id="d7090-116">After the last backup is restored, the database is recovered.</span></span>  
  
    ```  
    RESTORE LOG adb FROM log_backup1 WITH NORECOVERY;  
    RESTORE LOG adb FROM log_backup2 WITH NORECOVERY;  
    RESTORE LOG adb FROM log_backup3 WITH NORECOVERY;  
    RESTORE LOG adb WITH RECOVERY;  
    ```  
  
     <span data-ttu-id="d7090-117">Файл `a1` теперь находится в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="d7090-117">File `a1` is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="d7090-118">Дополнительные примеры</span><span class="sxs-lookup"><span data-stu-id="d7090-118">Additional Examples</span></span>  
  
-   [<span data-ttu-id="d7090-119">Пример. Поэтапное восстановление базы данных &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="d7090-119">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="d7090-120">Пример. Поэтапное восстановление отдельных файловых групп &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="d7090-120">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="d7090-121">Пример. Оперативное восстановление доступного только для чтения файла &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="d7090-121">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="d7090-122">Пример. Поэтапное восстановление базы данных &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="d7090-122">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="d7090-123">Пример. Поэтапное восстановление только некоторых файловых групп &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="d7090-123">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="d7090-124">Пример. Оперативное восстановление файла, доступного только для чтения &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="d7090-124">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="d7090-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="d7090-125">See Also</span></span>  
 <span data-ttu-id="d7090-126">[Восстановление в сети (SQL Server)](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d7090-126">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="d7090-127">[Поэтапное восстановление (SQL Server)](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d7090-127">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="d7090-128">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d7090-128">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="d7090-129">[Обзор процессов восстановления (SQL Server)](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d7090-129">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="d7090-130">[Применение резервных копий журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d7090-130">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="d7090-131">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d7090-131">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
