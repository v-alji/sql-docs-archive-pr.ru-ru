---
title: Учебник. Добавление круговой диаграммы к отчету (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eaadf7bf-c312-428a-b214-0a1fbf959c3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 318370b185dcd75a8c3c54be49c47756bad5f3c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735950"
---
# <a name="tutorial-add-a-pie-chart-to-your-report-report-builder"></a><span data-ttu-id="7af04-102">Учебник. Добавление круговой диаграммы к отчету (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="7af04-102">Tutorial: Add a Pie Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="7af04-103">Круговые и кольцевые диаграммы отображают данные в виде пропорциональных долей целого.</span><span class="sxs-lookup"><span data-stu-id="7af04-103">Pie charts and doughnut charts display data as a proportion of the whole.</span></span> <span data-ttu-id="7af04-104">Круговые диаграммы обычно используются для сравнения групп.</span><span class="sxs-lookup"><span data-stu-id="7af04-104">Pie charts are most commonly used to make comparisons between groups.</span></span> <span data-ttu-id="7af04-105">Круговые и кольцевые диаграммы, наряду с пирамидальными и воронкообразными диаграммами, относятся к группе диаграмм, называемых фигурными.</span><span class="sxs-lookup"><span data-stu-id="7af04-105">Pie and doughnut charts, along with pyramid and funnel charts, constitute a group of charts known as shape charts.</span></span> <span data-ttu-id="7af04-106">Фигурные диаграммы не имеют осей.</span><span class="sxs-lookup"><span data-stu-id="7af04-106">Shape charts have no axes.</span></span> <span data-ttu-id="7af04-107">После перетаскивания числового поля на фигурную диаграмму в этой диаграмме вычисляется процентная доля каждого значения в общей сумме.</span><span class="sxs-lookup"><span data-stu-id="7af04-107">When a numeric field is dropped on a shape chart, the chart calculates the percentage of each value to the total.</span></span>  
  
 <span data-ttu-id="7af04-108">Если на круговой диаграмме расположено слишком много точек данных, метки точек данных могут располагаться близко друг к другу, и их будет трудно читать.</span><span class="sxs-lookup"><span data-stu-id="7af04-108">If there are too many data points on a pie chart, your data point labels might be too crowded to read.</span></span> <span data-ttu-id="7af04-109">В этом случае лучше использовать график.</span><span class="sxs-lookup"><span data-stu-id="7af04-109">In that case, consider using a line chart.</span></span> <span data-ttu-id="7af04-110">Круговую диаграмму рекомендуется использовать только в случае, если данные статистически обработаны в небольшое количество точек данных.</span><span class="sxs-lookup"><span data-stu-id="7af04-110">Consider using pie charts only after you have aggregated your data into a few data points.</span></span>  
  
 <span data-ttu-id="7af04-111">На приведенной ниже иллюстрации показана круговая диаграмма, которую предстоит создать.</span><span class="sxs-lookup"><span data-stu-id="7af04-111">The following illustration shows the pie chart you will create.</span></span>  
  
 <span data-ttu-id="7af04-112">![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")</span><span class="sxs-lookup"><span data-stu-id="7af04-112">![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="7af04-113">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="7af04-113">What You Will Learn</span></span>  
 <span data-ttu-id="7af04-114">В этом учебнике рассматривается следующее.</span><span class="sxs-lookup"><span data-stu-id="7af04-114">In this tutorial, you will learn how to:</span></span>  
  
1.  [<span data-ttu-id="7af04-115">Создание круговой диаграммы с помощью мастера диаграмм</span><span class="sxs-lookup"><span data-stu-id="7af04-115">Create a Pie Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="7af04-116">Выбор типа диаграммы</span><span class="sxs-lookup"><span data-stu-id="7af04-116">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="7af04-117">Отображение процентов в каждом срезе</span><span class="sxs-lookup"><span data-stu-id="7af04-117">Display Percentages in Each Slice</span></span>](#Percentages)  
  
4.  [<span data-ttu-id="7af04-118">Объединение небольших срезов круговой диаграммы в один срез</span><span class="sxs-lookup"><span data-stu-id="7af04-118">Combine Small Slices into One Slice</span></span>](#CombineSlices)  
  
5.  [<span data-ttu-id="7af04-119">Настройка эффекта рисования</span><span class="sxs-lookup"><span data-stu-id="7af04-119">Customize the Drawing Effect</span></span>](#DrawingEffect)  
  
6.  [<span data-ttu-id="7af04-120">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="7af04-120">Add a Report Title</span></span>](#Title)  
  
7.  [<span data-ttu-id="7af04-121">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="7af04-121">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="7af04-122">В этом учебнике шаги для мастера объединены в две процедуры.</span><span class="sxs-lookup"><span data-stu-id="7af04-122">In this tutorial, the steps for the wizard are consolidated into two procedures.</span></span> <span data-ttu-id="7af04-123">Пошаговые инструкции по переходу к серверу отчетов, добавлению источника данных и набора данных см. в первом учебнике этой серии: [Учебник. Создание простого табличного отчета (построитель отчетов)](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="7af04-123">For step-by-step instructions about how to browse to a report server, add a data source, and add a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="7af04-124">Предполагаемое время для выполнения заданий этого учебника: 10 минут</span><span class="sxs-lookup"><span data-stu-id="7af04-124">Estimated time to complete this tutorial: 10 minutes</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7af04-125">Требования</span><span class="sxs-lookup"><span data-stu-id="7af04-125">Requirements</span></span>  
 <span data-ttu-id="7af04-126">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="7af04-126">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-pie-chart-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="7af04-127">1. Создание круговой диаграммы с помощью мастера диаграмм</span><span class="sxs-lookup"><span data-stu-id="7af04-127">1. Create a Pie Chart from the Chart Wizard</span></span>  
 <span data-ttu-id="7af04-128">В диалоговом окне «Приступая к работе» создайте внедренный набор данных с помощью мастера диаграмм, выберите общий источник данных и создайте круговую диаграмму.</span><span class="sxs-lookup"><span data-stu-id="7af04-128">From the Getting Started dialog box, use the Chart Wizard to create an embedded dataset, choose a shared data source, and create a pie chart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7af04-129">В этом учебнике запрос уже содержит значения данных, поэтому внешний источник данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="7af04-129">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="7af04-130">В связи с этим запрос получается весьма длинным.</span><span class="sxs-lookup"><span data-stu-id="7af04-130">This makes the query quite long.</span></span> <span data-ttu-id="7af04-131">В рабочей среде запрос не будет содержать данные.</span><span class="sxs-lookup"><span data-stu-id="7af04-131">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="7af04-132">Этот запрос содержит данные только в учебных целях.</span><span class="sxs-lookup"><span data-stu-id="7af04-132">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="7af04-133">Создание нового отчета с диаграммой</span><span class="sxs-lookup"><span data-stu-id="7af04-133">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="7af04-134">Нажмите кнопку **Пуск**, наведите курсор на пункты **Все программы**, **Построитель отчетов Microsoft SQL Server 2012**и выберите пункт **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="7af04-134">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="7af04-135">Откроется диалоговое окно Приступая к работе.</span><span class="sxs-lookup"><span data-stu-id="7af04-135">The Getting Started dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7af04-136"> Если диалоговое окно «Приступая к работе» не откроется, выберите команду **Создать**в меню кнопки «Построитель отчетов».</span><span class="sxs-lookup"><span data-stu-id="7af04-136">If the Getting Started dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="7af04-137">Убедитесь, что на левой панели выбран **Новый отчет** .</span><span class="sxs-lookup"><span data-stu-id="7af04-137">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="7af04-138">На правой панели выберите **Мастер диаграмм**.</span><span class="sxs-lookup"><span data-stu-id="7af04-138">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="7af04-139">На странице **Выбор набора данных** нажмите кнопку **Создать набор данных**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7af04-139">On the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="7af04-140">На странице **Выбор соединения с источником данных** выберите существующий источник данных или перейдите к серверу отчетов и выберите источник данных, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7af04-140">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="7af04-141">Может потребоваться указать имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="7af04-141">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7af04-142">При наличии необходимых разрешений выбор источника данных не имеет существенного значения.</span><span class="sxs-lookup"><span data-stu-id="7af04-142">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="7af04-143">Этот источник данных не будет использоваться для получения данных.</span><span class="sxs-lookup"><span data-stu-id="7af04-143">You will not be getting data from the data source.</span></span> <span data-ttu-id="7af04-144">Дополнительные сведения см. в разделе [Альтернативные способы создания подключения к данным &#40;построитель отчетов&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="7af04-144">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="7af04-145">На странице **Конструирование запроса** нажмите кнопку **изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="7af04-145">On the **Design a Query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="7af04-146">На панель запроса вставьте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="7af04-146">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Advanced Digital Camera' AS Product, CAST(254995.21 AS money) AS Sales  
    UNION SELECT 'Slim Digital Camera' AS Product, CAST(164499.04 AS money) AS Sales  
    UNION SELECT 'SLR Digital Camera' AS Product, CAST(782176.79 AS money) AS Sales  
    UNION SELECT 'Lens Adapter' AS Product, CAST(36333.08 AS money) AS Sales  
    UNION SELECT 'Macro Zoom Lens' AS Product, CAST(40199.3 AS money) AS Sales  
    UNION SELECT 'USB Cable' AS Product, CAST(53245.5 AS money) AS Sales  
    UNION SELECT 'Independent Filmmaker Camcorder' AS Product, CAST(452288.0 AS money) AS Sales  
    UNION SELECT 'Full Frame Digital Camera' AS Product, CAST(247250.85 AS money) AS Sales  
    ```  
  
8.  <span data-ttu-id="7af04-147">Нажмите кнопку Выполнить (**!**), чтобы просмотреть данные, на основе которых будет создана диаграмма (необязательно).</span><span class="sxs-lookup"><span data-stu-id="7af04-147">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="7af04-148">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7af04-148">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="7af04-149">2. Выбор типа диаграммы</span><span class="sxs-lookup"><span data-stu-id="7af04-149">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="7af04-150">Можно выбрать один из различных стандартных типов диаграмм.</span><span class="sxs-lookup"><span data-stu-id="7af04-150">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-pie-chart"></a><span data-ttu-id="7af04-151">Добавление круговой диаграммы</span><span class="sxs-lookup"><span data-stu-id="7af04-151">To add a pie chart</span></span>  
  
1.  <span data-ttu-id="7af04-152">На странице **Выбор типа диаграммы** выберите **круговая диаграмма**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7af04-152">On the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span> <span data-ttu-id="7af04-153">Откроется страница **Расположение полей диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="7af04-153">The **Arrange chart fields** page opens.</span></span>  
  
     <span data-ttu-id="7af04-154">На странице **Расположение полей диаграммы** перетащите поле Product на панель **Категории** .</span><span class="sxs-lookup"><span data-stu-id="7af04-154">On the **Arrange chart fields** page, drag the Product field to the **Categories** pane.</span></span> <span data-ttu-id="7af04-155">Категории определяют номера срезов в круговой диаграмме.</span><span class="sxs-lookup"><span data-stu-id="7af04-155">Categories define the number of slices in the pie chart.</span></span> <span data-ttu-id="7af04-156">В этом примере восемь срезов — по одному для каждого продукта.</span><span class="sxs-lookup"><span data-stu-id="7af04-156">In this example, there will be eight slices, one for each product.</span></span>  
  
2.  <span data-ttu-id="7af04-157">Перетащите поле Sales на панель **Значения** .</span><span class="sxs-lookup"><span data-stu-id="7af04-157">Drag the Sales field to the **Values** pane.</span></span> <span data-ttu-id="7af04-158">Поле Sales представляет объем продаж по подкатегории.</span><span class="sxs-lookup"><span data-stu-id="7af04-158">Sales represents the sales amount for the subcategory.</span></span> <span data-ttu-id="7af04-159">На панели **Значения** отображается выражение `[Sum(Sales)]` , так как на диаграмме отображается агрегат для каждого из продуктов.</span><span class="sxs-lookup"><span data-stu-id="7af04-159">The **Values** pane displays `[Sum(Sales)]` because the chart displays the aggregate for each product.</span></span>  
  
3.  <span data-ttu-id="7af04-160">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7af04-160">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="7af04-161">На панели Стили на странице **Выбор стиля** выберите стиль.</span><span class="sxs-lookup"><span data-stu-id="7af04-161">On the **Choose a style** page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="7af04-162">Стиль задает стиль шрифта, набор цветов и стиль границы.</span><span class="sxs-lookup"><span data-stu-id="7af04-162">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="7af04-163">При выборе стиля на панели просмотра отобразится образец диаграммы с этим стилем.</span><span class="sxs-lookup"><span data-stu-id="7af04-163">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
5.  <span data-ttu-id="7af04-164">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7af04-164">Click **Finish**.</span></span>  
  
     <span data-ttu-id="7af04-165">Диаграмма добавляется в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="7af04-165">The chart is added to the design surface.</span></span>  
  
6.  <span data-ttu-id="7af04-166">Щелкните диаграмму, чтобы отобразить ее маркеры.</span><span class="sxs-lookup"><span data-stu-id="7af04-166">Click the chart to display the chart handles.</span></span> <span data-ttu-id="7af04-167">Перетащите правый нижний угол диаграммы вниз, чтобы увеличить ее размер.</span><span class="sxs-lookup"><span data-stu-id="7af04-167">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span> <span data-ttu-id="7af04-168">Обратите внимание, что область конструктора отчета увеличивается для соответствия размеру диаграммы.</span><span class="sxs-lookup"><span data-stu-id="7af04-168">Note that the report design surface increases in size to accommodate the chart size.</span></span>  
  
7.  <span data-ttu-id="7af04-169">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="7af04-169">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="7af04-170">В отчете отображается круговая диаграмма с восемью срезами, по одному для каждого продукта.</span><span class="sxs-lookup"><span data-stu-id="7af04-170">The report displays the pie chart with eight slices, one for each product.</span></span> <span data-ttu-id="7af04-171">Размер каждого среза представляет продажи для этого продукта.</span><span class="sxs-lookup"><span data-stu-id="7af04-171">The size of each slice represents the sales for that product.</span></span> <span data-ttu-id="7af04-172">Три среза диаграммы достаточно тонкие.</span><span class="sxs-lookup"><span data-stu-id="7af04-172">Three of the slices are quite thin.</span></span>  
  
##  <a name="3-display-percentages-in-each-slice"></a><a name="Percentages"></a><span data-ttu-id="7af04-173">3. Отображение процентных значений в каждом срезе</span><span class="sxs-lookup"><span data-stu-id="7af04-173">3. Display Percentages in Each Slice</span></span>  
 <span data-ttu-id="7af04-174">На каждом срезе круговой диаграммы можно отобразить процент для этого среза относительно полной круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="7af04-174">On each slice of the pie, you can display a percentage for this slice compared to the whole pie.</span></span>  
  
#### <a name="to-display-percentages-in-each-slice-of-the-pie-chart"></a><span data-ttu-id="7af04-175">Отображение процентов в каждом срезе круговой диаграммы</span><span class="sxs-lookup"><span data-stu-id="7af04-175">To display percentages in each slice of the pie chart</span></span>  
  
1.  <span data-ttu-id="7af04-176">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="7af04-176">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="7af04-177">Щелкните правой кнопкой мыши круговую диаграмму и выберите пункт **Отобразить метки данных**.</span><span class="sxs-lookup"><span data-stu-id="7af04-177">Right-click the pie chart and click **Show Data Labels**.</span></span> <span data-ttu-id="7af04-178">На диаграмме появятся метки данных.</span><span class="sxs-lookup"><span data-stu-id="7af04-178">The data labels appear on the chart.</span></span>  
  
3.  <span data-ttu-id="7af04-179">Щелкните правой кнопкой мыши метку и выберите пункт **Свойства метки ряда**.</span><span class="sxs-lookup"><span data-stu-id="7af04-179">Right-click a label, and then click **Series Label Properties**.</span></span>  
  
4.  <span data-ttu-id="7af04-180">В поле данные метки в раскрывающемся списке выберите **#PERCENT**.</span><span class="sxs-lookup"><span data-stu-id="7af04-180">In Label data, from the drop-down box, select **#PERCENT**.</span></span>  
  
     <span data-ttu-id="7af04-181">Чтобы значения отображались в виде процентов, свойство UseValueAsLabel должно иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="7af04-181">To display values as percentages, the UseValueAsLabel property must be false.</span></span> <span data-ttu-id="7af04-182">Если в диалоговом окне **Подтверждение действия** будет предложено задать это значение, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="7af04-182">If you are prompted to set this value in the **Confirm Action** dialog, click **Yes**.</span></span>  
  
5.  <span data-ttu-id="7af04-183">Используемых Чтобы указать, сколько десятичных разрядов отображается в метке, введите, `#PERCENT{Pn}` где *n* — число десятичных разрядов для отображения.</span><span class="sxs-lookup"><span data-stu-id="7af04-183">(Optional) To specify how many decimal places the label shows, type `#PERCENT{Pn}` where *n* is the number of decimal places to display.</span></span> <span data-ttu-id="7af04-184">Например, чтобы не отображать десятичные разряды, введите `#PERCENT{P0}` .</span><span class="sxs-lookup"><span data-stu-id="7af04-184">For example, to display no decimal places, type `#PERCENT{P0}`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7af04-185">Поле**Формат чисел** в диалоговом окне **Свойства метки ряда** не имеет значения, если выбрано форматирование в процентах.</span><span class="sxs-lookup"><span data-stu-id="7af04-185">**Number Format** in the **Series Label Properties** dialog box has no effect when you format percentages.</span></span> <span data-ttu-id="7af04-186">Это форматирует метки в виде процентов, но не вычисляет процент, который представляет каждый срез круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="7af04-186">This formats the labels as percentages, but does not calculate the percentage of the pie that each slice represents.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="7af04-187">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="7af04-187">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="7af04-188">В отчете отображается процент от целого для каждого среза круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="7af04-188">The report displays the percentage of the whole for each pie slice.</span></span>  
  
##  <a name="4-combine-small-slices-into-one-slice"></a><a name="CombineSlices"></a><span data-ttu-id="7af04-189">4. Объединение маленьких срезов в один срез</span><span class="sxs-lookup"><span data-stu-id="7af04-189">4. Combine Small Slices into One Slice</span></span>  
 <span data-ttu-id="7af04-190">Три среза диаграммы достаточно маленькие.</span><span class="sxs-lookup"><span data-stu-id="7af04-190">Three of the slices in the pie are quite small.</span></span> <span data-ttu-id="7af04-191">Можно объединить несколько небольших срезов в один большой срез, представляющий все эти срезы.</span><span class="sxs-lookup"><span data-stu-id="7af04-191">You can combine multiple small slices into one larger slice that represents all of them.</span></span>  
  
#### <a name="to-combine-any-slices-on-the-pie-chart-smaller-than-5-percent-into-one-slice"></a><span data-ttu-id="7af04-192">Объединение срезов круговой диаграммы, имеющих размер менее 5 процентов, в один срез</span><span class="sxs-lookup"><span data-stu-id="7af04-192">To combine any slices on the pie chart smaller than 5 percent into one slice</span></span>  
  
1.  <span data-ttu-id="7af04-193">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="7af04-193">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="7af04-194">На вкладке **вид** в группе **Показать/скрыть** выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7af04-194">On the **View** tab, in the **Show/Hide** group, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="7af04-195">В области конструктора щелкните любой сегмент круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="7af04-195">On the design surface, click on any slice of the pie chart.</span></span> <span data-ttu-id="7af04-196">На панели «Свойства» отображаются свойства ряда.</span><span class="sxs-lookup"><span data-stu-id="7af04-196">The properties for the series are displayed in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="7af04-197">В разделе **Общие** разверните узел **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="7af04-197">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
5.  <span data-ttu-id="7af04-198">Присвойте свойству **CollectedStyle** значение **SingleSlice**.</span><span class="sxs-lookup"><span data-stu-id="7af04-198">Set the **CollectedStyle** property to **SingleSlice**.</span></span>  
  
6.  <span data-ttu-id="7af04-199">Убедитесь в том, что свойство **CollectedThreshold** имеет значение 5.</span><span class="sxs-lookup"><span data-stu-id="7af04-199">Verify that the **CollectedThreshold** property is set to 5.</span></span>  
  
7.  <span data-ttu-id="7af04-200">Убедитесь в том, что свойство **CollectedThresholdUsePercent** имеет значение **True**.</span><span class="sxs-lookup"><span data-stu-id="7af04-200">Verify that the **CollectedThresholdUsePercent** property is set to **True**.</span></span>  
  
8.  <span data-ttu-id="7af04-201">На ленте на вкладке **Главная** нажмите кнопку **выполнить** , чтобы просмотреть отчет.</span><span class="sxs-lookup"><span data-stu-id="7af04-201">On the Ribbon, on the **Home** tab, click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="7af04-202">В условных обозначениях теперь существует категория «Прочее».</span><span class="sxs-lookup"><span data-stu-id="7af04-202">In the legend, the category "Other" now exists.</span></span> <span data-ttu-id="7af04-203">Новый срез круговой диаграммы объединяет все срезы, имеющие размер менее 5%, в один срез, имеющий размер 6% от всей круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="7af04-203">The new pie slice combines all the slices that were under 5% into one slice that is 6% of the whole pie.</span></span>  
  
##  <a name="5-customize-the-drawing-effect"></a><a name="DrawingEffect"></a><span data-ttu-id="7af04-204">5. Настройка эффектов рисования</span><span class="sxs-lookup"><span data-stu-id="7af04-204">5. Customize the Drawing Effect</span></span>  
 <span data-ttu-id="7af04-205">В мастере диаграмм для круговой диаграммы по умолчанию установлен стиль «Аквамарин» с вогнутым эффектом рисования.</span><span class="sxs-lookup"><span data-stu-id="7af04-205">In the Chart Wizard, the default style for a pie chart is Ocean, which features a Concave drawing effect.</span></span> <span data-ttu-id="7af04-206">Эти параметры можно изменить после запуска мастера.</span><span class="sxs-lookup"><span data-stu-id="7af04-206">You can change that after you run the wizard.</span></span>  
  
#### <a name="to-add-a-drawing-effect-to-the-pie-chart"></a><span data-ttu-id="7af04-207">Добавление эффекта рисования к круговой диаграмме</span><span class="sxs-lookup"><span data-stu-id="7af04-207">To add a drawing effect to the pie chart</span></span>  
  
1.  <span data-ttu-id="7af04-208">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="7af04-208">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="7af04-209">Если панель свойств еще не открыта, на вкладке **вид** выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="7af04-209">If the Properties pane is not already opened, on the **View** tab, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="7af04-210">Дважды щелкните саму круговую диаграмму.</span><span class="sxs-lookup"><span data-stu-id="7af04-210">Double-click the pie chart itself.</span></span> <span data-ttu-id="7af04-211">На панели свойств отобразятся свойства рядов для круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="7af04-211">The series properties for the pie chart are shown in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="7af04-212">На панели «Свойства» разверните узел **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="7af04-212">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
5.  <span data-ttu-id="7af04-213">Задайте для **параметр PieDrawingStyle** значение **софтедже**.</span><span class="sxs-lookup"><span data-stu-id="7af04-213">Set the **PieDrawingStyle** to **SoftEdge**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7af04-214">Эффекты рисования и трехмерные эффекты являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="7af04-214">Drawing effects and three-dimensional effects are exclusive options.</span></span> <span data-ttu-id="7af04-215">Если к диаграмме применены трехмерные эффекты, **параметр PieDrawingStyle** недоступен на панели «Свойства».</span><span class="sxs-lookup"><span data-stu-id="7af04-215">If a chart has three-dimensional effects applied, **PieDrawingStyle** is not available on the Properties pane.</span></span>  
  
6.  <span data-ttu-id="7af04-216">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="7af04-216">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="7af04-217">На следующей иллюстрации показана круговая диаграмма с эффектом размытых краев.</span><span class="sxs-lookup"><span data-stu-id="7af04-217">The following illustration shows the pie chart with the soft edge effect.</span></span>  
  
 <span data-ttu-id="7af04-218">![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")</span><span class="sxs-lookup"><span data-stu-id="7af04-218">![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")</span></span>  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="7af04-219">6. Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="7af04-219">6. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="7af04-220">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="7af04-220">To add a report title</span></span>  
  
1.  <span data-ttu-id="7af04-221">В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.</span><span class="sxs-lookup"><span data-stu-id="7af04-221">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="7af04-222">Введите **Продажи фотоаппаратов и видеокамер**, нажмите клавишу ВВОД, а затем введите **В процентах от общего объема продаж**, после чего он будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7af04-222">Type **Camera and Camcorder Sales**, press ENTER, and then type **As a Percentage of Total Sales**, so it looks like this:</span></span>  
  
     <span data-ttu-id="7af04-223">**Продажи фотоаппаратов и видеокамер**</span><span class="sxs-lookup"><span data-stu-id="7af04-223">**Camera and Camcorder Sales**</span></span>  
  
     <span data-ttu-id="7af04-224">**В процентах от общего объема продаж**</span><span class="sxs-lookup"><span data-stu-id="7af04-224">**As a Percentage of Total Sales**</span></span>  
  
3.  <span data-ttu-id="7af04-225">Выберите **продажи камеры и**видеокамеры и нажмите кнопку **полужирный** в разделе **Шрифт** на вкладке ленты **Главная** .</span><span class="sxs-lookup"><span data-stu-id="7af04-225">Select **Camera and Camcorder Sales**, and click the **Bold** button from the **Font** section of the **Home** tab of the ribbon.</span></span>  
  
4.  <span data-ttu-id="7af04-226">Выберите в **процентах от общего объема продаж**, а в разделе **Шрифт** на вкладке **Главная** установите размер шрифта равным **10**.</span><span class="sxs-lookup"><span data-stu-id="7af04-226">Select **As a Percentage of Total Sales**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
5.  <span data-ttu-id="7af04-227">Может потребоваться увеличить высоту текстового поля «Заголовок» для соответствия размерам двух строк текста (необязательно).</span><span class="sxs-lookup"><span data-stu-id="7af04-227">(Optional) You may need to make the Title text box taller to accommodate the two lines of text.</span></span>  
  
     <span data-ttu-id="7af04-228">Данный заголовок появится в верхней части отчета.</span><span class="sxs-lookup"><span data-stu-id="7af04-228">This title will appear at the top of the report.</span></span> <span data-ttu-id="7af04-229">При отсутствии верхнего колонтитула страницы элементы в верхней части текста отчета выполняют роль заголовка отчета.</span><span class="sxs-lookup"><span data-stu-id="7af04-229">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
6.  <span data-ttu-id="7af04-230">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="7af04-230">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="7af04-231">7. Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="7af04-231">7. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="7af04-232">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="7af04-232">To save the report</span></span>  
  
1.  <span data-ttu-id="7af04-233">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="7af04-233">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="7af04-234">Нажмите кнопку «Построитель отчетов» и выберите **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="7af04-234">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="7af04-235">В поле **Имя**введите **Круговая диаграмма продаж**.</span><span class="sxs-lookup"><span data-stu-id="7af04-235">In **Name**, type **Sales Pie Chart**.</span></span>  
  
4.  <span data-ttu-id="7af04-236">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7af04-236">Click **Save**.</span></span>  
  
 <span data-ttu-id="7af04-237">Отчет будет сохранен на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="7af04-237">Your report is saved on the report server.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7af04-238">Next Steps</span><span class="sxs-lookup"><span data-stu-id="7af04-238">Next Steps</span></span>  
 <span data-ttu-id="7af04-239">Учебник «Добавление круговой диаграммы в отчет» успешно завершен.</span><span class="sxs-lookup"><span data-stu-id="7af04-239">You have successfully completed the Adding a Pie Chart to Your Report tutorial.</span></span> <span data-ttu-id="7af04-240">Дополнительные сведения о диаграммах см. в разделах [Диаграммы (построитель отчетов и службы SSRS)](report-design/charts-report-builder-and-ssrs.md) и [Спарклайны и гистограммы (построитель отчетов и службы SSRS)](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7af04-240">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7af04-241">См. также:</span><span class="sxs-lookup"><span data-stu-id="7af04-241">See Also</span></span>  
 <span data-ttu-id="7af04-242">[Учебники &#40;построитель отчетов&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="7af04-242">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="7af04-243">Построитель отчетов в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7af04-243">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
