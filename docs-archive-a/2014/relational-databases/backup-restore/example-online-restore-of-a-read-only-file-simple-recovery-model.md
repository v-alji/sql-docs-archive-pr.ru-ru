---
title: Пример. Оперативное восстановление файла только для чтения (простая модель восстановления) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restore sequences [SQL Server], online
- online restores [SQL Server], simple recovery model
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: 0c691fc6-9865-46a7-b055-8097424492d6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d84c920a2cb40866ba106b4d30d8e24c4caea611
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751223"
---
# <a name="example-online-restore-of-a-read-only-file-simple-recovery-model"></a><span data-ttu-id="2cfe9-102">Пример Оперативное восстановление файла только для чтения (простая модель восстановления)</span><span class="sxs-lookup"><span data-stu-id="2cfe9-102">Example: Online Restore of a Read-Only File (Simple Recovery Model)</span></span>
  <span data-ttu-id="2cfe9-103">Данный раздел относится только к базам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые содержат доступные только для чтения файловые группы в простой модели восстановления.</span><span class="sxs-lookup"><span data-stu-id="2cfe9-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the simple recovery model that contain a read-only filegroup.</span></span> <span data-ttu-id="2cfe9-104">При простой модели восстановления файл, доступный только для чтения, можно восстановить в режиме «в сети», если существует резервная копия файла, сделанная после того, как файл в последний раз стал доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="2cfe9-104">Under the simple recovery model, a read-only file can be restored online if a file backup exists that was taken since the file became read-only for the last time.</span></span>  
  
 <span data-ttu-id="2cfe9-105">В данном примере база данных `adb` содержит три файловые группы.</span><span class="sxs-lookup"><span data-stu-id="2cfe9-105">In this example, a database named `adb` contains three filegroups.</span></span> <span data-ttu-id="2cfe9-106">Файловая группа `A` предназначена для чтения и записи, а файловые группы `B` и `C` предназначены только для чтения.</span><span class="sxs-lookup"><span data-stu-id="2cfe9-106">Filegroup `A` is read/write, and filegroups `B` and `C` are read-only.</span></span> <span data-ttu-id="2cfe9-107">Изначально все файловые группы находятся в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="2cfe9-107">Initially, all of the filegroups are online.</span></span> <span data-ttu-id="2cfe9-108">Необходимо восстановить доступный только для чтения файл из файловой группы `B`, `b1`.</span><span class="sxs-lookup"><span data-stu-id="2cfe9-108">A read-only file in filegroup `B`, `b1`, has to be restored.</span></span> <span data-ttu-id="2cfe9-109">Администратор базы данных может восстановить его с помощью резервной копии, сделанной после того, как файл стал доступным только для чтения.</span><span class="sxs-lookup"><span data-stu-id="2cfe9-109">The database administrator can restore it by using a backup that was taken after the file became read-only.</span></span> <span data-ttu-id="2cfe9-110">На время восстановления файловая группа `B` будет переведена в режим «вне сети», однако остальная часть базы данных продолжит работать в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="2cfe9-110">For the duration of the restore, filegroup `B` will be offline, but the remainder of the database will remain online.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="2cfe9-111">Последовательность восстановления</span><span class="sxs-lookup"><span data-stu-id="2cfe9-111">Restore Sequence</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2cfe9-112">Синтаксис последовательности восстановления в сети тот же самый, что и в случае последовательности восстановления вне сети.</span><span class="sxs-lookup"><span data-stu-id="2cfe9-112">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
 <span data-ttu-id="2cfe9-113">Чтобы восстановить файл, администратор базы данных использует следующую последовательность восстановления:</span><span class="sxs-lookup"><span data-stu-id="2cfe9-113">To restore the file, the database administrator uses the following restore sequence:</span></span>  
  
```  
RESTORE DATABASE adb FILE='b1' FROM filegroup_B_backup   
WITH RECOVERY  
```  
  
 <span data-ttu-id="2cfe9-114">Файл в настоящий момент находится в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="2cfe9-114">The file is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="2cfe9-115">Дополнительные примеры</span><span class="sxs-lookup"><span data-stu-id="2cfe9-115">Additional Examples</span></span>  
  
-   [<span data-ttu-id="2cfe9-116">Пример. Поэтапное восстановление базы данных &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="2cfe9-116">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="2cfe9-117">Пример. Поэтапное восстановление отдельных файловых групп &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="2cfe9-117">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="2cfe9-118">Пример. Поэтапное восстановление базы данных &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="2cfe9-118">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="2cfe9-119">Пример. Поэтапное восстановление только некоторых файловых групп &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="2cfe9-119">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="2cfe9-120">Пример. Оперативное восстановление файла, доступного для чтения и записи &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="2cfe9-120">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="2cfe9-121">Пример. Оперативное восстановление файла, доступного только для чтения &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="2cfe9-121">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="2cfe9-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="2cfe9-122">See Also</span></span>  
 <span data-ttu-id="2cfe9-123">[Восстановление в сети (SQL Server)](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2cfe9-123">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="2cfe9-124">[Поэтапное восстановление (SQL Server)](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2cfe9-124">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="2cfe9-125">[Восстановление файлов (простая модель восстановления)](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="2cfe9-125">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="2cfe9-126">[Обзор процессов восстановления (SQL Server)](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2cfe9-126">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="2cfe9-127">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2cfe9-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
