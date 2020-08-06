---
title: Просмотр и изменение параметров командной строки агента репликации (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], command prompt parameters
ms.assetid: 45f2e781-c21d-4b44-8992-89f60fb3d022
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 752f674c21bb66c7b64e399e30e4917512431195
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655661"
---
# <a name="view-and-modify-replication-agent-command-prompt-parameters-sql-server-management-studio"></a><span data-ttu-id="cadc7-102">Просмотр и изменение параметров командной строки агента репликации (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cadc7-102">View and Modify Replication Agent Command Prompt Parameters (SQL Server Management Studio)</span></span>
  <span data-ttu-id="cadc7-103">Агенты репликации — это исполняемые файлы, принимающие параметры командной строки.</span><span class="sxs-lookup"><span data-stu-id="cadc7-103">Replication agents are executables that accept command line parameters.</span></span> <span data-ttu-id="cadc7-104">По умолчанию агенты выполняются при выполнении шагов заданий агента [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], поэтому данные параметры можно просматривать и изменять с помощью диалогового окна **Свойства задания — \<Job>** .</span><span class="sxs-lookup"><span data-stu-id="cadc7-104">By default, agents run under [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job steps, so these parameters can be viewed and modified using the **Job Properties - \<Job>** dialog box.</span></span> <span data-ttu-id="cadc7-105">Доступ к этому диалоговому окну можно получить из папки **Задания** в среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] и на вкладке **Агенты** монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="cadc7-105">This dialog box is available from the **Jobs** folder in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from the **Agents** tab in Replication Monitor.</span></span> <span data-ttu-id="cadc7-106">Сведения о запуске монитора репликации см. в [этой статье](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="cadc7-106">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cadc7-107">Изменения параметров агента вступают в действие при следующем запуске агента.</span><span class="sxs-lookup"><span data-stu-id="cadc7-107">Agent parameter changes take effect the next time the agent is started.</span></span> <span data-ttu-id="cadc7-108">Если агент выполняется в непрерывном режиме, следует остановить и перезапустить агент.</span><span class="sxs-lookup"><span data-stu-id="cadc7-108">If the agent runs continuously, you must stop and restart the agent.</span></span>  
  
 <span data-ttu-id="cadc7-109">Хотя параметры можно изменять непосредственно, чаще всего их изменяют через профиль агента.</span><span class="sxs-lookup"><span data-stu-id="cadc7-109">Although parameters can be modified directly, it is more common to modify them through an agent profile.</span></span> <span data-ttu-id="cadc7-110">Дополнительные сведения см. в статье [Replication Agent Profiles](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="cadc7-110">For more information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="cadc7-111">При доступе к заданиям агента из папки **Задания** для определения имени задания и параметров, доступных для каждого агента, воспользуйтесь следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="cadc7-111">If you access agent jobs from the **Jobs** folder, use the following table to determine the agent job name and the parameters available for each agent.</span></span>  
  
|<span data-ttu-id="cadc7-112">Агент</span><span class="sxs-lookup"><span data-stu-id="cadc7-112">Agent</span></span>|<span data-ttu-id="cadc7-113">Имя задания</span><span class="sxs-lookup"><span data-stu-id="cadc7-113">Job name</span></span>|<span data-ttu-id="cadc7-114">Для просмотра списка параметров см...</span><span class="sxs-lookup"><span data-stu-id="cadc7-114">For a list of parameters, see...</span></span>|  
|-----------|--------------|------------------------------------|  
|<span data-ttu-id="cadc7-115">агент моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="cadc7-115">Snapshot Agent</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<integer>**|[<span data-ttu-id="cadc7-116">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="cadc7-116">Replication Snapshot Agent</span></span>](replication-snapshot-agent.md)|  
|<span data-ttu-id="cadc7-117">Агент моментальных снимков для секции публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="cadc7-117">Snapshot Agent for a merge publication partition</span></span>|<span data-ttu-id="cadc7-118">**Dyn_\<Publisher>-\<PublicationDatabase>-\<Publication>-\<GUID>**</span><span class="sxs-lookup"><span data-stu-id="cadc7-118">**Dyn_\<Publisher>-\<PublicationDatabase>-\<Publication>-\<GUID>**</span></span>|[<span data-ttu-id="cadc7-119">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="cadc7-119">Replication Snapshot Agent</span></span>](replication-snapshot-agent.md)|  
|<span data-ttu-id="cadc7-120">Агент чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="cadc7-120">Log Reader Agent</span></span>|**\<Publisher>-\<PublicationDatabase>-\<integer>**|[<span data-ttu-id="cadc7-121">Агент чтения журнала репликации</span><span class="sxs-lookup"><span data-stu-id="cadc7-121">Replication Log Reader Agent</span></span>](replication-log-reader-agent.md)|  
|<span data-ttu-id="cadc7-122">Агент слияния для подписок по запросу</span><span class="sxs-lookup"><span data-stu-id="cadc7-122">Merge Agent for pull subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<integer>**|[<span data-ttu-id="cadc7-123">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="cadc7-123">Replication Merge Agent</span></span>](replication-merge-agent.md)|  
|<span data-ttu-id="cadc7-124">Агент слияния для принудительных подписок</span><span class="sxs-lookup"><span data-stu-id="cadc7-124">Merge Agent for push subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|[<span data-ttu-id="cadc7-125">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="cadc7-125">Replication Merge Agent</span></span>](replication-merge-agent.md)|  
|<span data-ttu-id="cadc7-126">Агент распространителя для принудительных подписок</span><span class="sxs-lookup"><span data-stu-id="cadc7-126">Distribution Agent for push subscriptions</span></span>|<span data-ttu-id="cadc7-127">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cadc7-127">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span></span>|[<span data-ttu-id="cadc7-128">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="cadc7-128">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="cadc7-129">Агент распространителя для подписок по запросу</span><span class="sxs-lookup"><span data-stu-id="cadc7-129">Distribution Agent for pull subscriptions</span></span>|<span data-ttu-id="cadc7-130">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cadc7-130">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span></span>|[<span data-ttu-id="cadc7-131">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="cadc7-131">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="cadc7-132">Агент распространителя для принудительных подписок подписчиков серверов, отличных от подписчиков SQL Server</span><span class="sxs-lookup"><span data-stu-id="cadc7-132">Distribution Agent for push subscriptions to non-SQL Server Subscribers</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|[<span data-ttu-id="cadc7-133">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="cadc7-133">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="cadc7-134">Агент чтения очереди.</span><span class="sxs-lookup"><span data-stu-id="cadc7-134">Queue Reader Agent</span></span>|<span data-ttu-id="cadc7-135">**[\<Distributor>].\<integer>**</span><span class="sxs-lookup"><span data-stu-id="cadc7-135">**[\<Distributor>].\<integer>**</span></span>|[<span data-ttu-id="cadc7-136">Replication Queue Reader Agent</span><span class="sxs-lookup"><span data-stu-id="cadc7-136">Replication Queue Reader Agent</span></span>](replication-queue-reader-agent.md)|  
  
 <span data-ttu-id="cadc7-137"><sup>1</sup> Для принудительных подписок на публикации Oracle это \*\*\<Publisher>-\<Publisher**>, а не **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="cadc7-137"><sup>1</sup> For push subscriptions to Oracle publications, it is \*\*\<Publisher>-\<Publisher**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
 <span data-ttu-id="cadc7-138"><sup>2</sup> Для подписок по запросу на публикации Oracle это \*\*\<Publisher>-\<DistributionDatabase**>, а не **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="cadc7-138"><sup>2</sup> For pull subscriptions to Oracle publications, it is \*\*\<Publisher>-\<DistributionDatabase**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
### <a name="to-view-and-modify-replication-agent-command-line-parameters-from-management-studio"></a><span data-ttu-id="cadc7-139">Просмотр и изменение параметров командной строки агента репликации из среды Management Studio</span><span class="sxs-lookup"><span data-stu-id="cadc7-139">To view and modify replication agent command line parameters from Management Studio</span></span>  
  
1.  <span data-ttu-id="cadc7-140">Подключитесь к соответствующему компьютеру в [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], а затем раскройте узел сервера:</span><span class="sxs-lookup"><span data-stu-id="cadc7-140">Connect to the appropriate computer in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node:</span></span>  
  
    -   <span data-ttu-id="cadc7-141">В случае использования агента распространителя и агента слияния для подписок по запросу подключитесь к подписчику.</span><span class="sxs-lookup"><span data-stu-id="cadc7-141">For the Distribution Agent and Merge Agent for pull subscriptions, connect to the Subscriber.</span></span>  
  
    -   <span data-ttu-id="cadc7-142">Для всех иных агентов подключитесь к распространителю.</span><span class="sxs-lookup"><span data-stu-id="cadc7-142">For all other agents, connect to the Distributor.</span></span>  
  
2.  <span data-ttu-id="cadc7-143">Раскройте папку **Агент SQL Server** , а затем — папку **Задания** .</span><span class="sxs-lookup"><span data-stu-id="cadc7-143">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="cadc7-144">Правой кнопкой мыши щелкните задание и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="cadc7-144">Right-click a job, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="cadc7-145">На странице **Шаги** диалогового окна **Свойства задания — \<Job>** выберите действие **Запустить агент**, а затем нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cadc7-145">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="cadc7-146">В диалоговом окне **Свойства шага задания — запустить агент** отредактировать поле **Команда** .</span><span class="sxs-lookup"><span data-stu-id="cadc7-146">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
6.  <span data-ttu-id="cadc7-147">Нажмите кнопку **OK** в обоих диалоговых окнах.</span><span class="sxs-lookup"><span data-stu-id="cadc7-147">Click **OK** on both dialog boxes.</span></span>  
  
### <a name="to-view-and-modify-distribution-agent-and-merge-agent-command-line-parameters-from-replication-monitor"></a><span data-ttu-id="cadc7-148">Просмотр и изменение параметров командной строки агента распространителя и агента слияния из монитора репликации</span><span class="sxs-lookup"><span data-stu-id="cadc7-148">To view and modify Distribution Agent and Merge Agent command line parameters from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="cadc7-149">На левой панели монитора репликации раскройте группу издателей, раскройте нужный издатель, а затем выберите публикацию.</span><span class="sxs-lookup"><span data-stu-id="cadc7-149">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="cadc7-150">Перейдите на вкладку **Все подписки** .</span><span class="sxs-lookup"><span data-stu-id="cadc7-150">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="cadc7-151">Щелкните правой кнопкой мыши подписку, а затем выберите **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="cadc7-151">Right-click a subscription, and then click **View Details**.</span></span>  
  
4.  <span data-ttu-id="cadc7-152">В окне **подписка \< SubscriptionName> \*\* щелкните **действие**и выберите \*\* \<AgentName> Свойства задания**.</span><span class="sxs-lookup"><span data-stu-id="cadc7-152">In the **Subscription \< SubscriptionName>** window, click **Action**, and then click **\<AgentName> Job Properties**.</span></span>  
  
5.  <span data-ttu-id="cadc7-153">На странице **Шаги** диалогового окна **Свойства задания — \<Job>** выберите действие **Запустить агент**, а затем нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cadc7-153">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
6.  <span data-ttu-id="cadc7-154">В диалоговом окне **Свойства шага задания — запустить агент** отредактировать поле **Команда** .</span><span class="sxs-lookup"><span data-stu-id="cadc7-154">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
7.  <span data-ttu-id="cadc7-155">Нажмите кнопку **OK** в обоих диалоговых окнах.</span><span class="sxs-lookup"><span data-stu-id="cadc7-155">Click **OK** on both dialog boxes.</span></span>  
  
### <a name="to-view-and-modify-snapshot-agent-log-reader-agent-and-queue-reader-agent-command-line-parameters-from-replication-monitor"></a><span data-ttu-id="cadc7-156">Просмотр и изменение параметров командной строки агента моментальных снимков, агента чтения журнала и агента чтения очереди из монитора репликации</span><span class="sxs-lookup"><span data-stu-id="cadc7-156">To view and modify Snapshot Agent, Log Reader Agent, and Queue Reader Agent command line parameters from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="cadc7-157">На левой панели монитора репликации раскройте группу издателей, раскройте нужный издатель, а затем выберите публикацию.</span><span class="sxs-lookup"><span data-stu-id="cadc7-157">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="cadc7-158">Перейдите на вкладку **Агенты** .</span><span class="sxs-lookup"><span data-stu-id="cadc7-158">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="cadc7-159">Щелкните правой кнопкой мыши агент в сетке, а затем щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="cadc7-159">Right-click an agent in the grid, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="cadc7-160">На странице **Шаги** диалогового окна **Свойства задания — \<Job>** выберите действие **Запустить агент**, а затем нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cadc7-160">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="cadc7-161">В диалоговом окне **Свойства шага задания — запустить агент** отредактировать поле **Команда** .</span><span class="sxs-lookup"><span data-stu-id="cadc7-161">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
6.  <span data-ttu-id="cadc7-162">Нажмите кнопку **OK** в обоих диалоговых окнах.</span><span class="sxs-lookup"><span data-stu-id="cadc7-162">Click **OK** on both dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cadc7-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="cadc7-163">See Also</span></span>  
 <span data-ttu-id="cadc7-164">[Администрирование агента репликации](replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="cadc7-164">[Replication Agent Administration](replication-agent-administration.md) </span></span>  
 <span data-ttu-id="cadc7-165">[Основные понятия исполняемых файлов агента репликации](../concepts/replication-agent-executables-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="cadc7-165">[Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) </span></span>  
 [<span data-ttu-id="cadc7-166">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="cadc7-166">Replication Agents Overview</span></span>](replication-agents-overview.md)  
  
  
