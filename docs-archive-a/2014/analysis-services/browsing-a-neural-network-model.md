---
title: Просмотр модели нейронной сети | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- mining model, neural network
- neural networks
- dependency network
ms.assetid: e4224cb7-115b-4889-ac07-03f096fb55fc
author: minewiskan
ms.author: owend
ms.openlocfilehash: ab2673d5b1881f74c2bc146b084d2efc7b06d69b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656819"
---
# <a name="browsing-a-neural-network-model"></a><span data-ttu-id="33a69-102">Просмотр модели нейронной сети</span><span class="sxs-lookup"><span data-stu-id="33a69-102">Browsing a Neural Network Model</span></span>
  <span data-ttu-id="33a69-103">При открытии модели нейронной сети или логистической регрессии с помощью кнопки **Обзор** модель отображается в интерактивном средстве просмотра, аналогичном средству просмотра модели нейронной сети в [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33a69-103">When you open a neural network or logistic regression model using **Browse**, the model is displayed in an interactive viewer, similar to the neural network model viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="33a69-104">Средство просмотра помогает исследовать корреляции и получать информацию об элементах организации в модели и в базовых данных.</span><span class="sxs-lookup"><span data-stu-id="33a69-104">The viewer helps you explore correlations, and get information about the patterns in the model and the underlying data.</span></span>

##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="33a69-105">Изучение модели</span><span class="sxs-lookup"><span data-stu-id="33a69-105">Explore the Model</span></span>
 <span data-ttu-id="33a69-106">Модели, основанные на алгоритмах нейронной сети или логистической регрессии [!INCLUDE[msCoName](../includes/msconame-md.md)] схожи в том, что они анализируют данные в виде набора известных соединений между вводными и выходными данными.</span><span class="sxs-lookup"><span data-stu-id="33a69-106">Models that are based on [!INCLUDE[msCoName](../includes/msconame-md.md)] Neural Network or Logistic Regression algorithms are similar in that they analyze data as a set of connections among known inputs and outputs.</span></span> <span data-ttu-id="33a69-107">Средство просмотра **Обзор** позволяет просматривать эти соединения с помощью следующих элементов управления:</span><span class="sxs-lookup"><span data-stu-id="33a69-107">The **Browse** viewer helps you to explore those connections, using the following controls:</span></span>

-   [<span data-ttu-id="33a69-108">Переменные</span><span class="sxs-lookup"><span data-stu-id="33a69-108">Variables</span></span>](#BKMK_Variables)

-   [<span data-ttu-id="33a69-109">Входные данные</span><span class="sxs-lookup"><span data-stu-id="33a69-109">Inputs</span></span>](#BKMK_Inputs)

-   [<span data-ttu-id="33a69-110">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="33a69-110">Outputs</span></span>](#BKMK_Outputs)

 <span data-ttu-id="33a69-111">При желании поэкспериментировать с этим средством просмотра можно создать модели с помощью мастера [Мастер классификации (надстройки интеллектуального анализа данных для Excel)](classify-wizard-data-mining-add-ins-for-excel.md) и использовать параметр **Дополнительно**, чтобы изменить алгоритм на алгоритм логистической регрессии (Майкрософт) в диалоговом окне **Параметры алгоритма**.</span><span class="sxs-lookup"><span data-stu-id="33a69-111">If you want to experiment with this viewer, you can create a model using the [Classify Wizard &#40;Data Mining Add-ins for Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) wizard, and use the **Advanced** option to change the algorithm to Microsoft Logistic Regression in the **Algorithm Parameters** dialog box.</span></span>

###  <a name="variables"></a><a name="BKMK_Variables"></a><span data-ttu-id="33a69-112">Среды</span><span class="sxs-lookup"><span data-stu-id="33a69-112">Variables</span></span>
 <span data-ttu-id="33a69-113">В панели **Переменные** выводится список вводных переменных в порядке их влияния на модели.</span><span class="sxs-lookup"><span data-stu-id="33a69-113">The **Variables** pane displays a list of input variables in order of their effect on the model.</span></span> <span data-ttu-id="33a69-114">Элементы управления **Вход** и **Выход** используются для фильтрации модели, что отражается на отображаемых переменных, а также на их порядке.</span><span class="sxs-lookup"><span data-stu-id="33a69-114">You use the **Input** and **Output** controls to filter the model, affecting the variables that are displayed, as well as their order.</span></span>

 <span data-ttu-id="33a69-115">С помощью этого средства просмотра можно исследовать факторы, наиболее важные для определения принадлежности клиента к категории покупателей велосипедов.</span><span class="sxs-lookup"><span data-stu-id="33a69-115">Using this viewer, you can explore the factors that are most important in determining whether a customer more likely belongs to the bike buyer category or the non-buyer category.</span></span>

 <span data-ttu-id="33a69-116">![Влияние тестирования на исход выбранных атрибутов](media/dm13-neuralnet-agebuyer1.gif "Влияние тестирования на исход выбранных атрибутов")</span><span class="sxs-lookup"><span data-stu-id="33a69-116">![Testing effect on outcome of selected attributes](media/dm13-neuralnet-agebuyer1.gif "Testing effect on outcome of selected attributes")</span></span>

##### <a name="explore-variables"></a><span data-ttu-id="33a69-117">Просмотр переменных</span><span class="sxs-lookup"><span data-stu-id="33a69-117">Explore variables</span></span>

1.  <span data-ttu-id="33a69-118">Изначально панель **Переменные** отсортирована в порядке наиболее важных атрибутов, исходя из текущих фильтров.</span><span class="sxs-lookup"><span data-stu-id="33a69-118">Initially, the **Variables** pane is sorted in order of the most important attributes, given the current filters.</span></span> <span data-ttu-id="33a69-119">Длина полосы показывает степень важности фактора.</span><span class="sxs-lookup"><span data-stu-id="33a69-119">The length of the bar indicates the strength of the factor.</span></span>

     <span data-ttu-id="33a69-120">В этом примере можно видеть, что доход — это наиболее важный фактор, за которым по важности следует регион.</span><span class="sxs-lookup"><span data-stu-id="33a69-120">In the example, you can see that income is the most influential factor, followed by region.</span></span> <span data-ttu-id="33a69-121">С другой стороны, клиенты-владельцы нескольких автомобилей и с большим количеством детей, вероятно, не купят велосипед.</span><span class="sxs-lookup"><span data-stu-id="33a69-121">On the other hand, customers with many cars and many children are highly unlikely to buy a bike.</span></span>

2.  <span data-ttu-id="33a69-122">На панели **Переменные** щелкните заголовок столбца **Атрибут**.</span><span class="sxs-lookup"><span data-stu-id="33a69-122">In the **Variables** pane, click the column heading for **Attribute**.</span></span>

     <span data-ttu-id="33a69-123">При сортировке по атрибуту можно видеть сегменты, созданные для каждого из входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="33a69-123">By sorting on attribute, you can see the bins that were created for each of the input columns.</span></span> <span data-ttu-id="33a69-124">Столбцы с дискретными значениями, например родом занятий, *сортируются* по литеральным значениям.</span><span class="sxs-lookup"><span data-stu-id="33a69-124">Columns with discrete values, such as occupation, are *binned* by the literal values.</span></span>

3.  <span data-ttu-id="33a69-125">Обратите внимание на диапазоны значений, определенные для **Возраст** и **Доход**.</span><span class="sxs-lookup"><span data-stu-id="33a69-125">Notice the ranges of values that were found for **Age** and **Income**.</span></span>

     <span data-ttu-id="33a69-126">Если любой из входных столбцов содержит числа (то есть если весь столбец данных имеет непрерывный числовой тип), то числа группируются или разбиваются в дискретные диапазоны.</span><span class="sxs-lookup"><span data-stu-id="33a69-126">If any of your input columns are numbers (that is, the entire column of data is a continuous numeric data type), the numbers are bucketed, or binned, into discrete ranges.</span></span>

     <span data-ttu-id="33a69-127">Для данных дохода столбец был разделен по группам, таким как 78.4-154.06 (для наиболее высоких диапазонов дохода).</span><span class="sxs-lookup"><span data-stu-id="33a69-127">For Income, the column has been subdivided into groupings such as 78.4-154.06 (for the uppermost income range).</span></span>

     <span data-ttu-id="33a69-128">![сортировка, чтобы посмотреть, как переменные ".](media/dm13-nn-bucketing-variables.gif "сортировка, чтобы посмотреть, как переменные ".")</span><span class="sxs-lookup"><span data-stu-id="33a69-128">![sort to view how variables were binned](media/dm13-nn-bucketing-variables.gif "sort to view how variables were binned")</span></span>

     <span data-ttu-id="33a69-129">Если нужно сделать другие группы, необходимо использовать средство [Переразметка (надстройки интеллектуального анализа данных SQL Server)](relabel-sql-server-data-mining-add-ins.md) или функции Excel, чтобы создать новые категории дохода перед построением модели.</span><span class="sxs-lookup"><span data-stu-id="33a69-129">If you want different groupings, you should use the [Relabel &#40;SQL Server Data Mining Add-ins&#41;](relabel-sql-server-data-mining-add-ins.md) tool, or Excel functions, to create new income categories before building the model.</span></span>

4.  <span data-ttu-id="33a69-130">Нажмите кнопку **Подходит Да**, чтобы вернуться в представление диаграммы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="33a69-130">Click **Favors Yes** to restore the graph to the default view.</span></span>

     <span data-ttu-id="33a69-131">По умолчанию представление отсортировано по значению **Подходит** для первого значения результатов.</span><span class="sxs-lookup"><span data-stu-id="33a69-131">By default, the view is sorted by the value of **Favors** for the first outcome value.</span></span> <span data-ttu-id="33a69-132">Можно изменить, какие результаты назначаются первому и второму столбцам, выбрав новое значение для **Значение 1** и **Значение 2** в разделе **Выход**.</span><span class="sxs-lookup"><span data-stu-id="33a69-132">You can change which outcomes are assigned to the first and second columns by choosing a new value for **Value 1** and **Value 2** in **Output**.</span></span>

5.  <span data-ttu-id="33a69-133">Наведите указатель мыши на самую верхнюю цветную полосу в диаграмме.</span><span class="sxs-lookup"><span data-stu-id="33a69-133">Pause the mouse over the topmost colored bar in the chart.</span></span>

     <span data-ttu-id="33a69-134">Появляется подсказка, которая включает показатель *важности*, пару показателей *вероятности* и пару значений *точности прогноза*.</span><span class="sxs-lookup"><span data-stu-id="33a69-134">A ToolTip appears that includes an *importance* score, a pair of *probability* scores, and a pair of *lift* values.</span></span>

    -   <span data-ttu-id="33a69-135">**Важность** рассчитывается по всему набору данных и определяет атрибут, который, с учетом всех входных данных, больше всего связан с целевым результатом.</span><span class="sxs-lookup"><span data-stu-id="33a69-135">**Importance** is calculated across the entire dataset, and identifies the attribute that, given all inputs, is most correlated with the target outcome.</span></span> <span data-ttu-id="33a69-136">Средство просмотра сортирует значения в диаграмме по показателям важности.</span><span class="sxs-lookup"><span data-stu-id="33a69-136">The viewer sorts the values in the chart by the importance scores.</span></span>

    -   <span data-ttu-id="33a69-137">**Вероятность** вычисляется для каждого набора пар атрибут-значение для целевых результатов по всему набору данных.</span><span class="sxs-lookup"><span data-stu-id="33a69-137">**Probability** is calculated for each set of attribute-value pairs, for the target outcomes, across the entire data set.</span></span>

    -   <span data-ttu-id="33a69-138">**Точность прогноза** показывает, насколько определяющей является конкретная пара атрибут-значение для того, чтобы сказаться на конкретном результате.</span><span class="sxs-lookup"><span data-stu-id="33a69-138">**Lift** tells you how useful this particular attribute-value pair is for promoting one outcome or another.</span></span>

     <span data-ttu-id="33a69-139">Примечание. Подсказка содержит одну и ту же информацию вне зависимости от позиции указателя мыши над одним или другим столбцом.</span><span class="sxs-lookup"><span data-stu-id="33a69-139">Note: The ToolTip contains the same information no matter whether you position the mouse over one column or the other.</span></span>

 [<span data-ttu-id="33a69-140">К началу</span><span class="sxs-lookup"><span data-stu-id="33a69-140">Back To Top</span></span>](#BKMK_Tabs)

###  <a name="inputs"></a><a name="BKMK_Inputs"></a><span data-ttu-id="33a69-141">Входа</span><span class="sxs-lookup"><span data-stu-id="33a69-141">Inputs</span></span>
 <span data-ttu-id="33a69-142">Панель **Входы** позволяет выбрать набор входных данных и применить его в качестве фильтра к модели. При этом вы сможете увидеть степень влияния выбранных параметров на результат на основе обучающих данных.</span><span class="sxs-lookup"><span data-stu-id="33a69-142">The **Inputs** pane lets you choose a set of inputs and apply that as a filter to the model, which lets you see the influence of those choices on the outcome, based on the training data</span></span>

##### <a name="explore-inputs"></a><span data-ttu-id="33a69-143">Просмотр входных данных</span><span class="sxs-lookup"><span data-stu-id="33a69-143">Explore inputs</span></span>

1.  <span data-ttu-id="33a69-144">Предположим, что необходимо обратиться к особой группе и просмотреть факторы, которые сильнее всего будут влиять на покупки в этой группе.</span><span class="sxs-lookup"><span data-stu-id="33a69-144">Suppose you want to target a particular group, and see the factors that most influence purchasing in that group.</span></span>

     <span data-ttu-id="33a69-145">На панели **входных данных** щелкните **\<All>** ячейку в поле **атрибут**и выберите **возраст**.</span><span class="sxs-lookup"><span data-stu-id="33a69-145">In the **Input** pane, click the **\<All>** cell under **Attribute**, and select **Age**.</span></span>

     <span data-ttu-id="33a69-146">В поле **Значение** выберите наиболее молодую возрастную категорию.</span><span class="sxs-lookup"><span data-stu-id="33a69-146">For **Value**, select the youngest age category.</span></span>

2.  <span data-ttu-id="33a69-147">Обратите внимание, что даже при фильтрации по определенной возрастной группе, тихоокеанский регион отображается в верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="33a69-147">Notice that even when you filter on a particular age group, the Pacific region comes to near the top of the list.</span></span> <span data-ttu-id="33a69-148">Это происходит потому, что клиенты в тихоокеанском регионе намного более вероятно приобретут велосипед, чем клиенты в других регионах.</span><span class="sxs-lookup"><span data-stu-id="33a69-148">This is because customers in the Pacific region are far more likely to buy a bike than customers in other regions.</span></span>

     <span data-ttu-id="33a69-149">Поскольку регион не относится к факторам, на который вы можете влиять, чтобы удалить эту переменную из числа переменных, подлежащих пересмотру и увидеть другие факторы, вы можете снова изменить входные данные.</span><span class="sxs-lookup"><span data-stu-id="33a69-149">Since region is not something you can influence, to remove this variable from consideration and see other factors, you can change the inputs again.</span></span>

     <span data-ttu-id="33a69-150">На панели **Входные данные** щелкните пустую ячейку под значением **Возраст** и выберите **Регион**.</span><span class="sxs-lookup"><span data-stu-id="33a69-150">In the **Input** pane, click the empty cell under **Age**, and select **Region**.</span></span>

     <span data-ttu-id="33a69-151">Для параметра **Значение** выберите значение **Европа**.</span><span class="sxs-lookup"><span data-stu-id="33a69-151">For **Value**, select **Europe**.</span></span>

3.  <span data-ttu-id="33a69-152">Продолжайте добавлять фильтры входа, чтобы сосредоточиться на группе, представляющей интерес.</span><span class="sxs-lookup"><span data-stu-id="33a69-152">Continue adding input filters to focus on a group of particular interest.</span></span>

     <span data-ttu-id="33a69-153">Например, для входного атрибута добавьте **Пол** и выберите **Жен.** в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="33a69-153">For example, for the input attribute, add **Gender**, and select **Female** as the value.</span></span>

     <span data-ttu-id="33a69-154">![Влияние тестирования на исход выбранных атрибутов](media/dm13-neuralnet-agebuyer2.gif "Влияние тестирования на исход выбранных атрибутов")</span><span class="sxs-lookup"><span data-stu-id="33a69-154">![Testing effect on outcome of selected attributes](media/dm13-neuralnet-agebuyer2.gif "Testing effect on outcome of selected attributes")</span></span>

     <span data-ttu-id="33a69-155">Обратите внимание на то, как изменяется список переменных.</span><span class="sxs-lookup"><span data-stu-id="33a69-155">Notice how the list of variables changes.</span></span> <span data-ttu-id="33a69-156">Теперь **Доход** является наиболее важной переменной в прогнозировании целевого результата.</span><span class="sxs-lookup"><span data-stu-id="33a69-156">Now **Income** is the variable that is most important in predicting the target outcome.</span></span>

     <span data-ttu-id="33a69-157">Порядок применения фильтров входа не влияет на результаты.</span><span class="sxs-lookup"><span data-stu-id="33a69-157">The order in which you apply the input filters does not affect the results.</span></span>

 [<span data-ttu-id="33a69-158">К началу</span><span class="sxs-lookup"><span data-stu-id="33a69-158">Back To Top</span></span>](#BKMK_Tabs)

###  <a name="outputs"></a><a name="BKMK_Outputs"></a><span data-ttu-id="33a69-159">Выходные</span><span class="sxs-lookup"><span data-stu-id="33a69-159">Outputs</span></span>
 <span data-ttu-id="33a69-160">На панели **Результаты** можно выбрать результат, в котором вы заинтересованы.</span><span class="sxs-lookup"><span data-stu-id="33a69-160">In the **Outputs** pane, you can choose the outcome that you are interested in.</span></span> <span data-ttu-id="33a69-161">Нейронные сети позволяют указать необходимое количество столбцов результатов, хотя добавление дополнительных выходных данных усложняет модель и может потребовать гораздо больше времени для обработки.</span><span class="sxs-lookup"><span data-stu-id="33a69-161">Neural networks let you specify as many outcome columns as you like, although adding more outputs adds to the complexity of the model and may require a much longer time to process.</span></span>

 <span data-ttu-id="33a69-162">Для сравнения двух показателей выходных данных они должны быть определены как столбцы **Прогноз** и **Только прогноз**.</span><span class="sxs-lookup"><span data-stu-id="33a69-162">To compare two outputs, they must have been designated as **Predict** or **Predict Only** columns.</span></span>

##### <a name="explore-outputs"></a><span data-ttu-id="33a69-163">Просмотр выходных данных</span><span class="sxs-lookup"><span data-stu-id="33a69-163">Explore outputs</span></span>

1.  <span data-ttu-id="33a69-164">Доступные атрибуты содержатся в списке **Выходной атрибут**.</span><span class="sxs-lookup"><span data-stu-id="33a69-164">Use the **Output Attribute** list to select an attribute.</span></span>

2.  <span data-ttu-id="33a69-165">Выберите из списка два результата из списков Значение 1 и Значение 2.</span><span class="sxs-lookup"><span data-stu-id="33a69-165">Select two outcomes from the Value 1 and Value 2 lists.</span></span> <span data-ttu-id="33a69-166">Эти два состояния выходного атрибута будут сравниваться в области **Переменные** .</span><span class="sxs-lookup"><span data-stu-id="33a69-166">These two states of the output attribute will be compared in the **Variables** pane.</span></span>

 [<span data-ttu-id="33a69-167">К началу</span><span class="sxs-lookup"><span data-stu-id="33a69-167">Back To Top</span></span>](#BKMK_Tabs)

## <a name="more-about-neural-network-models"></a><span data-ttu-id="33a69-168">Сведения о моделях нейронных сетей</span><span class="sxs-lookup"><span data-stu-id="33a69-168">More About Neural Network Models</span></span>
 <span data-ttu-id="33a69-169">Сведения в средстве просмотра извлекаются с сервера с помощью хранимой процедуры, которая конкретизируется типом модели: System.Microsoft.AnalysisServices.System.DataMining.NeuralNet.GetAttributeScores.</span><span class="sxs-lookup"><span data-stu-id="33a69-169">The information in the viewer is retrieved from the server using a stored procedure specific to this model type: System.Microsoft.AnalysisServices.System.DataMining.NeuralNet.GetAttributeScores.</span></span>

 <span data-ttu-id="33a69-170">Если необходимо создать модель с несколькими прогнозируемыми атрибутами, используя надстройки, применяйте параметры моделирования в разделе **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="33a69-170">If you want to create a model with multiple predictable attributes using the add-ins, use the **Advanced** modeling options.</span></span>

 <span data-ttu-id="33a69-171">Дополнительные сведения см. в разделах [Создание структуры интеллектуального анализа данных (надстройки интеллектуального анализа данных SQL Server)](create-mining-structure-sql-server-data-mining-add-ins.md) и [Добавление модели к структуре (надстройки интеллектуального анализа данных для Excel)](add-model-to-structure-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="33a69-171">For more information, see [Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md) and [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="33a69-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="33a69-172">See Also</span></span>
 [<span data-ttu-id="33a69-173">Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="33a69-173">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)


