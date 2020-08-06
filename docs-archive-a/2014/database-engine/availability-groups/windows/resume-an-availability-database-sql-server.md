---
title: Возобновление базы данных доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.resumedatamove.f1
helpviewer_keywords:
- Availability Groups [SQL Server], resuming a database
- secondary databases [SQL Server], in availability group
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], databases
ms.assetid: 20e9147b-e985-4caa-910e-fc4b38dbf9a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a2279940c2502a310e9dac4448bd6029b6e13dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740481"
---
# <a name="resume-an-availability-database-sql-server"></a><span data-ttu-id="a0383-102">Возобновление базы данных доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a0383-102">Resume an Availability Database (SQL Server)</span></span>
  <span data-ttu-id="a0383-103">В [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] можно возобновить выполнение приостановленной базы данных доступности с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], или PowerShell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0383-103">You can resume a suspended availability database in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a0383-104">Возобновление приостановленной базы данных переводит базу данных в состояние SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="a0383-104">Resuming a suspended database puts the database into the SYNCHRONIZING state.</span></span> <span data-ttu-id="a0383-105">Возобновление базы данных-источника возобновляет также все ее базы данных-получатели, которые были приостановлены в результате приостановки базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="a0383-105">Resuming the primary database also resumes any of its secondary databases that were suspended as the result of suspending the primary database.</span></span> <span data-ttu-id="a0383-106">Если какая-либо база данных-получатель была приостановлена локально на экземпляре сервера, на котором размещена вторичная реплика, эта база данных-получатель должна быть возобновлена локально.</span><span class="sxs-lookup"><span data-stu-id="a0383-106">If any secondary database was suspended locally, from the server instance that hosts the secondary replica, that secondary database must be resumed locally.</span></span> <span data-ttu-id="a0383-107">Как только определенная база данных-получатель и соответствующая база данных-источник вместе переходят в состояние SYNCHRONIZING, возобновляется синхронизация данных для базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="a0383-107">Once a given secondary database and the corresponding primary database are in the SYNCHRONIZING state, data synchronization resumes on the secondary database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0383-108">Приостановка и возобновление базы данных-получателя AlwaysOn непосредственно не влияет на доступность базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="a0383-108">Suspending and resuming an AlwaysOn secondary database does not directly affect the availability of the primary database.</span></span> <span data-ttu-id="a0383-109">Но приостановка базы данных-получателя может повлиять на избыточность и возможности отработки отказа для базы данных-источника, эти возможности снижены до тех пор, пока не будет возобновлена база данных-получатель.</span><span class="sxs-lookup"><span data-stu-id="a0383-109">However, suspending a secondary database can impact redundancy and failover capabilities for the primary database, until the suspended secondary database is resumed.</span></span> <span data-ttu-id="a0383-110">Этим она отличается от зеркального отображения базы данных, где состояние зеркального отображения приостанавливается как в зеркальной базе данных, так и в основной базе данных, до тех пор пока не возобновится зеркальное отображение.</span><span class="sxs-lookup"><span data-stu-id="a0383-110">This is in contrast to database mirroring, where the mirroring state is suspended on both the mirror database and the principal database until mirroring is resumed.</span></span> <span data-ttu-id="a0383-111">Приостановка базы данных-источника AlwaysOn приостанавливает перемещение данных для всех соответствующих баз данных-получателей, функции избыточности и отработки отказа для этой базы данных не работают до тех пор, пока работа базы данных-источника не будет возобновлена.</span><span class="sxs-lookup"><span data-stu-id="a0383-111">Suspending an AlwaysOn primary database suspends data movement on all the corresponding secondary databases, and redundancy and failover capabilities cease for that database until the primary database is resumed.</span></span>  
  
-   <span data-ttu-id="a0383-112">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a0383-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a0383-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a0383-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a0383-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a0383-114">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="a0383-115">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a0383-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a0383-116">**Возобновление базы данных-получателя с помощью:**</span><span class="sxs-lookup"><span data-stu-id="a0383-116">**To resume a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="a0383-117">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0383-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a0383-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0383-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a0383-119">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0383-119">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="a0383-120">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="a0383-120">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a0383-121">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a0383-121">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a0383-122">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a0383-122">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a0383-123">Команда RESUME возвращается сразу после принятия репликой, в которой размещена целевая база данных, но фактическое возобновление базы данных происходит асинхронно.</span><span class="sxs-lookup"><span data-stu-id="a0383-123">A RESUME command returns as soon as it has been accepted by the replica that hosts the target database, but actually resuming the database occurs asynchronously.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a0383-124">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a0383-124">Prerequisites</span></span>  
  
-   <span data-ttu-id="a0383-125">Необходимо подключиться к экземпляру сервера, на котором расположена возобновляемая база данных.</span><span class="sxs-lookup"><span data-stu-id="a0383-125">You must be connected to the server instance that hosts the database to be resumed.</span></span>  
  
-   <span data-ttu-id="a0383-126">Группа доступности должна быть в сети.</span><span class="sxs-lookup"><span data-stu-id="a0383-126">The availability group must be online.</span></span>  
  
-   <span data-ttu-id="a0383-127">База данных-источник должна быть в сети и доступна.</span><span class="sxs-lookup"><span data-stu-id="a0383-127">The primary database must be online and available.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a0383-128">безопасность</span><span class="sxs-lookup"><span data-stu-id="a0383-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a0383-129">Permissions</span><span class="sxs-lookup"><span data-stu-id="a0383-129">Permissions</span></span>  
 <span data-ttu-id="a0383-130">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="a0383-130">Requires ALTER permission on the database.</span></span>  
  
 <span data-ttu-id="a0383-131">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="a0383-131">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a0383-132">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0383-132">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a0383-133">**Возобновление базы данных-получателя**</span><span class="sxs-lookup"><span data-stu-id="a0383-133">**To resume a secondary database**</span></span>  
  
1.  <span data-ttu-id="a0383-134">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена реплика доступности, для которой нужно возобновить базу данных, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="a0383-134">In Object Explorer, connect to the server instance that hosts the availability replica on which you want to resume a database, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="a0383-135">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="a0383-135">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="a0383-136">Разверните группу доступности.</span><span class="sxs-lookup"><span data-stu-id="a0383-136">Expand the availability group.</span></span>  
  
4.  <span data-ttu-id="a0383-137">Разверните узел **Базы данных доступности** , щелкните правой кнопкой мыши базу данных и нажмите кнопку **Возобновить перемещение данных**.</span><span class="sxs-lookup"><span data-stu-id="a0383-137">Expand the **Availability Databases** node, right-click the database, and click **Resume Data Movement**.</span></span>  
  
5.  <span data-ttu-id="a0383-138">В диалоговом окне **Возобновление перемещения данных** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a0383-138">In the **Resume Data Movement** dialog box, click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0383-139">Чтобы возобновить дополнительные базы данных данной реплики, повторите шаги 4 и 5 для каждой базы данных.</span><span class="sxs-lookup"><span data-stu-id="a0383-139">To resume additional databases on this replica location, repeat steps 4 and 5 for each database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a0383-140">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0383-140">Using Transact-SQL</span></span>  
 <span data-ttu-id="a0383-141">**Возобновление базы данных-получателя, приостановленной локально**</span><span class="sxs-lookup"><span data-stu-id="a0383-141">**To resume a secondary database that was suspended locally**</span></span>  
  
1.  <span data-ttu-id="a0383-142">Подключитесь к экземпляру сервера, на котором размещена вторичная реплика, базу данных которой нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="a0383-142">Connect to the server instance that hosts the secondary replica whose database you want to resume.</span></span>  
  
2.  <span data-ttu-id="a0383-143">Возобновите базу данных-получатель с помощью следующей инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr):</span><span class="sxs-lookup"><span data-stu-id="a0383-143">Resume the secondary database by using the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)statement:</span></span>  
  
     <span data-ttu-id="a0383-144">ALTER DATABASE *database_name* задать HADR Resume</span><span class="sxs-lookup"><span data-stu-id="a0383-144">ALTER DATABASE *database_name* SET HADR RESUME</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a0383-145">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0383-145">Using PowerShell</span></span>  

### <a name="to-resume-a-secondary-database"></a><span data-ttu-id="a0383-146">Возобновление базы данных-получателя</span><span class="sxs-lookup"><span data-stu-id="a0383-146">To resume a secondary database</span></span>
  
1.  <span data-ttu-id="a0383-147">Измените папку (`cd`) на экземпляр сервера, на котором размещена реплика, базу данных которой нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="a0383-147">Change directory (`cd`) to the server instance that hosts the replica whose database you want to resume.</span></span> <span data-ttu-id="a0383-148">Дополнительные сведения см. в подразделе [Предварительные условия](#Prerequisites)ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="a0383-148">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="a0383-149">Для возобновления группы доступности воспользуйтесь командлетом **Resume-SqlAvailabilityDatabase** .</span><span class="sxs-lookup"><span data-stu-id="a0383-149">Use the **Resume-SqlAvailabilityDatabase** cmdlet to resume the availability group.</span></span>  
  
     <span data-ttu-id="a0383-150">Например, следующая команда возобновляет синхронизацию данных для базы данных доступности `MyDb3` в группе доступности `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="a0383-150">For example, the following command resumes data synchronization for the availability database `MyDb3` in the availability group `MyAg`.</span></span>  
  
    ```powershell
    Resume-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\Databases\MyDb3  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0383-151">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0383-151">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="a0383-152">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a0383-152">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="a0383-153">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a0383-153">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="a0383-154">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0383-154">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a0383-155">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="a0383-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a0383-156">Приостановка базы данных доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a0383-156">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0383-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0383-157">See Also</span></span>  
 [<span data-ttu-id="a0383-158">Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a0383-158">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
