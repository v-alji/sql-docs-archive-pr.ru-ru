---
title: Удаление вторичной реплики из группы доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removesecondaryar.f1
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], configuring
ms.assetid: 35ddc8b6-3e7c-4417-9a0a-d4987a09ddf7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e3f2b35ec9cf27f2f7b23714a41665f2709837a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657314"
---
# <a name="remove-a-secondary-replica-from-an-availability-group-sql-server"></a><span data-ttu-id="33366-102">Удаление вторичной реплики из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="33366-102">Remove a Secondary Replica from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="33366-103">В этом разделе описывается удаление вторичной реплики из группы доступности AlwaysOn с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33366-103">This topic describes how to remove a secondary replica from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="33366-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="33366-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="33366-105">Ограничения</span><span class="sxs-lookup"><span data-stu-id="33366-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="33366-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="33366-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="33366-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="33366-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="33366-108">**Удаление вторичной реплики с помощью**</span><span class="sxs-lookup"><span data-stu-id="33366-108">**To remove a secondary replica, using:**</span></span>  
  
     [<span data-ttu-id="33366-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="33366-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="33366-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="33366-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="33366-111">PowerShell</span><span class="sxs-lookup"><span data-stu-id="33366-111">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="33366-112">**Дальнейшие действия.**  [После удаления вторичной реплики](#PostBestPractices)</span><span class="sxs-lookup"><span data-stu-id="33366-112">**Follow Up:**  [After Removing a Secondary Replica](#PostBestPractices)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="33366-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="33366-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="33366-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="33366-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="33366-115">Эта задача поддерживается только в первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="33366-115">This task is supported only on the primary replica.</span></span>  
  
-   <span data-ttu-id="33366-116">Из группы доступности может быть удалена только вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="33366-116">Only a secondary replica can be removed from an availability group.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="33366-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="33366-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="33366-118">Необходимо иметь подключение к экземпляру сервера, на котором размещена первичная реплика группы доступности.</span><span class="sxs-lookup"><span data-stu-id="33366-118">You must be connected to the server instance that hosts the primary replica of the availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="33366-119">безопасность</span><span class="sxs-lookup"><span data-stu-id="33366-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="33366-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="33366-120">Permissions</span></span>  
 <span data-ttu-id="33366-121">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="33366-121">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="33366-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="33366-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="33366-123">**Удаление вторичной реплики**</span><span class="sxs-lookup"><span data-stu-id="33366-123">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="33366-124">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена первичная реплика, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="33366-124">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="33366-125">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="33366-125">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="33366-126">Выберите группу доступности и разверните узел **Реплики доступности** .</span><span class="sxs-lookup"><span data-stu-id="33366-126">Select the availability group, and expand the **Availability Replicas** node.</span></span>  
  
4.  <span data-ttu-id="33366-127">Этот шаг имеет следующие различия в зависимости от того, удаляется одна или несколько реплик.</span><span class="sxs-lookup"><span data-stu-id="33366-127">This step depends on whether you want to remove multiple replicas or only one replica, as follows:</span></span>  
  
    -   <span data-ttu-id="33366-128">Чтобы удалить несколько реплик, используйте область **Подробности** обозревателя объектов, чтобы просмотреть и выбрать реплики для удаления.</span><span class="sxs-lookup"><span data-stu-id="33366-128">To remove multiple replicas, use the **Object Explorer Details** pane to view and select all the replicas that you want to remove.</span></span> <span data-ttu-id="33366-129">Дополнительные сведения см. в разделе [Использование раздела "Подробности обозревателя объектов" для мониторинга групп доступности (среда SQL Server Management Studio)](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="33366-129">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="33366-130">Чтобы удалить одну реплику, выберите ее на панели **Обозреватель объектов** или на панели **Подробности обозревателя объектов** .</span><span class="sxs-lookup"><span data-stu-id="33366-130">To remove a single replica, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="33366-131">Щелкните правой кнопкой мыши выбранную вторичную реплику или реплики и выберите в контекстном меню команду **Удалить из группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="33366-131">Right-click the selected secondary replica or replicas, and select **Remove from Availability Group** in the command menu.</span></span>  
  
6.  <span data-ttu-id="33366-132">Чтобы удалить все перечисленные вторичные реплики, в диалоговом окне **Удаление вторичных реплик из группы доступности** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="33366-132">In the **Remove Secondary Replicas from Availability Group** dialog box, to remove all the listed secondary replicas, click **OK**.</span></span> <span data-ttu-id="33366-133">Если все перечисленные группы доступности удалять не нужно, нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="33366-133">If you do not want to remove all the listed replicas, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="33366-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="33366-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="33366-135">**Удаление вторичной реплики**</span><span class="sxs-lookup"><span data-stu-id="33366-135">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="33366-136">Подключитесь к экземпляру сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="33366-136">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="33366-137">Инструкция [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="33366-137">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="33366-138">ALTER AVAILABILITY GROUP *имя_группы* REMOVE REPLICA ON "*имя_экземпляра*" [,...*n*],</span><span class="sxs-lookup"><span data-stu-id="33366-138">ALTER AVAILABILITY GROUP *group_name* REMOVE REPLICA ON '*instance_name*' [,...*n*]</span></span>  
  
     <span data-ttu-id="33366-139">где *имя_группы* — имя группы доступности, а *имя_экземпляра* — экземпляр сервера, на котором размещена вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="33366-139">where *group_name* is the name of the availability group and *instance_name* is the server instance where the secondary replica is located.</span></span>  
  
     <span data-ttu-id="33366-140">В следующем примере удаляется вторичная реплика из группы доступности *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="33366-140">The following example removes a secondary replica from the *MyAG* availability group.</span></span> <span data-ttu-id="33366-141">Целевая вторичная реплика расположена на экземпляре сервера с именем *HADR_INSTANCE* на компьютере *COMPUTER02*.</span><span class="sxs-lookup"><span data-stu-id="33366-141">The target secondary replica is located on a server instance named *HADR_INSTANCE* on a computer named *COMPUTER02*.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG REMOVE REPLICA ON 'COMPUTER02\HADR_INSTANCE';  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="33366-142">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="33366-142">Using PowerShell</span></span>  
 <span data-ttu-id="33366-143">**Удаление вторичной реплики**</span><span class="sxs-lookup"><span data-stu-id="33366-143">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="33366-144">Перейдите в каталог (`cd`) экземпляра сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="33366-144">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="33366-145">Используйте командлет **Remove-SqlAvailabilityReplica** .</span><span class="sxs-lookup"><span data-stu-id="33366-145">Use the **Remove-SqlAvailabilityReplica** cmdlet.</span></span>  
  
     <span data-ttu-id="33366-146">Например, следующая команда удаляет реплику доступности на сервере `MyReplica` из группы доступности с именем `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="33366-146">For example, the following command removes the availability replica on the server `MyReplica` from the availability group named `MyAg`.</span></span>  <span data-ttu-id="33366-147">Эта команда должна выполняться на экземпляре сервера, на котором размещена первичная реплика группы доступности.</span><span class="sxs-lookup"><span data-stu-id="33366-147">This command must be run on the server instance that hosts the primary replica of the availability group.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityReplica -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="33366-148">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33366-148">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="33366-149">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="33366-149">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="33366-150">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="33366-150">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="33366-151">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="33366-151">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-a-secondary-replica"></a><a name="PostBestPractices"></a> <span data-ttu-id="33366-152">Дальнейшие действия. После удаления вторичной реплики</span><span class="sxs-lookup"><span data-stu-id="33366-152">Follow Up: After Removing a Secondary Replica</span></span>  
 <span data-ttu-id="33366-153">Если была выбрана реплика, которая в данный момент недоступна, ее удаление произойдет в момент перехода в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="33366-153">If you specify a replica that is currently unavailable, when the replica comes online, it will discover that it has been removed.</span></span>  
  
 <span data-ttu-id="33366-154">Удаление реплики прекращает поступление в нее данных.</span><span class="sxs-lookup"><span data-stu-id="33366-154">Removing a replica causes it to stop receiving data.</span></span> <span data-ttu-id="33366-155">После того, как вторичная реплика подтверждает, что она была удалена из глобального хранилища, реплика удаляет параметры группы доступности из своих баз данных, которые остаются на экземпляре локального сервера в состоянии RECOVERING.</span><span class="sxs-lookup"><span data-stu-id="33366-155">After a secondary replica confirms that it has been removed from the global store, the replica removes the availability group settings from its databases, which remain on the local server instance in the RECOVERING state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33366-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="33366-156">See Also</span></span>  
 <span data-ttu-id="33366-157">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="33366-157">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="33366-158">[Добавление вторичной реплики в группу доступности &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="33366-158">[Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md) </span></span>  
 [<span data-ttu-id="33366-159">Удаление группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="33366-159">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
