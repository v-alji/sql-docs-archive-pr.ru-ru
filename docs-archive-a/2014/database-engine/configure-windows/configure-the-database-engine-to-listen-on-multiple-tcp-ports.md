---
title: Настройка компонента Database Engine на прослушивание нескольких портов TCP | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- ports [SQL Server], multiple
- TDS
- listen on multiple ports
- endpoints [SQL Server], TDS
- adding ports
- tabular data stream
- multiple ports
ms.assetid: 8e955033-06ef-403f-b813-3d8241b62f1f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab803bcaa5ab6b6187c1a994abef02f81ae105c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655954"
---
# <a name="configure-the-database-engine-to-listen-on-multiple-tcp-ports"></a><span data-ttu-id="2a6c2-102">Настройка компонента Database Engine на прослушивание нескольких портов TCP</span><span class="sxs-lookup"><span data-stu-id="2a6c2-102">Configure the Database Engine to Listen on Multiple TCP Ports</span></span>
  <span data-ttu-id="2a6c2-103">В этой теме описан процесс настройки компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] для прослушивания нескольких портов на [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-103">This topic describes how to configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on multiple TCP ports in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="2a6c2-104">При включении TCP/IP для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] будет прослушивать входящие соединения в точке соединения по IP-адресу и номеру порта TCP. В результате выполнения следующих процедур будет создана конечная точка потока табличных данных (TDS), чтобы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] мог прослушивать соединения на дополнительном порту TCP.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-104">When TCP/IP is enabled for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will listen for incoming connections on a connection point consisting of an IP address and TCP port number.The following procedures create a tabular data stream (TDS) endpoint, so that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will listen on an additional TCP port.</span></span>  
  
 <span data-ttu-id="2a6c2-105">Ниже перечислены возможные причины создания второй конечной точки TDS.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-105">Possible reasons to create a second TDS endpoint include:</span></span>  
  
-   <span data-ttu-id="2a6c2-106">Усиление безопасности путем настройки брандмауэра для предоставления доступа к конечной точке по умолчанию только локальным клиентским компьютерам в определенной подсети.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-106">Increase security by configuring the firewall to restrict access to the default endpoint to local client computers on a specific subnet.</span></span> <span data-ttu-id="2a6c2-107">Обеспечьте доступ к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из Интернета для команды поддержки путем создания новой конечной точки, которую брандмауэр делает видимой из Интернета, и предоставьте права на соединение с этой конечной точкой только команде поддержки сервера.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-107">Maintain Internet access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for your support team by creating a new endpoint that the firewall exposes to the Internet, and restricting connection rights to this endpoint to your server support team.</span></span>  
  
-   <span data-ttu-id="2a6c2-108">Установка соответствия соединений определенным процессорам при использовании технологии доступа к неоднородной памяти (NUMA).</span><span class="sxs-lookup"><span data-stu-id="2a6c2-108">Affinitizing connections to specific processors when using Non-Uniform Memory Access (NUMA).</span></span>  
  
 <span data-ttu-id="2a6c2-109">Настройка конечной точки TDS включает в себя следующие шаги, которые могут быть выполнены в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-109">Configuring a TDS endpoint consists of the following steps, which can be done in any order:</span></span>  
  
-   <span data-ttu-id="2a6c2-110">Создайте конечную точку TDS для порта TCP и восстановите доступ к конечной точке по умолчанию, если необходимо.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-110">Create the TDS endpoint for the TCP port, and restore access to the default endpoint if appropriate.</span></span>  
  
-   <span data-ttu-id="2a6c2-111">Предоставьте необходимым участникам на уровне сервера доступ к конечной точке.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-111">Grant access to the endpoint to the desired server principals.</span></span>  
  
-   <span data-ttu-id="2a6c2-112">Укажите номер порта TCP для выбранного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-112">Specify the TCP port number for the selected IP address.</span></span>  
  
 <span data-ttu-id="2a6c2-113">Дополнительные сведения о настройках брандмауэра Windows по умолчанию и описание портов TCP, влияющих на компонент Database Engine, службы Analysis Services, службы Reporting Services и службы Integration Services, см. в разделе [Настройка брандмауэра Windows для разрешения доступа к SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="2a6c2-113">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the Database Engine, Analysis Services, Reporting Services, and Integration Services, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-create-a-tds-endpoint"></a><span data-ttu-id="2a6c2-114">Создание конечной точки TDS</span><span class="sxs-lookup"><span data-stu-id="2a6c2-114">To create a TDS endpoint</span></span>  
  
-   <span data-ttu-id="2a6c2-115">Выполните следующую инструкцию, чтобы создать конечную точку с именем **CustomConnection** для порта 1500 на всех доступных адресах TCP сервера.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-115">Issue the following statement to create an endpoint named **CustomConnection** for port 1500 for all available TCP addresses on the server.</span></span>  
  
    ```  
    USE master;  
    GO  
    CREATE ENDPOINT [CustomConnection]  
    STATE = STARTED  
    AS TCP  
       (LISTENER_PORT = 1500, LISTENER_IP =ALL)  
    FOR TSQL() ;  
    GO  
    ```  
  
 <span data-ttu-id="2a6c2-116">При создании новой конечной точки [!INCLUDE[tsql](../../includes/tsql-md.md)] разрешения на соединение с конечной точкой потока табличных данных по умолчанию для группы **public** отменяются.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-116">When you create a new [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoint, connect permissions for **public** are revoked for the default TDS endpoint.</span></span> <span data-ttu-id="2a6c2-117">Если группе **public** требуется доступ к конечной точке по умолчанию, то ей необходимо предоставить это разрешение, выполнив инструкцию `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` .</span><span class="sxs-lookup"><span data-stu-id="2a6c2-117">If access to the **public** group is needed for the default endpoint, reapply this permission by using the `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` statement.</span></span>  
  
#### <a name="to-grant-access-to-the-endpoint"></a><span data-ttu-id="2a6c2-118">Предоставление доступа к конечной точке</span><span class="sxs-lookup"><span data-stu-id="2a6c2-118">To grant access to the endpoint</span></span>  
  
-   <span data-ttu-id="2a6c2-119">Выполните следующую инструкцию, чтобы предоставить группе SQLSupport домена corp доступ к конечной точке **CustomConnection** .</span><span class="sxs-lookup"><span data-stu-id="2a6c2-119">Issue the following statement to grant access to the **CustomConnection** endpoint to the SQLSupport group in the corp domain.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[CustomConnection] to [corp\SQLSupport] ;  
    GO  
    ```  
  
#### <a name="to-configure-the-sql-server-database-engine-to-listen-on-an-additional-tcp-port"></a><span data-ttu-id="2a6c2-120">Настройка компонента SQL Server Database Engine на прослушивание дополнительного порта TCP</span><span class="sxs-lookup"><span data-stu-id="2a6c2-120">To configure the SQL Server Database Engine to listen on an additional TCP port</span></span>  
  
1.  <span data-ttu-id="2a6c2-121">В диспетчере конфигурации SQL Server разверните узел **Сетевая конфигурация SQL Server** и щелкните элемент **Протоколы для** _<имя_экземпляра>_ .</span><span class="sxs-lookup"><span data-stu-id="2a6c2-121">In SQL Server Configuration Manager, expand **SQL Server Network Configuration**, and then click **Protocols for**_<instance_name>_.</span></span>  
  
2.  <span data-ttu-id="2a6c2-122">Разверните узел **Протоколы для** _<имя_экземпляра>_ и щелкните **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-122">Expand **Protocols for**_<instance_name>_, and then click **TCP/IP**.</span></span>  
  
3.  <span data-ttu-id="2a6c2-123">В правой панели щелкните правой кнопкой мыши отключенный IP-адрес, который необходимо включить, и выберите **Включить**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-123">In the right pane, right-click each disabled IP address that you want to enable, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="2a6c2-124">Щелкните правой кнопкой мыши **IPAll**и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-124">Right-click **IPAll**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="2a6c2-125">В поле **TCP-порт** введите номера портов, которые должны прослушиваться компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)] , разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-125">In the **TCP Port** box, type the ports that you want the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on, separated by commas.</span></span> <span data-ttu-id="2a6c2-126">В нашем примере, если указан порт по умолчанию 1433, введите `,1500` , чтобы поле было прочитано `1433,1500` , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-126">In our example, if the default port 1433 is listed, type `,1500` so the box reads `1433,1500`, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a6c2-127">Если порт включается не для всех IP-адресов, настройте дополнительный порт в окне свойств только для необходимого адреса.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-127">If you are not enabling the port on all IP addresses, configure the additional port in the property box for only for the desired address.</span></span> <span data-ttu-id="2a6c2-128">Затем на панели консоли щелкните правой кнопкой мыши **TCP/IP**, выберите пункт **Свойства**и в поле **Прослушивать все** выберите **Нет**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-128">Then, in the console pane, right-click **TCP/IP**, click **Properties**, and in the **Listen All** box, select **No**.</span></span>  
  
6.  <span data-ttu-id="2a6c2-129">На левой панели щелкните **Службы SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-129">In the left pane, click **SQL Server Services**.</span></span>  
  
7.  <span data-ttu-id="2a6c2-130">На правой панели щелкните правой кнопкой мыши **SQL Server** _<имя_экземпляра>_ и выберите **Перезагрузка**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-130">In the right pane, right-click **SQL Server**_<instance_name>_, and then click **Restart**.</span></span>  
  
     <span data-ttu-id="2a6c2-131">После перезагрузки компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] журнал ошибок будет содержать список портов, прослушиваемых [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a6c2-131">When the [!INCLUDE[ssDE](../../includes/ssde-md.md)] restarts, the Error log will list the ports on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening.</span></span>  
  
#### <a name="to-connect-to-the-new-endpoint"></a><span data-ttu-id="2a6c2-132">Подключение к новой конечной точке</span><span class="sxs-lookup"><span data-stu-id="2a6c2-132">To connect to the new endpoint</span></span>  
  
-   <span data-ttu-id="2a6c2-133">Выполните следующую инструкцию, чтобы подключиться к конечной точке **CustomConnection** экземпляра SQL Server по умолчанию на сервере с именем ACCT, используя доверительное соединение, предполагая, что пользователь является членом группы [corp\SQLSupport].</span><span class="sxs-lookup"><span data-stu-id="2a6c2-133">Issue the following statement to connect to the **CustomConnection** endpoint of the default instance of SQL Server on the server named ACCT, using a trusted connection, and assuming the user is a member of the [corp\SQLSupport] group.</span></span>  
  
    ```  
    sqlcmd -SACCT,1500  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2a6c2-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a6c2-134">See Also</span></span>  
 <span data-ttu-id="2a6c2-135">[CREATE ENDPOINT (Transact-SQL)](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a6c2-135">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="2a6c2-136">[DROP ENDPOINT (Transact-SQL)](/sql/t-sql/statements/drop-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a6c2-136">[DROP ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="2a6c2-137">[GRANT, предоставление разрешений конечной точке (Transact-SQL)](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a6c2-137">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span></span>  
 [<span data-ttu-id="2a6c2-138">Сопоставление портов TCP/IP с узлами NUMA (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2a6c2-138">Map TCP IP Ports to NUMA Nodes &#40;SQL Server&#41;</span></span>](map-tcp-ip-ports-to-numa-nodes-sql-server.md)  
  
  
