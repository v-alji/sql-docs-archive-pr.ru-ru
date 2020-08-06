---
title: Удаление принудительной подписки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- removing subscriptions
- push subscriptions [SQL Server replication], deleting
- deleting subscriptions
- subscriptions [SQL Server replication], push
ms.assetid: 3c4847e2-aed9-4488-b45d-8164422bdb10
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 912958e00d117f51c5dc95c0dc1247d278acb0ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655644"
---
# <a name="delete-a-push-subscription"></a><span data-ttu-id="30b6e-102">Удаление принудительной подписки</span><span class="sxs-lookup"><span data-stu-id="30b6e-102">Delete a Push Subscription</span></span>
  <span data-ttu-id="30b6e-103">В данном разделе описывается удаление принудительной подписки в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="30b6e-103">This topic describes how to delete a push subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="30b6e-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="30b6e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="30b6e-105">**Для удаления принудительной подписки используется:**</span><span class="sxs-lookup"><span data-stu-id="30b6e-105">**To delete a push subscription, using:**</span></span>  
  
     [<span data-ttu-id="30b6e-106">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="30b6e-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="30b6e-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30b6e-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="30b6e-108">объекты RMO;</span><span class="sxs-lookup"><span data-stu-id="30b6e-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="30b6e-109">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="30b6e-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="30b6e-110">Удалите принудительную подписку на издателе (из папки **Локальные публикации** в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) или на подписчике (из папки **Локальные подписки** ).</span><span class="sxs-lookup"><span data-stu-id="30b6e-110">Delete a push subscription at the Publisher (from the **Local Publications** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) or the Subscriber (from the **Local Subscriptions** folder).</span></span> <span data-ttu-id="30b6e-111">При удалении подписки объекты и данные не удаляются из подписки, они должны быть удалены вручную.</span><span class="sxs-lookup"><span data-stu-id="30b6e-111">Deleting a subscription does not remove objects or data from the subscription; they must be removed manually.</span></span>  
  
#### <a name="to-delete-a-push-subscription-at-the-publisher"></a><span data-ttu-id="30b6e-112">Удаление принудительной подписки на издателе</span><span class="sxs-lookup"><span data-stu-id="30b6e-112">To delete a push subscription at the Publisher</span></span>  
  
1.  <span data-ttu-id="30b6e-113">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="30b6e-113">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="30b6e-114">Раскройте папку **Репликация** , а затем папку **Локальные публикации** .</span><span class="sxs-lookup"><span data-stu-id="30b6e-114">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="30b6e-115">Раскройте публикацию, связанную с удаляемой подпиской.</span><span class="sxs-lookup"><span data-stu-id="30b6e-115">Expand the publication associated with the subscription you want to delete.</span></span>  
  
4.  <span data-ttu-id="30b6e-116">Правой кнопкой мыши щелкните подписку и затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="30b6e-116">Right-click the subscription, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="30b6e-117">В окне подтверждения укажите, надо ли подключаться к подписчику для удаления сведений подписки.</span><span class="sxs-lookup"><span data-stu-id="30b6e-117">In the confirmation dialog box, select whether to connect to the Subscriber to delete subscription information.</span></span> <span data-ttu-id="30b6e-118">Если флажок **Соединиться с подписчиком** снят, необходимо позднее соединиться с подписчиком, чтобы удалить данные.</span><span class="sxs-lookup"><span data-stu-id="30b6e-118">If you clear the **Connect to Subscriber** checkbox, you should connect to the Subscriber later to delete the information.</span></span>  
  
#### <a name="to-delete-a-push-subscription-at-the-subscriber"></a><span data-ttu-id="30b6e-119">Удаление принудительной подписки на подписчике</span><span class="sxs-lookup"><span data-stu-id="30b6e-119">To delete a push subscription at the Subscriber</span></span>  
  
1.  <span data-ttu-id="30b6e-120">Подключитесь к подписчику в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]и раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="30b6e-120">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="30b6e-121">Раскройте папку **Репликация** , а затем — папку **Локальные подписки** .</span><span class="sxs-lookup"><span data-stu-id="30b6e-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="30b6e-122">Правой кнопкой мыши щелкните подписку, которую желаете удалить, и затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="30b6e-122">Right-click the subscription you want to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="30b6e-123">В окне подтверждения укажите, надо ли подключаться к издателю для удаления сведений подписки.</span><span class="sxs-lookup"><span data-stu-id="30b6e-123">In the confirmation dialog box, select whether to connect to the Publisher to delete subscription information.</span></span> <span data-ttu-id="30b6e-124">Если снять флажок **Соединиться с издателем** , то для удаления сведений потребуется соединиться с издателем позже.</span><span class="sxs-lookup"><span data-stu-id="30b6e-124">If you clear the **Connect to Publisher** check box, you should connect to the Publisher later to delete the information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="30b6e-125">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30b6e-125">Using Transact-SQL</span></span>  
 <span data-ttu-id="30b6e-126">Принудительные подписки можно удалять программно с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="30b6e-126">Push subscriptions can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="30b6e-127">Хранимые процедуры, используемые для этого, зависят от типа публикации, к которой принадлежит подписка.</span><span class="sxs-lookup"><span data-stu-id="30b6e-127">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="30b6e-128">Удаление принудительной подписки на публикацию моментальных снимков или транзакций</span><span class="sxs-lookup"><span data-stu-id="30b6e-128">To delete a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="30b6e-129">В издателе в базе данных публикации выполните процедуру [sp_dropsubscription (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30b6e-129">At the Publisher on the publication database, execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span></span> <span data-ttu-id="30b6e-130">Укажите **@publication** и **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="30b6e-130">Specify **@publication** and **@subscriber**.</span></span> <span data-ttu-id="30b6e-131">Задайте значение **all** в параметре **@article**.</span><span class="sxs-lookup"><span data-stu-id="30b6e-131">Specify a value of **all** for **@article**.</span></span> <span data-ttu-id="30b6e-132">Если распространитель недоступен, задайте значение **1** в параметре **@ignore_distributor** , чтобы удалить подписку без удаления связанных с ней объектов на распространителе (необязательно).</span><span class="sxs-lookup"><span data-stu-id="30b6e-132">(Optional) If the Distributor cannot be accessed, specify a value of **1** for **@ignore_distributor** to delete the subscription without removing related objects at the Distributor.</span></span>  
  
2.  <span data-ttu-id="30b6e-133">Чтобы удалить все метаданные репликации, оставшиеся в базе данных подписки, выполните в подписчике хранимую процедуру [sp_subscription_cleanup (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30b6e-133">At the Subscriber on the subscription database, execute [sp_subscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) to remove replication metadata in the subscription database.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="30b6e-134">Удаление принудительной подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="30b6e-134">To delete a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="30b6e-135">На издателе выполните [sp_dropmergesubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql), указав **@publication** **@subscriber** и **@subscriber_db** .</span><span class="sxs-lookup"><span data-stu-id="30b6e-135">At the Publisher, execute [sp_dropmergesubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql), specifying **@publication**, **@subscriber** and **@subscriber_db**.</span></span> <span data-ttu-id="30b6e-136">Если распространитель недоступен, задайте значение **1** в параметре **@ignore_distributor** , чтобы удалить подписку без удаления связанных с ней объектов на распространителе (необязательно).</span><span class="sxs-lookup"><span data-stu-id="30b6e-136">(Optional) If the Distributor cannot be accessed, specify a value of **1** for **@ignore_distributor** to delete the subscription without removing related objects at the Distributor.</span></span>  
  
2.  <span data-ttu-id="30b6e-137">В базе данных подписчика в подписчике выполните процедуру [sp_mergesubscription_cleanup (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30b6e-137">At the Subscriber on the subscription database, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql).</span></span> <span data-ttu-id="30b6e-138">Укажите **@publisher** , **@publisher_db** и **@publication** .</span><span class="sxs-lookup"><span data-stu-id="30b6e-138">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span> <span data-ttu-id="30b6e-139">Тем самым из базы данных подписки удаляются метаданные слияния.</span><span class="sxs-lookup"><span data-stu-id="30b6e-139">This removes merge metadata from the subscription database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="30b6e-140">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="30b6e-140">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="30b6e-141">В этом примере удаляется принудительная подписка на публикацию транзакций.</span><span class="sxs-lookup"><span data-stu-id="30b6e-141">This example deletes a push subscription to a transactional publication.</span></span>  
  
 [!code-sql[HowTo#sp_droptransubscription](../../snippets/tsql/SQL15/replication/howto/tsql/droptranpullsub.sql#sp_droptransubscription)]  
  
 <span data-ttu-id="30b6e-142">В этом примере удаляется принудительная подписка на публикацию слиянием.</span><span class="sxs-lookup"><span data-stu-id="30b6e-142">This example deletes a push subscription to a merge publication.</span></span>  
  
 [!code-sql[HowTo#sp_dropmergesubscription](../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepullsub.sql#sp_dropmergesubscription)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="30b6e-143">При помощи объектов RMO</span><span class="sxs-lookup"><span data-stu-id="30b6e-143">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="30b6e-144">Какие именно классы объектов RMO для этого применяются, зависит от типа публикации этой подписки.</span><span class="sxs-lookup"><span data-stu-id="30b6e-144">The RMO classes that you use to delete a push subscription depend on the type of publication to which the push subscription is subscribed.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="30b6e-145">Удаление принудительной подписки на публикацию моментальных снимков или транзакций</span><span class="sxs-lookup"><span data-stu-id="30b6e-145">To delete a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="30b6e-146">Создайте соединение с подписчиком с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="30b6e-146">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="30b6e-147">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.TransSubscription>.</span><span class="sxs-lookup"><span data-stu-id="30b6e-147">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class.</span></span>  
  
3.  <span data-ttu-id="30b6e-148">Установите свойства <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>и <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="30b6e-148">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="30b6e-149">Задайте соединение <xref:Microsoft.SqlServer.Management.Common.ServerConnection> с шага 1 для свойства <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="30b6e-149">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="30b6e-150">Проверьте свойство <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> , чтобы убедиться, что подписка существует.</span><span class="sxs-lookup"><span data-stu-id="30b6e-150">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the subscription exists.</span></span> <span data-ttu-id="30b6e-151">Если это свойство имеет значение `false`, значит, на шаге 2 были неправильно заданы свойства подписки либо подписка не существует.</span><span class="sxs-lookup"><span data-stu-id="30b6e-151">If the value of this property is `false`, either the subscription properties in step 2 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="30b6e-152">Вызовите метод <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="30b6e-152">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> method.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="30b6e-153">Удаление принудительной подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="30b6e-153">To delete a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="30b6e-154">Создайте соединение с подписчиком с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="30b6e-154">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="30b6e-155">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.MergeSubscription>.</span><span class="sxs-lookup"><span data-stu-id="30b6e-155">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class.</span></span>  
  
3.  <span data-ttu-id="30b6e-156">Установите свойства <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>и <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="30b6e-156">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="30b6e-157">Задайте соединение <xref:Microsoft.SqlServer.Management.Common.ServerConnection> с шага 1 для свойства <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="30b6e-157">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="30b6e-158">Проверьте свойство <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> , чтобы убедиться, что подписка существует.</span><span class="sxs-lookup"><span data-stu-id="30b6e-158">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the subscription exists.</span></span> <span data-ttu-id="30b6e-159">Если это свойство имеет значение `false`, значит, на шаге 2 были неправильно заданы свойства подписки либо подписка не существует.</span><span class="sxs-lookup"><span data-stu-id="30b6e-159">If the value of this property is `false`, either the subscription properties in step 2 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="30b6e-160">Вызовите метод <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="30b6e-160">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> method.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="30b6e-161">Примеры (объекты RMO)</span><span class="sxs-lookup"><span data-stu-id="30b6e-161">Examples (RMO)</span></span>  
 <span data-ttu-id="30b6e-162">Принудительные подписки могут быть удалены программно с помощью объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="30b6e-162">You can delete push subscriptions programmatically by using Replication Management Objects (RMO).</span></span>  
  
 [!code-csharp[HowTo#rmo_DropTranPushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_droptranpushsub)]  
  
 [!code-vb[HowTo#rmo_vb_DropTranPushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_droptranpushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="30b6e-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="30b6e-163">See Also</span></span>  
 <span data-ttu-id="30b6e-164">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="30b6e-164">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="30b6e-165">Рекомендации по защите репликации</span><span class="sxs-lookup"><span data-stu-id="30b6e-165">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
