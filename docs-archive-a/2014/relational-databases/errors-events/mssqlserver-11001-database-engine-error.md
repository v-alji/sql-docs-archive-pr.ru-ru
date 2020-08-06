---
title: MSSQLSERVER_11001 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "12001"
helpviewer_keywords:
- 11001 (Database Engine error)
ms.assetid: 53d4d63a-61e3-441f-bfe9-9d44f7a05fd4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da7dd171d1b6a64e0cc1666eda1e3593a81eece1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667187"
---
# <a name="mssqlserver_11001"></a><span data-ttu-id="6f0b1-102">MSSQLSERVER_11001</span><span class="sxs-lookup"><span data-stu-id="6f0b1-102">MSSQLSERVER_11001</span></span>
    
## <a name="details"></a><span data-ttu-id="6f0b1-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="6f0b1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6f0b1-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="6f0b1-104">Product Name</span></span>|<span data-ttu-id="6f0b1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6f0b1-105">SQL Server</span></span>|  
|<span data-ttu-id="6f0b1-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6f0b1-106">Event ID</span></span>|<span data-ttu-id="6f0b1-107">11001</span><span class="sxs-lookup"><span data-stu-id="6f0b1-107">11001</span></span>|  
|<span data-ttu-id="6f0b1-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="6f0b1-108">Event Source</span></span>|<span data-ttu-id="6f0b1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6f0b1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6f0b1-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="6f0b1-110">Component</span></span>|<span data-ttu-id="6f0b1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6f0b1-111">SQLEngine</span></span>|  
|<span data-ttu-id="6f0b1-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="6f0b1-112">Symbolic Name</span></span>||  
|<span data-ttu-id="6f0b1-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="6f0b1-113">Message Text</span></span>|<span data-ttu-id="6f0b1-114">При соединении с сервером произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="6f0b1-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="6f0b1-115">Эта ошибка при соединении с SQL Server может быть вызвана тем, что в параметрах SQL Server по умолчанию запрещены удаленные соединения.</span><span class="sxs-lookup"><span data-stu-id="6f0b1-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="6f0b1-116">(поставщик: поставщик TCP, ошибка: 0 — узел неизвестен.) (Поставщик данных .Net SqlClient)</span><span class="sxs-lookup"><span data-stu-id="6f0b1-116">(provider: TCP Provider, error: 0 - No such host is known.) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6f0b1-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="6f0b1-117">Explanation</span></span>  
 <span data-ttu-id="6f0b1-118">Клиенту [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удается установить соединение с сервером.</span><span class="sxs-lookup"><span data-stu-id="6f0b1-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="6f0b1-119">Эта ошибка может возникать в том случае, если клиенту не удается преобразовать имя сервера либо если указано неверное имя сервера.</span><span class="sxs-lookup"><span data-stu-id="6f0b1-119">The error could occur because either the client cannot resolve the name of the server or the name of the server is incorrect.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6f0b1-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="6f0b1-120">User Action</span></span>  
 <span data-ttu-id="6f0b1-121">Убедитесь, что в клиенте введено правильное имя сервера, а также в том, что удается преобразовать имя сервера от клиента.</span><span class="sxs-lookup"><span data-stu-id="6f0b1-121">Make sure that you have entered the correct server name on the client, and that you can resolve the name of the server from the client.</span></span> <span data-ttu-id="6f0b1-122">Разрешение имен TCP/IP можно проверить с помощью команды **ping** в операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="6f0b1-122">To check TCP/IP name resolution, you can use the **ping** command in the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f0b1-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f0b1-123">See Also</span></span>  
 <span data-ttu-id="6f0b1-124">[Сетевые протоколы и сетевые библиотеки](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="6f0b1-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="6f0b1-125">[Конфигурация клиентской сети](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6f0b1-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="6f0b1-126">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="6f0b1-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="6f0b1-127">Включение или отключение сетевого протокола сервера</span><span class="sxs-lookup"><span data-stu-id="6f0b1-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
