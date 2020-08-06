---
title: Синхронизация подписки с помощью диспетчера синхронизации Windows (диспетчер синхронизации Windows) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], Windows Synchronization Manager
- Windows Synchronization Manager
ms.assetid: 80f15dd6-e84d-4f96-9866-5b34ea531f1e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bb31c344f91c68b04e03dd218f22b09bec44830b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732557"
---
# <a name="synchronize-a-subscription-using-windows-synchronization-manager-windows-synchronization-manager"></a><span data-ttu-id="f9edb-102">Синхронизация подписки с помощью диспетчера синхронизации Windows (Windows Synchronization Manager)</span><span class="sxs-lookup"><span data-stu-id="f9edb-102">Synchronize a Subscription Using Windows Synchronization Manager (Windows Synchronization Manager)</span></span>
  <span data-ttu-id="f9edb-103">Диспетчер синхронизации[!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows можно использовать только для синхронизации подписок на публикации Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняется на том же самом компьютере, что и диспетчер синхронизации (кроме того, его можно использовать для синхронизации файлов и веб-страниц в режиме «вне сети»).</span><span class="sxs-lookup"><span data-stu-id="f9edb-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Synchronization Manager can only be used to synchronize subscriptions to Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publications if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running on the same computer as Synchronization Manager (it can also be used to synchronize offline files and Web pages).</span></span> <span data-ttu-id="f9edb-104">Чтобы использовать диспетчер синхронизации, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f9edb-104">To use Synchronization Manager:</span></span>  
  
1.  <span data-ttu-id="f9edb-105">Включите синхронизацию подписок по запросу с помощью диспетчера синхронизации Windows в диалоговом окне **Свойства подписки — \<Subscriber>: \<SubscriptionDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="f9edb-105">Enable the synchronization of pull subscriptions with Windows Synchronization Manager in the **Subscription Properties - \<Subscriber>: \<SubscriptionDatabase>** dialog box.</span></span> <span data-ttu-id="f9edb-106">Дополнительные сведения о доступе к этому диалоговому окну см. в статье [Просмотр и изменение свойств подписки по запросу](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f9edb-106">For more information about accessing this dialog box, see [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
2.  <span data-ttu-id="f9edb-107">Запустите диспетчер синхронизации из меню **Пуск** операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="f9edb-107">Access Synchronization Manager through the **Start** menu in Windows.</span></span>  
  
 <span data-ttu-id="f9edb-108">Диспетчер синхронизации позволяет использовать интерактивный сопоставитель для подписок на публикацию слиянием.</span><span class="sxs-lookup"><span data-stu-id="f9edb-108">Synchronization Manager allows you to use the Interactive Resolver for merge subscriptions.</span></span> <span data-ttu-id="f9edb-109">Обычно обнаружение и разрешение конфликтов во время синхронизации производится автоматически, но если включен интерактивный механизм разрешения конфликтов, то конфликты во время синхронизации могут устраняться пользователем.</span><span class="sxs-lookup"><span data-stu-id="f9edb-109">Typically, conflicts detected during synchronization are resolved automatically, but if interactive resolution is enabled, conflicts can be resolved by a user during synchronization.</span></span> <span data-ttu-id="f9edb-110">Если синхронизация выполняется не диспетчером синхронизации Windows (как синхронизация по расписанию или по запросу в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или мониторе репликации), конфликты устраняются автоматически без вмешательства пользователя в соответствии с сопоставителем, указанным для статьи.</span><span class="sxs-lookup"><span data-stu-id="f9edb-110">If a synchronization is performed outside of Windows Synchronization Manager (as a scheduled synchronization or an on demand synchronization in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Replication Monitor), conflicts are resolved automatically without user intervention, according to the resolver specified for the article.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f9edb-111">Начиная с [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] и [!INCLUDE[wiprlhlong](../../includes/wiprlhlong-md.md)], 64-разрядные версии диспетчера синхронизации Windows не могут определять 32-разрядные подписки.</span><span class="sxs-lookup"><span data-stu-id="f9edb-111">Beginning with [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] and [!INCLUDE[wiprlhlong](../../includes/wiprlhlong-md.md)], 64-bit versions of the Windows Synchronization Manager cannot detect 32-bit subscriptions.</span></span>  
  
### <a name="to-enable-the-synchronization-of-pull-subscriptions-with-windows-synchronization-manager"></a><span data-ttu-id="f9edb-112">Включение синхронизации подписок по запросу с помощью диспетчера синхронизации Windows</span><span class="sxs-lookup"><span data-stu-id="f9edb-112">To enable the synchronization of pull subscriptions with Windows Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="f9edb-113">На странице **Общие** диалогового окна **Свойства подписки — \<Subscriber>: \<SubscriptionDatabase>** выберите значение **Включить** для параметра **Использовать диспетчер синхронизации Windows**.</span><span class="sxs-lookup"><span data-stu-id="f9edb-113">On the **General** page of the **Subscription Properties - \<Subscriber>: \<SubscriptionDatabase>** dialog box, select a value of **Enable** for the **Use Windows Synchronization Manager** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-synchronize-a-pull-subscription-with-synchronization-manager"></a><span data-ttu-id="f9edb-114">Синхронизация подписок по запросу с помощью диспетчера синхронизации</span><span class="sxs-lookup"><span data-stu-id="f9edb-114">To synchronize a pull subscription with Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="f9edb-115">Запустите диспетчер синхронизации одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="f9edb-115">Launch Synchronization Manager using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="f9edb-116">В обозревателе Internet Explorer выберите меню **Сервис**, а затем выберите пункт **Синхронизировать...** .</span><span class="sxs-lookup"><span data-stu-id="f9edb-116">In Internet Explorer, click **Tools**, and then click **Synchronize**.</span></span>  
  
    -   <span data-ttu-id="f9edb-117">Нажмите кнопку **Пуск**, укажите **Программы** или **Все программы**, выберите пункт **Стандартные**, а затем выберите пункт **Синхронизировать**.</span><span class="sxs-lookup"><span data-stu-id="f9edb-117">Click **Start**, point to **Programs** or **All Programs**, point to **Accessories**, and then click **Synchronize**.</span></span>  
  
    -   <span data-ttu-id="f9edb-118">Нажмите кнопку **Пуск**, а затем выберите пункт **Выполнить**</span><span class="sxs-lookup"><span data-stu-id="f9edb-118">Click **Start**, and then click **Run.**</span></span> <span data-ttu-id="f9edb-119">В диалоговом окне **выполнить** введите `mobsync.exe` в поле **Открыть** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f9edb-119">In the **Run** dialog box, type `mobsync.exe` in the **Open** field, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="f9edb-120">В диалоговом окне **Синхронизируемые объекты** выберите синхронизацию подписок.</span><span class="sxs-lookup"><span data-stu-id="f9edb-120">In the **Items to Synchronize** dialog box, select the subscriptions to synchronize.</span></span> <span data-ttu-id="f9edb-121">Список подписок выводится для экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f9edb-121">Subscriptions are listed under the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
3.  <span data-ttu-id="f9edb-122">Выберите пункт **Синхронизировать**.</span><span class="sxs-lookup"><span data-stu-id="f9edb-122">Click **Synchronize**.</span></span>  
  
### <a name="to-reinitialize-a-pull-subscription-with-synchronization-manager"></a><span data-ttu-id="f9edb-123">Повторная инициализация подписок по запросу с помощью диспетчера синхронизации</span><span class="sxs-lookup"><span data-stu-id="f9edb-123">To reinitialize a pull subscription with Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="f9edb-124">В диалоговом окне **Синхронизируемые объекты** выберите подписку и щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f9edb-124">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f9edb-125">В диалоговом окне **Свойства подписки SQL Server** выберите **Повторно инициализировать подписку**.</span><span class="sxs-lookup"><span data-stu-id="f9edb-125">In the **SQL Server Subscription Properties** dialog box, click **Reinitialize Subscription**.</span></span>  
  
3.  <span data-ttu-id="f9edb-126">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="f9edb-126">Click **Yes**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="f9edb-127">При следующей синхронизации подписки к базе данных подписки применяется по умолчанию новый моментальный снимок.</span><span class="sxs-lookup"><span data-stu-id="f9edb-127">The next time the subscription is synchronized, by default a new snapshot is applied to the subscription database.</span></span> <span data-ttu-id="f9edb-128">Дополнительные сведения см. в статье [Повторная инициализация подписок](reinitialize-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="f9edb-128">For more information, see [Reinitialize Subscriptions](reinitialize-subscriptions.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f9edb-129">Репликация слиянием позволяет загрузить на издатель все необработанные изменения до применения моментального снимка, но в диспетчере синхронизации данная возможность недоступна.</span><span class="sxs-lookup"><span data-stu-id="f9edb-129">Merge replication allows any outstanding changes to be uploaded to the Publisher before the snapshot is applied, but this option is not available from Synchronization Manager.</span></span> <span data-ttu-id="f9edb-130">Для передачи изменений синхронизируйте подписку перед ее повторной инициализацией.</span><span class="sxs-lookup"><span data-stu-id="f9edb-130">To upload changes, synchronize the subscription before reinitializing it.</span></span>  
  
### <a name="to-set-properties-for-a-pull-subscription-in-synchronization-manager"></a><span data-ttu-id="f9edb-131">Установка свойств подписки по запросу в диспетчере синхронизации</span><span class="sxs-lookup"><span data-stu-id="f9edb-131">To set properties for a pull subscription in Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="f9edb-132">В диалоговом окне **Синхронизируемые объекты** выберите подписку и щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f9edb-132">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f9edb-133">Просмотрите и измените свойства на следующих вкладках:</span><span class="sxs-lookup"><span data-stu-id="f9edb-133">View and modify properties on the following tabs:</span></span>  
  
    -   <span data-ttu-id="f9edb-134">**Идентификация**</span><span class="sxs-lookup"><span data-stu-id="f9edb-134">**Identification**</span></span>  
  
    -   <span data-ttu-id="f9edb-135">**Имя входа подписчика**, **Имя входа распространителя**и **Имя входа издателя** (только для репликации слиянием)</span><span class="sxs-lookup"><span data-stu-id="f9edb-135">**Subscriber Login**, **Distributor Login**, and **Publisher Login** (for merge replication only)</span></span>  
  
    -   <span data-ttu-id="f9edb-136">**Данные о веб-сервере** (для подписок на публикацию слиянием на подписчиках, использующих SQL Server 2005 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="f9edb-136">**Web Server Information** (for merge subscriptions on Subscribers running SQL Server 2005 or later)</span></span>  
  
    -   <span data-ttu-id="f9edb-137">**Другое**</span><span class="sxs-lookup"><span data-stu-id="f9edb-137">**Other**</span></span>  
  
     <span data-ttu-id="f9edb-138">Рекомендуется использовать проверку подлинности Windows для всех соединений.</span><span class="sxs-lookup"><span data-stu-id="f9edb-138">It is recommended to use Windows Authentication for all connections.</span></span> <span data-ttu-id="f9edb-139">Дополнительные сведения о разрешениях, необходимых агенту распространителя и агенту слияния, см. в разделе [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="f9edb-139">For information about the permissions required by the Distribution Agent and the Merge Agent, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-a-pull-subscription-from-synchronization-manager"></a><span data-ttu-id="f9edb-140">Удаление из диспетчера синхронизации подписки по запросу</span><span class="sxs-lookup"><span data-stu-id="f9edb-140">To remove a pull subscription from Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="f9edb-141">В диалоговом окне **Синхронизируемые объекты** выберите подписку и щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f9edb-141">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f9edb-142">В диалоговом окне **Свойства подписки SQL Server** выберите **Удалить подписку**.</span><span class="sxs-lookup"><span data-stu-id="f9edb-142">In the **SQL Server Subscription Properties** dialog box, click **Remove Subscription**.</span></span>  
  
3.  <span data-ttu-id="f9edb-143">Выберите параметр в диалоговом окне **Удаление подписки** .</span><span class="sxs-lookup"><span data-stu-id="f9edb-143">Select an option in the **Remove Subscription** dialog box.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-use-the-interactive-resolver"></a><span data-ttu-id="f9edb-144">Использование интерактивного сопоставителя</span><span class="sxs-lookup"><span data-stu-id="f9edb-144">To use the Interactive Resolver</span></span>  
  
1.  <span data-ttu-id="f9edb-145">Включите для статьи и подписки использование интерактивного механизма разрешения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="f9edb-145">Enable the article and subscription to use interactive resolution.</span></span> <span data-ttu-id="f9edb-146">Дополнительные сведения см. в статье [Настройка интерактивного устранения конфликтов для статей публикации слиянием](../../relational-databases/replication/publish/specify-merge-replication-properties.md#interactive-conflict-resolution).</span><span class="sxs-lookup"><span data-stu-id="f9edb-146">For more information, see [Specify Interactive Conflict Resolution for Merge Articles](../../relational-databases/replication/publish/specify-merge-replication-properties.md#interactive-conflict-resolution).</span></span>
  
2.  <span data-ttu-id="f9edb-147">После запуска синхронизации подписки в диспетчере синхронизации интерактивный сопоставитель запускается автоматически, если включено интерактивное разрешение конфликтов и возникают конфликты для одной или нескольких статей.</span><span class="sxs-lookup"><span data-stu-id="f9edb-147">After the subscription begins synchronizing in Synchronization Manager, the Interactive Resolver launches automatically if interactive conflict resolution is enabled and there are conflicts for one or more articles.</span></span> <span data-ttu-id="f9edb-148">Интерактивный сопоставитель отображает по одному конфликту за раз и предлагает для каждого конфликта вариант разрешения, основанный на механизме разрешения конфликтов, который был указан при создании публикации и подписки.</span><span class="sxs-lookup"><span data-stu-id="f9edb-148">The Interactive Resolver displays conflicts one at a time, with a suggested resolution for each conflict (based on the resolver specified when the publication and subscription were created).</span></span>  
  
3.  <span data-ttu-id="f9edb-149">При необходимости можно отредактировать любой из столбцов, отображаемый в интерактивном сопоставителе, и затем нажать одну из следующих кнопок для разрешения конфликта:</span><span class="sxs-lookup"><span data-stu-id="f9edb-149">Optionally edit any of the columns displayed in the Interactive Resolver, and then click one of the following buttons to resolve the conflict:</span></span>  
  
    -   <span data-ttu-id="f9edb-150">**Принять предлагаемый вариант**</span><span class="sxs-lookup"><span data-stu-id="f9edb-150">**Accept Suggested**</span></span>  
  
    -   <span data-ttu-id="f9edb-151">**Принять вариант издателя**</span><span class="sxs-lookup"><span data-stu-id="f9edb-151">**Accept Publisher**</span></span>  
  
    -   <span data-ttu-id="f9edb-152">**Принять вариант подписчика**</span><span class="sxs-lookup"><span data-stu-id="f9edb-152">**Accept Subscriber**</span></span>  
  
    -   <span data-ttu-id="f9edb-153">**Разрешать все конфликты автоматически** (все текущие конфликты разрешаются без дальнейшего ввода данных)</span><span class="sxs-lookup"><span data-stu-id="f9edb-153">**Resolve All Automatically** (all current conflicts are resolved without further input)</span></span>  
  
     <span data-ttu-id="f9edb-154">Затем выбранная строка применяется к издателю или к подписчику; строка распространяется на другие узлы в топологии во время последующих синхронизаций.</span><span class="sxs-lookup"><span data-stu-id="f9edb-154">The selected row is then applied to the Publisher and/or Subscriber; it is propagated to other nodes in the topology during subsequent synchronizations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f9edb-155">Правки применяются, только если они являются частью строки, которая выбрана для разрешения конфликта.</span><span class="sxs-lookup"><span data-stu-id="f9edb-155">Edits are only applied if they are part of the row that is chosen for resolution.</span></span> <span data-ttu-id="f9edb-156">Например, если правки вносятся от имени **Издателя**и затем выбирается **Принять вариант подписчика**, правки отклоняются.</span><span class="sxs-lookup"><span data-stu-id="f9edb-156">For example, if you make edits under **Publisher**, and then click **Accept Subscriber**, the edits are discarded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9edb-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="f9edb-157">See Also</span></span>  
 [<span data-ttu-id="f9edb-158">Interactive Conflict Resolution</span><span class="sxs-lookup"><span data-stu-id="f9edb-158">Interactive Conflict Resolution</span></span>](merge/advanced-merge-replication-conflict-interactive-resolution.md)  
  
