---
title: MSSQLSERVER_53 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "53"
helpviewer_keywords:
- 53 (Database Engine error)
ms.assetid: 1234f5a2-b3d1-425a-b29f-480fa792305f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 85fda292fb956047f51b9c7cd1d229ac0afce6b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664947"
---
# <a name="mssqlserver_53"></a><span data-ttu-id="fba4c-102">MSSQLSERVER_53</span><span class="sxs-lookup"><span data-stu-id="fba4c-102">MSSQLSERVER_53</span></span>
    
## <a name="details"></a><span data-ttu-id="fba4c-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="fba4c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fba4c-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="fba4c-104">Product Name</span></span>|<span data-ttu-id="fba4c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fba4c-105">SQL Server</span></span>|  
|<span data-ttu-id="fba4c-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="fba4c-106">Event ID</span></span>|<span data-ttu-id="fba4c-107">53</span><span class="sxs-lookup"><span data-stu-id="fba4c-107">53</span></span>|  
|<span data-ttu-id="fba4c-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="fba4c-108">Event Source</span></span>|<span data-ttu-id="fba4c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fba4c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fba4c-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="fba4c-110">Component</span></span>|<span data-ttu-id="fba4c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fba4c-111">SQLEngine</span></span>|  
|<span data-ttu-id="fba4c-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="fba4c-112">Symbolic Name</span></span>||  
|<span data-ttu-id="fba4c-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="fba4c-113">Message Text</span></span>|<span data-ttu-id="fba4c-114">При соединении с сервером произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="fba4c-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="fba4c-115">Эта ошибка при соединении с SQL Server может быть вызвана тем, что в параметрах SQL Server по умолчанию запрещены удаленные соединения.</span><span class="sxs-lookup"><span data-stu-id="fba4c-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="fba4c-116">(поставщик: поставщик именованных каналов, ошибка: 40: не удалось открыть соединение с SQL Server (поставщик данных .Net SqlClient)</span><span class="sxs-lookup"><span data-stu-id="fba4c-116">(provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fba4c-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="fba4c-117">Explanation</span></span>  
 <span data-ttu-id="fba4c-118">Клиенту [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удается установить соединение с сервером.</span><span class="sxs-lookup"><span data-stu-id="fba4c-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="fba4c-119">Эта ошибка может возникать в том случае, если клиенту не удается преобразовать имя сервера либо если указано неверное имя сервера.</span><span class="sxs-lookup"><span data-stu-id="fba4c-119">This error could occur because either the client cannot resolve the name of the server or the name of the server is incorrect.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fba4c-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="fba4c-120">User Action</span></span>  
 <span data-ttu-id="fba4c-121">Убедитесь, что в клиенте введено правильное имя сервера, а также в том, что удается преобразовать имя сервера от клиента.</span><span class="sxs-lookup"><span data-stu-id="fba4c-121">Make sure that you have entered the correct server name on the client, and that you can resolve the name of the server from the client.</span></span> <span data-ttu-id="fba4c-122">Разрешение имен TCP/IP можно проверить с помощью команды **ping** в операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="fba4c-122">To check TCP/IP name resolution, you can use the **ping** command in the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fba4c-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="fba4c-123">See Also</span></span>  
 <span data-ttu-id="fba4c-124">[Сетевые протоколы и сетевые библиотеки](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="fba4c-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="fba4c-125">[Конфигурация клиентской сети](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="fba4c-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="fba4c-126">[Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="fba4c-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="fba4c-127">Включение или отключение сетевого протокола сервера</span><span class="sxs-lookup"><span data-stu-id="fba4c-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
