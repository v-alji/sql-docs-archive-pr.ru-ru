---
title: Добавление в диаграмму стилей багетной рамки, рельефа и текстуры (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 737cfc80-b39e-497c-817b-b46693deb58f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 92c5d4af47b7889b9ba5ec421706848f8822075b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667589"
---
# <a name="add-bevel-emboss-and-texture-styles-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="47e56-102">Добавление в диаграмму стилей рельефа, приподнятости и текстуры (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="47e56-102">Add Bevel, Emboss, and Texture Styles to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="47e56-103">При использовании диаграмм определенных типов можно ввести в действие эффекты рисования для повышения внешней привлекательности диаграммы.</span><span class="sxs-lookup"><span data-stu-id="47e56-103">When using certain chart types, you can specify a drawing effect to increase the visual impact of your chart.</span></span> <span data-ttu-id="47e56-104">Эти эффекты рисования применяются только к ряду, представленному на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="47e56-104">These drawing effects are only applied to the series of your chart.</span></span> <span data-ttu-id="47e56-105">Они не оказывают никакого влияния на другие элементы диаграммы.</span><span class="sxs-lookup"><span data-stu-id="47e56-105">They have no effect on any other chart element.</span></span>  
  
 <span data-ttu-id="47e56-106">Если используется какой-либо вариант круговой или кольцевой диаграммы, можно определить стиль рисования с применением размытых краев или вогнутых участков, аналогичный стилю с эффектами скоса или выпуклости, которые могут быть применены к изображению.</span><span class="sxs-lookup"><span data-stu-id="47e56-106">When you are using any variant of a pie or doughnut chart, you can specify a soft edge or concave drawing style, similar to bevel or emboss effects that can be applied to an image.</span></span>  
  
 <span data-ttu-id="47e56-107">Если используется какой-либо вариант линейчатой диаграммы или гистограммы, то можно применить стили текстуры, такие как оформление в виде цилиндра, клина и переход от светлого к темному, к отдельным линейкам или столбцам.</span><span class="sxs-lookup"><span data-stu-id="47e56-107">When you are using any variant of a bar or column chart, you can apply texture styles, such as cylinder, wedge, and light-to-dark, to the individual bars or columns.</span></span>  
  
 <span data-ttu-id="47e56-108">Кроме этих стилей рисования можно добавлять границы и тени ко многим элементам диаграммы для создания иллюзии глубины.</span><span class="sxs-lookup"><span data-stu-id="47e56-108">In addition to these drawing styles, you can add borders and shadows to many chart elements to give the illusion of depth.</span></span> <span data-ttu-id="47e56-109">Дополнительные сведения о других способах форматирования диаграммы см. в разделе [Форматирование диаграммы (построитель отчетов и службы SSRS)](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="47e56-109">For more information on other ways to format the chart, see [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-bevel-or-emboss-styles-to-a-pie-or-doughnut-chart"></a><span data-ttu-id="47e56-110">Добавление стилей скоса или выпуклости к круговой или кольцевой диаграмме</span><span class="sxs-lookup"><span data-stu-id="47e56-110">To add bevel or emboss styles to a pie or doughnut chart</span></span>  
  
1.  <span data-ttu-id="47e56-111">На вкладке **Представление** выберите **Свойства** , чтобы открыть панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="47e56-111">On the **View** tab, select **Properties** to open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="47e56-112">Выберите круговую или кольцевую диаграмму, которую необходимо сделать более привлекательной.</span><span class="sxs-lookup"><span data-stu-id="47e56-112">Select the pie or doughnut chart that you want to enhance.</span></span> <span data-ttu-id="47e56-113">Выберите поле данных на диаграмме, а не всю диаграмму.</span><span class="sxs-lookup"><span data-stu-id="47e56-113">Select a data field in the chart, not the entire chart.</span></span>  
  
3.  <span data-ttu-id="47e56-114">На панели «Свойства» разверните узел **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="47e56-114">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="47e56-115">Для PieDrawingStyle выберите стиль из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="47e56-115">For PieDrawingStyle, select a style from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47e56-116">На одной диаграмме не могут применяться объемный и рельефный или приподнятый стили.</span><span class="sxs-lookup"><span data-stu-id="47e56-116">You can't have 3D and bevel or emboss styles on the same chart.</span></span> <span data-ttu-id="47e56-117">Если для диаграммы включен объемный стиль, свойство PieDrawingStyle не будет выводиться.</span><span class="sxs-lookup"><span data-stu-id="47e56-117">If you have enabled 3D for the chart, you will not see the PieDrawingStyle property.</span></span>  
  
 <span data-ttu-id="47e56-118">![Круговая диаграмма, нарисованная с применением вогнутых участков](../media/rs-piedrawingeffects-concave.gif "Круговая диаграмма, нарисованная с применением вогнутых участков")</span><span class="sxs-lookup"><span data-stu-id="47e56-118">![Pie chart with concave drawing style](../media/rs-piedrawingeffects-concave.gif "Pie chart with concave drawing style")</span></span>  
  
### <a name="to-add-texture-styles-to-a-bar-or-column-chart"></a><span data-ttu-id="47e56-119">Чтобы добавить стили текстуры к линейчатой диаграмме или гистограмме</span><span class="sxs-lookup"><span data-stu-id="47e56-119">To add texture styles to a bar or column chart</span></span>  
  
1.  <span data-ttu-id="47e56-120">Выберите линейчатую диаграмму или гистограмму, которую необходимо сделать более привлекательной.</span><span class="sxs-lookup"><span data-stu-id="47e56-120">Select the bar or column chart that you want to enhance.</span></span> <span data-ttu-id="47e56-121">Выберите поле данных на диаграмме, а не всю диаграмму.</span><span class="sxs-lookup"><span data-stu-id="47e56-121">Select a data field in the chart, not the entire chart.</span></span>  
  
2.  <span data-ttu-id="47e56-122">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="47e56-122">Open the Properties pane.</span></span>  
  
3.  <span data-ttu-id="47e56-123">Разверните узел **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="47e56-123">Expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="47e56-124">Для DrawingStyle выберите стиль из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="47e56-124">For DrawingStyle, select a style from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47e56-125">На одной диаграмме не могут применяться объемный и рельефный или приподнятый стили.</span><span class="sxs-lookup"><span data-stu-id="47e56-125">You can't have 3D and bevel or emboss styles on the same chart.</span></span> <span data-ttu-id="47e56-126">Если для диаграммы включен объемный стиль, свойство PieDrawingStyle не будет выводиться.</span><span class="sxs-lookup"><span data-stu-id="47e56-126">If you have enabled 3D for the chart, you will not see the PieDrawingStyle property.</span></span>  
  
 <span data-ttu-id="47e56-127">![Линейчатая диаграмма с градиентом от светлого к темному](../media/rs-bardrawingeffects-lighttodark.gif "Линейчатая диаграмма с градиентом от светлого к темному")</span><span class="sxs-lookup"><span data-stu-id="47e56-127">![Bar chart with LightToDark drawing effect](../media/rs-bardrawingeffects-lighttodark.gif "Bar chart with LightToDark drawing effect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47e56-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="47e56-128">See Also</span></span>  
 <span data-ttu-id="47e56-129">[Линейчатые диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47e56-129">[Bar Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="47e56-130">[Гистограммы (построитель отчетов и службы SSRS)](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47e56-130">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="47e56-131">[Круговые диаграммы (построитель отчетов и службы SSRS)](pie-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47e56-131">[Pie Charts &#40;Report Builder and SSRS&#41;](pie-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="47e56-132">Форматирование диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="47e56-132">Formatting a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-a-chart-report-builder-and-ssrs.md)  
  
  
