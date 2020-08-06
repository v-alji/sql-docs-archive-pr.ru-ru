---
title: Примеры запросов модели линейной регрессии | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- linear regression algorithms [Analysis Services]
- linear regression [Analysis Services]
- content queries [DMX]
ms.assetid: fd3cf312-57a1-44b6-b772-fce6fc1c26d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 02d4b7309d7b5ea3d6295089f0fb2e778b1c9b4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668527"
---
# <a name="linear-regression-model-query-examples"></a><span data-ttu-id="4a05e-102">Примеры запросов модели линейной регрессии</span><span class="sxs-lookup"><span data-stu-id="4a05e-102">Linear Regression Model Query Examples</span></span>
  <span data-ttu-id="4a05e-103">К модели интеллектуального анализа данных можно создать два вида запросов: запросы содержимого, возвращающие подробные сведения о закономерностях, обнаруженных при анализе, и прогнозирующие запросы, использующие закономерности, содержащиеся в модели, для прогнозирования новых данных.</span><span class="sxs-lookup"><span data-stu-id="4a05e-103">When you create a query against a data mining model, you can create a content query, which provides details about the patterns discovered in analysis, or you can create a prediction query, which uses the patterns in the model to make predictions for new data.</span></span> <span data-ttu-id="4a05e-104">Например, запрос содержимого предоставит дополнительные сведения о формуле регрессии, а прогнозирующий запрос определит, подходит ли к модели новая точка данных.</span><span class="sxs-lookup"><span data-stu-id="4a05e-104">For example, a content query might provide additional details about the regression formula, while a prediction query might tell you if a new data point fits the model.</span></span> <span data-ttu-id="4a05e-105">Запрос также позволяет получить метаданные, описывающие модель.</span><span class="sxs-lookup"><span data-stu-id="4a05e-105">You can also retrieve metadata about the model by using a query.</span></span>  
  
 <span data-ttu-id="4a05e-106">В этом разделе описывается процесс создания запросов к моделям, основанным на алгоритме линейной регрессии (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="4a05e-106">This section explains how to create queries for models that are based on the Microsoft Linear Regression algorithm.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a05e-107">Поскольку линейная регрессия основана на частном случае алгоритма дерева принятия решений (Майкрософт), у них много общего, и некоторые модели деревьев решений с непрерывными прогнозируемыми атрибутами могут содержать формулы регрессии.</span><span class="sxs-lookup"><span data-stu-id="4a05e-107">Because linear regression is based on a special case of the Microsoft Decision Trees algorithm, there are many similarities, and some decision tree models that use continuous predictable attributes can contain regression formulas.</span></span> <span data-ttu-id="4a05e-108">Дополнительные сведения см. в разделе [Технический справочник по алгоритму дерева принятия решений (Майкрософт)](microsoft-decision-trees-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4a05e-108">For more information, see [Microsoft Decision Trees Algorithm Technical Reference](microsoft-decision-trees-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="4a05e-109">**Запросы содержимого**</span><span class="sxs-lookup"><span data-stu-id="4a05e-109">**Content queries**</span></span>  
  
 [<span data-ttu-id="4a05e-110">Определение параметров, использованных в модели, с помощью набора строк схемы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="4a05e-110">Using the Data Mining Schema Rowset to determine parameters used for a model</span></span>](#bkmk_Query1)  
  
 [<span data-ttu-id="4a05e-111">Получение формулы регрессии модели с помощью расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="4a05e-111">Using DMX to return the regression formula for the model</span></span>](#bkmk_Query2)  
  
 [<span data-ttu-id="4a05e-112">Возвращение только коэффициента для данной модели</span><span class="sxs-lookup"><span data-stu-id="4a05e-112">Returning only the coefficient for the model</span></span>](#bkmk_Query3)  
  
 <span data-ttu-id="4a05e-113">**Прогнозирующие запросы**</span><span class="sxs-lookup"><span data-stu-id="4a05e-113">**Prediction queries**</span></span>  
  
 [<span data-ttu-id="4a05e-114">Прогнозирование дохода с помощью одноэлементного запроса</span><span class="sxs-lookup"><span data-stu-id="4a05e-114">Predicting income using a singleton query</span></span>](#bkmk_Query4)  
  
 [<span data-ttu-id="4a05e-115">Использование прогнозирующих функций в модели регрессии</span><span class="sxs-lookup"><span data-stu-id="4a05e-115">Using prediction functions with a regression model</span></span>](#bkmk_Query5)  
  
##  <a name="finding-information-about-the-linear-regression-model"></a><a name="bkmk_top"></a> <span data-ttu-id="4a05e-116">Получение сведений о модели линейной регрессии</span><span class="sxs-lookup"><span data-stu-id="4a05e-116">Finding Information about the Linear Regression Model</span></span>  
 <span data-ttu-id="4a05e-117">Структура модели линейной регрессии чрезвычайно проста: модель интеллектуального анализа данных представляет данные в виде одного узла, определяющего формулу регрессии.</span><span class="sxs-lookup"><span data-stu-id="4a05e-117">The structure of a linear regression model is extremely simple: the mining model represents the data as a single node, which defines the regression formula.</span></span> <span data-ttu-id="4a05e-118">Дополнительные сведения см. в разделе [Содержимое моделей интеллектуального анализа данных для моделей логистической регрессии (службы Analysis Services — интеллектуальный анализ данных)](mining-model-content-for-logistic-regression-models.md).</span><span class="sxs-lookup"><span data-stu-id="4a05e-118">For more information, see [Mining Model Content for Logistic Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-logistic-regression-models.md).</span></span>  
  
 [<span data-ttu-id="4a05e-119">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="4a05e-119">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-1-using-the-data-mining-schema-rowset-to-determine-parameters-used-for-a-model"></a><a name="bkmk_Query1"></a> <span data-ttu-id="4a05e-120">Пример запроса 1. Определение параметров, использованных в модели, с помощью набора строк схемы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="4a05e-120">Sample Query 1: Using the Data Mining Schema Rowset to Determine Parameters Used for a Model</span></span>  
 <span data-ttu-id="4a05e-121">Используя запросы к набору строк схемы интеллектуального анализа данных, можно получать метаданные модели.</span><span class="sxs-lookup"><span data-stu-id="4a05e-121">By querying the data mining schema rowset, you can find metadata about the model.</span></span> <span data-ttu-id="4a05e-122">Они включают в себя, например, время создания модели, время ее последней обработки, имя структуры интеллектуального анализа данных, на которой основана данная модель, и имя столбца, назначенного в качестве прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="4a05e-122">This might include when the model was created, when the model was last processed, the name of the mining structure that the model is based on, and the name of the column designated as the predictable attribute.</span></span> <span data-ttu-id="4a05e-123">Также можно возвратить параметры, которые были использованы при первичном создании модели.</span><span class="sxs-lookup"><span data-stu-id="4a05e-123">You can also return the parameters that were used when the model was first created.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM_PredictIncome'  
```  
  
 <span data-ttu-id="4a05e-124">Образец результатов.</span><span class="sxs-lookup"><span data-stu-id="4a05e-124">Sample results:</span></span>  
  
|<span data-ttu-id="4a05e-125">MINING_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4a05e-125">MINING_PARAMETERS</span></span>|  
|------------------------|  
|<span data-ttu-id="4a05e-126">COMPLEXITY_PENALTY=0.9,</span><span class="sxs-lookup"><span data-stu-id="4a05e-126">COMPLEXITY_PENALTY=0.9,</span></span><br /><br /> <span data-ttu-id="4a05e-127">MAXIMUM_INPUT_ATTRIBUTES=255,</span><span class="sxs-lookup"><span data-stu-id="4a05e-127">MAXIMUM_INPUT_ATTRIBUTES=255,</span></span><br /><br /> <span data-ttu-id="4a05e-128">MAXIMUM_OUTPUT_ATTRIBUTES=255,</span><span class="sxs-lookup"><span data-stu-id="4a05e-128">MAXIMUM_OUTPUT_ATTRIBUTES=255,</span></span><br /><br /> <span data-ttu-id="4a05e-129">MINIMUM_SUPPORT=10,</span><span class="sxs-lookup"><span data-stu-id="4a05e-129">MINIMUM_SUPPORT=10,</span></span><br /><br /> <span data-ttu-id="4a05e-130">SCORE_METHOD=4,</span><span class="sxs-lookup"><span data-stu-id="4a05e-130">SCORE_METHOD=4,</span></span><br /><br /> <span data-ttu-id="4a05e-131">SPLIT_METHOD=3,</span><span class="sxs-lookup"><span data-stu-id="4a05e-131">SPLIT_METHOD=3,</span></span><br /><br /> <span data-ttu-id="4a05e-132">FORCE_REGRESSOR=</span><span class="sxs-lookup"><span data-stu-id="4a05e-132">FORCE_REGRESSOR=</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="4a05e-133">Значение параметра, "`FORCE_REGRESSOR =` ", указывает, что текущее значение параметра FORCE_REGRESSOR равно NULL.</span><span class="sxs-lookup"><span data-stu-id="4a05e-133">The parameter setting, "`FORCE_REGRESSOR =` ", indicates that the current value for the FORCE_REGRESSOR parameter is null.</span></span>  
  
 [<span data-ttu-id="4a05e-134">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="4a05e-134">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-2-retrieving-the-regression-formula-for-the-model"></a><a name="bkmk_Query2"></a> <span data-ttu-id="4a05e-135">Пример запроса 2. Получение формулы регрессии модели</span><span class="sxs-lookup"><span data-stu-id="4a05e-135">Sample Query 2: Retrieving the Regression Formula for the Model</span></span>  
 <span data-ttu-id="4a05e-136">Следующий запрос возвращает содержимое модели интеллектуального анализа данных с линейной регрессией, построенной для того же источника данных «Целевая рассылка», который использовался в пособии [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="4a05e-136">The following query returns the mining model content for a linear regression model that was built by using the same Targeted Mailing data source that was used in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="4a05e-137">Эта модель предсказывает доход клиента на основании возраста.</span><span class="sxs-lookup"><span data-stu-id="4a05e-137">This model predicts customer income based on age.</span></span>  
  
 <span data-ttu-id="4a05e-138">Запрос возвращает содержимое узла модели интеллектуального анализа данных, содержащего формулу регрессии.</span><span class="sxs-lookup"><span data-stu-id="4a05e-138">The query returns the contents of the node that contains the regression formula.</span></span> <span data-ttu-id="4a05e-139">Каждая переменная и коэффициент хранятся в отдельной строке вложенной таблицы NODE_DISTRIBUTION.</span><span class="sxs-lookup"><span data-stu-id="4a05e-139">Each variable and coefficient is stored in a separate row of the nested NODE_DISTRIBUTION table.</span></span> <span data-ttu-id="4a05e-140">Если требуется просмотреть полную формулу регрессии, используйте [средство просмотра деревьев (Майкрософт](browse-a-model-using-the-microsoft-tree-viewer.md)), щелкните узел **(все)** и откройте **Условные обозначения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="4a05e-140">If you want to view the complete regression formula, use the [Microsoft Tree Viewer](browse-a-model-using-the-microsoft-tree-viewer.md), click the **(All)** node, and open the **Mining Legend**.</span></span>  
  
```  
SELECT FLATTENED NODE_DISTRIBUTION as t  
FROM LR_PredictIncome.CONTENT  
```  
  
> [!NOTE]  
>  <span data-ttu-id="4a05e-141">При ссылках на отдельные столбцы вложенной таблицы в таких запросах, как `SELECT <column name> from NODE_DISTRIBUTION`, некоторые столбцы, например **SUPPORT** или **PROBABILITY**, нужно заключать в квадратные скобки, чтобы отличать их от одноименных зарезервированных ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="4a05e-141">If you reference individual columns of the nested table by using a query such as `SELECT <column name> from NODE_DISTRIBUTION`, some columns, such as **SUPPORT** or **PROBABILITY**, must be enclosed in brackets to distinguish them from reserved keywords of the same name.</span></span>  
  
 <span data-ttu-id="4a05e-142">Ожидаемый результат:</span><span class="sxs-lookup"><span data-stu-id="4a05e-142">Expected results:</span></span>  
  
|<span data-ttu-id="4a05e-143">T.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a05e-143">t.ATTRIBUTE_NAME</span></span>|<span data-ttu-id="4a05e-144">t.ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="4a05e-144">t.ATTRIBUTE_VALUE</span></span>|<span data-ttu-id="4a05e-145">t.SUPPORT</span><span class="sxs-lookup"><span data-stu-id="4a05e-145">t.SUPPORT</span></span>|<span data-ttu-id="4a05e-146">t.PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="4a05e-146">t.PROBABILITY</span></span>|<span data-ttu-id="4a05e-147">t.VARIANCE</span><span class="sxs-lookup"><span data-stu-id="4a05e-147">t.VARIANCE</span></span>|<span data-ttu-id="4a05e-148">t.VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="4a05e-148">t.VALUETYPE</span></span>|  
|-----------------------|------------------------|---------------|-------------------|----------------|-----------------|  
|<span data-ttu-id="4a05e-149">Годовой доход</span><span class="sxs-lookup"><span data-stu-id="4a05e-149">Yearly Income</span></span>|<span data-ttu-id="4a05e-150">Missing</span><span class="sxs-lookup"><span data-stu-id="4a05e-150">Missing</span></span>|<span data-ttu-id="4a05e-151">0</span><span class="sxs-lookup"><span data-stu-id="4a05e-151">0</span></span>|<span data-ttu-id="4a05e-152">0,000457142857142857</span><span class="sxs-lookup"><span data-stu-id="4a05e-152">0.000457142857142857</span></span>|<span data-ttu-id="4a05e-153">0</span><span class="sxs-lookup"><span data-stu-id="4a05e-153">0</span></span>|<span data-ttu-id="4a05e-154">1</span><span class="sxs-lookup"><span data-stu-id="4a05e-154">1</span></span>|  
|<span data-ttu-id="4a05e-155">Годовой доход</span><span class="sxs-lookup"><span data-stu-id="4a05e-155">Yearly Income</span></span>|<span data-ttu-id="4a05e-156">57220,8876687257</span><span class="sxs-lookup"><span data-stu-id="4a05e-156">57220.8876687257</span></span>|<span data-ttu-id="4a05e-157">17484</span><span class="sxs-lookup"><span data-stu-id="4a05e-157">17484</span></span>|<span data-ttu-id="4a05e-158">0,999542857142857</span><span class="sxs-lookup"><span data-stu-id="4a05e-158">0.999542857142857</span></span>|<span data-ttu-id="4a05e-159">1041275619,52776</span><span class="sxs-lookup"><span data-stu-id="4a05e-159">1041275619.52776</span></span>|<span data-ttu-id="4a05e-160">3</span><span class="sxs-lookup"><span data-stu-id="4a05e-160">3</span></span>|  
|<span data-ttu-id="4a05e-161">Возраст</span><span class="sxs-lookup"><span data-stu-id="4a05e-161">Age</span></span>|<span data-ttu-id="4a05e-162">471,687717702463</span><span class="sxs-lookup"><span data-stu-id="4a05e-162">471.687717702463</span></span>|<span data-ttu-id="4a05e-163">0</span><span class="sxs-lookup"><span data-stu-id="4a05e-163">0</span></span>|<span data-ttu-id="4a05e-164">0</span><span class="sxs-lookup"><span data-stu-id="4a05e-164">0</span></span>|<span data-ttu-id="4a05e-165">126.969442359327</span><span class="sxs-lookup"><span data-stu-id="4a05e-165">126.969442359327</span></span>|<span data-ttu-id="4a05e-166">7</span><span class="sxs-lookup"><span data-stu-id="4a05e-166">7</span></span>|  
|<span data-ttu-id="4a05e-167">Возраст</span><span class="sxs-lookup"><span data-stu-id="4a05e-167">Age</span></span>|<span data-ttu-id="4a05e-168">234,680904692439</span><span class="sxs-lookup"><span data-stu-id="4a05e-168">234.680904692439</span></span>|<span data-ttu-id="4a05e-169">0</span><span class="sxs-lookup"><span data-stu-id="4a05e-169">0</span></span>|<span data-ttu-id="4a05e-170">0</span><span class="sxs-lookup"><span data-stu-id="4a05e-170">0</span></span>|<span data-ttu-id="4a05e-171">0</span><span class="sxs-lookup"><span data-stu-id="4a05e-171">0</span></span>|<span data-ttu-id="4a05e-172">8</span><span class="sxs-lookup"><span data-stu-id="4a05e-172">8</span></span>|  
|<span data-ttu-id="4a05e-173">Возраст</span><span class="sxs-lookup"><span data-stu-id="4a05e-173">Age</span></span>|<span data-ttu-id="4a05e-174">45,4269617936399</span><span class="sxs-lookup"><span data-stu-id="4a05e-174">45.4269617936399</span></span>|<span data-ttu-id="4a05e-175">0</span><span class="sxs-lookup"><span data-stu-id="4a05e-175">0</span></span>|<span data-ttu-id="4a05e-176">0</span><span class="sxs-lookup"><span data-stu-id="4a05e-176">0</span></span>|<span data-ttu-id="4a05e-177">126.969442359327</span><span class="sxs-lookup"><span data-stu-id="4a05e-177">126.969442359327</span></span>|<span data-ttu-id="4a05e-178">9</span><span class="sxs-lookup"><span data-stu-id="4a05e-178">9</span></span>|  
||<span data-ttu-id="4a05e-179">35793,5477381267</span><span class="sxs-lookup"><span data-stu-id="4a05e-179">35793.5477381267</span></span>|<span data-ttu-id="4a05e-180">0</span><span class="sxs-lookup"><span data-stu-id="4a05e-180">0</span></span>|<span data-ttu-id="4a05e-181">0</span><span class="sxs-lookup"><span data-stu-id="4a05e-181">0</span></span>|<span data-ttu-id="4a05e-182">1012968919,28372</span><span class="sxs-lookup"><span data-stu-id="4a05e-182">1012968919.28372</span></span>|<span data-ttu-id="4a05e-183">11</span><span class="sxs-lookup"><span data-stu-id="4a05e-183">11</span></span>|  
  
 <span data-ttu-id="4a05e-184">Для сравнения, в окне **Условные обозначения интеллектуального анализа данных**формула регрессии показана в следующем виде:</span><span class="sxs-lookup"><span data-stu-id="4a05e-184">In comparison, in the **Mining Legend**, the regression formula appears as follows:</span></span>  
  
 <span data-ttu-id="4a05e-185">Yearly Income = 57 220,919 + 471,688 \* (Age - 45,427)</span><span class="sxs-lookup"><span data-stu-id="4a05e-185">Yearly Income = 57,220.919 + 471.688 \* (Age - 45.427)</span></span>  
  
 <span data-ttu-id="4a05e-186">Можно видеть, что в окне **Условные обозначения интеллектуального анализа данных**некоторые числа округлены; однако по существу таблица NODE_DISTRIBUTION и окно **Условные обозначения интеллектуального анализа данных** содержат одни и те же значения.</span><span class="sxs-lookup"><span data-stu-id="4a05e-186">You can see that in the **Mining Legend**, some numbers are rounded; however, the NODE_DISTRIBUTION table and the **Mining Legend** essentially contain the same values.</span></span>  
  
 <span data-ttu-id="4a05e-187">Значения в столбце VALUETYPE сообщают, какая информация содержится в каждой строке. Это полезно при программной обработке результатов.</span><span class="sxs-lookup"><span data-stu-id="4a05e-187">The values in the VALUETYPE column tell you what kind of information is contained in each row, which is useful if you are processing the results programmatically.</span></span> <span data-ttu-id="4a05e-188">В следующей таблице показаны типы значений, которые являются выводом формулы линейной регрессии.</span><span class="sxs-lookup"><span data-stu-id="4a05e-188">The following table shows the value types that are output for a linear regression formula.</span></span>  
  
|<span data-ttu-id="4a05e-189">VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="4a05e-189">VALUETYPE</span></span>|  
|---------------|  
|<span data-ttu-id="4a05e-190">1 (отсутствует)</span><span class="sxs-lookup"><span data-stu-id="4a05e-190">1 (Missing)</span></span>|  
|<span data-ttu-id="4a05e-191">3 (непрерывный)</span><span class="sxs-lookup"><span data-stu-id="4a05e-191">3 (Continuous)</span></span>|  
|<span data-ttu-id="4a05e-192">7 (коэффициент)</span><span class="sxs-lookup"><span data-stu-id="4a05e-192">7 (Coefficient)</span></span>|  
|<span data-ttu-id="4a05e-193">8 (рост оценки)</span><span class="sxs-lookup"><span data-stu-id="4a05e-193">8 (Score Gain)</span></span>|  
|<span data-ttu-id="4a05e-194">9 (статистика)</span><span class="sxs-lookup"><span data-stu-id="4a05e-194">9 (Statistics)</span></span>|  
|<span data-ttu-id="4a05e-195">7 (коэффициент)</span><span class="sxs-lookup"><span data-stu-id="4a05e-195">7 (Coefficient)</span></span>|  
|<span data-ttu-id="4a05e-196">8 (рост оценки)</span><span class="sxs-lookup"><span data-stu-id="4a05e-196">8 (Score Gain)</span></span>|  
|<span data-ttu-id="4a05e-197">9 (статистика)</span><span class="sxs-lookup"><span data-stu-id="4a05e-197">9 (Statistics)</span></span>|  
|<span data-ttu-id="4a05e-198">11 (отсекаемый отрезок)</span><span class="sxs-lookup"><span data-stu-id="4a05e-198">11 (Intercept)</span></span>|  
  
 <span data-ttu-id="4a05e-199">Дополнительные сведения о назначении каждого из типов значений в моделях регрессии см. в разделе [Содержимое моделей интеллектуального анализа данных для моделей линейной регрессии (службы Analysis Services — интеллектуальный анализ данных)](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4a05e-199">For more information about the meaning of each value type for regression models, see [Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span></span>  
  
 [<span data-ttu-id="4a05e-200">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="4a05e-200">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-3-returning-only-the-coefficient-for-the-model"></a><a name="bkmk_Query3"></a> <span data-ttu-id="4a05e-201">Пример запроса 3. Возвращение только коэффициента для модели</span><span class="sxs-lookup"><span data-stu-id="4a05e-201">Sample Query 3: Returning Only the Coefficient for the Model</span></span>  
 <span data-ttu-id="4a05e-202">Используя перечисление VALUETYPE, можно вернуть только коэффициент уравнения регрессии, как показано в следующем запросе:</span><span class="sxs-lookup"><span data-stu-id="4a05e-202">By using the VALUETYPE enumeration, you can return only the coefficient for the regression equation, as shown in the following query:</span></span>  
  
```  
SELECT FLATTENED MODEL_NAME,  
    (SELECT ATTRIBUTE_VALUE, VALUETYPE  
     FROM NODE_DISTRIBUTION  
     WHERE VALUETYPE = 11)   
AS t  
FROM LR_PredictIncome.CONTENT  
```  
  
 <span data-ttu-id="4a05e-203">Этот запрос возвращает две строки — одну из содержимого модели интеллектуального анализа данных и одну из вложенной таблицы, с коэффициентом.</span><span class="sxs-lookup"><span data-stu-id="4a05e-203">This query returns two rows, one from the mining model content, and the row from the nested table that contains the coefficient.</span></span> <span data-ttu-id="4a05e-204">Столбец ATTRIBUTE_NAME сюда не включается, потому что для коэффициента он всегда пустой.</span><span class="sxs-lookup"><span data-stu-id="4a05e-204">The ATTRIBUTE_NAME column is not included here because it is always blank for the coefficient.</span></span>  
  
|<span data-ttu-id="4a05e-205">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="4a05e-205">MODEL_NAME</span></span>|<span data-ttu-id="4a05e-206">t.ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="4a05e-206">t.ATTRIBUTE_VALUE</span></span>|<span data-ttu-id="4a05e-207">t.VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="4a05e-207">t.VALUETYPE</span></span>|  
|-----------------|------------------------|-----------------|  
|<span data-ttu-id="4a05e-208">LR_PredictIncome</span><span class="sxs-lookup"><span data-stu-id="4a05e-208">LR_PredictIncome</span></span>|||  
|<span data-ttu-id="4a05e-209">LR_PredictIncome</span><span class="sxs-lookup"><span data-stu-id="4a05e-209">LR_PredictIncome</span></span>|<span data-ttu-id="4a05e-210">35793,5477381267</span><span class="sxs-lookup"><span data-stu-id="4a05e-210">35793.5477381267</span></span>|<span data-ttu-id="4a05e-211">11</span><span class="sxs-lookup"><span data-stu-id="4a05e-211">11</span></span>|  
  
 [<span data-ttu-id="4a05e-212">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="4a05e-212">Return to Top</span></span>](#bkmk_top)  
  
## <a name="making-predictions-from-a-linear-regression-model"></a><span data-ttu-id="4a05e-213">Прогнозирование по модели линейной регрессии</span><span class="sxs-lookup"><span data-stu-id="4a05e-213">Making Predictions from a Linear Regression Model</span></span>  
 <span data-ttu-id="4a05e-214">Прогнозирующие запросы к модели линейной регрессии можно строить с помощью вкладки «Прогнозирование моделей интеллектуального анализа данных» конструктора интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4a05e-214">You can build prediction queries on linear regression models by using the Mining Model Prediction tab in Data Mining Designer.</span></span> <span data-ttu-id="4a05e-215">Построитель прогнозирующих запросов доступен как в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , так и в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a05e-215">The prediction query builder is available in both [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a05e-216">Можно также создавать запросы к моделям регрессии с помощью надстроек интеллектуального анализа данных [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] для Excel или [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] для Excel.</span><span class="sxs-lookup"><span data-stu-id="4a05e-216">You can also create queries on regression models by using the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Data Mining Add-ins for Excel or the [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] Data Mining Add-ins for Excel.</span></span> <span data-ttu-id="4a05e-217">Надстройки интеллектуального анализа данных для Excel не создают моделей регрессии, но позволяют просматривать любые модели интеллектуального анализа данных, хранящиеся в экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], и создавать запросы к ним.</span><span class="sxs-lookup"><span data-stu-id="4a05e-217">Even though the Data Mining Add-ins for Excel do not create regression models, you can browse and query any mining model that is stored on an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="4a05e-218">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="4a05e-218">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-4-predicting-income-using-a-singleton-query"></a><a name="bkmk_Query4"></a> <span data-ttu-id="4a05e-219">Пример запроса 4. Прогнозирование дохода с помощью одноэлементного запроса</span><span class="sxs-lookup"><span data-stu-id="4a05e-219">Sample Query 4: Predicting Income using a Singleton Query</span></span>  
 <span data-ttu-id="4a05e-220">Проще всего создать отдельный запрос к модели регрессии с помощью диалогового окна **Ввод одноэлементного запроса** .</span><span class="sxs-lookup"><span data-stu-id="4a05e-220">The easiest way to create a single query on a regression model is by using the **Singleton Query Input** dialog box.</span></span> <span data-ttu-id="4a05e-221">Например, можно создать следующий DMX-запрос, выбрав соответствующую модель регрессии, выбрав **одноэлементный запрос**, а затем введя в `20` качестве значения **Age**.</span><span class="sxs-lookup"><span data-stu-id="4a05e-221">For example, you can build the following DMX query by selecting the appropriate regression model, choosing **Singleton Query**, and then typing `20` as the value for **Age**.</span></span>  
  
```  
SELECT [LR_PredictIncome].[Yearly Income]  
From   [LR_PredictIncome]  
NATURAL PREDICTION JOIN  
(SELECT 20 AS [Age]) AS t  
```  
  
 <span data-ttu-id="4a05e-222">Образец результатов.</span><span class="sxs-lookup"><span data-stu-id="4a05e-222">Sample results:</span></span>  
  
|<span data-ttu-id="4a05e-223">Годовой доход</span><span class="sxs-lookup"><span data-stu-id="4a05e-223">Yearly Income</span></span>|  
|-------------------|  
|<span data-ttu-id="4a05e-224">45227,302092176</span><span class="sxs-lookup"><span data-stu-id="4a05e-224">45227.302092176</span></span>|  
  
 [<span data-ttu-id="4a05e-225">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="4a05e-225">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-5-using-prediction-functions-with-a-regression-model"></a><a name="bkmk_Query5"></a> <span data-ttu-id="4a05e-226">Пример запроса 5. Использование прогнозирующих функций в модели регрессии</span><span class="sxs-lookup"><span data-stu-id="4a05e-226">Sample Query 5: Using Prediction Functions with a Regression Model</span></span>  
 <span data-ttu-id="4a05e-227">В моделях линейной регрессии можно использовать многие стандартные прогнозирующие функции.</span><span class="sxs-lookup"><span data-stu-id="4a05e-227">You can use many of the standard prediction functions with linear regression models.</span></span> <span data-ttu-id="4a05e-228">Далее приводится пример добавления некоторых описательных статистических показателей к результатам прогнозирующего запроса.</span><span class="sxs-lookup"><span data-stu-id="4a05e-228">The following example illustrates how to add some descriptive statistics to the prediction query results.</span></span> <span data-ttu-id="4a05e-229">По этим результатам можно понять, что в данной модели наблюдается значительное отклонение от средней величины.</span><span class="sxs-lookup"><span data-stu-id="4a05e-229">From these results, you can see that there is considerable deviation from the mean for this model.</span></span>  
  
```  
SELECT  
  ([LR_PredictIncome].[Yearly Income]) as [PredIncome],  
  (PredictStdev([LR_PredictIncome].[Yearly Income])) as [StDev1]  
From  
  [LR_PredictIncome]  
NATURAL PREDICTION JOIN  
(SELECT 20 AS [Age]) AS t  
```  
  
 <span data-ttu-id="4a05e-230">Образец результатов.</span><span class="sxs-lookup"><span data-stu-id="4a05e-230">Sample results:</span></span>  
  
|<span data-ttu-id="4a05e-231">Годовой доход</span><span class="sxs-lookup"><span data-stu-id="4a05e-231">Yearly Income</span></span>|<span data-ttu-id="4a05e-232">StDev1</span><span class="sxs-lookup"><span data-stu-id="4a05e-232">StDev1</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="4a05e-233">45227,302092176</span><span class="sxs-lookup"><span data-stu-id="4a05e-233">45227.302092176</span></span>|<span data-ttu-id="4a05e-234">31827,1726561396</span><span class="sxs-lookup"><span data-stu-id="4a05e-234">31827.1726561396</span></span>|  
  
 [<span data-ttu-id="4a05e-235">Вернуться к началу</span><span class="sxs-lookup"><span data-stu-id="4a05e-235">Return to Top</span></span>](#bkmk_top)  
  
## <a name="list-of-prediction-functions"></a><span data-ttu-id="4a05e-236">Список прогнозирующих функций</span><span class="sxs-lookup"><span data-stu-id="4a05e-236">List of Prediction Functions</span></span>  
 <span data-ttu-id="4a05e-237">Все алгоритмы [!INCLUDE[msCoName](../../includes/msconame-md.md)] поддерживают общий набор функций.</span><span class="sxs-lookup"><span data-stu-id="4a05e-237">All [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms support a common set of functions.</span></span> <span data-ttu-id="4a05e-238">Однако алгоритм линейной регрессии [!INCLUDE[msCoName](../../includes/msconame-md.md)] поддерживает дополнительные функции, приведенные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4a05e-238">However, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression algorithm supports the additional functions listed in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4a05e-239">прогнозирующую функцию</span><span class="sxs-lookup"><span data-stu-id="4a05e-239">Prediction Function</span></span>|<span data-ttu-id="4a05e-240">Использование</span><span class="sxs-lookup"><span data-stu-id="4a05e-240">Usage</span></span>|  
|[<span data-ttu-id="4a05e-241">IsDescendant (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="4a05e-241">IsDescendant &#40;DMX&#41;</span></span>](/sql/dmx/isdescendant-dmx)|<span data-ttu-id="4a05e-242">Определяет, является ли узел дочерним для другого узла модели.</span><span class="sxs-lookup"><span data-stu-id="4a05e-242">Determines whether one node is a child of another node in the model.</span></span>|  
|[<span data-ttu-id="4a05e-243">IsInNode (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="4a05e-243">IsInNode &#40;DMX&#41;</span></span>](/sql/dmx/isinnode-dmx)|<span data-ttu-id="4a05e-244">Указывает, содержит ли заданный узел текущий вариант.</span><span class="sxs-lookup"><span data-stu-id="4a05e-244">Indicates whether the specified node contains the current case.</span></span>|  
|[<span data-ttu-id="4a05e-245">PredictHistogram (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="4a05e-245">PredictHistogram &#40;DMX&#41;</span></span>](/sql/dmx/predicthistogram-dmx)|<span data-ttu-id="4a05e-246">Возвращает прогнозируемое значение или набор значений для указанного столбца.</span><span class="sxs-lookup"><span data-stu-id="4a05e-246">Returns a predicted value, or set of values, for a specified column.</span></span>|  
|[<span data-ttu-id="4a05e-247">PredictNodeId (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="4a05e-247">PredictNodeId &#40;DMX&#41;</span></span>](/sql/dmx/predictnodeid-dmx)|<span data-ttu-id="4a05e-248">Возвращает параметр Node_ID для каждого случая.</span><span class="sxs-lookup"><span data-stu-id="4a05e-248">Returns the Node_ID for each case.</span></span>|  
|[<span data-ttu-id="4a05e-249">PredictStdev (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="4a05e-249">PredictStdev &#40;DMX&#41;</span></span>](/sql/dmx/predictstdev-dmx)|<span data-ttu-id="4a05e-250">Возвращает стандартное отклонение для прогнозируемого значения.</span><span class="sxs-lookup"><span data-stu-id="4a05e-250">Returns standard deviation for the predicted value.</span></span>|  
|[<span data-ttu-id="4a05e-251">PredictSupport (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="4a05e-251">PredictSupport &#40;DMX&#41;</span></span>](/sql/dmx/predictsupport-dmx)|<span data-ttu-id="4a05e-252">Возвращает опорное значение для указанного состояния.</span><span class="sxs-lookup"><span data-stu-id="4a05e-252">Returns the support value for a specified state.</span></span>|  
|[<span data-ttu-id="4a05e-253">PredictVariance (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="4a05e-253">PredictVariance &#40;DMX&#41;</span></span>](/sql/dmx/predictvariance-dmx)|<span data-ttu-id="4a05e-254">Возвращает дисперсию указанного столбца.</span><span class="sxs-lookup"><span data-stu-id="4a05e-254">Returns the variance of a specified column.</span></span>|  
  
 <span data-ttu-id="4a05e-255">Список общих функций для всех алгоритмов [!INCLUDE[msCoName](../../includes/msconame-md.md)] см. в статье [Алгоритмы интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4a05e-255">For a list of the functions that are common to all [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span> <span data-ttu-id="4a05e-256">Дополнительные сведения об использовании этих функций см. в разделе [Справочник по расширениям интеллектуального анализа данных](/sql/dmx/data-mining-extensions-dmx-function-reference).</span><span class="sxs-lookup"><span data-stu-id="4a05e-256">For more information about how to use these functions, see [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a05e-257">См. также:</span><span class="sxs-lookup"><span data-stu-id="4a05e-257">See Also</span></span>  
 <span data-ttu-id="4a05e-258">[Алгоритм линейной регрессии (Майкрософт)](microsoft-linear-regression-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="4a05e-258">[Microsoft Linear Regression Algorithm](microsoft-linear-regression-algorithm.md) </span></span>  
 <span data-ttu-id="4a05e-259">[Запросы интеллектуального анализа данных](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="4a05e-259">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="4a05e-260">[Технический справочник по алгоритму линейной регрессии (Майкрософт)](microsoft-linear-regression-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4a05e-260">[Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="4a05e-261">Содержимое моделей интеллектуального анализа данных для моделей линейной регрессии (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="4a05e-261">Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  
