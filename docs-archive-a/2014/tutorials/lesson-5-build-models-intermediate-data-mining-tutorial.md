---
title: Занятие 5. Создание моделей нейронной сети и логистической регрессии (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- logistic regression [Analysis Services]
- data mining [Analysis Services], tutorials
- neural networks
- tutorials [Data Mining]
- neural network model [Analysis Services]
ms.assetid: 42c3701a-1fd2-44ff-b7de-377345bbbd6b
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a8c9fcf0380582f15fa2bf30d6fdeb97bb2ab1fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658579"
---
# <a name="lesson-5-building-neural-network-and-logistic-regression-models-intermediate-data-mining-tutorial"></a><span data-ttu-id="ede3a-102">Занятие 5. Создание моделей нейронной сети и логистической регрессии (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="ede3a-102">Lesson 5: Building Neural Network and Logistic Regression Models (Intermediate Data Mining Tutorial)</span></span>
  
  
 <span data-ttu-id="ede3a-103">Отдел эксплуатации [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] занимается улучшением качества обслуживания клиентов в центре обработки звонков.</span><span class="sxs-lookup"><span data-stu-id="ede3a-103">The Operations department of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] is engaged in a project to improve customer satisfaction with their call center.</span></span> <span data-ttu-id="ede3a-104">Они наняли поставщика для управления центром обработки звонков и составлении отчетов о  производительности этого центра, и просят провести анализ предварительных данных, предоставленных поставщиком.</span><span class="sxs-lookup"><span data-stu-id="ede3a-104">They hired a vendor to manage the call center and to report metrics on call center effectiveness, and have asked you to analyze some preliminary data provided by the vendor.</span></span> <span data-ttu-id="ede3a-105">Они хотят узнать, если будут какие-либо интересные факты.</span><span class="sxs-lookup"><span data-stu-id="ede3a-105">They want to know if there are any interesting findings.</span></span> <span data-ttu-id="ede3a-106">В частности, они хотели бы знать, свидетельствуют ли эти данные о проблемах с кадрами и можно ли на основе этих данных выбрать способ улучшения качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="ede3a-106">In particular, they would like to know if the data suggests any staffing problems with staffing or ways to improve customer satisfaction.</span></span>  
  
 <span data-ttu-id="ede3a-107">Набор данных небольшой и содержит только тридцатидневный период работы центра обработки вызовов.</span><span class="sxs-lookup"><span data-stu-id="ede3a-107">The data set is small and covers only a 30-day period in the operation of the call center.</span></span> <span data-ttu-id="ede3a-108">Данные отслеживают количество новых и опытных операторов в каждой смене, количество входящих звонков и количество заказов, а также проблемы, которые необходимо устранить, и среднее время ожидания ответа для клиента.</span><span class="sxs-lookup"><span data-stu-id="ede3a-108">The data tracks the number of new and experienced operators in each shift, the number of incoming calls, the number of orders as well as issues that must be resolved, and the average time a customer waits for someone to respond to a call.</span></span> <span data-ttu-id="ede3a-109">Данные также включают метрику качества обслуживания, вычисленную по *показателю прекращенных звонков*, отражающему степень недовольства клиента.</span><span class="sxs-lookup"><span data-stu-id="ede3a-109">The data also includes a service quality metric based on *abandon rate*, which is an indicator of customer frustration.</span></span>  
  
 <span data-ttu-id="ede3a-110">Так как нет никаких предположений о том, что покажут эти данные, принимается решение использовать модель нейронной сети для исследования возможных корреляций.</span><span class="sxs-lookup"><span data-stu-id="ede3a-110">Because you do not have any prior expectations about what the data will show, you decide to use a neural network model to explore possible correlations.</span></span> <span data-ttu-id="ede3a-111">Модели нейронных сетей часто используются для исследования, так как они могут анализировать сложные связи между множеством входов и выходов.</span><span class="sxs-lookup"><span data-stu-id="ede3a-111">Neural network models are often used for exploration because they can analyze complex relationships between many inputs and outputs.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="ede3a-112">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="ede3a-112">What You Will Learn</span></span>  
 <span data-ttu-id="ede3a-113">На этом занятии будет использоваться алгоритм нейронной сети для построения модели, которую можно использовать для понимания трендов в данных.</span><span class="sxs-lookup"><span data-stu-id="ede3a-113">In this lesson, you will use the neural network algorithm to build a model that you and the Operations team can use to understand the trends in the data.</span></span> <span data-ttu-id="ede3a-114">Как часть этого занятия, вы попытаетесь ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="ede3a-114">As part of this lesson, you will try to answer the following questions:</span></span>  
  
-   <span data-ttu-id="ede3a-115">Какие факторы влияют на удовлетворенность заказчика?</span><span class="sxs-lookup"><span data-stu-id="ede3a-115">What factors affect customer satisfaction?</span></span>  
  
-   <span data-ttu-id="ede3a-116">Что может сделать центр обработки вызовов для повышения показателя обслуживания?</span><span class="sxs-lookup"><span data-stu-id="ede3a-116">What can the call center do to improve service quality?</span></span>  
  
 <span data-ttu-id="ede3a-117">На основе результатов будет построена модель логистической регрессии, которую можно использовать для прогнозов.</span><span class="sxs-lookup"><span data-stu-id="ede3a-117">Based on the results, you will then build a logistic regression model that you can use for predictions.</span></span> <span data-ttu-id="ede3a-118">Отдел эксплуатации будет использовать прогнозы как вспомогательное средство при планировании работы центра обработки звонков.</span><span class="sxs-lookup"><span data-stu-id="ede3a-118">The predictions will be used by the Operations team as an aid in planning call center operation.</span></span>  
  
 <span data-ttu-id="ede3a-119">Это занятие содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="ede3a-119">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="ede3a-120">Добавление представления источников данных для центра обработки вызовов &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede3a-120">Adding a Data Source View for Call Center Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-data-source-view-call-center-data-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="ede3a-121">Руководство по созданию структуры нейронной сети и модели &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede3a-121">Creating a Neural Network Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-neural-network-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ede3a-122">Руководство по использованию модели центра обработки вызовов &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede3a-122">Exploring the Call Center Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-call-center-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ede3a-123">Добавление модели логистической регрессии в учебник центра обработки вызовов &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede3a-123">Adding a Logistic Regression Model to the Call Center Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-logistic-regression-model-to-call-center-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="ede3a-124">Создание прогнозов для моделей центра обработки вызовов &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede3a-124">Creating Predictions for the Call Center Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-call-center-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ede3a-125">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="ede3a-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ede3a-126">Добавление представления источников данных для центра обработки вызовов &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede3a-126">Adding a Data Source View for Call Center Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-data-source-view-call-center-data-intermediate-data-mining.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="ede3a-127">Все занятия</span><span class="sxs-lookup"><span data-stu-id="ede3a-127">All Lessons</span></span>  
 [<span data-ttu-id="ede3a-128">Занятие 1. Создание промежуточного решения интеллектуального анализа данных &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede3a-128">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="ede3a-129">Занятие 2. Создание сценария прогнозирования &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede3a-129">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="ede3a-130">Урок 3. Построение сценария покупательского поведения (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="ede3a-130">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="ede3a-131">Занятие 4. Создание сценария кластеризации последовательностей &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede3a-131">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 <span data-ttu-id="ede3a-132">Урок 5. Сценарий нейронной сети и логистической регрессии (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="ede3a-132">Lesson 5: Neural Network and Logistic Regression Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede3a-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="ede3a-133">See Also</span></span>  
 <span data-ttu-id="ede3a-134">[Учебник по основам интеллектуального анализа данных](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="ede3a-134">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="ede3a-135">Учебник по интеллектуальному анализу данных &#40;Analysis Services — интеллектуальный анализ данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede3a-135">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
  
