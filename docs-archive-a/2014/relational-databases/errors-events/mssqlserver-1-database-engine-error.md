---
title: MSSQLSERVER_ 1 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "-1"
helpviewer_keywords:
- -1 (Database Engine error)
ms.assetid: bad25b91-eaed-46c0-a5b7-71117a32304c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 880212b1d2e9572bbb31535a5ba68b445c7e6f35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735286"
---
# <a name="mssqlserver_-1"></a><span data-ttu-id="6728a-102">MSSQLSERVER_-1</span><span class="sxs-lookup"><span data-stu-id="6728a-102">MSSQLSERVER_-1</span></span>
    
## <a name="details"></a><span data-ttu-id="6728a-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="6728a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6728a-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="6728a-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="6728a-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6728a-105">Event ID</span></span>|<span data-ttu-id="6728a-106">-1</span><span class="sxs-lookup"><span data-stu-id="6728a-106">-1</span></span>|  
|<span data-ttu-id="6728a-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="6728a-107">Event Source</span></span>|<span data-ttu-id="6728a-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6728a-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6728a-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="6728a-109">Component</span></span>|<span data-ttu-id="6728a-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6728a-110">SQLEngine</span></span>|  
|<span data-ttu-id="6728a-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="6728a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="6728a-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="6728a-112">Message Text</span></span>|<span data-ttu-id="6728a-113">При соединении с сервером произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="6728a-113">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="6728a-114">При подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] эта ошибка может быть вызвана тем, что в конфигурации по умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не поддерживает удаленные соединения.</span><span class="sxs-lookup"><span data-stu-id="6728a-114">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this failure may be caused by the fact that under the default settings [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow remote connections.</span></span> <span data-ttu-id="6728a-115">(поставщик: сетевые интерфейсы SQL, ошибка: 28 — сервер не поддерживает запрашиваемый протокол) (Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ошибка: –1)</span><span class="sxs-lookup"><span data-stu-id="6728a-115">(provider: SQL Network Interfaces, error: 28 - Server doesn't support requested protocol) (Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Error: -1)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6728a-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="6728a-116">Explanation</span></span>  
 <span data-ttu-id="6728a-117">Клиенту [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удается установить соединение с сервером.</span><span class="sxs-lookup"><span data-stu-id="6728a-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="6728a-118">Возможны следующие причины возникновения этой ошибки.</span><span class="sxs-lookup"><span data-stu-id="6728a-118">This error could be caused by one of the following reasons:</span></span>  
  
-   <span data-ttu-id="6728a-119">Указанное имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] недопустимо.</span><span class="sxs-lookup"><span data-stu-id="6728a-119">A specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name is not valid.</span></span>  
  
-   <span data-ttu-id="6728a-120">Протокол именованных каналов или TCP не включен.</span><span class="sxs-lookup"><span data-stu-id="6728a-120">The TCP, or named pipes protocols are not enabled.</span></span>  
  
-   <span data-ttu-id="6728a-121">Брандмауэр на сервере отклонил это соединение.</span><span class="sxs-lookup"><span data-stu-id="6728a-121">The firewall on the server has refused the connection.</span></span>  
  
-   <span data-ttu-id="6728a-122">Служба "Браузер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" (sqlbrowser) не запущена.</span><span class="sxs-lookup"><span data-stu-id="6728a-122">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service (sqlbrowser) is not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6728a-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="6728a-123">User Action</span></span>  
 <span data-ttu-id="6728a-124">Чтобы устранить эту неполадку, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6728a-124">To resolve this error, try one of the following actions:</span></span>  
  
-   <span data-ttu-id="6728a-125">Проверьте правильность указания имени экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которое указано в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="6728a-125">Check the spelling of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name that is specified in the connection string.</span></span>  
  
-   <span data-ttu-id="6728a-126">С помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настройте [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на прием удаленных соединений по протоколу TCP или по протоколам именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="6728a-126">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections over the TCP or named pipes protocols.</span></span>  
  
-   <span data-ttu-id="6728a-127">Убедитесь, что в брандмауэре на экземпляре сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] открыты порты для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и порт браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (UDP-порт 1434).</span><span class="sxs-lookup"><span data-stu-id="6728a-127">Make sure that you have configured the firewall on the server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to open ports for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser port (UDP 1434).</span></span>  
  
-   <span data-ttu-id="6728a-128">Убедитесь, что служба «[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], браузер» запущена на сервере.</span><span class="sxs-lookup"><span data-stu-id="6728a-128">Make sure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is started on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6728a-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="6728a-129">See Also</span></span>  
 <span data-ttu-id="6728a-130">[Настройка брандмауэра Windows для доступа к ядро СУБД](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="6728a-130">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="6728a-131">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="6728a-131">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="6728a-132">[Сетевые протоколы и сетевые библиотеки](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="6728a-132">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="6728a-133">[Конфигурация клиентской сети](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6728a-133">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="6728a-134">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="6728a-134">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="6728a-135">Включение или отключение сетевого протокола сервера</span><span class="sxs-lookup"><span data-stu-id="6728a-135">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
