---
title: Добавление базы данных в группу доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 2a54eef8-9e8e-4e04-909c-6970112d55cc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0907cf711cac65ad77a8948841d92705fdc1eac9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655393"
---
# <a name="add-a-database-to-an-availability-group-sql-server"></a><span data-ttu-id="43660-102">Добавление базы данных в группу доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="43660-102">Add a Database to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="43660-103">В этом разделе описывается добавление базы данных в группу доступности AlwaysOn с помощью [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell в среде [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43660-103">This topic describes how to add a database to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="43660-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="43660-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="43660-105">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="43660-105">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="43660-106">Разрешения</span><span class="sxs-lookup"><span data-stu-id="43660-106">Permissions</span></span>](#Permissions)  
  
-   <span data-ttu-id="43660-107">**Добавление базы данных в группу доступности с помощью:**</span><span class="sxs-lookup"><span data-stu-id="43660-107">**To add a database to an availability group, using:**</span></span>  
  
     [<span data-ttu-id="43660-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43660-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="43660-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43660-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="43660-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="43660-110">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="43660-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="43660-111">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="43660-112">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="43660-112">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="43660-113">Необходимо подключиться к экземпляру сервера, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="43660-113">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="43660-114">База данных должна находиться на экземпляре сервера, на котором размещена первичная реплика, и должна соответствовать предварительным условиям и требованиям к базам данных доступности.</span><span class="sxs-lookup"><span data-stu-id="43660-114">The database must reside on the server instance that hosts the primary replica and comply with the prerequisites and restrictions for availability databases.</span></span> <span data-ttu-id="43660-115">Дополнительные сведения см. в разделе [Предварительные требования, ограничения и рекомендации для групп доступности AlwaysOn (SQL Server)](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="43660-115">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="43660-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="43660-116">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="43660-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="43660-117">Permissions</span></span>  
 <span data-ttu-id="43660-118">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="43660-118">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="43660-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43660-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="43660-120">**Добавление базы данных в группу доступности**</span><span class="sxs-lookup"><span data-stu-id="43660-120">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="43660-121">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена первичная реплика, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="43660-121">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="43660-122">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="43660-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="43660-123">Щелкните правой кнопкой группу доступности и выберите одну из следующих команд.</span><span class="sxs-lookup"><span data-stu-id="43660-123">Right-click the availability group, and select one of the following commands:</span></span>  
  
    -   <span data-ttu-id="43660-124">Для запуска мастера добавления базы данных в группу доступности выберите команду **Добавление базы данных** .</span><span class="sxs-lookup"><span data-stu-id="43660-124">To launch the Add Database to Availability Group Wizard, select the **Add Database** command.</span></span> <span data-ttu-id="43660-125">Дополнительные сведения см. в разделе [Использование мастера добавления базы данных в группу доступности (среда SQL Server Management Studio)](availability-group-add-database-to-group-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="43660-125">For more information, see [Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md).</span></span>  
  
    -   <span data-ttu-id="43660-126">Для добавления одной или нескольких баз данных путем их указания в диалоговом окне **Свойства группы доступности** выберите команду **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="43660-126">To add one or more databases by specifying them in the **Availability Group Properties** dialog box, select the **Properties** command.</span></span> <span data-ttu-id="43660-127">Шаги для добавления базы данных.</span><span class="sxs-lookup"><span data-stu-id="43660-127">The steps for adding a database are as follows:</span></span>  
  
        1.  <span data-ttu-id="43660-128">На панели **Базы данных доступности** нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="43660-128">In the **Availability Databases** pane, click the **Add** button.</span></span> <span data-ttu-id="43660-129">Будет создано и выбрано пустое поле базы данных.</span><span class="sxs-lookup"><span data-stu-id="43660-129">This creates and selects a blank database field.</span></span>  
  
        2.  <span data-ttu-id="43660-130">Введите имя базы данных, удовлетворяющее требованиям баз данных доступности.</span><span class="sxs-lookup"><span data-stu-id="43660-130">Enter the name of a database that meets the availability-databases prerequisites.</span></span>  
  
         <span data-ttu-id="43660-131">Чтобы добавить другую базу данных, повторите предыдущие шаги.</span><span class="sxs-lookup"><span data-stu-id="43660-131">To add another database, repeat the preceding steps.</span></span> <span data-ttu-id="43660-132">После указания баз данных нажмите кнопку **ОК** для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="43660-132">When you are done specifying databases, click **OK** to complete the operation.</span></span>  
  
         <span data-ttu-id="43660-133">После добавления базы данных в группу доступности с помощью диалогового окна **Свойства группы доступности** необходимо настроить соответствующую базу данных-получатель на каждом из экземпляров сервера, на которых размещена вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="43660-133">After you use the **Availability Group Properties** dialog box to add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="43660-134">Дополнительные сведения см. в разделе [Запуск перемещения данных в базе данных-получателе AlwaysOn (SQL Server)](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="43660-134">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="43660-135">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43660-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="43660-136">**Добавление базы данных в группу доступности**</span><span class="sxs-lookup"><span data-stu-id="43660-136">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="43660-137">Подключитесь к экземпляру сервера, на котором размещен экземпляр сервера с первичной репликой доступности.</span><span class="sxs-lookup"><span data-stu-id="43660-137">Connect to the server instance that hosts the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="43660-138">Инструкция [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="43660-138">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="43660-139">ALTER AVAILABILITY GROUP *group_name* ADD DATABASE *database_name* [,...*n*]</span><span class="sxs-lookup"><span data-stu-id="43660-139">ALTER AVAILABILITY GROUP *group_name* ADD DATABASE *database_name* [,...*n*]</span></span>  
  
     <span data-ttu-id="43660-140">где *group_name* — это имя группы доступности, а *database_name* — это имя базы данных, добавляемой в группу.</span><span class="sxs-lookup"><span data-stu-id="43660-140">where *group_name* is the name of the availability group and *database_name* is the name of a database to be added to the group.</span></span>  
  
     <span data-ttu-id="43660-141">В следующем примере добавляется база данных *MyDb3* в группу доступности *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="43660-141">The following example adds the *MyDb3* database to the *MyAG* availability group.</span></span>  
  
    ```  
    -- Connect to the server instance that hosts the primary replica.  
    -- Add an existing database to the availability group.  
    ALTER AVAILABILITY GROUP MyAG ADD DATABASE MyDb3;  
    GO  
    ```  
  
3.  <span data-ttu-id="43660-142">После добавления базы данных в группу доступности необходимо настроить соответствующую базу данных-получатель на каждом из экземпляров сервера, на которых размещена вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="43660-142">After you add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="43660-143">Дополнительные сведения см. в разделе [Запуск перемещения данных в базе данных-получателе AlwaysOn (SQL Server)](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="43660-143">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="43660-144">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="43660-144">Using PowerShell</span></span>  
 <span data-ttu-id="43660-145">**Добавление базы данных в группу доступности**</span><span class="sxs-lookup"><span data-stu-id="43660-145">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="43660-146">Перейдите в каталог (`cd`) экземпляра сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="43660-146">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="43660-147">Используйте командлет `Add-SqlAvailabilityDatabase`.</span><span class="sxs-lookup"><span data-stu-id="43660-147">Use the `Add-SqlAvailabilityDatabase` cmdlet.</span></span>  
  
     <span data-ttu-id="43660-148">Например, следующая команда добавляет базу данных-получатель `MyDd` к группе доступности `MyAG` , первичная реплика которой размещена в расположении `PrimaryServer\InstanceName`.</span><span class="sxs-lookup"><span data-stu-id="43660-148">For example, the following command adds the secondary database `MyDd` to the `MyAG` availability group, whose primary replica is hosted by `PrimaryServer\InstanceName`.</span></span>  
  
    ```powershell
    Add-SqlAvailabilityDatabase `   
     -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAG `   
     -Database "MyDb"  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="43660-149">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43660-149">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="43660-150">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="43660-150">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
3.  <span data-ttu-id="43660-151">После добавления базы данных в группу доступности необходимо настроить соответствующую базу данных-получатель на каждом из экземпляров сервера, на которых размещена вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="43660-151">After you add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="43660-152">Дополнительные сведения см. в разделе [Запуск перемещения данных в базе данных-получателе AlwaysOn (SQL Server)](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="43660-152">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="43660-153">Сведения о настройке и использовании поставщика SQL Server PowerShell см. в разделе [поставщик SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="43660-153">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>

 <span data-ttu-id="43660-154">В следующем примере показан полный процесс подготовки базы данных-получателя из базы данных на экземпляре сервера, на котором размещается первичная реплика группы доступности, добавления базы данных в группу доступности (в качестве базы данных-источника) и присоединения базы данных-получателя к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="43660-154">The following example shows the full process for preparing a secondary database from a database on the server instance that hosts the primary replica of an availability group, adding the database to an availability group (as a primary database), and then joining the secondary database to the availability group.</span></span> <span data-ttu-id="43660-155">Во-первых, в примере выполняется резервное копирование базы данных и ее журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="43660-155">First, the example backs up the database and its transaction log.</span></span> <span data-ttu-id="43660-156">Затем выполняется восстановление из резервной копии базы данных и журнала в экземпляры сервера, в которых размещается вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="43660-156">Then the example restores the database and log backups to the server instances that host a secondary replica.</span></span>  
  
 <span data-ttu-id="43660-157">В этом примере `Add-SqlAvailabilityDatabase` вызывается дважды: сначала в первичной реплике для добавления базы данных в группу доступности, а затем во вторичной реплике для присоединения базы данных-получателя из этой реплики к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="43660-157">The example calls `Add-SqlAvailabilityDatabase` twice: first on the primary replica to add the database to the availability group, and then on the secondary replica to join the secondary database on that replica to the availability group.</span></span> <span data-ttu-id="43660-158">При наличии нескольких вторичных реплик нужно выполнить восстановление и присоединение базы данных-получателя в каждой из них.</span><span class="sxs-lookup"><span data-stu-id="43660-158">If you have more than one secondary replica, restore and join the secondary database on each of them.</span></span>  
  
```powershell
$DatabaseBackupFile = "\\share\backups\MyDatabase.bak"  
$LogBackupFile = "\\share\backups\MyDatabase.trn"  
$MyAgPrimaryPath = "SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg"  
$MyAgSecondaryPath = "SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAg"  
  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "PrimaryServer\InstanceName"  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "PrimaryServer\InstanceName" -BackupAction 'Log'  
  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "SecondaryServer\InstanceName" -NoRecovery  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "SecondaryServer\InstanceName" -RestoreAction 'Log' -NoRecovery  
  
Add-SqlAvailabilityDatabase -Path $MyAgPrimaryPath -Database "MyDatabase"  
Add-SqlAvailabilityDatabase -Path $MyAgSecondaryPath -Database "MyDatabase"
```  
  
## <a name="see-also"></a><span data-ttu-id="43660-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="43660-159">See Also</span></span>  
 <span data-ttu-id="43660-160">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="43660-160">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="43660-161">[Создание и настройка групп доступности (SQL Server)](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="43660-161">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="43660-162">[Использование панели мониторинга AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="43660-162">[Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="43660-163">Отслеживание групп доступности (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43660-163">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
