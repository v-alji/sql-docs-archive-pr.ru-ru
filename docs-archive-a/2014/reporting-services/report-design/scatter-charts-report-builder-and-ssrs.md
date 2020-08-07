---
title: Точечные диаграммы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2520ae24-0609-4890-807d-3267018aba8e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 93f9b31089eb8399c7fdfd201d3c799608f2e91e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733621"
---
# <a name="scatter-charts-report-builder-and-ssrs"></a><span data-ttu-id="d361b-102">Точечные диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d361b-102">Scatter Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d361b-103">В точечной диаграмме ряды отображаются как наборы точек.</span><span class="sxs-lookup"><span data-stu-id="d361b-103">A scatter chart displays a series as a set of points.</span></span> <span data-ttu-id="d361b-104">Значения представлены расположением точки на плоскости диаграммы.</span><span class="sxs-lookup"><span data-stu-id="d361b-104">Values are represented by the position of the points on the chart.</span></span> <span data-ttu-id="d361b-105">Категории представлены различными маркерами.</span><span class="sxs-lookup"><span data-stu-id="d361b-105">Categories are represented by different markers on the chart.</span></span> <span data-ttu-id="d361b-106">Точечные диаграммы обычно используются для сравнения агрегированных значений разных категорий.</span><span class="sxs-lookup"><span data-stu-id="d361b-106">Scatter charts are typically used to compare aggregated data across categories.</span></span> <span data-ttu-id="d361b-107">Дополнительные сведения о добавлении данных в точечные диаграммы см. в разделе [Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="d361b-107">For more information on how to add data to a scatter chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md)</span></span>  
  
 <span data-ttu-id="d361b-108">На следующем рисунке показан пример точечной диаграммы.</span><span class="sxs-lookup"><span data-stu-id="d361b-108">The following illustration shows an example of a scatter chart.</span></span>  
  
 <span data-ttu-id="d361b-109">![Точечная диаграмма](../media/rs-scatterchart.gif "Точечная диаграмма")</span><span class="sxs-lookup"><span data-stu-id="d361b-109">![Scatter chart](../media/rs-scatterchart.gif "Scatter chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="d361b-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="d361b-110">Variations</span></span>  
  
-   <span data-ttu-id="d361b-111">**Пузырьки.**</span><span class="sxs-lookup"><span data-stu-id="d361b-111">**Bubble.**</span></span> <span data-ttu-id="d361b-112">Пузырьковые диаграммы демонстрируют разницу между двумя значениями точки данных с помощью размера пузырька.</span><span class="sxs-lookup"><span data-stu-id="d361b-112">Bubble charts display the difference between two values of a data point based on the size of the bubble.</span></span> <span data-ttu-id="d361b-113">Чем больше пузырек, тем больше разница.</span><span class="sxs-lookup"><span data-stu-id="d361b-113">The larger the bubble, the larger the difference between the two values.</span></span>  
  
-   <span data-ttu-id="d361b-114">**Трехмерная пузырьковая диаграмма**.</span><span class="sxs-lookup"><span data-stu-id="d361b-114">**3-D Bubble**.</span></span> <span data-ttu-id="d361b-115">Пузырьковая диаграмма с трехмерным эффектом.</span><span class="sxs-lookup"><span data-stu-id="d361b-115">A bubble chart displayed in 3-D.</span></span>  
  
## <a name="data-considerations-for-a-scatter-chart"></a><span data-ttu-id="d361b-116">Вопросы работы с данными для точечной диаграммы</span><span class="sxs-lookup"><span data-stu-id="d361b-116">Data Considerations for a Scatter Chart</span></span>  
  
-   <span data-ttu-id="d361b-117">Точечные диаграммы часто используются для вывода и сравнения численных значений — научных, статистических, инженерных данных.</span><span class="sxs-lookup"><span data-stu-id="d361b-117">Scatter charts are commonly used for displaying and comparing numeric values, such as scientific, statistical, and engineering data.</span></span>  
  
-   <span data-ttu-id="d361b-118">Точечные диаграммы рекомендуется использовать при сравнении большого количества точек данных без учета времени.</span><span class="sxs-lookup"><span data-stu-id="d361b-118">Use the scatter chart when you want to compare large numbers of data points without regard to time.</span></span> <span data-ttu-id="d361b-119">Чем больше данных включено в точечную диаграмму, тем точнее сравнение.</span><span class="sxs-lookup"><span data-stu-id="d361b-119">The more data that you include in a scatter chart, the better the comparisons that you can make.</span></span>  
  
-   <span data-ttu-id="d361b-120">В пузырьковой диаграмме для каждой точки данных требуется два значения — верхнее и нижнее.</span><span class="sxs-lookup"><span data-stu-id="d361b-120">The bubble chart requires two values (top and bottom) per data point.</span></span>  
  
-   <span data-ttu-id="d361b-121">Точечные диаграммы идеально подходят для изучения распределения величин и кластеров точек данных.</span><span class="sxs-lookup"><span data-stu-id="d361b-121">Scatter charts are ideal for handling the distribution of values and clusters of data points.</span></span> <span data-ttu-id="d361b-122">Этот тип диаграммы лучше всего подходит для работы с наборами данных, содержащими много точек (например, несколько тысяч).</span><span class="sxs-lookup"><span data-stu-id="d361b-122">This is the best chart type if your dataset contains many points (for example, several thousand points).</span></span> <span data-ttu-id="d361b-123">Точечная диаграмма с несколькими рядами обычно выглядит неряшливо, и лучше не применять ее для таких случаев.</span><span class="sxs-lookup"><span data-stu-id="d361b-123">Displaying multiple series on a point chart is visually distracting and should be avoided.</span></span> <span data-ttu-id="d361b-124">В этом случае лучше использовать линейчатую диаграмму.</span><span class="sxs-lookup"><span data-stu-id="d361b-124">In this scenario, consider using a line chart.</span></span>  
  
-   <span data-ttu-id="d361b-125">По умолчанию на точечных диаграммах точки данных выводятся в виде точек.</span><span class="sxs-lookup"><span data-stu-id="d361b-125">By default, scatter charts display data points as circles.</span></span> <span data-ttu-id="d361b-126">Если на точечной диаграмме необходимо вывести несколько рядов, рекомендуется использовать маркеры разной формы — треугольные, квадратные, ромбические или иные.</span><span class="sxs-lookup"><span data-stu-id="d361b-126">If you have multiple series on a scatter chart, consider changing the marker shape of each point to be square, triangle, diamond, or another shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d361b-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="d361b-127">See Also</span></span>  
 <span data-ttu-id="d361b-128">[Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d361b-128">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d361b-129">[Типы диаграмм (построитель отчетов и службы SSRS)](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d361b-129">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d361b-130">[Форматирование диаграммы (построитель отчетов и службы SSRS)](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d361b-130">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d361b-131">Графики (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d361b-131">Line Charts &#40;Report Builder and SSRS&#41;</span></span>](line-charts-report-builder-and-ssrs.md)  
  
  
