---
title: Просмотр свойств реплики доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- ', policies'
ms.assetid: 14fed3c4-8ecc-4e1c-931d-a7ec1e9f9e90
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6ca7b0508907b4d86c9ee627438a3f18e1b01fdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733149"
---
# <a name="view-availability-replica-properties-sql-server"></a><span data-ttu-id="7f2f2-102">Просмотр свойств реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-102">View Availability Replica Properties (SQL Server)</span></span>
  <span data-ttu-id="7f2f2-103">В этом разделе описывается просмотр свойств реплики доступности для группы доступности AlwaysOn с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f2f2-103">This topic describes how to view the properties of an availability replica for an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7f2f2-104">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7f2f2-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7f2f2-105">**Просмотр и изменение свойств реплики доступности**</span><span class="sxs-lookup"><span data-stu-id="7f2f2-105">**To view and change properties an availability replica**</span></span>  
  
1.  <span data-ttu-id="7f2f2-106">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена первичная реплика, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="7f2f2-106">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="7f2f2-107">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="7f2f2-107">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="7f2f2-108">Разверните группу доступности, которой принадлежит реплика доступности, а затем разверните узел **Реплики доступности** .</span><span class="sxs-lookup"><span data-stu-id="7f2f2-108">Expand the availability group to which the availability replica belongs, and expand the **Availability Replicas** node.</span></span>  
  
4.  <span data-ttu-id="7f2f2-109">Щелкните правой кнопкой мыши реплику доступности, свойства которой нужно просмотреть, и выберите команду **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="7f2f2-109">Right-click the availability replica whose properties you want to view, and select the **Properties** command.</span></span>  
  
5.  <span data-ttu-id="7f2f2-110">В диалоговом окне **Свойства реплики доступности** на странице **Общие** просмотрите свойства текущей реплики.</span><span class="sxs-lookup"><span data-stu-id="7f2f2-110">In the **Availability Replica Properties** dialog box, use the **General** page to view the properties of this replica.</span></span> <span data-ttu-id="7f2f2-111">Если установлено соединение с первичной репликой, можно изменить следующие свойства: режим доступности, режим перехода на другой ресурс, доступ соединения для первичной роли, доступ чтения для вторичной роли (доступная для чтения вторичная роль) и значение времени ожидания сеанса.</span><span class="sxs-lookup"><span data-stu-id="7f2f2-111">If you are connected to the primary replica, you can change the following properties: availability mode, failover mode, connection access for the primary role, read-access for the secondary role (readable-secondary), and the session-timeout value.</span></span> <span data-ttu-id="7f2f2-112">Дополнительные сведения см. в разделе [Свойства реплики доступности &#40;общие&#41;страницы ](availability-replica-properties-general-page.md).</span><span class="sxs-lookup"><span data-stu-id="7f2f2-112">For more information, see  [Availability Replica Properties &#40;General Page&#41;](availability-replica-properties-general-page.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7f2f2-113">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7f2f2-113">Using Transact-SQL</span></span>  
 <span data-ttu-id="7f2f2-114">**Просмотр свойств и состояний реплик доступности**</span><span class="sxs-lookup"><span data-stu-id="7f2f2-114">**To view properties and states of availability replicas**</span></span>  
  
 <span data-ttu-id="7f2f2-115">Для просмотра свойств и состояний реплик доступности используются следующие представления и системная функция.</span><span class="sxs-lookup"><span data-stu-id="7f2f2-115">To view the properties and states of availability replicas, use the following views and system function:</span></span>  
  
 [<span data-ttu-id="7f2f2-116">sys.availability_replicas</span><span class="sxs-lookup"><span data-stu-id="7f2f2-116">sys.availability_replicas</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql)  
 <span data-ttu-id="7f2f2-117">Возвращает строку для каждой реплики доступности, для которой в локальном экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] размещена реплика доступности.</span><span class="sxs-lookup"><span data-stu-id="7f2f2-117">Returns a row for every availability replica in each availability group for which the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hosts an availability replica.</span></span>  
  
 <span data-ttu-id="7f2f2-118">**Имена столбцов:** replica_id, group_id, replica_metadata_id, replica_server_name, owner_sid, endpoint_url, availability_mode, availability_mode_desc, failover_mode, failover_mode_desc, session_timeout, primary_role_allow_connections, primary_role_allow_connections_desc, secondary_role_allow_connections, secondary_role_allow_connections_desc, create_date, modify_date, backup_priority, read_only_routing_url</span><span class="sxs-lookup"><span data-stu-id="7f2f2-118">**Column names:** replica_id, group_id, replica_metadata_id, replica_server_name, owner_sid, endpoint_url, availability_mode, availability_mode_desc, failover_mode, failover_mode_desc, session_timeout, primary_role_allow_connections, primary_role_allow_connections_desc, secondary_role_allow_connections, secondary_role_allow_connections_desc, create_date, modify_date, backup_priority, read_only_routing_url</span></span>  
  
 [<span data-ttu-id="7f2f2-119">sys.availability_read_only_routing_lists</span><span class="sxs-lookup"><span data-stu-id="7f2f2-119">sys.availability_read_only_routing_lists</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-read-only-routing-lists-transact-sql)  
 <span data-ttu-id="7f2f2-120">Возвращает строку для списка маршрутизации только для чтения для каждой реплики доступности в группе доступности AlwaysOn в отказоустойчивом кластере WSFC.</span><span class="sxs-lookup"><span data-stu-id="7f2f2-120">Returns a row for the read only routing list of each availability replica in an AlwaysOn availability group in the WSFC failover cluster.</span></span>  
  
 <span data-ttu-id="7f2f2-121">**Имена столбцов:** replica_id, routing_priority, read_only_replica_id</span><span class="sxs-lookup"><span data-stu-id="7f2f2-121">**Column names:** replica_id, routing_priority, read_only_replica_id</span></span>  
  
 [<span data-ttu-id="7f2f2-122">sys.dm_hadr_availability_replica_cluster_nodes</span><span class="sxs-lookup"><span data-stu-id="7f2f2-122">sys.dm_hadr_availability_replica_cluster_nodes</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-cluster-nodes-transact-sql)  
 <span data-ttu-id="7f2f2-123">Возвращает по строке для каждой из реплик доступности (независимо от состояния соединения) в группах доступности AlwaysOn в отказоустойчивой кластеризации Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="7f2f2-123">Returns a row for every availability replica (regardless of join state) of the AlwaysOn availability groups in the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="7f2f2-124">**Имена столбцов:** group_name, replica_server_name, node_name</span><span class="sxs-lookup"><span data-stu-id="7f2f2-124">**Column names:** group_name, replica_server_name, node_name</span></span>  
  
 [<span data-ttu-id="7f2f2-125">sys.dm_hadr_availability_replica_cluster_states</span><span class="sxs-lookup"><span data-stu-id="7f2f2-125">sys.dm_hadr_availability_replica_cluster_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-cluster-states-transact-sql)  
 <span data-ttu-id="7f2f2-126">Возвращает по строке для каждой из реплик (вне зависимости от состояния соединения) во всех группах доступности AlwaysOn (вне зависимости от расположения реплики) в отказоустойчивой кластеризации Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="7f2f2-126">Returns a row for each replica (regardless of join state) of all AlwaysOn availability groups (regardless of replica location) in the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="7f2f2-127">**Имена столбцов:** replica_id, replica_server_name, group_id, join_state, join_state_desc</span><span class="sxs-lookup"><span data-stu-id="7f2f2-127">**Column names:** replica_id, replica_server_name, group_id, join_state, join_state_desc</span></span>  
  
 [<span data-ttu-id="7f2f2-128">sys.dm_hadr_availability_replica_states</span><span class="sxs-lookup"><span data-stu-id="7f2f2-128">sys.dm_hadr_availability_replica_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-states-transact-sql)  
 <span data-ttu-id="7f2f2-129">Возвращает строку с состоянием каждой локальной реплики доступности и для каждой удаленной реплики доступности, входящей в ту же группу доступности.</span><span class="sxs-lookup"><span data-stu-id="7f2f2-129">Returns a row showing the state of each local availability replica and a row for each remote availability replica in the same availability group.</span></span>  
  
 <span data-ttu-id="7f2f2-130">**Имена столбцов:** replica_id, group_id, is_local, role, role_desc, operational_state, operational_state_desc, connected_state, connected_state_desc, recovery_health, recovery_health_desc, synchronization_health, synchronization_health_desc, last_connect_error_number, last_connect_error_description и last_connect_error_timestamp</span><span class="sxs-lookup"><span data-stu-id="7f2f2-130">**Column names:** replica_id, group_id, is_local, role, role_desc, operational_state, operational_state_desc, connected_state, connected_state_desc, recovery_health, recovery_health_desc, synchronization_health, synchronization_health_desc, last_connect_error_number, last_connect_error_description, and last_connect_error_timestamp</span></span>  
  
 [<span data-ttu-id="7f2f2-131">sys.fn_hadr_backup_is_preferred_replica</span><span class="sxs-lookup"><span data-stu-id="7f2f2-131">sys.fn_hadr_backup_is_preferred_replica</span></span>](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql)  
 <span data-ttu-id="7f2f2-132">Определяет, является ли текущая реплика предпочитаемой резервной репликой отработки.</span><span class="sxs-lookup"><span data-stu-id="7f2f2-132">Determines whether the current replica is the preferred backup replica.</span></span> <span data-ttu-id="7f2f2-133">Возвращаемое значение равно 1, если база данных в текущем экземпляре сервера является предпочитаемой репликой.</span><span class="sxs-lookup"><span data-stu-id="7f2f2-133">Returns 1 if the database on the current server instance is the preferred replica.</span></span> <span data-ttu-id="7f2f2-134">В противном случае возвращается значение 0.</span><span class="sxs-lookup"><span data-stu-id="7f2f2-134">Otherwise, it returns 0.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f2f2-135">Сведения о счетчиках производительности для реплик доступности (объект производительности **SQLServer:Availability Replica**  ) см. в разделе [SQL Server, реплика доступности](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="7f2f2-135">For information about performance counters for availability replicas (the **SQLServer:Availability Replica**  performance object), see [SQL Server, Availability Replica](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7f2f2-136">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="7f2f2-136">Related Tasks</span></span>  
 <span data-ttu-id="7f2f2-137">**Просмотр сведений о группах доступности**</span><span class="sxs-lookup"><span data-stu-id="7f2f2-137">**To view information about availability groups**</span></span>  
  
-   [<span data-ttu-id="7f2f2-138">Просмотр свойств группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-138">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="7f2f2-139">Просмотр свойств прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-139">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
-   [<span data-ttu-id="7f2f2-140">Политики AlwaysOn для проблем в работе с группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f2f2-140">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](always-on-policies-for-operational-issues-always-on-availability.md)
  
-   [<span data-ttu-id="7f2f2-141">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-141">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="7f2f2-142">Отслеживание групп доступности (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-142">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
 <span data-ttu-id="7f2f2-143">**Управление репликами доступности**</span><span class="sxs-lookup"><span data-stu-id="7f2f2-143">**To manage availability replicas**</span></span>  
  
-   [<span data-ttu-id="7f2f2-144">Добавление вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-144">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="7f2f2-145">Присоединение вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-145">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="7f2f2-146">Настройка доступа только для чтения в реплике доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-146">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="7f2f2-147">Смена режима доступности для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-147">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="7f2f2-148">Смена режима отработки отказа для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-148">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="7f2f2-149">Изменение периода ожидания сеанса для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-149">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="7f2f2-150">Удаление вторичной реплики из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-150">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="7f2f2-151">**Управление базой данных доступности**</span><span class="sxs-lookup"><span data-stu-id="7f2f2-151">**To manage an availability database**</span></span>  
  
-   [<span data-ttu-id="7f2f2-152">Добавление базы данных в группу доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-152">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="7f2f2-153">Присоединение базы данных-получателя к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-153">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="7f2f2-154">Приостановка базы данных доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-154">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="7f2f2-155">Возобновление базы данных доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-155">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="7f2f2-156">Удаление базы данных-получателя из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-156">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="7f2f2-157">Удаление базы данных-источника из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f2f2-157">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="7f2f2-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f2f2-158">See Also</span></span>  
 <span data-ttu-id="7f2f2-159">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7f2f2-159">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="7f2f2-160">[Мониторинг групп доступности &#40;&#41;Transact-SQL](monitor-availability-groups-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="7f2f2-160">[Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) </span></span>  
 <span data-ttu-id="7f2f2-161">[Политики AlwaysOn для проблем в работе с группы доступности AlwaysOn &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="7f2f2-161">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 [<span data-ttu-id="7f2f2-162">Администрирование &#40;SQL Server группы доступности&#41;</span><span class="sxs-lookup"><span data-stu-id="7f2f2-162">Administration of an Availability Group &#40;SQL Server&#41;</span></span>](administration-of-an-availability-group-sql-server.md)  
  
  
