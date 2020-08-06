---
title: Настройка клиентских протоколов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default protocols
- network protocols [SQL Server], client configuration
- TCP/IP [SQL Server], client protocols
- disabling client protocols
- ordering protocols [SQL Server]
- protocols [SQL Server], order for client computers
- configure client protocols
- client protocols [SQL Server]
- protocols [SQL Server], client configuration
ms.assetid: 3dfa2702-ba65-43b4-a777-6727846e133a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2eb223815c3e3af50813e02d3ded60573c327155
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669114"
---
# <a name="configure-client-protocols"></a><span data-ttu-id="eef3d-102">настройка клиентских протоколов</span><span class="sxs-lookup"><span data-stu-id="eef3d-102">Configure Client Protocols</span></span>
  <span data-ttu-id="eef3d-103">В этом разделе описано, как настроить клиентские протоколы, используемые клиентскими приложениями [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], с помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eef3d-103">This topic describes how to configure client protocols used by client applications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="eef3d-104">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает клиентский обмен данными через сетевой протокол TCP/IP и протокол именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="eef3d-104">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports client communication with the TCP/IP network protocol and the named pipes protocol.</span></span> <span data-ttu-id="eef3d-105">Может также использоваться протокол общей памяти, если клиент устанавливает соединение с экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="eef3d-105">The shared memory protocol is also available if the client is connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the same computer.</span></span> <span data-ttu-id="eef3d-106">Существуют три наиболее часто используемых способа для выбора протокола.</span><span class="sxs-lookup"><span data-stu-id="eef3d-106">There are three common methods of selecting the protocol.</span></span>  
  
-   <span data-ttu-id="eef3d-107">Настройте все клиентские приложения для использования одного и того же сетевого протокола, определив порядок протоколов в диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eef3d-107">Configure all client applications to use the same network protocol by setting the protocol order in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
-   <span data-ttu-id="eef3d-108">Настройте отдельное клиентское приложение для использования другого сетевого протокола, создав псевдоним.</span><span class="sxs-lookup"><span data-stu-id="eef3d-108">Configure a single client application to use a different network protocol by creating an alias.</span></span> <span data-ttu-id="eef3d-109">Дополнительные сведения см. в разделе [Создание или удаление псевдонима сервера для использования клиентом (диспетчер конфигурации SQL Server)](create-or-delete-a-server-alias-for-use-by-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="eef3d-109">For more information, see [Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md).</span></span>  
  
-   <span data-ttu-id="eef3d-110">Для некоторых клиентских приложений, например sqlcmd.exe, можно указать протокол как часть строки соединения.</span><span class="sxs-lookup"><span data-stu-id="eef3d-110">Some client applications, such as sqlcmd.exe, can specify the protocol as part of the connection string.</span></span> <span data-ttu-id="eef3d-111">Дополнительные сведения см. в разделе [Подключение к компоненту Database Engine при помощи программы sqlcmd](../../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="eef3d-111">For more information, see [Connect to the Database Engine With sqlcmd](../../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="eef3d-112">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="eef3d-112">Using SQL Server Configuration Manager</span></span>  
  
###  <a name="to-enable-or-disable-a-client-protocol"></a><a name="EnableDisable"></a> <span data-ttu-id="eef3d-113">Включение или отключение протокола клиента</span><span class="sxs-lookup"><span data-stu-id="eef3d-113">To enable or disable a client protocol</span></span>  
  
1.  <span data-ttu-id="eef3d-114">В диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разверните узел **Конфигурация SQL Server Native Client**, щелкните правой кнопкой мыши элемент **Клиентские протоколы** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="eef3d-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="eef3d-115">Выберите протокол в окне **Отключенные протоколы** и нажмите **Включить**, чтобы разрешить его работу.</span><span class="sxs-lookup"><span data-stu-id="eef3d-115">Click a protocol in the **Disabled Protocols** box, and then click **Enable**, to enable a protocol.</span></span>  
  
3.  <span data-ttu-id="eef3d-116">Выберите протокол в окне **Включенные протоколы** и нажмите кнопку **Отключить**, чтобы запретить его работу.</span><span class="sxs-lookup"><span data-stu-id="eef3d-116">Click a protocol in the **Enabled Protocols** box, and then click **Disable**, to disable a protocol.</span></span>  
  
###  <a name="to-change-the-default-protocol-or-the-protocol-order-for-client-computers"></a><a name="ChangeDefault"></a> <span data-ttu-id="eef3d-117">Изменение протокола по умолчанию или порядка задействования протоколов для компьютера клиента</span><span class="sxs-lookup"><span data-stu-id="eef3d-117">To change the default protocol or the protocol order for client computers</span></span>  
  
1.  <span data-ttu-id="eef3d-118">В диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разверните узел **Конфигурация SQL Server Native Client**, щелкните правой кнопкой мыши элемент **Клиентские протоколы** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="eef3d-118">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="eef3d-119">В окне **Включенные протоколы** нажмите кнопку **Вверх** или **Вниз**для изменения порядка, в котором задействуются протоколы при попытке соединения с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eef3d-119">In the **Enabled Protocols** box, click **Move Up** or **Move Down**, to change the order in which protocols are tried, when attempting to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eef3d-120">Верхний протокол в окне **Разрешенные протоколы** является протоколом по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eef3d-120">The top protocol in the **Enabled Protocols** box is the default protocol.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="eef3d-121">Диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] создает параметры реестра для конфигураций псевдонимов сервера и клиентскую сетевую библиотеку по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eef3d-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager creates registry entries for the server alias configurations and default client network library.</span></span> <span data-ttu-id="eef3d-122">Однако приложение не устанавливает какие-либо клиентские сетевые библиотеки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или сетевые протоколы.</span><span class="sxs-lookup"><span data-stu-id="eef3d-122">However, the application does not install either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network libraries or the network protocols.</span></span> <span data-ttu-id="eef3d-123">Клиентские сетевые библиотеки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] устанавливаются во время установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; сетевые протоколы ― во время установки Microsoft Windows (или через элемент **Сеть** на **панели управления**).</span><span class="sxs-lookup"><span data-stu-id="eef3d-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network libraries are installed during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup; the network protocols are installed as part of Microsoft Windows Setup (or through **Networks** in **Control Panel**).</span></span> <span data-ttu-id="eef3d-124">Конкретный сетевой протокол может быть недоступен при установке Windows.</span><span class="sxs-lookup"><span data-stu-id="eef3d-124">A particular network protocol may not be available as part of Windows Setup.</span></span> <span data-ttu-id="eef3d-125">Дополнительные сведения об установке этих сетевых протоколов см. в документации поставщика.</span><span class="sxs-lookup"><span data-stu-id="eef3d-125">For more information about installing these network protocols, see the vendor documentation.</span></span>  
  
###  <a name="to-configure-a-client-to-use-tcpip"></a><a name="Configure"></a> <span data-ttu-id="eef3d-126">Настройка клиента для использования TCP/IP</span><span class="sxs-lookup"><span data-stu-id="eef3d-126">To configure a client to use TCP/IP</span></span>  
  
1.  <span data-ttu-id="eef3d-127">В диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разверните узел **Конфигурация SQL Server Native Client**, щелкните правой кнопкой мыши элемент **Клиентские протоколы** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="eef3d-127">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="eef3d-128">В поле **Включенные протоколы** используйте кнопки со стрелками вниз и вверх, чтобы изменить порядок применения протоколов при попытках установить соединение с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eef3d-128">In the **Enabled Protocols** box, click the up and down arrows to change the order in which protocols are tried, when attempting to connect to SQL Server.</span></span> <span data-ttu-id="eef3d-129">Верхний протокол в окне **Разрешенные протоколы** является протоколом по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eef3d-129">The top protocol in the **Enabled Protocols** box is the default protocol.</span></span>  
  
 <span data-ttu-id="eef3d-130">Протокол общедоступной памяти активируется отдельно, установкой флажка **Включенный протокол общей памяти** .</span><span class="sxs-lookup"><span data-stu-id="eef3d-130">The shared memory protocol is enabled separately by checking the **Enabled Shared Memory Protocol** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef3d-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="eef3d-131">See Also</span></span>  
 [<span data-ttu-id="eef3d-132">Настройка параметра конфигурации сервера «remote login timeout»</span><span class="sxs-lookup"><span data-stu-id="eef3d-132">Configure the remote login timeout Server Configuration Option</span></span>](configure-the-remote-login-timeout-server-configuration-option.md)  
  
  
