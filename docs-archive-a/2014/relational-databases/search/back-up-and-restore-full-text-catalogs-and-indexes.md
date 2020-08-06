---
title: Создание резервных копий и восстановление полнотекстовых каталогов и индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes [SQL Server], backing up
- full-text search [SQL Server], back up and restore
- recovery [full-text search]
- backups [SQL Server], full-text indexes
- full-text indexes [SQL Server], restoring
- restore operations [full-text search]
ms.assetid: 6a4080d9-e43f-4b7b-a1da-bebf654c1194
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c0df49c03325da375427c6566799f374fcc9dd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667664"
---
# <a name="back-up-and-restore-full-text-catalogs-and-indexes"></a><span data-ttu-id="f84fb-102">Создание резервных копий и восстановление полнотекстовых каталогов и индексов</span><span class="sxs-lookup"><span data-stu-id="f84fb-102">Back Up and Restore Full-Text Catalogs and Indexes</span></span>
  <span data-ttu-id="f84fb-103">В этом разделе рассказывается о создании резервных копий и восстановлении полнотекстовых индексов, созданных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f84fb-103">This topic explains how to back up and restore full-text indexes created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f84fb-104">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]полнотекстовый каталог — это логическое понятие, он не хранится в файловой группе.</span><span class="sxs-lookup"><span data-stu-id="f84fb-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the full-text catalog is a logical concept and does not reside in a filegroup.</span></span> <span data-ttu-id="f84fb-105">Следовательно, для того чтобы создать резервную копию полнотекстового каталога в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], следует определить все файловые группы, содержащие полнотекстовый индекс, принадлежащий каталогу.</span><span class="sxs-lookup"><span data-stu-id="f84fb-105">Therefore, to back up a full-text catalog in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must identify every filegroup that contains a full-text index that belongs to the catalog.</span></span> <span data-ttu-id="f84fb-106">Затем необходимо создать резервные копии этих файловых групп, одну за другой.</span><span class="sxs-lookup"><span data-stu-id="f84fb-106">Then you must back up those filegroups, one by one.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f84fb-107">Импортировать полнотекстовые каталоги можно при обновлении базы данных [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f84fb-107">It is possible to import full-text catalogs when upgrading a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database.</span></span> <span data-ttu-id="f84fb-108">Каждый полнотекстовый каталог — это файл базы данных в собственной файловой группе.</span><span class="sxs-lookup"><span data-stu-id="f84fb-108">Each imported full-text catalog is a database file in its own filegroup.</span></span> <span data-ttu-id="f84fb-109">Чтобы создать резервную копию импортированного каталога, достаточно создать резервную копию его файловой группы.</span><span class="sxs-lookup"><span data-stu-id="f84fb-109">To back up an imported catalog, simply back up its filegroup.</span></span> <span data-ttu-id="f84fb-110">Дополнительные сведения см. в разделе [Резервное копирование и восстановление полнотекстовых каталогов](https://go.microsoft.com/fwlink/?LinkID=121052)электронной документации по [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f84fb-110">For more information, see [Backing Up and Restoring Full-Text Catalogs](https://go.microsoft.com/fwlink/?LinkID=121052), in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Books Online.</span></span>  
  
##  <a name="backing-up-the-full-text-indexes-of-a-full-text-catalog"></a><a name="backingup"></a> <span data-ttu-id="f84fb-111">Резервное копирование полнотекстовых индексов полнотекстового каталога</span><span class="sxs-lookup"><span data-stu-id="f84fb-111">Backing Up the Full-Text Indexes of a Full-Text Catalog</span></span>  
  
###  <a name="finding-the-full-text-indexes-of-a-full-text-catalog"></a><a name="Find_FTIs_of_a_Catalog"></a> <span data-ttu-id="f84fb-112">Поиск полнотекстовых индексов полнотекстового каталога</span><span class="sxs-lookup"><span data-stu-id="f84fb-112">Finding the Full-Text Indexes of a Full-Text Catalog</span></span>  
 <span data-ttu-id="f84fb-113">Свойства полнотекстовых индексов можно получить с помощью инструкции [SELECT](/sql/t-sql/queries/select-transact-sql) , выбирающей столбцы из представлений каталога [sys.fulltext_indexes](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql) и [sys.fulltext_catalogs](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="f84fb-113">You can retrieve the properties of the full-text indexes by using the following [SELECT](/sql/t-sql/queries/select-transact-sql) statement, which selects columns from the [sys.fulltext_indexes](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql) and [sys.fulltext_catalogs](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql) catalog views.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @TableID int;  
SET @TableID = (SELECT OBJECT_ID('AdventureWorks2012.Production.Product'));  
SELECT object_name(@TableID), i.is_enabled, i.change_tracking_state,   
   i.has_crawl_completed, i.crawl_type, c.name as fulltext_catalog_name   
   FROM sys.fulltext_indexes i, sys.fulltext_catalogs c   
   WHERE i.fulltext_catalog_id = c.fulltext_catalog_id;  
GO  
```  
  

  
###  <a name="finding-the-filegroup-or-file-that-contains-a-full-text-index"></a><a name="Find_FG_of_FTI"></a> <span data-ttu-id="f84fb-114">Поиск файловой группы или файла, содержащего полнотекстовый индекс</span><span class="sxs-lookup"><span data-stu-id="f84fb-114">Finding the Filegroup or File That Contains a Full-Text Index</span></span>  
 <span data-ttu-id="f84fb-115">При создании полнотекстовый индекс размещается в одном из следующих мест.</span><span class="sxs-lookup"><span data-stu-id="f84fb-115">When a full-text index is created, it is placed in one of the following locations:</span></span>  
  
-   <span data-ttu-id="f84fb-116">В указанной пользователем файловой группе.</span><span class="sxs-lookup"><span data-stu-id="f84fb-116">A user-specified filegroup.</span></span>  
  
-   <span data-ttu-id="f84fb-117">В несекционированной таблице — в той же файловой группе, что и базовая таблица или представление.</span><span class="sxs-lookup"><span data-stu-id="f84fb-117">The same filegroup as base table or view, for a nonpartitioned table.</span></span>  
  
-   <span data-ttu-id="f84fb-118">В секционированной таблице — в первичной файловой группе.</span><span class="sxs-lookup"><span data-stu-id="f84fb-118">The primary filegroup, for a partitioned table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f84fb-119">Сведения о создании полнотекстового индекса см. в разделах [Создание полнотекстовых индексов и управление ими](create-and-manage-full-text-indexes.md) и [CREATE FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f84fb-119">For information about creating a full-text index, see [Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md) and [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="f84fb-120">Чтобы найти файловую группу полнотекстового индекса таблицы или представления, можно использовать следующий запрос, в котором *object_name* — это имя таблицы или представления:</span><span class="sxs-lookup"><span data-stu-id="f84fb-120">To find the filegroup of full-text index on a table or view, use the following query, where *object_name* is the name of the table or view:</span></span>  
  
```  
SELECT name FROM sys.filegroups f, sys.fulltext_indexes i   
   WHERE f.data_space_id = i.data_space_id   
      and i.object_id = object_id('object_name');  
GO  
  
```  
  

  
###  <a name="backing-up-the-filegroups-that-contain-full-text-indexes"></a><a name="Back_up_FTIs_of_FTC"></a> <span data-ttu-id="f84fb-121">Создание резервных копий файловых групп, содержащих полнотекстовые индексы</span><span class="sxs-lookup"><span data-stu-id="f84fb-121">Backing Up the Filegroups That Contain Full-Text Indexes</span></span>  
 <span data-ttu-id="f84fb-122">После того как были найдены файловые группы с индексами полнотекстового каталога, следует создать резервные копии всех файловых групп.</span><span class="sxs-lookup"><span data-stu-id="f84fb-122">After you find the filegroups that contain the indexes of a full-text catalog, you need back up each of the filegroups.</span></span> <span data-ttu-id="f84fb-123">Во время резервного копирования удалять или добавлять полнотекстовые каталоги нельзя.</span><span class="sxs-lookup"><span data-stu-id="f84fb-123">During the backup process, full-text catalogs may not be dropped or added.</span></span>  
  
 <span data-ttu-id="f84fb-124">При первом резервном копировании необходимо создать полную резервную копию файла.</span><span class="sxs-lookup"><span data-stu-id="f84fb-124">The first backup of a filegroup must be a full file backup.</span></span> <span data-ttu-id="f84fb-125">После того как для файловой группы была создана полная резервная копия файла, резервное копирование можно выполнять, сохраняя только изменения в файловой группе путем создания ряда из нескольких разностных резервных копий файла, основанных на полной резервной копии файла.</span><span class="sxs-lookup"><span data-stu-id="f84fb-125">After you have created a full file backup for a filegroup, you could back up only the changes in a filegroup by creating a series of one or more differential file backups that are based on the full file backup.</span></span>  
  
 <span data-ttu-id="f84fb-126">**Создание резервных копий файлов и файловых групп**</span><span class="sxs-lookup"><span data-stu-id="f84fb-126">**To back up files and filegroups**</span></span>  
  
-   [<span data-ttu-id="f84fb-127">Резервное копирование файлов и файловых групп (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f84fb-127">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="f84fb-128">BACKUP (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f84fb-128">BACKUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-transact-sql)  
  

  
##  <a name="restoring-a-full-text-index"></a><a name="Restore_FTI"></a> <span data-ttu-id="f84fb-129">Восстановление полнотекстового индекса</span><span class="sxs-lookup"><span data-stu-id="f84fb-129">Restoring a Full-Text Index</span></span>  
 <span data-ttu-id="f84fb-130">При восстановлении резервной копии файловой группы выполняется восстановление файлов полнотекстового индекса, а также остальных файлов файловой группы.</span><span class="sxs-lookup"><span data-stu-id="f84fb-130">Restoring a backed-up filegroup restores the full-text index files, as well as the other files in the filegroup.</span></span> <span data-ttu-id="f84fb-131">По умолчанию файловая группа восстанавливается в том месте на диске, где была создана резервная копия.</span><span class="sxs-lookup"><span data-stu-id="f84fb-131">By default, the filegroup is restored to the disk location on which the filegroup was backed up.</span></span>  
  
 <span data-ttu-id="f84fb-132">Если во время создания резервной копии таблица с полнотекстовым индексом находилась в режиме «в сети» и в ней производилось заполнение, то после восстановления заполнение продолжится.</span><span class="sxs-lookup"><span data-stu-id="f84fb-132">If a full-text indexed table was online and a population was running when the backup was created, the population is resumed after the restore.</span></span>  
  
 <span data-ttu-id="f84fb-133">**Восстановление файловой группы**</span><span class="sxs-lookup"><span data-stu-id="f84fb-133">**To restore a filegroup**</span></span>  
  
-   [<span data-ttu-id="f84fb-134">Восстановление файлов и файловых групп (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f84fb-134">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="f84fb-135">Восстановление файлов и файловых групп поверх существующих файлов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f84fb-135">Restore Files and Filegroups over Existing Files &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-and-filegroups-over-existing-files-sql-server.md)  
  
-   [<span data-ttu-id="f84fb-136">Восстановление файлов в новое место (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f84fb-136">Restore Files to a New Location &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="f84fb-137">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f84fb-137">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  

  
## <a name="see-also"></a><span data-ttu-id="f84fb-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="f84fb-138">See Also</span></span>  
 <span data-ttu-id="f84fb-139">[Управление и наблюдение за полнотекстовым поиском для экземпляра сервера](manage-and-monitor-full-text-search-for-a-server-instance.md) </span><span class="sxs-lookup"><span data-stu-id="f84fb-139">[Manage and Monitor Full-Text Search for a Server Instance](manage-and-monitor-full-text-search-for-a-server-instance.md) </span></span>  
 [<span data-ttu-id="f84fb-140">Обновление полнотекстового поиска</span><span class="sxs-lookup"><span data-stu-id="f84fb-140">Upgrade Full-Text Search</span></span>](upgrade-full-text-search.md)  
  
  
