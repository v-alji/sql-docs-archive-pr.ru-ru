---
title: Смена режима доступности для реплики доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], availability modes
ms.assetid: c4da8f25-fb1b-45a4-8bf2-195df6df634c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1636f3ea86e083e47276423b120dbc8d3744d387
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750227"
---
# <a name="change-the-availability-mode-of-an-availability-replica-sql-server"></a><span data-ttu-id="03618-102">Смена режима доступности для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="03618-102">Change the Availability Mode of an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="03618-103">В этом разделе описывается изменение режима доступности для реплики доступности в группе доступности AlwaysOn в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03618-103">This topic describes how to change the availability mode of an availability replica in an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="03618-104">Режим доступности — это свойство реплики, которое определяет, происходит в ней синхронная или асинхронная фиксация.</span><span class="sxs-lookup"><span data-stu-id="03618-104">The availability mode is a replica property that controls the whether the replica commits asynchronously or synchronously.</span></span> <span data-ttu-id="03618-105">*Режим асинхронной фиксации* увеличивает производительность за счет средств высокого уровня доступности и поддерживает только принудительный переход на другой ресурс вручную (с возможной потерей данных), который обычно называется *принудительной отработкой отказа*.</span><span class="sxs-lookup"><span data-stu-id="03618-105">*Asynchronous-commit mode* maximizes performance at the expense of high availability and supports only forced manual failover (with possible data loss), typically called *forced failover*.</span></span> <span data-ttu-id="03618-106">*Режим синхронной фиксации* обеспечивает высокий уровень доступности за счет производительности и после завершения синхронизации вторичной реплики поддерживает как автоматическую отработку отказа, так и отработку отказа вручную.</span><span class="sxs-lookup"><span data-stu-id="03618-106">*Synchronous-commit mode* emphasizes high availability over performance and, once the secondary replica is synchronized, supports manual failover and, optionally, automatic failover.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="03618-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="03618-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="03618-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="03618-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="03618-109">Необходимо подключиться к экземпляру сервера, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="03618-109">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="03618-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="03618-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="03618-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="03618-111">Permissions</span></span>  
 <span data-ttu-id="03618-112">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="03618-112">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="03618-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03618-113">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="03618-114">**Изменение режима доступности для группы доступности**</span><span class="sxs-lookup"><span data-stu-id="03618-114">**To change the availability mode of an availability group**</span></span>  
  
1.  <span data-ttu-id="03618-115">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена первичная реплика, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="03618-115">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="03618-116">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="03618-116">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="03618-117">Щелкните группу доступности, реплику которой нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="03618-117">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="03618-118">Щелкните правой кнопкой мыши реплику и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="03618-118">Right-click the replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="03618-119">В диалоговом окне **Свойства реплики доступности** измените режим доступности для этой реплики с помощью раскрывающегося списка **Режим доступности** .</span><span class="sxs-lookup"><span data-stu-id="03618-119">In the **Availability Replica Properties** dialog box, use the **Availability mode** drop list to change the availability mode of this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="03618-120">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03618-120">Using Transact-SQL</span></span>  
 <span data-ttu-id="03618-121">**Изменение режима доступности для группы доступности**</span><span class="sxs-lookup"><span data-stu-id="03618-121">**To change the availability mode of an availability group**</span></span>  
  
1.  <span data-ttu-id="03618-122">Подключитесь к экземпляру сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="03618-122">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="03618-123">Инструкция [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="03618-123">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="03618-124">ALTER AVAILABILITY GROUP *имя_группы* MODIFY REPLICA ON '*имя_сервера*'</span><span class="sxs-lookup"><span data-stu-id="03618-124">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span></span>  
  
     <span data-ttu-id="03618-125">WITH ( {</span><span class="sxs-lookup"><span data-stu-id="03618-125">WITH ( {</span></span>  
  
     <span data-ttu-id="03618-126">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span><span class="sxs-lookup"><span data-stu-id="03618-126">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span></span>  
  
     <span data-ttu-id="03618-127">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span><span class="sxs-lookup"><span data-stu-id="03618-127">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span></span>  
  
     <span data-ttu-id="03618-128">} )</span><span class="sxs-lookup"><span data-stu-id="03618-128">} )</span></span>  
  
     <span data-ttu-id="03618-129">где *group_name* — имя группы доступности, а *server_name* — имя экземпляра сервера, на котором размещена изменяемая реплика.</span><span class="sxs-lookup"><span data-stu-id="03618-129">where *group_name* is the name of the availability group and *server_name* is the name of the server instance that hosts the replica to be modified.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="03618-130">FAILOVER_MODE = AUTOMATIC поддерживается, только если указан параметр AVAILABILITY_MODE = SYNCHRONOUS_COMMIT.</span><span class="sxs-lookup"><span data-stu-id="03618-130">FAILOVER_MODE = AUTOMATIC is supported only if you also specify AVAILABILITY_MODE = SYNCHRONOUS_COMMIT.</span></span>  
  
     <span data-ttu-id="03618-131">В следующем примере, введенном на первичной реплике группы доступности `AccountsAG` , выполняется изменение режимов доступности и отработки отказа на синхронную фиксацию и автоматический переход на другой ресурс соответственно для реплики, размещенной на экземпляре сервера `INSTANCE09` .</span><span class="sxs-lookup"><span data-stu-id="03618-131">The following example, entered on the primary replica of the `AccountsAG` availability group, changes the availability and failover modes to synchronous commit and automatic failover, respectively, for the replica hosted by the `INSTANCE09` server instance.</span></span>  
  
    ```  
  
    ALTER AVAILABILITY GROUP AccountsAG MODIFY REPLICA ON 'INSTANCE09'  
       WITH (AVAILABILITY_MODE = SYNCHRONOUS_COMMIT);  
    ALTER AVAILABILITY GROUP AccountsAG MODIFY REPLICA ON 'INSTANCE09'  
       WITH (FAILOVER_MODE = AUTOMATIC);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="03618-132">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="03618-132">Using PowerShell</span></span>

### <a name="to-change-the-availability-mode-of-an-availability-group"></a><span data-ttu-id="03618-133">Изменение режима доступности для группы доступности</span><span class="sxs-lookup"><span data-stu-id="03618-133">To change the availability mode of an availability group</span></span>
  
1.  <span data-ttu-id="03618-134">Перейдите в каталог (`cd`) экземпляра сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="03618-134">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="03618-135">Используйте командлет `Set-SqlAvailabilityReplica` с параметром `AvailabilityMode`. Дополнительно можно использовать параметр `FailoverMode`.</span><span class="sxs-lookup"><span data-stu-id="03618-135">Use the `Set-SqlAvailabilityReplica` cmdlet with the `AvailabilityMode` parameter and, optionally, the `FailoverMode` parameter.</span></span>  
  
     <span data-ttu-id="03618-136">Например, следующая команда изменяет реплику `MyReplica` в группе доступности `MyAg` , устанавливая использование режима доступности с синхронной фиксацией и поддержку автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="03618-136">For example, the following command modifies the replica `MyReplica` in the availability group `MyAg` to use synchronous-commit availability mode and to support automatic failover.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -AvailabilityMode "SynchronousCommit" -FailoverMode "Automatic" `   
     -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="03618-137">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03618-137">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="03618-138">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="03618-138">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="03618-139">Сведения о настройке и использовании поставщика SQL Server PowerShell см. в разделе [поставщик SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="03618-139">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="03618-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="03618-140">See Also</span></span>  
 <span data-ttu-id="03618-141">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="03618-141">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="03618-142">[Режимы доступности (группы доступности AlwaysOn)](availability-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="03618-142">[Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="03618-143">Отказоустойчивость и режимы отработки отказа &#40;группы доступности AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="03618-143">Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;</span></span>](failover-and-failover-modes-always-on-availability-groups.md)  
