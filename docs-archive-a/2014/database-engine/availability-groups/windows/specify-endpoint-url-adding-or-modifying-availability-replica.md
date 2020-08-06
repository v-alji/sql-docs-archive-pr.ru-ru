---
title: Укажите URL-адрес конечной точки при добавлении или изменении реплики доступности (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- endpoints [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], endpoint
- Endpoint URLs (HADR)
ms.assetid: d7520c13-a8ee-4ddc-9e9a-54cd3d27ef1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da1eb2bacd4d5a2f7d0b2a623343f62b5e89597d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750196"
---
# <a name="specify-the-endpoint-url-when-adding-or-modifying-an-availability-replica-sql-server"></a><span data-ttu-id="9c7ad-102">Укажите URL-адрес конечной точки при добавлении или изменении реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9c7ad-102">Specify the Endpoint URL When Adding or Modifying an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="9c7ad-103">Для размещения реплики доступности для группы доступности экземпляр сервера должен иметь конечную точку зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-103">To host an availability replica for an availability group, a server instance must possess a database mirroring endpoint.</span></span> <span data-ttu-id="9c7ad-104">Экземпляр сервера использует эту конечную точку для прослушивания сообщений [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , получаемых от реплик доступности, размещенных на других экземплярах сервера.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-104">The server instance uses this endpoint to listen for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] messages from availability replicas hosted by other server instances.</span></span> <span data-ttu-id="9c7ad-105">Чтобы определить реплику доступности для группы доступности, необходимо задать URL-адрес конечной точки экземпляра сервера, на котором размещена реплика.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-105">To define an availability replica for an availability group, you must specify the endpoint URL of the server instance that will host the replica.</span></span> <span data-ttu-id="9c7ad-106">*URL-адрес конечной точки* определяет транспортный протокол конечной точки зеркального отображения базы данных — TCP, системный адрес экземпляра сервера и номер порта, связанный с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-106">The *endpoint URL* identifies the transport protocol of the database mirroring endpoint-TCP, the system address of the server instance, and the port number associated with the endpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c7ad-107">Термин «URL-адрес конечной точки» является синонимом термина «сетевой адрес сервера», используемого в интерфейсе и документации по зеркальному отображению баз данных.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-107">The term "endpoint URL" is synonymous with the term "server network address" used by the database mirroring user interface and documentation.</span></span>  
  
-   [<span data-ttu-id="9c7ad-108">Синтаксис для URL-адреса конечной точки</span><span class="sxs-lookup"><span data-stu-id="9c7ad-108">Syntax for an Endpoint URL</span></span>](#SyntaxOfURL)  
  
-   [<span data-ttu-id="9c7ad-109">Поиск полного доменного имени системы</span><span class="sxs-lookup"><span data-stu-id="9c7ad-109">Finding the Fully Qualified Domain Name of A System</span></span>](#Finding_FQDN)  
  
-   [<span data-ttu-id="9c7ad-110">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9c7ad-110">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="9c7ad-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9c7ad-111">Related Content</span></span>](#RelatedContent)  
  
##  <a name="syntax-for-an-endpoint-url"></a><a name="SyntaxOfURL"></a> <span data-ttu-id="9c7ad-112">Синтаксис для URL-адреса конечной точки</span><span class="sxs-lookup"><span data-stu-id="9c7ad-112">Syntax for an Endpoint URL</span></span>  
 <span data-ttu-id="9c7ad-113">Синтаксис URL-адреса конечной точки имеет следующую форму:</span><span class="sxs-lookup"><span data-stu-id="9c7ad-113">The syntax for an endpoint URL is of the form:</span></span>  
  
 <span data-ttu-id="9c7ad-114">TCP<strong>://</strong> *\<system-address>* <strong>:</strong> *\<port>* ,</span><span class="sxs-lookup"><span data-stu-id="9c7ad-114">TCP<strong>://</strong>*\<system-address>*<strong>:</strong>*\<port>*</span></span>  
  
 <span data-ttu-id="9c7ad-115">где</span><span class="sxs-lookup"><span data-stu-id="9c7ad-115">where</span></span>  
  
-   <span data-ttu-id="9c7ad-116">*\<system-address>*  — строка, однозначно определяющая целевой компьютер.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-116">*\<system-address>* is a string that unambiguously identifies the target computer system.</span></span> <span data-ttu-id="9c7ad-117">Обычно сетевой адрес представляет собой системное имя (если компьютеры входят в один домен), полное доменное имя или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-117">Typically, the server address is a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address:</span></span>  
  
    -   <span data-ttu-id="9c7ad-118">Поскольку узлы отказоустойчивой кластеризации Windows Server (WSFC) входят в один домен, можно использовать имя компьютера, например `SYSTEM46`.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-118">Because the nodes of Windows Server Failover Clustering (WSFC) cluster are the same domain, you can use the name of the computer system; for example, `SYSTEM46`.</span></span>  
  
    -   <span data-ttu-id="9c7ad-119">Если указывается IP-адрес, то он должен быть уникальным в используемой среде.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-119">To use an IP address, it must be unique in your environment.</span></span> <span data-ttu-id="9c7ad-120">Рекомендуется использовать IP-адрес только в том случае, если он является статическим.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-120">We recommend that you use an IP address only if it is static.</span></span> <span data-ttu-id="9c7ad-121">IP-адреса бывают версии 4 (IPv4) или 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="9c7ad-121">The IP address can be IP Version 4 (IPv4) or IP Version 6 (IPv6).</span></span> <span data-ttu-id="9c7ad-122">Адреса IPv6 следует заключать в квадратные скобки, например: **[** _<адрес_IPv6>_ **]** .</span><span class="sxs-lookup"><span data-stu-id="9c7ad-122">An IPv6 address must be enclosed within square brackets, for example: **[**_<IPv6_address>_**]**.</span></span>  
  
         <span data-ttu-id="9c7ad-123">Чтобы определить IP-адрес системы, в командной строке Windows введите команду **ipconfig** .</span><span class="sxs-lookup"><span data-stu-id="9c7ad-123">To learn the IP address of a system, at the Windows command prompt, enter the **ipconfig** command.</span></span>  
  
    -   <span data-ttu-id="9c7ad-124">При указании полного доменного имени гарантируется правильная работа.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-124">The fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="9c7ad-125">Это локально определенная строка адреса, которая имеет различную форму в разных местах.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-125">This is a locally defined address string that takes different forms in different places.</span></span> <span data-ttu-id="9c7ad-126">Часто, но не всегда полное доменное имя представляет собой составное имя, состоящее из имени компьютера и нескольких компонентов доменов, разделенных точками, в следующем виде:</span><span class="sxs-lookup"><span data-stu-id="9c7ad-126">Often, but not always, a fully qualified domain name is a compound name that includes the computer name and a series of period-separated domain segments of the form:</span></span>  
  
         <span data-ttu-id="9c7ad-127">_имя_компьютера_ **.**</span><span class="sxs-lookup"><span data-stu-id="9c7ad-127">_computer_name_ **.**</span></span> <span data-ttu-id="9c7ad-128">_компонент_домена_[... **.** _компонент_домена_]</span><span class="sxs-lookup"><span data-stu-id="9c7ad-128">_domain_segment_[...**.**_domain_segment_]</span></span>  
  
         <span data-ttu-id="9c7ad-129">где *имя_компьютера*— сетевое имя компьютера, на котором запущен экземпляр сервера, а *сегмент_домена*[... **.** _сегмент_домена_] — остальные сведения о домене для сервера, например `localinfo.corp.Adventure-Works.com`.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-129">where *computer_name i*s the network name of the computer running the server instance, and *domain_segment*[...**.**_domain_segment_] is the remaining domain information of the server; for example: `localinfo.corp.Adventure-Works.com`.</span></span>  
  
         <span data-ttu-id="9c7ad-130">Содержание и количество доменных сегментов определяется компанией или организацией.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-130">The content and number of domain segments are determined within the company or organization.</span></span> <span data-ttu-id="9c7ad-131">Дополнительные сведения см. в подразделе [Определение полного доменного имени](#Finding_FQDN)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-131">For more information, see [Finding the Fully Qualified Domain Name](#Finding_FQDN), later in this topic.</span></span>  
  
-   <span data-ttu-id="9c7ad-132">*\<port>*  — порт, используемый конечной точкой зеркального отображения экземпляра сервера-участника.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-132">*\<port>* is the port number used by the mirroring endpoint of the partner server instance.</span></span>  
  
     <span data-ttu-id="9c7ad-133">Конечная точка зеркального отображения базы данных может использовать любой доступный порт.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-133">A database mirroring endpoint can use any available port on the computer system.</span></span> <span data-ttu-id="9c7ad-134">Номер каждого порта должен быть связан только с одной конечной точкой, а каждая конечная точка должна быть связана только с одним экземпляром сервера; таким образом, разные экземпляры сервера на одном и том же сервере прослушивают различные конечные точки через различные порты.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-134">Each port number must be associated with only one endpoint, and each endpoint is associated with a single server instance; thus, different server instances on the same server listen on different endpoints with different ports.</span></span> <span data-ttu-id="9c7ad-135">Поэтому порт, указанный в URL-адресе конечной точки при задании реплики доступности, будет всегда направлять входящие сообщения к экземпляру сервера, конечная точка которого связана с этим портом.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-135">Therefore, the port you specify in the endpoint URL when you specify an availability replica will always direct incoming messages to the server instance whose endpoint is associated with that port.</span></span>  
  
     <span data-ttu-id="9c7ad-136">В URL-адресе конечной точки только номер порта определяет экземпляр сервера, связанный с конечной точкой зеркального отображения на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-136">IIn the endpoint URL, only the number of the port identifies the server instance that is associated with the mirroring endpoint on the target computer.</span></span> <span data-ttu-id="9c7ad-137">На следующем рисунке показаны URL-адреса конечных точек двух экземпляров серверов, размещенных на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-137">The following figure illustrates the endpoint URLs of two server instances on a single computer.</span></span> <span data-ttu-id="9c7ad-138">Экземпляр по умолчанию использует порт `7022` , именованный экземпляр — порт `7033`.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-138">The default instance uses port `7022` and the named instance uses port `7033`.</span></span> <span data-ttu-id="9c7ad-139">URL-адрес конечной точки для этих двух экземпляров сервера будет соответственно иметь значение `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` и `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-139">The endpoint URL for these two server instances are, respectively: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` and `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span></span> <span data-ttu-id="9c7ad-140">Обратите внимание, что имя экземпляра сервера в адресе не указывается.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-140">Note that the address does not contain the name of the server instance.</span></span>  
  
     <span data-ttu-id="9c7ad-141">![Сетевые адреса сервера экземпляра по умолчанию](../../media/dbm-2-instances-ports-1-system.gif "Сетевые адреса сервера экземпляра по умолчанию")</span><span class="sxs-lookup"><span data-stu-id="9c7ad-141">![Server network addresses of a default instance](../../media/dbm-2-instances-ports-1-system.gif "Server network addresses of a default instance")</span></span>  
  
     <span data-ttu-id="9c7ad-142">Чтобы определить, какой порт в текущий момент связан с конечной точкой зеркального отображения базы данных экземпляра сервера, воспользуйтесь следующей инструкцией [!INCLUDE[tsql](../../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="9c7ad-142">To identify the port currently associated with database mirroring endpoint of a server instance, use the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql
    SELECT type_desc, port FROM sys.TCP_endpoints  
    ```  
  
     <span data-ttu-id="9c7ad-143">Найдите строку параметра **type_desc** , имеющую значение "DATABASE_MIRRORING", и используйте соответствующий номер порта.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-143">Find the row whose **type_desc** value is "DATABASE_MIRRORING," and use the corresponding port number.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="9c7ad-144">Примеры</span><span class="sxs-lookup"><span data-stu-id="9c7ad-144">Examples</span></span>  
  
#### <a name="a-using-a-system-name"></a><span data-ttu-id="9c7ad-145">A.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-145">A.</span></span> <span data-ttu-id="9c7ad-146">Использование имени системы</span><span class="sxs-lookup"><span data-stu-id="9c7ad-146">Using a system name</span></span>  
 <span data-ttu-id="9c7ad-147">В следующем URL-адресе конечной точки определено системное имя `SYSTEM46`и порт `7022`.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-147">The following endpoint URL specifies a system name, `SYSTEM46`, and port `7022`.</span></span>  
  
 `TCP://SYSTEM46:7022`  
  
#### <a name="b-using-a-fully-qualified-domain-name"></a><span data-ttu-id="9c7ad-148">Б.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-148">B.</span></span> <span data-ttu-id="9c7ad-149">Использование полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="9c7ad-149">Using a fully qualified domain name</span></span>  
 <span data-ttu-id="9c7ad-150">В следующем URL-адресе конечной точки определено полное доменное имя `DBSERVER8.manufacturing.Adventure-Works.com`и порт `7024`.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-150">The following endpoint URL specifies a fully qualified domain name, `DBSERVER8.manufacturing.Adventure-Works.com`, and port `7024`.</span></span>  
  
 `TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024`  
  
#### <a name="c-using-ipv4"></a><span data-ttu-id="9c7ad-151">В.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-151">C.</span></span> <span data-ttu-id="9c7ad-152">Использование IPv4</span><span class="sxs-lookup"><span data-stu-id="9c7ad-152">Using IPv4</span></span>  
 <span data-ttu-id="9c7ad-153">В следующем URL-адресе конечной точки определены адрес IPv4 `10.193.9.134`и порт `7023`.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-153">The following endpoint URL specifies an IPv4 address, `10.193.9.134`, and port `7023`.</span></span>  
  
 `TCP://10.193.9.134:7023`  
  
#### <a name="d-using-ipv6"></a><span data-ttu-id="9c7ad-154">Г.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-154">D.</span></span> <span data-ttu-id="9c7ad-155">Использование IPv6</span><span class="sxs-lookup"><span data-stu-id="9c7ad-155">Using IPv6</span></span>  
 <span data-ttu-id="9c7ad-156">В следующем URL-адресе конечной точки определен адрес IPv6 `2001:4898:23:1002:20f:1fff:feff:b3a3`и порт `7022`.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-156">The following endpoint URL contains an IPv6 address, `2001:4898:23:1002:20f:1fff:feff:b3a3`, and port `7022`.</span></span>  
  
 `TCP://[2001:4898:23:1002:20f:1fff:feff:b3a3]:7022`  
  
##  <a name="finding-the-fully-qualified-domain-name-of-a-system"></a><a name="Finding_FQDN"></a> <span data-ttu-id="9c7ad-157">Определение полного доменного имени системы</span><span class="sxs-lookup"><span data-stu-id="9c7ad-157">Finding the Fully Qualified Domain Name of A System</span></span>  
 <span data-ttu-id="9c7ad-158">Чтобы определить полное доменное имя системы, введите следующую команду в командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="9c7ad-158">To find the fully qualified domain name of a system, at the Windows command prompt on that system, enter:</span></span>  
  
 <span data-ttu-id="9c7ad-159">**IPCONFIG /ALL**</span><span class="sxs-lookup"><span data-stu-id="9c7ad-159">**IPCONFIG /ALL**</span></span>  
  
 <span data-ttu-id="9c7ad-160">Чтобы сформировать полное доменное имя, следует сцепить значения *<имя_узла>* и *<основной_DNS_суффикс>* следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9c7ad-160">To form the fully qualified domain name, concatenate the values of *<host_name>* and *<Primary_Dns_Suffix>* as follows:</span></span>  
  
 <span data-ttu-id="9c7ad-161">_<имя_узла>_ **.**</span><span class="sxs-lookup"><span data-stu-id="9c7ad-161">_<host_name>_ **.**</span></span> <span data-ttu-id="9c7ad-162">_<основной_DNS_суффикс>_</span><span class="sxs-lookup"><span data-stu-id="9c7ad-162">_<Primary_Dns_Suffix>_</span></span>  
  
 <span data-ttu-id="9c7ad-163">Например, следующая конфигурация IP:</span><span class="sxs-lookup"><span data-stu-id="9c7ad-163">For example, the IP configuration</span></span>  
  
 `Host Name  .  .  .  .  .  .  : MYSERVER`  
  
 `Primary Dns Suffix  .  .  .  : mydomain.Adventure-Works.com`  
  
 <span data-ttu-id="9c7ad-164">соответствует следующему полному доменному имени:</span><span class="sxs-lookup"><span data-stu-id="9c7ad-164">equates to the following fully qualified domain name:</span></span>  
  
 `MYSERVER.mydomain.Adventure-Works.com`  
  
> [!NOTE]  
>  <span data-ttu-id="9c7ad-165">Более подробные сведения о полном доменном имени можно получить у системного администратора.</span><span class="sxs-lookup"><span data-stu-id="9c7ad-165">If you need more information about a fully qualified domain name, see your system administrator.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9c7ad-166">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9c7ad-166">Related Tasks</span></span>  
 <span data-ttu-id="9c7ad-167">**Настройка конечной точки зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="9c7ad-167">**To Configure a Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="9c7ad-168">Создание конечной точки зеркального отображения базы данных для группы доступности AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="9c7ad-168">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="9c7ad-169">Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9c7ad-169">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="9c7ad-170">Использование сертификатов для конечной точки зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9c7ad-170">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="9c7ad-171">Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9c7ad-171">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="9c7ad-172">Включение использования сертификатов для входящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9c7ad-172">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="9c7ad-173">Указание сетевого адреса сервера (зеркальное отображение базы данных)</span><span class="sxs-lookup"><span data-stu-id="9c7ad-173">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="9c7ad-174">Устранение неполадок &#40;конфигурации группы доступности AlwaysOn SQL Server&#41;Deleted</span><span class="sxs-lookup"><span data-stu-id="9c7ad-174">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
 <span data-ttu-id="9c7ad-175">**Просмотр сведений о конечной точке зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="9c7ad-175">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="9c7ad-176">sys.database_mirroring_endpoints (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9c7ad-176">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
 <span data-ttu-id="9c7ad-177">**Добавление реплики доступности**</span><span class="sxs-lookup"><span data-stu-id="9c7ad-177">**To add an availability replica**</span></span>  
  
-   [<span data-ttu-id="9c7ad-178">Добавление вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9c7ad-178">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="9c7ad-179">Присоединение вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9c7ad-179">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="9c7ad-180">См. также</span><span class="sxs-lookup"><span data-stu-id="9c7ad-180">Related Content</span></span>  
  
-   [<span data-ttu-id="9c7ad-181">Руководство по решениям режима AlwaysOn в Microsoft SQL Server для обеспечения высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="9c7ad-181">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
## <a name="see-also"></a><span data-ttu-id="9c7ad-182">См. также:</span><span class="sxs-lookup"><span data-stu-id="9c7ad-182">See Also</span></span>  
 <span data-ttu-id="9c7ad-183">[Создание и настройка групп доступности (SQL Server)](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9c7ad-183">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="9c7ad-184">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9c7ad-184">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="9c7ad-185">CREATE ENDPOINT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9c7ad-185">CREATE ENDPOINT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-endpoint-transact-sql)  
