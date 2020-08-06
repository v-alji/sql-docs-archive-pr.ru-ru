---
title: Вставка или удаление строки (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b9642af3-b3ae-4f78-b0be-8f96b79fc313
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fdec24801d1fae3b95c7d75acb5a3add650d523b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739293"
---
# <a name="insert-or-delete-a-row-report-builder-and-ssrs"></a><span data-ttu-id="c570a-102">Вставка или удаление строки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="c570a-102">Insert or Delete a Row (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c570a-103">Добавить или удалить строки можно в области данных табликса.</span><span class="sxs-lookup"><span data-stu-id="c570a-103">You can add or delete rows in a tablix data region.</span></span> <span data-ttu-id="c570a-104">Областью данных табликса может быть таблица, матрица или список.</span><span class="sxs-lookup"><span data-stu-id="c570a-104">The tablix data region can be a table, a matrix, or a list.</span></span> <span data-ttu-id="c570a-105">Следующие процедуры не применяются к области данных диаграммы и датчика.</span><span class="sxs-lookup"><span data-stu-id="c570a-105">The following procedures do not apply to the chart and gauge data regions.</span></span>  
  
 <span data-ttu-id="c570a-106">В области данных табликса можно добавлять строки, связанные с группой (внутри группы) или не связанные с группой (вне группы).</span><span class="sxs-lookup"><span data-stu-id="c570a-106">In a tablix data region, you can add rows that are associated with a group (inside a group) or that are not associated with a group (outside a group).</span></span> <span data-ttu-id="c570a-107">Строка, находящаяся внутри группы, повторяется один раз для уникального значения группы.</span><span class="sxs-lookup"><span data-stu-id="c570a-107">A row that is inside a group repeats once per unique group value.</span></span> <span data-ttu-id="c570a-108">Например, строка в группе, основанной на значении столбца данных и содержащей имена цветов, повторяется один раз для каждого отдельного имени цвета.</span><span class="sxs-lookup"><span data-stu-id="c570a-108">For example, a row inside a group based on the value in a data column that contains color names, repeats once per distinct color name.</span></span> <span data-ttu-id="c570a-109">Что касается вложенных групп, то строка может находиться вне дочерней группы, но должна находиться в родительской группе.</span><span class="sxs-lookup"><span data-stu-id="c570a-109">For nested groups, a row can be outside the child group but inside the parent group.</span></span> <span data-ttu-id="c570a-110">В этом случае строка повторяется один раз для каждого уникального значения в родительской группе.</span><span class="sxs-lookup"><span data-stu-id="c570a-110">In this case, the row repeats once for each unique value in the parent group.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-select-a-data-region-so-the-row-and-column-handles-appear"></a><span data-ttu-id="c570a-111">Выделение области данных с целью отображения маркеров строки и столбца</span><span class="sxs-lookup"><span data-stu-id="c570a-111">To select a data region so the row and column handles appear</span></span>  
  
-   <span data-ttu-id="c570a-112">В конструкторе щелкните левый верхний угол области данных табликса, чтобы поверх и рядом с ней появились маркеры столбца и строки.</span><span class="sxs-lookup"><span data-stu-id="c570a-112">In Design view, click the upper left corner of the tablix data region so that column and row handles appear above and next to it.</span></span>  
  
     <span data-ttu-id="c570a-113">Дополнительные сведения об областях области данных см. в разделе [lists &#40;построитель отчетов and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c570a-113">For more information about data region areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-insert-a-row-in-a-selected-data-region"></a><span data-ttu-id="c570a-114">Вставка строки в выделенную область данных</span><span class="sxs-lookup"><span data-stu-id="c570a-114">To insert a row in a selected data region</span></span>  
  
-   <span data-ttu-id="c570a-115">Щелкните правой кнопкой мыши маркер строки, куда нужно вставить строку, выберите команду **Вставить строку**, а затем выберите **Выше** или **Ниже**.</span><span class="sxs-lookup"><span data-stu-id="c570a-115">Right-click a row handle where you want to insert a row, click **Insert Row**, and then click **Above** or **Below**.</span></span>  
  
     <span data-ttu-id="c570a-116">\- или -</span><span class="sxs-lookup"><span data-stu-id="c570a-116">\- or -</span></span>  
  
-   <span data-ttu-id="c570a-117">Щелкните правой кнопкой мыши ячейку области данных, куда нужно вставить строку, выберите команду **Вставить строку**, а затем выберите **Выше** или **Ниже**.</span><span class="sxs-lookup"><span data-stu-id="c570a-117">Right-click a cell in the data region where you want to insert a row, click **Insert Row**, and then click **Above** or **Below**.</span></span>  
  
### <a name="to-delete-a-row-from-a-selected-data-region"></a><span data-ttu-id="c570a-118">Удаление строки из выделенной области данных</span><span class="sxs-lookup"><span data-stu-id="c570a-118">To delete a row from a selected data region</span></span>  
  
-   <span data-ttu-id="c570a-119">Выберите строку или строки, которые нужно удалить, щелкните правой кнопкой мыши маркер одной из выбранных строк и выберите команду **Удалить строки**.</span><span class="sxs-lookup"><span data-stu-id="c570a-119">Select the row or rows that you want to delete, right-click the handle for one of the rows you selected, and then click **Delete Rows**.</span></span>  
  
     <span data-ttu-id="c570a-120">\- или -</span><span class="sxs-lookup"><span data-stu-id="c570a-120">\- or -</span></span>  
  
-   <span data-ttu-id="c570a-121">Щелкните правой кнопкой мыши ячейку области данных, где нужно удалить строку, и выберите команду **Удалить строки**.</span><span class="sxs-lookup"><span data-stu-id="c570a-121">Right-click a cell in the data region where you want to delete a row, and then click **Delete Rows**.</span></span>  
  
### <a name="to-insert-a-row-in-a-group-in-a-selected-data-region"></a><span data-ttu-id="c570a-122">Вставка строки в группу в выделенной области данных</span><span class="sxs-lookup"><span data-stu-id="c570a-122">To insert a row in a group in a selected data region</span></span>  
  
-   <span data-ttu-id="c570a-123">Щелкните правой кнопкой мыши ячейку группы строк в области группы строк в области данных табликса там, где нужно вставить строку, выберите команду **Вставить строку**и выберите **Выше — снаружи группы**, **Выше — внутри группы**, **Ниже — внутри группы**или **Ниже — снаружи группы**.</span><span class="sxs-lookup"><span data-stu-id="c570a-123">Right-click a row group cell in the row group area of a tablix data region where you want to insert a row, click **Insert Row**, and then click **Above - Outside Group**, **Above - Inside Group**, **Below - Inside Group**, or **Below - Outside Group**.</span></span>  
  
     <span data-ttu-id="c570a-124">Строка добавится внутри или снаружи группы, представленной выбранной ячейкой группы строк.</span><span class="sxs-lookup"><span data-stu-id="c570a-124">A row is added either inside or outside the group represented by the row group cell you clicked on.</span></span>  
  
### <a name="to-delete-a-row-from-a-group-in-a-selected-data-region"></a><span data-ttu-id="c570a-125">Удаление строки из группы в выделенной области данных</span><span class="sxs-lookup"><span data-stu-id="c570a-125">To delete a row from a group in a selected data region</span></span>  
  
-   <span data-ttu-id="c570a-126">Щелкните правой кнопкой мыши ячейку группы строк в области данных табликса там, где нужно удалить строку, и выберите команду **Удалить строки**.</span><span class="sxs-lookup"><span data-stu-id="c570a-126">Right-click a row group cell in the row group area of a tablix data region where you want to delete a row, and then click **Delete Rows**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c570a-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="c570a-127">See Also</span></span>  
 <span data-ttu-id="c570a-128">[Область данных табликса (построитель отчетов и службы SSRS)](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c570a-128">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c570a-129">[Основные сведения о группах (построитель отчетов и службы SSRS)](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c570a-129">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c570a-130">[Таблицы &#40;построитель отчетов и службы SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c570a-130">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c570a-131">[Матрицы &#40;построитель отчетов и службы SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c570a-131">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c570a-132">[Списки &#40;построитель отчетов и службы SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c570a-132">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c570a-133">Списки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="c570a-133">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
