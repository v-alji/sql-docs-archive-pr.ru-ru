---
title: Просмотр модели прогнозирования | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- forecasting [data mining]
- mining models, viewing
- mining model, time series
- time series [data mining]
ms.assetid: ad35a528-1949-4048-8678-3b9760c1c88c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d0b188c4ed6fba9bc5b1082725b17c99081c1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656827"
---
# <a name="browsing-a-forecasting-model"></a><span data-ttu-id="cbb38-102">Просмотр модели прогнозов</span><span class="sxs-lookup"><span data-stu-id="cbb38-102">Browsing a Forecasting Model</span></span>
  <span data-ttu-id="cbb38-103">При открытии модели прогнозирования с помощью **кнопки Обзор**модель отображается в интерактивном средстве просмотра, аналогичном средству просмотра моделей временных рядов в [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbb38-103">When you open a forecasting model using **Browse**, the model is displayed in an interactive viewer, similar to the time series model viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="cbb38-104">Средство просмотра помогает исследовать тенденции, сравнивать ряды, создавать прогнозы и получать информацию о модели и базовых данных.</span><span class="sxs-lookup"><span data-stu-id="cbb38-104">The viewer helps you explore trends, compare series, create predictions, and get information about the model and the underlying data.</span></span>  
  
##  <a name="explore-the-model"></a><a name="bkmk_Top"></a><span data-ttu-id="cbb38-105">Изучение модели</span><span class="sxs-lookup"><span data-stu-id="cbb38-105">Explore the Model</span></span>  
 <span data-ttu-id="cbb38-106">Средство просмотра **обзора** для моделей прогнозирования предоставляет представление диаграммы, которое показывает тенденции во времени и позволяет создавать прогнозы и представление модели, представляющее временные ряды в виде дерева принятия решений или дерева регрессии.</span><span class="sxs-lookup"><span data-stu-id="cbb38-106">The **Browse** viewer for forecasting models provides a chart view, which shows the trends over time and lets you create predictions, and a model view, which represents the time series as a decision tree or a regression tree.</span></span>  
  
-   [<span data-ttu-id="cbb38-107">Представление диаграммы</span><span class="sxs-lookup"><span data-stu-id="cbb38-107">Chart view</span></span>](#bkmk_charts)  
  
-   [<span data-ttu-id="cbb38-108">Представление модели</span><span class="sxs-lookup"><span data-stu-id="cbb38-108">Model view</span></span>](#bkmk_Model)  
  
 <span data-ttu-id="cbb38-109">Чтобы поэкспериментировать с моделью прогнозирования, можно использовать образец данных на вкладке Прогноз книги выборки данных и построить модель временных рядов с помощью [мастера прогнозов &#40;надстройки интеллектуального анализа данных для excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md) на ленте **интеллектуального анализа данных** или [Прогноз &#40;средства анализа таблиц для Excel&#41;](forecast-table-analysis-tools-for-excel.md) на ленте **анализ** .</span><span class="sxs-lookup"><span data-stu-id="cbb38-109">To experiment with a forecasting model, you can use the sample data on the Forecast tab of the sample data workbook, and build a time series model using the [Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md) in the **Data Mining** ribbon, or [Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) in the **Analyze** ribbon.</span></span>  
  
###  <a name="chart"></a><a name="bkmk_charts"></a><span data-ttu-id="cbb38-110">Диаграммы</span><span class="sxs-lookup"><span data-stu-id="cbb38-110">Chart</span></span>  
 <span data-ttu-id="cbb38-111">На вкладке **Диаграмма** отображается тенденция в ряде данных с течением времени, а также прогнозируемые значения.</span><span class="sxs-lookup"><span data-stu-id="cbb38-111">The **Chart** tab displays the trend in your data series over time, together with the predicted values.</span></span> <span data-ttu-id="cbb38-112">Вертикальная ось диаграммы представляет значения рядов, а горизонтальная — время.</span><span class="sxs-lookup"><span data-stu-id="cbb38-112">The vertical axis of the chart represents the values of the series, and the horizontal axis represents time.</span></span>  
  
##### <a name="explore-the-forecasting-chart"></a><span data-ttu-id="cbb38-113">Просмотр диаграммы прогнозирования</span><span class="sxs-lookup"><span data-stu-id="cbb38-113">Explore the forecasting chart</span></span>  
  
1.  <span data-ttu-id="cbb38-114">Эта модель содержит множество временных рядов, но для упрощения диаграммы можно выбрать для отображения один или несколько связанных рядов.</span><span class="sxs-lookup"><span data-stu-id="cbb38-114">This model contains multiple time series, but to simplify the chart, you can display a single series, or just a few related series.</span></span>  
  
     <span data-ttu-id="cbb38-115">![Исторические прогнозы в модели прогнозирования](media/dm13-forecast-chart-historicpredictions.gif "Исторические прогнозы в модели прогнозирования")</span><span class="sxs-lookup"><span data-stu-id="cbb38-115">![historical predictions in the forecasting model](media/dm13-forecast-chart-historicpredictions.gif "historical predictions in the forecasting model")</span></span>  
  
     <span data-ttu-id="cbb38-116">Выберите с помощью флажков прогноз только для Северной Америки или только для объема продаж.</span><span class="sxs-lookup"><span data-stu-id="cbb38-116">Use the check boxes to select the forecast for just North America, and just for sales Amount.</span></span>  
  
2.  <span data-ttu-id="cbb38-117">Щелкните **Прогноз шаги** и введите новое значение, чтобы определить, сколько значений времени должно отображаться на диаграмме в будущем.</span><span class="sxs-lookup"><span data-stu-id="cbb38-117">Click **Prediction Steps** and type a new value to control how many future time values you want to see in the chart.</span></span>  
  
     <span data-ttu-id="cbb38-118">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="cbb38-118">The default is 5.</span></span>  
  
3.  <span data-ttu-id="cbb38-119">Щелкните любую точку в строке (историческая или будущая), чтобы просмотреть точные значения для этого момента времени, отображаемые в условных обозначениях **интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="cbb38-119">Click any point in the line, either historical or future, to see the exact values for that point in time, displayed in the **Mining Legend**.</span></span>  
  
4.  <span data-ttu-id="cbb38-120">Диаграмма отображает как данные с предысторией, так и будущие данные.</span><span class="sxs-lookup"><span data-stu-id="cbb38-120">The chart displays both historical and future data.</span></span> <span data-ttu-id="cbb38-121">Обратите внимание на пунктирную линию с затененным фоном.</span><span class="sxs-lookup"><span data-stu-id="cbb38-121">Note the dotted line, with a shaded background.</span></span> <span data-ttu-id="cbb38-122">Эти значения — прогнозы на будущее, основанные на модели.</span><span class="sxs-lookup"><span data-stu-id="cbb38-122">These values are the future predictions, based on the model.</span></span>  
  
     <span data-ttu-id="cbb38-123">Исторические данные (на которых была построена модель) отображаются в левой части диаграммы.</span><span class="sxs-lookup"><span data-stu-id="cbb38-123">The historical data (which you used to build the model) is shown in the left side of the chart.</span></span>  
  
5.  <span data-ttu-id="cbb38-124">Выберите параметр **Показывать исторические прогнозы** , чтобы получить представление о стабильности временных рядов.</span><span class="sxs-lookup"><span data-stu-id="cbb38-124">Select the **Show historic predictions** option to get a sense for the stability of the time series.</span></span>  
  
     <span data-ttu-id="cbb38-125">![Прогнозы для отдельных рядов в модели](media/dm13-forecast-chart-singleseries.gif "Прогнозы для отдельных рядов в модели")</span><span class="sxs-lookup"><span data-stu-id="cbb38-125">![forecasts for a single series in the model](media/dm13-forecast-chart-singleseries.gif "forecasts for a single series in the model")</span></span>  
  
     <span data-ttu-id="cbb38-126">Исторические прогнозы — это значения, предсказанные на основе рядов до этой точки в сравнении с фактическими историческими значениями.</span><span class="sxs-lookup"><span data-stu-id="cbb38-126">Historical predictions are values predicted based on the series to that point, which are compared to actual historical values.</span></span> <span data-ttu-id="cbb38-127">Если пунктирная линия (обозначающая предсказанные значения) отходит слишком далеко от сплошной (фактические значения), это означает, что первая часть ряда неточно предсказывает последующие значения.</span><span class="sxs-lookup"><span data-stu-id="cbb38-127">If the dotted line (with the predicted values) is far apart from the solid line (the actual values), it means the first part of the series perhaps does not accurately predict the later values.</span></span> <span data-ttu-id="cbb38-128">Возможно, необходимо больше данных, а возможно, это просто признак изменчивости в цикле.</span><span class="sxs-lookup"><span data-stu-id="cbb38-128">You might need more data, or it might simply be an indicator of volatility in the cycle.</span></span>  
  
6.  <span data-ttu-id="cbb38-129">Выберите параметр **Показать отклонения** , чтобы отобразить планки погрешностей в диаграмме.</span><span class="sxs-lookup"><span data-stu-id="cbb38-129">Select the **Show Deviations** option to display error bars in the chart.</span></span>  
  
     <span data-ttu-id="cbb38-130">Строки погрешностей позволят визуально оценить изменчивость прогнозов.</span><span class="sxs-lookup"><span data-stu-id="cbb38-130">The error bars let you visually assess the variability of the predictions.</span></span> <span data-ttu-id="cbb38-131">Качество прогнозов изменяется в зависимости от исходных данных, но при повышении количества этапов прогнозирования отклонения стабильно будут расти.</span><span class="sxs-lookup"><span data-stu-id="cbb38-131">The quality of predictions varies depending on your source data, but as you increase the number of prediction steps, you should see the deviations steadily increase.</span></span>  
  
 <span data-ttu-id="cbb38-132">**Советы**</span><span class="sxs-lookup"><span data-stu-id="cbb38-132">**Tips**</span></span>  
  
-   <span data-ttu-id="cbb38-133">Чтобы переключить отображение **условных обозначений интеллектуального анализа данных**, щелкните правой кнопкой мыши любую точку диаграммы.</span><span class="sxs-lookup"><span data-stu-id="cbb38-133">To toggle display of the **Mining Legend**, right-click any point in the chart.</span></span>  
  
     <span data-ttu-id="cbb38-134">Можно просмотреть конкретный временной диапазон, щелкнув диаграмму, перетащив выбранное время по диаграмме и щелкнув вновь для увеличения выбранного диапазона.</span><span class="sxs-lookup"><span data-stu-id="cbb38-134">You can view a specific time range by clicking the chart, dragging a time selection across the chart, and then clicking again to zoom in on the selected range.</span></span>  
  
-   <span data-ttu-id="cbb38-135">Чтобы получить копию текущей диаграммы, нажмите кнопку **Копировать в Excel**, а затем выберите лист в Excel.</span><span class="sxs-lookup"><span data-stu-id="cbb38-135">To get a copy of the current chart, click **Copy to Excel**, then click a worksheet in Excel.</span></span> <span data-ttu-id="cbb38-136">График вставляется в лист со всеми заданными параметрами, включая условные обозначения.</span><span class="sxs-lookup"><span data-stu-id="cbb38-136">A graphic is inserted in the sheet using all the options you had set, including a legend.</span></span>  
  
     <span data-ttu-id="cbb38-137">Однако этот рисунок является статическим, поэтому вы не можете изменить условные обозначения или просмотреть базовые данные. Если требуется более интерактивное представление диаграммы, используйте [средства просмотра Visio](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="cbb38-137">However, this graphic is static so you cannot edit the legend or view the underlying data; if you need a more interactive chart view, use the [Visio viewers](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span></span>  
  
-   <span data-ttu-id="cbb38-138">В строке меню средства просмотра щелкните **ABS** , чтобы переключиться между абсолютными и относительными кривыми.</span><span class="sxs-lookup"><span data-stu-id="cbb38-138">Click **Abs** in the viewer menu bar to toggle between absolute and relative curves.</span></span>  
  
     <span data-ttu-id="cbb38-139">Эта возможность полезна, если диаграмма содержит несколько моделей, но масштабы данных для моделей значительно различаются.</span><span class="sxs-lookup"><span data-stu-id="cbb38-139">This option is useful if your chart contains multiple models, but the scale of the data for each model is very different.</span></span>  
  
     <span data-ttu-id="cbb38-140">Например, если магазины региона Pacific новые и продажи в них низкие, а при этом используются абсолютные значения, то линия, представляющая регион Pacific, может показаться плоской, что помешает увидеть фактические изменения, тогда как в других моделях они будут представлены в более удобном масштабе.</span><span class="sxs-lookup"><span data-stu-id="cbb38-140">For example, if the Pacific region stores were new and sales were low, and if absolute values are used, the line showing Pacific sales might appear flat, making it difficult to see actual changes, whereas the other models would be displayed at a more normal scale.</span></span>  
  
     <span data-ttu-id="cbb38-141">Переключение представления на относительные кривые поможет нормализовать масштаб различных моделей и отображать изменения в процентах, а не в абсолютных значениях.</span><span class="sxs-lookup"><span data-stu-id="cbb38-141">By switching the view to use relative values, you can normalize the scale of different models, and display differences as a percent of change.</span></span> <span data-ttu-id="cbb38-142">Если изменения выражаются в относительных величинах для каждой модели, их можно представить на одном графике без значительного искажения.</span><span class="sxs-lookup"><span data-stu-id="cbb38-142">When change is relative to each model, they can be displayed in the same graph without significant distortion.</span></span>  
  
 [<span data-ttu-id="cbb38-143">Просмотр модели</span><span class="sxs-lookup"><span data-stu-id="cbb38-143">Explore the Model</span></span>](#bkmk_Top)  
  
###  <a name="model"></a><a name="bkmk_Model"></a><span data-ttu-id="cbb38-144">Моделировать</span><span class="sxs-lookup"><span data-stu-id="cbb38-144">Model</span></span>  
 <span data-ttu-id="cbb38-145">Модель прогнозирования также можно представить в виде дерева принятия решений или, если ряды большей частью линейны, в виде регрессионной модели.</span><span class="sxs-lookup"><span data-stu-id="cbb38-145">A forecasting model can also be represented as a decision tree, or, if the series is mostly linear, a regression model.</span></span>  
  
 <span data-ttu-id="cbb38-146">Например, в данной модели имеется различие в формуле регрессии на основании определенного условия, поэтому дерево разделится на две ветви, каждая со своей формулой регрессии.</span><span class="sxs-lookup"><span data-stu-id="cbb38-146">For example, in this model, there is a difference in the regression formula based on a certain condition, so the tree splits into two branches, each with a different regression formula.</span></span>  
  
 <span data-ttu-id="cbb38-147">![Фильтрация отдельных рядов в модели прогнозирования](media/dm13-forecast-model-northamerica.gif "Фильтрация отдельных рядов в модели прогнозирования")</span><span class="sxs-lookup"><span data-stu-id="cbb38-147">![Filter single series in the forecasting model](media/dm13-forecast-model-northamerica.gif "Filter single series in the forecasting model")</span></span>  
  
##### <a name="explore-the-forecasting-model-as-a-tree"></a><span data-ttu-id="cbb38-148">Просмотр модели прогнозирования в виде дерева</span><span class="sxs-lookup"><span data-stu-id="cbb38-148">Explore the forecasting model as a tree</span></span>  
  
1.  <span data-ttu-id="cbb38-149">Щелкните раскрывающийся список **дерево** и выберите модель для вывода.</span><span class="sxs-lookup"><span data-stu-id="cbb38-149">Click the **Tree** dropdown list and choose a model to display.</span></span>  
  
     <span data-ttu-id="cbb38-150">Для каждого прогнозируемого атрибута отображается отдельное дерево или отдельный узел регрессии.</span><span class="sxs-lookup"><span data-stu-id="cbb38-150">A separate tree or regression node is displayed for each predictable attribute.</span></span> <span data-ttu-id="cbb38-151">Например, если в данных содержатся сведения о продажах в Европе, Северной Америке и Тихоокеанском регионе, они будут представлены тремя различными моделями, по одной для каждого ряда данных.</span><span class="sxs-lookup"><span data-stu-id="cbb38-151">For example, if your data contains sales for Europe, North America, and the Pacific, there would three different models, one for each data series.</span></span>  
  
2.  <span data-ttu-id="cbb38-152">Перетащите ползунок « **Показывать уровень** », чтобы отфильтровать нижние уровни дерева и сосредоточиться на наиболее важных разбиениях.</span><span class="sxs-lookup"><span data-stu-id="cbb38-152">Drag the **Show Level** slider to filter out lower levels of the tree, and focus on the most important splits.</span></span>  
  
3.  <span data-ttu-id="cbb38-153">Щелкните каждый узел, чтобы просмотреть описательную статистику в условных обозначениях **интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="cbb38-153">Click each node to view some descriptive statistics in the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="cbb38-154">Если задержать указатель мыши над узлом, в подсказке будет показана та же статистика и полная формула, описывающая узел.</span><span class="sxs-lookup"><span data-stu-id="cbb38-154">As you pause over a node with the mouse, a ToolTip also displays the same statistics, as well as the full formula describing that node.</span></span>  
  
4.  <span data-ttu-id="cbb38-155">Если вы хотите скопировать данные в **обозначения интеллектуального анализа данных**, щелкните правой кнопкой мыши **Условные обозначения интеллектуального анализа данных**, выберите **Копировать**и щелкните внутри листа Excel.</span><span class="sxs-lookup"><span data-stu-id="cbb38-155">If you want to copy the information in the **Mining Legend**, right-click the **Mining Legend**, select **Copy**, and click inside your Excel worksheet.</span></span> <span data-ttu-id="cbb38-156">Параметр **Копировать в Excel** копирует диаграмму, а не статистику.</span><span class="sxs-lookup"><span data-stu-id="cbb38-156">The **Copy to Excel** option copies the graph, not the statistics.</span></span>  
  
 [<span data-ttu-id="cbb38-157">Просмотр модели</span><span class="sxs-lookup"><span data-stu-id="cbb38-157">Explore the Model</span></span>](#bkmk_Top)  
  
## <a name="see-also"></a><span data-ttu-id="cbb38-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="cbb38-158">See Also</span></span>  
 [<span data-ttu-id="cbb38-159">Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="cbb38-159">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
