---
title: MSSQL_REPL027183 | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL027183 error
ms.assetid: 52c271ac-1a0e-43d5-85d4-35886d1efd32
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4484318cd6ec6ff4f0b201be69dc9b7544dd2c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750692"
---
# <a name="mssql_repl027183"></a><span data-ttu-id="75d2a-102">MSSQL_REPL027183</span><span class="sxs-lookup"><span data-stu-id="75d2a-102">MSSQL_REPL027183</span></span>
    
## <a name="message-details"></a><span data-ttu-id="75d2a-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="75d2a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75d2a-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="75d2a-104">Product Name</span></span>|<span data-ttu-id="75d2a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="75d2a-105">SQL Server</span></span>|  
|<span data-ttu-id="75d2a-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="75d2a-106">Event ID</span></span>|<span data-ttu-id="75d2a-107">27183</span><span class="sxs-lookup"><span data-stu-id="75d2a-107">27183</span></span>|  
|<span data-ttu-id="75d2a-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="75d2a-108">Event Source</span></span>|<span data-ttu-id="75d2a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="75d2a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="75d2a-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="75d2a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="75d2a-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="75d2a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="75d2a-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="75d2a-112">Message Text</span></span>|<span data-ttu-id="75d2a-113">Процессу слияния не удалось перечислить изменения в статьях с параметризованными фильтрами строк.</span><span class="sxs-lookup"><span data-stu-id="75d2a-113">The merge process failed to enumerate changes in articles with parameterized row filters.</span></span> <span data-ttu-id="75d2a-114">Если эта ошибка продолжает возникать, увеличьте тайм-аут запроса для этого процесса, уменьшите срок хранения публикации и оптимизируйте индексы по опубликованным таблицам.</span><span class="sxs-lookup"><span data-stu-id="75d2a-114">If this failure continues, increase the query timeout for this process, reduce the retention period for the publication, and improve indexes on published tables.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="75d2a-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="75d2a-115">Explanation</span></span>  
 <span data-ttu-id="75d2a-116">Эта ошибка появляется, если возникает тайм-аут агента слияния во время обработки изменений в фильтруемой публикации.</span><span class="sxs-lookup"><span data-stu-id="75d2a-116">This error is raised if a Merge Agent timeout occurs while processing changes in a filtered publication.</span></span> <span data-ttu-id="75d2a-117">Тайм-аут может быть вызван одной из следующих причин:</span><span class="sxs-lookup"><span data-stu-id="75d2a-117">The timeout might be caused by one of the following issues:</span></span>  
  
-   <span data-ttu-id="75d2a-118">Не используется оптимизация предварительно вычисляемых секций.</span><span class="sxs-lookup"><span data-stu-id="75d2a-118">Not using the precomputed partitions optimization.</span></span>  
  
-   <span data-ttu-id="75d2a-119">Для фильтрации используется фрагментация индекса столбцов.</span><span class="sxs-lookup"><span data-stu-id="75d2a-119">Index fragmentation on columns used for filtering.</span></span>  
  
-   <span data-ttu-id="75d2a-120">Большие объединенные таблицы метаданных, например **MSmerge_tombstone**, **MSmerge_contents**и **MSmerge_genhistory**.</span><span class="sxs-lookup"><span data-stu-id="75d2a-120">Large merge metadata tables, such as **MSmerge_tombstone**, **MSmerge_contents**, and **MSmerge_genhistory**.</span></span>  
  
-   <span data-ttu-id="75d2a-121">Фильтруемые таблицы, не соединенные уникальным ключом, и фильтры соединения, использующие большое количество таблиц.</span><span class="sxs-lookup"><span data-stu-id="75d2a-121">Filtered tables that are not joined on a unique key and join filters that involve a large number of tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="75d2a-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="75d2a-122">User Action</span></span>  
 <span data-ttu-id="75d2a-123">Чтобы устранить проблему:</span><span class="sxs-lookup"><span data-stu-id="75d2a-123">To resolve the issue:</span></span>  
  
-   <span data-ttu-id="75d2a-124">Увеличьте для агента слияния значение параметра **-QueryTimeOut** , чтобы разрешить продолжение обработки, пока будут устраняться основные причины, вызывающие эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="75d2a-124">Increase the value of the **-QueryTimeOut** parameter for the Merge Agent to allow processing to continue while you address the underlying issues causing the error.</span></span> <span data-ttu-id="75d2a-125">Параметры агента могут задаваться в профилях агента или в командной строке.</span><span class="sxs-lookup"><span data-stu-id="75d2a-125">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="75d2a-126">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="75d2a-126">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="75d2a-127">Работа с профилями агента репликации</span><span class="sxs-lookup"><span data-stu-id="75d2a-127">Work with Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="75d2a-128">Просмотр и изменение параметров командной строки агента репликации (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="75d2a-128">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   <span data-ttu-id="75d2a-129">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="75d2a-129">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="75d2a-130">По возможности используйте оптимизацию предварительно вычисляемых секций.</span><span class="sxs-lookup"><span data-stu-id="75d2a-130">Use the precomputed partitions optimization if possible.</span></span> <span data-ttu-id="75d2a-131">Эта оптимизация используется по умолчанию в случае выполнения ряда требований к публикации.</span><span class="sxs-lookup"><span data-stu-id="75d2a-131">This optimization is used by default if a number of publication requirements are met.</span></span> <span data-ttu-id="75d2a-132">Дополнительные сведения об этих требованиях см. в статье [Оптимизация производительности параметризованного фильтра с помощью предварительно вычисляемых секций](merge/parameterized-filters-optimize-for-precomputed-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="75d2a-132">For more information about these requirements, see [Optimize Parameterized Filter Performance with Precomputed Partitions](merge/parameterized-filters-optimize-for-precomputed-partitions.md).</span></span> <span data-ttu-id="75d2a-133">Если публикация не отвечает этим требованиям, рассмотрите возможность повторной разработки публикации.</span><span class="sxs-lookup"><span data-stu-id="75d2a-133">If the publication does not meet these requirements, consider redesigning the publication.</span></span>  
  
-   <span data-ttu-id="75d2a-134">Укажите наименьшее возможное значение срока хранения данной публикации, потому что репликация не может выполнять очистку метаданных в базах данных публикации и подписок, пока не истечет срок хранения.</span><span class="sxs-lookup"><span data-stu-id="75d2a-134">Specify the lowest setting possible for the publication retention period, because replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="75d2a-135">Дополнительные сведения см. в разделе [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="75d2a-135">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
-   <span data-ttu-id="75d2a-136">Обслуживая репликацию слиянием, иногда проверяйте увеличение размера системных таблиц, связанных с репликацией слиянием: **MSmerge_contents**, **MSmerge_genhistory**, **MSmerge_tombstone**, **MSmerge_current_partition_mappings**и **MSmerge_past_partition_mappings**.</span><span class="sxs-lookup"><span data-stu-id="75d2a-136">As part of maintenance for merge replication, occasionally check the growth of the system tables associated with merge replication: **MSmerge_contents**, **MSmerge_genhistory**, and **MSmerge_tombstone**, **MSmerge_current_partition_mappings**, and **MSmerge_past_partition_mappings**.</span></span> <span data-ttu-id="75d2a-137">Время от времени проводите повторную индексацию этих таблиц.</span><span class="sxs-lookup"><span data-stu-id="75d2a-137">Periodically re-index these tables.</span></span> <span data-ttu-id="75d2a-138">Дополнительные сведения см. в статье [Реорганизация и перестроение индексов](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="75d2a-138">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="75d2a-139">Убедитесь в том, что столбцы, используемые для фильтрации, надлежащим образом проиндексированы, и при необходимости перестройте такие индексы заново.</span><span class="sxs-lookup"><span data-stu-id="75d2a-139">Ensure that columns used for filtering are properly indexed and rebuild such indexes if necessary.</span></span> <span data-ttu-id="75d2a-140">Дополнительные сведения см. в статье [Реорганизация и перестроение индексов](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="75d2a-140">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="75d2a-141">Для фильтров соединения, основанных на уникальных столбцах, задайте свойство **join_unique_key** .</span><span class="sxs-lookup"><span data-stu-id="75d2a-141">Set the **join_unique_key** property for join filters that are based on unique columns.</span></span> <span data-ttu-id="75d2a-142">Дополнительные сведения см. в статье [Join Filters](merge/join-filters.md).</span><span class="sxs-lookup"><span data-stu-id="75d2a-142">For more information, see [Join Filters](merge/join-filters.md).</span></span>  
  
-   <span data-ttu-id="75d2a-143">Ограничьте число таблиц, входящих в иерархию фильтра соединения.</span><span class="sxs-lookup"><span data-stu-id="75d2a-143">Limit the number of tables in the join filter hierarchy.</span></span> <span data-ttu-id="75d2a-144">При создании фильтров соединения из пяти и более таблиц рассмотрите другие решения: не фильтруйте маленькие таблицы, таблицы, которые не изменяются или служат в основном таблицами подстановки.</span><span class="sxs-lookup"><span data-stu-id="75d2a-144">If you are generating join filters of five or more tables, consider other solutions: do not filter tables that are small, not subject to change, or are primarily lookup tables.</span></span> <span data-ttu-id="75d2a-145">Используйте фильтры соединения только между теми таблицами, которые должны быть секционированы среди подписок.</span><span class="sxs-lookup"><span data-stu-id="75d2a-145">Use join filters only between tables that must be partitioned among subscriptions.</span></span>  
  
-   <span data-ttu-id="75d2a-146">Уменьшите количество изменений в фильтруемых таблицах между синхронизациями или чаще запускайте агент слияния.</span><span class="sxs-lookup"><span data-stu-id="75d2a-146">Make a smaller number of changes on filtered tables between synchronizations, or run the Merge Agent more frequently.</span></span> <span data-ttu-id="75d2a-147">Дополнительные сведения о настройке расписаний синхронизации см. в разделе [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="75d2a-147">For more information about setting synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d2a-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="75d2a-148">See Also</span></span>  
 [<span data-ttu-id="75d2a-149">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="75d2a-149">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
