---
title: Создание и запуск трассировки с помощью хранимых процедур Transact-SQL | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 80347417-338d-4bea-8885-91fae5181cfe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2905ce2822598502ef6337d1a083fb6fde001c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665269"
---
# <a name="create-and-run-traces-using-transact-sql-stored-procedures"></a><span data-ttu-id="b4e35-102">Создание и запуск трассировки с помощью хранимых процедур Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4e35-102">Create and Run Traces Using Transact-SQL Stored Procedures</span></span>
  <span data-ttu-id="b4e35-103">Процесс трассировки с помощью компонента трассировки SQL зависит от того, каким образом создана и запущена трассировка: в приложении Microsoft [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] или с помощью системных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="b4e35-103">The process of tracing with SQL Trace varies depending on whether you create and run your trace by using Microsoft [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or by using system stored procedures.</span></span>  
  
 <span data-ttu-id="b4e35-104">Помимо компонента [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], для создания и запуска трассировок можно использовать системные хранимые процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4e35-104">As an alternative to [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can use [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to create and run traces.</span></span> <span data-ttu-id="b4e35-105">Для управления процессом трассировки предусмотрены следующие системные хранимые процедуры:</span><span class="sxs-lookup"><span data-stu-id="b4e35-105">The process of tracing by using system stored procedures is as follows:</span></span>  
  
1.  <span data-ttu-id="b4e35-106">Создание трассировки с использованием процедуры **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="b4e35-106">Create a trace by using **sp_trace_create**.</span></span>  
  
2.  <span data-ttu-id="b4e35-107">Добавление событий с использованием процедуры **sp_trace_setevent**.</span><span class="sxs-lookup"><span data-stu-id="b4e35-107">Add events with **sp_trace_setevent**.</span></span>  
  
3.  <span data-ttu-id="b4e35-108">Настройка фильтра с использованием процедуры **sp_trace_setfilter**(необязательно).</span><span class="sxs-lookup"><span data-stu-id="b4e35-108">(Optional) Set a filter with **sp_trace_setfilter**.</span></span>  
  
4.  <span data-ttu-id="b4e35-109">Запуск трассировки с использованием процедуры **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="b4e35-109">Start the trace with **sp_trace_setstatus**.</span></span>  
  
5.  <span data-ttu-id="b4e35-110">Остановка трассировки с использованием процедуры **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="b4e35-110">Stop the trace with **sp_trace_setstatus**.</span></span>  
  
6.  <span data-ttu-id="b4e35-111">Закрытие трассировки с использованием процедуры **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="b4e35-111">Close the trace with **sp_trace_setstatus**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b4e35-112">Системные хранимые процедуры языка [!INCLUDE[tsql](../../includes/tsql-md.md)] создают трассировку на уровне сервера, что гарантирует сохранность всех событий при условии наличия свободного места на диске и отсутствии ошибок записи.</span><span class="sxs-lookup"><span data-stu-id="b4e35-112">Using [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures creates a server-side trace, which guarantees that no events will be lost as long as there is space on the disk and no write errors occur.</span></span> <span data-ttu-id="b4e35-113">Если диск переполняется или происходит сбой, то экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] продолжает выполняться, но трассировка прерывается.</span><span class="sxs-lookup"><span data-stu-id="b4e35-113">If the disk becomes full or the disk fails, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance continues to run, but tracing stops.</span></span> <span data-ttu-id="b4e35-114">Если установлен режим аудита **c2** и происходит ошибка записи, то трассировка останавливается, а экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] закрывается.</span><span class="sxs-lookup"><span data-stu-id="b4e35-114">If the **c2 audit mode** is set, and there is a write failure, tracing stops and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span> <span data-ttu-id="b4e35-115">Дополнительные сведения о настройке **c2 audit mode** см. в разделе [Параметр конфигурации сервера c2 audit mode](../../database-engine/configure-windows/c2-audit-mode-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="b4e35-115">For more information about the **c2 audit mode** setting, see [c2 audit mode Server Configuration Option](../../database-engine/configure-windows/c2-audit-mode-server-configuration-option.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b4e35-116">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="b4e35-116">In This Section</span></span>  
  
|<span data-ttu-id="b4e35-117">Раздел</span><span class="sxs-lookup"><span data-stu-id="b4e35-117">Topic</span></span>|<span data-ttu-id="b4e35-118">Description</span><span class="sxs-lookup"><span data-stu-id="b4e35-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b4e35-119">Оптимизация трассировки SQL</span><span class="sxs-lookup"><span data-stu-id="b4e35-119">Optimize SQL Trace</span></span>](sql-trace.md)|<span data-ttu-id="b4e35-120">Сведения о способах снижения воздействия трассировки на производительность системы.</span><span class="sxs-lookup"><span data-stu-id="b4e35-120">Contains information about ways you can reduce the effects of tracing on system performance.</span></span>|  
|[<span data-ttu-id="b4e35-121">Фильтрация трассировки</span><span class="sxs-lookup"><span data-stu-id="b4e35-121">Filter a Trace</span></span>](filter-a-trace.md)|<span data-ttu-id="b4e35-122">Сведения о применении фильтров для трассировки.</span><span class="sxs-lookup"><span data-stu-id="b4e35-122">Contains information about using filters for tracing.</span></span>|  
|[<span data-ttu-id="b4e35-123">Ограничение размеров файла и таблицы трассировки</span><span class="sxs-lookup"><span data-stu-id="b4e35-123">Limit Trace File and Table Sizes</span></span>](limit-trace-file-and-table-sizes.md)|<span data-ttu-id="b4e35-124">Сведения об ограничении размера файлов и таблиц, в которые записываются данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="b4e35-124">Contains information about how to limit the size of files and tables where trace data is written.</span></span> <span data-ttu-id="b4e35-125">Обратите внимание, что записывать данные трассировки в таблицы может только [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4e35-125">Note that only [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] can write trace information to tables.</span></span>|  
|[<span data-ttu-id="b4e35-126">Планирование трассировок</span><span class="sxs-lookup"><span data-stu-id="b4e35-126">Schedule Traces</span></span>](schedule-traces.md)|<span data-ttu-id="b4e35-127">Сведения о настройке времени начала и завершения трассировки.</span><span class="sxs-lookup"><span data-stu-id="b4e35-127">Contains information about how to set the start time and the end time for tracing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4e35-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4e35-128">See Also</span></span>  
 <span data-ttu-id="b4e35-129">[Хранимая процедура sp_trace_create (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b4e35-129">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="b4e35-130">[Хранимая процедура sp_trace_setevent (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b4e35-130">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="b4e35-131">[sp_trace_setfilter (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b4e35-131">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span></span>  
 [<span data-ttu-id="b4e35-132">Хранимая процедура sp_trace_setstatus (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b4e35-132">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
  
