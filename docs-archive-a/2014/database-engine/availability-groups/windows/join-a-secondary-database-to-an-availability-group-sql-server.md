---
title: Присоединение базы данных-получателя к группе доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.joindbs.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- secondary databases [SQL Server]
- Availability Groups [SQL Server], joining
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: fd7efe79-c1f9-497d-bfe7-b2a2b2321cf5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b0d79325bcde33d13688003de079a42a9601cc41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658982"
---
# <a name="join-a-secondary-database-to-an-availability-group-sql-server"></a><span data-ttu-id="f0f13-102">Присоединение базы данных-получателя к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f0f13-102">Join a Secondary Database to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="f0f13-103">В этом разделе описывается присоединение базы данных-получателя к группе доступности AlwaysOn с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0f13-103">This topic explains how to join a secondary database to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="f0f13-104">После подготовки базы данных-получателя для вторичной реплики необходимо как можно скорее присоединить базу данных к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="f0f13-104">After you prepare a secondary database for a secondary replica, you need to join the database to the availability group as soon as possible.</span></span> <span data-ttu-id="f0f13-105">При этом начнется перемещение данных из соответствующей основной базы данных в базу данных-получатель.</span><span class="sxs-lookup"><span data-stu-id="f0f13-105">This will start data movement from the corresponding primary database to the secondary database.</span></span>  
  
-   <span data-ttu-id="f0f13-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f0f13-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f0f13-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f0f13-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="f0f13-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f0f13-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f0f13-109">**Подготовка базы данных-получателя с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="f0f13-109">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="f0f13-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0f13-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f0f13-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0f13-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="f0f13-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0f13-112">PowerShell</span></span>](#PowerShellProcedure)  
  
> [!NOTE]  
>  <span data-ttu-id="f0f13-113">Сведения о том, что происходит после того, как база данных-получатель присоединяется к группе, см. в разделе [обзор группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f0f13-113">For information about what happens after a secondary database joins the group, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f0f13-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f0f13-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f0f13-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f0f13-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="f0f13-116">Необходимо подключиться к экземпляру сервера, на котором находится дополнительная реплика.</span><span class="sxs-lookup"><span data-stu-id="f0f13-116">You must be connected to the server instance that hosts the secondary replica.</span></span>  
  
-   <span data-ttu-id="f0f13-117">Дополнительная реплика уже должна быть присоединена к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="f0f13-117">The secondary replica must already be joined to the availability group.</span></span> <span data-ttu-id="f0f13-118">Дополнительные сведения см. в разделе [Присоединение вторичной реплики к группе доступности (SQL Server)](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f0f13-118">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
-   <span data-ttu-id="f0f13-119">База данных-получатель должна быть подготовлена заранее.</span><span class="sxs-lookup"><span data-stu-id="f0f13-119">The secondary database must have been prepared recently.</span></span> <span data-ttu-id="f0f13-120">Дополнительные сведения см. в статье [Ручная подготовка базы данных-получателя для присоединения к группе доступности (SQL Server)](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f0f13-120">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f0f13-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="f0f13-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f0f13-122">Permissions</span><span class="sxs-lookup"><span data-stu-id="f0f13-122">Permissions</span></span>  
 <span data-ttu-id="f0f13-123">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="f0f13-123">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f0f13-124">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0f13-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="f0f13-125">**Присоединение базы данных-получателя к группе доступности**</span><span class="sxs-lookup"><span data-stu-id="f0f13-125">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="f0f13-126">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена вторичная реплика, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="f0f13-126">In Object Explorer, connect to the server instance that hosts the secondary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="f0f13-127">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="f0f13-127">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="f0f13-128">Разверните группу доступности, которую необходимо изменить, и разверните узел **Базы данных доступности** .</span><span class="sxs-lookup"><span data-stu-id="f0f13-128">Expand the availability group that you want to change, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="f0f13-129">Щелкните правой кнопкой мыши эту базу данных и выберите **Присоединить к группе доступности**.</span><span class="sxs-lookup"><span data-stu-id="f0f13-129">Right-click the database, and click **Join to Availability Group**.</span></span>  
  
5.  <span data-ttu-id="f0f13-130">Откроется диалоговое окно **Присоединение базы данных к группе доступности** .</span><span class="sxs-lookup"><span data-stu-id="f0f13-130">This opens the **Join Databases to Availability Group** dialog box.</span></span> <span data-ttu-id="f0f13-131">Проверьте имя группы доступности, которое отображается в панели заголовка. При этом имя или имена баз данных должны отображаться в сетке. Нажмите кнопку **ОК**или **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="f0f13-131">Verify the availability group name, which is displayed on the title bar, and database name or names displayed in the grid, and click **OK**, or click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f0f13-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0f13-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="f0f13-133">**Присоединение базы данных-получателя к группе доступности**</span><span class="sxs-lookup"><span data-stu-id="f0f13-133">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="f0f13-134">Подключитесь к экземпляру сервера, на котором находится дополнительная реплика.</span><span class="sxs-lookup"><span data-stu-id="f0f13-134">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="f0f13-135">Используйте предложение [SET HADR в инструкции ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f0f13-135">Use the [SET HADR clause of the ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) statement, as follows:</span></span>  
  
     <span data-ttu-id="f0f13-136">ALTER DATABASE *имя_базы_данных* SET HADR AVAILABILITY GROUP = *имя_группы*</span><span class="sxs-lookup"><span data-stu-id="f0f13-136">ALTER DATABASE *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span></span>  
  
     <span data-ttu-id="f0f13-137">где *имя_базы_данных* — это имя присоединяемой базы данных, а *имя_группы* — это имя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="f0f13-137">where *database_name* is the name of a database to be joined and *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="f0f13-138">В следующем примере база данных-получатель `Db1` включается в локальную вторичную реплику группы доступности `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="f0f13-138">The following example joins the secondary database, `Db1`, to the local secondary replica of the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER DATABASE Db1 SET HADR AVAILABILITY GROUP = MyAG;  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="f0f13-139">Пример использования инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)] в контексте см. в статье [Создание группы доступности (Transact-SQL)](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f0f13-139">To see this [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement used in context, see [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="f0f13-140">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0f13-140">Using PowerShell</span></span>  
 <span data-ttu-id="f0f13-141">**Присоединение базы данных-получателя к группе доступности**</span><span class="sxs-lookup"><span data-stu-id="f0f13-141">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="f0f13-142">Перейдите в каталог (`cd`) экземпляра сервера, на котором размещается вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="f0f13-142">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="f0f13-143">С помощью командлета `Add-SqlAvailabilityDatabase` присоедините одну или несколько баз данных-получателей к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="f0f13-143">Use the `Add-SqlAvailabilityDatabase` cmdlet to join one or more secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="f0f13-144">Например, следующая команда присоединяет базу данных-получатель `Db1`к группе доступности `MyAG` в одном из экземпляров сервера, на котором находится вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="f0f13-144">For example, the following command joins a secondary database, `Db1`, to the availability group `MyAG` on one of the server instances that hosts a secondary replica.</span></span>  
  
    ```powershell
    Add-SqlAvailabilityDatabase -Path SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAG -Database "Db1"  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="f0f13-145">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0f13-145">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="f0f13-146">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f0f13-146">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="f0f13-147">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f0f13-147">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="f0f13-148">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0f13-148">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f0f13-149">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f0f13-149">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f0f13-150">Присоединение вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f0f13-150">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f0f13-151">Подготовка базы данных-получателя для присоединения к группе доступности вручную (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f0f13-151">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="f0f13-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="f0f13-152">See Also</span></span>  
 <span data-ttu-id="f0f13-153">[ALTER AVAILABILITY GROUP (Transact-SQL)](/sql/t-sql/statements/alter-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0f13-153">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span></span>  
 <span data-ttu-id="f0f13-154">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f0f13-154">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="f0f13-155">Устранение неполадок &#40;конфигурации группы доступности AlwaysOn SQL Server&#41;Deleted</span><span class="sxs-lookup"><span data-stu-id="f0f13-155">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
