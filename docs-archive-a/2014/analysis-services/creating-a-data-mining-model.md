---
title: Создание модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining models, creating
- forecasting [data mining]
- mining models, creating
- clustering [data mining]
- association [data mining]
- data modeling [data mining]
- estimation
- classification [data mining]
ms.assetid: 804b7db3-1f6a-4f73-a81d-bbe02520d7c6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1e27739d3733c0b48dc6cff3e83e01f9cb12bce7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665163"
---
# <a name="creating-a-data-mining-model"></a><span data-ttu-id="59454-102">Создание модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="59454-102">Creating a Data Mining Model</span></span>
  <span data-ttu-id="59454-103">Моделирование данных — это этап интеллектуального анализа данных, при котором создаются закономерности и тенденции, применяемые *к данным* .</span><span class="sxs-lookup"><span data-stu-id="59454-103">Data modeling is the step of data mining where you build patterns and trends by applying *algorithms* to data.</span></span> <span data-ttu-id="59454-104">В дальнейшем можно использовать эти закономерности для анализа или прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="59454-104">Later you can use those patterns for analysis, or to make predictions.</span></span>  
  
 <span data-ttu-id="59454-105">Надстройки интеллектуального анализа данных для Office поддерживают интеллектуальный анализ данных с помощью мастеров, которые упрощают создание моделей.</span><span class="sxs-lookup"><span data-stu-id="59454-105">The Data Mining Add-ins for Office support data mining through wizards that make it easy to create models.</span></span> <span data-ttu-id="59454-106">Мастеры анализируют данные, определяют взаимосвязи, вычисляют статистическую значимость всех переменных и автоматически выбирают лучшую модель.</span><span class="sxs-lookup"><span data-stu-id="59454-106">The wizards analyze the data, identify correlations, compute statistical significance of all variables, and automatically select the best model.</span></span>  
  
 <span data-ttu-id="59454-107">Несмотря на то что эти функциональные возможности являются мощными для средств интеллектуального анализа данных, предоставляемых [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , сочетание мастеров и знакомого интерфейса Excel упрощает создание, изменение и использование интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="59454-107">Although this functionality is every bit as powerful as the data mining tools provided by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the combination of wizards and the familiar Excel interface makes it easy to create, modify, and use data mining.</span></span>  
  
## <a name="advanced-data-mining"></a><span data-ttu-id="59454-108">Расширенный интеллектуальный анализ данных</span><span class="sxs-lookup"><span data-stu-id="59454-108">Advanced (Data Mining)</span></span>  
 <span data-ttu-id="59454-109">Дополнительные мастера позволяют создавать новые модели интеллектуального анализа данных на основе данных, хранящихся в Excel, с помощью одного из алгоритмов интеллектуального анализа данных в среде [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59454-109">The Advanced wizards let you create new data mining models, based on data stored in Excel, by using one of the data mining algorithms in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
### <a name="create-mining-structure"></a><span data-ttu-id="59454-110">Создание структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="59454-110">Create Mining Structure</span></span>  
 <span data-ttu-id="59454-111">Мастер создания структур интеллектуального анализа данных позволяет сформировать новую структуру интеллектуального анализа данных, которая может служить в качестве основы для нескольких моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="59454-111">The Create Mining Structure wizard helps you build a new data mining structure, which you can use as the basis for multiple mining models.</span></span> <span data-ttu-id="59454-112">Мастер предоставляет этот параметр, чтобы зарезервировать часть данных для использования в виде проверочного набора, чтобы можно было оценить все модели с помощью одних и тех же данных в соответствии с согласованным стандартом проверки.</span><span class="sxs-lookup"><span data-stu-id="59454-112">The wizard gives you the option to set aside a portion of the data to use as a testing set, so that you can evaluate all models that use the same data according to a consistent testing standard.</span></span>  
  
 [<span data-ttu-id="59454-113">Создание структуры интеллектуального анализа &#40;SQL Server надстроек интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-113">Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;</span></span>](create-mining-structure-sql-server-data-mining-add-ins.md)  
  
### <a name="add-model-to-structure"></a><span data-ttu-id="59454-114">Добавление модели в структуру</span><span class="sxs-lookup"><span data-stu-id="59454-114">Add Model to Structure</span></span>  
 <span data-ttu-id="59454-115">Мастер добавления модели к структуре позволяет выбрать структуру интеллектуального анализа данных и создать для нее новую модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="59454-115">The Add Model to Structure wizard lets you choose an existing data mining structure and create a new data mining model for it.</span></span> <span data-ttu-id="59454-116">В структуре можно добавлять несколько моделей интеллектуального анализа данных, изменять параметры или выбирать другие алгоритмы интеллектуального анализа данных, а также настраивать выход.</span><span class="sxs-lookup"><span data-stu-id="59454-116">You can add multiple mining models to a structure, changing the parameters or choosing different data mining algorithms, and customize the output.</span></span>  
  
 [<span data-ttu-id="59454-117">Добавление модели в структуру &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-117">Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;</span></span>](add-model-to-structure-data-mining-add-ins-for-excel.md)  
  
## <a name="analyze-key-influencers-analyze"></a><span data-ttu-id="59454-118">Анализ ключевых факторов влияния</span><span class="sxs-lookup"><span data-stu-id="59454-118">Analyze Key Influencers (Analyze)</span></span>  
 <span data-ttu-id="59454-119">Пользователь выбирает нужный столбец или выходное значение, а затем алгоритм анализирует все входные данные для определения факторов, которые имеют наибольшее влияние на целевой объект.</span><span class="sxs-lookup"><span data-stu-id="59454-119">You choose a column or output value of interest, and then the algorithm analyzes all the input data to identify the factors that have the most influence on the target.</span></span> <span data-ttu-id="59454-120">Кроме того, можно создать отчет, который сравнивает любые два значения, чтобы увидеть, как изменяются основные факторы.</span><span class="sxs-lookup"><span data-stu-id="59454-120">Optionally, you can create a report that compares any two values, so that you can see how the influencers change.</span></span>  
  
 <span data-ttu-id="59454-121">Средство **Анализ ключевых факторов влияния** использует упрощенный алгоритм Байеса (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="59454-121">The **Analyze Key Influencers** tool uses the Microsoft Naïve Bayes algorithm.</span></span>  
  
 [<span data-ttu-id="59454-122">Анализ ключевых факторов влияния &#40;средств анализа таблиц для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-122">Analyze Key Influencers &#40;Table Analysis Tools for Excel&#41;</span></span>](analyze-key-influencers-table-analysis-tools-for-excel.md)  
  
## <a name="associate-data-mining"></a><span data-ttu-id="59454-123">Взаимосвязь (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="59454-123">Associate (Data Mining)</span></span>  
 <span data-ttu-id="59454-124">Мастер **связывает** модель взаимосвязей, которая обнаруживает связи между элементами, которые появляются в нескольких транзакциях, например, в анализе потребительской корзины.</span><span class="sxs-lookup"><span data-stu-id="59454-124">The **Associate** wizard builds an association model that detects associations between items that appear in multiple transactions: for example, in market basket analysis.</span></span>  
  
 [<span data-ttu-id="59454-125">Мастер связывания &#40;клиента интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-125">Associate Wizard &#40;Data Mining Client for Excel&#41;</span></span>](associate-wizard-data-mining-client-for-excel.md)  
  
## <a name="classify-data-mining"></a><span data-ttu-id="59454-126">Классификация (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="59454-126">Classify (Data Mining)</span></span>  
 <span data-ttu-id="59454-127">Мастер **классификации** строит модель классификации, которая анализирует факторы, влияющие на целевой результат.</span><span class="sxs-lookup"><span data-stu-id="59454-127">The  **Classify** wizard builds a classification model that analyzes the factors that contributed to a target outcome.</span></span> <span data-ttu-id="59454-128">Можно использовать несколько алгоритмов с помощью этого мастера, включая деревья принятия решений, упрощенный алгоритм Байеса и нейронные сети.</span><span class="sxs-lookup"><span data-stu-id="59454-128">You can use multiple algorithms with this wizard, including Decision Trees, Naïve Bayes, and Neural Networks.</span></span>  
  
 [<span data-ttu-id="59454-129">Мастер классификации &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-129">Classify Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](classify-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="cluster-data-mining"></a><span data-ttu-id="59454-130">Кластеризация (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="59454-130">Cluster (Data Mining)</span></span>  
 <span data-ttu-id="59454-131">Мастер **кластеров** создает модель кластеризации, которая определяет группы строк, имеющих аналогичные характеристики.</span><span class="sxs-lookup"><span data-stu-id="59454-131">The **Cluster** wizard builds a clustering model that detects groups of rows that share similar characteristics.</span></span> <span data-ttu-id="59454-132">Кластеризация (иногда называемая *сегментацией*) — это неконтролируемый метод обучения, который очень полезен при попытке понять закономерности и группирования в новых данных.</span><span class="sxs-lookup"><span data-stu-id="59454-132">Clustering (sometimes called *segmentation*) is an unsupervised learning technique that is very useful when trying to understand patterns and groupings in new data.</span></span>  
  
 <span data-ttu-id="59454-133">Алгоритм кластеризации Майкрософт поддерживает несколько вариаций кластеризации на основе k-средних и максимизации ожидания.</span><span class="sxs-lookup"><span data-stu-id="59454-133">The Microsoft Clustering algorithm supports several varieties of both K-means and Expectation maximization (EM) clustering</span></span>  
  
 <span data-ttu-id="59454-134">[Мастер кластеров &#40;надстройки интеллектуального анализа данных для&#41;Excel ](cluster-wizard-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="59454-134">[Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md).</span></span>  
  
## <a name="detect-categories-analyze"></a><span data-ttu-id="59454-135">Поиск категорий (анализ)</span><span class="sxs-lookup"><span data-stu-id="59454-135">Detect Categories (Analyze)</span></span>  
 <span data-ttu-id="59454-136">Средство **Поиск категорий** позволяет добавить любой набор данных и применить кластеризацию для поиска группирования данных.</span><span class="sxs-lookup"><span data-stu-id="59454-136">The **Detect Categories** tool lets you add any data set and apply clustering to find groupings of data.</span></span> <span data-ttu-id="59454-137">Это полезно для поиска сходства и создания групп для дальнейшего анализа.</span><span class="sxs-lookup"><span data-stu-id="59454-137">It's useful for finding similarities and for creating groups to further analyze.</span></span>  
  
 <span data-ttu-id="59454-138">Средство **Поиск категорий** использует алгоритм кластеризации (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="59454-138">The **Detect Categories** tool uses the Microsoft Clustering algorithm.</span></span>  
  
 [<span data-ttu-id="59454-139">Определение категорий &#40;средств анализа таблиц для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-139">Detect Categories &#40;Table Analysis Tools for Excel&#41;</span></span>](detect-categories-table-analysis-tools-for-excel.md)  
  
## <a name="estimate-data-mining"></a><span data-ttu-id="59454-140">Оценка (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="59454-140">Estimate (Data Mining)</span></span>  
 <span data-ttu-id="59454-141">Мастер оценки данных предназначен для построения модели оценки, извлекающей закономерности в данных и использующей их для прогнозирования непрерывных значений (числовых значений, значений даты или времени).</span><span class="sxs-lookup"><span data-stu-id="59454-141">The Estimate wizard builds an estimation model that extracts data patterns and uses the patterns to predict continuous numeric, date, or time values.</span></span> <span data-ttu-id="59454-142">В нем используется [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритм дерева принятия решений.</span><span class="sxs-lookup"><span data-stu-id="59454-142">It uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span>  
  
 [<span data-ttu-id="59454-143">Мастер оценки &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-143">Estimate Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](estimate-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="fill-from-example-analyze"></a><span data-ttu-id="59454-144">Заполнение по примеру (анализ)</span><span class="sxs-lookup"><span data-stu-id="59454-144">Fill From Example (Analyze)</span></span>  
 <span data-ttu-id="59454-145">Средство **Заполнение по примеру** позволяет аппроксимация недостающие значения.</span><span class="sxs-lookup"><span data-stu-id="59454-145">The **Fill From Example** tool helps you impute missing values.</span></span> <span data-ttu-id="59454-146">Пользователь предоставляет несколько примеров отсутствующих значений, после чего средство формирует закономерности на основе всех данных в таблице, а затем рекомендует новые значения на основе закономерностей в данных.</span><span class="sxs-lookup"><span data-stu-id="59454-146">You provide some examples of what the missing values should be, and the tool builds patterns based on all data in the table, and then recommends new values based on patterns in the data.</span></span>  
  
 <span data-ttu-id="59454-147">Инструмент « **Заполнение по примеру** » использует алгоритм логистической регрессии (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="59454-147">The **Fill From Example** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="59454-148">Заполнение из примера &#40;средства анализа таблиц для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-148">Fill From Example &#40;Table Analysis Tools for Excel&#41;</span></span>](fill-from-example-table-analysis-tools-for-excel.md)  
  
## <a name="forecast-analyze"></a><span data-ttu-id="59454-149">Прогноз (анализ)</span><span class="sxs-lookup"><span data-stu-id="59454-149">Forecast (Analyze)</span></span>  
 <span data-ttu-id="59454-150">Средство **прогнозирования** принимает данные, которые изменяются со временем, и прогнозирует будущие значения.</span><span class="sxs-lookup"><span data-stu-id="59454-150">The **Forecast** tool takes data that changes over time, and predicts future values.</span></span>  
  
 <span data-ttu-id="59454-151">Средство **прогнозирования** использует алгоритм временных рядов (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="59454-151">The **Forecast** tool uses the Microsoft Time Series algorithm.</span></span>  
  
 [<span data-ttu-id="59454-152">Прогнозирование &#40;средств анализа таблиц для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-152">Forecast &#40;Table Analysis Tools for Excel&#41;</span></span>](forecast-table-analysis-tools-for-excel.md)  
  
## <a name="forecast-data-mining"></a><span data-ttu-id="59454-153">Прогноз (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="59454-153">Forecast (Data Mining)</span></span>  
 <span data-ttu-id="59454-154">Мастер **прогнозов** создает модель прогнозирования, которая обнаруживает закономерности в ряде ячеек, а затем прогнозирует дополнительные значения.</span><span class="sxs-lookup"><span data-stu-id="59454-154">The **Forecast** wizard builds a forecasting model that detects patterns in a series of cells, and then forecasts additional values.</span></span>  
  
 [<span data-ttu-id="59454-155">Мастер прогнозов &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-155">Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](forecast-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="highlight-exceptions-analyze"></a><span data-ttu-id="59454-156">Выделение исключений (анализ)</span><span class="sxs-lookup"><span data-stu-id="59454-156">Highlight Exceptions (Analyze)</span></span>  
 <span data-ttu-id="59454-157">Средство **выделение исключений** анализирует закономерности в таблице данных и находит строки и значения, не соответствующие шаблону.</span><span class="sxs-lookup"><span data-stu-id="59454-157">The **Highlight Exceptions** tool analyzes patterns in a table of data and finds rows and values that don't fit the pattern.</span></span> <span data-ttu-id="59454-158">Затем можно просмотреть и исправить их и повторно применить модель или отметить значения для последующего анализа.</span><span class="sxs-lookup"><span data-stu-id="59454-158">You can then review and correct them and rerun the model, or flag values for later action.</span></span>  
  
 <span data-ttu-id="59454-159">Средство **выделение исключений** использует алгоритм кластеризации (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="59454-159">The **Highlight Exceptions** tool uses the Microsoft Clustering algorithm.</span></span>  
  
 [<span data-ttu-id="59454-160">Выделение исключений &#40;средств анализа таблиц для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-160">Highlight Exceptions &#40;Table Analysis Tools for Excel&#41;</span></span>](highlight-exceptions-table-analysis-tools-for-excel.md)  
  
## <a name="prediction-calculator-analyze"></a><span data-ttu-id="59454-161">Расчет прогноза (анализ)</span><span class="sxs-lookup"><span data-stu-id="59454-161">Prediction Calculator (Analyze)</span></span>  
 <span data-ttu-id="59454-162">Это средство создает модель, анализирующую факторы, которые позволяют получить нужные результаты, а затем предсказывает результат для новых входных данных на основе критериев, полученных из этих закономерностей. Оно также создает интерактивный лист процесса принятия решений, позволяющий легко оценить новые входные данные.</span><span class="sxs-lookup"><span data-stu-id="59454-162">This tool creates a model that analyzes the factors leading to target outcomes, and then predicts a result for any new input, based on criteria derived from these patterns It also generates an interactive decision making worksheet that lets you easily score new inputs.</span></span> <span data-ttu-id="59454-163">Также можно создать печатную версию листа оценки для автономного использования.</span><span class="sxs-lookup"><span data-stu-id="59454-163">You can also create a printed version of the scoring worksheet for offline use.</span></span>  
  
 <span data-ttu-id="59454-164">Средство **Расчет прогноза** использует алгоритм логистической регрессии (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="59454-164">The **Prediction Calculator** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="59454-165">Расчет прогноза &#40;средства анализа таблиц для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-165">Prediction Calculator &#40;Table Analysis Tools for Excel&#41;</span></span>](prediction-calculator-table-analysis-tools-for-excel.md)  
  
## <a name="scenario-goal-seek-analyze"></a><span data-ttu-id="59454-166">Сценарий: Поиск решения (анализ)</span><span class="sxs-lookup"><span data-stu-id="59454-166">Scenario: Goal Seek (Analyze)</span></span>  
 <span data-ttu-id="59454-167">В средстве **поиска решения** указывается целевое значение, и средство определяет базовые факторы, которые должны быть изменены для соответствия этому целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="59454-167">In the **Goal Seek** tool, you specify a target value, and the tool identifies the underlying factors that must change to meet that target.</span></span> <span data-ttu-id="59454-168">Например, если известно, что нужно увеличить уровень обслуживания входящих звонков на 20 %, можно настроить модель на прогнозирование факторов, изменение которых позволяет достигнуть этой цели.</span><span class="sxs-lookup"><span data-stu-id="59454-168">For example, if you know that you must increase call satisfaction by 20%, you can ask the model to predict the factors that should change to produce that goal.</span></span>  
  
 <span data-ttu-id="59454-169">Средство **поиска решения** использует алгоритм логистической регрессии (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="59454-169">The **Goal Seek** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 <span data-ttu-id="59454-170">подробности</span><span class="sxs-lookup"><span data-stu-id="59454-170">details</span></span>  
  
 [<span data-ttu-id="59454-171">Сценарий поиска решения &#40;средства анализа таблиц для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-171">Goal Seek Scenario &#40;Table Analysis Tools for Excel&#41;</span></span>](goal-seek-scenario-table-analysis-tools-for-excel.md)  
  
## <a name="scenario-what-if-scenario-analyze"></a><span data-ttu-id="59454-172">Сценарий: сценарий "что если" (анализ)</span><span class="sxs-lookup"><span data-stu-id="59454-172">Scenario: What-If Scenario (Analyze)</span></span>  
 <span data-ttu-id="59454-173">Средство **анализа гипотетических результатов** дополняет средство **поиска решения** .</span><span class="sxs-lookup"><span data-stu-id="59454-173">The **What-If Analysis** tool complements the **Goal Seek** tool.</span></span> <span data-ttu-id="59454-174">Средство позволяет ввести значение, которое нужно изменить, а модель прогнозирует, будет ли это изменение достаточно для достижения желаемого результата.</span><span class="sxs-lookup"><span data-stu-id="59454-174">With this tool, you entered the value you want to change, and the model predicts whether that change will be sufficient to achieve the desired outcome.</span></span> <span data-ttu-id="59454-175">Например, можно попросить модель определить, увеличит ли добавление дополнительного оператора удовлетворенность заказчика на один пункт.</span><span class="sxs-lookup"><span data-stu-id="59454-175">For example, you might ask the model to infer whether adding one extra call operator would increase customer satisfaction by one point.</span></span>  
  
 <span data-ttu-id="59454-176">Средство " **что если** " использует алгоритм логистической регрессии (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="59454-176">The **What-If** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="59454-177">Сценарий "что если" &#40;средств анализа таблиц для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-177">What-If Scenario &#40;Table Analysis Tools for Excel&#41;</span></span>](what-if-scenario-table-analysis-tools-for-excel.md)  
  
## <a name="shopping-basket-analysis-analyze"></a><span data-ttu-id="59454-178">Анализ покупательского поведения</span><span class="sxs-lookup"><span data-stu-id="59454-178">Shopping Basket Analysis (Analyze)</span></span>  
 <span data-ttu-id="59454-179">Средство **анализа покупательской корзины** создает группы продуктов, которые часто приобретаются вместе, чтобы определять закономерности, которые можно использовать при перекрестной продаже или продаже.</span><span class="sxs-lookup"><span data-stu-id="59454-179">The **Shopping Basket Analysis** tool creates groups of products that are frequently purchased together, to identify patterns that can be used in cross-selling or up-selling.</span></span> <span data-ttu-id="59454-180">Кроме того, оно создает отчеты на основе цены связанных пакетов продуктов для упрощения принятия решений.</span><span class="sxs-lookup"><span data-stu-id="59454-180">It also generates reports based on the price and cost of related product bundles, to aid in decision-making.</span></span>  
  
 <span data-ttu-id="59454-181">Это средство также можно использовать для событий, которые часто возникают вместе, факторов, позволяющих поставить диагноз, или любого другого набора потенциальных причин и результатов.</span><span class="sxs-lookup"><span data-stu-id="59454-181">You can also use this tool for events that frequently occur together, factors leading to a diagnosis, or any other set of potential causes and outcomes.</span></span>  
  
 <span data-ttu-id="59454-182">Средство **анализа покупательской корзины** использует алгоритм взаимосвязей (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="59454-182">The **Shopping Basket Analysis** tool uses the Microsoft Association algorithm.</span></span>  
  
 [<span data-ttu-id="59454-183">Анализ покупательской корзины &#40;таблицу Аналисистулс для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-183">Shopping Basket Analysis &#40;Table AnalysisTools for Excel&#41;</span></span>](shopping-basket-analysis-table-analysistools-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="59454-184">См. также:</span><span class="sxs-lookup"><span data-stu-id="59454-184">See Also</span></span>  
 <span data-ttu-id="59454-185">[Изучение и очистка данных](exploring-and-cleaning-data.md) </span><span class="sxs-lookup"><span data-stu-id="59454-185">[Exploring and Cleaning Data](exploring-and-cleaning-data.md) </span></span>  
 <span data-ttu-id="59454-186">[Проверка моделей и использование моделей для прогнозирования &#40;надстройки интеллектуального анализа данных для Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="59454-186">[Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="59454-187">Развертывание и масштабирование моделей интеллектуального анализа &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="59454-187">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
