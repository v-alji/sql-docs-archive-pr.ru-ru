---
title: Изменение подключений, использующих сетевые протоколы Banyan VINEs виртуализированного протокола (SPP), Multiprotocol, AppleTalk или NWLink IPX SPX | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- network protocols [SQL Server], modifying connections
- SPP [SQL Server]
- NWLink IPX/SPX [SQL Server]
- connections [SQL Server]
- AppleTalk [SQL Server]
- Sequenced Packet Protocol [SQL Server]
- Multiprotocol Net-Library [SQL Server]
- Banyan VINES Sequenced Package Protocol [SQL Server]
- IPX/SPX [SQL Server]
- protocols [SQL Server], modifying connections
- RPC [SQL Server]
ms.assetid: 5c5ae453-cc5b-4898-95c7-ad34157b1f60
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 750b9c0b76ab6c3b43908ecb8454f31ac1a25b1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749592"
---
# <a name="modify-connections-that-use-banyan-vines-sequenced-packet-protocol-spp-multiprotocol-appletalk-or-nwlink-ipx-spx-network-protocols"></a><span data-ttu-id="9d3a4-102">Изменение подключений, использующие сетевые протоколы Banyan VINES SPP, Multiprotocol, AppleTalk или NWLink IPX/SPX</span><span class="sxs-lookup"><span data-stu-id="9d3a4-102">Modify connections that use Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk, or NWLink IPX SPX network protocols</span></span>
  <span data-ttu-id="9d3a4-103">Помощник по обновлению обнаружил протоколы соединений «клиент-сервер», неподдерживаемые в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d3a4-103">The Upgrade Advisor has detected client server connectivity protocols that are not supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="9d3a4-104">Клиентские приложения, использующие сетевые протоколы Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk и NWLink IPX/SPX, должны устанавливать соединение с помощью поддерживаемого протокола.</span><span class="sxs-lookup"><span data-stu-id="9d3a4-104">Client applications that use Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol (RPC), AppleTalk, or NWLink IPX/SPX network protocols must connect using a supported protocol.</span></span>  
  
## <a name="component"></a><span data-ttu-id="9d3a4-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="9d3a4-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="9d3a4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9d3a4-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="9d3a4-107">не поддерживает сетевые протоколы Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk и NWLink IPX/SPX.</span><span class="sxs-lookup"><span data-stu-id="9d3a4-107">does not support the Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk, or NWLink IPX/SPX network protocols.</span></span> <span data-ttu-id="9d3a4-108">Клиенты, подключенные ранее с помощью этих протоколов, должны выбрать другой протокол.</span><span class="sxs-lookup"><span data-stu-id="9d3a4-108">Clients previously connecting with these protocols must select a different protocol.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="9d3a4-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="9d3a4-109">Corrective Action</span></span>  
 <span data-ttu-id="9d3a4-110">Измените клиентские приложения, чтобы они использовали для соединения с сервером поддерживаемый протокол.</span><span class="sxs-lookup"><span data-stu-id="9d3a4-110">Change the client applications to use a supported protocol when connecting to the server.</span></span> <span data-ttu-id="9d3a4-111">Если существует псевдоним, использующий один из неподдерживаемых протоколов, необходимо изменить псевдоним, чтобы использовался один из поддерживаемых протоколов.</span><span class="sxs-lookup"><span data-stu-id="9d3a4-111">If you have an alias setup that uses one of the unsupported protocols then the alias must be modified to use one of the supported protocols.</span></span>  
  
 <span data-ttu-id="9d3a4-112">Если строка подключения приложения использует или загружает один из этих протоколов, укажите NETWORK = DBMSRPCN для RPC, NETWORK = DBMSADSN for AppleTalk или NETWORK = ДБМСВИНН для свойства Banyan VINEs или с помощью явного префикса, например "SPX:*сохраняет*" для SPX, "BV:*Server*" для Banyan Vines, "ADSP:*Server*" для AppleTalk или "RPC:*Server*" для многопротокольного протокола, необходимо изменить приложение для использования одного из поддерживаемых протоколов.</span><span class="sxs-lookup"><span data-stu-id="9d3a4-112">If your application connection string specifically uses or loads one of these protocols, by either specifying NETWORK=DBMSRPCN for RPC, NETWORK=DBMSADSN for Appletalk, or NETWORK=DBMSVINN for Banyan VINES property, or by using an explicit prefix such as "spx:*server\instance*" for SPX, "bv:*server*" for Banyan VINES, "adsp:*server*" for AppleTalk, or "rpc:*server*" for multiprotocol, then you must modify your application to use one of the supported protocols.</span></span>  
  
 <span data-ttu-id="9d3a4-113">Дополнительные сведения см. в разделе «Выбор сетевого протокола» в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d3a4-113">For more information, see "Choosing a Network Protocol" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d3a4-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="9d3a4-114">See Also</span></span>  
 <span data-ttu-id="9d3a4-115">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="9d3a4-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="9d3a4-116">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="9d3a4-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
