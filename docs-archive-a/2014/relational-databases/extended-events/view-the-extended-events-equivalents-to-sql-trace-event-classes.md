---
title: Просмотр эквивалентов расширенных событий для классов событий трассировки SQL | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace, extended events equivalents
- extended events [SQL Server], SQL Trace equivalents
- extended events [SQL Server], user configurable events
ms.assetid: 7f24104c-201d-4361-9759-f78a27936011
author: rothja
ms.author: jroth
ms.openlocfilehash: 37459359f9f6cb7e3951b705c4007477ec43e36a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728242"
---
# <a name="view-the-extended-events-equivalents-to-sql-trace-event-classes"></a><span data-ttu-id="30146-102">Просмотр эквивалентов расширенных событий для классов событий трассировки SQL</span><span class="sxs-lookup"><span data-stu-id="30146-102">View the Extended Events Equivalents to SQL Trace Event Classes</span></span>
  <span data-ttu-id="30146-103">Если требуется с помощью расширенных событий выполнять сбор данных о событиях, эквивалентных классам и столбцам событий трассировки SQL, желательно иметь представление о том, как события SQL-трассировки сопоставляются с событиями и действиями расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="30146-103">If you want to use Extended Events to collect event data that is equivalent to SQL Trace event classes and columns, it is useful to understand how the SQL Trace events map to Extended Events events and actions.</span></span>  
  
 <span data-ttu-id="30146-104">С помощью приведенной ниже процедуры можно просматривать события и действия расширенных событий, аналогичных каждому событию трассировки SQL со связанными столбцами.</span><span class="sxs-lookup"><span data-stu-id="30146-104">You can use the following procedure to view the Extended Events events and actions that are equivalent to each SQL Trace event and its associated columns.</span></span>  
  
## <a name="to-view-the-extended-events-equivalents-to-sql-trace-events-using-query-editor"></a><span data-ttu-id="30146-105">Просмотр эквивалентов расширенных событий для событий трассировки SQL с помощью редактора запросов</span><span class="sxs-lookup"><span data-stu-id="30146-105">To view the Extended Events equivalents to SQL Trace events using Query Editor</span></span>  
  
-   <span data-ttu-id="30146-106">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]выполните следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="30146-106">From Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], run the following query:</span></span>  
  
    ```  
    USE MASTER;  
    GO  
    SELECT DISTINCT  
       tb.trace_event_id,  
       te.name AS 'Event Class',  
       em.package_name AS 'Package',  
       em.xe_event_name AS 'XEvent Name',  
       tb.trace_column_id,  
       tc.name AS 'SQL Trace Column',  
       am.xe_action_name as 'Extended Events action'  
    FROM (sys.trace_events te LEFT OUTER JOIN sys.trace_xe_event_map em  
       ON te.trace_event_id = em.trace_event_id) LEFT OUTER JOIN sys.trace_event_bindings tb  
       ON em.trace_event_id = tb.trace_event_id LEFT OUTER JOIN sys.trace_columns tc  
       ON tb.trace_column_id = tc.trace_column_id LEFT OUTER JOIN sys.trace_xe_action_map am  
       ON tc.trace_column_id = am.trace_column_id  
    ORDER BY te.name, tc.name  
    ```  
  
 <span data-ttu-id="30146-107">При просмотре результатов обратите внимание на следующее.</span><span class="sxs-lookup"><span data-stu-id="30146-107">When you view the results, note the following:</span></span>  
  
-   <span data-ttu-id="30146-108">Если все столбцы, кроме столбца класса событий, возвращают значение NULL, значит, данный класс событий не был перенесен из трассировки SQL.</span><span class="sxs-lookup"><span data-stu-id="30146-108">If all columns return NULL except for the Event Class column, this indicates that the event class was not migrated from SQL Trace.</span></span>  
  
-   <span data-ttu-id="30146-109">Если единственным значением, содержащимся в столбце действий расширенных событий, является NULL, значит, выполняется одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="30146-109">If only the value in the Extended Events action column is NULL, this indicates that either of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="30146-110">Столбец трассировки SQL сопоставлен с одним из полей данных, связанных с событием расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="30146-110">The SQL Trace column maps to one of the data fields that is associated with the Extended Events event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="30146-111">Каждое событие расширенных событий имеет набор полей данных по умолчанию, автоматически включаемых в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="30146-111">Each Extended Events event has a default set of data fields that are automatically included in the result set.</span></span>  
  
    -   <span data-ttu-id="30146-112">Столбец действий не имеет эквивалента в расширенных событиях.</span><span class="sxs-lookup"><span data-stu-id="30146-112">The action column does not have a meaningful Extended Events equivalent.</span></span> <span data-ttu-id="30146-113">Примером этого является столбец класса событий в трассировке SQL.</span><span class="sxs-lookup"><span data-stu-id="30146-113">An example of this is the EventClass column in SQL Trace.</span></span> <span data-ttu-id="30146-114">Этот столбец не нужен в расширенных событиях, поскольку достаточно имени события.</span><span class="sxs-lookup"><span data-stu-id="30146-114">This column is not needed in Extended Events because the event name serves the same purpose.</span></span>  
  
-   <span data-ttu-id="30146-115">Что касается настраиваемых пользователем классов событий трассировки SQL (с UserConfigurable:1 по UserConfigurable:9), в расширенных событиях вместо них используется одно событие.</span><span class="sxs-lookup"><span data-stu-id="30146-115">For user configurable SQL Trace event classes (UserConfigurable:1 through UserConfigurable:9), Extended Events uses a single event to replace these.</span></span> <span data-ttu-id="30146-116">Имя события — user_event.</span><span class="sxs-lookup"><span data-stu-id="30146-116">The event is named user_event.</span></span> <span data-ttu-id="30146-117">Это событие вызывается с помощью хранимой процедуры sp_trace_generateevent, которая используется и в трассировке SQL.</span><span class="sxs-lookup"><span data-stu-id="30146-117">This event is raised by using sp_trace_generateevent, which is the same stored procedure that is used by SQL Trace.</span></span> <span data-ttu-id="30146-118">Событие user_event возвращается независимо от того, какой идентификатор события передается хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="30146-118">The user_event event is returned regardless of which event ID is passed to the stored procedure.</span></span> <span data-ttu-id="30146-119">Однако поле event_id возвращается вместе с другими данными о событии.</span><span class="sxs-lookup"><span data-stu-id="30146-119">However, an event_id field is returned as part of the event data.</span></span> <span data-ttu-id="30146-120">Это позволяет составлять предикат на основе идентификатора события.</span><span class="sxs-lookup"><span data-stu-id="30146-120">This enables you to build a predicate that is based on the event ID.</span></span> <span data-ttu-id="30146-121">Например, если в коде используется UserConfigurable:0 (идентификатор события = 82), то можно добавить событие user_event в сеанс и указать предикат "event_id = 82".</span><span class="sxs-lookup"><span data-stu-id="30146-121">For example, if you use UserConfigurable:0 (event ID = 82) in the code, you can add the user_event event to the session, and specify a predicate of 'event_id = 82'.</span></span> <span data-ttu-id="30146-122">Таким образом, нет необходимости менять код, поскольку хранимая процедура sp_trace_generateevent формирует событие расширенных событий user_event и эквивалентный класс событий трассировки SQL.</span><span class="sxs-lookup"><span data-stu-id="30146-122">Therefore, you do not have to change the code because the sp_trace_generateevent stored procedure generates the Extended Events user_event event, and the equivalent SQL Trace event class.</span></span>  
  
-   <span data-ttu-id="30146-123">Если все столбцы, кроме столбца класса событий, возвращают значение NULL, значит, данный класс событий не был перенесен из трассировки SQL.</span><span class="sxs-lookup"><span data-stu-id="30146-123">If all columns return NULL except for the Event Class column, this indicates that the event class was not migrated from SQL Trace.</span></span>  
  
-   <span data-ttu-id="30146-124">Если единственным значением, содержащимся в столбце действий расширенных событий, является NULL, значит, выполняется одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="30146-124">If only the value in the Extended Events action column is NULL, this indicates that either of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="30146-125">Столбец трассировки SQL сопоставлен с одним из полей данных, связанных с событием расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="30146-125">The SQL Trace column maps to one of the data fields that is associated with the Extended Events event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="30146-126">Каждое событие расширенных событий имеет набор полей данных по умолчанию, автоматически включаемых в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="30146-126">Each Extended Events event has a default set of data fields that are automatically included in the result set.</span></span>  
  
    -   <span data-ttu-id="30146-127">Столбец действий не имеет эквивалента в расширенных событиях.</span><span class="sxs-lookup"><span data-stu-id="30146-127">The action column does not have a meaningful Extended Events equivalent.</span></span> <span data-ttu-id="30146-128">Примером этого является столбец класса событий в трассировке SQL.</span><span class="sxs-lookup"><span data-stu-id="30146-128">An example of this is the EventClass column in SQL Trace.</span></span> <span data-ttu-id="30146-129">Этот столбец не нужен в расширенных событиях, поскольку достаточно имени события.</span><span class="sxs-lookup"><span data-stu-id="30146-129">This column is not needed in Extended Events because the event name serves the same purpose.</span></span>  
  
-   <span data-ttu-id="30146-130">Что касается настраиваемых пользователем классов событий трассировки SQL (с UserConfigurable:1 по UserConfigurable:9), в расширенных событиях вместо них используется одно событие.</span><span class="sxs-lookup"><span data-stu-id="30146-130">For user configurable SQL Trace event classes (UserConfigurable:1 through UserConfigurable:9), Extended Events uses a single event to replace these.</span></span> <span data-ttu-id="30146-131">Имя события — user_event.</span><span class="sxs-lookup"><span data-stu-id="30146-131">The event is named user_event.</span></span> <span data-ttu-id="30146-132">Это событие вызывается с помощью хранимой процедуры sp_trace_generateevent, которая используется и в трассировке SQL.</span><span class="sxs-lookup"><span data-stu-id="30146-132">This event is raised by using sp_trace_generateevent, which is the same stored procedure that is used by SQL Trace.</span></span> <span data-ttu-id="30146-133">Событие user_event возвращается независимо от того, какой идентификатор события передается хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="30146-133">The user_event event is returned regardless of which event ID is passed to the stored procedure.</span></span> <span data-ttu-id="30146-134">Однако поле event_id возвращается вместе с другими данными о событии.</span><span class="sxs-lookup"><span data-stu-id="30146-134">However, an event_id field is returned as part of the event data.</span></span> <span data-ttu-id="30146-135">Это позволяет составлять предикат на основе идентификатора события.</span><span class="sxs-lookup"><span data-stu-id="30146-135">This enables you to build a predicate that is based on the event ID.</span></span> <span data-ttu-id="30146-136">Например, если в коде используется UserConfigurable:0 (идентификатор события = 82), то можно добавить событие user_event в сеанс и указать предикат "event_id = 82".</span><span class="sxs-lookup"><span data-stu-id="30146-136">For example, if you use UserConfigurable:0 (event ID = 82) in the code, you can add the user_event event to the session, and specify a predicate of 'event_id = 82'.</span></span> <span data-ttu-id="30146-137">Таким образом, нет необходимости менять код, поскольку хранимая процедура sp_trace_generateevent формирует событие расширенных событий user_event и эквивалентный класс событий трассировки SQL.</span><span class="sxs-lookup"><span data-stu-id="30146-137">Therefore, you do not have to change the code because the sp_trace_generateevent stored procedure generates the Extended Events user_event event, and the equivalent SQL Trace event class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30146-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="30146-138">See Also</span></span>  
 [<span data-ttu-id="30146-139">Хранимая процедура sp_trace_generateevent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="30146-139">sp_trace_generateevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)  
  
  
