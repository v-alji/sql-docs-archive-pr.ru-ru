---
title: Частичные резервные копии (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- partial backups [SQL Server]
- READ_WRITE_FILEGROUPS option
- database backups [SQL Server], about backing up databases
ms.assetid: fe6b6bb1-38d0-46c4-bab8-31df14e8999c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0c03cf2fb4d3af6fe87459e881e26c48cfacc232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666697"
---
# <a name="partial-backups-sql-server"></a><span data-ttu-id="643a0-102">Частичные резервные копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="643a0-102">Partial Backups (SQL Server)</span></span>
  <span data-ttu-id="643a0-103">Все модели восстановления в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживают частичные резервные копии, поэтому данный раздел относится ко всем базам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="643a0-103">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recovery models support partial backups, so this topic is relevant for all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="643a0-104">Однако частичные резервные копии предназначены для использования в простой модели восстановления с целью повышения гибкости при резервном копировании очень больших баз данных, которые содержат одну или несколько файловых групп только для чтения.</span><span class="sxs-lookup"><span data-stu-id="643a0-104">However, partial backups are designed for use under the simple recovery model to improve flexibility for backing up very large databases that contain one or more read-only filegroups.</span></span>  
  
 <span data-ttu-id="643a0-105">Частичные резервные копии могут оказаться полезны в тех случаях, когда необходимо исключить файловые группы только для чтения.</span><span class="sxs-lookup"><span data-stu-id="643a0-105">Partial backups are useful whenever you want to exclude read-only filegroups.</span></span> <span data-ttu-id="643a0-106">*Частичная резервная копия* отличается от полной тем, что содержит в себе не все файловые группы.</span><span class="sxs-lookup"><span data-stu-id="643a0-106">A *partial backup* resembles a full database backup, but a partial backup does not contain all the filegroups.</span></span> <span data-ttu-id="643a0-107">Вместо этого (для баз данных, доступных для записи и чтения) в нее включаются все данные первичной файловой группы, всех файловых групп с режимом доступа «чтение и запись» и (дополнительно) одного или нескольких файлов только для чтения.</span><span class="sxs-lookup"><span data-stu-id="643a0-107">Instead, for a read-write database, a partial backup contains the data in the primary filegroup, every read-write filegroup, and, optionally, one or more read-only files.</span></span> <span data-ttu-id="643a0-108">Частичная резервная копия базы данных, доступной только для чтения, содержит только первичную файловую группу.</span><span class="sxs-lookup"><span data-stu-id="643a0-108">A partial backup of a read-only database contains only the primary filegroup.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="643a0-109">Если база данных только для чтения переведена в режим чтения и записи после создания частичной резервной копии, то могут остаться некоторые файловые группы для чтения и записи, не вошедшие в частичную резервную копию.</span><span class="sxs-lookup"><span data-stu-id="643a0-109">If a read-only database is changed to read/write after a partial backup, there might be read/write secondary filegroups that are not in the partial backup.</span></span> <span data-ttu-id="643a0-110">Если это так, то попытка частичного разностного резервного копирования завершится неуспешно.</span><span class="sxs-lookup"><span data-stu-id="643a0-110">In this case, if you try to take a differential partial backup, the backup fails.</span></span> <span data-ttu-id="643a0-111">Перед созданием частичной разностной резервной копии базы данных необходимо создать другую частичную резервную копию.</span><span class="sxs-lookup"><span data-stu-id="643a0-111">Before you can take a differential partial backup of the database, you must take another partial backup.</span></span> <span data-ttu-id="643a0-112">Новая частичная резервная копия будет содержать все вторичные файловые группы для чтения и записи и может служить основой для создания частичных разностных резервных копий.</span><span class="sxs-lookup"><span data-stu-id="643a0-112">The new partial backup contains every read/write secondary filegroup and can serve as the base for differential partial backups.</span></span>  
  
 <span data-ttu-id="643a0-113">Резервные копии файловых групп, доступных только для чтения, могут совмещаться с частичными резервными копиями.</span><span class="sxs-lookup"><span data-stu-id="643a0-113">File backups of read-only filegroups can be combined with partial backups.</span></span> <span data-ttu-id="643a0-114">Сведения о резервных копиях файлов см. в статье [Полные резервные копии файлов (SQL Server)](full-file-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="643a0-114">For information about file backups, see [Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="643a0-115">Частичная резервная копия может служить *базовой копией для разностного копирования* для частичных разностных резервных копий.</span><span class="sxs-lookup"><span data-stu-id="643a0-115">A partial backup can serve as the *differential base* for differential partial backups.</span></span> <span data-ttu-id="643a0-116">Дополнительные сведения см. в разделе [Разностные резервные копии (SQL Server)](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="643a0-116">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="643a0-117">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="643a0-117">Related Tasks</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="643a0-118">Частичные резервные копии не поддерживаются в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и мастером планов обслуживания.</span><span class="sxs-lookup"><span data-stu-id="643a0-118">Partial backups are not supported by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the Maintenance Plan Wizard.</span></span>  
  
 <span data-ttu-id="643a0-119">**Создание частичной резервной копии**</span><span class="sxs-lookup"><span data-stu-id="643a0-119">**To create a partial backup**</span></span>  
  
-   <span data-ttu-id="643a0-120">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) (при необходимости, параметр READ_WRITE_FILEGROUPS; FILEGROUP)</span><span class="sxs-lookup"><span data-stu-id="643a0-120">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) (READ_WRITE_FILEGROUPS; FILEGROUP option, if needed)</span></span>  
  
 <span data-ttu-id="643a0-121">**Использование частичной резервной копии в последовательности восстановления**</span><span class="sxs-lookup"><span data-stu-id="643a0-121">**To use a partial backup in a restore sequence**</span></span>  
  
-   [<span data-ttu-id="643a0-122">Пример. Поэтапное восстановление базы данных &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="643a0-122">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="643a0-123">Пример. Поэтапное восстановление отдельных файловых групп &#40;простая модель восстановления&#41;</span><span class="sxs-lookup"><span data-stu-id="643a0-123">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="643a0-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="643a0-124">See Also</span></span>  
 <span data-ttu-id="643a0-125">[Общие сведения о резервном копировании (SQL Server)](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="643a0-125">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="643a0-126">[Восстановление файлов (простая модель восстановления)](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="643a0-126">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="643a0-127">Поэтапное восстановление (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="643a0-127">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
