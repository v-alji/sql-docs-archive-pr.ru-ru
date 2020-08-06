---
title: Использование панели мониторинга AlwaysOn (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
- Availability Groups [SQL Server], dashboard
ms.assetid: c9ba2589-139e-42bc-99e1-94546717c64d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c4ce0072bcd6642dcb4f3ac63e04c98786bd550e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657307"
---
# <a name="use-the-alwayson-dashboard-sql-server-management-studio"></a><span data-ttu-id="c5194-102">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c5194-102">Use the AlwaysOn Dashboard (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c5194-103">Администраторы баз данных используют панель мониторинга AlwaysOn, чтобы быстро определять исправность группы доступности AlwaysOn, а также ее реплик доступности и баз данных в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5194-103">Database administrators use the AlwaysOn Dashboard to obtains an at-a-glance view the health of an AlwaysOn availability group and its availability replicas and databases in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="c5194-104">Далее приведены некоторые стандартные варианты использования панели мониторинга AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c5194-104">Some of the typical uses for the AlwaysOn Dashboard are:</span></span>  
  
-   <span data-ttu-id="c5194-105">Выбор реплики для выполнения перехода на другой ресурс вручную.</span><span class="sxs-lookup"><span data-stu-id="c5194-105">Choosing a replica for a manual failover.</span></span>  
  
-   <span data-ttu-id="c5194-106">Оценка возможных потерь данных при принудительной отработке отказа.</span><span class="sxs-lookup"><span data-stu-id="c5194-106">Estimating data loss if you force failover.</span></span>  
  
-   <span data-ttu-id="c5194-107">Оценка производительности синхронизации данных.</span><span class="sxs-lookup"><span data-stu-id="c5194-107">Evaluating data-synchronization performance.</span></span>  
  
-   <span data-ttu-id="c5194-108">Оценка влияния на производительность вторичной реплики с синхронной фиксацией</span><span class="sxs-lookup"><span data-stu-id="c5194-108">Evaluating the performance impact of a synchronous-commit secondary replica</span></span>  
  
 <span data-ttu-id="c5194-109">Панель мониторинга AlwaysOn отображает ключевые состояния группы доступности и индикаторы производительности, что позволяет принимать решения, необходимые для обеспечения высокого уровня доступности, полагаясь на следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="c5194-109">The AlwaysOn Dashboard provides key availability group states and performance indicators allowing you to easily make high availability operational decisions using the following types of information.</span></span>  
  
-   <span data-ttu-id="c5194-110">Состояние свертки реплики</span><span class="sxs-lookup"><span data-stu-id="c5194-110">Replica roll-up state</span></span>  
  
-   <span data-ttu-id="c5194-111">Режим и состояние синхронизации</span><span class="sxs-lookup"><span data-stu-id="c5194-111">Synchronization mode and state</span></span>  
  
-   <span data-ttu-id="c5194-112">Оценка потерь данных</span><span class="sxs-lookup"><span data-stu-id="c5194-112">Estimate Data Loss</span></span>  
  
-   <span data-ttu-id="c5194-113">Предполагаемое время восстановления (отставание при накате не происходит)</span><span class="sxs-lookup"><span data-stu-id="c5194-113">Estimated Recovery Time (redo catch up)</span></span>  
  
-   <span data-ttu-id="c5194-114">Сведения о реплике базы данных</span><span class="sxs-lookup"><span data-stu-id="c5194-114">Database Replica details</span></span>  
  
-   <span data-ttu-id="c5194-115">Режим и состояние синхронизации</span><span class="sxs-lookup"><span data-stu-id="c5194-115">Synchronization mode and state</span></span>  
  
-   <span data-ttu-id="c5194-116">Время на восстановление журнала</span><span class="sxs-lookup"><span data-stu-id="c5194-116">Time to restore log</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c5194-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c5194-117">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="c5194-118">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c5194-118">Prerequisites</span></span>  
 <span data-ttu-id="c5194-119">Необходимо подключение к экземпляру сервера [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на котором размещена первичная либо вторичная реплика группы доступности.</span><span class="sxs-lookup"><span data-stu-id="c5194-119">You must be connected to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (server instance) that hosts either the primary replica or a secondary replica of an availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c5194-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="c5194-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c5194-121">Permissions</span><span class="sxs-lookup"><span data-stu-id="c5194-121">Permissions</span></span>  
 <span data-ttu-id="c5194-122">Требуются разрешения CONNECT, VIEW SERVER STATE и VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="c5194-122">Requires CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions.</span></span>  
  
##  <a name="to-start-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a><span data-ttu-id="c5194-123">Запуск панели мониторинга AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="c5194-123">To start the AlwaysOn Dashboard</span></span>  
  
1.  <span data-ttu-id="c5194-124">В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на котором требуется запустить панель мониторинга AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c5194-124">In Object Explorer, connect to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on which you want to run the AlwaysOn Dashboard.</span></span>  
  
2.  <span data-ttu-id="c5194-125">Разверните узел **Высокий уровень доступности AlwaysOn**, правой кнопкой мыши щелкните узел **Группы доступности** и выберите пункт **Показать панель мониторинга**.</span><span class="sxs-lookup"><span data-stu-id="c5194-125">Expand the **AlwaysOn High Availability** node, right-click the **Availability Groups** node, and then click **Show Dashboard**.</span></span>  
  
###  <a name="to-change-alwayson-dashboard-options"></a><a name="DashboardOptions"></a><span data-ttu-id="c5194-126">Изменение параметров панели мониторинга AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="c5194-126">To Change AlwaysOn Dashboard Options</span></span>  
 <span data-ttu-id="c5194-127">Для настройки поведения панели мониторинга [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn для выполнения автоматического обновления и включения самостоятельно определяемой политики AlwaysOn можно использовать диалоговое окно **Параметры**[!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5194-127">You can use the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]**Options** dialog box to configure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn Dashboard behavior for automatic refreshing and enabling an auto-defined AlwaysOn policy.</span></span>  
  
1.  <span data-ttu-id="c5194-128">В меню **Сервис** щелкните пункт **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="c5194-128">From the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="c5194-129">Чтобы панель мониторинга обновлялась автоматически, в диалоговом окне **Параметры** выберите **Включить автоматическое обновление**, введите интервал обновления в секундах, после чего введите число попыток подключения.</span><span class="sxs-lookup"><span data-stu-id="c5194-129">To automatically refresh the dashboard, in the **Options** dialog box, select **Turn on automatic refresh**, enter the refresh interval in seconds, and then enter the number of times you want to retry the connection.</span></span>  
  
3.  <span data-ttu-id="c5194-130">Чтобы включить определяемую пользователем политику, выберите **Включить определяемую пользователем политику AlwaysOn**.</span><span class="sxs-lookup"><span data-stu-id="c5194-130">To enable a user-defined policy, select **Enable user-defined AlwaysOn policy**.</span></span>  
  
##  <a name="availability-group-summary"></a><a name="AvGroupsView"></a> <span data-ttu-id="c5194-131">Краткие сведения о группе доступности</span><span class="sxs-lookup"><span data-stu-id="c5194-131">Availability Group Summary</span></span>  
 <span data-ttu-id="c5194-132">На экране группы доступности отображается строка сводки по каждой группе доступности, реплика которой размещена на подключенном сервере.</span><span class="sxs-lookup"><span data-stu-id="c5194-132">The availability group screen displays a summary line for each availability group for which the connected server instance hosts a replica.</span></span> <span data-ttu-id="c5194-133">На этой панели отображаются следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="c5194-133">This pane displays the following columns.</span></span>  
  
 <span data-ttu-id="c5194-134">**Имя группы доступности**</span><span class="sxs-lookup"><span data-stu-id="c5194-134">**Availability Group Name**</span></span>  
 <span data-ttu-id="c5194-135">Имя группы доступности, реплика которой размещена на подключенном сервере.</span><span class="sxs-lookup"><span data-stu-id="c5194-135">The name of an availability group for which the connected server instance hosts a replica.</span></span>  
  
 <span data-ttu-id="c5194-136">**Основной экземпляр**</span><span class="sxs-lookup"><span data-stu-id="c5194-136">**Primary Instance**</span></span>  
 <span data-ttu-id="c5194-137">Имя экземпляра сервера, на котором размещена первичная реплика группы доступности.</span><span class="sxs-lookup"><span data-stu-id="c5194-137">Name of the server instance that is hosting the primary replica of the availability group.</span></span>  
  
 <span data-ttu-id="c5194-138">**Режим отработки отказа**</span><span class="sxs-lookup"><span data-stu-id="c5194-138">**Failover Mode**</span></span>  
 <span data-ttu-id="c5194-139">Отображает тип режима отработки отказа, который настроен для реплики.</span><span class="sxs-lookup"><span data-stu-id="c5194-139">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="c5194-140">Возможные значения режима отработки отказа:</span><span class="sxs-lookup"><span data-stu-id="c5194-140">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="c5194-141">**Автоматически**.</span><span class="sxs-lookup"><span data-stu-id="c5194-141">**Automatic**.</span></span> <span data-ttu-id="c5194-142">Указывает, что одна или несколько реплик работают в режиме автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="c5194-142">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="c5194-143">**Вручную**.</span><span class="sxs-lookup"><span data-stu-id="c5194-143">**Manual**.</span></span> <span data-ttu-id="c5194-144">Указывает, что ни одна из реплик не работает в режиме автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="c5194-144">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="c5194-145">**Проблемы**</span><span class="sxs-lookup"><span data-stu-id="c5194-145">**Issues**</span></span>  
 <span data-ttu-id="c5194-146">Щелкните ссылку **Проблемы** , чтобы открыть документацию по поиску и устранению данной неисправности.</span><span class="sxs-lookup"><span data-stu-id="c5194-146">Click the **Issues** link to open troubleshooting documentation for a given issue.</span></span> <span data-ttu-id="c5194-147">Список всех проблем с политикой AlwaysOn см. в статье [политики AlwaysOn для проблем в работе с группы доступности AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="c5194-147">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="c5194-148">Чтобы выполнить сортировку сведений о группе доступности по имени группы доступности, основной реплике, режиму отработки отказа или проблеме, щелкайте заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="c5194-148">Click the column headings to sort the availability group information by the name of the availability group, primary instance, failover mode, or Issue.</span></span>  
  
##  <a name="availability-group-details"></a><a name="AvGroupDetails"></a> <span data-ttu-id="c5194-149">Подробные сведения о группе доступности</span><span class="sxs-lookup"><span data-stu-id="c5194-149">Availability Group Details</span></span>  
 <span data-ttu-id="c5194-150">Для группы доступности, выбранной на экране кратких сведений, отображаются следующие подробные сведения:</span><span class="sxs-lookup"><span data-stu-id="c5194-150">The following detail information is displayed for the availability group that you select from the summary screen:</span></span>  
  
 <span data-ttu-id="c5194-151">**Состояние группы доступности**</span><span class="sxs-lookup"><span data-stu-id="c5194-151">**Availability group state**</span></span>  
 <span data-ttu-id="c5194-152">Отображает состояние работоспособности этой группы доступности.</span><span class="sxs-lookup"><span data-stu-id="c5194-152">Displays the state of health for the availability group.</span></span>  
  
 <span data-ttu-id="c5194-153">**Primary instance**</span><span class="sxs-lookup"><span data-stu-id="c5194-153">**Primary instance**</span></span>  
 <span data-ttu-id="c5194-154">Имя экземпляра сервера, на котором размещена первичная реплика группы доступности.</span><span class="sxs-lookup"><span data-stu-id="c5194-154">Name of the server instance that is hosting the primary replica of the availability group.</span></span>  
  
 <span data-ttu-id="c5194-155">**Failover mode**</span><span class="sxs-lookup"><span data-stu-id="c5194-155">**Failover mode**</span></span>  
 <span data-ttu-id="c5194-156">Отображает тип режима отработки отказа, который настроен для реплики.</span><span class="sxs-lookup"><span data-stu-id="c5194-156">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="c5194-157">Возможные значения режима отработки отказа:</span><span class="sxs-lookup"><span data-stu-id="c5194-157">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="c5194-158">**Автоматически**.</span><span class="sxs-lookup"><span data-stu-id="c5194-158">**Automatic**.</span></span> <span data-ttu-id="c5194-159">Указывает, что одна или несколько реплик работают в режиме автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="c5194-159">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="c5194-160">**Вручную**.</span><span class="sxs-lookup"><span data-stu-id="c5194-160">**Manual**.</span></span> <span data-ttu-id="c5194-161">Указывает, что ни одна из реплик не работает в режиме автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="c5194-161">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="c5194-162">**Состояние кластера**</span><span class="sxs-lookup"><span data-stu-id="c5194-162">**Cluster state**</span></span>  
 <span data-ttu-id="c5194-163">Имя и состояние кластера, для которого экземпляр подключенного сервера и группа доступности являются узлом-участником.</span><span class="sxs-lookup"><span data-stu-id="c5194-163">Name and state of the cluster where the instance of the connected server and the availability group is a member node.</span></span>  
  
##  <a name="availability-replica-details"></a><a name="AvReplicaDetails"></a> <span data-ttu-id="c5194-164">Подробные сведения о реплике доступности</span><span class="sxs-lookup"><span data-stu-id="c5194-164">Availability Replica Details</span></span>  
 <span data-ttu-id="c5194-165">На панели **Реплика доступности** отображаются следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="c5194-165">The **Availability replica** pane displays the following columns:</span></span>  
  
 <span data-ttu-id="c5194-166">**имя**;</span><span class="sxs-lookup"><span data-stu-id="c5194-166">**Name**</span></span>  
 <span data-ttu-id="c5194-167">Отображает имя экземпляра сервера, на котором размещена реплика доступности.</span><span class="sxs-lookup"><span data-stu-id="c5194-167">The name of the server instance that hosts the availability replica.</span></span> <span data-ttu-id="c5194-168">Этот столбец отображается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5194-168">This column is shown by default.</span></span>  
  
 <span data-ttu-id="c5194-169">**Роль**</span><span class="sxs-lookup"><span data-stu-id="c5194-169">**Role**</span></span>  
 <span data-ttu-id="c5194-170">Указывает текущую роль реплики доступности, т. е. **Первичная** или **Вторичная**.</span><span class="sxs-lookup"><span data-stu-id="c5194-170">Indicates the current role of the availability replica, either **Primary** or **Secondary**.</span></span> <span data-ttu-id="c5194-171">Сведения о ролях [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] см. в разделе [Обзор групп доступности AlwaysOn (SQL Server)](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c5194-171">For information about [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] roles, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span> <span data-ttu-id="c5194-172">Этот столбец отображается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5194-172">This column is shown by default.</span></span>  
  
 <span data-ttu-id="c5194-173">**Режим отработки отказа**</span><span class="sxs-lookup"><span data-stu-id="c5194-173">**Failover Mode**</span></span>  
 <span data-ttu-id="c5194-174">Отображает тип режима отработки отказа, который настроен для реплики.</span><span class="sxs-lookup"><span data-stu-id="c5194-174">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="c5194-175">Возможные значения режима отработки отказа:</span><span class="sxs-lookup"><span data-stu-id="c5194-175">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="c5194-176">**Автоматически**.</span><span class="sxs-lookup"><span data-stu-id="c5194-176">**Automatic**.</span></span> <span data-ttu-id="c5194-177">Указывает, что одна или несколько реплик работают в режиме автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="c5194-177">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="c5194-178">**Вручную**.</span><span class="sxs-lookup"><span data-stu-id="c5194-178">**Manual**.</span></span> <span data-ttu-id="c5194-179">Указывает, что ни одна из реплик не работает в режиме автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="c5194-179">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="c5194-180">**Состояние синхронизации**</span><span class="sxs-lookup"><span data-stu-id="c5194-180">**Synchronization State**</span></span>  
 <span data-ttu-id="c5194-181">Указывает, синхронизирована ли вторичная реплика с первичной репликой в настоящий момент.</span><span class="sxs-lookup"><span data-stu-id="c5194-181">Indicates whether a secondary replica is currently synchronized with primary replica.</span></span> <span data-ttu-id="c5194-182">Этот столбец отображается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5194-182">This column is shown by default.</span></span> <span data-ttu-id="c5194-183">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c5194-183">The possible values are:</span></span>  
  
-   <span data-ttu-id="c5194-184">**Не синхронизировано**.</span><span class="sxs-lookup"><span data-stu-id="c5194-184">**Not Synchronized**.</span></span> <span data-ttu-id="c5194-185">Одна или несколько баз данных в реплике не синхронизированы или еще присоединены к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="c5194-185">One or more databases in the replica are not synchronized or have not yet been joined to the availability group.</span></span>  
  
-   <span data-ttu-id="c5194-186">Идет **Синхронизация**.</span><span class="sxs-lookup"><span data-stu-id="c5194-186">**Synchronizing**.</span></span> <span data-ttu-id="c5194-187">Одна или несколько баз данных в реплике синхронизированы.</span><span class="sxs-lookup"><span data-stu-id="c5194-187">One or more databases in the replica are being synchronized.</span></span>  
  
-   <span data-ttu-id="c5194-188">**Синхронизировано**.</span><span class="sxs-lookup"><span data-stu-id="c5194-188">**Synchronized**.</span></span> <span data-ttu-id="c5194-189">Все базы данных на вторичной реплике синхронизированы с соответствующими базами данных-источниками в текущей первичной реплике, если она имеется, или последней первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="c5194-189">All databases in the secondary replica are synchronized with the corresponding primary databases on the current primary replica, if any, or on the last primary replica.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5194-190">В режиме приоритета производительности база данных никогда не находится в синхронизированном состоянии.</span><span class="sxs-lookup"><span data-stu-id="c5194-190">In performance mode, the database is never in the synchronized state.</span></span>  
  
-   <span data-ttu-id="c5194-191">**Значение NULL**.</span><span class="sxs-lookup"><span data-stu-id="c5194-191">**NULL**.</span></span> <span data-ttu-id="c5194-192">Неизвестное состояние.</span><span class="sxs-lookup"><span data-stu-id="c5194-192">Unknown state.</span></span> <span data-ttu-id="c5194-193">Это значение возникает, когда экземпляр локального сервера не может обмениваться данными с отказоустойчивым кластером WSFC (то есть этот локальный узел не принадлежит кворуму отказоустойчивого кластера WSFC).</span><span class="sxs-lookup"><span data-stu-id="c5194-193">This value occurs when the local server instance cannot communicate with the WSFC failover cluster (that is the local node is not part of WSFC quorum).</span></span>  
  
 <span data-ttu-id="c5194-194">**Проблемы**</span><span class="sxs-lookup"><span data-stu-id="c5194-194">**Issues**</span></span>  
 <span data-ttu-id="c5194-195">Содержит имя проблемы.</span><span class="sxs-lookup"><span data-stu-id="c5194-195">Lists the issue name.</span></span> <span data-ttu-id="c5194-196">Это значение отображается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5194-196">This value is shown by default.</span></span> <span data-ttu-id="c5194-197">Список всех проблем с политикой AlwaysOn см. в статье [политики AlwaysOn для проблем в работе с группы доступности AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="c5194-197">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
 <span data-ttu-id="c5194-198">**Режим доступности**</span><span class="sxs-lookup"><span data-stu-id="c5194-198">**Availability Mode**</span></span>  
 <span data-ttu-id="c5194-199">Указывает свойство реплики, устанавливаемое отдельно для каждой реплики доступности.</span><span class="sxs-lookup"><span data-stu-id="c5194-199">Indicates the replica property that you set separately for each availability replica.</span></span> <span data-ttu-id="c5194-200">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-200">This value is hidden by default.</span></span> <span data-ttu-id="c5194-201">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c5194-201">The possible values are:</span></span>  
  
-   <span data-ttu-id="c5194-202">**Асинхронный**.</span><span class="sxs-lookup"><span data-stu-id="c5194-202">**Asynchronous**.</span></span> <span data-ttu-id="c5194-203">Вторичная реплика никогда не синхронизируется с первичной репликой.</span><span class="sxs-lookup"><span data-stu-id="c5194-203">The secondary replica never becomes synchronized with the primary replica.</span></span>  
  
-   <span data-ttu-id="c5194-204">**Синхронный**.</span><span class="sxs-lookup"><span data-stu-id="c5194-204">**Synchronous**.</span></span> <span data-ttu-id="c5194-205">В процессе синхронизации с базой данных-источником база данных-получатель входит в это состояние и остается синхронизированной, пока для этой базы данных продолжается синхронизация.</span><span class="sxs-lookup"><span data-stu-id="c5194-205">When catching up to the primary database, a secondary database enters this state, and it remains caught up as long as data synchronization continues for the database.</span></span>  
  
 <span data-ttu-id="c5194-206">**Основной режим подключения**</span><span class="sxs-lookup"><span data-stu-id="c5194-206">**Primary Connection Mode**</span></span>  
 <span data-ttu-id="c5194-207">Указывает режим, который используется при подключении к первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="c5194-207">Indicates the mode that is used to connect to the primary replica.</span></span>  <span data-ttu-id="c5194-208">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-208">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-209">**Вторичный режим подключения**</span><span class="sxs-lookup"><span data-stu-id="c5194-209">**Secondary Connection Mode**</span></span>  
 <span data-ttu-id="c5194-210">Указывает режим, который используется при подключении к вторичной реплике.</span><span class="sxs-lookup"><span data-stu-id="c5194-210">Indicates the mode that is used to connect to the secondary replica.</span></span>  <span data-ttu-id="c5194-211">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-211">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-212">**Состояние соединения**</span><span class="sxs-lookup"><span data-stu-id="c5194-212">**Connection State**</span></span>  
 <span data-ttu-id="c5194-213">Указывает, подключена ли в настоящий момент вторичная реплика к первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="c5194-213">Indicates whether a secondary replica is currently connected to the primary replica.</span></span> <span data-ttu-id="c5194-214">Этот столбец по умолчанию скрыт.</span><span class="sxs-lookup"><span data-stu-id="c5194-214">This column is hidden by default.</span></span> <span data-ttu-id="c5194-215">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c5194-215">The possible values are:</span></span>  
  
-   <span data-ttu-id="c5194-216">**Отключено**.</span><span class="sxs-lookup"><span data-stu-id="c5194-216">**Disconnected**.</span></span> <span data-ttu-id="c5194-217">Для удаленной реплики доступности указывает, что она отключена от локальной реплики доступности.</span><span class="sxs-lookup"><span data-stu-id="c5194-217">For a remote availability replica, indicates that it is disconnected from the local availability replica.</span></span> <span data-ttu-id="c5194-218">Реакция локальной реплики на состояние «Отключена» зависит от ее роли следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c5194-218">The response of the local replica to the Disconnected state depends on its role, as follows:</span></span>  
  
    -   <span data-ttu-id="c5194-219">На первичной реплике при отключении вторичной реплики базы данных-получатели отмечаются как **Не синхронизирована** , а первичная реплика ожидает восстановления подключения от вторичной.</span><span class="sxs-lookup"><span data-stu-id="c5194-219">On the primary replica, if a secondary replica is disconnected, the secondary databases are marked as **Not Synchronized** on the primary replica, and the primary replica waits for the secondary to reconnect.</span></span>  
  
    -   <span data-ttu-id="c5194-220">На вторичной реплике при обнаружении разрыва соединения начинаются попытки восстановить соединение с первичной репликой.</span><span class="sxs-lookup"><span data-stu-id="c5194-220">On the secondary replica, upon detecting that it is disconnected, the secondary replica attempts to reconnect to the primary replica.</span></span>  
  
-   <span data-ttu-id="c5194-221">**Подключено**.</span><span class="sxs-lookup"><span data-stu-id="c5194-221">**Connected**.</span></span> <span data-ttu-id="c5194-222">Удаленная реплика доступности, которая в настоящее время подключена к локальной реплике.</span><span class="sxs-lookup"><span data-stu-id="c5194-222">A remote availability replica that is currently connected to the local replica.</span></span>  
  
 <span data-ttu-id="c5194-223">**Операционное состояние**</span><span class="sxs-lookup"><span data-stu-id="c5194-223">**Operational State**</span></span>  
 <span data-ttu-id="c5194-224">Указывает текущее состояние работоспособности вторичной реплики.</span><span class="sxs-lookup"><span data-stu-id="c5194-224">Indicates the current operational state of the secondary replica.</span></span> <span data-ttu-id="c5194-225">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-225">This value is hidden by default.</span></span> <span data-ttu-id="c5194-226">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c5194-226">The possible values are:</span></span>  
  
 <span data-ttu-id="c5194-227">**0**. Ожидается отработка отказа</span><span class="sxs-lookup"><span data-stu-id="c5194-227">**0**. Pending failover</span></span>  
  
 <span data-ttu-id="c5194-228">**1**. Ожидает</span><span class="sxs-lookup"><span data-stu-id="c5194-228">**1**. Pending</span></span>  
  
 <span data-ttu-id="c5194-229">**2**. Справка в Интернете</span><span class="sxs-lookup"><span data-stu-id="c5194-229">**2**. Online</span></span>  
  
 <span data-ttu-id="c5194-230">**3**. Вне сети</span><span class="sxs-lookup"><span data-stu-id="c5194-230">**3**. Offline</span></span>  
  
 <span data-ttu-id="c5194-231">**4**. Ошибка</span><span class="sxs-lookup"><span data-stu-id="c5194-231">**4**. Failed</span></span>  
  
 <span data-ttu-id="c5194-232">**5**. Ошибка, нет кворума</span><span class="sxs-lookup"><span data-stu-id="c5194-232">**5**. Failed, no quorum</span></span>  
  
 <span data-ttu-id="c5194-233">**Значение NULL**.</span><span class="sxs-lookup"><span data-stu-id="c5194-233">**NULL**.</span></span> <span data-ttu-id="c5194-234">Реплика не является локальной</span><span class="sxs-lookup"><span data-stu-id="c5194-234">Replica is not local</span></span>  
  
 <span data-ttu-id="c5194-235">**№ ошибки последнего подключения**</span><span class="sxs-lookup"><span data-stu-id="c5194-235">**Last Connection Error No.**</span></span>  
 <span data-ttu-id="c5194-236">Номер последней возникшей ошибки подключения.</span><span class="sxs-lookup"><span data-stu-id="c5194-236">Number of the last connection error.</span></span>  <span data-ttu-id="c5194-237">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-237">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-238">**Описание ошибки последнего подключения**</span><span class="sxs-lookup"><span data-stu-id="c5194-238">**Last Connection Error Description**</span></span>  
 <span data-ttu-id="c5194-239">Описание ошибки, возникшей во время последнего подключения.</span><span class="sxs-lookup"><span data-stu-id="c5194-239">Description of the last connection error.</span></span>  <span data-ttu-id="c5194-240">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-240">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-241">**Отметка времени ошибки последнего подключения**</span><span class="sxs-lookup"><span data-stu-id="c5194-241">**Last Connection Error Timestamp**</span></span>  
 <span data-ttu-id="c5194-242">Отметка времени последней возникшей ошибки подключения.</span><span class="sxs-lookup"><span data-stu-id="c5194-242">Timestamp of the last connection error.</span></span> <span data-ttu-id="c5194-243">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-243">This value is hidden by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c5194-244">Сведения о счетчиках производительности для реплик доступности см. в статье [SQL Server, реплика доступности](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="c5194-244">For information about performance counters for availability replicas, see [SQL Server, Availability Replica](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span></span>  
  
##  <a name="to-group-availability-group-information"></a><a name="AvDbDetails"></a> <span data-ttu-id="c5194-245">Группирование сведений о группе доступности</span><span class="sxs-lookup"><span data-stu-id="c5194-245">To Group Availability Group Information</span></span>  
 <span data-ttu-id="c5194-246">Чтобы сгруппировать сведения, нажмите **Группировать по**и выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="c5194-246">To group the information, click **Group by**, and select one of the following:</span></span>  
  
-   <span data-ttu-id="c5194-247">**Реплики доступности**</span><span class="sxs-lookup"><span data-stu-id="c5194-247">**Availability replicas**</span></span>  
  
-   <span data-ttu-id="c5194-248">**Базы данных доступности**</span><span class="sxs-lookup"><span data-stu-id="c5194-248">**Availability databases**</span></span>  
  
-   <span data-ttu-id="c5194-249">**Состояние синхронизации**</span><span class="sxs-lookup"><span data-stu-id="c5194-249">**Synchronization state**</span></span>  
  
-   <span data-ttu-id="c5194-250">**Готовность к отработке отказа**</span><span class="sxs-lookup"><span data-stu-id="c5194-250">**Failover readiness**</span></span>  
  
-   <span data-ttu-id="c5194-251">**Проблемы**</span><span class="sxs-lookup"><span data-stu-id="c5194-251">**Issues**</span></span>  
  
 <span data-ttu-id="c5194-252">Панель, на которой отображаются сгруппированные сведения, содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="c5194-252">The pane that displays the grouped information displays the following columns:</span></span>  
  
 <span data-ttu-id="c5194-253">**имя**;</span><span class="sxs-lookup"><span data-stu-id="c5194-253">**Name**</span></span>  
 <span data-ttu-id="c5194-254">Имя базы данных доступности.</span><span class="sxs-lookup"><span data-stu-id="c5194-254">The name of the availability database.</span></span> <span data-ttu-id="c5194-255">Это значение отображается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5194-255">This value is shown by default.</span></span>  
  
 <span data-ttu-id="c5194-256">**Реплика**</span><span class="sxs-lookup"><span data-stu-id="c5194-256">**Replica**</span></span>  
 <span data-ttu-id="c5194-257">Имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , в котором размещается группа доступности.</span><span class="sxs-lookup"><span data-stu-id="c5194-257">The name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica.</span></span> <span data-ttu-id="c5194-258">Это значение отображается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5194-258">This value is shown by default.</span></span>  
  
 <span data-ttu-id="c5194-259">**Состояние синхронизации**</span><span class="sxs-lookup"><span data-stu-id="c5194-259">**Synchronization State**</span></span>  
 <span data-ttu-id="c5194-260">Указывает, синхронизирована ли база данных доступности с первичной репликой.</span><span class="sxs-lookup"><span data-stu-id="c5194-260">Indicates whether the availability database is currently synchronized with primary replica.</span></span> <span data-ttu-id="c5194-261">Это значение отображается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5194-261">This value is shown by default.</span></span> <span data-ttu-id="c5194-262">Возможны следующие состояния синхронизации.</span><span class="sxs-lookup"><span data-stu-id="c5194-262">The possible synchronization states are:</span></span>  
  
-   <span data-ttu-id="c5194-263">**Не синхронизирована**.</span><span class="sxs-lookup"><span data-stu-id="c5194-263">**Not synchronizing**.</span></span>  
  
    -   <span data-ttu-id="c5194-264">Для роли источника указывает, что база данных не готова к синхронизации своего журнала транзакций с соответствующими базами данных-получателями.</span><span class="sxs-lookup"><span data-stu-id="c5194-264">For the primary role, indicates that the database is not ready to synchronize its transaction log with the corresponding secondary databases.</span></span>  
  
    -   <span data-ttu-id="c5194-265">Для базы данных-получателя указывает, что на базе данных не запущена синхронизация журнала из-за проблем с соединением, синхронизация приостановлена или же база данных находится в переходных состояниях во время запуска или переключения ролей.</span><span class="sxs-lookup"><span data-stu-id="c5194-265">For a secondary database, indicates that the database has not started log synchronization because of a connection issue, is being suspended, or is going through transition states during startup or a role switch.</span></span>  
  
-   <span data-ttu-id="c5194-266">Идет **Синхронизация**.</span><span class="sxs-lookup"><span data-stu-id="c5194-266">**Synchronizing**.</span></span>  
  
     <span data-ttu-id="c5194-267">На первичной реплике:</span><span class="sxs-lookup"><span data-stu-id="c5194-267">On a primary replica:</span></span>  
  
    -   <span data-ttu-id="c5194-268">Для базы данных-источника указывает, что эта база данных готова принимать запросы на просмотр от базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="c5194-268">For a primary database, indicates that this database is ready to accept a scan request from a secondary database.</span></span>  
  
    -   <span data-ttu-id="c5194-269">На вторичной реплике указывает, что для этой базы данных-получателя происходит активное перемещение данных.</span><span class="sxs-lookup"><span data-stu-id="c5194-269">On a secondary replica, indicates that there is active data movement going on for that secondary database.</span></span>  
  
     <span data-ttu-id="c5194-270">На вторичной реплике указывает, что для этой реплики происходит активное перемещение данных.</span><span class="sxs-lookup"><span data-stu-id="c5194-270">On a secondary replica, indicates that there is active data movement going on for that replica.</span></span>  
  
-   <span data-ttu-id="c5194-271">**Синхронизировано**.</span><span class="sxs-lookup"><span data-stu-id="c5194-271">**Synchronized**.</span></span>  
  
     <span data-ttu-id="c5194-272">Для базы данных-источника указывает, что синхронизирована по крайней мере одна база данных-получатель.</span><span class="sxs-lookup"><span data-stu-id="c5194-272">For a primary database, indicates that at least one secondary database is synchronized.</span></span>  
  
     <span data-ttu-id="c5194-273">Для базы данных-получателя указывает, что база данных синхронизирована с соответствующей базой данных-источником.</span><span class="sxs-lookup"><span data-stu-id="c5194-273">For a secondary database, indicates that the database is synchronized with the corresponding primary database.</span></span>  
  
-   <span data-ttu-id="c5194-274">**Возврат**.</span><span class="sxs-lookup"><span data-stu-id="c5194-274">**Reverting**.</span></span>  
  
     <span data-ttu-id="c5194-275">Обозначает этап процесса отката, в котором база данных-получатель активно получает страницы с базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="c5194-275">Indicates the phase in the undo process when a secondary database is actively getting pages from the primary database.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="c5194-276">Когда база данных находится в состоянии REVERTING, принудительный переход на вторичную реплику может оставить эту базу данных в состоянии, при котором ее запуск будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="c5194-276">When a database is in the REVERTING state, forcing failover to the secondary replica can leave that database in a state in which it cannot be started.</span></span>  
  
-   <span data-ttu-id="c5194-277">**Инициализация**.</span><span class="sxs-lookup"><span data-stu-id="c5194-277">**Initializing**.</span></span>  
  
     <span data-ttu-id="c5194-278">Обозначает этап процесса отката, на котором журнал транзакций, по которому базе данных-получателю необходимо устранить вплоть до номера LSN, который доставляется и фиксируется на вторичной реплике.</span><span class="sxs-lookup"><span data-stu-id="c5194-278">Indicates the phase of undo when the transaction log required for a secondary database to catch up to the undo LSN is being shipped and hardened on a secondary replica.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="c5194-279">Когда база данных находится в состоянии INITIALIZING, принудительная отработка отказа на вторичную реплику всегда оставляет такую базу данных в состоянии, при котором ее запуск будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="c5194-279">When a database is in the INITIALIZING state, forcing failover to the secondary replica will always leave that database in a state in which it cannot be started.</span></span>  
  
 <span data-ttu-id="c5194-280">**Готовность к отработке отказа**</span><span class="sxs-lookup"><span data-stu-id="c5194-280">**Failover Readiness**</span></span>  
 <span data-ttu-id="c5194-281">Указывает, какая реплика доступности готова к отработке отказа, которая потенциально может пройти без потерь данных или с потерей данных.</span><span class="sxs-lookup"><span data-stu-id="c5194-281">Indicates which availability replica can be failed over with or without potential data loss.</span></span> <span data-ttu-id="c5194-282">Этот столбец отображается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5194-282">This column is shown by default.</span></span> <span data-ttu-id="c5194-283">Вы можете выбрать</span><span class="sxs-lookup"><span data-stu-id="c5194-283">The possible values are:</span></span>  
  
-   <span data-ttu-id="c5194-284">**Потери данных**</span><span class="sxs-lookup"><span data-stu-id="c5194-284">**Data Loss**</span></span>  
  
-   <span data-ttu-id="c5194-285">**Без потерь данных**</span><span class="sxs-lookup"><span data-stu-id="c5194-285">**No Data Loss**</span></span>  
  
 <span data-ttu-id="c5194-286">**Проблемы**</span><span class="sxs-lookup"><span data-stu-id="c5194-286">**Issues**</span></span>  
 <span data-ttu-id="c5194-287">Содержит имя проблемы.</span><span class="sxs-lookup"><span data-stu-id="c5194-287">Lists the issue name.</span></span> <span data-ttu-id="c5194-288">Этот столбец отображается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5194-288">This column is shown by default.</span></span> <span data-ttu-id="c5194-289">Вы можете выбрать</span><span class="sxs-lookup"><span data-stu-id="c5194-289">The possible values are:</span></span>  
  
-   <span data-ttu-id="c5194-290">**Предупреждения**.</span><span class="sxs-lookup"><span data-stu-id="c5194-290">**Warnings**.</span></span> <span data-ttu-id="c5194-291">Щелкните, чтобы отобразить пороговые значения и предупреждения.</span><span class="sxs-lookup"><span data-stu-id="c5194-291">Click to display the thresholds and warnings issues.</span></span>  
  
-   <span data-ttu-id="c5194-292">**Критическое**.</span><span class="sxs-lookup"><span data-stu-id="c5194-292">**Critical**.</span></span> <span data-ttu-id="c5194-293">Щелкните для отображения критических проблем.</span><span class="sxs-lookup"><span data-stu-id="c5194-293">Click to display the critical issues.</span></span>  
  
 <span data-ttu-id="c5194-294">Список всех проблем с политикой AlwaysOn см. в статье [политики AlwaysOn для проблем в работе с группы доступности AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="c5194-294">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
 <span data-ttu-id="c5194-295">**Приостановлена**</span><span class="sxs-lookup"><span data-stu-id="c5194-295">**Suspended**</span></span>  
 <span data-ttu-id="c5194-296">Указывает, что работа базы данных **Приостановлена** или **Возобновлена**.</span><span class="sxs-lookup"><span data-stu-id="c5194-296">Indicates whether the database is **Suspended** or has been **Resumed**.</span></span> <span data-ttu-id="c5194-297">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-297">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-298">**Причина приостановки**</span><span class="sxs-lookup"><span data-stu-id="c5194-298">**Suspend Reason**</span></span>  
 <span data-ttu-id="c5194-299">Указывает причину приостановки.</span><span class="sxs-lookup"><span data-stu-id="c5194-299">Indicates the reason for the suspended state.</span></span> <span data-ttu-id="c5194-300">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-300">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-301">**Оценка потерь данных (в секундах)**</span><span class="sxs-lookup"><span data-stu-id="c5194-301">**Estimate Data Loss (seconds)**</span></span>  
 <span data-ttu-id="c5194-302">Указывает разницу во времени между последними записями журнала транзакций на первичной и на вторичной репликах.</span><span class="sxs-lookup"><span data-stu-id="c5194-302">Indicates the time difference of the last transaction log record in the primary replica and secondary replica.</span></span> <span data-ttu-id="c5194-303">Если произойдет отказ в первичной реплике, то все записи журнала транзакций в этом временном окне будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="c5194-303">If the primary replica fails, all transaction log records within the time window will be lost.</span></span> <span data-ttu-id="c5194-304">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-304">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-305">**Примерное время восстановления (в секундах)**</span><span class="sxs-lookup"><span data-stu-id="c5194-305">**Estimated Recovery Time (seconds)**</span></span>  
 <span data-ttu-id="c5194-306">Указывает время в секундах, необходимое для повтора наверстывания времени.</span><span class="sxs-lookup"><span data-stu-id="c5194-306">Indicates the time in seconds it takes to redo the catch-up time.</span></span> <span data-ttu-id="c5194-307">*Время наверстывания* — это время, которое потребуется вторичной реплике для того, чтобы догнать первичную реплику.</span><span class="sxs-lookup"><span data-stu-id="c5194-307">The *catch-up time* is the time it will take for the secondary replica to catch up with the primary replica.</span></span> <span data-ttu-id="c5194-308">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-308">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-309">**Производительность синхронизации (в секундах)**</span><span class="sxs-lookup"><span data-stu-id="c5194-309">**Synchronization Performance (seconds)**</span></span>  
 <span data-ttu-id="c5194-310">Указывает время в секундах, необходимое для синхронизации между первичной и вторичной репликами.</span><span class="sxs-lookup"><span data-stu-id="c5194-310">Indicates the time in seconds it takes to synchronize between the primary and secondary replicas.</span></span> <span data-ttu-id="c5194-311">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-311">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-312">**Размер очереди отправки журнала (KB)**</span><span class="sxs-lookup"><span data-stu-id="c5194-312">**Log Send Queue Size (KB)**</span></span>  
 <span data-ttu-id="c5194-313">Указывает количество записей журнала в файлах журнала базы данных-источника, которые еще не отправлены вторичной реплике.</span><span class="sxs-lookup"><span data-stu-id="c5194-313">Indicates the amount of log records in the log files of the primary database that have not been sent to the secondary replica.</span></span> <span data-ttu-id="c5194-314">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-314">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-315">**Скорость отправки журнала (КБ/сек)**</span><span class="sxs-lookup"><span data-stu-id="c5194-315">**Log Send Rate (KB/sec)**</span></span>  
 <span data-ttu-id="c5194-316">Указывает скорость в КБ/сек, с которой записи журнала отправляются вторичной реплике. Это значение скрыто по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5194-316">Indicates the rate in KB per second at which log records are being sent to the secondary replica This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-317">**Размер очереди повторного выполнения (KB)**</span><span class="sxs-lookup"><span data-stu-id="c5194-317">**Redo Queue Size (KB)**</span></span>  
 <span data-ttu-id="c5194-318">Указывает количество записей журнала в файлах журнала вторичной реплики, которые еще не были выполнены повторно.</span><span class="sxs-lookup"><span data-stu-id="c5194-318">Indicates the amount of log records in the log files of the secondary replica that have not yet been redone.</span></span> <span data-ttu-id="c5194-319">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-319">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-320">**Скорость повторного выполнения (КБ/сек)**</span><span class="sxs-lookup"><span data-stu-id="c5194-320">**Redo Rate (KB/sec)**</span></span>  
 <span data-ttu-id="c5194-321">Указывает скорость в КБ/сек, с которой записи журналов обрабатываются повторно.</span><span class="sxs-lookup"><span data-stu-id="c5194-321">Indicates the rate in KB per second at which the log records are being redone.</span></span> <span data-ttu-id="c5194-322">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-322">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-323">**Скорость отправки FileStream (КБ/сек)**</span><span class="sxs-lookup"><span data-stu-id="c5194-323">**FileStream Send Rate (KB/sec)**</span></span>  
 <span data-ttu-id="c5194-324">Указывает скорость FileStream в килобайтах в секунду, с которой транзакции отправляются реплике.</span><span class="sxs-lookup"><span data-stu-id="c5194-324">Indicates the rate of the FileStream in KB per second at which transactions are being sent to the replica.</span></span> <span data-ttu-id="c5194-325">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-325">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-326">**Номер LSN конца журнала**</span><span class="sxs-lookup"><span data-stu-id="c5194-326">**End of Log LSN**</span></span>  
 <span data-ttu-id="c5194-327">Указывает регистрационный номер транзакции в журнале (LSN), соответствующий последней записи журнала в кэше журнала на первичной и вторичной репликах.</span><span class="sxs-lookup"><span data-stu-id="c5194-327">Indicates the actual log sequence number (LSN) that corresponds to the last log record in the log cache on the primary and secondary replicas.</span></span> <span data-ttu-id="c5194-328">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-328">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-329">**Номер LSN восстановления**</span><span class="sxs-lookup"><span data-stu-id="c5194-329">**Recovery LSN**</span></span>  
 <span data-ttu-id="c5194-330">Указывает окончание журнала транзакций до того, как реплика внесет любые новые записи журнала после восстановления или отработки отказа на первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="c5194-330">Indicates the end of the transaction log before the replica writes any new log records after recovery or failover on the primary replica.</span></span> <span data-ttu-id="c5194-331">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-331">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-332">**Номер LSN усечения**</span><span class="sxs-lookup"><span data-stu-id="c5194-332">**Truncation LSN**</span></span>  
 <span data-ttu-id="c5194-333">Указывает минимальное значение усечения журнала для первичной реплики.</span><span class="sxs-lookup"><span data-stu-id="c5194-333">Indicates the minimum log truncation value for the primary replica.</span></span> <span data-ttu-id="c5194-334">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-334">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-335">**Номер LSN последней фиксации**</span><span class="sxs-lookup"><span data-stu-id="c5194-335">**Last Commit LSN**</span></span>  
 <span data-ttu-id="c5194-336">Указывает фактический номер LSN, соответствующий последней записи фиксации в журнале транзакций.</span><span class="sxs-lookup"><span data-stu-id="c5194-336">Indicates the actual LSN corresponding to the last commit record in the transaction log.</span></span> <span data-ttu-id="c5194-337">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-337">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-338">**Время последней фиксации**</span><span class="sxs-lookup"><span data-stu-id="c5194-338">**Last Commit Time**</span></span>  
 <span data-ttu-id="c5194-339">Указывает время, соответствующее последней записи фиксации.</span><span class="sxs-lookup"><span data-stu-id="c5194-339">Indicates the time corresponding to the last commit record.</span></span> <span data-ttu-id="c5194-340">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-340">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-341">**Номер LSN последней отправки**</span><span class="sxs-lookup"><span data-stu-id="c5194-341">**Last Sent LSN**</span></span>  
 <span data-ttu-id="c5194-342">Указывает точку, до которой все блоки журнала уже отправлены первичной репликой.</span><span class="sxs-lookup"><span data-stu-id="c5194-342">Indicates the point up to which all log blocks have been sent by the primary replica.</span></span> <span data-ttu-id="c5194-343">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-343">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-344">**Время последней отправки**</span><span class="sxs-lookup"><span data-stu-id="c5194-344">**Last Sent Time**</span></span>  
 <span data-ttu-id="c5194-345">Указывает время отправки последнего блока.</span><span class="sxs-lookup"><span data-stu-id="c5194-345">Indicates the time when the last log block was sent.</span></span> <span data-ttu-id="c5194-346">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-346">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-347">**Номер LSN последнего получения**</span><span class="sxs-lookup"><span data-stu-id="c5194-347">**Last Received LSN**</span></span>  
 <span data-ttu-id="c5194-348">Указывает точку, до которой все блоки журнала были получены вторичной репликой, на которой размещена эта база данных-получатель.</span><span class="sxs-lookup"><span data-stu-id="c5194-348">Indicates the point up to which all log blocks have been received by the secondary replica that hosts the secondary database.</span></span> <span data-ttu-id="c5194-349">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-349">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-350">**Время последнего получения**</span><span class="sxs-lookup"><span data-stu-id="c5194-350">**Last Received Time**</span></span>  
 <span data-ttu-id="c5194-351">Указывает время, когда идентификатор блока журнала в последнем полученном сообщении был в последний раз прочитан во вторичной реплике.</span><span class="sxs-lookup"><span data-stu-id="c5194-351">Indicates the time when the log block identifier in last message received was read on the secondary replica.</span></span> <span data-ttu-id="c5194-352">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-352">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-353">**Последний зафиксированный номер LSN**</span><span class="sxs-lookup"><span data-stu-id="c5194-353">**Last Hardened LSN**</span></span>  
 <span data-ttu-id="c5194-354">Указывает точку, вплоть до которой все записи журнала были записаны на диск на вторичной реплике.</span><span class="sxs-lookup"><span data-stu-id="c5194-354">Indicates the point up to which all log records have been flushed to disk on the secondary replica.</span></span> <span data-ttu-id="c5194-355">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-355">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-356">**Время последней записи на диск**</span><span class="sxs-lookup"><span data-stu-id="c5194-356">**Last Hardened Time**</span></span>  
 <span data-ttu-id="c5194-357">Указывает время, в которое во вторичной реплике был получен идентификатор блока журнала для последнего зафиксированного номера LSN.</span><span class="sxs-lookup"><span data-stu-id="c5194-357">Indicates the time when the log-block identifier was received for the last hardened LSN on the secondary replica.</span></span> <span data-ttu-id="c5194-358">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-358">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-359">**Номер LSN последней повторной обработки**</span><span class="sxs-lookup"><span data-stu-id="c5194-359">**Last Redone LSN**</span></span>  
 <span data-ttu-id="c5194-360">Указывает фактический номер LSN записи в журнале, которая была в последний раз повторно обработана во вторичной реплике.</span><span class="sxs-lookup"><span data-stu-id="c5194-360">Indicates the actual LSN of the log record that was redone last on the secondary replica.</span></span> <span data-ttu-id="c5194-361">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-361">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="c5194-362">**Время последней повторной обработки**</span><span class="sxs-lookup"><span data-stu-id="c5194-362">**Last Redone Time**</span></span>  
 <span data-ttu-id="c5194-363">Указывает время, когда последняя запись журнала была повторно обработана в базе данных-получателе.</span><span class="sxs-lookup"><span data-stu-id="c5194-363">Indicates the time when the last log record was redone on the secondary database.</span></span> <span data-ttu-id="c5194-364">Это значение по умолчанию скрыто.</span><span class="sxs-lookup"><span data-stu-id="c5194-364">This value is hidden by default.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="c5194-365">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="c5194-365">Related Tasks</span></span>  
  
-   [<span data-ttu-id="c5194-366">Используйте политики AlwaysOn для просмотра работоспособности группы доступности &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c5194-366">Use AlwaysOn Policies to View the Health of an Availability Group &#40;SQL Server&#41;</span></span>](use-always-on-policies-to-view-the-health-of-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="c5194-367">См. также:</span><span class="sxs-lookup"><span data-stu-id="c5194-367">See Also</span></span>  
 <span data-ttu-id="c5194-368">[sys.dm_os_performance_counters (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c5194-368">[sys.dm_os_performance_counters &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql) </span></span>  
 [<span data-ttu-id="c5194-369">Отслеживание групп доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c5194-369">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
  
