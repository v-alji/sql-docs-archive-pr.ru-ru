---
title: Цель «кольцевой буфер» | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events], ring buffer target
- ring buffer target [SQL Server extended events]
ms.assetid: 54494e11-b56b-43b7-aa5e-c8724e56b251
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 186e847bb9f9b621543119c25510dc5d6107e274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667374"
---
# <a name="ring-buffer-target"></a><span data-ttu-id="7061a-102">Цель «Кольцевой буфер»</span><span class="sxs-lookup"><span data-stu-id="7061a-102">Ring Buffer Target</span></span>
  <span data-ttu-id="7061a-103">Цель «Кольцевой буфер» кратковременно хранит данные о событиях в памяти.</span><span class="sxs-lookup"><span data-stu-id="7061a-103">The ring buffer target briefly holds event data in memory.</span></span> <span data-ttu-id="7061a-104">Данная цель может управлять событиями в одном из двух режимов.</span><span class="sxs-lookup"><span data-stu-id="7061a-104">This target can manage events in one of two modes.</span></span>  
  
-   <span data-ttu-id="7061a-105">Первый режим — это режим, «первым поступил — первым обслужен» (FIFO), когда при заполнении всей памяти, выделенной цели, теряется событие, которое было добавлено первым.</span><span class="sxs-lookup"><span data-stu-id="7061a-105">The first mode is strict first-in first-out (FIFO), where the oldest event is discarded when all the memory allocated to the target is used.</span></span> <span data-ttu-id="7061a-106">В данном режиме (режим по умолчанию) для параметра occurrence_number задается значение 0.</span><span class="sxs-lookup"><span data-stu-id="7061a-106">In this mode (the default), the occurrence_number option is set to 0.</span></span>  
  
-   <span data-ttu-id="7061a-107">Второй режим — это режим FIFO по видам событий, в котором хранится только определенное число событий каждого типа.</span><span class="sxs-lookup"><span data-stu-id="7061a-107">The second mode is per-event FIFO, where a specified number of events of each type is kept.</span></span> <span data-ttu-id="7061a-108">В этом режиме при использовании всей памяти, выделенной для целевого объекта, удаляются самые старые события каждого типа.</span><span class="sxs-lookup"><span data-stu-id="7061a-108">In this mode, the oldest events of each type are discarded when all the memory allocated to the target is used.</span></span> <span data-ttu-id="7061a-109">Параметр occurrence_number можно изменить, чтобы указать количество событий каждого типа, которые следует сохранять.</span><span class="sxs-lookup"><span data-stu-id="7061a-109">You can configure the occurrence_number option to specify the number of events of each type to keep.</span></span>  
  
 <span data-ttu-id="7061a-110">В следующей таблице приведены доступные параметры для настройки цели «Кольцевой буфер».</span><span class="sxs-lookup"><span data-stu-id="7061a-110">The following table describes the available options for configuring the ring buffer target.</span></span>  
  
|<span data-ttu-id="7061a-111">Параметр</span><span class="sxs-lookup"><span data-stu-id="7061a-111">Option</span></span>|<span data-ttu-id="7061a-112">Допустимые значения</span><span class="sxs-lookup"><span data-stu-id="7061a-112">Allowed values</span></span>|<span data-ttu-id="7061a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7061a-113">Description</span></span>|  
|------------|--------------------|-----------------|  
|<span data-ttu-id="7061a-114">max_memory</span><span class="sxs-lookup"><span data-stu-id="7061a-114">max_memory</span></span>|<span data-ttu-id="7061a-115">Любое 32-разрядное целое число.</span><span class="sxs-lookup"><span data-stu-id="7061a-115">Any 32-bit integer.</span></span> <span data-ttu-id="7061a-116">Это значение является необязательным.</span><span class="sxs-lookup"><span data-stu-id="7061a-116">This value is optional.</span></span>|<span data-ttu-id="7061a-117">Максимальный объем памяти в килобайтах (КБ), который будет использован.</span><span class="sxs-lookup"><span data-stu-id="7061a-117">The maximum amount of memory in kilobytes (KB) to use.</span></span> <span data-ttu-id="7061a-118">Существующие события удаляются в соответствии с первым достигнутым ограничением — max_event_limit или max_memory.</span><span class="sxs-lookup"><span data-stu-id="7061a-118">Existing events are dropped based on the limit that is first reached: max_event_limit or max_memory.</span></span> <span data-ttu-id="7061a-119">Максимальное значение — 4194303 КБ.</span><span class="sxs-lookup"><span data-stu-id="7061a-119">The maximum value is 4194303 KB.</span></span> <span data-ttu-id="7061a-120">Необходимо тщательно рассмотреть вопрос, чтобы задать для размера кольцевого буфера ограничения в диапазоне от ГБ, так как это может повлиять на других потребителей памяти в SQL Server</span><span class="sxs-lookup"><span data-stu-id="7061a-120">A careful consideration should be made before setting the ring buffer size to limits in the GB range as it may impact other memory consumers in SQL Server</span></span>|  
|<span data-ttu-id="7061a-121">max_event_limit</span><span class="sxs-lookup"><span data-stu-id="7061a-121">max_event_limit</span></span>|<span data-ttu-id="7061a-122">Любое 32-разрядное целое число.</span><span class="sxs-lookup"><span data-stu-id="7061a-122">Any 32-bit integer.</span></span> <span data-ttu-id="7061a-123">Это значение является необязательным.</span><span class="sxs-lookup"><span data-stu-id="7061a-123">This value is optional.</span></span>|<span data-ttu-id="7061a-124">Максимальное количество событий, которые хранятся в ring_buffer.</span><span class="sxs-lookup"><span data-stu-id="7061a-124">The maximum number of events kept in the ring_buffer.</span></span> <span data-ttu-id="7061a-125">Существующие события удаляются в соответствии с первым достигнутым ограничением — max_event_limit или max_memory.</span><span class="sxs-lookup"><span data-stu-id="7061a-125">Existing events are dropped based on the limit that is first reached: max_event_limit or max_memory.</span></span> <span data-ttu-id="7061a-126">По умолчанию — 1000.</span><span class="sxs-lookup"><span data-stu-id="7061a-126">Default = 1000.</span></span>|  
|<span data-ttu-id="7061a-127">occurrence_number</span><span class="sxs-lookup"><span data-stu-id="7061a-127">occurrence_number</span></span>|<span data-ttu-id="7061a-128">Принимает одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="7061a-128">One of the following values:</span></span><br /><br /> <span data-ttu-id="7061a-129">0 (по умолчанию) — если вся выделенная цели память использована, то самое старое событие удаляется.</span><span class="sxs-lookup"><span data-stu-id="7061a-129">0 (the default) = Oldest event is discarded when all the memory allocated to the target is used.</span></span><br /><br /> <span data-ttu-id="7061a-130">Любое 32-разрядное целое число — число событий каждого типа, которые должны быть сохранятся, прежде чем они будут отброшены на основе каждого события FIFO.</span><span class="sxs-lookup"><span data-stu-id="7061a-130">Any 32-bit integer = The number of events of each type to keep before being discarded on a per-event FIFO basis.</span></span><br /><br /> <br /><br /> <span data-ttu-id="7061a-131">Это значение является необязательным.</span><span class="sxs-lookup"><span data-stu-id="7061a-131">This value is optional.</span></span>|<span data-ttu-id="7061a-132">Режим FIFO, который будет применяться, а также (в случае если установлено значение больше 0) предпочитаемое число событий каждого типа, которые следует сохранять в буфере.</span><span class="sxs-lookup"><span data-stu-id="7061a-132">The FIFO mode to use, and, if set to a value greater than 0, the preferred number of events of each type to keep in the buffer.</span></span>|
| &nbsp; | &nbsp; | &nbsp; |
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="7061a-133">Добавление цели к сеансу</span><span class="sxs-lookup"><span data-stu-id="7061a-133">Adding the Target to a Session</span></span>  
 <span data-ttu-id="7061a-134">Для добавления цели «Кольцевой буфер» в сеанс расширенных событий следует использовать одну из следующих инструкций при создании или изменении сеанса события.</span><span class="sxs-lookup"><span data-stu-id="7061a-134">To add the ring buffer target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```sql
ADD TARGET package0.ring_buffer  
```  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="7061a-135">Просмотр целевого вывода</span><span class="sxs-lookup"><span data-stu-id="7061a-135">Reviewing the Target Output</span></span>  
 <span data-ttu-id="7061a-136">Для просмотра результата цели "Кольцевой буфер" можно воспользоваться следующим запросом, заменив параметр *session_name* именем сеанса события.</span><span class="sxs-lookup"><span data-stu-id="7061a-136">To review the output from the ring buffer target, you can use the following query, replacing *session_name* with the name of the event session.</span></span>  
  
```sql
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="7061a-137">В следующем примере показан выходной формат цели «Кольцевой буфер».</span><span class="sxs-lookup"><span data-stu-id="7061a-137">The following example shows the ring buffer target output format.</span></span>  
  
```  
<RingBufferTarget eventsPerSec="" processingTime="" totalEventsProcessed="" eventCount="" droppedCount="" memoryUsed="">  
 <event name="" package="" id="" version="" timestamp="">  
    <data name="">  
      <type name="" package="" />  
      <value></value>  
      <text></text>  
    </data>  
    <action name="" package="">  
      <type name="" package="" />  
      <value></value>  
      <text></text>  
    </action>  
  </event>  
</RingBufferTarget>  
```


## <a name="see-also"></a><span data-ttu-id="7061a-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="7061a-138">See Also</span></span>

- [<span data-ttu-id="7061a-139">Цели расширенных событий SQL Server</span><span class="sxs-lookup"><span data-stu-id="7061a-139">SQL Server Extended Events Targets</span></span>](../../2014/database-engine/sql-server-extended-events-targets.md)
- [<span data-ttu-id="7061a-140">sys.dm_xe_session_targets (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7061a-140">sys.dm_xe_session_targets &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql?view=sql-server-2016)
- [<span data-ttu-id="7061a-141">CREATE EVENT SESSION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7061a-141">CREATE EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-event-session-transact-sql?view=sql-server-2016)
- [<span data-ttu-id="7061a-142">ALTER EVENT SESSION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7061a-142">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](https://docs.microsoft.com/sql/t-sql/statements/alter-event-session-transact-sql?view=sql-server-2016)

