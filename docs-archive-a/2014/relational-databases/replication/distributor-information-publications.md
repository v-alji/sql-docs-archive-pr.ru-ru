---
title: Диалоговое окно "сведения о распространителе" Репликация SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.Distributor.Publications.f1
- sql12.rep.monitor.Distributor.commonjobs..f1
- sql12.rep.monitor.Distributor.SubscriptionSummary.merge.f1
- sql12.rep.monitor.Distributor.SubscriptionSummary.snapshot.f1
- sql12.rep.monitor.Distributor.SubscriptionSummary.tran.f1
ms.assetid: 1f499277-7f12-42ba-8cf4-52b683434944
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8ca0717a63c9660c225ec238e1e4d2423f7d01ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655635"
---
# <a name="distributor-information-dialog-box"></a><span data-ttu-id="a5975-102">Диалоговое окно "сведения о распространителе"</span><span class="sxs-lookup"><span data-stu-id="a5975-102">Distributor Information Dialog Box</span></span> 
<span data-ttu-id="a5975-103">В этом разделе содержатся сведения о диалоговом окне **распространителя** .</span><span class="sxs-lookup"><span data-stu-id="a5975-103">This topic provides information on the **Distributor** dialog box</span></span> 

## <a name="publications"></a><span data-ttu-id="a5975-104">Публикации</span><span class="sxs-lookup"><span data-stu-id="a5975-104">Publications</span></span>

  <span data-ttu-id="a5975-105">Вкладка **Публикации** содержит сводные данные по всем публикациям на распространителе, выбранном в левой панели.</span><span class="sxs-lookup"><span data-stu-id="a5975-105">The **Publications** tab provides summary information for all publications at the Distributor that is selected in the left pane.</span></span>  
  
### <a name="options"></a><span data-ttu-id="a5975-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="a5975-106">Options</span></span>  
 <span data-ttu-id="a5975-107">Сведения о публикациях, поддерживаемых распространителем, включают столбец, содержащий экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] издателя.</span><span class="sxs-lookup"><span data-stu-id="a5975-107">The information that is displayed about the publications supported by the Distributor includes a column that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance of the Publisher.</span></span> <span data-ttu-id="a5975-108">В остальном сведения о публикации совпадают со сведениями о публикации при просмотре в представлении «Издатель» в мониторе репликации.</span><span class="sxs-lookup"><span data-stu-id="a5975-108">Otherwise, the publication information is the same as the publication information that is provided when you view publications in the Publisher view of Replication Monitor.</span></span> <span data-ttu-id="a5975-109">Дополнительные сведения о столбцах на вкладке **Публикации** см. в разделе [Publisher Information, Publications](publisher-information-publications.md).</span><span class="sxs-lookup"><span data-stu-id="a5975-109">For more information about the columns in the **Publications** tab, see [Publisher Information, Publications](publisher-information-publications.md).</span></span>  

## <a name="subscription-watch-list"></a><span data-ttu-id="a5975-110">Список отслеживания подписок</span><span class="sxs-lookup"><span data-stu-id="a5975-110">Subscription watch list</span></span>

### <a name="transactional-replication"></a><span data-ttu-id="a5975-111">Репликация транзакций</span><span class="sxs-lookup"><span data-stu-id="a5975-111">Transactional replication</span></span> 
  <span data-ttu-id="a5975-112">Сведения для подписок на публикации транзакций содержат имя издателя.</span><span class="sxs-lookup"><span data-stu-id="a5975-112">Information for transactional subscriptions includes the name of the Publisher.</span></span> <span data-ttu-id="a5975-113">В остальном функциональные возможности и сведения в этом диалоговом окне такие же, как в представлении Publisher.</span><span class="sxs-lookup"><span data-stu-id="a5975-113">Otherwise, the functionality and the information that is provided in this dialog box is the same as in the Publisher view.</span></span> <span data-ttu-id="a5975-114">Дополнительные сведения о том, как использовать это диалоговое окно, см. в статье [Сведения об издателе, список просмотра подписок (публикация транзакций в SQL Server 2005 и более поздних версиях)](publisher-information-subscription-watch-list-transactional.md).</span><span class="sxs-lookup"><span data-stu-id="a5975-114">For more information about how to use this dialog box, see [Publisher Information, Subscription Watch List &#40;Transactional Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-transactional.md).</span></span>  

### <a name="merge-replication"></a><span data-ttu-id="a5975-115">Репликация слиянием</span><span class="sxs-lookup"><span data-stu-id="a5975-115">Merge replication</span></span>
  <span data-ttu-id="a5975-116">Сведения для подписок на публикации слиянием содержат имя издателя.</span><span class="sxs-lookup"><span data-stu-id="a5975-116">Information for merge publication subscriptions includes the name of the Publisher.</span></span> <span data-ttu-id="a5975-117">В остальном функциональные возможности и сведения в этом диалоговом окне такие же, как в представлении Publisher.</span><span class="sxs-lookup"><span data-stu-id="a5975-117">Otherwise, the functionality and the information that is provided in this dialog box is the same as in the Publisher view.</span></span> <span data-ttu-id="a5975-118">Дополнительные сведения о том, как использовать это диалоговое окно, вы найдете в статье [Сведения об издателе, список просмотра подписок (публикация слиянием в SQL Server 2005 и более поздних версиях)](publisher-information-subscription-watch-list-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="a5975-118">For more information about how to use this dialog box, see [Publisher Information, Subscription Watch List &#40;Merge Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-merge-publication.md).</span></span> 

### <a name="snapshot-replication"></a><span data-ttu-id="a5975-119">репликация моментальных снимков;</span><span class="sxs-lookup"><span data-stu-id="a5975-119">Snapshot replication</span></span>
  <span data-ttu-id="a5975-120">Сведения для подписок на публикации моментальными снимками содержат имя издателя.</span><span class="sxs-lookup"><span data-stu-id="a5975-120">Information for snapshot publication subscriptions includes the name of the Publisher.</span></span> <span data-ttu-id="a5975-121">В остальном функциональные возможности и сведения в этом диалоговом окне такие же, как в представлении Publisher.</span><span class="sxs-lookup"><span data-stu-id="a5975-121">Otherwise, the functionality and the information that is provided in this dialog box is the same as in the Publisher view.</span></span> <span data-ttu-id="a5975-122">Дополнительные сведения о том, как использовать это диалоговое окно, см. в статье [Сведения об издателе, список просмотра подписок (публикация моментальных снимков в SQL Server 2005 и более поздних версиях)](publisher-information-subscription-watch-list-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="a5975-122">For more information about how to use this dialog box, see [Publisher Information, Subscription Watch List &#40;Snapshot Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-snapshot.md).</span></span>  

## <a name="agents"></a><span data-ttu-id="a5975-123">Агенты</span><span class="sxs-lookup"><span data-stu-id="a5975-123">Agents</span></span>
  <span data-ttu-id="a5975-124"> На вкладке **Агенты** приводятся сведения об агентах и заданиях обслуживания, связанных с издателем и подписчиком.</span><span class="sxs-lookup"><span data-stu-id="a5975-124">The **Agents** tab displays information about the agents and maintenance jobs that are associated with the Publisher and Subscriber.</span></span>  
  
 <span data-ttu-id="a5975-125">В списке агентов на вкладке **Агенты** и в представлении «Распространитель» для распространителя присутствуют все агенты, имеющиеся на вкладке **Агенты** для издателя.</span><span class="sxs-lookup"><span data-stu-id="a5975-125">The agents that are available in the **Agents** tab for a Distributor in Distributor view include all the agents that are available in the **Agents** tab for a Publisher.</span></span> <span data-ttu-id="a5975-126">Однако на вкладке **Агенты** в представлении «Распространитель» для распространителя указаны также агент распространителя и агент слияния.</span><span class="sxs-lookup"><span data-stu-id="a5975-126">However, the **Agents** tab for a Distributor in Distributor view also includes a Distributor Agent and a Merge Agent.</span></span>  
  
 <span data-ttu-id="a5975-127">Дополнительные сведения о заданиях обслуживания и об агентах моментальных снимков, чтения журнала и чтения очереди см. в разделе [Publisher Information, Agents](publisher-information-agents.md).</span><span class="sxs-lookup"><span data-stu-id="a5975-127">For more information about the Snapshot, Log Reader, and Queue Reader agents, and maintenance jobs, see [Publisher Information, Agents](publisher-information-agents.md).</span></span> <span data-ttu-id="a5975-128">Обратите внимание, что при просмотре сведений об агенте на вкладке **Агенты** для издателя, для агентов моментальных снимков и чтения журнала выводятся сведения о распространителе.</span><span class="sxs-lookup"><span data-stu-id="a5975-128">Notice that when you are viewing agent information on the **Agents** tab for a Distributor, Publisher information is present for the Snapshot and Log Reader agents.</span></span> <span data-ttu-id="a5975-129">Однако на вкладке **Агенты** в представлении «Распространитель» для распространителя можно также выбрать **Агент распространителя** и **Агент слияния**.</span><span class="sxs-lookup"><span data-stu-id="a5975-129">However, in the **Agents** tab for a Distributor in Distributor view, you can also select **Distributor Agent** and **Merge Agent**.</span></span>  
  
### <a name="options"></a><span data-ttu-id="a5975-130">Варианты</span><span class="sxs-lookup"><span data-stu-id="a5975-130">Options</span></span>  
 <span data-ttu-id="a5975-131">В следующих разделах описаны данные, которые отображаются на этой вкладке для агента распространителя и агента слияния.</span><span class="sxs-lookup"><span data-stu-id="a5975-131">The following sections describe the data that is displayed on this tab for the Distributor Agent and Merge Agent.</span></span>  
  
### <a name="distributor-agent"></a><span data-ttu-id="a5975-132">Агент распространителя</span><span class="sxs-lookup"><span data-stu-id="a5975-132">Distributor Agent</span></span>  
 <span data-ttu-id="a5975-133">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="a5975-133">**Status**</span></span>  
 <span data-ttu-id="a5975-134">Состояние агента.</span><span class="sxs-lookup"><span data-stu-id="a5975-134">The status of the agent.</span></span> <span data-ttu-id="a5975-135">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="a5975-135">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="a5975-136">Ошибка</span><span class="sxs-lookup"><span data-stu-id="a5975-136">Error</span></span>    
-   <span data-ttu-id="a5975-137">Повторить попытку</span><span class="sxs-lookup"><span data-stu-id="a5975-137">Retry</span></span>    
-   <span data-ttu-id="a5975-138">Запущен</span><span class="sxs-lookup"><span data-stu-id="a5975-138">Running</span></span>    
-   <span data-ttu-id="a5975-139">Не выполняется</span><span class="sxs-lookup"><span data-stu-id="a5975-139">Not Running</span></span>    
-   <span data-ttu-id="a5975-140">Запуск не выполнялся</span><span class="sxs-lookup"><span data-stu-id="a5975-140">Never started</span></span>  
  
 <span data-ttu-id="a5975-141">**Издатель**</span><span class="sxs-lookup"><span data-stu-id="a5975-141">**Publisher**</span></span>  
 <span data-ttu-id="a5975-142">Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] издателя.</span><span class="sxs-lookup"><span data-stu-id="a5975-142">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance of the Publisher.</span></span>  
  
 <span data-ttu-id="a5975-143">**Публикация**</span><span class="sxs-lookup"><span data-stu-id="a5975-143">**Publication**</span></span>  
 <span data-ttu-id="a5975-144">Имя публикации, с которой связан агент.</span><span class="sxs-lookup"><span data-stu-id="a5975-144">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="a5975-145">**Подписка**</span><span class="sxs-lookup"><span data-stu-id="a5975-145">**Subscription**</span></span>  
 <span data-ttu-id="a5975-146">Имя подписки, представленное в форме: [*SubscriberName*].[*Database*].</span><span class="sxs-lookup"><span data-stu-id="a5975-146">The name of the subscription, in the form: [*SubscriberName*].[*Database*].</span></span>  
  
 <span data-ttu-id="a5975-147">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a5975-147">**Type**</span></span>  
 <span data-ttu-id="a5975-148">Тип репликации: push (принудительная), pull (по запросу) или Anonymous (анонимная).</span><span class="sxs-lookup"><span data-stu-id="a5975-148">Type of replication: push, pull, or Anonymous.</span></span>  
  
 <span data-ttu-id="a5975-149">**Время последнего запуска**</span><span class="sxs-lookup"><span data-stu-id="a5975-149">**Last Start Time**</span></span>  
 <span data-ttu-id="a5975-150">Время последнего запуска агента.</span><span class="sxs-lookup"><span data-stu-id="a5975-150">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="a5975-151">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="a5975-151">**Duration**</span></span>  
 <span data-ttu-id="a5975-152">Продолжительность времени работы агента.</span><span class="sxs-lookup"><span data-stu-id="a5975-152">The length of time that the agent has run.</span></span> <span data-ttu-id="a5975-153">Это время представляет собой продолжительность выполнения агента, если он выполняется в настоящее время, и общее время выполнения, если агент запускался ранее.</span><span class="sxs-lookup"><span data-stu-id="a5975-153">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="a5975-154">**Последнее действие**</span><span class="sxs-lookup"><span data-stu-id="a5975-154">**Last Action**</span></span>  
 <span data-ttu-id="a5975-155">Последнее действие, которое было выполнено в течение последнего запуска агента.</span><span class="sxs-lookup"><span data-stu-id="a5975-155">The last action that was performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="a5975-156">**Скорость доставки**</span><span class="sxs-lookup"><span data-stu-id="a5975-156">**Delivery Rate**</span></span>  
 <span data-ttu-id="a5975-157">Скорость (команд в секунду), с которой команды инициализации фиксируются в базе данных распространителя во время последнего запуска агента.</span><span class="sxs-lookup"><span data-stu-id="a5975-157">The rate, in commands per second, at which initialization commands are committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="a5975-158">**Задержка**</span><span class="sxs-lookup"><span data-stu-id="a5975-158">**Latency**</span></span>  
 <span data-ttu-id="a5975-159">Время в секундах, прошедшее с момента фиксации последних изменений в базе данных публикации до фиксации соответствующих команд в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="a5975-159">The time, in seconds, that has elapsed between the most recent change being committed in the publication database, and the corresponding command being committed in the distribution database.</span></span>  
  
 <span data-ttu-id="a5975-160">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="a5975-160">**#Trans**</span></span>  
 <span data-ttu-id="a5975-161">Количество транзакций, зафиксированных в базе данных распространителя во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="a5975-161">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="a5975-162">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="a5975-162">**#Cmds**</span></span>  
 <span data-ttu-id="a5975-163">Количество команд, зафиксированных в базе данных распространителя во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="a5975-163">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="a5975-164">Команда является эквивалентом изменения данных, например обновления.</span><span class="sxs-lookup"><span data-stu-id="a5975-164">A command is the same as a data change, such as an update.</span></span>  
  
 <span data-ttu-id="a5975-165">**Ср. кол-во команд**</span><span class="sxs-lookup"><span data-stu-id="a5975-165">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="a5975-166">Среднее количество команд за транзакцию во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="a5975-166">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="merge-agent"></a><span data-ttu-id="a5975-167">Агент слияния.</span><span class="sxs-lookup"><span data-stu-id="a5975-167">Merge Agent</span></span>  
 <span data-ttu-id="a5975-168">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="a5975-168">**Status**</span></span>  
 <span data-ttu-id="a5975-169">Состояние агента.</span><span class="sxs-lookup"><span data-stu-id="a5975-169">The status of the agent.</span></span> <span data-ttu-id="a5975-170">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="a5975-170">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="a5975-171">Ошибка</span><span class="sxs-lookup"><span data-stu-id="a5975-171">Error</span></span>    
-   <span data-ttu-id="a5975-172">Повторить попытку</span><span class="sxs-lookup"><span data-stu-id="a5975-172">Retry</span></span>    
-   <span data-ttu-id="a5975-173">Запущен</span><span class="sxs-lookup"><span data-stu-id="a5975-173">Running</span></span>    
-   <span data-ttu-id="a5975-174">Не выполняется</span><span class="sxs-lookup"><span data-stu-id="a5975-174">Not Running</span></span>    
-   <span data-ttu-id="a5975-175">Запуск не выполнялся</span><span class="sxs-lookup"><span data-stu-id="a5975-175">Never started</span></span>  
  
 <span data-ttu-id="a5975-176">**Издатель**</span><span class="sxs-lookup"><span data-stu-id="a5975-176">**Publisher**</span></span>  
 <span data-ttu-id="a5975-177">Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] издателя.</span><span class="sxs-lookup"><span data-stu-id="a5975-177">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance of the Publisher.</span></span>  
  
 <span data-ttu-id="a5975-178">**Публикация**</span><span class="sxs-lookup"><span data-stu-id="a5975-178">**Publication**</span></span>  
 <span data-ttu-id="a5975-179">Имя публикации, с которой связан агент.</span><span class="sxs-lookup"><span data-stu-id="a5975-179">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="a5975-180">**Подписка**</span><span class="sxs-lookup"><span data-stu-id="a5975-180">**Subscription**</span></span>  
 <span data-ttu-id="a5975-181">Имя подписки, представленное в форме: [*SubscriberName*].[*Database*].</span><span class="sxs-lookup"><span data-stu-id="a5975-181">The name of the subscription, in the form: [*SubscriberName*].[*Database*].</span></span>  
  
 <span data-ttu-id="a5975-182">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a5975-182">**Type**</span></span>  
 <span data-ttu-id="a5975-183">Тип репликации: push (принудительная), pull (по запросу) или Anonymous (анонимная).</span><span class="sxs-lookup"><span data-stu-id="a5975-183">Type of replication: push, pull, or Anonymous.</span></span>  
  
 <span data-ttu-id="a5975-184">**Время последнего запуска**</span><span class="sxs-lookup"><span data-stu-id="a5975-184">**Last Start Time**</span></span>  
 <span data-ttu-id="a5975-185">Время последнего запуска агента.</span><span class="sxs-lookup"><span data-stu-id="a5975-185">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="a5975-186">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="a5975-186">**Duration**</span></span>  
 <span data-ttu-id="a5975-187">Продолжительность времени работы агента.</span><span class="sxs-lookup"><span data-stu-id="a5975-187">The length of time that the agent has run.</span></span> <span data-ttu-id="a5975-188">Это время представляет собой продолжительность выполнения агента, если он выполняется в настоящее время, и общее время выполнения, если агент запускался ранее.</span><span class="sxs-lookup"><span data-stu-id="a5975-188">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="a5975-189">**Последнее действие**</span><span class="sxs-lookup"><span data-stu-id="a5975-189">**Last Action**</span></span>  
 <span data-ttu-id="a5975-190">Последнее действие, которое было выполнено в течение последнего запуска агента.</span><span class="sxs-lookup"><span data-stu-id="a5975-190">The last action that was performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="a5975-191">**Скорость доставки**</span><span class="sxs-lookup"><span data-stu-id="a5975-191">**Delivery Rate**</span></span>  
 <span data-ttu-id="a5975-192">Показатель (команд в секунду), с которым изменения фиксируются в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="a5975-192">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="a5975-193">**Вставки издателя**</span><span class="sxs-lookup"><span data-stu-id="a5975-193">**Publisher Inserts**</span></span>  
 <span data-ttu-id="a5975-194">Количество команд INSERT, примененных на издателе.</span><span class="sxs-lookup"><span data-stu-id="a5975-194">Number of INSERT commands applied at the Publisher.</span></span>  
  
 <span data-ttu-id="a5975-195">**Обновления издателя**</span><span class="sxs-lookup"><span data-stu-id="a5975-195">**Publisher Updates**</span></span>  
 <span data-ttu-id="a5975-196">Количество команд UPDATE, примененных на издателе.</span><span class="sxs-lookup"><span data-stu-id="a5975-196">Number of UPDATE commands applied at the Publisher.</span></span>  
  
 <span data-ttu-id="a5975-197">**Удаления издателя**</span><span class="sxs-lookup"><span data-stu-id="a5975-197">**Publisher Deletes**</span></span>  
 <span data-ttu-id="a5975-198">Количество команд DELETE, примененных на издателе.</span><span class="sxs-lookup"><span data-stu-id="a5975-198">Number of DELETE commands applied at the Publisher.</span></span>  
  
 <span data-ttu-id="a5975-199">**Конфликты издателя**</span><span class="sxs-lookup"><span data-stu-id="a5975-199">**Publisher Conflicts**</span></span>  
 <span data-ttu-id="a5975-200">Число конфликтов, произошедших на издателе в течение процесса слияния.</span><span class="sxs-lookup"><span data-stu-id="a5975-200">The number of conflicts occurring at the Publisher during the merge process.</span></span>  
  
 <span data-ttu-id="a5975-201">**Вставки подписчика**</span><span class="sxs-lookup"><span data-stu-id="a5975-201">**Subscriber Inserts**</span></span>  
 <span data-ttu-id="a5975-202">Количество команд INSERT, примененных на подписчике.</span><span class="sxs-lookup"><span data-stu-id="a5975-202">Number of INSERT commands applied at the Subscriber.</span></span>  
  
 <span data-ttu-id="a5975-203">**Обновления подписчика**</span><span class="sxs-lookup"><span data-stu-id="a5975-203">**Subscriber Updates**</span></span>  
 <span data-ttu-id="a5975-204">Количество команд UPDATE, примененных на подписчике.</span><span class="sxs-lookup"><span data-stu-id="a5975-204">Number of UPDATE commands applied at the Subscriber.</span></span>  
  
 <span data-ttu-id="a5975-205">**Удаления подписчика**</span><span class="sxs-lookup"><span data-stu-id="a5975-205">**Subscriber Deletes**</span></span>  
 <span data-ttu-id="a5975-206">Количество команд DELETE, примененных на подписчике.</span><span class="sxs-lookup"><span data-stu-id="a5975-206">Number of DELETE commands applied at the Subscriber.</span></span>  
  
 <span data-ttu-id="a5975-207">**Конфликты подписчика**</span><span class="sxs-lookup"><span data-stu-id="a5975-207">**Subscriber Conflicts**</span></span>  
 <span data-ttu-id="a5975-208">Число конфликтов, произошедших на подписчике в течение процесса слияния.</span><span class="sxs-lookup"><span data-stu-id="a5975-208">The number of conflicts occurring at the Subscriber during the merge process.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="a5975-209">См. также:</span><span class="sxs-lookup"><span data-stu-id="a5975-209">See Also</span></span>  
 <span data-ttu-id="a5975-210">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="a5975-210">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="a5975-211">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="a5975-211">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
