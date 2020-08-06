---
title: Добавление диаграммы в отчет (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a6b595dc-f775-4a53-8554-74a0bf9335ec
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 789dd6cce10b0425833ea63f2f7941ea75970a25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654818"
---
# <a name="add-a-chart-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="77bc3-102">Добавление диаграммы в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="77bc3-102">Add a Chart to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="77bc3-103">Если необходимо создать сводку данных в визуальном формате, используется диаграммная область данных.</span><span class="sxs-lookup"><span data-stu-id="77bc3-103">When you want to summarize data in a visual format, use a Chart data region.</span></span> <span data-ttu-id="77bc3-104">Важно выбрать тип диаграммы, подходящий для типа представляемых данных.</span><span class="sxs-lookup"><span data-stu-id="77bc3-104">It is important to choose an appropriate chart type for the type of data that you are presenting.</span></span> <span data-ttu-id="77bc3-105">От этого зависит, насколько успешно можно будет интерпретировать данные, представленные в виде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="77bc3-105">This affects how well the data can be interpreted when put in chart form.</span></span> <span data-ttu-id="77bc3-106">Дополнительные сведения см. в разделе [Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="77bc3-106">For more information, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="77bc3-107">Самым простым способом добавления диаграммная область данных в отчет является запуск мастера создания диаграмм.</span><span class="sxs-lookup"><span data-stu-id="77bc3-107">The simplest way to add a Chart data region to your report is to run the New Chart Wizard.</span></span> <span data-ttu-id="77bc3-108">Мастер поддерживает гистограммы, графики, круговые диаграммы, линейчатые диаграммы и диаграммы с областями.</span><span class="sxs-lookup"><span data-stu-id="77bc3-108">The wizard offers column, line, pie, bar, and area charts.</span></span> <span data-ttu-id="77bc3-109">Диаграммы этих и других типов также можно добавить вручную.</span><span class="sxs-lookup"><span data-stu-id="77bc3-109">For these and other chart types, you can also add a chart manually.</span></span>  
  
 <span data-ttu-id="77bc3-110">Добавив диаграммную область данных в область конструктора, можно перетаскивать поля набора данных отчета с числовыми и нечисловыми данными на панель «Данные диаграммы».</span><span class="sxs-lookup"><span data-stu-id="77bc3-110">After you add a Chart data region to the design surface, you can drag report dataset fields for numeric and non-numeric data to the Chart Data pane of the chart.</span></span> <span data-ttu-id="77bc3-111">Щелкните в области данных диаграммы, чтобы отобразить панель "Данные диаграммы" с ее тремя областями: "Группы рядов", "Группы категорий" и "Значения".</span><span class="sxs-lookup"><span data-stu-id="77bc3-111">Click the chart to display the Chart Data pane with its three areas: Series Groups, Category Groups, and Values.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-chart-to-a-report-by-using-the-chart-wizard"></a><span data-ttu-id="77bc3-112">Добавление диаграммы в отчет с помощью мастера диаграмм</span><span class="sxs-lookup"><span data-stu-id="77bc3-112">To add a chart to a report by using the Chart Wizard</span></span>  
  
1.  > [!NOTE]  
    >  <span data-ttu-id="77bc3-113">Мастер диаграмм доступен только в построителе отчетов.</span><span class="sxs-lookup"><span data-stu-id="77bc3-113">The Chart Wizard is only available in Report Builder.</span></span>  
  
     <span data-ttu-id="77bc3-114">На вкладке **Вставка** нажмите кнопку **Диаграмма**, а затем щелкните **Мастер диаграмм**.</span><span class="sxs-lookup"><span data-stu-id="77bc3-114">On the **Insert** tab, click **Chart**, and then click **Chart Wizard**.</span></span>  
  
2.  <span data-ttu-id="77bc3-115">Выполните шаги **мастера создания диаграмм** .</span><span class="sxs-lookup"><span data-stu-id="77bc3-115">Follow the steps in the **New** Chart wizard.</span></span>  
  
3.  <span data-ttu-id="77bc3-116">На вкладке **Корневая папка** нажмите кнопку **Выполнить** , чтобы вывести отчет, готовый для просмотра.</span><span class="sxs-lookup"><span data-stu-id="77bc3-116">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
4.  <span data-ttu-id="77bc3-117">На вкладке **Выполнение** нажмите кнопку **Конструктор** , чтобы продолжить работу с отчетом.</span><span class="sxs-lookup"><span data-stu-id="77bc3-117">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
### <a name="to-add-a-chart-to-a-report"></a><span data-ttu-id="77bc3-118">Добавление диаграммы к отчету</span><span class="sxs-lookup"><span data-stu-id="77bc3-118">To add a chart to a report</span></span>  
  
1.  <span data-ttu-id="77bc3-119">Создайте отчет и определите набор данных.</span><span class="sxs-lookup"><span data-stu-id="77bc3-119">Create a report and define a dataset.</span></span> <span data-ttu-id="77bc3-120">Дополнительные сведения см. в разделе [Добавление данных в отчет &#40;построитель отчетов и службы SSRS&#41;](../report-data/report-datasets-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="77bc3-120">For more information, see [Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="77bc3-121">На вкладке **Вставка** выберите **Диаграмма**, затем **Вставить диаграмму**.</span><span class="sxs-lookup"><span data-stu-id="77bc3-121">On the **Insert** tab, click **Chart**, and then click **Insert Chart**.</span></span>  
  
3.  <span data-ttu-id="77bc3-122">Щелкните область конструктора в месте, где должен располагаться левый верхний угол диаграммы, а затем перетащите курсор мыши в место, где будет располагаться правый нижний угол диаграммы.</span><span class="sxs-lookup"><span data-stu-id="77bc3-122">Click on the design surface where you want the upper-left corner of the chart, and then drag to where you want the lower-right corner of the chart.</span></span>  
  
     <span data-ttu-id="77bc3-123">Откроется диалоговое окно **Выбор типа диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="77bc3-123">The **Select Chart Type** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="77bc3-124">Выберите тип диаграммы, который нужно добавить в отчет.</span><span class="sxs-lookup"><span data-stu-id="77bc3-124">Select the type of chart you want to add.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="77bc3-125">Щелкните диаграмму, чтобы отобразить панель **Данные диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="77bc3-125">Click the chart to display the **Chart Data** pane.</span></span>  
  
6.  <span data-ttu-id="77bc3-126">Добавьте одно или несколько полей в область **Значения** .</span><span class="sxs-lookup"><span data-stu-id="77bc3-126">Add one or more fields to the **Values** area.</span></span> <span data-ttu-id="77bc3-127">Эти данные будут выведены на оси значений.</span><span class="sxs-lookup"><span data-stu-id="77bc3-127">This information will be plotted on the value axis.</span></span>  
  
7.  <span data-ttu-id="77bc3-128">Добавьте поле группирования в область **Группы категорий** .</span><span class="sxs-lookup"><span data-stu-id="77bc3-128">Add a grouping field to the **Category Groups** area.</span></span> <span data-ttu-id="77bc3-129">При добавлении этого поля в область **Группы категорий** автоматически создается поле группирования.</span><span class="sxs-lookup"><span data-stu-id="77bc3-129">When you add this field to the **Category Groups** area, a grouping field is automatically created for you.</span></span> <span data-ttu-id="77bc3-130">Каждая группа представляет собой точку данных в рядах.</span><span class="sxs-lookup"><span data-stu-id="77bc3-130">Each group represents a data point in your series.</span></span>  
  
8.  <span data-ttu-id="77bc3-131">Чтобы получить сводку данных по категориям, щелкните правой кнопкой мыши набор данных и выберите пункт **Свойства ряда**.</span><span class="sxs-lookup"><span data-stu-id="77bc3-131">To summarize the data by category, right-click the data field and click **Series Properties**.</span></span> <span data-ttu-id="77bc3-132">В текстовом поле **Категория** выберите из раскрывающегося списка поле категории.</span><span class="sxs-lookup"><span data-stu-id="77bc3-132">In the **Category** box, select the category field from the drop-down list.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="77bc3-133">На вкладке **Корневая папка** нажмите кнопку **Выполнить** , чтобы вывести отчет, готовый для просмотра.</span><span class="sxs-lookup"><span data-stu-id="77bc3-133">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
10. <span data-ttu-id="77bc3-134">На вкладке **Выполнение** нажмите кнопку **Конструктор** , чтобы продолжить работу с отчетом.</span><span class="sxs-lookup"><span data-stu-id="77bc3-134">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
 <span data-ttu-id="77bc3-135">На диаграммах с осями (гистограмма, линейчатая диаграмма) на оси категорий могут отображаться не все метки категорий.</span><span class="sxs-lookup"><span data-stu-id="77bc3-135">On charts with axes, such as bar and column charts, the category axis may not display all the category labels.</span></span> <span data-ttu-id="77bc3-136">Дополнительные сведения об изменении меток оси см. в разделе [Задание интервала оси (построитель отчетов и службы SSRS)](specify-an-axis-interval-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="77bc3-136">For more information about how to change the axis labels, see [Specify an Axis Interval &#40;Report Builder and SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77bc3-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="77bc3-137">See Also</span></span>  
 <span data-ttu-id="77bc3-138">[Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="77bc3-138">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="77bc3-139">[Типы диаграмм (построитель отчетов и службы SSRS)](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="77bc3-139">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="77bc3-140">[Точки данных со значением NULL и пустые точки в диаграммах (построитель отчетов и службы SSRS)](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="77bc3-140">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="77bc3-141">[Учебник. Добавление в отчет линейчатой диаграммы (построитель отчетов)](https://go.microsoft.com/fwlink/?LinkId=198052) </span><span class="sxs-lookup"><span data-stu-id="77bc3-141">[Tutorial: Adding a Bar Chart to Your Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198052) </span></span>  
 <span data-ttu-id="77bc3-142">[Учебник. Добавление в отчет линейчатой диаграммы (конструктор отчетов)](https://go.microsoft.com/fwlink/?LinkId=198042) </span><span class="sxs-lookup"><span data-stu-id="77bc3-142">[Tutorial: Adding a Bar Chart to a Report (Report Designer)](https://go.microsoft.com/fwlink/?LinkId=198042) </span></span>  
 <span data-ttu-id="77bc3-143">[Учебник. Добавление в отчет круговой диаграммы (построитель отчетов)](https://go.microsoft.com/fwlink/?LinkId=198051) </span><span class="sxs-lookup"><span data-stu-id="77bc3-143">[Tutorial: Adding a Pie Chart to Your Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198051) </span></span>  
 [<span data-ttu-id="77bc3-144">Учебник. Добавление в отчет круговой диаграммы (конструктор отчетов)</span><span class="sxs-lookup"><span data-stu-id="77bc3-144">Tutorial: Adding a Pie Chart to a Report (Report Designer)</span></span>](https://go.microsoft.com/fwlink/?LinkId=198041)  
  
  
