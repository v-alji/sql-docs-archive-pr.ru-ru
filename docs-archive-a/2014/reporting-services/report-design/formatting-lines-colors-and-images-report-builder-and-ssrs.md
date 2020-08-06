---
title: Форматирование линий, цветов и изображений (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.textboxproperties.border.f1
- "10502"
- "10094"
- sql12.rtp.rptdesigner.pictureproperties.border.f1
- "10063"
- sql12.rtp.rptdesigner.rectangleproperties.border.f1
- "10055"
- sql12.rtp.rptdesigner.subreportproperties.border.f1
- "10126"
- sql12.rtp.rptdesigner.shared.borderdv.f1
- "10066"
- sql12.rtp.rptdesigner.reportbody.border.f1
ms.assetid: 0f5f0d2a-9537-4152-b441-b40d7f04cf4c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 681ff6b46f692804aef5c7cbbc16e5abe99dbb2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728018"
---
# <a name="formatting-lines-colors-and-images-report-builder-and-ssrs"></a><span data-ttu-id="238bb-102">Форматирование линий, цветов и изображений (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="238bb-102">Formatting Lines, Colors, and Images (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="238bb-103">позволяют форматировать линии, цвета, области данных, изображения и другие элементы отчета.</span><span class="sxs-lookup"><span data-stu-id="238bb-103">gives you the ability to format lines, colors, data regions, images, and other report items.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="borders-lines-and-gridlines"></a><span data-ttu-id="238bb-104">Границы, линии и сетки</span><span class="sxs-lookup"><span data-stu-id="238bb-104">Borders, Lines and Gridlines</span></span>  
 <span data-ttu-id="238bb-105">Границы, линии и сетки визуально связывают элементы на странице, облегчая чтение содержимого отчета.</span><span class="sxs-lookup"><span data-stu-id="238bb-105">Borders, lines, and gridlines can visually tie items together on the page and help your report readers easily read the contents of the report.</span></span> <span data-ttu-id="238bb-106">При помощи стандартных стилей границы можно быстро добавить границу вокруг текстового поля, группы текстовых полей или изображения.</span><span class="sxs-lookup"><span data-stu-id="238bb-106">Using the predefined border styles, you can quickly add a border around a text box, a group of text boxes, or an image.</span></span> <span data-ttu-id="238bb-107">Кроме того, можно изменить стиль, ширину и цвет границ, линий и сеток.</span><span class="sxs-lookup"><span data-stu-id="238bb-107">In addition, you can change the style, width, and color for the borders, lines, and gridlines.</span></span> <span data-ttu-id="238bb-108">Границы добавляются вокруг всего выделенного элемента или вдоль края элемента, например, вдоль нижнего края текстового поля.</span><span class="sxs-lookup"><span data-stu-id="238bb-108">Borders are added around the entire item selected or around a border along an edge of the item, for example, a border along the bottom of a text box.</span></span>  
  
 <span data-ttu-id="238bb-109">Для форматирования внутренних и внешних границ текстового поля, макета отчета или границ вокруг изображения используется вкладка **Граница** диалогового окна элемента отчета **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="238bb-109">To format borders and gridlines in a text box, report layout, or around an image, use the **Border** tab of the report item's **Properties** dialog box.</span></span> <span data-ttu-id="238bb-110">Например, если нужно добавить границу вокруг изображения, щелкните его правой кнопкой мыши и в диалоговом окне **Свойства изображения** перейдите на вкладку **Граница**.</span><span class="sxs-lookup"><span data-stu-id="238bb-110">For example, if you want to add a border around an image, right-click the image and then in the **Image Properties** dialog box, click **Border**.</span></span>  
  
 <span data-ttu-id="238bb-111">Дополнительно к стандартным, к диаграммам можно применить дополнительные границы.</span><span class="sxs-lookup"><span data-stu-id="238bb-111">In addition to the standard border frames, additional border frames can be applied to charts.</span></span> <span data-ttu-id="238bb-112">Дополнительные сведения см. в разделе [Добавление границы рамки в диаграмму (построитель отчетов и службы SSRS)](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="238bb-112">For more information, see [Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="238bb-113">Границу можно также добавить в сам отчет.</span><span class="sxs-lookup"><span data-stu-id="238bb-113">You can also add a border to the report itself.</span></span> <span data-ttu-id="238bb-114">Дополнительные сведения см. в разделе [Добавление границы в отчет (построитель отчетов и службы SSRS)](add-a-border-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="238bb-114">For more information, see [Add a Border to a Report &#40;Report Builder and SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
## <a name="applying-background-colors"></a><span data-ttu-id="238bb-115">Применение цветов фона</span><span class="sxs-lookup"><span data-stu-id="238bb-115">Applying Background Colors</span></span>  
 <span data-ttu-id="238bb-116">Можно задать сплошной цвет фона для всего отчета, текстового поля в отчете или для ячейки или группы ячеек в области данных.</span><span class="sxs-lookup"><span data-stu-id="238bb-116">A solid color can be added to the background of the entire report, a text box within the report, or to a cell or group of cells within a data region.</span></span> <span data-ttu-id="238bb-117">По умолчанию цвет фона является белым, однако его можно изменить на вкладке **Заливка** диалогового окна элемента отчета **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="238bb-117">By default, the background color is white; however, you can select a color from the **Fill** tab of the report item's **Properties** dialog box.</span></span> <span data-ttu-id="238bb-118">Например, если нужно изменить цвет фона текстового поля, щелкните правой кнопкой мыши текстовое поле и выберите **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="238bb-118">For example, if you want to change the background color of a text box, right-click the text box and select **Text Box Properties**.</span></span> <span data-ttu-id="238bb-119">Щелкните **Заливка** и выберите нужный цвет.</span><span class="sxs-lookup"><span data-stu-id="238bb-119">Click **Fill** and then select the color you want.</span></span> <span data-ttu-id="238bb-120">В этом диалоговом окне можно выбрать цвет фона для выделенного элемента или добавить фоновое изображение.</span><span class="sxs-lookup"><span data-stu-id="238bb-120">In this dialog box, you can select a background color for the selected item or you can add an image that appears in the background.</span></span>  
  
 <span data-ttu-id="238bb-121">Для диаграммы можно также указать градиенты и стили узора для фоновых цветов.</span><span class="sxs-lookup"><span data-stu-id="238bb-121">When you use the chart, you can also specify gradients and pattern styles for background colors.</span></span> <span data-ttu-id="238bb-122">Дополнительные сведения см. в разделе [Форматирование диаграммы (построитель отчетов и службы SSRS)](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="238bb-122">For more information, see [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="using-images-as-formatting"></a><span data-ttu-id="238bb-123">Использование изображений в качестве форматирования</span><span class="sxs-lookup"><span data-stu-id="238bb-123">Using Images as Formatting</span></span>  
 <span data-ttu-id="238bb-124">К области данных можно добавлять поля, содержащие изображения.</span><span class="sxs-lookup"><span data-stu-id="238bb-124">Fields that contain images can be added to a data region.</span></span> <span data-ttu-id="238bb-125">Если используются поля с изображениями, то изображения появляются в отчете при его запуске.</span><span class="sxs-lookup"><span data-stu-id="238bb-125">If you use an image field, the images appear in the report with the report is run.</span></span>  
  
 <span data-ttu-id="238bb-126">Можно также добавлять изображения, например логотипы, к фону отчета или в прямоугольник, текстовое поле, таблицу, матрицу или другие части диаграммы либо к тексту и страницам отчета.</span><span class="sxs-lookup"><span data-stu-id="238bb-126">You can also add images such as logos to the background of your report or to a rectangle, text box, table, matrix, or some parts of a chart, or to the body and page sections of a report.</span></span> <span data-ttu-id="238bb-127">Дополнительные сведения см. в разделе [Изображения (построитель отчетов и службы SSRS)](images-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="238bb-127">For more information, see [Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238bb-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="238bb-128">See Also</span></span>  
 <span data-ttu-id="238bb-129">[Форматирование текста и заполнителей (построитель отчетов и службы SSRS)](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="238bb-129">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="238bb-130">[Форматирование чисел и дат (построитель отчетов и службы SSRS)](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="238bb-130">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="238bb-131">[Форматирование текста в текстовом поле (построитель отчетов и службы SSRS)](format-text-in-a-text-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="238bb-131">[Format Text in a Text Box &#40;Report Builder and SSRS&#41;](format-text-in-a-text-box-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="238bb-132">Диалоговое окно "Заливка" (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="238bb-132">Fill Dialog Box &#40;Report Builder and SSRS&#41;</span></span>](../fill-dialog-box-report-builder-and-ssrs.md)  
  
  
