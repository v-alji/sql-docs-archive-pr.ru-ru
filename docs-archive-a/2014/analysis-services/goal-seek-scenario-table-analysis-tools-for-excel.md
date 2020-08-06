---
title: Сценарий поиска решения (средства анализа таблиц для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- scenario analysis
- goal seek scenario
ms.assetid: efe50306-cf7c-46b3-9cc4-e7f0b6968b0c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b3b4df4f78a2d3652b1dac3c566e66507b523ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657974"
---
# <a name="goal-seek-scenario-table-analysis-tools-for-excel"></a><span data-ttu-id="c25eb-102">Сценарий поиска решения (средства анализа таблиц для Excel)</span><span class="sxs-lookup"><span data-stu-id="c25eb-102">Goal Seek Scenario (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="c25eb-103">![Кнопка «Поиск решения» на ленте «Средства анализа таблиц»](media/tat-goalseek.gif "Кнопка «Поиск решения» на ленте «Средства анализа таблиц»")</span><span class="sxs-lookup"><span data-stu-id="c25eb-103">![Goal Seek button in Table Analysis tools](media/tat-goalseek.gif "Goal Seek button in Table Analysis tools")</span></span>  
  
 <span data-ttu-id="c25eb-104">Средство **поиска решения** является дополнением к средству сценария [What If](what-if-scenario-table-analysis-tools-for-excel.md) .</span><span class="sxs-lookup"><span data-stu-id="c25eb-104">The **Goal Seek** scenario tool is complementary to the [What If](what-if-scenario-table-analysis-tools-for-excel.md) scenario tool.</span></span> <span data-ttu-id="c25eb-105">Средство " **что если** " сообщает о влиянии изменения, в то время как средство **поиска решения** указывает базовые факторы, которые необходимо изменить для достижения желаемого результата.</span><span class="sxs-lookup"><span data-stu-id="c25eb-105">The **What-If** tool tells you the impact of making a change, whereas the **Goal Seek** tool tells you the underlying factors that must change to achieve a desired result.</span></span>  
  
 <span data-ttu-id="c25eb-106">Например, предположим, что ваша цель состоит в увеличении удовлетворенности клиентов.</span><span class="sxs-lookup"><span data-stu-id="c25eb-106">For example, let's say your goal is to increase customer satisfaction.</span></span> <span data-ttu-id="c25eb-107">Вы можете использовать анализ **поиска решения** , чтобы определить, какие факторы лучше всего увеличивают удовлетворенность клиентов, и решить, являются ли эти изменения экономичными.</span><span class="sxs-lookup"><span data-stu-id="c25eb-107">You can use **Goal Seek** analysis to determine which factors would be most likely to increase customer satisfaction, and decide whether those changes are cost-effective.</span></span>  
  
 <span data-ttu-id="c25eb-108">После окончания анализа в исходной таблице создаются два новых столбца.</span><span class="sxs-lookup"><span data-stu-id="c25eb-108">When the tool finishes its analysis, it creates two new columns in the source data table.</span></span> <span data-ttu-id="c25eb-109">В этих столбцах показана *вероятность* достижения целевого результата и рекомендуемого изменения (при наличии).</span><span class="sxs-lookup"><span data-stu-id="c25eb-109">These columns show the *likelihood* that the targeted outcome can be achieved, and the recommended change, if any.</span></span>  
  
 <span data-ttu-id="c25eb-110">Можно использовать это средство, которое способно анализировать набор данных и делать прогнозы для всего набора, либо пользователь может сам выполнить анализ, а затем последовательно проверить сценарии.</span><span class="sxs-lookup"><span data-stu-id="c25eb-110">The tool can analyze a set of data and make predictions for the entire set, or you can create the analysis and then test scenarios one at a time.</span></span>  
  
## <a name="using-the-goal-seek-scenario-tool"></a><span data-ttu-id="c25eb-111">Использование средства сценариев поиска решения</span><span class="sxs-lookup"><span data-stu-id="c25eb-111">Using the Goal Seek Scenario Tool</span></span>  
  
1.  <span data-ttu-id="c25eb-112">Откройте таблицу Excel.</span><span class="sxs-lookup"><span data-stu-id="c25eb-112">Open an Excel table.</span></span>  
  
2.  <span data-ttu-id="c25eb-113">Щелкните **сценарии**и выберите **Поиск решения**.</span><span class="sxs-lookup"><span data-stu-id="c25eb-113">Click **Scenarios**, and select **Goal Seek**.</span></span>  
  
3.  <span data-ttu-id="c25eb-114">В диалоговом окне **Анализ сценария: Поиск решения** выберите столбец, содержащий целевое значение из списка.</span><span class="sxs-lookup"><span data-stu-id="c25eb-114">In the **Scenario Analysis: Goal Seek** dialog box, select the column that contains the target value from the list.</span></span>  
  
4.  <span data-ttu-id="c25eb-115">Укажите значение, которое требуется достичь.</span><span class="sxs-lookup"><span data-stu-id="c25eb-115">Specify the value that you want to achieve.</span></span>  
  
     <span data-ttu-id="c25eb-116">Если столбец содержит непрерывные числовые значения, можно также в качестве цели указать нужное увеличение или уменьшение значения.</span><span class="sxs-lookup"><span data-stu-id="c25eb-116">If the column goal contains continuous numeric values, you can also specify a desired increase or decrease in the value.</span></span> <span data-ttu-id="c25eb-117">Например, можно выбрать **Sales** в качестве столбца и указать, что целевой объект будет увеличен на 120%.</span><span class="sxs-lookup"><span data-stu-id="c25eb-117">For example, you might choose **Sales** as the column and specify that the target is an increase of 120%.</span></span>  
  
     <span data-ttu-id="c25eb-118">Либо можно в качестве цели задать диапазон значений, введя нижний и верхний пределы.</span><span class="sxs-lookup"><span data-stu-id="c25eb-118">Or, you can specify the goal as a range of values, by typing a lower and upper limit.</span></span>  
  
5.  <span data-ttu-id="c25eb-119">Укажите столбец, содержащий значения, которые нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="c25eb-119">Specify the column that contains the values you will change.</span></span> <span data-ttu-id="c25eb-120">Другими словами, выберите столбец, с которым будет производиться работа для достижения нужного результата.</span><span class="sxs-lookup"><span data-stu-id="c25eb-120">In other words, pick the column that will be manipulated to produce the desired result.</span></span>  
  
6.  <span data-ttu-id="c25eb-121">При необходимости нажмите кнопку **выбрать столбцы, которые будут использоваться для анализа**, а затем выберите столбцы, содержащие полезную информацию.</span><span class="sxs-lookup"><span data-stu-id="c25eb-121">Optionally, click **Choose columns to be used for analysis**, and select columns that contain useful information.</span></span> <span data-ttu-id="c25eb-122">Не выбирайте столбцы, которые не влияют на анализ.</span><span class="sxs-lookup"><span data-stu-id="c25eb-122">Deselect columns that will not contribute to the analysis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c25eb-123">Не отменяйте выбор столбцов, которые нужно использовать для решения или изменения.</span><span class="sxs-lookup"><span data-stu-id="c25eb-123">Do not deselect columns that you will use for either the goal or the change.</span></span> <span data-ttu-id="c25eb-124">Это обязательные для выбора столбцы.</span><span class="sxs-lookup"><span data-stu-id="c25eb-124">These columns are required.</span></span>  
  
7.  <span data-ttu-id="c25eb-125">Укажите, будет ли прогноз выполнен для всей таблицы или только для выбранной строки.</span><span class="sxs-lookup"><span data-stu-id="c25eb-125">Specify whether you want to make predictions for the entire table, or for only the selected row.</span></span>  
  
8.  <span data-ttu-id="c25eb-126">Если выбран параметр « **вся таблица** », то средство добавляет прогнозы в исходную таблицу в двух новых столбцах.</span><span class="sxs-lookup"><span data-stu-id="c25eb-126">If you selected the **Entire table** option, the tool adds the predictions to the source table in two new columns.</span></span>  
  
9. <span data-ttu-id="c25eb-127">Если в **этой строке**был выбран параметр, результаты анализа будут выведены в диалоговое окно для проверки.</span><span class="sxs-lookup"><span data-stu-id="c25eb-127">If you selected the option **On this row**, the results of analysis are output to the dialog box for review.</span></span> <span data-ttu-id="c25eb-128">Это диалоговое окно будет оставаться открытым, поэтому можно продолжать работу по анализу новых значений и выбору новых решений.</span><span class="sxs-lookup"><span data-stu-id="c25eb-128">The dialog box stays open so that you can continue trying out different values and goals.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="c25eb-129">Требования</span><span class="sxs-lookup"><span data-stu-id="c25eb-129">Requirements</span></span>  
 <span data-ttu-id="c25eb-130">В этом средстве используется алгоритм логистической регрессии (Майкрософт), который может обрабатывать числовые или дискретные значения.</span><span class="sxs-lookup"><span data-stu-id="c25eb-130">This tool uses the Microsoft Logistic Regression algorithm, which can process either numeric or discrete values.</span></span>  
  
 <span data-ttu-id="c25eb-131">Прогноз может быть выполнен несколько раз для различных столбцов, однако каждое сочетание целевого значения и изменения должно быть рассчитано отдельно.</span><span class="sxs-lookup"><span data-stu-id="c25eb-131">You can run the prediction multiple times, and select different columns later, but each combination of a goal and a change must be calculated separately.</span></span>  
  
 <span data-ttu-id="c25eb-132">Для достижения лучших результатов следует выбирать такие столбцы, в которых содержится полезная для анализа информация.</span><span class="sxs-lookup"><span data-stu-id="c25eb-132">You can achieve better results if you select columns for analysis that contain useful information.</span></span> <span data-ttu-id="c25eb-133">Но если будет выбрано слишком мало столбцов, то достижение необходимого результата может быть затруднительным.</span><span class="sxs-lookup"><span data-stu-id="c25eb-133">However, if you include too few columns, it might be difficult to obtain a result.</span></span>  
  
 <span data-ttu-id="c25eb-134">При последовательном создании прогнозов необходимо выбирать строку, которая изначально не содержит нужный результат, чтобы не получить ошибку.</span><span class="sxs-lookup"><span data-stu-id="c25eb-134">When you create predictions one at a time, be sure to select a row that does not already contain the desired result, or you may get an error.</span></span> <span data-ttu-id="c25eb-135">Например, если целью поиска решения является определение факторов, способствующих покупкам велосипедов, необходимо включать только клиентов, у которых еще нет велосипеда.</span><span class="sxs-lookup"><span data-stu-id="c25eb-135">In other words, if the purpose of goal seeking is to determine factors that encourage bike purchases, you should only include customers who did not purchase a bike.</span></span>  
  
## <a name="understanding-the-results-of-goal-seek-analysis"></a><span data-ttu-id="c25eb-136">Основные сведения о результатах анализа поиска решения</span><span class="sxs-lookup"><span data-stu-id="c25eb-136">Understanding the Results of Goal Seek Analysis</span></span>  
 <span data-ttu-id="c25eb-137">При создании сценария поиска решения средство выполняет три действия.</span><span class="sxs-lookup"><span data-stu-id="c25eb-137">When you create a goal seeking scenario, the tool does three things:</span></span>  
  
-   <span data-ttu-id="c25eb-138">Создает структуру интеллектуального анализа данных, в которой хранятся ключевые факты о содержащихся в таблице данных.</span><span class="sxs-lookup"><span data-stu-id="c25eb-138">Creates a data mining structure that stores key facts about the data in your table.</span></span>  
  
-   <span data-ttu-id="c25eb-139">На основе существующих данных создает модель интеллектуального анализа данных с логистической регрессией.</span><span class="sxs-lookup"><span data-stu-id="c25eb-139">Creates a logistic regression mining model based on the data.</span></span>  
  
-   <span data-ttu-id="c25eb-140">Создает прогноз для каждого задаваемого значения.</span><span class="sxs-lookup"><span data-stu-id="c25eb-140">Creates a prediction for each value that you specify.</span></span>  
  
 <span data-ttu-id="c25eb-141">При последовательной проверке сценариев поиска решения результаты можно просматривать в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="c25eb-141">If you test goal-seeking scenarios one at a time, you can view the results interactively.</span></span> <span data-ttu-id="c25eb-142">Это то же самое, что и создание *одноэлементного прогнозирующего запроса*.</span><span class="sxs-lookup"><span data-stu-id="c25eb-142">This is the same as creating a *singleton prediction query*.</span></span>  
  
 <span data-ttu-id="c25eb-143">Средство сообщает об этом в области **результатов** диалогового окна о том, было ли оно успешным при поиске сценария, который достигает нужной цели.</span><span class="sxs-lookup"><span data-stu-id="c25eb-143">The tool reports in the **Results** pane of the dialog box whether it was successful in finding a scenario that achieves the desired goal.</span></span> <span data-ttu-id="c25eb-144">Если успешное решение найдено, средство также формирует рекомендацию, которая указывает необходимое изменение.</span><span class="sxs-lookup"><span data-stu-id="c25eb-144">If a successful solution was found, the tool also generates a recommendation that tells you the required change.</span></span> <span data-ttu-id="c25eb-145">Например, средство **поиска решения** может сообщить, что расстояние до работы должно быть меньше 5 миль.</span><span class="sxs-lookup"><span data-stu-id="c25eb-145">For example, the **Goal Seek** tool might tell you that the commuting distance should be less than 5 miles.</span></span>  
  
 <span data-ttu-id="c25eb-146">Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="c25eb-146">Example results:</span></span>  
  
 <span data-ttu-id="c25eb-147">**При поиске решения для задачи «Интерес к приобретению» удалось найти решение.**</span><span class="sxs-lookup"><span data-stu-id="c25eb-147">**Goal Seeking for Interest in Buying has found a solution.**</span></span>  
  
 <span data-ttu-id="c25eb-148">**Ближайшее соответствие достигается при изменении параметра «Расстояние до работы» на значение «2–5 километров».**</span><span class="sxs-lookup"><span data-stu-id="c25eb-148">**Closest match obtained by changing 'Commute distance' to '2-5 miles'.**</span></span>  
  
 <span data-ttu-id="c25eb-149">Поскольку данный результат основан на существующей строке таблицы данных, он говорит, что при уменьшении расстояния до работы до 2–5 километров, при неизменности всех остальных характеристик конкретного клиента, он купит велосипед с большей вероятностью.</span><span class="sxs-lookup"><span data-stu-id="c25eb-149">Because this result is based on an existing row in the data table, it means that, for a particular customer, if all else about the customer stayed the same but the customer's commute was reduced to 2-5 miles, the customer would be somewhat more likely buy a bicycle.</span></span>  
  
 <span data-ttu-id="c25eb-150">Если вы создаете прогнозы для всех строк в таблице Excel, указав **всю таблицу**, сетул создает два новых столбца в исходной таблице данных.</span><span class="sxs-lookup"><span data-stu-id="c25eb-150">If you create goal-seeking predictions for all the rows in the Excel table by specifying **Entire table**, thetool creates two new columns in the original data table.</span></span> <span data-ttu-id="c25eb-151">В первом добавленном столбце могут быть либо флажки на фоне зеленого круга, указывающие на то, что решение может быть найдено, либо символы «Х» на фоне красного круга, указывающие на то, что решение не может быть найдено ни при каких изменениях значения.</span><span class="sxs-lookup"><span data-stu-id="c25eb-151">The first column that is added to the table contains either a check mark in a green circle, to indicate that the goal can be met, or an X mark in a red circle, to indicate that no changes can be made that will enable the goal.</span></span>  
  
 <span data-ttu-id="c25eb-152">Второй столбец содержит рекомендуемое изменение.</span><span class="sxs-lookup"><span data-stu-id="c25eb-152">The second column contains the recommended change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c25eb-153">Степень достоверности рекомендаций и успешное их применение предопределяется исключительно используемым алгоритмом без возможности каких-либо изменений.</span><span class="sxs-lookup"><span data-stu-id="c25eb-153">The confidence level for the recommendation and its success are predetermined by the algorithm and cannot be changed.</span></span>  
  
## <a name="related-tools"></a><span data-ttu-id="c25eb-154">Дополнительные средства</span><span class="sxs-lookup"><span data-stu-id="c25eb-154">Related Tools</span></span>  
 <span data-ttu-id="c25eb-155">Клиент интеллектуального анализа данных для Excel представляет собой отдельную надстройку, поддерживающую дополнительные возможности интеллектуального анализа данных, в состав которой входят несколько мастеров, предназначенных для создания моделей интеллектуального анализа данных, прогнозирующих поведение.</span><span class="sxs-lookup"><span data-stu-id="c25eb-155">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, includes wizards for creating data mining models that predict behavior.</span></span> <span data-ttu-id="c25eb-156">Дополнительные сведения см. [в разделе Создание модели интеллектуального анализа данных](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="c25eb-156">For more information, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>  
  
 <span data-ttu-id="c25eb-157">Дополнительные сведения о алгоритме, используемом средством «сценарий **поиска решения** », см. в разделе «Алгоритм логистической регрессии (Майкрософт)» [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] электронной документации по.</span><span class="sxs-lookup"><span data-stu-id="c25eb-157">For more information about the algorithm used by the **Goal Seek** scenario tool, see the topic "Microsoft Logistic Regression Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c25eb-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="c25eb-158">See Also</span></span>  
 [<span data-ttu-id="c25eb-159">Средства анализа таблиц для Excel</span><span class="sxs-lookup"><span data-stu-id="c25eb-159">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  
