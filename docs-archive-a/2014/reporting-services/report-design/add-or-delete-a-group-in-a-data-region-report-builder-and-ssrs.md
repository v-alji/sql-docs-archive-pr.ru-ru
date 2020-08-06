---
title: Добавление или удаление группы в области данных (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4de53c3c-c6fc-49ce-b692-3609fc0b3ec5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c355ca87db578d47181935e1ca6bc48e75bf8b8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735046"
---
# <a name="add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="dd706-102">Добавление или удаление группы в области данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="dd706-102">Add or Delete a Group in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dd706-103">Группа добавляется к области данных для организации данных в зависимости от указанного значения или набора выражений, для отображения и вычислений.</span><span class="sxs-lookup"><span data-stu-id="dd706-103">Add a group to a data region when you want to organize data by a specific value or set of expressions, for display and calculations.</span></span> <span data-ttu-id="dd706-104">Группа имеет имя и выражение, указывающее, какие данные из набора принадлежат к этой группе.</span><span class="sxs-lookup"><span data-stu-id="dd706-104">A group has a name and an expression that identifies which data from a dataset belongs to the group.</span></span> <span data-ttu-id="dd706-105">Дополнительные сведения о группах см. в разделе [Основные сведения о группах (построитель отчетов и службы SSRS)](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dd706-105">For more information about groups, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="dd706-106">В области данных табликса щелкните таблицу, матрицу или список, чтобы вывести панель группирования.</span><span class="sxs-lookup"><span data-stu-id="dd706-106">In a tablix data region, click in the table, matrix, or list to display the Grouping pane.</span></span> <span data-ttu-id="dd706-107">Перетащите поля из набора данных в панель «Группы строк» или «Группы столбцов» для создания родительских или дочерних групп.</span><span class="sxs-lookup"><span data-stu-id="dd706-107">Drag dataset fields to the Row Group and Column Group pane to create parent or child groups.</span></span> <span data-ttu-id="dd706-108">Щелкните правой кнопкой мыши существующую группу, чтобы добавить смежную с ней группу.</span><span class="sxs-lookup"><span data-stu-id="dd706-108">Right-click an existing group to add an adjacent group.</span></span> <span data-ttu-id="dd706-109">По определению группа подробностей является самой внутренней группой и может быть добавлена только как дочерняя.</span><span class="sxs-lookup"><span data-stu-id="dd706-109">By definition, the details group is the innermost group and can only be added as a child group.</span></span> <span data-ttu-id="dd706-110">Щелкните правой кнопкой мыши существующую группу, чтобы удалить ее.</span><span class="sxs-lookup"><span data-stu-id="dd706-110">Right-click an existing group to delete it.</span></span> <span data-ttu-id="dd706-111">Строки и столбцы для вывода значений группы добавляются автоматически.</span><span class="sxs-lookup"><span data-stu-id="dd706-111">Rows and columns on which to display group values are automatically added for you.</span></span> <span data-ttu-id="dd706-112">Дополнительные сведения см. в разделе [Таблицы, матрицы и списки (построитель отчетов и службы SSRS)](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dd706-112">For more information, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="dd706-113">Щелкните в области данных диаграммы, чтобы отобразить области перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="dd706-113">In a Chart data region, click in the chart to display the drop-zones.</span></span> <span data-ttu-id="dd706-114">Создайте группы, перетащив поля набора данных на области перетаскивания категории и рядов.</span><span class="sxs-lookup"><span data-stu-id="dd706-114">Create groups by dragging dataset fields to the category and series drop zones.</span></span> <span data-ttu-id="dd706-115">Чтобы добавить вложенные группы, в область перетаскивания добавляют несколько полей.</span><span class="sxs-lookup"><span data-stu-id="dd706-115">To add nested groups, add multiple fields to the drop-zone.</span></span>  
  
 <span data-ttu-id="dd706-116">Группы не создаются в датчике по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dd706-116">Groups are not defined in a gauge by default.</span></span> <span data-ttu-id="dd706-117">По умолчанию датчик только вычисляет в указанном поле статистический показатель всех значений и выводит эту величину на датчике.</span><span class="sxs-lookup"><span data-stu-id="dd706-117">The default behavior for the gauge is to aggregate all values in the specified field into one value that is displayed on the gauge.</span></span> <span data-ttu-id="dd706-118">Дополнительные сведения см. в разделе [Датчики (построитель отчетов и службы SSRS)](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dd706-118">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-parent-or-child-row-or-column-group-to-a-tablix-data-region"></a><span data-ttu-id="dd706-119">Добавление дочерней или родительской группы строк или столбцов в область данных табликса</span><span class="sxs-lookup"><span data-stu-id="dd706-119">To add a parent or child row or column group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="dd706-120">Перетащите поле из области **Данные отчета** на область **Группы рядов** или область **Группы столбцов** .</span><span class="sxs-lookup"><span data-stu-id="dd706-120">Drag a field from the **Report Data** pane to the **Row Groups** pane or the **Column Groups** pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dd706-121">Если панель группирования не видна, на вкладке "Вид" выберите пункт **Группирование**.</span><span class="sxs-lookup"><span data-stu-id="dd706-121">If you do not see the Grouping pane, on the View tab, click **Grouping**.</span></span>  
  
2.  <span data-ttu-id="dd706-122">Перетащите поле и отпустите его над или под иерархией групп, используя панель консультанта, чтобы разместить эту группу как родительскую или дочернюю по отношению к существующей группе.</span><span class="sxs-lookup"><span data-stu-id="dd706-122">Drop the field above or below the group hierarchy using the guide bar to place the group as a parent group or a child group to an existing group.</span></span>  
  
     <span data-ttu-id="dd706-123">Группа добавляется с именем по умолчанию, выражением группы и выражением сортировки на основании имени поля.</span><span class="sxs-lookup"><span data-stu-id="dd706-123">The group is added with a default name, group expression, and sort expression that is based on the field name.</span></span>  
  
### <a name="to-add-an-adjacent-row-or-column-group-to-a-tablix-data-region"></a><span data-ttu-id="dd706-124">Добавление смежной группы строк или столбцов в область данных табликса</span><span class="sxs-lookup"><span data-stu-id="dd706-124">To add an adjacent row or column group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="dd706-125">На панели группирования щелкните правой кнопкой мыши группу, одноранговую добавляемой группе.</span><span class="sxs-lookup"><span data-stu-id="dd706-125">In the Grouping pane, right-click a group that is a peer to the group that you want to add.</span></span> <span data-ttu-id="dd706-126">Щелкните **Добавить группу**, а затем **Прилегающая до** или **Прилегающая после** , чтобы указать, куда именно добавить группу.</span><span class="sxs-lookup"><span data-stu-id="dd706-126">Click **Add Group**, and then click **Adjacent Before** or **Adjacent After** to specify where to add the group.</span></span> <span data-ttu-id="dd706-127">Откроется диалоговое окно **Группа табликсов** .</span><span class="sxs-lookup"><span data-stu-id="dd706-127">The **Tablix Group** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="dd706-128">В поле **Имя**введите имя группы.</span><span class="sxs-lookup"><span data-stu-id="dd706-128">In **Name**, type a name for the group.</span></span>  
  
3.  <span data-ttu-id="dd706-129">Чтобы создать выражение, в поле **Выражение группирования**нажмите кнопку (**fx**) или введите новое выражение.</span><span class="sxs-lookup"><span data-stu-id="dd706-129">In **Group expression**, type an expression or click the expression button (**fx**) to create an expression.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="dd706-130">На панель группирования будет добавлена новая группа, а в область данных табликса в области конструктора будут добавлены строка или столбец для вывода групповых значений.</span><span class="sxs-lookup"><span data-stu-id="dd706-130">A new group is added to the Grouping pane and a row or column on which to display group values is added to the tablix data region on the design surface.</span></span>  
  
### <a name="to-add-a-details-group-to-a-tablix-data-region"></a><span data-ttu-id="dd706-131">Добавление группы сведений к области данных табликса</span><span class="sxs-lookup"><span data-stu-id="dd706-131">To add a details group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="dd706-132">На панели "Группирование" щелкните правой кнопкой мыши самую внутреннюю дочернюю группу, но не группу **Сведения** .</span><span class="sxs-lookup"><span data-stu-id="dd706-132">In the Grouping pane, right-click a group that is the innermost child group, but not the **Details** group.</span></span> <span data-ttu-id="dd706-133">Нажмите **Добавить группу**и выберите **Дочерняя группа**.</span><span class="sxs-lookup"><span data-stu-id="dd706-133">Click **Add Group**, and then click **Child Group**.</span></span> <span data-ttu-id="dd706-134">Откроется диалоговое окно **Группа табликсов** .</span><span class="sxs-lookup"><span data-stu-id="dd706-134">The **Tablix Group** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="dd706-135">Оставьте поле **Выражение группы**пустым.</span><span class="sxs-lookup"><span data-stu-id="dd706-135">In **Group expression**, leave the expression blank.</span></span> <span data-ttu-id="dd706-136">Группа подробностей не имеет выражения.</span><span class="sxs-lookup"><span data-stu-id="dd706-136">A details group has no expression.</span></span>  
  
3.  <span data-ttu-id="dd706-137">Выберите **Показать подробные данные**.</span><span class="sxs-lookup"><span data-stu-id="dd706-137">Select **Show detail data**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="dd706-138">Новая группа подробностей добавляется в панель «Группирование» в виде дочерней группы, и маркер строки для группы, выбранной в шаге 1, отображает значок группы подробностей.</span><span class="sxs-lookup"><span data-stu-id="dd706-138">A new details group is added as a child group in the Grouping pane, and the row handle for the group you selected in step 1 displays the details group icon.</span></span> <span data-ttu-id="dd706-139">Дополнительные сведения о маркерах см. в разделе [Ячейки, строки и столбцы области данных табликса &#40;построитель отчетов&#41; и службы SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dd706-139">For more information about handles, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-edit-a-row-or-column-group-in-a-tablix-data-region"></a><span data-ttu-id="dd706-140">Изменение группы строк или столбцов в области данных табликса</span><span class="sxs-lookup"><span data-stu-id="dd706-140">To edit a row or column group in a tablix data region</span></span>  
  
1.  <span data-ttu-id="dd706-141">В области конструктора щелкните в любом месте области данных табликса для ее выделения.</span><span class="sxs-lookup"><span data-stu-id="dd706-141">On the report design surface, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="dd706-142">На панели группирования будут отображены группы столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="dd706-142">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="dd706-143">Щелкните правой кнопкой мыши группу, а затем щелкните **Свойства группы**.</span><span class="sxs-lookup"><span data-stu-id="dd706-143">Right-click the group, and then click **Group Properties**.</span></span>  
  
3.  <span data-ttu-id="dd706-144">В поле **Имя**введите имя группы.</span><span class="sxs-lookup"><span data-stu-id="dd706-144">In **Name**, type the name of the group.</span></span>  
  
4.  <span data-ttu-id="dd706-145">Чтобы создать выражение группирования, в поле **Выражения группирования**введите или выберите простое выражение или нажмите кнопку (**fx**).</span><span class="sxs-lookup"><span data-stu-id="dd706-145">In **Group expressions**, type or select a simple expression, or click the Expression (**fx**) button to create a group expression.</span></span>  
  
5.  <span data-ttu-id="dd706-146">Для создания дополнительных выражений щелкните **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="dd706-146">Click **Add** to create additional expressions.</span></span> <span data-ttu-id="dd706-147">Все заданные выражения будут соединены с помощью логического оператора ИЛИ, чтобы образовать выражение группирования данной группы.</span><span class="sxs-lookup"><span data-stu-id="dd706-147">All expressions you specify are combined using a logical AND to specify data for this group.</span></span>  
  
6.  <span data-ttu-id="dd706-148">Перейдите на вкладку **Разрывы страниц** , чтобы задать параметры разрывов страниц (необязательно).</span><span class="sxs-lookup"><span data-stu-id="dd706-148">(Optional) Click **Page Breaks** to set page break options.</span></span>  
  
7.  <span data-ttu-id="dd706-149">Перейдите на вкладку **Сортировка** , чтобы выбрать или ввести выражение для сортировки данных внутри группы (необязательно).</span><span class="sxs-lookup"><span data-stu-id="dd706-149">(Optional) Click **Sorting** to select or type expressions that specify the sort order for values in the group.</span></span>  
  
8.  <span data-ttu-id="dd706-150">Перейдите на вкладку **Видимость** , чтобы выбрать параметры видимости для элемента (необязательно).</span><span class="sxs-lookup"><span data-stu-id="dd706-150">(Optional) Click **Visibility** to select the visibility options for the item.</span></span>  
  
9. <span data-ttu-id="dd706-151">Перейдите на вкладку **Фильтры** , чтобы задать фильтры для группы (необязательно).</span><span class="sxs-lookup"><span data-stu-id="dd706-151">(Optional) Click **Filters** to set filters for this group.</span></span>  
  
10. <span data-ttu-id="dd706-152">Перейдите на вкладку **Переменные** , чтобы задать переменные, областью действия которых будет данная группа и все ее дочерние группы (необязательно).</span><span class="sxs-lookup"><span data-stu-id="dd706-152">(Optional) Click **Variables** to define variables scoped to this group and accessible from any child groups.</span></span>  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-group-from-a-tablix-data-region"></a><span data-ttu-id="dd706-153">Удаление группы из области данных табликса</span><span class="sxs-lookup"><span data-stu-id="dd706-153">To delete a group from a tablix data region</span></span>  
  
1.  <span data-ttu-id="dd706-154">На панели "Группирование" щелкните правой кнопкой мыши группу и выберите команду **Удалить группу**.</span><span class="sxs-lookup"><span data-stu-id="dd706-154">In the Grouping pane, right-click the group, and then click **Delete Group**.</span></span>  
  
2.  <span data-ttu-id="dd706-155">В диалоговом окне **Удаление группы** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="dd706-155">In the **Delete Group** dialog box, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="dd706-156">**Удалить группу, а также связанные строки и столбцы** Этот параметр удаляет определение группы и все связанные с ней строки, в которых выводятся данные группы.</span><span class="sxs-lookup"><span data-stu-id="dd706-156">**Delete group and related rows and columns** Choose this option to delete the group definition and all related rows that display group data.</span></span> <span data-ttu-id="dd706-157">В группе подробностей, если одна и та же строка принадлежит одновременно подробностям и данным группы, удаляются только строки данных подробностей.</span><span class="sxs-lookup"><span data-stu-id="dd706-157">For the details group, if the same row belongs to both detail and group data, only the detail data rows are deleted.</span></span>  
  
    -   <span data-ttu-id="dd706-158">**Удалить только группу** . Если выбрать этот параметр, область данных табликса сохранит свою структуру. Удалено будет только определение группы.</span><span class="sxs-lookup"><span data-stu-id="dd706-158">**Delete group only** Choose this option to keep the structure of the tablix data region the same and delete only the group definition.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-details-group-from-a-tablix-data-region"></a><span data-ttu-id="dd706-159">Удаление группы подробностей из области данных табликса</span><span class="sxs-lookup"><span data-stu-id="dd706-159">To delete a details group from a tablix data region</span></span>  
  
1.  <span data-ttu-id="dd706-160">На панели "Группирование" щелкните правой кнопкой мыши группу подробностей и выберите команду **Удалить группу**.</span><span class="sxs-lookup"><span data-stu-id="dd706-160">In the Grouping pane, right-click the details group, and then click **Delete Group**.</span></span>  
  
2.  <span data-ttu-id="dd706-161">В диалоговом окне **Удаление группы** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="dd706-161">In the **Delete Group** dialog box, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="dd706-162">**Удалить группу, а также связанные строки и столбцы** Этот параметр удаляет определение группы и все связанные с ней строки, в которых выводятся данные группы.</span><span class="sxs-lookup"><span data-stu-id="dd706-162">**Delete group and related rows and columns** Choose this option to delete the group definition and all related rows that display group data.</span></span> <span data-ttu-id="dd706-163">В группе подробностей, если одна и та же строка принадлежит одновременно подробностям и данным группы, удаляются только строки данных подробностей.</span><span class="sxs-lookup"><span data-stu-id="dd706-163">For the details group, if the same row belongs to both detail and group data, only the detail data rows are deleted.</span></span>  
  
    -   <span data-ttu-id="dd706-164">**Удалить только группу** . Если выбрать этот параметр, область данных табликса сохранит свою структуру. Удалено будет только определение группы.</span><span class="sxs-lookup"><span data-stu-id="dd706-164">**Delete group only** Choose this option to keep the structure of the tablix data region the same and delete only the group definition.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="dd706-165">Группа подробностей будет удалена.</span><span class="sxs-lookup"><span data-stu-id="dd706-165">The details group is deleted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dd706-166">Убедитесь, что после удаления строки подробностей выражение в каждой ячейке содержит статистическое выражение (там, где это уместно).</span><span class="sxs-lookup"><span data-stu-id="dd706-166">Verify that after you remove a details row, the expression in each cell specifies an aggregate expression where appropriate.</span></span> <span data-ttu-id="dd706-167">При необходимости измените выражение, чтобы задать агрегатные функции нужным образом.</span><span class="sxs-lookup"><span data-stu-id="dd706-167">If necessary, edit the expression to specify aggregate functions as needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd706-168">См. также:</span><span class="sxs-lookup"><span data-stu-id="dd706-168">See Also</span></span>  
 <span data-ttu-id="dd706-169">[Ссылки на коллекции переменных отчета и группы (построитель отчетов и службы SSRS)](built-in-collections-report-and-group-variables-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="dd706-169">[Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md) </span></span>  
 <span data-ttu-id="dd706-170">[Примеры выражений групп &#40;построитель отчетов и службы SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd706-170">[Group Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd706-171">[Фильтрация, группирование и сортировка данных (построитель отчетов и службы SSRS)](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd706-171">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd706-172">[Область данных табликса (построитель отчетов и службы SSRS)](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd706-172">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd706-173">[Таблицы &#40;построитель отчетов и службы SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd706-173">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd706-174">[Матрицы &#40;построитель отчетов и службы SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd706-174">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd706-175">[Списки &#40;построитель отчетов и службы SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd706-175">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="dd706-176">Таблицы, матрицы и списки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="dd706-176">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
