---
title: Конструктор интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], structure
- mining structures [Analysis Services], modifying
- data mining editor [Analysis Services]
- Data Mining Designer
- data mining [Analysis Services], modifying
ms.assetid: 2540db5b-2bf3-4b6c-87c8-79c48d71acce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 820cde158dfabff525081060369daace0e83c8dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655442"
---
# <a name="data-mining-designer"></a><span data-ttu-id="9a835-102">Конструктора моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9a835-102">Data Mining Designer</span></span>
  <span data-ttu-id="9a835-103">Конструктор интеллектуального анализа данных — это основная среда, в которой можно работать с моделями интеллектуального анализа в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a835-103">Data Mining Designer is the primary environment in which you work with mining models in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="9a835-104">Чтобы получить доступ к конструктору, выберите элемент существующей структуры интеллектуального анализа данных либо создайте новую структуру или модель интеллектуального анализа с помощью мастера интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9a835-104">You can access the designer either by selecting an existing mining structure, or by using the Data Mining Wizard to create a new mining structure and mining model.</span></span> <span data-ttu-id="9a835-105">Конструктор интеллектуального анализа данных можно использовать для выполнения следующих задач.</span><span class="sxs-lookup"><span data-stu-id="9a835-105">You can use Data Mining Designer to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="9a835-106">Изменение структуры и модели интеллектуального анализа, ранее созданных при помощи мастера интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9a835-106">Modify the mining structure and the mining model that were initially created by the Data Mining Wizard.</span></span>  
  
-   <span data-ttu-id="9a835-107">Создание новых моделей на основе существующей структуры интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="9a835-107">Create new models based on an existing mining structure.</span></span>  
  
-   <span data-ttu-id="9a835-108">Обучение и просмотр моделей интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="9a835-108">Train and browse mining models.</span></span>  
  
-   <span data-ttu-id="9a835-109">Сравнение моделей при помощи диаграммы точности.</span><span class="sxs-lookup"><span data-stu-id="9a835-109">Compare models by using accuracy charts.</span></span>  
  
-   <span data-ttu-id="9a835-110">Создание прогнозирующих запросов на основе моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9a835-110">Create prediction queries based on mining models.</span></span>  
  
## <a name="mining-structure-tab"></a><span data-ttu-id="9a835-111">Вкладка «Структура интеллектуального анализа данных»</span><span class="sxs-lookup"><span data-stu-id="9a835-111">Mining Structure Tab</span></span>  
 <span data-ttu-id="9a835-112">Добавление столбцов и изменение свойств существующей структуры интеллектуального анализа данных производится на вкладке **Структура интеллектуального анализа** .</span><span class="sxs-lookup"><span data-stu-id="9a835-112">Use the **Mining Structure** tab to add columns and modify the properties of an existing mining structure.</span></span> <span data-ttu-id="9a835-113">В следующих заданиях и подразделах приведены более подробные сведения о работе со структурами интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="9a835-113">The following tasks and topics provide more information about working with mining structures:</span></span>  
  
 [<span data-ttu-id="9a835-114">Структуры интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="9a835-114">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](mining-structures-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="9a835-115">Задачи и инструкции по структуре интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9a835-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
## <a name="mining-models-tab"></a><span data-ttu-id="9a835-116">Вкладка «Модели интеллектуального анализа данных»</span><span class="sxs-lookup"><span data-stu-id="9a835-116">Mining Models Tab</span></span>  
 <span data-ttu-id="9a835-117">Вкладка **Модели интеллектуального анализа данных** предназначена для управления существующими моделями интеллектуального анализа и создания новых моделей.</span><span class="sxs-lookup"><span data-stu-id="9a835-117">Use the **Mining Models** tab to manage existing mining models and to create new models.</span></span> <span data-ttu-id="9a835-118">Модели интеллектуального анализа данных всегда основаны на существующей структуре интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="9a835-118">Mining models are always based on an existing mining structure .</span></span>  
  
 <span data-ttu-id="9a835-119">На вкладке **Модели интеллектуального анализа данных** можно изменить тип алгоритма, добавить или удалить столбцы, связанные со структурой интеллектуального анализа, настроить характерные для каждого алгоритма свойства столбца, определить использование столбца модели интеллектуального анализа и настроить параметры алгоритма, связанные с моделью интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="9a835-119">In the **Mining Models** tab, you can change the algorithm type, add or remove columns that are associated with the model structure, adjust algorithm-specific column properties, specify the mining model column usage, and adjust algorithm parameters that are associated with the mining model.</span></span> <span data-ttu-id="9a835-120">Кроме того, можно обработать структуру интеллектуального анализа данных вместе с выбранными или всеми связанными моделями.</span><span class="sxs-lookup"><span data-stu-id="9a835-120">You can also process the mining structure together with selected models or with all the associated models.</span></span>  
  
 <span data-ttu-id="9a835-121">Дополнительные сведения о работе с моделями интеллектуального анализа данных см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="9a835-121">See the following topics for more information about working with mining models:</span></span>  
  
 [<span data-ttu-id="9a835-122">Модели интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="9a835-122">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="9a835-123">Задачи и инструкции по модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9a835-123">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
## <a name="mining-model-viewer-tab"></a><span data-ttu-id="9a835-124">Вкладка «Средство просмотра модели интеллектуального анализа данных»</span><span class="sxs-lookup"><span data-stu-id="9a835-124">Mining Model Viewer Tab</span></span>  
 <span data-ttu-id="9a835-125">Вкладка **Средство просмотра модели интеллектуального анализа данных** применяется для визуального изучения моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9a835-125">Use the **Mining Model Viewer** tab to visually explore your mining models.</span></span> <span data-ttu-id="9a835-126">Каждая модель интеллектуального анализа связана с пользовательским средством просмотра, которое отображает характерное для модели содержимое.</span><span class="sxs-lookup"><span data-stu-id="9a835-126">Each mining model is associated with a custom viewer that displays content that is specific to that model.</span></span> <span data-ttu-id="9a835-127">Модель интеллектуального анализа данных также можно изучать с помощью средства просмотра содержимого.</span><span class="sxs-lookup"><span data-stu-id="9a835-127">You can also view mining model content by using the content viewer.</span></span>  
  
 <span data-ttu-id="9a835-128">Дополнительные сведения об исследовании моделей интеллектуального анализа с помощью просмотрщиков см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="9a835-128">See the following topics for more information about exploring mining models with the data mining viewers:</span></span>  
  
 [<span data-ttu-id="9a835-129">Средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9a835-129">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
 [<span data-ttu-id="9a835-130">Задачи и инструкции средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9a835-130">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
## <a name="mining-accuracy-chart-tab"></a><span data-ttu-id="9a835-131">Вкладка «Диаграмма точности интеллектуального анализа»</span><span class="sxs-lookup"><span data-stu-id="9a835-131">Mining Accuracy Chart Tab</span></span>  
 <span data-ttu-id="9a835-132">Вкладка **Диаграмма точности интеллектуального анализа данных** позволяет проверить точность прогнозов отдельной модели интеллектуального анализа или сравнить эффективность нескольких моделей из одной структуры интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="9a835-132">Use the **Mining Accuracy Chart** tab to test the predictive accuracy of a single mining model, or to compare the effectiveness of multiple mining models contained within a mining structure.</span></span> <span data-ttu-id="9a835-133">Вкладка содержит средства для фильтрации данных, выбора моделей интеллектуального анализа данных и отображения результатов в виде диаграммы точности прогнозов, диаграммы прибыльности или матрицы классификации.</span><span class="sxs-lookup"><span data-stu-id="9a835-133">The tab contains tools for filtering the data, selecting mining models, and displaying the results in a lift chart, profit chart, or classification matrix.</span></span>  
  
 <span data-ttu-id="9a835-134">Дополнительные сведения о тестировании и проверке моделей интеллектуального анализа данных см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="9a835-134">See the following topics for more information about testing and validating mining models:</span></span>  
  
 [<span data-ttu-id="9a835-135">Тестирование и проверка (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="9a835-135">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
 [<span data-ttu-id="9a835-136">Задачи и решения по тестированию и проверке (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="9a835-136">Testing and Validation Tasks and How-tos &#40;Data Mining&#41;</span></span>](testing-and-validation-tasks-and-how-tos-data-mining.md)  
  
## <a name="mining-model-prediction-tab"></a><span data-ttu-id="9a835-137">Вкладка «Прогноз модели интеллектуального анализа данных»</span><span class="sxs-lookup"><span data-stu-id="9a835-137">Mining Model Prediction Tab</span></span>  
 <span data-ttu-id="9a835-138">Вкладка **Прогноз модели интеллектуального анализа данных** содержит построитель прогнозирующих запросов, который применяется для создания запроса прогнозов расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9a835-138">The **Mining Model Prediction** tab includes Prediction Query Builder, which you can use to create a Data Mining Extensions (DMX) prediction query.</span></span> <span data-ttu-id="9a835-139">Вкладка содержит средства, которые позволяют указать модели интеллектуального анализа и входные таблицы, сопоставить столбцы модели интеллектуального анализа столбцам во входных таблицах, добавить функции в запрос и указать условие для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="9a835-139">The tab contains tools for specifying mining models and input tables, mapping the columns in the mining model to columns in the input table, adding functions to a query, and specifying criteria for each column.</span></span>  
  
 <span data-ttu-id="9a835-140">После построения запроса можно использовать различные средства просмотра этой вкладки для проверки результатов запроса и изменения запроса вручную.</span><span class="sxs-lookup"><span data-stu-id="9a835-140">After you design a query, you can use different views in the tab to display the results of the query and to modify the query manually.</span></span> <span data-ttu-id="9a835-141">Результат запроса можно сохранить в таблицу базы данных.</span><span class="sxs-lookup"><span data-stu-id="9a835-141">You can also save the results of the query to a table in a database.</span></span>  
  
 <span data-ttu-id="9a835-142">Дополнительные сведения о создании запросов интеллектуального анализа данных см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="9a835-142">See the following topics for more information about creating data mining queries:</span></span>  
  
 [<span data-ttu-id="9a835-143">Запросы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9a835-143">Data Mining Queries</span></span>](data-mining-queries.md)  
  
 [<span data-ttu-id="9a835-144">Задачи и инструкции по запросам интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9a835-144">Data Mining Query Tasks and How-tos</span></span>](data-mining-query-tasks-and-how-tos.md)  
  
## <a name="see-also"></a><span data-ttu-id="9a835-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a835-145">See Also</span></span>  
 [<span data-ttu-id="9a835-146">Решения интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9a835-146">Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
  
