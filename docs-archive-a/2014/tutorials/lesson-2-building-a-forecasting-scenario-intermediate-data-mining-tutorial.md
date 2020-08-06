---
title: Занятие 2. Создание сценария прогнозирования (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time series [Analysis Services]
- data mining [Analysis Services], tutorials
- tutorials [Data Mining]
ms.assetid: 9a988156-c900-4c22-97fa-f6b0c1aea9e2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c81d5846df0a37c2b4182cb92fea86ce6f3417a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654687"
---
# <a name="lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="831f9-102">Занятие 2. Создание сценария прогнозирования (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="831f9-102">Lesson 2: Building a Forecasting Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="831f9-103">Предположим, что вы аналитик по сбыту в компании [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], получили задание составить прогноз продаж продуктов на следующий год.</span><span class="sxs-lookup"><span data-stu-id="831f9-103">As the sales analyst for [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], you have been asked to forecast the sales of products for the next year.</span></span> <span data-ttu-id="831f9-104">В частности, вам было предложено сравнить прогнозы для различных регионов и линеек продуктов.</span><span class="sxs-lookup"><span data-stu-id="831f9-104">In particular, you have been asked to compare forecasts for the different regions and product lines.</span></span> <span data-ttu-id="831f9-105">Кроме того, ему требуется понять, зависят ли продажи различных продуктов от времени года.</span><span class="sxs-lookup"><span data-stu-id="831f9-105">Additionally, you have been asked to determine whether sales of different products vary depending on the time of the year.</span></span>  
  
 <span data-ttu-id="831f9-106">Для поиска необходимых сведений в этом занятии будут использованы помесячные данные о продажах организации. Кроме того, будут сведены данные по продажам в трех регионах: Европа, Северная Америка и Тихоокеанский регион.</span><span class="sxs-lookup"><span data-stu-id="831f9-106">To find the requested information, in this lesson you will summarize the company's sales data at the monthly level, and you will also summarize sales figures by three regions: Europe, North America, and the Pacific.</span></span>  
  
 <span data-ttu-id="831f9-107">В результате выполнения задач этого занятия будут получены ответы на следующие ниже вопросы.</span><span class="sxs-lookup"><span data-stu-id="831f9-107">After you complete the tasks in this lesson, you will be able to answer the following questions:</span></span>  
  
-   <span data-ttu-id="831f9-108">Как меняется динамика продаж разных моделей велосипедов с течением времени?</span><span class="sxs-lookup"><span data-stu-id="831f9-108">How do the sales of different bike models change over time?</span></span>  
  
-   <span data-ttu-id="831f9-109">Существуют ли отличия между шаблонами продаж в трех регионах?</span><span class="sxs-lookup"><span data-stu-id="831f9-109">Are there differences between the patterns for sales in the three regions?</span></span>  
  
-   <span data-ttu-id="831f9-110">Возможно ли спрогнозировать пиковые значения продаж?</span><span class="sxs-lookup"><span data-stu-id="831f9-110">Can we forecast sales peaks?</span></span>  
  
 <span data-ttu-id="831f9-111">Занятие может быть завершено в два этапа:</span><span class="sxs-lookup"><span data-stu-id="831f9-111">The lesson can be completed in two parts:</span></span>  
  
-   <span data-ttu-id="831f9-112">Первая часть содержит базовые понятия создания и использования модели временных рядов.</span><span class="sxs-lookup"><span data-stu-id="831f9-112">Part One introduces the basics of how to create and use a time series model.</span></span>  
  
-   <span data-ttu-id="831f9-113">Вторая часть содержит пошаговые указания по созданию общей модели временных рядов на основе всех регионов.</span><span class="sxs-lookup"><span data-stu-id="831f9-113">Part Two walks you through creation of a general time series model, based on all regions.</span></span> <span data-ttu-id="831f9-114">Эту общую модель можно использовать для *перекрестного прогнозирования*.</span><span class="sxs-lookup"><span data-stu-id="831f9-114">You can use this general model for *cross-prediction*.</span></span>  
  
 <span data-ttu-id="831f9-115">Для выполнения задач этого занятия, которые перечислены ниже, будет использоваться [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] источник данных, созданный на [занятии 1. Создание промежуточного решения интеллектуального анализа данных &#40;руководстве по интеллектуальному анализу данных&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="831f9-115">To complete the tasks in this lesson, which are listed below, you will use the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source that you created in [Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="831f9-116">Даты, используемые в образце базы данных [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] , изменены для этой версии.</span><span class="sxs-lookup"><span data-stu-id="831f9-116">The dates in the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] sample database have been updated for this release.</span></span> <span data-ttu-id="831f9-117">При использовании более ранней версии [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)]можно построить модель, выполнив эти действия, но полученные результаты могут оказаться другими.</span><span class="sxs-lookup"><span data-stu-id="831f9-117">If you use an earlier version of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], you can build the model following these steps, but you might see different results.</span></span>  
  
 <span data-ttu-id="831f9-118">**Создание простой модели прогнозирования**</span><span class="sxs-lookup"><span data-stu-id="831f9-118">**Creating a Simple Forecasting Model**</span></span>  
  
-   [<span data-ttu-id="831f9-119">Руководство по добавлению представления источников данных для прогнозирования &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-119">Adding a Data Source View for Forecasting &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="831f9-120">Руководство по созданию структуры прогнозирования и модели &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-120">Creating a Forecasting Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="831f9-121">Изменение структуры прогнозирования &#40;промежуточное руководство по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-121">Modifying the Forecasting Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="831f9-122">Настройка и обработка модели прогнозирования &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-122">Customizing and Processing the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/customize-process-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="831f9-123">Изучите учебник по модели прогнозирования &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-123">Exploring the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="831f9-124">Создание прогнозов временных рядов &#40;учебнике по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-124">Creating Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="831f9-125">**Создание общей модели прогнозирования для перекрестного прогнозирования**</span><span class="sxs-lookup"><span data-stu-id="831f9-125">**Creating a General Forecasting Model for Cross-Prediction**</span></span>  
  
-   [<span data-ttu-id="831f9-126">Учебник по расширенному анализу временных рядов &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-126">Advanced Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="831f9-127">Прогнозирование временных рядов с помощью обновленного учебника по интеллектуальному анализу данных &#40;данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-127">Time Series Predictions using Updated Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="831f9-128">Прогнозирование временных рядов с использованием замещения данных &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-128">Time Series Predictions using Replacement Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="831f9-129">Сравнение прогнозов для моделей прогнозирования &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-129">Comparing Predictions for Forecasting Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="831f9-130">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="831f9-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="831f9-131">Руководство по добавлению представления источников данных для прогнозирования &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-131">Adding a Data Source View for Forecasting &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="831f9-132">Основные сведения о требованиях к модели временных рядов &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-132">Understanding the Requirements for a Time Series Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="831f9-133">Все занятия</span><span class="sxs-lookup"><span data-stu-id="831f9-133">All Lessons</span></span>  
 [<span data-ttu-id="831f9-134">Занятие 1. Создание промежуточного решения интеллектуального анализа данных &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-134">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="831f9-135">Урок 2. Сценарий прогнозирования (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="831f9-135">Lesson 2: Forecasting Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="831f9-136">Урок 3. Построение сценария покупательского поведения (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="831f9-136">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="831f9-137">Занятие 4. Создание сценария кластеризации последовательностей &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="831f9-137">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="831f9-138">Занятие 5. Построение моделей нейронной сети и логистической регрессии (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="831f9-138">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="831f9-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="831f9-139">See Also</span></span>  
 <span data-ttu-id="831f9-140">[Учебник по основам интеллектуального анализа данных](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="831f9-140">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 <span data-ttu-id="831f9-141">[Учебник по интеллектуальному анализу данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="831f9-141">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="831f9-142">Алгоритм временных рядов (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="831f9-142">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
