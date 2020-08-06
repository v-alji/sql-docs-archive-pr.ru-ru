---
title: Проверка моделей и использование моделей для прогнозирования (надстройки интеллектуального анализа данных для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, validating
- mining models, charting
- validation [data mining]
- mining models, testing
ms.assetid: e245ac1f-1230-48e9-9091-e70b131aa2a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: c1dd4f9bab977a90579076b824d2c0aa525c84af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657919"
---
# <a name="validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel"></a><span data-ttu-id="b0443-102">Проверка моделей и использование моделей для прогнозирования (надстройки интеллектуального анализа данных для Excel)</span><span class="sxs-lookup"><span data-stu-id="b0443-102">Validating Models and Using Models for Prediction (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="b0443-103">Проверка модели — это важный шаг в процессе интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="b0443-103">Testing and validating your model is an important step in the data mining process.</span></span> <span data-ttu-id="b0443-104">Знать то, насколько хорошо работают с реальными данными используемые модели интеллектуального анализа, важно еще до того, как модели будут развернуты в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="b0443-104">You must know how well your mining models perform against real data before you deploy the models into a production environment.</span></span>  
  
 <span data-ttu-id="b0443-105">Надстройки интеллектуального анализа данных содержат средства, позволяющие проверять созданные модели и создавать прогнозы и рекомендации с использованием моделей.</span><span class="sxs-lookup"><span data-stu-id="b0443-105">The Data Mining Add-ins include tools that help you test the models you built, and create predictions and recommendations using the models.</span></span>  
  
## <a name="accuracy-chart"></a><span data-ttu-id="b0443-106">Диаграмма точности</span><span class="sxs-lookup"><span data-stu-id="b0443-106">Accuracy Chart</span></span>  
 <span data-ttu-id="b0443-107">Мастер **диаграмм точности** помогает создать прогнозирующий запрос и оценить производительность модели интеллектуального анализа данных, создав диаграмму точности прогнозов или точечную диаграмму.</span><span class="sxs-lookup"><span data-stu-id="b0443-107">The **Accuracy Chart** wizard helps you create a prediction query and assess the performance of a data mining model by creating a lift chart or scatter plot chart.</span></span> <span data-ttu-id="b0443-108">Диаграммы точности прогнозов различают модели в структуре, которые являются почти одинаковыми, что позволяет выявить модель с наилучшей точностью прогнозов.</span><span class="sxs-lookup"><span data-stu-id="b0443-108">The lift chart helps distinguish between models in a structure that are almost the same, to help you determine which model provides the best predictions.</span></span>  
  
 [<span data-ttu-id="b0443-109">Диаграмма точности &#40;SQL Server надстроек интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="b0443-109">Accuracy Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](accuracy-chart-sql-server-data-mining-add-ins.md)  
  
## <a name="classification-matrix"></a><span data-ttu-id="b0443-110">Матрица классификации</span><span class="sxs-lookup"><span data-stu-id="b0443-110">Classification Matrix</span></span>  
 <span data-ttu-id="b0443-111">Мастер **матрицы классификации** помогает создать прогнозирующий запрос для оценки производительности модели классификации.</span><span class="sxs-lookup"><span data-stu-id="b0443-111">The **Classification Matrix** wizard helps you create a prediction query to assess the performance of a classification model.</span></span> <span data-ttu-id="b0443-112">Окончательная диаграмма содержит как точные, так и неточные прогнозы, выполненные моделью.</span><span class="sxs-lookup"><span data-stu-id="b0443-112">The output is a chart that summarizes both accurate and inaccurate predictions made by the model.</span></span> <span data-ttu-id="b0443-113">Матрица полезна, поскольку она отображает не только то, как часто модель прогнозировала верное значение, но и то, какие значения чаще всего прогнозируются неправильно.</span><span class="sxs-lookup"><span data-stu-id="b0443-113">The matrix is a valuable tool because it not only shows how frequently the model correctly predicted a value, but also shows which values the model most frequently predicted incorrectly.</span></span>  
  
 [<span data-ttu-id="b0443-114">Матрица классификации &#40;SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="b0443-114">Classification Matrix &#40;SQL Server Data Mining Add-ins&#41;</span></span>](classification-matrix-sql-server-data-mining-add-ins.md)  
  
## <a name="profit-chart"></a><span data-ttu-id="b0443-115">Диаграмма роста прибыли</span><span class="sxs-lookup"><span data-stu-id="b0443-115">Profit Chart</span></span>  
 <span data-ttu-id="b0443-116">Мастер **диаграмм роста прибыли** помогает взвесить преимущества использования модели интеллектуального анализа данных и оценить стоимость ложных срабатываний и ложных отрицательных результатов.</span><span class="sxs-lookup"><span data-stu-id="b0443-116">The **Profit Chart** wizard helps you weigh the benefits of using a data mining model and assess the costs of both false positives and false negatives</span></span>  
  
 <span data-ttu-id="b0443-117">Этот тип диаграммы измеряет точность прогноза модели и использует заданную единицу измерения и общие расходы.</span><span class="sxs-lookup"><span data-stu-id="b0443-117">This chart type measures the prediction accuracy of the model and incorporates unit and overall costs that you specify.</span></span>  
  
 <span data-ttu-id="b0443-118">[Диаграмма роста прибыли &#40;SQL Server надстройки интеллектуального анализа данных&#41;](profit-chart-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="b0443-118">[Profit Chart &#40;SQL Server Data Mining Add-ins&#41;](profit-chart-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="cross-validation"></a><span data-ttu-id="b0443-119">Перекрестная проверка</span><span class="sxs-lookup"><span data-stu-id="b0443-119">Cross-Validation</span></span>  
 <span data-ttu-id="b0443-120">Перекрестная проверка — это общепринятый метод в сообществе интеллектуального анализа данных для оценки допустимости набора данных и точности модели интеллектуального анализа данных для того или иного набора данных.</span><span class="sxs-lookup"><span data-stu-id="b0443-120">Cross-validation is an established technique in the data mining community for assessing the validity of a data set and the accuracy of a mining model on that data set.</span></span> <span data-ttu-id="b0443-121">Этот метод разбивает набор данных на подмножества, а затем последовательно создает, обучает и тестирует модели в каждом подмножестве.</span><span class="sxs-lookup"><span data-stu-id="b0443-121">It divides a set of data into subsets, and then iteratively creates, trains, and tests models on each subset.</span></span>  
  
 <span data-ttu-id="b0443-122">Мастер **перекрестной проверки** позволяет указать число сверток для разделения данных, а затем предоставляет отчет о перекрестной проверке, который статистически описывает различия между этими перекрестными разделами.</span><span class="sxs-lookup"><span data-stu-id="b0443-122">The **Cross-Validation** wizard lets you specify the number of folds to divide your data by, and then provides a cross-validation report that statistically describes the differences among these cross-sections.</span></span> <span data-ttu-id="b0443-123">На основании этого отчета можно определить, хорошо ли работает модель на всех обучающих данных, или она скошена к конкретному подмножеству.</span><span class="sxs-lookup"><span data-stu-id="b0443-123">From this you can determine whether the model performs well on all training data, or might be skewed to a particular subset.</span></span>  
  
 [<span data-ttu-id="b0443-124">&#40;перекрестной проверки SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="b0443-124">Cross-Validation &#40;SQL Server Data Mining Add-ins&#41;</span></span>](cross-validation-sql-server-data-mining-add-ins.md)  
  
## <a name="query-wizard"></a><span data-ttu-id="b0443-125">Мастер запросов</span><span class="sxs-lookup"><span data-stu-id="b0443-125">Query Wizard</span></span>  
 <span data-ttu-id="b0443-126">Мастер **запросов** — это интерактивное средство, помогающее создать прогнозирующий запрос.</span><span class="sxs-lookup"><span data-stu-id="b0443-126">The **Query** wizard is an interactive tool that helps you build a prediction query.</span></span> <span data-ttu-id="b0443-127">Запросы определяют способ создания рекомендаций, будущих прогнозов и т. д.</span><span class="sxs-lookup"><span data-stu-id="b0443-127">Queries are how you generate recommendations, future forecasts, and so forth.</span></span>  
  
 <span data-ttu-id="b0443-128">В мастере **запросов** выбирается модель, а затем предоставляются входные данные либо в виде отдельных значений, либо из таблицы или диапазона, а мастер помогает выбрать столбцы для вывода.</span><span class="sxs-lookup"><span data-stu-id="b0443-128">In the **Query** wizard, you pick a model, and then provide input data, either as single values or from a table or range, and the wizard helps you select columns to output.</span></span> <span data-ttu-id="b0443-129">Функции можно также добавить в запрос для формирования оценок вероятностей и другой полезной статистики.</span><span class="sxs-lookup"><span data-stu-id="b0443-129">You can also add functions to your query to generate probability scores and other useful statistics.</span></span>  
  
 [<span data-ttu-id="b0443-130">&#40;запросов SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="b0443-130">Query &#40;SQL Server Data Mining Add-ins&#41;</span></span>](query-sql-server-data-mining-add-ins.md)  
  
## <a name="advanced-query-editor"></a><span data-ttu-id="b0443-131">Расширенный редактор запросов</span><span class="sxs-lookup"><span data-stu-id="b0443-131">Advanced Query Editor</span></span>  
 <span data-ttu-id="b0443-132">**Расширенный редактор запросов** — это интерактивный набор диалоговых окон, позволяющий создавать все виды инструкций расширений интеллектуального анализа данных, от выполнения пользовательских запросов до создания и обучения новых моделей, удаления моделей или создания новых наборов данных.</span><span class="sxs-lookup"><span data-stu-id="b0443-132">The **Advanced Query Editor** is an interactive set of dialog boxes that helps you build all kinds of DMX statements, anything from running custom queries to creating and training new models, deleting models, or creating new data sets.</span></span>  
  
 [<span data-ttu-id="b0443-133">Расширенный редактор запросов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="b0443-133">Advanced Data Mining Query Editor</span></span>](advanced-data-mining-query-editor.md)  
  
## <a name="see-also"></a><span data-ttu-id="b0443-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="b0443-134">See Also</span></span>  
 <span data-ttu-id="b0443-135">[Изучение и очистка данных](exploring-and-cleaning-data.md) </span><span class="sxs-lookup"><span data-stu-id="b0443-135">[Exploring and Cleaning Data](exploring-and-cleaning-data.md) </span></span>  
 <span data-ttu-id="b0443-136">[Создание модели интеллектуального анализа данных](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="b0443-136">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="b0443-137">Развертывание и масштабирование моделей интеллектуального анализа &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="b0443-137">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
