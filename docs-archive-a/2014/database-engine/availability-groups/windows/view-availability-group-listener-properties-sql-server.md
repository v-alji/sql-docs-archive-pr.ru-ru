---
title: Просмотр свойств прослушивателя группы доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 07/11/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygrouplistenerproperties.general.f1
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
ms.assetid: aca0d016-3228-40b8-bdc3-285ed6d9b280
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef7fe316394a030350ceb12a0d1b8e2d48ee1d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655369"
---
# <a name="view-availability-group-listener-properties-sql-server"></a><span data-ttu-id="6cf4c-102">Просмотр свойств прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6cf4c-102">View Availability Group Listener Properties (SQL Server)</span></span>
  <span data-ttu-id="6cf4c-103">В этом разделе описывается просмотр свойств *прослушивателя группы доступности* AlwaysOn при помощи среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cf4c-103">This topic describes how to view the properties of an AlwaysOn *availability group listener* by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="6cf4c-104">**Просмотр свойств прослушивателя с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="6cf4c-104">**To view listener properties, using:**</span></span>  
  
     [<span data-ttu-id="6cf4c-105">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6cf4c-105">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6cf4c-106">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6cf4c-106">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6cf4c-107">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6cf4c-107">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6cf4c-108">**Просмотр свойств прослушивателя**</span><span class="sxs-lookup"><span data-stu-id="6cf4c-108">**To view listener properties**</span></span>  
  
1.  <span data-ttu-id="6cf4c-109">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена любая реплика группы доступности, свойства прослушивателя которой необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-109">In Object Explorer, connect to a server instance that hosts any availability replica of the availability group whose listener you want to view.</span></span> <span data-ttu-id="6cf4c-110">Щелкните имя сервера, чтобы развернуть дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-110">Click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="6cf4c-111">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="6cf4c-111">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="6cf4c-112">Разверните узел группы доступности и разверните узел **Прослушиватели группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="6cf4c-112">Expand the node of the availability group, and expand the **Availability Groups Listeners** node.</span></span>  
  
4.  <span data-ttu-id="6cf4c-113">Щелкните правой кнопкой мыши прослушиватель, свойства которого необходимо просмотреть, и выберите пункт **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="6cf4c-113">Right-click the listener that you want to view, and select the **Properties** command.</span></span>  
  
5.  <span data-ttu-id="6cf4c-114">Откроется диалоговое окно **Свойства прослушивателя группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="6cf4c-114">This opens the **Availability Group Listener Properties** dialog box.</span></span> <span data-ttu-id="6cf4c-115">Дополнительные сведения см. в подразделе [Свойства прослушивателя группы доступности (диалоговое окно)](#AgListenerPropertiesDialog)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-115">For more information, see [Availability Group Listener Properties (Dialog Box)](#AgListenerPropertiesDialog), later in this topic.</span></span>  
  
###  <a name="availability-group-listener-properties-dialog-box"></a><a name="AgListenerPropertiesDialog"></a> <span data-ttu-id="6cf4c-116">Свойства прослушивателя группы доступности (диалоговое окно)</span><span class="sxs-lookup"><span data-stu-id="6cf4c-116">Availability Group Listener Properties (Dialog Box)</span></span>  
 <span data-ttu-id="6cf4c-117">**DNS-имя прослушивателя**</span><span class="sxs-lookup"><span data-stu-id="6cf4c-117">**Listener DNS Name**</span></span>  
 <span data-ttu-id="6cf4c-118">Сетевое имя прослушивателя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-118">The network name of the availability group listener.</span></span>  
  
 <span data-ttu-id="6cf4c-119">**порт**.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-119">**Port**</span></span>  
 <span data-ttu-id="6cf4c-120">TPC-порт, используемый этим прослушивателем.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-120">The TCP port used by this listener.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cf4c-121">Если вы подключены к основной реплике, можно использовать это поле для изменения номера порта прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-121">If you are connected the primary replica, you can use this field to modify the port number of the listener.</span></span> <span data-ttu-id="6cf4c-122">Для этого необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-122">This requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
 <span data-ttu-id="6cf4c-123">**Сетевой режим**</span><span class="sxs-lookup"><span data-stu-id="6cf4c-123">**Network Mode**</span></span>  
 <span data-ttu-id="6cf4c-124">Указывает TCP-протокол, используемый прослушивателем, один из:</span><span class="sxs-lookup"><span data-stu-id="6cf4c-124">Indicates the TCP protocol used by the listener, one of:</span></span>  
  
 <span data-ttu-id="6cf4c-125">**DHCP**</span><span class="sxs-lookup"><span data-stu-id="6cf4c-125">**DHCP**</span></span>  
 <span data-ttu-id="6cf4c-126">Прослушиватель использует динамический IP-адрес, назначенный сервером, на котором запущен протокол DHCP.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-126">The listener uses an dynamic IP address that is assigned by a server running the Dynamic Host Configuration Protocol (DHCP).</span></span>  
  
 <span data-ttu-id="6cf4c-127">**Статический IP-адрес**</span><span class="sxs-lookup"><span data-stu-id="6cf4c-127">**Static IP**</span></span>  
 <span data-ttu-id="6cf4c-128">Прослушиватель использует один или несколько статических IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-128">The listener uses one or more Static IP addresses.</span></span> <span data-ttu-id="6cf4c-129">Для доступа к разным подсетям прослушивателю группы доступности необходимо использовать статический IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-129">To access the different subnets, an availability group listener must use static IP addresses.</span></span>  
  
 <span data-ttu-id="6cf4c-130">В сетке отображается каждая из подсетей, в которых работает прослушиватель и IP-адрес, связанный с данной подсетью.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-130">The grid displays each of the subnets on which the listener listens and the IP address associated with that subnet.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6cf4c-131">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6cf4c-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="6cf4c-132">**Просмотр свойств прослушивателя**</span><span class="sxs-lookup"><span data-stu-id="6cf4c-132">**To view listener properties**</span></span>  
  
 <span data-ttu-id="6cf4c-133">Для мониторинга прослушивателей группы доступности используйте следующие представления.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-133">To monitor the availability group listeners, use the following views:</span></span>  
  
 [<span data-ttu-id="6cf4c-134">sys.availability_group_listener_ip_addresses</span><span class="sxs-lookup"><span data-stu-id="6cf4c-134">sys.availability_group_listener_ip_addresses</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-group-listener-ip-addresses-transact-sql)  
 <span data-ttu-id="6cf4c-135">Возвращает строку для каждого совместимого виртуального IP-адреса, который в настоящее время включен для прослушивателя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-135">Returns a row for every conformant virtual IP address that is currently online for an availability group listener.</span></span>  
  
 <span data-ttu-id="6cf4c-136">**Имена столбцов:** listener_id, IP-адрес, ip_subnet_mask, is_dhcp, network_subnet_ip, network_subnet_prefix_length, network_subnet_ipv4_mask, state, state_desc</span><span class="sxs-lookup"><span data-stu-id="6cf4c-136">**Column names:** listener_id, ip_address, ip_subnet_mask, is_dhcp, network_subnet_ip, network_subnet_prefix_length, network_subnet_ipv4_mask, state, state_desc</span></span>  
  
 [<span data-ttu-id="6cf4c-137">sys.availability_group_listeners</span><span class="sxs-lookup"><span data-stu-id="6cf4c-137">sys.availability_group_listeners</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-group-listeners-transact-sql)  
 <span data-ttu-id="6cf4c-138">Для любой выбранной группы доступности возвращает либо ноль строк, указывая, что с группой доступности не связано ни одного сетевого имени, либо отдельную строку для каждой конфигурации прослушивателя группы доступности в кластере WSFC.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-138">For a given availability group, returns either zero rows indicating that no network name is associated with the availability group, or returns a row for each availability-group listener configuration in the WSFC cluster.</span></span>  
  
 <span data-ttu-id="6cf4c-139">**Имена столбцов:** group_id, listener_id, dns_name, порт, is_conformant, ip_configuration_string_from_cluster</span><span class="sxs-lookup"><span data-stu-id="6cf4c-139">**Column names:** group_id, listener_id, dns_name, port, is_conformant, ip_configuration_string_from_cluster</span></span>  
  
 [<span data-ttu-id="6cf4c-140">sys.dm_tcp_listener_states</span><span class="sxs-lookup"><span data-stu-id="6cf4c-140">sys.dm_tcp_listener_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-tcp-listener-states-transact-sql)  
 <span data-ttu-id="6cf4c-141">Возвращает строку, содержащую сведения о динамическом состоянии для каждого прослушивателя TCP.</span><span class="sxs-lookup"><span data-stu-id="6cf4c-141">Returns a row containing dynamic-state information for each TCP listener.</span></span>  
  
 <span data-ttu-id="6cf4c-142">**Имена столбцов:** listener_id, ip_address, is_ipv4, port, type, type_desc, state, state_desc, start_time</span><span class="sxs-lookup"><span data-stu-id="6cf4c-142">**Column names:** listener_id, ip_address, is_ipv4, port, type, type_desc, state, state_desc, start_time</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cf4c-143">Дополнительные сведения об использовании [!INCLUDE[tsql](../../../includes/tsql-md.md)] для отслеживания среды [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] см. в разделе [Отслеживание групп доступности (Transact-SQL)](monitor-availability-groups-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6cf4c-143">For more information about using [!INCLUDE[tsql](../../../includes/tsql-md.md)] to monitor your [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] environment, see [Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6cf4c-144">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="6cf4c-144">Related Tasks</span></span>  
  
-   [<span data-ttu-id="6cf4c-145">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6cf4c-145">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="6cf4c-146">Удаление прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6cf4c-146">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="6cf4c-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="6cf4c-147">See Also</span></span>  
 <span data-ttu-id="6cf4c-148">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6cf4c-148">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="6cf4c-149">[Прослушиватели групп доступности, возможность подключения клиентов и отработка отказа приложений (SQL Server)](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="6cf4c-149">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="6cf4c-150">Отслеживание групп доступности (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6cf4c-150">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
  
