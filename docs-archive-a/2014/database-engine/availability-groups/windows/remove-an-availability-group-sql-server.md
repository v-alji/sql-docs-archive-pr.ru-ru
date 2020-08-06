---
title: Удаление группы доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.deleteag.f1
helpviewer_keywords:
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], dropping
ms.assetid: 4b7f7f62-43a3-49db-a72e-22d4d7c2ddbb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c17b7d5b362d8b4030d66ebf7ba0e425495410e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657312"
---
# <a name="remove-an-availability-group-sql-server"></a><span data-ttu-id="8409e-102">Удаление группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8409e-102">Remove an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="8409e-103">В этом разделе описывается удаление группы доступности AlwaysOn с помощью [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)] или PowerShell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8409e-103">This topic describes how to delete (drop) an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="8409e-104">Если экземпляр сервера, на котором размещена одна из реплик доступности, находится в режиме «вне сети» при удалении группы доступности, то после перехода в режим «в сети» локальная реплика доступности будет удалена с экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="8409e-104">If a server instance that hosts one of the availability replicas is offline when you delete an availability group, after coming online, the server instance will drop the local availability replica.</span></span> <span data-ttu-id="8409e-105">При удалении группы доступности удаляются все связанные прослушиватели группы доступности.</span><span class="sxs-lookup"><span data-stu-id="8409e-105">Dropping an availability group deletes any associated availability group listener.</span></span>  
  
 <span data-ttu-id="8409e-106">Обратите внимание, что при необходимости группу доступности вы можете удалить из любого узла отказоустойчивого кластера Windows Server (WSFC), обладающего учетными данными, соответствующими группе доступности.</span><span class="sxs-lookup"><span data-stu-id="8409e-106">Note that, if necessary, you can drop an availability group from any Windows Server Failover Clustering (WSFC) node that possesses the correct security credentials for the availability group.</span></span> <span data-ttu-id="8409e-107">Благодаря этому обеспечивается возможность удаления группы доступности при отсутствии ее оставшихся реплик доступности.</span><span class="sxs-lookup"><span data-stu-id="8409e-107">This enables you to delete an availability group when none of its availability replicas remain.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8409e-108">Если возможно, удаляйте группу доступности только при наличии подключения к экземпляру сервера, где размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="8409e-108">If possible, remove the availability group only while connected to the server instance that hosts the primary replica.</span></span> <span data-ttu-id="8409e-109">При удалении группы доступности с первичной реплики разрешается внесение изменений в бывшие базы данных-источники (без защиты высокого уровня доступности).</span><span class="sxs-lookup"><span data-stu-id="8409e-109">When the availability group is dropped from the primary replica, changes are allowed in the former primary databases (without high availability protection).</span></span> <span data-ttu-id="8409e-110">Удаление группы доступности из вторичной реплики переводит первичную реплику в состояние RESTORING (восстановление), и в базы данных не разрешается вносить изменения.</span><span class="sxs-lookup"><span data-stu-id="8409e-110">Deleting an availability group from a secondary replica leaves the primary replica in the RESTORING state, and changes are not allowed on the databases.</span></span>  
  
-   <span data-ttu-id="8409e-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="8409e-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8409e-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="8409e-112">Limitations and Recommendations</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8409e-113">Безопасность</span><span class="sxs-lookup"><span data-stu-id="8409e-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8409e-114">**Удаление группы доступности с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="8409e-114">**To delete an availability group, using:**</span></span>  
  
     [<span data-ttu-id="8409e-115">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8409e-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8409e-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8409e-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="8409e-117">PowerShell</span><span class="sxs-lookup"><span data-stu-id="8409e-117">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="8409e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8409e-118">Related Content</span></span>](#RelatedContent)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8409e-119">Перед началом</span><span class="sxs-lookup"><span data-stu-id="8409e-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-recommendations"></a><a name="Restrictions"></a><span data-ttu-id="8409e-120">Ограничения и рекомендации</span><span class="sxs-lookup"><span data-stu-id="8409e-120">Limitations and Recommendations</span></span>  
  
-   <span data-ttu-id="8409e-121">При использовании группы доступности в режиме «в сети» удаление этой группы из вторичной реплики приведет к переходу первичной реплики в состояние RESTORING.</span><span class="sxs-lookup"><span data-stu-id="8409e-121">When the availability group is online, deleting it from a secondary replica causes the primary replica to transition to the RESTORING state.</span></span> <span data-ttu-id="8409e-122">Если возможно, удаляйте группу доступности только с того экземпляра сервера, где размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="8409e-122">Therefore, if possible, remove the availability group only from the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="8409e-123">Если удалить группу доступности с компьютера, который был удален или исключен из отказоустойчивого кластера WSFC, группа доступности удаляется только локально.</span><span class="sxs-lookup"><span data-stu-id="8409e-123">If you delete an availability group from a computer that has been removed or evicted from the WSFC failover cluster, the availability group is only deleted locally.</span></span>  
  
-   <span data-ttu-id="8409e-124">Старайтесь не удалять группу доступности, если отказоустойчивый кластер Windows Server (WSFC) не имеет кворума.</span><span class="sxs-lookup"><span data-stu-id="8409e-124">Avoid dropping an availability group when the Windows Server Failover Clustering (WSFC) cluster has no quorum.</span></span> <span data-ttu-id="8409e-125">Если необходимо удалить группу доступности, когда нет кворума кластера, то группа доступности метаданных, хранимая в кластере, не удаляется.</span><span class="sxs-lookup"><span data-stu-id="8409e-125">If you must drop an availability group while the cluster lacks quorum, the metadata availability group that is stored in the cluster is not removed.</span></span> <span data-ttu-id="8409e-126">После того как кластер снова получит кворум, необходимо будет удалить группу доступности еще раз, чтобы удалить ее из кластера WSFC.</span><span class="sxs-lookup"><span data-stu-id="8409e-126">After the cluster regains quorum, you will need to drop the availability group again to remove it from the WSFC cluster.</span></span>  
  
-   <span data-ttu-id="8409e-127">На вторичной реплике команда DROP AVAILABILITY GROUP должна использоваться только в экстренных случаях.</span><span class="sxs-lookup"><span data-stu-id="8409e-127">On a secondary replica, DROP AVAILABILITY GROUP should only be used only for emergency purposes.</span></span> <span data-ttu-id="8409e-128">Это связано с тем, что удаление группы доступности переводит группу в режим «вне сети».</span><span class="sxs-lookup"><span data-stu-id="8409e-128">This is because dropping an availability group takes the availability group offline.</span></span> <span data-ttu-id="8409e-129">При удалении группы доступности из вторичной реплики первичная реплика не может определить, возникло состояние OFFLINE из-за потери кворума, принудительного перехода на другой ресурс или команды DROP AVAILABILITY GROUP.</span><span class="sxs-lookup"><span data-stu-id="8409e-129">If you drop the availability group from a secondary replica, the primary replica cannot determine whether the OFFLINE state occurred because of quorum loss, a forced failover, or a DROP AVAILABILITY GROUP command.</span></span> <span data-ttu-id="8409e-130">Первичная реплика переходит в состояние RESTORING, чтобы избежать возможной ситуации с дроблением.</span><span class="sxs-lookup"><span data-stu-id="8409e-130">The primary replica transitions to the RESTORING state to prevent a possible split-brain situation.</span></span> <span data-ttu-id="8409e-131">Дополнительные сведения см. в статье [Поведение инструкции DROP AVAILABILITY GROUP](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (блог инженеров CSS SQL Server).</span><span class="sxs-lookup"><span data-stu-id="8409e-131">For more information, see [How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (CSS SQL Server Engineers blog).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8409e-132">безопасность</span><span class="sxs-lookup"><span data-stu-id="8409e-132">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8409e-133">Permissions</span><span class="sxs-lookup"><span data-stu-id="8409e-133">Permissions</span></span>  
 <span data-ttu-id="8409e-134">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="8409e-134">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span> <span data-ttu-id="8409e-135">Для удаления группы доступности, которая не размещена на экземпляре локального сервера, необходимо разрешение CONTROL SERVER или разрешение CONTROL для этой группы доступности.</span><span class="sxs-lookup"><span data-stu-id="8409e-135">To drop an availability group that is not hosted by the local server instance you need CONTROL SERVER permission or CONTROL permission on that Availability Group.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8409e-136">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8409e-136">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="8409e-137">**Удаление группы доступности**</span><span class="sxs-lookup"><span data-stu-id="8409e-137">**To delete an availability group**</span></span>  
  
1.  <span data-ttu-id="8409e-138">В обозревателе объектов при наличии соответствующей возможности подключитесь к экземпляру сервера, на котором размещена первичная реплика, или подключитесь к другому экземпляру сервера, включенному для групп доступности AlwaysOn на узле WSFC, на котором имеются правильные учетные данные для безопасного доступа для группы доступности.</span><span class="sxs-lookup"><span data-stu-id="8409e-138">In Object Explorer, connect to the server instance that hosts primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span> <span data-ttu-id="8409e-139">Разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="8409e-139">Expand the server tree.</span></span>  
  
2.  <span data-ttu-id="8409e-140">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="8409e-140">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="8409e-141">Этот шаг зависит от того, требуется ли удалить несколько групп доступности или только одну группу доступности:</span><span class="sxs-lookup"><span data-stu-id="8409e-141">This step depends on whether you want to delete multiple availability groups or only one availability group, as follows:</span></span>  
  
    -   <span data-ttu-id="8409e-142">Чтобы удалить несколько групп доступности (первичные реплики которых находятся на подключенном экземпляре сервера), используйте область **Подробности обозревателя объектов** для просмотра и выбора всех групп доступности, которые необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="8409e-142">To delete multiple availability groups (whose primary replicas are on the connected server instance), use the **Object Explorer Details** pane to view and select all the availability groups that you want to delete.</span></span> <span data-ttu-id="8409e-143">Дополнительные сведения см. в разделе [Использование раздела "Подробности обозревателя объектов" для мониторинга групп доступности (среда SQL Server Management Studio)](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="8409e-143">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="8409e-144">Чтобы удалить одну группу доступности, выберите ее на панели **обозревателя объектов** или на панели **Подробности обозревателя объектов** .</span><span class="sxs-lookup"><span data-stu-id="8409e-144">To delete a single availability group, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
4.  <span data-ttu-id="8409e-145">Щелкните правой кнопкой мыши выбранные группы или группу доступности и выберите команду **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="8409e-145">Right-click the selected availability group or groups, and select the **Delete** command.</span></span>  
  
5.  <span data-ttu-id="8409e-146">В диалоговом окне **Удаление группы доступности** для удаления всех указанных групп доступности щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8409e-146">In the **Remove Availability Group** dialog box, to delete all the listed availability groups, click **OK**.</span></span> <span data-ttu-id="8409e-147">Если все перечисленные группы доступности удалять не нужно, щелкните **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="8409e-147">If you do not want to remove all the listed availability groups, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8409e-148">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8409e-148">Using Transact-SQL</span></span>  
 <span data-ttu-id="8409e-149">**Удаление группы доступности**</span><span class="sxs-lookup"><span data-stu-id="8409e-149">**To delete an availability group**</span></span>  
  
1.  <span data-ttu-id="8409e-150">При наличии соответствующей возможности подключитесь к экземпляру сервера, на котором размещена первичная реплика, или подключитесь к другому экземпляру сервера, включенному для групп доступности AlwaysOn на узле WSFC, на котором имеются правильные учетные данные для безопасного доступа для группы доступности.</span><span class="sxs-lookup"><span data-stu-id="8409e-150">Connect to the server instance that hosts the primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span>  
  
2.  <span data-ttu-id="8409e-151">Используйте инструкцию [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8409e-151">Use the [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql) statement, as follows</span></span>  
  
     <span data-ttu-id="8409e-152">DROP AVAILABILITY GROUP *имя_группы*</span><span class="sxs-lookup"><span data-stu-id="8409e-152">DROP AVAILABILITY GROUP *group_name*</span></span>  
  
     <span data-ttu-id="8409e-153">где *имя_группы* — имя удаляемой группы доступности.</span><span class="sxs-lookup"><span data-stu-id="8409e-153">where *group_name* is the name of the availability group to be dropped.</span></span>  
  
     <span data-ttu-id="8409e-154">В следующем примере выполняется удаление группы доступности `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="8409e-154">The following example deletes the `MyAG` availability group.</span></span>  
  
    ```sql
    DROP AVAILABILITY GROUP MyAG;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="8409e-155">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="8409e-155">Using PowerShell</span></span>  
 <span data-ttu-id="8409e-156">**Удаление группы доступности**</span><span class="sxs-lookup"><span data-stu-id="8409e-156">**To delete an availability group**</span></span>  
  
 <span data-ttu-id="8409e-157">В поставщике [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8409e-157">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell provider:</span></span>  
  
1.  <span data-ttu-id="8409e-158">При наличии соответствующей возможности измените каталог (`cd`) на экземпляр сервера, на котором размещена первичная реплика, или подключитесь к другому экземпляру сервера, включенному для групп доступности AlwaysOn на узле WSFC, на котором имеются правильные учетные данные для безопасного доступа для группы доступности.</span><span class="sxs-lookup"><span data-stu-id="8409e-158">Change directory (`cd`) to the server instance that hosts the primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span>  
  
2.  <span data-ttu-id="8409e-159">Используйте командлет **Remove-SqlAvailabilityGroup** .</span><span class="sxs-lookup"><span data-stu-id="8409e-159">Use the **Remove-SqlAvailabilityGroup** cmdlet.</span></span>  
  
     <span data-ttu-id="8409e-160">Например, следующая команда удаляет группу доступности с именем `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="8409e-160">For example, the following command removes the availability group named `MyAg`.</span></span> <span data-ttu-id="8409e-161">Эта команда может выполняться на любом экземпляре сервера, где размещена реплика доступности для группы доступности.</span><span class="sxs-lookup"><span data-stu-id="8409e-161">This command can be executed on any server instance that hosts an availability replica for the availability group.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="8409e-162">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8409e-162">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="8409e-163">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="8409e-163">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="8409e-164">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8409e-164">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="8409e-165">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="8409e-165">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="8409e-166">См. также</span><span class="sxs-lookup"><span data-stu-id="8409e-166">Related Content</span></span>  
  
-   <span data-ttu-id="8409e-167">[Принцип работы. Поведение инструкции DROP AVAILABILITY GROUP](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (блог инженеров CSS SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8409e-167">[How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (CSS SQL Server Engineers blog)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8409e-168">См. также:</span><span class="sxs-lookup"><span data-stu-id="8409e-168">See Also</span></span>  
 <span data-ttu-id="8409e-169">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8409e-169">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="8409e-170">Создание и настройка групп доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8409e-170">Creation and Configuration of Availability Groups &#40;SQL Server&#41;</span></span>](creation-and-configuration-of-availability-groups-sql-server.md)  
