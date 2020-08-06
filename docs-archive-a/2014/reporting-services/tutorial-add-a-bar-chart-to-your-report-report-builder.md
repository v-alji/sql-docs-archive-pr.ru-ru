---
title: Учебник. Добавление линейчатой диаграммы к отчету (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6956ebd6-0217-4087-a4fa-5cc1c3804691
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01708ca548c40118daa03fac34d8a323d628b012
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658075"
---
# <a name="tutorial-add-a-bar-chart-to-your-report-report-builder"></a><span data-ttu-id="89a2d-102">Учебник. Добавление линейчатой диаграммы к отчету (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="89a2d-102">Tutorial: Add a Bar Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="89a2d-103">В линейчатых диаграммах категории данных отображаются по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="89a2d-103">A bar chart displays category data horizontally.</span></span> <span data-ttu-id="89a2d-104">Это может использоваться для:</span><span class="sxs-lookup"><span data-stu-id="89a2d-104">This can help to:</span></span>  
  
-   <span data-ttu-id="89a2d-105">улучшения читаемости длинных имен категорий;</span><span class="sxs-lookup"><span data-stu-id="89a2d-105">Improve readability of long category names.</span></span>  
  
-   <span data-ttu-id="89a2d-106">облегчения восприятия времени, отображаемого в виде значений;</span><span class="sxs-lookup"><span data-stu-id="89a2d-106">Improve understandability of times plotted as values.</span></span>  
  
-   <span data-ttu-id="89a2d-107">сравнение относительных значений нескольких рядов.</span><span class="sxs-lookup"><span data-stu-id="89a2d-107">Compare the relative value of multiple series.</span></span>  
  
 <span data-ttu-id="89a2d-108">На следующем рисунке показана создаваемая линейчатая диаграмма, на которой отображены данные продаж за 2008 и 2009 гг. для пяти менеджеров по продажам с максимальными объемами продаж, перечисленных в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="89a2d-108">The following illustration shows the bar chart that you will create, with sales for 2008 and 2009 for the top five salespeople, in alphabetical order.</span></span>  
  
 <span data-ttu-id="89a2d-109">![rs_BarChartTutorial](../../2014/tutorials/media/rs-barcharttutorial.gif "rs_BarChartTutorial")</span><span class="sxs-lookup"><span data-stu-id="89a2d-109">![rs_BarChartTutorial](../../2014/tutorials/media/rs-barcharttutorial.gif "rs_BarChartTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="89a2d-110">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="89a2d-110">What You Will Learn</span></span>  
 <span data-ttu-id="89a2d-111">В этом учебнике рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="89a2d-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="89a2d-112">Создание диаграммы с помощью мастера диаграмм</span><span class="sxs-lookup"><span data-stu-id="89a2d-112">Create a Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="89a2d-113">Выбор типа диаграммы</span><span class="sxs-lookup"><span data-stu-id="89a2d-113">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="89a2d-114">Отображение всех значений категорий по вертикальной оси</span><span class="sxs-lookup"><span data-stu-id="89a2d-114">Display all Category Values on the Vertical Axis</span></span>](#AllValues)  
  
4.  [<span data-ttu-id="89a2d-115">Изменение отображения имен по вертикальной оси</span><span class="sxs-lookup"><span data-stu-id="89a2d-115">Modify the Display of Names on the Vertical Axis</span></span>](#Sort)  
  
5.  [<span data-ttu-id="89a2d-116">Перемещение условных обозначений</span><span class="sxs-lookup"><span data-stu-id="89a2d-116">Move the Legend</span></span>](#Legend)  
  
6.  [<span data-ttu-id="89a2d-117">Перемещение заголовка диаграммы</span><span class="sxs-lookup"><span data-stu-id="89a2d-117">Move the Chart Title</span></span>](#ChartTitle)  
  
7.  [<span data-ttu-id="89a2d-118">Форматирование и задание меток для горизонтальной оси</span><span class="sxs-lookup"><span data-stu-id="89a2d-118">Format and Label the Horizontal Axis</span></span>](#Horizontal)  
  
8.  [<span data-ttu-id="89a2d-119">Добавление фильтра для отображения 5 максимальных значений</span><span class="sxs-lookup"><span data-stu-id="89a2d-119">Add a Filter to Display the Top Five Values</span></span>](#Filter)  
  
9. [<span data-ttu-id="89a2d-120">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="89a2d-120">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="89a2d-121">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="89a2d-121">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="89a2d-122">В этом учебнике шаги работы с мастером объединены в одну процедуру.</span><span class="sxs-lookup"><span data-stu-id="89a2d-122">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="89a2d-123">Пошаговые инструкции по переходу к серверу отчетов, созданию набора данных и выбору источника данных см. в первом учебнике этой серии: [Учебник. Создание простого табличного отчета (построитель отчетов)](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="89a2d-123">For step-by-step instructions about how to browse to a report server, create a dataset, and choose a data source, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="89a2d-124">Предполагаемое время для выполнения заданий этого учебника: 15 минут.</span><span class="sxs-lookup"><span data-stu-id="89a2d-124">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89a2d-125">Требования</span><span class="sxs-lookup"><span data-stu-id="89a2d-125">Requirements</span></span>  
 <span data-ttu-id="89a2d-126">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="89a2d-126">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-chart-report-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="89a2d-127">1. Создание отчета с диаграммой с помощью мастера диаграмм</span><span class="sxs-lookup"><span data-stu-id="89a2d-127">1. Create a Chart Report from the Chart Wizard</span></span>  
 <span data-ttu-id="89a2d-128">В диалоговом окне **Начало работы** создайте внедренный набор данных, выберите общий источник и создайте линейчатую диаграмму с помощью мастера диаграмм.</span><span class="sxs-lookup"><span data-stu-id="89a2d-128">From the **Getting Started** dialog box, create an embedded dataset, choose a shared data source, and create a bar chart by using the Chart Wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89a2d-129">В этом учебнике запрос уже содержит значения данных, поэтому внешний источник данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="89a2d-129">In this tutorial, the query contains the data values so that it does not need an external data source.</span></span> <span data-ttu-id="89a2d-130">В связи с этим запрос получается весьма длинным.</span><span class="sxs-lookup"><span data-stu-id="89a2d-130">This makes the query quite long.</span></span> <span data-ttu-id="89a2d-131">В рабочей среде запрос не будет содержать данные.</span><span class="sxs-lookup"><span data-stu-id="89a2d-131">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="89a2d-132">Этот запрос содержит данные только в учебных целях.</span><span class="sxs-lookup"><span data-stu-id="89a2d-132">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="89a2d-133">Создание нового отчета с диаграммой</span><span class="sxs-lookup"><span data-stu-id="89a2d-133">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="89a2d-134">Нажмите кнопку **Пуск**, наведите курсор на пункты **Все программы**, **Построитель отчетов Microsoft SQL Server 2012**и выберите пункт **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-134">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="89a2d-135">Откроется диалоговое окно **Начало работы** .</span><span class="sxs-lookup"><span data-stu-id="89a2d-135">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="89a2d-136">Если диалоговое окно **Начало работы** не отображается, нажмите кнопку Построитель отчетов, а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-136">If the **Getting Started** dialog box does not appear, click the Report Builder button, and then click **New**.</span></span>  
  
2.  <span data-ttu-id="89a2d-137">Убедитесь, что на левой панели выбран **Новый отчет** .</span><span class="sxs-lookup"><span data-stu-id="89a2d-137">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="89a2d-138">На правой панели выберите **Мастер диаграмм**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-138">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="89a2d-139">На странице **Выбор набора данных** нажмите кнопку **Создать набор данных**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-139">On the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="89a2d-140">На странице **Выбор соединения с источником данных** выберите существующий источник данных или перейдите к серверу отчетов и выберите источник данных, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-140">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="89a2d-141">Может потребоваться указать имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="89a2d-141">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="89a2d-142">При наличии необходимых разрешений выбор источника данных не имеет существенного значения.</span><span class="sxs-lookup"><span data-stu-id="89a2d-142">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="89a2d-143">Этот источник данных не будет использоваться для получения данных.</span><span class="sxs-lookup"><span data-stu-id="89a2d-143">You will not be getting data from the data source.</span></span> <span data-ttu-id="89a2d-144">Дополнительные сведения см. в разделе [Альтернативные способы создания подключения к данным &#40;построитель отчетов&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="89a2d-144">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="89a2d-145">На странице **Проектирование запроса** нажмите кнопку **Изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-145">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="89a2d-146">На панель запроса вставьте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="89a2d-146">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Luis' as FirstName, 'Alverca' as LastName, CAST(170000.00 AS money) AS SalesYear2009, CAST(150000. AS money) AS SalesYear2008  
    UNION SELECT 'Jeffrey' as FirstName, 'Zeng' as LastName, CAST(210000. AS money) AS SalesYear2009, CAST(190000. AS money) AS SalesYear2008  
    UNION SELECT 'Houman' as FirstName, 'Pournasseh' as LastName, CAST(150000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Robin' as FirstName, 'Wood' as LastName, CAST(75000. AS money) AS SalesYear2009, CAST(175000. AS money) AS SalesYear2008  
    UNION SELECT 'Daniela' as FirstName, 'Guaita' as LastName,  CAST(170000. AS money) AS SalesYear2009, CAST(175000. AS money) AS SalesYear2008  
    UNION SELECT 'John' as FirstName, 'Yokim' as LastName, CAST(160000. AS money) AS SalesYear2009, CAST(195000. AS money) AS SalesYear2008  
    UNION SELECT 'Delphine' as FirstName, 'Ribaute' as LastName, CAST(180000. AS money) AS SalesYear2009, CAST(205000. AS money) AS SalesYear2008  
    UNION SELECT 'Robert' as FirstName, 'Hernady' as LastName, CAST(140000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Tanja' as FirstName, 'Plate' as LastName, CAST(150000. AS money) AS SalesYear2009, CAST(160000. AS money) AS SalesYear2008  
    UNION SELECT 'David' as FirstName, 'Bradley' as LastName, CAST(210000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Michal' as FirstName, 'Jaworski' as LastName, CAST(175000. AS money) AS SalesYear2009, CAST(220000. AS money) AS SalesYear2008  
    UNION SELECT 'Chris' as FirstName, 'Ashton' as LastName, CAST(195000. AS money) AS SalesYear2009, CAST(205000. AS money) AS SalesYear2008  
    UNION SELECT 'Pongsiri' as FirstName, 'Hirunyanitiwatna' as LastName, CAST(175000. AS money) AS SalesYear2009, CAST(215000. AS money) AS SalesYear2008  
    UNION SELECT 'Brian' as FirstName, 'Burke' as LastName, CAST(187000. AS money) AS SalesYear2009, CAST(207000. AS money) AS SalesYear2008  
    ```  
  
8.  <span data-ttu-id="89a2d-147">Нажмите кнопку Выполнить (**!**), чтобы просмотреть данные, на основе которых будет создана диаграмма (необязательно).</span><span class="sxs-lookup"><span data-stu-id="89a2d-147">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="89a2d-148">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-148">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="89a2d-149">2. Выбор типа диаграммы</span><span class="sxs-lookup"><span data-stu-id="89a2d-149">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="89a2d-150">Можно выбрать один из различных стандартных типов диаграмм.</span><span class="sxs-lookup"><span data-stu-id="89a2d-150">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-column-chart"></a><span data-ttu-id="89a2d-151">Добавление гистограммы</span><span class="sxs-lookup"><span data-stu-id="89a2d-151">To add a column chart</span></span>  
  
1.  <span data-ttu-id="89a2d-152">На странице **Выбор типа диаграммы** в качестве типа диаграммы по умолчанию задана гистограмма.</span><span class="sxs-lookup"><span data-stu-id="89a2d-152">On the **Choose a chart type** page, the column chart is the default chart type.</span></span>  
  
2.  <span data-ttu-id="89a2d-153">Нажмите кнопку **Линейчатая**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-153">Click **Bar**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="89a2d-154">На странице **Расположение полей диаграммы** есть четыре поля в области **Доступные поля** : FirstName, LastName, SalesYear2009 и SalesYear2008.</span><span class="sxs-lookup"><span data-stu-id="89a2d-154">On the **Arrange chart fields** page, there are four fields in the **Available fields** pane: FirstName, LastName, SalesYear2009, and SalesYear2008.</span></span>  
  
3.  <span data-ttu-id="89a2d-155">Перетащите поле «LastName» на панель «Категории».</span><span class="sxs-lookup"><span data-stu-id="89a2d-155">Drag LastName to the Categories pane.</span></span>  
  
4.  <span data-ttu-id="89a2d-156">Перетащите поле «SalesYear2009» на панель «Значения».</span><span class="sxs-lookup"><span data-stu-id="89a2d-156">Drag SalesYear2009 to the Values pane.</span></span> <span data-ttu-id="89a2d-157">«SalesYear2009» представляет объем продаж всех менеджеров по продажам за 2009 г.</span><span class="sxs-lookup"><span data-stu-id="89a2d-157">SalesYear2009 represents the sales amount for each salesperson for the year 2009.</span></span> <span data-ttu-id="89a2d-158">На панели «Значения» отображается выражение `[Sum(SalesYear2009)]` , поскольку в диаграмме отображается агрегат для каждого из продуктов.</span><span class="sxs-lookup"><span data-stu-id="89a2d-158">The Values pane displays `[Sum(SalesYear2009)]` because the chart displays the aggregate for each product.</span></span>  
  
5.  <span data-ttu-id="89a2d-159">Перетащите поле «SalesYear2008» на панель «Значения» ниже «SalesYear2009».</span><span class="sxs-lookup"><span data-stu-id="89a2d-159">Drag SalesYear2008 to the Values pane under SalesYear2009.</span></span> <span data-ttu-id="89a2d-160">«SalesYear2008» представляет объем продаж всех менеджеров по продажам за 2008 г.</span><span class="sxs-lookup"><span data-stu-id="89a2d-160">SalesYear2008 represents the sales amount for each salesperson for the year 2008.</span></span>  
  
6.  <span data-ttu-id="89a2d-161">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-161">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="89a2d-162">На панели Стили на странице **Выбор стиля** выберите стиль.</span><span class="sxs-lookup"><span data-stu-id="89a2d-162">On the **Choose a style** page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="89a2d-163">Стиль задает стиль шрифта, набор цветов и стиль границы.</span><span class="sxs-lookup"><span data-stu-id="89a2d-163">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="89a2d-164">При выборе стиля на панели просмотра отобразится образец диаграммы с этим стилем.</span><span class="sxs-lookup"><span data-stu-id="89a2d-164">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
8.  <span data-ttu-id="89a2d-165">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-165">Click **Finish**.</span></span>  
  
     <span data-ttu-id="89a2d-166">Диаграмма добавляется в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="89a2d-166">The chart is added to the design surface.</span></span>  
  
9. <span data-ttu-id="89a2d-167">Щелкните диаграмму, чтобы отобразить ее маркеры.</span><span class="sxs-lookup"><span data-stu-id="89a2d-167">Click the chart to display the chart handles.</span></span> <span data-ttu-id="89a2d-168">Перетащите правый нижний угол диаграммы вниз, чтобы увеличить ее размер.</span><span class="sxs-lookup"><span data-stu-id="89a2d-168">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span>  
  
10. <span data-ttu-id="89a2d-169">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-169">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="89a2d-170">В отчете отображается линейчатая диаграмма с данными продаж всех менеджеров по продажам за 2008 и 2009 гг.</span><span class="sxs-lookup"><span data-stu-id="89a2d-170">The report displays the bar chart for sales for each sales person for the years 2008 and 2009.</span></span> <span data-ttu-id="89a2d-171">Длина линии на диаграмме соответствует общему значению объема продаж.</span><span class="sxs-lookup"><span data-stu-id="89a2d-171">The length of the bar corresponds to the sales total.</span></span>  
  
##  <a name="3-modify-the-display-of-names-on-the-vertical-axis"></a><a name="AllValues"></a><span data-ttu-id="89a2d-172">3. изменение отображаемых имен на вертикальной оси</span><span class="sxs-lookup"><span data-stu-id="89a2d-172">3. Modify the Display of Names on the Vertical Axis</span></span>  
 <span data-ttu-id="89a2d-173">По умолчанию на вертикальной оси отображаются только определенные значения.</span><span class="sxs-lookup"><span data-stu-id="89a2d-173">By default, only some of the values on the vertical axis appear.</span></span> <span data-ttu-id="89a2d-174">Диаграмму можно изменить для отображения всех категорий.</span><span class="sxs-lookup"><span data-stu-id="89a2d-174">You can change the chart to display all categories.</span></span>  
  
#### <a name="to-display-all-sales-persons-along-the-category-axis-of-a-bar-chart"></a><span data-ttu-id="89a2d-175">Отображение всех менеджеров по продажам на оси категорий линейчатой диаграммы</span><span class="sxs-lookup"><span data-stu-id="89a2d-175">To display all sales persons along the category axis of a bar chart</span></span>  
  
1.  <span data-ttu-id="89a2d-176">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-176">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="89a2d-177">Щелкните правой кнопкой мыши вертикальную ось и выберите пункт **Свойства вертикальной оси**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-177">Right-click the vertical axis, and then click **Vertical Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="89a2d-178">В области **Диапазон и интервал оси**в поле **Интервал** введите значение **1**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-178">Under **Axis range and interval**, in the **Interval** box, type **1**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="89a2d-179">Щелкните правой кнопкой мыши заголовок вертикальной **оси** и снимите флажок **Показывать заголовок оси** .</span><span class="sxs-lookup"><span data-stu-id="89a2d-179">Right-click the vertical **Axis Title** and clear the **Show Axis Title** check box.</span></span>  
  
6.  <span data-ttu-id="89a2d-180">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-180">Click **Run** to preview the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89a2d-181">Если имена менеджеров по продажам на вертикальной оси невозможно прочесть, можно увеличить высоту диаграммы или изменить параметры форматирования для меток оси.</span><span class="sxs-lookup"><span data-stu-id="89a2d-181">If you cannot read the salesperson names on the vertical axis, you can make your chart taller or change the formatting options for the axis labels.</span></span>  
  
###  <a name="display-last-name-and-first-name-on-vertical-axis"></a><a name="CategoryExpression"></a><span data-ttu-id="89a2d-182">Отображать фамилию и имя на вертикальной оси</span><span class="sxs-lookup"><span data-stu-id="89a2d-182">Display Last Name and First Name on Vertical Axis</span></span>  
 <span data-ttu-id="89a2d-183">Можно изменить выражение категории для отображения фамилии, после которой будет отображаться имя для всех менеджеров по продажам.</span><span class="sxs-lookup"><span data-stu-id="89a2d-183">You can change the category expression to include last name followed by first name of each sales person.</span></span>  
  
##### <a name="to-change-the-category-expression"></a><span data-ttu-id="89a2d-184">Изменение выражения категории</span><span class="sxs-lookup"><span data-stu-id="89a2d-184">To change the category expression</span></span>  
  
1.  <span data-ttu-id="89a2d-185">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-185">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="89a2d-186">Дважды щелкните диаграмму, чтобы отобразить панель **Данные диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="89a2d-186">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="89a2d-187">Щелкните правой кнопкой мыши поле [LastName] в области **Группы категорий** и выберите пункт **Свойства группы категорий**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-187">In the **Category Groups** area, right-click [LastName], and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="89a2d-188">В поле «Метка» нажмите кнопку «Выражение» (Fx).</span><span class="sxs-lookup"><span data-stu-id="89a2d-188">In Label, click the expression (Fx) button.</span></span>  
  
5.  <span data-ttu-id="89a2d-189">Введите следующее выражение: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span><span class="sxs-lookup"><span data-stu-id="89a2d-189">Type the following expression: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span></span>  
  
     <span data-ttu-id="89a2d-190">В выражении будут объединены фамилия, запятая и имя.</span><span class="sxs-lookup"><span data-stu-id="89a2d-190">This expression concatenates the last name, a comma, and the first name.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="89a2d-191">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-191">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="89a2d-192">Если фамилии не отображаются при выполнении отчета, то данные можно обновить вручную.</span><span class="sxs-lookup"><span data-stu-id="89a2d-192">If the first names do not appear when you run the report, you can refresh the data manually.</span></span> <span data-ttu-id="89a2d-193">Оставаясь в режиме предварительного просмотра, на вкладке **Выполнить** в группе **Навигация** нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-193">While still in preview mode, on the **Run** tab in the **Navigation** group, click **Refresh**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89a2d-194">Если имена менеджеров по продажам на вертикальной оси невозможно прочесть, можно увеличить высоту диаграммы или изменить параметры форматирования для меток оси.</span><span class="sxs-lookup"><span data-stu-id="89a2d-194">If you cannot read the salesperson names on the vertical axis, you can make your chart taller or change the formatting options for the axis labels.</span></span>  
  
##  <a name="4-change-the-sort-order-for-names-on-the-vertical-axis"></a><a name="Sort"></a><span data-ttu-id="89a2d-195">4. изменение порядка сортировки для имен на вертикальной оси</span><span class="sxs-lookup"><span data-stu-id="89a2d-195">4. Change the Sort Order for Names on the Vertical Axis</span></span>  
 <span data-ttu-id="89a2d-196">При сортировке данных на диаграмме изменяется порядок значений на осях категории.</span><span class="sxs-lookup"><span data-stu-id="89a2d-196">When you sort the data on a chart, you are changing the order of values on the category axis.</span></span>  
  
#### <a name="to-sort-the-names-in-alphabetical-order-on-the-bar-chart"></a><span data-ttu-id="89a2d-197">Сортировка имен на линейчатой диаграмме в алфавитном порядке</span><span class="sxs-lookup"><span data-stu-id="89a2d-197">To sort the names in alphabetical order on the bar chart</span></span>  
  
1.  <span data-ttu-id="89a2d-198">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-198">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="89a2d-199">Дважды щелкните диаграмму, чтобы отобразить панель **Данные диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="89a2d-199">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="89a2d-200">Щелкните правой кнопкой мыши поле [LastName] в области **Группы категорий** и выберите пункт **Свойства группы категорий**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-200">In the **Category Groups** area, right-click [LastName], and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="89a2d-201">Щелкните **Сортировка**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-201">Click **Sorting**.</span></span> <span data-ttu-id="89a2d-202">На странице **Изменение параметров сортировки** отображается список выражений фильтров.</span><span class="sxs-lookup"><span data-stu-id="89a2d-202">The **Change sorting options** page displays a list of sort expressions.</span></span> <span data-ttu-id="89a2d-203">По умолчанию в этом списке имеется одно выражение сортировки, идентичное исходному выражению группы категорий.</span><span class="sxs-lookup"><span data-stu-id="89a2d-203">By default, this list has one sort expression that is the same as the original category group expression.</span></span>  
  
5.  <span data-ttu-id="89a2d-204">В поле Сортировать по нажмите кнопку Выражение (**FX**).</span><span class="sxs-lookup"><span data-stu-id="89a2d-204">In Sort by, click the expression (**Fx**) button.</span></span>  
  
6.  <span data-ttu-id="89a2d-205">Введите следующее выражение: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span><span class="sxs-lookup"><span data-stu-id="89a2d-205">Type the following expression: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span></span>  
  
7.  <span data-ttu-id="89a2d-206">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-206">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="89a2d-207">Вернитесь на страницу **свойств группы категорий** , в раскрывающемся списке **порядок** выберите **от я до а**. Это позволяет выбрать обратный алфавитный порядок, чтобы имена отображались в порядке сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="89a2d-207">Back on the **Category Group Properties** page, in the **Order** drop-down list, select **Z to A**. This selects reverse alphabetical order so that the names appear in order from top to bottom.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="89a2d-208">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-208">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="89a2d-209">Имена на горизонтальной оси сортируются в обратном порядке, с **алерка** сверху и **Zeng)** внизу.</span><span class="sxs-lookup"><span data-stu-id="89a2d-209">The names on the horizontal axis are sorted in reverse order, with **Alerca** at the top and **Zeng** at the bottom.</span></span>  
  
##  <a name="5-move-the-legend"></a><a name="Legend"></a><span data-ttu-id="89a2d-210">5. Перемещение условных обозначений</span><span class="sxs-lookup"><span data-stu-id="89a2d-210">5. Move the Legend</span></span>  
 <span data-ttu-id="89a2d-211">Чтобы улучшить читаемость значений диаграммы, можно переместить ее условные обозначения.</span><span class="sxs-lookup"><span data-stu-id="89a2d-211">To improve the readability of the chart values, you might want to move the chart legend.</span></span> <span data-ttu-id="89a2d-212">Например, в линейчатой диаграмме, в которой столбцы отображаются горизонтально, можно изменить положение условных обозначений, чтобы они находились выше или ниже области диаграммы.</span><span class="sxs-lookup"><span data-stu-id="89a2d-212">For example, in a bar chart where bars are shown horizontally, you can change the position of the legend so that it is above or below the chart area.</span></span> <span data-ttu-id="89a2d-213">В результате для столбцов выделяется больше места.</span><span class="sxs-lookup"><span data-stu-id="89a2d-213">This gives more horizontal space to the bars.</span></span>  
  
#### <a name="to-display-the-legend-below-the-chart-area-of-a-bar-chart"></a><span data-ttu-id="89a2d-214">Вывод условных обозначений под областью линейчатой диаграммы</span><span class="sxs-lookup"><span data-stu-id="89a2d-214">To display the legend below the chart area of a bar chart</span></span>  
  
1.  <span data-ttu-id="89a2d-215">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-215">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="89a2d-216">Щелкните правой кнопкой мыши условные обозначения диаграммы.</span><span class="sxs-lookup"><span data-stu-id="89a2d-216">Right-click the legend on the chart.</span></span>  
  
3.  <span data-ttu-id="89a2d-217">Выберите **Свойства условных обозначений**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-217">Select **Legend Properties**.</span></span>  
  
4.  <span data-ttu-id="89a2d-218">Выберите другое значение для параметра **Положение условных обозначений**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-218">For **Legend position**, select a different position.</span></span> <span data-ttu-id="89a2d-219">Например, можно выбрать параметр, соответствующий расположению посередине в нижней части.</span><span class="sxs-lookup"><span data-stu-id="89a2d-219">For example, set the position to the middle bottom option.</span></span>  
  
     <span data-ttu-id="89a2d-220">Если условные обозначения перемесить в верхнюю или нижнюю часть диаграммы, их макет изменится с вертикального на горизонтальный.</span><span class="sxs-lookup"><span data-stu-id="89a2d-220">When the legend is placed at the top or bottom of a chart, the layout of the legend changes from vertical to horizontal.</span></span> <span data-ttu-id="89a2d-221">Можно выбрать другой макет в раскрывающемся списке **Макет** .</span><span class="sxs-lookup"><span data-stu-id="89a2d-221">You can select a different layout from the **Layout** drop-down list.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="89a2d-222">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-222">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-title-the-chart"></a><a name="ChartTitle"></a><span data-ttu-id="89a2d-223">6. заголовком диаграммы</span><span class="sxs-lookup"><span data-stu-id="89a2d-223">6. Title the Chart</span></span>  
  
#### <a name="to-change-the-chart-title-above-the-chart-area-of-a-bar-chart"></a><span data-ttu-id="89a2d-224">Изменение заголовка диаграммы над областью линейчатой диаграммы</span><span class="sxs-lookup"><span data-stu-id="89a2d-224">To change the chart title above the chart area of a bar chart</span></span>  
  
1.  <span data-ttu-id="89a2d-225">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-225">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="89a2d-226">Выберите **заголовок диаграммы** слова в верхней части диаграммы, а затем введите следующий текст: **Sales для 2008 и 2009**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-226">Select the words **Chart Title** at the top of the chart, and then type the following text: **Sales for 2008 and 2009**.</span></span>  
  
3.  <span data-ttu-id="89a2d-227">Щелкните в любом месте текста.</span><span class="sxs-lookup"><span data-stu-id="89a2d-227">Click anywhere outside the text.</span></span>  
  
4.  <span data-ttu-id="89a2d-228">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-228">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-format-and-label-the-horizontal-axis"></a><a name="Horizontal"></a><span data-ttu-id="89a2d-229">7. форматирование и пометка горизонтальной оси</span><span class="sxs-lookup"><span data-stu-id="89a2d-229">7. Format and Label the Horizontal Axis</span></span>  
 <span data-ttu-id="89a2d-230">По умолчанию по горизонтальной оси отображаются значения в общем формате, который автоматически масштабируется в соответствии с размером диаграммы.</span><span class="sxs-lookup"><span data-stu-id="89a2d-230">By default, the horizontal axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-the-numbers-on-the-horizontal-axis"></a><span data-ttu-id="89a2d-231">Форматирование чисел по горизонтальной оси</span><span class="sxs-lookup"><span data-stu-id="89a2d-231">To format the numbers on the horizontal axis</span></span>  
  
1.  <span data-ttu-id="89a2d-232">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-232">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="89a2d-233">Щелкните горизонтальную ось в нижней части диаграммы, чтобы выбрать ее.</span><span class="sxs-lookup"><span data-stu-id="89a2d-233">Click the horizontal axis along the bottom of the chart to select it.</span></span>  
  
     <span data-ttu-id="89a2d-234">На ленте на вкладке **Главная** в группе **число** нажмите кнопку **Валюта** .</span><span class="sxs-lookup"><span data-stu-id="89a2d-234">On the ribbon, on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="89a2d-235">Метки на горизонтальной оси изменятся на валюту.</span><span class="sxs-lookup"><span data-stu-id="89a2d-235">The horizontal axis labels change to currency.</span></span>  
  
3.  <span data-ttu-id="89a2d-236">(Необязательно) Удалите десятичные знаки.</span><span class="sxs-lookup"><span data-stu-id="89a2d-236">(Optional) Remove the decimal digits.</span></span> <span data-ttu-id="89a2d-237">Рядом с кнопкой **Денежный** дважды нажмите кнопку **Уменьшить число десятичных разрядов** .</span><span class="sxs-lookup"><span data-stu-id="89a2d-237">Near the **Currency** button, click the **Decrease Decimal** button twice.</span></span>  
  
4.  <span data-ttu-id="89a2d-238">Щелкните правой кнопкой мыши горизонтальную ось и выберите пункт **Свойства горизонтальной оси**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-238">Right-click the horizontal axis, and click **Horizontal Axis Properties**.</span></span>  
  
5.  <span data-ttu-id="89a2d-239">На вкладке **число** выберите **Показывать значения в тысячах.**</span><span class="sxs-lookup"><span data-stu-id="89a2d-239">On the **Number** tab, select **Show values in Thousands.**</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="89a2d-240">Щелкните правой кнопкой мыши **заголовок оси** и выберите пункт **Свойства заголовка оси**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-240">Right-click **Axis Title** and click **Axis Title Properties**.</span></span>  
  
8.  <span data-ttu-id="89a2d-241">В **текстовом поле Заголовок** введите **Sales в тысячах** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-241">In the **Title text** box, type **Sales in thousands** and click **OK**.</span></span>  
  
9. <span data-ttu-id="89a2d-242">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-242">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="89a2d-243">В отчете объем продаж отображается по горизонтальной оси в виде валюты в тысячах без десятичных знаков.</span><span class="sxs-lookup"><span data-stu-id="89a2d-243">The report displays the sales amount on the horizontal axis as currency in thousands, and has no decimal digits.</span></span>  
  
##  <a name="8-add-a-filter-to-display-the-top-five-values"></a><a name="Filter"></a><span data-ttu-id="89a2d-244">8. Добавление фильтра для вывода пяти верхних значений</span><span class="sxs-lookup"><span data-stu-id="89a2d-244">8. Add a Filter to Display the Top Five Values</span></span>  
 <span data-ttu-id="89a2d-245">К диаграмме можно добавить фильтр, чтобы выбрать данные в наборе данных для включения или исключения из диаграммы.</span><span class="sxs-lookup"><span data-stu-id="89a2d-245">You can add a filter to the chart to specify which data from the dataset to include or exclude in the chart.</span></span>  
  
#### <a name="to-add-a-filter-and-display-the-top-five-values"></a><span data-ttu-id="89a2d-246">Добавление фильтра и отображение 5 наибольших значений</span><span class="sxs-lookup"><span data-stu-id="89a2d-246">To add a filter and display the top five values</span></span>  
  
1.  <span data-ttu-id="89a2d-247">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-247">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="89a2d-248">Дважды щелкните диаграмму, чтобы отобразить панель **Данные диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="89a2d-248">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="89a2d-249">Щелкните правой кнопкой мыши поле [LastName] в области **Группы категорий** и выберите пункт **Свойства группы категорий**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-249">In the **Category Groups** area, right-click the [LastName] field, and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="89a2d-250">Перейдите на вкладку **Фильтры**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-250">Click **Filters**.</span></span> <span data-ttu-id="89a2d-251">На странице **Изменение фильтров** может отображаться список критериев фильтров.</span><span class="sxs-lookup"><span data-stu-id="89a2d-251">The **Change filters** page can display a list of filter expressions.</span></span> <span data-ttu-id="89a2d-252">По умолчанию этот список пустой.</span><span class="sxs-lookup"><span data-stu-id="89a2d-252">By default, this list is empty.</span></span>  
  
5.  <span data-ttu-id="89a2d-253">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-253">Click **Add**.</span></span> <span data-ttu-id="89a2d-254">Появится новый пустой фильтр.</span><span class="sxs-lookup"><span data-stu-id="89a2d-254">A new blank filter appears.</span></span>  
  
6.  <span data-ttu-id="89a2d-255">В **выражении**введите **[Sum (SalesYear2009)]**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-255">In **Expression**, type **[Sum(SalesYear2009)]**.</span></span> <span data-ttu-id="89a2d-256">При этом создается базовое выражение `=Sum(Fields!SalesYear2009.Value)`, которое можно просмотреть, нажав кнопку **fx** .</span><span class="sxs-lookup"><span data-stu-id="89a2d-256">This creates the underlying expression `=Sum(Fields!SalesYear2009.Value)`, which you can see if you click the **fx** button.</span></span>  
  
7.  <span data-ttu-id="89a2d-257">Убедитесь в том, что типом данных является **Текст**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-257">Verify that the data type is **Text**.</span></span>  
  
8.  <span data-ttu-id="89a2d-258">В раскрывающемся списке **Оператор**выберите вариант **Первые N** .</span><span class="sxs-lookup"><span data-stu-id="89a2d-258">In **Operator**, select **Top N** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="89a2d-259">В поле **Значение**введите следующее выражение: **=5**</span><span class="sxs-lookup"><span data-stu-id="89a2d-259">In **Value**, type the following expression: **=5**</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="89a2d-260">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-260">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="89a2d-261">Если к результатам не применяется фильтр при выполнении отчета, данные можно обновить вручную.</span><span class="sxs-lookup"><span data-stu-id="89a2d-261">If the results are not filtered when you run the report, you can refresh the data manually.</span></span> <span data-ttu-id="89a2d-262">На вкладке **Выполнить** в группе **Навигация** нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-262">On the **Run** tab in the **Navigation** group, click **Refresh**.</span></span>  
  
 <span data-ttu-id="89a2d-263">На диаграмме отобразятся имена пяти первых менеджеров по продажам из данных продаж за 2009 г.</span><span class="sxs-lookup"><span data-stu-id="89a2d-263">The chart shows the top five salesperson names from the 2009 sales data.</span></span>  
  
##  <a name="9-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="89a2d-264">9. Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="89a2d-264">9. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="89a2d-265">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="89a2d-265">To add a report title</span></span>  
  
1.  <span data-ttu-id="89a2d-266">В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-266">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="89a2d-267">Введите **линейчатую диаграмму продаж**, нажмите клавишу ВВОД, а затем введите **первые пять продавцов для 2009**, чтобы он выглядел следующим образом:</span><span class="sxs-lookup"><span data-stu-id="89a2d-267">Type **Sales Bar Chart**, press ENTER, and then type **Top Five Sellers for 2009**, so it looks like this:</span></span>  
  
     <span data-ttu-id="89a2d-268">**Линейчатая диаграмма продаж**</span><span class="sxs-lookup"><span data-stu-id="89a2d-268">**Sales Bar Chart**</span></span>  
  
     <span data-ttu-id="89a2d-269">**Пять менеджеров по продажам с наибольшим объемом продаж за 2009 г.**</span><span class="sxs-lookup"><span data-stu-id="89a2d-269">**Top Five Sellers for 2009**</span></span>  
  
3.  <span data-ttu-id="89a2d-270">Выберите **Линейчатая диаграмма продаж**и нажмите кнопку **Полужирный** .</span><span class="sxs-lookup"><span data-stu-id="89a2d-270">Select **Sales Bar Chart**, and click the **Bold** button.</span></span>  
  
4.  <span data-ttu-id="89a2d-271">Выберите **пять основных продавцов для 2009**, а в разделе **Шрифт** на вкладке **Главная** установите размер шрифта равным **10**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-271">Select **Top Five Sellers for 2009**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
5.  <span data-ttu-id="89a2d-272">Может потребоваться увеличить высоту текстового поля «Заголовок» для соответствия размерам двух строк текста (необязательно).</span><span class="sxs-lookup"><span data-stu-id="89a2d-272">(Optional) You may need to make the Title text box taller to accommodate the two lines of text.</span></span>  
  
     <span data-ttu-id="89a2d-273">Данный заголовок появится в верхней части отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-273">This title will appear at the top of the report.</span></span> <span data-ttu-id="89a2d-274">При отсутствии верхнего колонтитула страницы элементы в верхней части текста отчета выполняют роль заголовка отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-274">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
6.  <span data-ttu-id="89a2d-275">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-275">Click **Run** to preview the report.</span></span>  
  
##  <a name="10-save-the-report"></a><a name="Save"></a><span data-ttu-id="89a2d-276">10. Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="89a2d-276">10. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="89a2d-277">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="89a2d-277">To save the report</span></span>  
  
1.  <span data-ttu-id="89a2d-278">Переключитесь в режим конструктора отчета.</span><span class="sxs-lookup"><span data-stu-id="89a2d-278">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="89a2d-279">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-279">From the **Report Builder** button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="89a2d-280">В поле **Имя**введите **Линейчатая диаграмма продаж**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-280">In **Name**, type **Sales Bar Chart**.</span></span>  
  
4.  <span data-ttu-id="89a2d-281">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="89a2d-281">Click **Save**.</span></span>  
  
 <span data-ttu-id="89a2d-282">Отчет будет сохранен на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="89a2d-282">Your report is saved on the report server.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="89a2d-283">Next Steps</span><span class="sxs-lookup"><span data-stu-id="89a2d-283">Next Steps</span></span>  
 <span data-ttu-id="89a2d-284">Учебник «Добавление линейчатой диаграммы в отчет» успешно завершен.</span><span class="sxs-lookup"><span data-stu-id="89a2d-284">You have successfully completed the Adding a Bar Chart to Your Report tutorial.</span></span> <span data-ttu-id="89a2d-285">Дополнительные сведения о диаграммах см. в разделах [Диаграммы (построитель отчетов и службы SSRS)](report-design/charts-report-builder-and-ssrs.md) и [Спарклайны и гистограммы (построитель отчетов и службы SSRS)](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="89a2d-285">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a2d-286">См. также:</span><span class="sxs-lookup"><span data-stu-id="89a2d-286">See Also</span></span>  
 <span data-ttu-id="89a2d-287">[Учебники &#40;построитель отчетов&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="89a2d-287">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="89a2d-288">Построитель отчетов в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="89a2d-288">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
