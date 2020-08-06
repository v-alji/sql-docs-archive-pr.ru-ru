---
title: Подписчики | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.subscribers.f1
helpviewer_keywords:
- Subscribers [SQL Server replication]
ms.assetid: 43fb2454-c220-4d25-a826-83c332eb00d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c5281a53b755bc171cdf96e7856e38ee6a54a1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657634"
---
# <a name="subscribers"></a><span data-ttu-id="44645-102">Подписчики</span><span class="sxs-lookup"><span data-stu-id="44645-102">Subscribers</span></span>
  <span data-ttu-id="44645-103">Укажите [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или отличных от [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] подписчиков, которые получат подписку на выбранную публикацию.</span><span class="sxs-lookup"><span data-stu-id="44645-103">Specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers that will receive a subscription to the selected publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="44645-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="44645-104">Options</span></span>  
 <span data-ttu-id="44645-105">**Подписчики**</span><span class="sxs-lookup"><span data-stu-id="44645-105">**Subscribers**</span></span>  
 <span data-ttu-id="44645-106">Установите флажок на сетке, чтобы выбрать соответствующие [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или отличные от[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] источники данных в качестве подписчика публикации, выбранной на странице **Публикация** .</span><span class="sxs-lookup"><span data-stu-id="44645-106">Select the check box in the grid to enable the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source as a Subscriber to the publication chosen on the **Publication** page.</span></span> <span data-ttu-id="44645-107">Если подписчика нет в списке, выберите пункт **Добавить подписчик** или **Добавить подписчик SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="44645-107">If the Subscriber is not listed, click **Add Subscriber** or **Add SQL Server Subscriber**.</span></span>  
  
 <span data-ttu-id="44645-108">**База данных подписки**</span><span class="sxs-lookup"><span data-stu-id="44645-108">**Subscription database**</span></span>  
 <span data-ttu-id="44645-109">Данные и операции в данном столбце зависят от типов подписчиков, перечисленных в столбце **Подписчики** .</span><span class="sxs-lookup"><span data-stu-id="44645-109">The information displayed in and actions available from this column depend on the type of Subscriber listed in the **Subscribers** column:</span></span>  
  
-   <span data-ttu-id="44645-110">Для подписчиков [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выберите из списка **База данных подписки** базу данных или создайте новую базу данных с помощью команды **Создать базу данных** в этом же списке.</span><span class="sxs-lookup"><span data-stu-id="44645-110">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, select a subscription database from the **Subscription Database** list or create a new database by selecting the **New database** command from the same list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="44645-111">Если издатель выбран также в качестве подписчика, база данных подписки должна отличаться от базы данных публикации.</span><span class="sxs-lookup"><span data-stu-id="44645-111">If you are enabling the Publisher as a Subscriber, the subscription database must be different from the publication database.</span></span>  
  
-   <span data-ttu-id="44645-112">Для подписчиков, отличных от[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , база данных подписки не отображается.</span><span class="sxs-lookup"><span data-stu-id="44645-112">For non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, the subscription database is not displayed.</span></span> <span data-ttu-id="44645-113">В поле **Имя источника данных** диалогового окна **Добавление сервера, отличного от подписчика SQL Server** укажите базу данных вместе с другими сведениями о соединении.</span><span class="sxs-lookup"><span data-stu-id="44645-113">Specify the database, along with other connection information, in the **Data source name** field of the **Add Non-SQL Server** dialog box.</span></span> <span data-ttu-id="44645-114">Чтобы открыть это диалоговое окно, нажмите кнопку **Добавить подписчик** , а затем выберите пункт **Добавить подписчик, отличный от подписчика SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="44645-114">This dialog box is available by clicking **Add Subscriber** and then clicking **Add Non-SQL Server Subscriber**.</span></span>  
  
 <span data-ttu-id="44645-115">**Добавить подписчик**</span><span class="sxs-lookup"><span data-stu-id="44645-115">**Add Subscriber**</span></span>  
 <span data-ttu-id="44645-116">Добавьте сервер в список серверов, которые могут быть включены в качестве подписчиков.</span><span class="sxs-lookup"><span data-stu-id="44645-116">Add a server to the list of servers that can be enabled as Subscribers.</span></span> <span data-ttu-id="44645-117">Данная кнопка отображается, когда выполняются все перечисленные далее условия.</span><span class="sxs-lookup"><span data-stu-id="44645-117">This button is displayed when all of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="44645-118">Выбранная публикация является публикацией транзакций или моментальных снимков без поддержки обновляемых подписок.</span><span class="sxs-lookup"><span data-stu-id="44645-118">The publication you selected is a snapshot or transactional publication that does not support updating subscriptions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="44645-119">Если публикация, на которую выполняется подписка, имеет подписки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , но еще не подготовлена для подписчиков, не являющихся[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , добавить подписку, не являющуюся[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , невозможно.</span><span class="sxs-lookup"><span data-stu-id="44645-119">If the publication you are subscribing to has [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subscriptions and the publication is not already enabled for non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, you cannot add a non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subscription.</span></span>  
  
-   <span data-ttu-id="44645-120">Подписка является принудительной.</span><span class="sxs-lookup"><span data-stu-id="44645-120">The subscription is a push subscription.</span></span>  
  
-   <span data-ttu-id="44645-121">Издателем выбранной публикации является [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="44645-121">The Publisher of the selected publication is [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later.</span></span>  
  
 <span data-ttu-id="44645-122">При нажатии кнопки **Добавить подписчик** отображается меню с двумя пунктами: **Добавить подписчик SQL Server** и **Добавить подписчик, отличный от подписчика SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="44645-122">Clicking **Add Subscriber** shows a menu with two choices: **Add SQL Server Subscriber** and **Add Non-SQL Server Subscriber**.</span></span> <span data-ttu-id="44645-123">Чтобы добавить подписчик Oracle или IBM DB2, выберите пункт **Добавить подписчик, отличный от подписчика SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="44645-123">Click **Add Non-SQL Server Subscriber** to add an Oracle or IBM DB2 Subscriber.</span></span>  
  
 <span data-ttu-id="44645-124">**Добавить подписчик SQL Server**</span><span class="sxs-lookup"><span data-stu-id="44645-124">**Add SQL Server Subscriber**</span></span>  
 <span data-ttu-id="44645-125">Добавьте сервер в список серверов, которые могут быть включены в качестве подписчиков.</span><span class="sxs-lookup"><span data-stu-id="44645-125">Add a server to the list of servers that can be enabled as Subscribers.</span></span> <span data-ttu-id="44645-126">Данная кнопка отображается при выполнении одного или нескольких из перечисленных ниже условий.</span><span class="sxs-lookup"><span data-stu-id="44645-126">This button is displayed when one or more of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="44645-127">Выбранная публикация является публикацией слиянием, публикацией моментальными снимками или публикацией транзакций с поддержкой обновляемых подписок.</span><span class="sxs-lookup"><span data-stu-id="44645-127">The publication you selected is a merge publication, or a snapshot or transactional publication that supports updating subscriptions.</span></span>  
  
-   <span data-ttu-id="44645-128">Подписка является подпиской по запросу.</span><span class="sxs-lookup"><span data-stu-id="44645-128">The subscription is a pull subscription.</span></span>  
  
-   <span data-ttu-id="44645-129">Версия издателя выбранной публикации ниже [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44645-129">The Publisher of the selected publication is earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="44645-130">Для более ранних версий данная кнопка отображается при выполнении одного или нескольких из перечисленных ниже условий.</span><span class="sxs-lookup"><span data-stu-id="44645-130">For earlier versions, the button is displayed only if one or more of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="44645-131">Вы являетесь членом предопределенной роли сервера **sysadmin** на издателе.</span><span class="sxs-lookup"><span data-stu-id="44645-131">You are a member of the **sysadmin** fixed server role at the Publisher.</span></span>  
  
    -   <span data-ttu-id="44645-132">Подписка добавлена на странице **Подписчики** в диалоговом окне **Свойства издателя** .</span><span class="sxs-lookup"><span data-stu-id="44645-132">The Subscriber has been added on the **Subscribers** page of the **Publisher Properties** dialog box.</span></span>  
  
    -   <span data-ttu-id="44645-133">Публикация допускает анонимные подписки.</span><span class="sxs-lookup"><span data-stu-id="44645-133">The publication allows anonymous subscriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44645-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="44645-134">See Also</span></span>  
 <span data-ttu-id="44645-135">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="44645-135">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="44645-136">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="44645-136">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="44645-137">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="44645-137">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 [<span data-ttu-id="44645-138">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="44645-138">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
