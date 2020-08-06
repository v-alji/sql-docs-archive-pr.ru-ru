---
title: Реализация уведомлений о событиях | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- event notifications [SQL Server], target service
- target service [SQL Server]
- event notifications [SQL Server], creating
ms.assetid: 29ac8f68-a28a-4a77-b67b-a8663001308c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a89c66ca5c3b420fff14c087bd604b16c641369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664825"
---
# <a name="implement-event-notifications"></a><span data-ttu-id="c6cbb-102">Реализация уведомлений о событиях</span><span class="sxs-lookup"><span data-stu-id="c6cbb-102">Implement Event Notifications</span></span>
  <span data-ttu-id="c6cbb-103">Для реализации уведомлений о событиях необходимо сперва создать целевую службу, которая будет получать уведомления о событиях, а затем создать уведомление о событиях.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-103">To implement an event notification, you must first create a target service to receive event notifications, and then create the event notification.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="c6cbb-104">на удаленном сервере, необходимо настроить безопасность диалога.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-104">dialog security should be configured for event notifications that send messages to a service broker on a remote server.</span></span> <span data-ttu-id="c6cbb-105">Безопасность диалога должна быть настроена вручную согласно модели полной безопасности.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-105">Dialog security must be configured manually according to the full security model.</span></span>  
  
## <a name="creating-the-target-service"></a><span data-ttu-id="c6cbb-106">Создание целевой службы</span><span class="sxs-lookup"><span data-stu-id="c6cbb-106">Creating the Target Service</span></span>  
 <span data-ttu-id="c6cbb-107">Не нужно создавать службу, инициирующую компонент [!INCLUDE[ssSB](../../includes/sssb-md.md)], так как [!INCLUDE[ssSB](../../includes/sssb-md.md)] включает в себя следующий специальный тип сообщения и контракт для уведомлений о событиях:</span><span class="sxs-lookup"><span data-stu-id="c6cbb-107">You do not have to create a [!INCLUDE[ssSB](../../includes/sssb-md.md)]-initiating service because [!INCLUDE[ssSB](../../includes/sssb-md.md)] includes the following specific message type and contract for event notifications:</span></span>  
  
```  
https://schemas.microsoft.com/SQL/Notifications/PostEventNotification  
```  
  
 <span data-ttu-id="c6cbb-108">Целевая служба, принимающая уведомления о событиях, должна поддерживать такой уже существующий контракт.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-108">The target service that receives event notifications must honor this preexisting contract.</span></span>  
  
 <span data-ttu-id="c6cbb-109">**Создание целевой службы**</span><span class="sxs-lookup"><span data-stu-id="c6cbb-109">**To create a target service**:</span></span>  
  
1.  <span data-ttu-id="c6cbb-110">Создайте очередь для получения сообщений.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-110">Create a queue to receive messages.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6cbb-111">Очередь получает сообщения следующего типа: `https://schemas.microsoft.com/SQL/Notifications/QueryNotification`.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-111">The queue receives the following message type: `https://schemas.microsoft.com/SQL/Notifications/QueryNotification`.</span></span>  
  
2.  <span data-ttu-id="c6cbb-112">Создайте службу для очереди, ссылающуюся на контракт уведомлений о событии.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-112">Create a service on the queue that references the event notifications contract.</span></span>  
  
3.  <span data-ttu-id="c6cbb-113">Создайте маршрут для службы, чтобы определить адрес, на который компонент [!INCLUDE[ssSB](../../includes/sssb-md.md)] будет отправлять сообщения этой службе.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-113">Create a route on the service to define the address to which [!INCLUDE[ssSB](../../includes/sssb-md.md)] sends messages for the service.</span></span> <span data-ttu-id="c6cbb-114">Если уведомление о событии отправляется службе в той же базе данных, укажите `ADDRESS = 'LOCAL'`.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-114">For event notifications that target a service in the same database, specify `ADDRESS = 'LOCAL'`.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="c6cbb-115">определяет службу, получающую уведомления.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-115">routing determines the service that receives the notification messages.</span></span> <span data-ttu-id="c6cbb-116">Если уведомление о событии направляется службе на удаленном сервере, маршруты необходимо определить и на исходном, и на целевом сервере, чтобы обеспечить двухстороннюю связь.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-116">If the event notification targets a service on a remote server, both the source server and the target server must have routes defined on them to make sure that two-way communication occurs.</span></span>  
  
 <span data-ttu-id="c6cbb-117">В следующем примере создается очередь, служба для этой очереди и маршрут к службе, обрабатывающей сообщения от контракта уведомления о событиях:</span><span class="sxs-lookup"><span data-stu-id="c6cbb-117">The following example creates a queue, a service on the queue, and a route on the service to handle messages from the event notification contract.</span></span>  
  
```  
CREATE QUEUE NotifyQueue ;  
GO  
CREATE SERVICE NotifyService  
ON QUEUE NotifyQueue  
(  
[https://schemas.microsoft.com/SQL/Notifications/PostEventNotification]  
);  
GO  
CREATE ROUTE NotifyRoute  
WITH SERVICE_NAME = 'NotifyService',  
ADDRESS = 'LOCAL';  
GO  
```  
  
## <a name="creating-the-event-notification"></a><span data-ttu-id="c6cbb-118">Создание уведомления о событии</span><span class="sxs-lookup"><span data-stu-id="c6cbb-118">Creating the Event Notification</span></span>  
 <span data-ttu-id="c6cbb-119">Уведомления о событиях создаются при помощи инструкции языка [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE EVENT NOTIFICATION и удаляются при помощи инструкции DROP EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-119">Event notifications are created by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE EVENT NOTIFICATION statement, and are dropped by using the DROP EVENT NOTIFICATION STATEMENT.</span></span> <span data-ttu-id="c6cbb-120">Чтобы изменить уведомление о событии, его нужно удалить, а затем создать заново.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-120">To modify an event notification, you must drop and re-create the event notification.</span></span>  
  
 <span data-ttu-id="c6cbb-121">В следующем примере создается уведомление о событии `CreateDatabaseNotification`.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-121">The following example creates the event notification `CreateDatabaseNotification`.</span></span> <span data-ttu-id="c6cbb-122">Это уведомление отправляет предварительно созданной службе `CREATE_DATABASE` сообщения обо всех событиях `NotifyService`, происходящих на сервере.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-122">This notification sends a message about any `CREATE_DATABASE` event that occurs on the server to the `NotifyService` service that was previously created.</span></span>  
  
```  
CREATE EVENT NOTIFICATION CreateDatabaseNotification  
ON SERVER  
FOR CREATE_DATABASE  
TO SERVICE 'NotifyService', '8140a771-3c4b-4479-8ac0-81008ab17984' ;  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="c6cbb-123">Уведомления о событиях считают события CREATE_SCHEMA и определения <schema_element> в инструкциях CREATE SCHEMA различными событиями.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-123">Event notifications recognize CREATE_SCHEMA events and the <schema_element> definitions of CREATE SCHEMA statements as separate events.</span></span> <span data-ttu-id="c6cbb-124">Например, пусть создано уведомление о событиях CREATE_SCHEMA и CREATE_TABLE и выполняется следующий пакет.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-124">For example, an event notification is created on both the CREATE_SCHEMA and CREATE_TABLE events, and you run the following batch.</span></span>  
>   
>  `CREATE SCHEMA s`  
>   
>  `CREATE TABLE t1 (col1 int)`  
>   
>  <span data-ttu-id="c6cbb-125">В этом случае уведомление о событиях направляется дважды: в первый раз при возникновении события CREATE_SCHEMA, а во второй — при возникновении события CREATE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-125">In this case, the event notification is raised two times: Onne time when the CREATE_SCHEMA event occurs, and again when the CREATE_TABLE event occurs.</span></span> <span data-ttu-id="c6cbb-126">Рекомендуется либо избегать создания уведомлений о событиях одновременно для событий CREATE_SCHEMA и текстов <schema_element> в любых соответствующих определениях CREATE SCHEMA, либо встраивать в приложение логику, позволяющую избежать регистрации ненужных данных о событиях.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-126">We recommend that you either avoid creating event notifications on both the CREATE_SCHEMA events and the <schema_element> texts of any corresponding CREATE SCHEMA definitions, or build logic into your application to avoid capturing unwanted event data.</span></span>  
  
 <span data-ttu-id="c6cbb-127">**Создание уведомления о событии**</span><span class="sxs-lookup"><span data-stu-id="c6cbb-127">**To create an event notification**</span></span>  
  
-   [<span data-ttu-id="c6cbb-128">CREATE EVENT NOTIFICATION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c6cbb-128">CREATE EVENT NOTIFICATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-event-notification-transact-sql)  
  
 <span data-ttu-id="c6cbb-129">**Удаление уведомления о событии**</span><span class="sxs-lookup"><span data-stu-id="c6cbb-129">**To drop an event notification**</span></span>  
  
-   [<span data-ttu-id="c6cbb-130">DROP EVENT NOTIFICATION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c6cbb-130">DROP EVENT NOTIFICATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-event-notification-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="c6cbb-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="c6cbb-131">See Also</span></span>  
 <span data-ttu-id="c6cbb-132">[Получение сведений об уведомлениях о событиях](event-notifications.md) </span><span class="sxs-lookup"><span data-stu-id="c6cbb-132">[Get Information About Event Notifications](event-notifications.md) </span></span>  
 [<span data-ttu-id="c6cbb-133">EVENTDATA (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c6cbb-133">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
