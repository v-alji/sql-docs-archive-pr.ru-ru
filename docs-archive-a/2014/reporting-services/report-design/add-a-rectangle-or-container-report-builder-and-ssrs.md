---
title: Добавление прямоугольника или контейнера (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10061"
- sql12.rtp.rptdesigner.rectangleproperties.general.f1
ms.assetid: f905c35f-754d-4d02-80f3-85e29ddda826
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5fddda2f02b9f370d9742ae6add5bae444f8f55f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654805"
---
# <a name="add-a-rectangle-or-container-report-builder-and-ssrs"></a><span data-ttu-id="2363b-102">Добавление прямоугольника или контейнера (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="2363b-102">Add a Rectangle or Container (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2363b-103">Прямоугольник добавляется к отчету, если нужно разделить различные области отчета с помощью графического элемента, выделить области отчета или установить фон для одного или нескольких элементов отчета.</span><span class="sxs-lookup"><span data-stu-id="2363b-103">Add a rectangle to your report when you want a graphical element to separate areas of the report, emphasize areas of a report, or provide a background for one or more report items.</span></span> <span data-ttu-id="2363b-104">Прямоугольники используются также в качестве контейнеров, помогающих управлять подготовкой к просмотру областей данных в отчете.</span><span class="sxs-lookup"><span data-stu-id="2363b-104">Rectangles are also used as containers to help control the way data regions render in a report.</span></span> <span data-ttu-id="2363b-105">Внешний вид прямоугольника можно настроить, изменяя его свойства, например цвета фона и границ.</span><span class="sxs-lookup"><span data-stu-id="2363b-105">You can customize the appearance of a rectangle by editing rectangle properties such as the background and border colors.</span></span> <span data-ttu-id="2363b-106">Дополнительные сведения об использовании прямоугольника как контейнера см. в разделах [Прямоугольники и линии (построитель отчетов и службы SSRS)](rectangles-and-lines-report-builder-and-ssrs.md) и [Отображение одних и тех же данных в матрице и на диаграмме (построитель отчетов)](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="2363b-106">For more information about using a rectangle as a container, see [Rectangles and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) and [Display the Same Data on a Matrix and a Chart &#40;Report Builder&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-rectangle"></a><span data-ttu-id="2363b-107">Добавление прямоугольника</span><span class="sxs-lookup"><span data-stu-id="2363b-107">To add a rectangle</span></span>  
  
1.  <span data-ttu-id="2363b-108">На вкладке **Вставка** в группе **Элементы отчета** щелкните **Прямоугольник**.</span><span class="sxs-lookup"><span data-stu-id="2363b-108">On the **Insert** tab, in the **Report Items** group, click **Rectangle.**</span></span>  
  
2.  <span data-ttu-id="2363b-109">В области конструктора щелкните место расположения верхнего левого угла прямоугольника и перетащите указатель мыши в место расположения нижнего правого угла.</span><span class="sxs-lookup"><span data-stu-id="2363b-109">On the design surface, click the location where you want the upper left corner of the rectangle, and drag to where you want the lower-right corner.</span></span>  
  
     <span data-ttu-id="2363b-110">Обратите внимание при движении курсора: в момент, когда курсор располагается на одной линии с другими объектами в области конструктора, появляются линии привязки.</span><span class="sxs-lookup"><span data-stu-id="2363b-110">Note that as you move the cursor, "snap lines" appear as the cursor lines up with other objects on the design surface.</span></span> <span data-ttu-id="2363b-111">Это облегчает выравнивание объектов.</span><span class="sxs-lookup"><span data-stu-id="2363b-111">These help you if you want objects to be aligned.</span></span>  
  
### <a name="to-create-a-container"></a><span data-ttu-id="2363b-112">Создание контейнера</span><span class="sxs-lookup"><span data-stu-id="2363b-112">To create a container</span></span>  
  
1.  <span data-ttu-id="2363b-113">Добавьте прямоугольный элемент отчета в отчет.</span><span class="sxs-lookup"><span data-stu-id="2363b-113">Add a rectangle report item to the report.</span></span>  
  
2.  <span data-ttu-id="2363b-114">Перетащите в прямоугольник другие элементы отчета.</span><span class="sxs-lookup"><span data-stu-id="2363b-114">Drag other report items into the rectangle.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2363b-115">Прямоугольник является всего лишь контейнером для элементов, которые создаются в прямоугольнике или перетаскиваются в него.</span><span class="sxs-lookup"><span data-stu-id="2363b-115">A rectangle is only a container for items that you either create in the rectangle or drag into the rectangle.</span></span> <span data-ttu-id="2363b-116">Если нарисовать прямоугольник вокруг элемента, уже существующего в области конструктора, прямоугольник не будет функционировать как его контейнер.</span><span class="sxs-lookup"><span data-stu-id="2363b-116">If you draw a rectangle around an item that already exists on the design surface, the rectangle will not act as its container.</span></span>  
  
### <a name="to-change-rectangle-properties-such-as-color-style-or-weight"></a><span data-ttu-id="2363b-117">Изменение свойств прямоугольника, таких как цвет, стиль или вес</span><span class="sxs-lookup"><span data-stu-id="2363b-117">To change rectangle properties such as color, style, or weight</span></span>  
  
1.  <span data-ttu-id="2363b-118">Выберите прямоугольник, а затем выберите параметры цвета, стиля или веса в разделе **Граница** вкладки «Корневая папка».</span><span class="sxs-lookup"><span data-stu-id="2363b-118">Select the rectangle, and then click the line color, style, or weight options in the **Border** section of the Home tab.</span></span>  
  
2.  <span data-ttu-id="2363b-119">Для задания того, какие стороны прямоугольника изменять, нажмите стрелку рядом с кнопкой **Граница** .</span><span class="sxs-lookup"><span data-stu-id="2363b-119">Click the arrow next to the **Border** button to determine which sides of the rectangle to change.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2363b-120">Если для стиля линии задано значение **Double** , а ширина линии — 1 1/2 пт или более, то при запуске отчета в построитель отчетов, конструктор отчетов или диспетчер отчетов строка может не отображаться двойной.</span><span class="sxs-lookup"><span data-stu-id="2363b-120">If you set the line style to **Double** and the line width is 1 1/2 pt or narrower, the line may not appear double when you run the report in Report Builder, Report Designer, or Report Manager.</span></span> <span data-ttu-id="2363b-121">После экспорта отчета в другие форматы, такие как Microsoft Word и Acrobat PDF, линия будет отображаться двойной.</span><span class="sxs-lookup"><span data-stu-id="2363b-121">It will appear double when you export the report to other formats such as Microsoft Word and Acrobat PDF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2363b-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="2363b-122">See Also</span></span>  
 <span data-ttu-id="2363b-123">[Прямоугольники и линии (построитель отчетов и службы SSRS)](rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2363b-123">[Rectangles and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2363b-124">Поведение при подготовке к просмотру (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="2363b-124">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
