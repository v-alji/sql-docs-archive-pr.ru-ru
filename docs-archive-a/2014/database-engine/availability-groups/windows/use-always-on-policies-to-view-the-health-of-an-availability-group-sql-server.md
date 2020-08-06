---
title: Использование политик AlwaysOn для просмотра работоспособности группы доступности (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6f1bcbc3-1220-4071-8e53-4b957f5d3089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c4444afc2348b2407dc19c1c12761ef0251631e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750160"
---
# <a name="use-alwayson-policies-to-view-the-health-of-an-availability-group-sql-server"></a><span data-ttu-id="dddc6-102">Использование политик AlwaysOn для определения работоспособности группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dddc6-102">Use AlwaysOn Policies to View the Health of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="dddc6-103">В этом разделе описано, как определить состояние работоспособности группы доступности AlwaysOn с помощью политики AlwaysOn в среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или с помощью Powershell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dddc6-103">This topic describes how to determine the operational health of an AlwaysOn availability group by using an AlwaysOn policy in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="dddc6-104">Дополнительные сведения об управлении на основе политик AlwaysOn см. [в разделе политики AlwaysOn для проблем в работе с группы доступности AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="dddc6-104">For information about AlwaysOn Policy Based Management, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dddc6-105">При работе с политиками AlwaysOn имена категорий используются в качестве идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="dddc6-105">For AlwaysOn policies, the category names are used as IDs.</span></span> <span data-ttu-id="dddc6-106">При изменении имени категории AlwaysOn ее функция оценки работоспособности будет нарушена.</span><span class="sxs-lookup"><span data-stu-id="dddc6-106">Changing the name of an AlwaysOn category would break its health-evaluation functionality.</span></span> <span data-ttu-id="dddc6-107">Поэтому имена категорий AlwaysOn изменять не следует никогда.</span><span class="sxs-lookup"><span data-stu-id="dddc6-107">Therefore, the names of AlwaysOn category should never be modified.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dddc6-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="dddc6-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dddc6-109">безопасность</span><span class="sxs-lookup"><span data-stu-id="dddc6-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dddc6-110">Permissions</span><span class="sxs-lookup"><span data-stu-id="dddc6-110">Permissions</span></span>  
 <span data-ttu-id="dddc6-111">Требуются разрешения CONNECT, VIEW SERVER STATE и VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="dddc6-111">Requires CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions.</span></span>  
  
##  <a name="using-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a><span data-ttu-id="dddc6-112">Использование панели мониторинга AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="dddc6-112">Using the AlwaysOn Dashboard</span></span>  
 <span data-ttu-id="dddc6-113">**Открытие панели мониторинга AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="dddc6-113">**To open the AlwaysOn Dashboard**</span></span>  
  
1.  <span data-ttu-id="dddc6-114">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена одна из реплик доступности.</span><span class="sxs-lookup"><span data-stu-id="dddc6-114">In Object Explorer, connect to the server instance that hosts one of the availability replicas.</span></span> <span data-ttu-id="dddc6-115">Чтобы просмотреть сведения обо всех репликах доступности в группе доступности, используйте экземпляр сервера, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="dddc6-115">To view information about all of the availability replicas in an availability group, use to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="dddc6-116">Щелкните имя сервера, чтобы развернуть дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="dddc6-116">Click the server name to expand the server tree.</span></span>  
  
3.  <span data-ttu-id="dddc6-117">Разверните узел **Высокий уровень доступности AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="dddc6-117">Expand the **AlwaysOn High Availability** node.</span></span>  
  
     <span data-ttu-id="dddc6-118">Щелкните правой кнопкой мыши узел **Группы доступности** или разверните этот узел и щелкните правой кнопкой мыши определенную группу доступности.</span><span class="sxs-lookup"><span data-stu-id="dddc6-118">Either right-click the **Availability Groups** node or expand this node and right-click a specific availability group.</span></span>  
  
4.  <span data-ttu-id="dddc6-119">Выберите команду **Показать панель мониторинга** .</span><span class="sxs-lookup"><span data-stu-id="dddc6-119">Select the **Show Dashboard** command.</span></span>  
  
 <span data-ttu-id="dddc6-120">Дополнительные сведения об использовании панели мониторинга AlwaysOn см. в разделе [Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)](use-the-always-on-dashboard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="dddc6-120">For information about how to use the AlwaysOn Dashboard, see [Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="dddc6-121">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="dddc6-121">Using PowerShell</span></span>  
 <span data-ttu-id="dddc6-122">**Использование политик AlwaysOn для просмотра работоспособности группы доступности**</span><span class="sxs-lookup"><span data-stu-id="dddc6-122">**Use AlwaysOn policies to view the health of an availability group**</span></span>  
  
1.  <span data-ttu-id="dddc6-123">Перейдите в каталог (`cd`) экземпляра сервера, на котором размещена одна из реплик доступности.</span><span class="sxs-lookup"><span data-stu-id="dddc6-123">Set default (`cd`) to a server instance that hosts one of the availability replicas.</span></span> <span data-ttu-id="dddc6-124">Чтобы просмотреть сведения обо всех репликах доступности в группе доступности, используйте экземпляр сервера, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="dddc6-124">To view information about all of the availability replicas in an availability group, use to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="dddc6-125">Используйте следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="dddc6-125">Use the following cmdlets:</span></span>  
  
     `Test-SqlAvailabilityGroup`  
     <span data-ttu-id="dddc6-126">Оценивает работоспособность группы доступности при помощи оценки состояния политик управления SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dddc6-126">Assesses the health of an availability group by evaluating SQL Server policy based management (PBM) policies.</span></span> <span data-ttu-id="dddc6-127">Для выполнения этого командлета необходимо иметь разрешения CONNECT, VIEW SERVER STATE и VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="dddc6-127">You must have CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions to execute this cmdlet.</span></span>  
  
     <span data-ttu-id="dddc6-128">Например, следующая команда показывает все группы доступности с состоянием работоспособности «Ошибка» в экземпляре сервера `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="dddc6-128">For example, the following command shows all availability groups with a health state of "Error" on the server instance `Computer\Instance`.</span></span>  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups |
        Test-SqlAvailabilityGroup |
        Where-Object { $_.HealthState -eq "Error" }  
    ```  
  
     `Test-SqlAvailabilityReplica`  
     <span data-ttu-id="dddc6-129">Оценивает работоспособность реплик доступности при помощи оценки состояния политик управления SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dddc6-129">Assesses the health of availability replicas by evaluating SQL Server policy based management (PBM) policies.</span></span> <span data-ttu-id="dddc6-130">Для выполнения этого командлета необходимо иметь разрешения CONNECT, VIEW SERVER STATE и VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="dddc6-130">You must have CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions to execute this cmdlet.</span></span>  
  
     <span data-ttu-id="dddc6-131">Например, следующая команда оценивает работоспособность реплики доступности с именем `MyReplica` в группе доступности `MyAg` и выводит краткую сводку.</span><span class="sxs-lookup"><span data-stu-id="dddc6-131">For example, the following command evaluates the health of the availability replica named `MyReplica` in the availability group `MyAg` and outputs a brief summary.</span></span>  
  
    ```powershell
    Test-SqlAvailabilityReplica -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
     `Test-SqlDatabaseReplicaState`  
     <span data-ttu-id="dddc6-132">Оценивает работоспособность базы данных доступности на всех присоединенных репликах доступности при помощи оценки состояния политик управления SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dddc6-132">Assesses the health of an availability database on all joined availability replicas by evaluating SQL Server policy based management (PBM) policies.</span></span>  
  
     <span data-ttu-id="dddc6-133">Например, следующая команда оценивает работоспособность всех баз данных доступности в группе доступности `MyAg` и выводит краткую сводку по каждой базе данных.</span><span class="sxs-lookup"><span data-stu-id="dddc6-133">For example, the following command evaluates the health of all availability databases in the availability group `MyAg` and outputs a brief summary for each database.</span></span>  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\DatabaseReplicaStates |
        Test-SqlDatabaseReplicaState  
    ```  
  
     <span data-ttu-id="dddc6-134">Эти командлеты принимают следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="dddc6-134">These cmdlets accept the following options:</span></span>  
  
    |<span data-ttu-id="dddc6-135">Параметр</span><span class="sxs-lookup"><span data-stu-id="dddc6-135">Option</span></span>|<span data-ttu-id="dddc6-136">Описание</span><span class="sxs-lookup"><span data-stu-id="dddc6-136">Description</span></span>|  
    |------------|-----------------|  
    |`AllowUserPolicies`|<span data-ttu-id="dddc6-137">Выполняет пользовательские политики из категорий политик AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="dddc6-137">Runs user policies found in the AlwaysOn policy categories.</span></span>|  
    |`InputObject`|<span data-ttu-id="dddc6-138">Коллекция объектов, представляющих состояния групп доступности, реплик доступности или базы данных доступности (в зависимости от того, какой используется командлет).</span><span class="sxs-lookup"><span data-stu-id="dddc6-138">A collection of objects that, represent availability groups, availability replicas, or availability database states (depending on which cmdlet you are using).</span></span> <span data-ttu-id="dddc6-139">Этот командлет вычисляет исправность указанных объектов.</span><span class="sxs-lookup"><span data-stu-id="dddc6-139">The cmdlet will compute the health of the specified objects.</span></span>|  
    |`NoRefresh`|<span data-ttu-id="dddc6-140">Если задан этот параметр, командлет не обновляет вручную объекты, указанные в параметре `-Path` или `-InputObject`.</span><span class="sxs-lookup"><span data-stu-id="dddc6-140">When this parameter is set, the cmdlet will not manually refresh the objects specified by the `-Path` or `-InputObject` parameter.</span></span>|  
    |`Path`|<span data-ttu-id="dddc6-141">Путь к группе доступности, одной или нескольким репликам доступности или состоянию кластера реплики базы данных доступности (в зависимости от того, какой используется командлет).</span><span class="sxs-lookup"><span data-stu-id="dddc6-141">The path to the availability group, one or more availability replicas, or database replica cluster state of the availability database (depending on which cmdlet you are using).</span></span> <span data-ttu-id="dddc6-142">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="dddc6-142">This is an optional parameter.</span></span> <span data-ttu-id="dddc6-143">Если этот параметр не указан, его значение по умолчанию соответствует текущему рабочему расположению.</span><span class="sxs-lookup"><span data-stu-id="dddc6-143">If not specified, the value of this parameter defaults to the current working location.</span></span>|  
    |`ShowPolicyDetails`|<span data-ttu-id="dddc6-144">Показывает результат оценки каждой политики, выполненной этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="dddc6-144">Shows the result of each policy evaluation performed by this cmdlet.</span></span> <span data-ttu-id="dddc6-145">В результате работы командлета формируется по одному объекту для оценки каждой политики. Каждый такой объект имеет поле с описанием результатов оценки (было установлено соответствие политике или нет, имя и категория политики и так далее).</span><span class="sxs-lookup"><span data-stu-id="dddc6-145">The cmdlet outputs one object per policy evaluation, and this object has fields describing the results of evaluation (whether the policy passed or not, the policy name and category, and so forth).</span></span>|  
  
     <span data-ttu-id="dddc6-146">Например, следующая команда `Test-SqlAvailabilityGroup` указывает параметр `-ShowPolicyDetails`, чтобы показать результат вычисления, выполненного этим командлетом для управления на основе политик PBM в группе доступности с именем `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="dddc6-146">For example, the following `Test-SqlAvailabilityGroup` command specifies the `-ShowPolicyDetails` parameter to show the result of each policy evaluation performed by this cmdlet for each policy-based management (PBM) policy that was executed on the availability group named `MyAg`.</span></span>  
  
    ```powershell
    Test-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\AgName -ShowPolicyDetails  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="dddc6-147">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dddc6-147">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="dddc6-148">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="dddc6-148">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="dddc6-149">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="dddc6-149">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="dddc6-150">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="dddc6-150">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="dddc6-151">Получение справок по SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="dddc6-151">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="dddc6-152">См. также</span><span class="sxs-lookup"><span data-stu-id="dddc6-152">Related Content</span></span>  
 <span data-ttu-id="dddc6-153">**Блоги группы SQL Server AlwaysOn. Мониторинг работоспособности AlwaysOn с помощью PowerShell:**</span><span class="sxs-lookup"><span data-stu-id="dddc6-153">**SQL Server AlwaysOn Team Blogs-Monitoring AlwaysOn Health with PowerShell:**</span></span>  
  
-   [<span data-ttu-id="dddc6-154">Часть 1. Общие сведения о командлете</span><span class="sxs-lookup"><span data-stu-id="dddc6-154">Part 1: Basic Cmdlet Overview</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-1-basic-cmdlet-overview)  
  
-   [<span data-ttu-id="dddc6-155">Часть 2. Расширенное использование командлета</span><span class="sxs-lookup"><span data-stu-id="dddc6-155">Part 2: Advanced Cmdlet Usage</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/the-alwayson-health-model-part-2-extending-the-health-model)  
  
-   [<span data-ttu-id="dddc6-156">Часть 3. Простое приложение для мониторинга</span><span class="sxs-lookup"><span data-stu-id="dddc6-156">Part 3: A Simple Monitoring Application</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-3-a-simple-monitoring-application)  
  
-   [<span data-ttu-id="dddc6-157">Часть 4. Интеграция с агентом SQL Server</span><span class="sxs-lookup"><span data-stu-id="dddc6-157">Part 4: Integration with SQL Server Agent</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-4-integration-with-sql-server-agent)  
  
## <a name="see-also"></a><span data-ttu-id="dddc6-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="dddc6-158">See Also</span></span>  
 <span data-ttu-id="dddc6-159">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dddc6-159">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="dddc6-160">[Администрирование &#40;SQL Server группы доступности&#41;](administration-of-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dddc6-160">[Administration of an Availability Group &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="dddc6-161">[Отслеживание групп доступности (SQL Server)](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dddc6-161">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="dddc6-162">Политики AlwaysOn на случай проблем в работе с группами доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dddc6-162">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)</span></span>](always-on-policies-for-operational-issues-always-on-availability.md) 
