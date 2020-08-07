---
title: Наблюдение за репликацией | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], about monitoring replication
- transactional replication, monitoring
- monitoring [SQL Server replication]
- merge replication monitoring [SQL Server replication]
- snapshot replication [SQL Server], monitoring
- replication [SQL Server], monitoring
- administering replication, monitoring
ms.assetid: f182f43a-6af8-45bc-a708-08d5f7a6984a
author: rothja
ms.author: jroth
ms.openlocfilehash: df2760e4ce04c95f38ceb9dfe9fa9f79c4c467f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733978"
---
# <a name="monitoring-replication"></a><span data-ttu-id="9d79d-102">Наблюдение (репликация)</span><span class="sxs-lookup"><span data-stu-id="9d79d-102">Monitoring (Replication)</span></span>
  <span data-ttu-id="9d79d-103">Наблюдение за топологией репликации является важным аспектом развертывания репликации.</span><span class="sxs-lookup"><span data-stu-id="9d79d-103">Monitoring a replication topology is an important aspect of deploying replication.</span></span> <span data-ttu-id="9d79d-104">Так как активность репликации является распределенной, важно отслеживать активность и состояние всех компьютеров, участвующих в репликации.</span><span class="sxs-lookup"><span data-stu-id="9d79d-104">Because replication activity is distributed, it is essential to track activity and status across all computers involved in replication.</span></span> <span data-ttu-id="9d79d-105">Для наблюдения за репликацией можно использовать следующие средства:</span><span class="sxs-lookup"><span data-stu-id="9d79d-105">The following tools can be used to monitor replication:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)]<span data-ttu-id="9d79d-106">[!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)]Монитор репликации</span><span class="sxs-lookup"><span data-stu-id="9d79d-106">[!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)] Replication Monitor</span></span>  
  
     <span data-ttu-id="9d79d-107">Монитор репликации является самым важным средством наблюдения за репликацией, представляющим ориентированное на издателя представление всех действий, связанных с репликацией.</span><span class="sxs-lookup"><span data-stu-id="9d79d-107">Replication Monitor is the most important tool for monitoring replication, presenting a Publisher-focused view of all replication activity.</span></span> <span data-ttu-id="9d79d-108">Дополнительные сведения см. в статье [мониторинг производительности с помощью монитора репликации](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9d79d-108">For more information, see [Monitor performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)] <span data-ttu-id="9d79d-109">[!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d79d-109">[!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]</span></span>  
  
     <span data-ttu-id="9d79d-110">Среда[!INCLUDE[ssManStudio](../../includes/ssManStudio-md.md)] предоставляет доступ к монитору репликации.</span><span class="sxs-lookup"><span data-stu-id="9d79d-110">[!INCLUDE[ssManStudio](../../includes/ssManStudio-md.md)] provides access to Replication Monitor.</span></span> <span data-ttu-id="9d79d-111">Здесь же существует возможность просмотра текущего состояния и последнего сообщения, записанного в журнал следующими агентами, а также здесь можно запускать и останавливать все агенты: агент чтения журнала, агент моментальных снимков, агент слияния и агент распространения.</span><span class="sxs-lookup"><span data-stu-id="9d79d-111">It also allows you to view the current status and last message logged by the following agents and allows you start and stop each agent: Log Reader Agent, Snapshot Agent, Merge Agent, and Distribution Agent.</span></span> <span data-ttu-id="9d79d-112">Дополнительные сведения см. в статье [Monitor Replication Agents](monitor/monitor-replication-agents.md).</span><span class="sxs-lookup"><span data-stu-id="9d79d-112">For more information, see [Monitor Replication Agents](monitor/monitor-replication-agents.md).</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="9d79d-113">и объекты управления репликацией (RMO)</span><span class="sxs-lookup"><span data-stu-id="9d79d-113">and Replication Management Objects (RMO)</span></span>  
  
     <span data-ttu-id="9d79d-114">Оба интерфейса позволяют наблюдать с распространителя за репликациями всех типов.</span><span class="sxs-lookup"><span data-stu-id="9d79d-114">Both interfaces allow you to monitor all types of replication from the Distributor.</span></span> <span data-ttu-id="9d79d-115">Репликация слиянием также предоставляет возможность наблюдения за репликацией с подписчика.</span><span class="sxs-lookup"><span data-stu-id="9d79d-115">Merge replication also provides the ability to monitor replication from the Subscriber.</span></span>  
  
-   <span data-ttu-id="9d79d-116">Предупреждения для событий агентов репликации</span><span class="sxs-lookup"><span data-stu-id="9d79d-116">Alerts for replication agent events</span></span>  
  
     <span data-ttu-id="9d79d-117">Репликации предоставляют ряд предопределенных предупреждений о событиях агентов репликаций. Кроме этого, в случае необходимости можно создать дополнительные предупреждения.</span><span class="sxs-lookup"><span data-stu-id="9d79d-117">Replication provides a number of predefined alerts for replication agent events, and you can create additional alerts if necessary.</span></span> <span data-ttu-id="9d79d-118">Предупреждения используются для запуска автоматического ответа на событие и для уведомления администратора.</span><span class="sxs-lookup"><span data-stu-id="9d79d-118">Alerts can be used to trigger an automated response to an event and/or notify an administrator.</span></span> <span data-ttu-id="9d79d-119">Дополнительные сведения см. в статье [Использование предупреждений для событий агента репликации](agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="9d79d-119">For more information, see [Use Alerts for Replication Agent Events](agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
-   <span data-ttu-id="9d79d-120">Системный монитор</span><span class="sxs-lookup"><span data-stu-id="9d79d-120">System Monitor</span></span>  
  
     <span data-ttu-id="9d79d-121">Системный монитор может использоваться для наблюдения за производительностью, предоставляя ряд счетчиков для репликаций.</span><span class="sxs-lookup"><span data-stu-id="9d79d-121">System Monitor can be useful for monitoring performance, providing a number of counters for replication.</span></span> <span data-ttu-id="9d79d-122">Дополнительные сведения см. в статье [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9d79d-122">For more information, see [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d79d-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="9d79d-123">See Also</span></span>  
 <span data-ttu-id="9d79d-124">[Вопросы и ответы об администрировании репликации](administration/frequently-asked-questions-for-replication-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="9d79d-124">[Replication Administration FAQ](administration/frequently-asked-questions-for-replication-administrators.md) </span></span>  
 [<span data-ttu-id="9d79d-125">Best Practices for Replication Administration</span><span class="sxs-lookup"><span data-stu-id="9d79d-125">Best Practices for Replication Administration</span></span>](administration/best-practices-for-replication-administration.md)   

  
  
