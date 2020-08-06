---
title: MSSQLSERVER_-2 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- -2 (Database Engine error)
ms.assetid: f37a7b7d-26e1-4b9e-bcb4-57f7805393d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d39b4a11387a60056bba3f87adffcb2653b60f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732689"
---
# <a name="mssqlserver_-2"></a><span data-ttu-id="749b0-102">MSSQLSERVER_-2</span><span class="sxs-lookup"><span data-stu-id="749b0-102">MSSQLSERVER_-2</span></span>
    
## <a name="details"></a><span data-ttu-id="749b0-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="749b0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="749b0-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="749b0-104">Product Name</span></span>|<span data-ttu-id="749b0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="749b0-105">SQL Server</span></span>|  
|<span data-ttu-id="749b0-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="749b0-106">Event ID</span></span>|<span data-ttu-id="749b0-107">-2</span><span class="sxs-lookup"><span data-stu-id="749b0-107">-2</span></span>|  
|<span data-ttu-id="749b0-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="749b0-108">Event Source</span></span>|<span data-ttu-id="749b0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="749b0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="749b0-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="749b0-110">Component</span></span>|<span data-ttu-id="749b0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="749b0-111">SQLEngine</span></span>|  
|<span data-ttu-id="749b0-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="749b0-112">Symbolic Name</span></span>||  
|<span data-ttu-id="749b0-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="749b0-113">Message Text</span></span>|<span data-ttu-id="749b0-114">Время ожидания истекло.</span><span class="sxs-lookup"><span data-stu-id="749b0-114">Timeout expired.</span></span>  <span data-ttu-id="749b0-115">Время ожидания истекло до завершения операции, либо сервер не отвечает.</span><span class="sxs-lookup"><span data-stu-id="749b0-115">The timeout period elapsed prior to completion of the operation or the server is not responding.</span></span> <span data-ttu-id="749b0-116">(Microsoft SQL Server, ошибка: –2)</span><span class="sxs-lookup"><span data-stu-id="749b0-116">(Microsoft SQL Server, Error: -2)</span></span>|   
  
## <a name="explanation"></a><span data-ttu-id="749b0-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="749b0-117">Explanation</span></span>  
 <span data-ttu-id="749b0-118">Клиенту [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удается установить соединение с сервером.</span><span class="sxs-lookup"><span data-stu-id="749b0-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="749b0-119">Эта ошибка возникает, если брандмауэр сервера отказывает в соединении.</span><span class="sxs-lookup"><span data-stu-id="749b0-119">This error could occur because the firewall on the server has refused the connection.</span></span> 
  
## <a name="user-action"></a><span data-ttu-id="749b0-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="749b0-120">User Action</span></span>  
 <span data-ttu-id="749b0-121">Убедитесь, что в брандмауэре на экземпляре сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разрешен прием соединений.</span><span class="sxs-lookup"><span data-stu-id="749b0-121">Make sure that you have configured the firewall on the server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="749b0-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="749b0-122">See Also</span></span>  
 <span data-ttu-id="749b0-123">[Настройка брандмауэра Windows на разрешение доступа к SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) </span><span class="sxs-lookup"><span data-stu-id="749b0-123">[Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) </span></span>  
 <span data-ttu-id="749b0-124">[Настройка брандмауэра Windows для доступа к ядро СУБД](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="749b0-124">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="749b0-125">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="749b0-125">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="749b0-126">[Сетевые протоколы и сетевые библиотеки](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="749b0-126">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="749b0-127">[Конфигурация клиентской сети](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="749b0-127">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="749b0-128">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="749b0-128">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="749b0-129">Включение или отключение сетевого протокола сервера</span><span class="sxs-lookup"><span data-stu-id="749b0-129">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
