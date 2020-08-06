---
title: Пример. автономное восстановление основной и другой файловой группы (модель полного восстановления) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- offline restores [SQL Server]
- restore sequences [SQL Server], offline
ms.assetid: 7d6c50eb-dc84-4d66-855a-0b5f1bd89737
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f845927fdd74fba476139fccbf9a5fa112d434e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667739"
---
# <a name="example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model"></a><span data-ttu-id="95a71-102">Пример Автономное восстановление основной и еще одной файловой группы (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="95a71-102">Example: Offline Restore of Primary and One Other Filegroup (Full Recovery Model)</span></span>
  <span data-ttu-id="95a71-103">Данный раздел относится только к базам данных с моделью полного восстановления, содержащим несколько файловых групп.</span><span class="sxs-lookup"><span data-stu-id="95a71-103">This topic is relevant only for databases under the full recovery model that contain multiple filegroups.</span></span>  
  
 <span data-ttu-id="95a71-104">В данном примере база данных `adb` содержит три файловые группы.</span><span class="sxs-lookup"><span data-stu-id="95a71-104">In this example, a database named `adb` contains three filegroups.</span></span> <span data-ttu-id="95a71-105">Файловые группы `A` и `C` предназначены для считывания и записи, а файловые группы `B` предназначены только для чтения.</span><span class="sxs-lookup"><span data-stu-id="95a71-105">Filegroups `A` and `C` are read/write, and filegroup `B` is read-only.</span></span> <span data-ttu-id="95a71-106">Первичная файловая группа и файловая группа `B` повреждены, но файловые группы `A` и `C` не затронуты.</span><span class="sxs-lookup"><span data-stu-id="95a71-106">The primary filegroup and filegroup `B` are damaged, but filegroups `A` and `C` are intact.</span></span> <span data-ttu-id="95a71-107">До аварии все файловые группы находились в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="95a71-107">Before the disaster, all the filegroups were online.</span></span>  
  
 <span data-ttu-id="95a71-108">Администратор базы данных принял решение восстановить первичную файловую группу и файловую группу `B`.</span><span class="sxs-lookup"><span data-stu-id="95a71-108">The database administrator decides to restore and recover the primary filegroup and filegroup `B`.</span></span> <span data-ttu-id="95a71-109">Используется полная модель восстановления базы данных, поэтому перед началом восстановления необходимо сделать резервную копию заключительного фрагмента журнала базы данных.</span><span class="sxs-lookup"><span data-stu-id="95a71-109">The database is using the full recovery model; therefore, before the restore starts, a tail-log backup must be taken of the database.</span></span> <span data-ttu-id="95a71-110">Когда база данных переходит в режим «в сети», файловые группы `A` и `C` автоматически переходят в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="95a71-110">When the database comes on line, Filegroups `A` and `C` are automatically brought online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95a71-111">В последовательности восстановления вне сети предусмотрено меньше шагов, чем для восстановления файлов в сети только для чтения.</span><span class="sxs-lookup"><span data-stu-id="95a71-111">The offline restore sequence has fewer steps than an online restore of a read-only file.</span></span> <span data-ttu-id="95a71-112">Пример см. в разделе [Пример. Оперативное восстановление файла, доступного только для чтения &#40;модель полного восстановления&#41;](example-online-restore-of-a-read-only-file-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="95a71-112">For an example, see [Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;](example-online-restore-of-a-read-only-file-full-recovery-model.md).</span></span> <span data-ttu-id="95a71-113">Однако в процессе выполнения последовательности в режиме «вне сети» находится вся база данных.</span><span class="sxs-lookup"><span data-stu-id="95a71-113">However, the whole database is offline for the duration of the sequence.</span></span>  
  
## <a name="tail-log-backup"></a><span data-ttu-id="95a71-114">Резервная копия заключительного фрагмента журнала</span><span class="sxs-lookup"><span data-stu-id="95a71-114">Tail-Log Backup</span></span>  
 <span data-ttu-id="95a71-115">Перед тем как восстановить базу данных из копии, администратор этой базы данных должен создать резервную копию заключительного фрагмента журнала.</span><span class="sxs-lookup"><span data-stu-id="95a71-115">Before restoring the database, the database administrator must back up the tail of the log.</span></span> <span data-ttu-id="95a71-116">Поскольку база данных повреждена, для создания резервной копии заключительного фрагмента журнала требуется применение параметра NO_TRUNCATE:</span><span class="sxs-lookup"><span data-stu-id="95a71-116">Because the database is damaged, creating the tail-log backup requires using the NO_TRUNCATE option:</span></span>  
  
```  
BACKUP LOG adb TO tailLogBackup   
   WITH NORECOVERY, NO_TRUNCATE  
```  
  
 <span data-ttu-id="95a71-117">Резервная копия заключительного фрагмента журнала — это последняя резервная копия, используемая в следующих последовательностях восстановления.</span><span class="sxs-lookup"><span data-stu-id="95a71-117">The tail-log backup is the last backup that is applied in the following restore sequences.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="95a71-118">Последовательность восстановления</span><span class="sxs-lookup"><span data-stu-id="95a71-118">Restore Sequence</span></span>  
 <span data-ttu-id="95a71-119">Чтобы восстановить первичную файловую группу и файловую группу `B`, администратор базы данных использует последовательность восстановления без параметра PARTIAL, как указано ниже:</span><span class="sxs-lookup"><span data-stu-id="95a71-119">To restore the primary filegroup and filegroup `B`, the database administrator uses a restore sequence without the PARTIAL option, as follows:</span></span>  
  
```  
RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
WITH NORECOVERY  
RESTORE DATABASE adb FILEGROUP='B' FROM backup2   
WITH NORECOVERY  
RESTORE LOG adb FROM backup3 WITH NORECOVERY  
RESTORE LOG adb FROM backup4 WITH NORECOVERY  
RESTORE LOG adb FROM backup5 WITH NORECOVERY  
RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
```  
  
 <span data-ttu-id="95a71-120">Файлы, которые не затрагивает процесс восстановления, автоматически переводятся в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="95a71-120">The files that are not restored are automatically brought online.</span></span> <span data-ttu-id="95a71-121">Сейчас все файловые группы переведены в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="95a71-121">All the filegroups are now online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95a71-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="95a71-122">See Also</span></span>  
 <span data-ttu-id="95a71-123">[Восстановление в сети (SQL Server)](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95a71-123">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="95a71-124">[Поэтапное восстановление (SQL Server)](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95a71-124">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="95a71-125">[Восстановления файлов (модель полного восстановления)](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="95a71-125">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="95a71-126">[Применение резервных копий журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95a71-126">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="95a71-127">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="95a71-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
