---
title: Указание сетевого адреса сервера (зеркальное отображение базы данных) | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- database mirroring [SQL Server], endpoint
- endpoints [SQL Server], database mirroring
- server network addresses [SQL Server]
ms.assetid: a64d4b6b-9016-4f1e-a310-b1df181dd0c6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5c7db7ee6d321229205248059ce09a86f1da101f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665099"
---
# <a name="specify-a-server-network-address-database-mirroring"></a><span data-ttu-id="8ee5d-102">Указание сетевого адреса сервера (зеркальное отображение базы данных)</span><span class="sxs-lookup"><span data-stu-id="8ee5d-102">Specify a Server Network Address (Database Mirroring)</span></span>
  <span data-ttu-id="8ee5d-103">При настройке сеанса зеркального отображения базы данных для каждого экземпляра сервера необходим сетевой адрес.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-103">Setting up a database mirroring session requires a server network address for each of the server instances.</span></span> <span data-ttu-id="8ee5d-104">Он должен однозначно определять экземпляр по адресу и номеру порта, который прослушивается данным экземпляром.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-104">The server network address of a server instance must unambiguously identify the instance by providing a system address and the number of the port on which the instance is listening.</span></span>  
  
 <span data-ttu-id="8ee5d-105">Определение порта в сетевом адресе сервера возможно при наличии конечной точки зеркального отображения базы данных в экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-105">Before you can specify a port in a server network address, the database mirroring endpoint must exist on the server instance.</span></span> <span data-ttu-id="8ee5d-106">Дополнительные сведения см. в разделе [Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="8ee5d-106">For more information, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
  
  
##  <a name="syntax-for-a-server-network-address"></a><a name="Syntax"></a> <span data-ttu-id="8ee5d-107">Синтаксис сетевого адреса сервера</span><span class="sxs-lookup"><span data-stu-id="8ee5d-107">Syntax for a Server Network Address</span></span>  
 <span data-ttu-id="8ee5d-108">Сетевой адрес сервера имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8ee5d-108">The syntax for a server network address is of the form:</span></span>  
  
 <span data-ttu-id="8ee5d-109">TCP<strong>://</strong> *\<system-address>* <strong> :<strong>*\<port>*</span><span class="sxs-lookup"><span data-stu-id="8ee5d-109">TCP<strong>://</strong>*\<system-address>*<strong>:<strong>*\<port>*</span></span> 
  
 <span data-ttu-id="8ee5d-110">где</span><span class="sxs-lookup"><span data-stu-id="8ee5d-110">where</span></span>  
  
-   <span data-ttu-id="8ee5d-111">*\<system-address>*  — строка, однозначно определяющая целевой компьютер.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-111">*\<system-address>* is a string that unambiguously identifies the destination computer system.</span></span> <span data-ttu-id="8ee5d-112">Обычно сетевой адрес представляет собой системное имя (если компьютеры входят в один домен), полное доменное имя или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-112">Typically, the server address is a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address:</span></span>  
  
    -   <span data-ttu-id="8ee5d-113">Если компьютеры входят в один домен, можно указать имя компьютера (например `SYSTEM46`).</span><span class="sxs-lookup"><span data-stu-id="8ee5d-113">If the systems are the same domain, you can use the name of the computer system; for example, `SYSTEM46`.</span></span>  
  
    -   <span data-ttu-id="8ee5d-114">Если указывается IP-адрес, то он должен быть уникальным в используемой среде.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-114">To use an IP address, it must be unique in your environment.</span></span> <span data-ttu-id="8ee5d-115">Рекомендуется использовать IP-адрес только в том случае, если он является статическим.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-115">We recommend that you use an IP address only if it is static.</span></span> <span data-ttu-id="8ee5d-116">IP-адреса бывают версии 4 (IPv4) или 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="8ee5d-116">The IP address can be IP Version 4 (IPv4) or IP Version 6 (IPv6).</span></span> <span data-ttu-id="8ee5d-117">Адреса IPv6 следует заключать в квадратные скобки, например: **[** _<адрес_IPv6>_ **]** .</span><span class="sxs-lookup"><span data-stu-id="8ee5d-117">An IPv6 address must be enclosed within square brackets, for example: **[**_<IPv6_address>_**]**.</span></span>  
  
         <span data-ttu-id="8ee5d-118">Чтобы определить IP-адрес системы, в командной строке Windows введите команду **ipconfig** .</span><span class="sxs-lookup"><span data-stu-id="8ee5d-118">To learn the IP address of a system, at the Windows command prompt, enter the **ipconfig** command.</span></span>  
  
    -   <span data-ttu-id="8ee5d-119">При указании полного доменного имени гарантируется правильная работа.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-119">The fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="8ee5d-120">Это локально определенная строка адреса, которая имеет различную форму в разных местах.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-120">This is a locally defined address string that different forms in different places.</span></span> <span data-ttu-id="8ee5d-121">Часто, но не всегда полное доменное имя представляет собой составное имя, состоящее из имени компьютера и нескольких компонентов доменов, разделенных точками, в следующем виде:</span><span class="sxs-lookup"><span data-stu-id="8ee5d-121">Often, but not always, a fully qualified domain name is a compound name that includes the computer name and a series of period-separated domain segments of the form:</span></span>  
  
         <span data-ttu-id="8ee5d-122">_имя_компьютера_ **.**</span><span class="sxs-lookup"><span data-stu-id="8ee5d-122">_computer_name_ **.**</span></span> <span data-ttu-id="8ee5d-123">_компонент_домена_[... **.** _компонент_домена_]</span><span class="sxs-lookup"><span data-stu-id="8ee5d-123">_domain_segment_[...**.**_domain_segment_]</span></span>  
  
         <span data-ttu-id="8ee5d-124">где *имя_компьютера*— сетевое имя компьютера, на котором запущен экземпляр сервера, а *сегмент_домена*[... **.** _сегмент_домена_] — остальные сведения о домене для сервера, например `localinfo.corp.Adventure-Works.com`.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-124">where *computer_name i*s the network name of the computer running the server instance, and *domain_segment*[...**.**_domain_segment_] is the remaining domain information of the server; for example: `localinfo.corp.Adventure-Works.com`.</span></span>  
  
         <span data-ttu-id="8ee5d-125">Содержание и количество доменных сегментов определяется компанией или организацией.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-125">The content and number of domain segments are determined within the company or organization.</span></span> <span data-ttu-id="8ee5d-126">Полное доменное имя сервера можно узнать у системного администратора.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-126">If you do not know the fully qualified domain name for your server, see your system administrator.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8ee5d-127">Дополнительные сведения об определении полного доменного имени см. в подразделе «Определение полного доменного имени» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-127">For information about how to find a fully qualified domain name, see "Finding the Fully Qualified Domain Name," later in this topic.</span></span>  
  
-   <span data-ttu-id="8ee5d-128">*\<port>*  — порт, используемый конечной точкой зеркального отображения экземпляра сервера-участника.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-128">*\<port>* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="8ee5d-129">Сведения об определении конечной точки см. в разделе [Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="8ee5d-129">For information about specifying an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
     <span data-ttu-id="8ee5d-130">Конечная точка зеркального отображения базы данных может использовать любой доступный порт.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-130">A database mirroring endpoint can use any available port on the computer system.</span></span> <span data-ttu-id="8ee5d-131">Номер каждого порта в компьютерной системе должен быть связан только с одной конечной точкой, а каждая конечная точка должна быть связана только с одним экземпляром сервера; таким образом, разные экземпляры сервера на одном и том же сервере прослушивают различные конечные точки через различные порты.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-131">Each port number on a computer system must be associated with only one endpoint, and each endpoint is associated with a single server instance; thus, different server instances on the same server listen on different endpoints with different ports.</span></span> <span data-ttu-id="8ee5d-132">Поэтому порт, указанный в сетевом адресе сервера при настройке сеанса зеркального отображения базы данных, будет всегда направлять сеанс к экземпляру сервера, конечная точка которого связана с этим портом.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-132">Therefore, the port you specify in the server network address when you set up a database mirroring session will always direct the session to the server instance whose endpoint is associated with that port.</span></span>  
  
     <span data-ttu-id="8ee5d-133">Лишь номер порта в сетевом адресе сервера, указанный для экземпляра сервера и связанный с конечной точкой зеркального отображения, отличает этот экземпляр от других экземпляров, имеющихся на данном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-133">In the server network address of a server instance, only the number of the port associated with its mirroring endpoint distinguishes that instance from any other instances on the computer.</span></span> <span data-ttu-id="8ee5d-134">На следующем рисунке показаны сетевые адреса двух экземпляров серверов, имеющихся на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-134">The following figure illustrates the server network addresses of two server instances on a single computer.</span></span> <span data-ttu-id="8ee5d-135">Экземпляр по умолчанию использует порт `7022` , именованный экземпляр — порт `7033`.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-135">The default instance uses port `7022` and the named instance uses port `7033`.</span></span> <span data-ttu-id="8ee5d-136">Сетевым адресом сервера для этих двух экземпляров сервера будут соответственно `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` и `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-136">The server network address for these two server instances are, respectively: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` and `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span></span> <span data-ttu-id="8ee5d-137">Обратите внимание, что имя экземпляра сервера в адресе не указывается.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-137">Note that the address does not contain the name of the server instance.</span></span>  
  
     <span data-ttu-id="8ee5d-138">![Сетевые адреса сервера экземпляра по умолчанию](../media/dbm-2-instances-ports-1-system.gif "Сетевые адреса сервера экземпляра по умолчанию")</span><span class="sxs-lookup"><span data-stu-id="8ee5d-138">![Server network addresses of a default instance](../media/dbm-2-instances-ports-1-system.gif "Server network addresses of a default instance")</span></span>  
  
     <span data-ttu-id="8ee5d-139">Чтобы определить, какой порт в текущий момент связан с конечной точкой зеркального отображения базы данных экземпляра сервера, воспользуйтесь следующей инструкцией [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="8ee5d-139">To identify the port currently associated with database mirroring endpoint of a server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT type_desc, port FROM sys.tcp_endpoints  
    ```  
  
     <span data-ttu-id="8ee5d-140">Найдите строку параметра **type_desc** , имеющую значение "DATABASE_MIRRORING", и используйте соответствующий номер порта.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-140">Find the row whose **type_desc** value is "DATABASE_MIRRORING," and use the corresponding port number.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="8ee5d-141">Примеры</span><span class="sxs-lookup"><span data-stu-id="8ee5d-141">Examples</span></span>  
  
#### <a name="a-using-a-system-name"></a><span data-ttu-id="8ee5d-142">A.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-142">A.</span></span> <span data-ttu-id="8ee5d-143">Использование имени системы</span><span class="sxs-lookup"><span data-stu-id="8ee5d-143">Using a system name</span></span>  
 <span data-ttu-id="8ee5d-144">В следующем сетевом адресе сервера определено системное имя `SYSTEM46`и порт `7022`.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-144">The following server network address specifies a system name, `SYSTEM46`, and port `7022`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://SYSTEM46:7022';  
```  
  
#### <a name="b-using-a-fully-qualified-domain-name"></a><span data-ttu-id="8ee5d-145">Б.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-145">B.</span></span> <span data-ttu-id="8ee5d-146">Использование полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="8ee5d-146">Using a fully qualified domain name</span></span>  
 <span data-ttu-id="8ee5d-147">В следующем сетевом адресе сервера определено полное доменное имя `DBSERVER8.manufacturing.Adventure-Works.com`и порт `7024`.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-147">The following server network address specifies a fully qualified domain name, `DBSERVER8.manufacturing.Adventure-Works.com`, and port `7024`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://DBSERVER8.manufacturing.Adventure-Works.com:7024';  
```  
  
#### <a name="c-using-ipv4"></a><span data-ttu-id="8ee5d-148">В.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-148">C.</span></span> <span data-ttu-id="8ee5d-149">Использование IPv4</span><span class="sxs-lookup"><span data-stu-id="8ee5d-149">Using IPv4</span></span>  
 <span data-ttu-id="8ee5d-150">В следующем сетевом адресе сервера определены адрес IPv4 `10.193.9.134`и порт `7023`.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-150">The following server network address specifies an IPv4 address, `10.193.9.134`, and port `7023`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://10.193.9.134:7023';  
```  
  
#### <a name="d-using-ipv6"></a><span data-ttu-id="8ee5d-151">Г.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-151">D.</span></span> <span data-ttu-id="8ee5d-152">Использование IPv6</span><span class="sxs-lookup"><span data-stu-id="8ee5d-152">Using IPv6</span></span>  
 <span data-ttu-id="8ee5d-153">В следующем сетевом адресе сервера определен адрес IPv6 `2001:4898:23:1002:20f:1fff:feff:b3a3`и порт `7022`.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-153">The following server network address contains an IPv6 address, `2001:4898:23:1002:20f:1fff:feff:b3a3`, and port `7022`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://[2001:4898:23:1002:20f:1fff:feff:b3a3]:7022';  
```  
  
## <a name="finding-the-fully-qualified-domain-name"></a><span data-ttu-id="8ee5d-154">Определение полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="8ee5d-154">Finding the Fully Qualified Domain Name</span></span>  
 <span data-ttu-id="8ee5d-155">Чтобы определить полное доменное имя системы, введите следующую команду в командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="8ee5d-155">To find the fully qualified domain name of a system, at the Windows command prompt on that system, enter:</span></span>  
  
 <span data-ttu-id="8ee5d-156">**IPCONFIG /ALL**</span><span class="sxs-lookup"><span data-stu-id="8ee5d-156">**IPCONFIG /ALL**</span></span>  
  
 <span data-ttu-id="8ee5d-157">Чтобы сформировать полное доменное имя, следует сцепить значения *<имя_узла>* и *<основной_DNS_суффикс>* следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8ee5d-157">To form the fully qualified domain name, concatenate the values of *<host_name>* and *<Primary_Dns_Suffix>* as follows:</span></span>  
  
 <span data-ttu-id="8ee5d-158">_<имя_узла>_ **.**</span><span class="sxs-lookup"><span data-stu-id="8ee5d-158">_<host_name>_ **.**</span></span> <span data-ttu-id="8ee5d-159">_<основной_DNS_суффикс>_</span><span class="sxs-lookup"><span data-stu-id="8ee5d-159">_<Primary_Dns_Suffix>_</span></span>  
  
 <span data-ttu-id="8ee5d-160">Например, следующая конфигурация IP:</span><span class="sxs-lookup"><span data-stu-id="8ee5d-160">For example, the IP configuration</span></span>  
  
 `Host Name  .  .  .  .  .  .  : MYSERVER`  
  
 `Primary Dns Suffix  .  .  .  : mydomain.Adventure-Works.com`  
  
 <span data-ttu-id="8ee5d-161">соответствует следующему полному доменному имени:</span><span class="sxs-lookup"><span data-stu-id="8ee5d-161">equates to the following fully qualified domain name:</span></span>  
  
 `MYSERVER.mydomain.Adventure-Works.com`  
  
##  <a name="examples"></a><a name="Examples"></a> <span data-ttu-id="8ee5d-162">Примеры</span><span class="sxs-lookup"><span data-stu-id="8ee5d-162">Examples</span></span>  
 <span data-ttu-id="8ee5d-163">В следующем примере показан сетевой адрес сервера для экземпляра сервера на компьютере с именем `REMOTESYSTEM3` в другом домене.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-163">The following example shows the server network address for a server instance on a computer system named `REMOTESYSTEM3` in another domain.</span></span> <span data-ttu-id="8ee5d-164">Сведения о домене: `NORTHWEST.ADVENTURE-WORKS.COM`, порт конечной точки зеркального отображения базы данных — `7025`.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-164">The domain information is `NORTHWEST.ADVENTURE-WORKS.COM`, and the port of the database mirroring endpoint is `7025`.</span></span> <span data-ttu-id="8ee5d-165">Для приведенных примеров компонентов сетевой адрес сервера выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8ee5d-165">Given these example components, the server network address is.</span></span>  
  
 `TCP://REMOTESYSTEM3.NORTHWEST.ADVENTURE-WORKS.COM:7025`  
  
 <span data-ttu-id="8ee5d-166">В следующем примере показан сетевой адрес сервера для экземпляра сервера на компьютере с именем `DBSERVER1`.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-166">The following example shows the server network address for a server instance on a computer system named `DBSERVER1`.</span></span> <span data-ttu-id="8ee5d-167">Данный компьютер включен в локальный домен и однозначно определяется своим системным именем.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-167">This system is in the local domain and is unambiguously identified by its system name.</span></span> <span data-ttu-id="8ee5d-168">Порт конечной точки зеркального отображения базы данных — `7022`.</span><span class="sxs-lookup"><span data-stu-id="8ee5d-168">The port of the database mirroring endpoint is `7022`.</span></span>  
  
 `TCP://DBSERVER1:7022`  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="8ee5d-169">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="8ee5d-169">Related Tasks</span></span>  
  
-   [<span data-ttu-id="8ee5d-170">Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ee5d-170">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="8ee5d-171">См. также:</span><span class="sxs-lookup"><span data-stu-id="8ee5d-171">See Also</span></span>  
 <span data-ttu-id="8ee5d-172">[Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8ee5d-172">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="8ee5d-173">Конечная точка зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8ee5d-173">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
  
  
