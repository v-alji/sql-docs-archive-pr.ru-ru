---
title: Категория событий Broker | Документация Майкрософт
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Broker event category
- Broker event category [SQL Server]
- event classes [SQL Server], Broker event category
ms.assetid: 470dc93c-0dda-4d89-829b-937738d59b31
author: stevestein
ms.author: sstein
ms.openlocfilehash: 23f839416e3404bfdf0a7e61d1b1e8dbbb90ec95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655780"
---
# <a name="broker-event-category"></a><span data-ttu-id="05c04-102">Категория событий Broker</span><span class="sxs-lookup"><span data-stu-id="05c04-102">Broker Event Category</span></span>
  <span data-ttu-id="05c04-103">Категория событий **Broker** содержит общие события компонента Service Broker.</span><span class="sxs-lookup"><span data-stu-id="05c04-103">The **Broker** event category contains general Service Broker events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05c04-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="05c04-104">In This Section</span></span>  
  
|<span data-ttu-id="05c04-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="05c04-105">Topic</span></span>|<span data-ttu-id="05c04-106">Description</span><span class="sxs-lookup"><span data-stu-id="05c04-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="05c04-107">Класс событий Broker:Activation</span><span class="sxs-lookup"><span data-stu-id="05c04-107">Broker:Activation Event Class</span></span>](broker-activation-event-class.md)|<span data-ttu-id="05c04-108">Событие, формируемое при запуске монитором очереди хранимой процедуры активации.</span><span class="sxs-lookup"><span data-stu-id="05c04-108">An event generated when a queue monitor starts an activation stored procedure.</span></span>|  
|[<span data-ttu-id="05c04-109">Класс событий Broker:Connection</span><span class="sxs-lookup"><span data-stu-id="05c04-109">Broker:Connection Event Class</span></span>](broker-connection-event-class.md)|<span data-ttu-id="05c04-110">Событие, формируемое для передачи данных о состоянии транспортного соединения, которым управляет компонент Service Broker.</span><span class="sxs-lookup"><span data-stu-id="05c04-110">An event generated to report the status of a transport connection managed by Service Broker.</span></span>|  
|[<span data-ttu-id="05c04-111">Класс событий Broker:Conversation</span><span class="sxs-lookup"><span data-stu-id="05c04-111">Broker:Conversation Event Class</span></span>](broker-conversation-event-class.md)|<span data-ttu-id="05c04-112">Событие, формируемое для передачи данных о ходе диалога.</span><span class="sxs-lookup"><span data-stu-id="05c04-112">An event generated to report the progress of a conversation.</span></span>|  
|[<span data-ttu-id="05c04-113">Класс событий Broker:Conversation Group</span><span class="sxs-lookup"><span data-stu-id="05c04-113">Broker:Conversation Group Event Class</span></span>](broker-conversation-group-event-class.md)|<span data-ttu-id="05c04-114">Событие, формируемое, когда база данных создает или удаляет группу сообщений.</span><span class="sxs-lookup"><span data-stu-id="05c04-114">An event generated when the database creates or drops a conversation group.</span></span>|  
|[<span data-ttu-id="05c04-115">Класс событий Broker:Corrupted Message</span><span class="sxs-lookup"><span data-stu-id="05c04-115">Broker:Corrupted Message Event Class</span></span>](broker-corrupted-message-event-class.md)|<span data-ttu-id="05c04-116">Событие, формируемое для уведомления о получении базой данных поврежденного сообщения.</span><span class="sxs-lookup"><span data-stu-id="05c04-116">An event generated to report that the database has received a corrupt message.</span></span>|  
|[<span data-ttu-id="05c04-117">Класс событий Broker:Forwarded Message Dropped</span><span class="sxs-lookup"><span data-stu-id="05c04-117">Broker:Forwarded Message Dropped Event Class</span></span>](broker-forwarded-message-dropped-event-class.md)|<span data-ttu-id="05c04-118">Событие, формируемое в том случае, если SQL Server удаляет сообщение компонента Service Broker, которое было переслано.</span><span class="sxs-lookup"><span data-stu-id="05c04-118">An event generated when SQL Server drops a Service Broker message that was to have been forwarded.</span></span>|  
|[<span data-ttu-id="05c04-119">Класс событий Broker:Forwarded Message Sent</span><span class="sxs-lookup"><span data-stu-id="05c04-119">Broker:Forwarded Message Sent Event Class</span></span>](broker-forwarded-message-sent-event-class.md)|<span data-ttu-id="05c04-120">Событие, формируемое в том случае, если SQL Server пересылает сообщение компоненту Service Broker.</span><span class="sxs-lookup"><span data-stu-id="05c04-120">An event generated when SQL Server forwards a Service Broker message.</span></span>|  
|[<span data-ttu-id="05c04-121">Класс событий Broker:Message Classify</span><span class="sxs-lookup"><span data-stu-id="05c04-121">Broker:Message Classify Event Class</span></span>](broker-message-classify-event-class.md)|<span data-ttu-id="05c04-122">Событие, формируемое при определении компонентом Service Broker маршрута сообщения.</span><span class="sxs-lookup"><span data-stu-id="05c04-122">An event generated when Service Broker determines the routing for a message.</span></span>|  
|[<span data-ttu-id="05c04-123">Класс событий Broker: Message Drop</span><span class="sxs-lookup"><span data-stu-id="05c04-123">Broker:Message Drop Event Class</span></span>](broker-message-drop-event-class.md)|<span data-ttu-id="05c04-124">Событие, формируемое в том случае, если компонент Service Broker не может сохранить сообщение, которое должно быть доставлено службе в данном экземпляре.</span><span class="sxs-lookup"><span data-stu-id="05c04-124">An event generated when Service Broker is unable to retain a received message that should have been delivered to a service in this instance</span></span>|  
|[<span data-ttu-id="05c04-125">Класс событий Broker:Remote Message Ack</span><span class="sxs-lookup"><span data-stu-id="05c04-125">Broker:Remote Message Ack Event Class</span></span>](broker-remote-message-ack-event-class.md)|<span data-ttu-id="05c04-126">Событие, формируемое при получении или отправке компонентом Service Broker подтверждения сообщения.</span><span class="sxs-lookup"><span data-stu-id="05c04-126">An event generated when Service Broker sends or receives a message acknowledgement.</span></span>|  
  
 <span data-ttu-id="05c04-127">Также компонент Service Broker поддерживает два события аудита безопасности.</span><span class="sxs-lookup"><span data-stu-id="05c04-127">Two security audit events are also provided for Service Broker.</span></span> <span data-ttu-id="05c04-128">Дополнительные сведения об этих событиях см. в статьях [Класс событий Audit Broker Login](audit-broker-login-event-class.md) и [Класс событий Audit Broker Conversation](audit-broker-conversation-event-class.md).</span><span class="sxs-lookup"><span data-stu-id="05c04-128">For more information on those events, see [Audit Broker Login Event Class](audit-broker-login-event-class.md) and [Audit Broker Conversation Event Class](audit-broker-conversation-event-class.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c04-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="05c04-129">See Also</span></span>  
 [<span data-ttu-id="05c04-130">Категория событий «Аудит безопасности»</span><span class="sxs-lookup"><span data-stu-id="05c04-130">Security Audit Event Category</span></span>](https://docs.microsoft.com/bi-reference/trace-events/security-audit-event-category)  
  
  
