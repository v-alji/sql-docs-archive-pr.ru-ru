---
title: Пример. Оперативное восстановление файла только для чтения (модель полного восстановления) | Документация Майкрософт
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
ms.assetid: 7ea2d2af-086f-48dc-9636-38dc194c7090
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f493c88d64e6ed22e44f33f1442ae581daa8ed4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751224"
---
# <a name="example-online-restore-of-a-read-only-file-full-recovery-model"></a><span data-ttu-id="84f91-102">Пример Оперативное восстановление файла только для чтения (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="84f91-102">Example: Online Restore of a Read-Only File (Full Recovery Model)</span></span>
  <span data-ttu-id="84f91-103">Сведения в этом разделе относятся только к базам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , использующим полную модель восстановления, которые содержат несколько файлов или файловых групп.</span><span class="sxs-lookup"><span data-stu-id="84f91-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="84f91-104">В этом примере база данных `adb`, которая использует модель полного восстановления, содержит три файловые группы.</span><span class="sxs-lookup"><span data-stu-id="84f91-104">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="84f91-105">Файловая группа `A` доступна для записи и для чтения, файловые группы `B` и `C` доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="84f91-105">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="84f91-106">Изначально все файловые группы находятся в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="84f91-106">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="84f91-107">Необходимо восстановить файл `b1`с атрибутом «только для чтения» из файловой группы `B` базы данных `adb` .</span><span class="sxs-lookup"><span data-stu-id="84f91-107">A read-only file, `b1`, in filegroup `B` of database `adb` has to be restored.</span></span> <span data-ttu-id="84f91-108">Резервное копирование выполнялось после того, как файл был переведен в режим «только для чтения», поэтому резервные копии журналов не требуются.</span><span class="sxs-lookup"><span data-stu-id="84f91-108">A backup was taken since the file became read-only; therefore, log backups are not required.</span></span> <span data-ttu-id="84f91-109">Файловая группа `B` переводится в режим «вне сети» на период восстановления, однако оставшаяся часть базы данных остается в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="84f91-109">Filegroup `B` is offline for the duration of the restore, but the remainder of the database remains online.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="84f91-110">Последовательность восстановления</span><span class="sxs-lookup"><span data-stu-id="84f91-110">Restore Sequence</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84f91-111">Синтаксис последовательности восстановления в сети тот же самый, что и в случае последовательности восстановления вне сети.</span><span class="sxs-lookup"><span data-stu-id="84f91-111">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
 <span data-ttu-id="84f91-112">Чтобы восстановить файл, администратор базы данных использует следующую последовательность восстановления:</span><span class="sxs-lookup"><span data-stu-id="84f91-112">To restore the file, the database administrator uses the following restore sequence:</span></span>  
  
```  
RESTORE DATABASE adb FILE='b1' FROM filegroup_B_backup  
WITH RECOVERY   
```  
  
 <span data-ttu-id="84f91-113">Файловая группа B теперь находится в режиме в сети».</span><span class="sxs-lookup"><span data-stu-id="84f91-113">Filegroup B is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="84f91-114">Дополнительные примеры</span><span class="sxs-lookup"><span data-stu-id="84f91-114">Additional Examples</span></span>  
  
-   [<span data-ttu-id="84f91-115">Пример. Поэтапное восстановление базы данных &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="84f91-115">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="84f91-116">Пример. Поэтапное восстановление отдельных файловых групп &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="84f91-116">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="84f91-117">Пример. Оперативное восстановление доступного только для чтения файла &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="84f91-117">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="84f91-118">Пример. Поэтапное восстановление базы данных &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="84f91-118">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="84f91-119">Пример. Поэтапное восстановление только некоторых файловых групп &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="84f91-119">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="84f91-120">Пример. Оперативное восстановление файла, доступного для чтения и записи &#40;модель полного восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="84f91-120">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="84f91-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="84f91-121">See Also</span></span>  
 <span data-ttu-id="84f91-122">[Восстановление в сети (SQL Server)](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="84f91-122">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="84f91-123">[Обзор процессов восстановления (SQL Server)](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="84f91-123">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="84f91-124">[Восстановления файлов (модель полного восстановления)](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="84f91-124">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="84f91-125">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="84f91-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
