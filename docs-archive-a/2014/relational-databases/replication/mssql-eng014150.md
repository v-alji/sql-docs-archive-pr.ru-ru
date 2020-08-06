---
title: MSSQL_ENG014150 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014150 error
ms.assetid: c3dd3109-abf3-4b38-a4e9-ef48d0235656
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c926d05be9613ff559f119484fa5e238d71d861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655076"
---
# <a name="mssql_eng014150"></a><span data-ttu-id="4bed1-102">MSSQL_ENG014150</span><span class="sxs-lookup"><span data-stu-id="4bed1-102">MSSQL_ENG014150</span></span>
    
## <a name="message-details"></a><span data-ttu-id="4bed1-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="4bed1-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4bed1-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="4bed1-104">Product Name</span></span>|<span data-ttu-id="4bed1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4bed1-105">SQL Server</span></span>|  
|<span data-ttu-id="4bed1-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="4bed1-106">Event ID</span></span>|<span data-ttu-id="4bed1-107">14150</span><span class="sxs-lookup"><span data-stu-id="4bed1-107">14150</span></span>|  
|<span data-ttu-id="4bed1-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="4bed1-108">Event Source</span></span>|<span data-ttu-id="4bed1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4bed1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4bed1-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="4bed1-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="4bed1-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="4bed1-111">Symbolic Name</span></span>||  
|<span data-ttu-id="4bed1-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="4bed1-112">Message Text</span></span>|<span data-ttu-id="4bed1-113">Репликация-%s: агент %s выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="4bed1-113">Replication-%s: agent %s succeeded.</span></span> <span data-ttu-id="4bed1-114">%s</span><span class="sxs-lookup"><span data-stu-id="4bed1-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4bed1-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="4bed1-115">Explanation</span></span>  
 <span data-ttu-id="4bed1-116">Это сообщение указывает, что агент репликации успешно завершил работу.</span><span class="sxs-lookup"><span data-stu-id="4bed1-116">This message indicates that a replication agent has successfully finished running.</span></span> <span data-ttu-id="4bed1-117">Для репликации применяются следующие агенты.</span><span class="sxs-lookup"><span data-stu-id="4bed1-117">Replication uses the following agents:</span></span>  
  
-   <span data-ttu-id="4bed1-118">Агент моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="4bed1-118">The Snapshot Agent.</span></span> <span data-ttu-id="4bed1-119">Используется всеми публикациями.</span><span class="sxs-lookup"><span data-stu-id="4bed1-119">This agent is used by all publications.</span></span>  
  
-   <span data-ttu-id="4bed1-120">Агент чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="4bed1-120">The Log Reader Agent.</span></span> <span data-ttu-id="4bed1-121">Используется всеми публикациями транзакций.</span><span class="sxs-lookup"><span data-stu-id="4bed1-121">This agent is used by all transactional publications.</span></span>  
  
-   <span data-ttu-id="4bed1-122">Агент чтения очереди.</span><span class="sxs-lookup"><span data-stu-id="4bed1-122">The Queue Reader Agent.</span></span> <span data-ttu-id="4bed1-123">Используется публикациями транзакций, для которых включены обновляемые посредством очередей подписки.</span><span class="sxs-lookup"><span data-stu-id="4bed1-123">This agent is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="4bed1-124">Агент распространителя.</span><span class="sxs-lookup"><span data-stu-id="4bed1-124">The Distribution Agent.</span></span> <span data-ttu-id="4bed1-125">Синхронизирует подписки на публикации транзакций и публикации моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="4bed1-125">This agent synchronizes subscriptions to transactional and snapshot publications.</span></span>  
  
-   <span data-ttu-id="4bed1-126">Агент слияния.</span><span class="sxs-lookup"><span data-stu-id="4bed1-126">The Merge Agent.</span></span> <span data-ttu-id="4bed1-127">Синхронизирует подписки на публикации слиянием.</span><span class="sxs-lookup"><span data-stu-id="4bed1-127">This agent synchronizes subscriptions to merge publications.</span></span>  
  
-   <span data-ttu-id="4bed1-128">Задания по обслуживанию репликации.</span><span class="sxs-lookup"><span data-stu-id="4bed1-128">Replication maintenance jobs.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4bed1-129">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="4bed1-129">User Action</span></span>  
 <span data-ttu-id="4bed1-130">Агент чтения журнала, агент чтения очереди и агент распространителя обычно выполняются постоянно, тогда как другие агенты чаще всего выполняются по запросу или по расписанию.</span><span class="sxs-lookup"><span data-stu-id="4bed1-130">The Log Reader Agent, Queue Reader Agent, and Distribution Agent typically run continuously, whereas the other agents typically run on demand or on a schedule.</span></span> <span data-ttu-id="4bed1-131">Если агент неожиданно завершил работу, проверьте состояние агента.</span><span class="sxs-lookup"><span data-stu-id="4bed1-131">If you do not expect an agent to have completed a run, check the status of the agent.</span></span> <span data-ttu-id="4bed1-132">Дополнительные сведения см. в статье [Monitor Replication Agents](agents/replication-agents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4bed1-132">For more information, see [Monitor Replication Agents](agents/replication-agents-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bed1-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="4bed1-133">See Also</span></span>  
 <span data-ttu-id="4bed1-134">[Администрирование агента репликации](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="4bed1-134">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 <span data-ttu-id="4bed1-135">[Справочник по ошибкам и событиям (репликация)](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="4bed1-135">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="4bed1-136">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="4bed1-136">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="4bed1-137">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="4bed1-137">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="4bed1-138">[Replication Merge Agent](agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="4bed1-138">[Replication Merge Agent](agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="4bed1-139">[Агент чтения очереди репликации](agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="4bed1-139">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="4bed1-140">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="4bed1-140">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
  
