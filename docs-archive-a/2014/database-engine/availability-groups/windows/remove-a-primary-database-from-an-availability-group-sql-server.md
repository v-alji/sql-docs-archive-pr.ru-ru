---
title: Удаление базы данных-источника из группы доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removeprimarydb.f1
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 6d4ca31e-ddf0-44bf-be5e-a5da060bf096
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6fafaf6464431d68f8cfdf9dc9d8fa844a42a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657319"
---
# <a name="remove-a-primary-database-from-an-availability-group-sql-server"></a><span data-ttu-id="9434f-102">Удаление базы данных-источника из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9434f-102">Remove a Primary Database from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="9434f-103">В этом разделе описывается удаление базы данных-источника и соответствующих баз данных-получателей из группы доступности AlwaysOn с использованием среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)] или PowerShell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9434f-103">This topic describes how to remove both the primary database and the corresponding secondary database(s) from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="9434f-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="9434f-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9434f-105">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="9434f-105">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="9434f-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="9434f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9434f-107">**Удаление база данных доступности с помощью**</span><span class="sxs-lookup"><span data-stu-id="9434f-107">**To remove an availability database, using:**</span></span>  
  
     [<span data-ttu-id="9434f-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9434f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9434f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9434f-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="9434f-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9434f-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="9434f-111">**Дальнейшие действия**  [После удаления базы данных доступности из группы доступности](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="9434f-111">**Follow Up:**  [After Removing an Availability Database from an Availability Group](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9434f-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="9434f-112">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="9434f-113">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="9434f-113">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="9434f-114">Эта задача поддерживается только на первичных репликах.</span><span class="sxs-lookup"><span data-stu-id="9434f-114">This task is supported only on primary replicas.</span></span> <span data-ttu-id="9434f-115">Необходимо подключиться к экземпляру сервера, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="9434f-115">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9434f-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="9434f-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9434f-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="9434f-117">Permissions</span></span>  
 <span data-ttu-id="9434f-118">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="9434f-118">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9434f-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9434f-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="9434f-120">**Удаление базы данных доступности**</span><span class="sxs-lookup"><span data-stu-id="9434f-120">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="9434f-121">В обозревателе объектов подключитесь к экземпляру сервера, размещающего базы данных, которые требуется удалить, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="9434f-121">In Object Explorer, connect to the server instance that hosts the primary replica of the database or databases to be removed, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="9434f-122">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="9434f-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="9434f-123">Выберите группу доступности и разверните узел **Базы данных доступности** .</span><span class="sxs-lookup"><span data-stu-id="9434f-123">Select the availability group, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="9434f-124">Этот шаг зависит от того, удаляется несколько баз данных или только одна база данных.</span><span class="sxs-lookup"><span data-stu-id="9434f-124">This step depends on whether you want to remove multiple databases groups or only one database, as follows:</span></span>  
  
    -   <span data-ttu-id="9434f-125">Чтобы удалить несколько баз данных, используйте панель **Подробности обозревателя объектов** , чтобы просмотреть и выбрать базы данных, которые требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="9434f-125">To remove multiple databases, use the **Object Explorer Details** pane to view and select all the databases that you want to remove.</span></span> <span data-ttu-id="9434f-126">Дополнительные сведения см. в разделе [Использование раздела "Подробности обозревателя объектов" для мониторинга групп доступности (среда SQL Server Management Studio)](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9434f-126">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="9434f-127">Чтобы удалить одну базу данных, выберите ее в **обозревателе объектов** или на панели **Подробности обозревателя объектов** .</span><span class="sxs-lookup"><span data-stu-id="9434f-127">To remove a single database, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="9434f-128">Щелкните правой кнопкой мыши выбранную базу данных или базы данных и выберите в контекстном меню команду **Удаление базы данных из группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="9434f-128">Right-click the selected database or databases, and select **Remove Database from Availability Group** in the command menu.</span></span>  
  
6.  <span data-ttu-id="9434f-129">В диалоговом окне **Удаление баз данных из группы доступности** нажмите кнопку **ОК**, чтобы удалить все выбранные базы данных.</span><span class="sxs-lookup"><span data-stu-id="9434f-129">In the **Remove Databases from Availability Group** dialog box, to remove all the listed databases, click **OK**.</span></span> <span data-ttu-id="9434f-130">Если все удалять не нужно, нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="9434f-130">If you do not want to remove all them, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9434f-131">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9434f-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="9434f-132">**Удаление базы данных доступности**</span><span class="sxs-lookup"><span data-stu-id="9434f-132">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="9434f-133">Подключитесь к экземпляру сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="9434f-133">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="9434f-134">Инструкция [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9434f-134">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="9434f-135">ALTER AVAILABILITY GROUP *имя_группы* REMOVE DATABASE *имя_базы_данных_доступности*</span><span class="sxs-lookup"><span data-stu-id="9434f-135">ALTER AVAILABILITY GROUP *group_name* REMOVE DATABASE *availability_database_name*</span></span>  
  
     <span data-ttu-id="9434f-136">где *имя_группы* — имя группы доступности, а *имя_базы_данных_доступности* — имя удаляемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="9434f-136">where *group_name* is the name of the availability group and *database_name* is the name of the database to be removed.</span></span>  
  
     <span data-ttu-id="9434f-137">В следующем примере удаляется база данных с именем `Db6` из группы доступности `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="9434f-137">The following example removes a databases named `Db6` from the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG REMOVE DATABASE Db6;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="9434f-138">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="9434f-138">Using PowerShell</span></span>  
 <span data-ttu-id="9434f-139">**Удаление базы данных доступности**</span><span class="sxs-lookup"><span data-stu-id="9434f-139">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="9434f-140">Перейдите в каталог (`cd`) экземпляра сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="9434f-140">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="9434f-141">Используйте командлет `Remove-SqlAvailabilityDatabase`, указав имя базы данных доступности, которую требуется удалить из группы доступности.</span><span class="sxs-lookup"><span data-stu-id="9434f-141">Use the `Remove-SqlAvailabilityDatabase` cmdlet, specifying the name of the availability database to be removed from the availability group.</span></span> <span data-ttu-id="9434f-142">Если установлено подключение к экземпляру сервера, на котором размещается первичная реплика, из группы доступности удаляется как база данных-источник, так и все соответствующие базы данных-получатели.</span><span class="sxs-lookup"><span data-stu-id="9434f-142">When you are connected to the server instance that hosts the primary replica, the primary database and its corresponding secondary databases are all removed from the availability group.</span></span>  
  
     <span data-ttu-id="9434f-143">Например, следующая команда удаляет базу данных доступности `MyDb9` из группы доступности с именем `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="9434f-143">For example, the following command removes the availability database `MyDb9` from the availability group named `MyAg`.</span></span> <span data-ttu-id="9434f-144">Поскольку команда выполняется в экземпляре сервера, на котором размещается первичная реплика, из группы доступности удаляется как база данных-источник, так и все соответствующие базы данных-получатели.</span><span class="sxs-lookup"><span data-stu-id="9434f-144">Because the command is executed on the server instance that hosts the primary replica, the primary database and all its corresponding secondary databases are removed from the availability group.</span></span> <span data-ttu-id="9434f-145">Синхронизация данных для этой базы данных во всех вторичных репликах больше происходить не будет.</span><span class="sxs-lookup"><span data-stu-id="9434f-145">Data synchronization will no longer occur for this database on any secondary replica.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\PrimaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb9  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="9434f-146">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9434f-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="9434f-147">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="9434f-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="9434f-148">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9434f-148">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="9434f-149">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="9434f-149">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-an-availability-database-from-an-availability-group"></a><a name="FollowUp"></a> <span data-ttu-id="9434f-150">Дальнейшие действия. После удаления базы данных доступности из группы доступности</span><span class="sxs-lookup"><span data-stu-id="9434f-150">Follow Up: After Removing an Availability Database from an Availability Group</span></span>  
 <span data-ttu-id="9434f-151">При удалении базы данных доступности из соответствующей группы доступности выполнение синхронизации данных между бывшей базой данных-источником и соответствующими базами данных-получателями прекращается.</span><span class="sxs-lookup"><span data-stu-id="9434f-151">Removing an availability database from its availability group ends data synchronization between the former primary database and the corresponding secondary databases.</span></span> <span data-ttu-id="9434f-152">Бывшая база данных-источник остается в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="9434f-152">The former primary database remains online.</span></span> <span data-ttu-id="9434f-153">Все соответствующие базы данных-получатели переводятся в состояние RESTORING.</span><span class="sxs-lookup"><span data-stu-id="9434f-153">Every corresponding secondary database is placed in the RESTORING state.</span></span>  
  
 <span data-ttu-id="9434f-154">В этот момент поступить с удаленной базой данных-получателем можно следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9434f-154">At this point there are alternative ways of dealing with a removed secondary database:</span></span>  
  
-   <span data-ttu-id="9434f-155">Если база данных-получатель больше не нужна, ее можно удалить.</span><span class="sxs-lookup"><span data-stu-id="9434f-155">If you no longer need a given secondary database, you can drop it.</span></span>  
  
     <span data-ttu-id="9434f-156">Дополнительные сведения см. в разделе [Удаление базы данных](../../../relational-databases/databases/delete-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="9434f-156">For more information, see [Delete a Database](../../../relational-databases/databases/delete-a-database.md).</span></span>  
  
-   <span data-ttu-id="9434f-157">Если после удаления базы данных-получателя из группы доступности она еще может понадобиться, ее можно восстановить.</span><span class="sxs-lookup"><span data-stu-id="9434f-157">If you want to access a removed secondary database after it has been removed from the availability group, you can recover the database.</span></span> <span data-ttu-id="9434f-158">Однако при восстановлении удаленной базы данных-получателя в режиме «в сети» окажутся две разные базы данных с одним именем.</span><span class="sxs-lookup"><span data-stu-id="9434f-158">However, if you recover a removed secondary database, two divergent, independent databases that have the same name are online.</span></span> <span data-ttu-id="9434f-159">Нужно обеспечить, чтобы клиент имел доступ только к одной из них — обычно самой последней базе данных-источнику.</span><span class="sxs-lookup"><span data-stu-id="9434f-159">You must make sure that clients can access only one of them, typically the most recent primary database.</span></span>  
  
     <span data-ttu-id="9434f-160">Дополнительные сведения см. в разделе [Восстановление базы данных без восстановления данных (Transact-SQL)](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9434f-160">For more information, see [Recover a Database Without Restoring Data &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9434f-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="9434f-161">See Also</span></span>  
 <span data-ttu-id="9434f-162">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9434f-162">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="9434f-163">Удаление базы данных-получателя из группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9434f-163">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
