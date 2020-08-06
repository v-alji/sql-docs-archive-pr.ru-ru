---
title: MSSQLSERVER_2 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- 2 (Database Engine error)
ms.assetid: 567fb571-7cda-4ce8-a702-cdff2df5d419
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 87d19a24219fda79de2cad4c06af4f1936b37b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667145"
---
# <a name="mssqlserver_2"></a><span data-ttu-id="97b68-102">MSSQLSERVER_2</span><span class="sxs-lookup"><span data-stu-id="97b68-102">MSSQLSERVER_2</span></span>
    
## <a name="details"></a><span data-ttu-id="97b68-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="97b68-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="97b68-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="97b68-104">Product Name</span></span>|<span data-ttu-id="97b68-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="97b68-105">SQL Server</span></span>|  
|<span data-ttu-id="97b68-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="97b68-106">Event ID</span></span>|<span data-ttu-id="97b68-107">2</span><span class="sxs-lookup"><span data-stu-id="97b68-107">2</span></span>|  
|<span data-ttu-id="97b68-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="97b68-108">Event Source</span></span>|<span data-ttu-id="97b68-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="97b68-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="97b68-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="97b68-110">Component</span></span>|<span data-ttu-id="97b68-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="97b68-111">SQLEngine</span></span>|  
|<span data-ttu-id="97b68-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="97b68-112">Symbolic Name</span></span>||  
|<span data-ttu-id="97b68-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="97b68-113">Message Text</span></span>|<span data-ttu-id="97b68-114">При соединении с сервером произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="97b68-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="97b68-115">Эта ошибка при соединении с SQL Server может быть вызвана тем, что в параметрах SQL Server по умолчанию запрещены удаленные соединения.</span><span class="sxs-lookup"><span data-stu-id="97b68-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="97b68-116">(поставщик: поставщик именованных каналов, ошибка: 40: не удалось открыть соединение с SQL Server (поставщик данных .Net SqlClient)</span><span class="sxs-lookup"><span data-stu-id="97b68-116">(provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="97b68-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="97b68-117">Explanation</span></span>  
 <span data-ttu-id="97b68-118">Вероятно, от [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не поступил ответ на запрос клиента, потому что этот сервер не был запущен.</span><span class="sxs-lookup"><span data-stu-id="97b68-118">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] did not respond to the client request because the server is probably not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="97b68-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="97b68-119">User Action</span></span>  
 <span data-ttu-id="97b68-120">Убедитесь, что сервер запущен.</span><span class="sxs-lookup"><span data-stu-id="97b68-120">Make sure that the server is started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b68-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="97b68-121">See Also</span></span>  
 <span data-ttu-id="97b68-122">[Управление службами компонента Database Engine](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="97b68-122">[Manage the Database Engine Services](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="97b68-123">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="97b68-123">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="97b68-124">[Сетевые протоколы и сетевые библиотеки](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="97b68-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="97b68-125">[Конфигурация клиентской сети](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="97b68-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="97b68-126">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="97b68-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="97b68-127">Включение или отключение сетевого протокола сервера</span><span class="sxs-lookup"><span data-stu-id="97b68-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
