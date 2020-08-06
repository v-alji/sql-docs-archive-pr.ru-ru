---
title: Изменение режима отработки отказа для реплики доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover modes [SQL Server]
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], failover modes
- Availability Groups [SQL Server], configuring
ms.assetid: 619a826f-8e65-48eb-8c34-39497d238279
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d946440e2950192299c42652babb4082790dbd03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750216"
---
# <a name="change-the-failover-mode-of-an-availability-replica-sql-server"></a><span data-ttu-id="5d9df-102">Изменение режима отработки отказа для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5d9df-102">Change the Failover Mode of an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="5d9df-103">В этом разделе описывается изменение режима отработки отказа для реплики доступности в группе доступности AlwaysOn в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d9df-103">This topic describes how to change the failover mode of an availability replica in an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="5d9df-104">Режим отработки отказа ― это свойство реплики, которое определяет режим отработки отказа для реплик, работающих в режиме доступности с синхронной фиксацией.</span><span class="sxs-lookup"><span data-stu-id="5d9df-104">The failover mode is a replica property that determines the failover mode for replicas that run under synchronous-commit availability mode.</span></span> <span data-ttu-id="5d9df-105">Дополнительные сведения см. в разделах [Отработка отказа и режимы отработки отказа (группы доступности AlwaysOn)](failover-and-failover-modes-always-on-availability-groups.md) и [Режимы доступности (группы доступности AlwaysOn)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="5d9df-105">For more information, see [Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;](failover-and-failover-modes-always-on-availability-groups.md) and [Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5d9df-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5d9df-106">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="5d9df-107">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="5d9df-107">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="5d9df-108">Эта задача поддерживается только на первичных репликах.</span><span class="sxs-lookup"><span data-stu-id="5d9df-108">This task is supported only on primary replicas.</span></span> <span data-ttu-id="5d9df-109">Необходимо подключиться к экземпляру сервера, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="5d9df-109">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="5d9df-110">Экземпляры отказоустойчивого кластера SQL Server не поддерживают автоматический переход на другой ресурс с учетом групп доступности, поэтому любая реплика доступности, размещенная в них, должна быть настроена для перехода на другой ресурс вручную.</span><span class="sxs-lookup"><span data-stu-id="5d9df-110">SQL Server Failover Cluster Instances (FCIs) do not support automatic failover by availability groups, so any availability replica that is hosted by an FCI can only be configured for manual failover.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5d9df-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="5d9df-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5d9df-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="5d9df-112">Permissions</span></span>  
 <span data-ttu-id="5d9df-113">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="5d9df-113">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5d9df-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d9df-114">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="5d9df-115">**Изменение режима отработки отказа для реплики доступности**</span><span class="sxs-lookup"><span data-stu-id="5d9df-115">**To change the failover mode of an availability replica**</span></span>  
  
1.  <span data-ttu-id="5d9df-116">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена первичная реплика, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="5d9df-116">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="5d9df-117">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="5d9df-117">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="5d9df-118">Щелкните группу доступности, реплику которой нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="5d9df-118">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="5d9df-119">Щелкните правой кнопкой мыши реплику и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5d9df-119">Right-click the replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="5d9df-120">В диалоговом окне **Свойства реплики доступности** используйте раскрывающийся список **Режим отработки отказа** , чтобы изменить режим отработки отказа для этой реплики.</span><span class="sxs-lookup"><span data-stu-id="5d9df-120">In the **Availability Replica Properties** dialog box, use the **Failover mode** drop list to change the failover mode of this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5d9df-121">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5d9df-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="5d9df-122">**Изменение режима отработки отказа для реплики доступности**</span><span class="sxs-lookup"><span data-stu-id="5d9df-122">**To change the failover mode of an availability replica**</span></span>  
  
1.  <span data-ttu-id="5d9df-123">Подключитесь к экземпляру сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="5d9df-123">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="5d9df-124">Инструкция [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5d9df-124">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="5d9df-125">ALTER AVAILABILITY GROUP *имя_группы* MODIFY REPLICA ON '*имя_сервера*'</span><span class="sxs-lookup"><span data-stu-id="5d9df-125">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span></span>  
  
     <span data-ttu-id="5d9df-126">WITH ( {</span><span class="sxs-lookup"><span data-stu-id="5d9df-126">WITH ( {</span></span>  
  
     <span data-ttu-id="5d9df-127">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span><span class="sxs-lookup"><span data-stu-id="5d9df-127">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span></span>  
  
     <span data-ttu-id="5d9df-128">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span><span class="sxs-lookup"><span data-stu-id="5d9df-128">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span></span>  
  
     <span data-ttu-id="5d9df-129">}  )</span><span class="sxs-lookup"><span data-stu-id="5d9df-129">}  )</span></span>  
  
     <span data-ttu-id="5d9df-130">где</span><span class="sxs-lookup"><span data-stu-id="5d9df-130">where</span></span>  
  
    -   <span data-ttu-id="5d9df-131">*имя_группы* — это имя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="5d9df-131">*group_name* is the name of the availability group.</span></span>  
  
    -   <span data-ttu-id="5d9df-132">{ '*системное_имя*[\\*имя_экземпляра*]' | '*сетевое_имя_FCI*[\\*имя_экземпляра*]' }</span><span class="sxs-lookup"><span data-stu-id="5d9df-132">{ '*system_name*[\\*instance_name*]' | '*FCI_network_name*[\\*instance_name*]' }</span></span>  
  
         <span data-ttu-id="5d9df-133">Задает адрес экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на котором размещена изменяемая реплика доступности.</span><span class="sxs-lookup"><span data-stu-id="5d9df-133">Specifies the address of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica to be altered.</span></span> <span data-ttu-id="5d9df-134">Этот адрес состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="5d9df-134">The components of this address are as follows:</span></span>  
  
         <span data-ttu-id="5d9df-135">*системное_имя*</span><span class="sxs-lookup"><span data-stu-id="5d9df-135">*system_name*</span></span>  
         <span data-ttu-id="5d9df-136">Имя NetBIOS компьютера, на котором расположен изолированный экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="5d9df-136">Is the NetBIOS name of the computer system on which a stand-alone server instance resides.</span></span>  
  
         <span data-ttu-id="5d9df-137">*сетевое_имя_FCI*</span><span class="sxs-lookup"><span data-stu-id="5d9df-137">*FCI_network_name*</span></span>  
         <span data-ttu-id="5d9df-138">Сетевое имя, используемое для доступа к отказоустойчивому кластеру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , в котором целевой экземпляр сервера является партнером по обеспечению отработки отказа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d9df-138">Is the network name that is used to access a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster in which a target server instance is a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover partner (an FCI).</span></span>  
  
         <span data-ttu-id="5d9df-139">*instance_name*</span><span class="sxs-lookup"><span data-stu-id="5d9df-139">*instance_name*</span></span>  
         <span data-ttu-id="5d9df-140">Имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на котором размещается целевая реплика доступности.</span><span class="sxs-lookup"><span data-stu-id="5d9df-140">Is the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the target availability replica.</span></span> <span data-ttu-id="5d9df-141">Для экземпляра сервера по умолчанию указывать параметр *имя_экземпляра* не обязательно.</span><span class="sxs-lookup"><span data-stu-id="5d9df-141">For a default server instance, *instance_name* is optional.</span></span>  
  
     <span data-ttu-id="5d9df-142">Дополнительные сведения об этих параметрах см. в разделе [ALTER AVAILABILITY GROUP (Transact-SQL)](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5d9df-142">For more information about these parameters, see [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
     <span data-ttu-id="5d9df-143">В следующем примере для первичной реплики группы доступности *MyAG* режим отработки отказа меняется на автоматический переход на другой ресурс для реплики доступности, находящейся на экземпляре сервера по умолчанию на компьютере *COMPUTER01*.</span><span class="sxs-lookup"><span data-stu-id="5d9df-143">The following example, entered on the primary replica of the *MyAG* availability group, changes the failover mode to automatic failover on the availability replica that is located on the default server instance on a computer named *COMPUTER01*.</span></span>  
  
    ```  
    ALTER AVAILABILITY GROUP MyAG MODIFY REPLICA ON 'COMPUTER01' WITH  
       (FAILOVER_MODE = AUTOMATIC);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="5d9df-144">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d9df-144">Using PowerShell</span></span>  

### <a name="to-change-the-failover-mode-of-an-availability-replica"></a><span data-ttu-id="5d9df-145">Изменение режима отработки отказа для реплики доступности</span><span class="sxs-lookup"><span data-stu-id="5d9df-145">To change the failover mode of an availability replica</span></span>
  
1.  <span data-ttu-id="5d9df-146">Перейдите в каталог (`cd`) экземпляра сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="5d9df-146">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="5d9df-147">Используйте командлет `Set-SqlAvailabilityReplica` с параметром `FailoverMode`.</span><span class="sxs-lookup"><span data-stu-id="5d9df-147">Use the `Set-SqlAvailabilityReplica` cmdlet with the `FailoverMode` parameter.</span></span> <span data-ttu-id="5d9df-148">При выборе автоматического перехода на другой ресурс для реплики может потребоваться указать параметр `AvailabilityMode`, чтобы перевести реплику в режим доступности с синхронной фиксацией.</span><span class="sxs-lookup"><span data-stu-id="5d9df-148">When setting a replica to automatic failover, you might need to use the `AvailabilityMode` parameter to change the replica to synchronous-commit availability mode.</span></span>  
  
     <span data-ttu-id="5d9df-149">Например, следующая команда изменяет реплику `MyReplica` в группе доступности `MyAg` , устанавливая использование режима доступности с синхронной фиксацией и поддержку автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="5d9df-149">For example, the following command modifies the replica `MyReplica` in the availability group `MyAg` to use synchronous-commit availability mode and to support automatic failover.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -AvailabilityMode "SynchronousCommit" -FailoverMode "Automatic" `
     -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\Replicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="5d9df-150">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d9df-150">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="5d9df-151">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5d9df-151">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="5d9df-152">Сведения о настройке и использовании поставщика SQL Server PowerShell см. в разделе [поставщик SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="5d9df-152">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d9df-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d9df-153">See Also</span></span>  
 [<span data-ttu-id="5d9df-154">Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d9df-154">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="5d9df-155">[Режимы доступности &#40;группы доступности AlwaysOn&#41;](availability-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="5d9df-155">[Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="5d9df-156">Отказоустойчивость и режимы отработки отказа &#40;группы доступности AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="5d9df-156">Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;</span></span>](failover-and-failover-modes-always-on-availability-groups.md) 
