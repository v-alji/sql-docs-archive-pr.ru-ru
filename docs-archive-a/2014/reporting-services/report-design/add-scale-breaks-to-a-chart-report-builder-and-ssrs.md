---
title: Добавление в диаграмму разрывов шкалы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 84d66436-ed62-4967-bbbd-b457593ee787
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1c081debd1e0a84158615edebdb6b84705c10e5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735025"
---
# <a name="add-scale-breaks-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="667a7-102">Добавление в диаграмму разрывов шкалы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="667a7-102">Add Scale Breaks to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="667a7-103">Разрыв шкалы представляет собой полосу, нарисованную в области построения диаграммы, обозначающую нарушение непрерывной последовательности изменения значений от малых к большим на оси значений (обычно это вертикальная ось, или ось Y).</span><span class="sxs-lookup"><span data-stu-id="667a7-103">A scale break is a stripe drawn across the plotting area of a chart to denote a break in continuity between the high and low values on a value axis (usually the vertical, or y-axis).</span></span> <span data-ttu-id="667a7-104">Разрыв шкалы используется, чтобы отобразить два разных диапазона в одной и той же области диаграммы.</span><span class="sxs-lookup"><span data-stu-id="667a7-104">Use a scale break to display two distinct ranges in the same chart area.</span></span>  
  
 <span data-ttu-id="667a7-105">![Диаграмма с разрывом шкалы](../media/rs-multipledatarangeschart-scalebreak.gif "Диаграмма с разрывом шкалы")</span><span class="sxs-lookup"><span data-stu-id="667a7-105">![Chart with scale break](../media/rs-multipledatarangeschart-scalebreak.gif "Chart with scale break")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="667a7-106">Положение разрыва шкалы указать на диаграмме нельзя.</span><span class="sxs-lookup"><span data-stu-id="667a7-106">You cannot specify where to place a scale break on your chart.</span></span> <span data-ttu-id="667a7-107">Диаграмма на основе значений набора данных самостоятельно вычисляет, где имеется значительный разрыв между диапазонами данных, чтобы поместить разрыв шкалы на оси значений (оси Y) во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="667a7-107">The chart uses its own calculations based on the values in your dataset to determine whether there is sufficient separation between data ranges to draw a scale break on the value axis (y-axis) at run time.</span></span>  
  
 <span data-ttu-id="667a7-108">Пример диаграммы с разрывами шкалы доступен в виде образца отчета.</span><span class="sxs-lookup"><span data-stu-id="667a7-108">An example of a chart with scale breaks is available as a sample report.</span></span> <span data-ttu-id="667a7-109">Дополнительные сведения о скачивании этого и других примеров отчетов см. в статье [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="667a7-109">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-enable-scale-breaks-on-the-chart"></a><span data-ttu-id="667a7-110">Включение разрывов шкалы на диаграмме</span><span class="sxs-lookup"><span data-stu-id="667a7-110">To enable scale breaks on the chart</span></span>  
  
1.  <span data-ttu-id="667a7-111">Щелкните правой кнопкой мыши вертикальную ось и выберите пункт **Свойства оси**.</span><span class="sxs-lookup"><span data-stu-id="667a7-111">Right-click the vertical axis and then click **Axis Properties**.</span></span> <span data-ttu-id="667a7-112">Откроется диалоговое окно **Свойства вертикальной оси** .</span><span class="sxs-lookup"><span data-stu-id="667a7-112">The **VerticalAxis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="667a7-113">Установите флажок **Включить разрывы шкалы** .</span><span class="sxs-lookup"><span data-stu-id="667a7-113">Select the **Enable scale breaks** check box.</span></span>  
  
### <a name="to-change-the-style-of-the-scale-break"></a><span data-ttu-id="667a7-114">Изменение стиля разрыва шкалы</span><span class="sxs-lookup"><span data-stu-id="667a7-114">To change the style of the scale break</span></span>  
  
1.  <span data-ttu-id="667a7-115">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="667a7-115">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="667a7-116">В области конструктора щелкните правой кнопкой мыши ось Y диаграммы.</span><span class="sxs-lookup"><span data-stu-id="667a7-116">On the design surface, right-click on the y-axis of the chart.</span></span> <span data-ttu-id="667a7-117">На панели «Свойства» будут отображены свойства объекта оси Y (по умолчанию называемой «Ось диаграммы»).</span><span class="sxs-lookup"><span data-stu-id="667a7-117">The properties for the y-axis object (named Chart Axis by default) are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="667a7-118">В разделе **Шкала** раскройте свойство ScaleBreakStyle.</span><span class="sxs-lookup"><span data-stu-id="667a7-118">In the **Scale** section, expand the ScaleBreakStyle property.</span></span>  
  
4.  <span data-ttu-id="667a7-119">Измените значения свойства ScaleBreakStyle, такие как BreakLineType и Spacing.</span><span class="sxs-lookup"><span data-stu-id="667a7-119">Change the values for ScaleBreakStyle properties, such as BreakLineType and Spacing.</span></span> <span data-ttu-id="667a7-120">Дополнительные сведения о свойствах разрыва шкалы см. в разделе [Отображение на диаграмме ряда с несколькими диапазонами данных (построитель отчетов и службы SSRS)](displaying-a-series-with-multiple-data-ranges-on-a-chart.md).</span><span class="sxs-lookup"><span data-stu-id="667a7-120">For more information about scale break properties, see [Displaying a Series with Multiple Data Ranges on a Chart &#40;Report Builder and SSRS&#41;](displaying-a-series-with-multiple-data-ranges-on-a-chart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="667a7-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="667a7-121">See Also</span></span>  
 <span data-ttu-id="667a7-122">[Диаграммы &#40;построитель отчетов и службы SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="667a7-122">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="667a7-123">[Форматирование построитель отчетов &#40;диаграммы и SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="667a7-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="667a7-124">Диалоговое окно "Свойства оси" — "Параметры оси" (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="667a7-124">Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;</span></span>](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md)  
  
  
