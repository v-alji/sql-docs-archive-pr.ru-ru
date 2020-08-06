---
title: Изменение существующей трассировки (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], modifying
- modifying traces
ms.assetid: 8792b43f-2510-44e3-9239-e73ad8227b89
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 55b8172ef8e6188059c484ab41f1a719e0e9f8c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655555"
---
# <a name="modify-an-existing-trace-transact-sql"></a><span data-ttu-id="fcda4-102">изменить существующую трассировку (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fcda4-102">Modify an Existing Trace (Transact-SQL)</span></span>
  <span data-ttu-id="fcda4-103">В этом подразделе описано, как при помощи хранимых процедур изменить существующую трассировку.</span><span class="sxs-lookup"><span data-stu-id="fcda4-103">This topic describes how to use stored procedures to modify an existing trace.</span></span>  
  
### <a name="to-modify-an-existing-trace"></a><span data-ttu-id="fcda4-104">Изменение существующей трассировки</span><span class="sxs-lookup"><span data-stu-id="fcda4-104">To modify an existing trace</span></span>  
  
1.  <span data-ttu-id="fcda4-105">Чтобы остановить трассировку, если она уже выполняется, выполните процедуру **sp_trace_setstatus** , указав параметр **@status =0**.</span><span class="sxs-lookup"><span data-stu-id="fcda4-105">If the trace is already running, execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="fcda4-106">Чтобы изменить события трассировки, выполните процедуру **sp_trace_setevent** , указав изменения с помощью параметров.</span><span class="sxs-lookup"><span data-stu-id="fcda4-106">To modify trace events, execute **sp_trace_setevent** by specifying the changes through the parameters.</span></span> <span data-ttu-id="fcda4-107">Эти параметры перечислены ниже (по порядку):</span><span class="sxs-lookup"><span data-stu-id="fcda4-107">Listed in order, the parameters are:</span></span>  
  
    -   <span data-ttu-id="fcda4-108">**@traceid**(Идентификатор трассировки)</span><span class="sxs-lookup"><span data-stu-id="fcda4-108">**@traceid** (Trace ID)</span></span>  
  
    -   <span data-ttu-id="fcda4-109">**@eventid**(ИД события)</span><span class="sxs-lookup"><span data-stu-id="fcda4-109">**@eventid** (Event ID)</span></span>  
  
    -   <span data-ttu-id="fcda4-110">**@columnid**(Идентификатор столбца)</span><span class="sxs-lookup"><span data-stu-id="fcda4-110">**@columnid** (Column ID)</span></span>  
  
    -   <span data-ttu-id="fcda4-111">**@on**ON</span><span class="sxs-lookup"><span data-stu-id="fcda4-111">**@on** (ON)</span></span>  
  
     <span data-ttu-id="fcda4-112">При изменении параметра помните о **@on** его взаимодействии с **@columnid** параметром:</span><span class="sxs-lookup"><span data-stu-id="fcda4-112">When you modify the **@on** parameter, keep in mind its interaction with the **@columnid** parameter:</span></span>  
  
    |<span data-ttu-id="fcda4-113">ON</span><span class="sxs-lookup"><span data-stu-id="fcda4-113">ON</span></span>|<span data-ttu-id="fcda4-114">Идентификатор столбца</span><span class="sxs-lookup"><span data-stu-id="fcda4-114">Column ID</span></span>|<span data-ttu-id="fcda4-115">Результат</span><span class="sxs-lookup"><span data-stu-id="fcda4-115">Result</span></span>|  
    |--------|---------------|------------|  
    |<span data-ttu-id="fcda4-116">ON (**1**)</span><span class="sxs-lookup"><span data-stu-id="fcda4-116">ON (**1**)</span></span>|<span data-ttu-id="fcda4-117">NULL</span><span class="sxs-lookup"><span data-stu-id="fcda4-117">NULL</span></span>|<span data-ttu-id="fcda4-118">Событие включено.</span><span class="sxs-lookup"><span data-stu-id="fcda4-118">Event is turned on.</span></span> <span data-ttu-id="fcda4-119">Все столбцы очищены.</span><span class="sxs-lookup"><span data-stu-id="fcda4-119">All columns are cleared.</span></span>|  
    ||<span data-ttu-id="fcda4-120">NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fcda4-120">NOT NULL</span></span>|<span data-ttu-id="fcda4-121">Столбец включен для указанного события.</span><span class="sxs-lookup"><span data-stu-id="fcda4-121">Column is turned on for the specified event.</span></span>|  
    |<span data-ttu-id="fcda4-122">OFF (**0**)</span><span class="sxs-lookup"><span data-stu-id="fcda4-122">OFF (**0**)</span></span>|<span data-ttu-id="fcda4-123">NULL</span><span class="sxs-lookup"><span data-stu-id="fcda4-123">NULL</span></span>|<span data-ttu-id="fcda4-124">Событие выключено.</span><span class="sxs-lookup"><span data-stu-id="fcda4-124">Event is turned off.</span></span> <span data-ttu-id="fcda4-125">Все столбцы очищены.</span><span class="sxs-lookup"><span data-stu-id="fcda4-125">All columns are cleared.</span></span>|  
    ||<span data-ttu-id="fcda4-126">NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fcda4-126">NOT NULL</span></span>|<span data-ttu-id="fcda4-127">Столбец выключен для указанного события.</span><span class="sxs-lookup"><span data-stu-id="fcda4-127">Column is turned off for the specified event.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="fcda4-128">Параметры всех хранимых процедур [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] (<strong>sp_trace_*xx*</strong>), в отличие от обычных хранимых процедур, жестко типизированы и не поддерживают автоматическое преобразование типов данных.</span><span class="sxs-lookup"><span data-stu-id="fcda4-128">Unlike regular stored procedures, parameters of all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="fcda4-129">Если эти параметры не вызываются вместе с правильными типами данных входных параметров, как указано в описании аргумента, хранимая процедура возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="fcda4-129">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fcda4-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="fcda4-130">See Also</span></span>  
 <span data-ttu-id="fcda4-131">[Хранимая процедура sp_trace_setevent (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fcda4-131">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="fcda4-132">[Хранимая процедура sp_trace_setstatus (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fcda4-132">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="fcda4-133">[Системные хранимые процедуры (Transact-SQL)](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fcda4-133">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="fcda4-134">Хранимые процедуры приложения SQL Server Profiler (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fcda4-134">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
