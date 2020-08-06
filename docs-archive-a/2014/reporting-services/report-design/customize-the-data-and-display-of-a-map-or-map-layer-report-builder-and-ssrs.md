---
title: Настройка данных и отображения карты или слоя карты (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10521"
- sql12.rtp.rptdesigner.shared.shadowdv.f1
- "10515"
- "10512"
- "10520"
- "10523"
- sql12.rtp.rptdesigner.mapgroupproperties.variables.f1
- sql12.rtp.rptdesigner.mapgroupproperties.filter.f1
- sql12.rtp.rptdesigner.shared.number.f1
- sql12.rtp.rptdesigner.shared.font.f1
- sql12.rtp.rptdesigner.mapgroupproperties.general.f1
- "10507"
ms.assetid: fdd9b994-d138-4990-a291-279b0249eb72
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05987cea7ebde9d3587ade3f567eeb8ccef5e8fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736113"
---
# <a name="customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs"></a><span data-ttu-id="2593a-102">Настройка данных и отображения карты или слоя карты (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="2593a-102">Customize the Data and Display of a Map or Map Layer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2593a-103">После добавления в отчет карты или слоя карты с помощью мастера может потребоваться изменить способ отображения карты в отчете.</span><span class="sxs-lookup"><span data-stu-id="2593a-103">After you add a map or map layer to a report by using a wizard, you might want to change the way the map looks in the report.</span></span> <span data-ttu-id="2593a-104">При внесении изменений следует учитывать следующие соображения.</span><span class="sxs-lookup"><span data-stu-id="2593a-104">You can make improvements by considering the following ideas:</span></span>  
  
-   <span data-ttu-id="2593a-105">Чтобы пользователю было проще интерпретировать данные, отображаемые на карте, можно добавить условные обозначения, цветовую шкалу, метки и подсказки.</span><span class="sxs-lookup"><span data-stu-id="2593a-105">To help your users understand how to interpret the data display on a map, you can add legends and a color scale, and add labels and tooltips.</span></span>  
  
-   <span data-ttu-id="2593a-106">Чтобы карту было проще читать, измените центрирование и масштабирование отображения, добавьте шкалу расстояний и фоновую сетку.</span><span class="sxs-lookup"><span data-stu-id="2593a-106">To make the map easier to read, change the center and zoom level, add a distance scale, and display a background grid.</span></span>  
  
-   <span data-ttu-id="2593a-107">Чтобы сократить время построения карты при выполнении отчета, можно настроить разрешение карты и упростить ее элементы.</span><span class="sxs-lookup"><span data-stu-id="2593a-107">To help control map drawing time when you run the report, you can adjust the resolution to simplify the map elements.</span></span>  
  
-   <span data-ttu-id="2593a-108">Элементы карты можно внедрить в определение отчета, а затем изменить внешний вид отдельных элементов.</span><span class="sxs-lookup"><span data-stu-id="2593a-108">You can embed map elements in the report definition, and then change how individual elements appear.</span></span> <span data-ttu-id="2593a-109">Например, можно показать расположение главного офиса вешкой, а остальных офисов — окружностями.</span><span class="sxs-lookup"><span data-stu-id="2593a-109">For example, you can display the primary office location with a pushpin and other office locations with circles.</span></span>  
  
-   <span data-ttu-id="2593a-110">Можно добавлять определяемые пользователем области, задавая собственные выражения групп данных.</span><span class="sxs-lookup"><span data-stu-id="2593a-110">You can add customized regions by specifying your own data group expressions.</span></span>  
  
-   <span data-ttu-id="2593a-111">Можно добавить пользовательское местоположение в указанной точке слоя карты с внедренными точками.</span><span class="sxs-lookup"><span data-stu-id="2593a-111">You can add a custom location at a  point that you specify on a map layer that has embedded points.</span></span> <span data-ttu-id="2593a-112">Значение и свойства отображения пользовательской точки можно задать отдельно от других точек на слое точек.</span><span class="sxs-lookup"><span data-stu-id="2593a-112">You can set the value and display properties for custom points independently from other points on a point layer.</span></span>  
  
-   <span data-ttu-id="2593a-113">Чтобы обеспечить большую детализацию, на любом из слоев можно добавить ссылку на элементы карты, щелкнув которую, пользователь открывает связанный отчет.</span><span class="sxs-lookup"><span data-stu-id="2593a-113">To provide more detail, you can add links to map elements on each layer that a user can click to open related reports.</span></span>  
  
 <span data-ttu-id="2593a-114">Дополнительные соображения относительно улучшения отчета см. в разделе [Планирование отчета &#40;построитель отчетов&#41;](planning-a-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="2593a-114">For more ideas about improving a report, see [Planning a Report &#40;Report Builder&#41;](planning-a-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="2593a-115">Параметры отображения влияют на способ показа карты или ее частей при просмотре отчета.</span><span class="sxs-lookup"><span data-stu-id="2593a-115">Display options affect the way a map or the parts of a map appear when you view the report.</span></span> <span data-ttu-id="2593a-116">Одни параметры управляют внешним видом карты, например рамками и шрифтами области, представленной на карте.</span><span class="sxs-lookup"><span data-stu-id="2593a-116">Some options control the appearance of the map, such as the borders and fonts or the area represented on the map.</span></span> <span data-ttu-id="2593a-117">Другие параметры управляют содержимым каждого слоя, например размером пузырьков, типом маркеров, метками или подсказками.</span><span class="sxs-lookup"><span data-stu-id="2593a-117">Other options control the content of each layer, such as bubble sizes, marker types, labels, or tooltips.</span></span>  
  
 <span data-ttu-id="2593a-118">Элемент отчета-карты включает следующие части: саму карту, окно просмотра карты, набор заголовков, набор условных обозначений (обозначения, цветовая шкала и шкала расстояний), набор слоев, набор элементов карты на каждом слое (многоугольники, линии или точки).</span><span class="sxs-lookup"><span data-stu-id="2593a-118">A map report item includes the following parts: the map itself, a map viewport, a set of titles, a set of legends (legend, color scale, and distance scale), a set of layers, a set of map elements on each layer (polygons or lines or points).</span></span> <span data-ttu-id="2593a-119">Сведения, представленные в следующих разделах, помогут понять, какое диалоговое окно свойств управляет отображением различных частей карты.</span><span class="sxs-lookup"><span data-stu-id="2593a-119">Use the information in the following sections to understand which property dialog box controls the display options for different parts of a map.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="change-options-for-the-map"></a><a name="Map"></a> <span data-ttu-id="2593a-120">Изменение параметров карты</span><span class="sxs-lookup"><span data-stu-id="2593a-120">Change Options for the Map</span></span>  
 <span data-ttu-id="2593a-121">В элементе «отчет-карта» можно управлять следующим.</span><span class="sxs-lookup"><span data-stu-id="2593a-121">On a map report item, you can control the following:</span></span>  
  
-   <span data-ttu-id="2593a-122">Добавить несколько заголовков.</span><span class="sxs-lookup"><span data-stu-id="2593a-122">Add multiple titles.</span></span>  
  
-   <span data-ttu-id="2593a-123">Добавить несколько условных обозначений.</span><span class="sxs-lookup"><span data-stu-id="2593a-123">Add multiple legends.</span></span> <span data-ttu-id="2593a-124">Чтобы изменить содержимое условных обозначений, необходимо создать несколько условных обозначений и изменить правила, указав, к каким из них относятся элементы, создаваемые тем или иным правилом.</span><span class="sxs-lookup"><span data-stu-id="2593a-124">To change the contents of a legend, you need to create additional legends and then change the rules to specify in which legend to enter the legend items created by each rule.</span></span>  
  
-   <span data-ttu-id="2593a-125">Добавить новые слои.</span><span class="sxs-lookup"><span data-stu-id="2593a-125">Add more layers.</span></span>  
  
-   <span data-ttu-id="2593a-126">Скрыть или отобразить шкалу расстояний или цветовую шкалу.</span><span class="sxs-lookup"><span data-stu-id="2593a-126">Hide or show the distance scale or color scale.</span></span>  
  
-   <span data-ttu-id="2593a-127">Создать иллюзию глубины, определяя тень.</span><span class="sxs-lookup"><span data-stu-id="2593a-127">Provide the illusion of depth by specifying a shadow.</span></span>  
  
 <span data-ttu-id="2593a-128">Чтобы изменить эти параметры, щелкните правой кнопкой мыши карту, выберите пункт **Карта**и измените параметры.</span><span class="sxs-lookup"><span data-stu-id="2593a-128">To change these options, right-click the map, click **Map**, and change the options.</span></span>  
  
 
  
##  <a name="change-options-for-the-viewport"></a><a name="Viewport"></a> <span data-ttu-id="2593a-129">Изменение параметров окна просмотра</span><span class="sxs-lookup"><span data-stu-id="2593a-129">Change Options for the Viewport</span></span>  
 <span data-ttu-id="2593a-130">Параметры окна просмотра позволяют изменить представление карты в отчете.</span><span class="sxs-lookup"><span data-stu-id="2593a-130">Use the viewport options to change the view of the map that appears in your report.</span></span>  
  
 <span data-ttu-id="2593a-131">Источник пространственных данных может поставлять большую площадь, чем необходимо для отчета.</span><span class="sxs-lookup"><span data-stu-id="2593a-131">The source of spatial data might provide more area than you need to display in the report.</span></span> <span data-ttu-id="2593a-132">Окно просмотра позволяет задать центр, масштаб и границы области карты.</span><span class="sxs-lookup"><span data-stu-id="2593a-132">You can use the viewport to set the center, the zoom level, and to crop the area for the map.</span></span>  
  
 <span data-ttu-id="2593a-133">Для окна просмотра можно задать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="2593a-133">The following options can be set for the viewport:</span></span>  
  
-   <span data-ttu-id="2593a-134">Выбрать систему координат и (для географической системы координат) проекцию.</span><span class="sxs-lookup"><span data-stu-id="2593a-134">Choose the coordinate system and, for a geographic coordinate system, choose the projection.</span></span>  
  
-   <span data-ttu-id="2593a-135">Выбрать центр карты.</span><span class="sxs-lookup"><span data-stu-id="2593a-135">Choose the center for the map.</span></span>  
  
-   <span data-ttu-id="2593a-136">Обрезать представление карты.</span><span class="sxs-lookup"><span data-stu-id="2593a-136">Crop the view for the map.</span></span>  
  
-   <span data-ttu-id="2593a-137">Задать масштаб.</span><span class="sxs-lookup"><span data-stu-id="2593a-137">Set the zoom level.</span></span>  
  
-   <span data-ttu-id="2593a-138">Разрешение и упрощение.</span><span class="sxs-lookup"><span data-stu-id="2593a-138">Resolution and simplification.</span></span> <span data-ttu-id="2593a-139">Найдите компромисс между временем отрисовки и детализацией линий и многоугольников.</span><span class="sxs-lookup"><span data-stu-id="2593a-139">Choose a balance between drawing time and detailed outlines for lines and polygons.</span></span>  
  
 <span data-ttu-id="2593a-140">Чтобы изменить эти параметры, щелкните правой кнопкой мыши окно просмотра карты и воспользуйтесь страницей [Диалоговое окно "Свойства окна просмотра карты", вкладка "Общие"](../map-viewport-properties-dialog-box-general.md) и связанными с ней страницами.</span><span class="sxs-lookup"><span data-stu-id="2593a-140">To change these options, right-click the map viewport, use the [Map Viewport Properties Dialog Box, General](../map-viewport-properties-dialog-box-general.md) page and related pages.</span></span>  
  

  
##  <a name="change-options-for-the-legends"></a><a name="Legends"></a> <span data-ttu-id="2593a-141">Изменение параметров условных обозначений</span><span class="sxs-lookup"><span data-stu-id="2593a-141">Change Options for the Legends</span></span>  
 <span data-ttu-id="2593a-142">Условные обозначения помогают пользователям в интерпретации данных на карте.</span><span class="sxs-lookup"><span data-stu-id="2593a-142">Legends help users interpret the data on a map.</span></span>  
  
 <span data-ttu-id="2593a-143">По умолчанию все правила, заданные для слоя, добавляют элементы к первым условным обозначениям.</span><span class="sxs-lookup"><span data-stu-id="2593a-143">By default, all rules that you specify for a layer add items to the first legend.</span></span> <span data-ttu-id="2593a-144">Кроме того, все цветовые правила отображают значения на цветовой шкале.</span><span class="sxs-lookup"><span data-stu-id="2593a-144">In addition, all color rules display values in the color scale.</span></span>  
  
-   <span data-ttu-id="2593a-145">Чтобы изменить параметры отображения условных обозначений, включая их положение относительно окна просмотра, необходимо задать параметры самих условных обозначений.</span><span class="sxs-lookup"><span data-stu-id="2593a-145">To change the display options for the appearance of the legend, including its position relative to the viewport, set options on the legend itself.</span></span>  
  
-   <span data-ttu-id="2593a-146">Чтобы изменить содержимое условных обозначений или его формат, необходимо изменить параметры условных обозначений для соответствующего правила слоя.</span><span class="sxs-lookup"><span data-stu-id="2593a-146">To change the contents or the format of contents for a legend, change the legend options for the corresponding rules for a layer.</span></span>  
  
 <span data-ttu-id="2593a-147">Дополнительные сведения см. в разделе [Изменение условных обозначений карты, цветовой шкалы и связанных правил (построитель отчетов и службы SSRS)](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2593a-147">For more information, see [Change Map Legends, Color Scale, and Associated Rules &#40;Report Builder and SSRS&#41;](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="change-options-for-the-layer"></a><a name="Layer"></a> <span data-ttu-id="2593a-148">Изменение параметров слоя</span><span class="sxs-lookup"><span data-stu-id="2593a-148">Change Options for the Layer</span></span>  
 <span data-ttu-id="2593a-149">Чтобы показать слои карты, выберите ее щелчком мыши.</span><span class="sxs-lookup"><span data-stu-id="2593a-149">To display the layers for a map, click the map to select it.</span></span> <span data-ttu-id="2593a-150">Появляется панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="2593a-150">The Map pane appears.</span></span> <span data-ttu-id="2593a-151">Чтобы изменить параметры слоя, щелкните его правой кнопкой мыши и используйте контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="2593a-151">To change options for a layer, right-click the layer and use the shortcut menu.</span></span>  
  
 <span data-ttu-id="2593a-152">Слой может иметь один из трех типов, в зависимости от типа данных, возвращаемых источником пространственных данных: слой многоугольников, слой линий или слой точек.</span><span class="sxs-lookup"><span data-stu-id="2593a-152">A layer can be one of three types based on the spatial data that is returned by the spatial data source: a polygon layer, a line layer, or a point layer.</span></span>  
  
 <span data-ttu-id="2593a-153">Для слоя можно задать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="2593a-153">The following options can be set for the layer:</span></span>  
  
-   <span data-ttu-id="2593a-154">Связанные аналитические данные и поля соответствия.</span><span class="sxs-lookup"><span data-stu-id="2593a-154">The associated analytical data and match fields.</span></span> <span data-ttu-id="2593a-155">Источник пространственных данных, представленный на панели «Карта» под именем слоя.</span><span class="sxs-lookup"><span data-stu-id="2593a-155">The source of the spatial data is listed on the Map pane under the name of the layer.</span></span> <span data-ttu-id="2593a-156">Если этот источник является внедренным, то элементы карты для слоя являются частью определения отчета.</span><span class="sxs-lookup"><span data-stu-id="2593a-156">When the source is embedded, the map elements for the layer are part of the report definition.</span></span> <span data-ttu-id="2593a-157">Если источник не является внедренным, то получение пространственных данных производится во время выполнения, а обработчик отчета создает элементы карты для слоя во время обработки отчета.</span><span class="sxs-lookup"><span data-stu-id="2593a-157">If the source is not embedded, then the spatial data is retrieved at run time and the report processor creates the map elements for the layer when the report is processed.</span></span> <span data-ttu-id="2593a-158">Изменение параметров данных для слоя производится на странице «Аналитические данные» диалогового окна «Слой карты».</span><span class="sxs-lookup"><span data-stu-id="2593a-158">To change data options on the layer, use the Analytical Data page in the Map Layer dialog box.</span></span>  
  
-   <span data-ttu-id="2593a-159">Порядок отрисовки слоя.</span><span class="sxs-lookup"><span data-stu-id="2593a-159">Layer drawing order.</span></span> <span data-ttu-id="2593a-160">Отрисовка слоев производится в порядке, обратном тому, в котором слои представлены на панели «Карта».</span><span class="sxs-lookup"><span data-stu-id="2593a-160">The order that you see the layers listed in the Map pane is the reverse drawing order for the layers.</span></span> <span data-ttu-id="2593a-161">Последний слой в списке отрисовывается первым.</span><span class="sxs-lookup"><span data-stu-id="2593a-161">The last layer in the list is drawn first.</span></span> <span data-ttu-id="2593a-162">Например, если необходимо, чтобы точки со слоя точек выводились поверх многоугольников со слоя многоугольников, слой точек должен быть первым, а слой многоугольников — вторым.</span><span class="sxs-lookup"><span data-stu-id="2593a-162">For example, if you want the points on a point layer to appear on top of the polygons in the polygon layer, the point layer should be first and the polygon layer second.</span></span>  
  
-   <span data-ttu-id="2593a-163">Видимость слоя, включая прозрачность.</span><span class="sxs-lookup"><span data-stu-id="2593a-163">Layer visibility, including transparency.</span></span> <span data-ttu-id="2593a-164">Чтобы один слой просвечивал сквозь другой, установите для него уровень прозрачности больше 0.</span><span class="sxs-lookup"><span data-stu-id="2593a-164">To have one layer show through another layer, set the transparency to a value higher than 0.</span></span> <span data-ttu-id="2593a-165">Значение 100% означает, что слой невидим.</span><span class="sxs-lookup"><span data-stu-id="2593a-165">A value of 100% means the layer is not visible.</span></span> <span data-ttu-id="2593a-166">Для работы с отдельным слоем можно легко скрыть или отобразить любой слой независимо от других слоев с помощью значка **Видимость** панели «Карта».</span><span class="sxs-lookup"><span data-stu-id="2593a-166">To work with an individual layer, you can easily show or hide each layer independently by using the **Visibility** icon in the Map pane.</span></span> <span data-ttu-id="2593a-167">Можно также задать параметры масштаба, определив отображение или скрытие элементов карты в зависимости от масштаба.</span><span class="sxs-lookup"><span data-stu-id="2593a-167">You can also set zoom level options to specify when to show or hide map elements on the layer based on the zoom level.</span></span>  
  
-   <span data-ttu-id="2593a-168">Добавление мозаичного слоя Bing Map в окно просмотра с текущим центром и масштабом.</span><span class="sxs-lookup"><span data-stu-id="2593a-168">Add a Bing map tile layer for the current viewport center and zoom level.</span></span> <span data-ttu-id="2593a-169">Не нужно указывать географические координаты мозаичного слоя.</span><span class="sxs-lookup"><span data-stu-id="2593a-169">You do not need to specify the geographic coordinates for a tile layer.</span></span> <span data-ttu-id="2593a-170">Мозаики автоматически загружаются в соответствии с характеристиками окна просмотра, если задана географическая система координат, проекция Меркатора, серверы Bing Map доступны и сервер отчетов настроен для поддержки этой возможности.</span><span class="sxs-lookup"><span data-stu-id="2593a-170">Tiles are automatically loaded to match the viewport area when the coordinate system is Geographic, the projection is Mercator, the Bing Maps servers are available, and when the report server has been configured to support this feature.</span></span> <span data-ttu-id="2593a-171">Для каждого отчета можно указать, следует ли использовать безопасное соединения для получения мозаик.</span><span class="sxs-lookup"><span data-stu-id="2593a-171">For each report, you can specify whether to use a secure connection to retrieve tiles.</span></span>  
  
 <span data-ttu-id="2593a-172">Дополнительные сведения о слоях см. в разделе [Добавление, изменение или удаление карты или слоя карты (построитель отчетов и службы SSRS)](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2593a-172">For more information about layers, see [Add, Change, or Delete a Map or Map Layer &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="change-data-grouping-for-the-layer"></a><a name="DataGrouping"></a> <span data-ttu-id="2593a-173">Изменение группирования данных для слоя</span><span class="sxs-lookup"><span data-stu-id="2593a-173">Change Data Grouping for the Layer</span></span>  
 <span data-ttu-id="2593a-174">Предусмотрена возможность настраивать способ агрегирования пространственных данных для собственных фигур.</span><span class="sxs-lookup"><span data-stu-id="2593a-174">You can customize the way to aggregate spatial data for your own shapes.</span></span> <span data-ttu-id="2593a-175">Чтобы задать свойства группы для слоя, выберите слой на панели "Карта", на панели "Свойства" для слоя щелкните **Группа**, а затем щелкните многоточие (...) и откройте диалоговое окно "Свойства группы".</span><span class="sxs-lookup"><span data-stu-id="2593a-175">To set the group properties for a layer, select the layer in the Map pane, and in the Properties pane for the layer, click **Group**, and then click the ellipsis (...) to open the Group properties.</span></span> <span data-ttu-id="2593a-176">В этом диалоговом окне можно задавать выражения группы, создавать переменные группы и фильтровать данные, которые используются для группирования.</span><span class="sxs-lookup"><span data-stu-id="2593a-176">In this dialog box, you can specify group expressions, create group variables, and filter data that is used for grouping.</span></span>  
  
 <span data-ttu-id="2593a-177">Выражение группы определяет, как статистически обрабатываются аналитические данные, связанные с пространственными данными, для каждого элемента карты слоя.</span><span class="sxs-lookup"><span data-stu-id="2593a-177">The group expression specifies how analytical data that has a relationship to spatial data is aggregated for each map element on the layer.</span></span> <span data-ttu-id="2593a-178">По умолчанию выражение группы представляет собой набор полей сопоставления, указанный для связи между пространственными и аналитическими данными.</span><span class="sxs-lookup"><span data-stu-id="2593a-178">By default, the group expression is the set of match fields that was specified for the relationship between the spatial data and the analytical data.</span></span> <span data-ttu-id="2593a-179">Например, для пузырьковой карты, отображающей местоположения городов и численность населения страны или региона, поля сопоставления включают название города [City] и региона [Region], поскольку может существовать несколько городов с одним и тем же названием.</span><span class="sxs-lookup"><span data-stu-id="2593a-179">For example, for a bubble map that displays city locations and population size for a country or region, the match fields include city name [City] and region name [Region] because there can be multiple cities with the same name.</span></span> <span data-ttu-id="2593a-180">Соответствующее выражение группы включает два поля: [City] и [Region].</span><span class="sxs-lookup"><span data-stu-id="2593a-180">The corresponding group expression includes two fields: [City] and [Region].</span></span>  
  
 <span data-ttu-id="2593a-181">Дополнительные сведения см. в статье " [Как импортировать файлы фигур в SQL Server и агрегировать пространственные данные](https://go.microsoft.com/fwlink/?LinkID=214991)".</span><span class="sxs-lookup"><span data-stu-id="2593a-181">For more information, see [Map Tips: How To Import Shapefiles Into SQL Server and Aggregate Spatial Data](https://go.microsoft.com/fwlink/?LinkID=214991).</span></span>  
  
 
  
##  <a name="change-options-for-the-map-elements-on-the-layer"></a><a name="MapElements"></a> <span data-ttu-id="2593a-182">Изменение параметров для элементов карты на слое</span><span class="sxs-lookup"><span data-stu-id="2593a-182">Change Options for the Map Elements on the Layer</span></span>  
 <span data-ttu-id="2593a-183">Элементами карты являются точки, линии или многоугольники на слое соответствующего типа пространственных данных.</span><span class="sxs-lookup"><span data-stu-id="2593a-183">Map elements are the points, lines, or polygons on a layer that are based on the spatial data.</span></span> <span data-ttu-id="2593a-184">Для элементов карты можно установить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="2593a-184">For map elements, the following options can be set.</span></span> <span data-ttu-id="2593a-185">Эти параметры применяются ко всем элементам карты на слое, независимо о того, являются ли они внедренными.</span><span class="sxs-lookup"><span data-stu-id="2593a-185">These options apply to all map elements on the layer, whether or not they are embedded:</span></span>  
  
-   <span data-ttu-id="2593a-186">Метки, видимость меток, смещения меток и форматирование.</span><span class="sxs-lookup"><span data-stu-id="2593a-186">Labels, label visibility, label offset, and formatting.</span></span>  
  
-   <span data-ttu-id="2593a-187">Рамки и заливка.</span><span class="sxs-lookup"><span data-stu-id="2593a-187">Borders and fill.</span></span>  
  
-   <span data-ttu-id="2593a-188">Действия детализации.</span><span class="sxs-lookup"><span data-stu-id="2593a-188">Drillthrough actions.</span></span>  
  
-   <span data-ttu-id="2593a-189">Параметры отображения.</span><span class="sxs-lookup"><span data-stu-id="2593a-189">Display options.</span></span>  
  
 <span data-ttu-id="2593a-190">Параметры отображения элементов карты учитываются в следующем порядке приоритетов: слой, элемент карты, правила для элемента карты и переопределенные параметры для внедренных элементов карты.</span><span class="sxs-lookup"><span data-stu-id="2593a-190">Display options for map elements follow a precedence order based on the layer, the map element, rules for the map element, and override options for embedded map elements.</span></span>  
  
 <span data-ttu-id="2593a-191">Чтобы изменить эти параметры, щелкните правой кнопкой мыши элемент карты и воспользуйтесь внедренным диалоговым окном свойств.</span><span class="sxs-lookup"><span data-stu-id="2593a-191">To change these options, right-click the map element, use the embedded properties dialog box.</span></span> <span data-ttu-id="2593a-192">Например, для внедренного многоугольника используйте диалоговое окно «Свойства внедренных многоугольников карты», страницу «Общие» и связанные с ней страницы.</span><span class="sxs-lookup"><span data-stu-id="2593a-192">For example, for an embedded polygon, use the Map Embedded Polygon Properties Dialog Box, General page and related pages.</span></span>  
  

  
##  <a name="understanding-display-option-precedence"></a><a name="Precedence"></a> <span data-ttu-id="2593a-193">Основные сведения о приоритетах параметров отображения</span><span class="sxs-lookup"><span data-stu-id="2593a-193">Understanding Display Option Precedence</span></span>  
 <span data-ttu-id="2593a-194">При управлении внешним видом точки, линии или многоугольника на слое карты необходимо понимать, где настраиваются параметры отображения и какие из них имеют высший приоритет.</span><span class="sxs-lookup"><span data-stu-id="2593a-194">When you want to control the display appearance of a point, line, or polygon on a map layer, you must understand where display options can be set and which options have a higher precedence.</span></span> <span data-ttu-id="2593a-195">Ниже перечислены параметры отображения от нижнего уровня к верхнему.</span><span class="sxs-lookup"><span data-stu-id="2593a-195">The following display options are listed from lowest to highest.</span></span> <span data-ttu-id="2593a-196">Параметры, имеющие более высокий уровень, переопределяют параметры, имеющие более низкий уровень.</span><span class="sxs-lookup"><span data-stu-id="2593a-196">Higher display options override lower display options in this list:</span></span>  
  
-   <span data-ttu-id="2593a-197">Параметры слоя.</span><span class="sxs-lookup"><span data-stu-id="2593a-197">Layer options.</span></span>  
  
-   <span data-ttu-id="2593a-198">Параметры точек, линий и многоугольников на каждом слое.</span><span class="sxs-lookup"><span data-stu-id="2593a-198">Points, Lines, or Polygons options on each layer.</span></span> <span data-ttu-id="2593a-199">Они применяются при динамическом получении элементов карты в процессе обработки отчета либо в случае, если они являются элементами карты, внедренными в определение отчета.</span><span class="sxs-lookup"><span data-stu-id="2593a-199">This applies whether the map elements are dynamically retrieved when the report is processed or whether they the map elements are embedded in the report definition.</span></span> <span data-ttu-id="2593a-200">Например, можно указать цвет заливки для всех элементов слоя.</span><span class="sxs-lookup"><span data-stu-id="2593a-200">For example, you specify a fill color for all elements on a layer.</span></span>  
  
-   <span data-ttu-id="2593a-201">Правила.</span><span class="sxs-lookup"><span data-stu-id="2593a-201">Rules.</span></span> <span data-ttu-id="2593a-202">Можно задать правила для управления цветом, размером, толщиной и типом маркера для всех элементов карты на слое.</span><span class="sxs-lookup"><span data-stu-id="2593a-202">You can set rules to control color, size, width, or marker type for all map elements on a layer.</span></span> <span data-ttu-id="2593a-203">Правила, которые можно задать, зависят от типа элемента карты.</span><span class="sxs-lookup"><span data-stu-id="2593a-203">The rules that you can set depend on the type of map element.</span></span>  
  
    -   <span data-ttu-id="2593a-204">Правила цвета.</span><span class="sxs-lookup"><span data-stu-id="2593a-204">Color Rules.</span></span> <span data-ttu-id="2593a-205">Применяются к маркерам для точек, линиям, многоугольникам и маркерам, обозначающим центры многоугольников.</span><span class="sxs-lookup"><span data-stu-id="2593a-205">Apply to markers for points, lines, polygons, and markers for polygon center points.</span></span>  
  
    -   <span data-ttu-id="2593a-206">Правила размера.</span><span class="sxs-lookup"><span data-stu-id="2593a-206">Size Rules.</span></span> <span data-ttu-id="2593a-207">Применяются к маркерам точек и маркерам, обозначающим центры многоугольников.</span><span class="sxs-lookup"><span data-stu-id="2593a-207">Apply to markers for points and markers for polygon center points.</span></span>  
  
    -   <span data-ttu-id="2593a-208">Правила толщины.</span><span class="sxs-lookup"><span data-stu-id="2593a-208">Width Rules.</span></span> <span data-ttu-id="2593a-209">Применяются к толщине линий.</span><span class="sxs-lookup"><span data-stu-id="2593a-209">Applies to line widths.</span></span>  
  
    -   <span data-ttu-id="2593a-210">Правила типа маркера.</span><span class="sxs-lookup"><span data-stu-id="2593a-210">Marker Type Rules.</span></span> <span data-ttu-id="2593a-211">Применяются к маркерам точек и маркерам, обозначающим центры многоугольников.</span><span class="sxs-lookup"><span data-stu-id="2593a-211">Applies to markers for points and markers for polygon center points.</span></span>  
  
-   <span data-ttu-id="2593a-212">Переопределение параметров для отдельных внедренных точек, линий и многоугольников на слое.</span><span class="sxs-lookup"><span data-stu-id="2593a-212">Override options for individual embedded points, lines, or polygons on a layer.</span></span> <span data-ttu-id="2593a-213">Сделанные изменения являются постоянными.</span><span class="sxs-lookup"><span data-stu-id="2593a-213">Changes that you make are permanent.</span></span> <span data-ttu-id="2593a-214">Чтобы отменить их, необходимо перезагрузить данные для слоя.</span><span class="sxs-lookup"><span data-stu-id="2593a-214">To revert these changes, you must reload the data for the layer.</span></span>  
  
 <span data-ttu-id="2593a-215">Дополнительные сведения см. в разделе [Изменение параметров отображения многоугольников, линий и точек с помощью правил и аналитических данных (построитель отчетов и службы SSRS)](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="2593a-215">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="2593a-216">См. также:</span><span class="sxs-lookup"><span data-stu-id="2593a-216">See Also</span></span>  
 <span data-ttu-id="2593a-217">[Мастер карт и мастер слоев карт (построитель отчетов и службы SSRS)](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2593a-217">[Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2593a-218">Карты (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="2593a-218">Maps &#40;Report Builder and SSRS&#41;</span></span>](maps-report-builder-and-ssrs.md)  
  
  
