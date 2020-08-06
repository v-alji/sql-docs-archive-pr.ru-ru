---
title: Создание группы доступности (SQL Server PowerShell) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], creating
ms.assetid: bc69a7df-20fa-41e1-9301-11317c5270d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3af9bf896b954e6849c0d491f9ed267655369ccb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752356"
---
# <a name="create-an-availability-group-sql-server-powershell"></a><span data-ttu-id="80685-102">Создание группы доступности (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="80685-102">Create an Availability Group (SQL Server PowerShell)</span></span>
  <span data-ttu-id="80685-103">В данном разделе описывается использование командлетов PowerShell для создания и настройки группы доступности AlwaysOn в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80685-103">This topic describes how to use PowerShell cmdlets to create and configure an AlwaysOn availability group by using PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="80685-104">*Группа доступности* определяет набор пользовательских баз данных, которые будут действовать при сбое как единое целое, а также набор партнеров по обеспечению отработки отказа, называемых *репликами доступности*и поддерживающих отработку отказа.</span><span class="sxs-lookup"><span data-stu-id="80685-104">An *availability group* defines a set of user databases that will fail over as a single unit and a set of failover partners, known as *availability replicas*, which support failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80685-105">Базовые сведения о группах доступности см. в разделе [Обзор групп доступности AlwaysOn (SQL Server)](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="80685-105">For an introduction to availability groups, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="80685-106">Вместо командлетов PowerShell вы можете использовать мастер создания группы доступности или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80685-106">As an alternative to using PowerShell cmdlets, you can use the Create Availability Group wizard or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="80685-107">Дополнительные сведения см. в статьях [Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)](use-the-new-availability-group-dialog-box-sql-server-management-studio.md) и [Создание группы доступности (Transact-SQL)](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="80685-107">For more information, see [Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md) or [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="80685-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="80685-108">Before You Begin</span></span>  
 <span data-ttu-id="80685-109">Настоятельно рекомендуется прочитать этот раздел, прежде чем пытаться настроить свою первую группу доступности.</span><span class="sxs-lookup"><span data-stu-id="80685-109">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
###  <a name="prerequisites-restrictions-and-recommendations"></a><a name="PrerequisitesRestrictions"></a> <span data-ttu-id="80685-110">Предварительные условия, ограничения и рекомендации</span><span class="sxs-lookup"><span data-stu-id="80685-110">Prerequisites, Restrictions, and Recommendations</span></span>  
  
-   <span data-ttu-id="80685-111">Перед созданием группы доступности необходимо, чтобы экземпляры [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на которых находятся реплики доступности, были расположены на различных узлах одной отказоустойчивой кластеризации Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="80685-111">Before creating an availability group, verify that the host instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] each resides on a different Windows Server Failover Clustering (WSFC) node of a single WSFC failover cluster.</span></span> <span data-ttu-id="80685-112">Также необходимо обеспечить соответствие экземпляров сервера всем другим предварительным условиям для экземпляров сервера; кроме того, следует выполнить все требования [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] и ознакомиться с соответствующими рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="80685-112">Also, verify that your server instances met the other server-instance prerequisites and that all of the other [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] requirements are meet and that you are aware of the recommendations.</span></span> <span data-ttu-id="80685-113">Для получения дополнительных сведений настоятельно рекомендуется изучить раздел [Предварительные требования, ограничения и рекомендации для групп доступности AlwaysOn (SQL Server)](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="80685-113">For more information, we strongly recommend that you read [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="80685-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="80685-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="80685-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="80685-115">Permissions</span></span>  
 <span data-ttu-id="80685-116">Требуется членство в фиксированной роли сервера **sysadmin** и одно из разрешений: CREATE AVAILABILITY GROUP, ALTER ANY AVAILABILITY GROUP или CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="80685-116">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
###  <a name="summary-of-tasks-and-corresponding-powershell-cmdlets"></a><a name="SummaryPSStatements"></a><span data-ttu-id="80685-117">Сводка задач и соответствующих командлетов PowerShell</span><span class="sxs-lookup"><span data-stu-id="80685-117">Summary of Tasks and Corresponding PowerShell Cmdlets</span></span>  
 <span data-ttu-id="80685-118">В следующей таблице перечислены основные задачи, входящие в настройку группы доступности, и указывается, какие из них поддерживаются командлетами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80685-118">The following table lists the basic tasks involved in configuring an availability group and indicates those that are supported by PowerShell cmdlets.</span></span> <span data-ttu-id="80685-119">Задачи [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] должны выполняться в той последовательности, в которой они перечислены в таблице.</span><span class="sxs-lookup"><span data-stu-id="80685-119">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] tasks must be performed in the sequence in which they are presented in the table.</span></span>  
  
|<span data-ttu-id="80685-120">Задача</span><span class="sxs-lookup"><span data-stu-id="80685-120">Task</span></span>|<span data-ttu-id="80685-121">Командлеты PowerShell (если доступны) или инструкции Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="80685-121">PowerShell Cmdlets (if Available) or Transact-SQL Statement</span></span>|<span data-ttu-id="80685-122">Место выполнения задачи**<sup>\*</sup>**</span><span class="sxs-lookup"><span data-stu-id="80685-122">Where to Perform Task**<sup>\*</sup>**</span></span>|  
|----------|--------------------------------------------------------------------|-------------------------------------------|  
|<span data-ttu-id="80685-123">Создание конечной точки зеркального отображения базы данных (одна точка на экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="80685-123">Create database mirroring endpoint (once per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance)</span></span>|`New-SqlHadrEndPoint`|<span data-ttu-id="80685-124">Выполнить на каждом экземпляре сервера, у которого нет конечной точки зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="80685-124">Execute on each server instance that lacks database mirroring endpoint.</span></span><br /><br /> <span data-ttu-id="80685-125">Примечание. Для изменения существующей конечной точки зеркального отображения базы данных используйте `Set-SqlHadrEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="80685-125">Note: To alter an existing database mirroring endpoint, use `Set-SqlHadrEndpoint`.</span></span>|  
|<span data-ttu-id="80685-126">Создание группы доступности</span><span class="sxs-lookup"><span data-stu-id="80685-126">Create availability group</span></span>|<span data-ttu-id="80685-127">Во-первых, используйте командлет `New-SqlAvailabilityReplica` с параметром `-AsTemplate` для создания объекта реплики доступности в памяти для каждой из двух реплик доступности, которые планируется включить в группу доступности.</span><span class="sxs-lookup"><span data-stu-id="80685-127">First, use the `New-SqlAvailabilityReplica` cmdlet with the `-AsTemplate` parameter to create an in-memory availability-replica object for each of the two availability replicas that you plan to include in the availability group.</span></span><br /><br /> <span data-ttu-id="80685-128">Затем создайте группу доступности с помощью командлета `New-SqlAvailabilityGroup`, ссылаясь на объекты реплики доступности.</span><span class="sxs-lookup"><span data-stu-id="80685-128">Then, create the availability group by using the `New-SqlAvailabilityGroup` cmdlet and referencing your availability-replica objects.</span></span>|<span data-ttu-id="80685-129">Выполнить на экземпляре сервера, где будет размещена исходная первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="80685-129">Execute on the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="80685-130">Присоединить вторичную реплику к группе доступности</span><span class="sxs-lookup"><span data-stu-id="80685-130">Join secondary replica to availability group</span></span>|`Join-SqlAvailabilityGroup`|<span data-ttu-id="80685-131">Выполнить на каждом экземпляре сервера, размещающем вторичную реплику.</span><span class="sxs-lookup"><span data-stu-id="80685-131">Execute on each server instance that is hosts a secondary replica.</span></span>|  
|<span data-ttu-id="80685-132">Подготовьте базу данных-получатель</span><span class="sxs-lookup"><span data-stu-id="80685-132">Prepare the secondary database</span></span>|<span data-ttu-id="80685-133">`Backup-SqlDatabase` и `Restore-SqlDatabase`</span><span class="sxs-lookup"><span data-stu-id="80685-133">`Backup-SqlDatabase` and `Restore-SqlDatabase`</span></span>|<span data-ttu-id="80685-134">Создайте резервные копии на экземпляре сервера, размещающем первичную реплику.</span><span class="sxs-lookup"><span data-stu-id="80685-134">Create backups on the server instance that hosts the primary replica.</span></span><br /><br /> <span data-ttu-id="80685-135">Восстановите резервные копии на каждом из тех экземпляров сервера, на которых размещена вторичная реплика, при помощи параметра восстановления `NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="80685-135">Restore backups on each server instance that hosts a secondary replica, using the `NoRecovery` restore parameter.</span></span> <span data-ttu-id="80685-136">Если пути к файлам различны на компьютерах, на которых размещена основная реплика и целевая вторичная реплика, также следует использовать параметр восстановления `RelocateFile`.</span><span class="sxs-lookup"><span data-stu-id="80685-136">If the file paths differ between the computers that host the primary replica and the target secondary replica, also use the `RelocateFile` restore parameter.</span></span>|  
|<span data-ttu-id="80685-137">Запуск синхронизации данных с помощью присоединения каждой базы данных-получателя к группе доступности</span><span class="sxs-lookup"><span data-stu-id="80685-137">Start data synchronization by joining each secondary database to availability group</span></span>|`Add-SqlAvailabilityDatabase`|<span data-ttu-id="80685-138">Выполнить на каждом экземпляре сервера, размещающем вторичную реплику.</span><span class="sxs-lookup"><span data-stu-id="80685-138">Execute on each server instance that hosts a secondary replica.</span></span>|  
  
 <span data-ttu-id="80685-139">**<sup>\*</sup>** Чтобы выполнить указанную задачу, измените каталог ( `cd` ) на указанный экземпляр или экземпляры сервера.</span><span class="sxs-lookup"><span data-stu-id="80685-139">**<sup>\*</sup>**  To perform a given task, change directory (`cd`) to the indicated server instance or instances.</span></span>  
  
###  <a name="to-set-up-and-use-the-sql-server-powershell-provider"></a><a name="PsProviderLinks"></a><span data-ttu-id="80685-140">Настройка и использование поставщика SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="80685-140">To Set Up and Use the SQL Server PowerShell Provider</span></span>  
  
-   [<span data-ttu-id="80685-141">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="80685-141">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="80685-142">Получение справок по SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="80685-142">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="using-powershell-to-create-and-configure-an-availability-group"></a><a name="PowerShellProcedure"></a><span data-ttu-id="80685-143">Использование PowerShell для создания и настройки группы доступности</span><span class="sxs-lookup"><span data-stu-id="80685-143">Using PowerShell to Create and Configure an Availability Group</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80685-144">Чтобы просмотреть синтаксис и пример определенного командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80685-144">To view the syntax and an example of a given cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="80685-145">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="80685-145">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
1.  <span data-ttu-id="80685-146">Перейдите в каталог (`cd`) экземпляра сервера, на котором размещается первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="80685-146">Change directory (`cd`) to the server instance that is to host the primary replica.</span></span>  
  
2.  <span data-ttu-id="80685-147">Создайте объект реплики доступности в памяти для первичной реплики.</span><span class="sxs-lookup"><span data-stu-id="80685-147">Create an in-memory availability-replica object for the primary replica.</span></span>  
  
3.  <span data-ttu-id="80685-148">Создайте объект реплики доступности в памяти для каждой вторичной реплики.</span><span class="sxs-lookup"><span data-stu-id="80685-148">Create an in-memory availability-replica object for each of the secondary replicas.</span></span>  
  
4.  <span data-ttu-id="80685-149">Создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="80685-149">Create the availability group.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="80685-150">Максимальная длина имени группы доступности составляет 128 символов.</span><span class="sxs-lookup"><span data-stu-id="80685-150">The maximum length for an availability group name is 128 characters.</span></span>  
  
5.  <span data-ttu-id="80685-151">Присоедините новую вторичную реплику к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="80685-151">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="80685-152">Дополнительные сведения см. в разделе [Присоединение вторичной реплики к группе доступности (SQL Server)](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="80685-152">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
6.  <span data-ttu-id="80685-153">Для каждой базы данных в группе доступности создайте базу данных-получатель путем восстановления последней резервной копии базы данных-источника с помощью инструкции RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="80685-153">For each database in the availability group, create a secondary database by restoring recent backups of the primary database, using RESTORE WITH NORECOVERY.</span></span>  
  
7.  <span data-ttu-id="80685-154">Присоедините каждую новую базу данных-получатель к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="80685-154">Join every new secondary database to the availability group.</span></span> <span data-ttu-id="80685-155">Дополнительные сведения см. в разделе [Присоединение вторичной реплики к группе доступности (SQL Server)](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="80685-155">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
8.  <span data-ttu-id="80685-156">При необходимости с помощью команды Windows `dir` проверьте содержимое новой группы доступности.</span><span class="sxs-lookup"><span data-stu-id="80685-156">Optionally, use the Windows `dir` command to verify the contents of the new availability group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80685-157">Если учетные записи службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] экземпляров сервера запускаются в контексте других учетных записей пользователей домена, создайте имя входа для другого экземпляра сервера и предоставьте этому имени разрешение CONNECT для подключения к конечной точке зеркального отображения локальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="80685-157">If the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service accounts of the server instances run under different domain user accounts, on each server instance, create a login for the other server instance and grant this login CONNECT permission to the local database mirroring endpoint.</span></span>  
  
##  <a name="example-using-powershell-to-create-an-availability-group"></a><a name="ExampleConfigureGroup"></a><span data-ttu-id="80685-158">Пример. Использование PowerShell для создания группы доступности</span><span class="sxs-lookup"><span data-stu-id="80685-158">Example: Using PowerShell to Create an Availability Group</span></span>  
 <span data-ttu-id="80685-159">В следующем примере использования PowerShell создается и настраивается простая группа доступности с именем `MyAG` с двумя репликами доступности и с одной базой данных доступности.</span><span class="sxs-lookup"><span data-stu-id="80685-159">The following PowerShell example creates and configures a simple availability group named `MyAG` with two availability replicas and one availability database.</span></span> <span data-ttu-id="80685-160">Пример.</span><span class="sxs-lookup"><span data-stu-id="80685-160">The example:</span></span>  
  
1.  <span data-ttu-id="80685-161">Выполняется резервное копирование базы данных `MyDatabase` и ее журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="80685-161">Backs up `MyDatabase` and its transaction log.</span></span>  
  
2.  <span data-ttu-id="80685-162">Выполняется восстановление базы данных `MyDatabase` и ее журнала транзакций с использованием параметра `-NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="80685-162">Restores `MyDatabase` and its transaction log, using the `-NoRecovery` option.</span></span>  
  
3.  <span data-ttu-id="80685-163">Создается представление первичной реплики в памяти, которая будет размещена локальным экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (с именем `PrimaryComputer\Instance`).</span><span class="sxs-lookup"><span data-stu-id="80685-163">Creates an in-memory representation of the primary replica, which will be hosted by the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (named `PrimaryComputer\Instance`).</span></span>  
  
4.  <span data-ttu-id="80685-164">Создается представление вторичной реплики в памяти, которая будет размещена локальным экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (с именем `SecondaryComputer\Instance`).</span><span class="sxs-lookup"><span data-stu-id="80685-164">Creates an in-memory representation of the secondary replica, which will be hosted by an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (named `SecondaryComputer\Instance`).</span></span>  
  
5.  <span data-ttu-id="80685-165">Создается группа доступности с именем `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="80685-165">Creates an availability group named `MyAG`.</span></span>  
  
6.  <span data-ttu-id="80685-166">Вторичная реплика присоединяется к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="80685-166">Joins the secondary replica to the availability group.</span></span>  
  
7.  <span data-ttu-id="80685-167">База данных-получатель присоединяется к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="80685-167">Joins the secondary database to the availability group.</span></span>  
  
```powershell
# Backup my database and its log on the primary  
Backup-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.bak" `  
    -ServerInstance "PrimaryComputer\Instance"  
  
Backup-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.log" `  
    -ServerInstance "PrimaryComputer\Instance" `  
    -BackupAction Log   
  
# Restore the database and log on the secondary (using NO RECOVERY)  
Restore-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.bak" `  
    -ServerInstance "SecondaryComputer\Instance" `  
    -NoRecovery  
  
Restore-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.log" `  
    -ServerInstance "SecondaryComputer\Instance" `  
    -RestoreAction Log `  
    -NoRecovery  
  
# Create an in-memory representation of the primary replica.  
$primaryReplica = New-SqlAvailabilityReplica `  
    -Name "PrimaryComputer\Instance" `  
    -EndpointURL "TCP://PrimaryComputer.domain.com:5022" `  
    -AvailabilityMode "SynchronousCommit" `  
    -FailoverMode "Automatic" `  
    -Version 12 `  
    -AsTemplate  
  
# Create an in-memory representation of the secondary replica.  
$secondaryReplica = New-SqlAvailabilityReplica `  
    -Name "SecondaryComputer\Instance" `  
    -EndpointURL "TCP://SecondaryComputer.domain.com:5022" `  
    -AvailabilityMode "SynchronousCommit" `  
    -FailoverMode "Automatic" `  
    -Version 12 `  
    -AsTemplate  
  
# Create the availability group  
New-SqlAvailabilityGroup `  
    -Name "MyAG" `  
    -Path "SQLSERVER:\SQL\PrimaryComputer\Instance" `  
    -AvailabilityReplica @($primaryReplica,$secondaryReplica) `  
    -Database "MyDatabase"  
  
# Join the secondary replica to the availability group.  
Join-SqlAvailabilityGroup -Path "SQLSERVER:\SQL\SecondaryComputer\Instance" -Name "MyAG"  
  
# Join the secondary database to the availability group.  
Add-SqlAvailabilityDatabase -Path "SQLSERVER:\SQL\SecondaryComputer\Instance\AvailabilityGroups\MyAG" -Database "MyDatabase"  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="80685-168">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="80685-168">Related Tasks</span></span>  
 <span data-ttu-id="80685-169">**Настройка экземпляра сервера для групп доступности AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="80685-169">**To configure a server instance for AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="80685-170">Включение и отключение групп доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-170">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="80685-171">Создание конечной точки зеркального отображения базы данных для группы доступности AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="80685-171">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
 <span data-ttu-id="80685-172">**Настройка свойств группы доступности и реплики**</span><span class="sxs-lookup"><span data-stu-id="80685-172">**To configure availability group and replica properties**</span></span>  
  
-   [<span data-ttu-id="80685-173">Смена режима доступности для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-173">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="80685-174">Смена режима отработки отказа для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-174">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="80685-175">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-175">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="80685-176">Настройка гибкой политики отработки отказа для обеспечения контроля над автоматическим переходом на другой ресурс (группы доступности AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="80685-176">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="80685-177">Укажите URL-адрес конечной точки при добавлении или изменении реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-177">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="80685-178">Настройка резервного копирования в репликах доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-178">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="80685-179">Настройка доступа только для чтения в реплике доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-179">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="80685-180">Настройка маршрутизации только для чтения в группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-180">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="80685-181">Изменение периода ожидания сеанса для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-181">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="80685-182">**Завершение настройки группы доступности**</span><span class="sxs-lookup"><span data-stu-id="80685-182">**To complete availability group configuration**</span></span>  
  
-   [<span data-ttu-id="80685-183">Присоединение вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-183">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="80685-184">Подготовка базы данных-получателя для присоединения к группе доступности вручную (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-184">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="80685-185">Присоединение базы данных-получателя к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-185">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="80685-186">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-186">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
 <span data-ttu-id="80685-187">**Другие способы создания группы доступности**</span><span class="sxs-lookup"><span data-stu-id="80685-187">**Alternative ways to create an availability group**</span></span>  
  
-   [<span data-ttu-id="80685-188">Использование мастера групп доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="80685-188">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="80685-189">Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="80685-189">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="80685-190">Создание группы доступности (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="80685-190">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
 <span data-ttu-id="80685-191">**Устранение неполадок с конфигурацией групп доступности AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="80685-191">**To troubleshoot AlwaysOn Availability Groups configuration**</span></span>  
  
-   [<span data-ttu-id="80685-192">Устранение неполадок при группы доступности AlwaysOn конфигурации (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-192">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="80685-193">Устранение неполадок при &#40;операции добавления файла группы доступности AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="80685-193">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="80685-194">См. также</span><span class="sxs-lookup"><span data-stu-id="80685-194">Related Content</span></span>  
  
-   <span data-ttu-id="80685-195">**Блоги**</span><span class="sxs-lookup"><span data-stu-id="80685-195">**Blogs:**</span></span>  
  
     [<span data-ttu-id="80685-196">Обучающая серия AlwaysON — HADRON. использование пулов рабочих потоков для баз данных с HADRON</span><span class="sxs-lookup"><span data-stu-id="80685-196">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="80685-197">Настройка AlwaysOn с помощью SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="80685-197">Configuring AlwaysOn with SQL Server PowerShell</span></span>](https://blogs.msdn.com/b/sqlalwayson/archive/2012/02/03/configuring-alwayson-with-sql-server-powershell.aspx)  
  
     [<span data-ttu-id="80685-198">Блоги команды разработчиков SQL Server AlwaysOn: официальный блог по SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="80685-198">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="80685-199">Блоги инженеров CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="80685-199">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="80685-200">**Видеоролики**</span><span class="sxs-lookup"><span data-stu-id="80685-200">**Videos:**</span></span>  
  
     [<span data-ttu-id="80685-201">Microsoft SQL Server с рабочим названием Denali AlwaysOn, часть 1: вводные сведения о решении следующего поколения по обеспечению высокого уровня доступности</span><span class="sxs-lookup"><span data-stu-id="80685-201">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="80685-202">Microsoft SQL Server с рабочим названием Denali AlwaysOn, часть 2: создание критически важного решения по обеспечению высокого уровня доступности с использованием AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="80685-202">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="80685-203">**Технические документы**</span><span class="sxs-lookup"><span data-stu-id="80685-203">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="80685-204">Руководство по решениям режима AlwaysOn в Microsoft SQL Server для обеспечения высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="80685-204">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="80685-205">Технические документы Майкрософт Microsoft по SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="80685-205">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="80685-206">Технические документы группы консультантов по SQL Server</span><span class="sxs-lookup"><span data-stu-id="80685-206">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="80685-207">См. также:</span><span class="sxs-lookup"><span data-stu-id="80685-207">See Also</span></span>  
 [<span data-ttu-id="80685-208">Конечная точка зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80685-208">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md)   
