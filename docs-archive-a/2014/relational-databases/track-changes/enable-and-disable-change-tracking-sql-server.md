---
title: Включение и отключение отслеживания изменений (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server], disabling
- data changes [SQL Server]
- change tracking [SQL Server], enabling
- tracking data changes [SQL Server]
- change tracking [SQL Server], configuring
- data [SQL Server], changing
ms.assetid: 1c92ec7e-ae53-4498-8bfd-c66a42a24d54
author: rothja
ms.author: jroth
ms.openlocfilehash: 402c63ae03df14e3a725fbc440575f5233d502f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658667"
---
# <a name="enable-and-disable-change-tracking-sql-server"></a><span data-ttu-id="da189-102">Включение и отключение отслеживания изменений (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="da189-102">Enable and Disable Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="da189-103">В этом разделе описано, как включить и отключить отслеживания изменений для базы данных и таблицы.</span><span class="sxs-lookup"><span data-stu-id="da189-103">This topic describes how to enable and disable change tracking for a database and a table.</span></span>  
  
## <a name="enable-change-tracking-for-a-database"></a><span data-ttu-id="da189-104">Включение отслеживания изменений для базы данных</span><span class="sxs-lookup"><span data-stu-id="da189-104">Enable Change Tracking for a Database</span></span>  
 <span data-ttu-id="da189-105">Прежде чем начать отслеживание изменений, его надо включить на уровне базы данных.</span><span class="sxs-lookup"><span data-stu-id="da189-105">Before you can use change tracking, you must enable change tracking at the database level.</span></span> <span data-ttu-id="da189-106">В следующем примере показано, как включить отслеживание изменений с помощью инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="da189-106">The following example shows how to enable change tracking by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET CHANGE_TRACKING = ON  
(CHANGE_RETENTION = 2 DAYS, AUTO_CLEANUP = ON)  
```  
  
 <span data-ttu-id="da189-107">Включить отслеживание изменений можно также в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , в диалоговом окне [Свойства базы данных (страница "Отслеживание изменений")](../databases/database-properties-changetracking-page.md) .</span><span class="sxs-lookup"><span data-stu-id="da189-107">You can also enable change tracking in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="da189-108">При включении отслеживания изменений, а также в любое время в дальнейшем можно указать и изменить значения параметров CHANGE_RETENTION и AUTO_CLEANUP.</span><span class="sxs-lookup"><span data-stu-id="da189-108">You can specify the CHANGE_RETENTION and AUTO_CLEANUP options when you enable change tracking, and you can change the values at any time after change tracking is enabled.</span></span>  
  
 <span data-ttu-id="da189-109">Параметр срока хранения изменений определяет период времени, в течение которого сохраняются данные отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="da189-109">The change retention value specifies the time period for which change tracking information is kept.</span></span> <span data-ttu-id="da189-110">Данные отслеживания изменений, срок хранения которых истек, периодически удаляются.</span><span class="sxs-lookup"><span data-stu-id="da189-110">Change tracking information that is older than this time period is removed periodically.</span></span> <span data-ttu-id="da189-111">При установке этого значения необходимо учитывать частоту синхронизации приложений с таблицами в базе данных.</span><span class="sxs-lookup"><span data-stu-id="da189-111">When you are setting this value, you should consider how often applications will synchronize with the tables in the database.</span></span> <span data-ttu-id="da189-112">Указанный срок хранения должен быть не меньше максимального периода времени между синхронизациями.</span><span class="sxs-lookup"><span data-stu-id="da189-112">The specified retention period must be at least as long as the maximum time period between synchronizations.</span></span> <span data-ttu-id="da189-113">Если приложение получает сведения об изменениях через более длительные интервалы, возвращаемые результаты могут оказаться неверными, поскольку часть сведений об изменениях могла уже быть удалена.</span><span class="sxs-lookup"><span data-stu-id="da189-113">If an application obtains changes at longer intervals, the results that are returned might be incorrect because some of the change information has probably been removed.</span></span> <span data-ttu-id="da189-114">Чтобы избежать неверных результатов, приложение может определить, не является ли интервал между синхронизациями чрезмерно большим, с помощью системной функции CHANGE_TRACKING_MIN_VALID_VERSION.</span><span class="sxs-lookup"><span data-stu-id="da189-114">To avoid obtaining incorrect results, an application can use the CHANGE_TRACKING_MIN_VALID_VERSION system function to determine whether the interval between synchronizations has been too long.</span></span>  
  
 <span data-ttu-id="da189-115">Параметр AUTO_CLEANUP используется для включения и отключения задачи очистки, в процессе выполнения которой удаляются старые данные отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="da189-115">You can use the AUTO_CLEANUP option to enable or disable the cleanup task that removes old change tracking information.</span></span> <span data-ttu-id="da189-116">Он может оказаться полезным при возникновении временной проблемы, которая мешает синхронизации приложений и вызывает необходимость приостановки процесса удаления устаревших данных отслеживания изменений на период своего разрешения.</span><span class="sxs-lookup"><span data-stu-id="da189-116">This can be useful when there is a temporary problem that prevents applications from synchronizing and the process for removing change tracking information older than the retention period must be paused until the problem is resolved.</span></span>  
  
 <span data-ttu-id="da189-117">При этом следует учесть следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="da189-117">For any database that uses change tracking, be aware of the following:</span></span>  
  
-   <span data-ttu-id="da189-118">При отслеживании изменений уровень совместимости базы данных должен быть не ниже 90.</span><span class="sxs-lookup"><span data-stu-id="da189-118">To use change tracking, the database compatibility level must be set to 90 or greater.</span></span> <span data-ttu-id="da189-119">Если уровень совместимости базы данных менее 90, то можно настроить отслеживание изменений.</span><span class="sxs-lookup"><span data-stu-id="da189-119">If a database has a compatibility level of less than 90, you can configure change tracking.</span></span> <span data-ttu-id="da189-120">Однако функция CHANGETABLE, используемая для получения сведений об отслеживании изменений, возвратит ошибку.</span><span class="sxs-lookup"><span data-stu-id="da189-120">However, the CHANGETABLE function, which is used to obtain change tracking information, will return an error.</span></span>  
  
-   <span data-ttu-id="da189-121">Простейший способ обеспечения согласованности всех данных отслеживания изменений — изоляция моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="da189-121">Using snapshot isolation is the easiest way for you to help ensure that all change tracking information is consistent.</span></span> <span data-ttu-id="da189-122">По этой причине настоятельно рекомендуется включить для базы данных изоляцию моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="da189-122">For this reason, we strongly recommend that snapshot isolation be set to ON for the database.</span></span> <span data-ttu-id="da189-123">Дополнительные сведения см. в разделе [Работа с отслеживанием изменений (SQL Server)](work-with-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="da189-123">For more information, see [Work with Change Tracking &#40;SQL Server&#41;](work-with-change-tracking-sql-server.md).</span></span>  
  
## <a name="enable-change-tracking-for-a-table"></a><span data-ttu-id="da189-124">Включение отслеживания изменений для таблицы</span><span class="sxs-lookup"><span data-stu-id="da189-124">Enable Change Tracking for a Table</span></span>  
 <span data-ttu-id="da189-125">Отслеживание изменений должно быть включено для каждой отслеживаемой таблицы.</span><span class="sxs-lookup"><span data-stu-id="da189-125">Change tracking must be enabled for each table that you want tracked.</span></span> <span data-ttu-id="da189-126">Если отслеживание изменений включено, ведется сбор сведений об отслеживании для всех строк в таблице, на которую влияет операция DML.</span><span class="sxs-lookup"><span data-stu-id="da189-126">When change tracking is enabled, change tracking information is maintained for all rows in the table that are affected by a DML operation.</span></span>  
  
 <span data-ttu-id="da189-127">В следующем примере показано, как настроить отслеживание изменений для таблицы с помощью инструкции [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="da189-127">The following example shows how to enable change tracking for a table by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
```sql  
ALTER TABLE Person.Contact  
ENABLE CHANGE_TRACKING  
WITH (TRACK_COLUMNS_UPDATED = ON)  
```  
  
 <span data-ttu-id="da189-128">Включить отслеживание изменений можно также в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , в диалоговом окне [Свойства базы данных (страница "Отслеживание изменений")](../databases/database-properties-changetracking-page.md) .</span><span class="sxs-lookup"><span data-stu-id="da189-128">You can also enable change tracking for a table in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="da189-129">Если параметр TRACK_COLUMNS_UPDATED установлен в значение ON, компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] сохраняет во внутренней таблице отслеживания дополнительные сведения о столбцах, которые были обновлены.</span><span class="sxs-lookup"><span data-stu-id="da189-129">When the TRACK_COLUMNS_UPDATED option is set to ON, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] stores extra information about which columns were updated to the internal change tracking table.</span></span> <span data-ttu-id="da189-130">Отслеживание столбцов позволяет приложению синхронизировать только те столбцы, которые были обновлены.</span><span class="sxs-lookup"><span data-stu-id="da189-130">Column tracking can enable an application to synchronize only those columns that were updated.</span></span> <span data-ttu-id="da189-131">Это может повысить эффективность и производительность.</span><span class="sxs-lookup"><span data-stu-id="da189-131">This can improve efficiency and performance.</span></span> <span data-ttu-id="da189-132">Но поскольку отслеживание столбцов требует дополнительного места на диске, по умолчанию этот параметр имеет значение OFF.</span><span class="sxs-lookup"><span data-stu-id="da189-132">However, because maintaining column tracking information adds some extra storage overhead, this option is set to OFF by default.</span></span>  
  
## <a name="disable-change-tracking-for-a-database-or-table"></a><span data-ttu-id="da189-133">Отключение отслеживания изменений для базы данных или таблицы</span><span class="sxs-lookup"><span data-stu-id="da189-133">Disable Change Tracking for a Database or Table</span></span>  
 <span data-ttu-id="da189-134">Перед отключением отслеживания изменений для базы данных необходимо отключить его для всех таблиц в этой базе.</span><span class="sxs-lookup"><span data-stu-id="da189-134">Change tracking must first be disabled for all change-tracked tables before change tracking can be set to OFF for the database.</span></span> <span data-ttu-id="da189-135">Чтобы определить, для каких таблиц было включено отслеживание изменений, воспользуйтесь представлением каталога [sys.change_tracking_tables](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) .</span><span class="sxs-lookup"><span data-stu-id="da189-135">To determine the tables that have change tracking enabled for a database, use the [sys.change_tracking_tables](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) catalog view.</span></span>  
  
 <span data-ttu-id="da189-136">Если ни для одной из таблиц базы данных отслеживание изменений не настроено, то оно может быть отключено и на уровне базы данных.</span><span class="sxs-lookup"><span data-stu-id="da189-136">When no tables in a database track changes, you can disable change tracking for the database.</span></span> <span data-ttu-id="da189-137">В следующем примере показано, как отключить отслеживание изменений для базы данных с помощью инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="da189-137">The following example shows how to disable change tracking for a database by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET CHANGE_TRACKING = OFF  
```  
  
 <span data-ttu-id="da189-138">В следующем примере показано, как отключить отслеживание изменений для таблицы с помощью инструкции [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="da189-138">The following example shows how to disable change tracking for a table by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
```sql  
ALTER TABLE Person.Contact  
DISABLE CHANGE_TRACKING;  
```  
  
## <a name="see-also"></a><span data-ttu-id="da189-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="da189-139">See Also</span></span>  
 <span data-ttu-id="da189-140">[Свойства базы данных (страница "Отслеживание изменений")](../databases/database-properties-changetracking-page.md) </span><span class="sxs-lookup"><span data-stu-id="da189-140">[Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) </span></span>  
 <span data-ttu-id="da189-141">[Параметры ALTER DATABASE SET (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span><span class="sxs-lookup"><span data-stu-id="da189-141">[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span></span>  
 <span data-ttu-id="da189-142">[sys.change_tracking_databases (Transact-SQL)](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-databases) </span><span class="sxs-lookup"><span data-stu-id="da189-142">[sys.change_tracking_databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-databases) </span></span>  
 <span data-ttu-id="da189-143">[sys.change_tracking_tables (Transact-SQL)](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) </span><span class="sxs-lookup"><span data-stu-id="da189-143">[sys.change_tracking_tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) </span></span>  
 <span data-ttu-id="da189-144">[Отслеживание измененных данных (SQL Server)](track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="da189-144">[Track Data Changes &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="da189-145">[Об отслеживании изменений (SQL Server)](../track-changes/about-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="da189-145">[About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="da189-146">[Работа с информацией об изменениях (SQL Server)](work-with-change-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="da189-146">[Work with Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span></span>  
 [<span data-ttu-id="da189-147">Управление отслеживанием изменений (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="da189-147">Manage Change Tracking &#40;SQL Server&#41;</span></span>](manage-change-tracking-sql-server.md)  
  
  
