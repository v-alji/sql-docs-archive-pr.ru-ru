---
title: Задание области диаграммы для ряда (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10157"
- sql12.rtp.rptdesigner.chartareaproperties.alignment.f1
ms.assetid: dc3c365b-c263-402a-bf6f-c2a7081db073
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 483bc6d2fa4aa079c95e9dbd03e18c71d7b13abf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654785"
---
# <a name="specify-a-chart-area-for-a-series-report-builder-and-ssrs"></a><span data-ttu-id="9ac0c-102">Задание области диаграммы для ряда (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9ac0c-102">Specify a Chart Area for a Series (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9ac0c-103">Диаграмма является контейнером верхнего уровня, который включает внешнюю границу, заголовок диаграммы и условные обозначения.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-103">The chart is the top-level container that includes the outer border, the chart title, and the legend.</span></span> <span data-ttu-id="9ac0c-104">По умолчанию диаграмма содержит одну область диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-104">By default, the chart contains one default chart area.</span></span> <span data-ttu-id="9ac0c-105">Область диаграммы невидима на самой диаграмме, но ее можно считать контейнером, охватывающим только метки осей, заголовки осей и область построения одного или нескольких рядов.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-105">The chart area is not visible on the chart surface, but you can think of the chart area as a container that encompasses only the axis labels, the axis title and the plotting area of one or more series.</span></span> <span data-ttu-id="9ac0c-106">На следующем рисунке представлено понятие областей диаграммы с одной диаграммой.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-106">The following illustration shows the concept of chart areas within a single chart.</span></span>  
  
 <span data-ttu-id="9ac0c-107">![Схема области диаграммы](../media/chartareasdiagram.gif "Схема области диаграммы")</span><span class="sxs-lookup"><span data-stu-id="9ac0c-107">![Shows a diagram of a chart area](../media/chartareasdiagram.gif "Shows a diagram of a chart area")</span></span>  
  
 <span data-ttu-id="9ac0c-108">Как правило, все ряды добавляются в область диаграммы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-108">By default, all series are added to the default chart area.</span></span> <span data-ttu-id="9ac0c-109">При использовании диаграмм с областями, гистограмм, линейчатых и точечных диаграмм все комбинации этих рядов можно отобразить в одной области диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-109">When using area, column, line, and scatter charts, any combination of these series can be displayed on the same chart area.</span></span> <span data-ttu-id="9ac0c-110">Если в одной области диаграммы имеется несколько рядов, ухудшается читаемость диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-110">If you have several series in the same chart area, the readability of the chart is reduced.</span></span> <span data-ttu-id="9ac0c-111">В этом случае удобнее разделить типы диаграмм по нескольким областям.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-111">You may want to separate the chart types into multiple chart areas.</span></span> <span data-ttu-id="9ac0c-112">Использование нескольких областей диаграмм улучшает читаемость и облегчает сравнение.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-112">Using multiple chart areas will increase readability for easier comparisons.</span></span> <span data-ttu-id="9ac0c-113">Например, биржевые диаграммы цены и суммы выручки часто имеют разные диапазоны значений, но сравнение цены и суммы выручки можно выполнить за тот же период времени.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-113">For example, price-volume stock charts often have different ranges of values, but comparisons can be made between the price and volume data over the same period of time.</span></span>  
  
 <span data-ttu-id="9ac0c-114">Столбчатые, полярные и фигурные ряды можно сочетать только с рядами того же типа диаграмм в одной области диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-114">The bar, polar, or shape series can only be combined with series of the same chart types in the same chart area.</span></span> <span data-ttu-id="9ac0c-115">Если используется полярная или фигурная диаграмма, рассмотрите возможность применения отдельной области данных диаграммы для каждого отображаемого поля.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-115">If you are using a Polar or Shape chart, consider using a separate chart data region for each field that you wish to show.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-series-with-a-new-chart-area"></a><span data-ttu-id="9ac0c-116">Связывание ряда с новой областью диаграммы</span><span class="sxs-lookup"><span data-stu-id="9ac0c-116">To associate a series with a new chart area</span></span>  
  
1.  <span data-ttu-id="9ac0c-117">Щелкните правой кнопкой мыши в любом месте диаграммы и выберите **Добавить новую область диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-117">Right-click anywhere on the chart and select **Add New Chart Area**.</span></span> <span data-ttu-id="9ac0c-118">В диаграмме появится новая пустая область.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-118">A new, blank chart area appears on the chart.</span></span>  
  
2.  <span data-ttu-id="9ac0c-119">Щелкните правой кнопкой мыши ряд диаграммы либо ряд или поле данных в соответствующей области на панели "Данные диаграммы" и выберите пункт **Свойства ряда**.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-119">Right-click the series on the chart or right-click a series or data field in the appropriate area in the Chart Data pane, and then click **Series Properties**.</span></span>  
  
3.  <span data-ttu-id="9ac0c-120">На вкладке **Оси и область диаграммы**выберите область диаграммы, в которой будут отображаться ряды.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-120">In **Axes and Chart Areas**, select the chart area that you want the series to be shown in.</span></span>  
  
4.  <span data-ttu-id="9ac0c-121">Выровняйте области диаграммы по вертикали (необязательно).</span><span class="sxs-lookup"><span data-stu-id="9ac0c-121">(Optional) Align the chart areas vertically.</span></span> <span data-ttu-id="9ac0c-122">Для этого щелкните диаграмму правой кнопкой мыши и выберите **Свойства области диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-122">To do this, right-click the chart and select **Chart Area Properties**.</span></span> <span data-ttu-id="9ac0c-123">На вкладке **Выравнивание**выберите область диаграммы, с которой нужно выровнять выбранную область.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-123">In **Alignment**, select another chart area that you want to align the selected chart area with.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac0c-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ac0c-124">See Also</span></span>  
 <span data-ttu-id="9ac0c-125">[Несколько рядов на диаграмме (построитель отчетов и службы SSRS)](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9ac0c-125">[Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9ac0c-126">[Форматирование точек данных на диаграмме (построитель отчетов и службы SSRS)](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9ac0c-126">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9ac0c-127">[Задание цветов диаграммы с помощью палитры &#40;построитель отчетов и службы SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9ac0c-127">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9ac0c-128">[Полярные диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9ac0c-128">[Polar Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9ac0c-129">[Фигурные диаграммы &#40;построитель отчетов и службы SSRS&#41;](shape-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9ac0c-129">[Shape Charts &#40;Report Builder and SSRS&#41;](shape-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9ac0c-130">Круговые диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9ac0c-130">Pie Charts &#40;Report Builder and SSRS&#41;</span></span>](pie-charts-report-builder-and-ssrs.md)  
  
  
