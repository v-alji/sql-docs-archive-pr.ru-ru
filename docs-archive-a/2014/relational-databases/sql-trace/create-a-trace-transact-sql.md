---
title: Создание трассировки (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], example
- traces [SQL Server], creating
ms.assetid: 79dd4254-e3c6-467a-bb6f-f99e51757e99
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 35644891b2dca8359d6dc68fbddb67288d241cb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665268"
---
# <a name="create-a-trace-transact-sql"></a><span data-ttu-id="bd610-102">создать трассировку (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bd610-102">Create a Trace (Transact-SQL)</span></span>
  <span data-ttu-id="bd610-103">В этом подразделе описано, как использовать хранимые процедуры для создания трассировки.</span><span class="sxs-lookup"><span data-stu-id="bd610-103">This topic describes how to use stored procedures to create a trace.</span></span>  
  
### <a name="to-create-a-trace"></a><span data-ttu-id="bd610-104">Создание трассировки</span><span class="sxs-lookup"><span data-stu-id="bd610-104">To create a trace</span></span>  
  
1.  <span data-ttu-id="bd610-105">Выполните хранимую процедуру **sp_trace_create** с необходимыми аргументами для создания новой трассировки.</span><span class="sxs-lookup"><span data-stu-id="bd610-105">Execute **sp_trace_create** with the required parameters to create a new trace.</span></span> <span data-ttu-id="bd610-106">Новая трассировка будет находиться в остановленном состоянии (*status* имеет значение **0**).</span><span class="sxs-lookup"><span data-stu-id="bd610-106">The new trace will be in a stopped state (*status* is **0**).</span></span>  
  
2.  <span data-ttu-id="bd610-107">Выполните хранимую процедуру **sp_trace_setevent** с необходимыми аргументами, чтобы выбрать события и столбцы для трассировки.</span><span class="sxs-lookup"><span data-stu-id="bd610-107">Execute **sp_trace_setevent** with the required parameters to select the events and columns to trace.</span></span>  
  
3.  <span data-ttu-id="bd610-108">Дополнительно выполните хранимую процедуру **sp_trace_setfilter** , чтобы установить любой фильтр или комбинацию фильтров.</span><span class="sxs-lookup"><span data-stu-id="bd610-108">Optionally, execute **sp_trace_setfilter** to set any or a combination of filters.</span></span>  
  
     <span data-ttu-id="bd610-109">Хранимые процедуры**sp_trace_setevent** и **sp_trace_setfilter** могут быть выполнены только для существующих остановленных трассировок.</span><span class="sxs-lookup"><span data-stu-id="bd610-109">**sp_trace_setevent** and **sp_trace_setfilter** can be executed only on existing traces that are stopped.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="bd610-110">В отличие от обычных хранимых процедур, параметры всех хранимых процедур приложения SQL Server Profiler (<strong>sp_trace_*xx*</strong>) жестко типизированы и не поддерживают автоматическое преобразование типов данных.</span><span class="sxs-lookup"><span data-stu-id="bd610-110">Unlike regular stored procedures, parameters of all SQL Server Profiler stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="bd610-111">Если эти параметры не вызываются вместе с правильными типами данных входных параметров, как указано в описании аргумента, хранимая процедура возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="bd610-111">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd610-112">Пример</span><span class="sxs-lookup"><span data-stu-id="bd610-112">Example</span></span>  
 <span data-ttu-id="bd610-113">В следующем примере кода с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)]создается трассировка.</span><span class="sxs-lookup"><span data-stu-id="bd610-113">The following code demonstrates creating a trace using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bd610-114">Он состоит из трех разделов: создание трассировки, заполнение файла трассировки и остановка трассировки.</span><span class="sxs-lookup"><span data-stu-id="bd610-114">It is in three sections: creating the trace, populating the trace file, and stopping the trace.</span></span> <span data-ttu-id="bd610-115">Настройте трассировку, добавив события, которые необходимо отслеживать.</span><span class="sxs-lookup"><span data-stu-id="bd610-115">Customize the trace by adding the events that you want to trace.</span></span> <span data-ttu-id="bd610-116">Список событий и столбцов см. в статье [Хранимая процедура sp_trace_setevent (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)создается трассировка.</span><span class="sxs-lookup"><span data-stu-id="bd610-116">For the list of events and columns, see [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql).</span></span>  
  
 <span data-ttu-id="bd610-117">Следующий код создает трассировку, добавляет в нее события и затем запускает ее:</span><span class="sxs-lookup"><span data-stu-id="bd610-117">The following code creates a trace, adds events to the trace, and then starts the trace:</span></span>  
  
```  
DECLARE @RC int, @TraceID int, @on BIT  
EXEC @rc = sp_trace_create @TraceID output, 0, N'C:\SampleTrace'  
  
-- Select the return code to see if the trace creation was successful.  
SELECT RC = @RC, TraceID = @TraceID  
  
-- Set the events and data columns you need to capture.  
SELECT @on = 1  
  
-- 10 is RPC:Completed event. 1 is TextData column.   
EXEC sp_trace_setevent @TraceID, 10, 1, @on   
-- 13 is SQL:BatchStarting, 11 is LoginName  
EXEC sp_trace_setevent @TraceID, 13, 11, @on   
-- 13 is SQL:BatchStarting, 14 is StartTime  
EXEC sp_trace_setevent @TraceID, 13, 14, @on   
-- 12 is SQL:BatchCompleted, 15 is EndTime  
EXEC sp_trace_setevent @TraceID, 12, 15, @on   
-- 13 is SQL:BatchStarting, 1 is TextData  
EXEC sp_trace_setevent @TraceID, 13, 1, @on   
  
-- Set any filter. Not provided in this example  
--EXEC sp_trace_setfilter 1, 10, 0, 6, N'%Profiler%'  
  
-- Start Trace (status 1 = start)  
EXEC @RC = sp_trace_setstatus @TraceID, 1  
GO  
  
```  
  
## <a name="example"></a><span data-ttu-id="bd610-118">Пример</span><span class="sxs-lookup"><span data-stu-id="bd610-118">Example</span></span>  
 <span data-ttu-id="bd610-119">Теперь, когда трассировка создана и запущена, выполните следующий код, чтобы заполнить трассировку активностью.</span><span class="sxs-lookup"><span data-stu-id="bd610-119">Now that the trace has been created and started, execute the following code to populate the trace with activity.</span></span>  
  
```  
SELECT * FROM master.sys.databases  
GO  
SELECT * FROM ::fn_trace_getinfo(default)  
GO  
  
```  
  
## <a name="example"></a><span data-ttu-id="bd610-120">Пример</span><span class="sxs-lookup"><span data-stu-id="bd610-120">Example</span></span>  
 <span data-ttu-id="bd610-121">Трассировку можно в любое время остановить и перезапустить.</span><span class="sxs-lookup"><span data-stu-id="bd610-121">The trace can be stopped and restarted at any time.</span></span> <span data-ttu-id="bd610-122">В этом примере выполнение следующего кода позволит остановить трассировку, закрыть ее и удалить ее определение.</span><span class="sxs-lookup"><span data-stu-id="bd610-122">In this example, execute the following code to stop the trace, close the trace, and delete the trace definition.</span></span>  
  
```  
DECLARE @TraceID int  
-- Populate a variable with the trace_id of the current trace  
SELECT  @TraceID = TraceID FROM ::fn_trace_getinfo(default) WHERE VALUE = N'C:\SampleTrace.trc'  
  
-- First stop the trace.   
EXEC sp_trace_setstatus @TraceID, 0  
  
-- Close and then delete its definition from SQL Server.   
EXEC sp_trace_setstatus @TraceID, 2  
  
```  
  
## <a name="example"></a><span data-ttu-id="bd610-123">Пример</span><span class="sxs-lookup"><span data-stu-id="bd610-123">Example</span></span>  
 <span data-ttu-id="bd610-124">Чтобы изучить файл трассировки, откройте файл SampleTrace.trc в приложении [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd610-124">To examine the trace file, open the SampleTrace.trc file using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd610-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd610-125">See Also</span></span>  
 <span data-ttu-id="bd610-126">[Хранимые процедуры приложения SQL Server Profiler (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd610-126">[SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="bd610-127">[Хранимая процедура sp_trace_create (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd610-127">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="bd610-128">[Хранимая процедура sp_trace_setevent (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd610-128">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="bd610-129">sp_trace_setfilter (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bd610-129">sp_trace_setfilter &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)  
  
  
