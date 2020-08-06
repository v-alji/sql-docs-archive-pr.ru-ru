---
title: Сетевые протоколы и библиотеки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- protocols [SQL Server]
- configuration options [SQL Server], protocols
- network libraries [SQL Server]
- protocols [SQL Server], about network protocols
- pipes [SQL Server]
- network protocols [SQL Server]
- default SQL Server configurations
- library [SQL Server]
- network protocols [SQL Server], about network protocols
- configuration options [SQL Server], libraries
ms.assetid: 8cd437f6-9af1-44ce-9cb0-4d10c83da9ce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8be012ea2bc9499a99ca7763446c6f26cf219a18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668043"
---
# <a name="network-protocols-and-network-libraries"></a><span data-ttu-id="73cc6-102">Сетевые протоколы и библиотеки</span><span class="sxs-lookup"><span data-stu-id="73cc6-102">Network Protocols and Network Libraries</span></span>
  <span data-ttu-id="73cc6-103">Сервер может одновременно прослушивать или отслеживать работу нескольких сетевых протоколов.</span><span class="sxs-lookup"><span data-stu-id="73cc6-103">A server can listen on, or monitor, multiple network protocols at one time.</span></span> <span data-ttu-id="73cc6-104">Однако каждый из этих протоколов должен быть настроен.</span><span class="sxs-lookup"><span data-stu-id="73cc6-104">However, each protocol must be configured.</span></span> <span data-ttu-id="73cc6-105">Если какой-нибудь из протоколов не настроен, сервер не сможет его прослушивать.</span><span class="sxs-lookup"><span data-stu-id="73cc6-105">If a particular protocol is not configured, the server cannot listen on that protocol.</span></span> <span data-ttu-id="73cc6-106">После установки можно изменить конфигурации протоколов при помощи диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73cc6-106">After installation, you can change the protocol configurations using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="default-sql-server-network-configuration"></a><span data-ttu-id="73cc6-107">Сетевая конфигурация SQL Server по умолчанию</span><span class="sxs-lookup"><span data-stu-id="73cc6-107">Default SQL Server Network Configuration</span></span>  
 <span data-ttu-id="73cc6-108">В экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по умолчанию настроен порт TCP/IP 1433 и именованный канал \\\\.\pipe\sql\query.</span><span class="sxs-lookup"><span data-stu-id="73cc6-108">A default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured for TCP/IP port 1433, and named pipe \\\\.\pipe\sql\query.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="73cc6-109">задаются динамические порты TCP, при этом номер порта назначается операционной системой.</span><span class="sxs-lookup"><span data-stu-id="73cc6-109">named instances are configured for TCP dynamic ports, with a port number assigned by the operating system.</span></span>  
  
 <span data-ttu-id="73cc6-110">Если использование динамических номеров портов невозможно (например, если соединения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должны проходить через брандмауэр, настроенный на пропуск пакетов через конкретные номера портов).</span><span class="sxs-lookup"><span data-stu-id="73cc6-110">If you cannot use dynamic port addresses (for example, when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections must pass through a firewall server configured to pass through specific port addresses).</span></span> <span data-ttu-id="73cc6-111">Выберите незанятый номер порта.</span><span class="sxs-lookup"><span data-stu-id="73cc6-111">Select an unassigned port number.</span></span> <span data-ttu-id="73cc6-112">Присваиванием номеров портов управляет администрация адресного пространства Интернет (IANA), а списки этих номеров находятся по адресу [http://www.iana.org](https://go.microsoft.com/fwlink/?LinkId=48844).</span><span class="sxs-lookup"><span data-stu-id="73cc6-112">Port number assignments are managed by the Internet Assigned Numbers Authority and are listed at [http://www.iana.org](https://go.microsoft.com/fwlink/?LinkId=48844).</span></span>  
  
 <span data-ttu-id="73cc6-113">В целях повышения безопасности при установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] сетевой обмен данными включен не полностью.</span><span class="sxs-lookup"><span data-stu-id="73cc6-113">To enhance security, network connectivity is not fully enabled when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span> <span data-ttu-id="73cc6-114">Чтобы включить, отключить или настроить сетевые протоколы после завершения программы установки, используется область «Конфигурация сети [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] » диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73cc6-114">To enable, disable, and configure network protocols after Setup is complete, use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Network Configuration area of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="server-message-block-protocol"></a><span data-ttu-id="73cc6-115">Протокол SMB</span><span class="sxs-lookup"><span data-stu-id="73cc6-115">Server Message Block Protocol</span></span>  
 <span data-ttu-id="73cc6-116">На серверах в демилитаризованной зоне сети необходимо отключить все ненужные протоколы, в том числе протокол SMB.</span><span class="sxs-lookup"><span data-stu-id="73cc6-116">Servers in the perimeter network should have all unnecessary protocols disabled, including server message block (SMB).</span></span> <span data-ttu-id="73cc6-117">Веб-серверам и DNS-серверам не нужен протокол SMB.</span><span class="sxs-lookup"><span data-stu-id="73cc6-117">Web servers and Domain Name System (DNS) servers do not require SMB.</span></span> <span data-ttu-id="73cc6-118">Этот протокол необходимо отключить, чтобы противостоять угрозе сбора сведений о пользователях.</span><span class="sxs-lookup"><span data-stu-id="73cc6-118">This protocol should be disabled to counter the threat of user enumeration.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="73cc6-119">Отключение протокола SMB заблокирует доступ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или службы кластеров Windows к удаленной общей папке.</span><span class="sxs-lookup"><span data-stu-id="73cc6-119">Disabling Server Message Block will block the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or Windows Cluster service from accessing the remote file share.</span></span> <span data-ttu-id="73cc6-120">Не отключайте протокол SMB, если выполняется или планируется одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="73cc6-120">Do not disable SMB if you do or plan to do one of the following:</span></span>  
> 
>  -   <span data-ttu-id="73cc6-121">Использование режима кворума большинства общих папок и узлов кластера Windows</span><span class="sxs-lookup"><span data-stu-id="73cc6-121">Use Windows Cluster Node and File Share Majority Quorum mode</span></span>  
> -   <span data-ttu-id="73cc6-122">Указание общей папки SMB в качестве каталога данных во время установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73cc6-122">Specify an SMB file share as the data directory during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation</span></span>  
> -   <span data-ttu-id="73cc6-123">Создание файла базы данных в общей папке SMB</span><span class="sxs-lookup"><span data-stu-id="73cc6-123">Create a database file on an SMB file share</span></span>  
  
#### <a name="to-disable-smb"></a><span data-ttu-id="73cc6-124">Отключение протоколаSMB</span><span class="sxs-lookup"><span data-stu-id="73cc6-124">To disable SMB</span></span>  
  
1.  <span data-ttu-id="73cc6-125">В меню **Пуск** выберите **Настройки**и щелкните **Сетевые подключения и коммутируемые соединения**.</span><span class="sxs-lookup"><span data-stu-id="73cc6-125">On the **Start** menu, point to **Settings**, and then click **Network and Dial-up Connections**.</span></span>  
  
     <span data-ttu-id="73cc6-126">Щелкните правой кнопкой мыши ярлык соединения с Интернетом и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="73cc6-126">Right-click the Internet-facing connection, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="73cc6-127">Установите флажок **Клиент для сетей Microsoft** и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="73cc6-127">Select the **Client for Microsoft Networks** check box, and then click **Uninstall**.</span></span>  
  
3.  <span data-ttu-id="73cc6-128">Выполните шаги для удаления.</span><span class="sxs-lookup"><span data-stu-id="73cc6-128">Follow the uninstall steps.</span></span>  
  
4.  <span data-ttu-id="73cc6-129">Выберите **Службу доступа к файлам и принтерам сетей Microsoft**и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="73cc6-129">Select **File and Printer Sharing for Microsoft Networks**, and then click **Uninstall**.</span></span>  
  
5.  <span data-ttu-id="73cc6-130">Выполните шаги для удаления.</span><span class="sxs-lookup"><span data-stu-id="73cc6-130">Follow the uninstall steps.</span></span>  
  
#### <a name="to-disable-smb-on-servers-accessible-from-the-internet"></a><span data-ttu-id="73cc6-131">Отключение протокола SMB на серверах, доступных из Интернета</span><span class="sxs-lookup"><span data-stu-id="73cc6-131">To disable SMB on servers accessible from the Internet</span></span>  
  
-   <span data-ttu-id="73cc6-132">В окне "Соединение по локальной сети — свойства" используйте диалоговое окно **Свойства: протокол Интернета (TCP/IP)** , чтобы удалить компоненты **Совместный доступ к файлам и принтерам сетей Microsoft** и **Клиент для сетей Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="73cc6-132">In the Local Area Connection properties, use the **Transmission Control Protocol/Internet Protocol (TCP/IP) properties** dialog box to remove **File and Printer Sharing for Microsoft Networks** and **Client for Microsoft Networks**.</span></span>  
  
## <a name="endpoints"></a><span data-ttu-id="73cc6-133">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="73cc6-133">Endpoints</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="73cc6-134">для соединений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] введена новая концепция. Соединение представляется на стороне сервера в виде [!INCLUDE[tsql](../../includes/tsql-md.md)]*конечной точки*.</span><span class="sxs-lookup"><span data-stu-id="73cc6-134">introduces a new concept for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections; the connection is represented on the server end by a [!INCLUDE[tsql](../../includes/tsql-md.md)]*endpoint*.</span></span> <span data-ttu-id="73cc6-135">Для конечных точек [!INCLUDE[tsql](../../includes/tsql-md.md)] можно предоставлять, отменять и запрещать разрешения.</span><span class="sxs-lookup"><span data-stu-id="73cc6-135">Permissions can be granted, revoked, and denied for [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoints.</span></span> <span data-ttu-id="73cc6-136">По умолчанию все пользователи имеют разрешения на подключение к конечной точке, если только это разрешение не отменено и не запрещено членом группы sysadmin или владельцем конечной точки.</span><span class="sxs-lookup"><span data-stu-id="73cc6-136">By default, all users have permissions to access an endpoint unless the permissions are denied or revoked by a member of the sysadmin group or by the endpoint owner.</span></span> <span data-ttu-id="73cc6-137">В синтаксисе GRANT, REVOKE и DENY ENDPOINT применяется идентификатор, который администратор должен получить из представления каталога конечной точки.</span><span class="sxs-lookup"><span data-stu-id="73cc6-137">The GRANT, REVOKE, and DENY ENDPOINT syntax uses an endpoint ID that the administrator must get from the endpoint's catalog view.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="73cc6-138">создает конечные точки [!INCLUDE[tsql](../../includes/tsql-md.md)] для всех поддерживаемых сетевых протоколов, а также для выделенного административного соединения.</span><span class="sxs-lookup"><span data-stu-id="73cc6-138">Setup creates [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoints for all supported network protocols, as well as for the dedicated administrator connection.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="73cc6-139">создаются программой установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] следующим образом.</span><span class="sxs-lookup"><span data-stu-id="73cc6-139">endpoints created by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup are as follows:</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="73cc6-140">локальный компьютер</span><span class="sxs-lookup"><span data-stu-id="73cc6-140">local machine</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="73cc6-141">именованные каналы</span><span class="sxs-lookup"><span data-stu-id="73cc6-141">named pipes</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="73cc6-142">по умолчанию</span><span class="sxs-lookup"><span data-stu-id="73cc6-142">default TCP</span></span>  
  
 <span data-ttu-id="73cc6-143">Дополнительные сведения о конечных точках см. в разделах [Настройка ядра СУБД на прослушивание нескольких портов TCP](../../database-engine/configure-windows/configure-the-database-engine-to-listen-on-multiple-tcp-ports.md) и [Представления каталога конечных точек (Transact-SQL)](/sql/relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="73cc6-143">For more information about endpoints, see [Configure the Database Engine to Listen on Multiple TCP Ports](../../database-engine/configure-windows/configure-the-database-engine-to-listen-on-multiple-tcp-ports.md) and [Endpoints Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql).</span></span>  
  
 <span data-ttu-id="73cc6-144">Дополнительные сведения о конфигурациях сети [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в следующей статье электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="73cc6-144">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network configurations, see the following topic in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   [<span data-ttu-id="73cc6-145">Сетевая конфигурация сервера</span><span class="sxs-lookup"><span data-stu-id="73cc6-145">Server Network Configuration</span></span>](../../database-engine/configure-windows/server-network-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="73cc6-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="73cc6-146">See Also</span></span>  
 <span data-ttu-id="73cc6-147">[Настройка контактной зоны](../../relational-databases/security/surface-area-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="73cc6-147">[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md) </span></span>  
 <span data-ttu-id="73cc6-148">[Вопросы безопасности при установке SQL Server](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="73cc6-148">[Security Considerations for a SQL Server Installation](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="73cc6-149">Планирование установки SQL Server</span><span class="sxs-lookup"><span data-stu-id="73cc6-149">Planning a SQL Server Installation</span></span>](../../../2014/sql-server/install/planning-a-sql-server-installation.md)  
  
  
