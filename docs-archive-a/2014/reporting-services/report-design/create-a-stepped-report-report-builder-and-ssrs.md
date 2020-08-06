---
title: Создание пошагового отчета (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5933c4f0-c713-4ecb-b521-ff46c9c63fff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d845993ac1462cef2d39638101e5c7b9fc314b94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658136"
---
# <a name="create-a-stepped-report-report-builder-and-ssrs"></a><span data-ttu-id="3b2ff-102">Создание пошагового отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3b2ff-102">Create a Stepped Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3b2ff-103">В пошаговом отчете строки детализации или дочерние группы располагаются с отступом в родительской группе в том же столбце, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-103">A stepped report shows detail rows or child groups indented under a parent group in the same column, as shown in the example below:</span></span>  
  
 <span data-ttu-id="3b2ff-104">![Преобразованный для просмотра пошаговый отчет](../media/steppedreportrendered.gif "Преобразованный для просмотра пошаговый отчет")</span><span class="sxs-lookup"><span data-stu-id="3b2ff-104">![Rendered stepped report](../media/steppedreportrendered.gif "Rendered stepped report")</span></span>  
  
 <span data-ttu-id="3b2ff-105">В обычных табличных отчетах родительская группа помещается в соседний столбец отчета.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-105">Traditional table reports place the parent group in an adjacent column on the report.</span></span> <span data-ttu-id="3b2ff-106">Новая область данных табликса позволяет добавлять строки групп, строки детализации или дочерние группы в тот же столбец.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-106">The new tablix data region enables you to add a group and detail rows or child groups to the same column.</span></span> <span data-ttu-id="3b2ff-107">Чтобы отличить строки групп от строк детализации или строк дочерних групп, можно применить форматирование (например, цвет шрифта) либо создать отступ для строк детализации.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-107">To differentiate the group rows from the detail or child group rows, you can apply formatting such as font color, or you can indent the detail rows.</span></span>  
  
 <span data-ttu-id="3b2ff-108">В процедурах, описываемых в данном разделе, показывается, как можно вручную создать пошаговый отчет, но также можно использовать мастер создания таблиц и матриц.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-108">The procedures in this topic show you how to manually create a stepped report, but you can also use the New Table and Matrix Wizard.</span></span> <span data-ttu-id="3b2ff-109">Это упрощает создание пошаговых отчетов благодаря наличию макета такого отчета.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-109">It provides the layout for stepped reports, making it easy to create them.</span></span> <span data-ttu-id="3b2ff-110">После завершения работы мастера можно дополнительно расширить возможности отчета.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-110">After you complete the wizard, you can further enhance the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b2ff-111">Мастер доступен только в построителе отчетов.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-111">The wizard is available only in Report Builder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-stepped-report"></a><span data-ttu-id="3b2ff-112">Создание пошагового отчета</span><span class="sxs-lookup"><span data-stu-id="3b2ff-112">To create a stepped report</span></span>  
  
1.  <span data-ttu-id="3b2ff-113">Создайте табличный отчет.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-113">Create a table report.</span></span> <span data-ttu-id="3b2ff-114">Например, вставьте область данных табликса и добавьте поля в строку данных.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-114">For example, insert a tablix data region and add fields to the Data row.</span></span>  
  
2.  <span data-ttu-id="3b2ff-115">Добавьте в отчет родительскую группу.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-115">Add a parent group to your report.</span></span>  
  
    1.  <span data-ttu-id="3b2ff-116">Чтобы выбрать таблицу, щелкните в любом месте на ее поверхности.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-116">Click anywhere in the table to select it.</span></span> <span data-ttu-id="3b2ff-117">Группа подробностей будет отображена на панели «Группы строк» панели группирования.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-117">The Grouping pane displays the Details group in the Row Groups pane.</span></span>  
  
    2.  <span data-ttu-id="3b2ff-118">В панели группирования щелкните правой кнопкой мыши группу подробностей, выберите пункт **Добавить группу**, затем — **Родительская группа**.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-118">In the Grouping Pane, right-click the Details Group, point to **Add Group**, and then click **Parent Group**.</span></span>  
  
    3.  <span data-ttu-id="3b2ff-119">В диалоговом окне **Группа табликсов** введите имя для группы и введите или выберите выражение группы из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-119">In the **Tablix Group** dialog box, provide a name for the group and type or select a group expression from the drop-down list.</span></span> <span data-ttu-id="3b2ff-120">В раскрывающемся списке представлены простые выражения полей, доступные в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-120">The drop-down list displays the simple field expressions that are available in the Report Data pane.</span></span> <span data-ttu-id="3b2ff-121">Например, [PostalCode] является простым выражением поля PostalCode в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-121">For example, [PostalCode] is a simple field expression for the PostalCode field in a dataset.</span></span>  
  
    4.  <span data-ttu-id="3b2ff-122">Выберите **Добавить верхний колонтитул группы**.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-122">Select **Add group header**.</span></span> <span data-ttu-id="3b2ff-123">Этот параметр добавляет над группой статическую строку, в которой будут отображаться метка группы и ее статистические сведения.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-123">This option adds a static row above the group for the group label and group totals.</span></span> <span data-ttu-id="3b2ff-124">Аналогичным образом можно выбрать **Добавить нижний колонтитул группы** , чтобы добавить статическую строку ниже группы.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-124">Likewise, you can select **Add group footer** to add a static row below the group.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="3b2ff-125">В результате создан простой табличный отчет.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-125">You now have a basic tabular report.</span></span> <span data-ttu-id="3b2ff-126">После его подготовки один из его столбцов будет содержать значения экземпляра группы, а один или несколько других столбцов — сгруппированные подробные данные.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-126">When it is rendered, you see one column with the group instance value, and one or more columns with grouped detail data.</span></span> <span data-ttu-id="3b2ff-127">На следующем рисунке показано, как может выглядеть область данных в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-127">The following figure shows what the data region might look like on the design surface.</span></span>  
  
     <span data-ttu-id="3b2ff-128">![Табличная область данных с группированием](../media/tabledataregionwithgroup.gif "Табличная область данных с группированием")</span><span class="sxs-lookup"><span data-stu-id="3b2ff-128">![Table data region with group](../media/tabledataregionwithgroup.gif "Table data region with group")</span></span>  
  
     <span data-ttu-id="3b2ff-129">На следующем рисунке показано, как готовая для просмотра область данных может выглядеть при просмотре отчета.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-129">The following figure shows how the rendered data region might look when you view the report.</span></span>  
  
     <span data-ttu-id="3b2ff-130">![Преобразованный для просмотра отчет с группированием](../media/tablereportrendered.gif "Преобразованный для просмотра отчет с группированием")</span><span class="sxs-lookup"><span data-stu-id="3b2ff-130">![Rendered grouped report](../media/tablereportrendered.gif "Rendered grouped report")</span></span>  
  
3.  <span data-ttu-id="3b2ff-131">В пошаговом отчете не требуется наличие первого столбца, отображающего экземпляр группы.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-131">For a stepped report, you do not need the first column that shows the group instance.</span></span> <span data-ttu-id="3b2ff-132">Вместо этого следует скопировать значение ячейки заголовка группы, удалить столбец группы и вставить это значение в первое текстовое поле строки заголовка группы.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-132">Instead, copy the value in the group header cell, delete the group column, and paste in the first text box in the group header row.</span></span> <span data-ttu-id="3b2ff-133">Чтобы удалить столбец группы, щелкните правой кнопкой мыши столбец или ячейку группы и выберите команду **Удалить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-133">To remove the group column, right-click the group column or cell, and click **Delete Columns**.</span></span> <span data-ttu-id="3b2ff-134">На следующем рисунке показано, как может выглядеть область данных в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-134">The following figure shows what the data region might look like on the design surface.</span></span>  
  
     <span data-ttu-id="3b2ff-135">![Область данных с записью заголовка группы](../media/tabledataregiongroupheader.gif "Область данных с записью заголовка группы")</span><span class="sxs-lookup"><span data-stu-id="3b2ff-135">![Data region with group header row](../media/tabledataregiongroupheader.gif "Data region with group header row")</span></span>  
  
4.  <span data-ttu-id="3b2ff-136">Создать отступ для строк детализации под строкой заголовка в том же столбце можно, изменив поля ячеек с подробными данными.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-136">To indent the detail rows under the group header row in the same column, change the padding of the detail data cell.</span></span>  
  
    1.  <span data-ttu-id="3b2ff-137">Выберите ячейку с полем детализации, для которого необходимо создать отступ.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-137">Select the cell with the detail field that you want to indent.</span></span> <span data-ttu-id="3b2ff-138">Свойства текстового поля данной ячейки будут отображены в панели свойств.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-138">The text box properties for that cell appear in the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="3b2ff-139">На вкладке **Выравнивание**панели свойств разверните свойства **Заполнение**.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-139">In the Properties pane, under **Alignment**, expand the properties for **Padding**.</span></span>  
  
    3.  <span data-ttu-id="3b2ff-140">В поле **Left (левое**) введите новое значение заполнения, например `.5in` .</span><span class="sxs-lookup"><span data-stu-id="3b2ff-140">For **Left**, type a new padding value, such as `.5in`.</span></span> <span data-ttu-id="3b2ff-141">Заполнение смещает текст в ячейке на указанное значение.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-141">Padding indents the text in the cell by the value you specify.</span></span> <span data-ttu-id="3b2ff-142">Значение заполнения по умолчанию — 2 пункта.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-142">The default padding is 2 points.</span></span> <span data-ttu-id="3b2ff-143">Допустимыми значениями заполнения являются числовые значения, больше или равные нулю, за которыми следуют единицы измерения.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-143">Valid values for the Padding properties are zero or a positive number, followed by a size designator.</span></span>  
  
         <span data-ttu-id="3b2ff-144">Существуют следующие единицы измерения.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-144">Size designators are:</span></span>  
  
        |||  
        |-|-|  
        |`in`|<span data-ttu-id="3b2ff-145">Дюймы (1 дюйм = 2,54 сантиметра)</span><span class="sxs-lookup"><span data-stu-id="3b2ff-145">Inches (1 inch = 2.54 centimeters)</span></span>|  
        |`cm`|<span data-ttu-id="3b2ff-146">Сантиметры</span><span class="sxs-lookup"><span data-stu-id="3b2ff-146">Centimeters</span></span>|  
        |`mm`|<span data-ttu-id="3b2ff-147">Миллиметры</span><span class="sxs-lookup"><span data-stu-id="3b2ff-147">Millimeters</span></span>|  
        |`pt`|<span data-ttu-id="3b2ff-148">Пункты (1 пункт = 1/72 дюйма)</span><span class="sxs-lookup"><span data-stu-id="3b2ff-148">Points (1 point = 1/72 inch)</span></span>|  
        |`pc`|<span data-ttu-id="3b2ff-149">Пики (1 пик = 12 пунктов)</span><span class="sxs-lookup"><span data-stu-id="3b2ff-149">Picas (1 pica = 12 points)</span></span>|  
  
     <span data-ttu-id="3b2ff-150">Область данных может выглядеть примерно так.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-150">Your data region will look similar to the following example.</span></span>  
  
     <span data-ttu-id="3b2ff-151">![Область данных для пошагового отчета](../media/steppedreportdataregion.gif "Область данных для пошагового отчета")</span><span class="sxs-lookup"><span data-stu-id="3b2ff-151">![Data region for stepped report](../media/steppedreportdataregion.gif "Data region for stepped report")</span></span>  
  
     <span data-ttu-id="3b2ff-152">**Область данных для макета пошагового отчета**</span><span class="sxs-lookup"><span data-stu-id="3b2ff-152">**Data Region for Stepped Report Layout**</span></span>  
  
     <span data-ttu-id="3b2ff-153">На вкладке **Корневая папка** нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-153">On the **Home** tab Click **Run**.</span></span> <span data-ttu-id="3b2ff-154">Отчет отображает группу с разными отступами для значений дочерних групп.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-154">The report displays the group with indented levels for the child group values.</span></span>  
  
### <a name="to-create-a-stepped-report-with-multiple-groups"></a><span data-ttu-id="3b2ff-155">Создание пошагового отчета с несколькими группами</span><span class="sxs-lookup"><span data-stu-id="3b2ff-155">To create a stepped report with multiple groups</span></span>  
  
1.  <span data-ttu-id="3b2ff-156">Создайте отчет так, как это описано в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-156">Create a report as described in the previous procedure.</span></span>  
  
2.  <span data-ttu-id="3b2ff-157">Добавьте дополнительные группы в отчет.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-157">Add additional groups to your report.</span></span>  
  
    1.  <span data-ttu-id="3b2ff-158">В панели "Группы строк" щелкните правой кнопкой мыши группу, выберите команду **Добавить группу**и тип группы, которую необходимо добавить.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-158">In the Row Groups pane, right-click the group, click **Add Group**, and then choose the type of group you want to add.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="3b2ff-159">Существует несколько способов добавления групп в область данных.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-159">There are several ways to add groups to a data region.</span></span> <span data-ttu-id="3b2ff-160">Дополнительные сведения см. [в разделе Добавление или удаление группы в области данных &#40;построитель отчетов и служб SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ff-160">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
    2.  <span data-ttu-id="3b2ff-161">Введите имя в диалоговом окне **Группа табликсов** .</span><span class="sxs-lookup"><span data-stu-id="3b2ff-161">In the **Tablix Group** dialog box, type a name.</span></span>  
  
    3.  <span data-ttu-id="3b2ff-162">В поле **Выражение группы**введите выражение или выберите поле набора данных, по которому будет выполнено группирование.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-162">In **Group expression**, type an expression or select a dataset field to group on.</span></span> <span data-ttu-id="3b2ff-163">Чтобы создать выражение, нажмите кнопку выражения (**fx**) для открытия диалогового окна **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="3b2ff-163">To create an expression, click the expression (**fx**) button to open the **Expression** dialog box.</span></span>  
  
    4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
3.  <span data-ttu-id="3b2ff-164">Измените заполнение для ячейки, отображающей данные группы.</span><span class="sxs-lookup"><span data-stu-id="3b2ff-164">Change the padding for the cell that displays the group data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b2ff-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="3b2ff-165">See Also</span></span>  
 <span data-ttu-id="3b2ff-166">[Верхние и нижние колонтитулы страницы &#40;построитель отчетов и службы SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3b2ff-166">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3b2ff-167">[Форматирование элементов отчета &#40;построитель отчетов и SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3b2ff-167">[Formatting Report Items &#40;Report Builder and SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3b2ff-168">[Область данных табликса &#40;построитель отчетов и SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3b2ff-168">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3b2ff-169">[Таблицы &#40;построитель отчетов и службы SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3b2ff-169">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3b2ff-170">[Матрицы &#40;построитель отчетов и службы SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3b2ff-170">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3b2ff-171">[Содержит &#40;построитель отчетов и SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3b2ff-171">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3b2ff-172">Таблицы, матрицы и списки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3b2ff-172">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
