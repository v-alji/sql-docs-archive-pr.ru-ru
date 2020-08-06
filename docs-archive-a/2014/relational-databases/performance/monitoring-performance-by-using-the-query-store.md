---
title: Мониторинг производительности с использованием хранилища запросов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: e06344a4-22a5-4c67-b6c6-a7060deb5de6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e5d74b9c4def9c0314569a8d0bd87939cdcb11b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668258"
---
# <a name="monitoring-performance-by-using-the-query-store"></a><span data-ttu-id="e1f27-102">Monitoring Performance By Using the Query Store</span><span class="sxs-lookup"><span data-stu-id="e1f27-102">Monitoring Performance By Using the Query Store</span></span>
  <span data-ttu-id="e1f27-103">Хранилище запросов предоставляет DBA подробные сведения о выборе и производительности плана запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-103">The query store feature provides DBAs with insight on query plan choice and performance.</span></span> <span data-ttu-id="e1f27-104">Оно упрощает устранение неполадок с производительностью, позволяя быстро находить разницу в производительности, вызванную изменениями в планах запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-104">It simplifies performance troubleshooting by enabling you to quickly find performance differences caused by changes in query plans.</span></span> <span data-ttu-id="e1f27-105">Функция автоматически записывает журнал запросов, планы и статистику выполнения и сохраняет их для просмотра.</span><span class="sxs-lookup"><span data-stu-id="e1f27-105">The feature automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.</span></span> <span data-ttu-id="e1f27-106">Она разделяет данные по временным окнам, позволяя просмотреть шаблоны использования и понять, когда изменения плана запросов произошли на сервере.</span><span class="sxs-lookup"><span data-stu-id="e1f27-106">It separates data by time windows, allowing you to see database usage patterns and understand when query plan changes happened on the server.</span></span> <span data-ttu-id="e1f27-107">Хранилище запросов можно настроить с помощью параметра [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="e1f27-107">The query store can be configured by using the [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) option.</span></span>

||
|-|
|<span data-ttu-id="e1f27-108">**Применимо к**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] ([получить](http://azure.micosoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span><span class="sxs-lookup"><span data-stu-id="e1f27-108">**Applies to**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] ([Get it](http://azure.micosoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="e1f27-109">В настоящий момент это предварительная версия функции.</span><span class="sxs-lookup"><span data-stu-id="e1f27-109">This is currently a preview feature.</span></span> <span data-ttu-id="e1f27-110">Чтобы использовать хранилище запросов, вы должны подтвердить свое согласие с тем, что реализация хранилища запросов соответствует условиям лицензионного соглашения предварительной версии (например, соглашения Enterprise, соглашения для Microsoft Azure или соглашения Microsoft Online Subscription), а также всем применимым [Дополнительным условиям использования для предварительной версии Microsoft Azure](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span><span class="sxs-lookup"><span data-stu-id="e1f27-110">To use the Query Store you must acknowledge and agree that implementation of Query Store is subject to the preview terms in your license agreement (e.g. the Enterprise Agreement, Microsoft Azure Agreement, or Microsoft Online Subscription Agreement), as well as any applicable [Supplemental Terms of Use for Microsoft Azure Preview](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span></span>

##  <a name="enabling-the-query-store"></a><a name="Enabling"></a> <span data-ttu-id="e1f27-111">Включение хранилища запросов</span><span class="sxs-lookup"><span data-stu-id="e1f27-111">Enabling the Query Store</span></span>
 <span data-ttu-id="e1f27-112">Хранилище запросов неактивно для новых баз данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e1f27-112">Query Store is not active for new databases by default.</span></span>

#### <a name="by-using-the-query-store-page-in-management-studio"></a><span data-ttu-id="e1f27-113">На странице «Хранилище запросов» в Management Studio</span><span class="sxs-lookup"><span data-stu-id="e1f27-113">By Using the Query Store Page in Management Studio</span></span>

1.  <span data-ttu-id="e1f27-114">В обозревателе объектов щелкните правой кнопкой мыши базу данных и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e1f27-114">In Object Explorer, right-click a database, and then click **Properties**.</span></span> <span data-ttu-id="e1f27-115">(Требуется версия [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2016 для [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="e1f27-115">(Requires [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2016 version of [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].)</span></span>

2.  <span data-ttu-id="e1f27-116">В диалоговом окне **Свойства базы данных** перейдите на страницу **Хранилище запросов** .</span><span class="sxs-lookup"><span data-stu-id="e1f27-116">In the **Database Properties** dialog box, select the **Query Store** page.</span></span>

3.  <span data-ttu-id="e1f27-117">В окне **Включение** выберите **True**.</span><span class="sxs-lookup"><span data-stu-id="e1f27-117">In the **Enable** box, select **True**.</span></span>

#### <a name="by-using-transact-sql-statements"></a><span data-ttu-id="e1f27-118">Используя инструкции Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e1f27-118">By Using Transact-SQL Statements</span></span>

1.  <span data-ttu-id="e1f27-119">Используйте инструкцию `ALTER DATABASE`, чтобы включить хранилище запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-119">Use the `ALTER DATABASE` statement to enable the query store.</span></span> <span data-ttu-id="e1f27-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="e1f27-120">For example:</span></span>

    ```
    ALTER DATABASE AdventureWorks2012 SET QUERY_STORE = ON;
    ```

     <span data-ttu-id="e1f27-121">Дополнительные параметры синтаксиса, связанные с хранилищем запросов, см. в разделе [Параметры ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="e1f27-121">For more syntax options related to the query store, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>

> [!NOTE]
>  <span data-ttu-id="e1f27-122">Невозможно включить хранилище запросов для базы данных master.</span><span class="sxs-lookup"><span data-stu-id="e1f27-122">You cannot enable the query store for the master database.</span></span>



##  <a name="information-in-the-query-store"></a><a name="About"></a> <span data-ttu-id="e1f27-123">Сведения о хранилище запросов</span><span class="sxs-lookup"><span data-stu-id="e1f27-123">Information in the Query Store</span></span>
 <span data-ttu-id="e1f27-124">Планы выполнения для любого специального запроса в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] обычно меняются со временем по разным причинам, например из-за изменения статистики, схемы, создания и удаления индексов и т. д. В кэше процедур (где хранятся кэшированные планы запросов) хранится только последний план выполнения.</span><span class="sxs-lookup"><span data-stu-id="e1f27-124">Execution plans for any specific query in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] typically evolve over time due to a number of different reasons such as statistics changes, schema changes, creation/deletion of indexes, etc. The procedure cache (where cached query plans are stored) only stores the latest execution plan.</span></span> <span data-ttu-id="e1f27-125">Планы исключаются из кэша планов из-за нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="e1f27-125">Plans also get evicted from the plan cache due to memory pressure.</span></span> <span data-ttu-id="e1f27-126">В результате устранение проблем со снижением производительности запросов, вызванным изменениями планов выполнения, может оказаться сложным и требующим много времени.</span><span class="sxs-lookup"><span data-stu-id="e1f27-126">As a result, query performance regressions caused by execution plan changes can be non-trivial and time consuming to resolve.</span></span>

 <span data-ttu-id="e1f27-127">Так как хранилище запросов сохраняет несколько планов выполнения на запрос, оно может принудительно применить политики, чтобы заставить процессор запросов использовать конкретный план выполнения для запроса.</span><span class="sxs-lookup"><span data-stu-id="e1f27-127">Since the query store retains multiple execution plans per query, it can enforce policies to direct the query processor to use a specific execution plan for a query.</span></span> <span data-ttu-id="e1f27-128">Это называется принудительным выполнением плана.</span><span class="sxs-lookup"><span data-stu-id="e1f27-128">This is referred to as plan forcing.</span></span> <span data-ttu-id="e1f27-129">Принудительное выполнение плана в хранилище запросов обеспечивается с использованием механизма, аналогичного указанию запроса [USE PLAN](/sql/t-sql/queries/hints-transact-sql-query) , но не требует изменений в приложениях пользователей.</span><span class="sxs-lookup"><span data-stu-id="e1f27-129">Plan forcing in Query Store is provided by using a mechanism similar to the [USE PLAN](/sql/t-sql/queries/hints-transact-sql-query) query hint, but it does not require any change in user applications.</span></span> <span data-ttu-id="e1f27-130">Принудительное выполнение плана может решить проблему со снижением производительности запросов, вызванным изменением плана за очень короткий период времени.</span><span class="sxs-lookup"><span data-stu-id="e1f27-130">Plan forcing can resolve a query performance regression caused by a plan change in a very short period of time.</span></span>

 <span data-ttu-id="e1f27-131">Ниже перечислены стандартные сценарии использования хранилища запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-131">Common scenarios for using the Query Store feature are:</span></span>

-   <span data-ttu-id="e1f27-132">Быстрый поиск и устранение снижения производительности планов путем принудительного выполнения предыдущего плана запроса.</span><span class="sxs-lookup"><span data-stu-id="e1f27-132">Quickly find and fix a plan performance regression by forcing the previous query plan.</span></span> <span data-ttu-id="e1f27-133">Исправление запросов, производительность которых была недавно снижена из-за изменений в планах выполнения.</span><span class="sxs-lookup"><span data-stu-id="e1f27-133">Fix queries that have recently regressed in performance due to execution plan changes.</span></span>

-   <span data-ttu-id="e1f27-134">Определение количества выполнений запросов за заданный период времени и помощь DBA в устранении неполадок с производительностью ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-134">Determine the number of times a query was executed in a given time window, assisting a DBA in troubleshooting performance resource problems.</span></span>

-   <span data-ttu-id="e1f27-135">Определение первых *n* запросов (по времени выполнения, потреблению памяти и т. д.) за последние *x* часов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-135">Identify top *n* queries (by execution time, memory consumption, etc.) in the past *x* hours.</span></span>

-   <span data-ttu-id="e1f27-136">Аудит журнала планов запросов для указанного запроса.</span><span class="sxs-lookup"><span data-stu-id="e1f27-136">Audit the history of query plans for a given query.</span></span>

-   <span data-ttu-id="e1f27-137">Анализ шаблонов использования ресурсов (ЦП, операций ввода-вывода и памяти) для определенной базы данных.</span><span class="sxs-lookup"><span data-stu-id="e1f27-137">Analyze the resource (CPU, I/O, and Memory) usage patterns for a particular database.</span></span>

 <span data-ttu-id="e1f27-138">Хранилище запросов содержит два хранилища: **хранилище планов** для сохранения сведений о планах выполнения и **хранилище статистики времени выполнения** для сохранения сведений о статистике выполнения.</span><span class="sxs-lookup"><span data-stu-id="e1f27-138">The query store contains two stores; a **plan store** for persisting the execution plan information, and a **runtime stats store** for persisting the execution statistics information.</span></span> <span data-ttu-id="e1f27-139">Количество уникальных планов, которые можно сохранить для запроса в хранилище планов, ограничено параметром конфигурации `max_plans_per_query`.</span><span class="sxs-lookup"><span data-stu-id="e1f27-139">The number of unique plans that can be stored for a query in the plan store is limited by the `max_plans_per_query` configuration option.</span></span> <span data-ttu-id="e1f27-140">Для повышения производительности сведения записываются в два хранилища асинхронно.</span><span class="sxs-lookup"><span data-stu-id="e1f27-140">To enhance performance, the information is written to the two stores asynchronously.</span></span> <span data-ttu-id="e1f27-141">Для уменьшения использования свободного места статистические данные времени выполнения в хранилище вычисляются для фиксированного интервала времени.</span><span class="sxs-lookup"><span data-stu-id="e1f27-141">To minimize space usage, the runtime execution statistics in the runtime stats store are aggregated over a fixed time window.</span></span> <span data-ttu-id="e1f27-142">Сведения в этих хранилищах видны при запросе представлений каталога в хранилище запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-142">The information in these stores is visible by querying the query store catalog views.</span></span>

 <span data-ttu-id="e1f27-143">Следующий запрос возвращает сведения о запросах и планах в хранилище запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-143">The following query returns information about queries and plans in the query store.</span></span>

```
SELECT Txt.query_text_id, Txt.query_sql_text, Pl.plan_id, Qry.*
FROM sys.query_store_plan AS Pl
JOIN sys.query_store_query AS Qry
    ON Pl.query_id = Qry.query_id
JOIN sys.query_store_query_text AS Txt
    ON Qry.query_text_id = Txt.query_text_id ;
```



## <a name="using-the-regressed-queries-feature"></a><span data-ttu-id="e1f27-144">Использование функции сниженных запросов</span><span class="sxs-lookup"><span data-stu-id="e1f27-144">Using the Regressed Queries Feature</span></span>
 <span data-ttu-id="e1f27-145">После включения хранилища запросов обновите часть базы данных на панели Обозреватель объектов, чтобы добавить раздел **хранилище запросов** .</span><span class="sxs-lookup"><span data-stu-id="e1f27-145">After enabling the query store, refresh the database portion of the Object Explorer pane to add the **Query Store** section.</span></span>

 <span data-ttu-id="e1f27-146">![QueryStore](../../database-engine/media/querystore.PNG "QueryStore")</span><span class="sxs-lookup"><span data-stu-id="e1f27-146">![QueryStore](../../database-engine/media/querystore.PNG "QueryStore")</span></span>

 <span data-ttu-id="e1f27-147">При выборе пункта **Сниженные запросы**открывается панель **Сниженные запросы** в [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1f27-147">Selecting **Regressed Queries**, opens the **Regressed Queries** pane in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="e1f27-148">На панели «Сниженные запросы» отображаются запросы и планы в хранилище запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-148">The Regressed Queries pane shows you the queries, and plans in the query store.</span></span> <span data-ttu-id="e1f27-149">В раскрывающихся списках наверху можно выбрать запросы на основе разных условий.</span><span class="sxs-lookup"><span data-stu-id="e1f27-149">Drop down boxes at the top allow you to select queries based on various criteria.</span></span> <span data-ttu-id="e1f27-150">Выберите план для просмотра графического плана запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-150">Select a plan to see the graphical query plan.</span></span> <span data-ttu-id="e1f27-151">С помощью кнопок можно просмотреть исходный запрос, принудительно применить и отменить план запросов, а также обновить отображаемые на экране сведения.</span><span class="sxs-lookup"><span data-stu-id="e1f27-151">Buttons are available to view the source query, force, and unforce a query plan, and refresh the display.</span></span>

 <span data-ttu-id="e1f27-152">![регресседкуериес](../../database-engine/media/regressedqueries.PNG "регресседкуериес")</span><span class="sxs-lookup"><span data-stu-id="e1f27-152">![RegressedQueries](../../database-engine/media/regressedqueries.PNG "RegressedQueries")</span></span>

 <span data-ttu-id="e1f27-153">Чтобы принудительно применить план, выберите запрос и план, а затем нажмите кнопку **принудительно спланировать.**</span><span class="sxs-lookup"><span data-stu-id="e1f27-153">To force a plan, select a query and plan, and then click **Force Plan.**</span></span> <span data-ttu-id="e1f27-154">Принудительно выполнять можно только те планы, которые были сохранены с помощью функции плана запросов и все еще хранятся в кэше плана запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-154">You can only force plans that were saved by the query plan feature and are still retained in the query plan cache.</span></span>



##  <a name="configuration-options"></a><a name="Options"></a> <span data-ttu-id="e1f27-155">Параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="e1f27-155">Configuration Options</span></span>
 <span data-ttu-id="e1f27-156">OPERATION_MODE может быть READ_WRITE или READ_ONLY.</span><span class="sxs-lookup"><span data-stu-id="e1f27-156">OPERATION_MODE Can be READ_WRITE or READ_ONLY.</span></span>

 <span data-ttu-id="e1f27-157">CLEANUP_POLICY настроить аргумент STALE_QUERY_THRESHOLD_DAYS, чтобы указать число дней хранения данных в хранилище запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-157">CLEANUP_POLICY Configure the STALE_QUERY_THRESHOLD_DAYS argument to specify the number of days to retain data in the query store.</span></span>

 <span data-ttu-id="e1f27-158">DATA_FLUSH_INTERVAL_SECONDS определяет частоту, с которой данные, записанные в хранилище запросов, сохраняются на диск.</span><span class="sxs-lookup"><span data-stu-id="e1f27-158">DATA_FLUSH_INTERVAL_SECONDS Determines the frequency at which data written to the query store is persisted to disk.</span></span> <span data-ttu-id="e1f27-159">Для оптимизации производительности данные, собранные хранилищем запросов, асинхронно записываются на диск.</span><span class="sxs-lookup"><span data-stu-id="e1f27-159">To optimize for performance, data collected by the query store is asynchronously written to the disk.</span></span> <span data-ttu-id="e1f27-160">Частота, с которой происходит эта асинхронная передача, настраивается с помощью параметра DATA_FLUSH_INTERVAL_SECONDS.</span><span class="sxs-lookup"><span data-stu-id="e1f27-160">The frequency at which this asynchronous transfer occurs is configured via DATA_FLUSH_INTERVAL_SECONDS.</span></span>

 <span data-ttu-id="e1f27-161">MAX_SIZE_MB настраивает максимальный размер хранилища запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-161">MAX_SIZE_MB Configures the maximum size of the query store.</span></span> <span data-ttu-id="e1f27-162">Если данные в хранилище запросов достигают размера MAX_SIZE_MB, хранилище запроса автоматически изменяет состояние с read-write на read-only и останавливает сбор новых данных.</span><span class="sxs-lookup"><span data-stu-id="e1f27-162">If the data in the query store hits the MAX_SIZE_MB limit, the query store automatically changes the state from read-write to read-only and stops collecting new data.</span></span>

 <span data-ttu-id="e1f27-163">INTERVAL_LENGTH_MINUTES определяет интервал времени вычисления статистических данных о среде выполнения в хранилище запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-163">INTERVAL_LENGTH_MINUTES Determines the time interval at which runtime execution statistics data is aggregated into the query store.</span></span> <span data-ttu-id="e1f27-164">Для оптимизации использования свободного места статистические данные времени выполнения в хранилище вычисляются для фиксированного интервала времени.</span><span class="sxs-lookup"><span data-stu-id="e1f27-164">To optimize for space usage, the runtime execution statistics in the Runtime Stats Store are aggregated over a fixed time window.</span></span> <span data-ttu-id="e1f27-165">Этот интервал настраивается с помощью параметра INTERVAL_LENGTH_MINUTES.</span><span class="sxs-lookup"><span data-stu-id="e1f27-165">This fixed time window is configured via INTERVAL_LENGTH_MINUTES.</span></span>

 <span data-ttu-id="e1f27-166">Запросите представление `sys.database_query_store_options`, чтобы определить текущие параметры хранилища запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-166">Query the `sys.database_query_store_options` view to determine the current options of the query store.</span></span>

 <span data-ttu-id="e1f27-167">Дополнительные сведения о настройке параметров с помощью инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] см. в разделе [Управление параметрами](#OptionMgmt).</span><span class="sxs-lookup"><span data-stu-id="e1f27-167">For more information about setting options by using [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, see [Option Management](#OptionMgmt).</span></span>

 

##  <a name="related-views-functions-and-procedures"></a><a name="Related"></a> <span data-ttu-id="e1f27-168">Связанные представления, функции и процедуры</span><span class="sxs-lookup"><span data-stu-id="e1f27-168">Related Views, Functions, and Procedures</span></span>
 <span data-ttu-id="e1f27-169">Хранилище запросов можно просмотреть и контролировать в [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] либо с помощью следующих представлений и процедур.</span><span class="sxs-lookup"><span data-stu-id="e1f27-169">The Query Store can be viewed and managed through [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] or by using the following views and procedures.</span></span>

-   [<span data-ttu-id="e1f27-170">sys.fn_stmt_sql_handle_from_sql_stmt (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-170">sys.fn_stmt_sql_handle_from_sql_stmt &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-stmt-sql-handle-from-sql-stmt-transact-sql)

### <a name="query-store-catalog-views"></a><span data-ttu-id="e1f27-171">Представления каталога хранилища запросов</span><span class="sxs-lookup"><span data-stu-id="e1f27-171">Query Store Catalog Views</span></span>
 <span data-ttu-id="e1f27-172">В семи представлениях каталога представлены сведения о хранилище запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-172">Seven catalog views present information about the Query Store.</span></span>

-   [<span data-ttu-id="e1f27-173">sys.database_query_store_options (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-173">sys.database_query_store_options &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-query-store-options-transact-sql)

-   [<span data-ttu-id="e1f27-174">sys.query_context_settings (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-174">sys.query_context_settings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-context-settings-transact-sql)

-   [<span data-ttu-id="e1f27-175">sys.query_store_plan (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-175">sys.query_store_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-plan-transact-sql)

-   [<span data-ttu-id="e1f27-176">sys.query_store_query (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-176">sys.query_store_query &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-query-transact-sql)

-   [<span data-ttu-id="e1f27-177">sys.query_store_query_text (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-177">sys.query_store_query_text &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-query-text-transact-sql)

-   [<span data-ttu-id="e1f27-178">sys.query_store_runtime_stats (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-178">sys.query_store_runtime_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-transact-sql)

-   [<span data-ttu-id="e1f27-179">sys.query_store_runtime_stats_interval (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-179">sys.query_store_runtime_stats_interval &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-interval-transact-sql)

### <a name="query-store-stored-procedures"></a><span data-ttu-id="e1f27-180">Хранимые процедуры в хранилище запросов,</span><span class="sxs-lookup"><span data-stu-id="e1f27-180">Query Store Stored Procedures</span></span>
 <span data-ttu-id="e1f27-181">Шесть хранимых процедур настраивают хранилище запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-181">Six stored procedures configure the Query Store.</span></span>

-   [<span data-ttu-id="e1f27-182">sp_query_store_flush_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e1f27-182">sp_query_store_flush_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-flush-db-transact-sql)

-   [<span data-ttu-id="e1f27-183">sp_query_store_reset_exec_stats (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-183">sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-reset-exec-stats-transact-sql)

-   [<span data-ttu-id="e1f27-184">sp_query_store_force_plan (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-184">sp_query_store_force_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-force-plan-transact-sql)

-   [<span data-ttu-id="e1f27-185">sp_query_store_unforce_plan (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-185">sp_query_store_unforce_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-unforce-plan-transact-sql)

-   [<span data-ttu-id="e1f27-186">sp_query_store_remove_plan (Transct-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-186">sp_query_store_remove_plan &#40;Transct-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-remove-plan-transct-sql)

-   [<span data-ttu-id="e1f27-187">sp_query_store_remove_query (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1f27-187">sp_query_store_remove_query &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-remove-query-transact-sql)



##  <a name="key-usage-scenarios"></a><a name="Scenarios"></a> <span data-ttu-id="e1f27-188">Основные сценарии использования</span><span class="sxs-lookup"><span data-stu-id="e1f27-188">Key Usage Scenarios</span></span>

###  <a name="option-management"></a><a name="OptionMgmt"></a> <span data-ttu-id="e1f27-189">Управление параметрами</span><span class="sxs-lookup"><span data-stu-id="e1f27-189">Option Management</span></span>
 <span data-ttu-id="e1f27-190">В этом разделе представлены некоторые рекомендации по управлению самой функцией хранилища запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-190">This section provides some guidelines on managing Query Store feature itself.</span></span>

 <span data-ttu-id="e1f27-191">**Активно ли сейчас хранилище запросов?**</span><span class="sxs-lookup"><span data-stu-id="e1f27-191">**Is Query Store currently active?**</span></span>

 <span data-ttu-id="e1f27-192">Данные в хранилище запросов содержатся в базе данных пользователя, поэтому их размер ограничен (настраивается с помощью `MAX_STORAGE_SIZE_MB`).</span><span class="sxs-lookup"><span data-stu-id="e1f27-192">Query Store stores its data inside the user database and that is why it has size limit (configured  with `MAX_STORAGE_SIZE_MB`).</span></span> <span data-ttu-id="e1f27-193">Если размер данных в хранилище запросов достигнет предела, хранилище запросов автоматически изменит состояние с read-write на read-only и перестанет собирать новые данные.</span><span class="sxs-lookup"><span data-stu-id="e1f27-193">If data in Query Store hits that limit Query Store will automatically change state from read-write to read-only and stop collecting new data.</span></span>

 <span data-ttu-id="e1f27-194">Выполните следующий сценарий, чтобы определить, активно ли хранилище запросов и собирает ли оно статистику времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="e1f27-194">Execute the following script to determine if Query Store is currently active, and whether it is currently collects runtime stats or not.</span></span>

```
DECLARE @x nvarchar(100) = CAST(newid() AS nvarchar(100));
DECLARE @query nvarchar(max) = 
N'IF EXISTS
(
    SELECT * 
    FROM sys.query_store_query_text 
    WHERE query_sql_text LIKE ''%' + @x + N'%''
)
SELECT ''Query Store is active'' ;
ELSE SELECT ''Query Store is NOT active''' ;
EXEC sp_executesql @query;
```

 <span data-ttu-id="e1f27-195">**Получение параметров запросов**</span><span class="sxs-lookup"><span data-stu-id="e1f27-195">**Get Query Store options**</span></span>

 <span data-ttu-id="e1f27-196">Чтобы найти подробные сведения о состоянии хранилища запросов, выполните следующую команду в базе данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="e1f27-196">To find out detailed information about Query Store status, execute following in a user database.</span></span>

```
SELECT * FROM sys.database_query_store_options;
```

 <span data-ttu-id="e1f27-197">**Задание интервала для хранилища запросов**</span><span class="sxs-lookup"><span data-stu-id="e1f27-197">**Setting Query Store interval**</span></span>

 <span data-ttu-id="e1f27-198">Вы можете переопределить интервал для объединения статистики времени выполнения запросов (по умолчанию — 60 минут).</span><span class="sxs-lookup"><span data-stu-id="e1f27-198">You can override interval for aggregating query runtime statistics (default is 60 minutes).</span></span>

```

      USE master;
GO

ALTER DATABASE <database_name> 
SET QUERY_STORE (INTERVAL_LENGTH_MINUTES = 15);
```

 <span data-ttu-id="e1f27-199">Обратите внимание, что произвольные значения не допускаются. Следует использовать одно из следующих значений: 1, 5, 10, 15, 30 или 60.</span><span class="sxs-lookup"><span data-stu-id="e1f27-199">Note that arbitrary values are not allowed - you should use one of the following: 1, 5, 10, 15, 30 and 60.</span></span>

 <span data-ttu-id="e1f27-200">Новое значение интервала находится в представлении `sys.database_query_store_options`.</span><span class="sxs-lookup"><span data-stu-id="e1f27-200">New value for interval is exposed through `sys.database_query_store_options` view.</span></span>

 <span data-ttu-id="e1f27-201">Если хранилище запросов заполнено, используйте следующую инструкцию для его расширения.</span><span class="sxs-lookup"><span data-stu-id="e1f27-201">If the Query Store storage is full use the following statement to extend the storage.</span></span>

```
ALTER DATABASE <database_name> 
SET QUERY_STORE (MAX_STORAGE_SIZE_MB = <new_size>);
```

 <span data-ttu-id="e1f27-202">**Задание всех параметров для хранилища запросов**</span><span class="sxs-lookup"><span data-stu-id="e1f27-202">**Set all Query Store options**</span></span>

 <span data-ttu-id="e1f27-203">Вы можете задать несколько параметров хранилища запросов одновременно с помощью одной инструкции ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="e1f27-203">You can set multiple Query Store options at once with a single ALTER DATABASE statement.</span></span>

```
ALTER DATABASE <database name> 
SET QUERY_STORE (
    OPERATION_MODE = READ_WRITE,
    CLEANUP_POLICY = 
    (STALE_QUERY_THRESHOLD_DAYS = 30),
    DATA_FLUSH_INTERVAL_SECONDS = 3000,
    MAX_STORAGE_SIZE_MB = 500,
    INTERVAL_LENGTH_MINUTES = 15
);
```

 <span data-ttu-id="e1f27-204">**Очистка пространства**</span><span class="sxs-lookup"><span data-stu-id="e1f27-204">**Cleaning up the space**</span></span>

 <span data-ttu-id="e1f27-205">Внутренние таблицы хранилища запросов создаются в группе файлов PRIMARY во время создания базы данных, и эту конфигурацию невозможно изменить позже.</span><span class="sxs-lookup"><span data-stu-id="e1f27-205">Query Store internal tables are created in the PRIMARY filegroup during database creation and that configuration cannot be changed later.</span></span> <span data-ttu-id="e1f27-206">Если у вас заканчивается место, следует удалить более старые данные из хранилища запросов с помощью следующей инструкции.</span><span class="sxs-lookup"><span data-stu-id="e1f27-206">If you are running out of space you might want to clear older Query Store data by using the following statement.</span></span>

```
ALTER DATABASE <db_name> SET QUERY_STORE CLEAR;
```

 <span data-ttu-id="e1f27-207">Кроме того, можно очистить только данные ad-hoc-запросов, так как они менее актуальны для оптимизации запросов и анализа планов, но занимают столько же места.</span><span class="sxs-lookup"><span data-stu-id="e1f27-207">Alternatively, you might want to clear up only ad-hoc query data, since it is less relevant for query optimizations and plan analysis but takes up just as much space.</span></span>

 <span data-ttu-id="e1f27-208">**Удаление нерегламентированных запросов** . Эта функция удаляет запросы, которые были выполнены только один раз более 24 часов назад.</span><span class="sxs-lookup"><span data-stu-id="e1f27-208">**Delete ad-hoc queries** This deletes the queries that were only executed only once and that are more than 24 hours old.</span></span>

```
DECLARE @id int
DECLARE adhoc_queries_cursor CURSOR 
FOR 
SELECT q.query_id
FROM sys.query_store_query_text AS qt
JOIN sys.query_store_query AS q 
    ON q.query_text_id = qt.query_text_id
JOIN sys.query_store_plan AS p 
    ON p.query_id = q.query_id
JOIN sys.query_store_runtime_stats AS rs 
    ON rs.plan_id = p.plan_id
GROUP BY q.query_id
HAVING SUM(rs.count_executions) < 2 
AND MAX(rs.last_execution_time) < DATEADD (hour, -24, GETUTCDATE())
ORDER BY q.query_id ;

OPEN adhoc_queries_cursor ;
FETCH NEXT FROM adhoc_queries_cursor INTO @id;
WHILE @@fetch_status = 0
    BEGIN 
        PRINT @id
        EXEC sp_query_store_remove_query @id
        FETCH NEXT FROM adhoc_queries_cursor INTO @id
    END 
CLOSE adhoc_queries_cursor ;
DEALLOCATE adhoc_queries_cursor;
```

 <span data-ttu-id="e1f27-209">Вы можете задать собственную процедуру с другой логикой для очистки данных, которые вам больше не требуются.</span><span class="sxs-lookup"><span data-stu-id="e1f27-209">You can define your own procedure with different logic for clearing up the data that is no longer important for you.</span></span>

 <span data-ttu-id="e1f27-210">В примере выше используется расширенная хранимая процедура `sp_query_store_remove_query` для удаления ненужных данных.</span><span class="sxs-lookup"><span data-stu-id="e1f27-210">The example above uses the `sp_query_store_remove_query` extended stored procedure for removing unnecessary data.</span></span> <span data-ttu-id="e1f27-211">Вы можете также использовать две другие процедуры.</span><span class="sxs-lookup"><span data-stu-id="e1f27-211">You can also use two other procedures.</span></span>

-   <span data-ttu-id="e1f27-212">`sp_query_store_reset_exec_stats`— Очистка статистики времени выполнения для данного плана.</span><span class="sxs-lookup"><span data-stu-id="e1f27-212">`sp_query_store_reset_exec_stats` - clear runtime statistics for a given plan.</span></span>

-   <span data-ttu-id="e1f27-213">`sp_query_store_remove_plan`— Удаляет один план.</span><span class="sxs-lookup"><span data-stu-id="e1f27-213">`sp_query_store_remove_plan` - removes a single plan.</span></span>



###  <a name="performance-auditing-and-troubleshooting"></a><a name="Peformance"></a> <span data-ttu-id="e1f27-214">Аудит производительности и устранение проблем</span><span class="sxs-lookup"><span data-stu-id="e1f27-214">Performance Auditing and Troubleshooting</span></span>
 <span data-ttu-id="e1f27-215">Так как в хранилище запросов ведется журнал метрик компиляции и времени выполнения при выполнении запросов, возникает множество разных вопросов в отношении рабочей нагрузки, на которые вы легко можете ответить.</span><span class="sxs-lookup"><span data-stu-id="e1f27-215">Because Query Store keeps history of compilation and runtime metrics throughout query executions there are many different questions you can easily answer with regards to your workload.</span></span>

 <span data-ttu-id="e1f27-216">**Последние *n* запросов, выполненных в базе данных.**</span><span class="sxs-lookup"><span data-stu-id="e1f27-216">**Last *n* queries executed on the database.**</span></span>

```
SELECT TOP 10 qt.query_sql_text, q.query_id, 
    qt.query_text_id, p.plan_id, rs.last_execution_time
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
ORDER BY rs.last_execution_time DESC;
```

 <span data-ttu-id="e1f27-217">**Количество выполнений для каждого запроса.**</span><span class="sxs-lookup"><span data-stu-id="e1f27-217">**Number of executions for each query.**</span></span>

```
SELECT q.query_id, qt.query_text_id, qt.query_sql_text, 
    SUM(rs.count_executions) AS total_execution_count
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
GROUP BY q.query_id, qt.query_text_id, qt.query_sql_text
ORDER BY total_execution_count DESC;
```

 <span data-ttu-id="e1f27-218">**Число запросов с наибольшим средним временем выполнения за последний час.**</span><span class="sxs-lookup"><span data-stu-id="e1f27-218">**The number of queries with the longest average execution time within last hour.**</span></span>

```
SELECT TOP 10 rs.avg_duration, qt.query_sql_text, q.query_id,
    qt.query_text_id, p.plan_id, GETUTCDATE() AS CurrentUTCTime, 
    rs.last_execution_time 
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
WHERE rs.last_execution_time > DATEADD(hour, -1, GETUTCDATE())
ORDER BY rs.avg_duration DESC;
```

 <span data-ttu-id="e1f27-219">**Число запросов с наибольшим средним количеством операций чтения с физических операций ввода-вывода за последние 24 часа с соответствующим средним числом строк и числом выполнений.**</span><span class="sxs-lookup"><span data-stu-id="e1f27-219">**The number of queries that had the biggest average physical IO reads in last 24 hours, with corresponding average row count and execution count.**</span></span>

```
SELECT TOP 10 rs.avg_physical_io_reads, qt.query_sql_text, 
    q.query_id, qt.query_text_id, p.plan_id, rs.runtime_stats_id, 
    rsi.start_time, rsi.end_time, rs.avg_rowcount, rs.count_executions
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi 
    ON rsi.runtime_stats_interval_id = rs.runtime_stats_interval_id
WHERE rsi.start_time >= DATEADD(hour, -24, GETUTCDATE()) 
ORDER BY rs.avg_physical_io_reads DESC;
```

 <span data-ttu-id="e1f27-220">**Запросы с несколькими планами.**</span><span class="sxs-lookup"><span data-stu-id="e1f27-220">**Queries with multiple plans.**</span></span> <span data-ttu-id="e1f27-221">Эти запросы особенно интересны, так как они являются кандидатами на снижение из-за изменения выбранного плана.</span><span class="sxs-lookup"><span data-stu-id="e1f27-221">These queries are especially interesting because they are candidates for regressions due to plan choice change.</span></span> <span data-ttu-id="e1f27-222">Следующий запрос определяет данные запросы со всеми планами.</span><span class="sxs-lookup"><span data-stu-id="e1f27-222">The following query identifies these queries along with all plans:</span></span>

```
WITH Query_MultPlans
AS
(
    SELECT COUNT(*) AS cnt, q.query_id 
    FROM sys.query_store_query_text AS qt
    JOIN sys.query_store_query AS q
        ON qt.query_text_id = q.query_text_id
    JOIN sys.query_store_plan AS p
        ON p.query_id = q.query_id
    GROUP BY q.query_id
    HAVING COUNT(distinct plan_id) > 1
)

SELECT q.query_id, object_name(object_id) AS ContainingObject, query_sql_text,
plan_id, p.query_plan AS plan_xml,
p.last_compile_start_time, p.last_execution_time
FROM Query_MultPlans AS qm
JOIN sys.query_store_query AS q
    ON qm.query_id = q.query_id
JOIN sys.query_store_plan AS p
    ON q.query_id = p.query_id
JOIN sys.query_store_query_text qt 
    ON qt.query_text_id = q.query_text_id
ORDER BY query_id, plan_id;
```

 <span data-ttu-id="e1f27-223">**Запросы, которые недавно проводили к производительности (сравнивая разные точки во времени).**</span><span class="sxs-lookup"><span data-stu-id="e1f27-223">**Queries that recently regressed in performance (comparing different point in time).**</span></span> <span data-ttu-id="e1f27-224">Следующий пример запроса возвращает все запросы, для которых время выполнения удвоилось за последние 48 часов из-за изменения выбранного плана.</span><span class="sxs-lookup"><span data-stu-id="e1f27-224">The following query example returns all queries for which execution time doubled in last 48 hours due to a plan choice change.</span></span> <span data-ttu-id="e1f27-225">Запрос сравнивает все интервалы статистики времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="e1f27-225">Query compares all runtime stat intervals side by side.</span></span>

```
SELECT 
    qt.query_sql_text, 
    q.query_id, 
    qt.query_text_id, 
    rs1.runtime_stats_id AS runtime_stats_id_1,
    rsi1.start_time AS interval_1, 
    p1.plan_id AS plan_1, 
    rs1.avg_duration AS avg_duration_1, 
    rs2.avg_duration AS avg_duration_2,
    p2.plan_id AS plan_2, 
    rsi2.start_time AS interval_2, 
    rs2.runtime_stats_id AS runtime_stats_id_2
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p1 
    ON q.query_id = p1.query_id 
JOIN sys.query_store_runtime_stats AS rs1 
    ON p1.plan_id = rs1.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi1 
    ON rsi1.runtime_stats_interval_id = rs1.runtime_stats_interval_id 
JOIN sys.query_store_plan AS p2 
    ON q.query_id = p2.query_id 
JOIN sys.query_store_runtime_stats AS rs2 
    ON p2.plan_id = rs2.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi2 
    ON rsi2.runtime_stats_interval_id = rs2.runtime_stats_interval_id
WHERE rsi1.start_time > DATEADD(hour, -48, GETUTCDATE()) 
    AND rsi2.start_time > rsi1.start_time 
    AND p1.plan_id <> p2.plan_id
    AND rs2.avg_duration > 2*rs1.avg_duration
ORDER BY q.query_id, rsi1.start_time, rsi2.start_time;
```

 <span data-ttu-id="e1f27-226">Если вы хотите просмотреть производительность всех регрессий (а не только тех, которые связаны с изменением выбранного плана), удалите условие `AND p1.plan_id <> p2.plan_id` из предыдущего запроса.</span><span class="sxs-lookup"><span data-stu-id="e1f27-226">If you want to see performance all regressions (not only those related to plan choice change) than just remove condition `AND p1.plan_id <> p2.plan_id` from the previous query.</span></span>

 <span data-ttu-id="e1f27-227">**Запросы, которые недавно проводили к производительности (сравнение последних и выполненных событий).**</span><span class="sxs-lookup"><span data-stu-id="e1f27-227">**Queries that recently regressed in performance (comparing recent vs. history execution).**</span></span> <span data-ttu-id="e1f27-228">Следующий запрос сравнивает периоды выполнения на основе выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-228">The next query compares query execution based periods of execution.</span></span> <span data-ttu-id="e1f27-229">В этом примере запрос сравнивает выполнение за последний период (1 час) с периодом журнала (последний день) и определяет те, которые были представлены в additional_duration_workload.</span><span class="sxs-lookup"><span data-stu-id="e1f27-229">In this particular example the query compares execution in recent period (1 hour) vs. history period (last day) and identifies those that introduced additional_duration_workload.</span></span> <span data-ttu-id="e1f27-230">Эти метрики подсчитываются путем умножения разницы между средним последним выполнением и средним выполнением по журналу на количество последних выполнений.</span><span class="sxs-lookup"><span data-stu-id="e1f27-230">This metrics is calculated as a difference between recent average execution and history average execution multiplied by the number of recent executions.</span></span> <span data-ttu-id="e1f27-231">Фактически они представляют количество последних выполнений с дополнительной длительностью по сравнению с журналом:</span><span class="sxs-lookup"><span data-stu-id="e1f27-231">It actually represents how much of additional duration recent executions introduced compared to history:</span></span>

```
--- "Recent" workload - last 1 hour
DECLARE @recent_start_time datetimeoffset;
DECLARE @recent_end_time datetimeoffset;
SET @recent_start_time = DATEADD(hour, -1, SYSUTCDATETIME());
SET @recent_end_time = SYSUTCDATETIME();

--- "History" workload
DECLARE @history_start_time datetimeoffset;
DECLARE @history_end_time datetimeoffset;
SET @history_start_time = DATEADD(hour, -24, SYSUTCDATETIME());
SET @history_end_time = SYSUTCDATETIME();

WITH
hist AS
(
    SELECT 
        p.query_id query_id, 
        CONVERT(float, SUM(rs.avg_duration*rs.count_executions)) total_duration, 
        SUM(rs.count_executions) count_executions,
        COUNT(distinct p.plan_id) num_plans 
     FROM sys.query_store_runtime_stats AS rs
        JOIN sys.query_store_plan p ON p.plan_id = rs.plan_id
    WHERE  (rs.first_execution_time >= @history_start_time AND rs.last_execution_time < @history_end_time)
        OR (rs.first_execution_time <= @history_start_time AND rs.last_execution_time > @history_start_time)
        OR (rs.first_execution_time <= @history_end_time AND rs.last_execution_time > @history_end_time)
    GROUP BY p.query_id
),
recent AS
(
    SELECT 
        p.query_id query_id, 
        CONVERT(float, SUM(rs.avg_duration*rs.count_executions)) total_duration, 
        SUM(rs.count_executions) count_executions,
        COUNT(distinct p.plan_id) num_plans 
    FROM sys.query_store_runtime_stats AS rs
        JOIN sys.query_store_plan p ON p.plan_id = rs.plan_id
    WHERE  (rs.first_execution_time >= @recent_start_time AND rs.last_execution_time < @recent_end_time)
        OR (rs.first_execution_time <= @recent_start_time AND rs.last_execution_time > @recent_start_time)
        OR (rs.first_execution_time <= @recent_end_time AND rs.last_execution_time > @recent_end_time)
    GROUP BY p.query_id
)
SELECT 
    results.query_id query_id,
    results.query_text query_text,
    results.additional_duration_workload additional_duration_workload,
    results.total_duration_recent total_duration_recent,
    results.total_duration_hist total_duration_hist,
    ISNULL(results.count_executions_recent, 0) count_executions_recent,
    ISNULL(results.count_executions_hist, 0) count_executions_hist 
FROM
(
    SELECT
        hist.query_id query_id,
        qt.query_sql_text query_text,
        ROUND(CONVERT(float, recent.total_duration/recent.count_executions-hist.total_duration/hist.count_executions)*(recent.count_executions), 2) AS additional_duration_workload,
        ROUND(recent.total_duration, 2) total_duration_recent, 
        ROUND(hist.total_duration, 2) total_duration_hist,
        recent.count_executions count_executions_recent,
        hist.count_executions count_executions_hist   
    FROM hist 
        JOIN recent 
            ON hist.query_id = recent.query_id 
        JOIN sys.query_store_query AS q 
            ON q.query_id = hist.query_id
        JOIN sys.query_store_query_text AS qt 
            ON q.query_text_id = qt.query_text_id    
) AS results
WHERE additional_duration_workload > 0
ORDER BY additional_duration_workload DESC
OPTION (MERGE JOIN);
```



###  <a name="maintaining-query-performance-stability"></a><a name="Stability"></a><span data-ttu-id="e1f27-232">Поддержание стабильной производительности запросов</span><span class="sxs-lookup"><span data-stu-id="e1f27-232">Maintaining Query Performance Stability</span></span>
 <span data-ttu-id="e1f27-233">Вы могли заметить, что для запросов, которые выполняются несколько раз, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] использовал разные планы, что привело к другому уровню нагрузки и длительности использования ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-233">For queries that are executed multiple times you may notice that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] used different plans which resulted in different resource utilization and duration.</span></span> <span data-ttu-id="e1f27-234">В хранилище запросов вы можете легко обнаружить снижение производительности и определить оптимальный план за интересующий вас период.</span><span class="sxs-lookup"><span data-stu-id="e1f27-234">With Query Store you can easily detect when the query performance regressed and determine the optimal plan within a period of interest.</span></span> <span data-ttu-id="e1f27-235">Затем вы можете принудительно применить оптимальный план для выполнения будущих запросов.</span><span class="sxs-lookup"><span data-stu-id="e1f27-235">Then you can force that optimal plan for future query execution.</span></span>

 <span data-ttu-id="e1f27-236">Вы можете также определить несоответствующую производительность запросов для запроса с параметрами (заданными автоматически или вручную).</span><span class="sxs-lookup"><span data-stu-id="e1f27-236">You can also identify inconsistent query performance for a query with parameters (either auto- parameterized or manually parameterized).</span></span> <span data-ttu-id="e1f27-237">Среди разных планов вы можете найти достаточно быстрый и оптимальный план для всех или большинства значений параметров и принудительно применить его, сохранив прогнозируемую производительность для более широкого набора сценариев пользователя.</span><span class="sxs-lookup"><span data-stu-id="e1f27-237">Among different plans you can identify plan which is fast and optimal enough for all or most of the parameter values and force that plan; keeping predictable performance for the wider set of user scenarios.</span></span>

 <span data-ttu-id="e1f27-238">**Планирование или принудительное выполнение запроса (применение политики принудительного выполнения).**</span><span class="sxs-lookup"><span data-stu-id="e1f27-238">**Force or a plan for a query (apply forcing policy).**</span></span> <span data-ttu-id="e1f27-239">При принудительном применении определенного плана каждый раз, когда запрос выполняется, он будет выполняться в принудительно выбранном плане.</span><span class="sxs-lookup"><span data-stu-id="e1f27-239">When a plan is forced for a certain query, every time a query comes to execution it will be executed with the plan that is forced.</span></span>

```
EXEC sp_query_store_force_plan @query_id = 48, @plan_id = 49;
```

 <span data-ttu-id="e1f27-240">При использовании `sp_query_store_force_plan` можно принудительно выполнять только планы, записанные хранилищем запросов в качестве плана для этого запроса.</span><span class="sxs-lookup"><span data-stu-id="e1f27-240">When using `sp_query_store_force_plan` you can only force plans that were recorded by Query Store as a plan for that query.</span></span> <span data-ttu-id="e1f27-241">Другими словами, единственные доступные планы — это те, которые уже использовались для выполнения Q1, когда хранилище запросов было активно.</span><span class="sxs-lookup"><span data-stu-id="e1f27-241">In other words, the only plans available for a query are those that were already used to execute Q1 while Query Store was active.</span></span>

 <span data-ttu-id="e1f27-242">**Удаление форсирования плана для запроса.**</span><span class="sxs-lookup"><span data-stu-id="e1f27-242">**Remove plan forcing for a query.**</span></span> <span data-ttu-id="e1f27-243">Чтобы снова использовать [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] оптимизатор запросов для вычисления оптимального плана запроса, используйте команду `sp_query_store_unforce_plan` , чтобы отменить принудительный выбор плана, выбранного для запроса.</span><span class="sxs-lookup"><span data-stu-id="e1f27-243">To rely again on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] query optimizer to calculate the optimal query plan, use `sp_query_store_unforce_plan` to unforce the plan that was selected for the query.</span></span>

```
EXEC sp_query_store_unforce_plan @query_id = 48, @plan_id = 49;
```



## <a name="see-also"></a><span data-ttu-id="e1f27-244">См. также:</span><span class="sxs-lookup"><span data-stu-id="e1f27-244">See Also</span></span>
 <span data-ttu-id="e1f27-245">Мониторинг [и настройка](../performance/monitor-and-tune-for-performance.md) [средств мониторинга производительности и управления производительностью](../performance/performance-monitoring-and-tuning-tools.md) [Открытие монитора активности &#40;SQL Server Management Studio](../performance-monitor/open-activity-monitor-sql-server-management-studio.md) [Монитор активности](../performance-monitor/activity-monitor.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="e1f27-245">[Monitor and Tune for Performance](../performance/monitor-and-tune-for-performance.md) [Performance Monitoring and Tuning Tools](../performance/performance-monitoring-and-tuning-tools.md) [Open Activity Monitor &#40;SQL Server Management Studio&#41;](../performance-monitor/open-activity-monitor-sql-server-management-studio.md) [Activity Monitor](../performance-monitor/activity-monitor.md)</span></span>


