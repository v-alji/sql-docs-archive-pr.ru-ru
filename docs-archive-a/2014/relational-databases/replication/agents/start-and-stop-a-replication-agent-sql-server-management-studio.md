---
title: Запуск и остановка агента репликации (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], stopping
- agents [SQL Server replication], starting
ms.assetid: 97977c4a-8c7c-4a22-9480-69aa812bd1e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b40e329e0f04e8a54a2d5a40c30aff418da2cd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655662"
---
# <a name="start-and-stop-a-replication-agent-sql-server-management-studio"></a><span data-ttu-id="bc250-102">Запуск и остановка агента репликации (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="bc250-102">Start and Stop a Replication Agent (SQL Server Management Studio)</span></span>
  <span data-ttu-id="bc250-103">Запуск и остановка агентов выполняется из папки **Задания** и папки **Репликация** в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] и из монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="bc250-103">Start and stop agents from the **Jobs** folder and the **Replication** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from Replication Monitor.</span></span> <span data-ttu-id="bc250-104">Могут запускаться и останавливаться следующие агенты и задания:</span><span class="sxs-lookup"><span data-stu-id="bc250-104">Start and stop the following agents and jobs:</span></span>  
  
-   <span data-ttu-id="bc250-105">Агент моментальных снимков, используемый всеми публикациями.</span><span class="sxs-lookup"><span data-stu-id="bc250-105">The Snapshot Agent, which is used by all publications.</span></span>  
  
-   <span data-ttu-id="bc250-106">Агент чтения журналов, используемый всеми публикациями транзакций.</span><span class="sxs-lookup"><span data-stu-id="bc250-106">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
-   <span data-ttu-id="bc250-107">Агент чтения очереди, используемый публикациями транзакций, активированными для подписок, обновляемых посредством очередей.</span><span class="sxs-lookup"><span data-stu-id="bc250-107">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="bc250-108">Агент распространителя, синхронизирующий подписки на публикации транзакций и моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="bc250-108">The Distribution Agent, which synchronizes subscriptions to transactional and snapshot publications.</span></span>  
  
-   <span data-ttu-id="bc250-109">Агент слияния, синхронизирующий подписки на публикации слиянием.</span><span class="sxs-lookup"><span data-stu-id="bc250-109">The Merge Agent, which synchronizes subscriptions to merge publications.</span></span>  
  
-   <span data-ttu-id="bc250-110">Задания по обслуживанию репликации.</span><span class="sxs-lookup"><span data-stu-id="bc250-110">Replication maintenance jobs.</span></span>  
  
 <span data-ttu-id="bc250-111">Дополнительные сведения о запуске агента слияния и агента распространения см. в статьях [Синхронизация принудительной подписки](../synchronize-a-push-subscription.md) и [Синхронизация подписки по запросу](../synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="bc250-111">For more information about starting the Merge Agent and the Distribution Agent, see [Synchronize a Push Subscription](../synchronize-a-push-subscription.md) and [Synchronize a Pull Subscription](../synchronize-a-pull-subscription.md).</span></span> <span data-ttu-id="bc250-112">Дополнительные сведения о заданиях обслуживания см. в статье [Запуск заданий по обслуживанию репликаций (среда SQL Server Management Studio)](../../../ssms/sql-server-management-studio-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="bc250-112">For more information about maintenance jobs, see [Run Replication Maintenance Jobs &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md).</span></span>  
  
 <span data-ttu-id="bc250-113">Сведения о запуске монитора репликации см. в [этой статье](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="bc250-113">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span>  
  
### <a name="to-start-and-stop-a-snapshot-agent-or-log-reader-agent-from-management-studio"></a><span data-ttu-id="bc250-114">Запуск и остановка агента моментальных снимков или агента чтения журналов из среды Management Studio</span><span class="sxs-lookup"><span data-stu-id="bc250-114">To start and stop a Snapshot Agent or Log Reader Agent from Management Studio</span></span>  
  
1.  <span data-ttu-id="bc250-115">Подключитесь к издателю в [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], а затем раскройте узел сервера и папку **Репликация** .</span><span class="sxs-lookup"><span data-stu-id="bc250-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node and the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="bc250-116">Раскройте папку **Локальные публикации** , затем щелкните правой кнопкой публикацию.</span><span class="sxs-lookup"><span data-stu-id="bc250-116">Expand the **Local Publications** folder, and then right-click a publication.</span></span>  
  
3.  <span data-ttu-id="bc250-117">Щелкните **Просмотреть состояние агента моментальных снимков** или **Просмотреть состояние агента чтения журнала**.</span><span class="sxs-lookup"><span data-stu-id="bc250-117">Click **View Snapshot Agent Status** or **View Log Reader Agent Status**.</span></span>  
  
4.  <span data-ttu-id="bc250-118">Щелкните **Пуск** или **Стоп**.</span><span class="sxs-lookup"><span data-stu-id="bc250-118">Click **Start** or **Stop**.</span></span>  
  
### <a name="to-start-and-stop-a-queue-reader-agent-from-management-studio"></a><span data-ttu-id="bc250-119">Запуск и остановка агента чтения очереди из среды Management Studio</span><span class="sxs-lookup"><span data-stu-id="bc250-119">To start and stop a Queue Reader Agent from Management Studio</span></span>  
  
1.  <span data-ttu-id="bc250-120">Подключитесь к распространителю в [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]и разверните узел сервера.</span><span class="sxs-lookup"><span data-stu-id="bc250-120">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="bc250-121">Раскройте папку **Агент SQL Server** , а затем — папку **Задания** .</span><span class="sxs-lookup"><span data-stu-id="bc250-121">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="bc250-122">Щелкните правой кнопкой задание для агента и выберите пункт **Запустить задание** или **Остановить задание**.</span><span class="sxs-lookup"><span data-stu-id="bc250-122">Right-click the job for the agent, and then click **Start Job** or **Stop Job**.</span></span> <span data-ttu-id="bc250-123">Имя задания для агента чтения очереди имеет следующий формат: **[\<Distributor>].\<integer>** .</span><span class="sxs-lookup"><span data-stu-id="bc250-123">The name of the job for the Queue Reader Agent is in the form **[\<Distributor>].\<integer>**.</span></span>  
  
### <a name="to-start-and-stop-a-snapshot-agent-log-reader-agent-or-queue-reader-agent-from-replication-monitor"></a><span data-ttu-id="bc250-124">Запуск и остановка агента моментальных снимков, агента чтения журнала или агента чтения очереди из монитора репликации</span><span class="sxs-lookup"><span data-stu-id="bc250-124">To start and stop a Snapshot Agent, Log Reader Agent, or Queue Reader Agent from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="bc250-125">Раскройте на левой панели группу издателей, раскройте издатель и выберите нужную публикацию.</span><span class="sxs-lookup"><span data-stu-id="bc250-125">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="bc250-126">Перейдите на вкладку **Агенты** .</span><span class="sxs-lookup"><span data-stu-id="bc250-126">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="bc250-127">Щелкните правой кнопкой агент и затем щелкните **Запустить агент** или **Остановить агент**.</span><span class="sxs-lookup"><span data-stu-id="bc250-127">Right-click an agent, and then click **Start Agent** or **Stop Agent**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc250-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="bc250-128">See Also</span></span>  
 <span data-ttu-id="bc250-129">[Наблюдение за репликацией](../monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="bc250-129">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 <span data-ttu-id="bc250-130">[Основные понятия исполняемых файлов агента репликации](../concepts/replication-agent-executables-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="bc250-130">[Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) </span></span>  
 [<span data-ttu-id="bc250-131">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="bc250-131">Replication Agents Overview</span></span>](replication-agents-overview.md)  
  
  
