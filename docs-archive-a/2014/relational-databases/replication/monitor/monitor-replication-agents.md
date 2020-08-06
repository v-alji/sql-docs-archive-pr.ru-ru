---
title: Наблюдение за агентами репликации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], agents
- Log Reader Agent, monitoring
- Replication Monitor, agents
- Merge Agent, monitoring
- Queue Reader Agent, monitoring
- Snapshot Agent, monitoring
- agents [SQL Server replication], monitoring
- Distribution Agent, monitoring
ms.assetid: d06ed24f-82d7-4b9e-9e40-cc9780476a71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: baa22ef9e9f7c4621f76838e82c309d17f1e12a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657651"
---
# <a name="monitor-replication-agents"></a><span data-ttu-id="01187-102">Наблюдение за агентами репликации</span><span class="sxs-lookup"><span data-stu-id="01187-102">Monitor Replication Agents</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="01187-103">Монитор репликации [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] предоставляет систематический обзор действий репликации, а также облегчает поиск сведений о конкретном агенте.</span><span class="sxs-lookup"><span data-stu-id="01187-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor provides a systemic view of replication activity, but also makes it straightforward to find information on a specific agent.</span></span> <span data-ttu-id="01187-104">В приведенном ниже списке перечислены все агенты, для которых существуют вкладки в мониторе репликации, а также дается ссылка на раздел, где описывается порядок доступа к этим вкладкам.</span><span class="sxs-lookup"><span data-stu-id="01187-104">The following list includes each agent, the tabs in the Replication Monitor on which it can be found, and a link to a topic that explains how to access these tabs:</span></span>  
  
-   <span data-ttu-id="01187-105">С публикациями в мониторе репликации связаны следующие агенты.</span><span class="sxs-lookup"><span data-stu-id="01187-105">The following agents are associated with publications in Replication Monitor:</span></span>  
  
    -   <span data-ttu-id="01187-106">агент моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="01187-106">Snapshot Agent</span></span>  
  
    -   <span data-ttu-id="01187-107">Агент чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="01187-107">Log Reader Agent</span></span>  
  
    -   <span data-ttu-id="01187-108">Агент чтения очереди.</span><span class="sxs-lookup"><span data-stu-id="01187-108">Queue Reader Agent</span></span>  
  
     <span data-ttu-id="01187-109">Получить доступ к сведениям и задачам, связанным с этими агентами, можно на следующих вкладках: **Агенты** (доступна для всех издателей и публикаций) и **Предупреждения** (доступна для всех публикаций).</span><span class="sxs-lookup"><span data-stu-id="01187-109">Access information and tasks associated with these agents through the following tabs: **Agents** (available for each Publisher and publication) and **Warnings** (available for each publication).</span></span> <span data-ttu-id="01187-110">Дополнительные сведения см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="01187-110">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="01187-111">С подписками в мониторе репликации связаны следующие агенты:</span><span class="sxs-lookup"><span data-stu-id="01187-111">The following agents are associated with subscriptions in Replication Monitor:</span></span>  
  
    -   <span data-ttu-id="01187-112">Агент распространителя</span><span class="sxs-lookup"><span data-stu-id="01187-112">Distribution Agent</span></span>  
  
    -   <span data-ttu-id="01187-113">Агент слияния.</span><span class="sxs-lookup"><span data-stu-id="01187-113">Merge Agent</span></span>  
  
     <span data-ttu-id="01187-114">Получить доступ к сведениям и задачам, связанным с этими агентами, можно на следующих вкладках: **Список наблюдения за подписками** (доступна для каждого издателя) или вкладка **Все подписки** (доступна для каждой публикации).</span><span class="sxs-lookup"><span data-stu-id="01187-114">Access information and tasks associated with these agents through the following tabs: **Subscription Watch List** (available for each Publisher) or the **All Subscriptions** tab (available for each publication).</span></span> <span data-ttu-id="01187-115">Дополнительные сведения см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="01187-115">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
## <a name="using-sql-server-management-studio-to-monitor-replication-agents"></a><span data-ttu-id="01187-116">Использование среды Management Studio для наблюдения за агентами репликации</span><span class="sxs-lookup"><span data-stu-id="01187-116">Using SQL Server Management Studio to Monitor Replication Agents</span></span>  
 <span data-ttu-id="01187-117">Среда [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] предоставляет возможность наблюдения за агентами репликации с помощью следующих диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="01187-117">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] provides the following dialog boxes for monitoring replication agents:</span></span>  
  
-   <span data-ttu-id="01187-118">**Просмотр состояния агента моментальных снимков** (для всех публикаций).</span><span class="sxs-lookup"><span data-stu-id="01187-118">**View Snapshot Agent Status** (for all publications)</span></span>  
  
-   <span data-ttu-id="01187-119">**Просмотр состояния агента чтения журнала** (для всех публикаций транзакций).</span><span class="sxs-lookup"><span data-stu-id="01187-119">**View Log Reader Agent Status** (for all transactional publications)</span></span>  
  
-   <span data-ttu-id="01187-120">**Просмотр состояния синхронизации** (для всех подписок; это диалоговое окно предоставляет доступ к агенту распространителя и агенту слияния).</span><span class="sxs-lookup"><span data-stu-id="01187-120">**View Synchronization Status** (for all subscriptions; this dialog box allows access to the Distribution Agent and the Merge Agent)</span></span>  
  
 <span data-ttu-id="01187-121">Монитор репликации предоставляет дополнительные сведения о каждом агенте и предоставляет возможность наблюдения за агентом чтения очереди в случае его использования.</span><span class="sxs-lookup"><span data-stu-id="01187-121">Replication Monitor provides additional information about each agent and provides monitoring for the Queue Reader Agent, if it is used.</span></span> <span data-ttu-id="01187-122">Дополнительные сведения см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="01187-122">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
#### <a name="to-monitor-the-snapshot-agent-and-log-reader-agent"></a><span data-ttu-id="01187-123">Наблюдение за агентом моментальных снимков и агентом чтения журналов</span><span class="sxs-lookup"><span data-stu-id="01187-123">To monitor the Snapshot Agent and Log Reader Agent</span></span>  
  
1.  <span data-ttu-id="01187-124">Подключитесь к издателю в среде [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="01187-124">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="01187-125">Раскройте папку **Репликация** , а затем папку **Локальные публикации** .</span><span class="sxs-lookup"><span data-stu-id="01187-125">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="01187-126">Щелкните публикацию правой кнопкой мыши, затем щелкните **Просмотреть состояние агента чтения журнала** или **Просмотреть состояние агента моментальных снимков**.</span><span class="sxs-lookup"><span data-stu-id="01187-126">Right-click a publication, and then click **View Log Reader Agent Status** or **View Snapshot Agent Status**.</span></span>  
  
4.  <span data-ttu-id="01187-127">В диалоговом окне **Просмотр состояния агента чтения журнала** или **Просмотр состояния агента моментальных снимков** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="01187-127">In the **View Log Reader Agent Status** or **View Snapshot Agent Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="01187-128">Просмотрите состояние агента.</span><span class="sxs-lookup"><span data-stu-id="01187-128">View agent status.</span></span>  
  
    -   <span data-ttu-id="01187-129">Запустите или остановите агент при необходимости.</span><span class="sxs-lookup"><span data-stu-id="01187-129">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="01187-130">Щелкните **Отслеживать** , чтобы запустить **Монитор репликации**.</span><span class="sxs-lookup"><span data-stu-id="01187-130">Click **Monitor** to launch **Replication Monitor**.</span></span>  
  
5.  <span data-ttu-id="01187-131">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="01187-131">Click **Close**.</span></span>  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-publisher"></a><span data-ttu-id="01187-132">Наблюдение за агентом распространителя и агентом слияния (с издателя)</span><span class="sxs-lookup"><span data-stu-id="01187-132">To monitor the Distribution Agent and Merge Agent (from the Publisher)</span></span>  
  
1.  <span data-ttu-id="01187-133">Подключитесь к издателю в среде [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="01187-133">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="01187-134">Раскройте папку **Репликация** , а затем папку **Локальные публикации** .</span><span class="sxs-lookup"><span data-stu-id="01187-134">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="01187-135">Раскройте публикацию, связанную с подпиской, которую требуется проконтролировать.</span><span class="sxs-lookup"><span data-stu-id="01187-135">Expand the publication for the subscription you want to monitor.</span></span>  
  
4.  <span data-ttu-id="01187-136">Щелкните правой кнопкой мыши подписку, затем выберите **Просмотреть состояние синхронизации**.</span><span class="sxs-lookup"><span data-stu-id="01187-136">Right-click the subscription, and then click **View Synchronization Status**.</span></span>  
  
5.  <span data-ttu-id="01187-137">В диалоговом окне **Просмотр состояния синхронизации** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="01187-137">In the **View Synchronization Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="01187-138">Просмотрите состояние агента.</span><span class="sxs-lookup"><span data-stu-id="01187-138">View agent status.</span></span>  
  
    -   <span data-ttu-id="01187-139">Запустите или остановите агент при необходимости.</span><span class="sxs-lookup"><span data-stu-id="01187-139">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="01187-140">Для принудительных подписок щелкните **Отслеживать** , чтобы запустить **Монитор репликации**.</span><span class="sxs-lookup"><span data-stu-id="01187-140">For push subscriptions, click **Monitor** to launch **Replication Monitor**.</span></span>  
  
    -   <span data-ttu-id="01187-141">Для подписок по запросу щелкните **Просмотреть журнал заданий** , чтобы запустить **Средство просмотра файла журнала**, отображающего записи журнала агента.</span><span class="sxs-lookup"><span data-stu-id="01187-141">For pull subscriptions, click **View Job History** to launch the **Log File Viewer**, which displays output from the agent log.</span></span>  
  
6.  <span data-ttu-id="01187-142">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="01187-142">Click **Close**.</span></span>  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-subscriber"></a><span data-ttu-id="01187-143">Наблюдение за агентом распространителя и агентом слияния (с подписчика)</span><span class="sxs-lookup"><span data-stu-id="01187-143">To monitor the Distribution Agent and Merge Agent (from the Subscriber)</span></span>  
  
1.  <span data-ttu-id="01187-144">Подключитесь к подписчику в [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]и раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="01187-144">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="01187-145">Раскройте папку **Репликация** , а затем — папку **Локальные подписки** .</span><span class="sxs-lookup"><span data-stu-id="01187-145">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="01187-146">Щелкните подписку правой кнопкой мыши, и щелкните **Просмотреть состояние синхронизации**.</span><span class="sxs-lookup"><span data-stu-id="01187-146">Right-click the subscription you want to monitor, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="01187-147">В диалоговом окне **Просмотр состояния синхронизации** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="01187-147">In the **View Synchronization Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="01187-148">Просмотрите состояние агента.</span><span class="sxs-lookup"><span data-stu-id="01187-148">View agent status.</span></span>  
  
    -   <span data-ttu-id="01187-149">Запустите или остановите агент при необходимости.</span><span class="sxs-lookup"><span data-stu-id="01187-149">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="01187-150">Щелкните **Просмотреть журнал заданий** , чтобы запустить **Средство просмотра файла журнала**, отображающего записи журнала агента.</span><span class="sxs-lookup"><span data-stu-id="01187-150">Click **View Job History** to launch the **Log File Viewer**, which displays output from the agent log.</span></span>  
  
5.  <span data-ttu-id="01187-151">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="01187-151">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01187-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="01187-152">See Also</span></span>  
 <span data-ttu-id="01187-153">[Наблюдение за репликацией](../monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="01187-153">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 [<span data-ttu-id="01187-154">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="01187-154">Replication Agents Overview</span></span>](../agents/replication-agents-overview.md)  
  
  
