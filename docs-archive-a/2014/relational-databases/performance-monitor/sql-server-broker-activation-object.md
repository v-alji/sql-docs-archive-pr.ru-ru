---
title: Объект активации брокера (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Broker Activation
- Broker Activation object
ms.assetid: cd9b6880-c924-42c7-b333-09c303317c0b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4048c2baecaeb4bde7a1e215a15e8c51a60a01bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731554"
---
# <a name="sql-server-broker-activation-object"></a><span data-ttu-id="819fe-102">SQL Server, объект Broker Activation</span><span class="sxs-lookup"><span data-stu-id="819fe-102">SQL Server, Broker Activation Object</span></span>
  <span data-ttu-id="819fe-103">Объект производительности **SQLServer:BrokerActivation** содержит счетчики производительности, возвращающие сведения об активации хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="819fe-103">The **SQLServer:BrokerActivation** performance object contains performance counters that report information on stored procedure activation.</span></span> <span data-ttu-id="819fe-104">В следующей таблице перечислены счетчики этого объекта.</span><span class="sxs-lookup"><span data-stu-id="819fe-104">The table below lists the counters that this object contains.</span></span>  
  
|<span data-ttu-id="819fe-105">Счетчики SQL Server Broker Activation</span><span class="sxs-lookup"><span data-stu-id="819fe-105">SQL Server Broker Activation counters</span></span>|<span data-ttu-id="819fe-106">Описание</span><span class="sxs-lookup"><span data-stu-id="819fe-106">Description</span></span>|  
|-------------------------------------------|-----------------|  
|<span data-ttu-id="819fe-107">**Количество вызовов хранимых процедур/сек**</span><span class="sxs-lookup"><span data-stu-id="819fe-107">**Stored Procedures Invoked/sec**</span></span>|<span data-ttu-id="819fe-108">Этот счетчик возвращает общее количество хранимых процедур активации, вызываемых мониторами очереди в этом экземпляре за секунду.</span><span class="sxs-lookup"><span data-stu-id="819fe-108">This counter reports the total number of activation stored procedures invoked by all queue monitors in the instance per second.</span></span>|  
|<span data-ttu-id="819fe-109">**Достигнут предел задач**</span><span class="sxs-lookup"><span data-stu-id="819fe-109">**Task Limit Reached**</span></span>|<span data-ttu-id="819fe-110">Этот счетчик возвращает общее число раз, когда монитор очереди должен был запустить новую задачу, но не сделал этого, так как уже выполнялось максимальное число задач для очереди.</span><span class="sxs-lookup"><span data-stu-id="819fe-110">This counter reports the total number of times that a queue monitor would have started a new task, but did not because the maximum number of tasks for the queue is already running.</span></span>|  
|<span data-ttu-id="819fe-111">**Достигнут предел задач/сек**</span><span class="sxs-lookup"><span data-stu-id="819fe-111">**Task Limit Reached/sec**</span></span>|<span data-ttu-id="819fe-112">Этот счетчик сообщает, сколько раз в секунду монитор очереди должен был запустить новую задачу, но не сделал этого, так как уже выполнялось максимальное число задач для очереди.</span><span class="sxs-lookup"><span data-stu-id="819fe-112">This counter reports the number of times per second that a queue monitor would have started a new task, but did not because the maximum number of tasks for the queue is already running.</span></span>|  
|<span data-ttu-id="819fe-113">**Прервано задач/сек**</span><span class="sxs-lookup"><span data-stu-id="819fe-113">**Tasks Aborted/sec**</span></span>|<span data-ttu-id="819fe-114">Этот счетчик возвращает число задач хранимых процедур активации, завершившихся с ошибкой, либо тех, которые были прерваны монитором очереди из-за невозможности получать сообщения.</span><span class="sxs-lookup"><span data-stu-id="819fe-114">This counter reports the number of activation stored procedure tasks that end with an error, or are aborted by a queue monitor for failing to receive messages.</span></span>|  
|<span data-ttu-id="819fe-115">**Задач работает**</span><span class="sxs-lookup"><span data-stu-id="819fe-115">**Tasks Running**</span></span>|<span data-ttu-id="819fe-116">Этот счетчик возвращает число хранимых процедур активации, работающих в настоящий момент.</span><span class="sxs-lookup"><span data-stu-id="819fe-116">This counter reports the number of activation stored procedures that are currently running.</span></span>|  
|<span data-ttu-id="819fe-117">**Задач запущено/сек**</span><span class="sxs-lookup"><span data-stu-id="819fe-117">**Tasks Started/sec**</span></span>|<span data-ttu-id="819fe-118">Этот счетчик возвращает число хранимых процедур активации, запущенных за секунду всеми мониторами очереди в этом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="819fe-118">This counter reports the number of activation stored procedures started per second by all queue monitors in the instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="819fe-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="819fe-119">See Also</span></span>  
 <span data-ttu-id="819fe-120">[sys.dm_broker_activated_tasks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="819fe-120">[sys.dm_broker_activated_tasks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql) </span></span>  
 <span data-ttu-id="819fe-121">[sys.dm_broker_queue_monitors (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="819fe-121">[sys.dm_broker_queue_monitors &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql) </span></span>  
 [<span data-ttu-id="819fe-122">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="819fe-122">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
