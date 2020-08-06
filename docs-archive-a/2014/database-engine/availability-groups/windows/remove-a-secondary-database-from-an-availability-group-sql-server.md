---
title: Удаление базы данных-получателя из группы доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.unjoindb.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], databases
ms.assetid: 4e51a570-58d7-4f01-9390-4198f3602576
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1c3de0afd73b46ae5594d26d1763f5bd78483efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657317"
---
# <a name="remove-a-secondary-database-from-an-availability-group-sql-server"></a><span data-ttu-id="a6d25-102">Удаление базы данных-получателя из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a6d25-102">Remove a Secondary Database from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="a6d25-103">В этом разделе описывается удаление базы данных-получателя из группы доступности AlwaysOn с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6d25-103">This topic describes how to remove a secondary database from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="a6d25-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a6d25-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a6d25-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a6d25-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="a6d25-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a6d25-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a6d25-107">**Удаление базы данных-получателя с помощью**</span><span class="sxs-lookup"><span data-stu-id="a6d25-107">**To remove a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="a6d25-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a6d25-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a6d25-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a6d25-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a6d25-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6d25-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="a6d25-111">**Дальнейшие действия**  [После удаления базы данных-получателя из группы доступности](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a6d25-111">**Follow Up:**  [After Removing a Secondary Database from an Availability Group](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a6d25-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a6d25-112">Before You Begin</span></span>  
  
###  <a name="Restrictions"></a>   
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="a6d25-113">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="a6d25-113">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="a6d25-114">Эта задача поддерживается только на вторичных репликах.</span><span class="sxs-lookup"><span data-stu-id="a6d25-114">This task is supported only on secondary replicas.</span></span> <span data-ttu-id="a6d25-115">Необходимо подключиться к экземпляру сервера, размещающему вторичную реплику, из которой удаляется база данных.</span><span class="sxs-lookup"><span data-stu-id="a6d25-115">You must be connected to the server instance that hosts the secondary replica from which the database is to be removed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a6d25-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="a6d25-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a6d25-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="a6d25-117">Permissions</span></span>  
 <span data-ttu-id="a6d25-118">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="a6d25-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a6d25-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a6d25-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a6d25-120">**Удаление базы данных-получателя из группы доступности**</span><span class="sxs-lookup"><span data-stu-id="a6d25-120">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="a6d25-121">В обозревателе объектов подключитесь к экземпляру сервера, размещающему вторичную реплику, из которой требуется удалить одну или несколько баз данных-получателей, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="a6d25-121">In Object Explorer, connect to the server instance that hosts the secondary replica from which you want to remove one or more secondary databases, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="a6d25-122">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="a6d25-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="a6d25-123">Выберите группу доступности и разверните узел **Базы данных доступности** .</span><span class="sxs-lookup"><span data-stu-id="a6d25-123">Select the availability group, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="a6d25-124">Этот шаг зависит от того, удаляется несколько баз данных или только одна база данных.</span><span class="sxs-lookup"><span data-stu-id="a6d25-124">This step depends on whether you want to remove multiple databases groups or only one database, as follows:</span></span>  
  
    -   <span data-ttu-id="a6d25-125">Чтобы удалить несколько баз данных, используйте панель **Подробности обозревателя объектов** , чтобы просмотреть и выбрать базы данных, которые требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="a6d25-125">To remove multiple databases, use the **Object Explorer Details** pane to view and select all the databases that you want to remove.</span></span> <span data-ttu-id="a6d25-126">Дополнительные сведения см. в разделе [Использование раздела "Подробности обозревателя объектов" для мониторинга групп доступности (среда SQL Server Management Studio)](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="a6d25-126">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="a6d25-127">Чтобы удалить одну базу данных, выберите ее в **обозревателе объектов** или на панели **Подробности обозревателя объектов** .</span><span class="sxs-lookup"><span data-stu-id="a6d25-127">To remove a single database, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="a6d25-128">Щелкните правой кнопкой мыши выбранную базу данных или базы данных и выберите в контекстном меню команду **Удалить базу данных-получателя** .</span><span class="sxs-lookup"><span data-stu-id="a6d25-128">Right-click the selected database or databases, and select **Remove Secondary Database** in the command menu.</span></span>  
  
6.  <span data-ttu-id="a6d25-129">В диалоговом окне **Удаление базы данных из группы доступности** нажмите кнопку **ОК**, чтобы удалить все выбранные базы данных.</span><span class="sxs-lookup"><span data-stu-id="a6d25-129">In the **Remove Database from Availability Group** dialog box, to remove all the listed databases, click **OK**.</span></span> <span data-ttu-id="a6d25-130">Если все перечисленные базы данных удалять не нужно, нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="a6d25-130">If you do not want to remove all the listed databases, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a6d25-131">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a6d25-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="a6d25-132">**Удаление базы данных-получателя из группы доступности**</span><span class="sxs-lookup"><span data-stu-id="a6d25-132">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="a6d25-133">Подключитесь к экземпляру сервера, на котором находится дополнительная реплика.</span><span class="sxs-lookup"><span data-stu-id="a6d25-133">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="a6d25-134">Используйте предложение [SET HADR в инструкции ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a6d25-134">Use the [SET HADR clause of the ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) statement, as follows:</span></span>  
  
     <span data-ttu-id="a6d25-135">ALTER DATABASE *имя_базы_данных* SET HADR OFF</span><span class="sxs-lookup"><span data-stu-id="a6d25-135">ALTER DATABASE *database_name* SET HADR OFF</span></span>  
  
     <span data-ttu-id="a6d25-136">где *имя_базы_данных* ― имя базы данных-получателя, удаляемой из группы доступности, к которой она относится.</span><span class="sxs-lookup"><span data-stu-id="a6d25-136">where *database_name* is the name of a secondary database to be removed from the availability group to which it belongs.</span></span>  
  
     <span data-ttu-id="a6d25-137">В следующем примере локальная база данных-получатель *MyDb2* удаляется из соответствующей группы доступности.</span><span class="sxs-lookup"><span data-stu-id="a6d25-137">The following example removes the local secondary database *MyDb2* from its availability group.</span></span>  
  
    ```sql
    ALTER DATABASE MyDb2 SET HADR OFF;  
    GO  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a6d25-138">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6d25-138">Using PowerShell</span></span>  
 <span data-ttu-id="a6d25-139">**Удаление базы данных-получателя из группы доступности**</span><span class="sxs-lookup"><span data-stu-id="a6d25-139">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="a6d25-140">Перейдите в каталог (`cd`) экземпляра сервера, на котором размещается вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="a6d25-140">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="a6d25-141">Используйте командлет **Remove-SqlAvailabilityDatabase** , указав имя базы данных доступности, которую требуется удалить из группы доступности.</span><span class="sxs-lookup"><span data-stu-id="a6d25-141">Use the **Remove-SqlAvailabilityDatabase** cmdlet, specifying the name of the availability database to be removed from the availability group.</span></span> <span data-ttu-id="a6d25-142">Когда установлено подключение к экземпляру сервера, на котором находится вторичная реплика, из группы доступности удаляется только локальная база данных-получатель.</span><span class="sxs-lookup"><span data-stu-id="a6d25-142">When you are connected to a server instance that hosts a secondary replica, only the local secondary database is removed from the availability group.</span></span>  
  
     <span data-ttu-id="a6d25-143">Например, следующая команда удаляет базу данных-получатель `MyDb8` из вторичной реплики, размещенной на экземпляре сервера `SecondaryComputer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="a6d25-143">For example, the following command removes the secondary database `MyDb8` from the secondary replica hosted by the server instance named `SecondaryComputer\Instance`.</span></span> <span data-ttu-id="a6d25-144">Синхронизация данных для удаленных баз данных-получателей прекращается.</span><span class="sxs-lookup"><span data-stu-id="a6d25-144">Data synchronization to the removed secondary databases ceases.</span></span> <span data-ttu-id="a6d25-145">Эта команда не влияет на базу данных-источник и на любые другие базы данных-получатели.</span><span class="sxs-lookup"><span data-stu-id="a6d25-145">This command does not affect the primary database or any other secondary databases.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\SecondaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb8  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="a6d25-146">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6d25-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="a6d25-147">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a6d25-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="a6d25-148">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a6d25-148">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="a6d25-149">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6d25-149">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-a-secondary-database-from-an-availability-group"></a><a name="FollowUp"></a><span data-ttu-id="a6d25-150">Дальнейшие действия. После удаления базы данных-получателя из группы доступности</span><span class="sxs-lookup"><span data-stu-id="a6d25-150">Follow Up: After Removing a Secondary Database from an Availability Group</span></span>  
 <span data-ttu-id="a6d25-151">После удаления базы данных-получателя она перестает входить в группу доступности, кроме того, из группы доступности удаляются все сведения об этой базе данных-получателе.</span><span class="sxs-lookup"><span data-stu-id="a6d25-151">When a secondary database is removed, it is no longer joined to the availability group and all information about the removed secondary database is discarded by the availability group.</span></span> <span data-ttu-id="a6d25-152">Удаленная база данных-получатель переводится в состояние RESTORING.</span><span class="sxs-lookup"><span data-stu-id="a6d25-152">The removed secondary database is placed in the RESTORING state.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="a6d25-153">В течение некоторого времени после удаления базы данных-получателя можно перезапустить синхронизацию данных AlwaysOn в базе данных, повторно присоединив ее к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="a6d25-153">For a short time after removing a secondary database, you might be able to restart AlwaysOn data synchronization on the database by re-joining it to the availability group.</span></span> <span data-ttu-id="a6d25-154">Дополнительные сведения см. в статье [Присоединение базы данных-получателя к группе доступности (SQL Server)](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a6d25-154">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="a6d25-155">В этот момент поступить с удаленной базой данных-получателем можно следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a6d25-155">At this point there are alternative ways of dealing with a removed secondary database:</span></span>  
  
-   <span data-ttu-id="a6d25-156">Если эта база данных-получатель больше не нужна, ее можно удалить.</span><span class="sxs-lookup"><span data-stu-id="a6d25-156">If you no longer need the secondary database, you can drop it.</span></span>  
  
     <span data-ttu-id="a6d25-157">Дополнительные сведения см. в разделе [DROP DATABASE (Transact-SQL)](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) или [Удаление базы данных](../../../relational-databases/databases/delete-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="a6d25-157">For more information, see [DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) or [Delete a Database](../../../relational-databases/databases/delete-a-database.md).</span></span>  
  
-   <span data-ttu-id="a6d25-158">Если после удаления базы данных-получателя из группы доступности она еще может понадобиться, ее можно восстановить.</span><span class="sxs-lookup"><span data-stu-id="a6d25-158">If you want to access a removed secondary database after it has been removed from the availability group, you can recover the database.</span></span> <span data-ttu-id="a6d25-159">Однако при восстановлении удаленной базы данных-получателя в режиме «в сети» окажутся две разные базы данных с одним именем.</span><span class="sxs-lookup"><span data-stu-id="a6d25-159">However, if you recover a removed secondary database, two divergent, independent databases that have the same name are online.</span></span> <span data-ttu-id="a6d25-160">Необходимо обеспечить, чтобы клиенты могли получить доступ только к текущей базе данных-источнику.</span><span class="sxs-lookup"><span data-stu-id="a6d25-160">You must make sure that clients can access only the current primary database.</span></span>  
  
     <span data-ttu-id="a6d25-161">Дополнительные сведения см. в разделе [Восстановление базы данных без восстановления данных (Transact-SQL)](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a6d25-161">For more information, see [Recover a Database Without Restoring Data &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d25-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6d25-162">See Also</span></span>  
 <span data-ttu-id="a6d25-163">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a6d25-163">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="a6d25-164">Удаление базы данных-источника из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a6d25-164">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
