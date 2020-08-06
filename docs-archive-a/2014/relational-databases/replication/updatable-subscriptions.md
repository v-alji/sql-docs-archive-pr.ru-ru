---
title: Обновляемые подписки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptions.f1
ms.assetid: 8e9a13a0-6b24-47c6-9d83-3cbaf08f673d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 447114152365e098420f46d4b7e880e8f2907864
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730465"
---
# <a name="updatable-subscriptions"></a><span data-ttu-id="b1e54-102">Обновляемые подписки</span><span class="sxs-lookup"><span data-stu-id="b1e54-102">Updatable Subscriptions</span></span>
  <span data-ttu-id="b1e54-103">В случае репликации транзакций реплицированные данные следует рассматривать как находящиеся в режиме только для чтения; однако изменить реплицированные данные в подписчике [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно с помощью обновляемых подписок.</span><span class="sxs-lookup"><span data-stu-id="b1e54-103">With transactional replication, replicated data should be treated as read-only; however, you can modify replicated data at a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscriber by using updatable subscriptions.</span></span> <span data-ttu-id="b1e54-104">Если нужно изменить данные на подписчике, выберите один из следующих параметров в зависимости от потребностей.</span><span class="sxs-lookup"><span data-stu-id="b1e54-104">If you need to modify data at the Subscriber, choose one of the following options depending on your requirements.</span></span>  
  
|<span data-ttu-id="b1e54-105">Тип обновляемой подписки</span><span class="sxs-lookup"><span data-stu-id="b1e54-105">Updatable Subscription Type</span></span>|<span data-ttu-id="b1e54-106">Требования</span><span class="sxs-lookup"><span data-stu-id="b1e54-106">Requirements</span></span>|  
|---------------------------------|------------------|  
|<span data-ttu-id="b1e54-107">Немедленное обновление</span><span class="sxs-lookup"><span data-stu-id="b1e54-107">Immediate Updating</span></span>|<span data-ttu-id="b1e54-108">Чтобы обновить данные на сервере подписчика, между издателем и подписчиком должно быть установлено подключение.</span><span class="sxs-lookup"><span data-stu-id="b1e54-108">Publisher and Subscriber must be connected to update data at the Subscriber.</span></span>|  
|<span data-ttu-id="b1e54-109">Обновление посредством очереди</span><span class="sxs-lookup"><span data-stu-id="b1e54-109">Queued Updating</span></span>|<span data-ttu-id="b1e54-110">Чтобы обновить данные на сервере подписчика, установка подключения между издателем и подписчиком необязательна.</span><span class="sxs-lookup"><span data-stu-id="b1e54-110">Publisher and Subscriber do not have to be connected to update data at the Subscriber.</span></span> <span data-ttu-id="b1e54-111">Обновления можно осуществить в режиме «вне сети», а затем синхронизировать их между издателем и подписчиком.</span><span class="sxs-lookup"><span data-stu-id="b1e54-111">Updates can be made while offline, and later synchronized between the Publisher and Subscriber.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="b1e54-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1e54-112">Options</span></span>  
 <span data-ttu-id="b1e54-113">**Репликация изменений подписчика**</span><span class="sxs-lookup"><span data-stu-id="b1e54-113">**Replicate Subscriber changes**</span></span>  
 <span data-ttu-id="b1e54-114">Установите флажок в столбце **Репликация** для каждого подписчика, который должен иметь возможность осуществлять обновления.</span><span class="sxs-lookup"><span data-stu-id="b1e54-114">Select the check box in the **Replicate** column for each Subscriber that should be able to make updates.</span></span> <span data-ttu-id="b1e54-115">Для подписчиков, которые могут осуществлять обновления, выберите соответствующий параметр из раскрывающегося списка в столбце **Зафиксировать на стороне издателя** :</span><span class="sxs-lookup"><span data-stu-id="b1e54-115">For those Subscribers that can make updates, select the appropriate option from the drop-down list box in the **Commit at Publisher** column:</span></span>  
  
-   <span data-ttu-id="b1e54-116">Выберите **Одновременно фиксировать изменения** для немедленного обновления подписки;</span><span class="sxs-lookup"><span data-stu-id="b1e54-116">Select **Simultaneously commit changes** for an immediate updating subscription.</span></span>  
  
-   <span data-ttu-id="b1e54-117">Выберите **Ставить изменения в очередь и фиксировать при первой возможности** для подписки, обновляемой посредством очередей.</span><span class="sxs-lookup"><span data-stu-id="b1e54-117">Select **Queue changes and commit when possible** for a queued updating subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e54-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="b1e54-118">See Also</span></span>  
 <span data-ttu-id="b1e54-119">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="b1e54-119">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="b1e54-120">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="b1e54-120">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="b1e54-121">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="b1e54-121">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="b1e54-122">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="b1e54-122">Updatable Subscriptions for Transactional Replication</span></span>](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
