---
title: Service Broker с группы доступности AlwaysOn (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 881c20e5-1c99-44eb-b393-09fc5ea0f122
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da179219363422c4ec242d29be61f35dd1609823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664503"
---
# <a name="service-broker-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="9bcb0-102">Компонент Service Broker с группами доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9bcb0-102">Service Broker with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="9bcb0-103">В этом разделе содержатся сведения о настройке компонента Service Broker для работы с [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9bcb0-103">This topic contains information about configuring Service Broker to work with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="9bcb0-104">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="9bcb0-104">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="9bcb0-105">Требования к службе в группе доступности для получения удаленных сообщений</span><span class="sxs-lookup"><span data-stu-id="9bcb0-105">Requirements for a Service in an Availability Group to Receive Remote Messages</span></span>](#ReceiveRemoteMessages)  
  
-   [<span data-ttu-id="9bcb0-106">Требования к отправке сообщений в удаленную службу в группе доступности</span><span class="sxs-lookup"><span data-stu-id="9bcb0-106">Requirements for Sending Messages to a Remote Service in an Availability Group</span></span>](#SendRemoteMessages)  
  
##  <a name="requirements-for-a-service-in-an-availability-group-to-receive-remote-messages"></a><a name="ReceiveRemoteMessages"></a> <span data-ttu-id="9bcb0-107">Требования к службе в группе доступности для получения удаленных сообщений</span><span class="sxs-lookup"><span data-stu-id="9bcb0-107">Requirements for a Service in an Availability Group to Receive Remote Messages</span></span>  
  
1.  <span data-ttu-id="9bcb0-108">**Убедитесь, что группа доступности имеет прослушиватель.**</span><span class="sxs-lookup"><span data-stu-id="9bcb0-108">**Ensure that the availability group possesses a listener.**</span></span>  
  
     <span data-ttu-id="9bcb0-109">Дополнительные сведения см. в разделе [Создание или настройка прослушивателя группы доступности (SQL Server)](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9bcb0-109">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="9bcb0-110">**Убедитесь, что конечная точка компонента Service Broker существует и правильно настроена.**</span><span class="sxs-lookup"><span data-stu-id="9bcb0-110">**Ensure that the Service Broker endpoint exists and is correctly configured.**</span></span>  
  
     <span data-ttu-id="9bcb0-111">В каждом экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , где размещается реплика доступности для группы доступности, настройте конечную точку компонента Service Broker следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-111">On every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica for the availability group, configure the Service Broker endpoint, as follows:</span></span>  
  
    -   <span data-ttu-id="9bcb0-112">Установите параметр LISTENER_IP в значение ALL.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-112">Set LISTENER_IP to 'ALL'.</span></span> <span data-ttu-id="9bcb0-113">Этот параметр разрешает соединения по любому допустимому IP-адресу, привязанному к прослушивателю группы доступности.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-113">This setting enables connections on any valid IP address that is bound to the availability group listener.</span></span>  
  
    -   <span data-ttu-id="9bcb0-114">Установите в параметре PORT компонента Service Broker одинаковый номер порта во всех экземплярах сервера.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-114">Set the Service Broker PORT to the same port number on all the host server instances.</span></span>  
  
        > [!TIP]  
        >  <span data-ttu-id="9bcb0-115">Чтобы просмотреть номер порта конечной точки компонента Service Broker в заданном экземпляре сервера, запросите столбец **port** представления каталога [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) , где **type_desc** = 'SERVICE_BROKER'.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-115">To view the port number of the Service Broker endpoint on a given server instance, query the **port** column of the [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) catalog view, where **type_desc** = 'SERVICE_BROKER'.</span></span>  
  
     <span data-ttu-id="9bcb0-116">В следующем примере создается конечная точка компонента Service Broker с проверкой подлинности Windows, которая использует порт компонента Service Broker по умолчанию (4022) и прослушивает все допустимые IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-116">The following example creates a Windows authenticated Service Broker endpoint that uses the default Service Broker port (4022) and listens to all valid IP addresses.</span></span>  
  
    ```  
    CREATE ENDPOINT [SSBEndpoint]  
        STATE = STARTED  
        AS TCP  (LISTENER_PORT = 4022, LISTENER_IP = ALL )  
        FOR SERVICE_BROKER (AUTHENTICATION = WINDOWS)  
    ```  
  
     <span data-ttu-id="9bcb0-117">Дополнительные сведения см. в разделе [CREATE ENDPOINT (Transact-SQL)](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9bcb0-117">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
3.  <span data-ttu-id="9bcb0-118">**Предоставьте разрешение CONNECT на конечную точку.**</span><span class="sxs-lookup"><span data-stu-id="9bcb0-118">**Grant CONNECT permission on the endpoint.**</span></span>  
  
     <span data-ttu-id="9bcb0-119">Предоставьте разрешение CONNECT на конечную точку компонента Service Broker роли PUBLIC или некоторому имени входа.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-119">Grant CONNECT permission on the Service Broker endpoint either to PUBLIC or to a login.</span></span>  
  
     <span data-ttu-id="9bcb0-120">В следующем примере разрешение на подключение к конечной точке компонента Service Broker с именем `broker_endpoint` предоставляется роли PUBLIC.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-120">The following example grants the connection on a Service Broker endpoint named `broker_endpoint` to PUBLIC.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[broker_endpoint] TO [PUBLIC]  
    ```  
  
     <span data-ttu-id="9bcb0-121">Дополнительные сведения см. в статье [GRANT (Transact-SQL)](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9bcb0-121">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span>  
  
4.  <span data-ttu-id="9bcb0-122">**Убедитесь, что база данных msdb содержит маршрут AutoCreatedLocal или маршрут к некоторой службе.**</span><span class="sxs-lookup"><span data-stu-id="9bcb0-122">**Ensure that msdb contains either an AutoCreatedLocal route or a route to the specific service.**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9bcb0-123">По умолчанию все пользовательские базы данных, включая **msdb**, содержат маршрут **AutoCreatedLocal**.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-123">By default, each user database, including **msdb**, contains the route **AutoCreatedLocal**.</span></span> <span data-ttu-id="9bcb0-124">Он соответствует имени любой службы и любому экземпляру компонента Service Broker и указывает, что сообщение должно быть доставлено внутри текущего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-124">This route matches any service name and broker instance and specifies that the message should be delivered within the current instance.</span></span> <span data-ttu-id="9bcb0-125">Маршрут**AutoCreatedLocal** имеет более низкий приоритет, чем маршруты, в которых явно указывается служба, обменивающаяся данными с удаленным экземпляром.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-125">**AutoCreatedLocal** has lower priority than routes that explicitly specify a specific service that communicates with a remote instance.</span></span>  
  
     <span data-ttu-id="9bcb0-126">Сведения о создании маршрутов см. в статьях [Примеры маршрутизации для компонента Service Broker](https://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) (версия [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] электронной документации) и [CREATE ROUTE (Transact-SQL)](/sql/t-sql/statements/create-route-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9bcb0-126">For information about creating routes, see [Service Broker Routing Examples](https://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) (in the [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] version of Books Online) and [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span></span>  
  
##  <a name="requirements-for-sending-messages-to-a-remote-service-in-an-availability-group"></a><a name="SendRemoteMessages"></a> <span data-ttu-id="9bcb0-127">Требования к отправке сообщений удаленной службе в группе доступности</span><span class="sxs-lookup"><span data-stu-id="9bcb0-127">Requirements for Sending Messages to a Remote Service in an Availability Group</span></span>  
  
1.  <span data-ttu-id="9bcb0-128">**Создайте маршрут к целевой службе.**</span><span class="sxs-lookup"><span data-stu-id="9bcb0-128">**Create a route to the target service.**</span></span>  
  
     <span data-ttu-id="9bcb0-129">Настройте маршрут следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-129">Configure the route as follows:</span></span>  
  
    -   <span data-ttu-id="9bcb0-130">Задайте в параметре ADDRESS IP-адрес прослушивателя группы доступности, в которой размещается база данных службы.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-130">Set ADDRESS to the listener IP address of availability group that hosts the service database.</span></span>  
  
    -   <span data-ttu-id="9bcb0-131">Задайте в параметре PORT порт, указанный в конечной точке компонента Service Broker в каждом из удаленных экземпляров SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-131">Set PORT to the port that you specified in the Service Broker endpoint of each of the remote SQL Server instances.</span></span>  
  
     <span data-ttu-id="9bcb0-132">В следующем примере создается маршрут с именем `RouteToTargetService` для службы `ISBNLookupRequestService` .</span><span class="sxs-lookup"><span data-stu-id="9bcb0-132">The following example creates a route named `RouteToTargetService` for the `ISBNLookupRequestService` service.</span></span> <span data-ttu-id="9bcb0-133">Маршрут ведет к прослушивателю группы доступности `MyAgListener`, который использует порт 4022.</span><span class="sxs-lookup"><span data-stu-id="9bcb0-133">The route targets the availability group listener, `MyAgListener`, which uses port 4022.</span></span>  
  
    ```  
    CREATE ROUTE [RouteToTargetService] WITH   
    SERVICE_NAME = 'ISBNLookupRequestService',   
    ADDRESS = 'TCP://MyAgListener:4022';  
  
    ```  
  
     <span data-ttu-id="9bcb0-134">Дополнительные сведения см. в статье [CREATE ROUTE (Transact-SQL)](/sql/t-sql/statements/create-route-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9bcb0-134">For more information, see [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span></span>  
  
2.  <span data-ttu-id="9bcb0-135">**Убедитесь, что база данных msdb содержит маршрут AutoCreatedLocal или маршрут к некоторой службе.**</span><span class="sxs-lookup"><span data-stu-id="9bcb0-135">**Ensure that msdb contains either an AutoCreatedLocal route or a route to the specific service.**</span></span> <span data-ttu-id="9bcb0-136">(Дополнительные сведения см. в подразделе [Требования к службе в группе доступности для получения удаленных сообщений](#ReceiveRemoteMessages)выше.)</span><span class="sxs-lookup"><span data-stu-id="9bcb0-136">(For more information, see [Requirements for a Service in an Availability Group to Receive Remote Messages](#ReceiveRemoteMessages), earlier in this topic.)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9bcb0-137">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9bcb0-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9bcb0-138">CREATE ENDPOINT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9bcb0-138">CREATE ENDPOINT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-endpoint-transact-sql)  
  
-   [<span data-ttu-id="9bcb0-139">CREATE ROUTE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9bcb0-139">CREATE ROUTE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-route-transact-sql)  
  
-   [<span data-ttu-id="9bcb0-140">GRANT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9bcb0-140">GRANT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/grant-transact-sql)  
  
-   <span data-ttu-id="9bcb0-141">[Создание или настройка прослушивателя группы доступности (SQL Server)](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9bcb0-141">[Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="9bcb0-142">Создание и настройка групп доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9bcb0-142">Creation and Configuration of Availability Groups &#40;SQL Server&#41;</span></span>](creation-and-configuration-of-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="9bcb0-143">Настройка учетных записей входа для зеркального отображения базы данных или группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9bcb0-143">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../../database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
## <a name="see-also"></a><span data-ttu-id="9bcb0-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="9bcb0-144">See Also</span></span>  
 <span data-ttu-id="9bcb0-145">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9bcb0-145">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="9bcb0-146">[Прослушиватели групп доступности, возможность подключения клиентов и отработка отказа приложений (SQL Server)](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="9bcb0-146">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="9bcb0-147">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="9bcb0-147">SQL Server Service Broker</span></span>](../../configure-windows/sql-server-service-broker.md)  
  
  
