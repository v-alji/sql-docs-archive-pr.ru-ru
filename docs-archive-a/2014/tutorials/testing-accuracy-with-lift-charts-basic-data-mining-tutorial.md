---
title: Проверка точности с помощью диаграмм точности прогнозов (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 822d414b-4a39-473f-80c3-53476e30655a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7a3dcdd1d1b78911f5ffd37a383532abdd4814c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734637"
---
# <a name="testing-accuracy-with-lift-charts-basic-data-mining-tutorial"></a><span data-ttu-id="7ac6a-102">Проверка точности при помощи диаграмм точности прогнозов (учебник интеллектуального анализа данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="7ac6a-102">Testing Accuracy with Lift Charts (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="7ac6a-103">На вкладке **Диаграмма точности интеллектуального анализа** конструктора интеллектуального анализа данных можно вычислить, насколько хорошо каждая из моделей выполняет прогнозы, и сравнивать результаты каждой модели непосредственно с результатами других моделей.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-103">On the **Mining Accuracy Chart** tab of Data Mining Designer, you can calculate how well each of your models makes predictions, and compare the results of each model directly against the results of the other models.</span></span> <span data-ttu-id="7ac6a-104">Этот метод сравнения называется *диаграммой точности прогнозов*.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-104">This method of comparison is referred to as a *lift chart*.</span></span> <span data-ttu-id="7ac6a-105">Обычно точность прогнозирования модели интеллектуального анализа данных определяется либо точностью предсказания, либо точностью классификации.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-105">Typically, the predictive accuracy of a mining model is measured by either lift or classification accuracy.</span></span> <span data-ttu-id="7ac6a-106">В данном учебнике используются только диаграммы точности прогнозов.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-106">For this tutorial we will use the lift chart only.</span></span>  
  
 <span data-ttu-id="7ac6a-107">В этом разделе будут выполнены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="7ac6a-107">In this topic, you will perform the following tasks:</span></span>  
  
-   [<span data-ttu-id="7ac6a-108">Выбор входных данных</span><span class="sxs-lookup"><span data-stu-id="7ac6a-108">Choose the Input Data</span></span>](#BKMK_InputData)  
  
-   [<span data-ttu-id="7ac6a-109">Настройка параметров диаграммы точности</span><span class="sxs-lookup"><span data-stu-id="7ac6a-109">Configure Accuracy Chart Parameters</span></span>](#BKMK_Selecting)  
  
##  <a name="choosing-the-input-data"></a><a name="BKMK_InputData"></a><span data-ttu-id="7ac6a-110">Выбор входных данных</span><span class="sxs-lookup"><span data-stu-id="7ac6a-110">Choosing the Input Data</span></span>  
 <span data-ttu-id="7ac6a-111">Первым шагом в проверке точности моделей интеллектуального анализа данных является выбор источника данных, который будет использоваться для проверки.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-111">The first step in testing the accuracy of your mining models is to select the data source that you will use for testing.</span></span> <span data-ttu-id="7ac6a-112">Будет проверено, насколько хорошо работают модели на проверочных данных, а затем эти модели будут использованы с внешними данными.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-112">You will test how well the models perform against your testing data and then you will use them with external data.</span></span>  
  
#### <a name="to-select-the-data-set"></a><span data-ttu-id="7ac6a-113">Выбор набора данных</span><span class="sxs-lookup"><span data-stu-id="7ac6a-113">To select the data set</span></span>  
  
1.  <span data-ttu-id="7ac6a-114">Перейдите на вкладку **Диаграмма точности интеллектуального анализа** в конструкторе интеллектуального анализа данных в [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] и выберите вкладку **Выбор входа** .</span><span class="sxs-lookup"><span data-stu-id="7ac6a-114">Switch to the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and select the **Input Selection** tab.</span></span>  
  
2.  <span data-ttu-id="7ac6a-115">В поле **выберите набор данных для использования в группе диаграмм точности** выберите **использовать проверочные варианты структуры интеллектуального анализа**.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-115">In the **Select data set to be used for Accuracy Chart** group box, select **Use mining structure test cases**.</span></span> <span data-ttu-id="7ac6a-116">Это проверочные данные, которые задаются при создании структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-116">This is the testing data that you set aside when you created the mining structure.</span></span>  
  
     <span data-ttu-id="7ac6a-117">Дополнительные сведения о других параметрах см. в разделе [Выбор типа диаграммы точности и установка параметров диаграммы](../../2014/analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md).</span><span class="sxs-lookup"><span data-stu-id="7ac6a-117">For more information on the other options, see [Choose an Accuracy Chart Type and Set Chart Options](../../2014/analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md).</span></span>  
  
##  <a name="setting-accuracy-chart-parameters"></a><a name="BKMK_Selecting"></a><span data-ttu-id="7ac6a-118">Настройка параметров диаграммы точности</span><span class="sxs-lookup"><span data-stu-id="7ac6a-118">Setting Accuracy Chart Parameters</span></span>  
 <span data-ttu-id="7ac6a-119">Чтобы создать диаграмму точности, необходимо определить три вещи:</span><span class="sxs-lookup"><span data-stu-id="7ac6a-119">To create an accuracy chart, you must define three things:</span></span>  
  
-   <span data-ttu-id="7ac6a-120">Какие модели следует включить в диаграмму точности?</span><span class="sxs-lookup"><span data-stu-id="7ac6a-120">Which models should you include in the accuracy chart?</span></span>  
  
-   <span data-ttu-id="7ac6a-121">Какой прогнозируемый атрибут требуется измерить?</span><span class="sxs-lookup"><span data-stu-id="7ac6a-121">Which predictable attribute do you want to measure?</span></span> <span data-ttu-id="7ac6a-122">Некоторые модели могут иметь несколько целевых объектов, но каждая диаграмма может измерять только один результат за раз.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-122">Some models might have multiple targets, but each chart can measure only one outcome at a time.</span></span>  
  
     <span data-ttu-id="7ac6a-123">Для использования столбца в качестве **прогнозируемого имени столбца** в диаграмме точности столбцы должны иметь тип использования `Predict` или `Predict Only` .</span><span class="sxs-lookup"><span data-stu-id="7ac6a-123">To use a column as the **Predictable Column Name** in an accuracy chart, the columns must have the usage type of `Predict` or `Predict Only`.</span></span> <span data-ttu-id="7ac6a-124">Кроме того, тип содержимого целевого столбца должен быть либо `Discrete` или `Discretized` .</span><span class="sxs-lookup"><span data-stu-id="7ac6a-124">Also, the content type of the target column must be either `Discrete` or `Discretized`.</span></span> <span data-ttu-id="7ac6a-125">Иными словами, нельзя измерять точность для непрерывных числовых выходов с помощью диаграммы точности прогнозов.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-125">In other words, you cannot measure accuracy against continuous numeric outputs using the lift chart.</span></span>  
  
-   <span data-ttu-id="7ac6a-126">Вы хотите измерить общую точность модели или ее точность при прогнозировании определенного значения (например, [Покупатель велосипеда] = ' Да ')</span><span class="sxs-lookup"><span data-stu-id="7ac6a-126">Do you want to measure the model's general accuracy, or its accuracy  in predicting a particular value (such as [Bike Buyer] = 'Yes')</span></span>  
  
#### <a name="to-generate-the-lift-chart"></a><span data-ttu-id="7ac6a-127">Создание диаграммы точности прогнозов</span><span class="sxs-lookup"><span data-stu-id="7ac6a-127">To generate the lift chart</span></span>  
  
1.  <span data-ttu-id="7ac6a-128">На вкладке **Выбор входа** конструктора интеллектуального анализа данных в разделе **Выбор прогнозируемых столбцов модели интеллектуального анализа для отображения на диаграмме точности**прогнозов установите флажок **синхронизировать прогнозируемые столбцы и значения**.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-128">On the **Input Selection** tab of Data Mining Designer, under **Select predictable mining model columns to show in the lift chart**, select the checkbox for **Synchronize Prediction Columns and Values**.</span></span>  
  
2.  <span data-ttu-id="7ac6a-129">Убедитесь, что в столбце **имя прогнозируемого столбца** выбрано значение **Покупатель велосипеда** для каждой модели.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-129">In the **Predictable Column Name** column, verify that **Bike Buyer** is selected for each model.</span></span>  
  
3.  <span data-ttu-id="7ac6a-130">В столбце **Показывать** выберите каждую из моделей.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-130">In the **Show** column, select each of the models.</span></span>  
  
     <span data-ttu-id="7ac6a-131">По умолчанию выбраны все модели в структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-131">By default, all the models in the mining structure are selected.</span></span> <span data-ttu-id="7ac6a-132">Можно выбрать любую из моделей, однако в данном учебнике следует оставить выбранными все модели.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-132">You can decide not to include a model, but for this tutorial leave all the models selected.</span></span>  
  
4.  <span data-ttu-id="7ac6a-133">В столбце **значение прогноза** выберите **1**.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-133">In the **Predict Value** column, select **1**.</span></span> <span data-ttu-id="7ac6a-134">То же значение автоматически вводится для каждой модели, имеющей такой же прогнозируемый столбец.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-134">The same value is automatically filled in for each model that has the same predictable column.</span></span>  
  
5.  <span data-ttu-id="7ac6a-135">Перейдите на вкладку **Диаграмма точности прогнозов** .</span><span class="sxs-lookup"><span data-stu-id="7ac6a-135">Select the **Lift Chart** tab.</span></span>  
  
     <span data-ttu-id="7ac6a-136">При нажатии на вкладку выполняется прогнозирующий запрос для получения прогнозов для тестовых данных, а результаты сравниваются с известными значениями.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-136">When you click the tab, a prediction query is executed to get predictions for the test data, and the results are compared against the known values.</span></span> <span data-ttu-id="7ac6a-137">Результаты выводятся в виде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-137">The results are plotted on the graph.</span></span>  
  
     <span data-ttu-id="7ac6a-138">Если вы указали конкретный целевой результат с помощью параметра **Прогноз значения** , на диаграмме точности прогнозов отображаются результаты случайных прогнозов и результаты идеальной модели.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-138">If you specified a particular target outcome using the **Predict Value** option, the lift chart plots the results of random guesses and the results of an ideal model.</span></span>  
  
    -   <span data-ttu-id="7ac6a-139">В строке случайного предположения показано, насколько точна модель без использования каких-либо данных для информирования своих прогнозов: то есть 50-50 разбивается между двумя результатами.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-139">The random guess line shows how accurate the model would be without using any data to inform its predictions: that is, a 50-50 split between two outcomes.</span></span> <span data-ttu-id="7ac6a-140">Диаграмма точности прогнозов позволяет визуализировать, насколько эффективнее работает модель в сравнении с произвольным предположением.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-140">The lift chart helps you visualize how much better your model performs in comparison to a random guess.</span></span>  
  
    -   <span data-ttu-id="7ac6a-141">Идеальная линия модели представляет верхнюю границу точности.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-141">The ideal model line represents the upper bound of accuracy.</span></span> <span data-ttu-id="7ac6a-142">Он показывает максимально возможное преимущество, которое можно достигнуть, если модель всегда прогнозируется точно.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-142">It shows you the maximum possible benefit you could achieve if your model always predicted accurately.</span></span>  
  
     <span data-ttu-id="7ac6a-143">Созданные модели интеллектуального анализа данных, как правило, находятся между этими двумя крайними значениями.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-143">The mining models you created will usually fall between these two extremes.</span></span> <span data-ttu-id="7ac6a-144">Любое улучшение от случайного предположения считается *приподнятым*.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-144">Any improvement from the random guess is considered to be *lift*.</span></span>  
  
6.  <span data-ttu-id="7ac6a-145">Для нахождения линий, представляющих идеальную модель и модель случайного выбора, используйте условные обозначения.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-145">Use the legend to locate the colored lines representing the Ideal Model and the Random Guess Model.</span></span>  
  
     <span data-ttu-id="7ac6a-146">Вы заметите, что `TM_Decision_Tree` модель обеспечивает наибольший прогноз, использующий модели упрощенного алгоритма кластеризации и Байеса.</span><span class="sxs-lookup"><span data-stu-id="7ac6a-146">You'll notice that the `TM_Decision_Tree` model provides the greatest lift,  outperforming both the Clustering and Naive Bayes models.</span></span>  
  
 <span data-ttu-id="7ac6a-147">Подробное описание диаграммы точности прогнозов, подобной созданной на этом занятии, см. в разделе [Диаграмма точности прогнозов &#40;Analysis Services-&#41;интеллектуального анализа данных ](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="7ac6a-147">For an in-depth explanation of a lift chart similar to the one created in this lesson, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7ac6a-148">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="7ac6a-148">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7ac6a-149">Тестирование фильтрованной модели &#40;учебник по интеллектуальному анализу данных (Basic)&#41;</span><span class="sxs-lookup"><span data-stu-id="7ac6a-149">Testing a Filtered Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-a-filtered-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="7ac6a-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="7ac6a-150">See Also</span></span>  
 <span data-ttu-id="7ac6a-151">[Диаграмма точности прогнозов &#40;Analysis Services&#41;интеллектуального анализа данных](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7ac6a-151">[Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="7ac6a-152">Вкладка диаграммы точности прогнозов &#40;представление диаграммы точности интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7ac6a-152">Lift Chart Tab &#40;Mining Accuracy Chart View&#41;</span></span>](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md)  
  
  
