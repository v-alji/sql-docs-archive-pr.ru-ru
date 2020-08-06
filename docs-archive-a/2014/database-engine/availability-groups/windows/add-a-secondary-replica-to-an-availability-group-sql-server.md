---
title: Добавление вторичной реплики к группе доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], configuring
ms.assetid: 6669dcce-85f9-495f-aadf-7f62cff4a9da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 498103a781641c72e166c6b11663f5248ae5ccfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655974"
---
# <a name="add-a-secondary-replica-to-an-availability-group-sql-server"></a><span data-ttu-id="6dc0f-102">Добавление вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6dc0f-102">Add a Secondary Replica to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="6dc0f-103">В этом разделе описано, как добавить вторичную реплику в существующую группу доступности AlwaysOn с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dc0f-103">This topic describes how to add a secondary replica to an existing AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="6dc0f-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="6dc0f-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6dc0f-105">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="6dc0f-105">Prerequisites and Restrictions</span></span>](#PrerequisitesRestrictions)  
  
     [<span data-ttu-id="6dc0f-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="6dc0f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6dc0f-107">**Добавление реплики с помощью**</span><span class="sxs-lookup"><span data-stu-id="6dc0f-107">**To add a replica, using:**</span></span>  
  
     [<span data-ttu-id="6dc0f-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6dc0f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6dc0f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6dc0f-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="6dc0f-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6dc0f-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="6dc0f-111">**Дальнейшие действия**  [После добавления вторичной реплики](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="6dc0f-111">**Follow Up:**  [After Adding a Secondary Replica](#FollowUp)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="6dc0f-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6dc0f-112">Before You Begin</span></span>  
 <span data-ttu-id="6dc0f-113">Настоятельно рекомендуется прочитать этот раздел, прежде чем пытаться настроить свою первую группу доступности.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-113">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
##  <a name="prerequisites-and-restrictions"></a><a name="PrerequisitesRestrictions"></a> <span data-ttu-id="6dc0f-114">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="6dc0f-114">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="6dc0f-115">Необходимо подключиться к экземпляру сервера, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-115">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
 <span data-ttu-id="6dc0f-116">Дополнительные сведения см. в разделе [Предварительные требования, ограничения и рекомендации для групп доступности AlwaysOn (SQL Server)](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="6dc0f-116">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6dc0f-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="6dc0f-117">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6dc0f-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="6dc0f-118">Permissions</span></span>  
 <span data-ttu-id="6dc0f-119">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-119">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6dc0f-120">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6dc0f-120">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6dc0f-121">**Добавление реплики**</span><span class="sxs-lookup"><span data-stu-id="6dc0f-121">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="6dc0f-122">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена первичная реплика, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-122">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="6dc0f-123">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="6dc0f-123">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="6dc0f-124">Щелкните правой кнопкой группу доступности и выберите одну из следующих команд.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-124">Right-click the availability group, and select one of the following commands:</span></span>  
  
    -   <span data-ttu-id="6dc0f-125">Чтобы запустить мастер добавления реплики в группу доступности, выберите команду **Добавить реплику** .</span><span class="sxs-lookup"><span data-stu-id="6dc0f-125">Select the **Add Replica** command to launch the Add Replica to Availability Group Wizard.</span></span> <span data-ttu-id="6dc0f-126">Дополнительные сведения см. в разделе [Использование мастера добавления реплики в группу доступности (среда SQL Server Management Studio)](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="6dc0f-126">For more information, see [Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md).</span></span>  
  
    -   <span data-ttu-id="6dc0f-127">Либо выберите команду **Свойства** , чтобы открыть диалоговое окно **Свойства группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="6dc0f-127">Alternatively, select the **Properties** command to open the **Availability Group Properties** dialog box.</span></span> <span data-ttu-id="6dc0f-128">Чтобы добавить реплику в этом диалоговом окне, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-128">The steps for adding a replica in this dialog box are as follows:</span></span>  
  
        1.  <span data-ttu-id="6dc0f-129">На панели **Реплики доступности** этого диалогового окна нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="6dc0f-129">In the **Availability Replicas** pane of the dialog box, click the **Add** button.</span></span> <span data-ttu-id="6dc0f-130">Будет создана запись реплики с пустым полем «Экземпляр сервера».</span><span class="sxs-lookup"><span data-stu-id="6dc0f-130">This creates and selects a replica entry in which the blank Server Instance field is selected.</span></span>  
  
        2.  <span data-ttu-id="6dc0f-131">Введите имя экземпляра сервера, который соответствует обязательным условиям для размещения реплики доступности.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-131">Enter the name of a server instance that meets the prerequisites for hosting an availability replica.</span></span>  
  
         <span data-ttu-id="6dc0f-132">Чтобы добавить другие реплики, повторите предыдущие шаги.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-132">To add an additional replicas, repeat the preceding steps.</span></span> <span data-ttu-id="6dc0f-133">После завершения добавления реплик нажмите кнопку **ОК** для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-133">When you are done specifying replicas, click **OK** to complete the operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6dc0f-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6dc0f-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="6dc0f-135">**Добавление реплики**</span><span class="sxs-lookup"><span data-stu-id="6dc0f-135">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="6dc0f-136">Подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-136">Connect to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="6dc0f-137">Добавьте новую вторичную реплику в группу доступности с помощью предложения ADD REPLICA ON инструкции ALTER AVAILABILITY GROUP.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-137">Add the new secondary replica to the availability group by using the ADD REPLICA ON clause of the ALTER AVAILABILITY GROUP statement.</span></span> <span data-ttu-id="6dc0f-138">В предложении ADD REPLICA ON необходимо указать параметры ENDPOINT_URL, AVAILABILITY_MODE и FAILOVER_MODE.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-138">The ENDPOINT_URL, AVAILABILITY_MODE, and FAILOVER_MODE options are required in an ADD REPLICA ON clause.</span></span> <span data-ttu-id="6dc0f-139">Другие параметры реплики (BACKUP_PRIORITY, SECONDARY_ROLE, PRIMARY_ROLE и SESSION_TIMEOUT) являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-139">The other replica options- BACKUP_PRIORITY, SECONDARY_ROLE, PRIMARY_ROLE, and SESSION_TIMEOUT-are optional.</span></span> <span data-ttu-id="6dc0f-140">Дополнительные сведения см. в разделе [ALTER AVAILABILITY GROUP (Transact-SQL)](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6dc0f-140">For more information, see [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
     <span data-ttu-id="6dc0f-141">Например, следующая инструкция [!INCLUDE[tsql](../../../includes/tsql-md.md)] создает новую реплику в группе доступности `MyAG` в экземпляре сервера по умолчанию, размещенном на компьютере `COMPUTER04`, с URL-адресом конечной точки `TCP://COMPUTER04.Adventure-Works.com:5022'`.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-141">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement creates a new replica to an availability group named `MyAG` on the default server instance hosted by `COMPUTER04`, whose endpoint URL is `TCP://COMPUTER04.Adventure-Works.com:5022'`.</span></span> <span data-ttu-id="6dc0f-142">Данная реплика поддерживает переход на другой ресурс вручную и режим доступности «Asynchronous Commit».</span><span class="sxs-lookup"><span data-stu-id="6dc0f-142">This replica supports manual failover and asynchronous-commit availability mode.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG ADD REPLICA ON 'COMPUTER04'   
       WITH (  
             ENDPOINT_URL = 'TCP://COMPUTER04.Adventure-Works.com:5022',  
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             );  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="6dc0f-143">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="6dc0f-143">Using PowerShell</span></span>  
 <span data-ttu-id="6dc0f-144">**Добавление реплики**</span><span class="sxs-lookup"><span data-stu-id="6dc0f-144">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="6dc0f-145">Перейдите в каталог (`cd`) экземпляра сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-145">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="6dc0f-146">Используйте командлет **New-SqlAvailabilityReplica** .</span><span class="sxs-lookup"><span data-stu-id="6dc0f-146">Use the **New-SqlAvailabilityReplica** cmdlet.</span></span>  
  
     <span data-ttu-id="6dc0f-147">Например, следующая команда добавляет реплику доступности в существующую группу доступности с именем `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-147">For example, the following command adds an availability replica to an existing availability group named `MyAg`.</span></span> <span data-ttu-id="6dc0f-148">Данная реплика поддерживает переход на другой ресурс вручную и режим доступности «Asynchronous Commit».</span><span class="sxs-lookup"><span data-stu-id="6dc0f-148">This replica supports manual failover and asynchronous-commit availability mode.</span></span> <span data-ttu-id="6dc0f-149">В роли вторичной эта реплика будет поддерживать соединения с доступом на чтение, позволяя разгрузить обработку только для чтения для этой реплики.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-149">In the secondary role, this replica will support read access connections, allowing you to offload read-only processing to this replica.</span></span>  
  
    ```powershell
    $agPath = "SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg"  
    $endpointURL = "TCP://PrimaryServerName.domain.com:5022"  
    $failoverMode = "Manual"  
    $availabilityMode = "AsynchronousCommit"  
    $secondaryReadMode = "AllowAllConnections"  
  
    New-SqlAvailabilityReplica -Name SecondaryServer\Instance `   
    -EndpointUrl $endpointURL `   
    -FailoverMode $failoverMode `   
    -AvailabilityMode $availabilityMode `   
    -ConnectionModeInSecondaryRole $secondaryReadMode `   
    -Path $agPath  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="6dc0f-150">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-150">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="6dc0f-151">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6dc0f-151">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="6dc0f-152">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6dc0f-152">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="6dc0f-153">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="6dc0f-153">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-adding-a-secondary-replica"></a><a name="FollowUp"></a><span data-ttu-id="6dc0f-154">Дальнейшие действия. После добавления вторичной реплики</span><span class="sxs-lookup"><span data-stu-id="6dc0f-154">Follow Up: After Adding a Secondary Replica</span></span>  
 <span data-ttu-id="6dc0f-155">Для добавления реплики в существующую группу доступности необходимо выполнить следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-155">To add a replica for an existing availability group, you must perform the following steps:</span></span>  
  
1.  <span data-ttu-id="6dc0f-156">Подключитесь к экземпляру сервера, на котором должна быть размещена новая вторичная реплика доступности.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-156">Connect to the server instance that is going to host the new secondary replica.</span></span>  
  
2.  <span data-ttu-id="6dc0f-157">Присоедините новую вторичную реплику к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-157">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="6dc0f-158">Дополнительные сведения см. в разделе [Присоединение вторичной реплики к группе доступности (SQL Server)](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6dc0f-158">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="6dc0f-159">Для каждой базы данных в группе доступности создайте базу данных-получатель на экземпляре сервера, на котором размещается вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-159">For each database in the availability group, create a secondary database on the server instance that is hosting the secondary replica.</span></span> <span data-ttu-id="6dc0f-160">Дополнительные сведения см. в статье [Ручная подготовка базы данных-получателя для присоединения к группе доступности (SQL Server)](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6dc0f-160">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="6dc0f-161">Присоедините все новые базы данных-получатели к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-161">Join each of the new secondary databases to the availability group.</span></span> <span data-ttu-id="6dc0f-162">Дополнительные сведения см. в статье [Присоединение базы данных-получателя к группе доступности (SQL Server)](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6dc0f-162">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6dc0f-163">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="6dc0f-163">Related Tasks</span></span>  
 <span data-ttu-id="6dc0f-164">**Управление репликой доступности**</span><span class="sxs-lookup"><span data-stu-id="6dc0f-164">**To manage an availability replica**</span></span>  
  
-   [<span data-ttu-id="6dc0f-165">Присоединение вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6dc0f-165">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="6dc0f-166">Удаление вторичной реплики из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6dc0f-166">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="6dc0f-167">Настройка доступа только для чтения в реплике доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6dc0f-167">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="6dc0f-168">Смена режима доступности для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6dc0f-168">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="6dc0f-169">Смена режима отработки отказа для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6dc0f-169">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="6dc0f-170">Изменение периода ожидания сеанса для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6dc0f-170">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="6dc0f-171">Изменение периода ожидания сеанса для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6dc0f-171">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="6dc0f-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="6dc0f-172">See Also</span></span>  
 <span data-ttu-id="6dc0f-173">[ALTER AVAILABILITY GROUP (Transact-SQL)](/sql/t-sql/statements/alter-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6dc0f-173">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span></span>  
 <span data-ttu-id="6dc0f-174">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6dc0f-174">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="6dc0f-175">[Создание и настройка групп доступности (SQL Server)](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6dc0f-175">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="6dc0f-176">[Использование панели мониторинга AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="6dc0f-176">[Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="6dc0f-177">Отслеживание групп доступности (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6dc0f-177">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
  
