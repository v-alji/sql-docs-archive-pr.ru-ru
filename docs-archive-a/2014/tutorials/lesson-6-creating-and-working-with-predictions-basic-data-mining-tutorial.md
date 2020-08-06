---
title: Занятие 6. Создание прогнозов и работа с ними (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b213cb58-2c40-4c89-b08b-d3c36a4afad3
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d0a8bfdf83e96622a19ac72490e8602d12afc9df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657425"
---
# <a name="lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial"></a><span data-ttu-id="327b6-102">Занятие 6. Создание прогнозов и работа с ними (учебник по интеллектуальному анализу данных — базовый)</span><span class="sxs-lookup"><span data-stu-id="327b6-102">Lesson 6: Creating and Working with Predictions (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="327b6-103">Предыдущий раздел был посвящен обучению работе с созданными моделями интеллектуального анализа данных, их проверке и изучению.</span><span class="sxs-lookup"><span data-stu-id="327b6-103">You have trained, tested, and explored the data mining models you created.</span></span> <span data-ttu-id="327b6-104">Теперь вы готовы к использованию моделей для определения людей, которые с наибольшей вероятностью откликнутся на новую кампанию целевой рассылки.</span><span class="sxs-lookup"><span data-stu-id="327b6-104">Now you are ready to use the models to identify the people most likely to respond to the new targeted mailing campaign.</span></span>  
  
 <span data-ttu-id="327b6-105">На этом занятии будет создан запрос, чтобы предсказать, какие клиенты наиболее склонны приобрести велосипед.</span><span class="sxs-lookup"><span data-stu-id="327b6-105">In this lesson you will create a query to predict which customers are most likely to purchase a bike.</span></span> <span data-ttu-id="327b6-106">Также будет извлекаться *вероятность* того, что прогноз будет правильным, поэтому отдел маркетинга сможет решить, следует ли использовать прогноз.</span><span class="sxs-lookup"><span data-stu-id="327b6-106">You will also retrieve the *probability* that the prediction is correct, so the marketing department can decide whether to you can decide whether to use the prediction or not.</span></span>  
  
 <span data-ttu-id="327b6-107">Определив клиентов, которые с наибольшей вероятностью склонны приобрести велосипед, необходимо выполнить детализацию сведений о вариантах, содержащихся в модели интеллектуального анализа данных, чтобы получить имена и контактные данные этих клиентов.</span><span class="sxs-lookup"><span data-stu-id="327b6-107">Once you have identified customers with a high probability of purchasing a bike, you will drill through to the details of the cases in the mining model to retrieve names and contact information for these customers.</span></span>  
  
 <span data-ttu-id="327b6-108">Это занятие содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="327b6-108">This lesson contains the following topics:</span></span>  
  
 [<span data-ttu-id="327b6-109">Создание прогнозов (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="327b6-109">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="327b6-110">Использование детализации в данных структуры &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="327b6-110">Using Drillthrough on Structure Data &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/using-drillthrough-on-structure-data-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="327b6-111">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="327b6-111">Next Lesson</span></span>  
 [<span data-ttu-id="327b6-112">Учебник по интеллектуальному анализу данных &#40;Analysis Services — интеллектуальный анализ данных&#41;</span><span class="sxs-lookup"><span data-stu-id="327b6-112">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="327b6-113">Предыдущее занятие</span><span class="sxs-lookup"><span data-stu-id="327b6-113">Previous Lesson</span></span>  
 [<span data-ttu-id="327b6-114">Занятие 5. Тестирование моделей &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="327b6-114">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="327b6-115">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="327b6-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="327b6-116">Создание прогнозов (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="327b6-116">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="327b6-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="327b6-117">See Also</span></span>  
 <span data-ttu-id="327b6-118">[Содержимое моделей интеллектуального анализа данных для моделей дерева принятия решений &#40;Analysis Services-Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-decision-tree-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="327b6-118">[Mining Model Content for Decision Tree Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-decision-tree-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="327b6-119">Создание прогнозирующего запроса с помощью построителя прогнозирующих запросов</span><span class="sxs-lookup"><span data-stu-id="327b6-119">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
