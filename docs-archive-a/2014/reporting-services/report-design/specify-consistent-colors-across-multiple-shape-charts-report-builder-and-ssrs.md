---
title: Указание согласованных цветов для нескольких фигурных диаграмм (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d52f68e9-2ba7-4bff-9053-4089e5164ab4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c2c89f0f8cda3b7d6ef6b2acbd0de66c87170357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654781"
---
# <a name="specify-consistent-colors-across-multiple-shape-charts-report-builder-and-ssrs"></a><span data-ttu-id="114f2-102">Указание согласованных цветов для нескольких фигурных диаграмм (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="114f2-102">Specify Consistent Colors across Multiple Shape Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="114f2-103">На нефигурных диаграммах новые цвета выбираются из палитры, связанной с индексом рядов в диаграмме.</span><span class="sxs-lookup"><span data-stu-id="114f2-103">On non-shape charts, a new color is selected from the palette based on the index of series in the chart.</span></span> <span data-ttu-id="114f2-104">Например, первый ряд в диаграмме сопоставлен с первым цветом палитры.</span><span class="sxs-lookup"><span data-stu-id="114f2-104">For example, the first series on your chart will be mapped to the first color in the palette.</span></span> <span data-ttu-id="114f2-105">Однако в фигурных диаграммах используется другой принцип.</span><span class="sxs-lookup"><span data-stu-id="114f2-105">However, this behavior differs for shape charts.</span></span> <span data-ttu-id="114f2-106">В фигурных диаграммах каждый цвет палитры сопоставлен с точкой данных в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="114f2-106">On shape charts, each color in the palette is mapped to a data point in the dataset.</span></span> <span data-ttu-id="114f2-107">Так, точка данных 1 сопоставлен с первым цветом палитры, точка данных 2 — со вторым цветом палитры и т. д.</span><span class="sxs-lookup"><span data-stu-id="114f2-107">For example, data point 1 is mapped to the first color in the palette, data point 2 is mapped to the second color palette and so on.</span></span>  
  
 <span data-ttu-id="114f2-108">Если точка данных не имеет значения, она опускается из изображения на фигурной диаграмме.</span><span class="sxs-lookup"><span data-stu-id="114f2-108">If a data point has no value, it is omitted from display on a shape chart.</span></span> <span data-ttu-id="114f2-109">Это означает, что точка данных не включается в число окрашиваемых.</span><span class="sxs-lookup"><span data-stu-id="114f2-109">This means that the data point is skipped from being colored.</span></span> <span data-ttu-id="114f2-110">Так, если точка 2 имеет значение «ноль», точка 1 будет соответствовать первому цвету палитры, а точка 3 — второму цвету палитры.</span><span class="sxs-lookup"><span data-stu-id="114f2-110">For example, if point 2 has a value of zero, point 1 will be mapped to the first color in the palette, and point 3 will be mapped to the second color in the palette.</span></span> <span data-ttu-id="114f2-111">Такой подход полезен, поскольку пустые точки набора данных круговой диаграммы не обязательно используют палитру цветов, когда нет необходимости рисования пустой точки.</span><span class="sxs-lookup"><span data-stu-id="114f2-111">This approach is useful because the empty points in the dataset of a pie chart do not unnecessarily use a palette color when the empty point does not need to be drawn.</span></span>  
  
 <span data-ttu-id="114f2-112">В качестве побочного эффекта при отображении в отчете нескольких круговых диаграмм расположенные в этих диаграммах точки данных одной и той же категории группирования могут отображаться различными цветами.</span><span class="sxs-lookup"><span data-stu-id="114f2-112">As a side effect, when multiple pie charts are displayed in a report, the pie charts may display different colors for data points that have the same category grouping.</span></span> <span data-ttu-id="114f2-113">Для решения этой проблемы необходимо определять индивидуальные цвета, соответствующие группе категорий, а не индивидуальным значениям данных.</span><span class="sxs-lookup"><span data-stu-id="114f2-113">To resolve this, you need to define individual colors that map to a category group instead of individual data values.</span></span> <span data-ttu-id="114f2-114">Способ определения зависит от того, представляет ли собой фигурная диаграмма sparkline-график в таблице или матрице или она непосредственно находится в отчете.</span><span class="sxs-lookup"><span data-stu-id="114f2-114">How you do this depends on if the shape charts are sparklines in a table or matrix, or if they are shape charts in the report itself.</span></span>  
  
 <span data-ttu-id="114f2-115">Условные обозначения связаны с рядом, поэтому любой цвет, заданный пользователем для ряда, будет автоматически отображаться в условных обозначениях.</span><span class="sxs-lookup"><span data-stu-id="114f2-115">The legend is connected to the series, so any color you specify for the series will automatically be shown on the legend.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-consistent-colors-across-multiple-sparkline-shape-charts-in-a-table-or-matrix"></a><span data-ttu-id="114f2-116">Указание согласованных цветов для нескольких фигурных диаграмм в виде спарклайн-графиков в таблице или матрице</span><span class="sxs-lookup"><span data-stu-id="114f2-116">To specify consistent colors across multiple sparkline shape charts in a table or matrix</span></span>  
  
1.  <span data-ttu-id="114f2-117">Щелкните диаграмму, чтобы отобразить панель «Данные диаграммы».</span><span class="sxs-lookup"><span data-stu-id="114f2-117">Click the chart to display the Chart Data pane.</span></span>  
  
2.  <span data-ttu-id="114f2-118">Щелкните правой кнопкой мыши в области **Группы категорий** и выберите пункт **Свойства группы категорий**.</span><span class="sxs-lookup"><span data-stu-id="114f2-118">In the **Category Groups** area, right-click a category and click **Category Group Properties**.</span></span>  
  
3.  <span data-ttu-id="114f2-119">На вкладке «Общие» в окне **Синхронизация групп в** выберите название категории, которую вы хотите синхронизовать по цвету, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="114f2-119">On the General tab, in the **Synchronize groups in** box, click the name of the category for which you would like to synchronize colors, and then click **OK**.</span></span>  
  
### <a name="to-specify-consistent-colors-across-multiple-shape-charts"></a><span data-ttu-id="114f2-120">Указание согласованных цветов в нескольких фигурных диаграммах</span><span class="sxs-lookup"><span data-stu-id="114f2-120">To specify consistent colors across multiple shape charts</span></span>  
  
1.  <span data-ttu-id="114f2-121">Щелкните правой кнопкой мыши область за пределами текста отчета и выберите пункт **Свойства отчета**.</span><span class="sxs-lookup"><span data-stu-id="114f2-121">Right-click outside the body of the report, and select **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="114f2-122">В текстовом поле **Код**введите следующий код.</span><span class="sxs-lookup"><span data-stu-id="114f2-122">In **Code**, type the following code into the textbox.</span></span>  
  
    ```  
    Private colorPalette As String() = {"Color1", "Color2", "Color3"}  
    Private count As Integer = 0  
    Private mapping As New System.Collections.Hashtable()  
    Public Function GetColor(ByVal groupingValue As String) As String  
        If mapping.ContainsKey(groupingValue) Then  
            Return mapping(groupingValue)  
        End If  
        Dim c As String = colorPalette(count Mod colorPalette.Length)  
        count = count + 1  
        mapping.Add(groupingValue, c)  
        Return c  
    End Function  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="114f2-123">Строки «Color1» пользователю следует заменять собственными цветами.</span><span class="sxs-lookup"><span data-stu-id="114f2-123">You will need to replace the "Color1" strings with your own colors.</span></span> <span data-ttu-id="114f2-124">Можно использовать именованные цвета, например, «Красный», или представляющие тот или иной цвет шестиразрядные шестнадцатеричные значения, такие, как "#FFFFFF" для черного.</span><span class="sxs-lookup"><span data-stu-id="114f2-124">You can use named colors, for example "Red", or you can use six-digit hexadecimal value that represent the color, such as "#FFFFFF" for black.</span></span> <span data-ttu-id="114f2-125">Если определено более трех цветов, нужно расширить массив цветов, чтобы число цветов в массиве соответствовало числу точек в фигурной диаграмме.</span><span class="sxs-lookup"><span data-stu-id="114f2-125">If you have more than three colors defined, you will need to extend the array of colors so that the number of colors in the array matches the number of points in your shape chart.</span></span> <span data-ttu-id="114f2-126">Можно добавлять новые цвета к массиву, составив список строковых значений с разделителями-запятыми, содержащий именованные цвета или шестнадцатеричные представления цветов.</span><span class="sxs-lookup"><span data-stu-id="114f2-126">You can add new colors to the array by specifying a comma-separated list of string values that contain named colors or hexadecimal representations of colors.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="114f2-127">Щелкните правой кнопкой мыши фигурную диаграмму и выберите пункт **Свойства ряда**.</span><span class="sxs-lookup"><span data-stu-id="114f2-127">Right-click on the shape chart and select **Series Properties**.</span></span>  
  
5.  <span data-ttu-id="114f2-128">В меню **Заливка**нажмите кнопку **Выражение** (*fx*) и измените выражение для свойства **Цвет** .</span><span class="sxs-lookup"><span data-stu-id="114f2-128">In **Fill**, click the **Expression** (*fx*) button to edit the expression for the **Color** property.</span></span>  
  
6.  <span data-ttu-id="114f2-129">Введите следующее выражение, где "MyCategoryField" ― это поле, отображаемое в области **Группы Категорий (Category Groups)** :</span><span class="sxs-lookup"><span data-stu-id="114f2-129">Type the following expression, where "MyCategoryField" is the field that is displayed in the **Category Groups** area:</span></span>  
  
    ```  
    =Code.GetColor(Fields!MyCategoryField)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="114f2-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="114f2-130">See Also</span></span>  
 <span data-ttu-id="114f2-131">[Форматирование цветов для рядов на диаграмме (построитель отчетов и службы SSRS)](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="114f2-131">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="114f2-132">[Добавление в диаграмму стилей рамки, рельефа и текстуры &#40;построитель отчетов и службы SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="114f2-132">[Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span></span>  
 <span data-ttu-id="114f2-133">[Задание цветов диаграммы с помощью палитры &#40;построитель отчетов и службы SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="114f2-133">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="114f2-134">[Добавление пустых точек на диаграмму &#40;построитель отчетов и SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="114f2-134">[Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="114f2-135">[Фигурные диаграммы &#40;построитель отчетов и службы SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="114f2-135">[Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="114f2-136">[Связывание нескольких областей данных с одним набором данных (построитель отчетов и службы SSRS)](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="114f2-136">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="114f2-137">[Вложенные области данных (построитель отчетов и службы SSRS)](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="114f2-137">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="114f2-138">Спарклайны и гистограммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="114f2-138">Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
  
