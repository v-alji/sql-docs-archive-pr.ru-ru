---
title: Выполнение запланированного перехода на другой ресурс вручную для группы доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.manualfailover.f1
helpviewer_keywords:
- Availability Groups [SQL Server], failover
- failover [SQL Server], AlwaysOn Availability Groups
ms.assetid: 419f655d-3f9a-4e7d-90b9-f0bab47b3178
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c62942eaa8f4ab4472bca5c7123e5999eb069216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734473"
---
# <a name="perform-a-planned-manual-failover-of-an-availability-group-sql-server"></a><span data-ttu-id="63f43-102">Выполнение запланированного перехода на другой ресурс вручную для группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="63f43-102">Perform a Planned Manual Failover of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="63f43-103"> Этот раздел описывает, как выполнить переход на другой ресурс вручную без потери данных (*запланированный переход на другой ресурс вручную*) в группе доступности AlwaysOn с помощью [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)] или PowerShell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63f43-103">This topic describes how to perform a manual failover without data loss (a *planned manual failover*) on an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="63f43-104">Группа доступности выполняет переход на другой ресурс на уровне реплики доступности.</span><span class="sxs-lookup"><span data-stu-id="63f43-104">An availability group fails over at the level of an availability replica.</span></span> <span data-ttu-id="63f43-105">Запланированный переход на другой ресурс вручную, как и любая отработка отказа [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , переводит вторичную реплику в роль первичной и одновременно переводит реплику, бывшую первичной, в роль вторичной.</span><span class="sxs-lookup"><span data-stu-id="63f43-105">A planned manual failover, like any [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] failover, transitions a secondary replica to primary role and, concurrently, transitions the former primary replica to the secondary role.</span></span>  
  
 <span data-ttu-id="63f43-106">При запланированном переходе на другой ресурс вручную, который поддерживается, только если первичная и целевая вторичная реплики работают в режиме синхронной фиксации и в данный момент синхронизированы, сохраняются все данные в базах данных-получателях, присоединенных к группе доступности в целевой вторичной реплике.</span><span class="sxs-lookup"><span data-stu-id="63f43-106">A planned manual failover, which is supported only when the primary replica and the target secondary replica are running in synchronous-commit mode and are currently synchronized, preserves all the data in the secondary databases that are joined to the availability group on the target secondary replica.</span></span> <span data-ttu-id="63f43-107">После того как бывшая первичная реплика перейдет в роль вторичной, ее базы данных станут базами данных-получателями и начнут синхронизироваться с новыми базами данных-источниками.</span><span class="sxs-lookup"><span data-stu-id="63f43-107">Once the former primary replica transitions to the secondary role, its databases become secondary databases and begin synchronizing with the new primary databases.</span></span> <span data-ttu-id="63f43-108">После того как они все перейдут в состояние SYNCHRONIZED, новая вторичная реплика может служить целью будущей запланированного перехода на другой ресурс вручную.</span><span class="sxs-lookup"><span data-stu-id="63f43-108">After they all transition into the SYNCHRONIZED state, the new secondary replica becomes eligible to serve as the target of a future planned manual failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63f43-109">Если для первичной и вторичной реплики задан автоматический переход на другой ресурс, то после синхронизации вторичная реплика также может выступать в качестве цели для автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="63f43-109">If the secondary and primary replicas are both configured for automatic failover mode, once the secondary replica is synchronized, it can also serve as the target for an automatic failover.</span></span> <span data-ttu-id="63f43-110">Дополнительные сведения см. в разделе [Режимы доступности (группы доступности AlwaysOn)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="63f43-110">For more information, see [Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md).</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="63f43-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="63f43-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="63f43-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="63f43-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="63f43-113">Команда отработки отказа завершает работу сразу после того, как целевая вторичная реплика примет команду.</span><span class="sxs-lookup"><span data-stu-id="63f43-113">A failover command returns as soon as the target secondary replica has accepted the command.</span></span> <span data-ttu-id="63f43-114">Однако восстановление базы данных происходит асинхронно после того, как группа доступности закончит отработку отказа.</span><span class="sxs-lookup"><span data-stu-id="63f43-114">However, database recovery occurs asynchronously after the availability group has finished failing over.</span></span>  
  
-   <span data-ttu-id="63f43-115">Целостность данных между базами данных в рамках группы доступности во время отработки отказа не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="63f43-115">Cross-database consistency across databases within the availability group is not maintained on failover.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="63f43-116">Транзакции между базами данных и распределенные транзакции не поддерживаются в [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63f43-116">Cross-database transactions and distributed transactions are not supported by [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="63f43-117">Дополнительные сведения см. в разделе [Транзакции между базами данных не поддерживаются при зеркальном отображении баз данных или в группах доступности AlwaysOn (SQL Server)](transactions-always-on-availability-and-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="63f43-117">For more information, see [Cross-Database Transactions Not Supported For Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](transactions-always-on-availability-and-database-mirroring.md).</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="63f43-118">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="63f43-118">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="63f43-119">Целевая вторичная реплика и первичная реплика должны работать в режиме доступности с синхронной фиксацией.</span><span class="sxs-lookup"><span data-stu-id="63f43-119">The target secondary replica and the primary replica must both be running in synchronous-commit availability mode.</span></span>  
  
-   <span data-ttu-id="63f43-120">Целевая вторичная реплика должна в данный момент быть синхронизирована с первичной репликой.</span><span class="sxs-lookup"><span data-stu-id="63f43-120">The target secondary replica must currently be synchronized with the primary replica.</span></span> <span data-ttu-id="63f43-121">Для этого необходимо, чтобы все базы данных-получатели в этой вторичной реплике были присоединены к группе доступности и синхронизированы с соответствующими им базами данных-источниками (локальные базы данных-получатели должны находиться в состоянии SYNCHRONIZED).</span><span class="sxs-lookup"><span data-stu-id="63f43-121">This requires that all the secondary databases on this secondary replica must have been joined to the availability group and be synchronized with their corresponding primary databases (that is, the local secondary databases must be SYNCHRONIZED).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="63f43-122">Чтобы определить готовность вторичной реплики к переходу на другой ресурс, запросите столбец **is_failover_ready** в динамическом административном представлении [sys.dm_hadr_database_cluster_states](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql) или проверьте значение столбца **Готовность к отработке отказа** на [панели мониторинга групп AlwaysOn](use-the-always-on-dashboard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="63f43-122">To determine the failover readiness of an secondary replica, query the **is_failover_ready** column in the [sys.dm_hadr_database_cluster_states](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql) dynamic management view, or look at the **Failover Readiness** column of the [AlwaysOn Group Dashboard](use-the-always-on-dashboard-sql-server-management-studio.md).</span></span>  
  
-   <span data-ttu-id="63f43-123">Эта задача поддерживается только в целевой вторичной реплике.</span><span class="sxs-lookup"><span data-stu-id="63f43-123">This task is supported only on the target secondary replica.</span></span> <span data-ttu-id="63f43-124">Необходимо подключиться к экземпляру сервера, на котором размещается целевая вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="63f43-124">You must be connected to the server instance that hosts the target secondary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="63f43-125">безопасность</span><span class="sxs-lookup"><span data-stu-id="63f43-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="63f43-126">Permissions</span><span class="sxs-lookup"><span data-stu-id="63f43-126">Permissions</span></span>  
 <span data-ttu-id="63f43-127">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="63f43-127">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="63f43-128">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="63f43-128">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="63f43-129">**Переход на другой ресурс группы доступности вручную**</span><span class="sxs-lookup"><span data-stu-id="63f43-129">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="63f43-130">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена вторичная реплика группы доступности, на которую нужно выполнить отработку отказа, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="63f43-130">In Object Explorer, connect to a server instance that hosts a secondary replica of the availability group that needs to be failed over, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="63f43-131">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="63f43-131">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="63f43-132">Щелкните правой кнопкой мыши группу доступности для выполнения отработки отказа и выберите команду **Отработка отказа** .</span><span class="sxs-lookup"><span data-stu-id="63f43-132">Right-click the availability group to be failed over, and select the **Failover** command.</span></span>  
  
4.  <span data-ttu-id="63f43-133">Будет запущен мастер отработки отказа группой доступности.</span><span class="sxs-lookup"><span data-stu-id="63f43-133">This launches the Failover Availability Group Wizard.</span></span> <span data-ttu-id="63f43-134">Дополнительные сведения см. в подразделе [Использование мастера отработки отказа группы доступности (среда SQL Server Management Studio)](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="63f43-134">For more information, see [Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="63f43-135">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="63f43-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="63f43-136">**Переход на другой ресурс группы доступности вручную**</span><span class="sxs-lookup"><span data-stu-id="63f43-136">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="63f43-137">Подключитесь к экземпляру сервера, на котором находится целевая вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="63f43-137">Connect to the server instance that hosts the target secondary replica.</span></span>  
  
2.  <span data-ttu-id="63f43-138">Инструкция [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="63f43-138">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="63f43-139">ALTER AVAILABILITY GROUP *имя_группы* FAILOVER</span><span class="sxs-lookup"><span data-stu-id="63f43-139">ALTER AVAILABILITY GROUP *group_name* FAILOVER</span></span>  
  
     <span data-ttu-id="63f43-140">где *имя_группы* — это имя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="63f43-140">where *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="63f43-141">В следующем примере вручную выполняется отработка отказа группы доступности *MyAg»* на подключенную вторичную реплику.</span><span class="sxs-lookup"><span data-stu-id="63f43-141">The following example manually fails over the *MyAg* availability group to the connected secondary replica.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAg FAILOVER;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="63f43-142">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="63f43-142">Using PowerShell</span></span>  
 <span data-ttu-id="63f43-143">**Переход на другой ресурс группы доступности вручную**</span><span class="sxs-lookup"><span data-stu-id="63f43-143">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="63f43-144">Перейдите в каталог (`cd`) экземпляра сервера, на котором размещается целевая вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="63f43-144">Change directory (`cd`) to the server instance that hosts the target secondary replica.</span></span>  
  
2.  <span data-ttu-id="63f43-145">Используйте командлет `Switch-SqlAvailabilityGroup`.</span><span class="sxs-lookup"><span data-stu-id="63f43-145">Use the `Switch-SqlAvailabilityGroup` cmdlet.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="63f43-146">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63f43-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="63f43-147">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="63f43-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
     <span data-ttu-id="63f43-148">В следующем примере вручную выполняется отработка отказа группы доступности *MyAg»* на вторичную реплику с указанным путем.</span><span class="sxs-lookup"><span data-stu-id="63f43-148">The following example manually fails over the *MyAg* availability group to the secondary replica with the specified path.</span></span>  
  
    ```powershell
    Switch-SqlAvailabilityGroup -Path SQLSERVER:\Sql\SecondaryServer\InstanceName\AvailabilityGroups\MyAg  
    ```  
  
 <span data-ttu-id="63f43-149">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="63f43-149">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="63f43-150">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="63f43-150">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="63f43-151">Получение справок по SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="63f43-151">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="follow-up-after-manually-failing-over-an-availability-group"></a><a name="FollowUp"></a> <span data-ttu-id="63f43-152">Дальнейшие действия. После ручной отработки отказа группы доступности</span><span class="sxs-lookup"><span data-stu-id="63f43-152">Follow Up: After Manually Failing Over an Availability Group</span></span>  
 <span data-ttu-id="63f43-153">Если переход был выполнен на ресурс, находящийся за пределами группы доступности [!INCLUDE[ssFosAuto](../../../includes/ssfosauto-md.md)] , настройте кворум узлов кластера WSFC, чтобы отразить новую конфигурацию группы доступности.</span><span class="sxs-lookup"><span data-stu-id="63f43-153">If you failed over outside of the [!INCLUDE[ssFosAuto](../../../includes/ssfosauto-md.md)] of the availability group, adjust the quorum votes of the WSFC nodes to reflect your new availability group configuration.</span></span> <span data-ttu-id="63f43-154">Дополнительные сведения см. в разделе [отказоустойчивая кластеризация Windows Server &#40;WSFC&#41; с SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="63f43-154">For more information, see [Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f43-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="63f43-155">See Also</span></span>  
 <span data-ttu-id="63f43-156">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="63f43-156">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="63f43-157">[Отказоустойчивость и режимы отработки отказа &#40;группы доступности AlwaysOn&#41;](failover-and-failover-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="63f43-157">[Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;](failover-and-failover-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="63f43-158">Выполнение принудительного перехода на другой ресурс вручную для группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="63f43-158">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
