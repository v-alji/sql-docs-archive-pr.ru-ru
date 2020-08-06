---
title: Заполнение по примеру (средства анализа таблиц для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- fill from example
ms.assetid: dac57d8f-1c65-4878-8ea0-9c680df5e4fb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 69ff9f554c51240eb6f9151718d30677bfb57996
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732194"
---
# <a name="fill-from-example-table-analysis-tools-for-excel"></a><span data-ttu-id="8b1b0-102">Заполнение по примеру (средства анализа таблиц для Excel)</span><span class="sxs-lookup"><span data-stu-id="8b1b0-102">Fill From Example (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="8b1b0-103">![Кнопка «Заполнение по примеру» ленты «Средства анализа таблиц»](media/tat-fillex.gif "Кнопка «Заполнение по примеру» ленты «Средства анализа таблиц»")</span><span class="sxs-lookup"><span data-stu-id="8b1b0-103">![Fill From Example button in Table Analysis Tools](media/tat-fillex.gif "Fill From Example button in Table Analysis Tools")</span></span>  
  
 <span data-ttu-id="8b1b0-104">Средство **Заполнение по примеру** позволяет создавать новые столбцы данных на основе существующих значений.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-104">The **Fill From Example** tool helps you build new columns of data based on existing values.</span></span>  
  
 <span data-ttu-id="8b1b0-105">Например, предположим, что данные содержат столбец « **Сумма покупки** », столбец « **количество заказов** » и столбец **Premier Customer** , основанный на формуле с другими столбцами.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-105">For example, suppose your data contains a **Purchase Amount** column, an **Orders Quantity** column, and a **Premier Customer** column that is based on some formula using the other columns.</span></span> <span data-ttu-id="8b1b0-106">Если столбец **Premier Customer** содержит много пустых строк, для определения недостающих значений можно использовать столбцы **Сумма покупки** и **количество заказов** в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-106">If the  **Premier Customer** column contains many blank rows, you could use the **Purchase Amount** and **Orders Quantity** columns as the inputs, to infer the missing values.</span></span> <span data-ttu-id="8b1b0-107">Средство анализирует существующие закономерности в данных вместе с введенными примерами и прогнозирует, какую категорию назначить каждому клиенту.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-107">The tool analyzes existing patterns in the data together with the examples you entered, and predicts which category to assign to each customer.</span></span>  
  
 <span data-ttu-id="8b1b0-108">Если результат окажется неудовлетворительным, можно сделать уточнение, введя дополнительные примеры значений.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-108">If you are not satisfied with the results, you can refine the results by providing more examples.</span></span>  
  
## <a name="using-the-fill-from-example-tool"></a><span data-ttu-id="8b1b0-109">Использование средства «Заполнение по примеру»</span><span class="sxs-lookup"><span data-stu-id="8b1b0-109">Using the Fill From Example Tool</span></span>  
  
1.  <span data-ttu-id="8b1b0-110">На ленте **анализ** нажмите кнопку **заполнить по примеру**.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-110">In the **Analyze** ribbon, click **Fill From Example**.</span></span>  
  
2.  <span data-ttu-id="8b1b0-111">Средство автоматически выберет столбец для заполнения результатами анализа, после чего можно принять или переопределить полученные в результате анализа данные.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-111">The tool will automatically pick a column to fill based on analysis of the data, and you can either accept or override this suggestion.</span></span>  
  
3.  <span data-ttu-id="8b1b0-112">Создайте столбец для новых данных и введите примеры значений данных, для которых следует сформировать прогноз.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-112">Create a column for the new data, and type in examples of the data that you want to predict.</span></span> <span data-ttu-id="8b1b0-113">Необходимо ввести по крайней мере один пример для каждого значения, для которого требуется сформировать прогноз.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-113">Make sure that there is at least one example for every value that you want to predict.</span></span> <span data-ttu-id="8b1b0-114">Если данные вводятся в существующий столбец, выберите столбец, содержащий недостающие данные.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-114">If you are filling in data in an existing column, select the column that has missing values.</span></span>  
  
4.  <span data-ttu-id="8b1b0-115">При необходимости нажмите кнопку **выбрать столбцы для использования при анализе**.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-115">Optionally, click **Choose columns to be used in analysis**.</span></span> <span data-ttu-id="8b1b0-116">В диалоговом окне **Выбор дополнительных столбцов** укажите столбцы, которые, скорее всего, будут использоваться при заполнении недостающих данных.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-116">In the **Advanced Columns Selection** dialog box, specify the columns that are most likely to be useful when filling in the missing data.</span></span>  
  
     <span data-ttu-id="8b1b0-117">Например, если исходя из опыта известно, что существует причинно-следственная связь между одним столбцом и другим столбцом, в котором отсутствуют некоторые значения, то для получения лучших результатов, возможно, нет необходимости использовать остальные столбцы.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-117">For example, if you know from experience that there is a causal effect between one column and the column that has missing values, you can deselect other columns to get better results.</span></span>  
  
     <span data-ttu-id="8b1b0-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="8b1b0-119">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-119">Click **Run**.</span></span>  
  
     <span data-ttu-id="8b1b0-120">После завершения анализа средство создает новый лист **шаблонов** , содержащий результаты анализа.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-120">When analysis is complete, the tool creates a new **Patterns** worksheet that contains the results of analysis.</span></span> <span data-ttu-id="8b1b0-121">Отчет перечисляет правила или ключевые факторы влияния, которые были найдены, а также показывает вероятность для каждого правила.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-121">The report lists the rules, or key influencers, that were found, and shows the probability for each rule.</span></span>  
  
     <span data-ttu-id="8b1b0-122">Средство также автоматически добавляет столбец, который содержит новые значения, в таблицу исходных данных.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-122">The tool also automatically adds a column that contains the new values to the original data table.</span></span> <span data-ttu-id="8b1b0-123">Эти значения можно просмотреть и сравнить с первоначальными значениями.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-123">You can review the values and compare them against the original.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="8b1b0-124">Требования</span><span class="sxs-lookup"><span data-stu-id="8b1b0-124">Requirements</span></span>  
 <span data-ttu-id="8b1b0-125">Анализ выполняется только для данных, расположенных в столбцах.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-125">You can only work with data in columns.</span></span> <span data-ttu-id="8b1b0-126">Если ряд, который должен быть заполнен, хранится в виде строки, можно использовать функцию вставки и транспонирования Excel для представления данных в формате столбца.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-126">If the series that you want to fill is stored in a row, you can use the Paste, Transpose function in Excel to change the data to a columnar format.</span></span>  
  
## <a name="understanding-the-pattern-report"></a><span data-ttu-id="8b1b0-127">Основные сведения об отчете о закономерностях</span><span class="sxs-lookup"><span data-stu-id="8b1b0-127">Understanding the Pattern Report</span></span>  
 <span data-ttu-id="8b1b0-128">При запуске средства **заполнения из примера** создается отчет, содержащий дополнительные сведения об обнаруженных закономерностях.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-128">When you run the **Fill From Example** tool, a report is created that provides more information about the patterns that were detected.</span></span> <span data-ttu-id="8b1b0-129">Эти шаблоны используются при экстраполяции новых значений данных.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-129">These patterns are used for extrapolating new data values.</span></span>  
  
 <span data-ttu-id="8b1b0-130">Отчет о закономерностях раскрывает ключевые факторы, влияющие на каждое прогнозируемое значение.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-130">The Pattern Report shows the key influencers for each value that was predicted.</span></span> <span data-ttu-id="8b1b0-131">Описание каждого влияющего фактора или правила содержит в себе имя столбца, значение столбца и относительное влияние данного правила на прогноз.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-131">Each influencer or rule is described as a combination of a column, the value in that column, and the relative impact of the rule on the prediction.</span></span>  
  
 <span data-ttu-id="8b1b0-132">Например, если выполняется анализ листа, содержащего данные о расстоянии доставки заказанных товаров, то логично ожидать, что стоимость доставки практически напрямую зависит от расстояния до пункта назначения.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-132">For example, if you were trying to fill in a worksheet that shows the shipping distance for orders, you might logically expect the destination to have a strong impact on the value for shipping distance.</span></span> <span data-ttu-id="8b1b0-133">В этом случае отчет может содержать следующую строку.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-133">In this case, the report might contain the following row:</span></span>  
  
|<span data-ttu-id="8b1b0-134">Столбец</span><span class="sxs-lookup"><span data-stu-id="8b1b0-134">Column</span></span>|<span data-ttu-id="8b1b0-135">Значение</span><span class="sxs-lookup"><span data-stu-id="8b1b0-135">Value</span></span>|<span data-ttu-id="8b1b0-136">Подходит</span><span class="sxs-lookup"><span data-stu-id="8b1b0-136">Favors</span></span>|<span data-ttu-id="8b1b0-137">Относительное влияние</span><span class="sxs-lookup"><span data-stu-id="8b1b0-137">Relative Impact</span></span>|  
|------------|-----------|------------|---------------------|  
|<span data-ttu-id="8b1b0-138">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="8b1b0-138">StateProvinceCode</span></span>|<span data-ttu-id="8b1b0-139">AB</span><span class="sxs-lookup"><span data-stu-id="8b1b0-139">AB</span></span>|<span data-ttu-id="8b1b0-140">>500 километров</span><span class="sxs-lookup"><span data-stu-id="8b1b0-140">>500 kilometers</span></span>|<span data-ttu-id="8b1b0-141">80 %</span><span class="sxs-lookup"><span data-stu-id="8b1b0-141">80%</span></span>|  
  
 <span data-ttu-id="8b1b0-142">Это означает, что значение AB в столбце **статепровинцекоде** строго прогнозирует расстояние доставки >500 километров.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-142">This means that the value AB in the **StateProvinceCode** column strongly predicts a shipping distance of >500 kilometers.</span></span>  
  
 <span data-ttu-id="8b1b0-143">Обычно прогнозы основываются на более сложных закономерностях, чем приведенная в данном примере, и отчет может содержать большое количество строк правил для каждого прогноза.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-143">Typically, predictions are based on patterns that are far more complex than this example, and the report may contain many rows of rules for each prediction.</span></span> <span data-ttu-id="8b1b0-144">При получении окончательного значения прогноза учитывается влияние всех правил.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-144">The effect of all the rules are combined to derive the predicted value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b1b0-145">**Относительное влияние** отображается в виде затененной полосы.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-145">**Relative Impact** is shown as a shaded bar.</span></span> <span data-ttu-id="8b1b0-146">Чем длиннее эта полоса, тем больше вероятность того, что данное правило оказалось способным выработать прогноз для заполненного значения.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-146">The longer the bar, the greater the probability that this rule is predictive of the filled-in value.</span></span>  
  
 <span data-ttu-id="8b1b0-147">Средство также добавляет новый столбец в исходную таблицу данных с именем \<column name> Extended.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-147">The tool also adds a new column to the original data table, named \<column name> Extended.</span></span>  
  
 <span data-ttu-id="8b1b0-148">Если исходный столбец с данными уже содержал значение, это значение будет скопировано в новый столбец.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-148">If the original data column contained a value, that value is copied into the new column.</span></span> <span data-ttu-id="8b1b0-149">Однако если в исходном столбце не было значения, в новый столбец будет помещено значение прогноза, рассчитанное мастером.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-149">However, if the original column contained a blank cell, the new column contains the value that was predicted by the wizard.</span></span>  
  
## <a name="related-tools-and-information"></a><span data-ttu-id="8b1b0-150">Дополнительные средства и сведения</span><span class="sxs-lookup"><span data-stu-id="8b1b0-150">Related Tools and Information</span></span>  
 <span data-ttu-id="8b1b0-151">Для проверки распределения значений в столбце Excel можно также использовать мастер [просмотра данных](explore-data-sql-server-data-mining-add-ins.md) , доступный в клиенте интеллектуального анализа данных для Excel.</span><span class="sxs-lookup"><span data-stu-id="8b1b0-151">You can also use the [Explore Data](explore-data-sql-server-data-mining-add-ins.md) wizard, available in the Data Mining Client for Excel, to examine the distribution of values in an Excel column.</span></span> <span data-ttu-id="8b1b0-152">Дополнительные сведения см. в разделе [Просмотр и очистка данных](exploring-and-cleaning-data.md).</span><span class="sxs-lookup"><span data-stu-id="8b1b0-152">For more information, see [Exploring and Cleaning Data](exploring-and-cleaning-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b1b0-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b1b0-153">See Also</span></span>  
 [<span data-ttu-id="8b1b0-154">Средства анализа таблиц для Excel</span><span class="sxs-lookup"><span data-stu-id="8b1b0-154">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  
