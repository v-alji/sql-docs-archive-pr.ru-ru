---
title: Запросы содержимого (интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c4f4a5a8-a230-4222-bece-9d563501f65f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44b162c34f5f505462a713205d8434484473afa4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669182"
---
# <a name="content-queries-data-mining"></a><span data-ttu-id="52c7f-102">Запросы содержимого (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="52c7f-102">Content Queries (Data Mining)</span></span>
  <span data-ttu-id="52c7f-103">Запрос содержимого позволяет извлечь сведения о внутренней статистике и структуре модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="52c7f-103">A content query is a way of extracting information about the internal statistics and structure of the mining model.</span></span> <span data-ttu-id="52c7f-104">Иногда запрос содержимого может предоставить информацию, которую не удается получить с помощью средства просмотра.</span><span class="sxs-lookup"><span data-stu-id="52c7f-104">Sometimes a content query can provide details that are not readily available in the viewer.</span></span> <span data-ttu-id="52c7f-105">Результаты запроса содержимого можно также использовать для извлечения информации программным образом с целью ее последующего использования.</span><span class="sxs-lookup"><span data-stu-id="52c7f-105">You can also use the results of a content query to extract information programmatically for other uses.</span></span>  
  
 <span data-ttu-id="52c7f-106">В данном разделе предоставлены общие сведения о том, какого рода сведения могут быть получены в ответ на запрос к содержимому, а также об общем синтаксисе расширений интеллектуального анализа данных для запросов к содержимому.</span><span class="sxs-lookup"><span data-stu-id="52c7f-106">This section provides general information about the types of information that you can retrieve by using a content query, and the general DMX syntax for content queries.</span></span>  
  
 [<span data-ttu-id="52c7f-107">Базовые запросы к содержимому</span><span class="sxs-lookup"><span data-stu-id="52c7f-107">Basic Content Queries</span></span>](#bkmk_ContentQuery)  
  
-   [<span data-ttu-id="52c7f-108">Запросы к структуре и данным вариантов</span><span class="sxs-lookup"><span data-stu-id="52c7f-108">Queries on Structure and Case Data</span></span>](#bkmk_Structure)  
  
-   [<span data-ttu-id="52c7f-109">Запросы к шаблонам модели</span><span class="sxs-lookup"><span data-stu-id="52c7f-109">Queries on Model Patterns</span></span>](#bkmk_Patterns)  
  
 [<span data-ttu-id="52c7f-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="52c7f-110">Examples</span></span>](#bkmk_Examples)  
  
-   [<span data-ttu-id="52c7f-111">Запросы содержимого для моделей взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="52c7f-111">Content Query on an Association Model</span></span>](#bkmk_Assoc)  
  
-   [<span data-ttu-id="52c7f-112">Запрос содержимого из модели дерева принятия решений</span><span class="sxs-lookup"><span data-stu-id="52c7f-112">Content Query on a Decision Trees Model</span></span>](#bkmk_DecTree)  
  
 [<span data-ttu-id="52c7f-113">Работа с результатами запроса</span><span class="sxs-lookup"><span data-stu-id="52c7f-113">Working with the Query Results</span></span>](#bkmk_Results)  
  
##  <a name="basic-content-queries"></a><a name="bkmk_ContentQuery"></a><span data-ttu-id="52c7f-114">Базовые запросы к содержимому</span><span class="sxs-lookup"><span data-stu-id="52c7f-114">Basic Content Queries</span></span>  
 <span data-ttu-id="52c7f-115">Можно создавать запросы к содержимому с помощью построителя прогнозирующих запросов, использовать шаблоны запросов к содержимому расширения интеллектуального анализа данных, предусмотренные в среде SQL Server Management Studio, или писать запросы непосредственно с помощью расширения интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="52c7f-115">You can create content queries by using the Prediction Query Builder, use the DMX content query templates that are provided in SQL Server Management Studio, or write queries directly in DMX.</span></span> <span data-ttu-id="52c7f-116">В отличие от прогнозирующих запросов, необходимость применять операции соединения к внешним данным отсутствует, поэтому написание запросов к содержимому упрощается.</span><span class="sxs-lookup"><span data-stu-id="52c7f-116">Unlike prediction queries you do not need to join external data, so content queries are easy to write.</span></span>  
  
 <span data-ttu-id="52c7f-117">В этом разделе приводится общее описание типов запросов содержимого, которые можно создавать.</span><span class="sxs-lookup"><span data-stu-id="52c7f-117">This section provides an overview of the types of content queries you can create.</span></span>  
  
-   <span data-ttu-id="52c7f-118">Запросы к структуре интеллектуального анализа данных или данным варианта позволяют просматривать подробные данные, использовавшиеся для обучения.</span><span class="sxs-lookup"><span data-stu-id="52c7f-118">Queries on the mining structure or case data let you view the detailed data that was used for training.</span></span>  
  
-   <span data-ttu-id="52c7f-119">Запросы к модели могут возвращать шаблоны, списки атрибутов, формулы и т. д.</span><span class="sxs-lookup"><span data-stu-id="52c7f-119">Queries on the model can return patterns, lists of attributes, formulas, and so forth.</span></span>  
  
###  <a name="queries-on-structure-and-case-data"></a><a name="bkmk_Structure"></a> <span data-ttu-id="52c7f-120">Запросы к структуре и данным варианта</span><span class="sxs-lookup"><span data-stu-id="52c7f-120">Queries on Structure and Case Data</span></span>  
 <span data-ttu-id="52c7f-121">Расширения интеллектуального анализа данных поддерживают запросы к кэшируемым данным, которые используются для создания структур и моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="52c7f-121">DMX supports queries on the cached data that is used to build mining structures and models.</span></span> <span data-ttu-id="52c7f-122">По умолчанию этот кэш создается при определении структуры интеллектуального анализа данных и заполняется при обработке структуры или модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-122">By default, this cache is created when you define the mining structure, and is populated when you process the structure or model.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="52c7f-123">Этот кэш нельзя очистить или удалить, если потребуется разделить данные на обучающие и проверочные наборы.</span><span class="sxs-lookup"><span data-stu-id="52c7f-123">This cache cannot be cleared or deleted if you need to separate data into training and testing sets.</span></span> <span data-ttu-id="52c7f-124">После очистки кэша становится невозможным выполнение запроса к данным варианта.</span><span class="sxs-lookup"><span data-stu-id="52c7f-124">If the cache is cleared, you cannot query the case data.</span></span>  
  
 <span data-ttu-id="52c7f-125">В следующих примерах показаны стандартные шаблоны для создания запросов к данным варианта или запросов к данным из структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="52c7f-125">The following examples show the common patterns for creating queries on the case data, or queries on the data in the mining structure:</span></span>  
  
 <span data-ttu-id="52c7f-126">**Получение всех вариантов для модели**</span><span class="sxs-lookup"><span data-stu-id="52c7f-126">**Get all the cases for a model**</span></span>  
 `SELECT FROM <model>.CASES`  
  
 <span data-ttu-id="52c7f-127">Эта инструкция служит для получения указанных столбцов из данных варианта, применяемых для построения модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-127">Use this statement to retrieve specified columns from the case data used to build a model.</span></span> <span data-ttu-id="52c7f-128">Чтобы его выполнить, необходимо иметь разрешения детализации для этой модели, чтобы запустить запрос.</span><span class="sxs-lookup"><span data-stu-id="52c7f-128">You must have drillthrough permissions on the model to run this query.</span></span>  
  
 <span data-ttu-id="52c7f-129">**Просмотр всех данных, включенных в структуру**</span><span class="sxs-lookup"><span data-stu-id="52c7f-129">**View all the data that is included in the structure**</span></span>  
 `SELECT FROM <structure>.CASES`  
  
 <span data-ttu-id="52c7f-130">Эта инструкция служит для просмотра всех данных, которые включены в структуру, в том числе столбцов, не включенных в конкретную модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="52c7f-130">Use this statement to view all the data that is included in the structure, including columns that are not included in a particular mining model.</span></span> <span data-ttu-id="52c7f-131">Необходимо иметь разрешения детализации для модели, а также для структуры, чтобы извлекать данные из структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="52c7f-131">You must have drillthrough permissions on the model, as well as on the structure, to retrieve data from the mining structure.</span></span>  
  
 <span data-ttu-id="52c7f-132">**Получение диапазона значений**</span><span class="sxs-lookup"><span data-stu-id="52c7f-132">**Get range of values**</span></span>  
 `SELECT DISTINCT RangeMin(<column>), RangeMax(<column>) FROM <model>`  
  
 <span data-ttu-id="52c7f-133">Эта инструкция предназначена для поиска минимального, максимального и среднего значений для непрерывного столбца или для контейнеров столбца DISCRETIZED.</span><span class="sxs-lookup"><span data-stu-id="52c7f-133">Use this statement to find the minimum value, maximum value, and mean of a continuous column, or of the buckets of a DISCRETIZED column.</span></span>  
  
 <span data-ttu-id="52c7f-134">**Получение различимых значений**</span><span class="sxs-lookup"><span data-stu-id="52c7f-134">**Get distinct values**</span></span>  
 `SELECT DISTINCT <column>FROM <model>`  
  
 <span data-ttu-id="52c7f-135">Эта инструкция служит для получения всех значений столбца DISCRETE.</span><span class="sxs-lookup"><span data-stu-id="52c7f-135">Use this statement to retrieve all the values of a DISCRETE column.</span></span>  <span data-ttu-id="52c7f-136">Не используйте эту инструкцию для столбцов DISCRETIZED. Вместо этого воспользуйтесь функциями `RangeMin` и `RangeMax`.</span><span class="sxs-lookup"><span data-stu-id="52c7f-136">Do not use this statement for DISCRETIZED columns; use the `RangeMin` and `RangeMax` functions instead.</span></span>  
  
 <span data-ttu-id="52c7f-137">**Поиск вариантов, которые использовались для обучения модели или структуры**</span><span class="sxs-lookup"><span data-stu-id="52c7f-137">**Find the cases that were used to train a model or structure**</span></span>  
 `SELECT  FROM <mining structure.CASES WHERE IsTrainingCase()`  
  
 <span data-ttu-id="52c7f-138">Эта инструкция предназначена для получения полного набора данных, которые использовались при обучении модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-138">Use this statement to get the complete set of data that was used in a training a model.</span></span>  
  
 <span data-ttu-id="52c7f-139">**Поиск вариантов, которые использовались для проверки модели или структуры**</span><span class="sxs-lookup"><span data-stu-id="52c7f-139">**Find the cases that are used for testing a model or structure**</span></span>  
 `SELECT  FROM <mining structure.CASES WHERE IsTestingCase()`  
  
 <span data-ttu-id="52c7f-140">Эта инструкция предназначена для получения данных, которые зарезервированы для проверки моделей интеллектуального анализа данных, связанных с конкретной структурой.</span><span class="sxs-lookup"><span data-stu-id="52c7f-140">Use this statement to get the data that has been set aside for testing mining models related to a specific structure.</span></span>  
  
 <span data-ttu-id="52c7f-141">**Детализация с переходом от конкретного шаблона модели к основополагающим данным варианта**</span><span class="sxs-lookup"><span data-stu-id="52c7f-141">**Drillthrough from a specific model pattern to underlying case data**</span></span>  
 `SELECT FROM <model>.CASESWHERE IsTrainingCase() AND IsInNode(<node>)`  
  
 <span data-ttu-id="52c7f-142">Эта инструкция предназначена для получения детализированных данных варианта из обученной модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-142">Use this statement to retrieve detailed case data from a trained model.</span></span> <span data-ttu-id="52c7f-143">Необходимо указать конкретный узел, например нужно знать идентификатор узла кластера, конкретную ветвь дерева принятия решений и т. д. Более того, для выполнения этого запроса необходимо иметь разрешения на детализацию для этой модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-143">You must specify a specific node: for example, you must know the node ID of the cluster, the specific branch of the decision tree, etc. Moreover, you must have drillthrough permissions on the model to run this query.</span></span>  
  
###  <a name="queries-on-model-patterns-statistics-and-attributes"></a><a name="bkmk_Patterns"></a><span data-ttu-id="52c7f-144">Запросы к шаблонам, статистике и атрибутам моделей</span><span class="sxs-lookup"><span data-stu-id="52c7f-144">Queries on Model Patterns, Statistics, and Attributes</span></span>  
 <span data-ttu-id="52c7f-145">Содержимое модели интеллектуального анализа данных является полезным для многих целей.</span><span class="sxs-lookup"><span data-stu-id="52c7f-145">The content of a data mining model is useful for many purposes.</span></span> <span data-ttu-id="52c7f-146">С помощью запроса содержимого модели можно выполнять следующие действия.</span><span class="sxs-lookup"><span data-stu-id="52c7f-146">With a model content query, you can:</span></span>  
  
-   <span data-ttu-id="52c7f-147">Извлечение формул или значений вероятностей для выполнения собственных вычислений.</span><span class="sxs-lookup"><span data-stu-id="52c7f-147">Extract formulas or probabilities for making your own calculations.</span></span>  
  
-   <span data-ttu-id="52c7f-148">Для модели взаимосвязей — получать правила, которые используются для создания прогноза.</span><span class="sxs-lookup"><span data-stu-id="52c7f-148">For an association model, retrieve the rules that are used to generate a prediction.</span></span>  
  
-   <span data-ttu-id="52c7f-149">Получение описаний конкретных правил для использования этих правил в пользовательских приложениях.</span><span class="sxs-lookup"><span data-stu-id="52c7f-149">Retrieve the descriptions of specific rules so that you can use the rules in a custom application.</span></span>  
  
-   <span data-ttu-id="52c7f-150">Просматривать скользящие средние, обнаруженные моделью временного ряда.</span><span class="sxs-lookup"><span data-stu-id="52c7f-150">View the moving averages detected by a time series model.</span></span>  
  
-   <span data-ttu-id="52c7f-151">Получать формулу регрессии для некоторых сегментов линии тренда.</span><span class="sxs-lookup"><span data-stu-id="52c7f-151">Obtain the regression formula for some segment of the trend line.</span></span>  
  
-   <span data-ttu-id="52c7f-152">Получение искомых сведений о заказчиках, которые определены как относящиеся к конкретному кластеру.</span><span class="sxs-lookup"><span data-stu-id="52c7f-152">Retrieve actionable information about customers identified as being part of a specific cluster.</span></span>  
  
 <span data-ttu-id="52c7f-153">В следующих примерах показаны несколько стандартных шаблонов для создания запросов к содержимому модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-153">The following examples show some of the common patterns for creating queries on the model content:</span></span>  
  
 <span data-ttu-id="52c7f-154">**Получение шаблонов из модели**</span><span class="sxs-lookup"><span data-stu-id="52c7f-154">**Get patterns from the model**</span></span>  
 `SELECT FROM <model>.CONTENT`  
  
 <span data-ttu-id="52c7f-155">Эта инструкция предназначена для получения подробных сведений о конкретных узлах в модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-155">Use this statement to retrieve detailed information about specific nodes in the model.</span></span> <span data-ttu-id="52c7f-156">В зависимости от типа алгоритма, узел может содержать правила и формулы, статистические данные несущего множества и дисперсии и т. д.</span><span class="sxs-lookup"><span data-stu-id="52c7f-156">Depending on the algorithm type, the node can contain rules and formulas, support and variance statistics, and so forth.</span></span>  
  
 <span data-ttu-id="52c7f-157">**Получение атрибутов, используемых в обученной модели**</span><span class="sxs-lookup"><span data-stu-id="52c7f-157">**Retrieve attributes used in a trained model**</span></span>  
 `CALL System.GetModelAttributes(<model>)`  
  
 <span data-ttu-id="52c7f-158">Эта хранимая процедура предназначена для получения списка атрибутов, которые использовались в модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-158">Use this stored procedure to retrieve the list of attributes that were used by a model.</span></span> <span data-ttu-id="52c7f-159">Эти сведения могут служить для определения атрибутов, например тех, которые были устранены в результате выбора компонентов.</span><span class="sxs-lookup"><span data-stu-id="52c7f-159">This information is useful for determining attributes that were eliminated as a result of feature selection, for example.</span></span>  
  
 <span data-ttu-id="52c7f-160">**Получение содержимого, хранящегося в измерении интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="52c7f-160">**Retrieve content stored in a data mining dimension**</span></span>  
 `SELECT FROM <model>.DIMENSIONCONTENT`  
  
 <span data-ttu-id="52c7f-161">Эта инструкция предназначена для получения данных из измерения интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="52c7f-161">Use this statement to retrieve the data from a data mining dimension.</span></span>  
  
 <span data-ttu-id="52c7f-162">Этот тип запроса служит в основном для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="52c7f-162">This query type is principally for internal use.</span></span> <span data-ttu-id="52c7f-163">Но не все алгоритмы поддерживают эти функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="52c7f-163">However, not all algorithms support this functionality.</span></span> <span data-ttu-id="52c7f-164">Поддержка обозначается флажком в наборе строк схемы MINING_SERVICES.</span><span class="sxs-lookup"><span data-stu-id="52c7f-164">Support is indicated by a flag in the MINING_SERVICES schema rowset.</span></span>  
  
 <span data-ttu-id="52c7f-165">При разработке собственного сменного алгоритма эту инструкцию можно использовать в целях проверки содержимого конкретной модели для тестирования.</span><span class="sxs-lookup"><span data-stu-id="52c7f-165">If you develop your own plug-in algorithm, you might use this statement to verify the content of your model for testing.</span></span>  
  
 <span data-ttu-id="52c7f-166">**Получение представления PMML модели**</span><span class="sxs-lookup"><span data-stu-id="52c7f-166">**Get the PMML representation of a model**</span></span>  
 `SELECT * FROM <model>.PMML`  
  
 <span data-ttu-id="52c7f-167">Возвращает XML-документ, представляющий модель в формате PMML.</span><span class="sxs-lookup"><span data-stu-id="52c7f-167">Gets an XML document that represents the model in PMML format.</span></span> <span data-ttu-id="52c7f-168">Поддерживаются не все типы моделей.</span><span class="sxs-lookup"><span data-stu-id="52c7f-168">Not all model types are supported.</span></span>  
  
##  <a name="examples"></a><a name="bkmk_Examples"></a> <span data-ttu-id="52c7f-169">Примеры</span><span class="sxs-lookup"><span data-stu-id="52c7f-169">Examples</span></span>  
 <span data-ttu-id="52c7f-170">Несмотря на то что определенная часть содержимого любой модели остается стандартной при переходе от одного алгоритма к другому, содержимое некоторых частей значительно изменяется в зависимости от алгоритма, который использовался для построения модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-170">Although some model content is standard across algorithms, some parts of the content vary greatly depending on the algorithm that you used to build the model.</span></span> <span data-ttu-id="52c7f-171">Поэтому при создании запроса к содержимому следует учитывать, какого рода сведения о модели наиболее полезны применительно к данной конкретной модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-171">Therefore, when you create a content query, you must understand what information in the model is most useful to your specific model.</span></span>  
  
 <span data-ttu-id="52c7f-172">В этом разделе приведено несколько примеров, иллюстрирующих влияние выбранного алгоритма на то, какие сведения сохраняются в модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-172">A few examples are provided in this section to illustrate how the choice of algorithm affects the kind of information that is stored in the model.</span></span> <span data-ttu-id="52c7f-173">Дополнительные сведения о содержимом модели интеллектуального анализа данных и содержимом, характерном для каждого типа модели, см. в разделе [Содержимое моделей интеллектуального анализа (службы Analysis Services — интеллектуальный анализ данных)](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="52c7f-173">For more information about mining model content, and the content that is specific to each model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
###  <a name="example-1-content-query-on-an-association-model"></a><a name="bkmk_Assoc"></a> <span data-ttu-id="52c7f-174">Пример 1. Запрос содержимого для моделей взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="52c7f-174">Example 1: Content Query on an Association Model</span></span>  
 <span data-ttu-id="52c7f-175">Инструкция `SELECT FROM <model>.CONTENT`возвращает различные сведения в зависимости от типа модели, к которой выполняется запрос.</span><span class="sxs-lookup"><span data-stu-id="52c7f-175">The statement, `SELECT FROM <model>.CONTENT`, returns different kinds of information, depending on the type of model you are querying.</span></span> <span data-ttu-id="52c7f-176">Для модели взаимосвязей ключевыми являются сведения о *типе узла*.</span><span class="sxs-lookup"><span data-stu-id="52c7f-176">For an association model, a key piece of information is the *node type*.</span></span> <span data-ttu-id="52c7f-177">Узлы представляют собой своего рода контейнеры для сведений, составляющих содержимое модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-177">Nodes are like containers for information in the model content.</span></span> <span data-ttu-id="52c7f-178">В модели взаимосвязей узлы, представляющие правила, имеют параметр NODE_TYPE, равный 8, а узлы, представляющие наборы элементов, — равный 7.</span><span class="sxs-lookup"><span data-stu-id="52c7f-178">In an association model, nodes that represent rules have a NODE_TYPE value of 8, whereas nodes that represent itemsets have a NODE_TYPE value of 7.</span></span>  
  
 <span data-ttu-id="52c7f-179">Таким образом, следующий запрос возвращает первые 10 наборов элементов, упорядоченных по размеру несущего множества (сортировка по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="52c7f-179">Thus, the following query returns the top 10 itemsets, ranked by support (the default ordering).</span></span>  
  
```  
SELECT TOP 10 NODE_DESCRIPTION, NODE_PROBABILITY, SUPPORT  
FROM <model>.CONTENT WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="52c7f-180">Следующий запрос опирается на эти сведения.</span><span class="sxs-lookup"><span data-stu-id="52c7f-180">The following query builds on this information.</span></span> <span data-ttu-id="52c7f-181">Запрос возвращает три столбца: идентификатор узла, полное правило и продукт в правой части набора элементов, то есть продукт, который прогнозируется для связи с другими продуктами в составе набора элементов служб.</span><span class="sxs-lookup"><span data-stu-id="52c7f-181">The query returns three columns: the ID of the node, the complete rule, and the product on the right-hand side of the itemset-that is, the product that is predicted to be associated with some other products as part of an itemset.</span></span>  
  
```  
SELECT FLATTENED NODE_UNIQUE_NAME, NODE_DESCRIPTION,  
     (SELECT RIGHT(ATTRIBUTE_NAME, (LEN(ATTRIBUTE_NAME)-LEN('Association model name')))   
FROM NODE_DISTRIBUTION  
WHERE LEN(ATTRIBUTE_NAME)>2  
)   
AS RightSideProduct  
FROM [<Association model name>].CONTENT  
WHERE NODE_TYPE = 8   
ORDER BY NODE_SUPPORT DESC  
```  
  
 <span data-ttu-id="52c7f-182">Ключевое слово FLATTENED указывает, что вложенный набор строк следует перевести в формат плоской таблицы.</span><span class="sxs-lookup"><span data-stu-id="52c7f-182">The FLATTENED keyword indicates that the nested rowset should be converted into a flattened table.</span></span> <span data-ttu-id="52c7f-183">Атрибут, представляющий произведение в правой стороне правила, содержится в таблице NODE_DISTRIBUTION, поэтому добавляется требование, чтобы длина была больше 2, и в результате возвращается только строка, содержащая имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="52c7f-183">The attribute that represents the product on the right-hand side of the rule is contained in the NODE_DISTRIBUTION table; therefore, we retrieve only the row that contains an attribute name, by adding a requirement that the length be greater than 2.</span></span>  
  
 <span data-ttu-id="52c7f-184">Для удаления имени модели из третьего столбца используется обычная функция для работы со строками.</span><span class="sxs-lookup"><span data-stu-id="52c7f-184">A simple string function is used to remove the name of the model from the third column.</span></span> <span data-ttu-id="52c7f-185">(В качестве префикса для величин во вложенных столбцах обычно используется имя модели.)</span><span class="sxs-lookup"><span data-stu-id="52c7f-185">(Usually the model name is prefixed to the values of nested columns.)</span></span>  
  
 <span data-ttu-id="52c7f-186">Предложение WHERE задает для параметра NODE_TYPE значение 8, чтобы получить только правила.</span><span class="sxs-lookup"><span data-stu-id="52c7f-186">The WHERE clause specifies that the value of NODE_TYPE should be 8, to retrieve only rules.</span></span>  
  
 <span data-ttu-id="52c7f-187">Дополнительные примеры см. в статье [Примеры запросов моделей взаимосвязей](association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="52c7f-187">For more examples, see [Association Model Query Examples](association-model-query-examples.md).</span></span>  
  
###  <a name="example-2-content-query-on-a-decision-trees-model"></a><a name="bkmk_DecTree"></a> <span data-ttu-id="52c7f-188">Пример 2. Запрос содержимого из модели дерева принятия решений</span><span class="sxs-lookup"><span data-stu-id="52c7f-188">Example 2: Content Query on a Decision Trees Model</span></span>  
 <span data-ttu-id="52c7f-189">Модель дерева принятия решений может использоваться для прогнозирования, а также для классификации.</span><span class="sxs-lookup"><span data-stu-id="52c7f-189">A decision tree model can be used for prediction as well as for classification.</span></span>  <span data-ttu-id="52c7f-190">В этом примере предполагается, что модель используется для прогнозирования результата, но при этом также требуется определить, по каким факторам или правилами можно классифицировать результат.</span><span class="sxs-lookup"><span data-stu-id="52c7f-190">This example assumes that you are using the model to predict an outcome, but you also want to find out which factors or rules can be used to classify the outcome.</span></span>  
  
 <span data-ttu-id="52c7f-191">В модели дерева принятия решений узлы используются для представления и деревьев, и конечных узлов.</span><span class="sxs-lookup"><span data-stu-id="52c7f-191">In a decision tree model, nodes are used to represent both trees and leaf nodes.</span></span> <span data-ttu-id="52c7f-192">Заголовок каждого узла содержит описание пути к результату.</span><span class="sxs-lookup"><span data-stu-id="52c7f-192">The caption for each node contains the description of the path to the outcome.</span></span> <span data-ttu-id="52c7f-193">Поэтому, чтобы проследить путь для любого конкретного результата, необходимо определить узел, который его содержит, и получить подробные сведения по этому узлу.</span><span class="sxs-lookup"><span data-stu-id="52c7f-193">Therefore, to trace the path for any particular outcome, you need to identify the node that contains it, and get the details for that node.</span></span>  
  
 <span data-ttu-id="52c7f-194">Для получения идентификатора связанного узла в прогнозирующий запрос добавляется прогнозирующая функция [PredictNodeId (расширения интеллектуального анализа данных)](/sql/dmx/predictnodeid-dmx), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="52c7f-194">In your prediction query, you add the prediction function [PredictNodeId &#40;DMX&#41;](/sql/dmx/predictnodeid-dmx), to get the ID of the related node, as shown in the following example:</span></span>  
  
```  
SELECT  Predict([Bike Buyer]), PredictNodeID([Bike Buyer])   
FROM [<decision tree model name>]  
PREDICTION JOIN   
<input rowset>   
```  
  
 <span data-ttu-id="52c7f-195">Зная идентификатор узла, содержащего результат, можно узнать правило или путь, объясняющие прогноз, с помощью запроса к содержимому, в котором указан параметр NODE_CAPTION:</span><span class="sxs-lookup"><span data-stu-id="52c7f-195">Once you have the ID of the node that contains the outcome, you can retrieve the rule or path that explains the prediction by creating a content query that includes the NODE_CAPTION, as follows:</span></span>  
  
```  
SELECT NODE_CAPTION  
FROM [<decision tree model name>]   
WHERE NODE_UNIQUE_NAME= '<node id>'  
```  
  
 <span data-ttu-id="52c7f-196">Дополнительные примеры см. в разделе [Примеры запросов к модели дерева принятия решений](decision-trees-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="52c7f-196">For more examples, see [Decision Trees Model Query Examples](decision-trees-model-query-examples.md).</span></span>  
  
##  <a name="working-with-the-query-results"></a><a name="bkmk_Results"></a><span data-ttu-id="52c7f-197">Работа с результатами запроса</span><span class="sxs-lookup"><span data-stu-id="52c7f-197">Working with the Query Results</span></span>  
 <span data-ttu-id="52c7f-198">Как показывают эти примеры, запросы к содержимому чаще всего возвращают наборы строк в виде таблиц, но могут также включать сведения из вложенных столбцов.</span><span class="sxs-lookup"><span data-stu-id="52c7f-198">As the examples demonstrate, content queries mostly return tabular rowsets, but can also include information from nested columns.</span></span> <span data-ttu-id="52c7f-199">Можно выполнить сведение возвращенного набора строк, но это может привести к усложнению работы с результатами.</span><span class="sxs-lookup"><span data-stu-id="52c7f-199">You can flatten the rowset that is returned, but this can make working with results more complex.</span></span> <span data-ttu-id="52c7f-200">В частности, содержимое узла NODE_DISTRIBUTION является вложенным, но содержит много интересных сведений о модели.</span><span class="sxs-lookup"><span data-stu-id="52c7f-200">The content of the NODE_DISTRIBUTION node in particular is nested, but contains much interesting information about the model.</span></span>  
  
 <span data-ttu-id="52c7f-201">Дополнительные сведения о работе с иерархическими наборами строк см. в спецификации OLEDB на сайте MSDN.</span><span class="sxs-lookup"><span data-stu-id="52c7f-201">For more information about how to work with hierarchical rowsets, see the OLEDB specification on MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c7f-202">См. также:</span><span class="sxs-lookup"><span data-stu-id="52c7f-202">See Also</span></span>  
 <span data-ttu-id="52c7f-203">[Основные сведения о инструкции SELECT расширений интеллектуального анализа данных](/sql/dmx/understanding-the-dmx-select-statement) </span><span class="sxs-lookup"><span data-stu-id="52c7f-203">[Understanding the DMX Select Statement](/sql/dmx/understanding-the-dmx-select-statement) </span></span>  
 [<span data-ttu-id="52c7f-204">Запросы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="52c7f-204">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
