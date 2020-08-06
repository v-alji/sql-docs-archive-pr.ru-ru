---
title: Настройка маршрутизации только для чтения в группе доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- read-only routing
- Availability Groups [SQL Server], readable secondary replicas
- Availability Groups [SQL Server], read-only routing
- readable secondary replicas
- Availability Groups [SQL Server], client connectivity
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: 7bd89ddd-0403-4930-a5eb-3c78718533d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2d51d1db75caa29814a01fc1f49bfdd49b403c3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666218"
---
# <a name="configure-read-only-routing-for-an-availability-group-sql-server"></a><span data-ttu-id="1016f-102">Настройка маршрутизации только для чтения в группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1016f-102">Configure Read-Only Routing for an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="1016f-103">Чтобы настроить группу доступности AlwaysOn для поддержки маршрутизации только для чтения в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], можно использовать процедуру [!INCLUDE[tsql](../../../includes/tsql-md.md)] или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1016f-103">To configure an AlwaysOn availability group to support read-only routing in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], you can use either [!INCLUDE[tsql](../../../includes/tsql-md.md)] or PowerShell.</span></span> <span data-ttu-id="1016f-104">*Маршрутизация только для чтения* означает способность [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] направлять уточняющие запросы на соединение только для чтения к имеющейся [доступной для чтения вторичной реплике](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) AlwaysOn (то есть реплике, настроенной для разрешения рабочей нагрузки только для чтения при выполнении вторичной роли).</span><span class="sxs-lookup"><span data-stu-id="1016f-104">*Read-only routing* refers to the ability of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to route qualifying read-only connection requests to an available AlwaysOn [readable secondary replica](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) (that is, a replica that is configured to allow read-only workloads when running under the secondary role).</span></span> <span data-ttu-id="1016f-105">Для поддержки маршрутизации только для чтения группа доступности должна иметь [прослушиватель группы доступности](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="1016f-105">To support read-only routing, the availability group must possess an [availability group listener](../../listeners-client-connectivity-application-failover.md).</span></span> <span data-ttu-id="1016f-106">Клиент, запрашивающий данные в режиме только чтения, должен направлять свои запросы к данному прослушивателю, а строки подключения клиента должны определять намерение приложения как «только для чтения».</span><span class="sxs-lookup"><span data-stu-id="1016f-106">Read-only clients must direct their connection requests to this listener, and the client's connection strings must specify the application intent as "read-only."</span></span> <span data-ttu-id="1016f-107">Это означает, что они должны быть *запросами на соединение с правами чтения*.</span><span class="sxs-lookup"><span data-stu-id="1016f-107">That is, they must be *read-intent connection requests*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1016f-108">Дополнительные сведения о настройке доступной для чтения вторичной реплики см. в разделе [Настройка доступа только для чтения в реплике доступности (SQL Server)](configure-read-only-access-on-an-availability-replica-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1016f-108">For information about how to configure a readable secondary replica, see [Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="1016f-109">Настройка маршрутизации только для чтения не поддерживается в среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1016f-109">Configuring read-only routing is not supported by [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1016f-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1016f-110">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="1016f-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1016f-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="1016f-112">Группа доступности должна обладать прослушивателем группы доступности.</span><span class="sxs-lookup"><span data-stu-id="1016f-112">The availability group must possess an availability group listener.</span></span> <span data-ttu-id="1016f-113">Дополнительные сведения см. в разделе [Создание или настройка прослушивателя группы доступности (SQL Server)](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1016f-113">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
-   <span data-ttu-id="1016f-114">Одна или несколько реплик доступности должны быть настроены на прием только для чтения во вторичной роли (то есть доступны для чтения [вторичные реплики](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)(AlwaysOn% 20Availability% 20Groups \) . md)).</span><span class="sxs-lookup"><span data-stu-id="1016f-114">One or more availability replicas must be configured to accept read-only in the secondary role (that is, to be [readable secondary replicas](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)(AlwaysOn%20Availability%20Groups\).md)).</span></span> <span data-ttu-id="1016f-115">Дополнительные сведения см. в разделе [Настройка доступа только для чтения в реплике доступности (SQL Server)](configure-read-only-access-on-an-availability-replica-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1016f-115">For more information, see [Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span></span>  
  
-   <span data-ttu-id="1016f-116">Необходимо подключиться к экземпляру сервера, на котором размещена текущая первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="1016f-116">You must be connected to the server instance that hosts the current primary replica.</span></span>  
  
###  <a name="what-replica-properties-do-you-need-to-configure-to-support-read-only-routing"></a><a name="RORReplicaProperties"></a><span data-ttu-id="1016f-117">Какие свойства реплики необходимо настроить для поддержки маршрутизации только для чтения?</span><span class="sxs-lookup"><span data-stu-id="1016f-117">What Replica Properties Do you Need to Configure to Support Read-Only Routing?</span></span>  
  
-   <span data-ttu-id="1016f-118">Для каждой доступной для чтения вторичной реплики, которая поддерживает маршрутизацию только для чтения, необходимо указать *URL-адрес маршрутизации только для чтения*.</span><span class="sxs-lookup"><span data-stu-id="1016f-118">For each readable secondary replica that is to support read-only routing, you need to specify a *read-only routing URL*.</span></span> <span data-ttu-id="1016f-119">Этот URL-адрес задействуется, только если локальная реплика выполняется под вторичной ролью.</span><span class="sxs-lookup"><span data-stu-id="1016f-119">This URL takes effect only when the local replica is running under the secondary role.</span></span> <span data-ttu-id="1016f-120">URL-адрес маршрутизации только для чтения должен быть указан для каждой реплики отдельно (если для реплики требуется подобная маршрутизация).</span><span class="sxs-lookup"><span data-stu-id="1016f-120">The read-only routing URL must be specified on a replica-by-replica basis, as needed.</span></span> <span data-ttu-id="1016f-121">Все URL-адреса маршрутизации только для чтения используются для направления запросов на соединение с намерением чтения к определенной доступной для чтения вторичной реплике.</span><span class="sxs-lookup"><span data-stu-id="1016f-121">Each read-only routing URL is used for routing read-intent connection requests to a specific readable secondary replica.</span></span> <span data-ttu-id="1016f-122">Как правило, каждой доступной для чтения вторичной реплике назначается URL-адрес маршрутизации только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1016f-122">Typically, every readable secondary replica is assigned a read-only routing URL.</span></span>  
  
     <span data-ttu-id="1016f-123">Дополнительные сведения о вычислении URL-адреса маршрутизации только для чтения для реплики доступности см. в разделе [Вычисление для AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="1016f-123">For information about calculating the read-only routing URL for an availability replica, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
-   <span data-ttu-id="1016f-124">Для каждой реплики доступности, которая должна поддерживать маршрутизацию только для чтения и при этом является первичной, необходимо задать *список маршрутизации только для чтения*.</span><span class="sxs-lookup"><span data-stu-id="1016f-124">For each availability replica that you want to support read-only routing when it is the primary replica, you need to specify a *read-only routing list*.</span></span> <span data-ttu-id="1016f-125">Определенный список маршрутизации только для чтения вступает в силу, только если локальная реплика выполняется под первичной ролью.</span><span class="sxs-lookup"><span data-stu-id="1016f-125">A given read-only routing list takes effect only when the local replica is running under the primary role.</span></span> <span data-ttu-id="1016f-126">Такой список должен указываться для тех конкретных реплик, для которых он требуется.</span><span class="sxs-lookup"><span data-stu-id="1016f-126">This list must be specified on a replica-by-replica basis, as needed.</span></span> <span data-ttu-id="1016f-127">Как правило, каждый список маршрутизации только для чтения будет содержать все URL-адреса маршрутизации только для чтения, причем URL-адрес локальной реплики будет идти в конце списка.</span><span class="sxs-lookup"><span data-stu-id="1016f-127">Typically, each read-only routing list would contain every read-only routing URL, with the URL of the local replica at the end of the list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1016f-128">Запросы на соединение с намерением чтения направляются в первую имеющуюся вторичную реплику доступную для чтения из списка маршрутизации только для чтения текущей первичной реплики.</span><span class="sxs-lookup"><span data-stu-id="1016f-128">Read-intent connection requests are routed to the first available readable secondary on the read-only routing list of the current primary replica.</span></span> <span data-ttu-id="1016f-129">Балансировка нагрузки отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1016f-129">There is no load balancing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1016f-130">Сведения о прослушивателях групп доступности и дополнительные сведения о маршрутизации только для чтения см. в разделе [Прослушиватели групп доступности, возможность подключения клиентов и отработка отказа приложений (SQL Server)](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="1016f-130">For information about availability group listeners and more information about read-only routing, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1016f-131">безопасность</span><span class="sxs-lookup"><span data-stu-id="1016f-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1016f-132">Permissions</span><span class="sxs-lookup"><span data-stu-id="1016f-132">Permissions</span></span>  
  
|<span data-ttu-id="1016f-133">Задача</span><span class="sxs-lookup"><span data-stu-id="1016f-133">Task</span></span>|<span data-ttu-id="1016f-134">Разрешения</span><span class="sxs-lookup"><span data-stu-id="1016f-134">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1016f-135">Настройка реплик при создании группы доступности</span><span class="sxs-lookup"><span data-stu-id="1016f-135">To configure replicas when creating an availability group</span></span>|<span data-ttu-id="1016f-136">Требуется членство в фиксированной роли сервера **sysadmin** и одно из разрешений: CREATE AVAILABILITY GROUP, ALTER ANY AVAILABILITY GROUP или CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="1016f-136">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
|<span data-ttu-id="1016f-137">Изменение реплики доступности</span><span class="sxs-lookup"><span data-stu-id="1016f-137">To modify an availability replica</span></span>|<span data-ttu-id="1016f-138">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="1016f-138">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1016f-139">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1016f-139">Using Transact-SQL</span></span>  
 <span data-ttu-id="1016f-140">**Настройка маршрутизации только для чтения**</span><span class="sxs-lookup"><span data-stu-id="1016f-140">**To Configure read-only routing**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1016f-141">Пример кода см. в подразделе [Пример (Transact-SQL)](#TsqlExample)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1016f-141">For a code example, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="1016f-142">Подключитесь к экземпляру сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="1016f-142">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="1016f-143">Если вы указываете реплику для новой группы доступности, воспользуйтесь инструкцией [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1016f-143">If you are specifying a replica for a new availability group, use the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="1016f-144">При добавлении или изменении реплики для существующей группы доступности используйте инструкцию [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1016f-144">If you are adding or modifying a replica for an existing availability group, use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
    -   <span data-ttu-id="1016f-145">Чтобы настроить маршрутизацию только для чтения для вторичной роли, укажите в предложении ADD REPLICA или MODIFY REPLICA WITH параметр SECONDARY_ROLE следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1016f-145">To configure read-only routing for the secondary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the SECONDARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="1016f-146">SECONDARY_ROLE **(** READ_ONLY_ROUTING_URL **= '** TCP **:// *`system-address`* : *`port`* ')**</span><span class="sxs-lookup"><span data-stu-id="1016f-146">SECONDARY_ROLE **(** READ_ONLY_ROUTING_URL **='** TCP **://*`system-address`*:*`port`*')**</span></span>  
  
         <span data-ttu-id="1016f-147">Существуют следующие параметры URL-адреса маршрутизации только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1016f-147">The parameters of the read-only routing URL are as follows:</span></span>  
  
         <span data-ttu-id="1016f-148">*system-address*</span><span class="sxs-lookup"><span data-stu-id="1016f-148">*system-address*</span></span>  
         <span data-ttu-id="1016f-149">Это строка, такая как адрес системы, полное доменное имя или IP-адрес, однозначно идентифицирующий целевую компьютерную систему.</span><span class="sxs-lookup"><span data-stu-id="1016f-149">Is a string, such as a system name, a fully qualified domain name, or an IP address, that unambiguously identifies the destination computer system.</span></span>  
  
         <span data-ttu-id="1016f-150">*port*</span><span class="sxs-lookup"><span data-stu-id="1016f-150">*port*</span></span>  
         <span data-ttu-id="1016f-151">Номер порта, который используется компонентом ядра СУБД экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1016f-151">Is a port number that is used by the Database Engine of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span>  
  
         <span data-ttu-id="1016f-152">Например:   `SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433')`</span><span class="sxs-lookup"><span data-stu-id="1016f-152">For example:   `SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433')`</span></span>  
  
         <span data-ttu-id="1016f-153">В предложении MODIFY REPLICA параметр ALLOW_CONNECTIONS не является обязательным, если реплика уже настроена для соединений только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1016f-153">In a MODIFY REPLICA clause the ALLOW_CONNECTIONS is optional if the replica is already configured to allow read-only connections.</span></span>  
  
         <span data-ttu-id="1016f-154">Дополнительные сведения см. в разделе [Вычисления для AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="1016f-154">For more information, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
    -   <span data-ttu-id="1016f-155">Чтобы настроить маршрутизацию только для чтения для первичной роли, в предложении ADD REPLICA или MODIFY REPLICA WITH укажите параметр PRIMARY_ROLE следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1016f-155">To configure read-only routing for the primary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the PRIMARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="1016f-156">PRIMARY_ROLE **(** READ_ONLY_ROUTING_LIST **= (' *`server`* '** [ **,**... *n* ] **))**</span><span class="sxs-lookup"><span data-stu-id="1016f-156">PRIMARY_ROLE **(** READ_ONLY_ROUTING_LIST **=('*`server`*'** [ **,**...*n* ] **))**</span></span>  
  
         <span data-ttu-id="1016f-157">Здесь *server* идентифицирует экземпляр сервера, на котором размещена вторичная реплика только для чтения в группе доступности.</span><span class="sxs-lookup"><span data-stu-id="1016f-157">where, *server* identifies a server instance that hosts a read-only secondary replica in the availability group.</span></span>  
  
         <span data-ttu-id="1016f-158">Например:   `PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('Server1','Server2'))`</span><span class="sxs-lookup"><span data-stu-id="1016f-158">For example:   `PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('Server1','Server2'))`</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1016f-159">Необходимо настроить URL-адрес маршрутизации только для чтения перед настройкой списка маршрутизации только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1016f-159">You must set the read-only routing URL before configuring the read-only routing list.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="1016f-160">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1016f-160">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="1016f-161">В следующем примере изменяются две реплики доступности существующей группы доступности `AG1` для поддержки маршрутизации только для чтения в том случае, если одна из этих реплик в настоящий момент обладает первичной ролью.</span><span class="sxs-lookup"><span data-stu-id="1016f-161">The following example modifies two availability replicas of an existing availability group, `AG1` to support read-only routing if one of these replicas currently owns the primary role.</span></span> <span data-ttu-id="1016f-162">Чтобы определить экземпляры сервера, на которых размещена реплика доступности, в этом примере указаны имена экземпляров —`COMPUTER01` и `COMPUTER02`.</span><span class="sxs-lookup"><span data-stu-id="1016f-162">To identify the server instances that host the availability replica, this example specifies the instance names-`COMPUTER01` and `COMPUTER02`.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY));  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433'));  
  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY));  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER02.contoso.com:1433'));  
  
ALTER AVAILABILITY GROUP [AG1]   
MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('COMPUTER02','COMPUTER01')));  
  
ALTER AVAILABILITY GROUP [AG1]   
MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('COMPUTER01','COMPUTER02')));  
GO
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="1016f-163">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="1016f-163">Using PowerShell</span></span>  

### <a name="to-configure-read-only-routing"></a><span data-ttu-id="1016f-164">Настройка маршрутизации только для чтения</span><span class="sxs-lookup"><span data-stu-id="1016f-164">To Configure read-only routing</span></span>
  
> [!NOTE]  
>  <span data-ttu-id="1016f-165">Пример кода см. в подразделе [Пример (PowerShell)](#PSExample)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1016f-165">For a code example, see [Example (PowerShell)](#PSExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="1016f-166">Установите значение по умолчанию (`cd`) равным серверу экземпляра, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="1016f-166">Set default (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="1016f-167">При добавлении реплики доступности в группу доступности воспользуйтесь командлетом `New-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="1016f-167">When adding an availability replica to an availability group, use the `New-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="1016f-168">При изменении существующей реплики доступности воспользуйтесь командлетом `Set-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="1016f-168">When modifying an existing availability replica, use the `Set-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="1016f-169">Соответствующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1016f-169">The relevant parameters are as follows:</span></span>  
  
    -   <span data-ttu-id="1016f-170">Чтобы настроить маршрутизацию только для чтения для вторичной роли, укажите параметр **параметр readonlyroutingconnectionurl " *`url`* "** .</span><span class="sxs-lookup"><span data-stu-id="1016f-170">To configure read-only routing for the secondary role, specify the **ReadonlyRoutingConnectionUrl"*`url`*"** parameter.</span></span>  
  
         <span data-ttu-id="1016f-171">Здесь *url* — это полное доменное имя и порт, которые используются для маршрутизации к реплике соединений только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1016f-171">where, *url* is the connectivity fully-qualified domain name (FQDN) and port to use when routing to the replica for read-only connections.</span></span> <span data-ttu-id="1016f-172">Например: `-ReadonlyRoutingConnectionUrl "TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024"`</span><span class="sxs-lookup"><span data-stu-id="1016f-172">For example:  `-ReadonlyRoutingConnectionUrl "TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024"`</span></span>  
  
         <span data-ttu-id="1016f-173">Дополнительные сведения см. в разделе [Вычисления для AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="1016f-173">For more information, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
    -   <span data-ttu-id="1016f-174">Чтобы настроить доступ к соединению для первичной роли, укажите **ReadonlyRoutingList " *`server`* "** [ **,**... *n* ], где *Server* определяет экземпляр сервера, на котором размещена вторичная реплика только для чтения в группе доступности.</span><span class="sxs-lookup"><span data-stu-id="1016f-174">To configure connection access for the primary role, specify **ReadonlyRoutingList"*`server`*"** [ **,**...*n* ], where *server* identifies a server instance that hosts a read-only secondary replica in the availability group.</span></span> <span data-ttu-id="1016f-175">Например: `-ReadOnlyRoutingList "SecondaryServer","PrimaryServer"`</span><span class="sxs-lookup"><span data-stu-id="1016f-175">For example:  `-ReadOnlyRoutingList "SecondaryServer","PrimaryServer"`</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1016f-176">Необходимо настроить URL-адрес маршрутизации только для чтения для реплики перед тем, как перейти к настройке ее списка маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="1016f-176">You must set the read-only routing URL of a replica before configuring its read-only routing list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1016f-177">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1016f-177">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="1016f-178">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1016f-178">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="1016f-179">Чтобы настроить и использовать поставщик SQL Server PowerShell, см. статью [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md) и [Получение справки SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1016f-179">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md) and [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>
  
###  <a name="example-powershell"></a><a name="PSExample"></a> <span data-ttu-id="1016f-180">Пример (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="1016f-180">Example (PowerShell)</span></span>  
 <span data-ttu-id="1016f-181">В следующем примере выполняется настройка первичной реплики и одной вторичной реплики в группе доступности с использованием маршрутизации только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1016f-181">The following example configures the primary replica and one secondary replica in an availability group for read-only routing.</span></span> <span data-ttu-id="1016f-182">С начала примера каждой реплике присваивается URL-адрес для маршрутизации только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1016f-182">First, the example assigns a read-only routing URL to each replica.</span></span> <span data-ttu-id="1016f-183">Затем для первичной реплики задается список маршрутизации только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1016f-183">Then it sets the read-only routing list on the primary replica.</span></span> <span data-ttu-id="1016f-184">Соединения со свойством «ReadOnly» в строке подключения будут перенаправляться на вторичную реплику.</span><span class="sxs-lookup"><span data-stu-id="1016f-184">Connections with the "ReadOnly" property set in the connection string will be redirected to the secondary replica.</span></span> <span data-ttu-id="1016f-185">Если такая вторичная реплика недоступна для чтения (в соответствии со значением параметра `ConnectionModeInSecondaryRole`), соединение направляется обратно в первичную реплику.</span><span class="sxs-lookup"><span data-stu-id="1016f-185">If this secondary replica is not readable (as determined by the `ConnectionModeInSecondaryRole` setting), the connection will be directed back to the primary replica.</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\PrimaryServer\default\AvailabilityGroups\MyAg  
$primaryReplica = Get-Item "AvailabilityReplicas\PrimaryServer"  
$secondaryReplica = Get-Item "AvailabilityReplicas\SecondaryServer"  
  
Set-SqlAvailabilityReplica -ReadOnlyRoutingConnectionUrl "TCP://PrimaryServer.domain.com:1433" -InputObject $primaryReplica  
Set-SqlAvailabilityReplica -ReadOnlyRoutingConnectionUrl "TCP://SecondaryServer.domain.com:1433" -InputObject $secondaryReplica  
Set-SqlAvailabilityReplica -ReadOnlyRoutingList "SecondaryServer","PrimaryServer" -InputObject $primaryReplica  
```  
  
##  <a name="follow-up-after-configuring-read-only-routing"></a><a name="FollowUp"></a> <span data-ttu-id="1016f-186">Продолжение: после настройки маршрутизации только для чтения</span><span class="sxs-lookup"><span data-stu-id="1016f-186">Follow Up: After Configuring Read-Only Routing</span></span>  
 <span data-ttu-id="1016f-187">Как только текущая первичная реплика и предназначенные для чтения вторичные реплики будут настроены для поддержки маршрутизации только для чтения в обеих ролях, предназначенные для чтения вторичные реплики смогут принимать запросы соединения с намерением чтения от клиентов, которые подключаются через прослушиватель группы доступности.</span><span class="sxs-lookup"><span data-stu-id="1016f-187">Once the current primary replica and the readable secondary replicas are configured to support read-only routing in both roles, the readable secondary replicas can receive read read-intent connection requests from clients that connect via the availability group listener.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="1016f-188">При использовании [программы bcp](../../../tools/bcp-utility.md) или [программы sqlcmd](../../../tools/sqlcmd-utility.md)можно указать доступ только для чтения ко всем вторичным репликам, для которых разрешен доступ только для чтения, указав `-K ReadOnly` параметр.</span><span class="sxs-lookup"><span data-stu-id="1016f-188">When using the [bcp Utility](../../../tools/bcp-utility.md) or [sqlcmd Utility](../../../tools/sqlcmd-utility.md), you can specify read-only access to any secondary replica that is enabled for read-only access by specifying the `-K ReadOnly` switch.</span></span>  
  
###  <a name="requirements-and-recommendations-for-client-connection-strings"></a><a name="ConnStringReqsRecs"></a> <span data-ttu-id="1016f-189">Требования и рекомендации для строк подключения клиента</span><span class="sxs-lookup"><span data-stu-id="1016f-189">Requirements and Recommendations for Client Connection-Strings</span></span>  
 <span data-ttu-id="1016f-190">В случае если клиентское приложение использует маршрутизацию только для чтения, его строка подключения должна удовлетворять следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="1016f-190">For a client application to use read-only routing, its connection string must satisfy the following requirements:</span></span>  
  
-   <span data-ttu-id="1016f-191">Используйте протокол TCP.</span><span class="sxs-lookup"><span data-stu-id="1016f-191">Use the TCP protocol.</span></span>  
  
-   <span data-ttu-id="1016f-192">Задайте атрибут/свойство намерения приложения как «только для чтения».</span><span class="sxs-lookup"><span data-stu-id="1016f-192">Set the application intent attribute/property to readonly.</span></span>  
  
-   <span data-ttu-id="1016f-193">Создайте ссылку на прослушиватель группы доступности, настроенный для поддержки маршрутизации только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1016f-193">Reference the listener of an availability group that is configured to support read-only routing.</span></span>  
  
-   <span data-ttu-id="1016f-194">Сошлитесь на базу данных в этой группе доступности.</span><span class="sxs-lookup"><span data-stu-id="1016f-194">Reference a database in that availability group.</span></span>  
  
 <span data-ttu-id="1016f-195">Кроме того, рекомендуется, чтобы строки подключения использовали отработку отказа резервных подсетей при сбое, что поддерживает параллельный клиентский поток для каждой реплики в каждой подсети.</span><span class="sxs-lookup"><span data-stu-id="1016f-195">In addition, we recommend that connection strings enable multi-subnet failover, which supports a parallel client thread for each replica on each subnet.</span></span> <span data-ttu-id="1016f-196">Это позволяет свести к минимуму повторное подключение клиента после отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="1016f-196">This minimizes client reconnection time after a failover.</span></span>  
  
 <span data-ttu-id="1016f-197">Синтаксис строки подключения зависит от поставщика SQL Server, который использует приложение.</span><span class="sxs-lookup"><span data-stu-id="1016f-197">The syntax for a connection string depends on the SQL Server provider an application is using.</span></span> <span data-ttu-id="1016f-198">Следующий пример строки подключения для поставщика данных .NET Framework 4.0.2 для SQL Server демонстрирует фрагменты строки подключения, которые необходимы и рекомендуются для работы с маршрутизацией только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1016f-198">The following example connection string for the .NET Framework Data Provider 4.0.2 for SQL Server illustrates the parts of a connection string that are required and recommended to work for read-only routing.</span></span>  
  
```  
Server=tcp:MyAgListener,1433;Database=Db1;IntegratedSecurity=SSPI;ApplicationIntent=ReadOnly;MultiSubnetFailover=True  
```  
  
 <span data-ttu-id="1016f-199">Дополнительные сведения о намерении приложения и маршрутизации только для чтения см. в разделе [Прослушиватели групп доступности, возможность подключения клиентов и отработка отказа приложений (SQL Server)](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="1016f-199">For more information about read-only application intent and read-only routing, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
### <a name="if-read-only-routing-is-not-working-correctly"></a><span data-ttu-id="1016f-200">Маршрутизация только для чтения работает неправильно</span><span class="sxs-lookup"><span data-stu-id="1016f-200">If Read-Only Routing is Not Working Correctly</span></span>  
 <span data-ttu-id="1016f-201">Дополнительные сведения об устранении неполадок с конфигурацией маршрутизации только для чтения см. в разделе [Маршрутизация только для чтения работает неправильно](troubleshoot-always-on-availability-groups-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1016f-201">For information about troubleshooting a read-only routing configuration, see [Read-Only Routing is Not Working Correctly](troubleshoot-always-on-availability-groups-configuration-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1016f-202">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="1016f-202">Related Tasks</span></span>  

### <a name="to-view-read-only-routing-configurations"></a><span data-ttu-id="1016f-203">Просмотр конфигурации маршрутизации только для чтения</span><span class="sxs-lookup"><span data-stu-id="1016f-203">To view read-only routing configurations</span></span>
  
-   [<span data-ttu-id="1016f-204">sys.availability_read_only_routing_lists (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1016f-204">sys.availability_read_only_routing_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-read-only-routing-lists-transact-sql)  
  
-   <span data-ttu-id="1016f-205">[sys.availability_replicas (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) (столбец **read_only_routing_url**)</span><span class="sxs-lookup"><span data-stu-id="1016f-205">[sys.availability_replicas &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) (**read_only_routing_url** column)</span></span>  
  
### <a name="to-configure-client-connection-access"></a><span data-ttu-id="1016f-206">Настройка доступа соединения клиентов</span><span class="sxs-lookup"><span data-stu-id="1016f-206">To configure client connection access</span></span>
  
-   [<span data-ttu-id="1016f-207">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1016f-207">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="1016f-208">Настройка доступа только для чтения в реплике доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1016f-208">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
### <a name="to-use-connection-strings-in-applications"></a><span data-ttu-id="1016f-209">Использование строк подключения в приложениях</span><span class="sxs-lookup"><span data-stu-id="1016f-209">To use connection strings in applications</span></span>
  
-   [<span data-ttu-id="1016f-210">Поддержка высокого уровня доступности и аварийного восстановления собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="1016f-210">SQL Server Native Client Support for High Availability, Disaster Recovery</span></span>](../../../relational-databases/native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md)  
  
-   [<span data-ttu-id="1016f-211">Использование ключевых слов строки подключения с собственным клиентом SQL Server</span><span class="sxs-lookup"><span data-stu-id="1016f-211">Using Connection String Keywords with SQL Server Native Client</span></span>](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="1016f-212">См. также</span><span class="sxs-lookup"><span data-stu-id="1016f-212">Related Content</span></span>  
  
-   <span data-ttu-id="1016f-213">**Блоги**</span><span class="sxs-lookup"><span data-stu-id="1016f-213">**Blogs:**</span></span>  
  
     [<span data-ttu-id="1016f-214">Вычисление для AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="1016f-214">Calculating read_only_routing_url for AlwaysOn</span></span>](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson)  
  
     [<span data-ttu-id="1016f-215">Блоги команды разработчиков SQL Server AlwaysOn: официальный блог по SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="1016f-215">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="1016f-216">Блоги инженеров CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="1016f-216">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="1016f-217">**Технические документы:**</span><span class="sxs-lookup"><span data-stu-id="1016f-217">**White papers:**</span></span>  
  
     [<span data-ttu-id="1016f-218">Технические документы Майкрософт Microsoft по SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="1016f-218">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="1016f-219">Технические документы группы консультантов по SQL Server</span><span class="sxs-lookup"><span data-stu-id="1016f-219">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="1016f-220">См. также:</span><span class="sxs-lookup"><span data-stu-id="1016f-220">See Also</span></span>  
 <span data-ttu-id="1016f-221">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1016f-221">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="1016f-222">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1016f-222">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="1016f-223">[Активные базы данных-получатели: вторичные реплики для чтения (группы доступности AlwaysOn)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="1016f-223">[Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span></span>  
 <span data-ttu-id="1016f-224">[Сведения о доступе клиентского подключения к репликам доступности (SQL Server)](about-client-connection-access-to-availability-replicas-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1016f-224">[About Client Connection Access to Availability Replicas &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) </span></span>  
 [<span data-ttu-id="1016f-225">Прослушиватели групп доступности, возможность подключения клиентов и отработка отказа приложений (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1016f-225">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)  
