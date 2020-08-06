---
title: MSSQLSERVER_10060 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10060"
helpviewer_keywords:
- 10060 (Database Engine error)
ms.assetid: 28c21277-cad8-406c-a955-07933a56982a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d634cfb06381fb916ef2e421e0677e76edb9ae02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738453"
---
# <a name="mssqlserver_10060"></a><span data-ttu-id="25e2a-102">MSSQLSERVER_10060</span><span class="sxs-lookup"><span data-stu-id="25e2a-102">MSSQLSERVER_10060</span></span>
    
## <a name="details"></a><span data-ttu-id="25e2a-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="25e2a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25e2a-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="25e2a-104">Product Name</span></span>|<span data-ttu-id="25e2a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="25e2a-105">SQL Server</span></span>|  
|<span data-ttu-id="25e2a-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="25e2a-106">Event ID</span></span>|<span data-ttu-id="25e2a-107">10060</span><span class="sxs-lookup"><span data-stu-id="25e2a-107">10060</span></span>|  
|<span data-ttu-id="25e2a-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="25e2a-108">Event Source</span></span>|<span data-ttu-id="25e2a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="25e2a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="25e2a-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="25e2a-110">Component</span></span>|<span data-ttu-id="25e2a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="25e2a-111">SQLEngine</span></span>|  
|<span data-ttu-id="25e2a-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="25e2a-112">Symbolic Name</span></span>||  
|<span data-ttu-id="25e2a-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="25e2a-113">Message Text</span></span>|<span data-ttu-id="25e2a-114">При соединении с сервером произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="25e2a-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="25e2a-115">Эта ошибка при соединении с SQL Server может быть вызвана тем, что в параметрах SQL Server по умолчанию запрещены удаленные соединения.</span><span class="sxs-lookup"><span data-stu-id="25e2a-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="25e2a-116">(поставщик: поставщик TCP, ошибка: 0 — "Попытка установить соединение была безуспешной, т.к. от другого компьютера за требуемое время не получен нужный отклик, или было разорвано уже установленное соединение из-за неверного отклика уже подключенного компьютера".) (Microsoft SQL Server, ошибка: 10060)</span><span class="sxs-lookup"><span data-stu-id="25e2a-116">(provider: TCP Provider, error: 0 - A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.) (Microsoft SQL Server, Error: 10060)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="25e2a-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="25e2a-117">Explanation</span></span>  
 <span data-ttu-id="25e2a-118">Клиенту [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удается установить соединение с сервером.</span><span class="sxs-lookup"><span data-stu-id="25e2a-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="25e2a-119">Эта ошибка может возникать, если брандмауэр сервера отказывает в соединении либо если на сервере не настроен прием удаленных соединений.</span><span class="sxs-lookup"><span data-stu-id="25e2a-119">This error could occur because either the firewall on the server has refused the connection or the server is not configured to accept remote connections.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25e2a-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="25e2a-120">User Action</span></span>  
 <span data-ttu-id="25e2a-121">Чтобы устранить эту неполадку, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="25e2a-121">To resolve this error, try one of the following actions:</span></span>  
  
-   <span data-ttu-id="25e2a-122">Убедитесь, что в брандмауэре на компьютере для этого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настроен прием соединений.</span><span class="sxs-lookup"><span data-stu-id="25e2a-122">Make sure that you have configured the firewall on the computer to allow this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
-   <span data-ttu-id="25e2a-123">С помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разрешите в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] прием удаленных соединений.</span><span class="sxs-lookup"><span data-stu-id="25e2a-123">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e2a-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="25e2a-124">See Also</span></span>  
 <span data-ttu-id="25e2a-125">[Настройка брандмауэра Windows для доступа к ядро СУБД](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="25e2a-125">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="25e2a-126">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="25e2a-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="25e2a-127">[Сетевые протоколы и сетевые библиотеки](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="25e2a-127">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="25e2a-128">[Конфигурация клиентской сети](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="25e2a-128">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="25e2a-129">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="25e2a-129">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="25e2a-130">Включение или отключение сетевого протокола сервера</span><span class="sxs-lookup"><span data-stu-id="25e2a-130">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
