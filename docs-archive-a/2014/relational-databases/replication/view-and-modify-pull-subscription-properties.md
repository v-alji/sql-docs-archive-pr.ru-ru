---
title: Просмотр и изменение свойств подписки по запросу | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- modifying subscriptions
- viewing replication properties
- modifying replication properties, pull subscriptions
- pull subscriptions [SQL Server replication], modifying
- subscriptions [SQL Server replication], pull
- pull subscriptions [SQL Server replication], properties
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 1601e54f-86f0-49e8-b023-87a5d1def033
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b847a22d31bbf3ea7540c55339fe27531134125
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655018"
---
# <a name="view-and-modify-pull-subscription-properties"></a><span data-ttu-id="15cb3-102">Просмотр и изменение свойств подписки по запросу</span><span class="sxs-lookup"><span data-stu-id="15cb3-102">View and Modify Pull Subscription Properties</span></span>
  <span data-ttu-id="15cb3-103">В данном разделе описывается просмотр и изменение свойств подписки по запросу в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="15cb3-103">This topic describes how to view and modify pull subscription properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="15cb3-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="15cb3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="15cb3-105">**Для просмотра и изменения свойств подписки по запросу используется:**</span><span class="sxs-lookup"><span data-stu-id="15cb3-105">**To view and modify pull subscription properties, using:**</span></span>  
  
     [<span data-ttu-id="15cb3-106">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="15cb3-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="15cb3-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15cb3-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="15cb3-108">объекты RMO;</span><span class="sxs-lookup"><span data-stu-id="15cb3-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="15cb3-109">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="15cb3-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="15cb3-110">Просмотрите свойства подписки по запросу в издателе или подписчике в диалоговом окне **Свойства подписки — \<Publisher>: \<PublicationDatabase>** , которое можно открыть из [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15cb3-110">View pull subscription properties from the Publisher or the Subscriber in the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, which is available from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="15cb3-111">На подписчике можно просмотреть и изменить ряд дополнительных свойств.</span><span class="sxs-lookup"><span data-stu-id="15cb3-111">More properties are visible from the Subscriber, and properties can be modified at the Subscriber.</span></span> <span data-ttu-id="15cb3-112">Свойства можно также просмотреть на издателе на вкладке **Все подписки** , доступной в мониторе репликации.</span><span class="sxs-lookup"><span data-stu-id="15cb3-112">You can also view properties from the Publisher on the **All Subscriptions** tab, which is available in Replication Monitor.</span></span> <span data-ttu-id="15cb3-113">Сведения о запуске монитора репликации см. в [этой статье](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="15cb3-113">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-view-pull-subscription-properties-from-the-publisher-in-management-studio"></a><span data-ttu-id="15cb3-114">Просмотр свойств подписки по запросу на издателе в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="15cb3-114">To view pull subscription properties from the Publisher in Management Studio</span></span>  
  
1.  <span data-ttu-id="15cb3-115">Подключитесь к издателю в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="15cb3-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="15cb3-116">Раскройте папку **Репликация** , а затем папку **Локальные публикации** .</span><span class="sxs-lookup"><span data-stu-id="15cb3-116">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="15cb3-117">Раскройте соответствующую публикацию, щелкните правой кнопкой мыши подписку и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="15cb3-117">Expand the appropriate publication, right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="15cb3-118">Просмотрите свойства, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15cb3-118">View properties, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-pull-subscription-properties-from-the-subscriber-in-management-studio"></a><span data-ttu-id="15cb3-119">Просмотр и изменение свойств подписки по запросу на подписчике в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="15cb3-119">To view and modify pull subscription properties from the Subscriber in Management Studio</span></span>  
  
1.  <span data-ttu-id="15cb3-120">Подключитесь к подписчику в [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]и раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="15cb3-120">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="15cb3-121">Раскройте папку **Репликация** , а затем — папку **Локальные подписки** .</span><span class="sxs-lookup"><span data-stu-id="15cb3-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="15cb3-122">Щелкните правой кнопкой мыши подписку и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="15cb3-122">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="15cb3-123">Измените свойства, если необходимо, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15cb3-123">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-pull-subscription-properties-from-the-publisher-in-replication-monitor"></a><span data-ttu-id="15cb3-124">Просмотр свойств подписки по запросу на издателе в мониторе репликации</span><span class="sxs-lookup"><span data-stu-id="15cb3-124">To view pull subscription properties from the Publisher in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="15cb3-125">На левой панели монитора репликации раскройте группу издателей, раскройте нужный издатель, а затем выберите публикацию.</span><span class="sxs-lookup"><span data-stu-id="15cb3-125">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="15cb3-126">Перейдите на вкладку **Все подписки** .</span><span class="sxs-lookup"><span data-stu-id="15cb3-126">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="15cb3-127">Щелкните правой кнопкой мыши подписку и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="15cb3-127">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="15cb3-128">Просмотрите свойства, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15cb3-128">View properties, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="15cb3-129">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15cb3-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="15cb3-130">Подписки по запросу можно изменять и получать доступ к их свойствам программно с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="15cb3-130">Pull subscriptions can be modified and their properties accessed programmatically using replication stored procedures.</span></span> <span data-ttu-id="15cb3-131">Хранимые процедуры, используемые для этого, зависят от типа публикации, к которой принадлежит подписка.</span><span class="sxs-lookup"><span data-stu-id="15cb3-131">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-view-the-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="15cb3-132">Просмотр свойств подписки по запросу на публикацию моментальных снимков или публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="15cb3-132">To view the properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="15cb3-133">На подписчике выполните хранимую процедуру [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15cb3-133">At the Subscriber, execute [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql).</span></span> <span data-ttu-id="15cb3-134">Укажите **@publisher** , **@publisher_db** и **@publication** .</span><span class="sxs-lookup"><span data-stu-id="15cb3-134">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span> <span data-ttu-id="15cb3-135">Тем самым возвращаются сведения о подписке, хранящиеся в системных таблицах на подписчике.</span><span class="sxs-lookup"><span data-stu-id="15cb3-135">This returns information about the subscription that is stored in system tables at the Subscriber.</span></span>  
  
2.  <span data-ttu-id="15cb3-136">На подписчике выполните процедуру [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15cb3-136">At the Subscriber, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span></span> <span data-ttu-id="15cb3-137">Укажите **@publisher** **@publisher_db** значения,, **@publication** и одно из следующих значений для **@publication_type** :</span><span class="sxs-lookup"><span data-stu-id="15cb3-137">Specify **@publisher**, **@publisher_db**, **@publication**, and one of the following values for **@publication_type**:</span></span>  
  
    -   <span data-ttu-id="15cb3-138">**0** — подписка принадлежит публикации транзакций;</span><span class="sxs-lookup"><span data-stu-id="15cb3-138">**0** - Subscription belongs to a transactional publication.</span></span>  
  
    -   <span data-ttu-id="15cb3-139">**1** — подписка принадлежит публикации моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="15cb3-139">**1** - Subscription belongs to a snapshot publication.</span></span>  
  
3.  <span data-ttu-id="15cb3-140">На издателе выполните хранимую процедуру [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15cb3-140">At the Publisher, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span> <span data-ttu-id="15cb3-141">Укажите **@publication** и **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="15cb3-141">Specify **@publication** and **@subscriber**.</span></span>  
  
4.  <span data-ttu-id="15cb3-142">На издателе выполните [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), указав **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="15cb3-142">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span> <span data-ttu-id="15cb3-143">Будут выведены сведения о подписчике.</span><span class="sxs-lookup"><span data-stu-id="15cb3-143">This displays information about the Subscriber.</span></span>  
  
#### <a name="to-change-the-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="15cb3-144">Изменение свойств подписки по запросу на публикацию моментальных снимков или публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="15cb3-144">To change the properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="15cb3-145">На подписчике выполните [sp_change_subscription_properties](/sql/relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql), указав **@publisher** , **@publisher_db** , **@publication** , значение **0** (транзакционное) или **1** (моментальный снимок) для **@publication_type** Свойства подписки, которое изменяется как **@property** , и новое значение в виде **@value** .</span><span class="sxs-lookup"><span data-stu-id="15cb3-145">At the Subscriber, execute [sp_change_subscription_properties](/sql/relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql), specifying **@publisher**, **@publisher_db**, **@publication**, a value of either **0** (transactional) or **1** (snapshot) for **@publication_type**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
2.  <span data-ttu-id="15cb3-146">На подписчике в базе данных подписки выполните хранимую процедуру [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15cb3-146">(Optional) At the Subscriber on the subscription database, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql).</span></span> <span data-ttu-id="15cb3-147">Укажите идентификатор задания агент распространения **@jobid** , а также следующие свойства пакета служб DTS:</span><span class="sxs-lookup"><span data-stu-id="15cb3-147">Specify the ID of the Distribution Agent job for **@jobid**, and the following Data Transformation Services (DTS) package properties:</span></span>  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     <span data-ttu-id="15cb3-148">Свойства пакета служб подписки будут изменены.</span><span class="sxs-lookup"><span data-stu-id="15cb3-148">This changes the DTS package properties of a subscription.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15cb3-149">Идентификатор задания можно получить, выполнив процедуру [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15cb3-149">The job ID can be obtained by executing [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span>  
  
#### <a name="to-view-the-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="15cb3-150">Просмотр свойств подписки по запросу на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="15cb3-150">To view the properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="15cb3-151">На подписчике выполните хранимую процедуру [sp_helpmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15cb3-151">At the Subscriber, execute [sp_helpmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql).</span></span> <span data-ttu-id="15cb3-152">Укажите **@publisher** , **@publisher_db** и **@publication** .</span><span class="sxs-lookup"><span data-stu-id="15cb3-152">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span>  
  
2.  <span data-ttu-id="15cb3-153">На подписчике выполните процедуру [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15cb3-153">At the Subscriber, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span></span> <span data-ttu-id="15cb3-154">Укажите **@publisher** , **@publisher_db** , **@publication** и значение 2 в параметре **@publication_type** .</span><span class="sxs-lookup"><span data-stu-id="15cb3-154">Specify **@publisher**, **@publisher_db**, **@publication**, and a value of 2 for **@publication_type**.</span></span>  
  
3.  <span data-ttu-id="15cb3-155">Чтобы вывести сведения о подписке, выполните на издателе хранимую процедуру [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="15cb3-155">At the Publisher, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql) to display subscription information.</span></span> <span data-ttu-id="15cb3-156">Чтобы получить сведения о конкретной подписке, необходимо указать **@publication** , **@subscriber** и значение **Pull** для **@subscription_type** .</span><span class="sxs-lookup"><span data-stu-id="15cb3-156">To return information on a specific subscription, you must specify **@publication**, **@subscriber**, and a value of **pull** for **@subscription_type**.</span></span>  
  
4.  <span data-ttu-id="15cb3-157">На издателе выполните [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), указав **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="15cb3-157">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span> <span data-ttu-id="15cb3-158">Будут выведены сведения о подписчике.</span><span class="sxs-lookup"><span data-stu-id="15cb3-158">This displays information about the Subscriber.</span></span>  
  
#### <a name="to-change-the-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="15cb3-159">Изменение свойств подписки по запросу на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="15cb3-159">To change the properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="15cb3-160">На подписчике выполните хранимую процедуру [sp_changemergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15cb3-160">At the Subscriber, execute [sp_changemergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql).</span></span> <span data-ttu-id="15cb3-161">Укажите **@publication** , **@publisher** , **@publisher_db** , изменяемое свойство подписки **@property** , а новое значение — как **@value** .</span><span class="sxs-lookup"><span data-stu-id="15cb3-161">Specify **@publication**, **@publisher**, **@publisher_db**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="15cb3-162">При помощи объектов RMO</span><span class="sxs-lookup"><span data-stu-id="15cb3-162">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="15cb3-163">Конкретные классы объектов RMO, используемые для этого, зависят от типа публикации, для которой создается подписка по запросу.</span><span class="sxs-lookup"><span data-stu-id="15cb3-163">The RMO classes you use to view or modify pull subscription properties depend on the type of publication to which the pull subscription is subscribed.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="15cb3-164">Просмотр или изменение свойств подписки по запросу на публикацию моментальных снимков или транзакций</span><span class="sxs-lookup"><span data-stu-id="15cb3-164">To view or modify properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="15cb3-165">Создайте соединение с подписчиком с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="15cb3-165">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="15cb3-166">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.TransPullSubscription>.</span><span class="sxs-lookup"><span data-stu-id="15cb3-166">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class.</span></span>  
  
3.  <span data-ttu-id="15cb3-167">Установите свойства <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>и <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="15cb3-167">Set the <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>, and <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="15cb3-168">Установите полученное на шаге 1 соединение в качестве значения свойства <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="15cb3-168">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="15cb3-169">Чтобы получить свойства объекта, вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="15cb3-169">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="15cb3-170">Если этот метод возвращает `false`, то либо на шаге 3 были неверно определены свойства подписки, либо подписка не существует.</span><span class="sxs-lookup"><span data-stu-id="15cb3-170">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist on the server.</span></span>  
  
6.  <span data-ttu-id="15cb3-171">Чтобы изменить свойства, установите новое значение для одного из свойств <xref:Microsoft.SqlServer.Replication.TransPullSubscription> , которое можно установить, и затем вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="15cb3-171">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="15cb3-172">Чтобы просмотреть новые параметры, вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> , который перезагрузит свойства статьи (необязательно).</span><span class="sxs-lookup"><span data-stu-id="15cb3-172">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the article.</span></span>  
  
8.  <span data-ttu-id="15cb3-173">Закройте все соединения.</span><span class="sxs-lookup"><span data-stu-id="15cb3-173">Close all connections.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="15cb3-174">Просмотр или изменение свойств подписки по запросу на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="15cb3-174">To view or modify properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="15cb3-175">Создайте соединение с подписчиком с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="15cb3-175">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="15cb3-176">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.MergePullSubscription>.</span><span class="sxs-lookup"><span data-stu-id="15cb3-176">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class.</span></span>  
  
3.  <span data-ttu-id="15cb3-177">Установите свойства <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>и <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="15cb3-177">Set the <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>, and <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="15cb3-178">Установите полученное на шаге 1 соединение в качестве значения свойства <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="15cb3-178">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="15cb3-179">Чтобы получить свойства объекта, вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="15cb3-179">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="15cb3-180">Если этот метод возвращает `false`, то либо на шаге 3 были неверно определены свойства подписки, либо подписка не существует.</span><span class="sxs-lookup"><span data-stu-id="15cb3-180">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist on the server.</span></span>  
  
6.  <span data-ttu-id="15cb3-181">Чтобы изменить свойства, установите новое значение для одного из свойств <xref:Microsoft.SqlServer.Replication.MergePullSubscription> , которое можно установить, и затем вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="15cb3-181">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="15cb3-182">Чтобы просмотреть новые параметры, вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> , который перезагрузит свойства статьи (необязательно).</span><span class="sxs-lookup"><span data-stu-id="15cb3-182">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the article.</span></span>  
  
8.  <span data-ttu-id="15cb3-183">Закройте все соединения.</span><span class="sxs-lookup"><span data-stu-id="15cb3-183">Close all connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15cb3-184">См. также:</span><span class="sxs-lookup"><span data-stu-id="15cb3-184">See Also</span></span>  
 <span data-ttu-id="15cb3-185">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="15cb3-185">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="15cb3-186">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="15cb3-186">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="15cb3-187">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="15cb3-187">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
