---
title: Просмотр моментального снимка базы данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], viewing
- displaying database snapshots
- viewing database snapshots
ms.assetid: 123f19b2-0850-4033-8507-59ebdfb368ee
author: stevestein
ms.author: sstein
ms.openlocfilehash: 92c5c557656e87be562e9d5477f14f66b2c39e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749972"
---
# <a name="view-a-database-snapshot-sql-server"></a><span data-ttu-id="4e5c3-102">Просмотр моментального снимка базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4e5c3-102">View a Database Snapshot (SQL Server)</span></span>
  <span data-ttu-id="4e5c3-103">В этом разделе объясняется, как просмотреть моментальный снимок базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e5c3-103">This topic explains how to view a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshot using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e5c3-104">Создание, возврат к предыдущему состоянию и удаление моментального снимка базы данных необходимо производить с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e5c3-104">To create, revert to, or delete a database snapshot, you must use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4e5c3-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="4e5c3-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4e5c3-106">**Просмотр моментального снимка базы данных с помощью:**</span><span class="sxs-lookup"><span data-stu-id="4e5c3-106">**To view a database snapshot, using:**</span></span>  
  
     [<span data-ttu-id="4e5c3-107">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e5c3-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4e5c3-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4e5c3-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4e5c3-109">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e5c3-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4e5c3-110">**Просмотр моментального снимка базы данных**</span><span class="sxs-lookup"><span data-stu-id="4e5c3-110">**To view a database snapshot**</span></span>  
  
1.  <span data-ttu-id="4e5c3-111">В обозревателе объектов подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="4e5c3-111">In Object Explorer, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4e5c3-112">Разверните узел **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="4e5c3-112">Expand **Databases.**</span></span>  
  
3.  <span data-ttu-id="4e5c3-113">Разверните узел **Моментальные снимки базы данных**и выберите моментальный снимок, который необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="4e5c3-113">Expand **Database Snapshots**, and select the snapshot you want to view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4e5c3-114">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4e5c3-114">Using Transact-SQL</span></span>  
 <span data-ttu-id="4e5c3-115">**Просмотр моментального снимка базы данных**</span><span class="sxs-lookup"><span data-stu-id="4e5c3-115">**To view a database snapshot**</span></span>  
  
1.  <span data-ttu-id="4e5c3-116">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e5c3-116">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4e5c3-117">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="4e5c3-117">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4e5c3-118">Чтобы просмотреть список моментальных снимков базы данных для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], выполните запрос столбца **source_database_id** представления каталога [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) по значениям, отличным от NULL.</span><span class="sxs-lookup"><span data-stu-id="4e5c3-118">To list the database snapshots of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], query the **source_database_id** column of the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view for non-NULL values.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4e5c3-119">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="4e5c3-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4e5c3-120">Создание моментального снимка базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4e5c3-120">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="4e5c3-121">Восстановление базы данных до состояния, сохраненного в моментальном снимке</span><span class="sxs-lookup"><span data-stu-id="4e5c3-121">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  
-   [<span data-ttu-id="4e5c3-122">Удаление моментального снимка базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4e5c3-122">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="4e5c3-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e5c3-123">See Also</span></span>  
 [<span data-ttu-id="4e5c3-124">Моментальные снимки базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4e5c3-124">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
