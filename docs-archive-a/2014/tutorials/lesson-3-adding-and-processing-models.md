---
title: Занятие 3. Добавление и обработка моделей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: cc29927a-c368-4b8a-bbd0-af89a9f54dc9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 5da034089d8bbe7f1a967258d195a56ddbf13c03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655461"
---
# <a name="lesson-3-adding-and-processing-models"></a><span data-ttu-id="05683-102">Урок 3. Добавление и обработка моделей</span><span class="sxs-lookup"><span data-stu-id="05683-102">Lesson 3: Adding and Processing Models</span></span>
  <span data-ttu-id="05683-103">Структура интеллектуального анализа данных, созданная на предыдущем занятии, содержит одну модель интеллектуального анализа данных, основанную на [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритме дерева принятия решений.</span><span class="sxs-lookup"><span data-stu-id="05683-103">The mining structure that you created in the previous lesson contains a single mining model that is based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="05683-104">Эту модель можно использовать для идентификации заказчиков для кампании целевой рассылки.</span><span class="sxs-lookup"><span data-stu-id="05683-104">You can use this model to identify customers for the targeted mailing campaign.</span></span> <span data-ttu-id="05683-105">Однако для обеспечения надлежащей тщательности анализа рекомендуется создавать связанные модели с помощью других алгоритмов и сравнивать их результаты.</span><span class="sxs-lookup"><span data-stu-id="05683-105">However, to ensure that your analysis is thorough, it is a common practice to create related models using different algorithms and compare their results.</span></span> <span data-ttu-id="05683-106">Таким образом, вы сможете лучше разобраться в сути вопроса.</span><span class="sxs-lookup"><span data-stu-id="05683-106">That way you can get different insights as well.</span></span> <span data-ttu-id="05683-107">Следовательно необходимо создать две дополнительные модели, а затем выполнить их обработку и развертывание.</span><span class="sxs-lookup"><span data-stu-id="05683-107">Therefore, you will create two additional models, then process and deploy the models.</span></span>  
  
 <span data-ttu-id="05683-108">На этом занятии будет создан набор моделей интеллектуального анализа данных, с помощью которых можно будет выбрать наиболее подходящих заказчиков из списка всех потенциальных заказчиков.</span><span class="sxs-lookup"><span data-stu-id="05683-108">In this lesson, you will create a set of mining models that will suggest the most likely customers from a list of potential customers.</span></span>  
  
 <span data-ttu-id="05683-109">Для выполнения задач этого занятия будет использоваться [алгоритм кластеризации (Майкрософт](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) ) и [упрощенный алгоритм Байеса (Майкрософт](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md)).</span><span class="sxs-lookup"><span data-stu-id="05683-109">To complete the tasks in this lesson, you will use the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) and the [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md).</span></span>  
  
 <span data-ttu-id="05683-110">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="05683-110">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="05683-111">Добавление новых моделей в структуру целевой рассылки &#40;базовое руководство по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="05683-111">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="05683-112">Руководство по обработке моделей в структуре целевой рассылки &#40;базовом руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="05683-112">Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="05683-113">Первая задача занятия</span><span class="sxs-lookup"><span data-stu-id="05683-113">First Task in Lesson</span></span>  
 [<span data-ttu-id="05683-114">Добавление новых моделей в структуру целевой рассылки &#40;базовое руководство по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="05683-114">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="05683-115">Предыдущее занятие</span><span class="sxs-lookup"><span data-stu-id="05683-115">Previous Lesson</span></span>  
 [<span data-ttu-id="05683-116">Занятие 2. Создание структуры целевой рассылки &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="05683-116">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="05683-117">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="05683-117">Next Lesson</span></span>  
 [<span data-ttu-id="05683-118">Занятие 4. изучение моделей целевой рассылки &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="05683-118">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="05683-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="05683-119">See Also</span></span>  
 [<span data-ttu-id="05683-120">Добавление моделей интеллектуального анализа данных в структуру (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="05683-120">Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md)  
  
  
