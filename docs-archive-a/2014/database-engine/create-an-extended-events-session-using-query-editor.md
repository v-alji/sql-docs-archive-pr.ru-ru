---
title: Создание сеанса расширенных событий с помощью редактора запросов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- create extended events session
- extended events [SQL Server], create session
ms.assetid: cba0e02b-b201-4863-bf1b-9164e68e5fa8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 648370ecdd2938b6fb425955dc02da8960f884c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664478"
---
# <a name="create-an-extended-events-session-using-query-editor"></a><span data-ttu-id="61421-102">Создание сеанса расширенных событий с помощью редактора запросов</span><span class="sxs-lookup"><span data-stu-id="61421-102">Create an Extended Events Session Using Query Editor</span></span>
  <span data-ttu-id="61421-103">Сеанс расширенных событий можно создать с помощью редактора запросов или в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="61421-103">You can create an Extended Events session by using the Query Editor, or you can create a session in Object Explorer.</span></span> <span data-ttu-id="61421-104">В обозревателе объектов Расширенные события предоставляют два пользовательских интерфейса, которые можно использовать для создания, изменения и просмотра данных сеанса событий — мастер, который помогает выполнить процесс создания сеанса событий, и новый пользовательский интерфейс сеанса, предоставляющий более широкие возможности настройки.</span><span class="sxs-lookup"><span data-stu-id="61421-104">In Object Explorer, Extended Events provides two user interfaces you can use to create, modify, and view event session data - a wizard that guides you through the event session creation process, and a New Session UI that provides more advanced configuration options.</span></span> <span data-ttu-id="61421-105">Сеанс расширенных событий можно создать для диагностики трассировок SQL Server, что дает возможность решать, например, следующие проблемы.</span><span class="sxs-lookup"><span data-stu-id="61421-105">You can create Extended Events sessions to diagnose SQL Server tracing, which enables you to resolve issues such as the following:</span></span>  
  
-   <span data-ttu-id="61421-106">Находить наиболее ресурсоемкие запросы.</span><span class="sxs-lookup"><span data-stu-id="61421-106">Find your most expensive queries</span></span>  
  
-   <span data-ttu-id="61421-107">Находить основные причины конфликтов кратковременных блокировок.</span><span class="sxs-lookup"><span data-stu-id="61421-107">Find root causes of latch contention</span></span>  
  
-   <span data-ttu-id="61421-108">Находить запросы, которые блокируют другие запросы.</span><span class="sxs-lookup"><span data-stu-id="61421-108">Find a query that is blocking other queries</span></span>  
  
-   <span data-ttu-id="61421-109">Устранять неполадки чрезмерного использования ЦП, вызванные перекомпиляцией запросов.</span><span class="sxs-lookup"><span data-stu-id="61421-109">Troubleshoot excessive CPU usage caused by query recompilation</span></span>  
  
-   <span data-ttu-id="61421-110">Устранять неполадки взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="61421-110">Troubleshoot deadlocks</span></span>  
  
 <span data-ttu-id="61421-111">Сведения о создании сеанса расширенных событий с помощью мастера новых сеансов см. в статье [Создание сеанса расширенных событий с помощью пользовательского интерфейса нового сеанса (обозреватель объектов)](../ssms/object/object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="61421-111">For information about how to create an Extended Events session using the New Session Wizard, see [Create an Extended Events Session Using the Wizard &#40;Object Explorer&#41;](../ssms/object/object-explorer.md).</span></span> <span data-ttu-id="61421-112">Сведения о создании сеанса расширенных событий с помощью мастера новых сеансов см. в статье [Создание сеанса расширенных событий с помощью диалогового окна "Создание сеанса"](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md).</span><span class="sxs-lookup"><span data-stu-id="61421-112">For information about how to create an Extended Events session using the New Session UI, see [Create an Extended Events Session Using the New Session Dialog](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md).</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="61421-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="61421-113">Permissions</span></span>  
 <span data-ttu-id="61421-114">Для создания сеанса расширенных событий требуется разрешение ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="61421-114">To create an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
## <a name="creating-an-extended-events-session-using-query-editor"></a><span data-ttu-id="61421-115">Создание сеанса расширенных событий с помощью редактора запросов</span><span class="sxs-lookup"><span data-stu-id="61421-115">Creating an Extended Events session using Query Editor</span></span>  
  
#### <a name="to-create-an-extended-events-session"></a><span data-ttu-id="61421-116">Создание сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="61421-116">To create an Extended Events session</span></span>  
  
1.  <span data-ttu-id="61421-117">Ниже показано, как создать сеанс расширенных событий с помощью редактора запросов в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61421-117">The following procedure shows how to create an Extended Events session by using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="61421-118">Определите, какие события необходимо использовать в сеансе.</span><span class="sxs-lookup"><span data-stu-id="61421-118">Determine which events that you want to use in the session.</span></span> <span data-ttu-id="61421-119">Для просмотра всех доступных событий вместе с ключевым словом и каналом используйте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="61421-119">To see all the events that are available, together with the keyword and channel, use the following query:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61421-120">Дополнительные сведения о ключевых словах и каналах см. в статье [Пакеты обработки расширенных событий SQL Server](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span><span class="sxs-lookup"><span data-stu-id="61421-120">For information about keywords and channels, see [SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span></span>  
  
    ```  
    SELECT p.name, c.event, k.keyword, c.channel, c.description FROM  
       (  
       SELECT event_package = o.package_guid, o.description,   
       event=c.object_name, channel = v.map_value  
       FROM sys.dm_xe_objects o  
       LEFT JOIN sys.dm_xe_object_columns c ON o.name = c.object_name  
       INNER JOIN sys.dm_xe_map_values v ON c.type_name = v.name   
       AND c.column_value = cast(v.map_key AS nvarchar)  
       WHERE object_type = 'event' AND (c.name = 'CHANNEL' or c.name IS NULL)  
       ) c LEFT JOIN   
       (  
       SELECT event_package = c.object_package_guid, event = c.object_name,   
       keyword = v.map_value  
       FROM sys.dm_xe_object_columns c INNER JOIN sys.dm_xe_map_values v   
       ON c.type_name = v.name AND c.column_value = v.map_key   
       AND c.type_package_guid = v.object_package_guid  
       INNER JOIN sys.dm_xe_objects o ON o.name = c.object_name   
       AND o.package_guid = c.object_package_guid  
       WHERE object_type = 'event' AND c.name = 'KEYWORD'   
       ) k  
       ON  
       k.event_package = c.event_package AND (k.event=c.event or k.event IS NULL)  
       INNER JOIN sys.dm_xe_packages p ON p.guid = c.event_package  
    ORDER BY keyword desc, channel, event  
    ```  
  
2.  <span data-ttu-id="61421-121">В новом окне запроса добавьте следующие инструкции для создания сеанса события, заменив *имя_сеанса* на имя сеанса, который будет использован.</span><span class="sxs-lookup"><span data-stu-id="61421-121">In a new query window, add the following statements to create an event session, replacing *session_name* with the session name that you want to use:</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="61421-122">Шаги с 2 по 6 данной процедуры описывают каждый раздел определения сеанса событий.</span><span class="sxs-lookup"><span data-stu-id="61421-122">Steps 2 through 6 of this procedure describe each section of the event session definition.</span></span> <span data-ttu-id="61421-123">Перед исполнением необходимо добавить все инструкции в одно окно запроса.</span><span class="sxs-lookup"><span data-stu-id="61421-123">You would add all the statements to a single query window before executing.</span></span> <span data-ttu-id="61421-124">Полный пример запроса см. в подразделе «Пример» этого раздела.</span><span class="sxs-lookup"><span data-stu-id="61421-124">For a full example, see the Example section of this topic.</span></span>  
  
    ```  
    CREATE EVENT SESSION session_name   
    ON SERVER  
    ```  
  
3.  <span data-ttu-id="61421-125">Добавьте события, которые требуется отслеживать, в формате *имя_пакета*.*имя_события*.</span><span class="sxs-lookup"><span data-stu-id="61421-125">Add the events that you want to monitor, in the format *package_name*.*event_name*.</span></span> <span data-ttu-id="61421-126">Для каждого события добавьте строку следующего вида:</span><span class="sxs-lookup"><span data-stu-id="61421-126">For each event, add a line similar to the following:</span></span>  
  
    ```  
    ADD EVENT package_name.event_name  
    ```  
  
     <span data-ttu-id="61421-127">Пример:</span><span class="sxs-lookup"><span data-stu-id="61421-127">For example:</span></span>  
  
    ```  
    ADD EVENT sqlserver.file_read_completed,  
    ADD EVENT sqlserver.file_write_completed  
    ```  
  
4.  <span data-ttu-id="61421-128">(Необязательно) После добавления события можно добавить действия, подлежащие выполнению.</span><span class="sxs-lookup"><span data-stu-id="61421-128">(Optional) After you add an event, you can add actions to take.</span></span> <span data-ttu-id="61421-129">Можно также добавить предикаты.</span><span class="sxs-lookup"><span data-stu-id="61421-129">You can also add predicates.</span></span> <span data-ttu-id="61421-130">Предикаты используются для установки условия, когда целевой объект должен получить сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="61421-130">Predicates are used to establish criteria for when the event information should be consumed by the target.</span></span> <span data-ttu-id="61421-131">Действия добавляются с помощью предложения ACTION действия, а предикаты добавляются с помощью предложения WHERE.</span><span class="sxs-lookup"><span data-stu-id="61421-131">Actions are added by using an ACTION clause, and predicates are added by using a WHERE clause.</span></span> <span data-ttu-id="61421-132">Например, чтобы добавить действие и предикат, в котором текст [!INCLUDE[tsql](../includes/tsql-md.md)] записывается для события sqlserver.file_read_completed и идентификатор файла равен 1, следует включить следующий инструкцию:</span><span class="sxs-lookup"><span data-stu-id="61421-132">For example, to add an action and predicate where the [!INCLUDE[tsql](../includes/tsql-md.md)] text is captured for the sqlserver.file_read_completed event, where the file ID equals 1, you would include the following statement:</span></span>  
  
    ```  
    ADD EVENT sqlserver.file_read_completed  
       (ACTION (sqlserver.sql_text)  
       WHERE file_id = 1),  
    ```  
  
    -   <span data-ttu-id="61421-133">Для просмотра доступных действий используйте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="61421-133">To view which actions are available, use the following query:</span></span>  
  
        ```  
        SELECT p.name AS 'package_name', xo.name AS 'action_name', xo.description, xo.object_type  
        FROM sys.dm_xe_objects AS xo  
        JOIN sys.dm_xe_packages AS p  
           ON xo.package_guid = p.guid  
        WHERE xo.object_type = 'action'  
        AND (xo.capabilities & 1 = 0   
        OR xo.capabilities IS NULL)  
        ORDER BY p.name, xo.name  
        ```  
  
    -   <span data-ttu-id="61421-134">Чтобы просмотреть предикаты, доступные для события, используйте следующий запрос, заменив *имя_события* на имя события, для которого необходимо добавить предикат:</span><span class="sxs-lookup"><span data-stu-id="61421-134">To view which predicates are available for an event, use the following query, replacing *event_name* with the name of the event for which you want to add a predicate:</span></span>  
  
        ```  
        SELECT *  
        FROM sys.dm_xe_object_columns  
        WHERE object_name = 'event_name'  
        AND column_type = 'data'  
        ```  
  
         <span data-ttu-id="61421-135">Пример:</span><span class="sxs-lookup"><span data-stu-id="61421-135">For example:</span></span>  
  
        ```  
        SELECT *   
        FROM sys.dm_xe_object_columns   
        WHERE object_name = 'file_read_completed'  
        AND column_type = 'data'  
        ```  
  
         <span data-ttu-id="61421-136">Помните, что можно также добавить источники глобальных предикатов.</span><span class="sxs-lookup"><span data-stu-id="61421-136">Be aware that you can also add global predicate sources.</span></span> <span data-ttu-id="61421-137">Источник глобальных предикатов может быть использован в любом выражении предикатов.</span><span class="sxs-lookup"><span data-stu-id="61421-137">A global predicate source can be used in any predicate expression.</span></span> <span data-ttu-id="61421-138">Для просмотра доступных источников глобальных предикатов используйте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="61421-138">To view which global predicate sources are available, use the following query:</span></span>  
  
        ```  
        SELECT p.name AS package_name, xo.name AS predicate_name  
           , xo.description, xo.object_type  
        FROM sys.dm_xe_objects AS xo  
        JOIN sys.dm_xe_packages AS p  
           ON xo.package_guid = p.guid  
        WHERE xo.object_type = 'pred_source'  
        ORDER BY p.name, xo.name  
        ```  
  
         <span data-ttu-id="61421-139">Например, следующее выражение предиката можно использовать для указания, что данные должны быть собраны для события первые пять раз, когда происходит событие.</span><span class="sxs-lookup"><span data-stu-id="61421-139">For example, you could use the following predicate expression to specify that data should only be collected for an event the first five times that an event occurs.</span></span>  
  
        ```  
        WHERE package0.counter <= 5  
        ```  
  
5.  <span data-ttu-id="61421-140">Добавьте нужный целевой объект, в котором данные события будут обработаны и использованы.</span><span class="sxs-lookup"><span data-stu-id="61421-140">Add the desired target, where the event data will be processed and consumed.</span></span> <span data-ttu-id="61421-141">Используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="61421-141">Use the following format:</span></span>  
  
    ```  
    ADD TARGET package_name.target_name  
    ```  
  
     <span data-ttu-id="61421-142">В следующем примере добавляется асинхронный целевой объект файла.</span><span class="sxs-lookup"><span data-stu-id="61421-142">The following example adds the asynchronous file target:</span></span>  
  
    ```  
    ADD TARGET package0.asynchronous_file_target  
       (SET filename = 'c:\temp\xelog.xel', metadatafile = 'c:\temp\xelog.xem')  
    ```  
  
     <span data-ttu-id="61421-143">Для просмотра списка доступных целей используйте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="61421-143">To view the list of available targets, use the following query:</span></span>  
  
    ```  
    SELECT p.name AS 'package_name', xo.name AS 'target_name'  
       , xo.description, xo.object_type   
    FROM sys.dm_xe_objects AS xo  
    JOIN sys.dm_xe_packages AS p  
       ON xo.package_guid = p.guid  
    WHERE xo.object_type = 'target'  
    AND (xo.capabilities & 1 = 0  
    OR xo.capabilities IS NULL)  
    ORDER BY p.name, xo.name  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="61421-144">Дополнительные сведения о разных типах целевых объектов см. в статье [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="61421-144">For information about the different target types, see [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span></span>  
  
6.  <span data-ttu-id="61421-145">Просмотрите и добавьте любые дополнительные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="61421-145">Review and add any additional configuration options.</span></span> <span data-ttu-id="61421-146">Например, можно настроить параметры, такие как режим хранения событий, срок хранения событий в буфере или необходимость запуска сеанса событий автоматически при запуске [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61421-146">For example, you can configure options such as the event retention mode, how long events are buffered in memory, or whether the event session should start automatically when [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts.</span></span> <span data-ttu-id="61421-147">Параметры описаны в статье [ALTER EVENT SESSION (Transact-SQL)](/sql/t-sql/statements/alter-event-session-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="61421-147">The options are described in the topic [ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql).</span></span> <span data-ttu-id="61421-148">Если эти параметры не заданы вручную, будут использоваться значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61421-148">Be aware that default values are assigned if these options are not specified.</span></span>  
  
7.  <span data-ttu-id="61421-149">Запустите сеанс.</span><span class="sxs-lookup"><span data-stu-id="61421-149">Start the session.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61421-150">Дополнительные сведения о просмотре результатов сеанса см. в соответствующем разделе для типа целевого объекта [Цели расширенных событий SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) электронной документации.</span><span class="sxs-lookup"><span data-stu-id="61421-150">For more information about how to view the session results, see the corresponding topic for the target type that you used in the [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) node of Books Online.</span></span>  
  
 <span data-ttu-id="61421-151">В примере ниже создается сеанс расширенных событий с именем IOActivity, который собирает следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="61421-151">The following example creates an Extended Events session named IOActivity that captures the following information:</span></span>  
  
-   <span data-ttu-id="61421-152">Данные события для завершенных операций чтения файла, включая связанный текст [!INCLUDE[tsql](../includes/tsql-md.md)] для операций чтения, в которых идентификатор файла равен 1.</span><span class="sxs-lookup"><span data-stu-id="61421-152">Event data for completed file reads, including the associated [!INCLUDE[tsql](../includes/tsql-md.md)] text for file reads where the file ID is equal to 1.</span></span>  
  
-   <span data-ttu-id="61421-153">Данные события для завершенных операций записи в файл.</span><span class="sxs-lookup"><span data-stu-id="61421-153">Event data for completed file writes.</span></span>  
  
-   <span data-ttu-id="61421-154">Данные событий для данных, которые записаны из кэша журнала в физический файл журнала.</span><span class="sxs-lookup"><span data-stu-id="61421-154">Event data for when data is written from the log cache to the physical log file.</span></span>  
  
 <span data-ttu-id="61421-155">Сеанс отправляет результат в файл целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="61421-155">The session sends the output to a file target.</span></span>  
  
```  
CREATE EVENT SESSION IOActivity  
ON SERVER  
  
ADD EVENT sqlserver.file_read_completed  
   (  
   ACTION (sqlserver.sql_text)  
   WHERE file_id = 1),  
ADD EVENT sqlserver.file_write_completed,  
ADD EVENT sqlserver.databases_log_flush  
  
ADD TARGET package0.asynchronous_file_target   
   (SET filename = 'c:\temp\xelog.xel', metadatafile = 'c:\temp\xelog.xem')  
```  
  
## <a name="see-also"></a><span data-ttu-id="61421-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="61421-156">See Also</span></span>  
 <span data-ttu-id="61421-157">[CREATE EVENT SESSION (Transact-SQL)](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="61421-157">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="61421-158">[Цели расширенных событий SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="61421-158">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 [<span data-ttu-id="61421-159">Пакеты обработки расширенных событий SQL Server</span><span class="sxs-lookup"><span data-stu-id="61421-159">SQL Server Extended Events Packages</span></span>](../relational-databases/extended-events/sql-server-extended-events-packages.md)  
  
  
