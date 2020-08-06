---
title: Отслеживание производительности хранимых процедур, скомпилированных в собственном коде | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 55548cb2-77a8-4953-8b5a-f2778a4f13cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d14d27cdc20c0f090c7a030efe05cfce4842f437
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750967"
---
# <a name="monitoring-performance-of-natively-compiled-stored-procedures"></a><span data-ttu-id="9fff1-102">Отслеживание производительности скомпилированных в собственном коде хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="9fff1-102">Monitoring Performance of Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="9fff1-103">В этом разделе показано, как наблюдать за производительностью хранимых процедур, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="9fff1-103">This topic discusses how you can monitor the performance of natively compiled stored procedures</span></span>  
  
## <a name="using-extended-events"></a><span data-ttu-id="9fff1-104">Использование расширенных событий</span><span class="sxs-lookup"><span data-stu-id="9fff1-104">Using Extended Events</span></span>  
 <span data-ttu-id="9fff1-105">Для трассировки выполнения запроса используйте расширенное событие `sp_statement_completed`.</span><span class="sxs-lookup"><span data-stu-id="9fff1-105">Use the `sp_statement_completed` extended event to trace execution of a query.</span></span> <span data-ttu-id="9fff1-106">Создайте сеанс с этим событием, при этом можно использовать фильтр в object_id для определенной хранимой процедуры, скомпилированной в собственном коде. Расширенное событие вызывается после выполнения каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="9fff1-106">Create an extended event session with this event, optionally with a filter on object_id for a particular natively compiled stored procedure, The extended event is raised after the execution of each query.</span></span> <span data-ttu-id="9fff1-107">Время ЦП и время существования, указанные расширенным событием, показывают объем ресурсов ЦП, который потребовался на выполнение запроса, и время его выполнения.</span><span class="sxs-lookup"><span data-stu-id="9fff1-107">The CPU time and duration reported by the extended event indicate how much CPU the query used and the execution time.</span></span> <span data-ttu-id="9fff1-108">Скомпилированная в собственном коде хранимая процедура, которая потребляет значительное время ЦП, может сталкиваться с проблемами производительности.</span><span class="sxs-lookup"><span data-stu-id="9fff1-108">A natively compiled stored procedure that uses a lot of CPU time may have performance problems.</span></span>  
  
 <span data-ttu-id="9fff1-109">`line_number` вместе с `object_id` в расширенном событии можно использовать для анализа запросов.</span><span class="sxs-lookup"><span data-stu-id="9fff1-109">`line_number`, along with the `object_id` in the extended event can be used to investigate the query.</span></span> <span data-ttu-id="9fff1-110">Следующий запрос может использоваться для получения определения процедуры.</span><span class="sxs-lookup"><span data-stu-id="9fff1-110">The following query can be used to retrieve the procedure definition.</span></span> <span data-ttu-id="9fff1-111">Номер строки можно использовать для поиска запроса в определении.</span><span class="sxs-lookup"><span data-stu-id="9fff1-111">The line number can be used to identify the query within the definition:</span></span>  
  
```sql  
select [definition] from sys.sql_modules where object_id=object_id  
```  
  
 <span data-ttu-id="9fff1-112">Дополнительные сведения о `sp_statement_completed` расширенном событии см. в разделе [получение инструкции, вызвавшей событие](https://blogs.msdn.com/b/extended_events/archive/2010/05/07/making-a-statement-how-to-retrieve-the-t-sql-statement-that-caused-an-event.aspx).</span><span class="sxs-lookup"><span data-stu-id="9fff1-112">For more information about the `sp_statement_completed` extended event, see [How to retrieve the statement that caused an event](https://blogs.msdn.com/b/extended_events/archive/2010/05/07/making-a-statement-how-to-retrieve-the-t-sql-statement-that-caused-an-event.aspx).</span></span>  
  
## <a name="using-data-management-views"></a><span data-ttu-id="9fff1-113">Использование динамических административных представлений</span><span class="sxs-lookup"><span data-stu-id="9fff1-113">Using Data Management Views</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9fff1-114">поддерживает сбор статистики выполнения для скомпилированных в собственном коде хранимых процедур как на уровне процедуры, так и на уровне запроса.</span><span class="sxs-lookup"><span data-stu-id="9fff1-114">supports collecting execution statistics for natively compiled stored procedures, both on the procedure level and the query level.</span></span> <span data-ttu-id="9fff1-115">Из-за влияния на производительность сбор статистики выполнения по умолчанию не используется.</span><span class="sxs-lookup"><span data-stu-id="9fff1-115">Collecting execution statistics is not enabled by default due to performance impact.</span></span>  
  
 <span data-ttu-id="9fff1-116">Включать и отключать сбор статистики для скомпилированных в собственном коде хранимых процедур можно с помощью [sys.sp_xtp_control_proc_exec_stats (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9fff1-116">You can enable and disable statistics collection on natively compiled stored procedures using [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="9fff1-117">Если сбор статистики включен с помощью процедуры [sys.sp_xtp_control_proc_exec_stats (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql), можно с помощью [sys.dm_exec_procedure_stats (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) выполнять мониторинг производительности скомпилированной в собственном коде хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="9fff1-117">When statistics collection is enabled with [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql), you can use [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) to monitor performance of a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="9fff1-118">Если сбор статистики включен с помощью процедуры [sys.sp_xtp_control_query_exec_stats (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql), можно с помощью [sys.dm_exec_query_stats (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) выполнять мониторинг производительности скомпилированной в собственном коде хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="9fff1-118">When statistics collection is enabled with [sys.sp_xtp_control_query_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql), you can use [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) to monitor performance of a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="9fff1-119">Прежде всего включите сбор статистики.</span><span class="sxs-lookup"><span data-stu-id="9fff1-119">At the start of collection, enable statistics collection.</span></span> <span data-ttu-id="9fff1-120">Затем выполните скомпилированную в собственном коде хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="9fff1-120">Then, execute the natively compiled stored procedure.</span></span> <span data-ttu-id="9fff1-121">После завершения сбора статистики отключите его.</span><span class="sxs-lookup"><span data-stu-id="9fff1-121">At the end of collection, disable statistics collection.</span></span> <span data-ttu-id="9fff1-122">Затем проанализируйте статистику выполнения, которая была возвращена динамическими административными представлениями.</span><span class="sxs-lookup"><span data-stu-id="9fff1-122">Then, analyze the execution statistics returned by the DMVs.</span></span>  
  
 <span data-ttu-id="9fff1-123">После того как статистика выполнения хранимых процедур, скомпилированных в собственном коде, будет собрана, запросить ее для определенной процедуры можно будет с помощью [sys.dm_exec_procedure_stats (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql), а для запросов — с помощью [sys.dm_exec_query_stats (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9fff1-123">After you collect statistics, the execution statistics for natively compiled stored procedures can be queried for a procedure with [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql), and for queries with [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9fff1-124">Если сбор статистики включен, то накопленное время рабочей роли для скомпилированных в собственном коде хранимых процедур указывается в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="9fff1-124">For natively compiled stored procedures when statistics collection is enabled, worker time is collected in milliseconds.</span></span> <span data-ttu-id="9fff1-125">Если запрос выполняется за время меньше миллисекунды, это значение будет равно 0.</span><span class="sxs-lookup"><span data-stu-id="9fff1-125">If the query executes in less than a millisecond, the value will be 0.</span></span> <span data-ttu-id="9fff1-126">Для скомпилированных в собственном коде хранимых процедур функция **total_worker_time** может быть неточной, если за время меньше миллисекунды выполняется большое количество хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="9fff1-126">For natively compiled stored procedures, **total_worker_time** may not be accurate if many executions take less than 1 millisecond.</span></span>  
  
 <span data-ttu-id="9fff1-127">После сбора статистики следующий запрос возвращает имена и статистику выполнения скомпилированных в собственном коде хранимых процедур в текущей базе данных.</span><span class="sxs-lookup"><span data-stu-id="9fff1-127">The following query returns the procedure names and execution statistics for natively compiled stored procedures in the current database, after statistics collection:</span></span>  
  
```sql  
select object_id,  
       object_name(object_id) as 'object name',  
       cached_time,  
       last_execution_time,  
       execution_count,  
       total_worker_time,  
       last_worker_time,  
       min_worker_time,  
       max_worker_time,  
       total_elapsed_time,  
       last_elapsed_time,  
       min_elapsed_time,  
       max_elapsed_time   
from sys.dm_exec_procedure_stats  
where database_id=db_id() and object_id in (select object_id   
from sys.sql_modules where uses_native_compilation=1)  
order by total_worker_time desc  
```  
  
 <span data-ttu-id="9fff1-128">Следующий запрос возвращает текст запроса, а также статистику выполнения всех запросов из скомпилированных в собственном коде хранимых процедур в текущей базе данных, для которой были собраны статистические данные. Статистика при этом упорядочивается по общему времени рабочей роли в убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="9fff1-128">The following query returns the query text as well as execution statistics for all queries in natively compiled stored procedures in the current database for which statistics have been collected, ordered by total worker time, in descending order:</span></span>  
  
```sql  
select st.objectid,   
       object_name(st.objectid) as 'object name',   
       SUBSTRING(st.text, (qs.statement_start_offset/2) + 1, ((qs.statement_end_offset-qs.statement_start_offset)/2) + 1) as 'query text',   
       qs.creation_time,  
       qs.last_execution_time,  
       qs.execution_count,  
       qs.total_worker_time,  
       qs.last_worker_time,  
       qs.min_worker_time,  
       qs.max_worker_time,  
       qs.total_elapsed_time,  
       qs.last_elapsed_time,  
       qs.min_elapsed_time,  
       qs.max_elapsed_time  
from sys.dm_exec_query_stats qs cross apply sys.dm_exec_sql_text(sql_handle) st  
where  st.dbid=db_id() and st.objectid in (select object_id   
from sys.sql_modules where uses_native_compilation=1)  
order by qs.total_worker_time desc  
```  
  
 <span data-ttu-id="9fff1-129">Скомпилированные в собственном коде хранимые процедуры поддерживают SHOWPLAN_XML (предполагаемый план выполнения).</span><span class="sxs-lookup"><span data-stu-id="9fff1-129">Natively compiled stored procedures support SHOWPLAN_XML (estimated execution plan).</span></span> <span data-ttu-id="9fff1-130">С помощью предполагаемого плана выполнения можно проверять план запроса с целью выявления проблем.</span><span class="sxs-lookup"><span data-stu-id="9fff1-130">The estimated execution plan can be used to inspect the query plan, to find any bad plan issues.</span></span> <span data-ttu-id="9fff1-131">Общие причины появления некачественных планов.</span><span class="sxs-lookup"><span data-stu-id="9fff1-131">Common reasons for bad plans are:</span></span>  
  
-   <span data-ttu-id="9fff1-132">Статистика не была обновлена перед созданием процедуры.</span><span class="sxs-lookup"><span data-stu-id="9fff1-132">Stats were not updated before the procedure was created.</span></span>  
  
-   <span data-ttu-id="9fff1-133">Отсутствующие индексы</span><span class="sxs-lookup"><span data-stu-id="9fff1-133">Missing indexes</span></span>  
  
 <span data-ttu-id="9fff1-134">Для получения Showplan XML выполняется следующая инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9fff1-134">Showplan XML is obtained by executing the following [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
```sql  
SET SHOWPLAN_XML ON  
GO  
EXEC my_proc   
GO  
SET SHOWPLAN_XML OFF  
GO  
```  
  
 <span data-ttu-id="9fff1-135">Кроме того, в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]выберите имя процедуры и щелкните **Показать предполагаемый план выполнения**.</span><span class="sxs-lookup"><span data-stu-id="9fff1-135">Alternatively, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the procedure name and click **Display Estimated Execution Plan**.</span></span>  
  
 <span data-ttu-id="9fff1-136">Предполагаемый план выполнения для скомпилированных в собственном коде хранимых процедур показывает операторы и выражения для запросов из процедуры.</span><span class="sxs-lookup"><span data-stu-id="9fff1-136">The estimated execution plan for natively compiled stored procedures shows the query operators and expressions for the queries in the procedure.</span></span> [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] <span data-ttu-id="9fff1-137">не поддерживает все атрибуты SHOWPLAN_XML для скомпилированных в собственном коде хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="9fff1-137">does not support all SHOWPLAN_XML attributes for natively compiled stored procedures.</span></span> <span data-ttu-id="9fff1-138">Например, атрибуты, связанные с оценкой затрат оптимизатора запросов, не являются частью SHOWPLAN_XML для процедуры.</span><span class="sxs-lookup"><span data-stu-id="9fff1-138">For example, attributes related to query optimizer costing are not part of the SHOWPLAN_XML for the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fff1-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="9fff1-139">See Also</span></span>  
 [<span data-ttu-id="9fff1-140">Скомпилированные в собственном коде хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="9fff1-140">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
