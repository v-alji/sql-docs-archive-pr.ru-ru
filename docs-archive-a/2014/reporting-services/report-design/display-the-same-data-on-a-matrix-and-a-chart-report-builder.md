---
title: Отображение одних и тех же данных в матрице и на диаграмме (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1262f283-9fc2-4bc1-9c79-457f7642abc7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7746ce1f06d4dcc67c51ddc40714f19a3ff83d51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736085"
---
# <a name="display-the-same-data-on-a-matrix-and-a-chart-report-builder"></a><span data-ttu-id="9b8fa-102">Отображение одних и тех же данных в матрице и на диаграмме (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="9b8fa-102">Display the Same Data on a Matrix and a Chart (Report Builder)</span></span>
  <span data-ttu-id="9b8fa-103">Если нужно отобразить одинаковые данные в матрице и на диаграмме, необходимо установить свойства в обеих областях данных таким образом, чтобы они ссылались на один и тот же набор данных, а также на одни и те же выражения фильтров, групп, сортировки и данных.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-103">When you want to show the same data in a matrix and a chart, you must set properties on both data regions to specify the same dataset, and also the same expressions for filters, groups, sorts, and data.</span></span>  
  
 <span data-ttu-id="9b8fa-104">Поскольку обе области данных будут иметь один источник данных (набор данных отчета), к матрице можно добавить кнопку интерактивной сортировки, которая при нажатии пользователем будет изменять порядок сортировки как для матрицы, так и для диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-104">Because both data regions will have the same ancestor for data (the report dataset), you can add an interactive sort button to the matrix that, when the user clicks it, changes the sort order for both the matrix and the chart.</span></span> <span data-ttu-id="9b8fa-105">Дополнительные сведения см. в разделе [Добавление интерактивной сортировки в таблицу или матрицу (построитель отчетов и службы SSRS)](add-interactive-sort-to-a-table-or-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9b8fa-105">For more information, see [Add Interactive Sort to a Table or Matrix &#40;Report Builder and SSRS&#41;](add-interactive-sort-to-a-table-or-matrix-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="9b8fa-106">Чтобы использовать значения группы столбцов матрицы в качестве условных обозначений диаграммы, необходимо задать цвета для рядов данных диаграммы, а затем использовать те же цвета для заливки фона текстовых полей в ячейках матрицы, в которых отображаются эти значения группы.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-106">To use the matrix column group values as a legend for the chart, you must specify the colors for the series data on the chart, and then use the same colors as the fill colors for the background of the text boxes in the matrix cell that displays the group values.</span></span> <span data-ttu-id="9b8fa-107">Дополнительные сведения см. в разделе [Указание согласованных цветов для нескольких фигурных диаграмм (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9b8fa-107">For more information, see [Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="9b8fa-108">Во время выполнения отчет может выглядеть загроможденным, если в определениях групп имеется слишком много значений.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-108">At run-time, your report may appear cluttered if there are too many group values for your group definitions.</span></span> <span data-ttu-id="9b8fa-109">Возможно, придется фильтровать значения, объединять группы или настраивать пороговые значения диаграммы для объединения групп.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-109">You might need to filter values, combine groups, or adjust the threshold for the chart to combine groups for you.</span></span> <span data-ttu-id="9b8fa-110">Дополнительные сведения см. в разделе [Связывание нескольких областей данных с одним набором данных (построитель отчетов и службы SSRS)](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="9b8fa-110">For more information, see [Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-matrix-and-chart-to-display-the-same-data"></a><span data-ttu-id="9b8fa-111">Добавление матрицы и диаграммы для отображения одних и тех же данных</span><span class="sxs-lookup"><span data-stu-id="9b8fa-111">To add a matrix and chart to display the same data</span></span>  
  
1.  <span data-ttu-id="9b8fa-112">Откройте отчет в режиме конструктора.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-112">Open a report in design view.</span></span>  
  
2.  <span data-ttu-id="9b8fa-113">На вкладке **Вставка** в группе **Области данных** нажмите кнопку **Матрица**, а затем щелкните текст отчета либо в прямоугольнике в тексте отчета.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-113">From the **Insert** tab, in the **Data Regions** group, click **Matrix**, and then click the report body or in a rectangle in the report body.</span></span> <span data-ttu-id="9b8fa-114">В отчет будет добавлена матрица.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-114">A matrix is added to the report.</span></span>  
  
3.  <span data-ttu-id="9b8fa-115">На вкладке **Вставка** в группе **Области данных** нажмите кнопку **Диаграмма**и выберите тип диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-115">From the **Insert** tab, in the **Data Regions** group, click **Chart**, and then select the chart type.</span></span> <span data-ttu-id="9b8fa-116">В отчет будет добавлена диаграмма.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-116">A chart is added to the report.</span></span>  
  
4.  <span data-ttu-id="9b8fa-117">На вкладке **Вставка** в группе **Элементы отчета** нажмите кнопку **Прямоугольник**, а затем щелкните отчет (необязательно).</span><span class="sxs-lookup"><span data-stu-id="9b8fa-117">(Optional) From the **Insert** tab, in the **Report Items** group, click **Rectangle**, and then click the report.</span></span> <span data-ttu-id="9b8fa-118">В отчет будет добавлен прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-118">A rectangle is added to the report.</span></span> <span data-ttu-id="9b8fa-119">Перетащите матрицу и диаграмму, добавленные в шагах 2 и 3, в прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-119">Drag the matrix and chart from steps 2 and 3 into the rectangle.</span></span>  
  
     <span data-ttu-id="9b8fa-120">Поместив несколько областей данных в прямоугольный контейнер, можно контролировать то, как матрица и диаграмма будут отображаться при просмотре отчета.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-120">By placing multiple data regions in the rectangle container, you help control how the matrix and chart render when you view the report.</span></span>  
  
     <span data-ttu-id="9b8fa-121">На следующих шагах нужно будет выбрать одно поле набора данных, которое будет отображаться как в матрице, так и на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-121">In the next few steps, you will choose the same dataset field to display in the matrix and to display in the chart.</span></span>  
  
5.  <span data-ttu-id="9b8fa-122">Из области данных отчета перетащите числовое поле набора данных в ячейку данных матрицы.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-122">From the Report Data pane, drag a numeric dataset field to the Data cell in the matrix.</span></span>  
  
     <span data-ttu-id="9b8fa-123">По умолчанию для вычисления значения группы используется агрегатная функция Sum.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-123">By default, the aggregate function Sum is used for calculating the group value.</span></span> <span data-ttu-id="9b8fa-124">Если меняется агрегатная функция в матрице, ее необходимо также поменять в диаграмме.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-124">If you change the aggregate function in the matrix, you must change in the chart also.</span></span>  
  
6.  <span data-ttu-id="9b8fa-125">Щелкните правой кнопкой мыши ячейку данных в матрице, выберите **Свойства текстового поля**и щелкните **Число**.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-125">In the matrix, right-click the cell with data, click **Text Box Properties**, and then click **Number**.</span></span> <span data-ttu-id="9b8fa-126">Выберите соответствующий формат для значения поля набора данных.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-126">Choose an appropriate format for the dataset field value.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="9b8fa-127">Перетащите это же поле, выбранное на шаге 3, в зону **Значения** в диаграмме.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-127">Drag the same dataset field you chose in step 3 to the **Values** area on the chart.</span></span>  
  
9. <span data-ttu-id="9b8fa-128">Щелкните правой кнопкой мыши ось Y диаграммы, выберите **Свойства оси**и щелкните **Число**.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-128">In the chart, right-click the Y axis, click **Axis Properties**, and then click **Number**.</span></span> <span data-ttu-id="9b8fa-129">Выберите тот же формат данных, что и на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-129">Choose the same format for the data that you chose in step 4.</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="9b8fa-130">Далее вы присвоите группе строк матрицы и группе рядов диаграммы одно и то же выражение, а также установите порядок сортировки для группы рядов диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-130">In the next few steps, you will set the matrix row group and the chart series group to the same expression, and also set the sort order for the chart series group.</span></span>  
  
11. <span data-ttu-id="9b8fa-131">Перетащите из панели данных отчета поле набора данных, по которому будут группироваться строки матрицы, на панель «Группы строк».</span><span class="sxs-lookup"><span data-stu-id="9b8fa-131">From the Report Data pane, drag the dataset field that you want to group by for matrix rows to the Row Groups pane.</span></span>  
  
     <span data-ttu-id="9b8fa-132">По умолчанию выражение сортировки для группы строк матрицы равно выражению группы.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-132">By default, the matrix row group adds a sort expression that is the same as the group expression.</span></span>  
  
12. <span data-ttu-id="9b8fa-133">Перетащите это же поле, выбранное на шаге 9, в зону **Группы рядов** в диаграмме.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-133">Drag the same dataset field that you used in step 9 to the **Series Groups** area for the chart.</span></span>  
  
13. <span data-ttu-id="9b8fa-134">Щелкните правой кнопкой мыши группу в области **Группы рядов** и выберите пункт **Свойства группы рядов**.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-134">Right-click the group in the **Series Groups** area, and then click **Series Group Properties**.</span></span>  
  
14. <span data-ttu-id="9b8fa-135">Щелкните **Сортировка**.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-135">Click **Sorting**.</span></span>  
  
15. <span data-ttu-id="9b8fa-136">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-136">Click **Add**.</span></span> <span data-ttu-id="9b8fa-137">В сетке выражений сортировки появится новая строка.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-137">A new row appears in the sort expressions grid.</span></span>  
  
16. <span data-ttu-id="9b8fa-138">В поле **Сортировать по**выберите из раскрывающегося списка то же поле набора данных, выбранное на шаге 9 для группирования.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-138">In **Sort by**, from the drop-down list, choose the dataset field that you chose to group by in step 9.</span></span>  
  
17. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="9b8fa-139">Далее вы присвоите группе столбцов матрицы и группе категорий диаграммы одно и то же выражение, а также установите порядок сортировки для группы категорий диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-139">In the next few steps, you will set the matrix column group and the chart category group to the same expression, and also set the sort order for the chart category group.</span></span>  
  
18. <span data-ttu-id="9b8fa-140">Перетащите из панели данных отчета поле набора данных, по которому будут группироваться столбцы матрицы, на панель «Группы столбцов».</span><span class="sxs-lookup"><span data-stu-id="9b8fa-140">From the Report Data pane, drag the dataset field that you want to group by for matrix columns to the Column Groups pane.</span></span>  
  
     <span data-ttu-id="9b8fa-141">По умолчанию выражение сортировки для группы столбцов матрицы равно выражению группы.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-141">By default, the matrix column group adds a sort expression that is the same as the group expression.</span></span>  
  
19. <span data-ttu-id="9b8fa-142">Перетащите это же поле, выбранное на шаге 16, в область **Группы категорий** диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-142">Drag the same dataset field that you used in step 16 to the **Category Groups** area for the chart.</span></span>  
  
20. <span data-ttu-id="9b8fa-143">Правой кнопкой мыши щелкните группу в области **CategoryGroup** и выберите пункт **Свойства группы категорий**.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-143">Right-click the group in the **CategoryGroups** area, and then click **Category Group Properties**.</span></span>  
  
21. <span data-ttu-id="9b8fa-144">Щелкните **Сортировка**.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-144">Click **Sorting**.</span></span>  
  
22. <span data-ttu-id="9b8fa-145">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-145">Click **Add**.</span></span> <span data-ttu-id="9b8fa-146">В сетке выражений сортировки появится новая строка.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-146">A new row appears in the sort expressions grid.</span></span>  
  
23. <span data-ttu-id="9b8fa-147">В поле **Сортировать по**выберите из раскрывающегося списка то же поле набора данных, выбранное на шаге 16 для группирования.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-147">In **Sort by**, from the drop-down list, choose the dataset field that you chose to group by in step 16.</span></span>  
  
24. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
25. <span data-ttu-id="9b8fa-148">Просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-148">Preview the result.</span></span> <span data-ttu-id="9b8fa-149">Группы строк и столбцов матрицы отображают те же данные, что и группы рядов и категорий диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9b8fa-149">The matrix row and column groups display the same data as the chart series and category groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b8fa-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b8fa-150">See Also</span></span>  
 <span data-ttu-id="9b8fa-151">[Связывание нескольких областей данных с одним набором данных (построитель отчетов и службы SSRS)](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9b8fa-151">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9b8fa-152">[Добавление фильтров набора данных, фильтров области данных и групповых фильтров (построитель отчетов и службы SSRS)](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="9b8fa-152">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="9b8fa-153">[Содержит &#40;построитель отчетов и SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9b8fa-153">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9b8fa-154">Диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9b8fa-154">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
