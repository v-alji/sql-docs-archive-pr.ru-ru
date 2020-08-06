---
title: Обзор интерфейса монитора репликации | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor
- Replication Monitor, about Replication Monitor
ms.assetid: 078f0e34-7153-45c4-8725-778b5bef88da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d9b7edbd76153f23168ec9bcf4a286d5f7cbe9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657646"
---
# <a name="overview-of-the-replication-monitor-interface"></a><span data-ttu-id="34f9d-102">Обзор интерфейса монитора репликации</span><span class="sxs-lookup"><span data-stu-id="34f9d-102">Overview of the Replication Monitor Interface</span></span>
  <span data-ttu-id="34f9d-103">Монитор репликации [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] обеспечивает представление всех операций репликации в окне, состоящем из двух панелей, со стороны издателя и со стороны распространителя.</span><span class="sxs-lookup"><span data-stu-id="34f9d-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor presents a Publisher-focused view or Distributor-focused view of all replication activity in a two pane format.</span></span> <span data-ttu-id="34f9d-104">При добавлении издателя в монитор на левую панель, на правой панели монитора отображается информация об этом издателе, его публикациях, подписках на эти публикации и различных агентах репликации.</span><span class="sxs-lookup"><span data-stu-id="34f9d-104">You add a Publisher to the monitor in the left pane, and in the right pane the monitor displays information on the Publisher, its publications, the subscriptions to those publications, and the various replication agents.</span></span> <span data-ttu-id="34f9d-105">Помимо представления информации о топологии репликации, монитор репликации позволяет выполнять некоторые задачи, например пуск и остановку агентов, а также проверку данных.</span><span class="sxs-lookup"><span data-stu-id="34f9d-105">In addition to presenting information for the replication topology, Replication Monitor allows you to perform a number of tasks, such as starting and stopping agents, and validating data.</span></span>  
  
## <a name="viewing-information-for-the-entire-topology"></a><span data-ttu-id="34f9d-106">Просмотр информации обо всей топологии</span><span class="sxs-lookup"><span data-stu-id="34f9d-106">Viewing Information for the Entire Topology</span></span>  
 <span data-ttu-id="34f9d-107">На левой панели монитора репликации отображаются:</span><span class="sxs-lookup"><span data-stu-id="34f9d-107">The left pane of Replication Monitor displays</span></span>  
  
-   <span data-ttu-id="34f9d-108">группы издателей, издатели и публикации;</span><span class="sxs-lookup"><span data-stu-id="34f9d-108">Publisher groups, Publishers, and publications.</span></span>  
  
-   <span data-ttu-id="34f9d-109">распространители, издатели и публикации.</span><span class="sxs-lookup"><span data-stu-id="34f9d-109">Distributors, Publishers, and publications.</span></span>  
  
 <span data-ttu-id="34f9d-110">Для просмотра какой-либо информации в мониторе репликации необходимо добавить издатель.</span><span class="sxs-lookup"><span data-stu-id="34f9d-110">To view any information in Replication Monitor, you must first add a Publisher.</span></span> <span data-ttu-id="34f9d-111">Дополнительные сведения см. в статье [Добавление и удаление издателей в мониторе репликации](add-and-remove-publishers-from-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="34f9d-111">For more information, see [Add and Remove Publishers from Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="34f9d-112">Левая панель окна предназначена для ответа на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="34f9d-112">The left pane helps answer the following questions:</span></span>  
  
-   <span data-ttu-id="34f9d-113">Исправна ли система репликации?</span><span class="sxs-lookup"><span data-stu-id="34f9d-113">Is my replication system healthy?</span></span>  
  
     <span data-ttu-id="34f9d-114">Система репликации достаточно работоспособна при отсутствии значков ошибок на узлах в левой панели окна.</span><span class="sxs-lookup"><span data-stu-id="34f9d-114">The replication system is relatively healthy if there are no error icons on nodes in the left pane.</span></span> <span data-ttu-id="34f9d-115">Для получения более полного представления о исправности системы необходимо также проверить вкладку **Список наблюдения за подписками** , отображающую сведения о подписках, на которые следует обратить внимание.</span><span class="sxs-lookup"><span data-stu-id="34f9d-115">To get a more complete view of system health, you should also check the **Subscription Watch List** tab, which displays information on subscriptions that might require attention.</span></span>  
  
-   <span data-ttu-id="34f9d-116">Почему агент не запущен?</span><span class="sxs-lookup"><span data-stu-id="34f9d-116">Why is an agent not running?</span></span>  
  
     <span data-ttu-id="34f9d-117">Агент не запускается в определенное время либо потому что в расписании не задан его запуск в это время, либо вследствие возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="34f9d-117">An agent is not running at a particular time either because it is not scheduled to run or because an error has occurred.</span></span> <span data-ttu-id="34f9d-118">При возникновении ошибки на соответствующих узлах в левой панели окна отображаются значки ошибок.</span><span class="sxs-lookup"><span data-stu-id="34f9d-118">If an error has occurred, an error icon is displayed on the appropriate nodes in the left pane.</span></span> <span data-ttu-id="34f9d-119">Например, если агент моментальных снимков для публикации остановлен вследствие ошибки, то значок ошибки отображается на узлах группы издателей, издателя и публикации.</span><span class="sxs-lookup"><span data-stu-id="34f9d-119">For example, if the Snapshot Agent for a publication stopped because of an error, an error icon is displayed on the Publisher group, Publisher, and publication nodes.</span></span> <span data-ttu-id="34f9d-120">Сводная информация об агенте моментальных снимков отображается на вкладке **Агенты** публикации. Для просмотра подробных сведений об ошибке дважды щелкните агент моментальных снимков на этой вкладке.</span><span class="sxs-lookup"><span data-stu-id="34f9d-120">Summary information for the Snapshot Agent is displayed on the **Agents** tab for the publication; double click the Snapshot Agent on this tab for detailed error information.</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-distributors"></a><span data-ttu-id="34f9d-121">Просмотр сведений и выполнение задач, относящихся к распространителям</span><span class="sxs-lookup"><span data-stu-id="34f9d-121">Viewing Information and Performing Tasks Related to Distributors</span></span>  
 <span data-ttu-id="34f9d-122">Монитор репликации отображает информацию о распространителях на трех вкладках:</span><span class="sxs-lookup"><span data-stu-id="34f9d-122">Replication Monitor displays information about Distributors on three tabs:</span></span>  
  
-   <span data-ttu-id="34f9d-123">Вкладка**Публикации**</span><span class="sxs-lookup"><span data-stu-id="34f9d-123">**Publications** tab</span></span>  
  
     <span data-ttu-id="34f9d-124">На данной вкладке представлена сводная информация для всех публикаций распространителя.</span><span class="sxs-lookup"><span data-stu-id="34f9d-124">This tab provides summary information for all publications of a Distributor.</span></span>  
  
-   <span data-ttu-id="34f9d-125">Вкладка**Список наблюдения за подписками**</span><span class="sxs-lookup"><span data-stu-id="34f9d-125">**Subscription Watch List** tab</span></span>  
  
     <span data-ttu-id="34f9d-126">На этой вкладке содержится информация о подписчиках выбранного распространителя.</span><span class="sxs-lookup"><span data-stu-id="34f9d-126">This tab provides information about subscriptions for the selected Distributor.</span></span> <span data-ttu-id="34f9d-127">Список подписок можно фильтровать для просмотра ошибок, предупреждений и подписок с низкой производительностью.</span><span class="sxs-lookup"><span data-stu-id="34f9d-127">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="34f9d-128">На этой вкладке также можно выполнить следующие задачи: получить доступ к свойствам подписки и к подробным сведениях об агентах, связанных с подпиской, повторно инициализировать и проверять подписки.</span><span class="sxs-lookup"><span data-stu-id="34f9d-128">The tab also lets you to perform the following tasks: access subscription properties, access detailed information about the agent or agents associated with a subscription, reinitialize subscriptions, and validate subscriptions.</span></span>  
  
     <span data-ttu-id="34f9d-129">Вкладка **Список наблюдения за подписками** предназначена для ответа на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="34f9d-129">The **Subscription Watch List** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="34f9d-130">Какие подписки медленные?</span><span class="sxs-lookup"><span data-stu-id="34f9d-130">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="34f9d-131">Задайте параметры на этой вкладке так, чтобы отобразить в сетке список подписок, упорядоченный по их относительной производительности.</span><span class="sxs-lookup"><span data-stu-id="34f9d-131">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="34f9d-132">Исправна ли система репликации?</span><span class="sxs-lookup"><span data-stu-id="34f9d-132">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="34f9d-133">Сетка на этой вкладке выводит значки ошибок и предупреждений для всех подписок, на которые нужно обратить внимание.</span><span class="sxs-lookup"><span data-stu-id="34f9d-133">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
     <span data-ttu-id="34f9d-134">Эта вкладка недоступна для распространителей, работающих на [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] или более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="34f9d-134">This tab is not available for Distributors that are running versions of [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or earlier.</span></span>  
  
-   <span data-ttu-id="34f9d-135">Вкладка**Агенты**</span><span class="sxs-lookup"><span data-stu-id="34f9d-135">**Agents** tab</span></span>  
  
     <span data-ttu-id="34f9d-136">На этой вкладке отображаются подробные сведения об агентах и заданиях, используемых всеми типами репликации.</span><span class="sxs-lookup"><span data-stu-id="34f9d-136">This tab displays detailed information about the agents and jobs that are used by all types of replication.</span></span> <span data-ttu-id="34f9d-137">Эта вкладка также позволяет запускать и останавливать агенты и задания.</span><span class="sxs-lookup"><span data-stu-id="34f9d-137">The tab also let you start and stop each agent and job.</span></span>  
  
 <span data-ttu-id="34f9d-138">Монитор репликации также предоставляет контекстное меню для узла распространителя.</span><span class="sxs-lookup"><span data-stu-id="34f9d-138">Replication Monitor also provides a context menu for the Distributor node.</span></span> <span data-ttu-id="34f9d-139">Щелкните распространитель на левой панели правой кнопкой мыши, чтобы выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="34f9d-139">Right-click a Distributor in the left pane to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="34f9d-140">Добавить издателя в монитор репликации.</span><span class="sxs-lookup"><span data-stu-id="34f9d-140">Add a Publisher to Replication Monitor.</span></span>  
  
-   <span data-ttu-id="34f9d-141">Изменить настройки монитора репликации для распространителя.</span><span class="sxs-lookup"><span data-stu-id="34f9d-141">Edit Replication Monitor settings for the Distributor.</span></span>  
  
-   <span data-ttu-id="34f9d-142">Переключиться в представление «Группа издателей».</span><span class="sxs-lookup"><span data-stu-id="34f9d-142">Switch to the Publisher Group view.</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-publishers"></a><span data-ttu-id="34f9d-143">Просмотр информации и выполнение задач, относящихся к издателям</span><span class="sxs-lookup"><span data-stu-id="34f9d-143">Viewing Information and Performing Tasks Related to Publishers</span></span>  
 <span data-ttu-id="34f9d-144">Монитор репликации отображает информацию об издателях на трех вкладках:</span><span class="sxs-lookup"><span data-stu-id="34f9d-144">Replication Monitor displays information about Publishers on three tabs:</span></span>  
  
-   <span data-ttu-id="34f9d-145">Вкладка**Публикации**</span><span class="sxs-lookup"><span data-stu-id="34f9d-145">**Publications** tab</span></span>  
  
     <span data-ttu-id="34f9d-146">На данной вкладке представлена сводная информация для всех публикаций издателя.</span><span class="sxs-lookup"><span data-stu-id="34f9d-146">This tab provides summary information for all publications at a Publisher.</span></span>  
  
-   <span data-ttu-id="34f9d-147">Вкладка**Список наблюдения за подписками**</span><span class="sxs-lookup"><span data-stu-id="34f9d-147">**Subscription Watch List** tab</span></span>  
  
     <span data-ttu-id="34f9d-148">Данная вкладка предназначена для отображения информации о подписках для всех публикаций, доступных на выбранном издателе.</span><span class="sxs-lookup"><span data-stu-id="34f9d-148">This tab is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="34f9d-149">Список подписок можно фильтровать для просмотра ошибок, предупреждений и подписок с низкой производительностью.</span><span class="sxs-lookup"><span data-stu-id="34f9d-149">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="34f9d-150">На этой вкладке можно также получить доступ к свойствам подписки и к подробной информации об агенте или агентах, связанных с подпиской, повторно инициализировать и проверять подписки.</span><span class="sxs-lookup"><span data-stu-id="34f9d-150">The tab also allows you to: access subscription properties; access detailed information about the agent or agents associated with a subscription; reinitialize subscriptions; and validate subscriptions.</span></span>  
  
     <span data-ttu-id="34f9d-151">Вкладка **Список наблюдения за подписками** предназначена для ответа на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="34f9d-151">The **Subscription Watch List** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="34f9d-152">Какие подписки медленные?</span><span class="sxs-lookup"><span data-stu-id="34f9d-152">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="34f9d-153">Задайте параметры на этой вкладке так, чтобы отобразить в сетке список подписок, упорядоченный по их относительной производительности.</span><span class="sxs-lookup"><span data-stu-id="34f9d-153">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="34f9d-154">Исправна ли система репликации?</span><span class="sxs-lookup"><span data-stu-id="34f9d-154">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="34f9d-155">Сетка на этой вкладке выводит значки ошибок и предупреждений для всех подписок, на которые нужно обратить внимание.</span><span class="sxs-lookup"><span data-stu-id="34f9d-155">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
     <span data-ttu-id="34f9d-156">Эта вкладка не отображается для рабочих версий распространителей, предшествующих [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34f9d-156">This tab is not displayed for Distributors running versions prior to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="34f9d-157">Вкладка**Агенты**</span><span class="sxs-lookup"><span data-stu-id="34f9d-157">**Agents** tab</span></span>  
  
     <span data-ttu-id="34f9d-158">На этой вкладке отображаются подробные сведения об агентах и заданиях, используемых всеми типами репликации.</span><span class="sxs-lookup"><span data-stu-id="34f9d-158">This tab displays detailed information about the agents and jobs used by all types of replication.</span></span> <span data-ttu-id="34f9d-159">Эта вкладка также позволяет запускать и останавливать агенты и задания.</span><span class="sxs-lookup"><span data-stu-id="34f9d-159">The tab also allows you to start and stop each agent and job.</span></span>  
  
 <span data-ttu-id="34f9d-160">Дополнительные сведения см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="34f9d-160">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="34f9d-161">Монитор репликации также предоставляет контекстное меню для узла издателя.</span><span class="sxs-lookup"><span data-stu-id="34f9d-161">Replication Monitor also provides a context menu for the Publisher node.</span></span> <span data-ttu-id="34f9d-162">Щелкните правой кнопкой мыши издатель в левой панели окна, чтобы:</span><span class="sxs-lookup"><span data-stu-id="34f9d-162">Right-click a Publisher in the left pane to:</span></span>  
  
-   <span data-ttu-id="34f9d-163">Изменить настройки монитора репликации для издателя</span><span class="sxs-lookup"><span data-stu-id="34f9d-163">Edit Replication Monitor settings for the Publisher</span></span>  
  
-   <span data-ttu-id="34f9d-164">Удалить издатель из монитора репликации</span><span class="sxs-lookup"><span data-stu-id="34f9d-164">Remove the Publisher from Replication Monitor</span></span>  
  
-   <span data-ttu-id="34f9d-165">Просмотреть и изменить профили агентов</span><span class="sxs-lookup"><span data-stu-id="34f9d-165">View and edit agent profiles</span></span>  
  
-   <span data-ttu-id="34f9d-166">Соединиться или отсоединиться от распространителя, хранящего сведения об издателе</span><span class="sxs-lookup"><span data-stu-id="34f9d-166">Connect to or disconnect from the Distributor that stores information about the Publisher</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-publications"></a><span data-ttu-id="34f9d-167">Просмотр информации и выполнение задач, относящихся к публикациям</span><span class="sxs-lookup"><span data-stu-id="34f9d-167">Viewing Information and Performing Tasks Related to Publications</span></span>  
 <span data-ttu-id="34f9d-168">Монитор репликации отображает информацию о публикациях на трех вкладках и в нескольких окнах сведений:</span><span class="sxs-lookup"><span data-stu-id="34f9d-168">Replication Monitor displays information about publications on three tabs and a number of detail windows:</span></span>  
  
-   <span data-ttu-id="34f9d-169">Вкладка**Все подписки**</span><span class="sxs-lookup"><span data-stu-id="34f9d-169">**All Subscriptions** tab</span></span>  
  
     <span data-ttu-id="34f9d-170">На этой вкладке отображаются сведения о всех подписках на выбранную публикацию.</span><span class="sxs-lookup"><span data-stu-id="34f9d-170">This tab displays information about all subscriptions to the selected publication.</span></span> <span data-ttu-id="34f9d-171">По умолчанию эта вкладка отсортирована по приоритетам: ошибки, предупреждения, далее в порядке возрастания производительности, где подписки с наименьшей производительностью находятся сверху.</span><span class="sxs-lookup"><span data-stu-id="34f9d-171">By default, this tab is sorted in priority order: errors, then warnings, then in increasing order of performance, with any poorly performing subscriptions at the top.</span></span>  
  
     <span data-ttu-id="34f9d-172">Вкладка **Все подписки** предназначена для ответа на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="34f9d-172">The **All Subscriptions** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="34f9d-173">Какие подписки медленные?</span><span class="sxs-lookup"><span data-stu-id="34f9d-173">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="34f9d-174">Задайте параметры на этой вкладке так, чтобы отобразить в сетке список подписок, упорядоченный по их относительной производительности.</span><span class="sxs-lookup"><span data-stu-id="34f9d-174">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="34f9d-175">Исправна ли система репликации?</span><span class="sxs-lookup"><span data-stu-id="34f9d-175">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="34f9d-176">Сетка на этой вкладке выводит значки ошибок и предупреждений для всех подписок, на которые нужно обратить внимание.</span><span class="sxs-lookup"><span data-stu-id="34f9d-176">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
-   <span data-ttu-id="34f9d-177">Вкладка**Агенты**</span><span class="sxs-lookup"><span data-stu-id="34f9d-177">**Agents** tab</span></span>  
  
     <span data-ttu-id="34f9d-178">На этой вкладке отображаются подробные сведения об агентах, используемых репликацией.</span><span class="sxs-lookup"><span data-stu-id="34f9d-178">This tab displays information about the agents that are used by replication.</span></span> <span data-ttu-id="34f9d-179">На этой вкладке отображаются сведения о следующих агентах:</span><span class="sxs-lookup"><span data-stu-id="34f9d-179">This tab displays information about the following agents:</span></span>  
  
    -   <span data-ttu-id="34f9d-180">Агент моментальных снимков, используемый всеми публикациями.</span><span class="sxs-lookup"><span data-stu-id="34f9d-180">The Snapshot Agent, which is used by all publications.</span></span>  
  
    -   <span data-ttu-id="34f9d-181">Агент чтения журналов, используемый всеми публикациями транзакций.</span><span class="sxs-lookup"><span data-stu-id="34f9d-181">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
    -   <span data-ttu-id="34f9d-182">Агент чтения очереди, используемый публикациями транзакций, активированными для подписок, обновляемых посредством очередей.</span><span class="sxs-lookup"><span data-stu-id="34f9d-182">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
     <span data-ttu-id="34f9d-183">Кроме того, на вкладке можно выполнить следующие задачи: получить подробные сведения о каждом агенте, запустить или остановить любой из агентов.</span><span class="sxs-lookup"><span data-stu-id="34f9d-183">The tab also allows for you to perform the following tasks: access detailed information about each agent, and start and stop each agent.</span></span> <span data-ttu-id="34f9d-184">Сведения об агентах, связанных с подписками (агент распространителя и агент слияния), см. в подразделе «Просмотр информации и выполнение задач, относящихся к подпискам» данного раздела.</span><span class="sxs-lookup"><span data-stu-id="34f9d-184">For information about agents that are associated with subscriptions (the Distribution Agent and Merge Agent), see the section "Viewing Information and Performing Tasks Related to Subscriptions" in this topic.</span></span>  
  
-   <span data-ttu-id="34f9d-185">Вкладка**Предупреждения**</span><span class="sxs-lookup"><span data-stu-id="34f9d-185">**Warnings** tab</span></span>  
  
     <span data-ttu-id="34f9d-186">Эта вкладка позволяет задать предупреждения для агентов.</span><span class="sxs-lookup"><span data-stu-id="34f9d-186">This tab enables you to specify warnings and alerts for agents.</span></span> <span data-ttu-id="34f9d-187">Дополнительные сведения см. в статье [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="34f9d-187">For more information, see [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="34f9d-188">Вкладка**Трассировочные токены** (только для репликации транзакций)</span><span class="sxs-lookup"><span data-stu-id="34f9d-188">**Tracer Tokens** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="34f9d-189">Эта вкладка позволяет измерять величину задержки между моментом фиксации транзакции на издателе и моментом фиксации соответствующей транзакции на подписчике.</span><span class="sxs-lookup"><span data-stu-id="34f9d-189">This tab allows you to measure latency, the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span>  
  
     <span data-ttu-id="34f9d-190">Данная вкладка предназначена для ответа на следующий вопрос:</span><span class="sxs-lookup"><span data-stu-id="34f9d-190">This tab helps answers the following question:</span></span>  
  
    -   <span data-ttu-id="34f9d-191">Сколько времени понадобится, чтобы только что зафиксированная транзакция была получена подписчиком в репликации транзакций?</span><span class="sxs-lookup"><span data-stu-id="34f9d-191">How long will it take a transaction committed now to reach a Subscriber in transactional replication?</span></span>  
  
         <span data-ttu-id="34f9d-192">Просмотр общего времени прохождения транзакции через систему и сравнение его с ранее измеренным временем.</span><span class="sxs-lookup"><span data-stu-id="34f9d-192">View the total time for a transaction to travel through the system and also compare it to previous times.</span></span>  
  
     <span data-ttu-id="34f9d-193">Эта вкладка не отображается для распространителей, работающих на [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="34f9d-193">This tab is not displayed for Distributors running [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or earlier.</span></span> <span data-ttu-id="34f9d-194">Дополнительные сведения об использовании трассировочных токенов см. в разделе [Измерение задержки и проверка правильности соединений для репликации транзакций](measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="34f9d-194">For more information on tracer tokens, see [Measure Latency and Validate Connections for Transactional Replication](measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="34f9d-195">Окна сведений для агентов, связанных с публикацией.</span><span class="sxs-lookup"><span data-stu-id="34f9d-195">Detail windows for the agents associated with a publication.</span></span> <span data-ttu-id="34f9d-196">С публикациями связаны следующие агенты:</span><span class="sxs-lookup"><span data-stu-id="34f9d-196">The following agents are associated with publications:</span></span>  
  
    -   <span data-ttu-id="34f9d-197">Агент моментальных снимков, используемый всеми публикациями.</span><span class="sxs-lookup"><span data-stu-id="34f9d-197">The Snapshot Agent, which is used by all publications.</span></span>  
  
    -   <span data-ttu-id="34f9d-198">Агент чтения журналов, используемый всеми публикациями транзакций.</span><span class="sxs-lookup"><span data-stu-id="34f9d-198">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
    -   <span data-ttu-id="34f9d-199">Агент чтения очереди, используемый публикациями транзакций, активированными для подписок, обновляемых посредством очередей.</span><span class="sxs-lookup"><span data-stu-id="34f9d-199">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
     <span data-ttu-id="34f9d-200">Дважды щелкните мышью агент в мониторе репликации для доступа к информации в окне сведений.</span><span class="sxs-lookup"><span data-stu-id="34f9d-200">Double-click an agent in Replication Monitor to access information in a detail window.</span></span> <span data-ttu-id="34f9d-201">Кроме агентов, перечисленных выше, существуют агенты, связанные с подписками: агент распространителя подписок публикаций моментальными снимками и публикаций транзакций, а также агент слияния для публикаций слиянием.</span><span class="sxs-lookup"><span data-stu-id="34f9d-201">In addition to the agents listed above, there are agents associated with subscriptions: the Distribution Agent for subscriptions to snapshot and transactional publications; and the Merge Agent for subscriptions to merge publications.</span></span> <span data-ttu-id="34f9d-202">Дополнительные сведения см. в подразделе «Просмотр информации и выполнение задач, относящихся к подпискам» в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="34f9d-202">For more information, see the section "Viewing Information and Performing Tasks Related to Subscriptions" in this topic.</span></span>  
  
     <span data-ttu-id="34f9d-203">Окна сведений об агентах предоставляют информацию о сеансах работы агентов, включая время начала и окончания работы, продолжительность и действия, выполненные в течение сеанса.</span><span class="sxs-lookup"><span data-stu-id="34f9d-203">The agent detail windows provide information about agent sessions, including start time, end time, duration, and the actions performed in a session.</span></span> <span data-ttu-id="34f9d-204">Они помогают ответить на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="34f9d-204">They help to answer the following question:</span></span>  
  
    -   <span data-ttu-id="34f9d-205">Почему агент не запущен?</span><span class="sxs-lookup"><span data-stu-id="34f9d-205">Why is an agent not running?</span></span>  
  
         <span data-ttu-id="34f9d-206">Выводимые сообщения об ошибках содержат подробную информацию о том, почему агент не запущен, и предоставляют отправную точку для устранения проблем с агентами, связанных с публикацией.</span><span class="sxs-lookup"><span data-stu-id="34f9d-206">The error messages available provide detailed information on why an agent is not running and provide a starting point for troubleshooting issues with the agents associated with a publication.</span></span>  
  
 <span data-ttu-id="34f9d-207">Дополнительные сведения см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="34f9d-207">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="34f9d-208">Монитор репликации также предоставляет контекстное меню для узла публикаций.</span><span class="sxs-lookup"><span data-stu-id="34f9d-208">Replication Monitor also provides a context menu for the publications node.</span></span> <span data-ttu-id="34f9d-209">Щелкните правой кнопкой мыши публикацию в левой панели окна, чтобы:</span><span class="sxs-lookup"><span data-stu-id="34f9d-209">Right-click a publication in the left pane to:</span></span>  
  
-   <span data-ttu-id="34f9d-210">Повторно инициализировать все подписки на публикацию</span><span class="sxs-lookup"><span data-stu-id="34f9d-210">Reinitialize all subscriptions to a publication</span></span>  
  
-   <span data-ttu-id="34f9d-211">Проверить все подписки на публикацию</span><span class="sxs-lookup"><span data-stu-id="34f9d-211">Validate all subscriptions to a publication</span></span>  
  
-   <span data-ttu-id="34f9d-212">Создать моментальный снимок для публикации</span><span class="sxs-lookup"><span data-stu-id="34f9d-212">Generate a snapshot for a publication</span></span>  
  
-   <span data-ttu-id="34f9d-213">Просмотреть и изменить свойства публикации</span><span class="sxs-lookup"><span data-stu-id="34f9d-213">View and edit publication properties</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-subscriptions"></a><span data-ttu-id="34f9d-214">Просмотр информации и выполнение задач, относящихся к подпискам</span><span class="sxs-lookup"><span data-stu-id="34f9d-214">Viewing Information and Performing Tasks Related to Subscriptions</span></span>  
 <span data-ttu-id="34f9d-215">Монитор репликации отображает информацию о подписках на нескольких вкладках.</span><span class="sxs-lookup"><span data-stu-id="34f9d-215">Replication Monitor displays information about subscriptions on a number of different tabs.</span></span> <span data-ttu-id="34f9d-216">Дважды щелкните мышью подписку в мониторе репликации для доступа к этим вкладкам в окне сведений.</span><span class="sxs-lookup"><span data-stu-id="34f9d-216">Double-click a subscription in Replication Monitor to access these tabs in a detail window.</span></span> <span data-ttu-id="34f9d-217">Все вкладки предназначены для ответа на вопрос «Почему агент не запущен?»</span><span class="sxs-lookup"><span data-stu-id="34f9d-217">All of the tabs are useful in answering the question "Why is an agent not running?"</span></span> <span data-ttu-id="34f9d-218">Выводимые сообщения об ошибках содержат подробную информацию о том, почему агент не запущен, и предоставляют отправную точку для устранения проблем с агентами, связанных с подпиской.</span><span class="sxs-lookup"><span data-stu-id="34f9d-218">The error messages available provide detailed information on why an agent is not running and provide a starting point for troubleshooting issues with the agents associated with a subscription.</span></span>  
  
-   <span data-ttu-id="34f9d-219">Вкладка**Все подписки** и вкладка **Список наблюдения за подписками**.</span><span class="sxs-lookup"><span data-stu-id="34f9d-219">**All Subscriptions tab** and **Subscription Watch List tab.**</span></span>  
  
     <span data-ttu-id="34f9d-220">Описание этих вкладок приведено выше.</span><span class="sxs-lookup"><span data-stu-id="34f9d-220">These tabs are described earlier in this topic.</span></span>  
  
-   <span data-ttu-id="34f9d-221">Вкладка**Журнал операций от издателя к распространителю** (только для репликации транзакций)</span><span class="sxs-lookup"><span data-stu-id="34f9d-221">**Publisher to Distributor History** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="34f9d-222">На данной вкладке отображается информация агента чтения журнала для публикации (вкладка идентична окну сведений агента чтения журнала).</span><span class="sxs-lookup"><span data-stu-id="34f9d-222">This tab displays information on the Log Reader Agent for a publication (the tab is identical to the Log Reader Agent details window).</span></span>  
  
-   <span data-ttu-id="34f9d-223">Вкладка**Журнал операций от распространителя к подписчику** (репликация моментальными снимками и репликация транзакций)</span><span class="sxs-lookup"><span data-stu-id="34f9d-223">**Distributor to Subscriber History** tab (snapshot replication and transactional replication)</span></span>  
  
     <span data-ttu-id="34f9d-224">На данной вкладке отображается информация об агенте распространителя для публикации.</span><span class="sxs-lookup"><span data-stu-id="34f9d-224">This tab displays information on the Distribution Agent for a subscription.</span></span>  
  
-   <span data-ttu-id="34f9d-225">Вкладка**Нераспределенные команды** (только для репликации транзакций)</span><span class="sxs-lookup"><span data-stu-id="34f9d-225">**Undistributed Commands** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="34f9d-226">На данной вкладке отображается информация о количестве команд в базе данных распространителя, которые не были доставлены выбранному подписчику, и приблизительное время, требуемое для доставки этих команд.</span><span class="sxs-lookup"><span data-stu-id="34f9d-226">This tab displays information about the number of commands in the distribution database that have not been delivered to the selected Subscriber, and the estimated time to deliver those commands.</span></span> <span data-ttu-id="34f9d-227">Данная вкладка предназначена для ответа на вопрос «Насколько запаздывает подписка?»</span><span class="sxs-lookup"><span data-stu-id="34f9d-227">The tab helps answer the question, "How far behind is my subscription?"</span></span> <span data-ttu-id="34f9d-228">Эта вкладка не отображается для рабочих версий распространителей, предшествующих SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="34f9d-228">This tab is not displayed for Distributors running versions prior to SQL Server 2005.</span></span>  
  
-   <span data-ttu-id="34f9d-229">Вкладка**Журнал синхронизации** (только для репликации слиянием)</span><span class="sxs-lookup"><span data-stu-id="34f9d-229">**Synchronization History** tab (merge replication only)</span></span>  
  
     <span data-ttu-id="34f9d-230">На данной вкладке отображается информация об агенте слияния для подписки.</span><span class="sxs-lookup"><span data-stu-id="34f9d-230">This tab displays information on the Merge Agent for a subscription.</span></span> <span data-ttu-id="34f9d-231">Данная вкладка предназначена для ответа на следующий вопрос:</span><span class="sxs-lookup"><span data-stu-id="34f9d-231">This tab helps answer the following question:</span></span>  
  
    -   <span data-ttu-id="34f9d-232">Почему подписка на публикацию слиянием медленная?</span><span class="sxs-lookup"><span data-stu-id="34f9d-232">Why is my merge subscription slow?</span></span>  
  
         <span data-ttu-id="34f9d-233">На данной вкладке отображается подробная статистика для каждой статьи, обработанной во время синхронизации, включая продолжительность каждой фазы обработки (передача изменений, загрузка изменений и т. п.).</span><span class="sxs-lookup"><span data-stu-id="34f9d-233">This tab provides detailed statistics for each article processed during synchronization, including the amount of time spent in each processing phase (uploading changes, downloading changes, and so on).</span></span> <span data-ttu-id="34f9d-234">Данная вкладка может помочь определить конкретные таблицы, которые приводят к замедлению, и является наилучшим местом для устранения неполадок, связанных с производительностью подписок на публикацию слиянием.</span><span class="sxs-lookup"><span data-stu-id="34f9d-234">It can help pinpoint specific tables that are causing slowdowns and is the best place to troubleshoot performance issues with merge subscriptions.</span></span>  
  
 <span data-ttu-id="34f9d-235">Дополнительные сведения см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="34f9d-235">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>
  
## <a name="viewing-information-and-performing-tasks-related-to-agent-profiles"></a><span data-ttu-id="34f9d-236">Просмотр информации и выполнение задач, относящихся к профилям агентов</span><span class="sxs-lookup"><span data-stu-id="34f9d-236">Viewing Information and Performing Tasks Related to Agent Profiles</span></span>  
 <span data-ttu-id="34f9d-237">Монитор репликации содержит несколько диалоговых окон для управления профилями агентов.</span><span class="sxs-lookup"><span data-stu-id="34f9d-237">Replication Monitor includes a number of dialog boxes for managing agent profiles.</span></span> <span data-ttu-id="34f9d-238">Профили агентов представляют собой наборы параметров для агента, определяющих его функционирование.</span><span class="sxs-lookup"><span data-stu-id="34f9d-238">Agent profiles are sets of parameters for an agent that determine agent behavior.</span></span> <span data-ttu-id="34f9d-239">Дополнительные сведения см. в статье [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="34f9d-239">For more information, see [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span></span> <span data-ttu-id="34f9d-240">Эти диалоговые окна включают:</span><span class="sxs-lookup"><span data-stu-id="34f9d-240">The dialog boxes are:</span></span>  
  
-   <span data-ttu-id="34f9d-241">**Профили агентов**</span><span class="sxs-lookup"><span data-stu-id="34f9d-241">**Agent Profiles**</span></span>  
  
     <span data-ttu-id="34f9d-242">В этом диалоговом окне можно изменять свойства профилей, создавать и удалять профили, задавать профиль по умолчанию, а также указывать конкретный профиль для использования всеми агентами определенного типа (например, агентами моментальных снимков).</span><span class="sxs-lookup"><span data-stu-id="34f9d-242">This dialog box allows you to: change the properties of profiles; create and delete profiles; specify a default profile; and specify that all agents of a specific type (such as Snapshot Agents) should use a given profile.</span></span>  
  
-   <span data-ttu-id="34f9d-243">**Свойства \<AgentProfileName>**</span><span class="sxs-lookup"><span data-stu-id="34f9d-243">**\<AgentProfileName> Properties**</span></span>  
  
     <span data-ttu-id="34f9d-244">Данное диалоговое окно позволяет просматривать и изменять настройки параметров в профиле.</span><span class="sxs-lookup"><span data-stu-id="34f9d-244">This dialog box allows you to view and edit the parameter settings in a profile.</span></span>  
  
-   <span data-ttu-id="34f9d-245">**Создать профиль агента**</span><span class="sxs-lookup"><span data-stu-id="34f9d-245">**New Agent Profile**</span></span>  
  
     <span data-ttu-id="34f9d-246">Данное диалоговое окно позволяет создать новый профиль с возможностью включения значений из существующего профиля.</span><span class="sxs-lookup"><span data-stu-id="34f9d-246">This dialog box allows you to create a new profile, optionally including the values from an existing profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f9d-247">См. также:</span><span class="sxs-lookup"><span data-stu-id="34f9d-247">See Also</span></span>  
 [<span data-ttu-id="34f9d-248">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="34f9d-248">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
