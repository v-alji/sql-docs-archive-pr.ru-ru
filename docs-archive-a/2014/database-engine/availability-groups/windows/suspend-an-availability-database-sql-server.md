---
title: Приостановка базы данных доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.suspenddatamove.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], suspending a database
- Availability Groups [SQL Server], databases
ms.assetid: 86858982-6af1-4e80-9a93-87451f0d7ee9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 49afe868a509f84160fc1ad154135e8e67f6900a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750187"
---
# <a name="suspend-an-availability-database-sql-server"></a><span data-ttu-id="335d3-102">Приостановка базы данных доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="335d3-102">Suspend an Availability Database (SQL Server)</span></span>
  <span data-ttu-id="335d3-103">В [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] можно приостановить базу данных доступности с помощью [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="335d3-103">You can suspend an availability database in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="335d3-104">Обратите внимание, что команда приостановки должна выполняться на экземпляре сервера, содержащем базу данных, которая приостанавливается или возобновляется.</span><span class="sxs-lookup"><span data-stu-id="335d3-104">Note that a suspend command needs to be issued on the server instance that hosts the database to be suspended or resumed.</span></span>  
  
 <span data-ttu-id="335d3-105">Результат выполнения команды приостановки зависит от того, над какой базой данных выполняется команда: над базой данных-получателем или источником.</span><span class="sxs-lookup"><span data-stu-id="335d3-105">The effect of a suspend command depends on whether you suspend a secondary database or a primary database, as follows:</span></span>  
  
|<span data-ttu-id="335d3-106">Приостановленная базы данных</span><span class="sxs-lookup"><span data-stu-id="335d3-106">Suspended Database</span></span>|<span data-ttu-id="335d3-107">Результат выполнения команды приостановки</span><span class="sxs-lookup"><span data-stu-id="335d3-107">Effect of Suspend Command</span></span>|  
|------------------------|-------------------------------|  
|<span data-ttu-id="335d3-108">База данных-получатель</span><span class="sxs-lookup"><span data-stu-id="335d3-108">Secondary database</span></span>|<span data-ttu-id="335d3-109">Приостанавливается только локальная база данных-получатель, ее состояние синхронизации будет иметь значение NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="335d3-109">Only the local secondary database is suspended and its synchronization state becomes NOT SYNCHRONIZING.</span></span> <span data-ttu-id="335d3-110">Другие базы данных-получатели не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="335d3-110">Other secondary databases are not affected.</span></span> <span data-ttu-id="335d3-111">Приостановленная базы данных перестает получать и записывать данные (записи журнала), ее состояние не совпадает с базой данных-источником.</span><span class="sxs-lookup"><span data-stu-id="335d3-111">The suspended database stops receiving and applying data (log records) and begins to fall behind the primary database.</span></span> <span data-ttu-id="335d3-112">Существующие соединения в предназначенной для чтения вторичной реплике остаются применимыми.</span><span class="sxs-lookup"><span data-stu-id="335d3-112">Existing connections on the readable secondary remain usable.</span></span> <span data-ttu-id="335d3-113">Новые соединения с приостановленной базой данных в предназначенной только для чтения вторичной реплике не допускаются, пока движение данных не будет возобновлено.</span><span class="sxs-lookup"><span data-stu-id="335d3-113">New connections to the suspended database on the readable secondary are not allowed until data movement is resumed.</span></span><br /><br /> <span data-ttu-id="335d3-114">База данных-источник остается доступной.</span><span class="sxs-lookup"><span data-stu-id="335d3-114">The primary database remains available.</span></span> <span data-ttu-id="335d3-115">Если приостановить каждую из баз данных-получателей, база данных-источник будет работать в режиме без резервирования.</span><span class="sxs-lookup"><span data-stu-id="335d3-115">If you suspend each of the corresponding secondary databases, the primary database runs exposed.</span></span><br /><br /> <span data-ttu-id="335d3-116">**\*\* Важно. \*\*** Пока база данных-получатель остается приостановленной, в очереди отправки соответствующей основной базы данных накапливаются неотправленные записи журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="335d3-116">**\*\* Important \*\*** While a secondary database is suspended, the send queue of the corresponding primary database will accumulate unsent transaction log records.</span></span> <span data-ttu-id="335d3-117">Соединения с вторичной репликой возвращают данные, которые были доступными ко времени приостановки движения данных.</span><span class="sxs-lookup"><span data-stu-id="335d3-117">Connections to the secondary replica return data that was available at the time the data movement was suspended.</span></span>|  
|<span data-ttu-id="335d3-118">База данных-источник</span><span class="sxs-lookup"><span data-stu-id="335d3-118">Primary database</span></span>|<span data-ttu-id="335d3-119">База данных-источник останавливает перемещение данных в каждую подключенную базу данных-получатель.</span><span class="sxs-lookup"><span data-stu-id="335d3-119">The primary database stops data movement to every connected secondary database.</span></span> <span data-ttu-id="335d3-120">База данных-источник продолжает работу в режиме без резервирования.</span><span class="sxs-lookup"><span data-stu-id="335d3-120">The primary database continues running, in an exposed mode.</span></span> <span data-ttu-id="335d3-121">База данных-источник остается доступной для клиентов, действуют существующие соединения к предназначенной для чтения базе данных-получателю и можно устанавливать новые соединения.</span><span class="sxs-lookup"><span data-stu-id="335d3-121">The primary database remains available to clients, and existing connections on a readable secondary remain usable and new connections can be made.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="335d3-122">Приостановка вторичной базы данных AlwaysOn непосредственно не влияет на доступность базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="335d3-122">Suspending an AlwaysOn secondary database does not directly affect the availability of the primary database.</span></span> <span data-ttu-id="335d3-123">Но приостановка базы данных-получателя может повлиять на функции избыточности и отработки отказа базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="335d3-123">However, suspending a secondary database can impact redundancy and failover capabilities for the primary database.</span></span> <span data-ttu-id="335d3-124">В этом состоит отличие от зеркального отображения базы данных, где состояние зеркального отображения приостанавливается как в зеркальной базе данных, так и в основной базе данных.</span><span class="sxs-lookup"><span data-stu-id="335d3-124">This is in contrast to database mirroring, where the mirroring state is suspended on both the mirror database and the principal database.</span></span> <span data-ttu-id="335d3-125">Приостановка базы данных-источника AlwaysOn приостанавливает перемещение данных для всех соответствующих баз данных-получателей, функции избыточности и отработки отказа для этой базы данных не работают до тех пор, пока работа базы данных-источника не будет возобновлена.</span><span class="sxs-lookup"><span data-stu-id="335d3-125">Suspending an AlwaysOn primary database suspends data movement on all the corresponding secondary databases, and redundancy and failover capabilities cease for that database until the primary database is resumed.</span></span>  
  
-   <span data-ttu-id="335d3-126">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="335d3-126">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="335d3-127">Ограничения</span><span class="sxs-lookup"><span data-stu-id="335d3-127">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="335d3-128">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="335d3-128">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="335d3-129">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="335d3-129">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="335d3-130">Безопасность</span><span class="sxs-lookup"><span data-stu-id="335d3-130">Security</span></span>](#Security)  
  
-   <span data-ttu-id="335d3-131">**Для приостановки базы данных используется:**</span><span class="sxs-lookup"><span data-stu-id="335d3-131">**To suspend a database, using:**</span></span>  
  
-   [<span data-ttu-id="335d3-132">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="335d3-132">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="335d3-133">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="335d3-133">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="335d3-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="335d3-134">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="335d3-135">**Дальнейшие действия.** [Как избежать переполнения журнала транзакций](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="335d3-135">**Follow up:** [Avoiding a Full Transaction Log](#FollowUp)</span></span>  
  
-   [<span data-ttu-id="335d3-136">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="335d3-136">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="335d3-137">Перед началом</span><span class="sxs-lookup"><span data-stu-id="335d3-137">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="335d3-138">Ограничения</span><span class="sxs-lookup"><span data-stu-id="335d3-138">Limitations and Restrictions</span></span>  
 <span data-ttu-id="335d3-139">Команда SUSPEND возвращается сразу после принятия репликой, в которой размещена целевая база данных, но фактическая приостановка базы данных происходит асинхронно.</span><span class="sxs-lookup"><span data-stu-id="335d3-139">A SUSPEND command returns as soon as it has been accepted by the replica that hosts the target database, but actually suspending the database occurs asynchronously.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="335d3-140">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="335d3-140">Prerequisites</span></span>  
 <span data-ttu-id="335d3-141">Необходимо иметь соединение с экземпляром сервера, на котором размещена приостанавливаемая база данных.</span><span class="sxs-lookup"><span data-stu-id="335d3-141">You must be connected to the server instance that hosts the database that you want to suspend.</span></span> <span data-ttu-id="335d3-142">Чтобы приостановить базу данных-источник и соответствующие базы данных-получатели, подключитесь к экземпляру сервера, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="335d3-142">To suspend a primary database and the corresponding secondary databases, connect to the server instance that hosts the primary replica.</span></span> <span data-ttu-id="335d3-143">Чтобы приостановить базу данных-получатель, оставляя при этом доступной базу данных-источник, подключитесь к вторичной реплике.</span><span class="sxs-lookup"><span data-stu-id="335d3-143">To suspend a secondary database while leaving the primary database available, connect to the secondary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="335d3-144">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="335d3-144">Recommendations</span></span>  
 <span data-ttu-id="335d3-145">При возникновении узких мест краткая приостановка одной или нескольких баз данных-получателей может временно повысить производительность на первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="335d3-145">During bottlenecks, suspending one or more secondary databases briefly might be useful to improve performance temporarily on the primary replica.</span></span> <span data-ttu-id="335d3-146">Пока база данных-получатель находится в состоянии приостановки, журнал транзакций соответствующей базы данных-источника не может быть усечен.</span><span class="sxs-lookup"><span data-stu-id="335d3-146">As long as a secondary database remains suspended, the transaction log of the corresponding primary database cannot be truncated.</span></span> <span data-ttu-id="335d3-147">Это приводит к накоплению записей журнала в базе данных-источнике.</span><span class="sxs-lookup"><span data-stu-id="335d3-147">This causes log records to accumulate on the primary database.</span></span> <span data-ttu-id="335d3-148">Поэтому рекомендуется быстро возобновить или удалить приостановленную базу данных-получатель.</span><span class="sxs-lookup"><span data-stu-id="335d3-148">Therefore, we recommend that you resume, or remove, a suspended secondary database quickly.</span></span> <span data-ttu-id="335d3-149">Дополнительные сведения см. в разделе [Дальнейшие действия. Как избежать переполнения журнала транзакций](#FollowUp) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="335d3-149">For more information, see [Follow up: Avoiding a Full Transaction Log](#FollowUp), later in this topic.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="335d3-150">безопасность</span><span class="sxs-lookup"><span data-stu-id="335d3-150">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="335d3-151">Permissions</span><span class="sxs-lookup"><span data-stu-id="335d3-151">Permissions</span></span>  
 <span data-ttu-id="335d3-152">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="335d3-152">Requires ALTER permission on the database.</span></span>  
  
 <span data-ttu-id="335d3-153">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="335d3-153">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="335d3-154">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="335d3-154">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="335d3-155">**Приостановка базы данных**</span><span class="sxs-lookup"><span data-stu-id="335d3-155">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="335d3-156">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена реплика доступности, в которой нужно приостановить базу данных, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="335d3-156">In Object Explorer, connect to the server instance that hosts the availability replica on which you want to suspend a database, and expand the server tree.</span></span> <span data-ttu-id="335d3-157">Дополнительные сведения см. в подразделе [Предварительные условия](#Prerequisites)ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="335d3-157">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="335d3-158">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="335d3-158">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="335d3-159">Разверните группу доступности.</span><span class="sxs-lookup"><span data-stu-id="335d3-159">Expand the availability group.</span></span>  
  
4.  <span data-ttu-id="335d3-160">Разверните узел **Базы данных доступности** , щелкните правой кнопкой мыши базу данных и выберите пункт **Приостановить перемещение данных**.</span><span class="sxs-lookup"><span data-stu-id="335d3-160">Expand the **Availability Databases** node, right-click the database, and click **Suspend Data Movement**.</span></span>  
  
5.  <span data-ttu-id="335d3-161">В диалоговом окне **Приостановка перемещения данных** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="335d3-161">In the **Suspend Data Movement** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="335d3-162">В обозревателе объектов отображается, что база данных приостановлена путем изменения значка базы данных на знак паузы.</span><span class="sxs-lookup"><span data-stu-id="335d3-162">Object Explorer indicates that the database is suspended by changing  the database icon to display a pause indicator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="335d3-163">Чтобы приостановить дополнительные базы данных в расположении данной реплики, повторите шаги 4 и 5 для каждой базы данных.</span><span class="sxs-lookup"><span data-stu-id="335d3-163">To suspend additional databases on this replica location, repeat steps 4 and 5  for each database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="335d3-164">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="335d3-164">Using Transact-SQL</span></span>  
 <span data-ttu-id="335d3-165">**Приостановка базы данных**</span><span class="sxs-lookup"><span data-stu-id="335d3-165">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="335d3-166">Подключитесь к экземпляру сервера, на котором размещена реплика, базу данных которой нужно приостановить.</span><span class="sxs-lookup"><span data-stu-id="335d3-166">Connect to the server instance that hosts the replica whose database you want to suspend.</span></span> <span data-ttu-id="335d3-167">Дополнительные сведения см. в подразделе [Предварительные условия](#Prerequisites)ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="335d3-167">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="335d3-168">Приостановите базу данных с помощью следующей инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr):</span><span class="sxs-lookup"><span data-stu-id="335d3-168">Suspend the database by using the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)statement:</span></span>  
  
     <span data-ttu-id="335d3-169">ALTER DATABASE *database_name* задать приостановку HADR</span><span class="sxs-lookup"><span data-stu-id="335d3-169">ALTER DATABASE *database_name* SET HADR SUSPEND</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="335d3-170">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="335d3-170">Using PowerShell</span></span>  
 <span data-ttu-id="335d3-171">**Приостановка базы данных**</span><span class="sxs-lookup"><span data-stu-id="335d3-171">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="335d3-172">Перейдите в каталог (`cd`) экземпляра сервера, на котором размещена реплика, базу данных которой нужно приостановить.</span><span class="sxs-lookup"><span data-stu-id="335d3-172">Change directory (`cd`) to the server instance that hosts the replica whose database you want to suspend.</span></span> <span data-ttu-id="335d3-173">Дополнительные сведения см. в подразделе [Предварительные условия](#Prerequisites)ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="335d3-173">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="335d3-174">Воспользуйтесь командлетом `Suspend-SqlAvailabilityDatabase`, чтобы приостановить группу доступности.</span><span class="sxs-lookup"><span data-stu-id="335d3-174">Use the `Suspend-SqlAvailabilityDatabase` cmdlet to suspend the availability group.</span></span>  
  
     <span data-ttu-id="335d3-175">Например, следующая команда приостанавливает синхронизацию данных для базы данных доступности `MyDb3` в группе доступности `MyAg` на экземпляре сервера под именем `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="335d3-175">For example, the following command suspends data synchronization for the availability database `MyDb3` in the availability group `MyAg` on the server instance named `Computer\Instance`.</span></span>  
  
    ```powershell
    Suspend-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\Databases\MyDb3  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="335d3-176">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="335d3-176">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="335d3-177">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="335d3-177">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="335d3-178">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="335d3-178">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="335d3-179">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="335d3-179">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-avoiding-a-full-transaction-log"></a><a name="FollowUp"></a> <span data-ttu-id="335d3-180">Дальнейшие действия. Как избежать переполнения журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="335d3-180">Follow Up: Avoiding a Full Transaction Log</span></span>  
 <span data-ttu-id="335d3-181">Обычно при обработке в базе данных автоматической контрольной точки журнал транзакций этой базы данных усекается до этой контрольной точки после следующего резервного копирования журнала.</span><span class="sxs-lookup"><span data-stu-id="335d3-181">Normally, when an automatic checkpoint is performed on a database, its transaction log is truncated to that checkpoint after the next log backup.</span></span> <span data-ttu-id="335d3-182">Однако, пока база данных-получатель приостановлена, все текущие записи журнала остаются активными в базе данных-источнике.</span><span class="sxs-lookup"><span data-stu-id="335d3-182">However, while a secondary database is suspended, all of the current log records remain active on the primary database.</span></span> <span data-ttu-id="335d3-183">Если журнал транзакций заполняется до конца (достигается максимальный размер, или на экземпляре сервера не хватает пространства), база данных не позволяет обновить данные.</span><span class="sxs-lookup"><span data-stu-id="335d3-183">If the transaction log fills up (either because it reaches its maximum size or the server instance runs out of space), the database cannot perform any more updates.</span></span>  
  
 <span data-ttu-id="335d3-184">Во избежание этой проблемы следует предпринять одно из приведенных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="335d3-184">To avoid this problem, you should do one of the following:</span></span>  
  
-   <span data-ttu-id="335d3-185">Увеличить количество места под журнал для базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="335d3-185">Add more log space for the primary database.</span></span>  
  
-   <span data-ttu-id="335d3-186">Возобновите базу данных-получатель до полного заполнения журнала.</span><span class="sxs-lookup"><span data-stu-id="335d3-186">Resume the secondary database before the log fills up.</span></span> <span data-ttu-id="335d3-187">Дополнительные сведения см. ниже в разделе [Возобновление базы данных доступности (SQL Server)](resume-an-availability-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="335d3-187">For more information, see [Resume an Availability Database &#40;SQL Server&#41;](resume-an-availability-database-sql-server.md).</span></span>  
  
-   <span data-ttu-id="335d3-188">Удалите базу данных-получатель.</span><span class="sxs-lookup"><span data-stu-id="335d3-188">Remove the secondary database.</span></span> <span data-ttu-id="335d3-189">Дополнительные сведения см. в разделе [Удаление базы данных-получателя из группы доступности (SQL Server)](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="335d3-189">For more information, see [Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="335d3-190">**Устранение неполадок при переполнении журнала транзакций**</span><span class="sxs-lookup"><span data-stu-id="335d3-190">**To troubleshoot a full transaction log**</span></span>  
  
-   [<span data-ttu-id="335d3-191">Устранение неполадок при переполнении журнала транзакций (ошибка SQL Server 9002)</span><span class="sxs-lookup"><span data-stu-id="335d3-191">Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;</span></span>](../../../relational-databases/logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="335d3-192">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="335d3-192">Related Tasks</span></span>  
  
-   [<span data-ttu-id="335d3-193">Возобновление базы данных доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="335d3-193">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="335d3-194">См. также:</span><span class="sxs-lookup"><span data-stu-id="335d3-194">See Also</span></span>  
 <span data-ttu-id="335d3-195">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="335d3-195">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="335d3-196">Возобновление базы данных доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="335d3-196">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
