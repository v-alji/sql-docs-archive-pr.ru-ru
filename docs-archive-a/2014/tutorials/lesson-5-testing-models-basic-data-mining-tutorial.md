---
title: Занятие 5. Тестирование моделей (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9a7ddcf-2b01-485f-bbb5-62638b303bc6
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: fcfd9a9e90d9c6800af4dfd1599bbdd62d9520ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734686"
---
# <a name="lesson-5-testing-models-basic-data-mining-tutorial"></a><span data-ttu-id="623fe-102">Занятие 5. Тестирование моделей (учебник по интеллектуальному анализу данных — базовый)</span><span class="sxs-lookup"><span data-stu-id="623fe-102">Lesson 5: Testing Models (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="623fe-103">После того как модель была обработана с использованием проверочного набора сценария прямой почтовой рассылки, модели необходимо проверить по проверочному набору.</span><span class="sxs-lookup"><span data-stu-id="623fe-103">Now that you have processed the model by using the targeted mailing scenario training set, you will test your models against the testing set.</span></span> <span data-ttu-id="623fe-104">Проверка — это важный шаг в процессе интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="623fe-104">Validation is an important step in the data mining process.</span></span> <span data-ttu-id="623fe-105">Очень важно выяснить, насколько хорошо модели интеллектуального анализа данных прямой почтовой рассылки работают с реальными данными, прежде чем выполнять их развертывание в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="623fe-105">Knowing how well your targeted mailing mining models perform against real data is important before you deploy the models into a production environment.</span></span>  
  
 <span data-ttu-id="623fe-106">Поскольку данные в проверочном наборе уже содержат известные значения для покупок велосипедов, очень просто определить, правильны ли полученные моделью прогнозы.</span><span class="sxs-lookup"><span data-stu-id="623fe-106">Because the data in the testing set already contains known values for bike buying, it is easy to determine whether the model's predictions are correct.</span></span> <span data-ttu-id="623fe-107">Модель, которая работает наилучшим образом, будет использоваться в [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] отделе маркетинга, чтобы определять клиентов для их кампании по целевой рассылке.</span><span class="sxs-lookup"><span data-stu-id="623fe-107">The model that performs the best will be used by the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing department to identify the customers for their targeted mailing campaign.</span></span>  
  
 <span data-ttu-id="623fe-108">На этом занятии вы проверите модели с помощью нескольких методов:</span><span class="sxs-lookup"><span data-stu-id="623fe-108">In this lesson you will validate your models using multiple methods:</span></span>  
  
1.  <span data-ttu-id="623fe-109">Вы сделаете прогнозы в проверочном наборе, чтобы увидеть, насколько точна модель на основе известных результатов.</span><span class="sxs-lookup"><span data-stu-id="623fe-109">You'll make predictions against the testing set to see how accurate the model is on known results.</span></span> <span data-ttu-id="623fe-110">Для измерения эффективности работы используется *Диаграмма точности прогнозов* .</span><span class="sxs-lookup"><span data-stu-id="623fe-110">You'll use a *lift chart* to measure its effectiveness.</span></span>  
  
     [<span data-ttu-id="623fe-111">Проверка точности с помощью диаграмм точности прогнозов (учебник интеллектуального анализа данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="623fe-111">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
2.  <span data-ttu-id="623fe-112">Вы проверите модели на отфильтрованном подмножестве данных.</span><span class="sxs-lookup"><span data-stu-id="623fe-112">You will test your models on a filtered subset of the data.</span></span> <span data-ttu-id="623fe-113">Можно сравнить несколько моделей в одной и той же диаграмме точности прогнозов.</span><span class="sxs-lookup"><span data-stu-id="623fe-113">You can compare multiple models in the same lift chart.</span></span>  
  
     [<span data-ttu-id="623fe-114">Тестирование фильтрованной модели &#40;учебник по интеллектуальному анализу данных (Basic)&#41;</span><span class="sxs-lookup"><span data-stu-id="623fe-114">Testing a Filtered Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-a-filtered-model-basic-data-mining-tutorial.md)  
  
 <span data-ttu-id="623fe-115">Дополнительные сведения о проверке модели в целом см. в разделе [Основные понятия интеллектуального анализа данных](../../2014/analysis-services/data-mining/data-mining-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="623fe-115">For more information about how model validation in general, see [Data Mining Concepts](../../2014/analysis-services/data-mining/data-mining-concepts.md).</span></span>  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="623fe-116">Первая задача занятия</span><span class="sxs-lookup"><span data-stu-id="623fe-116">First Task in Lesson</span></span>  
 [<span data-ttu-id="623fe-117">Проверка точности с помощью диаграмм точности прогнозов (учебник интеллектуального анализа данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="623fe-117">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="623fe-118">Предыдущее занятие</span><span class="sxs-lookup"><span data-stu-id="623fe-118">Previous Lesson</span></span>  
 [<span data-ttu-id="623fe-119">Занятие 4. изучение моделей целевой рассылки &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="623fe-119">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="623fe-120">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="623fe-120">Next Lesson</span></span>  
 [<span data-ttu-id="623fe-121">Занятие 6. Создание прогнозов и работа с ними (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="623fe-121">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="623fe-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="623fe-122">See Also</span></span>  
 <span data-ttu-id="623fe-123">[Вкладка диаграммы точности прогнозов &#40;представление диаграммы точности интеллектуального анализа данных&#41;](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md) </span><span class="sxs-lookup"><span data-stu-id="623fe-123">[Lift Chart Tab &#40;Mining Accuracy Chart View&#41;](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md) </span></span>  
 <span data-ttu-id="623fe-124">[Диаграмма точности прогнозов &#40;Analysis Services&#41;интеллектуального анализа данных](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="623fe-124">[Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="623fe-125">[Тестирование и проверка &#40;&#41;интеллектуального анализа данных](../../2014/analysis-services/data-mining/testing-and-validation-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="623fe-125">[Testing and Validation &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/testing-and-validation-data-mining.md) </span></span>  
 <span data-ttu-id="623fe-126">[Вкладка Матрица классификации &#40;представление диаграммы точности интеллектуального анализа данных&#41;](../../2014/analysis-services/classification-matrix-tab-mining-accuracy-chart-view.md) </span><span class="sxs-lookup"><span data-stu-id="623fe-126">[Classification Matrix Tab &#40;Mining Accuracy Chart View&#41;](../../2014/analysis-services/classification-matrix-tab-mining-accuracy-chart-view.md) </span></span>  
 [<span data-ttu-id="623fe-127">Матрица классификации (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="623fe-127">Classification Matrix &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/classification-matrix-analysis-services-data-mining.md)  
  
  
