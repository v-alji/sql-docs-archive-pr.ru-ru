---
title: Занятие 3. Создание сценария потребительской корзины (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- association algorithms [Analysis Services]
- nested tables
- tutorials [Data Mining]
ms.assetid: 651eef38-772e-4d97-af51-075b1b27fc5a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a281aa62fbf08393c95f12ded9886ac212b3165f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735630"
---
# <a name="lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="c69fc-102">Занятие 3. Создание сценария потребительской корзины (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="c69fc-102">Lesson 3: Building a Market Basket Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="c69fc-103">Задача отдела маркетинга компании [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] — улучшить веб-сайт компании путем повышения объема перекрестных продаж.</span><span class="sxs-lookup"><span data-stu-id="c69fc-103">The marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to improve the company Web site to promote cross-selling.</span></span> <span data-ttu-id="c69fc-104">После обновления сайт должен поддерживать создание модели интеллектуального анализа данных, которая позволит на основании текущего содержимого корзин заказов в сети прогнозировать, какие продукты клиенты хотели бы купить.</span><span class="sxs-lookup"><span data-stu-id="c69fc-104">As part of the site update, they would like the ability to predict products that a customer might want to purchase, based on the other products that are already in the customer's online shopping basket.</span></span> <span data-ttu-id="c69fc-105">Отделу маркетинга также требуется более глубокое понимание поведения клиента в процессе покупки, что позволит сгруппировать на веб-сайте те позиции, которые часто приобретаются вместе.</span><span class="sxs-lookup"><span data-stu-id="c69fc-105">The marketing department also wants to understand customer purchasing behavior better, so that they can design the Web site so that the items that tend to be purchased together appear together.</span></span> <span data-ttu-id="c69fc-106">Отдел маркетинга пришел к выводу, что интеллектуальный анализ данных может быть особенно полезен для этого типа *анализа потребительской корзины* , и попросил разработать соответствующую модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="c69fc-106">They have learned that data mining is especially useful for this kind of *market basket analysis* and have asked you to develop a data mining model.</span></span>  
  
 <span data-ttu-id="c69fc-107">После завершения задач этого занятия будет создана модель интеллектуального анализа данных, показывающая товары в группах по транзакциям клиентов за более ранние периоды.</span><span class="sxs-lookup"><span data-stu-id="c69fc-107">After you complete the tasks in this lesson, you will have a mining model that shows groups of items from historical customer transactions.</span></span> <span data-ttu-id="c69fc-108">Кроме того, модель интеллектуального анализа данных можно использовать для прогнозирования дополнительных товаров, которые, возможно, захочет приобрести клиент.</span><span class="sxs-lookup"><span data-stu-id="c69fc-108">Additionally, you can use the mining model to predict additional items that a customer may want to purchase.</span></span>  
  
 <span data-ttu-id="c69fc-109">Для выполнения задач этого занятия будет использоваться решение и источник данных, созданные на первом занятии [учебника по интеллектуальному анализу данных &#40;Analysis Services-&#41;интеллектуального анализа данных ](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="c69fc-109">To complete the tasks in this lesson, you will use the solution and data source that you created in the first lesson of the [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span> <span data-ttu-id="c69fc-110">Решение будет изменено путем добавления представления источников данных с таблицами, касающимися заказчиков, в том числе с вложенной таблицей покупок заказчиков.</span><span class="sxs-lookup"><span data-stu-id="c69fc-110">You will modify this solution by adding a data source view that contains tables about the customer, including a nested table of customer purchases.</span></span>  <span data-ttu-id="c69fc-111">Затем будет построена модель интеллектуального анализа данных, использующая алгоритм правил взаимосвязей (Майкрософт), приспособленный для сценариев потребительских корзин.</span><span class="sxs-lookup"><span data-stu-id="c69fc-111">You will then build a mining model that uses the Microsoft Association Rules algorithm, which is suited to market basket scenarios.</span></span>  
  
 <span data-ttu-id="c69fc-112">Это занятие содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="c69fc-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="c69fc-113">Добавление представления источников данных с вложенными таблицами &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c69fc-113">Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="c69fc-114">Руководство по созданию структуры потребительской корзины и модели &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c69fc-114">Creating a Market Basket Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="c69fc-115">Изменение и обработка модели потребительской корзины &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c69fc-115">Modifying and Processing the Market Basket Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modify-process-market-basket-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="c69fc-116">Изучение моделей потребительской корзины &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c69fc-116">Exploring the Market Basket Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="c69fc-117">Фильтрация вложенной таблицы в модели интеллектуального анализа данных &#40;руководстве по интеллектуальному анализу&#41;</span><span class="sxs-lookup"><span data-stu-id="c69fc-117">Filtering a Nested Table in a Mining Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="c69fc-118">Учебник по прогнозированию взаимосвязей &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c69fc-118">Predicting Associations &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c69fc-119">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="c69fc-119">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c69fc-120">Добавление представления источников данных с вложенными таблицами &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c69fc-120">Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="c69fc-121">Все занятия</span><span class="sxs-lookup"><span data-stu-id="c69fc-121">All Lessons</span></span>  
 [<span data-ttu-id="c69fc-122">Занятие 1. Создание промежуточного решения интеллектуального анализа данных &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c69fc-122">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="c69fc-123">Занятие 2. Создание сценария прогнозирования &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c69fc-123">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="c69fc-124">Урок 3. Построение сценария покупательского поведения (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="c69fc-124">Lesson 3: Market Basket Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="c69fc-125">Занятие 4. Создание сценария кластеризации последовательностей &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c69fc-125">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="c69fc-126">Занятие 5. Построение моделей нейронной сети и логистической регрессии (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="c69fc-126">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="c69fc-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="c69fc-127">See Also</span></span>  
 <span data-ttu-id="c69fc-128">[Учебник по основам интеллектуального анализа данных](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="c69fc-128">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 <span data-ttu-id="c69fc-129">[Занятие 2. Создание сценария прогнозирования &#40;руководстве по интеллектуальному анализу данных&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="c69fc-129">[Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="c69fc-130">Занятие 4. Создание сценария кластеризации последовательностей &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c69fc-130">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
  
