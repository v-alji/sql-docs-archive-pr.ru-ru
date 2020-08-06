---
title: Управление Service Broker | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- Service Broker [SMO]
ms.assetid: b29d7432-d1e5-4bb6-b544-57b3a9430f95
author: stevestein
ms.author: sstein
ms.openlocfilehash: ce166825bb7adea241bac13defeca1a78b4f29cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728153"
---
# <a name="managing-service-broker"></a><span data-ttu-id="d55fb-102">Управление компонентом Service Broker</span><span class="sxs-lookup"><span data-stu-id="d55fb-102">Managing Service Broker</span></span>
  <span data-ttu-id="d55fb-103">В объектах SMO объекты компонента [!INCLUDE[ssSB](../../../includes/sssb-md.md)] находятся в пространстве имен `Microsoft.SqlServer.Management.Smo.Broker`, которое требует ссылки на сборку Microsoft.SqlServer.Smo.dll.</span><span class="sxs-lookup"><span data-stu-id="d55fb-103">In SMO, the [!INCLUDE[ssSB](../../../includes/sssb-md.md)] objects are found in the `Microsoft.SqlServer.Management.Smo.Broker` namespace, which requires a reference to the Microsoft.SqlServer.Smo.dll.</span></span> <span data-ttu-id="d55fb-104">Кроме того, необходима ссылка на сборку Microsoft.SqlServer.ServiceBrokerEnum.dll для поддержки сведений о классах.</span><span class="sxs-lookup"><span data-stu-id="d55fb-104">A reference to the Microsoft.SqlServer.ServiceBrokerEnum.dll is also required for supporting class information.</span></span>  
  
 <span data-ttu-id="d55fb-105">SMO предоставляет набор объектов компонента [!INCLUDE[ssSB](../../../includes/sssb-md.md)] , которые допускают программное управление (DDL) реализацией [!INCLUDE[ssSB](../../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d55fb-105">SMO provides a set of [!INCLUDE[ssSB](../../../includes/sssb-md.md)] objects that permit programmatic management (DDL) of the [!INCLUDE[ssSB](../../../includes/sssb-md.md)] implementation.</span></span> <span data-ttu-id="d55fb-106">Оно включает определение типов сообщений, контрактов, очередей и служб.</span><span class="sxs-lookup"><span data-stu-id="d55fb-106">This includes defining the message types, contracts, queues, and services.</span></span> <span data-ttu-id="d55fb-107">Так как SMO является средством управления, которое не предназначено для работы с данными, SMO не поддерживает отправку и получение сообщений компонента [!INCLUDE[ssSB](../../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d55fb-107">Because SMO is a management tool that is not intended for data manipulation, sending and receiving [!INCLUDE[ssSB](../../../includes/sssb-md.md)] messages is not supported by SMO.</span></span>  
  
 <span data-ttu-id="d55fb-108">В SMO объект <xref:Microsoft.SqlServer.Management.Smo.Database.ServiceBroker%2A> является классом верхнего уровня, который заключает всю функциональность компонента [!INCLUDE[ssSB](../../../includes/sssb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d55fb-108">In SMO, the <xref:Microsoft.SqlServer.Management.Smo.Database.ServiceBroker%2A> object is the top-level class under which all the [!INCLUDE[ssSB](../../../includes/sssb-md.md)] functionality resides.</span></span> <span data-ttu-id="d55fb-109">Реализация компонента [!INCLUDE[ssSB](../../../includes/sssb-md.md)] необходима для каждой базы данных, которая участвует в работе приложений с распределенным обменом сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d55fb-109">A [!INCLUDE[ssSB](../../../includes/sssb-md.md)] implementation is required for each database that is participating in the distributed messaging application.</span></span> <span data-ttu-id="d55fb-110">Поэтому объект <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceBroker> является потомком объекта <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="d55fb-110">Therefore, the <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceBroker> object is a child of the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span>  
  
 <span data-ttu-id="d55fb-111">Объект <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceBroker> содержит коллекции следующих объектов, используемых в определении реализации компонента [!INCLUDE[ssSB](../../../includes/sssb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d55fb-111">The <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceBroker> object contains collections of the following objects that are used to define the [!INCLUDE[ssSB](../../../includes/sssb-md.md)] implementation:</span></span>  
  
-   <span data-ttu-id="d55fb-112">Объекты <xref:Microsoft.SqlServer.Management.Smo.Broker.MessageType> представляют типы сообщений, которые определяют содержимое сообщений.</span><span class="sxs-lookup"><span data-stu-id="d55fb-112"><xref:Microsoft.SqlServer.Management.Smo.Broker.MessageType> objects represent message types that define the content of messages.</span></span>  
  
-   <span data-ttu-id="d55fb-113">Объекты <xref:Microsoft.SqlServer.Management.Smo.Broker.MessageTypeMapping> представляют контракты, которые указывают направление и тип сообщений заданного диалога.</span><span class="sxs-lookup"><span data-stu-id="d55fb-113"><xref:Microsoft.SqlServer.Management.Smo.Broker.MessageTypeMapping> objects represent contracts that specify the direction and type of messages in a given conversation.</span></span>  
  
-   <span data-ttu-id="d55fb-114">Объекты <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceQueue> хранят сообщения до их отправки и после их получения.</span><span class="sxs-lookup"><span data-stu-id="d55fb-114"><xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceQueue> objects store messages prior to sending and after they are received.</span></span> <span data-ttu-id="d55fb-115">Они обеспечивают асинхронную связь между службами, а также и другие преимущества, такие как автоматическая блокировка сообщений внутри группы диалога.</span><span class="sxs-lookup"><span data-stu-id="d55fb-115">They provide asynchronous communication between services, as well as other benefits, such as automatically locking messages in the same conversation group.</span></span>  
  
-   <span data-ttu-id="d55fb-116">Объект <xref:Microsoft.SqlServer.Management.Smo.Broker.BrokerService> представляет собой компонент [!INCLUDE[ssSB](../../../includes/sssb-md.md)], которые являются адресуемыми конечными точками для диалогов.</span><span class="sxs-lookup"><span data-stu-id="d55fb-116"><xref:Microsoft.SqlServer.Management.Smo.Broker.BrokerService> objects represent [!INCLUDE[ssSB](../../../includes/sssb-md.md)] services, which are the addressable endpoints for conversations.</span></span> <span data-ttu-id="d55fb-117">Сообщения компонента [!INCLUDE[ssSB](../../../includes/sssb-md.md)] отправляются от одной службы к другой.</span><span class="sxs-lookup"><span data-stu-id="d55fb-117">[!INCLUDE[ssSB](../../../includes/sssb-md.md)] messages are sent from one service to another service.</span></span> <span data-ttu-id="d55fb-118">Служба определяет очередь для ожидания сообщений и указывает контракты, для которых служба может быть целью.</span><span class="sxs-lookup"><span data-stu-id="d55fb-118">A service specifies a queue to hold messages, and specifies the contracts for which the service can be the target.</span></span>  
  
-   <span data-ttu-id="d55fb-119">Объекты <xref:Microsoft.SqlServer.Management.Smo.Broker.RemoteServiceBinding> представляют настройки, которые компонент [!INCLUDE[ssSB](../../../includes/sssb-md.md)] использует для безопасности и проверки подлинности при связи с удаленным сервером.</span><span class="sxs-lookup"><span data-stu-id="d55fb-119"><xref:Microsoft.SqlServer.Management.Smo.Broker.RemoteServiceBinding> objects represent the settings that [!INCLUDE[ssSB](../../../includes/sssb-md.md)] uses for security and authentication when communicating with a remote service.</span></span>  
  
-   <span data-ttu-id="d55fb-120">Объекты <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceRoute> представляют маршрут компонента [!INCLUDE[ssSB](../../../includes/sssb-md.md)], который содержит информацию о нахождении службы и базы данных, в которой она определена.</span><span class="sxs-lookup"><span data-stu-id="d55fb-120"><xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceRoute> objects represents a [!INCLUDE[ssSB](../../../includes/sssb-md.md)] route, which contains the location information for the service and the database on which it is defined.</span></span> <span data-ttu-id="d55fb-121">Маршрут необходим для доставки сообщения.</span><span class="sxs-lookup"><span data-stu-id="d55fb-121">A route is required for message delivery.</span></span> <span data-ttu-id="d55fb-122">По умолчанию каждая база данных содержит маршрут, который указывает расположение как текущий экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d55fb-122">By default, each database contains a route that specifies the location as the current instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d55fb-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="d55fb-123">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Broker>   
 [<span data-ttu-id="d55fb-124">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="d55fb-124">SQL Server Service Broker</span></span>](../../../database-engine/configure-windows/sql-server-service-broker.md)  
  
  