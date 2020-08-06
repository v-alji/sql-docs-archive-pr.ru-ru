---
title: Преобразование существующего скрипта трассировки SQL в сеанс расширенных событий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace, convert script to extended events
- extended events [SQL Server], convert SQL Trace script
ms.assetid: 4c8f29e6-0a37-490f-88b3-33493871b3f9
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e5b0d0e20fbf4fd55398c130abf6cfff128ebe8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666621"
---
# <a name="convert-an-existing-sql-trace-script-to-an-extended-events-session"></a><span data-ttu-id="2d948-102">Преобразование существующего скрипта трассировки SQL в сеанс расширенных событий</span><span class="sxs-lookup"><span data-stu-id="2d948-102">Convert an Existing SQL Trace Script to an Extended Events Session</span></span>
  <span data-ttu-id="2d948-103">При наличии существующего скрипта трассировки SQL, который требуется преобразовать для сеанса расширенных событий, можно использовать процедуры из данного раздела для создания эквивалентного сеанса расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="2d948-103">If you have an existing SQL Trace script that you want to convert to an Extended Events session, you can use the procedures in this topic to create an equivalent Extended Events session.</span></span> <span data-ttu-id="2d948-104">С помощью системных таблиц trace_xe_action_map и trace_xe_event_map можно собрать сведения, необходимые для выполнения преобразования.</span><span class="sxs-lookup"><span data-stu-id="2d948-104">By using the information in the trace_xe_action_map and trace_xe_event_map system tables, you can collect the information that you must have to do the conversion.</span></span>  
  
 <span data-ttu-id="2d948-105">Эти действия включают следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="2d948-105">The steps include the following:</span></span>  
  
1.  <span data-ttu-id="2d948-106">Создание сеанса трассировки SQL и получение идентификатора трассировки с помощью существующего скрипта.</span><span class="sxs-lookup"><span data-stu-id="2d948-106">Execute the existing script to create a SQL Trace session, and then obtain the ID of the trace.</span></span>  
  
2.  <span data-ttu-id="2d948-107">Выполнение запроса, использующего функцию fn_trace_geteventinfo для поиска эквивалентных событий и действий расширенных событий для каждого класса событий трассировки SQL и связанных с ним столбцов.</span><span class="sxs-lookup"><span data-stu-id="2d948-107">Run a query that uses the fn_trace_geteventinfo function to find the equivalent Extended Events events and actions for each SQL Trace event class and its associated columns.</span></span>  
  
3.  <span data-ttu-id="2d948-108">Функция fn_trace_getfilterinfo позволяет получить список фильтров и эквивалентных действий расширенных событий для использования.</span><span class="sxs-lookup"><span data-stu-id="2d948-108">Use the fn_trace_getfilterinfo function to list the filters and the equivalent Extended Events actions to use.</span></span>  
  
4.  <span data-ttu-id="2d948-109">Создайте сеанс расширенных событий вручную с помощью эквивалентных событий, действий и предикатов (фильтров) расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="2d948-109">Manually create an Extended Events session, using the equivalent Extended Events events, actions, and predicates (filters).</span></span>  
  
## <a name="to-obtain-the-trace-id"></a><span data-ttu-id="2d948-110">Получение идентификатора трассировки</span><span class="sxs-lookup"><span data-stu-id="2d948-110">To obtain the trace ID</span></span>  
  
1.  <span data-ttu-id="2d948-111">Откройте скрипт трассировки SQL в редакторе запросов и выполните его, чтобы создать сеанс трассировки.</span><span class="sxs-lookup"><span data-stu-id="2d948-111">Open the SQL Trace script in Query Editor, and then execute the script to create the trace session.</span></span> <span data-ttu-id="2d948-112">Обратите внимание, что для выполнения этой процедуры не нужно запускать сеанс трассировки.</span><span class="sxs-lookup"><span data-stu-id="2d948-112">Note that the trace session does not need to be running to complete this procedure.</span></span>  
  
2.  <span data-ttu-id="2d948-113">Получите идентификатор трассировки.</span><span class="sxs-lookup"><span data-stu-id="2d948-113">Obtain the ID of the trace.</span></span> <span data-ttu-id="2d948-114">Для этого выполните следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="2d948-114">To do this, use the following query:</span></span>  
  
    ```sql
    SELECT * FROM sys.traces;  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="2d948-115">Идентификатор трассировки 1 обычно соответствует трассировке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2d948-115">Trace ID 1 typically indicates the default trace.</span></span>  
  
## <a name="to-determine-the-extended-events-equivalents"></a><span data-ttu-id="2d948-116">Определение эквивалентов расширенных событий</span><span class="sxs-lookup"><span data-stu-id="2d948-116">To determine the Extended Events equivalents</span></span>  
  
1.  <span data-ttu-id="2d948-117">Чтобы определить эквивалентные события и действия расширенных событий, выполните приведенный ниже запрос, в котором параметру *trace_id* присвоено значение идентификатора трассировки, полученное в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="2d948-117">To determine the equivalent Extended Events events and actions, run the following query, where *trace_id* is set to the value of the trace ID that you obtained in the previous procedure.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2d948-118">В этом примере используется код идентификатор для трассировки по умолчанию (1).</span><span class="sxs-lookup"><span data-stu-id="2d948-118">In this example, the trace ID for the default trace (1) is used.</span></span>  
  
    ```sql
    USE MASTER;  
    GO  
    DECLARE @trace_id int;  
    SET @trace_id = 1;  
    SELECT DISTINCT el.eventid, em.package_name, em.xe_event_name AS 'event'  
       , el.columnid, ec.xe_action_name AS 'action'  
    FROM (sys.fn_trace_geteventinfo(@trace_id) AS el  
       LEFT OUTER JOIN sys.trace_xe_event_map AS em  
          ON el.eventid = em.trace_event_id)  
    LEFT OUTER JOIN sys.trace_xe_action_map AS ec  
       ON el.columnid = ec.trace_column_id  
    WHERE em.xe_event_name IS NOT NULL AND ec.xe_action_name IS NOT NULL;  
    ```  
  
     <span data-ttu-id="2d948-119">Возвращаются эквивалентные идентификатор события, имя пакета, имя события, идентификатор столбца и имя действия расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="2d948-119">The equivalent Extended Events event ID, package name, event name, column ID and action name are returned.</span></span> <span data-ttu-id="2d948-120">Эти выходные данные будут использоваться в процедуре «Создание сеанса расширенных событий» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2d948-120">You will use this output in the procedure "To create the Extended Events session" later in this topic.</span></span>  
  
     <span data-ttu-id="2d948-121">В некоторых случаях отфильтрованный столбец сопоставляется с полем данных события, включенным по умолчанию в событие расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="2d948-121">In some cases, the filtered column maps to an event data field that is included by default in the Extended Events event.</span></span> <span data-ttu-id="2d948-122">Поэтому столбец «Extended_Events_action_name» будет иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="2d948-122">Therefore, the "Extended_Events_action_name" column will be NULL.</span></span> <span data-ttu-id="2d948-123">В этом случае необходимо выполнить следующие действия, чтобы определить, какое поле данных эквивалентно отфильтрованному столбцу.</span><span class="sxs-lookup"><span data-stu-id="2d948-123">If this occurs, you must do the following to determine which data field is equivalent to the filtered column:</span></span>  
  
    1.  <span data-ttu-id="2d948-124">Для действий, возвращающих значение NULL, определите в скрипте классы событий трассировки SQL, содержащие фильтруемый столбец.</span><span class="sxs-lookup"><span data-stu-id="2d948-124">For the actions that return NULL, identify which SQL Trace event classes in the script contain the column that is being filtered.</span></span>  
  
         <span data-ttu-id="2d948-125">Например, при использовании класса событий SP:StmtCompleted мог быть указан фильтр по имени столбца трассировки Duration (идентификатор класса событий трассировки SQL — 45, идентификатор столбца трассировки SQL — 13).</span><span class="sxs-lookup"><span data-stu-id="2d948-125">For example, you may have used the SP:StmtCompleted event class, and specified a filter on the Duration trace column name (SQL Trace event class ID 45, and SQL Trace column ID 13).</span></span> <span data-ttu-id="2d948-126">В этом случае имя действия будет отображаться в результатах запроса как значение NULL.</span><span class="sxs-lookup"><span data-stu-id="2d948-126">In this case, the action name will appear as NULL in the query results.</span></span>  
  
    2.  <span data-ttu-id="2d948-127">Для каждого класса событий трассировки SQL, определенных в предыдущем шаге, найдите эквивалентное имя события расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="2d948-127">For each SQL Trace event class that you identified in the previous step, find the equivalent Extended Events event name.</span></span> <span data-ttu-id="2d948-128">(Если вы не уверены в правильности имени эквивалентного события, используйте запрос, приведенный в разделе [Просмотр эквивалентов расширенных событий для классов событий трассировки SQL](view-the-extended-events-equivalents-to-sql-trace-event-classes.md).)</span><span class="sxs-lookup"><span data-stu-id="2d948-128">(If you are not sure of the equivalent event name, use the query in the topic [View the Extended Events Equivalents to SQL Trace Event Classes](view-the-extended-events-equivalents-to-sql-trace-event-classes.md).)</span></span>  
  
    3.  <span data-ttu-id="2d948-129">Следующий запрос используется для определения правильных полей данных для событий, определенных в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="2d948-129">Use the following query to identify the correct data fields to use for the events that you identified in the previous step.</span></span> <span data-ttu-id="2d948-130">Запрос отображает поля данных расширенных событий в столбце «event_field».</span><span class="sxs-lookup"><span data-stu-id="2d948-130">The query shows the Extended Events data fields in the "event_field" column.</span></span> <span data-ttu-id="2d948-131">В запросе замените *<имя_события>* именем события, указанным в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="2d948-131">In the query, replace *<event_name>* with the name of an event that you specified in the previous step.</span></span>  
  
        ```sql
        SELECT xp.name package_name, xe.name event_name  
           ,xc.name event_field, xc.description  
        FROM sys.trace_xe_event_map AS em  
        INNER JOIN sys.dm_xe_objects AS xe  
           ON em.xe_event_name = xe.name  
        INNER JOIN sys.dm_xe_packages AS xp  
           ON xe.package_guid = xp.guid AND em.package_name = xp.name  
        INNER JOIN sys.dm_xe_object_columns AS xc  
           ON xe.name = xc.object_name  
        WHERE xe.object_type = 'event' AND xc.column_type <> 'readonly'  
           AND em.xe_event_name = '<event_name>';  
        ```  
  
         <span data-ttu-id="2d948-132">Например, класс событий SP:StmtCompleted сопоставляется с событием sp_statement_completed расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="2d948-132">For example, the SP:StmtCompleted event class maps to the sp_statement_completed Extended Events event.</span></span> <span data-ttu-id="2d948-133">Если указать в запросе в качестве имени события sp_statement_completed, то в полях, которые по умолчанию включаются в событие, появится столбец "event_field".</span><span class="sxs-lookup"><span data-stu-id="2d948-133">If you specify sp_statement_completed as the event name in the query, the "event_field" column shows the fields that are included by default with the event.</span></span> <span data-ttu-id="2d948-134">Среди полей есть поле «duration».</span><span class="sxs-lookup"><span data-stu-id="2d948-134">Looking at the fields, you can see that there is a "duration" field.</span></span> <span data-ttu-id="2d948-135">Чтобы создать фильтр в эквивалентном сеансе расширенных событий, необходимо добавить предикат, например "WHERE duration > 0".</span><span class="sxs-lookup"><span data-stu-id="2d948-135">To create the filter in the equivalent Extended Events session, you would add a predicate such as "WHERE duration > 0".</span></span> <span data-ttu-id="2d948-136">В качестве примера см. процедуру «Создание сеанса расширенных событий» в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2d948-136">For an example, see the "To create the Extended Events session" procedure in this topic.</span></span>  
  
## <a name="to-create-the-extended-events-session"></a><span data-ttu-id="2d948-137">Создание сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="2d948-137">To create the Extended Events session</span></span>  
 <span data-ttu-id="2d948-138">Воспользуйтесь редактором запросов для создания сеанса расширенных событий и записи выходных данных в целевой файл.</span><span class="sxs-lookup"><span data-stu-id="2d948-138">Use Query Editor to create the Extended Events session, and to write the output to a file target.</span></span> <span data-ttu-id="2d948-139">Следующие шаги описывают один запрос, там же объясняется, как строить запрос.</span><span class="sxs-lookup"><span data-stu-id="2d948-139">The following steps describe a single query, with explanations to show you how to build the query.</span></span> <span data-ttu-id="2d948-140">Полный пример запроса см. в подразделе «Пример» этого раздела.</span><span class="sxs-lookup"><span data-stu-id="2d948-140">For the full query example, see the "Example" section of this topic.</span></span>  
  
1.  <span data-ttu-id="2d948-141">Добавьте инструкции для создания сеанса событий, заменив*имя_сеанса* нужным именем сеанса расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="2d948-141">Add statements to create the event session, replacing s*ession_name* with the name that you want to use for the Extended Events session.</span></span>  
  
    ```sql
    IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
       DROP EVENT SESSION [Session_Name] ON SERVER;  
    CREATE EVENT SESSION [Session_Name]  
    ON SERVER;  
    ```  
  
2.  <span data-ttu-id="2d948-142">Добавьте события и действия расширенных событий, возвращенные в качестве выходных данных в процедуре «Определение эквивалентов расширенных событий», и предикаты (фильтры), определенные в процедуре «Определение фильтров, использованных в скрипте».</span><span class="sxs-lookup"><span data-stu-id="2d948-142">Add the Extended Events events and actions that were returned as output in the procedure "Determine the Extended Events equivalents", and add the predicates (filters) that you identified in the procedure "To determine the filters that were used in the script".</span></span>  
  
     <span data-ttu-id="2d948-143">В приведенном ниже примере используется скрипт трассировки SQL с классами событий SQL:StmtStarting и SP:StmtCompleted и фильтрами по полям session_id и duration.</span><span class="sxs-lookup"><span data-stu-id="2d948-143">The following example uses a SQL Trace script that includes the SQL:StmtStarting and SP:StmtCompleted event classes, with filters for session ID and duration.</span></span> <span data-ttu-id="2d948-144">Образец выходных данных для запроса процедуры «Определение эквивалентов расширенных событий» представляет собой следующий результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="2d948-144">Sample output for the query in the "Determine the Extended Events equivalents" procedure returned the following result set:</span></span>  
  
    ```  
    Eventid  package_name  event                   columnid  action  
    44       sqlserver     sp_statement_starting   6         nt_username  
    44       sqlserver     sp_statement_starting   9         client_pid  
    44       sqlserver     sp_statement_starting   10        client_app_name  
    44       sqlserver     sp_statement_starting   11        server_principal_name  
    44       sqlserver     sp_statement_starting   12        session_id  
    45       sqlserver     sp_statement_completed  6         nt_username  
    45       sqlserver     sp_statement_completed  9         client_pid  
    45       sqlserver     sp_statement_completed  10        client_app_name  
    45       sqlserver     sp_statement_completed  11        server_principal_name  
    45       sqlserver     sp_statement_completed  12        session_id  
    ```  
  
     <span data-ttu-id="2d948-145">Для преобразования его в эквивалент расширенных событий добавляются события sqlserver.sp_statement_starting и sqlserver.sp_statement_completed со списком действий.</span><span class="sxs-lookup"><span data-stu-id="2d948-145">To convert this to the Extended Events equivalent, the sqlserver.sp_statement_starting and the sqlserver.sp_statement_completed events are added, with a list of actions.</span></span> <span data-ttu-id="2d948-146">Инструкции-предикаты включены в качестве предложений WHERE.</span><span class="sxs-lookup"><span data-stu-id="2d948-146">Predicate statements are included as WHERE clauses.</span></span>  
  
    ```sql
    ADD EVENT sqlserver.sp_statement_starting  
       (ACTION  
          (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
          )  
       WHERE sqlserver.session_id = 59   
       ),  
  
    ADD EVENT sqlserver.sp_statement_completed  
       (ACTION  
          (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
          )  
       WHERE sqlserver.session_id = 59 AND duration > 0  
       )  
    ```  
  
3.  <span data-ttu-id="2d948-147">Добавьте целевой асинхронный файл, заменив путь к файлу расположением, в котором требуется сохранить выходные данные.</span><span class="sxs-lookup"><span data-stu-id="2d948-147">Add the asynchronous file target, replacing the file paths with the location where you want to save the output.</span></span> <span data-ttu-id="2d948-148">При использовании целевого файла следует включить путь к файлу журнала и метаданных.</span><span class="sxs-lookup"><span data-stu-id="2d948-148">When specifying the file target, you must include a log file and metadata file path file.</span></span>  
  
    ```sql
    ADD TARGET package0.asynchronous_file_target(  
       SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
    ```  
  
## <a name="to-view-the-results"></a><span data-ttu-id="2d948-149">Просмотр результатов</span><span class="sxs-lookup"><span data-stu-id="2d948-149">To view the results</span></span>  
  
1.  <span data-ttu-id="2d948-150">Просмотреть выходные данные можно с помощью функции sys.fn_xe_file_target_read_file.</span><span class="sxs-lookup"><span data-stu-id="2d948-150">You can use the sys.fn_xe_file_target_read_file function to view the output.</span></span> <span data-ttu-id="2d948-151">Для этого запустите следующий запрос, заменив пути к файлам указанными путями:</span><span class="sxs-lookup"><span data-stu-id="2d948-151">To do this, run the following query, replacing the file paths with the paths that you specified:</span></span>  
  
    ```sql
    SELECT *, CAST(event_data as XML) AS 'event_data_XML'  
    FROM sys.fn_xe_file_target_read_file('c:\temp\ExtendedEventsStoredProcs*.xel', 'c:\temp\ExtendedEventsStoredProcs*.xem', NULL, NULL);  
  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="2d948-152">Приведение данных события к XML является необязательным.</span><span class="sxs-lookup"><span data-stu-id="2d948-152">Casting the event data as XML is optional.</span></span>  
  
     <span data-ttu-id="2d948-153">Дополнительные сведения о функции sys.fn_xe_file_target_read_file см. в разделе [sys.fn_xe_file_target_read_file (Transact-SQL)](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2d948-153">For more information about the sys.fn_xe_file_target_read_file function, see [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>  
  
    ```sql
    IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
       DROP EVENT SESSION [session_name] ON SERVER;  
    CREATE EVENT SESSION [session_name]  
    ON SERVER  
  
    ADD EVENT sqlserver.sp_statement_starting  
       (ACTION  
       (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
       )  
       WHERE sqlserver.session_id = 59   
       ),  
  
    ADD EVENT sqlserver.sp_statement_completed  
       (ACTION  
       (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
       )  
       WHERE sqlserver.session_id = 59 AND duration > 0  
       );  
  
    ADD TARGET package0.asynchronous_file_target  
       (SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
    ```  
  
## <a name="example"></a><span data-ttu-id="2d948-154">Пример</span><span class="sxs-lookup"><span data-stu-id="2d948-154">Example</span></span>  
  
```sql
IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
   DROP EVENT SESSION [session_name] ON SERVER;  
CREATE EVENT SESSION [session_name]  
ON SERVER  
  
ADD EVENT sqlserver.sp_statement_starting  
   (ACTION  
   (  
      sqlserver.nt_username,  
      sqlserver.client_pid,  
      sqlserver.client_app_name,  
      sqlserver.server_principal_name,  
      sqlserver.session_id  
   )  
   WHERE sqlserver.session_id = 59   
   ),  
  
ADD EVENT sqlserver.sp_statement_completed  
   (ACTION  
   (  
      sqlserver.nt_username,  
      sqlserver.client_pid,  
      sqlserver.client_app_name,  
      sqlserver.server_principal_name,  
      sqlserver.session_id  
   )  
   WHERE sqlserver.session_id = 59 AND duration > 0  
   )  
  
ADD TARGET package0.asynchronous_file_target  
   (SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d948-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="2d948-155">See Also</span></span>  
 [<span data-ttu-id="2d948-156">Просмотр эквивалентов расширенных событий для классов событий трассировки SQL</span><span class="sxs-lookup"><span data-stu-id="2d948-156">View the Extended Events Equivalents to SQL Trace Event Classes</span></span>](view-the-extended-events-equivalents-to-sql-trace-event-classes.md)  
  
  
