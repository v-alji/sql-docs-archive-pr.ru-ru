---
title: Удаление моментального снимка базы данных (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- removing database snapshots
- deleting database snapshots
- database snapshots [SQL Server], deleting
ms.assetid: ad70ec97-d5fb-41aa-b72a-915e74b61b76
author: stevestein
ms.author: sstein
ms.openlocfilehash: e0d9d912a092e581fad7d3d53504309f63ba1806
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654331"
---
# <a name="drop-a-database-snapshot-transact-sql"></a><span data-ttu-id="270ed-102">удалить моментальный снимок базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="270ed-102">Drop a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="270ed-103">При удалении моментального снимка базы данных он удаляется из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и удаляются разреженные файлы, используемые моментальным снимком.</span><span class="sxs-lookup"><span data-stu-id="270ed-103">Dropping a database snapshot deletes the database snapshot from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and deletes the sparse files that are used by the snapshot.</span></span> <span data-ttu-id="270ed-104">При удалении моментального снимка базы данных все соединения пользователя с ним должны быть завершены.</span><span class="sxs-lookup"><span data-stu-id="270ed-104">When you drop a database snapshot, all user connections to it are terminated.</span></span>  
  
## <a name="security"></a><span data-ttu-id="270ed-105">Безопасность</span><span class="sxs-lookup"><span data-stu-id="270ed-105">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="270ed-106">Permissions</span><span class="sxs-lookup"><span data-stu-id="270ed-106">Permissions</span></span>  
 <span data-ttu-id="270ed-107">Любой пользователь с разрешениями DROP DATABASE может удалить моментальный снимок базы данных.</span><span class="sxs-lookup"><span data-stu-id="270ed-107">Any user with DROP DATABASE permissions can drop a database snapshot.</span></span>  
  
##  <a name="how-to-drop-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="270ed-108">Как удалить моментальный снимок базы данных (с помощью Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="270ed-108">How to Drop a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="270ed-109">**Удаление моментального снимка базы данных**</span><span class="sxs-lookup"><span data-stu-id="270ed-109">**To drop a database snapshot**</span></span>  
  
1.  <span data-ttu-id="270ed-110">Идентифицируйте моментальный снимок базы данных, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="270ed-110">Identify the database snapshot that you want to drop.</span></span> <span data-ttu-id="270ed-111">Просмотреть моментальные снимки в базе данных можно в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="270ed-111">You can view the snapshots on a database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="270ed-112">Дополнительные сведения см. в разделе [Просмотр моментального снимка базы данных (SQL Server)](view-a-database-snapshot-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="270ed-112">For more information, see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="270ed-113">Выполните инструкцию [DROP DATABASE](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) , указав имя моментального снимка базы данных, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="270ed-113">Issue a [DROP DATABASE](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) statement, specifying the name of the database snapshot to be dropped.</span></span> <span data-ttu-id="270ed-114">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="270ed-114">The syntax is as follows:</span></span>  
  
     <span data-ttu-id="270ed-115">DROP DATABASE *имя_моментального_снимка_базы_данных* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="270ed-115">DROP DATABASE *database_snapshot_name* [ **,**...*n* ]</span></span>  
  
     <span data-ttu-id="270ed-116">Где *имя_моментального_снимка_базы_данных* — имя удаляемого моментального снимка базы данных.</span><span class="sxs-lookup"><span data-stu-id="270ed-116">Where *database_snapshot_name* is the name of the database snapshot to be dropped.</span></span>  
  
####  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="270ed-117">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="270ed-117">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="270ed-118">Следующий код удаляет моментальный снимок базы данных, имеющий имя SalesSnapshot0600, без влияния на базу данных-источник.</span><span class="sxs-lookup"><span data-stu-id="270ed-118">This example drops a database snapshot named SalesSnapshot0600, without affecting the source database.</span></span>  
  
```  
DROP DATABASE SalesSnapshot0600 ;  
```  
  
 <span data-ttu-id="270ed-119">Все пользовательские соединения к SalesSnapshot0600 будут завершены, а все разреженные файлы файловой системы NTFS, используемые моментальным снимком, будут удалены.</span><span class="sxs-lookup"><span data-stu-id="270ed-119">Any user connections to SalesSnapshot0600 are terminated, and all of the NTFS file system sparse files used by the snapshot are deleted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="270ed-120">Сведения об использовании разреженных файлов для моментальных снимков баз данных см. в разделе [Моментальные снимки базы данных (SQL Server)](database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="270ed-120">For information about the use of sparse files by database snapshots, see [Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="270ed-121">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="270ed-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="270ed-122">Создание моментального снимка базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="270ed-122">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="270ed-123">Просмотр моментального снимка базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="270ed-123">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="270ed-124">Восстановление базы данных до состояния, сохраненного в моментальном снимке</span><span class="sxs-lookup"><span data-stu-id="270ed-124">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="270ed-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="270ed-125">See Also</span></span>  
 <span data-ttu-id="270ed-126">[DROP DATABASE (Transact-SQL)](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="270ed-126">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span></span>  
 [<span data-ttu-id="270ed-127">Моментальные снимки базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="270ed-127">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
