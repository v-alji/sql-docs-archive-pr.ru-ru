---
title: Просмотр и изменение свойств принудительной подписки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing replication properties
- push subscriptions [SQL Server replication], properties
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], modifying
- modifying replication properties, push subscriptions
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 801d2995-7aa5-4626-906e-c8190758ec71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c1506d4f83fcfb94d62efd01c4d6447048fecfd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738177"
---
# <a name="view-and-modify-push-subscription-properties"></a><span data-ttu-id="33078-102">Просмотр и изменение свойств принудительной подписки</span><span class="sxs-lookup"><span data-stu-id="33078-102">View and Modify Push Subscription Properties</span></span>
  <span data-ttu-id="33078-103">В данном разделе описывается просмотр и изменение свойств принудительной подписки в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="33078-103">This topic describes how to view and modify push subscription properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="33078-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="33078-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="33078-105">**Для просмотра и изменения свойств принудительной подписки используется:**</span><span class="sxs-lookup"><span data-stu-id="33078-105">**To view and modify push subscription properties, using:**</span></span>  
  
     [<span data-ttu-id="33078-106">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="33078-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="33078-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="33078-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="33078-108">объекты RMO;</span><span class="sxs-lookup"><span data-stu-id="33078-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="33078-109">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="33078-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="33078-110">Просмотр и изменение свойств принудительной подписки со стороны издателя:</span><span class="sxs-lookup"><span data-stu-id="33078-110">View and modify push subscription properties from the Publisher in:</span></span>  
  
-   <span data-ttu-id="33078-111">В диалоговом окне **Свойства подписки — \<Publisher>: \<PublicationDatabase>** , которое можно открыть из [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33078-111">The **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, which is available from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="33078-112">На вкладке **Все подписки** в мониторе репликации.</span><span class="sxs-lookup"><span data-stu-id="33078-112">The **All Subscriptions** tab, which is available in Replication Monitor.</span></span> <span data-ttu-id="33078-113">Сведения о запуске монитора репликации см. в [этой статье](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="33078-113">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-management-studio"></a><span data-ttu-id="33078-114">Просмотр и изменение свойств принудительной подписки в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="33078-114">To view and modify push subscription properties in Management Studio</span></span>  
  
1.  <span data-ttu-id="33078-115">Подключитесь к издателю в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="33078-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="33078-116">Раскройте папку **Репликация** , а затем папку **Локальные публикации** .</span><span class="sxs-lookup"><span data-stu-id="33078-116">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="33078-117">Раскройте соответствующую публикацию, щелкните правой кнопкой мыши подписку и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="33078-117">Expand the appropriate publication, right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="33078-118">Измените свойства, если необходимо, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="33078-118">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-replication-monitor"></a><span data-ttu-id="33078-119">Просмотр и изменение свойств принудительной подписки в мониторе репликации</span><span class="sxs-lookup"><span data-stu-id="33078-119">To view and modify push subscription properties in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="33078-120">На левой панели монитора репликации раскройте группу издателей, раскройте нужный издатель, а затем выберите публикацию.</span><span class="sxs-lookup"><span data-stu-id="33078-120">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="33078-121">Перейдите на вкладку **Все подписки** .</span><span class="sxs-lookup"><span data-stu-id="33078-121">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="33078-122">Щелкните правой кнопкой мыши подписку и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="33078-122">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="33078-123">Измените свойства, если необходимо, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="33078-123">Modify any properties if necessary, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="33078-124">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="33078-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="33078-125">Принудительные подписки могут быть изменены программно, кроме того, с помощью хранимых процедур репликации можно программно получить доступ к их свойствам.</span><span class="sxs-lookup"><span data-stu-id="33078-125">Push subscriptions can be modified and their properties accessed programmatically using replication stored procedures.</span></span> <span data-ttu-id="33078-126">Хранимые процедуры, используемые для этого, зависят от типа публикации, к которой принадлежит подписка.</span><span class="sxs-lookup"><span data-stu-id="33078-126">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="33078-127">Просмотр свойств принудительной подписки на публикацию моментальных снимков или транзакций</span><span class="sxs-lookup"><span data-stu-id="33078-127">To view the properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="33078-128">На издателе в базе данных публикации выполните хранимую процедуру [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="33078-128">At the Publisher on the publication database, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span> <span data-ttu-id="33078-129">Укажите **@publication** , **@subscriber** и значение **ALL** для **@article** .</span><span class="sxs-lookup"><span data-stu-id="33078-129">Specify **@publication**, **@subscriber**, and a value of **all** for **@article**.</span></span>  
  
2.  <span data-ttu-id="33078-130">На издателе в базе данных публикации выполните хранимую процедуру [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), указав параметр **@subscriber**.</span><span class="sxs-lookup"><span data-stu-id="33078-130">At the Publisher on the publication database, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span>  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="33078-131">Изменение свойств принудительной подписки на публикацию моментальных снимков или транзакций</span><span class="sxs-lookup"><span data-stu-id="33078-131">To change the properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="33078-132">На издателе в базе данных публикации выполните хранимую процедуру [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql), указав параметр **@subscriber** и любые параметры для свойств подписчика, которые нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="33078-132">At the Publisher on the publication database, execute [sp_changesubscriber](/sql/relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql), specifying **@subscriber** and any parameters for the Subscriber properties being changed.</span></span>  
  
2.  <span data-ttu-id="33078-133">На издателе в базе данных публикации выполните хранимую процедуру [sp_changesubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="33078-133">At the Publisher on the publication database, execute [sp_changesubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscription-transact-sql).</span></span> <span data-ttu-id="33078-134">Укажите **@publication** , **@subscriber** , **@destination_db** , значение **ALL** для **@article** , изменяемое свойство подписки **@property** , а новое значение — как **@value** .</span><span class="sxs-lookup"><span data-stu-id="33078-134">Specify **@publication**, **@subscriber**, **@destination_db**, a value of **all** for **@article**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span> <span data-ttu-id="33078-135">При этом изменятся параметры безопасности для принудительной подписки.</span><span class="sxs-lookup"><span data-stu-id="33078-135">This changes security settings for the push subscription.</span></span>  
  
3.  <span data-ttu-id="33078-136">Чтобы изменить свойства пакета служб DTS подписки, выполните хранимую процедуру [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql) на подписчике для базы данных подписки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="33078-136">(Optional) To change the Data Transformation Services (DTS) package properties of a subscription, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql) at the Subscriber on the subscription database.</span></span> <span data-ttu-id="33078-137">Укажите идентификатор задания агент распространения для **@jobid** и следующих свойств пакета служб DTS:</span><span class="sxs-lookup"><span data-stu-id="33078-137">Specify the ID of the Distribution Agent job for **@jobid** and the following DTS package properties:</span></span>  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     <span data-ttu-id="33078-138">Свойства пакета служб подписки будут изменены.</span><span class="sxs-lookup"><span data-stu-id="33078-138">This changes the DTS package properties of a subscription.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="33078-139">Идентификатор задания можно получить, выполнив процедуру [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="33078-139">The job ID can be obtained by executing [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span>  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="33078-140">Просмотр свойств принудительной подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="33078-140">To view the properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="33078-141">На издателе в базе данных публикации выполните хранимую процедуру [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="33078-141">At the Publisher on the publication database, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql).</span></span> <span data-ttu-id="33078-142">Укажите **@publication** и **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="33078-142">Specify **@publication** and **@subscriber**.</span></span>  
  
2.  <span data-ttu-id="33078-143">На издателе выполните [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), указав **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="33078-143">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span>  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="33078-144">Изменение свойств принудительной подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="33078-144">To change the properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="33078-145">На издателе в базе данных публикации выполните хранимую процедуру [sp_changemergesubscription](/sql/relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="33078-145">At the Publisher on the publication database, execute [sp_changemergesubscription](/sql/relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql).</span></span> <span data-ttu-id="33078-146">Укажите **@publication** , **@subscriber** , **@subscriber_db** , изменяемое свойство подписки **@property** , а новое значение — как **@value** .</span><span class="sxs-lookup"><span data-stu-id="33078-146">Specify **@publication**, **@subscriber**, **@subscriber_db**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="33078-147">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="33078-147">Example (Transact-SQL)</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="33078-148">При помощи объектов RMO</span><span class="sxs-lookup"><span data-stu-id="33078-148">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="33078-149">Какие именно классы объектов RMO для этого применяются, зависит от типа публикации этой подписки.</span><span class="sxs-lookup"><span data-stu-id="33078-149">The RMO classes you use to view or modify push subscription properties depend on the type of publication to which the push subscription is subscribed.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="33078-150">Просмотр и изменение свойств принудительной подписки на публикацию моментальных снимков или транзакций</span><span class="sxs-lookup"><span data-stu-id="33078-150">To view or modify properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="33078-151">Создайте соединение с издателем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="33078-151">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="33078-152">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.TransSubscription>.</span><span class="sxs-lookup"><span data-stu-id="33078-152">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class.</span></span>  
  
3.  <span data-ttu-id="33078-153">Установите свойства <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>и <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="33078-153">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="33078-154">Задайте соединение <xref:Microsoft.SqlServer.Management.Common.ServerConnection> с шага 1 для свойства <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="33078-154">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property setting.</span></span>  
  
5.  <span data-ttu-id="33078-155">Чтобы получить свойства объекта, вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="33078-155">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="33078-156">Если этот метод возвращает значение `false`, то либо на шаге 3 были неверно определены свойства подписки, либо подписка не существует.</span><span class="sxs-lookup"><span data-stu-id="33078-156">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="33078-157">Чтобы изменить свойства, установите новое значение для одного из свойств <xref:Microsoft.SqlServer.Replication.TransSubscription> , которое можно установить, и затем вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="33078-157">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.TransSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="33078-158">Чтобы просмотреть новые значения, вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> , который выполняет повторную загрузку свойств для подписки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="33078-158">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the subscription.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="33078-159">Просмотр и изменение свойств принудительной подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="33078-159">To view or modify properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="33078-160">Создайте соединение с подписчиком с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="33078-160">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="33078-161">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.MergeSubscription>.</span><span class="sxs-lookup"><span data-stu-id="33078-161">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class.</span></span>  
  
3.  <span data-ttu-id="33078-162">Установите свойства <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>и <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="33078-162">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="33078-163">Задайте соединение <xref:Microsoft.SqlServer.Management.Common.ServerConnection> с шага 1 для свойства <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="33078-163">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property setting.</span></span>  
  
5.  <span data-ttu-id="33078-164">Чтобы получить свойства объекта, вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="33078-164">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="33078-165">Если этот метод возвращает значение `false`, то либо на шаге 3 были неверно определены свойства подписки, либо подписка не существует.</span><span class="sxs-lookup"><span data-stu-id="33078-165">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="33078-166">Чтобы изменить свойства, установите новое значение для одного из свойств <xref:Microsoft.SqlServer.Replication.MergeSubscription> , которое можно установить, и затем вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="33078-166">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="33078-167">Чтобы просмотреть новые значения, вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> , который выполняет повторную загрузку свойств для подписки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="33078-167">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33078-168">См. также:</span><span class="sxs-lookup"><span data-stu-id="33078-168">See Also</span></span>  
 <span data-ttu-id="33078-169">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="33078-169">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="33078-170">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="33078-170">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="33078-171">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="33078-171">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
