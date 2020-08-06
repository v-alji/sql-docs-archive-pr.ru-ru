---
title: MSSQL_ENG002601 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG002601 error
ms.assetid: 657c3ae6-9e4b-4c60-becc-4caf7435c1dc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c2e8340fef83749fd6d041af42566b10ed3542c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749731"
---
# <a name="mssql_eng002601"></a><span data-ttu-id="57909-102">MSSQL_ENG002601</span><span class="sxs-lookup"><span data-stu-id="57909-102">MSSQL_ENG002601</span></span>
    
## <a name="message-details"></a><span data-ttu-id="57909-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="57909-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57909-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="57909-104">Product Name</span></span>|<span data-ttu-id="57909-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="57909-105">SQL Server</span></span>|  
|<span data-ttu-id="57909-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="57909-106">Event ID</span></span>|<span data-ttu-id="57909-107">2601</span><span class="sxs-lookup"><span data-stu-id="57909-107">2601</span></span>|  
|<span data-ttu-id="57909-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="57909-108">Event Source</span></span>|<span data-ttu-id="57909-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="57909-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="57909-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="57909-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="57909-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="57909-111">Symbolic Name</span></span>|<span data-ttu-id="57909-112">Недоступно</span><span class="sxs-lookup"><span data-stu-id="57909-112">N/A</span></span>|  
|<span data-ttu-id="57909-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="57909-113">Message Text</span></span>|<span data-ttu-id="57909-114">Не удается вставить повторяющуюся строку ключа в объект '%.\*ls' с уникальным индексом '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="57909-114">Cannot insert duplicate key row in object '%.\*ls' with unique index '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="57909-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="57909-115">Explanation</span></span>  
 <span data-ttu-id="57909-116">Это общая ошибка, которая может возникнуть независимо от того, реплицируется база данных или нет.</span><span class="sxs-lookup"><span data-stu-id="57909-116">This is a general error that can be raised regardless of whether a database is replicated.</span></span> <span data-ttu-id="57909-117">В реплицируемых базах данных эта ошибка возникает, как правило, по причине неправильного управления первичными ключами в топологии.</span><span class="sxs-lookup"><span data-stu-id="57909-117">In replicated databases, the error is typically raised because primary keys have not been managed appropriately across the topology.</span></span> <span data-ttu-id="57909-118">В распределенной среде необходимо убедиться в том, что одно и то же значение не вставлено в первичный ключевой столбец или в любой другой уникальный столбец на нескольких узлах.</span><span class="sxs-lookup"><span data-stu-id="57909-118">In a distributed environment it is essential to ensure that the same value is not inserted into a primary key column or any other unique column at more than one node.</span></span> <span data-ttu-id="57909-119">Возможные причины ошибки:</span><span class="sxs-lookup"><span data-stu-id="57909-119">Possible causes include the following:</span></span>  
  
-   <span data-ttu-id="57909-120">Вставки или обновления строки выполняются более чем в одном узле.</span><span class="sxs-lookup"><span data-stu-id="57909-120">Inserts and updates to a row are occurring at more than one node.</span></span> <span data-ttu-id="57909-121">И репликация слиянием, и обновляемые подписки для репликации транзакций обеспечивают обнаружение и разрешение конфликта, однако по-прежнему рекомендуется вставлять или обновлять строку только в одном узле.</span><span class="sxs-lookup"><span data-stu-id="57909-121">Merge replication and updatable subscriptions for transactional replication both provide conflict detection and resolution, but it is still preferable to insert or update a given row at only one node.</span></span> <span data-ttu-id="57909-122">Одноранговые транзакции не обеспечивают обнаружение и разрешение конфликтов. Требуется, чтобы операции вставки и обновления были секционированы.</span><span class="sxs-lookup"><span data-stu-id="57909-122">Peer-to-peer transactional does not provide conflict detection and resolution; it requires that inserts and updates be partitioned.</span></span>  
  
-   <span data-ttu-id="57909-123">Строка была вставлена на подписчике, который должен быть доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="57909-123">A row was inserted at a Subscriber that should be read-only.</span></span> <span data-ttu-id="57909-124">Подписчики на публикации моментальных снимков должны быть доступны только для чтения, так же как и подписчики на публикации транзакций, если только не используются обновляемые подписки или одноранговые репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="57909-124">Subscribers to snapshot publications should be treated as read-only, as should Subscribers to transactional publications unless updatable subscriptions or peer-to-peer transactional replication is used.</span></span>  
  
-   <span data-ttu-id="57909-125">Используется таблица со столбцом идентификаторов, однако управление столбцом осуществляется неверно.</span><span class="sxs-lookup"><span data-stu-id="57909-125">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
-   <span data-ttu-id="57909-126">В публикации слиянием эта ошибка также может возникнуть во время вставки в системную таблицу **MSmerge_contents**. Возникающая ошибка подобна следующей: Не удается вставить повторяющуюся строку ключа в объект MSmerge_contents с уникальным индексом ucl1SycContents.</span><span class="sxs-lookup"><span data-stu-id="57909-126">In merge replication, this error can also occur during an insert into the system table **MSmerge_contents**; the error raised is similar to: Cannot insert duplicate key row in object 'MSmerge_contents' with unique index 'ucl1SycContents.'</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="57909-127">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="57909-127">User Action</span></span>  
 <span data-ttu-id="57909-128">Действие по устранению проблемы зависит от причины, по которой она возникла:</span><span class="sxs-lookup"><span data-stu-id="57909-128">The action required depends on the reason the error was raised:</span></span>  
  
-   <span data-ttu-id="57909-129">Вставки или обновления строки выполняются более чем в одном узле.</span><span class="sxs-lookup"><span data-stu-id="57909-129">Inserts and updates to a row are occurring at more than one node.</span></span>  
  
     <span data-ttu-id="57909-130">Независимо от типа используемой репликации рекомендуется секционировать вставки и обновления везде, где это возможно, так как это уменьшит обработку данных, необходимую для обнаружения и разрешения конфликта.</span><span class="sxs-lookup"><span data-stu-id="57909-130">Regardless of the type of replication used, we recommend that you partition inserts and updates whenever possible, because this reduces the processing required for conflict detection and resolution.</span></span> <span data-ttu-id="57909-131">Секционирование вставок и обновлений является необходимым условием при использовании одноранговой репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="57909-131">For peer-to-peer transactional replication, partitioning inserts and updates is required.</span></span> <span data-ttu-id="57909-132">Дополнительные сведения см. в разделе [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="57909-132">For more information, see [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="57909-133">Строка была вставлена на подписчике, который должен быть доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="57909-133">A row was inserted at a Subscriber that should be read-only.</span></span>  
  
     <span data-ttu-id="57909-134">Не выполняйте вставку или обновление строк на подписчике, если не используется репликация слиянием, репликация транзакций с обновляемыми подписками или одноранговая репликация транзакций.</span><span class="sxs-lookup"><span data-stu-id="57909-134">Do not insert or update rows at the Subscriber unless you are using merge replication, transactional replication with updatable subscriptions, or peer-to-peer transactional replication.</span></span>  
  
-   <span data-ttu-id="57909-135">Используется таблица со столбцом идентификаторов, однако управление столбцом осуществляется неверно.</span><span class="sxs-lookup"><span data-stu-id="57909-135">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
     <span data-ttu-id="57909-136">При использовании репликации слиянием или репликации с обновляемыми подписками столбцы идентификаторов должны автоматически управляться репликацией.</span><span class="sxs-lookup"><span data-stu-id="57909-136">For merge replication and transactional replication with updatable subscriptions, identity columns should be managed automatically by replication.</span></span> <span data-ttu-id="57909-137">При использовании одноранговой репликации транзакций управление этими столбцами должно выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="57909-137">For peer-to-peer transactional replication, they must be managed manually.</span></span> <span data-ttu-id="57909-138">Дополнительные сведения см. в статье [Репликация столбцов идентификаторов](publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="57909-138">For more information, see [Replicate Identity Columns](publish/replicate-identity-columns.md).</span></span>  
  
-   <span data-ttu-id="57909-139">Ошибка возникает во время вставки в системную таблицу **MSmerge_contents**.</span><span class="sxs-lookup"><span data-stu-id="57909-139">The error occurs during an insert into the system table **MSmerge_contents**.</span></span>  
  
     <span data-ttu-id="57909-140">Эта ошибка может возникнуть вследствие неверного значения свойства **join_unique_key**фильтра соединения.</span><span class="sxs-lookup"><span data-stu-id="57909-140">This error can occur because of an incorrect value for the join filter property **join_unique_key**.</span></span> <span data-ttu-id="57909-141">Это свойство должно быть установлено равным TRUE, только если соединенный столбец в родительской таблице является уникальным.</span><span class="sxs-lookup"><span data-stu-id="57909-141">This property should be set to TRUE only if the joined column in the parent table is unique.</span></span> <span data-ttu-id="57909-142">Если это свойство установлено равным TRUE, но столбец не является уникальным, возникает эта ошибка.</span><span class="sxs-lookup"><span data-stu-id="57909-142">If the property is set to TRUE, but the column is not unique, this error is raised.</span></span> <span data-ttu-id="57909-143">Дополнительные сведения об установке данного свойства см. в разделе [Определение и изменение фильтра соединения между статьями публикации слиянием](publish/define-and-modify-a-join-filter-between-merge-articles.md).</span><span class="sxs-lookup"><span data-stu-id="57909-143">For more information on setting this property, see [Define and Modify a Join Filter Between Merge Articles](publish/define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57909-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="57909-144">See Also</span></span>  
 [<span data-ttu-id="57909-145">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="57909-145">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
