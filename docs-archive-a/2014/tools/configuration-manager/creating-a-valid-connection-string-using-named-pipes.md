---
title: Создание допустимой строки подключения с использованием именованных каналов | Документация Майкрософт
description: Узнайте, как создать допустимую строку подключения при использовании протокола именованных каналов для подключения к экземпляру SQL Server. Просмотр примеров допустимых имен каналов.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine], named pipes
- pipes [SQL Server]
- pipes [SQL Server], connecting to
- aliases [SQL Server], named pipes
- Named Pipes [SQL Server], connection strings
ms.assetid: 90930ff2-143b-4651-8ae3-297103600e4f
author: rothja
ms.author: jroth
ms.openlocfilehash: 10f3e1d01e9e5b7b1d1c0d1bb822bf233ceee636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659057"
---
# <a name="creating-a-valid-connection-string-using-named-pipes"></a><span data-ttu-id="ea792-104">Создание допустимой строки соединения, использующей протокол именованных каналов</span><span class="sxs-lookup"><span data-stu-id="ea792-104">Creating a Valid Connection String Using Named Pipes</span></span>
  <span data-ttu-id="ea792-105">Если пользователь по умолчанию [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] прослушивает протокол именованных каналов, он использует в `\\.\pipe\sql\query` качестве имени канала.</span><span class="sxs-lookup"><span data-stu-id="ea792-105">Unless changed by the user, when the default instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on the named pipes protocol, it uses `\\.\pipe\sql\query` as the pipe name.</span></span> <span data-ttu-id="ea792-106">Точка означает, что компьютер является локальным компьютером, `pipe` указывает, что соединение является именованным каналом, а `sql\query` — именем канала.</span><span class="sxs-lookup"><span data-stu-id="ea792-106">The period indicates that the computer is the local computer, `pipe` indicates that the connection is a named pipe, and `sql\query` is the name of the pipe.</span></span> <span data-ttu-id="ea792-107">Чтобы подключиться к каналу по умолчанию, псевдоним должен содержать `\\<computer_name>\pipe\sql\query` в качестве имени канала.</span><span class="sxs-lookup"><span data-stu-id="ea792-107">To connect to the default pipe, the alias must have `\\<computer_name>\pipe\sql\query` as the pipe name.</span></span> <span data-ttu-id="ea792-108">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] был настроен на прослушивание другого канала, то имя канала должно соответствовать этому каналу.</span><span class="sxs-lookup"><span data-stu-id="ea792-108">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been configured to listen on a different pipe, the pipe name must use that pipe.</span></span> <span data-ttu-id="ea792-109">Например, если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использует в качестве канала `\\.\pipe\unit\app`, то псевдоним должен использовать `\\<computer_name>\pipe\unit\app` в качестве имени канала.</span><span class="sxs-lookup"><span data-stu-id="ea792-109">For instance, if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is using `\\.\pipe\unit\app` as the pipe, the alias must use `\\<computer_name>\pipe\unit\app` as the pipe name.</span></span>  
  
 <span data-ttu-id="ea792-110">Создание допустимого имени канала</span><span class="sxs-lookup"><span data-stu-id="ea792-110">To create a valid pipe name, you must:</span></span>  
  
-   <span data-ttu-id="ea792-111">Укажите **Имя псевдонима**.</span><span class="sxs-lookup"><span data-stu-id="ea792-111">Specify an **Alias Name**.</span></span>  
  
-   <span data-ttu-id="ea792-112">Выберите **именованные каналы** в качестве **протокола**.</span><span class="sxs-lookup"><span data-stu-id="ea792-112">Select **Named Pipes** as the **Protocol**.</span></span>  
  
-   <span data-ttu-id="ea792-113">Введите **имя канала**.</span><span class="sxs-lookup"><span data-stu-id="ea792-113">Enter the **Pipe Name**.</span></span> <span data-ttu-id="ea792-114">Кроме того, можно оставить **имя канала** пустым, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] после того как вы укажете **протокол** и **сервер** , Configuration Manager заполнит соответствующее имя канала.</span><span class="sxs-lookup"><span data-stu-id="ea792-114">Alternatively, you can leave **Pipe Name** blank and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager will complete the appropriate pipe name after you specify the **Protocol** and **Server**</span></span>  
  
-   <span data-ttu-id="ea792-115">Укажите **сервер**.</span><span class="sxs-lookup"><span data-stu-id="ea792-115">Specify a **Server**.</span></span> <span data-ttu-id="ea792-116">Для именованного экземпляра можно ввести имя сервера и имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ea792-116">For a named instance you can provide a server name and instance name.</span></span>  
  
 <span data-ttu-id="ea792-117">Во время подключения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] компонент собственного клиента считывает значения имени сервера, протокола и канала из реестра для указанного имени псевдонима и создает имя канала в формате `np:\\<computer_name>\pipe\<pipename>` или `np:\\<IPAddress>\pipe\<pipename>` . Для именованного экземпляра имя канала по умолчанию — `\\<computer_name>\pipe\MSSQL$<instance_name>\sql\query` .</span><span class="sxs-lookup"><span data-stu-id="ea792-117">At the time of connection, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client component reads the server, protocol, and pipe name values from the registry for the specified alias name, and creates a pipe name in the format `np:\\<computer_name>\pipe\<pipename>` or `np:\\<IPAddress>\pipe\<pipename>`.For a named instance, the default pipe name is `\\<computer_name>\pipe\MSSQL$<instance_name>\sql\query`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea792-118">Брандмауэр Windows [!INCLUDE[msCoName](../../includes/msconame-md.md)] по умолчанию закрывает порт 445.</span><span class="sxs-lookup"><span data-stu-id="ea792-118">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall closes port 445 by default.</span></span> <span data-ttu-id="ea792-119">Так как [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] осуществляет связь через порт 445, необходимо повторно открыть порт, если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настроен для прослушивания клиентских подключений с помощью именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="ea792-119">Because [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communicates over port 445, you must reopen the port if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to listen for incoming client connections using named pipes.</span></span> <span data-ttu-id="ea792-120">Информацию о настройке брандмауэра см. в статье "Настройка брандмауэра Windows для разрешения доступа к SQL Server" в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или документации по вашей версии брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="ea792-120">For information on configuring a firewall, see "How to: Configure a Firewall for SQL Server Access" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or review your firewall documentation.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="ea792-121">Подключение к локальному серверу</span><span class="sxs-lookup"><span data-stu-id="ea792-121">Connecting to the Local Server</span></span>  
 <span data-ttu-id="ea792-122">При подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], выполняющемуся на том же компьютере, что и клиент, в качестве имени сервера можно использовать `(local)`.</span><span class="sxs-lookup"><span data-stu-id="ea792-122">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use `(local)`as the server name.</span></span> <span data-ttu-id="ea792-123">Применение `(local)` не рекомендуется, поскольку может вызвать неоднозначность, но может быть полезным, если известно, что клиент запущен на нужном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ea792-123">Using `(local)` is not encouraged because it leads to ambiguity; however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="ea792-124">Например, при создании приложения для мобильных отключенных пользователей, таких как торговый персонал, когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет запускаться на переносных компьютерах и использоваться для хранения данных проекта, клиент, подключающийся к (local), будет всегда подключаться к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], выполняющемуся на переносном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ea792-124">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to (local) would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="ea792-125">Слово `localhost` или точку (.) можно использовать вместо `(local)`.</span><span class="sxs-lookup"><span data-stu-id="ea792-125">The word `localhost` or a period (.) can be used in place of `(local)`.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="ea792-126">Проверка протокола соединения</span><span class="sxs-lookup"><span data-stu-id="ea792-126">Verifying Your Connection Protocol</span></span>  
 <span data-ttu-id="ea792-127">Следующий запрос возвратит протокол, используемый в текущем соединении.</span><span class="sxs-lookup"><span data-stu-id="ea792-127">The following query will return the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="ea792-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="ea792-128">Examples</span></span>  
 <span data-ttu-id="ea792-129">Подключение по имени сервера к каналу по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="ea792-129">Connecting by server name to the default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <blank>  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="ea792-130">Подключение по IP-адресу к каналу по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="ea792-130">Connecting by IP Address to the default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <leave blank>  
Protocol           Named Pipes  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="ea792-131">Подключение по имени сервера к каналу, отличному от канала по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="ea792-131">Connecting by server name to a non-default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          \\<servername>\pipe\unit\app  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="ea792-132">Подключение по имени сервера к именованному экземпляру:</span><span class="sxs-lookup"><span data-stu-id="ea792-132">Connecting by server name to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          \\<servername>\pipe\MSSQL$<instancename>\SQL\query  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="ea792-133">Подключение к локальному компьютеру при помощи `localhost`:</span><span class="sxs-lookup"><span data-stu-id="ea792-133">Connecting to the local computer using `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <blank>  
Protocol           Named Pipes  
Server             localhost  
  
```  
  
 <span data-ttu-id="ea792-134">Соединение с локальным компьютером при помощи точки:</span><span class="sxs-lookup"><span data-stu-id="ea792-134">Connecting to the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <left blank>  
Protocol           Named Pipes  
Server             .  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ea792-135">Сведения об указании сетевого протокола в качестве параметра **sqlcmd** см. в разделе «как подключиться к ядро СУБД с помощью sqlcmd.exe» [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] электронной документации по.</span><span class="sxs-lookup"><span data-stu-id="ea792-135">To specify the network protocol as a **sqlcmd** parameter, see "How to: Connect to the Database Engine Using sqlcmd.exe" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea792-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea792-136">See Also</span></span>  
 <span data-ttu-id="ea792-137">[Создание допустимой строки подключения с помощью протокола общей памяти](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="ea792-137">[Creating a Valid Connection String Using Shared Memory Protocol](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span></span>  
 <span data-ttu-id="ea792-138">[Создание допустимой строки подключения с помощью IP-адреса TCP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span><span class="sxs-lookup"><span data-stu-id="ea792-138">[Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span></span>  
 [<span data-ttu-id="ea792-139">Выбор сетевого протокола</span><span class="sxs-lookup"><span data-stu-id="ea792-139">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
