---
title: Целевой объект связывания событий | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- pairing target [SQL Server extended events]
- event pairing target
- targets [SQL Server extended events], pairing target
ms.assetid: 3c87dcfb-543a-4bd8-a73d-1390bdf4ffa3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a1a6beb1c6996e6e12f16c4555fd9dfcab97617d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732942"
---
# <a name="event-pairing-target"></a><span data-ttu-id="44311-102">Цель «Попарное разбиение событий»</span><span class="sxs-lookup"><span data-stu-id="44311-102">Event Pairing Target</span></span>
  <span data-ttu-id="44311-103">Цель «Попарное разбиение событий» устанавливает соответствие между двумя событиями с помощью одного или нескольких столбцов данных, присутствующих в каждом событии.</span><span class="sxs-lookup"><span data-stu-id="44311-103">The event pairing target matches two events using one or more columns of data that are present in each event.</span></span> <span data-ttu-id="44311-104">Многие события возникают попарно, например получение и снятие блокировки.</span><span class="sxs-lookup"><span data-stu-id="44311-104">Many events come in pairs, for example, lock acquires and lock releases.</span></span> <span data-ttu-id="44311-105">После выделения пары событий оба эти события отбрасываются.</span><span class="sxs-lookup"><span data-stu-id="44311-105">After an event sequence is paired, both events are discarded.</span></span> <span data-ttu-id="44311-106">Исключение парных наборов позволяет легко обнаруживать наличие не снятых блокировок.</span><span class="sxs-lookup"><span data-stu-id="44311-106">Discarding matched sets allows for easy detection of lock acquisitions that have not been released.</span></span>  
  
 <span data-ttu-id="44311-107">С помощью фильтрации на уровне события цель «Попарное разбиение событий» может использоваться только для сбора событий, не соответствующих заранее установленным условиям.</span><span class="sxs-lookup"><span data-stu-id="44311-107">By using event-level filters, the pairing target can be used to only capture events that do not match pre-set criteria.</span></span>  
  
 <span data-ttu-id="44311-108">При использовании цели «Попарное разбиение событий» разрешается выбирать два сопоставляемых события и последовательность столбцов, предназначенных для установки соответствия.</span><span class="sxs-lookup"><span data-stu-id="44311-108">When you use the event pairing target, you can choose two events that will be matched, together with a sequence of columns to perform the matching on.</span></span> <span data-ttu-id="44311-109">Все столбцы такой последовательности должны иметь одинаковый тип.</span><span class="sxs-lookup"><span data-stu-id="44311-109">All the columns in this sequence must be of the same type.</span></span>  
  
 <span data-ttu-id="44311-110">В следующей таблице описаны доступные параметры настройки попарного разбиения событий.</span><span class="sxs-lookup"><span data-stu-id="44311-110">The following table describes the available options for configuring event pairing.</span></span>  
  
|<span data-ttu-id="44311-111">Параметр</span><span class="sxs-lookup"><span data-stu-id="44311-111">Option</span></span>|<span data-ttu-id="44311-112">Допустимые значения</span><span class="sxs-lookup"><span data-stu-id="44311-112">Allowed values</span></span>|<span data-ttu-id="44311-113">Описание</span><span class="sxs-lookup"><span data-stu-id="44311-113">Description</span></span>|  
|------------|--------------------|-----------------|  
|<span data-ttu-id="44311-114">begin_event</span><span class="sxs-lookup"><span data-stu-id="44311-114">begin_event</span></span>|<span data-ttu-id="44311-115">Имя любого события, присутствующего в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="44311-115">Any event name that is present in the current session.</span></span>|<span data-ttu-id="44311-116">Имя события, определяющее начальное событие в парной последовательности.</span><span class="sxs-lookup"><span data-stu-id="44311-116">The event name specifying the beginning event in a paired sequence.</span></span>|  
|<span data-ttu-id="44311-117">end_event</span><span class="sxs-lookup"><span data-stu-id="44311-117">end_event</span></span>|<span data-ttu-id="44311-118">Имя любого события, присутствующего в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="44311-118">Any event name that is present in the current session.</span></span>|<span data-ttu-id="44311-119">Имя события, определяющее завершающее событие в парной последовательности.</span><span class="sxs-lookup"><span data-stu-id="44311-119">The event name specifying the ending event in a paired sequence.</span></span>|  
|<span data-ttu-id="44311-120">begin_matching_columns</span><span class="sxs-lookup"><span data-stu-id="44311-120">begin_matching_columns</span></span>|<span data-ttu-id="44311-121">Упорядоченный список имен столбцов с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="44311-121">A comma-delimited, ordered list of column names.</span></span>|<span data-ttu-id="44311-122">Столбцы, по которым выполняется установка соответствия.</span><span class="sxs-lookup"><span data-stu-id="44311-122">The columns to perform matching on.</span></span>|  
|<span data-ttu-id="44311-123">end_matching_columns</span><span class="sxs-lookup"><span data-stu-id="44311-123">end_matching_columns</span></span>|<span data-ttu-id="44311-124">Упорядоченный список имен столбцов с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="44311-124">A comma-delimited, ordered list of column names.</span></span>|<span data-ttu-id="44311-125">Столбцы, по которым выполняется установка соответствия.</span><span class="sxs-lookup"><span data-stu-id="44311-125">The columns to perform matching on.</span></span>|  
|<span data-ttu-id="44311-126">begin_matching_actions</span><span class="sxs-lookup"><span data-stu-id="44311-126">begin_matching_actions</span></span>|<span data-ttu-id="44311-127">Упорядоченный список действий с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="44311-127">A comma-delimited, ordered list of actions.</span></span>|<span data-ttu-id="44311-128">Действия, по которым выполняется установка соответствия.</span><span class="sxs-lookup"><span data-stu-id="44311-128">The actions to perform matching on.</span></span>|  
|<span data-ttu-id="44311-129">end_matching_actions</span><span class="sxs-lookup"><span data-stu-id="44311-129">end_matching_actions</span></span>|<span data-ttu-id="44311-130">Упорядоченный список действий с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="44311-130">A comma-delimited, ordered list of actions.</span></span>|<span data-ttu-id="44311-131">Действия, по которым выполняется установка соответствия.</span><span class="sxs-lookup"><span data-stu-id="44311-131">The actions to perform matching on.</span></span>|  
|<span data-ttu-id="44311-132">respond_to_memory_pressure</span><span class="sxs-lookup"><span data-stu-id="44311-132">respond_to_memory_pressure</span></span>|<span data-ttu-id="44311-133">Принимает одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="44311-133">One of the following values:</span></span><br /><br /> <span data-ttu-id="44311-134">0 = не отвечать;</span><span class="sxs-lookup"><span data-stu-id="44311-134">0 = Do not respond.</span></span><br /><br /> <span data-ttu-id="44311-135">1 = прекратить добавлять новые несвязанные события к списку при нехватке памяти.</span><span class="sxs-lookup"><span data-stu-id="44311-135">1 = Stop adding new orphans to the list when there is memory pressure.</span></span>|<span data-ttu-id="44311-136">Реакция цели на события памяти.</span><span class="sxs-lookup"><span data-stu-id="44311-136">The target response to memory events.</span></span> <span data-ttu-id="44311-137">Если значение равно 1, а сервер испытывает недостаток памяти, сохраненные данные о непарных событиях удаляются.</span><span class="sxs-lookup"><span data-stu-id="44311-137">If set to 1 and the server is low on memory, unpaired information that is being maintained is removed.</span></span>|  
|<span data-ttu-id="44311-138">max_orphans</span><span class="sxs-lookup"><span data-stu-id="44311-138">max_orphans</span></span>||<span data-ttu-id="44311-139">Указывает общее количество непарных событий, которые будут собраны в целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="44311-139">Specifies the total number of unpaired events that will be collected in the target.</span></span> <span data-ttu-id="44311-140">После достижения этого предела непарные события удаляются по принципу «первым пришел, первым ушел» (FIFO).</span><span class="sxs-lookup"><span data-stu-id="44311-140">Once the limit is reached, unpaired events are removed on a first-in, first-out (FIFO) basis.</span></span> <span data-ttu-id="44311-141">По умолчанию равно 10,000.</span><span class="sxs-lookup"><span data-stu-id="44311-141">Default = 10,000.</span></span>|  
  
 <span data-ttu-id="44311-142">Все данные, связанные с событием, собираются и хранятся для будущей установки соответствия.</span><span class="sxs-lookup"><span data-stu-id="44311-142">All the data associated with an event is captured and stored for future pairing.</span></span> <span data-ttu-id="44311-143">Кроме того, также собираются данные, добавленные действиями.</span><span class="sxs-lookup"><span data-stu-id="44311-143">In addition, data added by actions is also collected.</span></span> <span data-ttu-id="44311-144">Собранные данные события хранятся в памяти, а следовательно, их объем ограничен.</span><span class="sxs-lookup"><span data-stu-id="44311-144">The collected event data is stored in memory, and therefore has a finite limit.</span></span> <span data-ttu-id="44311-145">Это ограничение зависит от объема памяти и активности системы.</span><span class="sxs-lookup"><span data-stu-id="44311-145">This limit is based on system capacity and activity.</span></span> <span data-ttu-id="44311-146">В качестве параметра указывается не максимальный объем памяти, а объем доступных системных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="44311-146">Instead of taking the maximum amount of memory to be used as a parameter, the amount of memory used will be based on available system resources.</span></span> <span data-ttu-id="44311-147">При их недостатке сохраненные непарные события удаляются.</span><span class="sxs-lookup"><span data-stu-id="44311-147">When these are not available, unpaired events that have been retained will be dropped.</span></span> <span data-ttu-id="44311-148">Если непарное событие удаляется, соответствующее ему событие появится как непарное.</span><span class="sxs-lookup"><span data-stu-id="44311-148">If an event has not been paired and is dropped, the matching event will appear as an unpaired event.</span></span>  
  
 <span data-ttu-id="44311-149">Цель «Попарное разбиение событий» сериализует непарные события в формате XML.</span><span class="sxs-lookup"><span data-stu-id="44311-149">The pairing target serializes unpaired events to an XML format.</span></span> <span data-ttu-id="44311-150">Этот формат не соответствует ни одной схеме.</span><span class="sxs-lookup"><span data-stu-id="44311-150">This format does not conform to any schema.</span></span> <span data-ttu-id="44311-151">Он содержит только два типа элементов.</span><span class="sxs-lookup"><span data-stu-id="44311-151">The format only contains two element types.</span></span> <span data-ttu-id="44311-152">**\<unpaired>** Элемент является корнем, за которым следует один.</span><span class="sxs-lookup"><span data-stu-id="44311-152">The **\<unpaired>** element is the root, followed by one.</span></span> <span data-ttu-id="44311-153">**\<event>** элемент для каждого непарного события, которое в настоящее время отслеживается.</span><span class="sxs-lookup"><span data-stu-id="44311-153">**\<event>** element for each unpaired event that is currently being tracked.</span></span> <span data-ttu-id="44311-154">**\<event>** Элемент содержит один атрибут, который содержит имя непарного события.</span><span class="sxs-lookup"><span data-stu-id="44311-154">The **\<event>** element contains one attribute that contains the name of the unpaired event.</span></span>  
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="44311-155">Добавление цели к сеансу</span><span class="sxs-lookup"><span data-stu-id="44311-155">Adding the Target to a Session</span></span>  
 <span data-ttu-id="44311-156">Для добавления цели попарного разбиения событий в сеанс расширенных событий следует использовать одну из следующих инструкций при создании или изменении сеанса события:</span><span class="sxs-lookup"><span data-stu-id="44311-156">To add the pair matching target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```  
ADD TARGET package0.pair_matching   
```  
  
 <span data-ttu-id="44311-157">После этого необходимо использовать инструкцию SET для определения начального и конечного событий и выбора действий и столбцов для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="44311-157">You would follow this with a SET statement, to define the beginning and ending events, and which actions or columns to match.</span></span> <span data-ttu-id="44311-158">В следующем примере показан образец синтаксиса для сопоставления пар событий sqlserver.lock_acquired и sqlserver.lock_released.</span><span class="sxs-lookup"><span data-stu-id="44311-158">The following example shows sample syntax for pair matching the sqlserver.lock_acquired and sqlserver.lock_released events.</span></span>  
  
```  
   ( SET begin_event = 'sqlserver.lock_acquired',  
      begin_matching_columns = 'database_id, resource_0, resource_1, resource_2, transaction_id, mode',  
      end_event = 'sqlserver.lock_released',  
      end_matching_columns = 'database_id, resource_0, resource_1, resource_2, transaction_id, mode',  
   respond_to_memory_pressure = 1)  
```  
  
 <span data-ttu-id="44311-159">Дополнительные сведения см. в разделе [Определение запросов, удерживающих блокировки](../relational-databases/extended-events/determine-which-queries-are-holding-locks.md).</span><span class="sxs-lookup"><span data-stu-id="44311-159">For more information, see [Determine Which Queries Are Holding Locks](../relational-databases/extended-events/determine-which-queries-are-holding-locks.md).</span></span>  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="44311-160">Просмотр целевого вывода</span><span class="sxs-lookup"><span data-stu-id="44311-160">Reviewing the Target Output</span></span>  
 <span data-ttu-id="44311-161">Для просмотра результата цели попарного разбиения событий можно воспользоваться следующим запросом, заменив параметр *session_name* на имя сеанса события.</span><span class="sxs-lookup"><span data-stu-id="44311-161">To review the output for the pair matching target, you can use the following query, replacing *session_name* with the name of the event session.</span></span>  
  
```  
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="44311-162">В следующем примере показан выходной формат цели «Попарное разбиение событий».</span><span class="sxs-lookup"><span data-stu-id="44311-162">The following example shows the pairing target output format.</span></span>  
  
```  
<unpaired truncated = "0" matchedCount = "[matched count]" memoryPressureDroppedCount = " [lost count]">  
    <event name  = "[event name]" package = "[package]" id= "[event ID value]" version = "[event version]">  
    <data name = "[column name]">   
    <type name = "[column type]" package = "[type package]" />   
    <value>[column value]</value>  
    <text value>[text value]</text>>  
        </data>  
    </event>  
</unpaired>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44311-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="44311-163">See Also</span></span>  
 <span data-ttu-id="44311-164">[Цели расширенных событий SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="44311-164">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 <span data-ttu-id="44311-165">[sys.dm_xe_session_targets (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44311-165">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span></span>  
 <span data-ttu-id="44311-166">[CREATE EVENT SESSION (Transact-SQL)](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44311-166">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="44311-167">ALTER EVENT SESSION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="44311-167">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-event-session-transact-sql)  
  
  
