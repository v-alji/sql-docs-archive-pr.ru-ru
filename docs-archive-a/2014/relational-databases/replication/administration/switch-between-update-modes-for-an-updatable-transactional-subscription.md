---
title: Переключение между режимами обновления для обновляемой подписки на публикацию транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, updatable subscriptions
- updatable subscriptions, update modes
- subscriptions [SQL Server replication], updatable
ms.assetid: ab5ebab1-7ee4-41f4-999b-b4f0c420c921
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c31814d1e2ab6fac64ffcde883f3cac2439828a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669395"
---
# <a name="switch-between-update-modes-for-an-updatable-transactional-subscription"></a><span data-ttu-id="288e6-102">Переключение между режимами обновления для обновляемой подписки на публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="288e6-102">Switch Between Update Modes for an Updatable Transactional Subscription</span></span>
  <span data-ttu-id="288e6-103">В этом разделе описывается переключение между режимами обновления для обновляемой подписки на публикацию транзакций в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="288e6-103">This topic describes how to switch between update modes for an updatable transaction subscription in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="288e6-104">Режим обновляемых подписок можно указать с помощью мастера создания подписки.</span><span class="sxs-lookup"><span data-stu-id="288e6-104">Specify the mode for updatable subscriptions using the New Subscription Wizard.</span></span> <span data-ttu-id="288e6-105">Сведения об установке режима с помощью этого мастера см. в статье [Просмотр и изменение свойств подписки по запросу](../view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="288e6-105">For information about setting the mode when using this wizard, see [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md).</span></span>  
  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="288e6-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="288e6-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="288e6-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="288e6-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="288e6-108">Переход из режима немедленного обновления в режим отложенного обновления может быть произведен в любой момент,</span><span class="sxs-lookup"><span data-stu-id="288e6-108">You can fail over from immediate to queued updating at any time.</span></span> <span data-ttu-id="288e6-109">однако после этого возврат в режим немедленного обновления будет возможен только тогда, когда появится соединение между подписчиком и издателем, а агент чтения очереди применит к издателю все сообщения, находящиеся в очереди.</span><span class="sxs-lookup"><span data-stu-id="288e6-109">After you do, however, you cannot return to immediate updating until the Subscriber and Publisher are connected and the Queue Reader Agent has applied all pending messages in the queue to the Publisher.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="288e6-110">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="288e6-110">Recommendations</span></span>  
  
-   <span data-ttu-id="288e6-111">Если обновляемая подписка на публикацию транзакций поддерживает отработку отказа из одного режима обновления в другой, то возможно программное переключение режимов обновления для выхода из ситуаций, когда возможность подключения изменяется на короткий промежуток времени.</span><span class="sxs-lookup"><span data-stu-id="288e6-111">When an updating subscription to a transactional publication supports failover from one updating mode to another, you can programmatically switch update modes to handle situations when connectivity changes for a short period of time.</span></span> <span data-ttu-id="288e6-112">Режим обновления может быть установлен как программно, так и по запросу при помощи хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="288e6-112">The update mode can be set programmatically and on demand using replication stored procedures.</span></span> <span data-ttu-id="288e6-113">Дополнительные сведения см. в статье [Updatable Subscriptions for Transactional Replication](../transactional/updatable-subscriptions-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="288e6-113">For more information, see [Updatable Subscriptions for Transactional Replication](../transactional/updatable-subscriptions-for-transactional-replication.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="288e6-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="288e6-114">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="288e6-115">Чтобы изменить режим обновления после создания подписки, необходимо установить для свойства **update_mode** значение **failover** (что позволяет переключиться с немедленного обновления на обновление посредством очередей) или значение **queued failover** (что позволяет переключиться с обновления по очереди на немедленное обновление), когда подписка создана.</span><span class="sxs-lookup"><span data-stu-id="288e6-115">To change the update mode after the subscription is created, the **update_mode** property must be set to **failover** (which allows a switch from immediate updating to queued updating) or **queued failover** (which allows a switch from queued updating to immediate updating) when the subscription is created.</span></span> <span data-ttu-id="288e6-116">Эти свойства устанавливаются автоматически в мастере создания подписки.</span><span class="sxs-lookup"><span data-stu-id="288e6-116">These properties are set automatically in the New Subscription Wizard.</span></span>  
  
#### <a name="to-set-the-updating-mode-for-a-push-subscription"></a><span data-ttu-id="288e6-117">Установка режима обновления для принудительной подписки</span><span class="sxs-lookup"><span data-stu-id="288e6-117">To set the updating mode for a push subscription</span></span>  
  
1.  <span data-ttu-id="288e6-118">Подключитесь к подписчику в [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]и раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="288e6-118">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="288e6-119">Раскройте папку **Репликация** , а затем — папку **Локальные подписки** .</span><span class="sxs-lookup"><span data-stu-id="288e6-119">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="288e6-120">Щелкните правой кнопкой подписку, для которой хотите установить режим обновления, и щелкните **Выбор метода обновления**.</span><span class="sxs-lookup"><span data-stu-id="288e6-120">Right-click the subscription for which you want to set the update mode, and then click **Set Update Method**.</span></span>  
  
4.  <span data-ttu-id="288e6-121">В диалоговом окне **Выбор метода обновления — \<Subscriber>: \<SubscriptionDatabase>** выберите **Немедленное обновление** или **Обновление посредством очередей**.</span><span class="sxs-lookup"><span data-stu-id="288e6-121">In the **Set Update Method - \<Subscriber>: \<SubscriptionDatabase>** dialog box, select **Immediate updating** or **Queued updating**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-set-the-updating-mode-for-a-pull-subscription"></a><span data-ttu-id="288e6-122">Установка режима обновления для подписки по запросу</span><span class="sxs-lookup"><span data-stu-id="288e6-122">To set the updating mode for a pull subscription</span></span>  
  
1.  <span data-ttu-id="288e6-123">В диалоговом окне **Свойства подписки — \<Publisher>\<PublicationDatabase>** выберите значение **Немедленно реплицировать изменения** или **Ставить изменения в очередь** для параметра **Метод обновления подписчика**.</span><span class="sxs-lookup"><span data-stu-id="288e6-123">In the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, select a value of **Immediately replicate changes** or **Queue changes** for the **Subscriber update method** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="288e6-124">Дополнительные сведения о доступе к диалоговому окну **Свойства подписки — \<Publisher>: \<PublicationDatabase>** см. в разделе [Просмотр и изменение свойств подписки по запросу](../view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="288e6-124">For more information about accessing the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, see [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="288e6-125">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="288e6-125">Using Transact-SQL</span></span>  
  
#### <a name="to-switch-between-update-modes"></a><span data-ttu-id="288e6-126">Переключение режимов обновления</span><span class="sxs-lookup"><span data-stu-id="288e6-126">To switch between update modes</span></span>  
  
1.  <span data-ttu-id="288e6-127">Удостоверьтесь в том, что данная подписка поддерживает отработку отказа, выполнив хранимую процедуру [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql) для подписки по запросу или [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) для принудительной подписки.</span><span class="sxs-lookup"><span data-stu-id="288e6-127">Verify that the subscription supports failover by executing [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql) for a pull subscription or [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) for a push subscription.</span></span> <span data-ttu-id="288e6-128">Если значение **update mode** результирующего набора равен **3** или **4**, то отработка отказа поддерживается.</span><span class="sxs-lookup"><span data-stu-id="288e6-128">If the value of **update mode** in the result set is **3** or **4**, failover is supported.</span></span>  
  
2.  <span data-ttu-id="288e6-129">На подписчике в базе данных подписки выполните процедуру [sp_setreplfailovermode](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="288e6-129">At the Subscriber on the subscription database, execute [sp_setreplfailovermode](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql).</span></span> <span data-ttu-id="288e6-130">Укажите **@publisher** **@publisher_db** значения,, **@publication** и одно из следующих значений для **@failover_mode** :</span><span class="sxs-lookup"><span data-stu-id="288e6-130">Specify **@publisher**, **@publisher_db**, **@publication**, and one of the following values for **@failover_mode**:</span></span>  
  
    -   <span data-ttu-id="288e6-131">**queued** — переход в режим обновления посредством очередей при временной потере соединения;</span><span class="sxs-lookup"><span data-stu-id="288e6-131">**queued** - fail over to queued updating when connectivity has been temporarily lost.</span></span>  
  
    -   <span data-ttu-id="288e6-132">**immediate** — переход в режим немедленного обновления, при восстановлении.</span><span class="sxs-lookup"><span data-stu-id="288e6-132">**immediate** - fail over to immediate updating when connectivity has been restored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="288e6-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="288e6-133">See Also</span></span>  
 [<span data-ttu-id="288e6-134">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="288e6-134">Updatable Subscriptions for Transactional Replication</span></span>](../transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
