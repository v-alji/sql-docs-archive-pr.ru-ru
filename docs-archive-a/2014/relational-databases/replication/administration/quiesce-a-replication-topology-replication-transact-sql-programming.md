---
title: Заморозка топологии репликации (программирование репликации на языке Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- administering replication, quiescing
- quiesce [SQL Server replication]
- transactional replication, backup and restore
ms.assetid: 7626d575-9994-47be-b772-5b6f1b7ef7ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f12f0fb8ee3a6118e03799d17836573fb5c733df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736248"
---
# <a name="quiesce-a-replication-topology-replication-transact-sql-programming"></a><span data-ttu-id="695b7-102">заморозить топологию репликации (программирование репликации на языке Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="695b7-102">Quiesce a Replication Topology (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="695b7-103">*Замораживание* системы предполагает прекращение операций с опубликованными таблицами на всех узлах и проверку того, что каждый узел получил все изменения со всех других узлов.</span><span class="sxs-lookup"><span data-stu-id="695b7-103">*Quiescing* a system involves stopping activity on published tables at all nodes and ensuring that each node has received all changes from all other nodes.</span></span> <span data-ttu-id="695b7-104">В этом разделе показано, как заморозить топологию репликации (что необходимо для решения ряда административных задач) и убедиться в том, что узел получил все изменения от других узлов.</span><span class="sxs-lookup"><span data-stu-id="695b7-104">This topic explains how to quiesce a replication topology, which is required for a number of administrative tasks, and how to ensure that a node has received all changes from other nodes.</span></span>  
  
### <a name="to-quiesce-a-transactional-replication-topology-with-read-only-subscriptions"></a><span data-ttu-id="695b7-105">Замораживание топологии репликации транзакций с подписками только для чтения</span><span class="sxs-lookup"><span data-stu-id="695b7-105">To quiesce a transactional replication topology with read-only subscriptions</span></span>  
  
1.  <span data-ttu-id="695b7-106">Приостановите операции со всеми опубликованными таблицами на издателе.</span><span class="sxs-lookup"><span data-stu-id="695b7-106">Stop activity on all published tables at the Publisher.</span></span>  
  
2.  <span data-ttu-id="695b7-107">В издателе в базе данных публикации выполните процедуру [sp_posttracertoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="695b7-107">At the Publisher on the publication database, execute [sp_posttracertoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span></span>  
  
3.  <span data-ttu-id="695b7-108">В базе данных публикации на издателе выполните процедуру [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="695b7-108">At the Publisher on the publication database, execute [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span></span>  
  
4.  <span data-ttu-id="695b7-109">Убедитесь, что каждый подписчик получил трассировочный токен.</span><span class="sxs-lookup"><span data-stu-id="695b7-109">Ensure that each Subscriber has received the tracer token.</span></span>  
  
### <a name="to-quiesce-a-transactional-replication-topology-with-updatable-subscriptions"></a><span data-ttu-id="695b7-110">Замораживание топологии репликации транзакций с обновляемыми подписками</span><span class="sxs-lookup"><span data-stu-id="695b7-110">To quiesce a transactional replication topology with updatable subscriptions</span></span>  
  
1.  <span data-ttu-id="695b7-111">Приостановите операции со всеми опубликованными таблицами на издателе и на всех подписчиках.</span><span class="sxs-lookup"><span data-stu-id="695b7-111">Stop activity on all published tables at the Publisher and all Subscribers.</span></span>  
  
2.  <span data-ttu-id="695b7-112">Если кто-либо из подписчиков использует подписки, обновляемые посредством очередей, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="695b7-112">If any Subscribers use queued updating subscriptions:</span></span>  
  
    1.  <span data-ttu-id="695b7-113">Если агент чтения очереди не работает постоянно, запустите его.</span><span class="sxs-lookup"><span data-stu-id="695b7-113">If the Queue Reader Agent is not running in continuous mode, run the agent.</span></span> <span data-ttu-id="695b7-114">Дополнительные сведения о выполнении агентов см. в статьях [Основные понятия исполняемых файлов агента репликации](../concepts/replication-agent-executables-concepts.md) и [Запуск и остановка агента репликации (среда SQL Server Management Studio)](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="695b7-114">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
    2.  <span data-ttu-id="695b7-115">Чтобы убедиться в том, что очередь пуста, выполните процедуру [sp_replqueuemonitor](/sql/relational-databases/system-stored-procedures/sp-replqueuemonitor-transact-sql) на каждом подписчике.</span><span class="sxs-lookup"><span data-stu-id="695b7-115">To verify that the queue is empty, execute [sp_replqueuemonitor](/sql/relational-databases/system-stored-procedures/sp-replqueuemonitor-transact-sql) at each Subscriber.</span></span>  
  
3.  <span data-ttu-id="695b7-116">В базе данных публикации на издателе выполните процедуру [sp_posttracertoken](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="695b7-116">At the Publisher on the publication database, execute [sp_posttracertoken](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span></span>  
  
4.  <span data-ttu-id="695b7-117">В базе данных публикации на издателе выполните процедуру [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="695b7-117">At the Publisher on the publication database, execute [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span></span>  
  
5.  <span data-ttu-id="695b7-118">Убедитесь, что каждый подписчик получил трассировочный токен.</span><span class="sxs-lookup"><span data-stu-id="695b7-118">Ensure that each Subscriber has received the tracer token.</span></span>  
  
### <a name="to-quiesce-a-peer-to-peer-transactional-replication-topology"></a><span data-ttu-id="695b7-119">Замораживание одноранговой топологии репликации транзакций</span><span class="sxs-lookup"><span data-stu-id="695b7-119">To quiesce a peer-to-peer transactional replication topology</span></span>  
  
1.  <span data-ttu-id="695b7-120">Приостановите операции со всеми опубликованными таблицами на всех узлах.</span><span class="sxs-lookup"><span data-stu-id="695b7-120">Stop activity on all published tables at all nodes.</span></span>  
  
2.  <span data-ttu-id="695b7-121">Выполните процедуру [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) в каждой базе данных публикации в топологии.</span><span class="sxs-lookup"><span data-stu-id="695b7-121">Execute [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) on each publication database in the topology.</span></span>  
  
3.  <span data-ttu-id="695b7-122">Если агент чтения журнала или агент распространителя не выполняется в непрерывном режиме, запустите его.</span><span class="sxs-lookup"><span data-stu-id="695b7-122">If the Log Reader Agent or Distribution Agent is not running in continuous mode, run the agent.</span></span> <span data-ttu-id="695b7-123">Сначала необходимо запустить агент чтения журнала, а затем агент распространителя.</span><span class="sxs-lookup"><span data-stu-id="695b7-123">The Log Reader Agent must be started before the Distribution Agent.</span></span> <span data-ttu-id="695b7-124">Дополнительные сведения о выполнении агентов см. в статьях [Основные понятия исполняемых файлов агента репликации](../concepts/replication-agent-executables-concepts.md) и [Запуск и остановка агента репликации (среда SQL Server Management Studio)](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="695b7-124">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
4.  <span data-ttu-id="695b7-125">Выполните процедуру [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) в каждой базе данных публикации в топологии.</span><span class="sxs-lookup"><span data-stu-id="695b7-125">Execute [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) on each publication database in the topology.</span></span> <span data-ttu-id="695b7-126">Убедитесь, что в результирующем наборе содержатся ответы от всех других узлов.</span><span class="sxs-lookup"><span data-stu-id="695b7-126">Ensure that the result set contains responses from each of the other nodes.</span></span>  
  
### <a name="to-ensure-a-peer-to-peer-node-has-received-all-prior-changes"></a><span data-ttu-id="695b7-127">Проверка того, что одноранговый узел получил все предыдущие изменения</span><span class="sxs-lookup"><span data-stu-id="695b7-127">To ensure a peer-to-peer node has received all prior changes</span></span>  
  
1.  <span data-ttu-id="695b7-128">Выполните процедуру [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) в каждой базе данных публикации на проверяемом узле.</span><span class="sxs-lookup"><span data-stu-id="695b7-128">Execute [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) on the publication database at the node you are checking.</span></span>  
  
2.  <span data-ttu-id="695b7-129">Если агент чтения журнала или агент распространителя не выполняется в непрерывном режиме, запустите его.</span><span class="sxs-lookup"><span data-stu-id="695b7-129">If the Log Reader Agent or Distribution Agent is not running in continuous mode, run the agent.</span></span> <span data-ttu-id="695b7-130">Сначала необходимо запустить агент чтения журнала, а затем агент распространителя.</span><span class="sxs-lookup"><span data-stu-id="695b7-130">The Log Reader Agent must be started before the Distribution Agent.</span></span> <span data-ttu-id="695b7-131">Дополнительные сведения о выполнении агентов см. в статьях [Основные понятия исполняемых файлов агента репликации](../concepts/replication-agent-executables-concepts.md) и [Запуск и остановка агента репликации (среда SQL Server Management Studio)](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="695b7-131">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
3.  <span data-ttu-id="695b7-132">Выполните процедуру [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) в каждой базе данных публикации на проверяемом узле.</span><span class="sxs-lookup"><span data-stu-id="695b7-132">Execute [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) on the publication database at the node you are checking.</span></span> <span data-ttu-id="695b7-133">Убедитесь, что в результирующем наборе содержатся ответы от всех других узлов.</span><span class="sxs-lookup"><span data-stu-id="695b7-133">Ensure that the result set contains responses from each of the other nodes.</span></span>  
  
### <a name="to-quiesce-a-merge-replication-topology"></a><span data-ttu-id="695b7-134">Замораживание топологии репликации слиянием</span><span class="sxs-lookup"><span data-stu-id="695b7-134">To quiesce a merge replication topology</span></span>  
  
1.  <span data-ttu-id="695b7-135">Приостановите операции со всеми опубликованными таблицами на издателе и на всех подписчиках.</span><span class="sxs-lookup"><span data-stu-id="695b7-135">Stop activity on all published tables at the Publisher and at all Subscribers.</span></span>  
  
2.  <span data-ttu-id="695b7-136">Выполните агент слияния для каждой подписки дважды: сначала для синхронизации всех подписок, а затем для повторной синхронизации каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="695b7-136">Run the Merge Agent for each subscription two times: synchronize all subscriptions once and then synchronize each subscription a second time.</span></span> <span data-ttu-id="695b7-137">Таким образом будет гарантирована репликация изменений на все узлы.</span><span class="sxs-lookup"><span data-stu-id="695b7-137">This ensures that all changes are replicated to all nodes.</span></span> <span data-ttu-id="695b7-138">Дополнительные сведения о выполнении агентов см. в статьях [Основные понятия исполняемых файлов агента репликации](../concepts/replication-agent-executables-concepts.md) и [Запуск и остановка агента репликации (среда SQL Server Management Studio)](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="695b7-138">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="695b7-139">Если во время синхронизации обнаружен конфликт, то изменения, необходимые для разрешения конфликта, могут не распространиться на все узлы после того, как агент слияния будет запущен дважды.</span><span class="sxs-lookup"><span data-stu-id="695b7-139">If conflicts occur during synchronization, it is possible that changes required by conflict resolution will not be propagated to all nodes after running the Merge Agent two times.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="695b7-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="695b7-140">See Also</span></span>  
 <span data-ttu-id="695b7-141">[Администрирование одноранговой топологии (программирование репликации на языке Transact-SQL)](administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span><span class="sxs-lookup"><span data-stu-id="695b7-141">[Administer a Peer-to-Peer Topology &#40;Replication Transact-SQL Programming&#41;](administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span></span>  
 [<span data-ttu-id="695b7-142">Измерение задержки и проверка правильности соединений для репликации транзакций</span><span class="sxs-lookup"><span data-stu-id="695b7-142">Measure Latency and Validate Connections for Transactional Replication</span></span>](../monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
  
