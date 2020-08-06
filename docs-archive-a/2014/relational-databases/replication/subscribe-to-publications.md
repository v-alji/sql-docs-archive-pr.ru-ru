---
title: Подписка на публикации | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.conc.subtopubs.f1
helpviewer_keywords:
- subscriptions [SQL Server replication], about subscriptions
- pull subscriptions [SQL Server replication]
- subscriptions [SQL Server replication]
- push subscriptions [SQL Server replication], about push subscriptions
- merge replication subscribing [SQL Server replication]
- merge replication subscribing [SQL Server replication], about subscribing
- publications [SQL Server replication], subscribing
- push subscriptions [SQL Server replication]
- pull subscriptions [SQL Server replication], about pull subscriptions
- snapshot replication [SQL Server], subscribing
- transactional replication, subscribing
ms.assetid: 088ee30a-05ab-47c4-92ed-316b93e12445
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c565aae26c6d549eb67043168797d5fb059c8e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655023"
---
# <a name="subscribe-to-publications"></a><span data-ttu-id="e14e9-102">Subscribe to Publications</span><span class="sxs-lookup"><span data-stu-id="e14e9-102">Subscribe to Publications</span></span>
  <span data-ttu-id="e14e9-103">Подписка представляет собой запрос на копию данных и объектов из базы данных в публикации.</span><span class="sxs-lookup"><span data-stu-id="e14e9-103">A subscription is a request for a copy of the data and database objects in a publication.</span></span> <span data-ttu-id="e14e9-104">Подписка определяет получаемую публикацию, а также место и время ее получения.</span><span class="sxs-lookup"><span data-stu-id="e14e9-104">A subscription defines which publication will be received, and where and when it will be received.</span></span> <span data-ttu-id="e14e9-105">При планировании подписок необходимо определить место обработки агентом.</span><span class="sxs-lookup"><span data-stu-id="e14e9-105">When planning for subscriptions, consider where you want agent processing to occur.</span></span> <span data-ttu-id="e14e9-106">Выбранный тип подписки определяет место запуска агента.</span><span class="sxs-lookup"><span data-stu-id="e14e9-106">The type of subscription you choose controls where the agent runs.</span></span> <span data-ttu-id="e14e9-107">В случае принудительной подписки агент слияния или агент распространителя запускается у распространителя, а в случае подписки по запросу агент запускается у подписчиков.</span><span class="sxs-lookup"><span data-stu-id="e14e9-107">With a push subscription, the Merge Agent or Distribution Agent runs at the Distributor, whereas with a pull subscription, agents run at the Subscribers.</span></span> <span data-ttu-id="e14e9-108">После того, как подписка создана, ее тип нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="e14e9-108">After a subscription is created, it cannot be changed from one type to another.</span></span>  
  
|<span data-ttu-id="e14e9-109">Подписка</span><span class="sxs-lookup"><span data-stu-id="e14e9-109">Subscription</span></span>|<span data-ttu-id="e14e9-110">Характеристики</span><span class="sxs-lookup"><span data-stu-id="e14e9-110">Characteristics</span></span>|<span data-ttu-id="e14e9-111">Использовать</span><span class="sxs-lookup"><span data-stu-id="e14e9-111">Use When</span></span>|  
|------------------|---------------------|--------------|  
|<span data-ttu-id="e14e9-112">Принудительная подписка</span><span class="sxs-lookup"><span data-stu-id="e14e9-112">Push Subscription</span></span>|<span data-ttu-id="e14e9-113">В случае принудительной подписки издатель передает изменения подписчику без запроса со стороны последнего.</span><span class="sxs-lookup"><span data-stu-id="e14e9-113">With a push subscription, the Publisher propagates changes to a Subscriber without a request from the Subscriber.</span></span> <span data-ttu-id="e14e9-114">Изменения могут передаваться подписчикам по запросу, непрерывно или по расписанию.</span><span class="sxs-lookup"><span data-stu-id="e14e9-114">Changes can be pushed to Subscribers on demand, continuously, or on a scheduled basis.</span></span> <span data-ttu-id="e14e9-115">Агент распространителя или агент слияния запускается у распространителя.</span><span class="sxs-lookup"><span data-stu-id="e14e9-115">The Distribution Agent or Merge Agent runs at the Distributor.</span></span>|<span data-ttu-id="e14e9-116">Синхронизация данных обычно будет осуществляться непрерывно или по повторяющемуся расписанию.</span><span class="sxs-lookup"><span data-stu-id="e14e9-116">Data will typically be synchronized continuously or on a frequently recurring schedule.</span></span><br /><br /> <span data-ttu-id="e14e9-117">Для публикаций требуется перемещение данных практически в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="e14e9-117">Publications require near real-time movement of data.</span></span><br /><br /> <span data-ttu-id="e14e9-118">Повышенная загрузка процессора у распространителя не влияет на производительность.</span><span class="sxs-lookup"><span data-stu-id="e14e9-118">The higher processor overhead at the Distributor does not affect performance.</span></span><br /><br /> <span data-ttu-id="e14e9-119">Наиболее часто используется с репликацией моментальных снимков и с репликацией транзакций.</span><span class="sxs-lookup"><span data-stu-id="e14e9-119">Most often used with snapshot and transactional replication.</span></span>|  
|<span data-ttu-id="e14e9-120">Подписка по запросу</span><span class="sxs-lookup"><span data-stu-id="e14e9-120">Pull Subscription</span></span>|<span data-ttu-id="e14e9-121">В случае подписки по запросу подписчик запрашивает изменения, внесенные у издателя.</span><span class="sxs-lookup"><span data-stu-id="e14e9-121">With a pull subscription, the Subscriber requests changes made at the Publisher.</span></span> <span data-ttu-id="e14e9-122">Подписки по запросу позволяют пользователю подписчика определить момент синхронизации изменений данных.</span><span class="sxs-lookup"><span data-stu-id="e14e9-122">Pull subscriptions allow the user at the Subscriber to determine when the data changes are synchronized.</span></span> <span data-ttu-id="e14e9-123">Агент распространителя или агент слияния запускается у подписчика.</span><span class="sxs-lookup"><span data-stu-id="e14e9-123">The Distribution Agent or the Merge Agent runs at the Subscriber.</span></span>|<span data-ttu-id="e14e9-124">Синхронизация данных обычно будет осуществляться по запросу или по расписанию, а не непрерывно.</span><span class="sxs-lookup"><span data-stu-id="e14e9-124">Data will typically be synchronized on demand or on a schedule rather than continuously.</span></span><br /><br /> <span data-ttu-id="e14e9-125">У публикации большое количество подписчиков, и/или запуск всех агентов на распространителе потребует слишком большого количества ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e14e9-125">The publication has a large number of Subscribers, and/or it would be too resource-intensive to run all the agents at the Distributor.</span></span><br /><br /> <span data-ttu-id="e14e9-126">Подписчики автономны, не подключены или мобильны.</span><span class="sxs-lookup"><span data-stu-id="e14e9-126">Subscribers are autonomous, disconnected, and/or mobile.</span></span> <span data-ttu-id="e14e9-127">Подписчики будут определять момент подключения и синхронизации изменений.</span><span class="sxs-lookup"><span data-stu-id="e14e9-127">Subscribers will determine when they will connect and synchronize changes.</span></span><br /><br /> <span data-ttu-id="e14e9-128">Наиболее часто используется с репликацией слиянием.</span><span class="sxs-lookup"><span data-stu-id="e14e9-128">Most often used with merge replication.</span></span>|  
  
## <a name="merge-replication-subscription-types"></a><span data-ttu-id="e14e9-129">Типы подписки на репликацию слиянием</span><span class="sxs-lookup"><span data-stu-id="e14e9-129">Merge Replication Subscription Types</span></span>  
 <span data-ttu-id="e14e9-130">Все типы репликации поддерживают принудительные подписки и подписки по запросу.</span><span class="sxs-lookup"><span data-stu-id="e14e9-130">All replication types allow push and pull subscriptions.</span></span> <span data-ttu-id="e14e9-131">Для репликации слиянием используются два дополнительных термина с целью различения подписок: клиентские подписки и серверные подписки.</span><span class="sxs-lookup"><span data-stu-id="e14e9-131">Merge replication uses two additional terms to distinguish subscriptions: client subscriptions and server subscriptions.</span></span> <span data-ttu-id="e14e9-132">Подписки как клиентского, так и серверного типов могут использоваться для принудительных подписок и подписок по запросу.</span><span class="sxs-lookup"><span data-stu-id="e14e9-132">Both client and server subscription types can be used with push and pull subscriptions.</span></span> <span data-ttu-id="e14e9-133">Клиентские подписки подходят для большинства подписчиков, в то время как серверные подписки обычно используются для подписчиков, которые повторно публикуют данные для других подписчиков.</span><span class="sxs-lookup"><span data-stu-id="e14e9-133">Client subscriptions are appropriate for most Subscribers, whereas server subscriptions are typically used for Subscribers that republish data to other Subscribers.</span></span> <span data-ttu-id="e14e9-134">Выбор подписки влияет на разрешение конфликтов.</span><span class="sxs-lookup"><span data-stu-id="e14e9-134">Subscription choice also affects conflict resolution.</span></span>  
  
## <a name="non-sql-server-subscribers"></a><span data-ttu-id="e14e9-135">Подписчики, отличные от подписчиков SQL Server</span><span class="sxs-lookup"><span data-stu-id="e14e9-135">Non-SQL Server Subscribers</span></span>  
 <span data-ttu-id="e14e9-136">Клиенты Oracle и IBM DB2 могут подписываться на публикации моментальных снимков и публикации транзакций с использованием принудительных подписок.</span><span class="sxs-lookup"><span data-stu-id="e14e9-136">Oracle and IBM DB2 can subscribe to snapshot and transactional publications using push subscriptions.</span></span> <span data-ttu-id="e14e9-137">Дополнительные сведения см. в статье [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="e14e9-137">For more information, see [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span></span>  
  
## <a name="creating-subscriptions"></a><span data-ttu-id="e14e9-138">Создание подписок</span><span class="sxs-lookup"><span data-stu-id="e14e9-138">Creating Subscriptions</span></span>  
 <span data-ttu-id="e14e9-139">Чтобы создать подписку, нужно ввести следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="e14e9-139">To create a subscription, you supply the following information:</span></span>  
  
-   <span data-ttu-id="e14e9-140">Имя публикации.</span><span class="sxs-lookup"><span data-stu-id="e14e9-140">The name of the publication.</span></span>  
  
-   <span data-ttu-id="e14e9-141">Имя подписчика и базы данных подписки.</span><span class="sxs-lookup"><span data-stu-id="e14e9-141">The name of the Subscriber and the subscription database.</span></span>  
  
-   <span data-ttu-id="e14e9-142">Где запускается агент распространителя или агент слияния — на распространителе или на подписчике.</span><span class="sxs-lookup"><span data-stu-id="e14e9-142">Whether the Distribution Agent or Merge Agent runs at the Distributor or at the Subscriber.</span></span>  
  
-   <span data-ttu-id="e14e9-143">Агент распространителя или агент слияния работает постоянно, запускается по расписанию или только по запросу.</span><span class="sxs-lookup"><span data-stu-id="e14e9-143">Whether the Distribution Agent or Merge Agent runs continuously, on a scheduled basis, or on demand only.</span></span>  
  
-   <span data-ttu-id="e14e9-144">Необходимость создания агентом моментальных снимков исходного моментального снимка для подписки и необходимость применения агентом распространителя или агентом слияния этого моментального снимка на подписчике.</span><span class="sxs-lookup"><span data-stu-id="e14e9-144">Whether the Snapshot Agent should create an initial snapshot for the subscription and whether the Distribution Agent or Merge Agent should apply that snapshot at the Subscriber.</span></span>  
  
-   <span data-ttu-id="e14e9-145">Учетные записи, с которыми будет запускаться агент распространителя или агент слияния.</span><span class="sxs-lookup"><span data-stu-id="e14e9-145">Accounts under which the Distribution Agent or Merge Agent will run.</span></span>  
  
-   <span data-ttu-id="e14e9-146">Для репликации слиянием — тип подписки: серверная или клиентская.</span><span class="sxs-lookup"><span data-stu-id="e14e9-146">For merge replication, the type of subscription: server or client.</span></span>  
  
 <span data-ttu-id="e14e9-147">**Создание принудительной подписки**</span><span class="sxs-lookup"><span data-stu-id="e14e9-147">**To create a push subscription**</span></span>  
  
 [<span data-ttu-id="e14e9-148">Создание принудительной подписки</span><span class="sxs-lookup"><span data-stu-id="e14e9-148">Create a Push Subscription</span></span>](create-a-push-subscription.md)  
  
 <span data-ttu-id="e14e9-149">**Просмотр или изменение свойств принудительной подписки**</span><span class="sxs-lookup"><span data-stu-id="e14e9-149">**To view or modify push subscription properties**</span></span>  
  
 [<span data-ttu-id="e14e9-150">Просмотр и изменение свойств принудительной подписки</span><span class="sxs-lookup"><span data-stu-id="e14e9-150">View and Modify Push Subscription Properties</span></span>](view-and-modify-push-subscription-properties.md)  
  
 <span data-ttu-id="e14e9-151">**Удаление принудительной подписки**</span><span class="sxs-lookup"><span data-stu-id="e14e9-151">**To delete a push subscription**</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="e14e9-152">: [Удаление принудительной подписки](delete-a-push-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="e14e9-152">: [Delete a Push Subscription](delete-a-push-subscription.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e14e9-153">Удаление подписки не приводит к удалению опубликованных объектов у подписчика.</span><span class="sxs-lookup"><span data-stu-id="e14e9-153">Deleting a subscription does not remove published objects from the Subscriber.</span></span>  
  
 <span data-ttu-id="e14e9-154">**Создание подписки по запросу**</span><span class="sxs-lookup"><span data-stu-id="e14e9-154">**To create a pull subscription**</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="e14e9-155">: [Создание подписки по запросу](create-a-pull-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="e14e9-155">: [Create a Pull Subscription](create-a-pull-subscription.md)</span></span>  
  
 <span data-ttu-id="e14e9-156">**Просмотр или изменение свойств подписки по запросу**</span><span class="sxs-lookup"><span data-stu-id="e14e9-156">**To view or modify pull subscription properties**</span></span>  
  
 [<span data-ttu-id="e14e9-157">Просмотр и изменение свойств подписки по запросу</span><span class="sxs-lookup"><span data-stu-id="e14e9-157">View and Modify Pull Subscription Properties</span></span>](view-and-modify-pull-subscription-properties.md)  
  
 <span data-ttu-id="e14e9-158">**Удаление подписки по запросу**</span><span class="sxs-lookup"><span data-stu-id="e14e9-158">**To delete a pull subscription**</span></span>  
  
 [<span data-ttu-id="e14e9-159">Удаление подписки по запросу</span><span class="sxs-lookup"><span data-stu-id="e14e9-159">Delete a Pull Subscription</span></span>](delete-a-pull-subscription.md)  
  
## <a name="see-also"></a><span data-ttu-id="e14e9-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="e14e9-160">See Also</span></span>  
 <span data-ttu-id="e14e9-161">[Защита подписчика](security/secure-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="e14e9-161">[Secure the Subscriber](security/secure-the-subscriber.md) </span></span>  
 [<span data-ttu-id="e14e9-162">Окончание срока действия и отключение подписки</span><span class="sxs-lookup"><span data-stu-id="e14e9-162">Subscription Expiration and Deactivation</span></span>](subscription-expiration-and-deactivation.md)  
  
  
