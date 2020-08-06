---
title: Учебник. Добавление гистограммы к отчету (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 63480059-b7b9-44b5-9d7f-91780db708b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ef3b3f2872c2f8181296bb05337ca18975ac2f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737862"
---
# <a name="tutorial-add-a-column-chart-to-your-report-report-builder"></a><span data-ttu-id="9da2a-102">Учебник. Добавление гистограммы к отчету (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="9da2a-102">Tutorial: Add a Column Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="9da2a-103">Гистограмма отображает ряды в виде набора вертикальных прямоугольников, сгруппированных по категориям.</span><span class="sxs-lookup"><span data-stu-id="9da2a-103">A column chart displays a series as a set of vertical bars that are grouped by category.</span></span> <span data-ttu-id="9da2a-104">Гистограмма может быть полезна в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="9da2a-104">A column chart can be useful to:</span></span>  
  
-   <span data-ttu-id="9da2a-105">отображение изменений данных в течение периода времени;</span><span class="sxs-lookup"><span data-stu-id="9da2a-105">Show data changes over a period of time.</span></span>  
  
-   <span data-ttu-id="9da2a-106">сравнение относительных значений нескольких рядов.</span><span class="sxs-lookup"><span data-stu-id="9da2a-106">Compare the relative value of multiple series.</span></span>  
  
-   <span data-ttu-id="9da2a-107">отображение скользящего среднего для показа трендов.</span><span class="sxs-lookup"><span data-stu-id="9da2a-107">Display a moving average to show trends.</span></span>  
  
 <span data-ttu-id="9da2a-108">На следующем рисунке показывается создаваемая столбцовая диаграмма со скользящим средним.</span><span class="sxs-lookup"><span data-stu-id="9da2a-108">The following illustration shows the column chart you will create, with a moving average.</span></span>  
  
 <span data-ttu-id="9da2a-109">![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")</span><span class="sxs-lookup"><span data-stu-id="9da2a-109">![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="9da2a-110">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="9da2a-110">What You Will Learn</span></span>  
 <span data-ttu-id="9da2a-111">В этом учебнике рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="9da2a-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="9da2a-112">Создание диаграммы с помощью мастера диаграмм</span><span class="sxs-lookup"><span data-stu-id="9da2a-112">Create a Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="9da2a-113">Выбор типа диаграммы</span><span class="sxs-lookup"><span data-stu-id="9da2a-113">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="9da2a-114">Форматирование и задание меток для горизонтальной оси</span><span class="sxs-lookup"><span data-stu-id="9da2a-114">Format and Label the Horizontal Axis</span></span>](#Horizontal)  
  
4.  [<span data-ttu-id="9da2a-115">Перемещение условных обозначений</span><span class="sxs-lookup"><span data-stu-id="9da2a-115">Move the Legend</span></span>](#Legend)  
  
5.  [<span data-ttu-id="9da2a-116">Задание заголовка для диаграммы</span><span class="sxs-lookup"><span data-stu-id="9da2a-116">Title the Chart</span></span>](#ChartTitle)  
  
6.  [<span data-ttu-id="9da2a-117">Форматирование и задание меток для вертикальной оси</span><span class="sxs-lookup"><span data-stu-id="9da2a-117">Format and Label the Vertical Axis</span></span>](#Vertical)  
  
7.  [<span data-ttu-id="9da2a-118">Добавление скользящего среднего</span><span class="sxs-lookup"><span data-stu-id="9da2a-118">Add a Moving Average</span></span>](#Average)  
  
8.  [<span data-ttu-id="9da2a-119">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="9da2a-119">Add a Report Title</span></span>](#Title)  
  
9. [<span data-ttu-id="9da2a-120">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="9da2a-120">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="9da2a-121">В этом учебнике шаги работы с мастером объединены в одну процедуру.</span><span class="sxs-lookup"><span data-stu-id="9da2a-121">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="9da2a-122">Пошаговые инструкции по переходу к серверу отчетов, выбору источника данных и созданию набора данных см. в первом учебнике этой серии: [Учебник. Создание простого табличного отчета &#40;построитель отчетов&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="9da2a-122">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="9da2a-123">Предполагаемое время для выполнения заданий этого учебника: 15 минут.</span><span class="sxs-lookup"><span data-stu-id="9da2a-123">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9da2a-124">Требования</span><span class="sxs-lookup"><span data-stu-id="9da2a-124">Requirements</span></span>  
 <span data-ttu-id="9da2a-125">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="9da2a-125">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-chart-report-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="9da2a-126">1. Создание отчета с диаграммой с помощью мастера диаграмм</span><span class="sxs-lookup"><span data-stu-id="9da2a-126">1. Create a Chart Report from the Chart Wizard</span></span>  
 <span data-ttu-id="9da2a-127">В диалоговом окне **Начало работы** с помощью мастера диаграмм создайте внедренный набор данных, выберите общий источник и Создайте гистограмму.</span><span class="sxs-lookup"><span data-stu-id="9da2a-127">From the **Getting Started** dialog box, use the Chart Wizard to create an embedded dataset, choose a shared data source, and create a column chart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9da2a-128">В этом учебнике запрос уже содержит значения данных, поэтому внешний источник данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="9da2a-128">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="9da2a-129">В связи с этим запрос получается весьма длинным.</span><span class="sxs-lookup"><span data-stu-id="9da2a-129">This makes the query quite long.</span></span> <span data-ttu-id="9da2a-130">В рабочей среде запрос не будет содержать данные.</span><span class="sxs-lookup"><span data-stu-id="9da2a-130">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="9da2a-131">Этот запрос содержит данные только в учебных целях.</span><span class="sxs-lookup"><span data-stu-id="9da2a-131">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="9da2a-132">Создание нового отчета с диаграммой</span><span class="sxs-lookup"><span data-stu-id="9da2a-132">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="9da2a-133">Нажмите кнопку **Пуск**, наведите курсор на пункты **Все программы**, **Построитель отчетов Microsoft SQL Server 2012**и выберите пункт **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-133">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="9da2a-134">Откроется диалоговое окно **Начало работы** .</span><span class="sxs-lookup"><span data-stu-id="9da2a-134">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9da2a-135">Если диалоговое окно **Начало работы** не отображается, на кнопке **Построитель отчетов** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-135">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="9da2a-136">Убедитесь, что на левой панели выбран **Новый отчет** .</span><span class="sxs-lookup"><span data-stu-id="9da2a-136">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="9da2a-137">На правой панели выберите **Мастер диаграмм**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-137">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="9da2a-138">На **странице Выбор набора данных**щелкните **создать набор данных**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-138">On the **Choose a dataset page**, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="9da2a-139">На странице **Выбор соединения с источником данных** выберите существующий источник данных или перейдите к серверу отчетов и выберите источник данных, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="9da2a-140">Может потребоваться указать имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="9da2a-140">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9da2a-141">При наличии необходимых разрешений выбор источника данных не имеет существенного значения.</span><span class="sxs-lookup"><span data-stu-id="9da2a-141">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="9da2a-142">Этот источник данных не будет использоваться для получения данных.</span><span class="sxs-lookup"><span data-stu-id="9da2a-142">You will not be getting data from the data source.</span></span> <span data-ttu-id="9da2a-143">Дополнительные сведения см. в разделе [Альтернативные способы создания подключения к данным &#40;построитель отчетов&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="9da2a-143">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="9da2a-144">На странице **Проектирование запроса** нажмите кнопку **Изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-144">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="9da2a-145">На панель запроса вставьте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="9da2a-145">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-01' AS date) AS SalesDate, CAST(54995.21 AS money) AS Sales  
    UNION SELECT CAST('2009-01-05' AS date) AS SalesDate, CAST(64499.04 AS money) AS Sales  
    UNION SELECT CAST('2009-02-11' AS date) AS SalesDate, CAST(37821.79 AS money) AS Sales  
    UNION SELECT CAST('2009-03-18' AS date) AS SalesDate, CAST(53633.08 AS money) AS Sales  
    UNION SELECT CAST('2009-04-23' AS date) AS SalesDate, CAST(24019.3 AS money) AS Sales  
    UNION SELECT CAST('2009-05-01' AS date) AS SalesDate, CAST(93245.5 AS money) AS Sales  
    UNION SELECT CAST('2009-06-06' AS date) AS SalesDate, CAST(55288.0 AS money) AS Sales  
    UNION SELECT CAST('2009-06-16' AS date) AS SalesDate, CAST(68733.5 AS money) AS Sales  
    UNION SELECT CAST('2009-07-16' AS date) AS SalesDate, CAST(24750.85 AS money) AS Sales  
    UNION SELECT CAST('2009-08-23' AS date) AS SalesDate, CAST(43452.3 AS money) AS Sales  
    UNION SELECT CAST('2009-09-24' AS date) AS SalesDate, CAST(58656. AS money) AS Sales  
    UNION SELECT CAST('2009-10-15' AS date) AS SalesDate, CAST(44583. AS money) AS Sales  
    UNION SELECT CAST('2009-11-21' AS date) AS SalesDate, CAST(81568. AS money) AS Sales  
    UNION SELECT CAST('2009-12-15' AS date) AS SalesDate, CAST(45973. AS money) AS Sales  
    UNION SELECT CAST('2009-12-26' AS date) AS SalesDate, CAST(96357. AS money) AS Sales  
    UNION SELECT CAST('2009-12-31' AS date) AS SalesDate, CAST(81946. AS money) AS Sales  
    ```  
  
8.  <span data-ttu-id="9da2a-146">Нажмите кнопку Выполнить (**!**), чтобы просмотреть данные, на основе которых будет создана диаграмма (необязательно).</span><span class="sxs-lookup"><span data-stu-id="9da2a-146">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="9da2a-147">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-147">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="9da2a-148">2. Выбор типа диаграммы</span><span class="sxs-lookup"><span data-stu-id="9da2a-148">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="9da2a-149">Можно выбрать один из различных стандартных типов диаграмм.</span><span class="sxs-lookup"><span data-stu-id="9da2a-149">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-column-chart"></a><span data-ttu-id="9da2a-150">Добавление гистограммы</span><span class="sxs-lookup"><span data-stu-id="9da2a-150">To add a column chart</span></span>  
  
1.  <span data-ttu-id="9da2a-151">На странице **Выбор типа диаграммы** в качестве типа диаграммы по умолчанию задана гистограмма.</span><span class="sxs-lookup"><span data-stu-id="9da2a-151">On the **Choose a chart type** page, the column chart is the default chart type.</span></span> <span data-ttu-id="9da2a-152">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-152">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="9da2a-153">На странице **Расположение полей диаграммы** перетащите поле "ДатаПродаж" в **Категории**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-153">On the **Arrange chart fields** page, drag the SalesDate field to **Categories**.</span></span> <span data-ttu-id="9da2a-154">Категории отображаются по горизонтальной оси.</span><span class="sxs-lookup"><span data-stu-id="9da2a-154">Categories display on the horizontal axis.</span></span>  
  
3.  <span data-ttu-id="9da2a-155">Перетащите поле "Продажи" в область **Значения**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-155">Drag the Sales field to **Values**.</span></span> <span data-ttu-id="9da2a-156">В поле **Значения** отображается выражение Sum(Продажи), так как общее значение строки суммируется для каждой даты заказа на продажу.</span><span class="sxs-lookup"><span data-stu-id="9da2a-156">The **Values** box displays Sum(Sales) because the sum of the sales total value is aggregated for each date.</span></span> <span data-ttu-id="9da2a-157">Значения отображаются по вертикальной оси.</span><span class="sxs-lookup"><span data-stu-id="9da2a-157">Values display on the vertical axis.</span></span>  
  
4.  <span data-ttu-id="9da2a-158">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-158">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="9da2a-159">На странице **Выбор стиля** в поле Стили выберите стиль.</span><span class="sxs-lookup"><span data-stu-id="9da2a-159">On the **Choose a Style** page, in the Styles box, select a style.</span></span>  
  
     <span data-ttu-id="9da2a-160">Стиль задает стиль шрифта, набор цветов и стиль границы.</span><span class="sxs-lookup"><span data-stu-id="9da2a-160">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="9da2a-161">При выборе стиля на панели просмотра отобразится образец диаграммы с этим стилем.</span><span class="sxs-lookup"><span data-stu-id="9da2a-161">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
6.  <span data-ttu-id="9da2a-162">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-162">Click **Finish**.</span></span>  
  
     <span data-ttu-id="9da2a-163">Диаграмма добавляется в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="9da2a-163">The chart is added to the design surface.</span></span>  
  
7.  <span data-ttu-id="9da2a-164">Щелкните диаграмму, чтобы отобразить ее маркеры.</span><span class="sxs-lookup"><span data-stu-id="9da2a-164">Click the chart to display the chart handles.</span></span> <span data-ttu-id="9da2a-165">Перетащите правый нижний угол диаграммы вниз, чтобы увеличить ее размер.</span><span class="sxs-lookup"><span data-stu-id="9da2a-165">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span> <span data-ttu-id="9da2a-166">Обратите внимание, что область конструктора отчета увеличивается для соответствия размеру диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9da2a-166">Note that the report design surface increases in size to accommodate the chart size.</span></span>  
  
8.  <span data-ttu-id="9da2a-167">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-167">Click **Run** to preview the report.</span></span>  
  
##  <a name="3-format-and-label-the-horizontal-axis"></a><a name="Horizontal"></a><span data-ttu-id="9da2a-168">3. форматирование и пометка горизонтальной оси</span><span class="sxs-lookup"><span data-stu-id="9da2a-168">3. Format and Label the Horizontal Axis</span></span>  
 <span data-ttu-id="9da2a-169">По умолчанию по горизонтальной оси отображаются значения в общем формате, который автоматически масштабируется в соответствии с размером диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9da2a-169">By default, the horizontal axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-a-date-on-the-horizontal-axis"></a><span data-ttu-id="9da2a-170">Форматирование даты по горизонтальной оси</span><span class="sxs-lookup"><span data-stu-id="9da2a-170">To format a date on the horizontal axis</span></span>  
  
1.  <span data-ttu-id="9da2a-171">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-171">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="9da2a-172">Щелкните правой кнопкой мыши горизонтальную ось и выберите пункт **Свойства горизонтальной оси**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-172">Right-click the horizontal axis, and then click **Horizontal Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="9da2a-173">Выберите **Число**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-173">Click **Number**.</span></span>  
  
4.  <span data-ttu-id="9da2a-174">В списке **Категория**выберите **Дата**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-174">In **Category**, select **Date**.</span></span>  
  
5.  <span data-ttu-id="9da2a-175">В поле **Тип** выберите **31 января 2000 года**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-175">In the **Type** box, select **31 Jan 2000**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="9da2a-176">На вкладке Главная нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-176">On the Home tab, click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="9da2a-177">Дата отображается в выбранном формате дат.</span><span class="sxs-lookup"><span data-stu-id="9da2a-177">The date displays in the date format that you selected.</span></span> <span data-ttu-id="9da2a-178">Обратите внимание, что на горизонтальной оси диаграммы имеются метки не для всех категорий.</span><span class="sxs-lookup"><span data-stu-id="9da2a-178">Notice that the chart does not label every category on the horizontal axis.</span></span> <span data-ttu-id="9da2a-179">По умолчанию включаются только метки, расположенные рядом с осью.</span><span class="sxs-lookup"><span data-stu-id="9da2a-179">By default, only labels that fit next to the axis are included.</span></span>  
  
 <span data-ttu-id="9da2a-180">Можно настроить отображение меток, повернув их и указав интервал.</span><span class="sxs-lookup"><span data-stu-id="9da2a-180">You can customize the label display by rotating the labels and specifying the interval.</span></span>  
  
#### <a name="to-rotate-the-axis-labels-and-change-the-display-interval-along-the-horizontal-axis"></a><span data-ttu-id="9da2a-181">Поворот меток осей и изменение интервала отображения по горизонтальной оси</span><span class="sxs-lookup"><span data-stu-id="9da2a-181">To rotate the axis labels and change the display interval along the horizontal axis</span></span>  
  
1.  <span data-ttu-id="9da2a-182">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-182">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="9da2a-183">Щелкните правой кнопкой мыши заголовок горизонтальной оси и выберите команду **отобразить заголовок оси** , чтобы удалить заголовок.</span><span class="sxs-lookup"><span data-stu-id="9da2a-183">Right-click the horizontal axis title, and then click **Show Axis Title** to remove the title.</span></span> <span data-ttu-id="9da2a-184">Так как на горизонтальной оси отображаются даты, заголовок не нужен.</span><span class="sxs-lookup"><span data-stu-id="9da2a-184">Because the horizontal axis displays dates, the title is not needed.</span></span>  
  
3.  <span data-ttu-id="9da2a-185">Щелкните правой кнопкой мыши горизонтальную ось и выберите пункт **Свойства горизонтальной оси**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-185">Right-click the horizontal axis and then click **Horizontal Axis Properties**.</span></span>  
  
4.  <span data-ttu-id="9da2a-186">На странице **Параметры оси** в разделе **Диапазон оси и интервал**введите **3** для параметра **интервал**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-186">In the **Axis Options** page under **Axis range and interval**, type **3** for **Interval**.</span></span> <span data-ttu-id="9da2a-187">На диаграмме отобразится каждая третья дата.</span><span class="sxs-lookup"><span data-stu-id="9da2a-187">The chart will display every third date.</span></span>  
  
5.  <span data-ttu-id="9da2a-188">Щелкните **Метки**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-188">Click **Labels**.</span></span>  
  
6.  <span data-ttu-id="9da2a-189">В окне **изменение параметров автоподбора метки оси**установите флажок Отключить автоподбор **размера**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-189">In **Change axis label auto-fit options**, select **Disable auto-fit**.</span></span>  
  
7.  <span data-ttu-id="9da2a-190">В поле **Угол поворота метки**выберите значение **-90**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-190">In **Label rotation angle**, select **-90**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="9da2a-191">Образец текста для горизонтальной оси поворачивается на 90 градусов.</span><span class="sxs-lookup"><span data-stu-id="9da2a-191">The sample text for the horizontal axis rotates by 90 degrees.</span></span>  
  
9. <span data-ttu-id="9da2a-192">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-192">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="9da2a-193">На диаграмме метки поворачиваются, причем отображаются метки для каждой третьей даты.</span><span class="sxs-lookup"><span data-stu-id="9da2a-193">On the chart, the labels are rotated and the label for every third date is shown.</span></span>  
  
##  <a name="4-move-the-legend"></a><a name="Legend"></a><span data-ttu-id="9da2a-194">4. Перемещение условных обозначений</span><span class="sxs-lookup"><span data-stu-id="9da2a-194">4. Move the Legend</span></span>  
 <span data-ttu-id="9da2a-195">Условные обозначения автоматически создаются на основе данных категорий и рядов.</span><span class="sxs-lookup"><span data-stu-id="9da2a-195">The legend is automatically created from category and series data.</span></span>  
  
#### <a name="to-move-the-legend-below-the-chart-area-of-a-column-chart"></a><span data-ttu-id="9da2a-196">Перемещение условных обозначений под область гистограммы</span><span class="sxs-lookup"><span data-stu-id="9da2a-196">To move the legend below the chart area of a column chart</span></span>  
  
1.  <span data-ttu-id="9da2a-197">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-197">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="9da2a-198">Щелкните правой кнопкой мыши условные обозначения на диаграмме и выберите пункт **Свойства условных обозначений**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-198">Right-click the legend on the chart, and then click **Legend Properties**.</span></span>  
  
3.  <span data-ttu-id="9da2a-199">Выберите другую положение для **макета и расположения**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-199">For **Layout and Position**, select a different position.</span></span> <span data-ttu-id="9da2a-200">Например, можно выбрать параметр, соответствующий расположению посередине в нижней части.</span><span class="sxs-lookup"><span data-stu-id="9da2a-200">For example, set the position to the middle bottom option.</span></span>  
  
     <span data-ttu-id="9da2a-201">Если условные обозначения перемесить в верхнюю или нижнюю часть диаграммы, их макет изменится с вертикального на горизонтальный.</span><span class="sxs-lookup"><span data-stu-id="9da2a-201">When the legend is placed at the top or bottom of a chart, the layout of the legend changes from vertical to horizontal.</span></span> <span data-ttu-id="9da2a-202">Можно выбрать другой макет в раскрывающемся списке **Макет** .</span><span class="sxs-lookup"><span data-stu-id="9da2a-202">You can select a different layout from the **Layout** drop-down list.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="9da2a-203">(Необязательно) Так как в данном учебнике имеется только одна категория, условные обозначения не требуются.</span><span class="sxs-lookup"><span data-stu-id="9da2a-203">(Optional) Because there is only one category in this tutorial, the legend is not needed.</span></span> <span data-ttu-id="9da2a-204">Чтобы удалить условные обозначения, щелкните условные обозначения правой кнопкой мыши и выберите пункт **удалить условные обозначения**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-204">To remove the legend, right-click the legend and then click **Delete Legend**.</span></span>  
  
6.  <span data-ttu-id="9da2a-205">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-205">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-title-the-chart"></a><a name="ChartTitle"></a><span data-ttu-id="9da2a-206">5. заголовком диаграммы</span><span class="sxs-lookup"><span data-stu-id="9da2a-206">5. Title the Chart</span></span>  
  
#### <a name="to-change-the-chart-title-above-the-chart-area"></a><span data-ttu-id="9da2a-207">Изменение заголовка диаграммы над областью диаграммы</span><span class="sxs-lookup"><span data-stu-id="9da2a-207">To change the chart title above the chart area</span></span>  
  
1.  <span data-ttu-id="9da2a-208">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-208">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="9da2a-209">Выберите **заголовок диаграммы** "слова" в верхней части диаграммы, а затем введите следующий текст: " **Хранение итогов заказов на продажу**".</span><span class="sxs-lookup"><span data-stu-id="9da2a-209">Select the words **Chart Title** at the top of the chart, and then type the following text: **Store Sales Order Totals**.</span></span>  
  
3.  <span data-ttu-id="9da2a-210">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-210">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-format-and-label-the-vertical-axis"></a><a name="Vertical"></a><span data-ttu-id="9da2a-211">6. форматирование и пометка вертикальной оси</span><span class="sxs-lookup"><span data-stu-id="9da2a-211">6. Format and Label the Vertical Axis</span></span>  
 <span data-ttu-id="9da2a-212">По умолчанию по вертикальной оси отображаются значения в общем формате, который автоматически масштабируется в соответствии с размером диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9da2a-212">By default, the vertical axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-as-currency-the-numbers-on-the-vertical-axis"></a><span data-ttu-id="9da2a-213">Форматирование чисел по вертикальной оси для представления валюты</span><span class="sxs-lookup"><span data-stu-id="9da2a-213">To format as currency the numbers on the vertical axis</span></span>  
  
1.  <span data-ttu-id="9da2a-214">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-214">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="9da2a-215">Чтобы выбрать метки, дважды щелкните метки на вертикальной оси сбоку от диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9da2a-215">Double-click the labels on the vertical axis along the side of the chart to select them.</span></span>  
  
3.  <span data-ttu-id="9da2a-216">На ленте на вкладке **Главная** в группе **число** нажмите кнопку **Валюта** .</span><span class="sxs-lookup"><span data-stu-id="9da2a-216">On the ribbon, on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="9da2a-217">Метки оси изменятся, отображая формат валюты.</span><span class="sxs-lookup"><span data-stu-id="9da2a-217">The axis labels change to show the currency format.</span></span>  
  
4.  <span data-ttu-id="9da2a-218">На ленте на вкладке **Главная** в группе **число** нажмите кнопку **уменьшить десятичную дробь** два раза, чтобы отобразить число, округленное до ближайшего доллара.</span><span class="sxs-lookup"><span data-stu-id="9da2a-218">On the ribbon, on the **Home** tab, in the **Number** group, click the **Decrease Decimal** button two times, to show the number rounded to the nearest dollar.</span></span>  
  
5.  <span data-ttu-id="9da2a-219">Щелкните правой кнопкой мыши вертикальную ось и выберите пункт **Свойства вертикальной оси**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-219">Right-click the vertical axis and click **Vertical Axis Properties**.</span></span>  
  
6.  <span data-ttu-id="9da2a-220">Выберите **Число**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-220">Click **Number**.</span></span> <span data-ttu-id="9da2a-221">Обратите внимание, что **Валюта** уже выбрана в поле **Категория** , а **десятичные разряды** уже **равны 0** (нулю).</span><span class="sxs-lookup"><span data-stu-id="9da2a-221">Note that **Currency** is already selected in the **Category** box, and **Decimal places** is already **0** (zero).</span></span>  
  
7.  <span data-ttu-id="9da2a-222">В поле **Показывать значения в** выберите **тысячи**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-222">In the **Show Values in** box, click **Thousands**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="9da2a-223">Щелкните правой кнопкой мыши заголовок вертикальной оси вдоль стороны диаграммы и выберите пункт **Свойства заголовка оси**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-223">Right-click the vertical axis title along the side of the chart and click **Axis Title Properties**.</span></span>  
  
10. <span data-ttu-id="9da2a-224">Замените текст в поле " **текст заголовка** " следующим текстом: **объем продаж (в тысячах)**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-224">Replace the text in the **Title text** field with the following text: **Sales Total (in Thousands)**.</span></span> <span data-ttu-id="9da2a-225">Можно также указать несколько параметров, связанных с форматом заголовка.</span><span class="sxs-lookup"><span data-stu-id="9da2a-225">You can also specify a variety of options related to how the title is formatted.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="9da2a-226">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-226">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-add-a-moving-average"></a><a name="Average"></a><span data-ttu-id="9da2a-227">7. Добавление скользящего среднего</span><span class="sxs-lookup"><span data-stu-id="9da2a-227">7. Add a Moving Average</span></span>  
  
#### <a name="to-add-a-moving-average"></a><span data-ttu-id="9da2a-228">Добавление скользящего среднего</span><span class="sxs-lookup"><span data-stu-id="9da2a-228">To add a moving average</span></span>  
  
1.  <span data-ttu-id="9da2a-229">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-229">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="9da2a-230">Дважды щелкните диаграмму, чтобы отобразить панель **Данные диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="9da2a-230">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="9da2a-231">Щелкните правой кнопкой мыши поле **[Sum (Sales)]** , которое находится в области **значения** , и выберите команду **Добавить вычисляемый ряд**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-231">Right-click the **[Sum(Sales)]** field that is in the **Values** area, and then click **Add Calculated Series**.</span></span>  
  
4.  <span data-ttu-id="9da2a-232">Убедитесь в том, что в поле **Формула**выбрано **Скользящее среднее** .</span><span class="sxs-lookup"><span data-stu-id="9da2a-232">In **Formula**, verify that **Moving average** is selected.</span></span>  
  
5.  <span data-ttu-id="9da2a-233">В разделе **Задание параметров формулы**для параметра **Период**задайте значение **4**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-233">In **Set Formula Parameters**, for **Period**, select **4**.</span></span>  
  
6.  <span data-ttu-id="9da2a-234">Нажмите кнопку **граница**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-234">Click **Border**.</span></span>  
  
7.  <span data-ttu-id="9da2a-235">В окне **толщина линии**выберите **3 пунктов**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-235">In **Line width**, select **3pt**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="9da2a-236">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-236">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="9da2a-237">На диаграмме отображается линия, показывающая скользящее среднее для общих продаж по дате, усредненное по каждым четырем дням.</span><span class="sxs-lookup"><span data-stu-id="9da2a-237">The chart displays a line that shows the moving average for total sales by date, averaged over every four dates.</span></span>  
  
##  <a name="8-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="9da2a-238">8. Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="9da2a-238">8. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="9da2a-239">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="9da2a-239">To add a report title</span></span>  
  
1.  <span data-ttu-id="9da2a-240">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-240">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="9da2a-241">В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-241">On the design surface, click **Click to add title**.</span></span>  
  
3.  <span data-ttu-id="9da2a-242">Введите **Диаграмма продаж**, нажмите клавишу ВВОД, а затем введите **Январь 2009 декабря**, чтобы он выглядел следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9da2a-242">Type **Sales Chart**, press ENTER, and then type **January to December 2009**, so it looks like this:</span></span>  
  
     <span data-ttu-id="9da2a-243">**Диаграмма продаж**</span><span class="sxs-lookup"><span data-stu-id="9da2a-243">**Sales Chart**</span></span>  
  
     <span data-ttu-id="9da2a-244">**Январь — декабрь 2009 г.**</span><span class="sxs-lookup"><span data-stu-id="9da2a-244">**January to December 2009**</span></span>  
  
4.  <span data-ttu-id="9da2a-245">Выберите **Диаграмма продаж**и нажмите кнопку **полужирный** в разделе **Шрифт** на вкладке **Главная** ленты.</span><span class="sxs-lookup"><span data-stu-id="9da2a-245">Select **Sales Chart**, and click the **Bold** button in the **Font** section on the **Home** tab of the ribbon.</span></span>  
  
5.  <span data-ttu-id="9da2a-246">Выберите **Январь до декабря 2009**, а в разделе **Шрифт** на вкладке **Главная** установите размер шрифта равным **10**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-246">Select **January to December 2009**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
6.  <span data-ttu-id="9da2a-247">Используемых Может потребоваться увеличить высоту текстового поля **заголовка** , чтобы разместить две строки текста, выжимая стрелки двойных стрелок при щелчке по середине нижнего края.</span><span class="sxs-lookup"><span data-stu-id="9da2a-247">(Optional) You may need to make the **Title** text box taller to accommodate the two lines of text by pulling down on the double-headed arrows when you click in the middle of the bottom edge.</span></span>  
  
     <span data-ttu-id="9da2a-248">Данный заголовок появится в верхней части отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-248">This title will appear at the top of the report.</span></span> <span data-ttu-id="9da2a-249">При отсутствии верхнего колонтитула страницы элементы в верхней части текста отчета выполняют роль заголовка отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-249">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
7.  <span data-ttu-id="9da2a-250">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-250">Click **Run** to preview the report.</span></span>  
  
##  <a name="9-save-the-report"></a><a name="Save"></a><span data-ttu-id="9da2a-251">9. Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="9da2a-251">9. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="9da2a-252">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="9da2a-252">To save the report</span></span>  
  
1.  <span data-ttu-id="9da2a-253">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="9da2a-253">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="9da2a-254">Нажмите кнопку «Построитель отчетов» и выберите **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-254">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="9da2a-255">В поле **Имя**введите **Гистограмма заказов на продажу**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-255">In **Name**, type **Sales Order Column Chart**.</span></span>  
  
4.  <span data-ttu-id="9da2a-256">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9da2a-256">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9da2a-257">Next Steps</span><span class="sxs-lookup"><span data-stu-id="9da2a-257">Next Steps</span></span>  
 <span data-ttu-id="9da2a-258">Учебник «Добавление гистограммы к отчету» завершен.</span><span class="sxs-lookup"><span data-stu-id="9da2a-258">You have successfully completed the Adding a Column Chart to Your Report tutorial.</span></span> <span data-ttu-id="9da2a-259">Дополнительные сведения о диаграммах см. в разделах [Диаграммы (построитель отчетов и службы SSRS)](report-design/charts-report-builder-and-ssrs.md) и [Спарклайны и гистограммы (построитель отчетов и службы SSRS)](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9da2a-259">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9da2a-260">См. также:</span><span class="sxs-lookup"><span data-stu-id="9da2a-260">See Also</span></span>  
 <span data-ttu-id="9da2a-261">[Учебники &#40;построитель отчетов&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="9da2a-261">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="9da2a-262">Построитель отчетов в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="9da2a-262">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
