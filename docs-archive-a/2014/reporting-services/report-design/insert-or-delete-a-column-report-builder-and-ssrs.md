---
title: Вставка или удаление столбца (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e9db79e2-7e7d-4359-a706-cb746c94182a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9a6f782dbb6cc1024583926aafe4bab1cfe2d042
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739302"
---
# <a name="insert-or-delete-a-column-report-builder-and-ssrs"></a><span data-ttu-id="72e05-102">Вставка или удаление столбца (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="72e05-102">Insert or Delete a Column (Report Builder and SSRS)</span></span>
  <span data-ttu-id="72e05-103">Добавить или удалить столбцы можно в области данных табликса.</span><span class="sxs-lookup"><span data-stu-id="72e05-103">You can add or delete columns in a tablix data region.</span></span> <span data-ttu-id="72e05-104">Областью данных табликса может быть таблица, матрица или список.</span><span class="sxs-lookup"><span data-stu-id="72e05-104">The tablix data region can be a table, a matrix, or a list.</span></span> <span data-ttu-id="72e05-105">Следующие процедуры не применяются к области данных диаграммы и датчика.</span><span class="sxs-lookup"><span data-stu-id="72e05-105">The following procedures do not apply to the chart and gauge data regions.</span></span>  
  
 <span data-ttu-id="72e05-106">В области данных табликса можно добавлять столбцы, связанные с группой (внутри группы) или не связанные с группой (вне группы).</span><span class="sxs-lookup"><span data-stu-id="72e05-106">In a tablix data region, you can add columns that are associated with a group (inside a group) or that are not associated with a group (outside a group).</span></span> <span data-ttu-id="72e05-107">Столбец, находящийся внутри группы, повторяется один раз для уникального значения группы.</span><span class="sxs-lookup"><span data-stu-id="72e05-107">A column that is inside a group repeats once per unique group value.</span></span> <span data-ttu-id="72e05-108">Например, столбец в группе, основанной на значении столбца данных и содержащей имена цветов, повторяется один раз для каждого отдельного имени цвета.</span><span class="sxs-lookup"><span data-stu-id="72e05-108">For example, a column inside a group based the value in a data column that contains color names, repeats once per distinct color name.</span></span> <span data-ttu-id="72e05-109">Что касается вложенных групп, то столбец может находиться вне дочерней группы, но должен находиться в родительской группе.</span><span class="sxs-lookup"><span data-stu-id="72e05-109">For nested groups, a column can be outside the child group but inside the parent group.</span></span> <span data-ttu-id="72e05-110">В этом случае строка повторяется один раз для каждого уникального значения в родительской группе.</span><span class="sxs-lookup"><span data-stu-id="72e05-110">In this case, the row repeats once for each unique value in the parent group.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-select-a-data-region-so-that-the-row-and-column-handles-appear"></a><span data-ttu-id="72e05-111">Выделение области данных с целью отображения маркеров строки и столбца</span><span class="sxs-lookup"><span data-stu-id="72e05-111">To select a data region so that the row and column handles appear</span></span>  
  
-   <span data-ttu-id="72e05-112">В конструкторе щелкните левый верхний угол области данных табликса, чтобы поверх и рядом с ней появились маркеры столбца и строки.</span><span class="sxs-lookup"><span data-stu-id="72e05-112">In Design view, click the upper left corner of the tablix data region, so that column and row handles appear above and next to it.</span></span>  
  
     <span data-ttu-id="72e05-113">Дополнительные сведения об областях области данных см. в разделе [lists &#40;построитель отчетов and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="72e05-113">For more information about data region areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-insert-a-column-in-a-selected-data-region"></a><span data-ttu-id="72e05-114">Вставка столбца в выделенную область данных</span><span class="sxs-lookup"><span data-stu-id="72e05-114">To insert a column in a selected data region</span></span>  
  
-   <span data-ttu-id="72e05-115">Щелкните правой кнопкой мыши маркер там, где нужно вставить столбец, выберите команду **Вставить столбец**и укажите **Слева** или **Справа**.</span><span class="sxs-lookup"><span data-stu-id="72e05-115">Right-click a column handle where you want to insert a column, click **Insert Column**, and then click **Left** or **Right**.</span></span>  
  
     <span data-ttu-id="72e05-116">-- или --</span><span class="sxs-lookup"><span data-stu-id="72e05-116">-- or --</span></span>  
  
-   <span data-ttu-id="72e05-117">Щелкните правой кнопкой мыши ячейку области данных там, где нужно вставить столбец, выберите команду **Вставить столбец**и укажите **Слева** или **Справа**.</span><span class="sxs-lookup"><span data-stu-id="72e05-117">Right-click a cell in the data region where you want to insert a row, click **Insert Column**, and then click **Left** or **Right**.</span></span>  
  
### <a name="to-delete-a-column-from-a-selected-data-region"></a><span data-ttu-id="72e05-118">Удаление столбца из выделенной области данных</span><span class="sxs-lookup"><span data-stu-id="72e05-118">To delete a column from a selected data region</span></span>  
  
-   <span data-ttu-id="72e05-119">Выделите один или несколько столбцов, которые нужно удалить, щелкните правой кнопкой мыши маркер одного из выделенных столбцов и выберите команду **Удалить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="72e05-119">Select the column or columns that you want to delete, right-click the handle for one of the columns you selected, and then click **Delete Columns**.</span></span>  
  
     <span data-ttu-id="72e05-120">-- или --</span><span class="sxs-lookup"><span data-stu-id="72e05-120">-- or --</span></span>  
  
-   <span data-ttu-id="72e05-121">Щелкните правой кнопкой мыши ячейку области данных там, где нужно удалить столбец, и выберите команду **Удалить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="72e05-121">Right-click a cell in the data region where you want to delete a column, and then click **Delete Columns**.</span></span>  
  
### <a name="to-insert-a-column-in-a-group-in-a-selected-data-region"></a><span data-ttu-id="72e05-122">Вставка столбца в группу в выделенной области данных</span><span class="sxs-lookup"><span data-stu-id="72e05-122">To insert a column in a group in a selected data region</span></span>  
  
-   <span data-ttu-id="72e05-123">Щелкните правой кнопкой мыши ячейку группы столбцов в области данных табликса там, где нужно вставить столбец, выберите команду **Вставить столбец**и укажите **Слева — снаружи группы**, **Слева — внутри группы**, **Справа — внутри группы**или **Справа — снаружи группы**.</span><span class="sxs-lookup"><span data-stu-id="72e05-123">Right-click a column group cell in the column group area of a tablix data region where you want to insert a column, click **Insert Column**, and then click **Left - Outside Group**, **Left - Inside Group**, **Right - Inside Group**, or **Right - Outside Group**.</span></span>  
  
     <span data-ttu-id="72e05-124">Столбец добавится внутри или снаружи группы, представленной выбранной ячейкой группы столбцов.</span><span class="sxs-lookup"><span data-stu-id="72e05-124">A column is added either inside or outside the group represented by the column group cell you clicked on.</span></span>  
  
### <a name="to-delete-a-column-from-a-group-in-a-selected-data-region"></a><span data-ttu-id="72e05-125">Удаление столбца из группы в выделенной области данных</span><span class="sxs-lookup"><span data-stu-id="72e05-125">To delete a column from a group in a selected data region</span></span>  
  
-   <span data-ttu-id="72e05-126">Щелкните правой кнопкой мыши ячейку группы столбцов в области данных табликса там, где нужно удалить столбец, и выберите команду **Удалить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="72e05-126">Right-click a column group cell in the column group area of a tablix data region where you want to delete a column, and then click **Delete Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e05-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="72e05-127">See Also</span></span>  
 <span data-ttu-id="72e05-128">[Основные сведения о группах (построитель отчетов и службы SSRS)](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72e05-128">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="72e05-129">[Область данных табликса (построитель отчетов и службы SSRS)](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72e05-129">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="72e05-130">[Таблицы &#40;построитель отчетов и службы SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72e05-130">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="72e05-131">[Матрицы &#40;построитель отчетов и службы SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72e05-131">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="72e05-132">[Списки &#40;построитель отчетов и службы SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72e05-132">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="72e05-133">Списки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="72e05-133">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
