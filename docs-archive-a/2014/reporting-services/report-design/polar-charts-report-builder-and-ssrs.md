---
title: Полярные диаграммы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c9402d8f-202a-4cdf-949e-50f5b1d2b885
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b8c4dd9394fab3e076c4a714375954a616e081f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727934"
---
# <a name="polar-charts-report-builder-and-ssrs"></a><span data-ttu-id="98ecb-102">Полярные диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="98ecb-102">Polar Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="98ecb-103">На полярной диаграмме ряд отображается как набор точек, сгруппированных по категориям на площади круга.</span><span class="sxs-lookup"><span data-stu-id="98ecb-103">A polar chart displays a series as a set of points that are grouped by category on a 360-degree circle.</span></span> <span data-ttu-id="98ecb-104">Значения представлены расстоянием точки от центра круга.</span><span class="sxs-lookup"><span data-stu-id="98ecb-104">Values are represented by the length of the point as measured from the center of the circle.</span></span> <span data-ttu-id="98ecb-105">Чем дальше точка от центра, тем больше ее значение.</span><span class="sxs-lookup"><span data-stu-id="98ecb-105">The farther the point is from the center, the greater its value.</span></span> <span data-ttu-id="98ecb-106">Метки категорий отображаются на периметре диаграммы.</span><span class="sxs-lookup"><span data-stu-id="98ecb-106">Category labels are displayed on the perimeter of the chart.</span></span> <span data-ttu-id="98ecb-107">Дополнительные сведения о добавлении данных в полярные диаграммы см. в разделе [Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="98ecb-107">For more information on how to add data to a polar chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="98ecb-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="98ecb-108">Variations</span></span>  
  
-   <span data-ttu-id="98ecb-109">**Лепестковая диаграмма**.</span><span class="sxs-lookup"><span data-stu-id="98ecb-109">**Radar chart**.</span></span> <span data-ttu-id="98ecb-110">На лепестковой диаграмме ряды отображаются в виде окружностей или областей.</span><span class="sxs-lookup"><span data-stu-id="98ecb-110">A radar chart displays a series as a circular line or area.</span></span> <span data-ttu-id="98ecb-111">В отличие от полярных диаграмм, на лепестковых диаграммах данные отражаются не в виде полярных координат.</span><span class="sxs-lookup"><span data-stu-id="98ecb-111">Unlike the polar chart, the radar chart does not display data in terms of polar coordinates.</span></span>  
  
## <a name="data-considerations-for-polar-charts"></a><span data-ttu-id="98ecb-112">Соображения касательно данных в полярных диаграммах</span><span class="sxs-lookup"><span data-stu-id="98ecb-112">Data Considerations for Polar Charts</span></span>  
  
-   <span data-ttu-id="98ecb-113">Лепестковые диаграммы удобны для сравнения нескольких рядов данных, разбитых на категории.</span><span class="sxs-lookup"><span data-stu-id="98ecb-113">The radar chart is useful for comparisons between multiple series of category data.</span></span>  
  
-   <span data-ttu-id="98ecb-114">Полярные диаграммы обычно используются для отображения полярных данных, когда любая из точек данных определяется углом и расстоянием.</span><span class="sxs-lookup"><span data-stu-id="98ecb-114">Polar charts are most commonly used to graph polar data, where each data point is determined by an angle and a distance.</span></span>  
  
-   <span data-ttu-id="98ecb-115">Полярная диаграмма несовместима с другими типами диаграмм в одной области диаграммы.</span><span class="sxs-lookup"><span data-stu-id="98ecb-115">Polar charts cannot be combined with any other chart type in the same chart area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98ecb-116">Пример</span><span class="sxs-lookup"><span data-stu-id="98ecb-116">Example</span></span>  
 <span data-ttu-id="98ecb-117">В следующем примере показано использование лепестковой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="98ecb-117">The following example shows how a radar chart can be used.</span></span> <span data-ttu-id="98ecb-118">В следующей таблице содержится образец данных для диаграммы.</span><span class="sxs-lookup"><span data-stu-id="98ecb-118">The table below provides sample data for the chart.</span></span>  
  
|<span data-ttu-id="98ecb-119">Имя</span><span class="sxs-lookup"><span data-stu-id="98ecb-119">Name</span></span>|<span data-ttu-id="98ecb-120">Sales</span><span class="sxs-lookup"><span data-stu-id="98ecb-120">Sales</span></span>|  
|----------|-----------|  
|<span data-ttu-id="98ecb-121">Кусты</span><span class="sxs-lookup"><span data-stu-id="98ecb-121">Shrubs</span></span>|<span data-ttu-id="98ecb-122">61</span><span class="sxs-lookup"><span data-stu-id="98ecb-122">61</span></span>|  
|<span data-ttu-id="98ecb-123">Начальные значения</span><span class="sxs-lookup"><span data-stu-id="98ecb-123">Seeds</span></span>|<span data-ttu-id="98ecb-124">78</span><span class="sxs-lookup"><span data-stu-id="98ecb-124">78</span></span>|  
|<span data-ttu-id="98ecb-125">Клубни</span><span class="sxs-lookup"><span data-stu-id="98ecb-125">Bulbs</span></span>|<span data-ttu-id="98ecb-126">60</span><span class="sxs-lookup"><span data-stu-id="98ecb-126">60</span></span>|  
|<span data-ttu-id="98ecb-127">Деревья</span><span class="sxs-lookup"><span data-stu-id="98ecb-127">Trees</span></span>|<span data-ttu-id="98ecb-128">38</span><span class="sxs-lookup"><span data-stu-id="98ecb-128">38</span></span>|  
|<span data-ttu-id="98ecb-129">Цветы</span><span class="sxs-lookup"><span data-stu-id="98ecb-129">Flowers</span></span>|<span data-ttu-id="98ecb-130">81</span><span class="sxs-lookup"><span data-stu-id="98ecb-130">81</span></span>|  
  
 <span data-ttu-id="98ecb-131">В данном примере поле Name помещается в область групп категорий.</span><span class="sxs-lookup"><span data-stu-id="98ecb-131">In this example, the Name field is placed in the Category Groups area.</span></span> <span data-ttu-id="98ecb-132">Поле Sales помещается в область значений.</span><span class="sxs-lookup"><span data-stu-id="98ecb-132">The Sales field is placed in the Values area.</span></span> <span data-ttu-id="98ecb-133">После перетаскивания происходит автоматическая статистическая обработка поля «Продажи» для диаграммы.</span><span class="sxs-lookup"><span data-stu-id="98ecb-133">The Sales field is automatically aggregated for the chart when you drop it.</span></span> <span data-ttu-id="98ecb-134">Лепестковая диаграмма вычисляет расположение меток, основываясь на числе значений в поле «Продажи», содержащем пять значений, и размещает метки около пяти равноудаленных точек на периметре круга.</span><span class="sxs-lookup"><span data-stu-id="98ecb-134">The radar chart calculates where to place the labels based on the number of values in the Sales field, which contains five values and places labels at five equidistant points on a circle.</span></span> <span data-ttu-id="98ecb-135">Если бы в поле «Продажи» содержалось три значения, то метки были бы расставлены у трех равноудаленных точек на периметре круга.</span><span class="sxs-lookup"><span data-stu-id="98ecb-135">If the Sales field contained three values, the labels would be placed at three equidistant points on a circle.</span></span>  
  
 <span data-ttu-id="98ecb-136">На следующем рисунке показана лепестковая диаграмма, основанная на представленных данных.</span><span class="sxs-lookup"><span data-stu-id="98ecb-136">The following illustration shows an example of a radar chart based on the data presented.</span></span>  
  
 <span data-ttu-id="98ecb-137">![Лепестковая диаграмма](../media/rs-radarchart.gif "Лепестковая диаграмма")</span><span class="sxs-lookup"><span data-stu-id="98ecb-137">![Radar chart](../media/rs-radarchart.gif "Radar chart")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ecb-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="98ecb-138">See Also</span></span>  
 <span data-ttu-id="98ecb-139">[Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="98ecb-139">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="98ecb-140">[Форматирование диаграммы (построитель отчетов и службы SSRS)](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="98ecb-140">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="98ecb-141">[Типы диаграмм (построитель отчетов и службы SSRS)](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="98ecb-141">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="98ecb-142">[Графики (построитель отчетов и службы SSRS)](line-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="98ecb-142">[Line Charts &#40;Report Builder and SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="98ecb-143">Точки данных со значением NULL и пустые точки в диаграммах (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="98ecb-143">Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;</span></span>](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)  
  
  
