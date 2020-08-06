---
title: Добавление рамки границы в диаграмму (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ca0c5040-40bb-4cb7-bc2b-5bcbe73858bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4c91d3de00caa4eab6ed1894042b2214b7dcf4b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739386"
---
# <a name="add-a-border-frame-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="d24dd-102">Добавление границы рамки в диаграмму (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d24dd-102">Add a Border Frame to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d24dd-103">Чтобы улучшить визуальное восприятие диаграммы, можно использовать границы рамки.</span><span class="sxs-lookup"><span data-stu-id="d24dd-103">To give a chart more visual impact, consider using a border frame around the outside of the chart.</span></span> <span data-ttu-id="d24dd-104">Границу рамки можно выбрать в диалоговом окне **Свойства диаграммы** или в панели свойств.</span><span class="sxs-lookup"><span data-stu-id="d24dd-104">You can select a border frame by using the **Chart Properties** dialog box or by using the Properties pane.</span></span> <span data-ttu-id="d24dd-105">Границы рамки диаграммы нельзя применить ни к какой другой области данных.</span><span class="sxs-lookup"><span data-stu-id="d24dd-105">The chart border frames cannot be applied to any other data region.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-apply-a-border-to-a-chart"></a><span data-ttu-id="d24dd-106">Выбор границы рамки для диаграммы</span><span class="sxs-lookup"><span data-stu-id="d24dd-106">To apply a border to a chart</span></span>  
  
1.  <span data-ttu-id="d24dd-107">Щелкните правой кнопкой мыши любое место диаграммы и выберите пункт **Свойства диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="d24dd-107">Right-click anywhere on the chart and select **Chart Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d24dd-108">Если диалоговое окно **Свойства диаграммы**не появилось, в контекстном меню наведите указатель на элемент **Диаграмма** и выберите пункт **Свойства диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="d24dd-108">If you do not see the **Chart Properties**, point to **Chart** on the shortcut menu and select **Chart Properties**.</span></span>  
  
2.  <span data-ttu-id="d24dd-109">Выберите **Границы**и щелкните нужный тип границы диаграммы.</span><span class="sxs-lookup"><span data-stu-id="d24dd-109">Select **Border**, and click the type of border to apply to the chart.</span></span>  
  
3.  <span data-ttu-id="d24dd-110">Выберите значение или введите выражение, задающее стиль границы (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d24dd-110">(Optional) Select a value or type an expression that represents the style of the border.</span></span>  
  
4.  <span data-ttu-id="d24dd-111">Укажите цвет линии, которая будет нарисована вокруг диаграммы в качестве границы (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d24dd-111">(Optional) Specify the color of the line that will be drawn around the chart as the border.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d24dd-112">Список **Цвет линии** содержит распространенные цвета.</span><span class="sxs-lookup"><span data-stu-id="d24dd-112">The **Line color** list contains common colors.</span></span> <span data-ttu-id="d24dd-113">Чтобы выбрать цвет из более обширного списка, выберите пункт списка **Дополнительные цвета** или нажмите кнопку выражений (**fx**) рядом со списком, чтобы вывести редактор **выражений** .</span><span class="sxs-lookup"><span data-stu-id="d24dd-113">If you want to select from a list of more colors, click **More colors** in the list or click the expression (**fx**) button next to the list to bring up the **Expression** editor.</span></span>  
  
5.  <span data-ttu-id="d24dd-114">Укажите ширину границы (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d24dd-114">(Optional) Specify the width of the border.</span></span> <span data-ttu-id="d24dd-115">Допустимыми являются значения от 0,25 пункта до 20 пунктов.</span><span class="sxs-lookup"><span data-stu-id="d24dd-115">Valid values are between 0.25pt and 20pt.</span></span> <span data-ttu-id="d24dd-116">Для наилучшего эффекта рекомендуется использовать границы шириной от 1 до 3 пунктов.</span><span class="sxs-lookup"><span data-stu-id="d24dd-116">Consider keeping the size of your border to between 1 and 3pt for the best visual effect.</span></span>  
  
6.  <span data-ttu-id="d24dd-117">Если в отчете используется цвет фона, отличный от белого, можно определить цвет страницы, совпадающий с цветом фона (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d24dd-117">(Optional) If your report contains a background color other than white, consider defining a page color that is the same color.</span></span> <span data-ttu-id="d24dd-118">Цвет страницы — это цвет фона за пределами линии границы.</span><span class="sxs-lookup"><span data-stu-id="d24dd-118">The page color is the background color outside of the border line.</span></span>  
  
7.  <span data-ttu-id="d24dd-119">Если выбран тип «Рамка», укажите стиль и цвет рамки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d24dd-119">(Optional) If you choose a Frame type, specify a style and color for the frame.</span></span> <span data-ttu-id="d24dd-120">Список **Цвет заливки рамки** содержит распространенные цвета.</span><span class="sxs-lookup"><span data-stu-id="d24dd-120">The **Frame fill color** list contains common colors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d24dd-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="d24dd-121">See Also</span></span>  
 <span data-ttu-id="d24dd-122">[Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d24dd-122">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d24dd-123">[Форматирование диаграммы (построитель отчетов и службы SSRS)](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d24dd-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d24dd-124">Добавление в диаграмму стилей рельефа, приподнятости и текстуры &#40;построитель отчетов и службы SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d24dd-124">Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
