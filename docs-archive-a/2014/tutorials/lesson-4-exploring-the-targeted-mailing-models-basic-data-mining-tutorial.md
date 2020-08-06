---
title: Занятие 4. изучение моделей целевой рассылки (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1e00c5b9-a9f8-4503-99ee-377c9cc02d7f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 8659350b126164e06550acdbecec04bb07499c55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735622"
---
# <a name="lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial"></a><span data-ttu-id="72c64-102">Занятие 4. изучение моделей целевой рассылки (учебник по интеллектуальному анализу данных — базовый)</span><span class="sxs-lookup"><span data-stu-id="72c64-102">Lesson 4: Exploring the Targeted Mailing Models (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="72c64-103">После обработки моделей в проекте их можно просмотреть, чтобы найти интересные тенденции.</span><span class="sxs-lookup"><span data-stu-id="72c64-103">After the models in your project have been processed, you can explore them to look for interesting trends.</span></span> <span data-ttu-id="72c64-104">Поскольку закономерности могут быть сложными и сложными, просто просмотрев числа, SQL Server интеллектуальный анализ данных предоставляет некоторые визуальные средства, помогающие исследовать данные и понять правила и связи, обнаруженные алгоритмами в данных.</span><span class="sxs-lookup"><span data-stu-id="72c64-104">Because patterns can be complex and difficult simply by looking at numbers, SQL Server Data Mining provides some visual tools that help you investigate the data and understand the rules and relationships that the algorithms have discovered within the data.</span></span> <span data-ttu-id="72c64-105">Вы также можете использовать различные проверки точности для проверки набора данных или определения модели, которая лучше работает перед развертыванием.</span><span class="sxs-lookup"><span data-stu-id="72c64-105">You can also use a variety of accuracy tests to validate your dataset or discover which model performs best before you deploy it.</span></span>  
  
 <span data-ttu-id="72c64-106">При использовании [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для просмотра моделей каждая созданная модель отображается на вкладке **средство просмотра моделей интеллектуального анализа** данных в конструкторе интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="72c64-106">When you use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to explore your models, each model you created is listed in the **Mining Model Viewer** tab in Data Mining Designer.</span></span> <span data-ttu-id="72c64-107">Для исследования моделей можно использовать средства просмотра.</span><span class="sxs-lookup"><span data-stu-id="72c64-107">You can use the viewers to explore the models.</span></span> <span data-ttu-id="72c64-108">Эти средства просмотра также доступны в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72c64-108">These viewers are also available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="72c64-109">Различные алгоритмы, используемые для создания модели в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], возвращают результаты разных типов.</span><span class="sxs-lookup"><span data-stu-id="72c64-109">Each algorithm that you used to build a model in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] returns a different type of result.</span></span> <span data-ttu-id="72c64-110">Поэтому [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] предоставляет пользовательские средства просмотра для каждого типа модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="72c64-110">Therefore, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides custom viewers for each type of machine learning model.</span></span>  
  
 <span data-ttu-id="72c64-111">Если вы хотите получить подробные сведения, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] также предоставляет средство просмотра HTML-страниц, называемое **средством просмотра деревьев содержимого общего вида**, которое отображает подробные сведения о данных модели и всех найденных закономерностях в нетабличном формате.</span><span class="sxs-lookup"><span data-stu-id="72c64-111">If you want to get into details, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] also provides an HTML viewer, called the **Generic Content Tree Viewer**, that displays detailed information about the model data and any patterns that were found, in a semi-tabular format.</span></span> <span data-ttu-id="72c64-112">Дополнительные сведения см. в разделе [Просмотр модели в средстве просмотра деревьев содержимого общего вида (Майкрософт)](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="72c64-112">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span></span>  
  
 <span data-ttu-id="72c64-113">На этом занятии будут рассмотрены результаты из трех моделей.</span><span class="sxs-lookup"><span data-stu-id="72c64-113">In this lesson you will look at the results from your three models.</span></span> <span data-ttu-id="72c64-114">Каждый тип модели основан на отдельном алгоритме и позволяет рассмотреть эти данные с различных точек зрения.</span><span class="sxs-lookup"><span data-stu-id="72c64-114">Each model type is based on a different algorithm and provides different insights into the data.</span></span>  
  
-   <span data-ttu-id="72c64-115">Модель дерева принятия решений содержит сведения о факторах, влияющих на покупку велосипеда.</span><span class="sxs-lookup"><span data-stu-id="72c64-115">The Decision Tree model tells you about factors that influence bike buying.</span></span>  
  
-   <span data-ttu-id="72c64-116">Модель кластеризации группирует клиентов по атрибутам, включающим их поведение при покупке велосипеда, и другие выбранные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="72c64-116">The Clustering model groups your customers by attributes that include their bike buying behavior and other selected attributes.</span></span>  
  
-   <span data-ttu-id="72c64-117">Модель упрощенного алгоритма Байеса позволяет исследовать связь между различными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="72c64-117">The Naive Bayes model enables you to explore the relationship between different attributes.</span></span>  
  
 <span data-ttu-id="72c64-118">Дополнительные сведения о каждом средстве просмотра модели интеллектуального анализа данных см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="72c64-118">See the following topics to learn more about each of the mining model viewers.</span></span>  
  
-   [<span data-ttu-id="72c64-119">Изучение модели дерева принятия решений &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="72c64-119">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="72c64-120">Изучение модели кластеризации &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="72c64-120">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="72c64-121">Обзор модели упрощенного алгоритма Байеса &#40;учебнике по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="72c64-121">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
 <span data-ttu-id="72c64-122">Все три модели можно просмотреть с помощью **средства просмотра деревьев содержимого общего вида**, чтобы извлечь формулы, значения данных и т. д.</span><span class="sxs-lookup"><span data-stu-id="72c64-122">All three models can be viewed using the **Generic Content Tree Viewer**, to extract formulas, data values, and so forth.</span></span>  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="72c64-123">Первая задача занятия</span><span class="sxs-lookup"><span data-stu-id="72c64-123">First Task in Lesson</span></span>  
 [<span data-ttu-id="72c64-124">Изучение модели дерева принятия решений &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="72c64-124">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="72c64-125">Предыдущее занятие</span><span class="sxs-lookup"><span data-stu-id="72c64-125">Previous Lesson</span></span>  
 [<span data-ttu-id="72c64-126">Урок 3. Добавление и обработка моделей</span><span class="sxs-lookup"><span data-stu-id="72c64-126">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="72c64-127">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="72c64-127">Next Lesson</span></span>  
 [<span data-ttu-id="72c64-128">Занятие 5. Тестирование моделей &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="72c64-128">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="72c64-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="72c64-129">See Also</span></span>  
 <span data-ttu-id="72c64-130">[Задачи и инструкции средства просмотра моделей интеллектуального анализа данных](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="72c64-130">[Mining Model Viewer Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="72c64-131">Средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="72c64-131">Data Mining Model Viewers</span></span>](../../2014/analysis-services/data-mining/data-mining-model-viewers.md)  
  
  
