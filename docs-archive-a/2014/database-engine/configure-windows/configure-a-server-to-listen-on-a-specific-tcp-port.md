---
title: Настройка сервера для прослушивания определенного TCP-порта (диспетчер конфигурации SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- fixed port
- static ports
- ports [SQL Server], assigning numbers
- assigning port numbers
- dynamic ports [SQL Server]
- TCP/IP [SQL Server], port numbers
ms.assetid: 2276a5ed-ae3f-4855-96d8-f5bf01890640
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4feb740910c65580e8ea3170d03481e6cb628860
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655365"
---
# <a name="configure-a-server-to-listen-on-a-specific-tcp-port-sql-server-configuration-manager"></a><span data-ttu-id="f8ecf-102">Настройка сервера для прослушивания указанного TCP-порта (диспетчер конфигурации SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f8ecf-102">Configure a Server to Listen on a Specific TCP Port (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="f8ecf-103">В этом разделе описано, как настроить экземпляр компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] для прослушивания определенного фиксированного порта с помощью диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-103">This topic describes how to configure an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] to listen on a specific fixed port by using the SQL Server Configuration Manager.</span></span> <span data-ttu-id="f8ecf-104">Если прослушивание включено, то экземпляр компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] по умолчанию прослушивает TCP-порт 1433.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-104">If enabled, the default instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] listens on TCP port 1433.</span></span> <span data-ttu-id="f8ecf-105">Именованные экземпляры компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и [!INCLUDE[ssEW](../../includes/ssew-md.md)] настроены для использования динамических портов.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-105">Named instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssEW](../../includes/ssew-md.md)] are configured for dynamic ports.</span></span> <span data-ttu-id="f8ecf-106">Это означает, что при запуске службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для них выбирается свободный порт.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-106">This means they select an available port when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service is started.</span></span> <span data-ttu-id="f8ecf-107">При соединении с именованным экземпляром через брандмауэр необходимо настроить компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] на прослушивание определенного порта. Это позволит открыть в брандмауэре необходимый порт.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-107">When you are connecting to a named instance through a firewall, configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on a specific port, so that the appropriate port can be opened in the firewall.</span></span>  
  
 <span data-ttu-id="f8ecf-108">Дополнительные сведения о настройках брандмауэра Windows по умолчанию и описание портов TCP, влияющих на компонент Database Engine, службы Analysis Services, службы Reporting Services и службы Integration Services, см. в разделе [Настройка брандмауэра Windows для разрешения доступа к SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="f8ecf-108">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the Database Engine, Analysis Services, Reporting Services, and Integration Services, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="f8ecf-109">При выборе номера порта руководствуйтесь приведенным по адресу [http://www.iana.org/assignments/port-numbers](http://www.iana.org/assignments/port-numbers) списком номеров портов, которые назначаются конкретным приложениям.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-109">When selecting a port number, consult [http://www.iana.org/assignments/port-numbers](http://www.iana.org/assignments/port-numbers) for a list of port numbers that are assigned to specific applications.</span></span> <span data-ttu-id="f8ecf-110">Выберите незанятый номер порта.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-110">Select an unassigned port number.</span></span> <span data-ttu-id="f8ecf-111">Дополнительные сведения см. в разделе [Предусмотренный по умолчанию динамический диапазон портов для TCP/IP, который изменился в Windows Vista и Windows Server 2008](https://support.microsoft.com/kb/929851).</span><span class="sxs-lookup"><span data-stu-id="f8ecf-111">For more information, see [The default dynamic port range for TCP/IP has changed in Windows Vista and in Windows Server 2008](https://support.microsoft.com/kb/929851).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="f8ecf-112">Компонент Database Engine начнет прослушивание нового порта после перезапуска.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-112">The Database Engine begins listening on a new port when restarted.</span></span> <span data-ttu-id="f8ecf-113">Однако служба браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отслеживает реестр и возвращает новый номер порта, как только будет изменена конфигурация, даже если компонент Database Engine его не использует.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-113">However the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service monitors the registry and reports the new port number as soon as the configuration is changed, even though the Database Engine might not be using it.</span></span> <span data-ttu-id="f8ecf-114">Перезапустите компонент Database Engine, чтобы обеспечить согласованность и избежать ошибок соединения.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-114">Restart the Database Engine to ensure consistency and avoid connection failures.</span></span>  
  
 <span data-ttu-id="f8ecf-115">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f8ecf-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f8ecf-116">**Настройка сервера для прослушивания определенного TCP-порта с помощью:**</span><span class="sxs-lookup"><span data-stu-id="f8ecf-116">**To configure a server to listen on a specific TCP port, using:**</span></span>  
  
     [<span data-ttu-id="f8ecf-117">Диспетчер конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="f8ecf-117">SQL Server Configuration Manager</span></span>](#SSMSProcedure)  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f8ecf-118">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="f8ecf-118">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-assign-a-tcpip-port-number-to-the-sql-server-database-engine"></a><span data-ttu-id="f8ecf-119">Назначение ядру СУБД SQL Server порта TCP/IP</span><span class="sxs-lookup"><span data-stu-id="f8ecf-119">To assign a TCP/IP port number to the SQL Server Database Engine</span></span>  
  
1.  <span data-ttu-id="f8ecf-120">В области консоли диспетчера конфигурации SQL Server разверните узел **Сетевая конфигурация SQL Server**, **Протоколы для \<instance name>** , а затем дважды щелкните **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-120">In SQL Server Configuration Manager, in the console pane, expand **SQL Server Network Configuration**, expand **Protocols for \<instance name>**, and then double-click **TCP/IP**.</span></span>  
  
2.  <span data-ttu-id="f8ecf-121">В диалоговом окне **Свойства TCP/IP** на вкладке **IP-адреса** появится несколько IP-адресов в формате **IP1**, **IP2**до **IPAll**.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-121">In the **TCP/IP Properties** dialog box, on the **IP Addresses** tab, several IP addresses appear in the format **IP1**, **IP2**, up to **IPAll**.</span></span> <span data-ttu-id="f8ecf-122">Одним из приведенных IP-адресов является адрес адаптера заглушки 127.0.0.1.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-122">One of these is for the IP address of the loopback adapter, 127.0.0.1.</span></span> <span data-ttu-id="f8ecf-123">Для каждого IP-адреса на компьютере появляются дополнительные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-123">Additional IP addresses appear for each IP Address on the computer.</span></span> <span data-ttu-id="f8ecf-124">Чтобы определить настраиваемый IP-адрес, щелкните правой кнопкой мыши каждый адрес и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-124">Right-click each address, and then click **Properties** to identify the IP address that you want to configure.</span></span>  
  
3.  <span data-ttu-id="f8ecf-125">Если в диалоговом окне **Динамические порты TCP** содержится значение **0**, означающее прослушивание компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)] динамических портов, удалите его.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-125">If the **TCP Dynamic Ports** dialog box contains **0**, indicating the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is listening on dynamic ports, delete the 0.</span></span>  
  
4.  <span data-ttu-id="f8ecf-126">В области окна**IP**_n_ — **свойства** в поле **Порт TCP** введите номер порта, который необходимо прослушивать по этому IP-адресу, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-126">In the **IP**_n_ **Properties** area box, in the **TCP Port** box, type the port number you want this IP address to listen on, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="f8ecf-127">В области консоли выберите **Службы SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-127">In the console pane, click **SQL Server Services**.</span></span>  
  
6.  <span data-ttu-id="f8ecf-128">В области сведений щелкните правой кнопкой мыши **SQL Server (** \<instance name> **)** и выберите команду **Перезапустить**, чтобы остановить и снова запустить [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8ecf-128">In the details pane, right-click **SQL Server (**\<instance name>**)** and then click **Restart**, to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f8ecf-129">После настройки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на прослушивание определенного порта установить соединение с ним с помощью клиентского приложения можно тремя способами:</span><span class="sxs-lookup"><span data-stu-id="f8ecf-129">After you have configured [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to listen on a specific port, there are three ways to connect to a specific port with a client application:</span></span>  
  
-   <span data-ttu-id="f8ecf-130">Запустите службу браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на сервере для подключения к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] по имени.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-130">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server to connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance by name.</span></span>  
  
-   <span data-ttu-id="f8ecf-131">Создайте псевдоним на клиенте, указав номер порта.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-131">Create an alias on the client, specifying the port number.</span></span>  
  
-   <span data-ttu-id="f8ecf-132">Настройте клиент на использование пользовательской строки подключения.</span><span class="sxs-lookup"><span data-stu-id="f8ecf-132">Program the client to connect using a custom connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ecf-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8ecf-133">See Also</span></span>  
 [<span data-ttu-id="f8ecf-134">Создание или удаление псевдонима сервера для использования клиентом (диспетчер конфигурации SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f8ecf-134">Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;</span></span>](create-or-delete-a-server-alias-for-use-by-a-client.md)  
  
  
