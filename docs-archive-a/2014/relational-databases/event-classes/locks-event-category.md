---
title: Категория событий Locks | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Locks event category [SQL Server]
- SQL Server event classes, Locks event category
- event classes [SQL Server], Locks event category
- lock escalation [SQL Server], locks event category
ms.assetid: 27d6afa2-7dab-4fe7-a1ad-064b879dc654
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a202279021e3e6c7c3c44a167792bb9439567aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656409"
---
# <a name="locks-event-category"></a><span data-ttu-id="8e201-102">Категория событий Locks</span><span class="sxs-lookup"><span data-stu-id="8e201-102">Locks Event Category</span></span>
  <span data-ttu-id="8e201-103">Классы событий в категории **Locks** применяются для контроля за активностью блокировок в экземпляре [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e201-103">Use the event classes in the **Locks** event category to monitor locking activity in an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="8e201-104">Эти классы событий помогают исследовать связанные с блокировками проблемы, вызванные одновременным чтением и записью данных несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="8e201-104">These event classes can help you investigate locking problems caused by multiple users reading and modifying data concurrently.</span></span>  
  
 <span data-ttu-id="8e201-105">Поскольку компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] часто обрабатывает большое количество блокировок, перехват событий из категории **Блокировки** во время трассировки может существенно увеличить нагрузку и размер файлов и таблиц трассировки.</span><span class="sxs-lookup"><span data-stu-id="8e201-105">Because the [!INCLUDE[ssDE](../../includes/ssde-md.md)] often processes many locks, capturing the **Locks** event classes during a trace can incur significant overhead and result in large trace files or tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e201-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="8e201-106">In This Section</span></span>  
  
|<span data-ttu-id="8e201-107">Раздел</span><span class="sxs-lookup"><span data-stu-id="8e201-107">Topic</span></span>|<span data-ttu-id="8e201-108">Description</span><span class="sxs-lookup"><span data-stu-id="8e201-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8e201-109">Класс событий Deadlock Graph</span><span class="sxs-lookup"><span data-stu-id="8e201-109">Deadlock Graph Event Class</span></span>](deadlock-graph-event-class.md)|<span data-ttu-id="8e201-110">Предоставляет описание взаимоблокировки в формате XML.</span><span class="sxs-lookup"><span data-stu-id="8e201-110">Provides an XML description of a deadlock.</span></span>|  
|[<span data-ttu-id="8e201-111">Класс событий Lock:Acquired</span><span class="sxs-lookup"><span data-stu-id="8e201-111">Lock:Acquired Event Class</span></span>](lock-acquired-event-class.md)|<span data-ttu-id="8e201-112">Указывает, что была получена блокировка ресурса, например строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="8e201-112">Indicates that a lock has been acquired on a resource, such as a row in a table.</span></span>|  
|[<span data-ttu-id="8e201-113">Класс событий Lock:Cancel</span><span class="sxs-lookup"><span data-stu-id="8e201-113">Lock:Cancel Event Class</span></span>](lock-cancel-event-class.md)|<span data-ttu-id="8e201-114">Отслеживает запросы на получение блокировки, которые были отменены до ее получения (например, чтобы избежать взаимоблокировки).</span><span class="sxs-lookup"><span data-stu-id="8e201-114">Tracks requests for locks that were canceled before the lock was acquired (for example, to prevent a deadlock).</span></span>|  
|[<span data-ttu-id="8e201-115">Класс событий Lock:Deadlock Chain</span><span class="sxs-lookup"><span data-stu-id="8e201-115">Lock:Deadlock Chain Event Class</span></span>](lock-deadlock-chain-event-class.md)|<span data-ttu-id="8e201-116">Отслеживает возникновение условий взаимоблокировки и объектов, которые в них участвуют.</span><span class="sxs-lookup"><span data-stu-id="8e201-116">Monitors when deadlock conditions occur and which objects are involved.</span></span>|  
|[<span data-ttu-id="8e201-117">Класс событий Lock:Deadlock</span><span class="sxs-lookup"><span data-stu-id="8e201-117">Lock:Deadlock Event Class</span></span>](lock-deadlock-event-class.md)|<span data-ttu-id="8e201-118">Отслеживает момент, когда транзакция запрашивает блокировку на ресурс, уже блокированный другой транзакцией, в результате чего происходит взаимоблокировка.</span><span class="sxs-lookup"><span data-stu-id="8e201-118">Tracks when a transaction has requested a lock on a resource already locked by another transaction, resulting in a deadlock.</span></span>|  
|[<span data-ttu-id="8e201-119">Класс событий Lock:Escalation</span><span class="sxs-lookup"><span data-stu-id="8e201-119">Lock:Escalation Event Class</span></span>](lock-escalation-event-class.md)|<span data-ttu-id="8e201-120">Указывает, что мелкогранулированная блокировка была преобразована в крупногранулированную.</span><span class="sxs-lookup"><span data-stu-id="8e201-120">Indicates that a finer-grained lock has been converted to a coarser-grained lock.</span></span>|  
|[<span data-ttu-id="8e201-121">Класс событий Lock:Released</span><span class="sxs-lookup"><span data-stu-id="8e201-121">Lock:Released Event Class</span></span>](lock-released-event-class.md)|<span data-ttu-id="8e201-122">Отслеживает освобождение блокировки.</span><span class="sxs-lookup"><span data-stu-id="8e201-122">Tracks when a lock is released.</span></span>|  
|[<span data-ttu-id="8e201-123">Класс событий Lock:Timeout (timeout &#62; 0)</span><span class="sxs-lookup"><span data-stu-id="8e201-123">Lock:Timeout &#40;timeout &#62; 0&#41; Event Class</span></span>](lock-timeout-timeout-0-event-class.md)|<span data-ttu-id="8e201-124">Отслеживает запросы блокировок, которые не удалось выполнить, поскольку запрошенный ресурс был блокирован другой транзакцией.</span><span class="sxs-lookup"><span data-stu-id="8e201-124">Tracks when lock requests cannot be completed because another transaction has a blocking lock on the requested resource.</span></span> <span data-ttu-id="8e201-125">Это событие происходит только тогда, когда время ожидания блокировки больше нуля.</span><span class="sxs-lookup"><span data-stu-id="8e201-125">This event occurs only in situations where the lock time-out value is greater than zero.</span></span>|  
|[<span data-ttu-id="8e201-126">Класс событий Lock:Timeout</span><span class="sxs-lookup"><span data-stu-id="8e201-126">Lock:Timeout Event Class</span></span>](lock-timeout-event-class.md)|<span data-ttu-id="8e201-127">Отслеживает запросы блокировок, которые не удалось выполнить, поскольку запрошенный ресурс был блокирован другой транзакцией.</span><span class="sxs-lookup"><span data-stu-id="8e201-127">Tracks when lock requests cannot be completed because another transaction has a blocking lock on the requested resource.</span></span>|  
  
  
