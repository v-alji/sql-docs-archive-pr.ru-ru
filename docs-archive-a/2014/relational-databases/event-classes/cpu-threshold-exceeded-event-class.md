---
title: Класс событий CPU Threshold Exceeded | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- CPU Threshold Exceeded Event Class
ms.assetid: eb106f7d-baa3-4a2b-96b2-f9fe0844057d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07b51e1a6f08f48c601b00d2dcb67bc6d09006f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655766"
---
# <a name="cpu-threshold-exceeded-event-class"></a><span data-ttu-id="2fe04-102">класс событий CPU Threshold Exceeded</span><span class="sxs-lookup"><span data-stu-id="2fe04-102">CPU Threshold Exceeded Event Class</span></span>
  <span data-ttu-id="2fe04-103">Класс событий CPU Threshold Exceeded указывает, что регулятор ресурсов обнаружил запрос, превышающий пороговое значение ЦП, заданное параметром REQUEST_MAX_CPU_TIME_SEC.</span><span class="sxs-lookup"><span data-stu-id="2fe04-103">The CPU Threshold Exceeded event class indicates that Resource Governor detects a query that exceeds the CPU threshold specified for REQUEST_MAX_CPU_TIME_SEC.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2fe04-104">Интервал обнаружения для этого события — пять секунд.</span><span class="sxs-lookup"><span data-stu-id="2fe04-104">The detection interval for this event is five seconds.</span></span> <span data-ttu-id="2fe04-105">Это событие гарантированно создается в том случае, если запрос превышает указанное ограничение в течение более чем пяти секунд.</span><span class="sxs-lookup"><span data-stu-id="2fe04-105">It is guaranteed that an event will be generated if a query exceeds the specified limit by at least five seconds.</span></span> <span data-ttu-id="2fe04-106">Однако, если запрос превышает указанное пороговое значение в течение меньшего времени, его обнаружение может быть пропущено в зависимости от времени поступления запроса и времени последнего прохода.</span><span class="sxs-lookup"><span data-stu-id="2fe04-106">However, if a query exceeds the specified threshold by less than five seconds, its detection might be missed depending on the timing of the query and the time of last detection sweep.</span></span>  
  
## <a name="cpu-threshold-exceeded-data-columns"></a><span data-ttu-id="2fe04-107">Столбцы данных класса событий CPU Threshold Exceeded</span><span class="sxs-lookup"><span data-stu-id="2fe04-107">CPU Threshold Exceeded Data Columns</span></span>  
  
|<span data-ttu-id="2fe04-108">Имя столбца данных</span><span class="sxs-lookup"><span data-stu-id="2fe04-108">Data column name</span></span>|<span data-ttu-id="2fe04-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2fe04-109">Data type</span></span>|<span data-ttu-id="2fe04-110">Description</span><span class="sxs-lookup"><span data-stu-id="2fe04-110">Description</span></span>|<span data-ttu-id="2fe04-111">Идентификатор столбца</span><span class="sxs-lookup"><span data-stu-id="2fe04-111">Column ID</span></span>|<span data-ttu-id="2fe04-112">Фильтруемый</span><span class="sxs-lookup"><span data-stu-id="2fe04-112">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="2fe04-113">ЦП</span><span class="sxs-lookup"><span data-stu-id="2fe04-113">CPU</span></span>|`int`|<span data-ttu-id="2fe04-114">Использование ЦП в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="2fe04-114">CPU usage in milliseconds.</span></span>|<span data-ttu-id="2fe04-115">18</span><span class="sxs-lookup"><span data-stu-id="2fe04-115">18</span></span>|<span data-ttu-id="2fe04-116">Да</span><span class="sxs-lookup"><span data-stu-id="2fe04-116">Yes</span></span>|  
|<span data-ttu-id="2fe04-117">EventClass</span><span class="sxs-lookup"><span data-stu-id="2fe04-117">EventClass</span></span>|`int`|<span data-ttu-id="2fe04-118">214</span><span class="sxs-lookup"><span data-stu-id="2fe04-118">214</span></span>|<span data-ttu-id="2fe04-119">27</span><span class="sxs-lookup"><span data-stu-id="2fe04-119">27</span></span>|<span data-ttu-id="2fe04-120">Нет</span><span class="sxs-lookup"><span data-stu-id="2fe04-120">No</span></span>|  
|<span data-ttu-id="2fe04-121">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="2fe04-121">EventSubClass</span></span>|`int`|<span data-ttu-id="2fe04-122">Нарушение ограничения ЦП.</span><span class="sxs-lookup"><span data-stu-id="2fe04-122">CPU limit violation.</span></span>|<span data-ttu-id="2fe04-123">21</span><span class="sxs-lookup"><span data-stu-id="2fe04-123">21</span></span>|<span data-ttu-id="2fe04-124">Да</span><span class="sxs-lookup"><span data-stu-id="2fe04-124">Yes</span></span>|  
|<span data-ttu-id="2fe04-125">GroupID</span><span class="sxs-lookup"><span data-stu-id="2fe04-125">GroupID</span></span>|`int`|<span data-ttu-id="2fe04-126">Идентификатор группы, в которой произошло нарушение.</span><span class="sxs-lookup"><span data-stu-id="2fe04-126">Group ID where the violation occurred.</span></span>|<span data-ttu-id="2fe04-127">66</span><span class="sxs-lookup"><span data-stu-id="2fe04-127">66</span></span>|<span data-ttu-id="2fe04-128">Да</span><span class="sxs-lookup"><span data-stu-id="2fe04-128">Yes</span></span>|  
|<span data-ttu-id="2fe04-129">OwnerID</span><span class="sxs-lookup"><span data-stu-id="2fe04-129">OwnerID</span></span>|`int`|<span data-ttu-id="2fe04-130">Идентификатор SPID процесса, который вызвал нарушение.</span><span class="sxs-lookup"><span data-stu-id="2fe04-130">SPID of the process that caused the violation.</span></span>|<span data-ttu-id="2fe04-131">58</span><span class="sxs-lookup"><span data-stu-id="2fe04-131">58</span></span>|<span data-ttu-id="2fe04-132">Да</span><span class="sxs-lookup"><span data-stu-id="2fe04-132">Yes</span></span>|  
|<span data-ttu-id="2fe04-133">SPID</span><span class="sxs-lookup"><span data-stu-id="2fe04-133">SPID</span></span>|`int`|<span data-ttu-id="2fe04-134">Идентификатор процесса сервера, запустившего данное событие.</span><span class="sxs-lookup"><span data-stu-id="2fe04-134">ID of the server process that fires this event.</span></span><br /><br /> <span data-ttu-id="2fe04-135">Примечание. Он может отличаться от действительного пользовательского идентификатора SPID, если в потоке операционной системы проверка использования ЦП является фоновой задачей.</span><span class="sxs-lookup"><span data-stu-id="2fe04-135">Note: This can differ from the actual user SPID if a system thread validates CPU usage as a background task.</span></span>|<span data-ttu-id="2fe04-136">12</span><span class="sxs-lookup"><span data-stu-id="2fe04-136">12</span></span>|<span data-ttu-id="2fe04-137">Да</span><span class="sxs-lookup"><span data-stu-id="2fe04-137">Yes</span></span>|  
|<span data-ttu-id="2fe04-138">StartTime</span><span class="sxs-lookup"><span data-stu-id="2fe04-138">StartTime</span></span>|`datetime`|<span data-ttu-id="2fe04-139">Время срабатывания события.</span><span class="sxs-lookup"><span data-stu-id="2fe04-139">The time when this event fired.</span></span>|<span data-ttu-id="2fe04-140">14</span><span class="sxs-lookup"><span data-stu-id="2fe04-140">14</span></span>|<span data-ttu-id="2fe04-141">Да</span><span class="sxs-lookup"><span data-stu-id="2fe04-141">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2fe04-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="2fe04-142">See Also</span></span>  
 [<span data-ttu-id="2fe04-143">Хранимая процедура sp_trace_setevent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2fe04-143">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
