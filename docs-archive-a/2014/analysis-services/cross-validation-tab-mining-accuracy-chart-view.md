---
title: Вкладка "Перекрестная проверка" (представление диаграммы точности интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.crossvalidation.f1
ms.assetid: bd215a68-1ad7-4046-9c44-ec8e2be13a64
author: minewiskan
ms.author: owend
ms.openlocfilehash: 867bd6d1abffb29ec3eb2a8a78e562e5cbcc5b29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658572"
---
# <a name="cross-validation-tab-mining-accuracy-chart-view"></a><span data-ttu-id="40a4f-102">Вкладка «Перекрестная проверка» (просмотр диаграммы точности интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="40a4f-102">Cross-Validation Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="40a4f-103">Перекрестная проверка позволяет секционировать структуру интеллектуального анализа данных на разрезы, после чего — выполнить итеративное обучение и проверку моделей по каждому разрезу.</span><span class="sxs-lookup"><span data-stu-id="40a4f-103">Cross-validation lets you partition a mining structure into cross-sections and iteratively train and test models against each cross-section.</span></span> <span data-ttu-id="40a4f-104">Необходимо указать количество сверток, на которые разделяются данные, и каждая свертка, в свою очередь, играет роль проверочных данных, тогда как остальные данные используются для обучения новой модели.</span><span class="sxs-lookup"><span data-stu-id="40a4f-104">You specify a number of folds to divide the data into, and each fold is used in turn as the test data, whereas the remaining data is used to train a new model.</span></span> <span data-ttu-id="40a4f-105">Затем в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] для каждой модели формируется набор стандартных показателей точности.</span><span class="sxs-lookup"><span data-stu-id="40a4f-105">[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] then generates a set of standard accuracy metrics for each model.</span></span> <span data-ttu-id="40a4f-106">Сравнивая показатели моделей, созданных для каждого разреза, можно получить хорошее представление о том, насколько верна модель интеллектуального анализа для всего набора данных.</span><span class="sxs-lookup"><span data-stu-id="40a4f-106">By comparing the metrics for the models generated for each cross-section, you can get a good idea of how reliable the mining model is for the whole data set.</span></span>  
  
 <span data-ttu-id="40a4f-107">Дополнительные сведения см. в разделе [Перекрестная проверка (службы Analysis Services — интеллектуальный анализ данных)](data-mining/cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="40a4f-107">For more information, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](data-mining/cross-validation-analysis-services-data-mining.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40a4f-108">Перекрестная проверка не может использоваться с моделями, построенными с помощью алгоритма временных рядов [!INCLUDE[msCoName](../includes/msconame-md.md)] или алгоритма кластеризации последовательностей [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40a4f-108">Cross-validation cannot be used with models that were built by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm.</span></span> <span data-ttu-id="40a4f-109">При составлении отчета по структуре интеллектуального анализа данных, в которой содержатся модели таких типов, эти модели не будут включены в отчет.</span><span class="sxs-lookup"><span data-stu-id="40a4f-109">If you run the report on a mining structure that contains these types of models, the models will not be included in the report.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="40a4f-110">Список задач</span><span class="sxs-lookup"><span data-stu-id="40a4f-110">Task List</span></span>  
  
-   <span data-ttu-id="40a4f-111">Укажите число сверток.</span><span class="sxs-lookup"><span data-stu-id="40a4f-111">Specify the number of folds.</span></span>  
  
-   <span data-ttu-id="40a4f-112">Укажите максимальное число вариантов, используемых в перекрестной проверке.</span><span class="sxs-lookup"><span data-stu-id="40a4f-112">Specify the maximum number of cases to use for cross-validation.</span></span>  
  
-   <span data-ttu-id="40a4f-113">Укажите прогнозируемый столбец.</span><span class="sxs-lookup"><span data-stu-id="40a4f-113">Specify the predictable column.</span></span>  
  
-   <span data-ttu-id="40a4f-114">(Необязательно) Укажите прогнозируемое состояние.</span><span class="sxs-lookup"><span data-stu-id="40a4f-114">Optionally, specify a predictable state.</span></span>  
  
-   <span data-ttu-id="40a4f-115">(Необязательно) Задайте параметры, управляющие оценкой точности прогноза.</span><span class="sxs-lookup"><span data-stu-id="40a4f-115">Optionally, set parameters that control how the accuracy of prediction is assessed.</span></span>  
  
-   <span data-ttu-id="40a4f-116">Нажмите кнопку **Получить результаты** , чтобы отобразить результаты перекрестной проверки.</span><span class="sxs-lookup"><span data-stu-id="40a4f-116">Click **Get Results** to display the results of cross-validation.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="40a4f-117">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="40a4f-117">UI element list</span></span>  
 <span data-ttu-id="40a4f-118">**Число сверток**</span><span class="sxs-lookup"><span data-stu-id="40a4f-118">**Fold Count**</span></span>  
 <span data-ttu-id="40a4f-119">Укажите количество создаваемых сверток или секций.</span><span class="sxs-lookup"><span data-stu-id="40a4f-119">Specify the number of folds, or partitions, to create.</span></span> <span data-ttu-id="40a4f-120">Минимальное значение равно 2, то есть одна половина набора данных используется для проверки, другая — для обучения.</span><span class="sxs-lookup"><span data-stu-id="40a4f-120">The minimum value is 2, meaning that half the data set is used for testing and half for training.</span></span>  
  
 <span data-ttu-id="40a4f-121">Максимальное значение составляет 10 для структур интеллектуального анализа данных сеансов.</span><span class="sxs-lookup"><span data-stu-id="40a4f-121">The maximum value is 10 for session mining structures.</span></span>  
  
 <span data-ttu-id="40a4f-122">Если структура интеллектуального анализа данных хранится в экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], максимальное значение составляет 256.</span><span class="sxs-lookup"><span data-stu-id="40a4f-122">The maximum value is 256 if the mining structure is stored in an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40a4f-123">По мере увеличения количества сверток соответствующим образом увеличивается время, необходимое для выполнения перекрестной проверки.</span><span class="sxs-lookup"><span data-stu-id="40a4f-123">As you increase the number of folds, the time that is required to perform cross-validation similarly increases by n.</span></span> <span data-ttu-id="40a4f-124">Большое количество вариантов и большее значение параметра **Количество сверток** может привести к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="40a4f-124">You might experience performance issues if the number of cases is large and the value of **Fold Count** is also large.</span></span>  
  
 <span data-ttu-id="40a4f-125">**Максимальное количество вариантов**</span><span class="sxs-lookup"><span data-stu-id="40a4f-125">**Max Cases**</span></span>  
 <span data-ttu-id="40a4f-126">Укажите максимальное число вариантов, используемых в перекрестной проверке.</span><span class="sxs-lookup"><span data-stu-id="40a4f-126">Specify the maximum number of cases to use for cross-validation.</span></span> <span data-ttu-id="40a4f-127">Количество вариантов в любой отдельной свертке можно вычислить как отношение значения **Максимальное количество вариантов** к значению **Количество сверток** .</span><span class="sxs-lookup"><span data-stu-id="40a4f-127">The number of cases in any particular fold is equal to the **Max Cases** value divided by the **Fold Count** value.</span></span>  
  
 <span data-ttu-id="40a4f-128">При значении **0**для перекрестной проверки используются все варианты исходных данных.</span><span class="sxs-lookup"><span data-stu-id="40a4f-128">If you use **0**, all cases in the source data are used for cross-validation.</span></span>  
  
 <span data-ttu-id="40a4f-129">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="40a4f-129">There is no default value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40a4f-130">По мере увеличения количества вариантов увеличивается и время обработки.</span><span class="sxs-lookup"><span data-stu-id="40a4f-130">As you increase the number of cases, processing time also increases.</span></span>  
  
 <span data-ttu-id="40a4f-131">**Целевой атрибут**</span><span class="sxs-lookup"><span data-stu-id="40a4f-131">**Target Attribute**</span></span>  
 <span data-ttu-id="40a4f-132">Выберите столбец из списка прогнозируемых столбцов, обнаруженных во всех моделях.</span><span class="sxs-lookup"><span data-stu-id="40a4f-132">Select a column from the list of predictable columns found in all models.</span></span> <span data-ttu-id="40a4f-133">Каждый раз при выполнении перекрестной проверки можно выбрать только один прогнозируемый столбец.</span><span class="sxs-lookup"><span data-stu-id="40a4f-133">You can only select one predictable column every time that you perform cross-validation.</span></span>  
  
 <span data-ttu-id="40a4f-134">Чтобы проверить только модели кластеризации, выберите **Кластер**.</span><span class="sxs-lookup"><span data-stu-id="40a4f-134">To test only clustering models, select **Cluster**.</span></span>  
  
 <span data-ttu-id="40a4f-135">**Целевое состояние**</span><span class="sxs-lookup"><span data-stu-id="40a4f-135">**Target State**</span></span>  
 <span data-ttu-id="40a4f-136">Введите значение или выберите целевое значение из раскрывающегося списка значений.</span><span class="sxs-lookup"><span data-stu-id="40a4f-136">Type a value, or select a target value from a drop-down list of values.</span></span>  
  
 <span data-ttu-id="40a4f-137">Значением по умолчанию является `null`, обозначающее проверку всех состояний.</span><span class="sxs-lookup"><span data-stu-id="40a4f-137">The default value is `null`, indicating that all states are to be tested.</span></span>  
  
 <span data-ttu-id="40a4f-138">Отключено для моделей кластеризации.</span><span class="sxs-lookup"><span data-stu-id="40a4f-138">Disabled for clustering models.</span></span>  
  
 <span data-ttu-id="40a4f-139">**Целевой**  **порог**</span><span class="sxs-lookup"><span data-stu-id="40a4f-139">**Target**  **Threshold**</span></span>  
 <span data-ttu-id="40a4f-140">Укажите значение в диапазоне от 0 до 1, обозначающее вероятность прогноза, прогнозируемое состояние выше которой считается верным.</span><span class="sxs-lookup"><span data-stu-id="40a4f-140">Specify a value between 0 and 1 that indicates the prediction probability above which a predicted state is considered to be correct.</span></span> <span data-ttu-id="40a4f-141">Задать это значение можно с шагом 0,1.</span><span class="sxs-lookup"><span data-stu-id="40a4f-141">The value can be set in 0.1 increments.</span></span>  
  
 <span data-ttu-id="40a4f-142">Значением по умолчанию является `null`, обозначающее, что верным считается прогноз с наивысшей вероятностью.</span><span class="sxs-lookup"><span data-stu-id="40a4f-142">The default is `null`, indicating that the most probable prediction is counted as correct.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40a4f-143">Значение 0,0 присвоить этому параметру можно, но это приведет к увеличению времени обработки и не даст значительных результатов.</span><span class="sxs-lookup"><span data-stu-id="40a4f-143">Although you can set the value to 0.0, using this value will increase processing time and not yield meaningful results.</span></span>  
  
 <span data-ttu-id="40a4f-144">**Получить результаты**</span><span class="sxs-lookup"><span data-stu-id="40a4f-144">**Get Results**</span></span>  
 <span data-ttu-id="40a4f-145">Нажмите, чтобы запустить перекрестную проверку модели с указанными параметрами.</span><span class="sxs-lookup"><span data-stu-id="40a4f-145">Click to begin cross-validation of the model using the specified parameters.</span></span>  
  
 <span data-ttu-id="40a4f-146">Модель секционируется на указанное количество сверток, и для каждой свертки выполняется проверка отдельной модели.</span><span class="sxs-lookup"><span data-stu-id="40a4f-146">The model is partitioned into the specified number of folds and a separate model is tested for each fold.</span></span> <span data-ttu-id="40a4f-147">Поэтому, чтобы получить результаты перекрестной проверки, необходимо некоторое время.</span><span class="sxs-lookup"><span data-stu-id="40a4f-147">Therefore, it might take some time for cross-validation to return the results.</span></span>  
  
 <span data-ttu-id="40a4f-148">Дополнительные сведения об интерпретации результатов отчета перекрестной проверки см. в разделе [Меры в отчете перекрестной проверки](data-mining/measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="40a4f-148">For more information about how to interpret the results of the cross-validation report, see [Measures in the Cross-Validation Report](data-mining/measures-in-the-cross-validation-report.md).</span></span>  
  
## <a name="setting-the-accuracy-threshold"></a><span data-ttu-id="40a4f-149">Задание порога точности</span><span class="sxs-lookup"><span data-stu-id="40a4f-149">Setting the Accuracy Threshold</span></span>  
 <span data-ttu-id="40a4f-150">Управлять стандартом измерения точности прогнозов можно с помощью значения **Целевой** **порог**.</span><span class="sxs-lookup"><span data-stu-id="40a4f-150">You can control the standard for measuring prediction accuracy by setting a value for **Target** **Threshold**.</span></span> <span data-ttu-id="40a4f-151">Порог представляет собой разновидность диаграммы точности.</span><span class="sxs-lookup"><span data-stu-id="40a4f-151">A threshold represents a kind of accuracy bar.</span></span> <span data-ttu-id="40a4f-152">Каждому прогнозу присваивается вероятность достоверности прогнозируемого значения.</span><span class="sxs-lookup"><span data-stu-id="40a4f-152">Each prediction is assigned a probability that the predicted value is correct.</span></span> <span data-ttu-id="40a4f-153">Таким образом, если значение **Целевой** **порог** близко к 1, вероятность в любых конкретных прогнозах должна быть довольно высокой, чтобы прогноз считался хорошим.</span><span class="sxs-lookup"><span data-stu-id="40a4f-153">Therefore, if you set the **Target** **Threshold** value closer to 1, you are requiring that the probability for any particular prediction to be fairly high to be counted as a good prediction.</span></span> <span data-ttu-id="40a4f-154">И наоборот, если значение параметра **Целевой** **порог** близко к 0, то хорошими будут считаться даже прогнозы с невысокими значениями вероятности.</span><span class="sxs-lookup"><span data-stu-id="40a4f-154">Conversely, if you set **Target** **Threshold** closer to 0, even predictions with lower probability values are counted as "good" predictions.</span></span>  
  
 <span data-ttu-id="40a4f-155">Рекомендованных значений порога нет, поскольку вероятность в любом прогнозе зависит от объема данных и типа составляемого прогноза.</span><span class="sxs-lookup"><span data-stu-id="40a4f-155">There is no recommended threshold value because the probability of any prediction depends on the amount of data and the type of prediction you are making.</span></span> <span data-ttu-id="40a4f-156">Чтобы построить диаграмму точности для своих данных, изучите несколько прогнозов с разными уровнями вероятности.</span><span class="sxs-lookup"><span data-stu-id="40a4f-156">You should review some predictions at different probability levels to determine an appropriate accuracy bar for your data.</span></span> <span data-ttu-id="40a4f-157">Данный этап важен, поскольку значение, заданное для параметра **Целевой** **порог** , влияет на измеряемую точность модели.</span><span class="sxs-lookup"><span data-stu-id="40a4f-157">It is important that you do this, because the value that you set for **Target** **Threshold** affects the measured accuracy of the model.</span></span>  
  
 <span data-ttu-id="40a4f-158">Например, имеется три прогноза, составленных для определенного целевого состояния, с вероятностями 0,05, 0,15 и 0,8.</span><span class="sxs-lookup"><span data-stu-id="40a4f-158">For example, suppose three predictions are made for a particular target state, and the probabilities of each prediction are 0.05, 0.15, and 0.8.</span></span> <span data-ttu-id="40a4f-159">Если порогу задано значение 0,5, правильным будет считаться только один прогноз.</span><span class="sxs-lookup"><span data-stu-id="40a4f-159">If you set the threshold to 0.5, only one prediction is counted as being correct.</span></span> <span data-ttu-id="40a4f-160">Если параметру **Целевой** **порог** присвоено значение 0,10, то верными будут считаться два прогноза.</span><span class="sxs-lookup"><span data-stu-id="40a4f-160">If you set **Target** **Threshold** to 0.10, two predictions are counted as being correct.</span></span>  
  
 <span data-ttu-id="40a4f-161">Если параметру **целевой** **порог** присвоено `null` значение, которое является значением по умолчанию, наиболее вероятной прогноз для каждого варианта считается правильным.</span><span class="sxs-lookup"><span data-stu-id="40a4f-161">When **Target** **Threshold** is set to `null`, which is the default value, the most probable prediction for each case is counted as correct.</span></span> <span data-ttu-id="40a4f-162">В только что приведенном примере вероятности 0,05, 0,15 и 0,8 являются прогнозами в трех различных вариантах.</span><span class="sxs-lookup"><span data-stu-id="40a4f-162">In the example just cited, 0.05, 0.15, and 0.8 are the probabilities for predictions in three different cases.</span></span> <span data-ttu-id="40a4f-163">Несмотря на большую разницу в вероятностях, каждый из прогнозов будет считаться верным, поскольку в каждом варианте формируется только один прогноз, и указанные прогнозы являются лучшими в данных вариантах.</span><span class="sxs-lookup"><span data-stu-id="40a4f-163">Although the probabilities are very different, each prediction would be counted as correct, because each case generates only one prediction and these are the best predictions for these cases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a4f-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="40a4f-164">See Also</span></span>  
 <span data-ttu-id="40a4f-165">[Тестирование и проверка &#40;&#41;интеллектуального анализа данных](data-mining/testing-and-validation-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="40a4f-165">[Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md) </span></span>  
 <span data-ttu-id="40a4f-166">[&#40;перекрестной проверки Analysis Services — интеллектуальный анализ данных&#41;](data-mining/cross-validation-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="40a4f-166">[Cross-Validation &#40;Analysis Services - Data Mining&#41;](data-mining/cross-validation-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="40a4f-167">[Меры в отчете перекрестной проверки](data-mining/measures-in-the-cross-validation-report.md) </span><span class="sxs-lookup"><span data-stu-id="40a4f-167">[Measures in the Cross-Validation Report](data-mining/measures-in-the-cross-validation-report.md) </span></span>  
 [<span data-ttu-id="40a4f-168">Хранимые процедуры интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="40a4f-168">Data Mining Stored Procedures &#40;Analysis Services - Data Mining&#41;</span></span>](/sql/analysis-services/data-mining/data-mining-stored-procedures-analysis-services-data-mining)  
  
  
