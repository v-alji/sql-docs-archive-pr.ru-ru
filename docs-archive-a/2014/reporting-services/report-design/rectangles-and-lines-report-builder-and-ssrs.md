---
title: Прямоугольники и линии (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d6226b0c-0398-4185-8565-96099876fc21
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 96b795c3edeabb938e836be3486e28e08737a8e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667569"
---
# <a name="rectangles-and-lines-report-builder-and-ssrs"></a><span data-ttu-id="cfbfd-102">Прямоугольники и линии (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="cfbfd-102">Rectangles and Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cfbfd-103">Для создания визуальных эффектов в отчете можно использовать прямоугольники и линии.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-103">Rectangles and lines can create visual effects within a report.</span></span> <span data-ttu-id="cfbfd-104">Свойства отображения этих элементов отчета можно задать в разделе «Граница» вкладки «Главная», а другие свойства — с помощью панели «Свойства».</span><span class="sxs-lookup"><span data-stu-id="cfbfd-104">You can set display properties on these report items from the Border section of the Home tab, and set other properties by using the Properties pane.</span></span> <span data-ttu-id="cfbfd-105">Для прямоугольника можно добавлять такие характеристики, как цвет фона, изображение, подсказка или закладка.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-105">You can add features like a background color or image, a tooltip, or a bookmark to a rectangle.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="rectangles-and-lines-as-report-parts"></a><a name="RectanglesLinesReportParts"></a> <span data-ttu-id="cfbfd-106">Использование прямоугольников и линий в качестве элементов отчета</span><span class="sxs-lookup"><span data-stu-id="cfbfd-106">Rectangles and Lines as Report Parts</span></span>  
 <span data-ttu-id="cfbfd-107">Прямоугольники вместе с их содержимым можно опубликовать отдельно от отчета как элементы отчета.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-107">You can publish rectangles with the items that they contain separately from the report as report parts.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
 <span data-ttu-id="cfbfd-108">При этом нельзя публиковать как части отчета элементы отчета, содержащиеся в прямоугольнике.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-108">You cannot publish the report items within the rectangle as report parts.</span></span> <span data-ttu-id="cfbfd-109">При добавлении пользователями прямоугольников к отчету выполняется добавление и прямоугольника, и содержащихся в нем элементов.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-109">When people add the rectangle to a report, they get the rectangle and the items it contains.</span></span>  
  

  
##  <a name="using-a-rectangle-as-a-container"></a><a name="RectangleAsContainer"></a><span data-ttu-id="cfbfd-110">Использование прямоугольника в качестве контейнера</span><span class="sxs-lookup"><span data-stu-id="cfbfd-110">Using a Rectangle as a Container</span></span>  
 <span data-ttu-id="cfbfd-111">Прямоугольник можно использовать в качестве контейнера для других элементов.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-111">You can use a rectangle as a container for other items.</span></span> <span data-ttu-id="cfbfd-112">При перемещении прямоугольника элементы внутри него перемещаются вместе с ним.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-112">When you move the rectangle, the items that are contained within the rectangle move along with it.</span></span> <span data-ttu-id="cfbfd-113">Элемент внутри прямоугольника отображает его имя в свойстве **Parent** .</span><span class="sxs-lookup"><span data-stu-id="cfbfd-113">An item within the rectangle shows the name of the rectangle in its **Parent** property.</span></span> <span data-ttu-id="cfbfd-114">Дополнительные сведения об использовании прямоугольника как контейнера см. в разделах [Добавление прямоугольника или контейнера (построитель отчетов и службы SSRS)](add-a-rectangle-or-container-report-builder-and-ssrs.md) и [Отображение одних и тех же данных в матрице и на диаграмме (построитель отчетов)](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="cfbfd-114">For more information about using a rectangle as a container, see [Add a Rectangle or Container &#40;Report Builder and SSRS&#41;](add-a-rectangle-or-container-report-builder-and-ssrs.md) and [Display the Same Data on a Matrix and a Chart &#40;Report Builder&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfbfd-115">Прямоугольник является всего лишь контейнером для элементов, которые создаются в прямоугольнике или перетаскиваются в него.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-115">A rectangle is only a container for items that you either create in the rectangle or drag into the rectangle.</span></span> <span data-ttu-id="cfbfd-116">Если нарисовать прямоугольник вокруг элемента, уже существующего в области конструктора, прямоугольник не будет функционировать как его контейнер.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-116">If you draw a rectangle around an item that already exists on the design surface, the rectangle will not act as its container.</span></span> <span data-ttu-id="cfbfd-117">Прямоугольник будет отсутствовать в свойстве Parent этого элемента.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-117">The rectangle will not be listed in the item's Parent property.</span></span>  
  
 <span data-ttu-id="cfbfd-118">При помещении элементов отчета в прямоугольники необходимо учесть, какие изменения повлияют на эти элементы при подготовке отчета.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-118">When using rectangles to contain report items, consider how the items will be affected as a whole during report rendering.</span></span> <span data-ttu-id="cfbfd-119">Элементы отчета, которые содержат повторяющиеся строки данных (например, таблицы) развернутся таким образом, чтобы разместить все возвращенные запросом данные, и это повлияет на расположение других элементов в прямоугольнике.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-119">Report items that contain repeated rows of data (for example, tables) will expand to accommodate the data that is returned by a query, and this affects the positioning of other items in the rectangle.</span></span> <span data-ttu-id="cfbfd-120">Таблица передвинет вниз элементы, расположенные ниже области данных.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-120">A table will push items down if they are positioned below the data region.</span></span> <span data-ttu-id="cfbfd-121">Чтобы привязать элемент к месту, можно расположить элемент отчета внутри прямоугольника, верхний край которого находится выше нижнего края таблицы.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-121">To anchor an item in place, you can place the report item inside of a rectangle that has an upper edge above the lower edge of the table.</span></span> <span data-ttu-id="cfbfd-122">Дополнительные сведения см. в разделе [Поведение при подготовке к просмотру (построитель отчетов и службы SSRS)](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cfbfd-122">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="adding-a-report-border"></a><a name="ReportBorder"></a> <span data-ttu-id="cfbfd-123">Добавление границы отчета</span><span class="sxs-lookup"><span data-stu-id="cfbfd-123">Adding a Report Border</span></span>  
 <span data-ttu-id="cfbfd-124">Можно добавить границу к отчету путем добавления границ к самим верхним колонтитулам, нижним колонтитулам и тексту отчета, не добавляя линии или прямоугольники.</span><span class="sxs-lookup"><span data-stu-id="cfbfd-124">You can add a border to a report by adding borders to the headers, footers, and report body themselves, without adding lines or rectangles.</span></span> <span data-ttu-id="cfbfd-125">Дополнительные сведения см. в разделе [Добавление границы в отчет (построитель отчетов и службы SSRS)](add-a-border-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cfbfd-125">For more information, see [Add a Border to a Report &#40;Report Builder and SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="cfbfd-126">Разделы руководства</span><span class="sxs-lookup"><span data-stu-id="cfbfd-126">How-To Topics</span></span>  
 [<span data-ttu-id="cfbfd-127">Добавление границы в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="cfbfd-127">Add a Border to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-border-to-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="cfbfd-128">Добавление прямоугольника или контейнера (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="cfbfd-128">Add a Rectangle or Container &#40;Report Builder and SSRS&#41;</span></span>](add-a-rectangle-or-container-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="cfbfd-129">Добавление и изменение линии (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="cfbfd-129">Add and Modify a Line &#40;Report Builder and SSRS&#41;</span></span>](add-and-modify-a-line-report-builder-and-ssrs.md)  
  
## <a name="see-also"></a><span data-ttu-id="cfbfd-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="cfbfd-130">See Also</span></span>  
 [<span data-ttu-id="cfbfd-131">Добавление прямоугольника или контейнера (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="cfbfd-131">Add a Rectangle or Container &#40;Report Builder and SSRS&#41;</span></span>](add-a-rectangle-or-container-report-builder-and-ssrs.md)  
  
  
