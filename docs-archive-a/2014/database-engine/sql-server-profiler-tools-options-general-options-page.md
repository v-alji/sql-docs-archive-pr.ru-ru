---
title: SQL Server Profiler-Tools-Options (страница «Общие параметры») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.tools.generaloptions.f1
helpviewer_keywords:
- General Options dialog box
ms.assetid: a888246d-ccfe-415f-bbdc-d6adafac250a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fad4d3529482835367898276a973bd7c8827b553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666203"
---
# <a name="sql-server-profiler---tools-options-general-options-page"></a><span data-ttu-id="d7c6d-102">SQL Server Profiler-Tools-Options (страница «Общие параметры»)</span><span class="sxs-lookup"><span data-stu-id="d7c6d-102">SQL Server Profiler - Tools-Options (General Options Page)</span></span>
  <span data-ttu-id="d7c6d-103">Диалоговое окно **Общие параметры** используется для просмотра или указания следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-103">Use the **General Options** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d7c6d-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="d7c6d-104">Options</span></span>  
  
### <a name="display-options"></a><span data-ttu-id="d7c6d-105">Параметры отображения</span><span class="sxs-lookup"><span data-stu-id="d7c6d-105">Display Options</span></span>  
 <span data-ttu-id="d7c6d-106">**Имя шрифта**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-106">**Font name**</span></span>  
 <span data-ttu-id="d7c6d-107">Выводит имя шрифта, который во время трассировки используется в сетке результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-107">Displays the name of the font used in the trace results grid during traces.</span></span>  
  
 <span data-ttu-id="d7c6d-108">**Размер шрифта**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-108">**Font size**</span></span>  
 <span data-ttu-id="d7c6d-109">Выводит размер шрифта, который во время трассировки используется в сетке результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-109">Displays the size of the font used in the trace results grid during traces.</span></span>  
  
 <span data-ttu-id="d7c6d-110">**Выбор шрифта**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-110">**Choose Font**</span></span>  
 <span data-ttu-id="d7c6d-111">Открывает диалоговое окно для изменения параметров шрифта.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-111">Opens a dialog to change the font settings.</span></span>  
  
 <span data-ttu-id="d7c6d-112">**Использовать региональные настройки при показе значений даты и времени**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-112">**Use regional settings to display date and time values**</span></span>  
 <span data-ttu-id="d7c6d-113">Выводит значения даты и времени согласно региональным настройкам компьютера.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-113">Displays date and time values in regional settings configured for your computer.</span></span> <span data-ttu-id="d7c6d-114">Если не выбрать этот параметр, значения даты и времени будут отображаться в фиксированном формате, используемом Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], который включает миллисекунды.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-114">If you do not select this option, the date and time values are displayed in the fixed format used by Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], which includes milliseconds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7c6d-115">При установке и снятии этого флажка изменяется формат отображения столбцов времени, таких как **StartTime** и **EndTime**.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-115">Toggling this checkbox changes the time columns display format such as **StartTime** and **EndTime**.</span></span> <span data-ttu-id="d7c6d-116">Однако это не приводит к изменению значений параметров **DateTime**, передаваемых в языковых событиях или удаленных вызовах процедур (вызовах RPC).</span><span class="sxs-lookup"><span data-stu-id="d7c6d-116">However, it does not change the **DateTime** value parameters inside the language events or remote procedure calls (RPCs).</span></span>  
  
 <span data-ttu-id="d7c6d-117">**Показывать значения в столбце «Длительность» в микросекундах**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-117">**Show values in Duration column in microseconds**</span></span>  
 <span data-ttu-id="d7c6d-118">Выводит значения в миллисекундах в столбце данных трассировок **Продолжительность** .</span><span class="sxs-lookup"><span data-stu-id="d7c6d-118">Displays the values in microseconds in the **Duration** data column of traces.</span></span> <span data-ttu-id="d7c6d-119">По умолчанию в столбце **Продолжительность** отображаются значения в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-119">By default, the **Duration** column displays values in milliseconds.</span></span>  
  
### <a name="tracing-options"></a><span data-ttu-id="d7c6d-120">Параметры трассировки</span><span class="sxs-lookup"><span data-stu-id="d7c6d-120">Tracing Options</span></span>  
 <span data-ttu-id="d7c6d-121">**Начать трассировку немедленно после установки соединения**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-121">**Start tracing immediately after making connection**</span></span>  
 <span data-ttu-id="d7c6d-122">Начать трассировку с помощью шаблона по умолчанию сразу после установки соединения.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-122">Begin a trace using the default template as soon as a connection is made.</span></span>  
  
 <span data-ttu-id="d7c6d-123">**Обновить определение трассировки при изменении версии поставщика**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-123">**Update trace definition when provider version changes**</span></span>  
 <span data-ttu-id="d7c6d-124">Применить для [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] самое последнее определение трассировки, если обновляется поставщик.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-124">Apply the most current trace definition to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] when the provider is updated.</span></span> <span data-ttu-id="d7c6d-125">Этот элемент выключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-125">This item is not checked by default.</span></span> <span data-ttu-id="d7c6d-126">Тем самым приложение [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] принудительно запрашивает определение трассировки с сервера и заново создает соответствующий файл на диске, если таковой имеется.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-126">This forces [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to query the server for the trace definition and re-create, if one exists, the file on disk.</span></span>  
  
### <a name="file-rollover-options"></a><span data-ttu-id="d7c6d-127">Параметры переключения на файл продолжения</span><span class="sxs-lookup"><span data-stu-id="d7c6d-127">File Rollover Options</span></span>  
 <span data-ttu-id="d7c6d-128">**Загружать все файлы продолжения по порядку без дополнительных запросов**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-128">**Load all rollover files in sequence without prompting**</span></span>  
 <span data-ttu-id="d7c6d-129">Загружать файлы продолжения автоматически при открытии файла трассировки.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-129">Load rollover files automatically when a trace file is opened.</span></span> <span data-ttu-id="d7c6d-130">Если во время трассировки было создано более одного файла, то при выборе этого параметра автоматически загружаются все файлы продолжения.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-130">If more than one file was created while tracing, selecting this option automatically loads all rollover files.</span></span>  
  
 <span data-ttu-id="d7c6d-131">**Запрашивать перед загрузкой файлов продолжения**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-131">**Prompt before loading rollover files**</span></span>  
 <span data-ttu-id="d7c6d-132">При открытии файла трассировки перед добавлением файла продолжения выдается запрос приложения [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7c6d-132">Have [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] prompt you before adding a rollover file when a trace file is opened.</span></span>  
  
 <span data-ttu-id="d7c6d-133">**Никогда не загружать последующие файлы продолжения**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-133">**Never load subsequent rollover files**</span></span>  
 [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="d7c6d-134">никогда не загружает последующие файлы продолжения при открытии файла трассировки.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-134">never loads subsequent rollover files when a trace file is opened.</span></span>  
  
### <a name="replay-options"></a><span data-ttu-id="d7c6d-135">Параметры воспроизведения</span><span class="sxs-lookup"><span data-stu-id="d7c6d-135">Replay Options</span></span>  
 <span data-ttu-id="d7c6d-136">**Число потоков воспроизведения по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-136">**Default number of replay threads**</span></span>  
 <span data-ttu-id="d7c6d-137">Задайте число потоков воспроизведения, используемых одновременно.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-137">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="d7c6d-138">При более высоком значении потребляется больше ресурсов, но при этом увеличивается параллелизм воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-138">A higher number consumes more resources during replay, but increases replay concurrency.</span></span>  
  
 <span data-ttu-id="d7c6d-139">**Интервал опроса монитора исправности по умолчанию (сек)**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-139">**Default health monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="d7c6d-140">Задает интервал ожидания воспроизведения в секундах.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-140">Specify the wait interval to replay in seconds.</span></span> <span data-ttu-id="d7c6d-141">По умолчанию — 3 600 секунд (1 час).</span><span class="sxs-lookup"><span data-stu-id="d7c6d-141">Default is 3600 seconds (1 hour).</span></span> <span data-ttu-id="d7c6d-142">Этот параметр влияет на продолжительность времени, которое разрешается для выполнения потока, прежде чем его завершит монитор исправности.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-142">This setting affects the amount of time a thread is allowed to run before being terminated by the health monitor.</span></span>  
  
 <span data-ttu-id="d7c6d-143">**Интервал опроса монитора исправности по умолчанию (сек)**</span><span class="sxs-lookup"><span data-stu-id="d7c6d-143">**Default health monitor poll interval (sec)**</span></span>  
 <span data-ttu-id="d7c6d-144">Задайте интервал опроса монитора исправности во время воспроизведения в секундах.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-144">Specify the health monitor poll interval during replay in seconds.</span></span> <span data-ttu-id="d7c6d-145">По умолчанию — 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-145">Default is 60 seconds.</span></span> <span data-ttu-id="d7c6d-146">Это значение дает возможность пользователю определить, как часто монитор исправности выполняет опрос кандидатов на завершение.</span><span class="sxs-lookup"><span data-stu-id="d7c6d-146">This value allows the user to configure how often the health monitor polls for candidates for termination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7c6d-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="d7c6d-147">See Also</span></span>  
 <span data-ttu-id="d7c6d-148">[Автоматический запуск трассировки после подключения к серверу &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d7c6d-148">[Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="d7c6d-149">[Задать параметры по умолчанию для отображаемых данных трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d7c6d-149">[Set Trace Display Defaults &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="d7c6d-150">[Воспроизведение таблицы трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d7c6d-150">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="d7c6d-151">[Воспроизведение файла трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d7c6d-151">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="d7c6d-152">[Воспроизвести трассировки](../tools/sql-server-profiler/replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="d7c6d-152">[Replay Traces](../tools/sql-server-profiler/replay-traces.md) </span></span>  
 <span data-ttu-id="d7c6d-153">[Задать глобальные параметры трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d7c6d-153">[Set Global Trace Options &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="d7c6d-154">[Шаблоны и разрешения приложения SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="d7c6d-154">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="d7c6d-155">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="d7c6d-155">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
