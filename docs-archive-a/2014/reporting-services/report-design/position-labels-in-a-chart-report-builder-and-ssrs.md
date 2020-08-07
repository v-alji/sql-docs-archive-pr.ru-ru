---
title: Размещение меток на диаграмме (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5db74e0b-8be8-4b47-b386-faab56dffa9b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e90cbf04e0282454658e6324f0ba6600a99cb718
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727929"
---
# <a name="position-labels-in-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="02f28-102">Размещение меток на диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="02f28-102">Position Labels in a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="02f28-103">Поскольку формы всех типов диаграмм различны, метки точек данных помещаются в оптимальные положения, не ухудшающие удобочитаемость диаграммы.</span><span class="sxs-lookup"><span data-stu-id="02f28-103">Because each chart type has a different shape, data point labels are placed in an optimal location so as not to interfere on the chart.</span></span> <span data-ttu-id="02f28-104">Позиции меток по умолчанию зависят от типа диаграммы:</span><span class="sxs-lookup"><span data-stu-id="02f28-104">The default position of the labels depends varies with the chart type:</span></span>  
  
-   <span data-ttu-id="02f28-105">на диаграммах с накоплением метки могут располагаться только внутри рядов;</span><span class="sxs-lookup"><span data-stu-id="02f28-105">On stacked charts, labels can only be positioned inside the series.</span></span>  
  
-   <span data-ttu-id="02f28-106">на воронкообразных и пирамидальных диаграммах метки помещаются за пределами столбца;</span><span class="sxs-lookup"><span data-stu-id="02f28-106">On funnel or pyramid charts, labels are placed on the outside in a column.</span></span>  
  
-   <span data-ttu-id="02f28-107">на круговых диаграммах метки помещаются внутри отдельных срезов;</span><span class="sxs-lookup"><span data-stu-id="02f28-107">On pie charts, labels are placed inside the individual slices on a pie chart.</span></span>  
  
-   <span data-ttu-id="02f28-108">на линейчатых диаграммах метки помещаются за пределами столбцов, представляющих точки данных;</span><span class="sxs-lookup"><span data-stu-id="02f28-108">On bar charts, labels are placed outside of the bars that represent data points.</span></span>  
  
-   <span data-ttu-id="02f28-109">на полярных диаграммах метки помещаются за пределами круговой области, представляющей точки данных.</span><span class="sxs-lookup"><span data-stu-id="02f28-109">On polar charts, labels are placed outside of the circular area that represents data points.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-position-of-point-labels-in-a-pie-chart"></a><span data-ttu-id="02f28-110">Изменение положения меток точек на круговой диаграмме</span><span class="sxs-lookup"><span data-stu-id="02f28-110">To change the position of point labels in a Pie chart</span></span>  
  
1.  <span data-ttu-id="02f28-111">Создайте круговую диаграмму.</span><span class="sxs-lookup"><span data-stu-id="02f28-111">Create a pie chart.</span></span>  
  
2.  <span data-ttu-id="02f28-112">В области конструктора щелкните правой кнопкой мыши диаграмму и выберите команду **Отобразить метки данных**.</span><span class="sxs-lookup"><span data-stu-id="02f28-112">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="02f28-113">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="02f28-113">Open the Properties pane.</span></span> <span data-ttu-id="02f28-114">На вкладке **Вид** щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="02f28-114">On the **View** tab, click **Properties**.</span></span>  
  
4.  <span data-ttu-id="02f28-115">Щелкните диаграмму в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="02f28-115">On the design surface, click the chart.</span></span> <span data-ttu-id="02f28-116">В панели «Свойства» отображаются свойства диаграммы.</span><span class="sxs-lookup"><span data-stu-id="02f28-116">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="02f28-117">В разделе **Общие** разверните узел **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="02f28-117">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="02f28-118">Отобразится список атрибутов круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="02f28-118">A list of attributes for the pie chart is displayed.</span></span>  
  
6.  <span data-ttu-id="02f28-119">Выберите значение для свойства PieLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="02f28-119">Select a value for the PieLabelStyle property.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-a-funnel-or-pyramid-chart"></a><span data-ttu-id="02f28-120">Изменение положения меток точек на воронкообразной или пирамидальной диаграмме</span><span class="sxs-lookup"><span data-stu-id="02f28-120">To change the position of point labels in a Funnel or Pyramid chart</span></span>  
  
1.  <span data-ttu-id="02f28-121">Создайте воронкообразную или пирамидальную диаграмму.</span><span class="sxs-lookup"><span data-stu-id="02f28-121">Create a funnel or pyramid chart.</span></span>  
  
2.  <span data-ttu-id="02f28-122">В области конструктора щелкните правой кнопкой мыши диаграмму и выберите команду **Отобразить метки данных**.</span><span class="sxs-lookup"><span data-stu-id="02f28-122">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="02f28-123">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="02f28-123">Open the Properties pane.</span></span> <span data-ttu-id="02f28-124">На вкладке **Вид** щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="02f28-124">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="02f28-125">Щелкните диаграмму в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="02f28-125">On the design surface, click the chart.</span></span> <span data-ttu-id="02f28-126">В панели «Свойства» отображаются свойства диаграммы.</span><span class="sxs-lookup"><span data-stu-id="02f28-126">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="02f28-127">В разделе **Общие** разверните узел **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="02f28-127">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="02f28-128">Отобразится список атрибутов воронкообразной диаграммы.</span><span class="sxs-lookup"><span data-stu-id="02f28-128">A list of attributes for the funnel chart is displayed.</span></span>  
  
6.  <span data-ttu-id="02f28-129">Для воронкообразной диаграммы выберите значение для свойства FunnelLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="02f28-129">For a funnel chart, select a value for the FunnelLabelStyle property.</span></span> <span data-ttu-id="02f28-130">Для воронкообразной диаграммы выберите значение для свойства PyramidLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="02f28-130">For a pyramid chart, select a value for the PyramidLabelStyle property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02f28-131">Если это свойство имеет значение `OutsideInColumn`, метки отображаются в вертикальном столбце.</span><span class="sxs-lookup"><span data-stu-id="02f28-131">When this property is set to a value `OutsideInColumn`, the labels are drawn in a vertical column.</span></span> <span data-ttu-id="02f28-132">Положение столбца изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="02f28-132">There is no way to change the position of the column.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-a-bar-chart"></a><span data-ttu-id="02f28-133">Изменение положения меток точек на линейчатой диаграмме</span><span class="sxs-lookup"><span data-stu-id="02f28-133">To change the position of point labels in a Bar chart</span></span>  
  
1.  <span data-ttu-id="02f28-134">Создайте линейчатую диаграмму.</span><span class="sxs-lookup"><span data-stu-id="02f28-134">Create a bar chart.</span></span>  
  
2.  <span data-ttu-id="02f28-135">В области конструктора щелкните правой кнопкой мыши диаграмму и выберите команду **Отобразить метки данных**.</span><span class="sxs-lookup"><span data-stu-id="02f28-135">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="02f28-136">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="02f28-136">Open the Properties pane.</span></span> <span data-ttu-id="02f28-137">На вкладке **Вид** щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="02f28-137">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="02f28-138">Щелкните диаграмму в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="02f28-138">On the design surface, click the chart.</span></span> <span data-ttu-id="02f28-139">В панели «Свойства» отображаются свойства диаграммы.</span><span class="sxs-lookup"><span data-stu-id="02f28-139">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="02f28-140">В разделе **Общие** разверните узел **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="02f28-140">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="02f28-141">Отобразится список атрибутов линейчатой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="02f28-141">A list of attributes for the bar chart is displayed.</span></span>  
  
6.  <span data-ttu-id="02f28-142">Выберите значение для свойства BarLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="02f28-142">Select a value for the BarLabelStyle property.</span></span>  
  
 <span data-ttu-id="02f28-143">Если стиль линейчатой диаграммы имеет значение `Outside`, метки будут располагаться за пределами линейки, пока она помещается в области диаграммы.</span><span class="sxs-lookup"><span data-stu-id="02f28-143">When the bar label style is set to `Outside`, the labels will be placed outside of the bar, as long as it fits in the chart area.</span></span> <span data-ttu-id="02f28-144">Если метку не удается поместить за пределами линейки, но ее можно расположить в области диаграммы, метка помещается внутри линейки в позиции, ближайшей к концу линейки.</span><span class="sxs-lookup"><span data-stu-id="02f28-144">If the label cannot be placed outside of the bar but inside of the chart area, the label is placed inside the bar at the position closest to the end of the bar.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-an-area-column-line-or-scatter-chart"></a><span data-ttu-id="02f28-145">Изменение положения меток точек в диаграмме с областями, гистограмме, графике и точечной диаграмме</span><span class="sxs-lookup"><span data-stu-id="02f28-145">To change the position of point labels in an Area, Column, Line or Scatter chart</span></span>  
  
1.  <span data-ttu-id="02f28-146">Создайте диаграмму с областями, гистограмму, график или точечную диаграмму.</span><span class="sxs-lookup"><span data-stu-id="02f28-146">Create an Area, Column, Line or Scatter chart.</span></span>  
  
2.  <span data-ttu-id="02f28-147">В области конструктора щелкните правой кнопкой мыши диаграмму и выберите команду **Отобразить метки данных**.</span><span class="sxs-lookup"><span data-stu-id="02f28-147">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="02f28-148">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="02f28-148">Open the Properties pane.</span></span> <span data-ttu-id="02f28-149">На вкладке **Вид** щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="02f28-149">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="02f28-150">Щелкните ряд в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="02f28-150">On the design surface, click the series.</span></span> <span data-ttu-id="02f28-151">На панели «Свойства» отображаются свойства ряда.</span><span class="sxs-lookup"><span data-stu-id="02f28-151">The properties for the series are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="02f28-152">В разделе **Данные** разверните узел **Точка данных** , а затем узел **Метка**.</span><span class="sxs-lookup"><span data-stu-id="02f28-152">In the **Data** section, expand the **DataPoint** node, then expand the **Label**node.</span></span>  
  
6.  <span data-ttu-id="02f28-153">Выберите значение для свойства Position.</span><span class="sxs-lookup"><span data-stu-id="02f28-153">Select a value for the Position property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02f28-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="02f28-154">See Also</span></span>  
 <span data-ttu-id="02f28-155">[Круговые диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="02f28-155">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="02f28-156">[Линейчатые диаграммы (построитель отчетов и службы SSRS)](bar-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="02f28-156">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="02f28-157">[Форматирование меток оси на диаграмме (построитель отчетов и службы SSRS)](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="02f28-157">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="02f28-158">[Форматирование меток оси в виде значений даты или валюты &#40;построитель отчетов и службы SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="02f28-158">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="02f28-159">[Отображение меток точек данных за пределами круговой диаграммы (построитель отчетов и службы SSRS)](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="02f28-159">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="02f28-160">Форматирование точек данных на диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="02f28-160">Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)  
  
  
