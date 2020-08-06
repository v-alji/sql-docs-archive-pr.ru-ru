---
title: Мастер оценки (надстройки интеллектуального анализа данных для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data modeling [data mining]
- estimation
ms.assetid: 7f2b1d5f-c9b3-4939-b35a-34ae099af15f
author: minewiskan
ms.author: owend
ms.openlocfilehash: ace9fa3a62690061677312d4f7dbb6b8a1d0ea5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734562"
---
# <a name="estimate-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="35e28-102">Мастер оценки (надстройки интеллектуального анализа данных для Excel)</span><span class="sxs-lookup"><span data-stu-id="35e28-102">Estimate Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="35e28-103">![Мастер оценки на ленте «Интеллектуальный анализ данных»](media/dmc-estimate.gif "Мастер оценки на ленте «Интеллектуальный анализ данных»")</span><span class="sxs-lookup"><span data-stu-id="35e28-103">![Estimate wizard in Data Mining ribbon](media/dmc-estimate.gif "Estimate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="35e28-104">Мастер **оценки** помогает создать модель оценки.</span><span class="sxs-lookup"><span data-stu-id="35e28-104">The **Estimate** wizard helps you create an estimation model.</span></span> <span data-ttu-id="35e28-105">Модель оценки извлекает из данных закономерности и использует их, чтобы прогнозировать факторы, влияющие на результаты.</span><span class="sxs-lookup"><span data-stu-id="35e28-105">An estimation model extracts patterns from data and uses the patterns to predict the factors that affect outcomes.</span></span>  
  
 <span data-ttu-id="35e28-106">Оценка используется для прогнозирования числовых результатов.</span><span class="sxs-lookup"><span data-stu-id="35e28-106">Estimation is used for predicting numeric outcomes.</span></span> <span data-ttu-id="35e28-107">Например, если в целевом столбце содержатся показатели окончания школы, указанные в процентах, можно проанализировать факторы, повышающие или снижающие показатели окончания, такие как количество учеников в школе, соотношение числа учеников и учителей и количество учителей.</span><span class="sxs-lookup"><span data-stu-id="35e28-107">For example, if your target column contains graduation rates for schools, with graduation rates expressed as percentages, you could analyze factors that potentially increase or decrease graduation rates, such as the number of students per school, the student-teacher ratio, and the number of teachers.</span></span>  
  
## <a name="using-the-estimate-data-wizard"></a><span data-ttu-id="35e28-108">Использование мастера оценки данных</span><span class="sxs-lookup"><span data-stu-id="35e28-108">Using the Estimate Data Wizard</span></span>  
  
1.  <span data-ttu-id="35e28-109">На ленте **интеллектуальный анализ данных** нажмите кнопку **оценить**.</span><span class="sxs-lookup"><span data-stu-id="35e28-109">On the **Data Mining** ribbon, click **Estimate**.</span></span>  
  
2.  <span data-ttu-id="35e28-110">В диалоговом окне **Выбор источника данных** выберите исходные данные для использования.</span><span class="sxs-lookup"><span data-stu-id="35e28-110">In the **Select Source Data** dialog box, select the source data to use.</span></span> <span data-ttu-id="35e28-111">Данные можно использовать в **таблицах**Excel, в **диапазоне данных**Excel или во **внешнем источнике данных**.</span><span class="sxs-lookup"><span data-stu-id="35e28-111">You can use data in an Excel **Table**, an Excel **Data Range**, or from an **External data source**.</span></span>  
  
     <span data-ttu-id="35e28-112">Если используется внешний источник данных, можно создать пользовательские представления или запросы и сохранить их как источник данных [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35e28-112">If you use an external data source, you can create custom views or queries and save them as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="35e28-113">В диалоговом окне **Оценка** выберите **столбец для анализа**.</span><span class="sxs-lookup"><span data-stu-id="35e28-113">In the **Estimation** dialog box, select the **Column to analyze**.</span></span>  
  
     <span data-ttu-id="35e28-114">В целевом столбце должны содержаться непрерывные числовые данные.</span><span class="sxs-lookup"><span data-stu-id="35e28-114">The target column must contain continuous numeric data.</span></span>  
  
4.  <span data-ttu-id="35e28-115">Выберите столбцы для использования в качестве входных данных, установив флажок **входные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="35e28-115">Select columns to use as input by checking the **Input columns** checkbox.</span></span>  
  
     <span data-ttu-id="35e28-116">Эти столбцы применяются для создания шаблонов.</span><span class="sxs-lookup"><span data-stu-id="35e28-116">These columns will be used to create the patterns.</span></span> <span data-ttu-id="35e28-117">Из анализа необходимо исключить столбцы, которые не смогут помочь, например номера идентификаторов или столбцы, содержащие несущественные данные.</span><span class="sxs-lookup"><span data-stu-id="35e28-117">You should eliminate from analysis any columns that are not likely to help, such as ID numbers, or columns that contain irrelevant data.</span></span>  
  
5.  <span data-ttu-id="35e28-118">Мастер **оценки** выбирает оптимальный алгоритм для набора данных.</span><span class="sxs-lookup"><span data-stu-id="35e28-118">The **Estimate** wizard selects the optimum algorithm for your data set.</span></span> <span data-ttu-id="35e28-119">Однако можно нажать кнопку **Параметры** , чтобы открыть диалоговое окно **Параметры алгоритма** и задать дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="35e28-119">However, you can click **Parameters** to open the **Algorithm Parameters** dialog box and set advanced options.</span></span>  
  
6.  <span data-ttu-id="35e28-120">Если данные являются числовыми и можно использовать метод линейной регрессии (Майкрософт), можно проверить поле **регрессии** для всех числовых столбцов, которые известно (или хорошо подозрительное) для корреляции с прогнозируемым значением.</span><span class="sxs-lookup"><span data-stu-id="35e28-120">If your data is numeric and you can use the Microsoft Linear Regression method, you can check the **Regressor** box for any numeric columns that you know (or strongly suspect) to be correlated with the predictable value.</span></span>  
  
     <span data-ttu-id="35e28-121">После этого алгоритм проверит значения в указанном столбце и определит, влияют ли они на исход.</span><span class="sxs-lookup"><span data-stu-id="35e28-121">The algorithm will then test the values in that column to determine if they affect the outcomes.</span></span> <span data-ttu-id="35e28-122">Если вы не уверены, нажмите кнопку **предложить** , и алгоритм проверит все столбцы и автоматически определит лучшие значения для использования в качестве регрессий.</span><span class="sxs-lookup"><span data-stu-id="35e28-122">If you are unsure, click **Suggest** and the algorithm will test all column and automatically detect the best values to use as regressors.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="35e28-123">Регрессор требуется для создания оценки.</span><span class="sxs-lookup"><span data-stu-id="35e28-123">A regressor is required to create an estimate.</span></span> <span data-ttu-id="35e28-124">Мастер всегда рекомендует лучший регрессор на основе начального прохода по данным.</span><span class="sxs-lookup"><span data-stu-id="35e28-124">The wizard always recommends the best regressor, based on an initial pass over the data.</span></span> <span data-ttu-id="35e28-125">Поэтому, если нет полной уверенности в правильности выбора, лучше принять рекомендованные варианты выбора.</span><span class="sxs-lookup"><span data-stu-id="35e28-125">Therefore, if you are not sure, it is best to accept the recommended selections.</span></span>  
  
7.  <span data-ttu-id="35e28-126">На странице **разделение данных на обучающий и проверочный наборы** укажите, следует ли создать небольшое подмножество данных для тестирования.</span><span class="sxs-lookup"><span data-stu-id="35e28-126">On the **Split data into training and testing sets** page, specify whether you want to create a small subset of the data for testing.</span></span>  
  
8.  <span data-ttu-id="35e28-127">На странице **Готово** укажите имена для новой структуры интеллектуального анализа данных и режима интеллектуального анализа данных или примите указанные имена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="35e28-127">On the **Finish** page, provide names for the new mining structure and mining mode, or accept the default names that are provided.</span></span>  
  
9. <span data-ttu-id="35e28-128">Задайте параметры для использования модели.</span><span class="sxs-lookup"><span data-stu-id="35e28-128">Set options for using the model.</span></span>  
  
    -   <span data-ttu-id="35e28-129">Нажмите кнопку **Обзор** , чтобы немедленно открыть модель в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="35e28-129">Select **Browse** to immediately open the model in a viewer.</span></span>  
  
         <span data-ttu-id="35e28-130">Средство графического просмотра отображает диаграмму сети зависимостей и дерево принятия решений, формируемые алгоритмом.</span><span class="sxs-lookup"><span data-stu-id="35e28-130">This graphical viewer displays a dependency network graph and the decision tree generated by the algorithm.</span></span> <span data-ttu-id="35e28-131">Изучая эти данные, можно глубже понять, какие факторы внесли свой вклад в оцениваемые значения.</span><span class="sxs-lookup"><span data-stu-id="35e28-131">By exploring this information, you can better understand the factors that contribute to the estimated values.</span></span>  
  
    -   <span data-ttu-id="35e28-132">Выберите **включить детализацию** , чтобы разрешить пользователям анализа просматривать базовые данные.</span><span class="sxs-lookup"><span data-stu-id="35e28-132">Select **Enable drillthrough** to let users of your analysis view the underlying data.</span></span>  
  
         <span data-ttu-id="35e28-133">Этот параметр доступен только при использовании алгоритма дерева принятия решений или алгоритма линейной регрессии.</span><span class="sxs-lookup"><span data-stu-id="35e28-133">This option is available only if you use the Decision Trees opr Linear Regression algorithms.</span></span>  
  
    -   <span data-ttu-id="35e28-134">**Использовать временную модель**.</span><span class="sxs-lookup"><span data-stu-id="35e28-134">**Use temporary model**.</span></span> <span data-ttu-id="35e28-135">Если выбрать этот параметр, модель не будет сохранена на сервере.</span><span class="sxs-lookup"><span data-stu-id="35e28-135">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="35e28-136">Временные модели удаляются при закрытии Excel.</span><span class="sxs-lookup"><span data-stu-id="35e28-136">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-estimation-models"></a><span data-ttu-id="35e28-137">Дополнительные сведения о моделях оценки</span><span class="sxs-lookup"><span data-stu-id="35e28-137">More About Estimation Models</span></span>  
 <span data-ttu-id="35e28-138">Мастер **оценки** поддерживает использование любого из следующих алгоритмов:</span><span class="sxs-lookup"><span data-stu-id="35e28-138">The **Estimate** wizard supports the use of any of the following algorithms:</span></span>  
  
-   <span data-ttu-id="35e28-139">Алгоритм дерева принятия решений (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="35e28-139">Microsoft Decision Tree algorithm</span></span>  
  
-   <span data-ttu-id="35e28-140">Алгоритм линейной регрессии (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="35e28-140">Microsoft Linear Regression algorithm</span></span>  
  
-   <span data-ttu-id="35e28-141">Алгоритм логистической регрессии (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="35e28-141">Microsoft Logistic Regression algorithm</span></span>  
  
-   <span data-ttu-id="35e28-142">Алгоритм нейронной сети (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="35e28-142">Microsoft Neural network algorithm</span></span>  
  
 <span data-ttu-id="35e28-143">В диалоговом окне **Параметры алгоритма** можно задать дополнительные дополнительные параметры в зависимости от выбранного алгоритма.</span><span class="sxs-lookup"><span data-stu-id="35e28-143">In the **Algorithm Parameters** dialog box, you can set additional advanced options, depending on which algorithm you chose.</span></span> <span data-ttu-id="35e28-144">Подробные сведения о параметрах для каждого из алгоритмов см. в следующих разделах электронной документации по SQL Server:</span><span class="sxs-lookup"><span data-stu-id="35e28-144">For information on the options for each algorithm see these topics in SQL Server Books Online:</span></span>  
  
 [<span data-ttu-id="35e28-145">Технический справочник по алгоритму дерева принятия решений (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="35e28-145">Microsoft Decision Trees Algorithm Technical Reference</span></span>](data-mining/microsoft-decision-trees-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="35e28-146">Технический справочник по алгоритму линейной регрессии (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="35e28-146">Microsoft Linear Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-linear-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="35e28-147">техническом справочнике по алгоритму логистической регрессии (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="35e28-147">Microsoft Logistic Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-logistic-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="35e28-148">Технический справочник по алгоритму нейронной сети (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="35e28-148">Microsoft Neural Network Algorithm Technical Reference</span></span>](data-mining/microsoft-neural-network-algorithm-technical-reference.md)  
  
### <a name="requirements"></a><span data-ttu-id="35e28-149">Требования</span><span class="sxs-lookup"><span data-stu-id="35e28-149">Requirements</span></span>  
 <span data-ttu-id="35e28-150">Чтобы использовать мастер оценки данных, необходимо установить соединение с базой данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35e28-150">To use the Estimate Data Wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="35e28-151">Сведения о создании подключения см. в разделе [Подключение к источнику данных &#40;клиент интеллектуального анализа данных для Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="35e28-151">For information about how to create a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="35e28-152">Чтобы использовать алгоритм оценки, результат, который требуется предсказать, должен быть выражен в виде числового значения, например валюты, объема продаж, даты или времени.</span><span class="sxs-lookup"><span data-stu-id="35e28-152">To use the estimation algorithm, the outcome that you are trying to predict must be expressed as a numeric value, such as a currency, sales amount, date, or time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35e28-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="35e28-153">See Also</span></span>  
 <span data-ttu-id="35e28-154">[Создание модели интеллектуального анализа данных](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="35e28-154">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="35e28-155">Пошаговое руководство по диаграмме дерева решений &#40;надстроек интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="35e28-155">Decision Tree Diagram Walkthrough  &#40;Data Mining Add-ins&#41;</span></span>](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
  
