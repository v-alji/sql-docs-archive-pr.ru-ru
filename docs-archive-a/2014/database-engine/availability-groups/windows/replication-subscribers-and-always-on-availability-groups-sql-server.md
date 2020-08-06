---
title: Подписчики и группы доступности AlwaysOn репликации (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 01/16/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover subscribers with AlwaysOn
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 0995f269-0580-43ed-b8bf-02b9ad2d7ee6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 449b5ac416f2ae86395c40a984678ed4258b3b85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665125"
---
# <a name="replication-subscribers-and-alwayson-availability-groups-sql-server"></a><span data-ttu-id="32ae8-102">Подписчики репликации и группы доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32ae8-102">Replication Subscribers and AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="32ae8-103">Если в группе доступности AlwaysOn, содержащей базу данных, которая является подписчиком репликации, выполняется отработка отказа, то подписка на репликацию может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="32ae8-103">When an AlwaysOn availability group containing a database that is a replication subscriber fails over, the replication subscription might fail.</span></span> <span data-ttu-id="32ae8-104">Для владельцев принудительной подписки на репликацию транзакций агент распространителя сможет продолжить репликацию автоматически после отработки отказа, если подписка была создана с использованием имени прослушивателя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="32ae8-104">For transactional replication push subscribers, the distribution agent will continue to replicate automatically after a failover if the subscription was created using the AG listener name.</span></span> <span data-ttu-id="32ae8-105">Для владельцев подписки по запросу на репликацию транзакций агент распространителя сможет продолжить репликацию автоматически после отработки отказа, если подписка была создана с использованием имени прослушивателя группы доступности, а исходный сервер подписчика настроен и запущен.</span><span class="sxs-lookup"><span data-stu-id="32ae8-105">For transactional replication pull subscribers, the distribution agent will continue to replicate automatically after a failover, if the subscription was created using the AG listener name and the original subscriber server is up and running.</span></span> <span data-ttu-id="32ae8-106">Это обусловлено тем, что задания агента распространения создаются только для исходного подписчика (первичная реплика группы доступности).</span><span class="sxs-lookup"><span data-stu-id="32ae8-106">This is because the distribution agent jobs only get created on the original subscriber (primary replica of the AG).</span></span> <span data-ttu-id="32ae8-107">Для подписчиков на публикацию слиянием администратор репликации должен вручную перенастроить подписчик путем повторного создания подписки.</span><span class="sxs-lookup"><span data-stu-id="32ae8-107">For merge subscribers, a replication administrator must manually reconfigure the subscriber, by recreating the subscription.</span></span>  
  
## <a name="what-is-supported"></a><span data-ttu-id="32ae8-108">Что поддерживается</span><span class="sxs-lookup"><span data-stu-id="32ae8-108">What is Supported</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="32ae8-109">поддерживает автоматический переход издателя и подписчиков транзакции и переход подписчиков на публикацию слиянием вручную.</span><span class="sxs-lookup"><span data-stu-id="32ae8-109">replication supports the automatic failover of the publisher, the automatic failover of transactional subscribers, and the manual failover of merge subscribers.</span></span> <span data-ttu-id="32ae8-110">Отработка отказа распространителя на базе данных доступности не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="32ae8-110">The failover of a distributor on an availability database is not supported.</span></span> <span data-ttu-id="32ae8-111">AlwaysOn нельзя объединять со сценариями Websync и [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="32ae8-111">AlwaysOn cannot be combined with Websync and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Compact scenarios.</span></span>  
  
 <span data-ttu-id="32ae8-112">**Перенос подписки слиянием по запросу**</span><span class="sxs-lookup"><span data-stu-id="32ae8-112">**Failover of a Merge Pull Subscription**</span></span>  
  
 <span data-ttu-id="32ae8-113">При отработке отказа группы доступности подписка по запросу возвращает ошибку, так как соответствующий агент не может найти задания, сохраненные в базе данных **msdb** экземпляра сервера, на котором расположена первичная реплика; он недоступен вследствие отказа экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="32ae8-113">A pull subscription fails upon availability group failover, because pull agent cannot find the jobs stored in the **msdb** database of the server instance that hosts the primary replica; which is not available because the server instance has failed.</span></span>  
  
 <span data-ttu-id="32ae8-114">**Перенос принудительной подписки слиянием**</span><span class="sxs-lookup"><span data-stu-id="32ae8-114">**Failover of a Merge Push Subscription**</span></span>  
  
 <span data-ttu-id="32ae8-115">При отработке отказа группы доступности принудительная подписка возвращает ошибку, так как соответствующий агент больше не может подключиться к изначальной базе данных подписки на изначальном подписчике.</span><span class="sxs-lookup"><span data-stu-id="32ae8-115">A push subscription fails upon availability group failover, because the push agent can no longer connect to original subscription database on original subscriber.</span></span>  
  
## <a name="how-to-create-transactional-subscription-in-an-alwayson-environment"></a><span data-ttu-id="32ae8-116">Создание подписок транзакций в среде AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="32ae8-116">How to Create Transactional Subscription in an AlwaysOn Environment</span></span>  
 <span data-ttu-id="32ae8-117">Для настройки и отработки отказа группы доступности подписчика в отношении репликации транзакций выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="32ae8-117">For transactional replication, use the following steps to configure and failover a subscriber availability group:</span></span>  
  
1.  <span data-ttu-id="32ae8-118">Прежде чем создавать подписку, добавьте базу данных подписчика в соответствующую группу доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="32ae8-118">Before creating the subscription, add the subscriber database to the appropriate AlwaysOn availability group.</span></span>  
  
2.  <span data-ttu-id="32ae8-119">Добавьте прослушиватель группы доступности подписчика в качестве связанного сервера во все узлы группы доступности.</span><span class="sxs-lookup"><span data-stu-id="32ae8-119">Add the subscriber's availability group Listener as a linked server to all nodes of the availability group.</span></span> <span data-ttu-id="32ae8-120">Это действие гарантирует, что все возможные участники отработки отказа будут знать о существовании прослушивателя и смогут к нему подключиться.</span><span class="sxs-lookup"><span data-stu-id="32ae8-120">This step ensures that all potential failover partners are aware of and can connect to the listener.</span></span>  
  
3.  <span data-ttu-id="32ae8-121">Используя сценарий в **Создание Репликации Транзакции Принудительной Подписки** разделе ниже, создайте подписку, используя имя прослушивателя группы доступности подписчика.</span><span class="sxs-lookup"><span data-stu-id="32ae8-121">Using the script in the **Creating a Transactional Replication Push Subscription** section below, create the subscription using the name of the availability group listener of the subscriber.</span></span> <span data-ttu-id="32ae8-122">После отработки отказа имя прослушивателя всегда будет допустимым, а фактическое имя сервера подписчика будет зависеть от того, какой узел стал основным.</span><span class="sxs-lookup"><span data-stu-id="32ae8-122">After a failover, the listener name will always remain valid, whereas the actual server name of the subscriber will depend on the actual node that became the new primary.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="32ae8-123">Подписка должна быть создана с использованием сценария [!INCLUDE[tsql](../../../includes/tsql-md.md)] и не может быть создана с использованием [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32ae8-123">The subscription must be created by using a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script and cannot be created using [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="32ae8-124">Создание подписки по запросу.</span><span class="sxs-lookup"><span data-stu-id="32ae8-124">If creating a pull subscription:</span></span>  
  
    1.  <span data-ttu-id="32ae8-125">В среде [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]на основном узле подписчика откройте дерево агента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32ae8-125">In [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], on the primary subscriber node, open the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent tree.</span></span>  
  
    2.  <span data-ttu-id="32ae8-126">Найдите задание **агента распространителя по запросу** и измените его.</span><span class="sxs-lookup"><span data-stu-id="32ae8-126">Identify the **Pull Distribution Agent** job and edit the job.</span></span>  
  
    3.  <span data-ttu-id="32ae8-127">На шаге задания **Запуск агента** выполните проверку параметров `-Publisher` и `-Distributor` .</span><span class="sxs-lookup"><span data-stu-id="32ae8-127">On the **Run Agent** job step, check the `-Publisher` and `-Distributor` parameters.</span></span> <span data-ttu-id="32ae8-128">Эти параметры должны содержать правильные имена непосредственно применяемого сервера, экземпляра издателя и распространителя.</span><span class="sxs-lookup"><span data-stu-id="32ae8-128">Make sure that these parameters contain the correct direct server and instance names of the publisher and distributor server.</span></span>  
  
    4.  <span data-ttu-id="32ae8-129">В качестве значения параметра `-Subscriber` укажите имя прослушивателя группы доступности подписчика.</span><span class="sxs-lookup"><span data-stu-id="32ae8-129">Change the `-Subscriber` parameter to the subscriber's availability group listener name.</span></span>  
  
 <span data-ttu-id="32ae8-130">Когда подписка создается с помощью этих действий, вам не придется больше ничего делать после отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="32ae8-130">When you create your subscription following these steps, then you won't have to do anything after a failover.</span></span>  
  
## <a name="creating-a-transactional-replication-push-subscription"></a><span data-ttu-id="32ae8-131">Создание Репликации Транзакции Принудительной Подписки</span><span class="sxs-lookup"><span data-stu-id="32ae8-131">Creating a Transactional Replication Push Subscription</span></span>  
  
```  
-- commands to execute at the publisher, in the publisher database:  
use [<publisher database name>]  
EXEC sp_addsubscription @publication = N'<publication name>',   
       @subscriber = N'<availability group listener name>',   
       @destination_db = N'<subscriber database name>',   
       @subscription_type = N'Push',   
       @sync_type = N'automatic', @article = N'all', @update_mode = N'read only', @subscriber_type = 0;  
GO  
  
EXEC sp_addpushsubscription_agent @publication = N'<publication name>',   
       @subscriber = N'<availability group listener name>',   
       @subscriber_db = N'<subscriber database name>',   
       @job_login = null, @job_password = null, @subscriber_security_mode = 1;  
GO  
```  
  
## <a name="to-resume-the-merge-agents-after-the-availability-group-of-the-subscriber-fails-over"></a><span data-ttu-id="32ae8-132">Возобновление работы агентов слияния после переноса группы доступности подписчика</span><span class="sxs-lookup"><span data-stu-id="32ae8-132">To Resume the Merge Agents After the Availability Group of the Subscriber Fails Over</span></span>  
 <span data-ttu-id="32ae8-133">Для репликации слиянием администратор репликации должен вручную перенастроить подписчик следующим образом.</span><span class="sxs-lookup"><span data-stu-id="32ae8-133">For merge replication, a replication administrator must manually reconfigure the subscriber with the following steps:</span></span>  
  
1.  <span data-ttu-id="32ae8-134">Для удаления старой подписки подписчика выполните процедуру `sp_subscription_cleanup`.</span><span class="sxs-lookup"><span data-stu-id="32ae8-134">Execute `sp_subscription_cleanup` to remove the old subscription for the subscriber.</span></span> <span data-ttu-id="32ae8-135">Запустите действие на новой первичной реплике (которая раньше была вторичной репликой).</span><span class="sxs-lookup"><span data-stu-id="32ae8-135">Perform this action on the new primary replica (which was formerly the secondary replica).</span></span>  
  
2.  <span data-ttu-id="32ae8-136">Создайте подписку заново, начиная с нового моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="32ae8-136">Recreate the subscription by creating a new subscription, beginning with a new snapshot.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32ae8-137">Текущий процесс неудобен для подписчиков репликации слиянием, однако основным сценарием для репликации слиянием являются отключенные пользователи (ПК, ноутбуки, переносные устройства), которые не используют группы доступности AlwaysOn в подписчике.</span><span class="sxs-lookup"><span data-stu-id="32ae8-137">The current process is inconvenient for merge replication subscribers, however the main scenario for merge replication is disconnected users (desktops, laptops, handset devices) which will not use AlwaysOn availability groups on the subscriber.</span></span>  
  
  
