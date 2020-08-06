---
title: Сохранение результатов трассировки в файл | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 74f80667-62f3-4e14-bb1a-f0c2b6ef3402
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 644fc812bbb4863c336ff2f53f5b2d67ee0a4d5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655553"
---
# <a name="save-trace-results-to-a-file"></a><span data-ttu-id="a7de0-102">Сохранение результатов трассировки в файл</span><span class="sxs-lookup"><span data-stu-id="a7de0-102">Save Trace Results to a File</span></span>
  <span data-ttu-id="a7de0-103">Результаты трассировки можно сохранить в файле.</span><span class="sxs-lookup"><span data-stu-id="a7de0-103">You can save trace results to a file.</span></span> <span data-ttu-id="a7de0-104">Файл трассировки — это файл, в который записаны результаты трассировки.</span><span class="sxs-lookup"><span data-stu-id="a7de0-104">A trace file is a file where the trace results are written.</span></span> <span data-ttu-id="a7de0-105">Файл трассировки может находиться в локальном каталоге (например, C:\\*имя_папки*\\*имя_файла.trc*) или в сетевом (например, \\\имя_компьютера\сетевое_имя\имя_файла.trc).</span><span class="sxs-lookup"><span data-stu-id="a7de0-105">A trace file can be located either in a local directory (such as C:\\*foldername*\\*filename.trc*) or a network directory (such as \\\computername\sharename\filename.trc).</span></span>  
  
 <span data-ttu-id="a7de0-106">Файлы трассировки можно применять для:</span><span class="sxs-lookup"><span data-stu-id="a7de0-106">You can use the trace files to do the following:</span></span>  
  
-   <span data-ttu-id="a7de0-107">воспроизведения трассировок;</span><span class="sxs-lookup"><span data-stu-id="a7de0-107">Replay traces</span></span>  
  
-   <span data-ttu-id="a7de0-108">Аудит [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7de0-108">Audit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="a7de0-109">выполнения анализа производительности;</span><span class="sxs-lookup"><span data-stu-id="a7de0-109">Conduct performance analysis</span></span>  
  
-   <span data-ttu-id="a7de0-110">сравнения событий трассировки со счетчиками производительности для улучшения распознавания неполадок;</span><span class="sxs-lookup"><span data-stu-id="a7de0-110">Correlate trace events with performance counters to enhance problem detection</span></span>  
  
-   <span data-ttu-id="a7de0-111">выполнения анализа при помощи помощника по настройке ядра СУБД;</span><span class="sxs-lookup"><span data-stu-id="a7de0-111">Perform Database Engine Tuning Advisor analysis</span></span>  
  
-   <span data-ttu-id="a7de0-112">оптимизации запросов.</span><span class="sxs-lookup"><span data-stu-id="a7de0-112">Carry out query optimization</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="a7de0-113">сохраняет результаты трассировки в файл, если путь и имя файла указаны для **@tracefile** аргумента хранимой процедуры **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="a7de0-113">saves trace results to a file when a path and file name are specified for the **@tracefile** argument of the stored procedure **sp_trace_create**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7de0-114">Если для сохранения файла трассировки хранимой процедуре **sp_trace_create** передается путь к файлу, то этот каталог должен быть доступен серверу.</span><span class="sxs-lookup"><span data-stu-id="a7de0-114">If a path is specified to the **sp_trace_create** stored procedure for saving the trace file, the directory must be accessible to the server.</span></span> <span data-ttu-id="a7de0-115">Также помните, что если процедуре **sp_trace_create**передается путь к локальному каталогу, то это локальный каталог на данном сервере.</span><span class="sxs-lookup"><span data-stu-id="a7de0-115">Also be aware that if a local directory is specified to **sp_trace_create**, it is a local directory on the server computer.</span></span>  
  
 <span data-ttu-id="a7de0-116">Если используется [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , результаты трассировки можно сохранить в файле или в таблице.</span><span class="sxs-lookup"><span data-stu-id="a7de0-116">If [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is used, it allows you to save trace results to a file or to a table.</span></span> <span data-ttu-id="a7de0-117">Сохранение результатов трассировки в таблице обеспечивает такой же доступ, как и при сохранении трассировки в файле; помимо этого, для поиска определенных событий можно выполнять запросы к этой таблице.</span><span class="sxs-lookup"><span data-stu-id="a7de0-117">Saving trace results to a table allows the same access as saving the trace to a file plus you can query the table to search for specific events.</span></span>  
  
 <span data-ttu-id="a7de0-118">Дополнительные сведения о сохранении результатов трассировки см. в разделах [Сохранить результаты трассировки в таблицу (приложение SQL Server Profiler)](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) и [Сохранить результаты трассировки в файл (приложение SQL Server Profiler)](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="a7de0-118">For more information about saving trace results, see [Save Trace Results to a Table &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) and [Save Trace Results to a File &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7de0-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7de0-119">See Also</span></span>  
 <span data-ttu-id="a7de0-120">[Хранимая процедура sp_trace_create (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a7de0-120">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="a7de0-121">[Создание трассировки (Transact-SQL)](../sql-trace/create-a-trace-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="a7de0-121">[Create a Trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md) </span></span>  
 [<span data-ttu-id="a7de0-122">Создание трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="a7de0-122">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
  
