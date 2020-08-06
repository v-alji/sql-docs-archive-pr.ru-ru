---
title: MSSQL_ENG014157 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014157 error
ms.assetid: 1a0890cf-d977-43e0-a2ba-9c5ff1a8f856
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0682d740d82c995d64427f56aabce24b8a48ca65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658210"
---
# <a name="mssql_eng014157"></a><span data-ttu-id="7c54d-102">MSSQL_ENG014157</span><span class="sxs-lookup"><span data-stu-id="7c54d-102">MSSQL_ENG014157</span></span>
    
## <a name="message-details"></a><span data-ttu-id="7c54d-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="7c54d-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7c54d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7c54d-104">Product Name</span></span>|<span data-ttu-id="7c54d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c54d-105">SQL Server</span></span>|  
|<span data-ttu-id="7c54d-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7c54d-106">Event ID</span></span>|<span data-ttu-id="7c54d-107">14157</span><span class="sxs-lookup"><span data-stu-id="7c54d-107">14157</span></span>|  
|<span data-ttu-id="7c54d-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="7c54d-108">Event Source</span></span>|<span data-ttu-id="7c54d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7c54d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7c54d-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="7c54d-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="7c54d-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="7c54d-111">Symbolic Name</span></span>||  
|<span data-ttu-id="7c54d-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="7c54d-112">Message Text</span></span>|<span data-ttu-id="7c54d-113">Подписка, созданная подписчиком "%s" на издателе "%s", истекла и была удалена.</span><span class="sxs-lookup"><span data-stu-id="7c54d-113">The subscription created by Subscriber '%s' to publication '%s' has expired and has been dropped.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7c54d-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="7c54d-114">Explanation</span></span>  
 <span data-ttu-id="7c54d-115">Подписчик должен синхронизироваться с издателем в течение времени, указанного в сроке хранения публикации.</span><span class="sxs-lookup"><span data-stu-id="7c54d-115">A Subscriber must synchronize with the Publisher within the time specified in the publication retention period.</span></span> <span data-ttu-id="7c54d-116">Если подписчик не будет синхронизирован в указанный период, то срок действия подписки истечет.</span><span class="sxs-lookup"><span data-stu-id="7c54d-116">If a Subscriber does not synchronize within this period, the subscription expires.</span></span> <span data-ttu-id="7c54d-117">Дополнительные сведения см. в разделе [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="7c54d-117">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7c54d-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="7c54d-118">User Action</span></span>  
 <span data-ttu-id="7c54d-119">Прежде чем подписчик сможет снова получать изменения данных, подписка должна быть создана и инициализирована заново:</span><span class="sxs-lookup"><span data-stu-id="7c54d-119">The subscription must be re-created and initialized before the Subscriber can begin receiving data changes again:</span></span>  
  
-   <span data-ttu-id="7c54d-120">Дополнительные сведения о создании подписок см. в статье [Подписка на публикации](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="7c54d-120">For information about creating subscriptions, see [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
-   <span data-ttu-id="7c54d-121">Сведения об инициализации подписок см. в [этой статье](initialize-a-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="7c54d-121">For information about initializing subscriptions, see [Initialize a Subscription](initialize-a-subscription.md).</span></span>  
  
 <span data-ttu-id="7c54d-122">Если в базе данных подписки содержатся изменения, которые не были синхронизированы с издателем, при помощи [tablediff Utility](../../tools/tablediff-utility.md) можно определить, какие строки в базах данных публикации и подписки отличаются.</span><span class="sxs-lookup"><span data-stu-id="7c54d-122">If the subscription database contains changes that have not been synchronized with the Publisher, you can use the [tablediff Utility](../../tools/tablediff-utility.md) to determine which rows are different in the publication and subscription databases.</span></span>  
  
 <span data-ttu-id="7c54d-123">Срок действия подписок можно продлить, увеличив срок хранения публикации.</span><span class="sxs-lookup"><span data-stu-id="7c54d-123">You can increase the publication retention period to avoid having subscriptions expire.</span></span> <span data-ttu-id="7c54d-124">Не рекомендуется задавать слишком большое значение, поскольку это может привести к хранению большего объема данных и метаданных, что оказывает отрицательное влияние на производительность.</span><span class="sxs-lookup"><span data-stu-id="7c54d-124">Use caution in setting a high value, because this can result in more data and metadata being stored, which affects performance.</span></span> <span data-ttu-id="7c54d-125">Дополнительные сведения см. в разделе [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="7c54d-125">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c54d-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c54d-126">See Also</span></span>  
 [<span data-ttu-id="7c54d-127">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="7c54d-127">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
