---
title: Ограничение размеров файла и таблицы трассировки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- maximum file size for traces
- traces [SQL Server], file size
- size [SQL Server], tables
- file rollover option [SQL Server]
- size [SQL Server], files
ms.assetid: 88c31b02-f44c-4a14-be8b-437f2097de12
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b7795dfdadb8fb3bbaa1b55dcd5c962d24a7ba29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665980"
---
# <a name="limit-trace-file-and-table-sizes"></a><span data-ttu-id="59645-102">Ограничение размеров файла и таблицы трассировки</span><span class="sxs-lookup"><span data-stu-id="59645-102">Limit Trace File and Table Sizes</span></span>
  <span data-ttu-id="59645-103">Результаты трассировки SQL могут иметь различный размер в зависимости от того, какие классы событий включены в трассировку и каким образом был использован компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59645-103">SQL Trace results vary in size depending on the event classes that are included in the trace and the way in which the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is used.</span></span> <span data-ttu-id="59645-104">Если производится трассировка часто происходящих классов событий, объем собираемых данных может быть уменьшен путем установки максимального размера файла или максимального числа строк.</span><span class="sxs-lookup"><span data-stu-id="59645-104">If you trace event classes that occur frequently, you can minimize the amount of data that the trace collects by setting the maximum file size or the maximum number of rows.</span></span> <span data-ttu-id="59645-105">Указывая максимальный размер файла или максимальное число строк, можно гарантировать, что файл или таблица трассировки не превысят указанные размеры.</span><span class="sxs-lookup"><span data-stu-id="59645-105">By specifying the maximum file size or rows, you ensure that the trace file or table will not grow beyond the specified limit.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59645-106">Если данные трассировки сохраняются в уже существующем файле, можно добавить данные в файл или перезаписать файл.</span><span class="sxs-lookup"><span data-stu-id="59645-106">If you save trace data to a file that already exists, you can append data to the file or overwrite the file.</span></span> <span data-ttu-id="59645-107">Если данные добавляются в файл, а файл трассировки уже имеет или превышает заданный максимальный размер, будет показано уведомление и будет предложено либо увеличить максимальный размер файла, либо выбрать новый файл.</span><span class="sxs-lookup"><span data-stu-id="59645-107">If you choose to append data to the file, and the trace file already meets or exceeds the specified maximum file size, you are notified and given the opportunity either to increase the maximum file size or specify a new file.</span></span> <span data-ttu-id="59645-108">Это верно и для таблиц трассировки.</span><span class="sxs-lookup"><span data-stu-id="59645-108">The same is true for trace tables.</span></span>  
  
## <a name="maximum-file-size"></a><span data-ttu-id="59645-109">Максимальный размер файла</span><span class="sxs-lookup"><span data-stu-id="59645-109">Maximum File Size</span></span>  
 <span data-ttu-id="59645-110">Трассировка, для которой указан максимальный размер файла, прекращает сохранять трассировочные сведения после того, как максимальный размер файла достигнут.</span><span class="sxs-lookup"><span data-stu-id="59645-110">A trace that has a maximum file size stops saving trace information to the file after the maximum file size has been reached.</span></span> <span data-ttu-id="59645-111">Этот параметр позволяет группировать события в меньшие, более удобные для управления файлы.</span><span class="sxs-lookup"><span data-stu-id="59645-111">This option allows you to group events into smaller, more manageable files.</span></span> <span data-ttu-id="59645-112">Кроме того, ограничение размера файла делает более безопасным запуск автоматических трассировок, так как трассировка прекращается по достижении максимального размера файла.</span><span class="sxs-lookup"><span data-stu-id="59645-112">In addition, limiting file size makes it safer to run unattended traces, because the trace stops when the maximum file size is reached.</span></span> <span data-ttu-id="59645-113">Максимальный размер файла может быть установлен для трассировок, созданных как посредством хранимых процедур языка Transact-SQL, так и при помощи приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59645-113">You can set the maximum file size for traces created by means of Transact-SQL stored procedures or by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="59645-114">Существует верхняя граница для параметра максимального размера файла, равная 1 гигабайт (ГБ).</span><span class="sxs-lookup"><span data-stu-id="59645-114">There is an upper limit of 1 gigabyte (GB) for the maximum file size option.</span></span> <span data-ttu-id="59645-115">По умолчанию максимальный размер файла равен 5 мегабайт (МБ).</span><span class="sxs-lookup"><span data-stu-id="59645-115">The default maximum file size is 5 megabytes (MB).</span></span>  
  
### <a name="enabling-file-rollover"></a><span data-ttu-id="59645-116">Включение операции переключение на файл продолжения</span><span class="sxs-lookup"><span data-stu-id="59645-116">Enabling File Rollover</span></span>  
 <span data-ttu-id="59645-117">Если выбран параметр «операция переключения на файл продолжения», то [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] закрывает текущий файл, как только он достигнет максимального размера, а затем создает новый файл.</span><span class="sxs-lookup"><span data-stu-id="59645-117">The file rollover option causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to close the current file and create a new file when the maximum file size is reached.</span></span> <span data-ttu-id="59645-118">Новый файл имеет такое же имя, что и предыдущий файл, но к нему добавляется целое число для указания последовательности.</span><span class="sxs-lookup"><span data-stu-id="59645-118">The new file has the same name as the previous file, but an integer is appended to the name to indicate its sequence.</span></span> <span data-ttu-id="59645-119">Например, если оригинальный файл трассировки имел имя «filename_1.trc», следующий файл трассировки будет иметь имя «filename_2.trc» и т.д.</span><span class="sxs-lookup"><span data-stu-id="59645-119">For example, if the original trace file is named filename_1.trc, the next trace file is filename_2.trc, and so on.</span></span> <span data-ttu-id="59645-120">Если имя, присвоенное новому файлу продолжения, уже используется существующим файлом, существующий файл будет перезаписан, если не является файлом только для чтения.</span><span class="sxs-lookup"><span data-stu-id="59645-120">If the name assigned to a new rollover file is already used by an existing file, the existing file is overwritten unless it is read only.</span></span> <span data-ttu-id="59645-121">Параметр «операция переключения на файл продолжения» устанавливается автоматически при сохранении данных трассировки в файл.</span><span class="sxs-lookup"><span data-stu-id="59645-121">The file rollover option is enabled by default when you are saving trace data to a file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59645-122">Если параметр «операция переключения на файл продолжения» включен, то трассировка будет продолжаться до тех пор, пока не будет остановлена другими средствами.</span><span class="sxs-lookup"><span data-stu-id="59645-122">With the file rollover option on, the trace continues until it is stopped by some other means.</span></span> <span data-ttu-id="59645-123">Чтобы трассировка останавливалась по достижении максимального размера файла, отключите параметр «операция переключения на файл продолжения».</span><span class="sxs-lookup"><span data-stu-id="59645-123">To stop the trace after you have reached the file size limit, disable the file rollover option.</span></span>  
  
 <span data-ttu-id="59645-124">**Указание максимального размера файла трассировки**</span><span class="sxs-lookup"><span data-stu-id="59645-124">**To set a maximum file size for a trace file**</span></span>  
  
 [<span data-ttu-id="59645-125">Установка максимального размера для файла трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="59645-125">Set a Maximum File Size for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-file-size-for-a-trace-file-sql-server-profiler.md)  
  
## <a name="maximum-number-of-rows"></a><span data-ttu-id="59645-126">Максимальное число строк</span><span class="sxs-lookup"><span data-stu-id="59645-126">Maximum Number of Rows</span></span>  
 <span data-ttu-id="59645-127">Трассировка с заданным максимальным числом строк прекращает сохранять трассировочные сведения по достижении таблицей максимального числа строк.</span><span class="sxs-lookup"><span data-stu-id="59645-127">A trace with a maximum number of rows stops saving trace information to a table after the maximum number of rows has been reached.</span></span> <span data-ttu-id="59645-128">Каждое событие создает одну строку, поэтому этот параметр устанавливает границу числа собранных событий.</span><span class="sxs-lookup"><span data-stu-id="59645-128">Each event constitutes one row, so this parameter sets a limit on the number of events that are gathered.</span></span> <span data-ttu-id="59645-129">Установка максимального числа строк упрощает выполнение автоматических трассировок.</span><span class="sxs-lookup"><span data-stu-id="59645-129">Setting the maximum number of rows makes it easier to run unattended traces.</span></span> <span data-ttu-id="59645-130">Например, если необходимо запустить трассировку, которая сохраняет данные трассировки в таблицу, но желательно прекратить трассировку, когда таблица становится слишком большой, это может быть сделано автоматически.</span><span class="sxs-lookup"><span data-stu-id="59645-130">For example, if you need to start a trace that saves trace data to a table, but you want to stop the trace if the table becomes too large, you can do so automatically.</span></span>  
  
 <span data-ttu-id="59645-131">Если указано максимальное число строк и таблица содержит количество строк, равное максимальному числу строк, трассировка продолжает выполняться, пока выполняется приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , но сведения трассировки больше не записываются.</span><span class="sxs-lookup"><span data-stu-id="59645-131">When the maximum number of rows is specified and the maximum number of rows has been reached, the trace continues to run while [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is running, but the trace information is no longer recorded.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="59645-132">результаты трассировки продолжают отображаться до завершения трассировки.</span><span class="sxs-lookup"><span data-stu-id="59645-132">continues to display the trace results until the trace stops.</span></span>  
  
 <span data-ttu-id="59645-133">**Установка максимального числа строк для трассировки**</span><span class="sxs-lookup"><span data-stu-id="59645-133">**To set a maximum number of rows for a trace**</span></span>  
  
 [<span data-ttu-id="59645-134">Установка максимального размера для таблицы трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="59645-134">Set a Maximum Table Size for a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-table-size-for-a-trace-table-sql-server-profiler.md)  
  
## <a name="see-also"></a><span data-ttu-id="59645-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="59645-135">See Also</span></span>  
 [<span data-ttu-id="59645-136">Хранимая процедура sp_trace_create (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="59645-136">sp_trace_create &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql)  
  
  