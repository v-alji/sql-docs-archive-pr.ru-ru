---
title: Учебник. Отчет-карта (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8d831356-7efa-40cc-ae95-383b3eecf833
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b737bb3fe74eb3524f2944a7458cb4837b1aeedf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737787"
---
# <a name="tutorial-map-report-report-builder"></a><span data-ttu-id="672fe-102">Учебник. Отчет-карта (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="672fe-102">Tutorial: Map Report (Report Builder)</span></span>
  <span data-ttu-id="672fe-103">Этот учебник позволяет изучить функции карты, которые можно использовать для отображения данных отчета в географическом контексте.</span><span class="sxs-lookup"><span data-stu-id="672fe-103">This tutorial is designed to help you learn about the map features you can use to display report data against a geographic background.</span></span>  
  
 <span data-ttu-id="672fe-104">Карты строятся по пространственным данным, которые обычно представляют собой набор точек, линий и многоугольников.</span><span class="sxs-lookup"><span data-stu-id="672fe-104">Maps are based on spatial data that typically consists of points, lines, and polygons.</span></span> <span data-ttu-id="672fe-105">Например, многоугольник может представлять очертания страны, линия — дорогу, а точка может обозначать местоположение города.</span><span class="sxs-lookup"><span data-stu-id="672fe-105">For example, a polygon can represent the outline of a county, a line can represent a road, and a point can represent the location of a city.</span></span> <span data-ttu-id="672fe-106">Все типы пространственных данных отображаются на отдельном слое карты в виде набора элементов карты.</span><span class="sxs-lookup"><span data-stu-id="672fe-106">Each type of spatial data is displayed on a separate map layer as a set of map elements.</span></span>  
  
 <span data-ttu-id="672fe-107">Чтобы изменить внешний вид элементов карты, необходимо указать поле со значениями, сопоставляющими элементы карты с аналитическими данными из набора данных.</span><span class="sxs-lookup"><span data-stu-id="672fe-107">To vary the appearance of map elements, you specify a field that has values that match the map elements with analytical data from a dataset.</span></span> <span data-ttu-id="672fe-108">Также можно определять на основе диапазонов данных правила, с помощью которых задается цвет, размер и другие свойства.</span><span class="sxs-lookup"><span data-stu-id="672fe-108">You can also define rules that vary color, size, or other properties based on ranges of data.</span></span>  
  
 <span data-ttu-id="672fe-109">В этом учебнике выполняется создание отчета-карты, где отображается местоположение магазинов в округах штата Нью-Йорк.</span><span class="sxs-lookup"><span data-stu-id="672fe-109">In this tutorial, you will build a map report that displays store locations in New York state counties.</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="672fe-110">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="672fe-110">What You Will Learn</span></span>  
 <span data-ttu-id="672fe-111">В этом учебнике рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="672fe-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="672fe-112">Создание карты со слоем многоугольника с помощью мастера карт</span><span class="sxs-lookup"><span data-stu-id="672fe-112">Create a Map with a Polygon Layer from the Map Wizard</span></span>](#Map)  
  
2.  [<span data-ttu-id="672fe-113">Добавление слоя точек карты для отображения местоположения магазинов</span><span class="sxs-lookup"><span data-stu-id="672fe-113">Add a Map Point Layer to Display Store Locations</span></span>](#PointLayer)  
  
3.  [<span data-ttu-id="672fe-114">Добавление слоя линий карты для отображения маршрута</span><span class="sxs-lookup"><span data-stu-id="672fe-114">Add a Map Line Layer to Display a Route</span></span>](#LineLayer)  
  
4.  [<span data-ttu-id="672fe-115">Добавление мозаичного фона Bing Maps</span><span class="sxs-lookup"><span data-stu-id="672fe-115">Add a Bing Maps Tile Background</span></span>](#TileLayer)  
  
5.  [<span data-ttu-id="672fe-116">Преобразование слоя в прозрачный</span><span class="sxs-lookup"><span data-stu-id="672fe-116">Make a Layer Transparent</span></span>](#Transparent)  
  
6.  [<span data-ttu-id="672fe-117">Задание различных цветов для округов в зависимости от уровня продаж</span><span class="sxs-lookup"><span data-stu-id="672fe-117">Vary County Color Based on Sales</span></span>](#Vary)  
  
    1.  [<span data-ttu-id="672fe-118">Построение связей между пространственными и аналитическими данными</span><span class="sxs-lookup"><span data-stu-id="672fe-118">Build a Relationship between Spatial and Analytical Data</span></span>](#Relationship)  
  
    2.  [<span data-ttu-id="672fe-119">Указание правил цвета для многоугольников</span><span class="sxs-lookup"><span data-stu-id="672fe-119">Specify Color Rules for Polygons</span></span>](#ColorRules)  
  
    3.  [<span data-ttu-id="672fe-120">Форматирование данных в цветовой шкале как различных валют</span><span class="sxs-lookup"><span data-stu-id="672fe-120">Format the Data in the Color Scale as Currency</span></span>](#ColorScale)  
  
    4.  [<span data-ttu-id="672fe-121">Создание новых условных обозначений</span><span class="sxs-lookup"><span data-stu-id="672fe-121">Create a New Legend</span></span>](#NewLegend)  
  
    5.  [<span data-ttu-id="672fe-122">Связывание условных обозначений и правил цветов</span><span class="sxs-lookup"><span data-stu-id="672fe-122">Associate Legend and Color Rules</span></span>](#Associate)  
  
    6.  [<span data-ttu-id="672fe-123">Очистка цветов округов, не содержащих данных</span><span class="sxs-lookup"><span data-stu-id="672fe-123">Clear Color from Counties with No Data</span></span>](#NoData)  
  
7.  [<span data-ttu-id="672fe-124">Добавление пользовательской точки</span><span class="sxs-lookup"><span data-stu-id="672fe-124">Add a Custom Point</span></span>](#CustomPoint)  
  
8.  [<span data-ttu-id="672fe-125">Центрирование представления карты</span><span class="sxs-lookup"><span data-stu-id="672fe-125">Center the Map View</span></span>](#CenterView)  
  
9. [<span data-ttu-id="672fe-126">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="672fe-126">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="672fe-127">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="672fe-127">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="672fe-128">В данном учебнике стадии работы мастера объединены в две процедуры: для создания набора данных и для создания таблиц.</span><span class="sxs-lookup"><span data-stu-id="672fe-128">In this tutorial, the steps for the wizard are consolidated into two procedures: one to create the dataset and one to create a table.</span></span> <span data-ttu-id="672fe-129">Пошаговые инструкции по переходу к серверу отчетов, выбору источника данных, созданию набора данных и запуску мастера см. в первом учебнике этой серии: [Учебник. Создание простого табличного отчета &#40;построитель отчетов&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="672fe-129">For step-by-step instructions about how to browse to a report server, choose a data source, create a dataset, and run the wizard, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="672fe-130">Предполагаемое время для выполнения заданий данного учебника: 30 минут.</span><span class="sxs-lookup"><span data-stu-id="672fe-130">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="672fe-131">Требования</span><span class="sxs-lookup"><span data-stu-id="672fe-131">Requirements</span></span>  
 <span data-ttu-id="672fe-132">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="672fe-132">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-map-with-a-polygon-layer-from-the-map-wizard"></a><a name="Map"></a><span data-ttu-id="672fe-133">1. Создание схемы с слоем многоугольников с помощью мастера карт</span><span class="sxs-lookup"><span data-stu-id="672fe-133">1. Create a Map with a Polygon Layer from the Map Wizard</span></span>  
 <span data-ttu-id="672fe-134">Добавление карты к отчету из галереи отчетов.</span><span class="sxs-lookup"><span data-stu-id="672fe-134">Add a map to your report from the map gallery.</span></span> <span data-ttu-id="672fe-135">На карте имеется один слой, на котором отображаются округи штата Нью-Йорк.</span><span class="sxs-lookup"><span data-stu-id="672fe-135">The map has one layer that displays the counties in New York state.</span></span> <span data-ttu-id="672fe-136">Все округи имеют одну форму — форму многоугольника, заданную на основе пространственных данных, внедряемых в карту из галереи карт.</span><span class="sxs-lookup"><span data-stu-id="672fe-136">The shape of each county is a polygon based on spatial data that is embedded in the map from the map gallery.</span></span>  
  
#### <a name="to-add-a-map-with-the-map-wizard-in-a-new-report"></a><span data-ttu-id="672fe-137">Добавление в новый отчет карты с помощью мастера карт</span><span class="sxs-lookup"><span data-stu-id="672fe-137">To add a map with the map wizard in a new report</span></span>  
  
1.  <span data-ttu-id="672fe-138">Нажмите кнопку **Пуск**, укажите пункт **программы**, выберите пункт [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Построитель отчетов**, а затем щелкните **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="672fe-138">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="672fe-139">Откроется диалоговое окно Приступая к работе.</span><span class="sxs-lookup"><span data-stu-id="672fe-139">The Getting Started dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="672fe-140"> Если диалоговое окно «Приступая к работе» не откроется, выберите команду **Создать**в меню кнопки «Построитель отчетов».</span><span class="sxs-lookup"><span data-stu-id="672fe-140">If the Getting Started dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="672fe-141">Убедитесь, что на панели слева выбран пункт **Отчет** .</span><span class="sxs-lookup"><span data-stu-id="672fe-141">In the left pane, verify that **Report** is selected.</span></span>  
  
3.  <span data-ttu-id="672fe-142">На правой панели щелкните **Мастер карт**.</span><span class="sxs-lookup"><span data-stu-id="672fe-142">In the right pane, click **Map Wizard**.</span></span>  
  
4.  <span data-ttu-id="672fe-143">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="672fe-143">Click **Create**.</span></span>  
  
5.  <span data-ttu-id="672fe-144">На странице**Выбор источника пространственных данных** убедитесь, что выбран параметр **Галерея карт** .</span><span class="sxs-lookup"><span data-stu-id="672fe-144">**Choose a source of spatial data** page, verify that **Map gallery** is selected.</span></span>  
  
6.  <span data-ttu-id="672fe-145">На панели «Галерея карт» разверните узел **Штаты по округам** в узле **США**и выберите **Нью-Йорк**.</span><span class="sxs-lookup"><span data-stu-id="672fe-145">In the Map Gallery pane, expand **States by County** under **USA**, and click **New York**.</span></span>  
  
     <span data-ttu-id="672fe-146">На панели «Предварительный просмотр карты» отобразится карта округов штата Нью-Йорк.</span><span class="sxs-lookup"><span data-stu-id="672fe-146">The Map Preview pane displays the New York county map.</span></span>  
  
7.  <span data-ttu-id="672fe-147">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-147">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="672fe-148">На странице **Выбор пространственных данных и параметров просмотра карты** примите значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="672fe-148">On the **Choose spatial data and map view options** page, accept the defaults.</span></span> <span data-ttu-id="672fe-149">По умолчанию все элементы карты из галереи карт автоматически внедряются в определение отчета.</span><span class="sxs-lookup"><span data-stu-id="672fe-149">By default, map elements from a map gallery will automatically be embedded in the report definition.</span></span>  
  
9. <span data-ttu-id="672fe-150">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-150">Click **Next**.</span></span>  
  
10. <span data-ttu-id="672fe-151">На странице **Выбор визуализации карты** выберите параметр **Простая карта** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-151">On the **Choose map visualization** page, verify **Basic Map** is selected, and click **Next**.</span></span>  
  
11. <span data-ttu-id="672fe-152">На странице **Выбор цветовой схемы и визуализации данных** выберите параметр **Отображать метки** .</span><span class="sxs-lookup"><span data-stu-id="672fe-152">On the **Choose color theme and data visualization** page, select the **Display labels** option.</span></span>  
  
12. <span data-ttu-id="672fe-153">Если флажок **Одноцветная карта** установлен, снимите его.</span><span class="sxs-lookup"><span data-stu-id="672fe-153">If it is selected, clear the **Single color map** option.</span></span>  
  
13. <span data-ttu-id="672fe-154">В раскрывающемся списке **поле данных** выберите #COUNTYNAME.</span><span class="sxs-lookup"><span data-stu-id="672fe-154">From the **Data field** drop-down list, click #COUNTYNAME.</span></span> <span data-ttu-id="672fe-155">На панели «Предварительный просмотр карты» в мастере отображаются следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="672fe-155">The Map Preview pane in the wizard displays the following items:</span></span>  
  
    -   <span data-ttu-id="672fe-156">Заголовок с текстом **Заголовок карты**.</span><span class="sxs-lookup"><span data-stu-id="672fe-156">A title with the text **Map Title**.</span></span>  
  
    -   <span data-ttu-id="672fe-157">На карте отображаются округи, входящие в штат Нью-Йорк, причем каждый из округов окрашен в собственный цвет, а его название выведено в наиболее подходящем месте площади этого округа.</span><span class="sxs-lookup"><span data-stu-id="672fe-157">A map that displays counties in New York where each county is a different color and the county name appears wherever it fits over the county area.</span></span>  
  
    -   <span data-ttu-id="672fe-158">Условные обозначения, содержащие заголовок и перечень элементов от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="672fe-158">A legend that contains a title and a list of items 1 through 5.</span></span>  
  
    -   <span data-ttu-id="672fe-159">Цветовая шкала, содержащая значения от 0 до 160 и отсутствие цвета.</span><span class="sxs-lookup"><span data-stu-id="672fe-159">A color scale that contains values 0 to 160 and no color.</span></span>  
  
    -   <span data-ttu-id="672fe-160">Шкала расстояний, отображающая расстояния в километрах и милях.</span><span class="sxs-lookup"><span data-stu-id="672fe-160">A distance scale that displays kilometers (km) and miles (mi).</span></span>  
  
14. <span data-ttu-id="672fe-161">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="672fe-161">Click **Finish**.</span></span>  
  
     <span data-ttu-id="672fe-162">Карта добавляется в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-162">The map is added to the design surface.</span></span>  
  
15. <span data-ttu-id="672fe-163">Щелкните карту, чтобы выбрать ее и отобразить панель **Слои карты**.</span><span class="sxs-lookup"><span data-stu-id="672fe-163">Click the map to select it and display the **Map Layers Pane**.</span></span> <span data-ttu-id="672fe-164">Панель **Слои карты** показывает один слой многоугольников типа **Внедренный**.</span><span class="sxs-lookup"><span data-stu-id="672fe-164">The **Map Layers Pane** shows one polygon layer of layer type **Embedded**.</span></span> <span data-ttu-id="672fe-165">Каждый округ представляет собой элемент карты, внедренный в этот слой.</span><span class="sxs-lookup"><span data-stu-id="672fe-165">Each county is an embedded map element on this layer.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="672fe-166">Если панель **Слои карты** не видна, она может отображаться за пределами текущего представления.</span><span class="sxs-lookup"><span data-stu-id="672fe-166">If you do not see the **Map Layers** pane, it might be displayed outside your current view.</span></span> <span data-ttu-id="672fe-167">Используйте полосу прокрутки в нижней части окна в режиме конструктора для перемещения представления.</span><span class="sxs-lookup"><span data-stu-id="672fe-167">Use the scroll bar at the bottom of the Design view window to change your view.</span></span> <span data-ttu-id="672fe-168">Также можно снять флажок параметра **Свойства** или **Данные отчета** на вкладке **Вид** , чтобы освободить дополнительную область конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-168">Alternatively, in the **View** tab, clear the **Properties** or the **Report Data** option to provide more design surface area.</span></span>  
  
16. <span data-ttu-id="672fe-169">Щелкните правой кнопкой мыши заголовок карты и выберите пункт **Свойства заголовка**.</span><span class="sxs-lookup"><span data-stu-id="672fe-169">Right-click the map title, and then click **Title Properties**.</span></span>  
  
17. <span data-ttu-id="672fe-170">Замените текст заголовка текстом **Продажи по магазинам**.</span><span class="sxs-lookup"><span data-stu-id="672fe-170">Replace the title text with **Sales by Store**.</span></span>  
  
18. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
19. <span data-ttu-id="672fe-171">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="672fe-171">Preview the report.</span></span>  
  
 <span data-ttu-id="672fe-172">В готовом к просмотру отчете отображается заголовок карты, карта и шкала расстояний.</span><span class="sxs-lookup"><span data-stu-id="672fe-172">The rendered report displays the map title, the map, and the distance scale.</span></span> <span data-ttu-id="672fe-173">Округи находятся на слое многоугольников карты.</span><span class="sxs-lookup"><span data-stu-id="672fe-173">The counties are on a map polygon layer.</span></span> <span data-ttu-id="672fe-174">Каждый округ представляет собой многоугольник, окрашенный в определенный цвет цветовой палитры, однако цвета не связаны с данными.</span><span class="sxs-lookup"><span data-stu-id="672fe-174">Each county is a polygon that varies by color from a color palette, but the colors are not associated with any data.</span></span> <span data-ttu-id="672fe-175">Шкала расстояний отображает расстояния в километрах и в милях.</span><span class="sxs-lookup"><span data-stu-id="672fe-175">The distance scale displays distances in both kilometers and miles.</span></span>  
  
 <span data-ttu-id="672fe-176">Условные обозначения и цветовая шкала не отображаются на этом этапе, поскольку отсутствуют аналитические данные, связанные с каждым из округов.</span><span class="sxs-lookup"><span data-stu-id="672fe-176">The map legend and color scale do not yet appear because there is no analytical data associated with each county.</span></span> <span data-ttu-id="672fe-177">Добавление аналитических данных описано в этом учебнике ниже.</span><span class="sxs-lookup"><span data-stu-id="672fe-177">You will add analytical data later in this tutorial.</span></span>  
  
##  <a name="2-add-a-map-point-layer-to-display-store-locations"></a><a name="PointLayer"></a><span data-ttu-id="672fe-178">2. Добавление слоя точек на карте для отображения расположений магазинов</span><span class="sxs-lookup"><span data-stu-id="672fe-178">2. Add a Map Point Layer to Display Store Locations</span></span>  
 <span data-ttu-id="672fe-179">Чтобы добавить слой точек, в котором отображается местоположение магазинов, воспользуйтесь мастером слоев карты.</span><span class="sxs-lookup"><span data-stu-id="672fe-179">Use the map layer wizard to add a point layer that displays the locations of stores.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="672fe-180">В этом учебнике запрос уже содержит значения данных, поэтому внешний источник данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="672fe-180">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="672fe-181">В связи с этим запрос получается весьма длинным.</span><span class="sxs-lookup"><span data-stu-id="672fe-181">This makes the query quite long.</span></span> <span data-ttu-id="672fe-182">В рабочей среде запрос не будет содержать данные.</span><span class="sxs-lookup"><span data-stu-id="672fe-182">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="672fe-183">Этот запрос содержит данные только в учебных целях.</span><span class="sxs-lookup"><span data-stu-id="672fe-183">This is for learning purposes only.</span></span>  
  
#### <a name="to-add-a-point-layer-based-on-a-sql-server-spatial-query"></a><span data-ttu-id="672fe-184">Добавление слоя точек на основе пространственного запроса SQL Server</span><span class="sxs-lookup"><span data-stu-id="672fe-184">To add a point layer based on a SQL Server spatial query</span></span>  
  
1.  <span data-ttu-id="672fe-185">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-185">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="672fe-186">Дважды щелкните карту, чтобы отобразить панель **Слой карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-186">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="672fe-187">На панели инструментов нажмите кнопку **Мастер создания слоя**![rs_IconMapLayerWizard](../../2014/tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard").</span><span class="sxs-lookup"><span data-stu-id="672fe-187">On the toolbar, click the **New layer wizard** button ![rs_IconMapLayerWizard](../../2014/tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard").</span></span>  
  
3.  <span data-ttu-id="672fe-188">На странице **Выбор источника пространственных данных** выберите параметр **Пространственный запрос SQL Server**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-188">On the **Choose a source of spatial data** page, select **SQL Server spatial query**, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="672fe-189">На странице **Выбор набора данных с пространственными данными SQL Server** нажмите **Добавить новый набор данных с пространственными данными SQL Server**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-189">On the **Choose a dataset with SQL Server spatial data** page, click **Add a new dataset with SQL Server spatial data**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="672fe-190">На странице **Выбор соединения с источником пространственных данных SQL Server** выберите существующий источник данных или перейдите к серверу отчетов и выберите источник данных.</span><span class="sxs-lookup"><span data-stu-id="672fe-190">On the **Choose a connection to a SQL Server spatial data source** page, select an existing data source or browse to the report server and select a data source.</span></span>  
  
6.  <span data-ttu-id="672fe-191">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-191">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="672fe-192">На странице Конструирование запроса нажмите кнопку **изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="672fe-192">On the Design a Query page, click **Edit as Text**.</span></span>  
  
8.  <span data-ttu-id="672fe-193">Вставьте на панель запроса следующий текст:</span><span class="sxs-lookup"><span data-stu-id="672fe-193">Paste the following text in the query pane:</span></span>  
  
    ```  
    Select 114 as StoreKey, 'Contoso Albany Store' as StoreName, 1125 as SellingArea, 'Albany' as City, 'Albany' as County,   
     CAST(1000000 as money) as Sales, CAST('POINT(-73.7472924218681 42.6564617079878)' as geography) AS SpatialLocation  
    UNION ALL SELECT 115 AS StoreKey, 'Contoso New York No.1 Store' AS  StoreName, 500 as SellingArea, 'New York' AS City, 'New York City' as County,  
     CAST('2000000' as money) as Sales, CAST('POINT(-73.9922069374483 40.7549638237402)' as geography) AS SpatialLocation  
    UNION ALL Select 116 as StoreKey, 'Contoso Rochester No.1 Store' as StoreName, 462 as SellingArea, 'Rochester' as City,  'Monroe' as County,    
     CAST(3000000 as money) as Sales, CAST('POINT(-77.624041566786 43.1547066024338)' as geography)  AS SpatialLocation  
    UNION ALL Select 117 as StoreKey, 'Contoso New York No.2 Store' as StoreName, 700 as SellingArea, 'New York' as City,'New York City' as County,    
      CAST(4000000 as money) as Sales, CAST('POINT(-73.9712488 40.7830603)' as geography) AS SpatialLocation  
    UNION ALL Select 118 as StoreKey, 'Contoso Syracuse Store' as StoreName, 680 as SellingArea, 'Syracuse' as City, 'Onondaga' as County,  
     CAST(5000000 as money) as Sales, CAST('POINT(-76.1349120532546 43.0610223535974)' as geography) AS SpatialLocation  
    UNION ALL Select 120 as StoreKey, 'Contoso Plattsburgh Store' as StoreName, 560 as SellingArea, 'Plattsburgh' as City,  'Clinton' as County,  
     CAST(6000000 as money) as Sales, CAST('POINT(-73.4728622833178 44.7028831413324)' as geography) AS SpatialLocation  
    UNION ALL Select 121 as StoreKey, 'Contoso Brooklyn Store' as StoreName, 1125 as SellingArea, 'Brooklyn' as City, 'New York City' as County,  
     CAST(7000000 as money) as Sales, CAST('POINT (-73.9638533447143 40.6785123489351)' as geography) AS SpatialLocation  
    UNION ALL Select 122 as StoreKey, 'Contoso Oswego Store' as StoreName, 500 as SellingArea, 'Oswego' as City, 'Oswego' as County,    
     CAST(8000000 as money) as Sales, CAST('POINT(-76.4602850815536 43.4353224527794)' as geography) AS SpatialLocation  
    UNION ALL Select 123 as StoreKey, 'Contoso Ithaca Store' as StoreName, 460 as SellingArea, 'Ithaca' as City, 'Tompkins' as County,  
     CAST(9000000 as money) as Sales, CAST('POINT(-76.5001866085881 42.4310489934743)' as geography) AS SpatialLocation  
    UNION ALL Select 124 as StoreKey, 'Contoso Rochester No.2 Store' as StoreName, 700 as SellingArea, 'Rochester' as City, 'Monroe' as County,    
     CAST(100000 as money) as Sales, CAST('POINT(-77.6240415667866 43.1547066024338)' as geography) AS SpatialLocation  
    UNION ALL Select 125 as StoreKey, 'Contoso Queens Store' as StoreName, 700 as SellingArea,'Queens' as City, 'New York City' as County,  
     CAST(500000 as money) as Sales, CAST('POINT(-73.7930979029883 40.7152781765927)' as geography) AS SpatialLocation  
    UNION ALL Select 126 as StoreKey, 'Contoso Elmira Store' as StoreName, 680 as SellingArea, 'Elmira' as City, 'Chemung' as County,  
     CAST(800000 as money) as Sales, CAST('POINT(-76.7397414783301 42.0736492742663)' as geography) AS SpatialLocation  
    UNION ALL Select 127 as StoreKey, 'Contoso Poestenkill Store' as StoreName, 455 as SellingArea, 'Poestenkill' as City, 'Rensselaer' as County,    
    CAST(1500000 as money) as Sales, CAST('POINT(-73.5626737425063 42.6940551238618)' as geography) AS SpatialLocation  
    ```  
  
9. <span data-ttu-id="672fe-194">На панели инструментов конструктора запросов нажмите кнопку **выполнить** (**!**).</span><span class="sxs-lookup"><span data-stu-id="672fe-194">On the query designer toolbar, click **Run** (**!**).</span></span>  
  
     <span data-ttu-id="672fe-195">Результирующий набор отображает семь столбцов: StoreKey, StoreName, SellingArea, City, округ, Sales и SpatialLocation.</span><span class="sxs-lookup"><span data-stu-id="672fe-195">The result set displays seven columns: StoreKey, StoreName, SellingArea, City, County, Sales, and SpatialLocation.</span></span> <span data-ttu-id="672fe-196">Эти данные представляют определенную совокупность магазинов в штате Нью-Йорк, торгующих потребительскими товарами.</span><span class="sxs-lookup"><span data-stu-id="672fe-196">This data represents a set of stores in New York State that sell consumer goods.</span></span> <span data-ttu-id="672fe-197">Каждая строка в результирующем наборе содержит идентификатор магазина, его название, торговую площадь, используемую для демонстрации товаров, город и округ расположения, общий объем продаж и пространственное положение (широту и долготу).</span><span class="sxs-lookup"><span data-stu-id="672fe-197">Each row in the result set contains a store identifier, store name, the area available for product display, the city and county where the store is located, the sales total, and the spatial location in longitude and latitude.</span></span> <span data-ttu-id="672fe-198">Торговая площадь лежит в диапазоне от 455 кв. ф. до 1125 кв. ф.</span><span class="sxs-lookup"><span data-stu-id="672fe-198">The display area ranges from 455 square feet to 1125 square feet.</span></span>  
  
10. <span data-ttu-id="672fe-199">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-199">Click **Next**.</span></span>  
  
     <span data-ttu-id="672fe-200">Будет создан набор данных отчета с именем DataSet1.</span><span class="sxs-lookup"><span data-stu-id="672fe-200">The report dataset named DataSet1 is created for you.</span></span> <span data-ttu-id="672fe-201">После завершения работы с мастером можно просмотреть коллекцию полей отчета в области «Данные отчета».</span><span class="sxs-lookup"><span data-stu-id="672fe-201">After you complete the wizard, you can use the Report Data to its field collection.</span></span>  
  
11. <span data-ttu-id="672fe-202">На странице **Выбор пространственных данных и параметров представления карт** убедитесь, что **пространственное поле** имеет значение, `SpatialLocation` а **тип слоя** — **Point**.</span><span class="sxs-lookup"><span data-stu-id="672fe-202">On the **Choose a spatial data and map view options** page, verify that the **Spatial field** is `SpatialLocation` and that the **Layer type** is **Point**.</span></span> <span data-ttu-id="672fe-203">Примите другие значения по умолчанию на этой странице.</span><span class="sxs-lookup"><span data-stu-id="672fe-203">Accept the other defaults on this page.</span></span>  
  
     <span data-ttu-id="672fe-204">На представлении карты будут отображены окружности, отмечающие местоположения магазинов.</span><span class="sxs-lookup"><span data-stu-id="672fe-204">The map view displays circles that mark the location of each store.</span></span>  
  
12. <span data-ttu-id="672fe-205">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-205">Click **Next**.</span></span>  
  
13. <span data-ttu-id="672fe-206">Укажите тип карты, для которого отображение маркеров зависит от аналитических данных.</span><span class="sxs-lookup"><span data-stu-id="672fe-206">Specify a map type that displays markers that vary by analytic data.</span></span> <span data-ttu-id="672fe-207">На странице «Выбор параметров визуализации карты» выберите **Аналитическая карта с отметками**, затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-207">On the Choose map visualization page, click **Analytical Marker Map**, and then click **Next**.</span></span>  
  
14. <span data-ttu-id="672fe-208">На странице **Выбор набора аналитических данных** щелкните DataSet1.</span><span class="sxs-lookup"><span data-stu-id="672fe-208">On the **Choose the analytical dataset** page, click DataSet1.</span></span> <span data-ttu-id="672fe-209">На новом слое точек будет отображен набор данных, содержащий аналитические и пространственные данные.</span><span class="sxs-lookup"><span data-stu-id="672fe-209">This dataset contains both analytical data and spatial data that will be displayed on the new point layer.</span></span>  
  
15. <span data-ttu-id="672fe-210">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-210">Click **Next**.</span></span>  
  
16. <span data-ttu-id="672fe-211">На странице **Выбор цветовой темы и визуализации данных** снимите флажок **Использовать цвета маркеров для визуализации данных** и установите флажок **Использовать типы маркеров для визуализации данных**.</span><span class="sxs-lookup"><span data-stu-id="672fe-211">On the **Choose color theme and data visualization** page, clear the **Use marker colors to visualize data** option, and then select the option **Use marker types to visualize data**.</span></span>  
  
17. <span data-ttu-id="672fe-212">В **Поле данных**выберите `[Sum(SellingArea)]` , чтобы задать разные типы маркеров в зависимости от размера площади, используемой для демонстрации продуктов.</span><span class="sxs-lookup"><span data-stu-id="672fe-212">In **Data field**, select `[Sum(SellingArea)]` to vary marker types by the size of the area a store sets aside to display the products.</span></span>  
  
18. <span data-ttu-id="672fe-213">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="672fe-213">Click **Finish**.</span></span>  
  
     <span data-ttu-id="672fe-214">В отчет будет добавлен слой карты.</span><span class="sxs-lookup"><span data-stu-id="672fe-214">The map layer is added to the report.</span></span> <span data-ttu-id="672fe-215">В условном обозначении будут отображены типы маркеров, зависящих от значения SellingArea.</span><span class="sxs-lookup"><span data-stu-id="672fe-215">The legend displays marker types based on SellingArea values.</span></span>  
  
     <span data-ttu-id="672fe-216">Дважды щелкните карту, чтобы отобразить панель **Слой карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-216">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="672fe-217">На панели **Слой карты** отображается новый слой PointLayer1 с источником пространственных данных типа **DataRegion**.</span><span class="sxs-lookup"><span data-stu-id="672fe-217">The **Map Layer** pane displays a new layer, PointLayer1, with spatial data source type **DataRegion**.</span></span>  
  
19. <span data-ttu-id="672fe-218">Добавьте заголовок условных обозначений.</span><span class="sxs-lookup"><span data-stu-id="672fe-218">Add a legend title.</span></span> <span data-ttu-id="672fe-219">Щелкните правой кнопкой мыши заголовок условных обозначений и выберите пункт **Свойства заголовка условных обозначений**.</span><span class="sxs-lookup"><span data-stu-id="672fe-219">Right-click the legend title, and then click **Legend Title Properties**.</span></span>  
  
20. <span data-ttu-id="672fe-220">Удалите название и введите **Торговая площадь (в кв.ф.)**.</span><span class="sxs-lookup"><span data-stu-id="672fe-220">Delete the title, and type **Display Area (Square Feet)**.</span></span>  
  
21. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
22. <span data-ttu-id="672fe-221">Просмотрите значения по умолчанию, заданные мастером.</span><span class="sxs-lookup"><span data-stu-id="672fe-221">View the default values that were set by the wizard.</span></span> <span data-ttu-id="672fe-222">На панели **Слои карты**щелкните правой кнопкой мыши слой точек, а затем щелкните **Правило типа маркера**.</span><span class="sxs-lookup"><span data-stu-id="672fe-222">In the **Map Layers Pane**, right-click the point layer, and then click **Marker Type Rule**.</span></span>  
  
     <span data-ttu-id="672fe-223">На вкладке **Общие** маркеры указаны в порядке, в котором они отображаются в условном обозначении.</span><span class="sxs-lookup"><span data-stu-id="672fe-223">On the **General** tab, the markers are listed in the order in which they appear in the legend.</span></span> <span data-ttu-id="672fe-224">На вкладке **Распространение** количество поддиапазонов равно 5.</span><span class="sxs-lookup"><span data-stu-id="672fe-224">On the **Distribution** tab, the number of subranges is 5.</span></span> <span data-ttu-id="672fe-225">На вкладке **Условные обозначения** текст условного обозначения настроен на отображение начального и конечного значений в каждом из диапазонов.</span><span class="sxs-lookup"><span data-stu-id="672fe-225">On the **Legend** tab, the legend text is set to display the start and end value in each range.</span></span>  
  
23. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
24. <span data-ttu-id="672fe-226">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="672fe-226">Preview the report.</span></span>  
  
 <span data-ttu-id="672fe-227">На карте отображаются местоположения магазинов в штате Нью-Йорк.</span><span class="sxs-lookup"><span data-stu-id="672fe-227">The map displays the locations of stores in New York state.</span></span> <span data-ttu-id="672fe-228">Тип маркера для каждого магазина зависит от торговой площади.</span><span class="sxs-lookup"><span data-stu-id="672fe-228">The marker type for each store is based on the display area.</span></span> <span data-ttu-id="672fe-229">Пять диапазонов площади рассчитаны автоматически.</span><span class="sxs-lookup"><span data-stu-id="672fe-229">Five ranges of display area were automatically calculated for you.</span></span>  
  
##  <a name="3-add-a-map-line-layer-to-display-a-route"></a><a name="LineLayer"></a><span data-ttu-id="672fe-230">3. Добавление слоя линий на карте для отображения маршрута</span><span class="sxs-lookup"><span data-stu-id="672fe-230">3. Add a Map Line Layer to Display a Route</span></span>  
 <span data-ttu-id="672fe-231">С помощью мастера слоя карты добавьте слой карты, который будет показывать маршрут между двумя магазинами.</span><span class="sxs-lookup"><span data-stu-id="672fe-231">Use the map layer wizard to add a map layer that displays a route between two stores.</span></span> <span data-ttu-id="672fe-232">В этом учебнике создается путь от трех местоположений магазинов.</span><span class="sxs-lookup"><span data-stu-id="672fe-232">In this tutorial, the path is created from three store locations.</span></span> <span data-ttu-id="672fe-233">В бизнес-приложениях путь может представлять оптимальный маршрут между магазинами.</span><span class="sxs-lookup"><span data-stu-id="672fe-233">In a business application, the path might be the best route between stores.</span></span>  
  
#### <a name="to-add-a-line-layer-to-map"></a><span data-ttu-id="672fe-234">Добавление на карту слоя линий</span><span class="sxs-lookup"><span data-stu-id="672fe-234">To add a line layer to map</span></span>  
  
1.  <span data-ttu-id="672fe-235">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-235">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="672fe-236">Дважды щелкните карту, чтобы отобразить панель **Слой карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-236">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="672fe-237">На панели инструментов нажмите кнопку **Мастер создания слоя**.</span><span class="sxs-lookup"><span data-stu-id="672fe-237">On the toolbar, click **New layer wizard**.</span></span>  
  
3.  <span data-ttu-id="672fe-238">На странице **Выбор источника пространственных данных** выберите **SQL Server пространственный запрос** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-238">On the **Choose a source of spatial data** page, select **SQL Server spatial query** and click **Next**.</span></span>  
  
4.  <span data-ttu-id="672fe-239">На странице **Выбор набора данных с пространственными данными SQL Server** нажмите **Добавить новый набор данных с пространственными данными SQL Server** , затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-239">On the **Choose a dataset with SQL Server spatial data** page, click **Add a new dataset with SQL Server spatial data** and click **Next**.</span></span>  
  
5.  <span data-ttu-id="672fe-240">На странице **Выбор соединения с источником пространственных данных SQL Server**выберите DataSource1 — источник данных, созданный в первой процедуре.</span><span class="sxs-lookup"><span data-stu-id="672fe-240">On the **Choose a connection to a SQL Server spatial data source**, select DataSource1, the data source that you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="672fe-241">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-241">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="672fe-242">На странице **Конструирование запроса** нажмите кнопку **изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="672fe-242">On the **Design a Query** page, click **Edit as Text**.</span></span> <span data-ttu-id="672fe-243">Конструктор запросов переключается в текстовый режим.</span><span class="sxs-lookup"><span data-stu-id="672fe-243">The query designer switches to text-based mode.</span></span>  
  
8.  <span data-ttu-id="672fe-244">Вставьте на панель запроса следующий текст:</span><span class="sxs-lookup"><span data-stu-id="672fe-244">Paste the following text in the query pane:</span></span>  
  
    ```  
    SELECT N'Path' AS Name, CAST('LINESTRING(  
       -76.5001866085881 42.4310489934743,  
       -76.4602850815536 43.4353224527794,  
       -73.4728622833178 44.7028831413324)' AS geography) as Route  
    ```  
  
9. <span data-ttu-id="672fe-245">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-245">Click **Next**.</span></span>  
  
     <span data-ttu-id="672fe-246">На карте отображается путь, соединяющий три магазина.</span><span class="sxs-lookup"><span data-stu-id="672fe-246">A path appears on the map that connects three stores.</span></span>  
  
10. <span data-ttu-id="672fe-247">На странице **Выбор пространственных данных и параметров просмотра карты** установите для параметра **Пространственное поле** значение **Маршрут** , а для параметра **Тип слоя** — значение **Линейный**.</span><span class="sxs-lookup"><span data-stu-id="672fe-247">On the **Choose spatial data and map view options** page, verify that the **Spatial field** is **Route** and that the **Layer type** is **Line**.</span></span> <span data-ttu-id="672fe-248">Остальные значения примите по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="672fe-248">Accept the other defaults.</span></span>  
  
     <span data-ttu-id="672fe-249">На карте отображается путь от магазина в северной части штата Нью-Йорк к магазину в южной части штата Нью-Йорк.</span><span class="sxs-lookup"><span data-stu-id="672fe-249">The map view displays a path from a store in the northern part of New York state to a store in the southern part of New York state.</span></span>  
  
11. <span data-ttu-id="672fe-250">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-250">Click **Next**.</span></span>  
  
12. <span data-ttu-id="672fe-251">На странице **Выбор визуализации карты** нажмите **Базовая карта линий**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="672fe-251">On the **Choose map visualization** page, click **Basic Line Map**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="672fe-252">На странице **Выбор цветовой схемы и визуализации данных**выберите параметр **Одноцветная карта**.</span><span class="sxs-lookup"><span data-stu-id="672fe-252">On the **Choose color theme and data visualization**, select the option **Single color map**.</span></span> <span data-ttu-id="672fe-253">Путь отображается одним цветом, в соответствии с выбранной темой.</span><span class="sxs-lookup"><span data-stu-id="672fe-253">The path appears as a single color based on the selected theme.</span></span>  
  
14. <span data-ttu-id="672fe-254">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="672fe-254">Click **Finish**.</span></span>  
  
 <span data-ttu-id="672fe-255">На карте отображается новый слой линий с источником пространственных данных типа **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="672fe-255">The map displays a new line layer with spatial data source type **DataSet**.</span></span> <span data-ttu-id="672fe-256">В этом примере пространственные данные поступают из набора данных, но нет никаких аналитических данных, связанных с этой линией.</span><span class="sxs-lookup"><span data-stu-id="672fe-256">In this example, the spatial data comes from a dataset but no analytical data is associated with the line.</span></span>  
  
##  <a name="4-add-a-bing-maps-tile-background"></a><a name="TileLayer"></a><span data-ttu-id="672fe-257">4. Добавление мозаичного фона Bing Maps</span><span class="sxs-lookup"><span data-stu-id="672fe-257">4. Add a Bing Maps Tile Background</span></span>  
 <span data-ttu-id="672fe-258">Добавление слоя карты, который используется для отображения мозаичного фона Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="672fe-258">Add a map layer that displays a Bing Maps tile background.</span></span>  
  
#### <a name="to-add-a-virtual-earth-tile-background"></a><span data-ttu-id="672fe-259">Добавление мозаичного фона Virtual Earth</span><span class="sxs-lookup"><span data-stu-id="672fe-259">To add a Virtual Earth tile background</span></span>  
  
1.  <span data-ttu-id="672fe-260">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-260">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="672fe-261">Дважды щелкните карту, чтобы отобразить панель **Слой карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-261">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="672fe-262">На панели инструментов нажмите кнопку **Добавить слой**![rs_IconMapAddLayer](../../2014/tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer").</span><span class="sxs-lookup"><span data-stu-id="672fe-262">On the toolbar, click **Add Layer**![rs_IconMapAddLayer](../../2014/tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer").</span></span>  
  
3.  <span data-ttu-id="672fe-263">Из раскрывающегося списка выберите пункт **Слой мозаики**.</span><span class="sxs-lookup"><span data-stu-id="672fe-263">From the drop-down list, click **Tile Layer**.</span></span>  
  
     <span data-ttu-id="672fe-264">Последним слоем на панели **Слой карты** является слой TileLayer1.</span><span class="sxs-lookup"><span data-stu-id="672fe-264">The last layer in the **Map Layer** pane is TileLayer1.</span></span> <span data-ttu-id="672fe-265">По умолчанию мозаичный слой отображается в стиле дорожной карты.</span><span class="sxs-lookup"><span data-stu-id="672fe-265">By default, the tile layer displays the road map style.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="672fe-266">В мастере также можно добавить мозаичный слой на странице **Выбор пространственных данных и параметров отображения карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-266">In the wizard, you can also add a tile layer on the **Choose spatial data and map view options** page.</span></span> <span data-ttu-id="672fe-267">Для этого выберите **Добавить фон Bing Maps для данного представления карты**.</span><span class="sxs-lookup"><span data-stu-id="672fe-267">To do this, select **Add a Bing Maps background for this map view**.</span></span> <span data-ttu-id="672fe-268">В подготовленном к просмотру отчете мозаичный фон Bing Maps отображается в соответствии с текущими параметрами центрирования и масштабирования карты.</span><span class="sxs-lookup"><span data-stu-id="672fe-268">In a rendered report, the tile background displays Bing Maps tiles for the current map viewport center and zoom level.</span></span>  
  
4.  <span data-ttu-id="672fe-269">Щелкните на TileLayer1 стрелку вниз, а затем выберите **Свойства мозаичных элементов**.</span><span class="sxs-lookup"><span data-stu-id="672fe-269">Click the down arrow on TileLayer1, and then click **Tile Properties**.</span></span>  
  
5.  <span data-ttu-id="672fe-270">В поле **Тип**выберите **Воздушный**.</span><span class="sxs-lookup"><span data-stu-id="672fe-270">In **Type**, select **Aerial**.</span></span> <span data-ttu-id="672fe-271">Воздушное представление не содержит текста.</span><span class="sxs-lookup"><span data-stu-id="672fe-271">The aerial view does not contain text.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="5-make-a-layer-transparent"></a><a name="Transparent"></a><span data-ttu-id="672fe-272">5. сделать слой прозрачным</span><span class="sxs-lookup"><span data-stu-id="672fe-272">5. Make a Layer Transparent</span></span>  
 <span data-ttu-id="672fe-273">Чтобы настроить отображение элементов на одном слое сквозь другой слой, можно изменять порядок слоев и прозрачность каждого из слоев, пока не будет достигнут необходимый эффект.</span><span class="sxs-lookup"><span data-stu-id="672fe-273">To let the items on one layer show through another layer, you can adjust the order of layers and the transparency of each layer to get the effect that you want.</span></span>  
  
#### <a name="to-set-the-transparency-of-a-layer"></a><span data-ttu-id="672fe-274">Изменение прозрачности слоя</span><span class="sxs-lookup"><span data-stu-id="672fe-274">To set the transparency of a layer</span></span>  
  
1.  <span data-ttu-id="672fe-275">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-275">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="672fe-276">Дважды щелкните карту, чтобы отобразить панель **Слой карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-276">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="672fe-277">Щелкните на PolygonLayer1 стрелку вниз и выберите **Данные слоя**.</span><span class="sxs-lookup"><span data-stu-id="672fe-277">Click the down arrow on PolygonLayer1, and then click **Layer Data**.</span></span> <span data-ttu-id="672fe-278">Открывается диалоговое окно **Свойства слоя многоугольников карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-278">The **Map Polygon Layer Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="672fe-279">Щелкните **Видимость**.</span><span class="sxs-lookup"><span data-stu-id="672fe-279">Click **Visibility**.</span></span>  
  
5.  <span data-ttu-id="672fe-280">В поле **Прозрачность (%)** введите значение **30**.</span><span class="sxs-lookup"><span data-stu-id="672fe-280">In **Transparency (%)**, type **30**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="672fe-281">В области конструктора округа отображаются полупрозрачными.</span><span class="sxs-lookup"><span data-stu-id="672fe-281">The design surface displays the counties as semi-transparent.</span></span>  
  
##  <a name="6-vary-county-color-based-on-sales"></a><a name="Vary"></a><span data-ttu-id="672fe-282">6. Изменяйте цвет района на основе продаж</span><span class="sxs-lookup"><span data-stu-id="672fe-282">6. Vary County Color Based on Sales</span></span>  
 <span data-ttu-id="672fe-283">Все округа на слое многоугольников имеют разные цвета, поскольку обработчик отчетов автоматически назначает им значения цветов из цветовой палитры темы, которую можно выбрать на последней странице шаге мастера создания карты.</span><span class="sxs-lookup"><span data-stu-id="672fe-283">Each county on the polygon layer has a different color because the report processor automatically assigns a color value from the color palette based on the theme that you chose on the last page of the map wizard.</span></span>  
  
 <span data-ttu-id="672fe-284">В последующих шагах укажите правило выбора цвета для связывания цветов с диапазонами значений продаж магазинов по каждому из округов.</span><span class="sxs-lookup"><span data-stu-id="672fe-284">In the following steps, specify a color rule to associate specific colors with a range of store sales for each county.</span></span> <span data-ttu-id="672fe-285">Красный, желтый и зеленый цвета обозначают относительные значения уровня продаж.</span><span class="sxs-lookup"><span data-stu-id="672fe-285">The colors red-yellow-green indicate relative high-middle-low sales.</span></span> <span data-ttu-id="672fe-286">Отформатируйте цветовую шкалу для отображения валюты.</span><span class="sxs-lookup"><span data-stu-id="672fe-286">Format the color scale to show currency.</span></span> <span data-ttu-id="672fe-287">Отобразите диапазоны значений годовых продаж в новых условных обозначениях.</span><span class="sxs-lookup"><span data-stu-id="672fe-287">Display the annual sales ranges in a new legend.</span></span> <span data-ttu-id="672fe-288">Округа, в которых нет магазинов, не будут выделены цветом, чтобы показать, что для них нет связанных данных.</span><span class="sxs-lookup"><span data-stu-id="672fe-288">For counties that do not contain stores, use no color to show that there is no associated data.</span></span>  
  
###  <a name="6a-build-a-relationship-between-spatial-and-analytical-data"></a><a name="Relationship"></a><span data-ttu-id="672fe-289">SP6a.</span><span class="sxs-lookup"><span data-stu-id="672fe-289">6a.</span></span> <span data-ttu-id="672fe-290">Построение связей между пространственными и аналитическими данными</span><span class="sxs-lookup"><span data-stu-id="672fe-290">Build a Relationship between Spatial and Analytical Data</span></span>  
 <span data-ttu-id="672fe-291">Чтобы при окраске фигур округов в соответствии с аналитическими данными границы между ними были различимы, необходимо сначала связать аналитические данные с пространственными.</span><span class="sxs-lookup"><span data-stu-id="672fe-291">To vary the county shapes by color based on analytical data, you first must associate the analytical data with the spatial data.</span></span> <span data-ttu-id="672fe-292">В этом учебнике для сопоставления используются имена округов.</span><span class="sxs-lookup"><span data-stu-id="672fe-292">In this tutorial, you will use the county name to match on.</span></span>  
  
##### <a name="to-build-a-relationship-between-spatial-data-and-analytical-data"></a><span data-ttu-id="672fe-293">Построение связи между пространственными и аналитическими данными</span><span class="sxs-lookup"><span data-stu-id="672fe-293">To build a relationship between spatial data and analytical data</span></span>  
  
1.  <span data-ttu-id="672fe-294">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-294">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="672fe-295">Дважды щелкните карту, чтобы отобразить панель **Слой карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-295">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="672fe-296">Щелкните на PolygonLayer1 стрелку вниз и выберите **Данные слоя**.</span><span class="sxs-lookup"><span data-stu-id="672fe-296">Click the down arrow on PolygonLayer1, and then click **Layer Data**.</span></span> <span data-ttu-id="672fe-297">Открывается диалоговое окно **Свойства слоя многоугольников карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-297">The **Map Polygon Layer Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="672fe-298">Выберите **Аналитические данные**.</span><span class="sxs-lookup"><span data-stu-id="672fe-298">Click **Analytical data**.</span></span>  
  
5.  <span data-ttu-id="672fe-299">В раскрывающемся списке выберите DataSet1.</span><span class="sxs-lookup"><span data-stu-id="672fe-299">From the drop-down list, select DataSet1.</span></span> <span data-ttu-id="672fe-300">Этот набор данных был создан мастером, когда был выбран запрос пространственных данных для округов.</span><span class="sxs-lookup"><span data-stu-id="672fe-300">This dataset was created by the wizard when you specified the spatial data query for the counties.</span></span>  
  
6.  <span data-ttu-id="672fe-301">В списке **Поля для соответствия**нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="672fe-301">In **Fields to match on**, click **Add**.</span></span> <span data-ttu-id="672fe-302">Добавляется новая строка.</span><span class="sxs-lookup"><span data-stu-id="672fe-302">A new row is added.</span></span>  
  
7.  <span data-ttu-id="672fe-303">В поле **Из пространственного набора данных**выберите из раскрывающегося списка COUNTYNAME.</span><span class="sxs-lookup"><span data-stu-id="672fe-303">In **From spatial dataset**, from the drop-down list, click COUNTYNAME.</span></span>  
  
8.  <span data-ttu-id="672fe-304">В поле **Из аналитического набора данных**из раскрывающегося списка выберите [County].</span><span class="sxs-lookup"><span data-stu-id="672fe-304">In **From analytical dataset**, from the drop-down list, click [County].</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="672fe-305">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="672fe-305">Preview the report.</span></span>  
  
 <span data-ttu-id="672fe-306">После выбора поля соответствия в источнике пространственных данных и аналитическом наборе данных обработчик отчета получает возможность группировать аналитические данные на основе элементов карты.</span><span class="sxs-lookup"><span data-stu-id="672fe-306">By specifying a match field from the spatial data source and from the analytical dataset, you enable the report processor to group analytical data based on the map elements.</span></span> <span data-ttu-id="672fe-307">У элемента карты, привязанного к данным, имеется совпадение с указанными значениями.</span><span class="sxs-lookup"><span data-stu-id="672fe-307">A data-bound map element has a successful match for the values that you specified.</span></span>  
  
 <span data-ttu-id="672fe-308">У всех округов, в которых имеются магазины, имеется цвет, определяемый на основе цветовой палитры стиля, выбранного в мастере.</span><span class="sxs-lookup"><span data-stu-id="672fe-308">Each county that contains a store has a color that is based on the color palette for the style that you chose in the wizard.</span></span>  
  
###  <a name="6b-specify-color-rules-for-polygons"></a><a name="ColorRules"></a><span data-ttu-id="672fe-309">6B.</span><span class="sxs-lookup"><span data-stu-id="672fe-309">6b.</span></span> <span data-ttu-id="672fe-310">Указание правил цвета для многоугольников</span><span class="sxs-lookup"><span data-stu-id="672fe-310">Specify Color Rules for Polygons</span></span>  
 <span data-ttu-id="672fe-311">Чтобы создать правило, управляющее выбором различных цветов для округов в зависимости от объема продаж магазина в этом округе, необходимо указать значения диапазона, количество интервалов в отображаемом диапазоне, а также используемые цвета.</span><span class="sxs-lookup"><span data-stu-id="672fe-311">To create a rule that varies the color of each county based store sales, you must specify the range values, the number of divisions within that range that you want to display, and the colors to use.</span></span>  
  
##### <a name="to-specify-color-rules-for-all-polygons-that-have-associated-data"></a><span data-ttu-id="672fe-312">Указание цветовых правил для всех многоугольников, с которыми связаны данные</span><span class="sxs-lookup"><span data-stu-id="672fe-312">To specify color rules for all polygons that have associated data</span></span>  
  
1.  <span data-ttu-id="672fe-313">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-313">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="672fe-314">Щелкните на PolygonLayer1 стрелку вниз и выберите **Правило цвета многоугольника**.</span><span class="sxs-lookup"><span data-stu-id="672fe-314">Click the down arrow on PolygonLayer1, and then click **Polygon Color Rule**.</span></span> <span data-ttu-id="672fe-315">Открывается диалоговое окно **Свойства цветовых правил карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-315">The **Map Color Rules Properties** dialog box opens.</span></span> <span data-ttu-id="672fe-316">Обратите внимание, что выбран параметр цветового правила **Визуализировать данные с помощью цветовой палитры** .</span><span class="sxs-lookup"><span data-stu-id="672fe-316">Notice that the color rule option **Visualize data by using color palette** is selected.</span></span> <span data-ttu-id="672fe-317">Этот параметр был установлен мастером.</span><span class="sxs-lookup"><span data-stu-id="672fe-317">This option was set by the wizard.</span></span>  
  
3.  <span data-ttu-id="672fe-318">Выберите **Визуализировать данные с помощью цветовых диапазонов**.</span><span class="sxs-lookup"><span data-stu-id="672fe-318">Select **Visualize data by using color ranges**.</span></span> <span data-ttu-id="672fe-319">Вместо палитры появляются параметры выбора начального, среднего и конечного цветов.</span><span class="sxs-lookup"><span data-stu-id="672fe-319">The palette option is replaced by start color, middle color, and end color options.</span></span>  
  
4.  <span data-ttu-id="672fe-320">Определите значения диапазонов для продаж в округах.</span><span class="sxs-lookup"><span data-stu-id="672fe-320">Define range values for sales per county.</span></span> <span data-ttu-id="672fe-321">Из раскрывающегося списка **Поле данных**выберите элемент `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="672fe-321">In **Data field**, from the drop-down list, select `[Sum(Sales)]`.</span></span>  
  
5.  <span data-ttu-id="672fe-322">Чтобы валюта отображалась в тысячах, измените выражение на следующее: `=Sum(Fields!Sales.Value)/1000`</span><span class="sxs-lookup"><span data-stu-id="672fe-322">To change the format to display currency in thousands, change the expression to the following: `=Sum(Fields!Sales.Value)/1000`</span></span>  
  
6.  <span data-ttu-id="672fe-323">Измените **Начальный цвет** на **Красный**.</span><span class="sxs-lookup"><span data-stu-id="672fe-323">Change **Start color** to **Red**.</span></span>  
  
7.  <span data-ttu-id="672fe-324">Измените **Конечный цвет** на **Зеленый**.</span><span class="sxs-lookup"><span data-stu-id="672fe-324">Change **End color** to **Green**.</span></span>  
  
     <span data-ttu-id="672fe-325">**Красный** представляет значения низкого уровня продаж, **Желтый** — средние, а **Зеленый** — значения высокого уровня продаж.</span><span class="sxs-lookup"><span data-stu-id="672fe-325">**Red** represents low sales values, **Yellow** represents middle sales values, and **Green** represents high sales values.</span></span> <span data-ttu-id="672fe-326">Обработчик отчета вычисляет цветовой диапазон исходя из этих значений и параметров, выбранных на странице **Распределение** .</span><span class="sxs-lookup"><span data-stu-id="672fe-326">The report processor calculates a range of colors based on these values and the options that you choose on the **Distribution** page.</span></span>  
  
8.  <span data-ttu-id="672fe-327">Щелкните **Распределение**.</span><span class="sxs-lookup"><span data-stu-id="672fe-327">Click **Distribution**.</span></span>  
  
9. <span data-ttu-id="672fe-328">Выберите тип распределения **Оптимальный**.</span><span class="sxs-lookup"><span data-stu-id="672fe-328">Verify that the distribution type is **Optimal**.</span></span> <span data-ttu-id="672fe-329">Для выражения, заданного на шаге 5, оптимальное распределение сортирует значения по поддиапазонам, обеспечивая равномерность распределения элементов по диапазонам и длин диапазонов.</span><span class="sxs-lookup"><span data-stu-id="672fe-329">For the expression from step 5, optimal distribution divides the values into subranges that balance the number of items in each range and the span for each range.</span></span>  
  
10. <span data-ttu-id="672fe-330">Для остальных параметров на этой странице примите значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="672fe-330">Accept the default values for other options on this page.</span></span> <span data-ttu-id="672fe-331">В случае выбора оптимального типа распределения, число поддиапазонов рассчитывается при выполнении отчета.</span><span class="sxs-lookup"><span data-stu-id="672fe-331">When you select the optimal distribution type, the number of subranges are calculated when the report runs.</span></span>  
  
11. <span data-ttu-id="672fe-332">Выберите **Условные обозначения**.</span><span class="sxs-lookup"><span data-stu-id="672fe-332">Click **Legend**.</span></span>  
  
12. <span data-ttu-id="672fe-333">В разделе **Параметры цветовой шкалы**выберите параметр **Показать на цветовой шкале** .</span><span class="sxs-lookup"><span data-stu-id="672fe-333">In **Color scale options**, verify that **Show in color scale** is selected.</span></span>  
  
13. <span data-ttu-id="672fe-334">В раскрывающемся списке **Показать в этих условных обозначениях**выберите пустую строку.</span><span class="sxs-lookup"><span data-stu-id="672fe-334">In **Show in this legend**, from the drop-down list, select the blank line.</span></span> <span data-ttu-id="672fe-335">Пока цветовые диапазоны будут показаны только на цветовой шкале.</span><span class="sxs-lookup"><span data-stu-id="672fe-335">For now, you will show the color ranges only in the color scale.</span></span>  
  
14. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="672fe-336">Цветовая шкала содержит пять цветов: красный, оранжевый, желтый, желто-зеленый и зеленый.</span><span class="sxs-lookup"><span data-stu-id="672fe-336">The color scale displays five colors: red, orange, yellow, yellow green, and green.</span></span> <span data-ttu-id="672fe-337">Каждый цвет представляет диапазон объемов продаж, рассчитанный автоматически на основе объемов продаж по округам.</span><span class="sxs-lookup"><span data-stu-id="672fe-337">Each color represents a sales range that is automatically calculated based on the sales by county.</span></span>  
  
###  <a name="6c-format-the-data-in-the-color-scale-as-currency"></a><a name="ColorScale"></a><span data-ttu-id="672fe-338">6c.</span><span class="sxs-lookup"><span data-stu-id="672fe-338">6c.</span></span> <span data-ttu-id="672fe-339">Форматирование данных в цветовой шкале как различных валют</span><span class="sxs-lookup"><span data-stu-id="672fe-339">Format the Data in the Color Scale as Currency</span></span>  
 <span data-ttu-id="672fe-340">По умолчанию для данных задается общий формат.</span><span class="sxs-lookup"><span data-stu-id="672fe-340">By default, data has a general format.</span></span> <span data-ttu-id="672fe-341">Для них можно применять пользовательские форматы.</span><span class="sxs-lookup"><span data-stu-id="672fe-341">You can apply custom formats.</span></span>  
  
##### <a name="to-set-the-format-for-the-color-scale"></a><span data-ttu-id="672fe-342">Задание формата цветовой шкалы</span><span class="sxs-lookup"><span data-stu-id="672fe-342">To set the format for the color scale</span></span>  
  
1.  <span data-ttu-id="672fe-343">Щелкните правой кнопкой мыши цветовую шкалу и выберите пункт **Свойства цветовой шкалы**.</span><span class="sxs-lookup"><span data-stu-id="672fe-343">Right-click the color scale, and then click **Color Scale Properties**.</span></span>  
  
2.  <span data-ttu-id="672fe-344">Выберите **Число**.</span><span class="sxs-lookup"><span data-stu-id="672fe-344">Click **Number**.</span></span>  
  
3.  <span data-ttu-id="672fe-345">В пункте **Категория**выберите **Валюта**.</span><span class="sxs-lookup"><span data-stu-id="672fe-345">In **Category**, click **Currency**.</span></span>  
  
4.  <span data-ttu-id="672fe-346">В поле **Десятичные разряды**введите **0**.</span><span class="sxs-lookup"><span data-stu-id="672fe-346">In **Decimal places**, type **0**.</span></span> <span data-ttu-id="672fe-347">Этот формат указывает на отсутствие десятичных разрядов для валюты.</span><span class="sxs-lookup"><span data-stu-id="672fe-347">This format specifies no decimal places for currency.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="672fe-348">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="672fe-348">Preview the report.</span></span>  
  
 <span data-ttu-id="672fe-349">Цветовая шкала отображает годовой объем продаж в формате денежной суммы для каждого из диапазонов.</span><span class="sxs-lookup"><span data-stu-id="672fe-349">The color scale displays annual sales in currency format for each range.</span></span>  
  
###  <a name="6d-create-a-new-legend"></a><a name="NewLegend"></a><span data-ttu-id="672fe-350">6d.</span><span class="sxs-lookup"><span data-stu-id="672fe-350">6d.</span></span> <span data-ttu-id="672fe-351">Создание новых условных обозначений</span><span class="sxs-lookup"><span data-stu-id="672fe-351">Create a New Legend</span></span>  
 <span data-ttu-id="672fe-352">По умолчанию все правила отображаются в первых условных обозначениях.</span><span class="sxs-lookup"><span data-stu-id="672fe-352">By default, all rules display in the first legend.</span></span> <span data-ttu-id="672fe-353">Чтобы улучшить отображение карты, можно добавить дополнительные условные обозначения.</span><span class="sxs-lookup"><span data-stu-id="672fe-353">To improve the display for a map, you can add legends.</span></span>  
  
 <span data-ttu-id="672fe-354">Чтобы изменить параметры отображения по умолчанию, выполните два следующих действия: создайте новое условное обозначение и свяжите результаты правила для слоя карты с новым условным обозначением.</span><span class="sxs-lookup"><span data-stu-id="672fe-354">To change the default display, there are two steps: create a new legend and then associate the rule results for a map layer with the new legend.</span></span>  
  
##### <a name="to-create-a-new-legend"></a><span data-ttu-id="672fe-355">Создание новых условных обозначений</span><span class="sxs-lookup"><span data-stu-id="672fe-355">To create a new legend</span></span>  
  
1.  <span data-ttu-id="672fe-356">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-356">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="672fe-357">Щелкните правой кнопкой мыши карту за пределами окна просмотра, а затем выберите пункт **Добавить условные обозначения**.</span><span class="sxs-lookup"><span data-stu-id="672fe-357">Right-click the map outside the viewport, and then click **Add Legend**.</span></span> <span data-ttu-id="672fe-358">Новые условные обозначения добавляются на карту в месте по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="672fe-358">A new legend is added to the map at a default location.</span></span>  
  
3.  <span data-ttu-id="672fe-359">Щелкните правой кнопкой мыши условные обозначения и выберите пункт **Свойства условных обозначений**.</span><span class="sxs-lookup"><span data-stu-id="672fe-359">Right-click the legend, and then click **Legend Properties**.</span></span>  
  
4.  <span data-ttu-id="672fe-360">В разделе **Параметры позиции**щелкните место, где должны находиться условные обозначения относительно окна просмотра.</span><span class="sxs-lookup"><span data-stu-id="672fe-360">In **Position options**, click the location that specifies where you want the legend to appear relative to the viewport.</span></span> <span data-ttu-id="672fe-361">Карта в области конструктора изменяется, показывая эффект от изменения параметров.</span><span class="sxs-lookup"><span data-stu-id="672fe-361">The map on the design surface changes to show the effect of your selections.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="672fe-362">Щелкните **Заголовок** на условных обозначениях, чтобы выбрать их заголовок.</span><span class="sxs-lookup"><span data-stu-id="672fe-362">Click **Title** on the legend to select the legend title.</span></span>  
  
7.  <span data-ttu-id="672fe-363">Еще раз щелкните **Заголовок** , чтобы войти в режим ввода текста.</span><span class="sxs-lookup"><span data-stu-id="672fe-363">Click **Title** again to enter insert mode for the text.</span></span> <span data-ttu-id="672fe-364">Замените текст **Заголовок** на **Продажи (в тыс.)**, а затем щелкните за пределами текста.</span><span class="sxs-lookup"><span data-stu-id="672fe-364">Replace **Title** by **Sales (Thousands)**, and then click outside the text.</span></span>  
  
 <span data-ttu-id="672fe-365">Условные обозначения расширяются, отображая заголовок.</span><span class="sxs-lookup"><span data-stu-id="672fe-365">The legend expands to display the title.</span></span>  
  
###  <a name="6e-associate-legend-and-color-rules"></a><a name="Associate"></a><span data-ttu-id="672fe-366">6e.</span><span class="sxs-lookup"><span data-stu-id="672fe-366">6e.</span></span> <span data-ttu-id="672fe-367">Связывание условных обозначений и правил цветов</span><span class="sxs-lookup"><span data-stu-id="672fe-367">Associate Legend and Color Rules</span></span>  
 <span data-ttu-id="672fe-368">Во всех условных обозначениях могут отображаться один или несколько наборов результатов правил.</span><span class="sxs-lookup"><span data-stu-id="672fe-368">Each legend can display one or more sets of rule results.</span></span>  
  
##### <a name="to-associate-a-legend-with-color-rules"></a><span data-ttu-id="672fe-369">Связывание условных обозначений с цветовыми правилами</span><span class="sxs-lookup"><span data-stu-id="672fe-369">To associate a legend with color rules</span></span>  
  
1.  <span data-ttu-id="672fe-370">Дважды щелкните карту, чтобы отобразить панель **Слой карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-370">Double-click the map to display the **Map Layer** pane.</span></span>  
  
2.  <span data-ttu-id="672fe-371">Щелкните на PolygonLayer1 стрелку вниз и выберите **Правило цвета многоугольника**.</span><span class="sxs-lookup"><span data-stu-id="672fe-371">Click the down arrow on PolygonLayer1, and then click **Polygon Color Rule**.</span></span> <span data-ttu-id="672fe-372">Открывается диалоговое окно **Свойства цветовых правил карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-372">The **Map Color Rules Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="672fe-373">Выберите **Условные обозначения**.</span><span class="sxs-lookup"><span data-stu-id="672fe-373">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="672fe-374">В области **Параметры цветовой шкалы**снимите флажок **Показать на цветовой шкале**.</span><span class="sxs-lookup"><span data-stu-id="672fe-374">In **Color scale options**, clear **Show in color scale**.</span></span>  
  
5.  <span data-ttu-id="672fe-375">В области **Параметры условных обозначений**выберите из раскрывающегося списка Legend2.</span><span class="sxs-lookup"><span data-stu-id="672fe-375">In **Legend options**, from the drop-down list, select Legend2.</span></span> <span data-ttu-id="672fe-376">Отображаются параметры текста условных обозначений.</span><span class="sxs-lookup"><span data-stu-id="672fe-376">The legend text option appears.</span></span> <span data-ttu-id="672fe-377">По умолчанию текст условного обозначения форматируется с помощью общей строки формата [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="672fe-377">By default, legend text is formatted with a general [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] format string.</span></span> <span data-ttu-id="672fe-378">Число 0 в «N0» указывает на отсутствие десятичных знаков.</span><span class="sxs-lookup"><span data-stu-id="672fe-378">The 0 in N0 specifies no decimal digits.</span></span>  
  
6.  <span data-ttu-id="672fe-379">В **тексте условных обозначений**используйте следующий формат, чтобы указать валюту без десятичных знаков:`#FROMVALUE {C0} - #TOVALUE {C0}`</span><span class="sxs-lookup"><span data-stu-id="672fe-379">In **Legend text**, use the following format to specify currency with no decimal digits: `#FROMVALUE {C0} - #TOVALUE {C0}`</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="672fe-380">В области конструктора условные обозначения отображают цветовые диапазоны с образцами данных, отформатированных в качестве валюты.</span><span class="sxs-lookup"><span data-stu-id="672fe-380">On the design surface, the legend displays the color ranges with sample data formatted as currency.</span></span>  
  
8.  <span data-ttu-id="672fe-381">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="672fe-381">Preview the report.</span></span>  
  
 <span data-ttu-id="672fe-382">Округи, в которых имеются связанные магазины и данные о продажах, отображаются в соответствии с правилами цвета.</span><span class="sxs-lookup"><span data-stu-id="672fe-382">The counties that have associated stores and sales display according to the color rules.</span></span> <span data-ttu-id="672fe-383">Округи, в которых отсутствуют продажи, отображаются без цвета.</span><span class="sxs-lookup"><span data-stu-id="672fe-383">Counties that have no sales have no color.</span></span>  
  
###  <a name="6f-change-color-for-counties-with-no-data"></a><a name="NoData"></a><span data-ttu-id="672fe-384">6f.</span><span class="sxs-lookup"><span data-stu-id="672fe-384">6f.</span></span> <span data-ttu-id="672fe-385">Изменение цветов округов, не содержащих данных</span><span class="sxs-lookup"><span data-stu-id="672fe-385">Change Color for Counties with No Data</span></span>  
 <span data-ttu-id="672fe-386">Можно настроить параметры отображения по умолчанию для всех элементов карты на слое.</span><span class="sxs-lookup"><span data-stu-id="672fe-386">You can set the default display options for all map elements on a layer.</span></span> <span data-ttu-id="672fe-387">Правила цвета имеют больший приоритет, чем эти параметры отображения.</span><span class="sxs-lookup"><span data-stu-id="672fe-387">Color rules take precedence over these display options.</span></span>  
  
##### <a name="to-set-the-display-properties-for-all-elements-on-a-layer"></a><span data-ttu-id="672fe-388">Задание свойств отображения для всех элементов слоя</span><span class="sxs-lookup"><span data-stu-id="672fe-388">To set the display properties for all elements on a layer</span></span>  
  
1.  <span data-ttu-id="672fe-389">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-389">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="672fe-390">Дважды щелкните карту, чтобы отобразить панель **Слой карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-390">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="672fe-391">Щелкните на PolygonLayer1 стрелку вниз и выберите **Свойства многоугольника**.</span><span class="sxs-lookup"><span data-stu-id="672fe-391">Click the down arrow on PolygonLayer1, and then click **Polygon Properties**.</span></span> <span data-ttu-id="672fe-392">Открывается диалоговое окно **Свойства многоугольников карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-392">The **Map Polygon Properties** dialog box opens.</span></span> <span data-ttu-id="672fe-393">Параметры отображения, заданные в этом диалоговом окне, применяются ко всем многоугольникам на слое до применения параметров отображения, заданных на основе правил.</span><span class="sxs-lookup"><span data-stu-id="672fe-393">Display options set in this dialog box apply to all polygons on the layer before rule-based display options are applied.</span></span>  
  
4.  <span data-ttu-id="672fe-394">Нажмите кнопку **Заливка**.</span><span class="sxs-lookup"><span data-stu-id="672fe-394">Click **Fill**.</span></span>  
  
5.  <span data-ttu-id="672fe-395">Убедитесь, что выбран стиль заливки **Сплошная.**</span><span class="sxs-lookup"><span data-stu-id="672fe-395">Verify that the fill style is **Solid.**</span></span> <span data-ttu-id="672fe-396">Градиенты и узоры применяются ко всем цветам.</span><span class="sxs-lookup"><span data-stu-id="672fe-396">Gradients and patterns apply to all colors.</span></span>  
  
6.  <span data-ttu-id="672fe-397">В поле **Цвет**нажмите стрелку вниз и выберите **Светло-синий металлик**.</span><span class="sxs-lookup"><span data-stu-id="672fe-397">In **Color**, click the down arrow, and then click **Light Steel Blue**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="672fe-398">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="672fe-398">Preview the report.</span></span>  
  
 <span data-ttu-id="672fe-399">Округи, не имеющие связанных данных, отображаются синим цветом.</span><span class="sxs-lookup"><span data-stu-id="672fe-399">Counties that have no associated data display as blue.</span></span> <span data-ttu-id="672fe-400">Цвета в диапазоне от **Красного** по **Зеленый** в соответствии с заданными правилами цвета используются для отображения только тех округов, для которых имеются связанные аналитические данные.</span><span class="sxs-lookup"><span data-stu-id="672fe-400">Only counties that have associated analytical data appear in the **Red** through **Green** colors from the color rules that you specified.</span></span>  
  
##  <a name="7-add-a-custom-point"></a><a name="CustomPoint"></a><span data-ttu-id="672fe-401">7. Добавление пользовательской точки</span><span class="sxs-lookup"><span data-stu-id="672fe-401">7. Add a Custom Point</span></span>  
 <span data-ttu-id="672fe-402">Чтобы создать представление нового магазина, который еще не построен, укажите точку и воспользуйтесь типом маркера **Вешка** .</span><span class="sxs-lookup"><span data-stu-id="672fe-402">To represent a new store that has not yet been built, specify a point and use the **PushPin** marker type.</span></span>  
  
#### <a name="to-add-a-custom-point"></a><span data-ttu-id="672fe-403">Добавление пользовательской точки</span><span class="sxs-lookup"><span data-stu-id="672fe-403">To add a custom point</span></span>  
  
1.  <span data-ttu-id="672fe-404">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-404">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="672fe-405">Дважды щелкните карту, чтобы отобразить панель **Слой карты** .</span><span class="sxs-lookup"><span data-stu-id="672fe-405">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="672fe-406">На панели инструментов нажмите кнопку **Добавить слой**, а затем выберите **Слой точек**.</span><span class="sxs-lookup"><span data-stu-id="672fe-406">On the toolbar, click **Add Layer**, and then click **Point Layer**.</span></span>  
  
     <span data-ttu-id="672fe-407">На карту добавляется новый слой точек.</span><span class="sxs-lookup"><span data-stu-id="672fe-407">A new point layer is added to the map.</span></span> <span data-ttu-id="672fe-408">По умолчанию он имеет тип пространственных данных **Внедренный**.</span><span class="sxs-lookup"><span data-stu-id="672fe-408">By default, the point layer has spatial data type **Embedded**.</span></span>  
  
3.  <span data-ttu-id="672fe-409">Щелкните стрелку рядом с PointLayer2 и выберите **Добавить точку**.</span><span class="sxs-lookup"><span data-stu-id="672fe-409">Click the down arrow on PointLayer2, and then click **Add Point**.</span></span>  
  
4.  <span data-ttu-id="672fe-410">Переместите указатель над окном просмотра карты.</span><span class="sxs-lookup"><span data-stu-id="672fe-410">Move the pointer over the map viewport.</span></span> <span data-ttu-id="672fe-411">Курсор превращается в перекрестье.</span><span class="sxs-lookup"><span data-stu-id="672fe-411">The cursor changes to crosshairs.</span></span>  
  
5.  <span data-ttu-id="672fe-412">Щелкните место на карте, где нужно добавить точку.</span><span class="sxs-lookup"><span data-stu-id="672fe-412">Click the location on the map where you want to add a point.</span></span> <span data-ttu-id="672fe-413">В этом учебнике щелкните расположение в округе рядом с началом маршрута.</span><span class="sxs-lookup"><span data-stu-id="672fe-413">In this tutorial, click a location in a county next to the start of the route.</span></span> <span data-ttu-id="672fe-414">Точка, помеченная окружностью, добавляется на слой в месте щелчка.</span><span class="sxs-lookup"><span data-stu-id="672fe-414">A point marked by a circle is added to the layer at the location where you clicked.</span></span> <span data-ttu-id="672fe-415">По умолчанию точка будет выбрана.</span><span class="sxs-lookup"><span data-stu-id="672fe-415">By default, the point is selected.</span></span>  
  
6.  <span data-ttu-id="672fe-416">Щелкните правой кнопкой мыши добавленную точку и выберите пункт **Свойства внедренной точки**.</span><span class="sxs-lookup"><span data-stu-id="672fe-416">Right-click the point you added, and then click **Embedded Point Properties**.</span></span>  
  
7.  <span data-ttu-id="672fe-417">Выберите параметр **Переопределить свойства точки для этого слоя**.</span><span class="sxs-lookup"><span data-stu-id="672fe-417">Select the option **Override point options for this layer**.</span></span> <span data-ttu-id="672fe-418">В диалоговом окне появляются дополнительные страницы.</span><span class="sxs-lookup"><span data-stu-id="672fe-418">Additional pages appear in the dialog box.</span></span> <span data-ttu-id="672fe-419">Значения, заданные на этих страницах, имеют более высокий приоритет, чем параметры отображения, заданные для слоя или цветовых правил.</span><span class="sxs-lookup"><span data-stu-id="672fe-419">Values that you set here take precedence over display options for the layer or for color rules.</span></span>  
  
8.  <span data-ttu-id="672fe-420">Нажмите кнопку **Маркер**.</span><span class="sxs-lookup"><span data-stu-id="672fe-420">Click **Marker**.</span></span>  
  
9. <span data-ttu-id="672fe-421">В поле **Тип маркера**выберите **Звезда**.</span><span class="sxs-lookup"><span data-stu-id="672fe-421">For **Marker type**, select **Star**.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="672fe-422">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="672fe-422">Preview the report.</span></span>  
  
 <span data-ttu-id="672fe-423">Новая добавленная точка отображается, как **Звезда**.</span><span class="sxs-lookup"><span data-stu-id="672fe-423">The new point you added appears as a **Star**.</span></span>  
  
#### <a name="to-add-a-label-for-the-custom-point"></a><span data-ttu-id="672fe-424">Добавление метки для пользовательской точки</span><span class="sxs-lookup"><span data-stu-id="672fe-424">To add a label for the custom point</span></span>  
  
1.  <span data-ttu-id="672fe-425">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-425">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="672fe-426">Щелкните правой кнопкой мыши добавленную точку и выберите параметр **Свойства внедренной точки**.</span><span class="sxs-lookup"><span data-stu-id="672fe-426">Right-click the point you just added, and then click **Embedded Point Properties**.</span></span>  
  
3.  <span data-ttu-id="672fe-427">Щелкните **Метки**.</span><span class="sxs-lookup"><span data-stu-id="672fe-427">Click **Labels**.</span></span>  
  
4.  <span data-ttu-id="672fe-428">В поле **Текст метки**введите **Новый магазин**.</span><span class="sxs-lookup"><span data-stu-id="672fe-428">In **Label text**, type **New Store**.</span></span>  
  
5.  <span data-ttu-id="672fe-429">В поле **Размещение**выберите **Сверху**.</span><span class="sxs-lookup"><span data-stu-id="672fe-429">In **Placement**, click **Top**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="672fe-430">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="672fe-430">Preview the report.</span></span>  
  
 <span data-ttu-id="672fe-431">Метка помещается над местоположением магазина.</span><span class="sxs-lookup"><span data-stu-id="672fe-431">The label appears above the store location.</span></span>  
  
##  <a name="center-the-map-view"></a><a name="CenterView"></a><span data-ttu-id="672fe-432">Центрирование представления карт</span><span class="sxs-lookup"><span data-stu-id="672fe-432">Center the Map View</span></span>  
 <span data-ttu-id="672fe-433">Измените параметры центрирования и масштабирования окна просмотра карты.</span><span class="sxs-lookup"><span data-stu-id="672fe-433">Change the map viewport center and zoom level.</span></span>  
  
#### <a name="to-change-the-viewport"></a><span data-ttu-id="672fe-434">Изменение области просмотра</span><span class="sxs-lookup"><span data-stu-id="672fe-434">To change the viewport</span></span>  
  
1.  <span data-ttu-id="672fe-435">Щелкните правой кнопкой мыши область просмотра и выберите пункт **Свойства окна просмотра карты**.</span><span class="sxs-lookup"><span data-stu-id="672fe-435">Right-click the map viewport, and then click **Viewport Properties**.</span></span>  
  
2.  <span data-ttu-id="672fe-436">Нажмите кнопку **Центрирование и масштабирование**.</span><span class="sxs-lookup"><span data-stu-id="672fe-436">Click **Center and Zoom**.</span></span>  
  
3.  <span data-ttu-id="672fe-437">Убедитесь, что установлен флажок **Задать центр представления и масштаб** .</span><span class="sxs-lookup"><span data-stu-id="672fe-437">Verify that the option **Set a view center and zoom level** is selected.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="672fe-438">Щелкните окно просмотра карты и перетащите центр области просмотра в необходимое местоположение.</span><span class="sxs-lookup"><span data-stu-id="672fe-438">Left-click the map viewport, and drag the center of the viewport to the location that you want.</span></span>  
  
6.  <span data-ttu-id="672fe-439">Используйте колесо прокрутки на мыши, чтобы изменить масштаб области просмотра.</span><span class="sxs-lookup"><span data-stu-id="672fe-439">Use the mouse wheel to change the zoom level of the viewport.</span></span>  
  
7.  <span data-ttu-id="672fe-440">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="672fe-440">Preview the report.</span></span>  
  
 <span data-ttu-id="672fe-441">В режиме конструктора при отображении карты в отображаемой области и в представлении будут использоваться образцы данных.</span><span class="sxs-lookup"><span data-stu-id="672fe-441">In Design view, the map on the display surface and the view is based on sample data.</span></span> <span data-ttu-id="672fe-442">В подготовленном для просмотру отчете представление карты будет центрировано по выбранному представлению.</span><span class="sxs-lookup"><span data-stu-id="672fe-442">In the rendered report, the map view is centered on the view that you specified.</span></span>  
  
##  <a name="add-a-report-title"></a><a name="Title"></a><span data-ttu-id="672fe-443">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="672fe-443">Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="672fe-444">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="672fe-444">To add a report title</span></span>  
  
1.  <span data-ttu-id="672fe-445">В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.</span><span class="sxs-lookup"><span data-stu-id="672fe-445">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="672fe-446">Введите фразу **Продажи в магазинах Нью-Йорка** и щелкните вне текстового поля.</span><span class="sxs-lookup"><span data-stu-id="672fe-446">Type **Sales in New York Stores** and then click outside the text box.</span></span>  
  
 <span data-ttu-id="672fe-447">Данный заголовок появится в верхней части отчета.</span><span class="sxs-lookup"><span data-stu-id="672fe-447">This title will appear at the top of the report.</span></span> <span data-ttu-id="672fe-448">Элементы, расположенные в верхней части текста отчета, при отсутствии определенного верхнего колонтитула страницы служат заголовком отчета.</span><span class="sxs-lookup"><span data-stu-id="672fe-448">Items at the top of the report body when there is no page header defined are the equivalent of a report header.</span></span>  
  
##  <a name="save-the-report"></a><a name="Save"></a><span data-ttu-id="672fe-449">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="672fe-449">Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="672fe-450">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="672fe-450">To save the report</span></span>  
  
1.  <span data-ttu-id="672fe-451">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="672fe-451">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="672fe-452">Нажмите кнопку «Построитель отчетов» и выберите **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="672fe-452">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="672fe-453">В поле **Имя**введите **Продажи магазинов в Нью-Йорке**.</span><span class="sxs-lookup"><span data-stu-id="672fe-453">In **Name**, type **Store Sales in New York**.</span></span>  
  
 <span data-ttu-id="672fe-454">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="672fe-454">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="672fe-455">Next Steps</span><span class="sxs-lookup"><span data-stu-id="672fe-455">Next Steps</span></span>  
 <span data-ttu-id="672fe-456">На этом пошаговое руководство по добавлению карты в отчет завершается.</span><span class="sxs-lookup"><span data-stu-id="672fe-456">This concludes the walkthrough for how to add a map to your report.</span></span>  
  
 <span data-ttu-id="672fe-457">Дополнительные сведения см. в статьях [Maps &#40;построитель отчетов и SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) и запись блога [картографическую корректировка пространственных данных для SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=152771) на blogs.MSDN.com.</span><span class="sxs-lookup"><span data-stu-id="672fe-457">For more information, see [Maps &#40;Report Builder and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) and the blog entry [Cartographic Adjustment of Spatial Data for SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=152771) on blogs.msdn.com.</span></span>  
  
 <span data-ttu-id="672fe-458">Дополнительные руководства см. в [учебниках &#40;построитель отчетов&#41;](report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="672fe-458">For more tutorials, see [Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="672fe-459">См. также:</span><span class="sxs-lookup"><span data-stu-id="672fe-459">See Also</span></span>  
 <span data-ttu-id="672fe-460">[Учебники &#40;построитель отчетов&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="672fe-460">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="672fe-461">[построитель отчетов в SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="672fe-461">[Report Builder in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md) </span></span>  
 <span data-ttu-id="672fe-462">[Мастера карт и мастер слоев карт &#40;построитель отчетов и SSRS&#41;](report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="672fe-462">[Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="672fe-463">Изменение параметров отображения многоугольников, линий и точек с помощью правил и аналитических данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="672fe-463">Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)  
  
  
