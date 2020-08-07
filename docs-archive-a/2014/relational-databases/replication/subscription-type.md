---
title: Тип подписки | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.subscriptiontype.f1
ms.assetid: 9a50f588-ee45-4a87-826f-372ff0798587
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 614ff910b13706485ee9466c884243ff1c9027ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731506"
---
# <a name="subscription-type"></a><span data-ttu-id="45fe2-102">Тип подписки</span><span class="sxs-lookup"><span data-stu-id="45fe2-102">Subscription Type</span></span>
  <span data-ttu-id="45fe2-103">Репликация слиянием реализует два типа подписки: серверную и клиентскую (в предыдущих версиях [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] им соответствуют глобальная и локальная подписки).</span><span class="sxs-lookup"><span data-stu-id="45fe2-103">Merge replication offers two subscription types: server and client (referred to in previous versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as global and local, respectively).</span></span> <span data-ttu-id="45fe2-104">Подписчики с серверной подпиской могут:</span><span class="sxs-lookup"><span data-stu-id="45fe2-104">Subscribers with a server subscription can:</span></span>  
  
-   <span data-ttu-id="45fe2-105">повторно публиковать данные для других подписчиков;</span><span class="sxs-lookup"><span data-stu-id="45fe2-105">Republish data to other Subscribers.</span></span>  
  
-   <span data-ttu-id="45fe2-106">служить альтернативным участником синхронизации;</span><span class="sxs-lookup"><span data-stu-id="45fe2-106">Serve as alternate synchronization partners.</span></span>  
  
-   <span data-ttu-id="45fe2-107">разрешать конфликты в соответствии с установленным приоритетом.</span><span class="sxs-lookup"><span data-stu-id="45fe2-107">Resolve conflicts according to a priority you set.</span></span>  
  
 <span data-ttu-id="45fe2-108">Большинству подписчиков не требуются такие функциональные возможности, и они могут использовать клиентскую подписку.</span><span class="sxs-lookup"><span data-stu-id="45fe2-108">Most Subscribers do not require this functionality and can use a client subscription.</span></span> <span data-ttu-id="45fe2-109">Клиентские подписки также позволяют отслеживать и решать конфликты, однако подписчикам не назначается приоритет: первый подписчик, подавший изменение издателю, выигрывает любой конфликт, который может возникнуть из-за внесения данного изменения.</span><span class="sxs-lookup"><span data-stu-id="45fe2-109">Client subscriptions still allow conflict detection and resolution, but Subscribers are not assigned a priority: the first Subscriber to submit a change to the Publisher wins any conflicts that might arise from that change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45fe2-110">Тип подписки нельзя изменить после ее создания.</span><span class="sxs-lookup"><span data-stu-id="45fe2-110">Subscription type cannot be changed after a subscription is created.</span></span>  
  
## <a name="options"></a><span data-ttu-id="45fe2-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="45fe2-111">Options</span></span>  
 <span data-ttu-id="45fe2-112">**Свойства подписки**</span><span class="sxs-lookup"><span data-stu-id="45fe2-112">**Subscription properties**</span></span>  
 <span data-ttu-id="45fe2-113">Выберите **Клиентская** или **Серверная** из раскрывающегося списка в столбце **Тип подписки** для каждого подписчика.</span><span class="sxs-lookup"><span data-stu-id="45fe2-113">For each Subscriber, select **Client** or **Server** from the drop-down list box in the **Subscription Type** column.</span></span> <span data-ttu-id="45fe2-114">Для подписчиков с серверными подписками введите число между 0 и 99,99 в столбце **Приоритет устранения конфликтов** (чем выше число, тем выше приоритет подписчика).</span><span class="sxs-lookup"><span data-stu-id="45fe2-114">For Subscribers with server subscriptions, enter a number between 0 and 99.99 in the **Priority for Conflict Resolution** column (the higher the number, the higher the priority for the Subscriber).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45fe2-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="45fe2-115">See Also</span></span>  
 <span data-ttu-id="45fe2-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="45fe2-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="45fe2-117">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="45fe2-117">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 [<span data-ttu-id="45fe2-118">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="45fe2-118">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
