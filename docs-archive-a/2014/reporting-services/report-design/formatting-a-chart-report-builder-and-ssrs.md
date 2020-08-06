---
title: Форматирование диаграммы (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10214"
- sql12.rtp.rptdesigner.calculatedseriesproperties.fill.f1
- sql12.rtp.rptdesigner.serieslabelproperties.fill.f1
- sql12.rtp.rptdesigner.legendproperties.fill.f1
- "10149"
- sql12.rtp.rptdesigner.seriesproperties.shadow.f1
- sql12.rtp.rptdesigner.seriesproperties.markers.f1
- "10255"
- sql12.rtp.rptdesigner.charttitleproperties.fill.f1
- "10154"
- "10170"
- "10173"
- sql12.rtp.rptdesigner.seriesproperties.fill.f1
- "10169"
- "10158"
- sql12.rtp.rptdesigner.chartareaproperties.fill.f1
- sql12.rtp.rptdesigner.charttitleproperties.shadow.f1
- "10246"
- "10150"
- sql12.rtp.rptdesigner.calculatedseriesproperties.borders.f1
- sql12.rtp.rptdesigner.chartproperties.fill.f1
- "10159"
- sql12.rtp.rptdesigner.majorgridlineproperties.gridlineoptions.f1
- "10160"
- sql12.rtp.rptdesigner.serieslabelproperties.font.f1
- "10182"
- "10163"
- "10164"
- "10253"
- "10216"
- "10171"
- "10257"
- sql12.rtp.rptdesigner.chartareaproperties.border.f1
- sql12.rtp.rptdesigner.calculatedseriesproperties.shadow.f1
- sql12.rtp.rptdesigner.chartproperties.border.f1
- sql12.rtp.rptdesigner.minorgridlineproperties.gridlineoptions.f1
- sql12.rtp.rptdesigner.chartareaproperties.shadow.f1
- sql12.rtp.rptdesigner.charttitleproperties.borders.f1
- sql12.rtp.rptdesigner.charttitleproperties.font.f1
- "10247"
ms.assetid: d3984300-c766-42f8-b7c4-863123d67c99
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af164d4db9b6439f0634d113652b95939827b0f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658098"
---
# <a name="formatting-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="6966f-102">Форматирование диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6966f-102">Formatting a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6966f-103">После определения данных для диаграммы и нужного представления диаграммы можно добавить форматирование, чтобы улучшить общий внешний вид и выделить ключевые точки данных.</span><span class="sxs-lookup"><span data-stu-id="6966f-103">After you have defined the data for your chart and it is appearing the way you want, you can add formatting to improve the overall appearance and highlight key data points.</span></span> <span data-ttu-id="6966f-104">Наиболее общие параметры форматирования могут быть изменены в диалоговом окне «Свойства». Для этого нужно щелкнуть правой кнопкой мыши элемент диаграммы, чтобы отобразить контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="6966f-104">The most common formatting options can be modified from the Properties dialog box that are found when you right-click a chart element to display its shortcut menu.</span></span> <span data-ttu-id="6966f-105">Каждый элемент диаграммы имеет собственное диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="6966f-105">Each chart element has its own dialog box.</span></span> <span data-ttu-id="6966f-106">Дополнительные сведения о элементах диаграмм см. в статье [Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6966f-106">For more information about chart elements, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="6966f-107">Все свойства, связанные с диаграммой, расположены на панели «Свойства», но многие из этих свойств можно также задать в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="6966f-107">All properties that relate to the chart are located in the Properties pane, but many of these properties can also be set from a dialog box.</span></span> <span data-ttu-id="6966f-108">При форматировании ряда можно указать характерные для ряда свойства с помощью пользовательских атрибутов, которые можно найти только в категории свойств **CustomAttributes** , расположенной на панели "Свойства".</span><span class="sxs-lookup"><span data-stu-id="6966f-108">If you are formatting the series, you can specify series-specific properties using custom attributes, which can only be found in the **CustomAttributes** category of properties, located in the Properties pane.</span></span>  
  
 <span data-ttu-id="6966f-109">Для эффективного форматирования диаграммы с помощью минимального числа шагов измените стиль границ по умолчанию, палитру и стиль отображения.</span><span class="sxs-lookup"><span data-stu-id="6966f-109">To effectively format the chart using a minimal number of steps, change the default border style, palette and drawing style.</span></span> <span data-ttu-id="6966f-110">Эти три характеристики оказывают самое большое влияние на зрительное восприятие диаграммы.</span><span class="sxs-lookup"><span data-stu-id="6966f-110">These three features produce the largest visible change on the chart.</span></span> <span data-ttu-id="6966f-111">Стили отображения применимы только к круговым, кольцевым, столбчатым диаграммам и гистограммам.</span><span class="sxs-lookup"><span data-stu-id="6966f-111">Drawing styles are only applicable to pie, doughnut, bar and column charts.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="6966f-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="6966f-112">In This Section</span></span>  
 [<span data-ttu-id="6966f-113">Форматирование цветов для рядов на диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6966f-113">Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="6966f-114">Рассматривается определение цветов с помощью палитры, определение собственной палитры и определение цветов на основе выражения.</span><span class="sxs-lookup"><span data-stu-id="6966f-114">Discusses how colors are defined using a palette, how you can define your own color palette, and how to define colors based on an expression.</span></span>  
  
 [<span data-ttu-id="6966f-115">Форматирование меток оси на диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6966f-115">Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="6966f-116">Рассматривается отображение линий сетки, делений и заголовков, а также форматирование чисел и дат на шкале оси.</span><span class="sxs-lookup"><span data-stu-id="6966f-116">Discusses how to display gridlines, tick marks, and titles, and how to format numbers and dates on the axis scale.</span></span>  
  
 [<span data-ttu-id="6966f-117">Форматирование условных обозначений на диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6966f-117">Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-legend-formatting-report-builder.md)  
 <span data-ttu-id="6966f-118">Рассматривается изменение расположения и форматирование элементов в условных обозначениях диаграммы.</span><span class="sxs-lookup"><span data-stu-id="6966f-118">Discusses how to re-order and format items in the chart legend.</span></span>  
  
 [<span data-ttu-id="6966f-119">Форматирование точек данных на диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6966f-119">Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="6966f-120">Рассматривается размещение меток точек данных и форматирование маркеров точек данных для каждого ряда диаграммы.</span><span class="sxs-lookup"><span data-stu-id="6966f-120">Discusses how to position data point labels and format data point markers for every series on the chart.</span></span>  
  
 [<span data-ttu-id="6966f-121">Эффекты рельефа, объемные и другие эффекты в диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6966f-121">3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-3d-bevel-and-other-report-builder.md)  
 <span data-ttu-id="6966f-122">Рассматриваются различные объемные эффекты, которые можно применить к диаграмме.</span><span class="sxs-lookup"><span data-stu-id="6966f-122">Discusses various 3D effects that you can apply to a chart.</span></span>  
  
 [<span data-ttu-id="6966f-123">Добавление границы рамки в диаграмму (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6966f-123">Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="6966f-124">Объясняет, как добавить к диаграмме границу рамки.</span><span class="sxs-lookup"><span data-stu-id="6966f-124">Explains how to add a border frame to a chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6966f-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="6966f-125">See Also</span></span>  
 <span data-ttu-id="6966f-126">[Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6966f-126">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6966f-127">[Добавление границы рамки в диаграмму &#40;построитель отчетов и службы SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6966f-127">[Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6966f-128">[Задание цветов диаграммы с помощью палитры &#40;построитель отчетов и службы SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6966f-128">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6966f-129">Добавление в диаграмму стилей рельефа, приподнятости и текстуры &#40;построитель отчетов и службы SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6966f-129">Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
