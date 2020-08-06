---
title: Сортировка данных в области данных (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2fcb9be2-1daa-4c92-ad00-5f63cdf39f70
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc1fb458066bb942a490b08c0faad876dd3d5438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739224"
---
# <a name="sort-data-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="047a4-102">Сортировка данных в области данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="047a4-102">Sort Data in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="047a4-103">Чтобы изменить порядок сортировки данных в области данных при первом запуске отчета, необходимо создать выражение сортировки для области данных или в группы.</span><span class="sxs-lookup"><span data-stu-id="047a4-103">To change the sort order of data in a data region when a report first runs, you must set the sort expression on the data region or group.</span></span> <span data-ttu-id="047a4-104">По умолчанию выражению сортировки для группы автоматически присваивается то же значение, что и выражению группы.</span><span class="sxs-lookup"><span data-stu-id="047a4-104">By default, the sort expression for a group is automatically set to the same value as the group expression.</span></span>  
  
-   <span data-ttu-id="047a4-105">В области данных табликса создайте выражение сортировки для области данных или каждой группы, включая группу подробностей.</span><span class="sxs-lookup"><span data-stu-id="047a4-105">In a tablix data region, set the sort expression for the data region or for each group, including the details group.</span></span> <span data-ttu-id="047a4-106">Если в области данных табликса имеется только одна группа подробностей, можно определить выражение сортировки в запросе, в области данных или в группе подробностей, поскольку его результат будет одинаковым.</span><span class="sxs-lookup"><span data-stu-id="047a4-106">If you have only one details group in a tablix data region, you can define a sort expression in the query, on the data region, or on the details group and they all have the same effect.</span></span>  
  
-   <span data-ttu-id="047a4-107">В диаграммной области данных создайте выражение сортировки для групп категорий и рядов, чтобы управлять порядком сортировки для каждой группы.</span><span class="sxs-lookup"><span data-stu-id="047a4-107">In a chart data region, set the sort expression for the Category and Series groups to control the sort order for each group.</span></span> <span data-ttu-id="047a4-108">Порядок цветов в условных обозначениях диаграммы определяется выражением сортировки для точек данных в группе категорий.</span><span class="sxs-lookup"><span data-stu-id="047a4-108">The order for colors in a chart legend is determined by the sort expression for the data points in the Category group.</span></span>  
  
-   <span data-ttu-id="047a4-109">В области данных датчика обычно не требуется сортировать данные, поскольку датчик отображает одно значение из диапазона.</span><span class="sxs-lookup"><span data-stu-id="047a4-109">In a gauge data region, you do not typically need to sort data because the gauge displays a single value relative to a range.</span></span> <span data-ttu-id="047a4-110">Если потребуется сортировать данные датчика, необходимо вначале определить группу, а затем создать выражение сортировки для этой группы.</span><span class="sxs-lookup"><span data-stu-id="047a4-110">If you do need sort data in a gauge, you must first define a group, and then set the sort expression for the group.</span></span>  
  
 <span data-ttu-id="047a4-111">Дополнительные сведения см. в разделе [Фильтрация, группирование и сортировка данных (построитель отчетов и службы SSRS)](filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="047a4-111">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="047a4-112">Для области данных табликса в заголовок столбца можно также добавить интерактивную кнопку сортировки, чтобы пользователь мог изменять порядок сортировки групп или строк подробностей.</span><span class="sxs-lookup"><span data-stu-id="047a4-112">For a tablix data region, you can also add an interactive sort button to the top of a column header to provide the user with the ability to change the sort order of groups or detail rows.</span></span> <span data-ttu-id="047a4-113">Дополнительные сведения см. в разделе [Интерактивная сортировка (построитель отчетов и службы SSRS)](interactive-sort-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="047a4-113">For more information, see [Interactive Sort &#40;Report Builder and SSRS&#41;](interactive-sort-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-sort-data-in-a-tablix-data-region"></a><span data-ttu-id="047a4-114">Сортировка данных в области данных табликса</span><span class="sxs-lookup"><span data-stu-id="047a4-114">To sort data in a Tablix data region</span></span>  
  
1.  <span data-ttu-id="047a4-115">В области конструктора щелкните правой кнопкой мыши маркер строки и выберите пункт **Свойства табликса**.</span><span class="sxs-lookup"><span data-stu-id="047a4-115">On the design surface, right-click a row handle, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="047a4-116">Щелкните **Сортировка**.</span><span class="sxs-lookup"><span data-stu-id="047a4-116">Click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="047a4-117">Выполните следующие действия для каждого выражения.</span><span class="sxs-lookup"><span data-stu-id="047a4-117">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="047a4-118">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="047a4-118">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="047a4-119">Введите или выберите выражение, по которому будут сортироваться данные.</span><span class="sxs-lookup"><span data-stu-id="047a4-119">Type or select an expression by which to sort the data.</span></span>  
  
    3.  <span data-ttu-id="047a4-120">В раскрывающемся списке столбца **Порядок** выберите порядок сортировки для каждого выражения.</span><span class="sxs-lookup"><span data-stu-id="047a4-120">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="047a4-121">**A-Z** сортирует выражение по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="047a4-121">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="047a4-122">**Z-A** сортирует выражение по убыванию.</span><span class="sxs-lookup"><span data-stu-id="047a4-122">**Z-A** sorts the expression in descending order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-values-in-a-group-including-the-details-group-for-a-tablix"></a><span data-ttu-id="047a4-123">Сортировка значений в группе, в том числе группе подробностей, для табликса</span><span class="sxs-lookup"><span data-stu-id="047a4-123">To sort values in a group, including the details group, for a Tablix</span></span>  
  
1.  <span data-ttu-id="047a4-124">В области конструктора щелкните в любом месте области данных табликса, чтобы выделить ее.</span><span class="sxs-lookup"><span data-stu-id="047a4-124">On the design surface, click in the tablix data region to select it.</span></span> <span data-ttu-id="047a4-125">На панели группировки отобразятся группы строк и столбцов для области данных табликса.</span><span class="sxs-lookup"><span data-stu-id="047a4-125">The Grouping pane displays the row groups and column groups for the Tablix data region.</span></span>  
  
2.  <span data-ttu-id="047a4-126">На панели "Группы строк" щелкните правой кнопкой мыши имя группы и выберите пункт **Изменить группу**.</span><span class="sxs-lookup"><span data-stu-id="047a4-126">In the Row Groups pane, right-click the group name, and then click **Edit Group**.</span></span>  
  
3.  <span data-ttu-id="047a4-127">В диалоговом окне **Группа табликсов** щелкните **Сортировать**.</span><span class="sxs-lookup"><span data-stu-id="047a4-127">In the **Tablix Group** dialog box, click **Sort**.</span></span>  
  
4.  <span data-ttu-id="047a4-128">Выполните следующие действия для каждого выражения.</span><span class="sxs-lookup"><span data-stu-id="047a4-128">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="047a4-129">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="047a4-129">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="047a4-130">Введите или выберите выражение, по которому будут сортироваться данные.</span><span class="sxs-lookup"><span data-stu-id="047a4-130">Type or select an expression by which to sort the data.</span></span>  
  
    3.  <span data-ttu-id="047a4-131">В раскрывающемся списке столбца **Порядок** выберите порядок сортировки для каждого выражения.</span><span class="sxs-lookup"><span data-stu-id="047a4-131">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="047a4-132">**A-Z** сортирует выражение по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="047a4-132">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="047a4-133">**Z-A** сортирует выражение по убыванию.</span><span class="sxs-lookup"><span data-stu-id="047a4-133">**Z-A** sorts the expression in descending order.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-x-axis-labels-in-alphabetical-order-on-a-chart"></a><span data-ttu-id="047a4-134">Сортировка меток оси X в алфавитном порядке в диаграмме</span><span class="sxs-lookup"><span data-stu-id="047a4-134">To sort x-axis labels in alphabetical order on a chart</span></span>  
  
1.  <span data-ttu-id="047a4-135">Щелкните правой кнопкой мыши поле в области добавления "Поле категории" и выберите **Свойства группы категорий**.</span><span class="sxs-lookup"><span data-stu-id="047a4-135">Right-click a field in the Category Field drop-zone and click **Category GroupProperties**.</span></span>  
  
2.  <span data-ttu-id="047a4-136">В диалоговом окне **Свойства группы категорий** щелкните **Сортировка**.</span><span class="sxs-lookup"><span data-stu-id="047a4-136">In the **Category Group Properties** dialog box, click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="047a4-137">Выполните следующие действия для каждого выражения.</span><span class="sxs-lookup"><span data-stu-id="047a4-137">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="047a4-138">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="047a4-138">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="047a4-139">Выберите выражение, соответствующее полю группирования.</span><span class="sxs-lookup"><span data-stu-id="047a4-139">Select the expression that matches your grouping field.</span></span> <span data-ttu-id="047a4-140">Это выражение можно проверить, щелкнув **Группирование**.</span><span class="sxs-lookup"><span data-stu-id="047a4-140">You can verify the expression for the grouping field by clicking **Grouping**.</span></span>  
  
    3.  <span data-ttu-id="047a4-141">В раскрывающемся списке столбца **Порядок** выберите порядок сортировки для каждого выражения.</span><span class="sxs-lookup"><span data-stu-id="047a4-141">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="047a4-142">**A-Z** сортирует выражение по возрастанию в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="047a4-142">**A-Z** sorts the expression in ascending alphabetical order.</span></span> <span data-ttu-id="047a4-143">**Z-A** сортирует выражение по убыванию в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="047a4-143">**Z-A** sorts the expression in descending alphabetical order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-the-data-points-in-ascending-or-descending-order-on-a-chart"></a><span data-ttu-id="047a4-144">Сортировка точек данных по возрастанию или по убыванию в диаграмме</span><span class="sxs-lookup"><span data-stu-id="047a4-144">To sort the data points in ascending or descending order on a chart</span></span>  
  
1.  <span data-ttu-id="047a4-145">Щелкните правой кнопкой мыши поле в области добавления "Поле категории" и выберите **Свойства группы категорий**.</span><span class="sxs-lookup"><span data-stu-id="047a4-145">Right-click a field in the Category Field drop zone and click **Category GroupProperties**.</span></span>  
  
2.  <span data-ttu-id="047a4-146">В диалоговом окне **Свойства группы категорий** щелкните **Сортировка**.</span><span class="sxs-lookup"><span data-stu-id="047a4-146">In the **Category Group Properties** dialog box, click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="047a4-147">Выполните следующие действия для каждого выражения.</span><span class="sxs-lookup"><span data-stu-id="047a4-147">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="047a4-148">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="047a4-148">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="047a4-149">Выберите выражение, соответствующее полю данных.</span><span class="sxs-lookup"><span data-stu-id="047a4-149">Select the expression that matches your data field.</span></span> <span data-ttu-id="047a4-150">В большинстве случаев это статистическое выражение, такое как `=Sum(Fields!Quantity.Value)`.</span><span class="sxs-lookup"><span data-stu-id="047a4-150">In most cases, this is an aggregated value, such as `=Sum(Fields!Quantity.Value)`.</span></span>  
  
    3.  <span data-ttu-id="047a4-151">В раскрывающемся списке столбца **Порядок** выберите порядок сортировки для каждого выражения.</span><span class="sxs-lookup"><span data-stu-id="047a4-151">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="047a4-152">**A-Z** сортирует выражение по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="047a4-152">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="047a4-153">**Z-A** сортирует выражение по убыванию.</span><span class="sxs-lookup"><span data-stu-id="047a4-153">**Z-A** sorts the expression in descending order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-data-in-ascending-or-descending-order-for-display-on-a-gauge"></a><span data-ttu-id="047a4-154">Сортировка данных по возрастанию или по убыванию для отображения в датчике</span><span class="sxs-lookup"><span data-stu-id="047a4-154">To sort data in ascending or descending order for display on a gauge</span></span>  
  
1.  <span data-ttu-id="047a4-155">Щелкните правой кнопкой мыши датчик и выполните команду **Добавить группу данных**.</span><span class="sxs-lookup"><span data-stu-id="047a4-155">Right-click the gauge and click **Add Data Group**.</span></span>  
  
2.  <span data-ttu-id="047a4-156">При необходимости перейдите на вкладку **Общие** в диалоговом окне **Свойства группы панелей датчиков** .</span><span class="sxs-lookup"><span data-stu-id="047a4-156">In the **Gauge Panel GroupProperties** dialog box, click **General** if necessary.</span></span>  
  
3.  <span data-ttu-id="047a4-157">Щелкните **Добавить**в области **Выражения группирования**.</span><span class="sxs-lookup"><span data-stu-id="047a4-157">In **Group expressions**, click **Add**.</span></span>  
  
4.  <span data-ttu-id="047a4-158">В поле **Группировать по**введите или выберите выражение, по которым будут группироваться данные.</span><span class="sxs-lookup"><span data-stu-id="047a4-158">In **Group on**, type or select an expression by which to group the data.</span></span>  
  
5.  <span data-ttu-id="047a4-159">Повторите шаги 3 и 4 для каждого нужного выражения группы.</span><span class="sxs-lookup"><span data-stu-id="047a4-159">Repeat steps 3 and 4 until you have added all the group expressions you want to use.</span></span>  
  
6.  <span data-ttu-id="047a4-160">Щелкните **Сортировка**.</span><span class="sxs-lookup"><span data-stu-id="047a4-160">Click **Sorting**.</span></span>  
  
7.  <span data-ttu-id="047a4-161">Выполните следующие действия для каждого выражения.</span><span class="sxs-lookup"><span data-stu-id="047a4-161">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="047a4-162">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="047a4-162">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="047a4-163">Выберите выражение, соответствующее полю группирования.</span><span class="sxs-lookup"><span data-stu-id="047a4-163">Select the expression that matches your grouping field.</span></span> <span data-ttu-id="047a4-164">Это выражение можно проверить, щелкнув **Группирование**.</span><span class="sxs-lookup"><span data-stu-id="047a4-164">You can verify the expression for the grouping field by clicking **Grouping**.</span></span>  
  
    3.  <span data-ttu-id="047a4-165">В раскрывающемся списке столбца **Порядок** выберите порядок сортировки для каждого выражения.</span><span class="sxs-lookup"><span data-stu-id="047a4-165">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="047a4-166">**A-Z** сортирует выражение по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="047a4-166">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="047a4-167">**Z-A** сортирует выражение по убыванию.</span><span class="sxs-lookup"><span data-stu-id="047a4-167">**Z-A** sorts the expression in descending order.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="047a4-168">Дополнительные сведения о группировании данных в датчике см. в разделе [Датчики (построитель отчетов и службы SSRS)](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="047a4-168">For more information about how data is grouped in a gauge, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047a4-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="047a4-169">See Also</span></span>  
 <span data-ttu-id="047a4-170">[Построитель отчетов справки по диалоговым окнам, панелям и мастерам](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="047a4-170">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="047a4-171">[Диаграммы &#40;построитель отчетов и службы SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="047a4-171">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="047a4-172">[Форматирование меток оси на построитель отчетов &#40;диаграммы и SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="047a4-172">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="047a4-173">Указание согласованных цветов для нескольких фигурных диаграмм (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="047a4-173">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
  
