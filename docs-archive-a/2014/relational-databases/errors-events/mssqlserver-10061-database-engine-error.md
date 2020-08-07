---
title: MSSQLSERVER_10061 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10061"
helpviewer_keywords:
- 10061 (Database Engine error)
ms.assetid: 729602f3-08df-474c-8740-8dea13c1eee3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0c866bd8dce01f65036f1d508a94252a97613424
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735281"
---
# <a name="mssqlserver_10061"></a><span data-ttu-id="3108e-102">MSSQLSERVER_10061</span><span class="sxs-lookup"><span data-stu-id="3108e-102">MSSQLSERVER_10061</span></span>
    
## <a name="details"></a><span data-ttu-id="3108e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="3108e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3108e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="3108e-104">Product Name</span></span>|<span data-ttu-id="3108e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3108e-105">SQL Server</span></span>|  
|<span data-ttu-id="3108e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="3108e-106">Event ID</span></span>|<span data-ttu-id="3108e-107">10061</span><span class="sxs-lookup"><span data-stu-id="3108e-107">10061</span></span>|  
|<span data-ttu-id="3108e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="3108e-108">Event Source</span></span>|<span data-ttu-id="3108e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3108e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3108e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="3108e-110">Component</span></span>|<span data-ttu-id="3108e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3108e-111">SQLEngine</span></span>|  
|<span data-ttu-id="3108e-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="3108e-112">Symbolic Name</span></span>||  
|<span data-ttu-id="3108e-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="3108e-113">Message Text</span></span>|<span data-ttu-id="3108e-114">При соединении с сервером произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="3108e-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="3108e-115">Эта ошибка при соединении с SQL Server может быть вызвана тем, что в параметрах SQL Server по умолчанию запрещены удаленные соединения.</span><span class="sxs-lookup"><span data-stu-id="3108e-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="3108e-116">(поставщик: поставщик TCP, ошибка: 0 — Подключение не установлено, т.к. конечный компьютер отверг запрос на подключение.) (Microsoft SQL Server, ошибка: 10061)</span><span class="sxs-lookup"><span data-stu-id="3108e-116">(provider: TCP Provider, error: 0 - No connection could be made because the target machine actively refused it.) (Microsoft SQL Server, Error: 10061)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3108e-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="3108e-117">Explanation</span></span>  
 <span data-ttu-id="3108e-118">Сервер не ответил на запрос клиента.</span><span class="sxs-lookup"><span data-stu-id="3108e-118">The server did not respond to the client request.</span></span> <span data-ttu-id="3108e-119">Возможно, это связано с тем, что сервер не запущен.</span><span class="sxs-lookup"><span data-stu-id="3108e-119">This error could occur because the server is not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3108e-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="3108e-120">User Action</span></span>  
 <span data-ttu-id="3108e-121">Убедитесь, что сервер запущен.</span><span class="sxs-lookup"><span data-stu-id="3108e-121">Make sure that the server is started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3108e-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="3108e-122">See Also</span></span>  
 <span data-ttu-id="3108e-123">[Управление службами компонента Database Engine](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="3108e-123">[Manage the Database Engine Services](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="3108e-124">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="3108e-124">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="3108e-125">[Сетевые протоколы и сетевые библиотеки](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="3108e-125">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="3108e-126">[Конфигурация клиентской сети](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="3108e-126">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="3108e-127">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="3108e-127">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="3108e-128">Включение или отключение сетевого протокола сервера</span><span class="sxs-lookup"><span data-stu-id="3108e-128">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
