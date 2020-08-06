---
title: MSSQLSERVER_233 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "233"
helpviewer_keywords:
- 233 (Database Engine error)
ms.assetid: 201665dc-7ac8-4c19-90d3-33354c5caa72
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c51fac7c0af16c520d7cf5538e512912e62cf87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730710"
---
# <a name="mssqlserver_233"></a><span data-ttu-id="d8804-102">MSSQLSERVER_233</span><span class="sxs-lookup"><span data-stu-id="d8804-102">MSSQLSERVER_233</span></span>
    
## <a name="details"></a><span data-ttu-id="d8804-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="d8804-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8804-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="d8804-104">Product Name</span></span>|<span data-ttu-id="d8804-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d8804-105">SQL Server</span></span>|  
|<span data-ttu-id="d8804-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="d8804-106">Event ID</span></span>|<span data-ttu-id="d8804-107">233</span><span class="sxs-lookup"><span data-stu-id="d8804-107">233</span></span>|  
|<span data-ttu-id="d8804-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="d8804-108">Event Source</span></span>|<span data-ttu-id="d8804-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d8804-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d8804-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="d8804-110">Component</span></span>|<span data-ttu-id="d8804-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d8804-111">SQLEngine</span></span>|  
|<span data-ttu-id="d8804-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="d8804-112">Symbolic Name</span></span>||  
|<span data-ttu-id="d8804-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="d8804-113">Message Text</span></span>|<span data-ttu-id="d8804-114">Соединение с сервером было успешно установлено, но при входе в систему произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="d8804-114">A connection was successfully established with the server, but then an error occurred during the login process.</span></span> <span data-ttu-id="d8804-115">(поставщик: поставщик общей памяти, ошибка: 0 — На другом конце канала отсутствует процесс.) (Microsoft SQL Server, ошибка: 233)</span><span class="sxs-lookup"><span data-stu-id="d8804-115">(provider: Shared Memory Provider, error: 0 - No process is on the other end of the pipe.) (Microsoft SQL Server, Error: 233)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d8804-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="d8804-116">Explanation</span></span>  
 <span data-ttu-id="d8804-117">Клиенту [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удается установить соединение с сервером.</span><span class="sxs-lookup"><span data-stu-id="d8804-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="d8804-118">Эта ошибка может возникать, если на сервере не настроен прием удаленных соединений.</span><span class="sxs-lookup"><span data-stu-id="d8804-118">This error could occur because the server is not configured to accept remote connections.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8804-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="d8804-119">User Action</span></span>  
 <span data-ttu-id="d8804-120">С помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разрешите в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] прием удаленных соединений.</span><span class="sxs-lookup"><span data-stu-id="d8804-120">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8804-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8804-121">See Also</span></span>  
 <span data-ttu-id="d8804-122">[Сетевые протоколы и сетевые библиотеки](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="d8804-122">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="d8804-123">[Конфигурация клиентской сети](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="d8804-123">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="d8804-124">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="d8804-124">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="d8804-125">Включение или отключение сетевого протокола сервера</span><span class="sxs-lookup"><span data-stu-id="d8804-125">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
