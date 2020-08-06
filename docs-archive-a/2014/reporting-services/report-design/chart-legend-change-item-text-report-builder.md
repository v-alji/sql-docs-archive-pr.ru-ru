---
title: Изменение текста элемента условных обозначений (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9e82fa34-17ed-494f-b25d-03dcc353a21f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d0bb721aa0ff03a5211065111c98605cd86e971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667584"
---
# <a name="change-the-text-of-a-legend-item-report-builder-and-ssrs"></a><span data-ttu-id="72676-102">Изменение текста элемента условных обозначений (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="72676-102">Change the Text of a Legend Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="72676-103">При помещении поля в область «Значения» диаграммы автоматически создается элемент условных обозначений, содержащий имя этого поля.</span><span class="sxs-lookup"><span data-stu-id="72676-103">When a field is placed in the Values area of the chart, a legend item is automatically generated that contains the name of this field.</span></span> <span data-ttu-id="72676-104">Каждый элемент условных обозначений связан с отдельным рядом на диаграмме, за исключением фигурных диаграмм, в которых условные обозначения связаны с конкретными точками данных, а не с отдельными рядами.</span><span class="sxs-lookup"><span data-stu-id="72676-104">Every legend item is connected to an individual series on the chart, with the exception of shape charts, where the legend is connected to individual data points instead of individual series.</span></span>  
  
 <span data-ttu-id="72676-105">В фигурных диаграммах можно изменять текст элемента условных обозначений для отображения дополнительных сведений об отдельных точках данных.</span><span class="sxs-lookup"><span data-stu-id="72676-105">On shape charts, you can change the text of a legend item to show more information about the individual data points.</span></span> <span data-ttu-id="72676-106">Например, если в условных обозначениях необходимо отобразить значения точек данных в виде процентов, то используется ключевое слово `#PERCENT`.</span><span class="sxs-lookup"><span data-stu-id="72676-106">For example, if you want to show the values of the data points as percentages in the legend, you can use a keyword such as `#PERCENT`.</span></span> <span data-ttu-id="72676-107">Для применения числовых форматов и форматов данных добавляются коды формата .NET Framework совместно с ключевыми словами.</span><span class="sxs-lookup"><span data-stu-id="72676-107">You can append .NET Framework format codes in conjunction with keywords to apply numeric and date formats.</span></span> <span data-ttu-id="72676-108">Дополнительные сведения о ключевых словах см. в разделе [Форматирование точек данных на диаграмме (построитель отчетов и службы SSRS)](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="72676-108">For more information about keywords, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="72676-109">![Форма диаграммы](../media/sharpchart.png "Форма диаграммы")</span><span class="sxs-lookup"><span data-stu-id="72676-109">![Sharp Chart](../media/sharpchart.png "Sharp Chart")</span></span>  
  
 <span data-ttu-id="72676-110">В диаграммах, отличных от фигурных, можно изменять текст элемента условных обозначений.</span><span class="sxs-lookup"><span data-stu-id="72676-110">On non-shape charts, you can change the text of a legend item.</span></span> <span data-ttu-id="72676-111">Например, если ряд имеет имя «Ряд1», то может потребоваться изменить этот текст на более описательное имя, например, «Продажи за 2008 год».</span><span class="sxs-lookup"><span data-stu-id="72676-111">For example, if your series name is "Series1", you may want to change the text to something more descriptive like "Sales for 2008".</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-modify-the-text-that-appears-in-the-legend-on-a-shape-chart"></a><span data-ttu-id="72676-112">Изменение текста, появляющегося в элементе условных обозначений фигурной диаграммы</span><span class="sxs-lookup"><span data-stu-id="72676-112">To modify the text that appears in the legend on a Shape chart</span></span>  
  
1.  <span data-ttu-id="72676-113">Щелкните правой кнопкой мыши ряд или поле в области **Значения** и выберите пункт **Свойства ряда**.</span><span class="sxs-lookup"><span data-stu-id="72676-113">Right-click on a series, or right-click on a field in the **Values** area, and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="72676-114">Щелкните элемент **Условные обозначения** и в поле **Пользовательский текст условных обозначений** введите ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="72676-114">Click **Legend** and in the **Custom legend text** box, type a keyword.</span></span>  
  
 <span data-ttu-id="72676-115">В следующей таблице представлены примеры ключевых слов, относящихся к определенным диаграммам, которые могут использоваться для свойства **Пользовательский текст условных обозначений** .</span><span class="sxs-lookup"><span data-stu-id="72676-115">The following table provides examples of chart-specific keywords to use for the **Custom Legend Text** property.</span></span> <span data-ttu-id="72676-116">Дополнительные сведения о ключевых словах см. в разделе [Форматирование точек данных на диаграмме (построитель отчетов и службы SSRS)](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="72676-116">For more information about keywords, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
|<span data-ttu-id="72676-117">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="72676-117">Keyword</span></span>|<span data-ttu-id="72676-118">Description</span><span class="sxs-lookup"><span data-stu-id="72676-118">Description</span></span>|<span data-ttu-id="72676-119">Пример отображения текста в условных обозначениях</span><span class="sxs-lookup"><span data-stu-id="72676-119">Example of what appears as text in the legend</span></span>|  
|-------------|-----------------|---------------------------------------------------|  
|`#PERCENT{P1}`|<span data-ttu-id="72676-120">Отображает общее значение в процентах с точностью до одного десятичного разряда.</span><span class="sxs-lookup"><span data-stu-id="72676-120">Displays the percentage of the total value to one decimal place.</span></span>|<span data-ttu-id="72676-121">85,0 %</span><span class="sxs-lookup"><span data-stu-id="72676-121">85.0%</span></span>|  
|`#VALY`|<span data-ttu-id="72676-122">Отображает действительное числовое значение поля данных.</span><span class="sxs-lookup"><span data-stu-id="72676-122">Displays the actual numeric value of the data field.</span></span>|<span data-ttu-id="72676-123">17 000</span><span class="sxs-lookup"><span data-stu-id="72676-123">17000</span></span>|  
|`#VALY{C2}`|<span data-ttu-id="72676-124">Отображает действительное числовое значение поля данных в виде валюты с точностью до двух десятичных разрядов.</span><span class="sxs-lookup"><span data-stu-id="72676-124">Displays the actual numeric value of the data field as a currency to two decimal places.</span></span>|<span data-ttu-id="72676-125">$ 170 00,00</span><span class="sxs-lookup"><span data-stu-id="72676-125">$17000.00</span></span>|  
|`#AXISLABEL (#PERCENT{P0})`|<span data-ttu-id="72676-126">Отображает текстовое представление поля категории, за которым следует значение в процентах, отображаемое для каждой категории на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="72676-126">Displays the text representation of the category field, followed by the percentage that each category displays on the chart.</span></span>|<span data-ttu-id="72676-127">Michael Blythe (85%)</span><span class="sxs-lookup"><span data-stu-id="72676-127">Michael Blythe (85%)</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="72676-128">Ключевое слово #AXISLABEL может вычисляться во время выполнения только если нет поля, указанного в области **Группы рядов** .</span><span class="sxs-lookup"><span data-stu-id="72676-128">The #AXISLABEL keyword can only be evaluated at run time when there is not a field specified in the **Series Groups** area.</span></span>  
  
### <a name="to-modify-the-text-that-appears-in-the-legend-on-a-non-shape-chart"></a><span data-ttu-id="72676-129">Изменение текста, появляющегося в элементе условных обозначений диаграммы, отличной от фигурной</span><span class="sxs-lookup"><span data-stu-id="72676-129">To modify the text that appears in the legend on a non-Shape chart</span></span>  
  
1.  <span data-ttu-id="72676-130">Щелкните правой кнопкой мыши ряд или поле в области **Значения** и выберите пункт **Свойства ряда**.</span><span class="sxs-lookup"><span data-stu-id="72676-130">Right-click on a series, or right-click on a field in the **Values** area, and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="72676-131">Щелкните элемент **Условные обозначения** и в поле **Пользовательский текст условных обозначений** введите метку условных обозначений.</span><span class="sxs-lookup"><span data-stu-id="72676-131">Click **Legend** and in the **Custom legend text** box, type a legend label.</span></span> <span data-ttu-id="72676-132">Произойдет обновление ряда с учетом этого текста.</span><span class="sxs-lookup"><span data-stu-id="72676-132">The series is updated with your text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72676-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="72676-133">See Also</span></span>  
 <span data-ttu-id="72676-134">[Форматирование условных обозначений на диаграмме (построитель отчетов и службы SSRS)](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="72676-134">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="72676-135">[Форматирование цветов для рядов на диаграмме (построитель отчетов и службы SSRS)](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72676-135">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="72676-136">Скрытие элементов условных обозначений на диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="72676-136">Hide Legend Items on the Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-legend-hide-items-report-builder.md)  
  
  
