---
title: Производительность сервера и мониторинг активности | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- activity monitoring [SQL Server]
- traces [SQL Server], how-to topics
- monitoring server performance [SQL Server], activity monitoring
- stored procedures [SQL Server], traces
- performance [SQL Server], servers
- servers [SQL Server], performance
- SQL Server Profiler, how-to topics
- SQL Server Management Studio [SQL Server], monitoring system
- Profiler [SQL Server Profiler], how-to topics
ms.assetid: f9abe48d-d6e9-4c38-a355-fc5eb5a95a25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a0fa7902d68c587a7733f07ceb8daccd3a6a98fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668825"
---
# <a name="server-performance-and-activity-monitoring"></a><span data-ttu-id="878f3-102">Производительность сервера и мониторинг активности</span><span class="sxs-lookup"><span data-stu-id="878f3-102">Server Performance and Activity Monitoring</span></span>
  <span data-ttu-id="878f3-103">Наблюдение за базами данных выполняется с целью оценки производительности сервера.</span><span class="sxs-lookup"><span data-stu-id="878f3-103">The goal of monitoring databases is to assess how a server is performing.</span></span> <span data-ttu-id="878f3-104">Эффективное наблюдение подразумевает регулярное создание моментальных снимков текущей производительности для обнаружения процессов, вызывающих неполадки, и постоянный сбор данных для отслеживания тенденций роста или изменения производительности.</span><span class="sxs-lookup"><span data-stu-id="878f3-104">Effective monitoring involves taking periodic snapshots of current performance to isolate processes that are causing problems, and gathering data continuously over time to track performance trends.</span></span> <span data-ttu-id="878f3-105">В состав [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и операционной системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows входят программы, позволяющие следить за текущим состоянием базы данных и измерять производительность по мере изменения состояния.</span><span class="sxs-lookup"><span data-stu-id="878f3-105">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows operating system provide utilities that let you view the current condition of the database and to track performance as conditions change.</span></span>  
  
 <span data-ttu-id="878f3-106">Далее приведены разделы, объясняющие использование средств наблюдения за производительностью и активностью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и Windows.</span><span class="sxs-lookup"><span data-stu-id="878f3-106">The following section contains topics that describe how to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows performance and activity monitoring tools.</span></span> <span data-ttu-id="878f3-107">Занятие содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="878f3-107">It contains the following topics:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="878f3-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="878f3-108">In This Section</span></span>  
 <span data-ttu-id="878f3-109">**Выполнение задач наблюдения с помощью средств Windows**</span><span class="sxs-lookup"><span data-stu-id="878f3-109">**To perform monitoring tasks with Windows tools**</span></span>  
  
-   [<span data-ttu-id="878f3-110">Запуск системного монитора (Windows)</span><span class="sxs-lookup"><span data-stu-id="878f3-110">Start System Monitor &#40;Windows&#41;</span></span>](start-system-monitor-windows.md)  
  
-   [<span data-ttu-id="878f3-111">Просмотр журнала приложений Windows (Windows)</span><span class="sxs-lookup"><span data-stu-id="878f3-111">View the Windows Application Log &#40;Windows&#41;</span></span>](view-the-windows-application-log-windows-10.md)  
  
 <span data-ttu-id="878f3-112">**Создание предупреждений базы данных SQL Server с помощью инструментов Windows**</span><span class="sxs-lookup"><span data-stu-id="878f3-112">**To create SQL Server database alerts with Windows tools**</span></span>  
  
-   [<span data-ttu-id="878f3-113">Настройка оповещения базы данных SQL Server (Windows)</span><span class="sxs-lookup"><span data-stu-id="878f3-113">Set Up a SQL Server Database Alert &#40;Windows&#41;</span></span>](set-up-a-sql-server-database-alert-windows.md)  
  
 <span data-ttu-id="878f3-114">**Выполнение задач наблюдения в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="878f3-114">**To perform monitoring tasks with SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="878f3-115">Просмотр журнала ошибок SQL Server (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="878f3-115">View the SQL Server Error Log &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="878f3-116">Открытие монитора активности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="878f3-116">Open Activity Monitor &#40;SQL Server Management Studio&#41;</span></span>](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)  
  
 <span data-ttu-id="878f3-117">**Выполнение задач наблюдения с помощью трассировки SQL с использованием хранимых процедур Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="878f3-117">**To perform monitoring tasks with SQL Trace by using Transact-SQL stored procedures**</span></span>  
  
-   [<span data-ttu-id="878f3-118">Создание трассировки (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="878f3-118">Create a Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/create-a-trace-transact-sql.md)  
  
-   [<span data-ttu-id="878f3-119">Создание фильтра трассировки (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="878f3-119">Set a Trace Filter &#40;Transact-SQL&#41;</span></span>](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md)  
  
-   [<span data-ttu-id="878f3-120">Изменение существующей трассировки (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="878f3-120">Modify an Existing Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/modify-an-existing-trace-transact-sql.md)  
  
-   [<span data-ttu-id="878f3-121">Просмотр сохраненной трассировки (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="878f3-121">View a Saved Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/view-a-saved-trace-transact-sql.md)  
  
-   [<span data-ttu-id="878f3-122">Просмотр сведений о фильтре (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="878f3-122">View Filter Information &#40;Transact-SQL&#41;</span></span>](../sql-trace/view-filter-information-transact-sql.md)  
  
-   [<span data-ttu-id="878f3-123">Удаление трассировки (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="878f3-123">Delete a Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/delete-a-trace-transact-sql.md)  
  
 <span data-ttu-id="878f3-124">**Создание и изменения трассировок с помощью приложения SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="878f3-124">**To create and modify traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="878f3-125">Создание трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-125">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-126">Настройка глобальных параметров трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-126">Set Global Trace Options &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-127">Указание столбцов событий и данных для файла трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-127">Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-128">Создание скрипта Transact-SQL для выполнения трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-128">Create a Transact-SQL Script for Running a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-transact-sql-script-for-running-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-129">Сохранение результатов трассировки в файл (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-129">Save Trace Results to a File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-130">Установка максимального размера для файла трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-130">Set a Maximum File Size for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-file-size-for-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-131">Сохранение результатов трассировки в таблицу (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-131">Save Trace Results to a Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-132">Установка максимального размера для таблицы трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-132">Set a Maximum Table Size for a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-table-size-for-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-133">Фильтрация событий в трассировке (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-133">Filter Events in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-134">Просмотр сведений о фильтре (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-134">View Filter Information &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-135">Изменение фильтра (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-135">Modify a Filter &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-136">Фильтрация событий по времени начала (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-136">Filter Events Based on the Event Start Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-start-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-137">Фильтрация событий по времени окончания (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-137">Filter Events Based on the Event End Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-138">Фильтрация идентификаторов серверных процессов (SPID) в трассировке (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-138">Filter Server Process IDs &#40;SPIDs&#41; in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-server-process-ids-spids-in-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-139">Упорядочивание столбцов, отображаемых в трассировке (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-139">Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md)  
  
 <span data-ttu-id="878f3-140">**Запуск, приостановка и полная остановка трассировок с помощью приложения SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="878f3-140">**To start, pause, and stop traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="878f3-141">Автоматический запуск трассировки после соединения с сервером (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-141">Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-142">Приостановка трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-142">Pause a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/pause-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-143">Остановка трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-143">Stop a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/stop-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-144">Проведение трассировки после паузы или остановки (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-144">Run a Trace After It Has Been Paused or Stopped &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
 <span data-ttu-id="878f3-145">**Открытие трассировок и конфигурации их отображения с помощью приложения SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="878f3-145">**To open traces and configure how traces are displayed by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="878f3-146">Открыть файл трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-146">Open a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-147">Открыть таблицу трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-147">Open a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-148">Очистка окна трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-148">Clear a Trace Window &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/clear-a-trace-window-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-149">Закрытие окна трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-149">Close a Trace Window &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/close-a-trace-window-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-150">Установка значений по умолчанию для определения трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-150">Set Trace Definition Defaults &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-trace-definition-defaults-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-151">Настройка параметров отображения трассировки по умолчанию (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-151">Set Trace Display Defaults &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)  
  
 <span data-ttu-id="878f3-152">**Воспроизведение трассировок с помощью приложения SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="878f3-152">**To replay traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="878f3-153">Воспроизведение файла трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-153">Replay a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-154">Воспроизведение таблицы трассировки (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-154">Replay a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-155">Воспроизведение одиночного события за раз (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-155">Replay a Single Event at a Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-single-event-at-a-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-156">Воспроизведение нагрузки до точки останова (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-156">Replay to a Breakpoint &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-to-a-breakpoint-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-157">Воспроизведение нагрузки до курсора (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-157">Replay to a Cursor &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-to-a-cursor-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-158">Воспроизведение скрипта на языке Transact-SQL (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-158">Replay a Transact-SQL Script &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-transact-sql-script-sql-server-profiler.md)  
  
 <span data-ttu-id="878f3-159">**Создание, изменение и использование шаблонов трассировок с помощью приложения SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="878f3-159">**To create, modify, and use trace templates by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="878f3-160">Создание шаблона трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-160">Create a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-161">Изменение шаблона трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-161">Modify a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/modify-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-162">Извлечь шаблон из выполняемой трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-162">Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-163">Извлечь шаблон из файла трассировки или таблицы трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-163">Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-164">Экспорт шаблона трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-164">Export a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/export-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-165">Импорт шаблона трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-165">Import a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/import-a-trace-template-sql-server-profiler.md)  
  
 <span data-ttu-id="878f3-166">**Использование приложения SQL Server Profiler с целью сбора данных о производительности сервера мониторинга**</span><span class="sxs-lookup"><span data-stu-id="878f3-166">**To use SQL Server Profiler traces to collect and monitor server performance**</span></span>  
  
-   [<span data-ttu-id="878f3-167">Поиск значения или столбца данных во время трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-167">Find a Value or Data Column While Tracing &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-168">Сохранение графов взаимоблокировок (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-168">Save Deadlock Graphs &#40;SQL Server Profiler&#41;</span></span>](save-deadlock-graphs-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-169">Раздельное сохранение событий Showplan XML (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-169">Save Showplan XML Events Separately &#40;SQL Server Profiler&#41;</span></span>](save-showplan-xml-events-separately-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-170">Раздельное сохранение событий Showplan XML Statistics Profile (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-170">Save Showplan XML Statistics Profile Events Separately &#40;SQL Server Profiler&#41;</span></span>](save-showplan-xml-statistics-profile-events-separately-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-171">Извлечение скрипта из трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-171">Extract a Script from a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/extract-a-script-from-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="878f3-172">Сопоставить трассировку с данными журнала производительности Windows (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="878f3-172">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
