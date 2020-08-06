---
title: Выделение данных диаграммы путем добавления полосковых линий (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: addd6137-4b6e-4e88-a7e8-9600fcd1ccce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01b0bb41a71daf9ac558ce8d8bb84480426870c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656153"
---
# <a name="highlight-chart-data-by-adding-strip-lines-report-builder-and-ssrs"></a><span data-ttu-id="b18ed-102">Выделение данных диаграммы путем добавления полосковых линий (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="b18ed-102">Highlight Chart Data by Adding Strip Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b18ed-103">Полосковые линии, или полосы, представляют собой горизонтальные или вертикальные области, которые оттеняют фон диаграммы через регулярные или заданные пользователем интервалы.</span><span class="sxs-lookup"><span data-stu-id="b18ed-103">Strip lines, or strips, are horizontal or vertical ranges that shade the background of the chart in regular or custom intervals.</span></span> <span data-ttu-id="b18ed-104">Полосковые линии используют, чтобы:</span><span class="sxs-lookup"><span data-stu-id="b18ed-104">You can use strip lines to:</span></span>  
  
-   <span data-ttu-id="b18ed-105">Улучшить читаемость отдельных значений диаграммы.</span><span class="sxs-lookup"><span data-stu-id="b18ed-105">Improve readability for looking up individual values on the chart.</span></span> <span data-ttu-id="b18ed-106">Указывайте полосковые линии через регулярные интервалы, чтобы отделить точки данных при чтении диаграммы.</span><span class="sxs-lookup"><span data-stu-id="b18ed-106">Specify strip lines at regular intervals to help separate data points when reading the chart.</span></span>  
  
-   <span data-ttu-id="b18ed-107">Выделить даты, возникающие через регулярные интервалы.</span><span class="sxs-lookup"><span data-stu-id="b18ed-107">Highlight dates that occur at regular intervals.</span></span> <span data-ttu-id="b18ed-108">Например, в отчете о продажах можно воспользоваться полосковыми линиями для обозначения точек данных, соответствующих концу недели.</span><span class="sxs-lookup"><span data-stu-id="b18ed-108">For example, in a sales report you might use strip lines to identify weekend data points.</span></span>  
  
-   <span data-ttu-id="b18ed-109">Выделить конкретный ключевой диапазон.</span><span class="sxs-lookup"><span data-stu-id="b18ed-109">Highlight a specific key range.</span></span> <span data-ttu-id="b18ed-110">В предыдущем примере можно выделить полосковой линией наибольший диапазон продаж от 80 до 100 долларов.</span><span class="sxs-lookup"><span data-stu-id="b18ed-110">Using the previous example, you can use one strip line to highlight the highest range of sales that is between $80-100.</span></span>  
  
 <span data-ttu-id="b18ed-111">Полосковые линии не применяются в фигурных и полярных типах диаграмм.</span><span class="sxs-lookup"><span data-stu-id="b18ed-111">Strip lines are not applicable to Shape or Polar chart types.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-interlaced-strip-lines-at-regular-intervals-on-a-chart"></a><span data-ttu-id="b18ed-112">Отображение на диаграмме полосковых линий, чередующихся через равные интервалы</span><span class="sxs-lookup"><span data-stu-id="b18ed-112">To display interlaced strip lines at regular intervals on a chart</span></span>  
  
1.  <span data-ttu-id="b18ed-113">Для отображения горизонтальных полосковых линий щелкните правой кнопкой мыши вертикальную ось диаграммы и выберите пункт **Свойства вертикальной оси**.</span><span class="sxs-lookup"><span data-stu-id="b18ed-113">To show horizontal strip lines, right-click the vertical chart axis and click **VerticalAxis Properties**.</span></span>  
  
     <span data-ttu-id="b18ed-114">Для отображения вертикальных полосковых линий щелкните правой кнопкой мыши горизонтальную ось диаграммы и выберите пункт **Свойства горизонтальной оси**.</span><span class="sxs-lookup"><span data-stu-id="b18ed-114">To show vertical strip lines, right-click the horizontal chart axis and click **Horizontal Axis Properties**.</span></span>  
  
2.  <span data-ttu-id="b18ed-115">Выберите параметр **Использовать чередование** .</span><span class="sxs-lookup"><span data-stu-id="b18ed-115">Select the **Use interlacing** option.</span></span> <span data-ttu-id="b18ed-116">На диаграмме появятся серые полосковые линии.</span><span class="sxs-lookup"><span data-stu-id="b18ed-116">Grey strip lines will appear on your chart.</span></span>  
  
3.  <span data-ttu-id="b18ed-117">Укажите цвет полосковых линий с помощью расположенного рядом раскрывающегося списка **Цвет** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="b18ed-117">(Optional) Specify a color for the strip lines using the adjacent **Color** drop-down list.</span></span>  
  
### <a name="to-display-interlaced-strip-lines-at-custom-intervals-on-a-chart"></a><span data-ttu-id="b18ed-118">Отображение на диаграмме полосковых линий, чередующихся через заданные пользователем интервалы</span><span class="sxs-lookup"><span data-stu-id="b18ed-118">To display interlaced strip lines at custom intervals on a chart</span></span>  
  
1.  <span data-ttu-id="b18ed-119">Для отображения горизонтальных полосковых линий щелкните правой кнопкой мыши вертикальную ось диаграммы и выберите пункт **Свойства вертикальной оси**.</span><span class="sxs-lookup"><span data-stu-id="b18ed-119">To show horizontal strip lines, right-click the vertical chart axis and click **VerticalAxis Properties**.</span></span>  
  
     <span data-ttu-id="b18ed-120">Для отображения вертикальных полосковых линий щелкните правой кнопкой мыши горизонтальную ось диаграммы и выберите пункт **Свойства горизонтальной оси**.</span><span class="sxs-lookup"><span data-stu-id="b18ed-120">To show vertical strip lines, right-click the horizontal chart axis and click **Horizontal Axis Properties**.</span></span>  
  
     <span data-ttu-id="b18ed-121">Ее свойства отображаются в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="b18ed-121">The axis properties are displayed in the Properties window.</span></span>  
  
2.  <span data-ttu-id="b18ed-122">В разделе **Вид** панели свойств нажмите для свойства StripLines кнопку "Изменить коллекцию (...)", чтобы открыть **редактор коллекции ChartStripLine**.</span><span class="sxs-lookup"><span data-stu-id="b18ed-122">In the **Appearance** section of the Properties pane, for the StripLines property, click the Edit Collection (...) button to open the **ChartStripLine Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="b18ed-123">Нажмите кнопку **Добавить** , чтобы добавить новую полосковую линию в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="b18ed-123">Click **Add** to add a new strip line to the collection.</span></span>  
  
4.  <span data-ttu-id="b18ed-124">Щелкните StripWidth, чтобы задать ширину полосковой линии в отчете в дюймах.</span><span class="sxs-lookup"><span data-stu-id="b18ed-124">Click StripWidth to specify the width of the strip line, measured in inches on the report.</span></span> <span data-ttu-id="b18ed-125">При выделении даты или времени щелкните StripWidthType и выберите интервал времени.</span><span class="sxs-lookup"><span data-stu-id="b18ed-125">If you are highlighting dates or times, click StripWidthType and select a time interval.</span></span>  
  
5.  <span data-ttu-id="b18ed-126">Введите значение или выражение для свойства Interval, чтобы задать частоту повторения полосковых линий.</span><span class="sxs-lookup"><span data-stu-id="b18ed-126">Type a value or expression for the Interval to specify how often the strip line will repeat.</span></span>  <span data-ttu-id="b18ed-127">Например, если указать интервал 10, а толщина полосковой линии равна 5, то полосковые линии появятся у значений от 0 до 5, от 15 до 20, от 30 до 35 и т. д.</span><span class="sxs-lookup"><span data-stu-id="b18ed-127">For example, if you specify an interval of 10, and your strip line width is 5, strip lines will display at values of 0 to 5, 15 to 20, 30 to 35, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b18ed-128">По умолчанию свойство Interval установлено в значение Auto. Оно означает, что диаграмма не будет вычислять интервал для пользовательских полосковых линий.</span><span class="sxs-lookup"><span data-stu-id="b18ed-128">By default, Interval is set to Auto, which means the chart will not calculate an interval for custom strip lines.</span></span> <span data-ttu-id="b18ed-129">Диаграмма вычисляет интервалы для полосковых линий, только если задано значение интервала.</span><span class="sxs-lookup"><span data-stu-id="b18ed-129">The chart only calculates intervals for strip lines if an interval value is set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b18ed-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="b18ed-130">See Also</span></span>  
 <span data-ttu-id="b18ed-131">[Форматирование меток оси на диаграмме (построитель отчетов и службы SSRS)](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b18ed-131">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b18ed-132">[Форматирование диаграммы (построитель отчетов и службы SSRS)](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b18ed-132">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b18ed-133">Добавление скользящего среднего в диаграмму (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="b18ed-133">Add a Moving Average to a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md)  
  
  
