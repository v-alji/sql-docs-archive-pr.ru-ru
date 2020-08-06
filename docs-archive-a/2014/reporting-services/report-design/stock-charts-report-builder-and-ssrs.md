---
title: Биржевые диаграммы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f75ca11e-b7f5-4ac0-ba17-fe6f82742dad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a0f8c9c7dbc750bdb477f2ea1d96aa03f7ad022f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654774"
---
# <a name="stock-charts-report-builder-and-ssrs"></a><span data-ttu-id="6c2a2-102">Биржевые диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6c2a2-102">Stock Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6c2a2-103">Биржевая диаграмма — это диаграмма, специально созданная для работы с финансовыми или научными данными, в которой на каждую точку данных приходится до четырех значений.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-103">A stock chart is specifically designed for financial or scientific data that uses up to four values per data point.</span></span> <span data-ttu-id="6c2a2-104">Эти значения сравниваются со значениями максимума, минимума, открытия и закрытия, используемыми для отображения биржевых данных.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-104">These values align with the high, low, open and close values that are used to plot financial stock data.</span></span> <span data-ttu-id="6c2a2-105">В этом типе диаграммы значения открытия и закрытия отображаются с помощью маркеров (обычно это линии или треугольники).</span><span class="sxs-lookup"><span data-stu-id="6c2a2-105">This chart type displays opening and closing values by using markers, which are typically lines or triangles.</span></span> <span data-ttu-id="6c2a2-106">В следующем примере значения открытия помечены маркерами слева, а значения закрытия — маркерами справа.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-106">In the following example, the opening values are shown by the markers on the left, and the closing values are shown by the markers on the right.</span></span>  
  
 <span data-ttu-id="6c2a2-107">![Биржевая диаграмма](../media/rs-stockchart.gif "Биржевая диаграмма")</span><span class="sxs-lookup"><span data-stu-id="6c2a2-107">![Stock chart](../media/rs-stockchart.gif "Stock chart")</span></span>  
  
 <span data-ttu-id="6c2a2-108">Пример биржевой диаграммы доступен в виде образца отчета построителя отчетов [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c2a2-108">An example of a stock chart is available as a sample [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="6c2a2-109">Дополнительные сведения о скачивании этого и других примеров отчетов см. в статье [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="6c2a2-109">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="6c2a2-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="6c2a2-110">Variations</span></span>  
  
-   <span data-ttu-id="6c2a2-111">**Диаграмма «японские свечи»** .</span><span class="sxs-lookup"><span data-stu-id="6c2a2-111">**Candlestick**.</span></span> <span data-ttu-id="6c2a2-112">Диаграмма «японские свечи» — это специализированная форма биржевой диаграммы, в которой для отражения расстояния между значениями открытия и закрытия используются прямоугольники.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-112">The candlestick chart is a specialized form of the stock chart, wherein boxes are used to show the range between the open and close values.</span></span> <span data-ttu-id="6c2a2-113">Как и в биржевой диаграмме, в диаграмме «японские свечи» может быть отображено до четырех значений для каждой точки данных.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-113">Like the stock chart, the candlestick chart can display up to four values per data point.</span></span>  
  
## <a name="data-considerations-for-stock-charts"></a><span data-ttu-id="6c2a2-114">Соображения касательно данных в биржевых диаграммах</span><span class="sxs-lookup"><span data-stu-id="6c2a2-114">Data Considerations for Stock Charts</span></span>  
  
-   <span data-ttu-id="6c2a2-115">При представлении большого количества биржевых точек данных, например изменения курса акций в течение года, сложно определить каждое отдельное значение максимума, минимума, открытия и закрытия каждой точки данных.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-115">When presenting many stock data points, such as annual stock price trend, it is difficult to distinguish each open, close, high and low value of each data point.</span></span> <span data-ttu-id="6c2a2-116">В этом случае вместо биржевой диаграммы следует использовать график.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-116">In this scenario, consider using a line chart instead of a stock chart.</span></span>  
  
-   <span data-ttu-id="6c2a2-117">При создании осей метки на них обычно начинаются с нуля.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-117">When axis labels are generated, labeling usually begins at zero.</span></span>  <span data-ttu-id="6c2a2-118">Обычно колебания курса акций не так велики, как разброс значений в других наборах данных.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-118">In general, stock prices do not fluctuate to the same degree as other data sets.</span></span> <span data-ttu-id="6c2a2-119">В связи с этим можно отключить метки осей, начиная с нуля, чтобы обеспечить лучший просмотр данных.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-119">For this reason, you may want to disable the axis labels from starting at zero, in order to get a better view of your data.</span></span> <span data-ttu-id="6c2a2-120">Это можно сделать, установив свойство **IncludeZero** в значение **false** в диалоговом окне **Свойства оси** окна «Свойства».</span><span class="sxs-lookup"><span data-stu-id="6c2a2-120">To do this, set **IncludeZero** to **false** in the **Axis Properties** dialog box or the Properties window.</span></span> <span data-ttu-id="6c2a2-121">Дополнительные сведения о том, как диаграмма создает метки осей, см. в разделе [Форматирование меток оси на диаграмме (построитель отчетов и службы SSRS)](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6c2a2-121">For more information about how the chart generates axis labels, see [Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="6c2a2-122">предоставляют множество вычисляемых формул для работы с биржевыми диаграммами, включая «Индикатор цен», «Индекс относительной силы», «Схождение/расхождение скользящего среднего» и т.п.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-122">provides many calculated formulas for use with stock charts, including Price Indicator, Relative Strength Index, MACD and more.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c2a2-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="6c2a2-123">See Also</span></span>  
 <span data-ttu-id="6c2a2-124">[Диаграммы диапазонов &#40;построитель отчетов и службы SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6c2a2-124">[Range Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6c2a2-125">[Диаграммы &#40;построитель отчетов и службы SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6c2a2-125">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6c2a2-126">[Форматирование построитель отчетов &#40;диаграммы и SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6c2a2-126">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6c2a2-127">Диалоговое окно "Свойства оси" — "Параметры оси" (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6c2a2-127">Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;</span></span>](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md)  
  
  
