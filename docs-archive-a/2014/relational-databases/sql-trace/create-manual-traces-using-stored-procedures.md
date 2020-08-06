---
title: Создание трассировок вручную с помощью хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: f6f47fa2-7c17-41d4-9f69-9be144d56832
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e2840dced22ccdba8fe71cc87c05d7fd6fb4be58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665267"
---
# <a name="create-manual-traces-using-stored-procedures"></a><span data-ttu-id="8ae8a-102">Создание трассировок вручную с помощью хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="8ae8a-102">Create Manual Traces using Stored Procedures</span></span>
  <span data-ttu-id="8ae8a-103">Для создания трассировок на экземпляре компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Microsoft [!INCLUDE[tsql](../../includes/tsql-md.md)] предоставляет системные хранимые процедуры на языке [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ae8a-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to create traces on an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="8ae8a-104">Эти системные хранимые процедуры можно использовать для создания трассировок вручную в рамках пользовательских приложений вместо использования приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ae8a-104">These system stored procedures can be used from within your own applications to create traces manually, instead of using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="8ae8a-105">Это позволяет писать пользовательские приложения, отвечающие конкретным нуждам предприятия.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-105">This allows you to write custom applications specific to the needs of your enterprise.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ae8a-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="8ae8a-106">In This Section</span></span>  
 <span data-ttu-id="8ae8a-107">В приведенной ниже таблице представлены системные хранимые процедуры, используемые для трассировки экземпляра компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ae8a-107">The following table lists the system stored procedures for tracing an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
|<span data-ttu-id="8ae8a-108">Хранимая процедура</span><span class="sxs-lookup"><span data-stu-id="8ae8a-108">Stored procedure</span></span>|<span data-ttu-id="8ae8a-109">Выполненная задача</span><span class="sxs-lookup"><span data-stu-id="8ae8a-109">Task performed</span></span>|  
|----------------------|--------------------|  
|[<span data-ttu-id="8ae8a-110">sys.fn_trace_geteventinfo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ae8a-110">sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-geteventinfo-transact-sql)|<span data-ttu-id="8ae8a-111">Возвращает сведения о событии, включенном в трассировку.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-111">Returns information about events included in a trace.</span></span>|  
|[<span data-ttu-id="8ae8a-112">sys.fn_trace_getinfo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ae8a-112">sys.fn_trace_getinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql)|<span data-ttu-id="8ae8a-113">Возвращает сведения об указанной трассировке или всех существующих трассировках.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-113">Returns information about a specified trace or all existing traces.</span></span>|  
|[<span data-ttu-id="8ae8a-114">Хранимая процедура sp_trace_create (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ae8a-114">sp_trace_create &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql)|<span data-ttu-id="8ae8a-115">Создает определение трассировки.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-115">Creates a trace definition.</span></span> <span data-ttu-id="8ae8a-116">Новая трассировка будет находиться в остановленном состоянии.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-116">The new trace will be in a stopped state.</span></span>|  
|[<span data-ttu-id="8ae8a-117">Хранимая процедура sp_trace_generateevent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ae8a-117">sp_trace_generateevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)|<span data-ttu-id="8ae8a-118">Создает пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-118">Creates a user-defined event.</span></span>|  
|[<span data-ttu-id="8ae8a-119">Хранимая процедура sp_trace_setevent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ae8a-119">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)|<span data-ttu-id="8ae8a-120">Добавляет класс событий или столбец данных к трассировке либо удаляет их из трассировки.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-120">Adds an event class or data column to a trace, or removes one from it.</span></span>|  
|[<span data-ttu-id="8ae8a-121">Хранимая процедура sp_trace_setstatus (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ae8a-121">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)|<span data-ttu-id="8ae8a-122">Запускает, останавливает или закрывает трассировку.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-122">Starts, stops, or closes a trace.</span></span>|  
|[<span data-ttu-id="8ae8a-123">sys.fn_trace_getfilterinfo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ae8a-123">sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql)|<span data-ttu-id="8ae8a-124">Возвращает сведения о фильтрах, примененных к трассировке.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-124">Returns information about filters applied to a trace.</span></span>|  
|[<span data-ttu-id="8ae8a-125">sp_trace_setfilter (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ae8a-125">sp_trace_setfilter &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)|<span data-ttu-id="8ae8a-126">Применяет новый или измененный фильтр к трассировке.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-126">Applies a new or modified filter to a trace.</span></span>|  
  
 <span data-ttu-id="8ae8a-127">**Определение пользовательской трассировки при помощи хранимых процедур**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-127">**To define your own trace using stored procedures**</span></span>  
  
1.  <span data-ttu-id="8ae8a-128">Укажите событие, которое необходимо зарегистрировать с помощью процедуры **sp_trace_setevent**.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-128">Specify the events to capture using **sp_trace_setevent**.</span></span>  
  
2.  <span data-ttu-id="8ae8a-129">Укажите фильтры события.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-129">Specify any event filters.</span></span> <span data-ttu-id="8ae8a-130">Дополнительные сведения см. в разделе [Создание фильтра трассировки (Transact-SQL)](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="8ae8a-130">For more information, see [Set a Trace Filter &#40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md).</span></span>  
  
3.  <span data-ttu-id="8ae8a-131">Укажите назначение для данных зарегистрированного события с помощью процедуры **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="8ae8a-131">Specify the destination for the captured event data using **sp_trace_create**.</span></span>  
  
 <span data-ttu-id="8ae8a-132">Пример использования хранимых процедур трассировки см. в разделе [Создание трассировки (Transact-SQL)](../sql-trace/create-a-trace-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="8ae8a-132">For an example of using trace stored procedures, see [Create a Trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md).</span></span>  
  
 <span data-ttu-id="8ae8a-133">**Установка определения трассировки по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-133">**To set trace definition defaults**</span></span>  
  
 [<span data-ttu-id="8ae8a-134">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8ae8a-134">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
 <span data-ttu-id="8ae8a-135">**Установка параметров по умолчанию для отображения трассировки**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-135">**To set trace display defaults**</span></span>  
  
 [<span data-ttu-id="8ae8a-136">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8ae8a-136">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)  
  
 <span data-ttu-id="8ae8a-137">**Создание трассировки**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-137">**To create a trace**</span></span>  
  
 [<span data-ttu-id="8ae8a-138">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8ae8a-138">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
 [<span data-ttu-id="8ae8a-139">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ae8a-139">Transact-SQL</span></span>](../sql-trace/create-a-trace-transact-sql.md)  
  
 <span data-ttu-id="8ae8a-140">**Добавление или удаление события из шаблона трассировки**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-140">**To add or remove events from a trace template**</span></span>  
  
 [<span data-ttu-id="8ae8a-141">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8ae8a-141">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
 [<span data-ttu-id="8ae8a-142">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ae8a-142">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
