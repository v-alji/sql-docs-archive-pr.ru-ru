---
title: Примеры запросов модели взаимосвязей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- association algorithms [Analysis Services]
- rules [Data Mining]
- association rules
- content queries [DMX]
ms.assetid: 68b39f5c-c439-44ac-8046-6f2d36649059
author: minewiskan
ms.author: owend
ms.openlocfilehash: a19eb2302639c7f13d48a8778969bbeca4fee18d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667967"
---
# <a name="association-model-query-examples"></a><span data-ttu-id="d7acb-102">Примеры запросов моделей взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="d7acb-102">Association Model Query Examples</span></span>
  <span data-ttu-id="d7acb-103">Создаваемый запрос к модели интеллектуального анализа данных может быть запросом содержимого. Такой запрос предоставляет подробные сведения о правилах и наборах элементов, обнаруженных в процессе анализа. Можно также создавать прогнозирующие запросы. Они используют взаимосвязи, обнаруженные в данных, для создания прогнозов.</span><span class="sxs-lookup"><span data-stu-id="d7acb-103">When you create a query against a data mining model, you can create either a content query, which provides details about the rules and itemsets discovered during analysis, or you can create a prediction query, which uses the associations discovered in the data to make predictions.</span></span> <span data-ttu-id="d7acb-104">Прогнозы для моделей взаимосвязей обычно основаны на правилах, и их можно использовать для рекомендаций, в то время как запросы к содержимому обычно исследуют связи между наборами элементов.</span><span class="sxs-lookup"><span data-stu-id="d7acb-104">For an association model, predictions typically are based on rules, and can be used to make recommendations, whereas queries on content typically explore the relationship among itemsets.</span></span> <span data-ttu-id="d7acb-105">Можно также получать метаданные, описывающие модель.</span><span class="sxs-lookup"><span data-stu-id="d7acb-105">You can also retrieve metadata about the model.</span></span>  
  
 <span data-ttu-id="d7acb-106">Этот раздел посвящен созданию указанных запросов для моделей, основанных на алгоритме правил взаимосвязей [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7acb-106">This section explains how to create these kinds of queries for models that are based on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules algorithm.</span></span>  
  
 <span data-ttu-id="d7acb-107">**Запросы содержимого**</span><span class="sxs-lookup"><span data-stu-id="d7acb-107">**Content Queries**</span></span>  
  
 [<span data-ttu-id="d7acb-108">Получение метаданных модели с помощью расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="d7acb-108">Getting model metadata data by using DMX</span></span>](#bkmk_Query1)  
  
 [<span data-ttu-id="d7acb-109">Получение метаданных из набора строк схемы</span><span class="sxs-lookup"><span data-stu-id="d7acb-109">Getting metadata from the schema rowset</span></span>](#bkmk_Query2)  
  
 [<span data-ttu-id="d7acb-110">Получение первоначальных параметров модели</span><span class="sxs-lookup"><span data-stu-id="d7acb-110">Retrieving the original parameters for the model</span></span>](#bkmk_Query3)  
  
 [<span data-ttu-id="d7acb-111">Получение списка наборов элементов и продуктов</span><span class="sxs-lookup"><span data-stu-id="d7acb-111">Retrieving a list of itemsets and products</span></span>](#bkmk_Query4)  
  
 [<span data-ttu-id="d7acb-112">Возвращение первых 10 наборов элементов</span><span class="sxs-lookup"><span data-stu-id="d7acb-112">Returning the top 10 itemsets</span></span>](#bkmk_Query5)  
  
 <span data-ttu-id="d7acb-113">**Прогнозирующие запросы**</span><span class="sxs-lookup"><span data-stu-id="d7acb-113">**Prediction Queries**</span></span>  
  
 [<span data-ttu-id="d7acb-114">Прогноз взаимосвязи элементов</span><span class="sxs-lookup"><span data-stu-id="d7acb-114">Predicting associated items</span></span>](#bkmk_Query6)  
  
 [<span data-ttu-id="d7acb-115">Определение достоверности для связанных наборов элементов</span><span class="sxs-lookup"><span data-stu-id="d7acb-115">Determining confidence for related itemsets</span></span>](#bkmk_Query7)  
  
##  <a name="finding-information-about-the-model"></a><a name="bkmk_top2"></a> <span data-ttu-id="d7acb-116">Поиск сведений о модели</span><span class="sxs-lookup"><span data-stu-id="d7acb-116">Finding Information about the Model</span></span>  
 <span data-ttu-id="d7acb-117">Все модели интеллектуального анализа данных возвращают содержимое, полученное алгоритмом, в соответствии со стандартизованной схемой, то есть набором строк схемы модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="d7acb-117">All mining models expose the content learned by the algorithm according to a standardized schema, which is named the mining model schema rowset.</span></span> <span data-ttu-id="d7acb-118">Запросы к набору строк схемы модели интеллектуального анализа данных можно создавать с помощью инструкций расширений интеллектуального анализа данных или с помощью хранимых процедур служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7acb-118">You can create queries against the mining model schema rowset either by using Data Mining Extensions (DMX) statements, or by using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stored procedures.</span></span> <span data-ttu-id="d7acb-119">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]возможны также запросы непосредственно к наборам строк схемы модели интеллектуального анализа данных как к системным таблицам с использованием синтаксиса, подобного языку SQL.</span><span class="sxs-lookup"><span data-stu-id="d7acb-119">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can also query the schema rowsets directly as system tables, by using a SQL-like syntax.</span></span>  
  
###  <a name="sample-query-1-getting-model-metadata-by-using-dmx"></a><a name="bkmk_Query1"></a> <span data-ttu-id="d7acb-120">Образец запроса 1. Получение метаданных модели с помощью расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="d7acb-120">Sample Query 1: Getting Model Metadata by Using DMX</span></span>  
 <span data-ttu-id="d7acb-121">Следующий запрос возвращает основные метаданные модели взаимосвязей `Association`, такие как имя модели, базу данных, в которой она хранится, и количество дочерних узлов модели.</span><span class="sxs-lookup"><span data-stu-id="d7acb-121">The following query returns basic metadata about the association model, `Association`, such as the name of the model, the database where the model is stored, and the number of child nodes in the model.</span></span> <span data-ttu-id="d7acb-122">В этом запросе для получения метаданных из родительского узла модели применяется DMX-запрос содержимого.</span><span class="sxs-lookup"><span data-stu-id="d7acb-122">This query uses a DMX content query to retrieve the metadata from the parent node of the model:</span></span>  
  
```  
SELECT MODEL_CATALOG, MODEL_NAME, NODE_CAPTION,   
NODE_SUPPORT, [CHILDREN_CARDINALITY], NODE_DESCRIPTION  
FROM Association.CONTENT  
WHERE NODE_TYPE = 1  
```  
  
> [!NOTE]  
>  <span data-ttu-id="d7acb-123">Имя столбца CHILDREN_CARDINALITY следует заключить в квадратные скобки, чтобы отличить его от одноименного зарезервированного ключевого слова языка многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="d7acb-123">You must enclose the name of the column, CHILDREN_CARDINALITY, in brackets to distinguish it from the MDX reserved keyword of the same name.</span></span>  
  
 <span data-ttu-id="d7acb-124">Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="d7acb-124">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7acb-125">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d7acb-125">MODEL_CATALOG</span></span>|<span data-ttu-id="d7acb-126">Проверка взаимосвязи</span><span class="sxs-lookup"><span data-stu-id="d7acb-126">Association Test</span></span>|  
|<span data-ttu-id="d7acb-127">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="d7acb-127">MODEL_NAME</span></span>|<span data-ttu-id="d7acb-128">Взаимосвязь</span><span class="sxs-lookup"><span data-stu-id="d7acb-128">Association</span></span>|  
|<span data-ttu-id="d7acb-129">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="d7acb-129">NODE_CAPTION</span></span>|<span data-ttu-id="d7acb-130">Модель правил взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="d7acb-130">Association Rules Model</span></span>|  
|<span data-ttu-id="d7acb-131">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="d7acb-131">NODE_SUPPORT</span></span>|<span data-ttu-id="d7acb-132">14879</span><span class="sxs-lookup"><span data-stu-id="d7acb-132">14879</span></span>|  
|<span data-ttu-id="d7acb-133">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d7acb-133">CHILDREN_CARDINALITY</span></span>|<span data-ttu-id="d7acb-134">942</span><span class="sxs-lookup"><span data-stu-id="d7acb-134">942</span></span>|  
|<span data-ttu-id="d7acb-135">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d7acb-135">NODE_DESCRIPTION</span></span>|<span data-ttu-id="d7acb-136">Модель правил взаимосвязей; ITEMSET_COUNT=679; RULE_COUNT=263; MIN_SUPPORT=14; MAX_SUPPORT=4334; MIN_ITEMSET_SIZE=0; MAX_ITEMSET_SIZE=3; MIN_PROBABILITY=0.400390625; MAX_PROBABILITY=1; MIN_LIFT=0.14309369632511; MAX_LIFT=1.95758227647523</span><span class="sxs-lookup"><span data-stu-id="d7acb-136">Association Rules Model; ITEMSET_COUNT=679; RULE_COUNT=263; MIN_SUPPORT=14; MAX_SUPPORT=4334; MIN_ITEMSET_SIZE=0; MAX_ITEMSET_SIZE=3; MIN_PROBABILITY=0.400390625; MAX_PROBABILITY=1; MIN_LIFT=0.14309369632511; MAX_LIFT=1.95758227647523</span></span>|  
  
 <span data-ttu-id="d7acb-137">Узнать, что означают эти столбцы в модели взаимосвязей, можно в разделе [Содержимое моделей интеллектуального анализа данных для моделей взаимосвязей (службы Analysis Services — интеллектуальный анализ данных)](mining-model-content-for-association-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="d7acb-137">For a definition of what these columns mean in an association model, see [Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-association-models-analysis-services-data-mining.md).</span></span>  
  
 [<span data-ttu-id="d7acb-138">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="d7acb-138">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-2-getting-additional-metadata-from-the-schema-rowset"></a><a name="bkmk_Query2"></a> <span data-ttu-id="d7acb-139">Пример запроса 2: получение дополнительных метаданных из набора строк схемы</span><span class="sxs-lookup"><span data-stu-id="d7acb-139">Sample Query 2: Getting Additional Metadata from the Schema Rowset</span></span>  
 <span data-ttu-id="d7acb-140">Выполнение запроса набора строк схемы интеллектуального анализа данных позволяет получить те же сведения, которые возвращаются DMX-запросом содержимого.</span><span class="sxs-lookup"><span data-stu-id="d7acb-140">By querying the data mining schema rowset, you can find the same information that is returned in a DMX content query.</span></span> <span data-ttu-id="d7acb-141">Однако набор строк схемы предоставляет и некоторые дополнительные столбцы, например дату последней обработки модели, структуру интеллектуального анализа данных, имя столбца прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="d7acb-141">However, the schema rowset provides some additional columns, such as the date the model was last processed, the mining structure, and the name of the column used as the predictable attribute.</span></span>  
  
```  
SELECT MODEL_CATALOG, MODEL_NAME, SERVICE_NAME, PREDICTION_ENTITY,   
MINING_STRUCTURE, LAST_PROCESSED  
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'Association'  
```  
  
 <span data-ttu-id="d7acb-142">Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="d7acb-142">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7acb-143">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d7acb-143">MODEL_CATALOG</span></span>|<span data-ttu-id="d7acb-144">Adventure Works DW Multidimensional 2012</span><span class="sxs-lookup"><span data-stu-id="d7acb-144">Adventure Works DW Multidimensional 2012</span></span>|  
|<span data-ttu-id="d7acb-145">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="d7acb-145">MODEL_NAME</span></span>|<span data-ttu-id="d7acb-146">Взаимосвязь</span><span class="sxs-lookup"><span data-stu-id="d7acb-146">Association</span></span>|  
|<span data-ttu-id="d7acb-147">SERVICE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7acb-147">SERVICE_NAME</span></span>|<span data-ttu-id="d7acb-148">Модель правил взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="d7acb-148">Association Rules Model</span></span>|  
|<span data-ttu-id="d7acb-149">PREDICTION_ENTITY</span><span class="sxs-lookup"><span data-stu-id="d7acb-149">PREDICTION_ENTITY</span></span>|<span data-ttu-id="d7acb-150">v Assoc Seq Line Items</span><span class="sxs-lookup"><span data-stu-id="d7acb-150">v Assoc Seq Line Items</span></span>|  
|<span data-ttu-id="d7acb-151">MINING_STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="d7acb-151">MINING_STRUCTURE</span></span>|<span data-ttu-id="d7acb-152">Взаимосвязь</span><span class="sxs-lookup"><span data-stu-id="d7acb-152">Association</span></span>|  
|<span data-ttu-id="d7acb-153">LAST_PROCESSED</span><span class="sxs-lookup"><span data-stu-id="d7acb-153">LAST_PROCESSED</span></span>|<span data-ttu-id="d7acb-154">9/29/2007 10:21:24 PM</span><span class="sxs-lookup"><span data-stu-id="d7acb-154">9/29/2007 10:21:24 PM</span></span>|  
  
 [<span data-ttu-id="d7acb-155">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="d7acb-155">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-3-retrieving-original-parameters-for-model"></a><a name="bkmk_Query3"></a> <span data-ttu-id="d7acb-156">Пример запроса 3: получение первоначальных параметров модели</span><span class="sxs-lookup"><span data-stu-id="d7acb-156">Sample Query 3: Retrieving Original Parameters for Model</span></span>  
 <span data-ttu-id="d7acb-157">Следующий запрос возвращает один столбец, содержащий подробные сведения о значениях параметров, использованных при создании модели.</span><span class="sxs-lookup"><span data-stu-id="d7acb-157">The following query returns a single column that contains details about the parameter settings that were used when the model was created.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
from $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'Association'  
```  
  
 <span data-ttu-id="d7acb-158">Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="d7acb-158">Example results:</span></span>  
  
 <span data-ttu-id="d7acb-159">MAXIMUM_ITEMSET_COUNT=200000,MAXIMUM_ITEMSET_SIZE=3,MAXIMUM_SUPPORT=1,MINIMUM_SUPPORT=9.40923449156529E-04,MINIMUM_IMPORTANCE=-999999999,MINIMUM_ITEMSET_SIZE=0,MINIMUM_PROBABILITY=0.4</span><span class="sxs-lookup"><span data-stu-id="d7acb-159">MAXIMUM_ITEMSET_COUNT=200000,MAXIMUM_ITEMSET_SIZE=3,MAXIMUM_SUPPORT=1,MINIMUM_SUPPORT=9.40923449156529E-04,MINIMUM_IMPORTANCE=-999999999,MINIMUM_ITEMSET_SIZE=0,MINIMUM_PROBABILITY=0.4</span></span>  
  
 [<span data-ttu-id="d7acb-160">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="d7acb-160">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="finding-information-about-rules-and-itemsets"></a><span data-ttu-id="d7acb-161">Поиск сведений о правилах и наборах элементов</span><span class="sxs-lookup"><span data-stu-id="d7acb-161">Finding Information about Rules and Itemsets</span></span>  
 <span data-ttu-id="d7acb-162">Модель взаимосвязей чаще всего применяется для поиска часто встречающихся наборов элементов и для извлечения подробных сведений о конкретных правилах и наборах элементов.</span><span class="sxs-lookup"><span data-stu-id="d7acb-162">There are two common uses of an association model: to discover information about frequent itemsets, and to extract details about particular rules and itemsets.</span></span> <span data-ttu-id="d7acb-163">Например, можно извлечь список правил, рейтинги которых представляют особый интерес, или создать список наиболее часто встречающихся наборов элементов.</span><span class="sxs-lookup"><span data-stu-id="d7acb-163">For example, you might want to extract a list of rules that were scored as being especially interesting, or create a list of the most common itemsets.</span></span> <span data-ttu-id="d7acb-164">Эти сведения можно получить с помощью запроса к содержимому, созданного с помощью расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="d7acb-164">You retrieve such information by using a DMX content query.</span></span> <span data-ttu-id="d7acb-165">Эти сведения также можно просматривать с помощью **средства просмотра взаимосвязей (Майкрософт)**.</span><span class="sxs-lookup"><span data-stu-id="d7acb-165">You can also browse this information by using the **Microsoft Association Viewer**.</span></span>  
  
###  <a name="sample-query-4-retrieving-list-of-itemsets-and-products"></a><a name="bkmk_Query4"></a> <span data-ttu-id="d7acb-166">Пример запроса 4: получение списка наборов элементов и продуктов</span><span class="sxs-lookup"><span data-stu-id="d7acb-166">Sample Query 4: Retrieving List of Itemsets and Products</span></span>  
 <span data-ttu-id="d7acb-167">Следующий запрос получает все наборы элементов вместе с вложенной таблицей, содержащей товары, включенные в каждый набор элементов.</span><span class="sxs-lookup"><span data-stu-id="d7acb-167">The following query retrieves all of the itemsets, together with a nested table that lists the products included in each itemset.</span></span> <span data-ttu-id="d7acb-168">Столбец NODE_NAME содержит уникальный идентификатор набора элементов в данной модели, а NODE_CAPTION — текстовое описание элементов.</span><span class="sxs-lookup"><span data-stu-id="d7acb-168">The NODE_NAME column contains the unique ID of the itemset within the model, whereas the NODE_CAPTION provides a text description of the items.</span></span> <span data-ttu-id="d7acb-169">В данном примере вложенная таблица переведена в плоский формат, так что для набора элементов, содержащего два товара, результаты состоят из двух строк.</span><span class="sxs-lookup"><span data-stu-id="d7acb-169">In this example, the nested table is flattened, so that an itemset that contains two products generates two rows in the results.</span></span> <span data-ttu-id="d7acb-170">Ключевое слово FLATTENED можно опустить, если клиент поддерживает иерархические данные.</span><span class="sxs-lookup"><span data-stu-id="d7acb-170">You can omit the FLATTENED keyword if your client supports hierarchical data.</span></span>  
  
```  
SELECT FLATTENED NODE_NAME, NODE_CAPTION,  
NODE_PROBABILITY, NODE_SUPPORT,  
(SELECT ATTRIBUTE_NAME FROM NODE_DISTRIBUTION) as PurchasedProducts  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="d7acb-171">Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="d7acb-171">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7acb-172">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7acb-172">NODE_NAME</span></span>|<span data-ttu-id="d7acb-173">37</span><span class="sxs-lookup"><span data-stu-id="d7acb-173">37</span></span>|  
|<span data-ttu-id="d7acb-174">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="d7acb-174">NODE_CAPTION</span></span>|<span data-ttu-id="d7acb-175">Sport-100 = существует</span><span class="sxs-lookup"><span data-stu-id="d7acb-175">Sport-100 = Existing</span></span>|  
|<span data-ttu-id="d7acb-176">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="d7acb-176">NODE_PROBABILITY</span></span>|<span data-ttu-id="d7acb-177">0.291283016331743</span><span class="sxs-lookup"><span data-stu-id="d7acb-177">0.291283016331743</span></span>|  
|<span data-ttu-id="d7acb-178">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="d7acb-178">NODE_SUPPORT</span></span>|<span data-ttu-id="d7acb-179">4334</span><span class="sxs-lookup"><span data-stu-id="d7acb-179">4334</span></span>|  
|<span data-ttu-id="d7acb-180">PURCHASEDPRODUCTS.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7acb-180">PURCHASEDPRODUCTS.ATTRIBUTE_NAME</span></span>|<span data-ttu-id="d7acb-181">v Assoc Seq Line Items(Sport-100)</span><span class="sxs-lookup"><span data-stu-id="d7acb-181">v Assoc Seq Line Items(Sport-100)</span></span>|  
  
 [<span data-ttu-id="d7acb-182">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="d7acb-182">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-5-returning-top-10-itemsets"></a><a name="bkmk_Query5"></a> <span data-ttu-id="d7acb-183">Пример запроса 5: возвращение первых 10 наборов элементов</span><span class="sxs-lookup"><span data-stu-id="d7acb-183">Sample Query 5: Returning Top 10 Itemsets</span></span>  
 <span data-ttu-id="d7acb-184">В данном примере показано, как использовать некоторые функции группирования и сортировки, предоставляемые языком расширений интеллектуального анализа данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d7acb-184">This example demonstrates how to use some of the grouping and ordering functions that DMX provides by default.</span></span> <span data-ttu-id="d7acb-185">Запрос возвращает первые 10 наборов элементов после сортировки результатов по мощности несущего множества каждого узла.</span><span class="sxs-lookup"><span data-stu-id="d7acb-185">The query returns the top 10 itemsets when ordered by the support for each node.</span></span> <span data-ttu-id="d7acb-186">Заметьте, что в явном виде группировать результаты, как это делается в Transact-SQL, не нужно, однако в каждом запросе можно использовать только одну агрегатную функцию.</span><span class="sxs-lookup"><span data-stu-id="d7acb-186">Note that you do not need to explicitly group the results, as you would in Transact-SQL; however, you can use only one aggregate function in each query.</span></span>  
  
```  
SELECT TOP 10 (NODE_SUPPORT),NODE_NAME, NODE_CAPTION  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="d7acb-187">Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="d7acb-187">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7acb-188">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="d7acb-188">NODE_SUPPORT</span></span>|<span data-ttu-id="d7acb-189">4334</span><span class="sxs-lookup"><span data-stu-id="d7acb-189">4334</span></span>|  
|<span data-ttu-id="d7acb-190">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7acb-190">NODE_NAME</span></span>|<span data-ttu-id="d7acb-191">37</span><span class="sxs-lookup"><span data-stu-id="d7acb-191">37</span></span>|  
|<span data-ttu-id="d7acb-192">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="d7acb-192">NODE_CAPTION</span></span>|<span data-ttu-id="d7acb-193">Sport-100 = существует</span><span class="sxs-lookup"><span data-stu-id="d7acb-193">Sport-100 = Existing</span></span>|  
  
 [<span data-ttu-id="d7acb-194">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="d7acb-194">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="making-predictions-using-the-model"></a><span data-ttu-id="d7acb-195">Создание прогнозов с помощью модели</span><span class="sxs-lookup"><span data-stu-id="d7acb-195">Making Predictions using the Model</span></span>  
 <span data-ttu-id="d7acb-196">Модель правил взаимосвязи часто используют для создания рекомендаций, основанных на выявленной связи между наборами элементов.</span><span class="sxs-lookup"><span data-stu-id="d7acb-196">An association rules model is often used to generate recommendations, which are based on correlations discovered in the itemsets.</span></span> <span data-ttu-id="d7acb-197">Таким образом, при создании прогнозирующего запроса на основе модели ассоциативных правил используются правила модели для генерирования предположений на основе новых данных.</span><span class="sxs-lookup"><span data-stu-id="d7acb-197">Therefore, when you create a prediction query based on an association rules model, you are typically using the rules in the model to make guesses based on new data.</span></span>  <span data-ttu-id="d7acb-198">[PredictAssociation (расширения интеллектуального анализа данных)](/sql/dmx/predictassociation-dmx) — это функция, которая возвращает рекомендации и содержит несколько аргументов, которые можно использовать для изменения результатов запросов.</span><span class="sxs-lookup"><span data-stu-id="d7acb-198">[PredictAssociation &#40;DMX&#41;](/sql/dmx/predictassociation-dmx) is the function that returns recommendations, and has several arguments that you can use to customize the query results.</span></span>  
  
 <span data-ttu-id="d7acb-199">Другой пример использования запросов к модели взаимосвязей — определение достоверности различных правил и наборов элементов для сравнения эффективности различных стратегий продажи связанных товаров и услуг.</span><span class="sxs-lookup"><span data-stu-id="d7acb-199">Another example of where queries on an association model might be useful is to return the confidence for various rules and itemsets so that you can compare the effectiveness of different cross-sell strategies.</span></span> <span data-ttu-id="d7acb-200">В следующих примерах показано создание таких запросов.</span><span class="sxs-lookup"><span data-stu-id="d7acb-200">The following examples illustrate how to create such queries.</span></span>  
  
###  <a name="sample-query-6-predicting-associated-items"></a><a name="bkmk_Query6"></a> <span data-ttu-id="d7acb-201">Пример запроса 6: прогноз взаимосвязанных элементов</span><span class="sxs-lookup"><span data-stu-id="d7acb-201">Sample Query 6: Predicting Associated Items</span></span>  
 <span data-ttu-id="d7acb-202">В этом примере используется модель взаимосвязей, созданная в разделе [Учебник по интеллектуальному анализу данных — средний уровень (службы Analysis Services — интеллектуальный анализ данных)](../../tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="d7acb-202">This example uses the Association model created in the [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span> <span data-ttu-id="d7acb-203">В примере показано создание прогнозирующего запроса, который определяет, какие товары рекомендовать клиенту, купившему определенный товар.</span><span class="sxs-lookup"><span data-stu-id="d7acb-203">It demonstrates how to create a prediction query that tells you what products to recommend to a customer who has purchased a particular product.</span></span> <span data-ttu-id="d7acb-204">Тип запроса, в котором модель получает входные данные из инструкции `SELECT...UNION`, называется одноэлементным.</span><span class="sxs-lookup"><span data-stu-id="d7acb-204">This type of query, where you provide values to the model in a `SELECT...UNION` statement, is called a singleton query.</span></span> <span data-ttu-id="d7acb-205">Поскольку прогнозируемый столбец модели, соответствующий новым значениям, представляет собой вложенную таблицу, следует использовать одно предложение `SELECT` для установления соответствия между новым значением и столбцом вложенной таблицы `[Model]`, а другое предложение `SELECT` — для установления соответствия между столбцом вложенной таблицы и столбцом уровня вариантов `[v Assoc Seq Line Items]`.</span><span class="sxs-lookup"><span data-stu-id="d7acb-205">Because the predictable model column that corresponds to the new values is a nested table, you must use one `SELECT` clause to map the new value to the nested table column, `[Model]`, and another `SELECT` clause to map the nested table column to the case-level column, `[v Assoc Seq Line Items]`.</span></span> <span data-ttu-id="d7acb-206">Добавив к запросу ключевое слово INCLUDE-STATISTICS, можно увидеть вероятность и мощность несущего множества для рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="d7acb-206">Adding the keyword INCLUDE-STATISTICS to the query lets you see the probability and support for the recommendations.</span></span>  
  
```  
SELECT PredictAssociation([Association].[vAssocSeqLineItems],INCLUDE_STATISTICS, 3)  
FROM [Association]  
NATURAL PREDICTION JOIN   
(SELECT  
(SELECT 'Classic Vest' as [Model])  
AS [v Assoc Seq Line Items])  
AS t  
```  
  
 <span data-ttu-id="d7acb-207">Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="d7acb-207">Example results:</span></span>  
  
|<span data-ttu-id="d7acb-208">Модель</span><span class="sxs-lookup"><span data-stu-id="d7acb-208">Model</span></span>|<span data-ttu-id="d7acb-209">$SUPPORT</span><span class="sxs-lookup"><span data-stu-id="d7acb-209">$SUPPORT</span></span>|<span data-ttu-id="d7acb-210">$PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="d7acb-210">$PROBABILITY</span></span>|<span data-ttu-id="d7acb-211">$ADJUSTEDPROBABILITY</span><span class="sxs-lookup"><span data-stu-id="d7acb-211">$ADJUSTEDPROBABILITY</span></span>|  
|-----------|--------------|------------------|--------------------------|  
|<span data-ttu-id="d7acb-212">Sport-100</span><span class="sxs-lookup"><span data-stu-id="d7acb-212">Sport-100</span></span>|<span data-ttu-id="d7acb-213">4334</span><span class="sxs-lookup"><span data-stu-id="d7acb-213">4334</span></span>|<span data-ttu-id="d7acb-214">0.291283</span><span class="sxs-lookup"><span data-stu-id="d7acb-214">0.291283</span></span>|<span data-ttu-id="d7acb-215">0.252696</span><span class="sxs-lookup"><span data-stu-id="d7acb-215">0.252696</span></span>|  
|<span data-ttu-id="d7acb-216">Фляга для воды</span><span class="sxs-lookup"><span data-stu-id="d7acb-216">Water Bottle</span></span>|<span data-ttu-id="d7acb-217">2866</span><span class="sxs-lookup"><span data-stu-id="d7acb-217">2866</span></span>|<span data-ttu-id="d7acb-218">0.19262</span><span class="sxs-lookup"><span data-stu-id="d7acb-218">0.19262</span></span>|<span data-ttu-id="d7acb-219">0.175205</span><span class="sxs-lookup"><span data-stu-id="d7acb-219">0.175205</span></span>|  
|<span data-ttu-id="d7acb-220">Ремонтный комплект</span><span class="sxs-lookup"><span data-stu-id="d7acb-220">Patch kit</span></span>|<span data-ttu-id="d7acb-221">2113</span><span class="sxs-lookup"><span data-stu-id="d7acb-221">2113</span></span>|<span data-ttu-id="d7acb-222">0.142012</span><span class="sxs-lookup"><span data-stu-id="d7acb-222">0.142012</span></span>|<span data-ttu-id="d7acb-223">0.132389</span><span class="sxs-lookup"><span data-stu-id="d7acb-223">0.132389</span></span>|  
  
 [<span data-ttu-id="d7acb-224">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="d7acb-224">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-7-determining-confidence-for-related-itemsets"></a><a name="bkmk_Query7"></a> <span data-ttu-id="d7acb-225">Пример запроса 7: определение достоверности для связанных наборов элементов</span><span class="sxs-lookup"><span data-stu-id="d7acb-225">Sample Query 7: Determining Confidence for Related Itemsets</span></span>  
 <span data-ttu-id="d7acb-226">Правила полезны для формирования рекомендаций, но наборы элементов представляют больший интерес для углубленного анализа закономерностей в наборах данных.</span><span class="sxs-lookup"><span data-stu-id="d7acb-226">Whereas rules are useful for generating recommendations, itemsets are more interesting for deeper analysis of the patterns in the data set.</span></span> <span data-ttu-id="d7acb-227">Например, если рекомендация, возвращенная предыдущим запросом к выборке, неудовлетворительна, можно исследовать другие наборы элементов, содержащие продукт А, чтобы получить о нем более точное представление: покупают ли его вместе с любыми другими продуктами или его продажи сильно зависят от продаж каких-то определенных товаров.</span><span class="sxs-lookup"><span data-stu-id="d7acb-227">For example, if you were not satisfied with the recommendation that are returned by the previous sample query, you could examine other itemsets that contain Product A, to can get a better idea of whether Product A is an accessory that people tend to buy with all kinds of products, or whether A is strongly correlated with purchases of particular products.</span></span> <span data-ttu-id="d7acb-228">Легче всего исследовать подобные закономерности, отфильтровав наборы элементов в средстве просмотра взаимосвязей [!INCLUDE[msCoName](../../includes/msconame-md.md)] ; можно также получить эти сведения с помощью запроса.</span><span class="sxs-lookup"><span data-stu-id="d7acb-228">The easiest way to explore these relationships is by filtering the itemsets in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Viewer; however, you can retrieve the same information with a query.</span></span>  
  
 <span data-ttu-id="d7acb-229">Далее следует образец запроса, возвращающего все наборы данных с элементом «Фляга для воды», в том числе все наборы, состоящие из единственного элемента «Фляга для воды».</span><span class="sxs-lookup"><span data-stu-id="d7acb-229">The following sample query returns all itemsets that include the Water Bottle item, including the single item Water bottle.</span></span>  
  
```  
SELECT TOP 100 FROM   
(  
SELECT FLATTENED NODE_CAPTION, NODE_SUPPORT,   
(SELECT ATTRIBUTE_NAME from NODE_DISTRIBUTION  
WHERE ATTRIBUTE_NAME = 'v Assoc Seq Line Items(Water Bottle)') as D  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
) AS Items  
WHERE [D.ATTRIBUTE_NAME] <> NULL  
ORDER BY NODE_SUPPORT DESC  
```  
  
 <span data-ttu-id="d7acb-230">Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="d7acb-230">Example results:</span></span>  
  
|<span data-ttu-id="d7acb-231">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="d7acb-231">NODE_CAPTION</span></span>|<span data-ttu-id="d7acb-232">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="d7acb-232">NODE_SUPPORT</span></span>|<span data-ttu-id="d7acb-233">D.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7acb-233">D.ATTRIBUTE_NAME</span></span>|  
|-------------------|-------------------|-----------------------|  
|<span data-ttu-id="d7acb-234">Фляга для воды = имеется</span><span class="sxs-lookup"><span data-stu-id="d7acb-234">Water Bottle = Existing</span></span>|<span data-ttu-id="d7acb-235">2866</span><span class="sxs-lookup"><span data-stu-id="d7acb-235">2866</span></span>|<span data-ttu-id="d7acb-236">vAssocSeqLineItems(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="d7acb-236">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="d7acb-237">Держатель фляги для горного велосипеда = имеется, фляга для воды = имеется</span><span class="sxs-lookup"><span data-stu-id="d7acb-237">Mountain Bottle Cage = Existing, Water Bottle = Existing</span></span>|<span data-ttu-id="d7acb-238">1136</span><span class="sxs-lookup"><span data-stu-id="d7acb-238">1136</span></span>|<span data-ttu-id="d7acb-239">vAssocSeqLineItems(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="d7acb-239">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="d7acb-240">Держатель фляги для дорожного велосипеда = имеется, фляга для воды = имеется</span><span class="sxs-lookup"><span data-stu-id="d7acb-240">Road Bottle Cage = Existing, Water Bottle = Existing</span></span>|<span data-ttu-id="d7acb-241">1068</span><span class="sxs-lookup"><span data-stu-id="d7acb-241">1068</span></span>|<span data-ttu-id="d7acb-242">vAssocSeqLineItems(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="d7acb-242">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="d7acb-243">Фляга для воды = имеется, Sport-100 = имеется</span><span class="sxs-lookup"><span data-stu-id="d7acb-243">Water Bottle = Existing, Sport-100 = Existing</span></span>|<span data-ttu-id="d7acb-244">734</span><span class="sxs-lookup"><span data-stu-id="d7acb-244">734</span></span>|<span data-ttu-id="d7acb-245">vAssocSeqLineItems(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="d7acb-245">v Assoc Seq Line Items(Water Bottle)</span></span>|  
  
 <span data-ttu-id="d7acb-246">Этот запрос возвращает и соответствующие критерию строки из вложенной таблицы, и все строки из таблицы вариантов или все внешние строки.</span><span class="sxs-lookup"><span data-stu-id="d7acb-246">This query returns both the rows from the nested table that match the criteria, and all the rows from the outside or case table.</span></span> <span data-ttu-id="d7acb-247">Поэтому следует добавить условие, отсеивающее строки таблицы вариантов, у которых имя целевого атрибута имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="d7acb-247">Therefore, you must add a condition that eliminates the case table rows that have a null value for the target attribute name.</span></span>  
  
 [<span data-ttu-id="d7acb-248">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="d7acb-248">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="function-list"></a><span data-ttu-id="d7acb-249">Список функций</span><span class="sxs-lookup"><span data-stu-id="d7acb-249">Function List</span></span>  
 <span data-ttu-id="d7acb-250">Все алгоритмы [!INCLUDE[msCoName](../../includes/msconame-md.md)] поддерживают общий набор функций.</span><span class="sxs-lookup"><span data-stu-id="d7acb-250">All [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms support a common set of functions.</span></span> <span data-ttu-id="d7acb-251">Алгоритм взаимосвязей [!INCLUDE[msCoName](../../includes/msconame-md.md)] поддерживает также дополнительные функции, представленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d7acb-251">However, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association algorithm supports the additional functions listed in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7acb-252">прогнозирующую функцию</span><span class="sxs-lookup"><span data-stu-id="d7acb-252">Prediction Function</span></span>|<span data-ttu-id="d7acb-253">Использование</span><span class="sxs-lookup"><span data-stu-id="d7acb-253">Usage</span></span>|  
|[<span data-ttu-id="d7acb-254">IsDescendant (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="d7acb-254">IsDescendant &#40;DMX&#41;</span></span>](/sql/dmx/isdescendant-dmx)|<span data-ttu-id="d7acb-255">Определяет, является ли один узел дочерним для другого узла в диаграмме нейронной сети.</span><span class="sxs-lookup"><span data-stu-id="d7acb-255">Determines whether one node is a child of another node in the neural network graph.</span></span>|  
|[<span data-ttu-id="d7acb-256">IsInNode (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="d7acb-256">IsInNode &#40;DMX&#41;</span></span>](/sql/dmx/isinnode-dmx)|<span data-ttu-id="d7acb-257">Указывает, содержит ли заданный узел текущий вариант.</span><span class="sxs-lookup"><span data-stu-id="d7acb-257">Indicates whether the specified node contains the current case.</span></span>|  
|[<span data-ttu-id="d7acb-258">PredictAdjustedProbability (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="d7acb-258">PredictAdjustedProbability &#40;DMX&#41;</span></span>](/sql/dmx/predictadjustedprobability-dmx)|<span data-ttu-id="d7acb-259">Возвращает взвешенную вероятность.</span><span class="sxs-lookup"><span data-stu-id="d7acb-259">Returns the weighted probability.</span></span>|  
|[<span data-ttu-id="d7acb-260">PredictAssociation (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="d7acb-260">PredictAssociation &#40;DMX&#41;</span></span>](/sql/dmx/predictassociation-dmx)|<span data-ttu-id="d7acb-261">Прогнозирует вхождение в ассоциативном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="d7acb-261">Predicts membership in an associative dataset.</span></span>|  
|[<span data-ttu-id="d7acb-262">PredictHistogram (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="d7acb-262">PredictHistogram &#40;DMX&#41;</span></span>](/sql/dmx/predicthistogram-dmx)|<span data-ttu-id="d7acb-263">Возвращает таблицу значений, связанную с текущим прогнозируемым значением.</span><span class="sxs-lookup"><span data-stu-id="d7acb-263">Returns a table of values related to the current predicted value.</span></span>|  
|[<span data-ttu-id="d7acb-264">PredictNodeId (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="d7acb-264">PredictNodeId &#40;DMX&#41;</span></span>](/sql/dmx/predictnodeid-dmx)|<span data-ttu-id="d7acb-265">Возвращает параметр Node_ID для каждого случая.</span><span class="sxs-lookup"><span data-stu-id="d7acb-265">Returns the Node_ID for each case.</span></span>|  
|[<span data-ttu-id="d7acb-266">PredictProbability (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="d7acb-266">PredictProbability &#40;DMX&#41;</span></span>](/sql/dmx/predictprobability-dmx)|<span data-ttu-id="d7acb-267">Возвращает вероятность для прогнозируемого значения.</span><span class="sxs-lookup"><span data-stu-id="d7acb-267">Returns probability for the predicted value.</span></span>|  
|[<span data-ttu-id="d7acb-268">PredictSupport (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="d7acb-268">PredictSupport &#40;DMX&#41;</span></span>](/sql/dmx/predictsupport-dmx)|<span data-ttu-id="d7acb-269">Возвращает опорное значение для указанного состояния.</span><span class="sxs-lookup"><span data-stu-id="d7acb-269">Returns the support value for a specified state.</span></span>|  
|[<span data-ttu-id="d7acb-270">PredictVariance (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="d7acb-270">PredictVariance &#40;DMX&#41;</span></span>](/sql/dmx/predictvariance-dmx)|<span data-ttu-id="d7acb-271">Возвращает дисперсию для прогнозируемого значения.</span><span class="sxs-lookup"><span data-stu-id="d7acb-271">Returns variance for the predicted value.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7acb-272">См. также:</span><span class="sxs-lookup"><span data-stu-id="d7acb-272">See Also</span></span>  
 <span data-ttu-id="d7acb-273">[Алгоритм взаимосвязей (Майкрософт)](microsoft-association-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="d7acb-273">[Microsoft Association Algorithm](microsoft-association-algorithm.md) </span></span>  
 <span data-ttu-id="d7acb-274">[Технический справочник по алгоритму взаимосвязей (Майкрософт)](microsoft-association-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d7acb-274">[Microsoft Association Algorithm Technical Reference](microsoft-association-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="d7acb-275">Содержимое моделей интеллектуального анализа данных для моделей взаимосвязей (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="d7acb-275">Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-association-models-analysis-services-data-mining.md)  
  
  
