---
title: MSSQL_ENG014160 | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014160 error
ms.assetid: d0f3855e-d095-4a81-a5bd-9d7ad51f2c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3351567a31a0a0384ab8957073ab0457ef0ea7c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655069"
---
# <a name="mssql_eng014160"></a><span data-ttu-id="19ab8-102">MSSQL_ENG014160</span><span class="sxs-lookup"><span data-stu-id="19ab8-102">MSSQL_ENG014160</span></span>
    
## <a name="message-details"></a><span data-ttu-id="19ab8-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="19ab8-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19ab8-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="19ab8-104">Product Name</span></span>|<span data-ttu-id="19ab8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="19ab8-105">SQL Server</span></span>|  
|<span data-ttu-id="19ab8-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="19ab8-106">Event ID</span></span>|<span data-ttu-id="19ab8-107">14160</span><span class="sxs-lookup"><span data-stu-id="19ab8-107">14160</span></span>|  
|<span data-ttu-id="19ab8-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="19ab8-108">Event Source</span></span>|<span data-ttu-id="19ab8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="19ab8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="19ab8-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="19ab8-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="19ab8-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="19ab8-111">Symbolic Name</span></span>||  
|<span data-ttu-id="19ab8-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="19ab8-112">Message Text</span></span>|<span data-ttu-id="19ab8-113">Задан порог [%s:%s] для публикации [%s].</span><span class="sxs-lookup"><span data-stu-id="19ab8-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="19ab8-114">Срок действия подписки на эту публикацию истек у одного или нескольких подписчиков.</span><span class="sxs-lookup"><span data-stu-id="19ab8-114">One or more subscriptions to this publication have expired.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="19ab8-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="19ab8-115">Explanation</span></span>  
 <span data-ttu-id="19ab8-116">При репликации можно включить предупреждения для ряда условий.</span><span class="sxs-lookup"><span data-stu-id="19ab8-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="19ab8-117">Сюда входит приближение истечения срока действия подписки.</span><span class="sxs-lookup"><span data-stu-id="19ab8-117">This includes imminent subscription expiration.</span></span> <span data-ttu-id="19ab8-118">Срок действия подписок может закончиться, если они не будут синхронизированы в течение определенного *срока хранения*.</span><span class="sxs-lookup"><span data-stu-id="19ab8-118">Subscriptions can expire if they are not synchronized within a specified *retention period*.</span></span> <span data-ttu-id="19ab8-119">Дополнительные сведения см. в разделе [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="19ab8-119">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
 <span data-ttu-id="19ab8-120">Когда предупреждение включается при помощи монитора репликации или процедуры [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), необходимо указать пороговое значение, определяющее, в какой момент выдается предупреждение.</span><span class="sxs-lookup"><span data-stu-id="19ab8-120">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="19ab8-121">При достижении или превышении порогового значения предупреждение отображается в мониторе репликации, а в журнал событий Windows записывается событие.</span><span class="sxs-lookup"><span data-stu-id="19ab8-121">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="19ab8-122">Достижение порогового значения также может приводить к выдаче предупреждения агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="19ab8-122">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="19ab8-123">Дополнительные сведения см. в статьях [Настройка пороговых значений и предупреждений в мониторе репликации](monitor/set-thresholds-and-warnings-in-replication-monitor.md). и [Наблюдение за репликацией программным образом](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="19ab8-123">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="19ab8-124">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="19ab8-124">User Action</span></span>  
 <span data-ttu-id="19ab8-125">Решение проблемы зависит от причины выдачи предупреждения:</span><span class="sxs-lookup"><span data-stu-id="19ab8-125">The resolution for this issue depends on the reason the warning was raised:</span></span>  
  
-   <span data-ttu-id="19ab8-126">Если превышено пороговое значение, но срок действия подписки еще не истек, синхронизируйте подписку.</span><span class="sxs-lookup"><span data-stu-id="19ab8-126">If the threshold has been exceeded, but the subscription has not yet expired, synchronize the subscription.</span></span> <span data-ttu-id="19ab8-127">Дополнительные сведения см. в разделе [Синхронизация данных](synchronize-data.md).</span><span class="sxs-lookup"><span data-stu-id="19ab8-127">For more information, see [Synchronize Data](synchronize-data.md).</span></span>  
  
-   <span data-ttu-id="19ab8-128">Если агент работал, но неправильно реплицировал изменения, это могло стать причиной истечения срока действия подписки.</span><span class="sxs-lookup"><span data-stu-id="19ab8-128">If the agent has been running, but has not been replicating changes properly, this can cause the subscription to expire.</span></span> <span data-ttu-id="19ab8-129">В случае репликации транзакций удостоверьтесь, что работают агент распространителя и агент чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="19ab8-129">For transactional replication, make sure that the Distribution Agent and Log Reader Agent are running.</span></span> <span data-ttu-id="19ab8-130">В случае репликации слиянием удостоверьтесь, что работает агент слияния.</span><span class="sxs-lookup"><span data-stu-id="19ab8-130">For merge replication, make sure the Merge Agent is running.</span></span> <span data-ttu-id="19ab8-131">Дополнительные сведения о запуске этих агентов см. в статьях [Запуск и остановка агента репликации (среда SQL Server Management Studio)](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) и [Основные понятия исполняемых файлов агента репликации](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="19ab8-131">For information about how to start these agents, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="19ab8-132">Если срок действия подписки истек, ее необходимо либо повторно инициализировать, либо удалить и создать повторно. Это зависит от типа подписки и того, как давно истек ее срок действия.</span><span class="sxs-lookup"><span data-stu-id="19ab8-132">If the subscription has expired, it must either be reinitialized or dropped and re-created, depending on the type of subscription and how long it has been expired.</span></span> <span data-ttu-id="19ab8-133">Дополнительные сведения см. в разделе [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="19ab8-133">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ab8-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="19ab8-134">See Also</span></span>  
 [<span data-ttu-id="19ab8-135">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="19ab8-135">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
