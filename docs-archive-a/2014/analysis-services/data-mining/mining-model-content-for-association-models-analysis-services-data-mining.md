---
title: Содержимое моделей интеллектуального анализа данных для моделей взаимосвязей (Analysis Services-Data Mining) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- association algorithms [Analysis Services]
- mining model content, association models
- rules [Data Mining]
- associations [Analysis Services]
ms.assetid: d5849bcb-4b8f-4f71-9761-7dc5bb465224
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8904ce155526aee595db19094fd2bad48770e83e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658548"
---
# <a name="mining-model-content-for-association-models-analysis-services---data-mining"></a><span data-ttu-id="24682-102">Содержимое моделей интеллектуального анализа данных для моделей взаимосвязей (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="24682-102">Mining Model Content for Association Models (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="24682-103">В этой статье описано содержимое модели интеллектуального анализа данных, характерное для моделей, в которых используется алгоритм правил взаимосвязей [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24682-103">This topic describes mining model content that is specific to models that use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules algorithm.</span></span> <span data-ttu-id="24682-104">Описание общей и статистической терминологии, связанной с содержимым модели интеллектуального анализа данных, областью применения которого являются модели всех типов, см. в статье [Содержимое модели интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="24682-104">For an explanation of general and statistical terminology related to mining model content that applies to all model types, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="understanding-the-structure-of-an-association-model"></a><span data-ttu-id="24682-105">Основные сведения о структуре модели взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="24682-105">Understanding the Structure of an Association Model</span></span>  
 <span data-ttu-id="24682-106">Модель взаимосвязей имеет простую структуру.</span><span class="sxs-lookup"><span data-stu-id="24682-106">An association model has a simple structure.</span></span> <span data-ttu-id="24682-107">Каждая модель имеет единственный родительский узел, который представляет модель и ее метаданные, а каждый родительский узел включает плоский список наборов элементов и правил.</span><span class="sxs-lookup"><span data-stu-id="24682-107">Each model has a single parent node that represents the model and its metadata, and each parent node has a flat list of itemsets and rules.</span></span> <span data-ttu-id="24682-108">Наборы элементов и правила не организованы в виде деревьев, а упорядочены так, что вначале представлены наборы элементов, а за ними следуют правила, как показано в следующей диаграмме.</span><span class="sxs-lookup"><span data-stu-id="24682-108">The itemsets and rules are not organized in trees, they are ordered with itemsets first and rules next as shown in the following diagram.</span></span>  
  
 <span data-ttu-id="24682-109">![структура содержимого для моделей взаимосвязей](../media/modelcontentstructure-assoc.gif "структура содержимого для моделей взаимосвязей")</span><span class="sxs-lookup"><span data-stu-id="24682-109">![structure of model content for association models](../media/modelcontentstructure-assoc.gif "structure of model content for association models")</span></span>  
  
 <span data-ttu-id="24682-110">Каждый набор элементов содержится в своем собственном узле (NODE_TYPE = 7).</span><span class="sxs-lookup"><span data-stu-id="24682-110">Each itemset is contained in its own node (NODE_TYPE = 7).</span></span> <span data-ttu-id="24682-111">Этот *узел* включает определение набора элементов, данные о количестве вариантов, содержащих этот набор элементов, и другую информацию.</span><span class="sxs-lookup"><span data-stu-id="24682-111">The *node* includes the definition of the itemset, the number of cases that contain this itemset, and other information.</span></span>  
  
 <span data-ttu-id="24682-112">Каждое правило также содержится в своем собственном узле (NODE_TYPE = 8).</span><span class="sxs-lookup"><span data-stu-id="24682-112">Each rule is also contained in its own node (NODE_TYPE = 8).</span></span> <span data-ttu-id="24682-113">*Правило* описывает общий шаблон, который показывает, как устанавливаются связи между элементами.</span><span class="sxs-lookup"><span data-stu-id="24682-113">A *rule* describes a general pattern for how items are associated.</span></span> <span data-ttu-id="24682-114">Правило внешне выглядит как инструкция IF-THEN.</span><span class="sxs-lookup"><span data-stu-id="24682-114">A rule is like an IF-THEN statement.</span></span> <span data-ttu-id="24682-115">Левая часть правила показывает существующее условие или набор условий.</span><span class="sxs-lookup"><span data-stu-id="24682-115">The left-hand side of the rule shows an existing condition or set of conditions.</span></span> <span data-ttu-id="24682-116">Правая часть правила показывает элемент в конкретном наборе данных, который обычно связан с условиями в левой части.</span><span class="sxs-lookup"><span data-stu-id="24682-116">The right-hand side of the rule shows the item in your data set that is usually associated with the conditions on the left side.</span></span>  
  
 <span data-ttu-id="24682-117">**Примечание.** Если есть необходимость извлечь либо правила, либо наборы элементов, можно воспользоваться запросом, который возвращает только узлы требуемого типа.</span><span class="sxs-lookup"><span data-stu-id="24682-117">**Note** If you want to extract either the rules or the itemsets, you can use a query to return only the node types that you want.</span></span> <span data-ttu-id="24682-118">Дополнительные сведения см. в статье [Примеры запросов моделей взаимосвязей](association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="24682-118">For more information, see [Association Model Query Examples](association-model-query-examples.md).</span></span>  
  
## <a name="model-content-for-an-association-model"></a><span data-ttu-id="24682-119">Содержимое модели для модели взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="24682-119">Model Content for an Association Model</span></span>  
 <span data-ttu-id="24682-120">В этом разделе приведены подробные сведения и примеры, относящиеся только к тем столбцам в содержимом модели интеллектуального анализа данных, которые являются значимыми для моделей взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="24682-120">This section provides detail and examples only for those columns in the mining model content that are relevant for association models.</span></span>  
  
 <span data-ttu-id="24682-121">Сведения о столбцах общего назначения MODEL_CATALOG, MODEL_NAME и других в наборе строк схемы см. в разделе [Содержимое модели интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="24682-121">For information about the general-purpose columns in the schema rowset, such as MODEL_CATALOG and MODEL_NAME, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="24682-122">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="24682-122">MODEL_CATALOG</span></span>  
 <span data-ttu-id="24682-123">Имя базы данных, в которой хранится модель.</span><span class="sxs-lookup"><span data-stu-id="24682-123">Name of the database where the model is stored.</span></span>  
  
 <span data-ttu-id="24682-124">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="24682-124">MODEL_NAME</span></span>  
 <span data-ttu-id="24682-125">Имя модели.</span><span class="sxs-lookup"><span data-stu-id="24682-125">Name of the model.</span></span>  
  
 <span data-ttu-id="24682-126">ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="24682-126">ATTRIBUTE_NAME</span></span>  
 <span data-ttu-id="24682-127">Имена атрибутов, соответствующих этому узлу.</span><span class="sxs-lookup"><span data-stu-id="24682-127">The names of the attributes that correspond to this node.</span></span>  
  
 <span data-ttu-id="24682-128">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="24682-128">NODE_NAME</span></span>  
 <span data-ttu-id="24682-129">Имя узла.</span><span class="sxs-lookup"><span data-stu-id="24682-129">The name of the node.</span></span> <span data-ttu-id="24682-130">Применительно к модели взаимосвязей этот столбец совпадает с NODE_UNIQUE_NAME.</span><span class="sxs-lookup"><span data-stu-id="24682-130">For an association model, this column contains the same value as NODE_UNIQUE_NAME.</span></span>  
  
 <span data-ttu-id="24682-131">NODE_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="24682-131">NODE_UNIQUE_NAME</span></span>  
 <span data-ttu-id="24682-132">Уникальное имя узла.</span><span class="sxs-lookup"><span data-stu-id="24682-132">The unique name of the node.</span></span>  
  
 <span data-ttu-id="24682-133">NODE_TYPE</span><span class="sxs-lookup"><span data-stu-id="24682-133">NODE_TYPE</span></span>  
 <span data-ttu-id="24682-134">Модель взаимосвязей выводит узлы только следующих типов.</span><span class="sxs-lookup"><span data-stu-id="24682-134">A association model outputs only the following node types:</span></span>  
  
|<span data-ttu-id="24682-135">Идентификатор типа узла</span><span class="sxs-lookup"><span data-stu-id="24682-135">Node Type ID</span></span>|<span data-ttu-id="24682-136">Type</span><span class="sxs-lookup"><span data-stu-id="24682-136">Type</span></span>|  
|------------------|----------|  
|<span data-ttu-id="24682-137">1 (модель)</span><span class="sxs-lookup"><span data-stu-id="24682-137">1 (Model)</span></span>|<span data-ttu-id="24682-138">Корневой или родительский узел.</span><span class="sxs-lookup"><span data-stu-id="24682-138">Root or parent node.</span></span>|  
|<span data-ttu-id="24682-139">7 (набор элементов)</span><span class="sxs-lookup"><span data-stu-id="24682-139">7 (Itemset)</span></span>|<span data-ttu-id="24682-140">Набор элементов или коллекция пар «атрибут-значение».</span><span class="sxs-lookup"><span data-stu-id="24682-140">An itemset, or collection of attribute-value pairs.</span></span> <span data-ttu-id="24682-141">Примеры:</span><span class="sxs-lookup"><span data-stu-id="24682-141">Examples:</span></span><br /><br /> `Product 1 = Existing, Product 2 = Existing`<br /><br /> <span data-ttu-id="24682-142">,</span><span class="sxs-lookup"><span data-stu-id="24682-142">or</span></span><br /><br /> <span data-ttu-id="24682-143">`Gender = Male`.</span><span class="sxs-lookup"><span data-stu-id="24682-143">`Gender = Male`.</span></span>|  
|<span data-ttu-id="24682-144">8 (правило)</span><span class="sxs-lookup"><span data-stu-id="24682-144">8 (Rule)</span></span>|<span data-ttu-id="24682-145">Правило, определяющее то, как связаны элементы друг с другом.</span><span class="sxs-lookup"><span data-stu-id="24682-145">A rule defining how items relate to each other.</span></span><br /><br /> <span data-ttu-id="24682-146">Пример.</span><span class="sxs-lookup"><span data-stu-id="24682-146">Example:</span></span><br /><br /> <span data-ttu-id="24682-147">`Product 1 = Existing, Product 2 = Existing -> Product 3 = Existing`.</span><span class="sxs-lookup"><span data-stu-id="24682-147">`Product 1 = Existing, Product 2 = Existing -> Product 3 = Existing`.</span></span>|  
  
 <span data-ttu-id="24682-148">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="24682-148">NODE_CAPTION</span></span>  
 <span data-ttu-id="24682-149">Метка или заголовок, связанный с узлом.</span><span class="sxs-lookup"><span data-stu-id="24682-149">A label or a caption associated with the node.</span></span>  
  
 <span data-ttu-id="24682-150">**Узел набора элементов** . Список элементов с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="24682-150">**Itemset node** A comma-separated list of items.</span></span>  
  
 <span data-ttu-id="24682-151">**Узел правила** . Содержит левую и правую части правила.</span><span class="sxs-lookup"><span data-stu-id="24682-151">**Rule node** Contains the left and right-hand sides of the rule.</span></span>  
  
 <span data-ttu-id="24682-152">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="24682-152">CHILDREN_CARDINALITY</span></span>  
 <span data-ttu-id="24682-153">Указывает количество дочерних узлов текущего узла.</span><span class="sxs-lookup"><span data-stu-id="24682-153">Indicates the number of children of the current node.</span></span>  
  
 <span data-ttu-id="24682-154">**Родительский узел** Указывает общее количество наборов элементов и правил.</span><span class="sxs-lookup"><span data-stu-id="24682-154">**Parent node** Indicates the total number of itemsets plus rules.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24682-155">Чтобы узнать, чему равно отдельно взятое количество наборов элементов и правил, можно просмотреть атрибут NODE_DESCRIPTION, относящийся к корневому узлу модели.</span><span class="sxs-lookup"><span data-stu-id="24682-155">To get a breakdown of the count for itemsets and rules, see the NODE_DESCRIPTION for the root node of the model.</span></span>  
  
 <span data-ttu-id="24682-156">**Узел правила или набора элементов** Всегда 0.</span><span class="sxs-lookup"><span data-stu-id="24682-156">**Itemset or rule node** Always 0.</span></span>  
  
 <span data-ttu-id="24682-157">PARENT_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="24682-157">PARENT_UNIQUE_NAME</span></span>  
 <span data-ttu-id="24682-158">Уникальное имя родителя узла.</span><span class="sxs-lookup"><span data-stu-id="24682-158">The unique name of the node's parent.</span></span>  
  
 <span data-ttu-id="24682-159">**Родительский узел** Всегда имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="24682-159">**Parent node** Always NULL.</span></span>  
  
 <span data-ttu-id="24682-160">**Узел правила или набора элементов** Всегда 0.</span><span class="sxs-lookup"><span data-stu-id="24682-160">**Itemset or rule node** Always 0.</span></span>  
  
 <span data-ttu-id="24682-161">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="24682-161">NODE_DESCRIPTION</span></span>  
 <span data-ttu-id="24682-162">Понятное описание содержимого узла.</span><span class="sxs-lookup"><span data-stu-id="24682-162">A user-friendly description of the contents of the node.</span></span>  
  
 <span data-ttu-id="24682-163">**Родительский узел** . Включает список с разделителями-запятыми, содержащий следующую информацию о модели:</span><span class="sxs-lookup"><span data-stu-id="24682-163">**Parent node** Includes a comma-separated list of the following information about the model:</span></span>  
  
|<span data-ttu-id="24682-164">Элемент</span><span class="sxs-lookup"><span data-stu-id="24682-164">Item</span></span>|<span data-ttu-id="24682-165">Описание</span><span class="sxs-lookup"><span data-stu-id="24682-165">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="24682-166">ITEMSET_COUNT</span><span class="sxs-lookup"><span data-stu-id="24682-166">ITEMSET_COUNT</span></span>|<span data-ttu-id="24682-167">Количество всех наборов элементов в модели.</span><span class="sxs-lookup"><span data-stu-id="24682-167">Count of all itemsets in model.</span></span>|  
|<span data-ttu-id="24682-168">RULE_COUNT</span><span class="sxs-lookup"><span data-stu-id="24682-168">RULE_COUNT</span></span>|<span data-ttu-id="24682-169">Количество всех правил в модели.</span><span class="sxs-lookup"><span data-stu-id="24682-169">Count of all rules in model.</span></span>|  
|<span data-ttu-id="24682-170">MIN_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="24682-170">MIN_SUPPORT</span></span>|<span data-ttu-id="24682-171">Минимальное несущее множество, обнаруженное для любого отдельно взятого набора элементов.</span><span class="sxs-lookup"><span data-stu-id="24682-171">The minimum support found for any single itemset.</span></span><br /><br /> <span data-ttu-id="24682-172">**Примечание.** Это значение может отличаться от значения, заданного для параметра *MINIMUM_SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="24682-172">**Note** This value might differ from the value that you set for the *MINIMUM _SUPPORT* parameter.</span></span>|  
|<span data-ttu-id="24682-173">MAX_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="24682-173">MAX_SUPPORT</span></span>|<span data-ttu-id="24682-174">Максимальное несущее множество, обнаруженное для любого отдельно взятого набора элементов.</span><span class="sxs-lookup"><span data-stu-id="24682-174">The maximum support found for any single itemset.</span></span><br /><br /> <span data-ttu-id="24682-175">**Примечание.** Это значение может отличаться от значения, заданного для параметра *MAXIMUM_SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="24682-175">**Note** This value might differ from the value that you set for the *MAXIMUM_SUPPORT* parameter.</span></span>|  
|<span data-ttu-id="24682-176">MIN_ITEMSET_SIZE</span><span class="sxs-lookup"><span data-stu-id="24682-176">MIN_ITEMSET_SIZE</span></span>|<span data-ttu-id="24682-177">Размер наименьшего набора элементов, выраженный количеством элементов.</span><span class="sxs-lookup"><span data-stu-id="24682-177">The size of the smallest itemset, represented as a count of items.</span></span><br /><br /> <span data-ttu-id="24682-178">Значение 0 указывает, что состояние `Missing` рассматривалось как независимый элемент.</span><span class="sxs-lookup"><span data-stu-id="24682-178">A value of 0 indicates that the `Missing` state was treated as an independent item.</span></span><br /><br /> <span data-ttu-id="24682-179">**Примечание.** По умолчанию параметр *MINIMUM_ITEMSET_SIZE* имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="24682-179">**Note** The default value of the *MINIMUM_ITEMSET_SIZE* parameter is 1.</span></span>|  
|<span data-ttu-id="24682-180">MAX_ITEMSET_SIZE</span><span class="sxs-lookup"><span data-stu-id="24682-180">MAX_ITEMSET_SIZE</span></span>|<span data-ttu-id="24682-181">Размер самого крупного найденного набора элементов.</span><span class="sxs-lookup"><span data-stu-id="24682-181">Indicates the size of the largest itemset that was found.</span></span><br /><br /> <span data-ttu-id="24682-182">**Примечание.** Это значение ограничивается значением, которое было установлено для параметра *MAX_ITEMSET_SIZE* при создании модели.</span><span class="sxs-lookup"><span data-stu-id="24682-182">**Note** This value is constrained by the value that you set for the *MAX_ITEMSET_SIZE* parameter when you created the model.</span></span> <span data-ttu-id="24682-183">Оно не может превысить это значение, но может быть меньше.</span><span class="sxs-lookup"><span data-stu-id="24682-183">This value can never exceed that value; however, it can be less.</span></span> <span data-ttu-id="24682-184">Значение по умолчанию равно 3.</span><span class="sxs-lookup"><span data-stu-id="24682-184">The default value is 3.</span></span>|  
|<span data-ttu-id="24682-185">MIN_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="24682-185">MIN_PROBABILITY</span></span>|<span data-ttu-id="24682-186">Минимальная вероятность, обнаруженная для любого отдельно взятого набора элементов или правила в модели.</span><span class="sxs-lookup"><span data-stu-id="24682-186">The minimum probability detected for any single itemset or rule in the model.</span></span><br /><br /> <span data-ttu-id="24682-187">Пример: 0,400390625</span><span class="sxs-lookup"><span data-stu-id="24682-187">Example: 0.400390625</span></span><br /><br /> <span data-ttu-id="24682-188">**Примечание.** Применительно к наборам элементов это значение всегда больше значения, установленного для параметра *MINIMUM_PROBABILITY* при создании модели.</span><span class="sxs-lookup"><span data-stu-id="24682-188">**Note** For itemsets, this value is always greater than the value that you set for the *MINIMUM_PROBABILITY* parameter when you created the model.</span></span>|  
|<span data-ttu-id="24682-189">MAX_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="24682-189">MAX_PROBABILITY</span></span>|<span data-ttu-id="24682-190">Максимальная вероятность, обнаруженная для любого отдельно взятого набора элементов или правила в модели.</span><span class="sxs-lookup"><span data-stu-id="24682-190">The maximum probability detected for any single itemset or rule in the model.</span></span><br /><br /> <span data-ttu-id="24682-191">Пример: 1</span><span class="sxs-lookup"><span data-stu-id="24682-191">Example: 1</span></span><br /><br /> <span data-ttu-id="24682-192">**Примечание.** Этот параметр не предназначен для ограничения максимальной вероятности наборов элементов.</span><span class="sxs-lookup"><span data-stu-id="24682-192">**Note** There is no parameter to constrain maximum probability of itemsets.</span></span> <span data-ttu-id="24682-193">Если требуется исключить элементы, которые встречаются слишком часто, используйте параметр *MAXIMUM_SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="24682-193">If you want to eliminate items that are too frequent, use the *MAXIMUM_SUPPORT* parameter instead.</span></span>|  
|<span data-ttu-id="24682-194">MIN_LIFT</span><span class="sxs-lookup"><span data-stu-id="24682-194">MIN_LIFT</span></span>|<span data-ttu-id="24682-195">Минимальная величина точности предсказания, предоставляемая моделью для любого набора элементов.</span><span class="sxs-lookup"><span data-stu-id="24682-195">The minimum amount of lift that is provided by the model for any itemset.</span></span><br /><br /> <span data-ttu-id="24682-196">Пример: 0,14309369632511</span><span class="sxs-lookup"><span data-stu-id="24682-196">Example: 0.14309369632511</span></span><br /><br /> <span data-ttu-id="24682-197">Примечание. Знание минимальной точности предсказания позволяет определить, является ли точность предсказания для любого отдельно взятого набора элементов значимой.</span><span class="sxs-lookup"><span data-stu-id="24682-197">Note: Knowing the minimum lift can help you determine whether the lift for any one itemset is significant.</span></span>|  
|<span data-ttu-id="24682-198">MAX_LIFT</span><span class="sxs-lookup"><span data-stu-id="24682-198">MAX_LIFT</span></span>|<span data-ttu-id="24682-199">Максимальная величина точности предсказания, предоставляемая моделью для любого набора элементов.</span><span class="sxs-lookup"><span data-stu-id="24682-199">The maximum amount of lift that is provided by the model for any itemset.</span></span><br /><br /> <span data-ttu-id="24682-200">Пример: 1,95758227647523 **Примечание.** Знание максимальной точности предсказания позволяет определить, является ли точность прогноза для любого отдельно взятого набора элементов значимой.</span><span class="sxs-lookup"><span data-stu-id="24682-200">Example: 1.95758227647523 **Note** Knowing the maximum lift can help you determine whether the lift for any one itemset is significant.</span></span>|  
  
 <span data-ttu-id="24682-201">**Узел набора элементов** . Узлы набора элементов содержат список элементов, отображаемый в виде текстовой строки с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="24682-201">**Itemset node** Itemset nodes contain a list of the items, displayed as a comma-separated text string.</span></span>  
  
 <span data-ttu-id="24682-202">Пример.</span><span class="sxs-lookup"><span data-stu-id="24682-202">Example:</span></span>  
  
 `Touring Tire = Existing, Water Bottle = Existing`  
  
 <span data-ttu-id="24682-203">Это означает, что шины для туристического велосипеда и фляги для воды были приобретены вместе.</span><span class="sxs-lookup"><span data-stu-id="24682-203">This means touring tires and water bottles were purchased together.</span></span>  
  
 <span data-ttu-id="24682-204">**Узел правила** . Узлы правила содержат левую и правую части правила, разделенные стрелкой.</span><span class="sxs-lookup"><span data-stu-id="24682-204">**Rule node** Rule nodes contains a left-hand and right-hand side of the rule, separated by an arrow.</span></span>  
  
 <span data-ttu-id="24682-205">Например, `Touring Tire = Existing, Water Bottle = Existing -> Cycling cap = Existing`.</span><span class="sxs-lookup"><span data-stu-id="24682-205">Example: `Touring Tire = Existing, Water Bottle = Existing -> Cycling cap = Existing`</span></span>  
  
 <span data-ttu-id="24682-206">Это означает, что если некто купил шину для туристического велосипеда и флягу для воды, то, скорее всего, он купит и велосипедную шапочку.</span><span class="sxs-lookup"><span data-stu-id="24682-206">This means that if someone bought a touring tire and a water bottle, they were also likely to buy a cycling cap.</span></span>  
  
 <span data-ttu-id="24682-207">NODE_RULE</span><span class="sxs-lookup"><span data-stu-id="24682-207">NODE_RULE</span></span>  
 <span data-ttu-id="24682-208">Фрагмент XML-кода, который описывает правило или набор элементов, внедренный в узел.</span><span class="sxs-lookup"><span data-stu-id="24682-208">An XML fragment that describes the rule or itemset that is embedded in the node.</span></span>  
  
 <span data-ttu-id="24682-209">**Родительский узел** Пусто.</span><span class="sxs-lookup"><span data-stu-id="24682-209">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="24682-210">**Узел набора элементов** Пусто.</span><span class="sxs-lookup"><span data-stu-id="24682-210">**Itemset node** Blank.</span></span>  
  
 <span data-ttu-id="24682-211">**Узел правила** . Фрагмент XML-кода, который включает дополнительную полезную информацию о правиле, такую как несущее множество, достоверность и количество элементов, а также идентификатор узла, который представляет левую часть правила.</span><span class="sxs-lookup"><span data-stu-id="24682-211">**Rule node** The XML fragment includes additional useful information about the rule, such as support, confidence, and the number of items, and the ID of the node that represents the left-hand side of the rule.</span></span>  
  
 <span data-ttu-id="24682-212">MARGINAL_RULE</span><span class="sxs-lookup"><span data-stu-id="24682-212">MARGINAL_RULE</span></span>  
 <span data-ttu-id="24682-213">Пусто.</span><span class="sxs-lookup"><span data-stu-id="24682-213">Blank.</span></span>  
  
 <span data-ttu-id="24682-214">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="24682-214">NODE_PROBABILITY</span></span>  
 <span data-ttu-id="24682-215">Вероятность или оценка достоверности, связанная с набором элементов или правилом.</span><span class="sxs-lookup"><span data-stu-id="24682-215">A probability or confidence score associated with the itemset or rule.</span></span>  
  
 <span data-ttu-id="24682-216">**Родительский узел** Всегда 0.</span><span class="sxs-lookup"><span data-stu-id="24682-216">**Parent node** Always 0.</span></span>  
  
 <span data-ttu-id="24682-217">**Узел набора элементов** Вероятность набора элементов.</span><span class="sxs-lookup"><span data-stu-id="24682-217">**Itemset node** Probability of the itemset.</span></span>  
  
 <span data-ttu-id="24682-218">**Узел правила** Показатель достоверности для правила.</span><span class="sxs-lookup"><span data-stu-id="24682-218">**Rule node** Confidence value for the rule.</span></span>  
  
 <span data-ttu-id="24682-219">MARGINAL_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="24682-219">MARGINAL_PROBABILITY</span></span>  
 <span data-ttu-id="24682-220">То же, что и NODE_PROBABILITY.</span><span class="sxs-lookup"><span data-stu-id="24682-220">Same as NODE_PROBABILITY.</span></span>  
  
 <span data-ttu-id="24682-221">NODE_DISTRIBUTION</span><span class="sxs-lookup"><span data-stu-id="24682-221">NODE_DISTRIBUTION</span></span>  
 <span data-ttu-id="24682-222">Таблица содержит данные, различающиеся в зависимости от того, является ли узел набором элементов или правилом.</span><span class="sxs-lookup"><span data-stu-id="24682-222">The table contains very different information, depending on whether the node is an itemset or a rule.</span></span>  
  
 <span data-ttu-id="24682-223">**Родительский узел** Пусто.</span><span class="sxs-lookup"><span data-stu-id="24682-223">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="24682-224">**Узел набора элементов** Содержит перечень всех элементов в наборе элементов наряду со значением вероятности и значением несущего множества.</span><span class="sxs-lookup"><span data-stu-id="24682-224">**Itemset node** Lists each item in the itemset together with a probability and support value.</span></span> <span data-ttu-id="24682-225">Например, если набор элементов включает два продукта, то в перечень входит название каждого продукта и количество вариантов, включающих продукт.</span><span class="sxs-lookup"><span data-stu-id="24682-225">For example, if the itemset contains two products, the name of each product is listed, together with the count of cases that include each product.</span></span>  
  
 <span data-ttu-id="24682-226">**Узел правила** Содержит две строки.</span><span class="sxs-lookup"><span data-stu-id="24682-226">**Rule node** Contains two rows.</span></span> <span data-ttu-id="24682-227">Первая строка показывает атрибут из правой части правила, представляющий собой прогнозируемый элемент, и оценку достоверности.</span><span class="sxs-lookup"><span data-stu-id="24682-227">The first row shows the attribute from the right-hand side of the rule, which is the predicted item, together with a confidence score.</span></span>  
  
 <span data-ttu-id="24682-228">Вторая строка является уникальной для моделей взаимосвязей; она содержит указатель на набор элементов в правой части правила.</span><span class="sxs-lookup"><span data-stu-id="24682-228">The second row is unique to association models; it contains a pointer to the itemset on the right-hand side of the rule.</span></span> <span data-ttu-id="24682-229">Этот указатель представлен в столбце ATTRIBUTE_VALUE как идентификатор набора элементов, который содержит только правый элемент.</span><span class="sxs-lookup"><span data-stu-id="24682-229">The pointer is represented in the ATTRIBUTE_VALUE column as the ID of the itemset that contains only the right-hand item.</span></span>  
  
 <span data-ttu-id="24682-230">Например, если правилом является `If {A,B} Then {C}`, то таблица содержит имя элемента `{C}`и идентификатор узла, содержащего набор элементов для элемента C.</span><span class="sxs-lookup"><span data-stu-id="24682-230">For example, if the rule is `If {A,B} Then {C}`, the table contains the name of the item `{C}`, and the ID of the node that contains the itemset for item C.</span></span>  
  
 <span data-ttu-id="24682-231">Этот указатель является полезным, поскольку позволяет определить на основе узла набора элементов, сколько всего вариантов включают продукт из правой части.</span><span class="sxs-lookup"><span data-stu-id="24682-231">This pointer is useful because you can determine from the itemset node how many cases in all include the right-hand side product.</span></span> <span data-ttu-id="24682-232">Варианты, подчиняющиеся правилу `If {A,B} Then {C}` , представляют собой подмножество вариантов, перечисленных в наборе элементов для `{C}`.</span><span class="sxs-lookup"><span data-stu-id="24682-232">The cases that are subject to the rule `If {A,B} Then {C}` are a subset of the cases listed in the itemset for `{C}`.</span></span>  
  
 <span data-ttu-id="24682-233">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="24682-233">NODE_SUPPORT</span></span>  
 <span data-ttu-id="24682-234">Число вариантов, поддерживаемое этим узлом.</span><span class="sxs-lookup"><span data-stu-id="24682-234">The number of cases that support this node.</span></span>  
  
 <span data-ttu-id="24682-235">**Родительский узел** Количество вариантов в модели.</span><span class="sxs-lookup"><span data-stu-id="24682-235">**Parent node** Number of cases in the model.</span></span>  
  
 <span data-ttu-id="24682-236">**Узел набора элементов** Количество вариантов, которые содержат все элементы из набора элементов.</span><span class="sxs-lookup"><span data-stu-id="24682-236">**Itemset node** Number of cases that contains all items in the itemset.</span></span>  
  
 <span data-ttu-id="24682-237">**Узел правила** Количество вариантов, которые содержат все элементы, включенные в правило.</span><span class="sxs-lookup"><span data-stu-id="24682-237">**Rule node** The number of cases that contain all items included in the rule.</span></span>  
  
 <span data-ttu-id="24682-238">MSOLAP_MODEL_COLUMN</span><span class="sxs-lookup"><span data-stu-id="24682-238">MSOLAP_MODEL_COLUMN</span></span>  
 <span data-ttu-id="24682-239">Содержит различную информацию, зависящую от того, является ли узел набором элементов или правилом.</span><span class="sxs-lookup"><span data-stu-id="24682-239">Contains different information depending on whether the node is an itemset or rule.</span></span>  
  
 <span data-ttu-id="24682-240">**Родительский узел** Пусто.</span><span class="sxs-lookup"><span data-stu-id="24682-240">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="24682-241">**Узел набора элементов** Пусто.</span><span class="sxs-lookup"><span data-stu-id="24682-241">**Itemset node** Blank.</span></span>  
  
 <span data-ttu-id="24682-242">**Узел правила** . Идентификатор набора элементов, который содержит элементы из левой части правила.</span><span class="sxs-lookup"><span data-stu-id="24682-242">**Rule node** The ID of the itemset that contains the items in the left-hand side of the rule.</span></span> <span data-ttu-id="24682-243">Например, если правилом является `If {A,B} Then {C}`, то данный столбец содержит идентификатор набора элементов, содержащего только `{A,B}`.</span><span class="sxs-lookup"><span data-stu-id="24682-243">For example, if the rule is `If {A,B} Then {C}`, this column contains the ID of the itemset that contains only `{A,B}`.</span></span>  
  
 <span data-ttu-id="24682-244">MSOLAP_NODE_SCORE</span><span class="sxs-lookup"><span data-stu-id="24682-244">MSOLAP_NODE_SCORE</span></span>  
 <span data-ttu-id="24682-245">**Родительский узел** Пусто.</span><span class="sxs-lookup"><span data-stu-id="24682-245">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="24682-246">**Узел набора элементов** Оценка важности для набора элементов.</span><span class="sxs-lookup"><span data-stu-id="24682-246">**Itemset node** Importance score for the itemset.</span></span>  
  
 <span data-ttu-id="24682-247">**Узел правила** Оценка важности для правила.</span><span class="sxs-lookup"><span data-stu-id="24682-247">**Rule node** Importance score for the rule.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24682-248">Важность рассчитывается по-разному для наборов элементов и правил.</span><span class="sxs-lookup"><span data-stu-id="24682-248">Importance is calculated differently for itemsets and rules.</span></span> <span data-ttu-id="24682-249">Дополнительные сведения см. в разделе [Технический справочник по алгоритму взаимосвязей (Майкрософт)](microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="24682-249">For more information, see [Microsoft Association Algorithm Technical Reference](microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="24682-250">MSOLAP_NODE_SHORT_CAPTION</span><span class="sxs-lookup"><span data-stu-id="24682-250">MSOLAP_NODE_SHORT_CAPTION</span></span>  
 <span data-ttu-id="24682-251">Пусто.</span><span class="sxs-lookup"><span data-stu-id="24682-251">Blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24682-252">См. также:</span><span class="sxs-lookup"><span data-stu-id="24682-252">See Also</span></span>  
 <span data-ttu-id="24682-253">[&#40;содержимого моделей интеллектуального анализа данных Analysis Services — интеллектуальный анализ&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="24682-253">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="24682-254">[Алгоритм взаимосвязей (Майкрософт)](microsoft-association-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="24682-254">[Microsoft Association Algorithm](microsoft-association-algorithm.md) </span></span>  
 [<span data-ttu-id="24682-255">Примеры запросов моделей взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="24682-255">Association Model Query Examples</span></span>](association-model-query-examples.md)  
  
  
