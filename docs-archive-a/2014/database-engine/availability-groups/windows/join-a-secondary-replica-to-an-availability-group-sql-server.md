---
title: Присоединение вторичной реплики к группе доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.joinreplica.f1
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], joining
- Availability Groups [SQL Server], configuring
ms.assetid: e5bd2489-097a-490e-8ea1-34fe48378ad1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c38c2d59a46b15fc9a1dca77ae6a67e8e59e1b80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658981"
---
# <a name="join-a-secondary-replica-to-an-availability-group-sql-server"></a><span data-ttu-id="9c337-102">Присоединение вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9c337-102">Join a Secondary Replica to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="9c337-103">В этом разделе описывается присоединение вторичной реплики к группе доступности AlwaysOn с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c337-103">This topic describes how to join a secondary replica to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="9c337-104">После добавления вторичной реплики в группу доступности AlwaysOn необходимо присоединить эту реплику к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="9c337-104">After a secondary replica is added to an AlwaysOn availability group, the secondary replica must be joined to the availability group.</span></span> <span data-ttu-id="9c337-105">Операция присоединения реплики должна быть выполнена на экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на котором находится вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="9c337-105">The join-replica operation must be performed on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting the secondary replica.</span></span>  
  
-   <span data-ttu-id="9c337-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="9c337-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9c337-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9c337-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="9c337-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="9c337-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9c337-109">**Подготовка базы данных-получателя с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="9c337-109">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="9c337-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c337-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9c337-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9c337-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="9c337-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c337-112">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="9c337-113">**Дополнительные действия:** [Настройте базы данных-получатели](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="9c337-113">**Follow Up:** [Configure Secondary Databases](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9c337-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="9c337-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="9c337-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9c337-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="9c337-116">Первичная реплика группы доступности должна быть в сети.</span><span class="sxs-lookup"><span data-stu-id="9c337-116">The primary replica of the availability group must currently be online.</span></span>  
  
-   <span data-ttu-id="9c337-117">Пользователь должен быть подключен к экземпляру сервера, на котором находится дополнительная реплика, которая еще не была присоединена к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="9c337-117">You must be connected to the server instance that hosts a secondary replica that has not yet have been joined to the availability group.</span></span>  
  
-   <span data-ttu-id="9c337-118">Экземпляр локального сервера должен иметь возможность подключения к конечной точке зеркального отображения базы данных на экземпляре сервера, где находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="9c337-118">The local server instance must be able to connect to the database mirroring endpoint of the server instance that is hosting the primary replica.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9c337-119">Если какое-либо из предварительных условий не выполняется, происходит сбой операции соединения.</span><span class="sxs-lookup"><span data-stu-id="9c337-119">If any prerequisite is not met, the join operation fails.</span></span> <span data-ttu-id="9c337-120">После неудачной попытки соединения может быть необходимо подключиться к экземпляру сервера, на котором содержится первичная реплика, чтобы удалить и повторно добавить вторичную реплику, прежде чем можно будет выполнить соединение с группой доступности.</span><span class="sxs-lookup"><span data-stu-id="9c337-120">After a failed join attempt, you might need to connect to the server instance that hosts the primary replica to remove and re-add the secondary replica before you can join it to the availability group.</span></span> <span data-ttu-id="9c337-121">Дополнительные сведения см. в разделах [Удаление вторичной реплики из группы доступности (SQL Server)](remove-a-secondary-replica-from-an-availability-group-sql-server.md) и [Добавление вторичной реплики к группе доступности (SQL Server)](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9c337-121">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) and [Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9c337-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="9c337-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9c337-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="9c337-123">Permissions</span></span>  
 <span data-ttu-id="9c337-124">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="9c337-124">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9c337-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c337-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="9c337-126">**Присоединение реплики доступности к группе доступности**</span><span class="sxs-lookup"><span data-stu-id="9c337-126">**To join an availability replica to an availability group**</span></span>  
  
1.  <span data-ttu-id="9c337-127">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена вторичная реплика, и щелкните имя сервера, чтобы развернуть его дерево.</span><span class="sxs-lookup"><span data-stu-id="9c337-127">In Object Explorer, connect to the server instance that hosts the secondary replica, and click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="9c337-128">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="9c337-128">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="9c337-129">Выберите группу доступности вторичной реплики, к которой выполнено подключение.</span><span class="sxs-lookup"><span data-stu-id="9c337-129">Select the availability group of the secondary replica to which you are connected.</span></span>  
  
4.  <span data-ttu-id="9c337-130">Щелкните правой кнопкой мыши вторичную реплику и выберите пункт **Включить в группу доступности**.</span><span class="sxs-lookup"><span data-stu-id="9c337-130">Right-click the secondary replica, and click **Join to Availability Group**.</span></span>  
  
5.  <span data-ttu-id="9c337-131">Откроется диалоговое окно **Присоединить реплику к группе доступности** .</span><span class="sxs-lookup"><span data-stu-id="9c337-131">This opens the **Join Replica to Availability Group** dialog box.</span></span>  
  
6.  <span data-ttu-id="9c337-132">Чтобы присоединить вторичную реплику к группе доступности, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c337-132">To join the secondary replica to the availability group, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9c337-133">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9c337-133">Using Transact-SQL</span></span>  
 <span data-ttu-id="9c337-134">**Присоединение реплики доступности к группе доступности**</span><span class="sxs-lookup"><span data-stu-id="9c337-134">**To join an availability replica to an availability group**</span></span>  
  
1.  <span data-ttu-id="9c337-135">Подключитесь к экземпляру сервера, на котором находится дополнительная реплика.</span><span class="sxs-lookup"><span data-stu-id="9c337-135">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="9c337-136">Инструкция [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9c337-136">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="9c337-137">ALTER AVAILABILITY GROUP *имя_группы* JOIN</span><span class="sxs-lookup"><span data-stu-id="9c337-137">ALTER AVAILABILITY GROUP *group_name* JOIN</span></span>  
  
     <span data-ttu-id="9c337-138">где *имя_группы* — это имя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="9c337-138">where *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="9c337-139">В следующем примере объединяются дополнительная реплика и группа доступности `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="9c337-139">The following example, joins the secondary replica to the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG JOIN;  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="9c337-140">Пример использования инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)] в контексте см. в статье [Создание группы доступности (Transact-SQL)](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9c337-140">To see this [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement used in context, see [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="9c337-141">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c337-141">Using PowerShell</span></span>  
 <span data-ttu-id="9c337-142">**Присоединение реплики доступности к группе доступности**</span><span class="sxs-lookup"><span data-stu-id="9c337-142">**To join an availability replica to an availability group**</span></span>  
  
 <span data-ttu-id="9c337-143">В поставщике [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9c337-143">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell provider:</span></span>  
  
1.  <span data-ttu-id="9c337-144">Перейдите в каталог (`cd`) экземпляра сервера, на котором размещается вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="9c337-144">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="9c337-145">Присоедините вторичную реплику к группе доступности, выполнив командлет **Join-SqlAvailabilityGroup** с именем группы доступности.</span><span class="sxs-lookup"><span data-stu-id="9c337-145">Join the secondary replica to the availability group by executing the **Join-SqlAvailabilityGroup** cmdlet with the name of the availability group.</span></span>  
  
     <span data-ttu-id="9c337-146">Например, следующая команда присоединяет вторичную реплику, размещенную на экземпляре сервера по указанному пути, к группе доступности `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="9c337-146">For example, the following command joins a secondary replica hosted by the server instance located at the specified path to the availability group named `MyAg`.</span></span>  <span data-ttu-id="9c337-147">На этом экземпляре сервера должна быть размещена вторичная реплика этой группы доступности.</span><span class="sxs-lookup"><span data-stu-id="9c337-147">This server instance must host a secondary replica in this availability group.</span></span>  
  
    ```powershell
    Join-SqlAvailabilityGroup -Path SQLSERVER:\SQL\SecondaryServer\InstanceName -Name 'MyAg'  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="9c337-148">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c337-148">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="9c337-149">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="9c337-149">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="9c337-150">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9c337-150">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="9c337-151">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c337-151">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-configure-secondary-databases"></a><a name="FollowUp"></a><span data-ttu-id="9c337-152">Дальнейшие действия. Настройка баз данных-получателей</span><span class="sxs-lookup"><span data-stu-id="9c337-152">Follow Up: Configure Secondary Databases</span></span>  
 <span data-ttu-id="9c337-153">Для каждой базы данных в группе доступности необходимо настроить базу данных-получатель на экземпляре сервера, где находится дополнительная реплика.</span><span class="sxs-lookup"><span data-stu-id="9c337-153">For every database in the availability group, you need a secondary database on the server instance that is hosting the secondary replica.</span></span> <span data-ttu-id="9c337-154">Настроить базы данных-получатели до или после присоединения дополнительной реплики к группе доступности можно следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9c337-154">You can configure secondary databases either before or after you join a secondary replica to an availability group, as follows:</span></span>  
  
1.  <span data-ttu-id="9c337-155">Восстановите последние базы данных и резервные копии журналов каждой базы данных-источника на экземпляр сервера, где находится вторичная реплика, используя инструкцию RESTORE WITH NORECOVERY для каждой операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="9c337-155">Restore recent database and log backups of each primary database onto the server instance that hosts the secondary replica, using RESTORE WITH NORECOVERY for every restore operation.</span></span> <span data-ttu-id="9c337-156">Дополнительные сведения см. в статье [Ручная подготовка базы данных-получателя для присоединения к группе доступности (SQL Server)](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9c337-156">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="9c337-157">Присоедините каждую базу данных-получатель к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="9c337-157">Join each secondary database to the availability group.</span></span> <span data-ttu-id="9c337-158">Дополнительные сведения см. в статье [Присоединение базы данных-получателя к группе доступности (SQL Server)](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9c337-158">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c337-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="9c337-159">See Also</span></span>  
 <span data-ttu-id="9c337-160">[Создание и настройка групп доступности (SQL Server)](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9c337-160">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="9c337-161">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9c337-161">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="9c337-162">Устранение неполадок &#40;конфигурации группы доступности AlwaysOn SQL Server&#41;Deleted</span><span class="sxs-lookup"><span data-stu-id="9c337-162">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
