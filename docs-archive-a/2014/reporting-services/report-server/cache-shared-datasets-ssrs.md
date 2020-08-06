---
title: Общие наборы данных в кэше (службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4acb1bbe-1c04-4979-b893-dc1b1c5039b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5b08149b075ae3fd267baf2dad0ca342457958c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665832"
---
# <a name="cache-shared-datasets-ssrs"></a><span data-ttu-id="83b1f-102">Общий набор данных в кэше (служба SSRS)</span><span class="sxs-lookup"><span data-stu-id="83b1f-102">Cache Shared Datasets (SSRS)</span></span>
  <span data-ttu-id="83b1f-103">Результаты запроса для общего набора данных могут быть скопированы в кэш, чтобы предоставить согласованные данные для нескольких отчетов и улучшить время ответа для запроса к набору данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-103">Query results for a shared dataset can be copied to a cache to provide consistent data for multiple reports and to improve response time for the dataset query.</span></span> <span data-ttu-id="83b1f-104">Как и отчеты, общие наборы данных можно настраивать как подлежащие кэшированию при первом использовании или согласно расписанию.</span><span class="sxs-lookup"><span data-stu-id="83b1f-104">Like reports, you can configure a shared dataset to be cached on first use or by specifying a schedule.</span></span>  
  
 <span data-ttu-id="83b1f-105">Общий набор данных может быть включен в несколько отчетов или задан как часть определений компонентов.</span><span class="sxs-lookup"><span data-stu-id="83b1f-105">A shared dataset can be included in multiple reports or as part of component definitions.</span></span> <span data-ttu-id="83b1f-106">Кэширование общего набора данных позволяет предоставить согласованный набор данных для всех использующих его отчетов, а также уменьшить количество запросов к внешнему источнику набору данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-106">By caching the shared dataset, you provide a consistent set of data for all reports that use it, and also reduce the number of times that the dataset query runs against the external data source.</span></span>  
  
 <span data-ttu-id="83b1f-107">В следующем списке приведены примеры, когда следует кэшировать общий набор данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-107">The following list provides examples of when to cache a shared dataset:</span></span>  
  
-   <span data-ttu-id="83b1f-108">Выполнение запроса требует значительного времени.</span><span class="sxs-lookup"><span data-stu-id="83b1f-108">The query takes a substantial amount of time to run.</span></span>  
  
-   <span data-ttu-id="83b1f-109">Запрос принимает параметры, но чаще всего количество сочетаний параметров невелико.</span><span class="sxs-lookup"><span data-stu-id="83b1f-109">The query takes parameters, but most of the time, the number of parameter combinations is small.</span></span> <span data-ttu-id="83b1f-110">Для каждого сочетания параметров создаются кэшированные результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="83b1f-110">Each combination creates cached query results.</span></span>  
  
-   <span data-ttu-id="83b1f-111">Запрос запускается в прогнозируемое время дня, недели или месяца.</span><span class="sxs-lookup"><span data-stu-id="83b1f-111">The query runs at predictable times of the day, week, or month.</span></span>  
  
-   <span data-ttu-id="83b1f-112">Запрос запускается в результате ссылки на общий набор данных в отчете, который доставляется по электронной почте, и велика вероятность того, что за короткий промежуток времени эту ссылку щелкнут многие пользователи.</span><span class="sxs-lookup"><span data-stu-id="83b1f-112">The query runs as the result of a shared dataset reference in a report that is delivered via e-mail, where a large number of people are likely to click the link in a short span of time.</span></span>  
  
-   <span data-ttu-id="83b1f-113">В следующем списке приведены примеры, когда не следует кэшировать общий набор данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-113">The following list provides examples of when not to cache a shared dataset:</span></span>  
  
-   <span data-ttu-id="83b1f-114">Результаты запроса должны всегда содержать самые последние данные.</span><span class="sxs-lookup"><span data-stu-id="83b1f-114">The query results must always include the most recent data.</span></span>  
  
-   <span data-ttu-id="83b1f-115">Запрос выполняется быстро.</span><span class="sxs-lookup"><span data-stu-id="83b1f-115">The query runs quickly.</span></span>  
  
-   <span data-ttu-id="83b1f-116">Запрос выполняется редко.</span><span class="sxs-lookup"><span data-stu-id="83b1f-116">The query runs infrequently.</span></span>  
  
-   <span data-ttu-id="83b1f-117">Запрос принимает параметры, количество сочетаний параметров велико, и ни одно сочетание не является более вероятным, чем другие.</span><span class="sxs-lookup"><span data-stu-id="83b1f-117">The query takes parameters, the number of parameter combinations is large, and no combination is more likely than another.</span></span>  
  
-   <span data-ttu-id="83b1f-118">Источник данных, на котором основан общий набор данных, имеет учетные данные, предоставляемые с помощью приглашения или встроенной безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="83b1f-118">The data source that the shared dataset is based on has Prompt or Windows Integrated credentials.</span></span>  
  
-   <span data-ttu-id="83b1f-119">Фильтр общего набора данных или запрос содержит выражение со ссылкой на пользователя глобальной коллекции.</span><span class="sxs-lookup"><span data-stu-id="83b1f-119">The shared dataset filter or the query contains an expression with a reference to the global collection User.</span></span>  
  
 <span data-ttu-id="83b1f-120">Если пользователь выбирает значения параметров отчета, которые отличаются от значений по умолчанию, указанных для кэшированного результирующего набора, то запрос к набору данных выполняется активно и для этого запроса не используются кэшированные результаты.</span><span class="sxs-lookup"><span data-stu-id="83b1f-120">If a user chooses report parameter values that differ from the default values that are specified for the cached result set, the dataset query runs actively and the cached results are not used for that query.</span></span>  
  
## <a name="caching-shared-datasets"></a><span data-ttu-id="83b1f-121">Кэширование общих наборов данных</span><span class="sxs-lookup"><span data-stu-id="83b1f-121">Caching Shared Datasets</span></span>  
 <span data-ttu-id="83b1f-122">Чтобы включить кэширование для общего набора данных, необходимо выбрать параметр кэширования для этого общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-122">To enable caching for a shared dataset, you must select the cache option on the shared dataset.</span></span> <span data-ttu-id="83b1f-123">После включения кэширования результаты запроса для общего набора данных копируются в кэш при первом использовании.</span><span class="sxs-lookup"><span data-stu-id="83b1f-123">After caching is enabled, the query results for a shared dataset are copied to the cache on first use.</span></span> <span data-ttu-id="83b1f-124">Если общий набор данных имеет параметры, то каждое сочетание параметров создает новую запись в кэше.</span><span class="sxs-lookup"><span data-stu-id="83b1f-124">If the shared dataset has parameters, each combination of parameters creates a new entry in the cache.</span></span>  
  
 <span data-ttu-id="83b1f-125">До тех пор пока результаты запроса для конкретного сочетания параметров находятся в кэше, каждый отчет, запускаемый на обработку и включающий ссылку на общий набор данных с теми же значениями параметров, будет использовать кэшированные данные.</span><span class="sxs-lookup"><span data-stu-id="83b1f-125">While the query results for a specific parameter combination are in the cache, each report that is launched for processing and that includes a reference to the shared dataset with those parameter values will use the cached data.</span></span>  
  
 <span data-ttu-id="83b1f-126">Можно указать, как долго данные должны храниться в кэше до истечения срока их действия.</span><span class="sxs-lookup"><span data-stu-id="83b1f-126">You can specify how long to keep data in the cache before it expires.</span></span> <span data-ttu-id="83b1f-127">Дополнительные сведения см. в разделе [Страница "Кэширование", "Общие наборы данных" (диспетчер отчетов)](../caching-page-shared-datasets-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="83b1f-127">For more information, see [Caching Page, Shared Datasets &#40;Report Manager&#41;](../caching-page-shared-datasets-report-manager.md).</span></span>  
  
## <a name="preloading-the-cache"></a><span data-ttu-id="83b1f-128">Предварительная загрузка кэша</span><span class="sxs-lookup"><span data-stu-id="83b1f-128">Preloading the Cache</span></span>  
 <span data-ttu-id="83b1f-129">Можно произвести предварительную загрузку кэша путем создания плана обновления кэша.</span><span class="sxs-lookup"><span data-stu-id="83b1f-129">You can preload the cache by creating a cache refresh plan.</span></span> <span data-ttu-id="83b1f-130">План обновления позволяет указать, как часто следует обновлять кэш с помощью расписания элемента или общего расписания.</span><span class="sxs-lookup"><span data-stu-id="83b1f-130">With a refresh plan, you can specify how often to refresh the cache by using an item-specific schedule or a shared schedule.</span></span> <span data-ttu-id="83b1f-131">Чтобы избежать появления нескольких записей кэша для одного и того же элемента, заданное расписание должно предусматривать достаточное количество времени для обработки запроса по отношению к внешнему источнику данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-131">To avoid multiple cache entries for the same item, the schedule that you specify should allow enough time for query processing on the external data source.</span></span> <span data-ttu-id="83b1f-132">Например, если для выполнения запроса требуется 20 минут, то расписание обновления должно предусматривать интервал больше 20 минут.</span><span class="sxs-lookup"><span data-stu-id="83b1f-132">For example, if the query takes 20 minutes to run, the refresh schedule should be greater than 20 minutes.</span></span> <span data-ttu-id="83b1f-133">Дополнительные сведения см. в разделе [Schedules](../subscriptions/schedules.md).</span><span class="sxs-lookup"><span data-stu-id="83b1f-133">For more information, see [Schedules](../subscriptions/schedules.md).</span></span>  
  
 <span data-ttu-id="83b1f-134">При создании плана обновления кэша для общего набора данных применяются следующие условия.</span><span class="sxs-lookup"><span data-stu-id="83b1f-134">To create a cache refresh plan for a shared dataset, the following conditions apply.</span></span>  
  
-   <span data-ttu-id="83b1f-135">Для общего набора данных должно быть включено кэширование.</span><span class="sxs-lookup"><span data-stu-id="83b1f-135">The shared dataset must be enabled for caching.</span></span>  
  
-   <span data-ttu-id="83b1f-136">В общем источнике данных, от которого зависит общий набор данных, не могут использоваться учетные данные, предоставляемые с помощью приглашения или встроенной безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="83b1f-136">The shared data source that the shared dataset depends on cannot use Prompt or Windows Integrated credentials.</span></span>  
  
-   <span data-ttu-id="83b1f-137">Если общий набор данных имеет параметры, следует указать статические значения по умолчанию для каждого параметра, который не отмечен как предназначенный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="83b1f-137">If the shared dataset has parameters, you must specify static default values for each parameter that is not marked read-only.</span></span> <span data-ttu-id="83b1f-138">Для параметров, допускающих только чтение, всегда используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83b1f-138">Read-only parameters will always use the default value.</span></span> <span data-ttu-id="83b1f-139">Чтобы кэшировать общий набор данных для нескольких сочетаний параметров, необходимо создать отдельный план обновления кэша для каждого сочетания значений.</span><span class="sxs-lookup"><span data-stu-id="83b1f-139">To cache a shared dataset for multiple combinations of parameters, you must create a separate cache refresh plan for each combination of values.</span></span> <span data-ttu-id="83b1f-140">Параметры не могут содержать ссылки на другие наборы данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-140">Parameters cannot contain references to other datasets.</span></span>  
  
-   <span data-ttu-id="83b1f-141">Каждый план обновления кэша связан только с одним общим набором данных или отчетом.</span><span class="sxs-lookup"><span data-stu-id="83b1f-141">Each cache refresh plan is associated with only one shared dataset or report.</span></span>  
  
-   <span data-ttu-id="83b1f-142">Необходимо иметь разрешения ReadPolicy и UpdatePolicy на общий набор данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-142">You must have ReadPolicy and UpdatePolicy permissions on the shared dataset.</span></span>  
  
 <span data-ttu-id="83b1f-143">Планы обновления кэша применяются и к общим наборам данных, и к отчетам.</span><span class="sxs-lookup"><span data-stu-id="83b1f-143">Cache refresh plans apply to both shared datasets and reports.</span></span> <span data-ttu-id="83b1f-144">Дополнительные сведения см. в разделе [Параметры обновления кэша (диспетчер отчетов)](../cache-refresh-options-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="83b1f-144">For more information, see [Cache Refresh Options &#40;Report Manager&#41;](../cache-refresh-options-report-manager.md).</span></span>  
  
## <a name="conditions-that-cause-cache-expiration"></a><span data-ttu-id="83b1f-145">Условия, приводящие к истечению срока кэша</span><span class="sxs-lookup"><span data-stu-id="83b1f-145">Conditions that Cause Cache Expiration</span></span>  
 <span data-ttu-id="83b1f-146">Кэш общего набора данных может стать недействительным при следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="83b1f-146">The following conditions can cause a shared dataset cache to become not valid.</span></span>  
  
-   <span data-ttu-id="83b1f-147">Истек срок действия одного из условий расписания.</span><span class="sxs-lookup"><span data-stu-id="83b1f-147">A schedule condition expires.</span></span> <span data-ttu-id="83b1f-148">Происходит очистка кэша по времени ожидания, или истекает срок хранения.</span><span class="sxs-lookup"><span data-stu-id="83b1f-148">The cache times out or the expiration time occurs.</span></span>  
  
-   <span data-ttu-id="83b1f-149">Удаляется общее расписание.</span><span class="sxs-lookup"><span data-stu-id="83b1f-149">A shared schedule is deleted.</span></span>  
  
-   <span data-ttu-id="83b1f-150">В общее расписание вносятся изменения.</span><span class="sxs-lookup"><span data-stu-id="83b1f-150">Changes to a shared schedule.</span></span> <span data-ttu-id="83b1f-151">Общие расписания могут быть приостановлены, что также влияет на истечение срока действия кэша.</span><span class="sxs-lookup"><span data-stu-id="83b1f-151">Shared schedules can be paused, which also affects when a cache expires.</span></span>  
  
-   <span data-ttu-id="83b1f-152">Изменяется определение запроса для общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-152">The query definition for the shared dataset changes.</span></span>  
  
-   <span data-ttu-id="83b1f-153">Изменяются учетные данные для общего источника данных, от которого зависит общий набор данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-153">The credentials for the shared data source that the shared dataset depends on change.</span></span>  
  
-   <span data-ttu-id="83b1f-154">Изменяются параметры кэша для общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-154">The cache options for the shared dataset change.</span></span>  
  
-   <span data-ttu-id="83b1f-155">Изменяются значения по умолчанию для допускающих только чтение параметров общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-155">The default values for read-only parameters for the shared dataset change.</span></span>  
  
-   <span data-ttu-id="83b1f-156">Изменяются фильтры, которые являются частью определения общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-156">The filters that are part of the shared dataset definition change.</span></span>  
  
-   <span data-ttu-id="83b1f-157">Общий набор данных удаляется с сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="83b1f-157">The shared dataset is deleted from the report server.</span></span> <span data-ttu-id="83b1f-158">При удалении общего набора данных удаляются также связанные с ним кэшированные копии и планы обновления кэша.</span><span class="sxs-lookup"><span data-stu-id="83b1f-158">When a shared dataset is deleted, associated cached copies and cache refresh plans are also deleted.</span></span>  
  
 <span data-ttu-id="83b1f-159">Внесение изменений в планы обновления кэша для общих наборов данных не затрагивает отчеты, которые уже обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="83b1f-159">Updates to cache refresh plans for shared datasets do not affect reports that are already being processed.</span></span> <span data-ttu-id="83b1f-160">Изменение плана обновления кэша затрагивает только будущие запуски отчетов, которые ссылаются на рассматриваемый общий набор данных.</span><span class="sxs-lookup"><span data-stu-id="83b1f-160">Updating a cache refresh plan affects only future launches of reports that reference the shared dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b1f-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="83b1f-161">See Also</span></span>  
 [<span data-ttu-id="83b1f-162">Управление общими наборами данных</span><span class="sxs-lookup"><span data-stu-id="83b1f-162">Manage Shared Datasets</span></span>](../report-data/manage-shared-datasets.md)  
  
  
