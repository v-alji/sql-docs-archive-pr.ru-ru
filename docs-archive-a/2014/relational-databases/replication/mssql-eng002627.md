---
title: MSSQL_ENG002627 | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG002627 error
ms.assetid: 7f4136ac-3784-4a41-a98c-8a02308e4883
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cf481635d6a24570792c9da04fe71ebea885ce5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750700"
---
# <a name="mssql_eng002627"></a><span data-ttu-id="ca86e-102">MSSQL_ENG002627</span><span class="sxs-lookup"><span data-stu-id="ca86e-102">MSSQL_ENG002627</span></span>
    
## <a name="message-details"></a><span data-ttu-id="ca86e-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="ca86e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ca86e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="ca86e-104">Product Name</span></span>|<span data-ttu-id="ca86e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca86e-105">SQL Server</span></span>|  
|<span data-ttu-id="ca86e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ca86e-106">Event ID</span></span>|<span data-ttu-id="ca86e-107">2627</span><span class="sxs-lookup"><span data-stu-id="ca86e-107">2627</span></span>|  
|<span data-ttu-id="ca86e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="ca86e-108">Event Source</span></span>|<span data-ttu-id="ca86e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ca86e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ca86e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="ca86e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="ca86e-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="ca86e-111">Symbolic Name</span></span>|<span data-ttu-id="ca86e-112">Недоступно</span><span class="sxs-lookup"><span data-stu-id="ca86e-112">N/A</span></span>|  
|<span data-ttu-id="ca86e-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ca86e-113">Message Text</span></span>|<span data-ttu-id="ca86e-114">Нарушение ограничения "%.\*ls" для %ls.</span><span class="sxs-lookup"><span data-stu-id="ca86e-114">Violation of %ls constraint '%.\*ls'.</span></span> <span data-ttu-id="ca86e-115">Не удается вставить повторяющийся ключ в объект "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="ca86e-115">Cannot insert duplicate key in object '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ca86e-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ca86e-116">Explanation</span></span>  
 <span data-ttu-id="ca86e-117">Это общая ошибка, которая может возникнуть независимо от того, реплицируется база данных или нет.</span><span class="sxs-lookup"><span data-stu-id="ca86e-117">This is a general error that can be raised regardless of whether a database is replicated.</span></span> <span data-ttu-id="ca86e-118">В реплицируемых базах данных эта ошибка возникает, как правило, по причине неправильного управления первичными ключами в топологии.</span><span class="sxs-lookup"><span data-stu-id="ca86e-118">In replicated databases, the error is typically raised because primary keys have not been managed appropriately across the topology.</span></span> <span data-ttu-id="ca86e-119">В распределенной среде необходимо убедиться в том, что одно и то же значение не вставлено в первичный ключевой столбец или в любой другой уникальный столбец на нескольких узлах.</span><span class="sxs-lookup"><span data-stu-id="ca86e-119">In a distributed environment it is essential to ensure that the same value is not inserted into a primary key column or any other unique column at more than one node.</span></span> <span data-ttu-id="ca86e-120">Возможные причины ошибки:</span><span class="sxs-lookup"><span data-stu-id="ca86e-120">Possible causes include the following:</span></span>  
  
-   <span data-ttu-id="ca86e-121">Вставки или обновления строки выполняются более чем в одном узле.</span><span class="sxs-lookup"><span data-stu-id="ca86e-121">Inserts and updates to a row are occurring at more than one node.</span></span> <span data-ttu-id="ca86e-122">И репликация слиянием, и обновляемые подписки для репликации транзакций обеспечивают обнаружение и разрешение конфликта, однако по-прежнему рекомендуется вставлять или обновлять строку только в одном узле.</span><span class="sxs-lookup"><span data-stu-id="ca86e-122">Merge replication and updatable subscriptions for transactional replication both provide conflict detection and resolution, but it is still preferable to insert or update a given row at only one node.</span></span> <span data-ttu-id="ca86e-123">Одноранговые транзакции не обеспечивают обнаружение и разрешение конфликтов. Требуется, чтобы операции вставки и обновления были секционированы.</span><span class="sxs-lookup"><span data-stu-id="ca86e-123">Peer-to-peer transactional does not provide conflict detection and resolution; it requires that inserts and updates be partitioned.</span></span>  
  
-   <span data-ttu-id="ca86e-124">Строка была вставлена на подписчике, который должен быть доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ca86e-124">A row was inserted at a Subscriber that should be read-only.</span></span> <span data-ttu-id="ca86e-125">Подписчики на публикации моментальных снимков должны быть доступны только для чтения, так же как и подписчики на публикации транзакций, если только не используются обновляемые подписки или одноранговые репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="ca86e-125">Subscribers to snapshot publications should be treated as read-only, as should Subscribers to transactional publications unless updatable subscriptions or peer-to-peer transactional replication is used.</span></span>  
  
-   <span data-ttu-id="ca86e-126">Используется таблица со столбцом идентификаторов, однако управление столбцом осуществляется неверно.</span><span class="sxs-lookup"><span data-stu-id="ca86e-126">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ca86e-127">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ca86e-127">User Action</span></span>  
 <span data-ttu-id="ca86e-128">Действие по устранению проблемы зависит от причины, по которой она возникла:</span><span class="sxs-lookup"><span data-stu-id="ca86e-128">The action required depends on the reason the error was raised:</span></span>  
  
-   <span data-ttu-id="ca86e-129">Вставки или обновления строки выполняются более чем в одном узле.</span><span class="sxs-lookup"><span data-stu-id="ca86e-129">Inserts and updates to a row are occurring at more than one node.</span></span>  
  
     <span data-ttu-id="ca86e-130">Независимо от типа используемой репликации рекомендуется секционировать вставки и обновления везде, где это возможно, так как это уменьшит обработку данных, необходимую для обнаружения и разрешения конфликта.</span><span class="sxs-lookup"><span data-stu-id="ca86e-130">Regardless of the type of replication used, we recommend that you partition inserts and updates whenever possible, because this reduces the processing required for conflict detection and resolution.</span></span> <span data-ttu-id="ca86e-131">Секционирование вставок и обновлений является необходимым условием при использовании одноранговой репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="ca86e-131">For peer-to-peer transactional replication, partitioning inserts and updates is required.</span></span> <span data-ttu-id="ca86e-132">Дополнительные сведения см. в разделе [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ca86e-132">For more information, see [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="ca86e-133">Строка была вставлена на подписчике, который должен быть доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ca86e-133">A row was inserted at a Subscriber that should be read-only.</span></span>  
  
     <span data-ttu-id="ca86e-134">Не выполняйте вставку или обновление строк на подписчике, если не используется репликация слиянием, репликация транзакций с обновляемыми подписками или одноранговая репликация транзакций.</span><span class="sxs-lookup"><span data-stu-id="ca86e-134">Do not insert or update rows at the Subscriber unless you are using merge replication, transactional replication with updatable subscriptions, or peer-to-peer transactional replication.</span></span>  
  
-   <span data-ttu-id="ca86e-135">Используется таблица со столбцом идентификаторов, однако управление столбцом осуществляется неверно.</span><span class="sxs-lookup"><span data-stu-id="ca86e-135">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
     <span data-ttu-id="ca86e-136">При использовании репликации слиянием или репликации с обновляемыми подписками столбцы идентификаторов должны автоматически управляться репликацией.</span><span class="sxs-lookup"><span data-stu-id="ca86e-136">For merge replication and transactional replication with updatable subscriptions, identity columns should be managed automatically by replication.</span></span> <span data-ttu-id="ca86e-137">При использовании одноранговой репликации транзакций управление этими столбцами должно выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="ca86e-137">For peer-to-peer transactional replication, they must be managed manually.</span></span> <span data-ttu-id="ca86e-138">Дополнительные сведения см. в статье [Репликация столбцов идентификаторов](publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="ca86e-138">For more information, see [Replicate Identity Columns](publish/replicate-identity-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca86e-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca86e-139">See Also</span></span>  
 <span data-ttu-id="ca86e-140">[Справочник по ошибкам и событиям (репликация)](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="ca86e-140">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="ca86e-141">[Репликация слиянием](merge/merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="ca86e-141">[Merge Replication](merge/merge-replication.md) </span></span>  
 <span data-ttu-id="ca86e-142">[Одноранговая репликация транзакций](transactional/peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="ca86e-142">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span></span>  
 [<span data-ttu-id="ca86e-143">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="ca86e-143">Updatable Subscriptions for Transactional Replication</span></span>](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
