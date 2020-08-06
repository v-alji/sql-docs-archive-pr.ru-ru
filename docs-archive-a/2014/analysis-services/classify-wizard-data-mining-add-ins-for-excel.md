---
title: Мастер классификации (надстройки интеллектуального анализа данных для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data modeling [data mining]
- classification [data mining]
ms.assetid: 409c5076-c4c3-4f09-8f30-d3297df45f13
author: minewiskan
ms.author: owend
ms.openlocfilehash: b82fc98df10ae2e6754a378dacea108f9f3379ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656784"
---
# <a name="classify-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="8e6bf-102">Мастер классификации (надстройки интеллектуального анализа данных для Excel)</span><span class="sxs-lookup"><span data-stu-id="8e6bf-102">Classify Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="8e6bf-103">![Мастер классификации на ленте «Интеллектуальный анализ данных»](media/dmc-classify.gif "Мастер классификации на ленте «Интеллектуальный анализ данных»")</span><span class="sxs-lookup"><span data-stu-id="8e6bf-103">![Classify wizard in Data Mining ribbon](media/dmc-classify.gif "Classify wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="8e6bf-104">Мастер **классификации** помогает построить модель классификации на основе существующих данных в таблице Excel, диапазоне Excel или внешнем источнике данных.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-104">The **Classify** wizard helps you build a classification model based on existing data in an Excel table, an Excel range, or an external data source.</span></span>  
  
 <span data-ttu-id="8e6bf-105">Модель классификации извлекает из данных шаблоны, которые свидетельствуют о наличии схожести в данных, и помогает делать прогнозы, основываясь на группированиях данных.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-105">A classification model extracts patterns in your data that indicate similarities and helps you make predictions based on groupings of values.</span></span> <span data-ttu-id="8e6bf-106">Например, модель классификации можно использовать для прогнозирования рисков на основе шаблонов доходов или расходов.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-106">For example, a classification model might be used to predict risk based on income or spending patterns.</span></span>  
  
## <a name="using-the-classify-wizard"></a><span data-ttu-id="8e6bf-107">Использование мастера классификации</span><span class="sxs-lookup"><span data-stu-id="8e6bf-107">Using the Classify Wizard</span></span>  
  
1.  <span data-ttu-id="8e6bf-108">На ленте **интеллектуальный анализ данных** щелкните **классификация**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-108">In the **Data Mining** ribbon, click **Classify**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="8e6bf-109">На странице **Выбор источника данных** выберите данные для анализа.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-109">In the **Select Source Data** page, choose the data to analyze.</span></span>  
  
     <span data-ttu-id="8e6bf-110">Этот мастер поддерживает несколько типов данных: таблицы Excel, диапазоны Excel и внешние источники данных.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-110">This wizard supports multiple kinds of data: Excel tables, Excel ranges, and external data sources.</span></span> <span data-ttu-id="8e6bf-111">При использовании внешних данных можно либо добавить их в Excel, либо выбрать набор таблиц или представлений в источнике данных Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-111">With external data, you can either add it into Excel, or choose a set of tables or views in an Analysis Services data source.</span></span> <span data-ttu-id="8e6bf-112">Также можно добавлять таблицы и изменять столбцы для создания нерегламентированных источников данных.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-112">You can also add tables and change columns to create ad hoc data sources.</span></span>  
  
3.  <span data-ttu-id="8e6bf-113">На странице **классификация** выберите столбец, который необходимо классифицировать.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-113">On the **Classification** page, choose the column that you want to classify.</span></span>  
  
     <span data-ttu-id="8e6bf-114">Проверьте столбцы в списке, **входные столбцы**и отмените выбор столбцов, имеющих уникальные значения, и не рекомендуется для создания шаблонов, таких как номера идентификаторов, имена клиентов и т. д.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-114">Review the columns in the list, **Input columns**, and deselect any columns that have unique values and thus aren't useful for creating patterns, such as ID numbers, customer names, and so on.</span></span> <span data-ttu-id="8e6bf-115">Также следует удалить столбцы, в основном повторяющие классифицируемый столбец.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-115">You should also remove columns that essentially duplicate the classifiable column.</span></span>  
  
     <span data-ttu-id="8e6bf-116">Например, если классифицируется прогноз категории продукта, следует исключить поле подкатегории, если имеется известное бизнес-правило, иначе сила этого правила может не дать обнаружить другие корреляции.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-116">For example, if you are classifying predicting the category of a product, you should exclude the subcategory field if there is a known business rule, or else the strength of that rule might prevent you from discovering other correlations.</span></span>  
  
4.  <span data-ttu-id="8e6bf-117">При необходимости нажмите кнопку **Параметры** , чтобы изменить параметры алгоритма и настроить поведение модели кластеризации.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-117">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the clustering model.</span></span>  
  
5.  <span data-ttu-id="8e6bf-118">На странице **разделение данных на обучающий и проверочный наборы** укажите объем данных для тестирования.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-118">In the **Split data into training and testing sets** page, specify how much data to hold out for testing.</span></span> <span data-ttu-id="8e6bf-119">Остаток всегда используется для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-119">The remainder is always used for training the model.</span></span>  
  
     <span data-ttu-id="8e6bf-120">Значение по умолчанию — 30 % для проверочных данных и 70 % для обучения.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-120">The default setting is 30% testing data and 70% training data.</span></span>  
  
6.  <span data-ttu-id="8e6bf-121">На странице **Готово** укажите описательное имя для набора данных и модели и задайте следующие параметры, определяющие способ работы с готовой моделью.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-121">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="8e6bf-122">**Обзор модели**.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-122">**Browse model**.</span></span> <span data-ttu-id="8e6bf-123">Если выбран этот параметр, то после того, как мастер закончит обработку модели, откроется окно **обзора** , в котором можно просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-123">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="8e6bf-124">Содержимое средства просмотра зависит от типа создаваемой модели.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-124">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="8e6bf-125">Дополнительные сведения см. в статьях [Просмотр модели дерева принятия решений](browsing-a-decision-trees-model.md) и [Просмотр модели нейронной сети](browsing-a-neural-network-model.md).</span><span class="sxs-lookup"><span data-stu-id="8e6bf-125">For more information, see [Browsing a Decision Trees Model](browsing-a-decision-trees-model.md) and [Browsing a Neural Network Model](browsing-a-neural-network-model.md).</span></span>  
  
    -   <span data-ttu-id="8e6bf-126">**Включить детализацию**.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-126">**Enable drillthrough**.</span></span> <span data-ttu-id="8e6bf-127">Выберите этот параметр, чтобы просмотреть базовые данные из созданной модели.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-127">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="8e6bf-128">Этот параметр доступен только для модели «дерево принятия решений».</span><span class="sxs-lookup"><span data-stu-id="8e6bf-128">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="8e6bf-129">**Использовать временную модель**.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-129">**Use temporary model**.</span></span> <span data-ttu-id="8e6bf-130">Если выбрать этот параметр, модель не будет сохранена на сервере.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-130">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="8e6bf-131">Временные модели удаляются при закрытии Excel.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-131">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-classification-models"></a><span data-ttu-id="8e6bf-132">Дополнительные сведения о моделях классификации</span><span class="sxs-lookup"><span data-stu-id="8e6bf-132">More About Classification Models</span></span>  
 <span data-ttu-id="8e6bf-133">В диалоговом окне **Параметры алгоритма** можно также выбрать метод классификации из следующих алгоритмов, предоставленных в Analysis Services:</span><span class="sxs-lookup"><span data-stu-id="8e6bf-133">In the **Algorithm Parameters** dialog box, you can also choose the classification method from among these algorithms provided in Analysis Services:</span></span>  
  
-   <span data-ttu-id="8e6bf-134">Алгоритм дерева принятия решений Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8e6bf-134">Microsoft Decision Tree</span></span>  
  
-   <span data-ttu-id="8e6bf-135">Алгоритм логистической регрессии Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8e6bf-135">Microsoft Logistic Regression</span></span>  
  
-   <span data-ttu-id="8e6bf-136">Упрощенный алгоритм Байеса (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="8e6bf-136">Microsoft Naïve Bayes</span></span>  
  
-   <span data-ttu-id="8e6bf-137">Алгоритм нейронной сети Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8e6bf-137">Microsoft Neural Network</span></span>  
  
 <span data-ttu-id="8e6bf-138">Хотя алгоритмы могут дать сходные результаты, они анализируют данные по-разному, поэтому рекомендуем попробовать несколько алгоритмов и сравнить результаты.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-138">Although the algorithms might yield similar results, they analyze the data differently, so we recommend trying several algorithms and comparing the results.</span></span> <span data-ttu-id="8e6bf-139">Метод по умолчанию — алгоритм деревьев принятия решений (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="8e6bf-139">The default method is Microsoft Decision Trees.</span></span>  
  
 <span data-ttu-id="8e6bf-140">В списке **Параметры** можно изменить дополнительные параметры, которые зависят от выбранного типа алгоритма.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-140">In the **Parameters** list, you can change advanced options, which depend on the type of algorithm you choose.</span></span> <span data-ttu-id="8e6bf-141">Параметры для каждого из алгоритмов подробнее описаны в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-141">The parameters for each algorithm are described in more detail in SQL Server Books Online.</span></span>  
  
 [<span data-ttu-id="8e6bf-142">Технический справочник по алгоритму дерева принятия решений (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="8e6bf-142">Microsoft Decision Trees Algorithm Technical Reference</span></span>](data-mining/microsoft-decision-trees-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="8e6bf-143">техническом справочнике по алгоритму логистической регрессии (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="8e6bf-143">Microsoft Logistic Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-logistic-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="8e6bf-144">Технический справочник по упрощенному алгоритму Байеса (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="8e6bf-144">Microsoft Naive Bayes Algorithm Technical Reference</span></span>](data-mining/microsoft-naive-bayes-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="8e6bf-145">Технический справочник по алгоритму нейронной сети (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="8e6bf-145">Microsoft Neural Network Algorithm Technical Reference</span></span>](data-mining/microsoft-neural-network-algorithm-technical-reference.md)  
  
### <a name="requirements"></a><span data-ttu-id="8e6bf-146">Требования</span><span class="sxs-lookup"><span data-stu-id="8e6bf-146">Requirements</span></span>  
 <span data-ttu-id="8e6bf-147">Чтобы использовать мастер **классификации** , необходимо подключиться к [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="8e6bf-147">To use the **Classify** wizard, you must be connected to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="8e6bf-148">Сведения о создании подключения см. в разделе [Подключение к источнику данных &#40;клиент интеллектуального анализа данных для Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8e6bf-148">For information about how to create a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e6bf-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e6bf-149">See Also</span></span>  
 [<span data-ttu-id="8e6bf-150">Создание модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="8e6bf-150">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
