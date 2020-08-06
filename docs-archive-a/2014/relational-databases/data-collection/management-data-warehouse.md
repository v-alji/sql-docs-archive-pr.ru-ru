---
title: Хранилище данных управления | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collector [SQL Server], management data warehouse
- data warehouse
- management data warehouse
ms.assetid: 9874a8b2-7ccd-494a-944c-ad33b30b5499
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 96eb26c3e273832aead4aa0421304df17dc5b8ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657816"
---
# <a name="management-data-warehouse"></a><span data-ttu-id="eaf7c-102">хранилище данных управления</span><span class="sxs-lookup"><span data-stu-id="eaf7c-102">Management Data Warehouse</span></span>
  <span data-ttu-id="eaf7c-103">Хранилище данных управления — это реляционная база данных, собираемых с сервера, который при сборе данных является целевым.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-103">The management data warehouse is a relational database that contains the data that is collected from a server that is a data collection target.</span></span> <span data-ttu-id="eaf7c-104">Эти данные используются при подготовке отчетов для наборов сбора системных данных и могут быть использованы для создания настраиваемых отчетов.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-104">This data is used to generate the reports for the System Data collection sets, and can also be used to create custom reports.</span></span>  
  
 <span data-ttu-id="eaf7c-105">Инфраструктура сборщика данных определяет планы выполнения заданий и планы обслуживания, необходимые для реализации политик хранения, определенных администратором базы данных.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-105">The data collector infrastructure defines the jobs and maintenance plans that are needed to implement the retention policies defined by the database administrator.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="eaf7c-106">В этой версии сборщика данных хранилище данных управления создается с помощью простой модели восстановления с целью минимизации объемов журнала.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-106">For this release of the data collector, the management data warehouse is created using the Simple recovery model, to minimize logging.</span></span> <span data-ttu-id="eaf7c-107">Для каждой организации следует реализовывать подходящую модель восстановления.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-107">You should implement the appropriate recovery model for your organization.</span></span>  
  
## <a name="deploying-and-using-the-data-warehouse"></a><span data-ttu-id="eaf7c-108">Развертывание и использование хранилища данных</span><span class="sxs-lookup"><span data-stu-id="eaf7c-108">Deploying and Using the Data Warehouse</span></span>  
 <span data-ttu-id="eaf7c-109">Хранилище данных управления можно установить на том же экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , на котором работает сборщик данных.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-109">You can install the management data warehouse on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that runs the data collector.</span></span> <span data-ttu-id="eaf7c-110">Однако, если ресурсы или производительность контролируемого сервера недостаточны, то хранилище данных управления можно установить на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-110">However, if server resources or performance is an issue on the server being monitored, you can install the management data warehouse on a different computer.</span></span>  
  
 <span data-ttu-id="eaf7c-111">При создании хранилища данных управления создаются необходимые схемы и их объекты для стандартных системных наборов сбора.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-111">The required schemas and their objects for the predefined system collection sets are created when you create the management data warehouse.</span></span> <span data-ttu-id="eaf7c-112">Создаются схемы core и snapshots. Третья схема, custom_snapshots, создается при создании наборов сбора (определенных пользователем), в которые входят элементы сбора, использующие тип сборщика "Универсальный запрос T-SQL".</span><span class="sxs-lookup"><span data-stu-id="eaf7c-112">The schemas that are created are core and snapshots.A third schema, custom_snapshots, is created when user-defined collection sets are created that include collection items that use the Generic T-SQL Query collector type.</span></span>  
  
###### <a name="core-schema"></a><span data-ttu-id="eaf7c-113">Схема core</span><span class="sxs-lookup"><span data-stu-id="eaf7c-113">Core schema</span></span>  
 <span data-ttu-id="eaf7c-114">Схема core определяет таблицы, хранимые процедуры и представления, используемые для организации и идентификации собранных данных.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-114">The core schema describes the tables, stored procedures, and views that are used to organize and to identify collected data.</span></span> <span data-ttu-id="eaf7c-115">Эти таблицы являются общими для всех таблиц данных, созданных для конкретных типов сборщика.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-115">These tables are shared among all the data tables created for individual collector types.</span></span> <span data-ttu-id="eaf7c-116">Эта схема заблокирована и может изменяться только владельцем базы данных хранилища данных управления.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-116">This schema is locked and can only be modified by the owner of the management data warehouse database.</span></span> <span data-ttu-id="eaf7c-117">Имена таблиц в этой схеме дополняются префиксом «core».</span><span class="sxs-lookup"><span data-stu-id="eaf7c-117">The names of the tables in this schema are prefixed by "core".</span></span>  
  
 <span data-ttu-id="eaf7c-118">В следующей таблице описаны таблицы базы данных в схеме core.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-118">The following table describes the database tables in the core schema.</span></span> <span data-ttu-id="eaf7c-119">Эти таблицы базы данных позволяют сборщику данных отслеживать источники данных, пользователей, вставивших данные, и время передачи в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-119">These database tables enable the data collector to track where the data came from, who inserted it, and when it was uploaded to the data warehouse.</span></span>  
  
|<span data-ttu-id="eaf7c-120">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="eaf7c-120">Table name</span></span>|<span data-ttu-id="eaf7c-121">Описание</span><span class="sxs-lookup"><span data-stu-id="eaf7c-121">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="eaf7c-122">core.performance_counter_report_group_items</span><span class="sxs-lookup"><span data-stu-id="eaf7c-122">core.performance_counter_report_group_items</span></span>|<span data-ttu-id="eaf7c-123">Хранит сведения о группировке отчетов из хранилища данных управления, а также статистику счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-123">Stores information about how the management data warehouse reports should group and aggregate performance counters.</span></span>|  
|<span data-ttu-id="eaf7c-124">core.snapshots_internal</span><span class="sxs-lookup"><span data-stu-id="eaf7c-124">core.snapshots_internal</span></span>|<span data-ttu-id="eaf7c-125">Определяет каждый новый моментальный снимок.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-125">Identifies each new snapshot.</span></span> <span data-ttu-id="eaf7c-126">Новая строка вставляется в эту таблицу каждый раз, когда пакет передачи начинает передачу нового пакета данных.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-126">A new row is inserted into this table whenever an upload package starts uploading a new batch of data.</span></span>|  
|<span data-ttu-id="eaf7c-127">core.snapshot_timetable_internal</span><span class="sxs-lookup"><span data-stu-id="eaf7c-127">core.snapshot_timetable_internal</span></span>|<span data-ttu-id="eaf7c-128">Хранит сведения о времени создания моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-128">Stores information about the snapshot times.</span></span> <span data-ttu-id="eaf7c-129">Время создания моментального снимка хранится в отдельной таблице, поскольку множество моментальных снимков может быть создано почти в одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-129">The snapshot time is stored in a separate table because many snapshots can happen at nearly the same time.</span></span>|  
|<span data-ttu-id="eaf7c-130">core.source.info_internal</span><span class="sxs-lookup"><span data-stu-id="eaf7c-130">core.source.info_internal</span></span>|<span data-ttu-id="eaf7c-131">В этой таблице хранятся сведения об источнике данных.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-131">This table stores information about the data source.</span></span> <span data-ttu-id="eaf7c-132">Эта таблица обновляется каждый раз, когда новый набор элементов сбора начинает передачу данных в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-132">This table is updated whenever a new collection set starts uploading data to the data warehouse.</span></span>|  
|<span data-ttu-id="eaf7c-133">core.supported_collector_types_internal</span><span class="sxs-lookup"><span data-stu-id="eaf7c-133">core.supported_collector_types_internal</span></span>|<span data-ttu-id="eaf7c-134">Содержит идентификаторы зарегистрированных типов сборщика, которые могут передавать данные в хранилище данных управления.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-134">Contains the IDs of registered collector types that can upload data to the management data warehouse.</span></span> <span data-ttu-id="eaf7c-135">Эта таблица обновляется только в тех случаях, когда схема хранилища обновляется для поддержки нового типа сборщика.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-135">This table is only updated when the schema of the warehouse is updated to support a new collector type.</span></span> <span data-ttu-id="eaf7c-136">При создании хранилища данных управления эта таблица заполняется идентификаторами типов сборщика, предоставленными сборщиком данных.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-136">When the management data warehouse is created, this table is populated with the IDs of the collector types provided by the data collector.</span></span>|  
|<span data-ttu-id="eaf7c-137">core.wait_categories</span><span class="sxs-lookup"><span data-stu-id="eaf7c-137">core.wait_categories</span></span>|<span data-ttu-id="eaf7c-138">Содержит категории, используемые для группирования типов ожидания в соответствии с характеристикой wait_type.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-138">Contains the categories used to group wait types according to wait_type characteristic.</span></span>|  
|<span data-ttu-id="eaf7c-139">core.wait_types</span><span class="sxs-lookup"><span data-stu-id="eaf7c-139">core.wait_types</span></span>|<span data-ttu-id="eaf7c-140">Содержит типы ожидания, распознаваемые сборщиком данных.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-140">Contains the wait types recognized by the data collector.</span></span>|  
|<span data-ttu-id="eaf7c-141">core.purge_info_internal</span><span class="sxs-lookup"><span data-stu-id="eaf7c-141">core.purge_info_internal</span></span>|<span data-ttu-id="eaf7c-142">Указывает, что был сделан запрос с целью остановить очистку хранилища данных управления.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-142">Indicates that a request has been made to stop the removal of data from the management data warehouse.</span></span>|  
  
 <span data-ttu-id="eaf7c-143">Предшествующие таблицы используются с таблицами типа сборщика для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-143">The preceding tables are used with collector type tables to store information.</span></span> <span data-ttu-id="eaf7c-144">Например, тип сборщика «Универсальная трассировка SQL» использует следующие таблицы для хранения данных трассировки:</span><span class="sxs-lookup"><span data-stu-id="eaf7c-144">For example, the Generic SQL Trace collector type uses the following tables to store trace data:</span></span>  
  
-   <span data-ttu-id="eaf7c-145">core.source_info_internal</span><span class="sxs-lookup"><span data-stu-id="eaf7c-145">core.source_info_internal</span></span>  
  
-   <span data-ttu-id="eaf7c-146">core.snapshots_internal</span><span class="sxs-lookup"><span data-stu-id="eaf7c-146">core.snapshots_internal</span></span>  
  
-   <span data-ttu-id="eaf7c-147">snapshots.trace_info</span><span class="sxs-lookup"><span data-stu-id="eaf7c-147">snapshots.trace_info</span></span>  
  
-   <span data-ttu-id="eaf7c-148">snapshots.trace_data</span><span class="sxs-lookup"><span data-stu-id="eaf7c-148">snapshots.trace_data</span></span>  
  
###### <a name="snapshots-schema"></a><span data-ttu-id="eaf7c-149">Схема snapshots</span><span class="sxs-lookup"><span data-stu-id="eaf7c-149">Snapshots schema</span></span>  
 <span data-ttu-id="eaf7c-150">Схема snapshots определяет объекты, необходимые для хранения и обслуживания данных, собранных предоставленными типами сборщиков.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-150">The snapshots schema describes the objects needed to store and maintain the data collected by the collector types that are provided.</span></span> <span data-ttu-id="eaf7c-151">Таблицы этой схемы являются постоянными, и в течение времени жизни типа сборщика их изменение не требуется.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-151">The tables in this schema are fixed and do not need to be changed during the lifetime of the collector type.</span></span> <span data-ttu-id="eaf7c-152">Если необходимы изменения, то данная схема может изменяться только членами роли mdw_admin.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-152">If changes are needed, the schema can only be changed by members of the mdw_admin role.</span></span> <span data-ttu-id="eaf7c-153">Эти таблицы создаются для хранения данных, собранных наборами сбора системных данных.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-153">These tables are created to store the data collected by the System Data collection sets.</span></span>  
  
 <span data-ttu-id="eaf7c-154">Следующие таблицы иллюстрируют фрагмент схемы хранилища управляющих данных, необходимый для наборов сбора активности сервера и статистики запросов.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-154">The following tables illustrate a portion of the management data warehouse schema that is required for the Server Activity and Query Statistics collection sets.</span></span>  
  
-   <span data-ttu-id="eaf7c-155">Таблицы ресурсов системного уровня</span><span class="sxs-lookup"><span data-stu-id="eaf7c-155">System-level resource tables</span></span>  
  
    -   <span data-ttu-id="eaf7c-156">**snapshots.os_wait_stats**</span><span class="sxs-lookup"><span data-stu-id="eaf7c-156">**snapshots.os_wait_stats**</span></span>  
  
    -   <span data-ttu-id="eaf7c-157">**snapshots.os_latch_stats**</span><span class="sxs-lookup"><span data-stu-id="eaf7c-157">**snapshots.os_latch_stats**</span></span>  
  
    -   <span data-ttu-id="eaf7c-158">**snapshots.os_schedulers**</span><span class="sxs-lookup"><span data-stu-id="eaf7c-158">**snapshots.os_schedulers**</span></span>  
  
    -   `snapshots.os_memory_clerks`  
  
    -   <span data-ttu-id="eaf7c-159">**snapshots.os_memory_nodes**</span><span class="sxs-lookup"><span data-stu-id="eaf7c-159">**snapshots.os_memory_nodes**</span></span>  
  
    -   <span data-ttu-id="eaf7c-160">snapshots.sql_process_and_system_memory</span><span class="sxs-lookup"><span data-stu-id="eaf7c-160">snapshots.sql_process_and_system_memory</span></span>  
  
-   <span data-ttu-id="eaf7c-161">Активность в системе</span><span class="sxs-lookup"><span data-stu-id="eaf7c-161">System activity</span></span>  
  
    -   <span data-ttu-id="eaf7c-162">snapshots.active_sessions_and_requests</span><span class="sxs-lookup"><span data-stu-id="eaf7c-162">snapshots.active_sessions_and_requests</span></span>  
  
-   <span data-ttu-id="eaf7c-163">Статистика запросов</span><span class="sxs-lookup"><span data-stu-id="eaf7c-163">Query statistics</span></span>  
  
    -   <span data-ttu-id="eaf7c-164">snapshots.query_stats</span><span class="sxs-lookup"><span data-stu-id="eaf7c-164">snapshots.query_stats</span></span>  
  
-   <span data-ttu-id="eaf7c-165">Статистика ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="eaf7c-165">I/O statistics</span></span>  
  
    -   `snapshots.io_virtual_file_stats`  
  
-   <span data-ttu-id="eaf7c-166">Текст и план запроса</span><span class="sxs-lookup"><span data-stu-id="eaf7c-166">Query text and plan</span></span>  
  
    -   <span data-ttu-id="eaf7c-167">snapshots.notable_query_text</span><span class="sxs-lookup"><span data-stu-id="eaf7c-167">snapshots.notable_query_text</span></span>  
  
    -   <span data-ttu-id="eaf7c-168">snapshots.notable_query_plan</span><span class="sxs-lookup"><span data-stu-id="eaf7c-168">snapshots.notable_query_plan</span></span>  
  
-   <span data-ttu-id="eaf7c-169">Статистика нормализованных запросов</span><span class="sxs-lookup"><span data-stu-id="eaf7c-169">Normalized query statistics</span></span>  
  
    -   <span data-ttu-id="eaf7c-170">snapshots.distinct_queries</span><span class="sxs-lookup"><span data-stu-id="eaf7c-170">snapshots.distinct_queries</span></span>  
  
    -   <span data-ttu-id="eaf7c-171">snapshots.distinct_query_to_handle</span><span class="sxs-lookup"><span data-stu-id="eaf7c-171">snapshots.distinct_query_to_handle</span></span>  
  
 <span data-ttu-id="eaf7c-172">**Схема custom_snapshots**</span><span class="sxs-lookup"><span data-stu-id="eaf7c-172">**Custom_snapshots schema**</span></span>  
  
 <span data-ttu-id="eaf7c-173">Схема custom_snapshots описывает новые таблицы и представления, которые создаются, когда стандартные или сторонние типы сборщика используются для создания пользовательских наборов сбора.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-173">The custom_snapshots schema describes new tables and views that are created when standard or third-party collector types are used to create user-defined collection sets.</span></span> <span data-ttu-id="eaf7c-174">Любой тип сборщика, которому необходима новая таблица данных для элемента сбора, может создать ее в этой схеме.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-174">Any collector type that requires a new data table for a collection item can create that table in this schema.</span></span> <span data-ttu-id="eaf7c-175">Новые таблицы могут быть добавлены в эту схему членами роли mdw_writer.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-175">New tables can be added in this schema by members of the mdw_writer role.</span></span> <span data-ttu-id="eaf7c-176">Любые другие изменения схемы могут выполнять только члены роли mdw_admin.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-176">Any other changes to the schema can only be made by members of the mdw_admin role.</span></span>  
  
 <span data-ttu-id="eaf7c-177">Подробные сведения о типе данных и содержимом столбцов таблиц базы данных можно получить из документации или с помощью соответствующей хранимой процедуры сборщика данных для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-177">You can get detailed data type and content information for the database table columns by reading the documentation for the appropriate data collector stored procedure for each of the tables.</span></span>  
  
### <a name="best-practices"></a><span data-ttu-id="eaf7c-178">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="eaf7c-178">Best Practices</span></span>  
 <span data-ttu-id="eaf7c-179">При работе с хранилищем управляющих данных рекомендуется следовать данным рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-179">When working with the management data warehouse, we recommend following these best practices:</span></span>  
  
-   <span data-ttu-id="eaf7c-180">Не изменяйте метаданные в таблицах хранилища управляющих данных за исключением тех случаев, когда происходит добавление нового типа сборщика.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-180">Do not modify the metadata of management data warehouse tables unless you are adding a new collector type.</span></span>  
  
-   <span data-ttu-id="eaf7c-181">Не изменяйте данные в хранилище управляющих данных напрямую.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-181">Do not directly modify the data in the management data warehouse.</span></span> <span data-ttu-id="eaf7c-182">Изменение собранных данных делает их недействительными.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-182">Changing the data that you have collected invalidates the legitimacy of the collected data.</span></span>  
  
-   <span data-ttu-id="eaf7c-183">Вместо непосредственного использования таблиц следует использовать документированные хранимые процедуры и функции, предоставляемые сборщиком данных для доступа к данным экземпляров и приложений.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-183">Instead of directly using the tables, use the documented stored procedures and functions that are provided with the data collector to access instance and application data.</span></span> <span data-ttu-id="eaf7c-184">Имена таблиц и определений могут меняться в процессе работы, изменяются при обновлении приложения и, возможно, изменятся в следующих версиях.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-184">The table names and definitions can change, do change when you update the application, and might change in future releases.</span></span>  
  
## <a name="change-history"></a><span data-ttu-id="eaf7c-185">Журнал изменений</span><span class="sxs-lookup"><span data-stu-id="eaf7c-185">Change History</span></span>  
  
|<span data-ttu-id="eaf7c-186">Обновленное содержимое</span><span class="sxs-lookup"><span data-stu-id="eaf7c-186">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="eaf7c-187">В раздел «Схема core» добавлена таблица core.performance_counter_report_group_items.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-187">Added the core.performance_counter_report_group_items table to the "Core schema" section.</span></span>|  
|<span data-ttu-id="eaf7c-188">Обновлен список таблиц в разделе «Схема snapshots».</span><span class="sxs-lookup"><span data-stu-id="eaf7c-188">Updated the list of tables in the "Snapshots schema" section.</span></span> <span data-ttu-id="eaf7c-189">Добавлены таблицы snapshots.os_memory_clerks, snapshots.sql_process_and_system_memory и snapshots.io_virtual_file_stats.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-189">Added snapshots.os_memory_clerks,snapshots.sql_process_and_system_memory, and snapshots.io_virtual_file_stats.</span></span> <span data-ttu-id="eaf7c-190">Удалены таблицы snapshots.os_process_memory и snapshots.distinct_query_stats.</span><span class="sxs-lookup"><span data-stu-id="eaf7c-190">Removedsnapshots.os_process_memory and snapshots.distinct_query_stats.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eaf7c-191">См. также:</span><span class="sxs-lookup"><span data-stu-id="eaf7c-191">See Also</span></span>  
 <span data-ttu-id="eaf7c-192">[Хранимые процедуры хранилища данных управления (Transact-SQL)](/sql/relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eaf7c-192">[Management Data Warehouse Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="eaf7c-193">[Хранимые процедуры сборщика данных (Transact-SQL)](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eaf7c-193">[Data Collector Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="eaf7c-194">[Сбор данных](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="eaf7c-194">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="eaf7c-195">Просмотр отчета о наборе элементов сбора (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="eaf7c-195">View a Collection Set Report &#40;SQL Server Management Studio&#41;</span></span>](view-a-collection-set-report-sql-server-management-studio.md)  
  
  
