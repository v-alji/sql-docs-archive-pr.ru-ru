---
title: Занятие 4. Создание сценария кластеризации последовательностей (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- sequence clustering algorithms [Analysis Services]
- tutorials [Data Mining]
ms.assetid: 63436bbd-0f73-4012-b6f1-358c81e4d92a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 0f417c685d8af898de7c66ffe82045fa76b582e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727498"
---
# <a name="lesson-4-building-a-sequence-clustering-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="d178f-102">Занятие 4. Создание сценария кластеризации последовательностей (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="d178f-102">Lesson 4: Building a Sequence Clustering Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="d178f-103">Отделу маркетинга компании [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] необходимо знать, как перемещаются заказчики по веб-сайту компании [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d178f-103">The marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to understand how customers move through the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] Web site.</span></span> <span data-ttu-id="d178f-104">Компания полагает, что есть какой-то определенный порядок, в котором они помещают продукты в корзину заказа.</span><span class="sxs-lookup"><span data-stu-id="d178f-104">The company suspects that there is a pattern to the order in which customers put products into their shopping baskets.</span></span> <span data-ttu-id="d178f-105">Отделу требуется проанализировать порядок последовательностей покупок, чтобы узнать, как заказчики добавляют в корзины связанные элементы.</span><span class="sxs-lookup"><span data-stu-id="d178f-105">They want to analyze the order of purchase sequences to learn how customers add related items to their baskets.</span></span> <span data-ttu-id="d178f-106">Эти сведения можно также использовать для оптимизации веб-сайта таким образом, чтобы заказчики покупали больше продуктов.</span><span class="sxs-lookup"><span data-stu-id="d178f-106">They can then use this information to streamline the flow of the Web site so that it leads customers to purchase additional products.</span></span>  
  
 <span data-ttu-id="d178f-107">После выполнения задач этого занятия будет создана модель интеллектуального анализа данных, использующая алгоритм кластеризации последовательностей ( [!INCLUDE[msCoName](../includes/msconame-md.md)] ), который позволит прогнозировать, какой элемент будет помещен заказчиком в корзину заказов следующим.</span><span class="sxs-lookup"><span data-stu-id="d178f-107">After you complete the tasks in this lesson, you will have created a mining model that uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm to predict the next item that customers will put into their shopping baskets.</span></span> <span data-ttu-id="d178f-108">Эксперименты проводятся с двумя версиями модели: с версией, в которой анализируется только порядок продуктов в корзине, и с версией, которая содержит некоторые дополнительные демографические данные о заказчике для кластеризации.</span><span class="sxs-lookup"><span data-stu-id="d178f-108">You will experiment with two versions of the model: one that analyzes only the order of products in the basket, and one that contains some additional customer demographics for clustering.</span></span> <span data-ttu-id="d178f-109">Наконец, будут использоваться модели для создания прогнозов, на основе которых можно рекомендовать продукцию клиентам.</span><span class="sxs-lookup"><span data-stu-id="d178f-109">Finally, you will use the models to create predictions that you can use to recommend products to customers.</span></span>  
  
 <span data-ttu-id="d178f-110">Для выполнения задач на этом занятии будет использоваться структура интеллектуального анализа данных "потребительская корзина", созданная на [занятии 3. Создание сценария потребительской корзины &#40;учебнике по интеллектуальному анализу данных&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d178f-110">To complete the tasks in the lesson, you will use the market basket mining structure that you created in [Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md).</span></span> <span data-ttu-id="d178f-111">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="d178f-111">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="d178f-112">Создание структуры модели интеллектуального анализа кластеризации последовательностей &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d178f-112">Creating a Sequence Clustering Mining Model Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-sequence-clustering-mining-model-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="d178f-113">Обработка модели кластеризации последовательностей</span><span class="sxs-lookup"><span data-stu-id="d178f-113">Processing the Sequence Clustering Model</span></span>](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
-   [<span data-ttu-id="d178f-114">Изучение модели кластеризации последовательностей &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d178f-114">Exploring the Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="d178f-115">Создание связанной модели кластеризации последовательностей &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d178f-115">Creating a Related Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="d178f-116">Создание прогнозов на модели кластеризации последовательностей &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d178f-116">Creating Predictions on a Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-on-model-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d178f-117">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="d178f-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d178f-118">Создание структуры модели интеллектуального анализа кластеризации последовательностей &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d178f-118">Creating a Sequence Clustering Mining Model Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-sequence-clustering-mining-model-intermediate-data-mining.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="d178f-119">Все занятия</span><span class="sxs-lookup"><span data-stu-id="d178f-119">All Lessons</span></span>  
 [<span data-ttu-id="d178f-120">Занятие 1. Создание промежуточного решения интеллектуального анализа данных &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d178f-120">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="d178f-121">Занятие 2. Создание сценария прогнозирования &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d178f-121">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="d178f-122">Урок 3. Построение сценария покупательского поведения (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="d178f-122">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="d178f-123">Урок 4. Сценарий кластеризации последовательностей (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="d178f-123">Lesson 4: Sequence Clustering Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="d178f-124">Занятие 5. Построение моделей нейронной сети и логистической регрессии (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="d178f-124">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="d178f-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="d178f-125">See Also</span></span>  
 <span data-ttu-id="d178f-126">[Учебник по основам интеллектуального анализа данных](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="d178f-126">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="d178f-127">Учебник по интеллектуальному анализу данных &#40;Analysis Services — интеллектуальный анализ данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d178f-127">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
  
