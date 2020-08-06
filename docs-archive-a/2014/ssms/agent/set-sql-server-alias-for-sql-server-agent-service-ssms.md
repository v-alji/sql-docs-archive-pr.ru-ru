---
title: Создание фильтра трассировки (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- traces [SQL Server], filters
ms.assetid: 7b976a84-7381-43a6-a828-ba83ada71cbe
author: stevestein
ms.author: sstein
ms.openlocfilehash: 47d797c84a05f50da026280f6e197f965d804426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665754"
---
# <a name="set-a-trace-filter-transact-sql"></a><span data-ttu-id="93f79-102">создать фильтр трассировки (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="93f79-102">Set a Trace Filter (Transact-SQL)</span></span>
  <span data-ttu-id="93f79-103">В этом разделе описывается, как использовать хранимые процедуры для создания фильтра, который возвращает только данные, необходимые для трассируемого события.</span><span class="sxs-lookup"><span data-stu-id="93f79-103">This topic describes how to use stored procedures to create a filter that retrieves only the information you need on an event being traced.</span></span>  
  
### <a name="to-set-a-trace-filter"></a><span data-ttu-id="93f79-104">Установка фильтра трассировки</span><span class="sxs-lookup"><span data-stu-id="93f79-104">To set a trace filter</span></span>  
  
1.  <span data-ttu-id="93f79-105">Чтобы остановить трассировку, если она уже выполняется, выполните процедуру **sp_trace_setstatus** , указав параметр **@status =0**.</span><span class="sxs-lookup"><span data-stu-id="93f79-105">If the trace is already running, execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="93f79-106">Выполните хранимую процедуру **sp_trace_setfilter** , чтобы определить тип данных, которые необходимо получить для трассируемого события.</span><span class="sxs-lookup"><span data-stu-id="93f79-106">Execute **sp_trace_setfilter** to configure the type of information to retrieve for the event being traced.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="93f79-107">Параметры всех хранимых процедур [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] (<strong>sp_trace_*xx*</strong>), в отличие от обычных хранимых процедур, жестко типизированы и не поддерживают автоматическое преобразование типов данных.</span><span class="sxs-lookup"><span data-stu-id="93f79-107">Unlike regular stored procedures, parameters of all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="93f79-108">Если эти аргументы указываются с неправильными типами данных входных параметров, как указано в описании их аргументов, хранимая процедура возвратит ошибку.</span><span class="sxs-lookup"><span data-stu-id="93f79-108">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure will return an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93f79-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="93f79-109">See Also</span></span>  
 <span data-ttu-id="93f79-110">[Фильтрация трассировки](../../relational-databases/sql-trace/filter-a-trace.md) </span><span class="sxs-lookup"><span data-stu-id="93f79-110">[Filter a Trace](../../relational-databases/sql-trace/filter-a-trace.md) </span></span>  
 <span data-ttu-id="93f79-111">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="93f79-111">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span></span>  
 <span data-ttu-id="93f79-112">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="93f79-112">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="93f79-113">[Системные хранимые процедуры &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="93f79-113">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="93f79-114">Хранимые процедуры приложения SQL Server Profiler (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="93f79-114">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
