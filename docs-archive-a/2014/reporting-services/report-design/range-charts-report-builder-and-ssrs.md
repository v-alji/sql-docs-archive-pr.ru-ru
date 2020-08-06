---
title: Диаграммы диапазонов (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 48e351d3-ac5b-4eda-a4bd-32a0de206a30
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 76a9723bc55030da59d22c945a40ce4418b84ab3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733618"
---
# <a name="range-charts-report-builder-and-ssrs"></a><span data-ttu-id="24385-102">Диаграммы диапазонов (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="24385-102">Range Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="24385-103">Тип диаграммы диапазонов предназначен для отображения набора точек данных, каждая из которых определена несколькими значениями, относящимися к одной и той же категории.</span><span class="sxs-lookup"><span data-stu-id="24385-103">A range chart type displays a set of data points that are each defined by multiple values for the same category.</span></span> <span data-ttu-id="24385-104">Значения представлены высотой маркера на оси значений.</span><span class="sxs-lookup"><span data-stu-id="24385-104">Values are represented by the height of the marker as measured by the value axis.</span></span> <span data-ttu-id="24385-105">Метки категорий отображаются на оси категорий.</span><span class="sxs-lookup"><span data-stu-id="24385-105">Category labels are displayed on the category axis.</span></span> <span data-ttu-id="24385-106">В простой диаграмме диапазонов заполняется область между верхним и нижним значениями для каждой точки данных.</span><span class="sxs-lookup"><span data-stu-id="24385-106">The plain range chart fills in the area between the top and bottom value for each data point.</span></span>  
  
 <span data-ttu-id="24385-107">На следующей иллюстрации показана простая диаграмма диапазонов с тремя рядами.</span><span class="sxs-lookup"><span data-stu-id="24385-107">The following illustration shows a plain range chart with three series.</span></span>  
  
 <span data-ttu-id="24385-108">![Диаграмма диапазонов](../media/rs-rangechart.gif "Диаграмма диапазонов")</span><span class="sxs-lookup"><span data-stu-id="24385-108">![Range chart](../media/rs-rangechart.gif "Range chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="24385-109">Варианты</span><span class="sxs-lookup"><span data-stu-id="24385-109">Variations</span></span>  
  
-   <span data-ttu-id="24385-110">**Гладкая диаграмма диапазонов**.</span><span class="sxs-lookup"><span data-stu-id="24385-110">**Smooth range**.</span></span> <span data-ttu-id="24385-111">На гладкой диаграмме диапазонов отображаются кривые, а не прямые линии.</span><span class="sxs-lookup"><span data-stu-id="24385-111">A smooth range chart displays curved lines rather than straight.</span></span>  
  
-   <span data-ttu-id="24385-112">**Гистограмма диапазонов**.</span><span class="sxs-lookup"><span data-stu-id="24385-112">**Column range**.</span></span> <span data-ttu-id="24385-113">На гистограмме диапазонов для отображения диапазонов вместо областей используются столбцы.</span><span class="sxs-lookup"><span data-stu-id="24385-113">A column range chart uses columns instead of areas to display the ranges.</span></span>  
  
-   <span data-ttu-id="24385-114">**Линейчатая диаграмма диапазонов**.</span><span class="sxs-lookup"><span data-stu-id="24385-114">**Bar range**.</span></span> <span data-ttu-id="24385-115">На линейчатой диаграмме диапазонов для отображения диапазонов вместо областей используются линейки.</span><span class="sxs-lookup"><span data-stu-id="24385-115">A bar range chart uses bars instead of areas to display the ranges.</span></span>  
  
## <a name="data-considerations-for-range-charts"></a><span data-ttu-id="24385-116">Данные для диаграмм диапазонов</span><span class="sxs-lookup"><span data-stu-id="24385-116">Data Considerations for Range Charts</span></span>  
  
-   <span data-ttu-id="24385-117">Для диаграмм диапазонов требуется по два значения на каждую точку данных.</span><span class="sxs-lookup"><span data-stu-id="24385-117">Range chart types require two values per data point.</span></span> <span data-ttu-id="24385-118">Эти значения соответствуют высокому и низкому значениям, определяющим диапазон для каждой точки данных.</span><span class="sxs-lookup"><span data-stu-id="24385-118">These values correspond with a high value and a low value that defines the range for each data point.</span></span>  
  
-   <span data-ttu-id="24385-119">Диаграммы диапазонов могут применяться для анализа, только если высокие значения всегда выше низких значений.</span><span class="sxs-lookup"><span data-stu-id="24385-119">Range charts are useful for analysis only if the top values are always higher than the bottom values.</span></span> <span data-ttu-id="24385-120">Если это условие не соблюдается, рассмотрите возможность использовать график.</span><span class="sxs-lookup"><span data-stu-id="24385-120">If this is not the case, consider using a line chart.</span></span> <span data-ttu-id="24385-121">Если высокое значение меньше низкого значения, то на диаграмме диапазонов отображается абсолютная величина разности между этими значениями.</span><span class="sxs-lookup"><span data-stu-id="24385-121">If the high value is lower the low value, the range chart will display the absolute value of the difference between these values.</span></span>  
  
-   <span data-ttu-id="24385-122">Если указано только одно значение, диаграмма диапазонов отображается как обычная диаграмма с областями, с единственным значением для каждой точки данных.</span><span class="sxs-lookup"><span data-stu-id="24385-122">If only one value is specified, the range chart will display as if it were a regular area chart, with one value per data point.</span></span>  
  
-   <span data-ttu-id="24385-123">Диаграммы диапазонов часто используются для графического представления данных, которые содержат минимальное и максимальное значения для каждой группы категорий в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="24385-123">Range charts are often used to graph data that contains minimum and maximum values for each category group in the dataset.</span></span>  
  
-   <span data-ttu-id="24385-124">Возможность отображения маркеров в каждой точке данных на диаграмме диапазонов не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="24385-124">Displaying markers on each data point is not supported on the range chart.</span></span>  
  
-   <span data-ttu-id="24385-125">Как и на диаграмме с областями, на простой диаграмме диапазонов при наличии одинаковых значений в нескольких рядах эти ряды перекрываются.</span><span class="sxs-lookup"><span data-stu-id="24385-125">Like the area chart, in a plain range chart, if the values in multiple series are similar, the series will overlap.</span></span> <span data-ttu-id="24385-126">В таком случае может потребоваться использовать гистограмму диапазонов или линейчатую диаграмму диапазонов вместо простой диаграммы диапазонов.</span><span class="sxs-lookup"><span data-stu-id="24385-126">In this scenario, you may want to use a column range or bar range chart instead of a plain range chart.</span></span>  
  
-   <span data-ttu-id="24385-127">Диаграммы Ганта могут быть созданы с помощью линейчатой диаграммы диапазонов.</span><span class="sxs-lookup"><span data-stu-id="24385-127">Gantt charts can be created using a range bar chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24385-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="24385-128">See Also</span></span>  
 <span data-ttu-id="24385-129">[Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="24385-129">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="24385-130">[Типы диаграмм (построитель отчетов и службы SSRS)](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="24385-130">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="24385-131">Форматирование диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="24385-131">Formatting a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-a-chart-report-builder-and-ssrs.md)  
  
  
