---
title: Графики (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 194e6679-890d-4a3e-a756-130d32ef7e29
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 44e7a011186e66e6b8bdc8b5dd31939c883e320b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739269"
---
# <a name="line-charts-report-builder-and-ssrs"></a><span data-ttu-id="d6e88-102">Графики (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d6e88-102">Line Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d6e88-103">График отображает ряды значений в виде точек, соединенных линией.</span><span class="sxs-lookup"><span data-stu-id="d6e88-103">A line chart displays a series as a set of points connected by a single line.</span></span> <span data-ttu-id="d6e88-104">Графики используются для представления больших объемов данных, распределенных на непрерывном отрезке времени.</span><span class="sxs-lookup"><span data-stu-id="d6e88-104">Line charts are used to representing large amounts of data that occur over a continuous period of time.</span></span> <span data-ttu-id="d6e88-105">Дополнительные сведения о добавлении данных на график см. в разделе [Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d6e88-105">For more information about how to add data to a line chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="d6e88-106">На следующем рисунке показан график, содержащий три ряда.</span><span class="sxs-lookup"><span data-stu-id="d6e88-106">The following illustration shows a line chart that contains three series.</span></span>  
  
 <span data-ttu-id="d6e88-107">![График](../media/rs-linechart.gif "График")</span><span class="sxs-lookup"><span data-stu-id="d6e88-107">![Line chart](../media/rs-linechart.gif "Line chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="d6e88-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="d6e88-108">Variations</span></span>  
  
-   <span data-ttu-id="d6e88-109">**Гладкий график**.</span><span class="sxs-lookup"><span data-stu-id="d6e88-109">**Smooth line**.</span></span> <span data-ttu-id="d6e88-110">График, в котором вместо обычных линий используются изогнутые.</span><span class="sxs-lookup"><span data-stu-id="d6e88-110">A line chart that uses a curved line instead of a regular line.</span></span>  
  
-   <span data-ttu-id="d6e88-111">**Ступенчатый график**.</span><span class="sxs-lookup"><span data-stu-id="d6e88-111">**Stepped line**.</span></span> <span data-ttu-id="d6e88-112">График, в котором вместо обычных линий используются ступенчатые.</span><span class="sxs-lookup"><span data-stu-id="d6e88-112">A line chart that uses a stepped line instead of a regular line.</span></span> <span data-ttu-id="d6e88-113">В ступенчатом графике точки соединяются линией, напоминающей ступеньки на лестнице.</span><span class="sxs-lookup"><span data-stu-id="d6e88-113">The stepped line connects points by using a line that makes it look like steps on a ladder or staircase.</span></span>  
  
-   <span data-ttu-id="d6e88-114">**Спарклайн-графики**.</span><span class="sxs-lookup"><span data-stu-id="d6e88-114">**Sparkline charts**.</span></span> <span data-ttu-id="d6e88-115">Вариации линейного графика, которые показывают только последовательность линий в ячейке таблицы или матрицы.</span><span class="sxs-lookup"><span data-stu-id="d6e88-115">Variations of the line chart that show only the line series in the cell of a table or matrix.</span></span> <span data-ttu-id="d6e88-116">Дополнительные сведения см. в разделе [Спарклайны и гистограммы (построитель отчетов и службы SSRS)](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d6e88-116">For more information, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="data-considerations-for-line-charts"></a><span data-ttu-id="d6e88-117">Соображения о данных в графиках</span><span class="sxs-lookup"><span data-stu-id="d6e88-117">Data Considerations for Line Charts</span></span>  
  
-   <span data-ttu-id="d6e88-118">Усилить зрительный эффект графика можно, увеличив ширину границы до 3 и добавив смещение тени со значением 1.</span><span class="sxs-lookup"><span data-stu-id="d6e88-118">To improve the visual impact of the default line chart, consider changing the width of the series border to 3, and adding a shadow offset of 1.</span></span> <span data-ttu-id="d6e88-119">В результате график станет намного более выразительным.</span><span class="sxs-lookup"><span data-stu-id="d6e88-119">This will create a much bolder line chart.</span></span> <span data-ttu-id="d6e88-120">Если понадобится сменить тип диаграммы с графика на другой тип, то может понадобиться присвоить этим свойствам значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d6e88-120">You will need to revert these properties to their original values if you change the chart type from Line to another type.</span></span>  
  
-   <span data-ttu-id="d6e88-121">Ели в наборе данных существуют пустые значения, график заполнит их линиями-заполнителями для обеспечения непрерывности графика.</span><span class="sxs-lookup"><span data-stu-id="d6e88-121">If your dataset includes empty values, the line chart will add empty points, in the form of placeholder lines, in order to maintain continuity on the chart.</span></span> <span data-ttu-id="d6e88-122">Если отображение этих линий нежелательно, набор данных можно представить с помощью дискретных типов диаграмм, например линейчатых диаграмм или гистограмм.</span><span class="sxs-lookup"><span data-stu-id="d6e88-122">If you would rather not see these lines, consider displaying your dataset using a non-contiguous chart type such as a bar or column chart.</span></span>  
  
-   <span data-ttu-id="d6e88-123">Для создания линии графику требуются как минимум 2 точки.</span><span class="sxs-lookup"><span data-stu-id="d6e88-123">A line chart requires at least two points to draw a line.</span></span>  <span data-ttu-id="d6e88-124">Если в наборе данных существует только одна точка данных, то график будет отображен как единственный маркер точки данных.</span><span class="sxs-lookup"><span data-stu-id="d6e88-124">If your dataset has only one data point, the line chart will display as a single data point marker.</span></span>  
  
-   <span data-ttu-id="d6e88-125">Ряд, отображенный в виде линии, не займет много места в области диаграммы.</span><span class="sxs-lookup"><span data-stu-id="d6e88-125">A series that is drawn as a line will not take up much space within a chart area.</span></span>  <span data-ttu-id="d6e88-126">В связи с этим графики часто совмещаются с другими типами диаграмм, например гистограммами.</span><span class="sxs-lookup"><span data-stu-id="d6e88-126">For this reason, line charts are frequently combined with other chart types such as column charts.</span></span> <span data-ttu-id="d6e88-127">Однако график не может быть совмещен с линейчатыми, полярными, круговыми и фигурными диаграммами.</span><span class="sxs-lookup"><span data-stu-id="d6e88-127">However, you cannot combine a line chart with bar, polar, pie or shape chart types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e88-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6e88-128">See Also</span></span>  
 <span data-ttu-id="d6e88-129">[Линейчатые диаграммы (построитель отчетов и службы SSRS)](bar-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6e88-129">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6e88-130">[Гистограммы (построитель отчетов и службы SSRS)](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6e88-130">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6e88-131">[Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6e88-131">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6e88-132">[Типы диаграмм (построитель отчетов и службы SSRS)](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6e88-132">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6e88-133">[Диаграммы с областями (построитель отчетов и службы SSRS)](area-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6e88-133">[Area Charts &#40;Report Builder and SSRS&#41;](area-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6e88-134">[Точки данных со значением NULL и пустые точки в диаграммах (построитель отчетов и службы SSRS)](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6e88-134">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d6e88-135">Диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d6e88-135">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
