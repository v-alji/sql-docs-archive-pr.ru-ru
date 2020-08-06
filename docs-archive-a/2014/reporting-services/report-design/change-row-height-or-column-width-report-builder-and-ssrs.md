---
title: Изменение высоты строки или ширины столбца (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f061c204-5cd5-4467-9a9c-8a12803d93ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b5d75a8101d07d7d6e81c624d08cd951277936eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666433"
---
# <a name="change-row-height-or-column-width-report-builder-and-ssrs"></a><span data-ttu-id="c99ab-102">Изменение высоты строки или ширины столбца (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="c99ab-102">Change Row Height or Column Width (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c99ab-103">При установке высоты строк указывается максимальная высота строки в готовом для просмотра отчете.</span><span class="sxs-lookup"><span data-stu-id="c99ab-103">When you set a row height, you are specifying the maximum height for the row in the rendered report.</span></span> <span data-ttu-id="c99ab-104">Но по умолчанию текстовые поля в строке расширяются в вертикальном направлении, чтобы вместить все данные во время выполнения отчета, поэтому строка может расширяться по высоте за заданные пределы.</span><span class="sxs-lookup"><span data-stu-id="c99ab-104">However, by default, text boxes in the row are set to grow vertically to accommodate their data at run-time, and this can cause a row to expand beyond the height that you specify.</span></span> <span data-ttu-id="c99ab-105">Чтобы установить фиксированную высоту строки, необходимо изменить свойства текстового поля так, чтобы они не расширялись автоматически.</span><span class="sxs-lookup"><span data-stu-id="c99ab-105">To set a fixed row height, you must change the text box properties so they do not automatically expand.</span></span>  
  
 <span data-ttu-id="c99ab-106">При установке ширины столбца указывается максимальная ширина столбца в готовом для просмотра отчете.</span><span class="sxs-lookup"><span data-stu-id="c99ab-106">When you set a column width, you are specifying the maximum width for the column in the rendered report.</span></span> <span data-ttu-id="c99ab-107">Столбцы не расширяются горизонтально, чтобы вместить текст.</span><span class="sxs-lookup"><span data-stu-id="c99ab-107">Columns do not automatically adjust horizontally to accommodate text.</span></span>  
  
 <span data-ttu-id="c99ab-108">Если ячейка в строке или столбце содержит прямоугольник или область данных, минимальная высота и ширина ячейки определяется высотой содержащегося элемента.</span><span class="sxs-lookup"><span data-stu-id="c99ab-108">If a cell in a row or column contains a rectangle or data region, the minimum height and width of the cell is determined by the height and width of the contained item.</span></span> <span data-ttu-id="c99ab-109">Дополнительные сведения см. в разделе [Поведение при подготовке к просмотру (построитель отчетов и службы SSRS)](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c99ab-109">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-row-height-by-moving-row-handles"></a><span data-ttu-id="c99ab-110">Для изменения высоты строки перемещением маркеров строки</span><span class="sxs-lookup"><span data-stu-id="c99ab-110">To change row height by moving row handles</span></span>  
  
1.  <span data-ttu-id="c99ab-111">В режиме конструктора щелкните в любом месте области данных табликса, чтобы выделить ее.</span><span class="sxs-lookup"><span data-stu-id="c99ab-111">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="c99ab-112">На внешней границе области данных табликса появятся серые маркеры строк.</span><span class="sxs-lookup"><span data-stu-id="c99ab-112">Gray row handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="c99ab-113">Поместите указатель мыши на краю нужного маркера строки.</span><span class="sxs-lookup"><span data-stu-id="c99ab-113">Hover over the row handle edge that you want to expand.</span></span> <span data-ttu-id="c99ab-114">Появится двунаправленная стрелка.</span><span class="sxs-lookup"><span data-stu-id="c99ab-114">A double-headed arrow appears.</span></span>  
  
3.  <span data-ttu-id="c99ab-115">Щелкните, чтобы захватить край строки, и перетащите его выше или ниже на нужное расстояние.</span><span class="sxs-lookup"><span data-stu-id="c99ab-115">Click to grab the edge of the row and move it higher or lower to adjust the row height.</span></span>  
  
### <a name="to-change-row-height-by-setting-cell-properties"></a><span data-ttu-id="c99ab-116">Для изменения высоты строки настройкой параметров ячейки</span><span class="sxs-lookup"><span data-stu-id="c99ab-116">To change row height by setting cell properties</span></span>  
  
1.  <span data-ttu-id="c99ab-117">В режиме конструктора щелкните по ячейке в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="c99ab-117">In Design view, click a cell in the table row.</span></span>  
  
     <span data-ttu-id="c99ab-118">![Выделенная ячейка в таблице](../media/table-selectcell.png "Выделенная ячейка в таблице")</span><span class="sxs-lookup"><span data-stu-id="c99ab-118">![Selected Cell in a Table](../media/table-selectcell.png "Selected Cell in a Table")</span></span>  
  
2.  <span data-ttu-id="c99ab-119">На отображаемой вкладке **Свойства** , измените свойство **Высота** , а затем щелкните где-нибудь за пределами вкладки **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="c99ab-119">In the **Properties** pane that displays, modify the **Height** property, and then click anywhere outside the **Properties** pane.</span></span>  
  
     <span data-ttu-id="c99ab-120">![Панель свойств для выбранной ячейки таблицы](../media/cell-propertiespane.png "Панель свойств для выбранной ячейки таблицы")</span><span class="sxs-lookup"><span data-stu-id="c99ab-120">![Properties Pane for selected table cell](../media/cell-propertiespane.png "Properties Pane for selected table cell")</span></span>  
  
### <a name="to-prevent-a-row-from-automatically-expanding-vertically"></a><span data-ttu-id="c99ab-121">Отключение автоматического расширения строки по вертикали</span><span class="sxs-lookup"><span data-stu-id="c99ab-121">To prevent a row from automatically expanding vertically</span></span>  
  
1.  <span data-ttu-id="c99ab-122">В режиме конструктора щелкните в любом месте области данных табликса, чтобы выделить ее.</span><span class="sxs-lookup"><span data-stu-id="c99ab-122">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="c99ab-123">На внешней границе области данных табликса появятся серые маркеры строк.</span><span class="sxs-lookup"><span data-stu-id="c99ab-123">Gray row handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="c99ab-124">Щелкните маркер, чтобы выбрать строку.</span><span class="sxs-lookup"><span data-stu-id="c99ab-124">Click the row handle to select the row.</span></span>  
  
3.  <span data-ttu-id="c99ab-125">На панели "Свойства" присвойте параметру CanGrow значение **False**.</span><span class="sxs-lookup"><span data-stu-id="c99ab-125">In the Properties pane, set CanGrow to **False**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c99ab-126">Если панель "Свойства" не появилась, в меню **Вид** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c99ab-126">If you cannot see the Properties pane, from the **View** menu, click **Properties**.</span></span>  
  
### <a name="to-change-column-width"></a><span data-ttu-id="c99ab-127">Изменение ширины столбца</span><span class="sxs-lookup"><span data-stu-id="c99ab-127">To change column width</span></span>  
  
1.  <span data-ttu-id="c99ab-128">В режиме конструктора щелкните в любом месте области данных табликса, чтобы выделить ее.</span><span class="sxs-lookup"><span data-stu-id="c99ab-128">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="c99ab-129">На внешней границе области данных табликса появятся серые маркеры столбца.</span><span class="sxs-lookup"><span data-stu-id="c99ab-129">Gray column handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="c99ab-130">Поместите указатель мыши на краю нужного маркера столбца.</span><span class="sxs-lookup"><span data-stu-id="c99ab-130">Hover over the column handle edge that you want to expand.</span></span> <span data-ttu-id="c99ab-131">Появится двунаправленная стрелка.</span><span class="sxs-lookup"><span data-stu-id="c99ab-131">A double-headed arrow appears.</span></span>  
  
3.  <span data-ttu-id="c99ab-132">Щелкните, чтобы захватить край столбца, и перетащите его вправо или влево на нужное расстояние.</span><span class="sxs-lookup"><span data-stu-id="c99ab-132">Click to grab the edge of the column and move it left or right to adjust the column width.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c99ab-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="c99ab-133">See Also</span></span>  
 <span data-ttu-id="c99ab-134">[Область данных табликса &#40;построитель отчетов и SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c99ab-134">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c99ab-135">[Ячейки, строки и столбцы области данных табликса &#40;построитель отчетов&#41; и SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c99ab-135">[Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c99ab-136">[Таблицы &#40;построитель отчетов и службы SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c99ab-136">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c99ab-137">[Матрицы &#40;построитель отчетов и службы SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c99ab-137">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c99ab-138">[Содержит &#40;построитель отчетов и SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c99ab-138">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c99ab-139">Таблицы, матрицы и списки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="c99ab-139">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
