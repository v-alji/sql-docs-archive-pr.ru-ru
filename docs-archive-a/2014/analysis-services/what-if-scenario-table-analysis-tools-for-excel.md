---
title: Сценарий "что если" (средства анализа таблиц для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- what if scenario
- scenario analysis
ms.assetid: 4df5a5c5-1983-4009-a7c5-cd340649fd2f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4bb5c5e866c1320c297fb4f2760bca58623f6601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752367"
---
# <a name="what-if-scenario-table-analysis-tools-for-excel"></a><span data-ttu-id="c54d0-102">Сценарий «Анализ гипотетических вариантов» (средства анализа таблиц для Excel)</span><span class="sxs-lookup"><span data-stu-id="c54d0-102">What-If Scenario (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="c54d0-103">![Кнопка «Сценарий анализа вариантов» на ленте «Средства анализа таблиц»](media/tat-whatif.gif "Кнопка «Сценарий анализа вариантов» на ленте «Средства анализа таблиц»")</span><span class="sxs-lookup"><span data-stu-id="c54d0-103">![What If Scenario button in Table Analysis tools](media/tat-whatif.gif "What If Scenario button in Table Analysis tools")</span></span>

 <span data-ttu-id="c54d0-104">Средство моделирования **гипотетических вариантов** анализирует закономерности в существующих данных, а затем позволяет оценить воздействие изменений в одном столбце на значение другого столбца.</span><span class="sxs-lookup"><span data-stu-id="c54d0-104">The **What-If** scenario tool analyzes patterns in existing data, and then enables you to evaluate the effect that changes in one column would have on the value of a different column.</span></span>

 <span data-ttu-id="c54d0-105">Например, можно проанализировать влияние повышения цены товара на общий объем его продаж.</span><span class="sxs-lookup"><span data-stu-id="c54d0-105">For example, you could explore the effect of raising the price of an item on its total sales.</span></span>

 <span data-ttu-id="c54d0-106">Средство позволяет создавать произвольное количество прогнозов.</span><span class="sxs-lookup"><span data-stu-id="c54d0-106">The tool is flexible about the number of predictions you can create.</span></span> <span data-ttu-id="c54d0-107">После выполнения начального анализа можно выполнять прогноз изменений для всех данных в таблице либо вводить проверочные значения по одному.</span><span class="sxs-lookup"><span data-stu-id="c54d0-107">After the initial analysis is complete, you can either predict changes for all the data in the table, or enter test values one at a time.</span></span>

## <a name="using-the-what-if-scenario-tool"></a><span data-ttu-id="c54d0-108">Использование средства-сценария «Анализ гипотетических вариантов»</span><span class="sxs-lookup"><span data-stu-id="c54d0-108">Using the What-If Scenario Tool</span></span>

1.  <span data-ttu-id="c54d0-109">Откройте таблицу данных Excel.</span><span class="sxs-lookup"><span data-stu-id="c54d0-109">Open an Excel data table.</span></span>

2.  <span data-ttu-id="c54d0-110">Щелкните **сценарии**, а затем выберите элемент **что если**.</span><span class="sxs-lookup"><span data-stu-id="c54d0-110">Click **Scenarios**, and then select **What-If**.</span></span>

3.  <span data-ttu-id="c54d0-111">В поле **сценарий** выберите столбец, содержащий значение, которое будет изменено, и укажите изменение либо в виде определенного значения, либо в виде процента изменения (увеличения или уменьшения) для текущих значений.</span><span class="sxs-lookup"><span data-stu-id="c54d0-111">In the **Scenario** box, select the column that contains the value you will change, and specify the change either as a specific value or as a percentage of change (either increased or decreased) on the current values.</span></span>

4.  <span data-ttu-id="c54d0-112">В поле **что происходит с** укажите столбец, для которого необходимо оценить результат.</span><span class="sxs-lookup"><span data-stu-id="c54d0-112">In the **What happens to** box, specify the column for which you want to assess the effect.</span></span>

5.  <span data-ttu-id="c54d0-113">При необходимости нажмите кнопку **выбрать столбцы, которые будут использоваться для анализа** , чтобы выбрать столбцы, которые, скорее всего, будут полезны при выполнении прогноза.</span><span class="sxs-lookup"><span data-stu-id="c54d0-113">Optionally, click **Choose columns to be used for analysis** to select columns that are likely to be useful in making the prediction.</span></span> <span data-ttu-id="c54d0-114">Также можно отключить столбцы, которые вряд ли будут способствовать выявлению закономерностей (например, идентификаторы или имена строк).</span><span class="sxs-lookup"><span data-stu-id="c54d0-114">You can also deselect columns that are likely to be of little use in detecting patterns, such as row IDs or names.</span></span>

6.  <span data-ttu-id="c54d0-115">В поле **Укажите строку или таблицу** выберите, следует ли оценить влияние только для выбранной строки или для полного набора данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="c54d0-115">In the **Specify row or table** box, choose whether you want the impact assessed for the currently selected row only, or for the complete set of data in the table.</span></span>

7.  <span data-ttu-id="c54d0-116">При выборе **в этой строке**средство отображает результат в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="c54d0-116">If you select **On this row**, the tool displays the result in the dialog box.</span></span> <span data-ttu-id="c54d0-117">Пока диалоговое окно остается открытым, можно изменять выбранные позиции для проверки других сценариев.</span><span class="sxs-lookup"><span data-stu-id="c54d0-117">While the dialog box remains open, you can modify your selections to test other scenarios.</span></span>

8.  <span data-ttu-id="c54d0-118">При выборе **всей таблицы**в диалоговом окне отображается сообщение о состоянии, а в исходную таблицу данных добавляются два новых столбца.</span><span class="sxs-lookup"><span data-stu-id="c54d0-118">If you select **Entire table**, the tool displays a status message in the dialog box, and adds two new columns to the original data table.</span></span> <span data-ttu-id="c54d0-119">Нажмите кнопку **Закрыть** , чтобы просмотреть все результаты на листе.</span><span class="sxs-lookup"><span data-stu-id="c54d0-119">Click **Close** to view the complete results in the worksheet.</span></span>

### <a name="requirements"></a><span data-ttu-id="c54d0-120">Требования</span><span class="sxs-lookup"><span data-stu-id="c54d0-120">Requirements</span></span>
 <span data-ttu-id="c54d0-121">В этом средстве используется алгоритм логистической регрессии (Майкрософт), который поддерживает выполнение прогнозов числовых или дискретных значений.</span><span class="sxs-lookup"><span data-stu-id="c54d0-121">This tool uses the Microsoft Logistic Regression algorithm, which supports prediction of either numeric or discrete values.</span></span> <span data-ttu-id="c54d0-122">Для достижения лучших результатов мы советуем следовать следующим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="c54d0-122">However, to achieve the best results, we suggest the following best practices:</span></span>

-   <span data-ttu-id="c54d0-123">Выбирайте для анализа столбцы, содержащие полезную информацию.</span><span class="sxs-lookup"><span data-stu-id="c54d0-123">Select columns for analysis that contain useful information.</span></span>

-   <span data-ttu-id="c54d0-124">Слишком малое количество выбранных столбцов может затруднить получение результатов.</span><span class="sxs-lookup"><span data-stu-id="c54d0-124">If you include too few columns it may be difficult to obtain a result.</span></span>

-   <span data-ttu-id="c54d0-125">Если используется параметр **to Value** , необходимо ввести значение в поле или выбрать значение из списка.</span><span class="sxs-lookup"><span data-stu-id="c54d0-125">If you use the **To value** option, you must type a value in the box or select a value from the list.</span></span>

-   <span data-ttu-id="c54d0-126">Если используется параметр **процент** , задайте изменение в процентах увеличения или уменьшения.</span><span class="sxs-lookup"><span data-stu-id="c54d0-126">If you use the **Percentage** option, set the change as a percentage increase or decrease.</span></span> <span data-ttu-id="c54d0-127">По умолчанию предлагается 120%, то есть увеличение текущего значения на 20%.</span><span class="sxs-lookup"><span data-stu-id="c54d0-127">The default is 120%, meaning a 20% increase over the current value.</span></span>

> [!NOTE]
>  <span data-ttu-id="c54d0-128">Если значение не будет задано, то может возникнуть ошибка.</span><span class="sxs-lookup"><span data-stu-id="c54d0-128">If you do not set a value, you might receive an error.</span></span>

## <a name="understanding-the-results-of-what-if-analysis"></a><span data-ttu-id="c54d0-129">Основные сведения о результатах анализа гипотетических вариантов</span><span class="sxs-lookup"><span data-stu-id="c54d0-129">Understanding the Results of What-If Analysis</span></span>
 <span data-ttu-id="c54d0-130">При создании сценария " **что если** " средство выполняет три действия:</span><span class="sxs-lookup"><span data-stu-id="c54d0-130">When you create a **What-If** scenario, the tool does three things:</span></span>

-   <span data-ttu-id="c54d0-131">Создает структуру интеллектуального анализа данных, в которой хранятся ключевые факты о содержащихся в таблице данных.</span><span class="sxs-lookup"><span data-stu-id="c54d0-131">Creates a data mining structure that stores key facts about the data in your table.</span></span>

-   <span data-ttu-id="c54d0-132">На основе существующих данных создает модель интеллектуального анализа данных с логистической регрессией.</span><span class="sxs-lookup"><span data-stu-id="c54d0-132">Creates a logistic regression mining model based on the data.</span></span>

-   <span data-ttu-id="c54d0-133">Создает прогнозирующий запрос для каждого из указанных значений.</span><span class="sxs-lookup"><span data-stu-id="c54d0-133">Creates a prediction query for each of the values you specify.</span></span>

 <span data-ttu-id="c54d0-134">Вы можете вывести все прогнозы за один раз, указав **всю таблицу**.</span><span class="sxs-lookup"><span data-stu-id="c54d0-134">You can output all the predictions at one time by specifying **Entire table**.</span></span> <span data-ttu-id="c54d0-135">При этом средство создает два новых столбца в исходной таблице данных.</span><span class="sxs-lookup"><span data-stu-id="c54d0-135">The tool then creates two new columns in the original data table.</span></span>

 <span data-ttu-id="c54d0-136">Столбцы, добавляемые в таблицу, содержат два типа данных: прогнозируемое значение, заданное изменением, и его достоверность.</span><span class="sxs-lookup"><span data-stu-id="c54d0-136">The columns that are added to the table contain two types of information: the predicted value given the change, and its confidence.</span></span> <span data-ttu-id="c54d0-137">Достоверность представляет собой вероятность правильности прогноза.</span><span class="sxs-lookup"><span data-stu-id="c54d0-137">Confidence means the probability that the prediction is correct.</span></span>

 <span data-ttu-id="c54d0-138">Также можно вводить значения изменения по одному и просматривать прогнозы в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="c54d0-138">You can also enter change values one by one in the dialog box, and view the predictions interactively.</span></span> <span data-ttu-id="c54d0-139">Это то же самое, что и создание *одноэлементного прогнозирующего запроса*.</span><span class="sxs-lookup"><span data-stu-id="c54d0-139">This is the same as creating a *singleton prediction query*.</span></span> <span data-ttu-id="c54d0-140">Результаты прогнозирующего запроса выводятся со следующими сведениями: успешное или неуспешное прогнозирование, прогнозируемое значение и уровень достоверности.</span><span class="sxs-lookup"><span data-stu-id="c54d0-140">The results of the prediction query are output with the following information: the success or failure of prediction, the predicted value, and the confidence level.</span></span> <span data-ttu-id="c54d0-141">Степень достоверности отображена в виде пунктирной линии.</span><span class="sxs-lookup"><span data-stu-id="c54d0-141">The confidence level is shown as a bar that contains a dotted line.</span></span> <span data-ttu-id="c54d0-142">Чем длиннее пунктирная линия, тем выше степень достоверности.</span><span class="sxs-lookup"><span data-stu-id="c54d0-142">The longer the dotted line, the higher the confidence in the result.</span></span>

 <span data-ttu-id="c54d0-143">Например, если вы пытаетесь определить результат увеличения возраста клиента на готовность к приобретению клиента и увеличить возраст клиента до 25, то средство " **что если** " запрашивает модель интеллектуального анализа данных и возвращает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="c54d0-143">For example, if you are trying to determine the effect of increasing the customer's age on the customer's willingness to buy, and increase the customer's age to 25, the **What-If** tool queries the data mining model and returns the following result:</span></span>

 <span data-ttu-id="c54d0-144">**При анализе гипотетических вариантов для задачи «Покупка велосипеда» удалось найти решение.**</span><span class="sxs-lookup"><span data-stu-id="c54d0-144">**What-If Analysis for Purchases Bicycle has found a solution.**</span></span>

 <span data-ttu-id="c54d0-145">**«Покупка велосипеда» = да**</span><span class="sxs-lookup"><span data-stu-id="c54d0-145">**'Purchases Bicycle' = yes**</span></span>

 <span data-ttu-id="c54d0-146">**Достоверность: удовлетворительно**</span><span class="sxs-lookup"><span data-stu-id="c54d0-146">**Confidence: Fair**</span></span>

 <span data-ttu-id="c54d0-147">Поскольку данный результат основан на существующей строке таблицы данных, он говорит о том, что с увеличением возраста до 25 лет при неизменности всех остальных характеристик конкретного покупателя он купит велосипед с большей вероятностью.</span><span class="sxs-lookup"><span data-stu-id="c54d0-147">Because this result is based on an existing row in the data table, it means that, for a particular customer, if all else about the customer stayed the same but the customer's age was increased to 25, the customer would likely buy a bicycle.</span></span>

 <span data-ttu-id="c54d0-148">Вывод прогнозов в исходную таблицу данных упрощает оценку их эффективности.</span><span class="sxs-lookup"><span data-stu-id="c54d0-148">Outputting the predictions to the original data table might make it easier to determine whether the predictions are useful.</span></span>

## <a name="related-tools"></a><span data-ttu-id="c54d0-149">Дополнительные средства</span><span class="sxs-lookup"><span data-stu-id="c54d0-149">Related Tools</span></span>
 <span data-ttu-id="c54d0-150">Клиент интеллектуального анализа данных для Excel представляет собой отдельную надстройку, поддерживающую дополнительные возможности интеллектуального анализа данных, в состав которой входят несколько мастеров, предназначенных для создания моделей интеллектуального анализа данных, прогнозирующих поведение.</span><span class="sxs-lookup"><span data-stu-id="c54d0-150">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, includes wizards for creating data mining models that predict behavior.</span></span> <span data-ttu-id="c54d0-151">Дополнительные сведения см. [в разделе Создание модели интеллектуального анализа данных](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="c54d0-151">For more information, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>

 <span data-ttu-id="c54d0-152">Дополнительные сведения о алгоритме, используемом средством моделирования **гипотетических** сценариев, см. в разделе «Алгоритм логистической регрессии (Майкрософт)» в Электронная документация на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c54d0-152">For more information about the algorithm used by the **What-If** scenario tool, see the topic "Microsoft Logistic Regression Algorithm" in SQL Server Books Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="c54d0-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="c54d0-153">See Also</span></span>
 [<span data-ttu-id="c54d0-154">Средства анализа таблиц для Excel</span><span class="sxs-lookup"><span data-stu-id="c54d0-154">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)


