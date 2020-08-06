---
title: Добавление фильтра (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 10ae54e7-0e8a-4dff-995d-05516c51d076
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61a5444c437027d92a9f054e74cbcac6af5cc776
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751728"
---
# <a name="add-a-filter-report-builder-and-ssrs"></a><span data-ttu-id="0beb7-102">Добавление фильтра (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="0beb7-102">Add a Filter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0beb7-103">Добавьте фильтр к набору данных, области данных или группе, если нужно включить или исключить определенные значения из вычислений или отображения.</span><span class="sxs-lookup"><span data-stu-id="0beb7-103">Add a filter to a dataset, data region, or group when you want to include or exclude specific values for calculations or display.</span></span> <span data-ttu-id="0beb7-104">Фильтры применяются во время выполнения вначале для набора данных, затем для области данных и группы в нисходящем порядке для иерархий групп.</span><span class="sxs-lookup"><span data-stu-id="0beb7-104">Filters are applied at run time first on the dataset, and then on the data region, and then on the group, in top-down order for group hierarchies.</span></span> <span data-ttu-id="0beb7-105">В таблице, матрице и списке фильтры для групп строк, групп столбцов и смежных групп применяются независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="0beb7-105">In a table, matrix, or list, filters for row groups, column groups, and adjacent groups are applied independently.</span></span> <span data-ttu-id="0beb7-106">В диаграмме фильтры для групп категорий и групп рядов применяются независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="0beb7-106">In a chart, filters for category groups and series groups are applied independently.</span></span>  
  
 <span data-ttu-id="0beb7-107">Чтобы добавить фильтр, необходимо указать одно или несколько уравнений фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-107">To add a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="0beb7-108">Уравнение фильтра состоит из выражения, определяющего фильтруемые данные, оператор и значения сравнения.</span><span class="sxs-lookup"><span data-stu-id="0beb7-108">A filter equation consists of an expression that identifies the data that you want to filter, an operator, and the value to compare to.</span></span> <span data-ttu-id="0beb7-109">Тип данных фильтруемых данных и тип данных значения должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="0beb7-109">The data types of the filtered data and the value must match.</span></span> <span data-ttu-id="0beb7-110">Фильтрация статистических значений набора данных или области данных не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0beb7-110">Filtering on aggregate values for a dataset or data region is not supported.</span></span>  
  
 <span data-ttu-id="0beb7-111">Чтобы отфильтровать точки данных в диаграмме, нужно установить фильтр для группы категорий или группы рядов.</span><span class="sxs-lookup"><span data-stu-id="0beb7-111">To filter data points in a chart, you can set a filter on a category group or a series group.</span></span> <span data-ttu-id="0beb7-112">По умолчанию диаграмма использует встроенную функцию Sum, чтобы вычислить агрегаты, принадлежащие одной группе, в отдельной точке данных ряда.</span><span class="sxs-lookup"><span data-stu-id="0beb7-112">By default, the chart uses the built-in function Sum to aggregate values that belong to the same group into an individual data point in the series.</span></span> <span data-ttu-id="0beb7-113">Если изменить агрегатную функцию ряда, необходимо также изменить агрегатную функцию в критерии фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-113">If you change the aggregate function of a series, you must change the aggregate function in the filter expression.</span></span>  
  
 <span data-ttu-id="0beb7-114">Дополнительные сведения о фильтрации внедренных и общих наборов данных см. в разделе [Добавление фильтра к набору данных (построитель отчетов и службы SSRS)](../report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0beb7-114">For more information about filtering embedded and shared datasets, see [Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;](../report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-filter-on-a-data-region"></a><span data-ttu-id="0beb7-115">Установка фильтра для области данных</span><span class="sxs-lookup"><span data-stu-id="0beb7-115">To set a filter on a data region</span></span>  
  
1.  <span data-ttu-id="0beb7-116">Откройте отчет в режиме **конструктора** .</span><span class="sxs-lookup"><span data-stu-id="0beb7-116">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="0beb7-117">Выберите область данных в области конструктора, а затем щелкните правой кнопкой мыши _\<data region>_ **свойства**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-117">Select the data region on the design surface, and then right-click _\<data region>_**Properties**.</span></span> <span data-ttu-id="0beb7-118">Для датчика выберите пункт **Свойства панели датчиков**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-118">For a gauge, select **Gauge Panel Properties**.</span></span> <span data-ttu-id="0beb7-119">_\<data region>_ Откроется диалоговое окно **свойства** .</span><span class="sxs-lookup"><span data-stu-id="0beb7-119">The _\<data region>_**Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0beb7-120">В области данных табликса щелкните угловую ячейку, строку или дескриптор столбца правой кнопкой мыши, а затем выберите команду **Свойства табликса**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-120">On a Tablix data region, right-click the corner cell or a row or column handle, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="0beb7-121">Перейдите на вкладку **Фильтры**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-121">Click **Filters**.</span></span> <span data-ttu-id="0beb7-122">Откроется список текущих уравнений фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-122">This displays the current list of filter equations.</span></span> <span data-ttu-id="0beb7-123">По умолчанию этот список пустой.</span><span class="sxs-lookup"><span data-stu-id="0beb7-123">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="0beb7-124">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-124">Click **Add**.</span></span> <span data-ttu-id="0beb7-125">Появится новое пустое уравнение фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-125">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="0beb7-126">В поле **Выражение**введите или выберите выражение для фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-126">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="0beb7-127">Чтобы изменить выражение, нажмите кнопку "Выражение" (*fx*).</span><span class="sxs-lookup"><span data-stu-id="0beb7-127">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="0beb7-128">Из раскрывающегося списка выберите тип данных, соответствующий типу данных в выражении, созданном на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="0beb7-128">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="0beb7-129">В поле **Оператор** выберите оператор, который фильтр должен использовать для сравнения значений в полях **Выражение** и **Значение** .</span><span class="sxs-lookup"><span data-stu-id="0beb7-129">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="0beb7-130">Выбранный оператор определяет число значений, которые используются в следующих шагах.</span><span class="sxs-lookup"><span data-stu-id="0beb7-130">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="0beb7-131">В поле **Значение** введите выражение или значение, с которым фильтр будет сравнивать значение в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-131">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="0beb7-132">Примеры уравнений фильтра см. в разделе [Примеры уравнений фильтра (построитель отчетов и службы SSRS)](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0beb7-132">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-tablix-row-or-column-group"></a><span data-ttu-id="0beb7-133">Установка фильтра для группы строк или столбцов табликса</span><span class="sxs-lookup"><span data-stu-id="0beb7-133">To set a filter on a Tablix row or column group</span></span>  
  
1.  <span data-ttu-id="0beb7-134">Откройте отчет в режиме **конструктора** .</span><span class="sxs-lookup"><span data-stu-id="0beb7-134">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="0beb7-135">Щелкните правой кнопкой мыши таблицу, матрицу или область списка данных в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="0beb7-135">Right-click the table, matrix, or list data region on the design surface to select it.</span></span> <span data-ttu-id="0beb7-136">На панели группирования отображаются группы выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="0beb7-136">The Grouping pane displays the groups for the selected item.</span></span>  
  
3.  <span data-ttu-id="0beb7-137">На панели группирования щелкните правой кнопкой мыши группу и выберите команду **Изменить группу**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-137">In the Grouping pane, right-click the group, and then click **Edit Group**.</span></span> <span data-ttu-id="0beb7-138">Откроется диалоговое окно **Группа табликсов** .</span><span class="sxs-lookup"><span data-stu-id="0beb7-138">The **Tablix Group** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="0beb7-139">Перейдите на вкладку **Фильтры**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-139">Click **Filters**.</span></span> <span data-ttu-id="0beb7-140">Откроется список текущих уравнений фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-140">This displays the current list of filter equations.</span></span> <span data-ttu-id="0beb7-141">По умолчанию этот список пустой.</span><span class="sxs-lookup"><span data-stu-id="0beb7-141">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="0beb7-142">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-142">Click **Add**.</span></span> <span data-ttu-id="0beb7-143">Появится новое пустое уравнение фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-143">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="0beb7-144">В поле **Выражение**введите или выберите выражение для фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-144">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="0beb7-145">Чтобы изменить выражение, нажмите кнопку "Выражение" (*fx*).</span><span class="sxs-lookup"><span data-stu-id="0beb7-145">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="0beb7-146">Из раскрывающегося списка выберите тип данных, соответствующий типу данных в выражении, созданном на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="0beb7-146">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="0beb7-147">В поле **Оператор** выберите оператор, который фильтр должен использовать для сравнения значений в полях **Выражение** и **Значение** .</span><span class="sxs-lookup"><span data-stu-id="0beb7-147">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="0beb7-148">Выбранный оператор определяет число значений, которые используются в следующих шагах.</span><span class="sxs-lookup"><span data-stu-id="0beb7-148">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="0beb7-149">В поле **Значение** введите выражение или значение, с которым фильтр будет сравнивать значение в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-149">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="0beb7-150">Примеры уравнений фильтра см. в разделе [Примеры уравнений фильтра (построитель отчетов и службы SSRS)](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0beb7-150">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-category-group"></a><span data-ttu-id="0beb7-151">Установка фильтра для группы категорий диаграммы</span><span class="sxs-lookup"><span data-stu-id="0beb7-151">To set a filter on a Chart category group</span></span>  
  
1.  <span data-ttu-id="0beb7-152">Откройте отчет в режиме **конструктора** .</span><span class="sxs-lookup"><span data-stu-id="0beb7-152">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="0beb7-153">В области конструктора дважды щелкните диаграмму, чтобы отобразить зоны перетаскивания для категорий, рядов и данных.</span><span class="sxs-lookup"><span data-stu-id="0beb7-153">On the design surface, click the chart twice to bring up data, series and category field drop zones.</span></span>  
  
3.  <span data-ttu-id="0beb7-154">Щелкните правой кнопкой мыши поле, расположенное в зоне перетаскивания категории, и выберите пункт **Свойства группы категорий**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-154">Right-click on a field contained in the category field drop zone and select **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="0beb7-155">Перейдите на вкладку **Фильтры**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-155">Click **Filters**.</span></span> <span data-ttu-id="0beb7-156">Откроется список текущих уравнений фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-156">This displays the current list of filter equations.</span></span> <span data-ttu-id="0beb7-157">По умолчанию этот список пустой.</span><span class="sxs-lookup"><span data-stu-id="0beb7-157">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="0beb7-158">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-158">Click **Add**.</span></span> <span data-ttu-id="0beb7-159">Появится новое пустое уравнение фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-159">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="0beb7-160">В поле **Выражение**введите или выберите выражение для фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-160">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="0beb7-161">Чтобы изменить выражение, нажмите кнопку "Выражение" (*fx*).</span><span class="sxs-lookup"><span data-stu-id="0beb7-161">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="0beb7-162">Из раскрывающегося списка выберите тип данных, соответствующий типу данных в выражении, созданном на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="0beb7-162">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="0beb7-163">В поле **Оператор** выберите оператор, который фильтр должен использовать для сравнения значений в полях **Выражение** и **Значение** .</span><span class="sxs-lookup"><span data-stu-id="0beb7-163">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="0beb7-164">Выбранный оператор определяет число значений, которые используются в следующих шагах.</span><span class="sxs-lookup"><span data-stu-id="0beb7-164">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="0beb7-165">В поле **Значение** введите выражение или значение, с которым фильтр будет сравнивать значение в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-165">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="0beb7-166">Примеры уравнений фильтра см. в разделе [Примеры уравнений фильтра (построитель отчетов и службы SSRS)](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0beb7-166">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-series-group"></a><span data-ttu-id="0beb7-167">Установка фильтра для группы рядов диаграммы</span><span class="sxs-lookup"><span data-stu-id="0beb7-167">To set a filter on a Chart series group</span></span>  
  
1.  <span data-ttu-id="0beb7-168">Откройте отчет в режиме **конструктора** .</span><span class="sxs-lookup"><span data-stu-id="0beb7-168">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="0beb7-169">В области конструктора дважды щелкните диаграмму, чтобы отобразить зоны перетаскивания для категорий, рядов и данных.</span><span class="sxs-lookup"><span data-stu-id="0beb7-169">On the design surface, click the chart twice to bring up data, series and category field drop zones.</span></span>  
  
3.  <span data-ttu-id="0beb7-170">Щелкните правой кнопкой мыши поле, расположенное в зоне перетаскивания поля ряда, и выберите пункт **Свойства группы рядов**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-170">Right-click on a field contained in the series field drop zone and select **Series Group Properties**.</span></span>  
  
4.  <span data-ttu-id="0beb7-171">Перейдите на вкладку **Фильтры**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-171">Click **Filters**.</span></span> <span data-ttu-id="0beb7-172">Откроется список текущих уравнений фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-172">This displays the current list of filter equations.</span></span> <span data-ttu-id="0beb7-173">По умолчанию этот список пустой.</span><span class="sxs-lookup"><span data-stu-id="0beb7-173">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="0beb7-174">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-174">Click **Add**.</span></span> <span data-ttu-id="0beb7-175">Появится новое пустое уравнение фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-175">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="0beb7-176">В поле **Выражение**введите или выберите выражение для фильтра.</span><span class="sxs-lookup"><span data-stu-id="0beb7-176">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="0beb7-177">Чтобы изменить выражение, нажмите кнопку "Выражение" (*fx*).</span><span class="sxs-lookup"><span data-stu-id="0beb7-177">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="0beb7-178">Из раскрывающегося списка выберите тип данных, соответствующий типу данных в выражении, созданном на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="0beb7-178">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="0beb7-179">В поле **Оператор** выберите оператор, который фильтр должен использовать для сравнения значений в полях **Выражение** и **Значение** .</span><span class="sxs-lookup"><span data-stu-id="0beb7-179">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="0beb7-180">Выбранный оператор определяет число значений, которые используются в следующих шагах.</span><span class="sxs-lookup"><span data-stu-id="0beb7-180">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="0beb7-181">В поле **Значение** введите выражение или значение, с которым фильтр будет сравнивать значение в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="0beb7-181">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="0beb7-182">Примеры уравнений фильтра см. в разделе [Примеры уравнений фильтра (построитель отчетов и службы SSRS)](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0beb7-182">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0beb7-183">См. также:</span><span class="sxs-lookup"><span data-stu-id="0beb7-183">See Also</span></span>  
 <span data-ttu-id="0beb7-184">[Добавление фильтров набора данных, фильтров области данных и групповых фильтров (построитель отчетов и службы SSRS)](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="0beb7-184">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="0beb7-185">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0beb7-185">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0beb7-186">[Датчики (построитель отчетов и службы SSRS)](gauges-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0beb7-186">[Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0beb7-187">[Содержит &#40;построитель отчетов и SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0beb7-187">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0beb7-188">Диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="0beb7-188">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
