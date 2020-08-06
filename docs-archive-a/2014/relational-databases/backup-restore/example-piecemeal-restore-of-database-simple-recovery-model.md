---
title: Пример. Поэтапное восстановление базы данных (простая модель восстановления) | Документация Майкрософт
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
ms.assetid: 9834b14a-4e56-4654-b190-c2a38624b6b4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69de84fa2ff3a853eb9926549ad4859d2f1ae38e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735373"
---
# <a name="example-piecemeal-restore-of-database-simple-recovery-model"></a><span data-ttu-id="af2bb-102">Пример поэтапного восстановления базы данных (простая модель восстановления)</span><span class="sxs-lookup"><span data-stu-id="af2bb-102">Example: Piecemeal Restore of Database (Simple Recovery Model)</span></span>
  <span data-ttu-id="af2bb-103">В последовательности поэтапного восстановления база данных восстанавливается за несколько шагов на уровне файловой группы, начиная с первичной и всех вторичных файловых групп, доступных для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="af2bb-103">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, starting with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="af2bb-104">В данном примере база данных `adb` восстанавливается после сбоя на новом компьютере.</span><span class="sxs-lookup"><span data-stu-id="af2bb-104">In this example, database `adb` is restored to a new computer after a disaster.</span></span> <span data-ttu-id="af2bb-105">Для базы данных выбрана простая модель восстановления.</span><span class="sxs-lookup"><span data-stu-id="af2bb-105">The database is using the simple recovery model.</span></span> <span data-ttu-id="af2bb-106">До сбоя все файловые группы работали в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="af2bb-106">Before the disaster, all the filegroups are online.</span></span> <span data-ttu-id="af2bb-107">Файловые группы `A` и `C` предназначены для считывания и записи, а файловые группы `B` предназначены только для чтения.</span><span class="sxs-lookup"><span data-stu-id="af2bb-107">Filegroups `A` and `C` are read/write, and filegroup `B` is read-only.</span></span> <span data-ttu-id="af2bb-108">Файловая группа `B` становится доступной только для чтения до последнего частичного резервного копирования, содержащего первичную файловую группу и вторичные файловые группы, предназначенные для считывания и записи, `A` и `C`.</span><span class="sxs-lookup"><span data-stu-id="af2bb-108">Filegroup `B` became read-only before the most recent partial backup, which contains the primary filegroup and the read/write secondary filegroups, `A` and `C`.</span></span> <span data-ttu-id="af2bb-109">Отдельная резервная копия файлов файловой группы `B` была создана после того, как файловая группа `B` стала доступной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="af2bb-109">After filegroup `B` became read-only, a separate file backup of filegroup `B` was taken.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="af2bb-110">Последовательности восстановления</span><span class="sxs-lookup"><span data-stu-id="af2bb-110">Restore Sequences</span></span>  
  
1.  <span data-ttu-id="af2bb-111">Частичное восстановление первичной файловой группы и файловых групп `A` и `C`.</span><span class="sxs-lookup"><span data-stu-id="af2bb-111">Partial restore of the primary and filegroups `A` and `C`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='A',FILEGROUP='C'   
       FROM partial_backup   
       WITH PARTIAL, RECOVERY;  
  
    ```  
  
     <span data-ttu-id="af2bb-112">На этом этапе первичная файловая группа и файловые группы `A` и `C` работают в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="af2bb-112">At this point, the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="af2bb-113">Все файлы из файловой группы `B` ожидают восстановления, а файловая группа работает в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="af2bb-113">All files in filegroup `B` are recovery pending, and the filegroup is offline.</span></span>  
  
2.  <span data-ttu-id="af2bb-114">Восстановление файловой группы `B`«в сети».</span><span class="sxs-lookup"><span data-stu-id="af2bb-114">Online restore of filegroup `B`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup WITH RECOVERY;  
  
    ```  
  
     <span data-ttu-id="af2bb-115">Теперь все файловые группы находятся в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="af2bb-115">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="af2bb-116">Дополнительные примеры</span><span class="sxs-lookup"><span data-stu-id="af2bb-116">Additional Examples</span></span>  
  
-   [<span data-ttu-id="af2bb-117">Пример. Поэтапное восстановление отдельных файловых групп &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="af2bb-117">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="af2bb-118">Пример. Оперативное восстановление доступного только для чтения файла &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="af2bb-118">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="af2bb-119">Пример. Поэтапное восстановление базы данных &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="af2bb-119">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="af2bb-120">Пример. Поэтапное восстановление только некоторых файловых групп &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="af2bb-120">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="af2bb-121">Пример. Оперативное восстановление файла, доступного для чтения и записи &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="af2bb-121">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="af2bb-122">Пример. Оперативное восстановление файла, доступного только для чтения &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="af2bb-122">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="af2bb-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="af2bb-123">See Also</span></span>  
 <span data-ttu-id="af2bb-124">[Восстановление в сети (SQL Server)](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="af2bb-124">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="af2bb-125">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="af2bb-125">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="af2bb-126">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="af2bb-126">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="af2bb-127">Поэтапное восстановление (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="af2bb-127">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
