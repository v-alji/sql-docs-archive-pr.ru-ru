---
title: Сбор мелких срезов на круговой диаграмме (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 21c2b8cb-b9ca-4bc0-bf49-50ba432562f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2302217843864115847aeb544d1c64727b8ad3a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664719"
---
# <a name="collect-small-slices-on-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="6d63e-102">Сбор мелких срезов на круговой диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6d63e-102">Collect Small Slices on a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6d63e-103">Если круговая диаграмма содержит слишком много данных, она выглядит загроможденной.</span><span class="sxs-lookup"><span data-stu-id="6d63e-103">When pie charts display too many points of data, they begin to look cluttered.</span></span> <span data-ttu-id="6d63e-104">Чтобы исправить это, можно отобразить на круговой диаграмме все данные, находящиеся в пределах определенного значения, одним срезом.</span><span class="sxs-lookup"><span data-stu-id="6d63e-104">To resolve this issue, you can show all data that falls beneath a certain value as one slice on the pie chart.</span></span>  
  
 <span data-ttu-id="6d63e-105">Чтобы собрать мелкие срезы в один, сначала следует решить, как будет измеряться порог для сбора мелких срезов — в процентном отношении от круговой диаграммы или как фиксированное значение.</span><span class="sxs-lookup"><span data-stu-id="6d63e-105">To collect small slices into one slice, first decide whether your threshold for collecting small slices is measured as a percentage of the pie chart or as a fixed value.</span></span> <span data-ttu-id="6d63e-106">Затем задайте свойства CollectedThreshold и CollectedThresholdUsePercent. Присвойте свойству CollectedThreshold либо значение в процентах для диаграммы (собираемые данные не будут превышать это значение), либо фактическое пороговое значение собираемых данных.</span><span class="sxs-lookup"><span data-stu-id="6d63e-106">Then set the CollectedThreshold and CollectedThresholdUsePercent properties.Set the CollectedThreshold property to either the percentage of the chart that a value must fall below to be collected, or the actual threshold data value for collection.</span></span> <span data-ttu-id="6d63e-107">Присвойте свойству CollectedThresholdUsePercent значение, чтобы `True` использовать процентное значение, или `False` для использования фактического значения.</span><span class="sxs-lookup"><span data-stu-id="6d63e-107">Set the CollectedThresholdUsePercent property to `True` to use a percentage or `False` to use an actual value.</span></span>  
  
 <span data-ttu-id="6d63e-108">Можно также собрать мелкие срезы во вторую круговую диаграмму, вызываемую из собранного среза первой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="6d63e-108">You can also collect small slices into a second pie chart that is called out from a collected slice of the first pie chart.</span></span> <span data-ttu-id="6d63e-109">Вторая круговая диаграмма отображается справа от исходной круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="6d63e-109">The second pie chart is drawn to the right of the original pie chart.</span></span>  
  
 <span data-ttu-id="6d63e-110">Нельзя объединить в один срез срезы воронкообразных и пирамидальных диаграмм.</span><span class="sxs-lookup"><span data-stu-id="6d63e-110">You cannot combine slices of funnel or pyramid charts into one slice.</span></span>  
  
 <span data-ttu-id="6d63e-111">Пример этой диаграммы доступен в виде образца отчета.</span><span class="sxs-lookup"><span data-stu-id="6d63e-111">An example of this chart is available as a sample report.</span></span> <span data-ttu-id="6d63e-112">Дополнительные сведения о скачивании этого и других примеров отчетов см. в статье [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="6d63e-112">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
### <a name="to-collect-small-slices-into-a-single-slice-on-a-pie-chart"></a><span data-ttu-id="6d63e-113">Сбор мелких срезов в один срез круговой диаграммы</span><span class="sxs-lookup"><span data-stu-id="6d63e-113">To collect small slices into a single slice on a pie chart</span></span>  
  
1.  <span data-ttu-id="6d63e-114">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="6d63e-114">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="6d63e-115">В области конструктора щелкните любой сегмент круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="6d63e-115">On the design surface, click on any slice of the pie chart.</span></span> <span data-ttu-id="6d63e-116">На панели «Свойства» отображаются свойства ряда.</span><span class="sxs-lookup"><span data-stu-id="6d63e-116">The properties for the series are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="6d63e-117">В разделе **Общие** разверните узел **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="6d63e-117">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="6d63e-118">Присвойте свойству CollectedStyle значение **SingleSlice**.</span><span class="sxs-lookup"><span data-stu-id="6d63e-118">Set the CollectedStyle property to **SingleSlice**.</span></span>  
  
5.  <span data-ttu-id="6d63e-119">Задайте значение порога сбора и его тип.</span><span class="sxs-lookup"><span data-stu-id="6d63e-119">Set the collected threshold value and type of threshold.</span></span> <span data-ttu-id="6d63e-120">Следующие примеры демонстрируют общие способы задания порогов сбора.</span><span class="sxs-lookup"><span data-stu-id="6d63e-120">The following examples are common ways of setting collected thresholds.</span></span>  
  
    -   <span data-ttu-id="6d63e-121">**В процентах.**</span><span class="sxs-lookup"><span data-stu-id="6d63e-121">**By percentage.**</span></span> <span data-ttu-id="6d63e-122">Например, можно собрать в один срез все срезы круговой диаграммы, не превышающие 10%.</span><span class="sxs-lookup"><span data-stu-id="6d63e-122">For example, to collect any slice on your pie chart that is less than 10% into a single slice:</span></span>  
  
         <span data-ttu-id="6d63e-123">Задайте для свойства CollectedThresholdUsePercent значение `True` .</span><span class="sxs-lookup"><span data-stu-id="6d63e-123">Set the CollectedThresholdUsePercent property to `True`.</span></span>  
  
         <span data-ttu-id="6d63e-124">Присвойте свойству CollectedThreshold значение **10**.</span><span class="sxs-lookup"><span data-stu-id="6d63e-124">Set the CollectedThreshold property to **10**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="6d63e-125">Если для присвойте свойству collectedstyle задано значение **значение singleslice**, CollectedThreshold равно значению больше **100**, а CollectedThresholdUsePercent — `True` , то диаграмма выдаст исключение, поскольку не может вычислить процент.</span><span class="sxs-lookup"><span data-stu-id="6d63e-125">If you set CollectedStyle to **SingleSlice**, CollectedThreshold to a value greater than **100**, and CollectedThresholdUsePercent is `True`, the chart will throw an exception because it cannot calculate a percentage.</span></span> <span data-ttu-id="6d63e-126">Чтобы избежать этого, присвойте свойству CollectedThreshold значение меньше **100**.</span><span class="sxs-lookup"><span data-stu-id="6d63e-126">To resolve this issue, set the CollectedThreshold to a value less than **100**.</span></span>  
  
    -   <span data-ttu-id="6d63e-127">**По значению данных.**</span><span class="sxs-lookup"><span data-stu-id="6d63e-127">**By data value.**</span></span> <span data-ttu-id="6d63e-128">Например, можно собрать в один срез все срезы круговой диаграммы, не превышающие 5000%.</span><span class="sxs-lookup"><span data-stu-id="6d63e-128">For example, to collect any slice on your pie chart that is less than 5000 into a single slice:</span></span>  
  
         <span data-ttu-id="6d63e-129">Задайте для свойства CollectedThresholdUsePercent значение `False` .</span><span class="sxs-lookup"><span data-stu-id="6d63e-129">Set the CollectedThresholdUsePercent property to `False`.</span></span>  
  
         <span data-ttu-id="6d63e-130">Присвойте свойству CollectedThreshold значение **5000**.</span><span class="sxs-lookup"><span data-stu-id="6d63e-130">Set the CollectedThreshold property to **5000**.</span></span>  
  
6.  <span data-ttu-id="6d63e-131">Задайте в качестве свойства CollectedLabel строку, представляющую текстовую метку, которая будет отображена на собранном срезе.</span><span class="sxs-lookup"><span data-stu-id="6d63e-131">Set the CollectedLabel property to a string that represents the text label that will be shown on the collected slice.</span></span>  
  
7.  <span data-ttu-id="6d63e-132">(Необязательно) Присвойте значения свойствам CollectedSliceExploded, CollectedColor, CollectedLegendText и CollectedToolTip.</span><span class="sxs-lookup"><span data-stu-id="6d63e-132">(Optional) Set the CollectedSliceExploded, CollectedColor, CollectedLegendText and CollectedToolTip properties.</span></span> <span data-ttu-id="6d63e-133">Эти свойства определяют внешний вид, цвет, текстовую метку, текст условных обозначений и подсказку отдельного среза.</span><span class="sxs-lookup"><span data-stu-id="6d63e-133">These properties change the appearance, color, label text, legend text and tooltip aspects of the single slice.</span></span>  
  
### <a name="to-collect-small-slices-into-a-secondary-callout-pie-chart"></a><span data-ttu-id="6d63e-134">Сбор мелких срезов во вторичную, вызываемую круговую диаграмму</span><span class="sxs-lookup"><span data-stu-id="6d63e-134">To collect small slices into a secondary, callout pie chart</span></span>  
  
1.  <span data-ttu-id="6d63e-135">Выполните приведенные выше шаги 1—3.</span><span class="sxs-lookup"><span data-stu-id="6d63e-135">Follow Steps 1-3 from above.</span></span>  
  
2.  <span data-ttu-id="6d63e-136">Присвойте свойству CollectedStyle значение **CollectedPie**.</span><span class="sxs-lookup"><span data-stu-id="6d63e-136">Set the CollectedStyle property to **CollectedPie**.</span></span>  
  
3.  <span data-ttu-id="6d63e-137">Определите для свойства CollectedThresholdproperty значение порога, мелкие срезы со значениями ниже которого будут собираться в один срез.</span><span class="sxs-lookup"><span data-stu-id="6d63e-137">Set the CollectedThresholdproperty to a value that represents the threshold at which small slices will be collected into one slice.</span></span> <span data-ttu-id="6d63e-138">Если свойство присвойте свойству collectedstyle имеет значение **коллектедпие**, коллектедсрешолдусеперцентпроперти всегда имеет значение `True` , а собранное пороговое значение всегда измеряется в процентах.</span><span class="sxs-lookup"><span data-stu-id="6d63e-138">When the CollectedStyle property is set to **CollectedPie**, the CollectedThresholdUsePercentproperty is always set to `True`, and the collected threshold is always measured in percent.</span></span>  
  
4.  <span data-ttu-id="6d63e-139">(Необязательно) Присвойте значения свойствам CollectedColor, CollectedLabel, CollectedLegendText и CollectedToolTip.</span><span class="sxs-lookup"><span data-stu-id="6d63e-139">(Optional) Set the CollectedColor, CollectedLabel, CollectedLegendText and CollectedToolTip properties.</span></span> <span data-ttu-id="6d63e-140">Все остальные свойства, в имя которых входит «Collected», не относятся к собранной диаграмме.</span><span class="sxs-lookup"><span data-stu-id="6d63e-140">All other properties named "Collected" do not apply to the collected pie.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d63e-141">Поскольку вторичная круговая диаграмма вычисляется на основе мелких срезов данных, она появится только в режиме предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="6d63e-141">The secondary pie chart is calculated based on the small slices in your data so it will only appear in Preview.</span></span> <span data-ttu-id="6d63e-142">Она не появляется в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="6d63e-142">It does not appear on the design surface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d63e-143">Форматировать вторичную круговую диаграмму нельзя.</span><span class="sxs-lookup"><span data-stu-id="6d63e-143">You cannot format the secondary pie chart.</span></span> <span data-ttu-id="6d63e-144">По этой причине настоятельно рекомендуется пользоваться для сбора мелких срезов круговых диаграмм первым методом.</span><span class="sxs-lookup"><span data-stu-id="6d63e-144">For this reason, it is strongly recommended to use the first approach when collecting pie slices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d63e-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="6d63e-145">See Also</span></span>  
 <span data-ttu-id="6d63e-146">[Круговые диаграммы &#40;построитель отчетов и службы SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6d63e-146">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6d63e-147">[Форматирование точек данных на диаграмме &#40;построитель отчетов и SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6d63e-147">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6d63e-148">[Отображение меток точек данных за пределами круговой диаграммы &#40;построитель отчетов и SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6d63e-148">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6d63e-149">[Отображение процентных значений на круговой диаграмме &#40;построитель отчетов и SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6d63e-149">[Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6d63e-150">Добавление в диаграмму объемных эффектов (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6d63e-150">Add 3D Effects to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-3d-effects-report-builder.md)  
  
  
