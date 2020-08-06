---
title: Просмотр свойств группы доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server]
ms.assetid: 61243c87-bd62-4510-863f-2a8f347caf1f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b7d1f57a9bd29b6c65160ec9a163bc77dfca48b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657895"
---
# <a name="view-availability-group-properties-sql-server"></a><span data-ttu-id="461ae-102">Просмотр свойств группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-102">View Availability Group Properties (SQL Server)</span></span>
  <span data-ttu-id="461ae-103">В этом разделе описывается просмотр свойств группы доступности для группы доступности AlwaysOn с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="461ae-103">This topic describes how to view the properties of an availability group for an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  

  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="461ae-104">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="461ae-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="461ae-105">**Просмотр и изменение свойств группы доступности**</span><span class="sxs-lookup"><span data-stu-id="461ae-105">**To view and change the properties an availability group**</span></span>  
  
1.  <span data-ttu-id="461ae-106">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена первичная реплика, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="461ae-106">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="461ae-107">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="461ae-107">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="461ae-108">Щелкните правой кнопкой мыши группу доступности, свойства которой нужно просмотреть, и выберите команду **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="461ae-108">Right-click the availability group whose properties you want to view, and select the **Properties** command.</span></span>  
  
4.  <span data-ttu-id="461ae-109">В диалоговом окне **Свойства группы доступности** просмотреть и в некоторых случаях изменить свойства выбранной группы доступности можно на страницах **Общие** и **Настройки резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="461ae-109">In the **Availability Group Properties** dialog box, use the **General** and **Backup Preferences** pages to view and, in some cases, change properties of the selected availability group.</span></span> <span data-ttu-id="461ae-110">Дополнительные сведения см. в статье [Свойства группы доступности и создание группы доступности (страница "Общие")](availability-group-properties-new-availability-group-general-page.md) и [Свойства группы доступности и создание группы доступности (страница "Параметры резервного копирования")](availability-group-properties-new-availability-group-backup-preferences-page.md).</span><span class="sxs-lookup"><span data-stu-id="461ae-110">For more information, see [Availability Group Properties and New Availability Group &#40;General Page&#41;](availability-group-properties-new-availability-group-general-page.md) and [Availability Group Properties: New Availability Group &#40;Backup Preferences Page&#41;](availability-group-properties-new-availability-group-backup-preferences-page.md).</span></span>  
  
     <span data-ttu-id="461ae-111">На странице **Разрешения** можно просмотреть текущие имена входа, роли и явные разрешения, связанные с группой доступности.</span><span class="sxs-lookup"><span data-stu-id="461ae-111">Use the **Permissions** page to view the current logins, roles, and explicit permissions associated with the availability group.</span></span> <span data-ttu-id="461ae-112">Дополнительные сведения см. в статье [Permissions or Securables Page](../../../relational-databases/security/permissions-or-securables-page.md).</span><span class="sxs-lookup"><span data-stu-id="461ae-112">For more information, see [Permissions or Securables Page](../../../relational-databases/security/permissions-or-securables-page.md).</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="461ae-113">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="461ae-113">Using Transact-SQL</span></span>  
 <span data-ttu-id="461ae-114">**Просмотр свойств и состояния группы доступности**</span><span class="sxs-lookup"><span data-stu-id="461ae-114">**To view the properties and state of an availability group**</span></span>  
  
 <span data-ttu-id="461ae-115">Чтобы запросить свойства и состояния групп доступности, для которых на экземпляре сервера размещена реплика доступности, используйте следующие представления.</span><span class="sxs-lookup"><span data-stu-id="461ae-115">To query the properties and states of the availability groups for which the server instance hosts an availability replica, use the following views:</span></span>  
  
 [<span data-ttu-id="461ae-116">sys.availability_groups</span><span class="sxs-lookup"><span data-stu-id="461ae-116">sys.availability_groups</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-groups-transact-sql)  
 <span data-ttu-id="461ae-117">Возвращает строку для каждой группы доступности, для которых в локальном экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] размещена реплика доступности.</span><span class="sxs-lookup"><span data-stu-id="461ae-117">Returns a row for each availability group for which the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hosts an availability replica.</span></span> <span data-ttu-id="461ae-118">Каждая строка содержит кэшированную копию метаданных группы доступности.</span><span class="sxs-lookup"><span data-stu-id="461ae-118">Each row contains a cached copy of the availability group metadata.</span></span>  
  
 <span data-ttu-id="461ae-119">**Имена столбцов:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span><span class="sxs-lookup"><span data-stu-id="461ae-119">**Column names:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span></span>  
  
 [<span data-ttu-id="461ae-120">sys.availability_groups_cluster</span><span class="sxs-lookup"><span data-stu-id="461ae-120">sys.availability_groups_cluster</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-groups-cluster-transact-sql)  
 <span data-ttu-id="461ae-121">Возвращает строку для каждой группы доступности в кластере WSFC.</span><span class="sxs-lookup"><span data-stu-id="461ae-121">Returns a row for each availability group in the WSFC cluster.</span></span> <span data-ttu-id="461ae-122">Каждая строка содержит метаданные группы доступности из отказоустойчивой кластеризации Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="461ae-122">Each row contains the availability group metadata from the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="461ae-123">**Имена столбцов:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span><span class="sxs-lookup"><span data-stu-id="461ae-123">**Column names:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span></span>  
  
 [<span data-ttu-id="461ae-124">sys.dm_hadr_availability_group_states</span><span class="sxs-lookup"><span data-stu-id="461ae-124">sys.dm_hadr_availability_group_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-group-states-transact-sql)  
 <span data-ttu-id="461ae-125">Возвращает по строке для каждой из групп доступности, у которых имеется реплика доступности на локальном экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="461ae-125">Returns a row for each availability group that possesses an availability replica on the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="461ae-126">Каждая строка отображает состояния работоспособности определенной группы доступности.</span><span class="sxs-lookup"><span data-stu-id="461ae-126">Each row displays the states that define the health of a given availability group.</span></span>  
  
 <span data-ttu-id="461ae-127">**Имена столбцов:** group_id, primary_replica, primary_recovery_health, primary_recovery_health_desc, secondary_recovery_health, secondary_recovery_health_desc, synchronization_health, synchronization_health_desc</span><span class="sxs-lookup"><span data-stu-id="461ae-127">**Column names:** group_id, primary_replica, primary_recovery_health, primary_recovery_health_desc, secondary_recovery_health, secondary_recovery_health_desc, synchronization_health, synchronization_health_desc</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="461ae-128">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="461ae-128">Related Tasks</span></span>  
 <span data-ttu-id="461ae-129">**Просмотр сведений о группах доступности**</span><span class="sxs-lookup"><span data-stu-id="461ae-129">**To view information about availability groups**</span></span>  
  
-   [<span data-ttu-id="461ae-130">Просмотр свойств реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-130">View Availability Replica Properties &#40;SQL Server&#41;</span></span>](view-availability-replica-properties-sql-server.md)  
  
-   [<span data-ttu-id="461ae-131">Просмотр свойств прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-131">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
-   [<span data-ttu-id="461ae-132">Политики AlwaysOn для проблем в работе с группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="461ae-132">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](always-on-policies-for-operational-issues-always-on-availability.md)
  
-   [<span data-ttu-id="461ae-133">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="461ae-133">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="461ae-134">Отслеживание групп доступности (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="461ae-134">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
 <span data-ttu-id="461ae-135">**Настройка существующей группы доступности**</span><span class="sxs-lookup"><span data-stu-id="461ae-135">**To configure an existing availability group**</span></span>  
  
-   [<span data-ttu-id="461ae-136">Добавление вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-136">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="461ae-137">Удаление вторичной реплики из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-137">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="461ae-138">Добавление базы данных в группу доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-138">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="461ae-139">Удаление базы данных-получателя из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-139">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="461ae-140">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-140">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="461ae-141">Удаление прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-141">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="461ae-142">Удаление базы данных-источника из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-142">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="461ae-143">Удаление группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-143">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="461ae-144">**Переход на другой ресурс группы доступности вручную**</span><span class="sxs-lookup"><span data-stu-id="461ae-144">**To manually fail over an availability group**</span></span>  
  
-   [<span data-ttu-id="461ae-145">Выполнение запланированного перехода на другой ресурс вручную для группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-145">Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="461ae-146">Выполнение принудительного перехода на другой ресурс вручную для группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="461ae-146">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="461ae-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="461ae-147">See Also</span></span>  
 <span data-ttu-id="461ae-148">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) [мониторинг групп доступности &#40;политик Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) [AlwaysOn для проблем в работе с группы доступности AlwaysOn](always-on-policies-for-operational-issues-always-on-availability.md) &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="461ae-148">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) [Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md)</span></span> 
  
  
