---
title: Создание допустимой строки подключения с использованием протокола TCP/IP | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine]
- ports [SQL Server], connecting to
- TCP/IP [SQL Server], connection strings
- connection strings [Database Engine], TCP/IP
- aliases [SQL Server], TCP/IP
ms.assetid: ee5dbc2c-1fc6-42bd-bdf5-efa792557934
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5f761fa86ec4ed09c13bf4807489754c10b979ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659055"
---
# <a name="creating-a-valid-connection-string-using-tcp-ip"></a><span data-ttu-id="1bda5-102">Создание допустимой строки подключения с использованием протокола TCP/IP</span><span class="sxs-lookup"><span data-stu-id="1bda5-102">Creating a Valid Connection String Using TCP IP</span></span>
  <span data-ttu-id="1bda5-103">Чтобы создать допустимую строку подключения с использованием протокола TCP/IP, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1bda5-103">To create a valid connection string using TCP/IP, you must:</span></span>  
  
-   <span data-ttu-id="1bda5-104">Укажите **Имя псевдонима**.</span><span class="sxs-lookup"><span data-stu-id="1bda5-104">Specify an **Alias Name**.</span></span>  
  
-   <span data-ttu-id="1bda5-105">В поле **Сервер**введите имя сервера, к которому можно подключиться с помощью команды **PING** , или IP-адрес, к которому можно подключиться с помощью команды **PING** .</span><span class="sxs-lookup"><span data-stu-id="1bda5-105">For the **Server**, enter either a server name to which you can connect using the **PING** utility, or an IP address to which you can connect using the **PING** utility.</span></span> <span data-ttu-id="1bda5-106">Для именованного экземпляра добавьте имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1bda5-106">For a named instance append the instance name.</span></span>  
  
-   <span data-ttu-id="1bda5-107">Укажите **TCP/IP** в поле **Протокол**.</span><span class="sxs-lookup"><span data-stu-id="1bda5-107">Specify **TCP/IP** for the **Protocol**.</span></span>  
  
-   <span data-ttu-id="1bda5-108">При необходимости в поле **Номер порта**введите номер порта.</span><span class="sxs-lookup"><span data-stu-id="1bda5-108">Optionally, enter a port number for the **Port No**.</span></span> <span data-ttu-id="1bda5-109">Номер порта по умолчанию равен 1433. Это номер порта экземпляра по умолчанию компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] на сервере.</span><span class="sxs-lookup"><span data-stu-id="1bda5-109">The default is 1433, which is the port number of the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on a server.</span></span> <span data-ttu-id="1bda5-110">Для подключения к именованному экземпляру или к экземпляру по умолчанию, не прослушивающему порт 1433, необходимо указать номер порта или запустить службу « [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , браузер».</span><span class="sxs-lookup"><span data-stu-id="1bda5-110">To connect to a named instance or a default instance that is not listening on port 1433, you must provide the port number, or start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span> <span data-ttu-id="1bda5-111">Дополнительные сведения о настройке службы браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Служба браузера SQL Server](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span><span class="sxs-lookup"><span data-stu-id="1bda5-111">For information on configuring the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service, see [SQL Server Browser Service](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span></span>  
  
 <span data-ttu-id="1bda5-112">Во время соединения компонент собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] считывает значения сервера, протокола и порта из реестра для заданного имени псевдонима и создает строку подключения в формате `tcp:<servername>[\<instancename>],<port>` или `tcp:<IPAddress>[\<instancename>],<port>`.</span><span class="sxs-lookup"><span data-stu-id="1bda5-112">At the time of connection, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client component reads the server, protocol, and port values from the registry for the specified alias name, and creates a connection string in the format `tcp:<servername>[\<instancename>],<port>` or `tcp:<IPAddress>[\<instancename>],<port>`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bda5-113">Брандмауэр Windows [!INCLUDE[msCoName](../../includes/msconame-md.md)] по умолчанию закрывает порт 1433.</span><span class="sxs-lookup"><span data-stu-id="1bda5-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall closes port 1433 by default.</span></span> <span data-ttu-id="1bda5-114">Так как [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] осуществляет связь через порт 1433, необходимо повторно открыть этот порт, если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настроен на прослушивание клиентских соединений с использованием TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="1bda5-114">Because [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communicates over port 1433, you must reopen the port if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to listen for incoming client connections using TCP/IP.</span></span> <span data-ttu-id="1bda5-115">Информацию о настройке брандмауэра см. в статье "Настройка брандмауэра Windows для разрешения доступа к SQL Server" в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или документации по вашей версии брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="1bda5-115">For information on configuring a firewall, see "How to: Configure a Firewall for SQL Server Access" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or review your firewall documentation.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1bda5-116">и собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] полностью поддерживают протокол IP версии 4 (IPv4) и версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="1bda5-116">and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client fully support both Internet Protocol version 4 (IPv4) and Internet Protocol version 6 (IPv6).</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1bda5-117">Диспетчер конфигурации для IP-адресов принимает как формат IPv4, так и формат IPv6.</span><span class="sxs-lookup"><span data-stu-id="1bda5-117">Configuration Manager accepts both IPv4 and IPv6 formats for IP addresses.</span></span> <span data-ttu-id="1bda5-118">Сведения о протоколе IPv6 см. в разделе "Подключение при помощи IPv6" электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1bda5-118">For information on IPv6, see "Connecting Using IPv6" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="1bda5-119">Подключение к локальному серверу</span><span class="sxs-lookup"><span data-stu-id="1bda5-119">Connecting to the Local Server</span></span>  
 <span data-ttu-id="1bda5-120">При подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выполняющемуся на том же компьютере, что и клиент, в качестве имени сервера можно использовать `(local)` .</span><span class="sxs-lookup"><span data-stu-id="1bda5-120">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use `(local)` as the server name.</span></span> <span data-ttu-id="1bda5-121">Это действие не рекомендуется, поскольку может вызвать неоднозначность, но может быть полезным, если известно, что клиент запущен на нужном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1bda5-121">This is not encouraged as it leads to ambiguity, however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="1bda5-122">Например, при создании приложения для мобильных отключенных пользователей, таких как торговый персонал, когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет запускаться на переносных компьютерах и использоваться для хранения данных проекта, клиент, подключающийся к `(local)` , всегда будет подключаться к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выполняющемуся на переносном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1bda5-122">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to `(local)` would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="1bda5-123">Слово `localhost` или точку ( **.** ) можно использовать вместо `(local)`.</span><span class="sxs-lookup"><span data-stu-id="1bda5-123">The word `localhost` or a period (**.**) can be used in place of `(local)`.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="1bda5-124">Проверка протокола соединения</span><span class="sxs-lookup"><span data-stu-id="1bda5-124">Verifying Your Connection Protocol</span></span>  
 <span data-ttu-id="1bda5-125">Следующий запрос возвращает протокол, используемый в текущем соединении.</span><span class="sxs-lookup"><span data-stu-id="1bda5-125">The following query returns the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="1bda5-126">Примеры</span><span class="sxs-lookup"><span data-stu-id="1bda5-126">Examples</span></span>  
 <span data-ttu-id="1bda5-127">Подключение по имени сервера:</span><span class="sxs-lookup"><span data-stu-id="1bda5-127">Connecting by server name:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <servername>  
  
```  
  
 <span data-ttu-id="1bda5-128">Подключение по имени сервера к именованному экземпляру:</span><span class="sxs-lookup"><span data-stu-id="1bda5-128">Connecting by server name to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <servername>\<instancename>  
  
```  
  
 <span data-ttu-id="1bda5-129">Подключение по имени сервера к указанному порту:</span><span class="sxs-lookup"><span data-stu-id="1bda5-129">Connecting by server name to a specified port:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <port>  
Protocol           TCP/IP  
Server             <servername>  
  
```  
  
 <span data-ttu-id="1bda5-130">Подключение по IP-адресу:</span><span class="sxs-lookup"><span data-stu-id="1bda5-130">Connecting by IP address:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="1bda5-131">Подключение по IP-адресу к именованному экземпляру:</span><span class="sxs-lookup"><span data-stu-id="1bda5-131">Connecting by IP address to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <IPAddress>\<instancename>  
  
```  
  
 <span data-ttu-id="1bda5-132">Подключение по IP-адресу к указанному порту:</span><span class="sxs-lookup"><span data-stu-id="1bda5-132">Connecting by IP address to a specified port:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <port number>  
Protocol           TCP/IP  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="1bda5-133">Подключение к локальному компьютеру при помощи `(local)`:</span><span class="sxs-lookup"><span data-stu-id="1bda5-133">Connecting to the local computer using `(local)`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             (local)  
  
```  
  
 <span data-ttu-id="1bda5-134">Подключение к локальному компьютеру при помощи `localhost`:</span><span class="sxs-lookup"><span data-stu-id="1bda5-134">Connecting to the local computer using `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             localhost  
  
```  
  
 <span data-ttu-id="1bda5-135">Подключение к именованному экземпляру на локальном компьютере `localhost`:</span><span class="sxs-lookup"><span data-stu-id="1bda5-135">Connecting to a named instance on the local computer `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             localhost\<instancename>  
  
```  
  
 <span data-ttu-id="1bda5-136">Соединение с локальным компьютером при помощи точки:</span><span class="sxs-lookup"><span data-stu-id="1bda5-136">Connecting to the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             .  
  
```  
  
 <span data-ttu-id="1bda5-137">Соединение с именованным экземпляром на локальном компьютере при помощи точки:</span><span class="sxs-lookup"><span data-stu-id="1bda5-137">Connecting to a named instance on the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             .\<instancename>  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="1bda5-138">Сведения о настройке сетевого протокола с помощью параметра **sqlcmd** см. в статье "Подключение к компоненту Database Engine при помощи программы sqlcmd" в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1bda5-138">For information on specifying the network protocol as a **sqlcmd** parameter, see "How to: Connect to the Database Engine Using sqlcmd.exe" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bda5-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="1bda5-139">See Also</span></span>  
 <span data-ttu-id="1bda5-140">[Создание допустимой строки соединения с использованием протокола общей памяти](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="1bda5-140">[Creating a Valid Connection String Using Shared Memory Protocol](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span></span>  
 <span data-ttu-id="1bda5-141">[Создание допустимой строки подключения, использующей протокол именованных каналов](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span><span class="sxs-lookup"><span data-stu-id="1bda5-141">[Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span></span>  
 [<span data-ttu-id="1bda5-142">Выбор сетевого протокола</span><span class="sxs-lookup"><span data-stu-id="1bda5-142">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
