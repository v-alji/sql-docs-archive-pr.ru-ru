---
title: Добавление, изменение или удаление карты или слоя карты (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10526"
- sql12.rtp.rptdesigner.maptilelayerproperties.general.f1
- "10529"
- "10525"
- "10535"
- sql12.rtp.rptdesigner.mappolygonlayerproperties.general.f1
- sql12.rtp.rptdesigner.shared.layervisibility.f1
- sql12.rtp.rptdesigner.mappointlayerproperties.general.f1
- sql12.rtp.rptdesigner.shared.layerfilters.f1
- "10524"
- sql12.rtp.rptdesigner.maplayerproperties.general.f1
- sql12.rtp.rptdesigner.maplinelayerproperties.general.f1
- "10532"
- "10528"
- "10527"
- sql12.rtp.rptdesigner.maplayerproperties.analyticaldata.f1
ms.assetid: 6e89815e-187e-45bf-bf63-3d5c4a246360
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4e9fd178d36ee3322c0bd94dd44d621439139b71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663985"
---
# <a name="add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs"></a><span data-ttu-id="99cce-102">Добавление, изменение или удаление карты или слоя карты (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="99cce-102">Add, Change, or Delete a Map or Map Layer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="99cce-103">Карта представляет собой набор слоев.</span><span class="sxs-lookup"><span data-stu-id="99cce-103">A map is a collection of layers.</span></span> <span data-ttu-id="99cce-104">При добавлении карты в отчет необходимо определить первый ее слой.</span><span class="sxs-lookup"><span data-stu-id="99cce-104">When you add a map to a report, you define the first layer.</span></span> <span data-ttu-id="99cce-105">Дополнительные слои можно создать с помощью мастера «Слой карты».</span><span class="sxs-lookup"><span data-stu-id="99cce-105">You can create additional layers by using the map layer wizard.</span></span>  
  
 <span data-ttu-id="99cce-106">Добавить или удалить слой либо изменить его параметры проще всего с помощью мастера «Слой карты».</span><span class="sxs-lookup"><span data-stu-id="99cce-106">The easiest way to add, remove, or change options for a layer is to use the map layer wizard.</span></span> <span data-ttu-id="99cce-107">Также параметры можно изменить вручную с помощью панели «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-107">You can also change options manually from the Map pane.</span></span> <span data-ttu-id="99cce-108">Чтобы отобразить панель **Карта** , щелкните карту в области конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="99cce-108">To display the **Map** pane, click in the map on the report design surface.</span></span> <span data-ttu-id="99cce-109">На следующем рисунке изображены составные части панели:</span><span class="sxs-lookup"><span data-stu-id="99cce-109">The following figure displays the parts of the pane:</span></span>  
  
 <span data-ttu-id="99cce-110">![rsMapLayerZone](../media/rsmaplayerzone.gif "rsMapLayerZone")</span><span class="sxs-lookup"><span data-stu-id="99cce-110">![rsMapLayerZone](../media/rsmaplayerzone.gif "rsMapLayerZone")</span></span>  
  
 <span data-ttu-id="99cce-111">Слои карты отрисовываются снизу вверх в порядке отображения на панели «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-111">Map layers are drawn from bottom to top in the order that they appear in the Map pane.</span></span> <span data-ttu-id="99cce-112">На предыдущем рисунке первым отрисовывается мозаичный слой, а последним — слой многоугольников.</span><span class="sxs-lookup"><span data-stu-id="99cce-112">In the previous figure, the tile layer is drawn first and the polygon layer is drawn last.</span></span> <span data-ttu-id="99cce-113">Слои, которые отрисовываются позже, могут скрывать элементы карты, расположенные на слоях, которые отрисовываются раньше.</span><span class="sxs-lookup"><span data-stu-id="99cce-113">Layers that are drawn later might hide map elements on layers that are drawn earlier.</span></span> <span data-ttu-id="99cce-114">Порядок слоев можно изменить с помощью кнопок со стрелками на панели инструментов панели «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-114">You can change the order of layers by using the arrow keys on the Map pane toolbar.</span></span> <span data-ttu-id="99cce-115">Чтобы показать или скрыть слой, переключите значок видимости слоя.</span><span class="sxs-lookup"><span data-stu-id="99cce-115">To show or hide layers, toggle the visibility icon.</span></span> <span data-ttu-id="99cce-116">Прозрачность слоя можно изменить на `Visibility` странице диалогового окна свойства **данных слоя** .</span><span class="sxs-lookup"><span data-stu-id="99cce-116">You can change the transparency of a layer on the `Visibility` page of the **Layer Data** properties dialog box.</span></span>  
  
 <span data-ttu-id="99cce-117">В следующей таблице содержатся значки панели инструментов панель **Карта** .</span><span class="sxs-lookup"><span data-stu-id="99cce-117">The following table displays the toolbar icons for the **Map** pane.</span></span>  
  
|<span data-ttu-id="99cce-118">Символ</span><span class="sxs-lookup"><span data-stu-id="99cce-118">Symbol</span></span>|<span data-ttu-id="99cce-119">Описание</span><span class="sxs-lookup"><span data-stu-id="99cce-119">Description</span></span>|<span data-ttu-id="99cce-120">Назначение</span><span class="sxs-lookup"><span data-stu-id="99cce-120">When to use</span></span>|  
|------------|-----------------|-----------------|  
|<span data-ttu-id="99cce-121">![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")</span><span class="sxs-lookup"><span data-stu-id="99cce-121">![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")</span></span>|<span data-ttu-id="99cce-122">Мастер «Слой карты»</span><span class="sxs-lookup"><span data-stu-id="99cce-122">Map Layer Wizard</span></span>|<span data-ttu-id="99cce-123">Чтобы добавить слой с помощью мастера, нажмите кнопку **Мастер создания слоя**.</span><span class="sxs-lookup"><span data-stu-id="99cce-123">To add a layer by using a wizard, click **New layer wizard**.</span></span>|  
|<span data-ttu-id="99cce-124">![rs_IconMapAddLayer](../../tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer")</span><span class="sxs-lookup"><span data-stu-id="99cce-124">![rs_IconMapAddLayer](../../tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer")</span></span>|<span data-ttu-id="99cce-125">Добавить слой</span><span class="sxs-lookup"><span data-stu-id="99cce-125">Add Layer</span></span>|<span data-ttu-id="99cce-126">Чтобы добавить слой вручную, нажмите кнопку **Добавить слой**и выберите тип добавляемого слоя карты.</span><span class="sxs-lookup"><span data-stu-id="99cce-126">To manually add a layer, click **Add Layer**, and then click the type of map layer to add.</span></span>|  
|<span data-ttu-id="99cce-127">![rs_IconMapPolygonLayer](../media/rs-iconmappolygonlayer.gif "rs_IconMapPolygonLayer")</span><span class="sxs-lookup"><span data-stu-id="99cce-127">![rs_IconMapPolygonLayer](../media/rs-iconmappolygonlayer.gif "rs_IconMapPolygonLayer")</span></span>|<span data-ttu-id="99cce-128">Слой многоугольников</span><span class="sxs-lookup"><span data-stu-id="99cce-128">Polygon Layer</span></span>|<span data-ttu-id="99cce-129">Добавление слоя карты, отображающего области или фигуры, заданные наборами координат вершин многоугольников.</span><span class="sxs-lookup"><span data-stu-id="99cce-129">Add a map layer that displays areas or shapes that are based sets of polygon coordinates.</span></span>|  
|<span data-ttu-id="99cce-130">![rs_IconMapLineLayer](../media/rs-iconmaplinelayer.gif "rs_IconMapLineLayer")</span><span class="sxs-lookup"><span data-stu-id="99cce-130">![rs_IconMapLineLayer](../media/rs-iconmaplinelayer.gif "rs_IconMapLineLayer")</span></span>|<span data-ttu-id="99cce-131">Слой линий</span><span class="sxs-lookup"><span data-stu-id="99cce-131">Line Layer</span></span>|<span data-ttu-id="99cce-132">Добавление слоя карты, отображающего пути или маршруты, заданные наборами координат точек линий.</span><span class="sxs-lookup"><span data-stu-id="99cce-132">Add a map layer that displays paths or routes that are based on sets of line coordinates.</span></span>|  
|<span data-ttu-id="99cce-133">![rs_IconMapPointLayer](../media/rs-iconmappointlayer.gif "rs_IconMapPointLayer")</span><span class="sxs-lookup"><span data-stu-id="99cce-133">![rs_IconMapPointLayer](../media/rs-iconmappointlayer.gif "rs_IconMapPointLayer")</span></span>|<span data-ttu-id="99cce-134">Слой точек</span><span class="sxs-lookup"><span data-stu-id="99cce-134">Point Layer</span></span>|<span data-ttu-id="99cce-135">Добавление слоя карты, отображающего местоположения, заданные наборами координат точек.</span><span class="sxs-lookup"><span data-stu-id="99cce-135">Add a map layer that displays locations that are based on sets of point coordinates.</span></span>|  
|<span data-ttu-id="99cce-136">![rs_IconMapTileLayer](../media/rs-iconmaptilelayer.gif "rs_IconMapTileLayer")</span><span class="sxs-lookup"><span data-stu-id="99cce-136">![rs_IconMapTileLayer](../media/rs-iconmaptilelayer.gif "rs_IconMapTileLayer")</span></span>|<span data-ttu-id="99cce-137">Мозаичный слой</span><span class="sxs-lookup"><span data-stu-id="99cce-137">Tile Layer</span></span>|<span data-ttu-id="99cce-138">Добавление слоя карты, отображающего элементы мозаики Bing Map, соответствующие области видимости текущей карты, определенной областью просмотра.</span><span class="sxs-lookup"><span data-stu-id="99cce-138">Add a map layer that displays Bing Map tiles that correspond to the current map view area that is defined by the viewport.</span></span>|  
  
 <span data-ttu-id="99cce-139">В нижней части панели «Карта» отображается область просмотра карты.</span><span class="sxs-lookup"><span data-stu-id="99cce-139">At the bottom of the Map pane is the Map view area.</span></span> <span data-ttu-id="99cce-140">Чтобы изменить параметры центрирования и масштабирования, заданные для карты, используйте кнопки со стрелками для настройки центра представления и ползунок для выбора масштаба.</span><span class="sxs-lookup"><span data-stu-id="99cce-140">To change the center or zoom options for the map, use the arrow keys to adjust the view center and the slider to adjust the zoom level.</span></span>  
  
 <span data-ttu-id="99cce-141">Дополнительные сведения см. в разделе [Карты (построитель отчетов и службы SSRS)](maps-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="99cce-141">For more information about layers, see [Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="to-add-a-layer-from-the-map-layer-wizard"></a><a name="AddLayer"></a> <span data-ttu-id="99cce-142">Добавление слоя с помощью мастера слоя карты</span><span class="sxs-lookup"><span data-stu-id="99cce-142">To add a layer from the map layer wizard</span></span>  
  
-   <span data-ttu-id="99cce-143">На ленте в меню **Вставка** выберите **Карта**, затем **Карта Wizard.**</span><span class="sxs-lookup"><span data-stu-id="99cce-143">From the Ribbon, on the **Insert** menu, click **Map**, and then click **Map Wizard.**</span></span> <span data-ttu-id="99cce-144">. Этот мастер позволяет добавить слой в существующую карту.</span><span class="sxs-lookup"><span data-stu-id="99cce-144">The wizard enables you to add a layer to the existing map.</span></span> <span data-ttu-id="99cce-145">Большая часть страниц мастера создания карты и мастера создания слоя карты идентичны.</span><span class="sxs-lookup"><span data-stu-id="99cce-145">Most wizard pages are identical between the map wizard and the map layer wizard.</span></span>  
  
     <span data-ttu-id="99cce-146">Дополнительные сведения см. в разделе [Мастер карт и мастер слоев карт (построитель отчетов и службы SSRS)](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="99cce-146">For more information, see [Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-change-options-for-a-layer-by-using-the-map-layer-wizard"></a><a name="ChangeLayer"></a> <span data-ttu-id="99cce-147">Изменение параметров слоя с помощью мастера «Слой карты»</span><span class="sxs-lookup"><span data-stu-id="99cce-147">To change options for a layer by using the map layer wizard</span></span>  
  
-   <span data-ttu-id="99cce-148">Запустите мастер «Слой карты».</span><span class="sxs-lookup"><span data-stu-id="99cce-148">Run the map layer wizard.</span></span> <span data-ttu-id="99cce-149">Этот мастер используется для изменения параметров слоя, созданного с помощью мастера «Слой карты».</span><span class="sxs-lookup"><span data-stu-id="99cce-149">This wizard enables you to change options for a layer that you created by using the map layer wizard.</span></span> <span data-ttu-id="99cce-150">На панели "Карта" щелкните правой кнопкой мыши слой и на панели инструментов нажмите кнопку мастера слоя (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span><span class="sxs-lookup"><span data-stu-id="99cce-150">In the Map pane, right-click the layer, and on the toolbar, click the layer wizard button (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span></span>  
  
     <span data-ttu-id="99cce-151">Дополнительные сведения см. в разделе [Мастер карт и мастер слоев карт (построитель отчетов и службы SSRS)](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="99cce-151">For more information, see [Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-add-a-point-line-or-polygon-layer-from-the-map-pane-toolbar"></a><a name="AddVectorLayer"></a> <span data-ttu-id="99cce-152">Добавление слоя точек, линий или многоугольников с помощью панели инструментов панели «Карта»</span><span class="sxs-lookup"><span data-stu-id="99cce-152">To add a point, line, or polygon layer from the Map pane toolbar</span></span>  
  
1.  <span data-ttu-id="99cce-153">Щелкните карту, чтобы отобразить панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-153">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="99cce-154">На панели инструментов нажмите кнопку **Добавить слой** и выберите в раскрывающемся списке тип добавляемого слоя: **Точка**, **Линия** или **Многоугольник**.</span><span class="sxs-lookup"><span data-stu-id="99cce-154">On the toolbar, click the **Add Layer** button, and from the drop-down list, click the type of layer that you want to add: **Point**, **Line**, or **Polygon**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="99cce-155">Хотя слой карты можно добавить и настроить вручную, для добавления новых слоев рекомендуется использовать мастер слоя.</span><span class="sxs-lookup"><span data-stu-id="99cce-155">Although you can add a map layer and configure it manually, we recommend that you use the map layer wizard to add new layers.</span></span> <span data-ttu-id="99cce-156">Чтобы запустить этот мастер с панели инструментов области "Карта", нажмите кнопку мастера создания слоя (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span><span class="sxs-lookup"><span data-stu-id="99cce-156">To launch the wizard from the Map pane toolbar, click the layer wizard button (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span></span>  
  
3.  <span data-ttu-id="99cce-157">Щелкните правой кнопкой мыши слой и выберите пункт **Данные слоя**.</span><span class="sxs-lookup"><span data-stu-id="99cce-157">Right-click the layer, and then click **Layer Data**.</span></span>  
  
4.  <span data-ttu-id="99cce-158">Выберите в списке **Использовать пространственные данные из**источник пространственных данных.</span><span class="sxs-lookup"><span data-stu-id="99cce-158">In **Use spatial data from**, select the source of spatial data.</span></span> <span data-ttu-id="99cce-159">Доступные параметры различаются в зависимости от сделанного выбора.</span><span class="sxs-lookup"><span data-stu-id="99cce-159">Options vary based on your selection.</span></span>  
  
     <span data-ttu-id="99cce-160">Если необходимо визуализировать в слое аналитические данные отчета, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="99cce-160">If you want to visualize analytical from your report on this layer, do the following:</span></span>  
  
    1.  <span data-ttu-id="99cce-161">Выберите **Аналитические данные**.</span><span class="sxs-lookup"><span data-stu-id="99cce-161">Click **Analytical data**.</span></span>  
  
    2.  <span data-ttu-id="99cce-162">Выберите в списке **Набор аналитических данных**имя набора данных, содержащего аналитические данные и поля сопоставления, определяющие связь между аналитическими и пространственными данными.</span><span class="sxs-lookup"><span data-stu-id="99cce-162">In **Analytical dataset**, click the name of the dataset that contains analytical data and the match fields to build a relationship between analytical and spatial data.</span></span>  
  
    3.  <span data-ttu-id="99cce-163">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="99cce-163">Click **Add**.</span></span>  
  
    4.  <span data-ttu-id="99cce-164">Введите имя поля сопоставления в наборе пространственных данных.</span><span class="sxs-lookup"><span data-stu-id="99cce-164">Type the name of the match field from the spatial dataset.</span></span>  
  
    5.  <span data-ttu-id="99cce-165">Введите имя поля сопоставления в наборе аналитических данных.</span><span class="sxs-lookup"><span data-stu-id="99cce-165">Type the name of the match field from the analytical dataset.</span></span>  
  
     <span data-ttu-id="99cce-166">Дополнительные сведения о создании связи между пространственными и аналитическими данными см. в разделе [Настройка данных и отображения карты или слоя карты (построитель отчетов и службы SSRS)](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="99cce-166">For more information about linking spatial and analytical data, see [Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-filter-analytical-data-for-the-layer"></a><a name="FilterAnalyticalData"></a> <span data-ttu-id="99cce-167">Фильтрация аналитических данных для слоя</span><span class="sxs-lookup"><span data-stu-id="99cce-167">To filter analytical data for the layer</span></span>  
  
1.  <span data-ttu-id="99cce-168">Щелкните карту, чтобы отобразить панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-168">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="99cce-169">На панели "Карта" щелкните слой правой кнопкой мыши, а затем щелкните  **Данные слоя**.</span><span class="sxs-lookup"><span data-stu-id="99cce-169">Right-click the layer in the Map pane, and then click  **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="99cce-170">Перейдите на вкладку **Фильтры**.</span><span class="sxs-lookup"><span data-stu-id="99cce-170">Click **Filters**.</span></span>  
  
4.  <span data-ttu-id="99cce-171">Определите уравнение фильтра для ограничения аналитических данных, которые используются в отображении карты.</span><span class="sxs-lookup"><span data-stu-id="99cce-171">Define a filter equation to limit the analytical data that is used in the map display.</span></span> <span data-ttu-id="99cce-172">Дополнительные сведения см. в разделе [Примеры уравнений фильтра (построитель отчетов и службы SSRS)](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="99cce-172">For more information, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-control-point-properties-for-a-point-layer-or-for-polygon-center-points"></a><a name="PointProperties"></a> <span data-ttu-id="99cce-173">Управление свойствами точек для слоя точек или для центральных точек многоугольника.</span><span class="sxs-lookup"><span data-stu-id="99cce-173">To control point properties for a point layer or for polygon center points</span></span>  
  
1.  <span data-ttu-id="99cce-174">Страница **Общие** диалогового окна **Свойства точки карты** позволяет изменить параметры метки, всплывающей подсказки и типа маркера для следующих элементов карты.</span><span class="sxs-lookup"><span data-stu-id="99cce-174">Select **General** on the **Map Point Properties** dialog box to change label, tooltip, and marker type options for the following map elements:</span></span>  
  
    -   <span data-ttu-id="99cce-175">Все динамические или внедренные точки слоя точек.</span><span class="sxs-lookup"><span data-stu-id="99cce-175">All dynamic or embedded points on a point layer.</span></span> <span data-ttu-id="99cce-176">Эти параметры переопределяются правилами для цветов, размеров и типов маркеров точек.</span><span class="sxs-lookup"><span data-stu-id="99cce-176">Color rules, size rules, and marker type rules for points override these options.</span></span> <span data-ttu-id="99cce-177">Чтобы переопределить параметры отдельной внедренной точки, используйте страницу [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) .</span><span class="sxs-lookup"><span data-stu-id="99cce-177">To override options for a specific embedded point, use the [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) page.</span></span>  
  
    -   <span data-ttu-id="99cce-178">Центральная точка всех динамических или внедренных многоугольников слоя многоугольников.</span><span class="sxs-lookup"><span data-stu-id="99cce-178">The center point for all dynamic or embedded polygons on a polygon layer.</span></span> <span data-ttu-id="99cce-179">Эти параметры переопределяются правилами цветов, размеров и типов маркеров для центральных точек.</span><span class="sxs-lookup"><span data-stu-id="99cce-179">Color rules, size rules, and marker type rules for center points override these options.</span></span> <span data-ttu-id="99cce-180">Чтобы переопределить параметры отдельной центральной точки, используйте страницу [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) .</span><span class="sxs-lookup"><span data-stu-id="99cce-180">To override options for a specific center point, use the [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) page.</span></span>  

##  <a name="to-specify-embedded-data-as-a-source-of-spatial-data"></a><a name="Embedded"></a> <span data-ttu-id="99cce-181">Указание внедренных данных в качестве источника пространственных данных</span><span class="sxs-lookup"><span data-stu-id="99cce-181">To specify embedded data as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="99cce-182">Щелкните карту, чтобы отобразить панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-182">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="99cce-183">Щелкните правой кнопкой мыши слой и выберите пункт **Данные слоя**.</span><span class="sxs-lookup"><span data-stu-id="99cce-183">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="99cce-184">Выберите в списке **Использовать пространственные данные из**пункт **Данные, внедренные в отчет**.</span><span class="sxs-lookup"><span data-stu-id="99cce-184">In **Use spatial data from**, select **Data embedded in report**.</span></span>  
  
4.  <span data-ttu-id="99cce-185">Чтобы загрузить элементы карты из существующего отчета или создать их на основе файла ESRI, нажмите кнопку **Обзор**, укажите файл и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="99cce-185">To load map elements from an existing report or to create map elements based on an ESRI file, click **Browse**, point to the file, and then click **Open**.</span></span> <span data-ttu-id="99cce-186">Элементы карты внедрены в определение отчета.</span><span class="sxs-lookup"><span data-stu-id="99cce-186">The map elements are embedded in this report definition.</span></span> <span data-ttu-id="99cce-187">Указанные пространственные данные должны соответствовать типу слоя.</span><span class="sxs-lookup"><span data-stu-id="99cce-187">The spatial data that you point to must match the layer type.</span></span> <span data-ttu-id="99cce-188">Например, для слоя точек необходимо указать пространственные данные, содержащие набор координат точек.</span><span class="sxs-lookup"><span data-stu-id="99cce-188">For example, for a point layer, you must point to spatial data that specifies sets of point coordinates.</span></span>  
  
5.  <span data-ttu-id="99cce-189">Выберите в списке **Пространственное поле**имя поля, содержащего пространственные данные.</span><span class="sxs-lookup"><span data-stu-id="99cce-189">In **Spatial field**, specify the name of the field that contains spatial data.</span></span> <span data-ttu-id="99cce-190">Это имя нужно определить по источнику пространственных данных.</span><span class="sxs-lookup"><span data-stu-id="99cce-190">You might need to determine this name from the source of spatial data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="99cce-191">Если имя этого поля неизвестно, но выбран шейп-файл ESRI, используйте вместо этого параметр **Ссылка на файл фигуры ESRI** .</span><span class="sxs-lookup"><span data-stu-id="99cce-191">If you do not know the name of the field and you browsed to an ESRI Shapefile, use the **Link to ESRI shape file option** instead of this option.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-an-esri-shapefile-as-a-source-of-spatial-data"></a><a name="ESRI"></a> <span data-ttu-id="99cce-192">Указание файла фигуры ESRI в качестве источника пространственных данных</span><span class="sxs-lookup"><span data-stu-id="99cce-192">To specify an ESRI Shapefile as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="99cce-193">Щелкните карту, чтобы отобразить панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-193">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="99cce-194">Щелкните правой кнопкой мыши слой и выберите пункт **Данные слоя**.</span><span class="sxs-lookup"><span data-stu-id="99cce-194">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="99cce-195">Выберите в списке **Использовать пространственные данные из**пункт **Связать с файлом фигуры ESRI**.</span><span class="sxs-lookup"><span data-stu-id="99cce-195">In **Use spatial data from**, select **Link to ESRI Shapefile**.</span></span>  
  
4.  <span data-ttu-id="99cce-196">Введите в поле **Имя файла**путь к файлу фигуры ESRI или нажмите кнопку **Обзор** и выберите файл фигуры ESRI.</span><span class="sxs-lookup"><span data-stu-id="99cce-196">In **File name**, type the location of an ESRI Shapefile, or click **Browse** to select an ESRI Shapefile.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="99cce-197">Если файл фигуры расположен на локальном компьютере, пространственные данные внедряются в определение отчета.</span><span class="sxs-lookup"><span data-stu-id="99cce-197">If the Shapefile is on your local computer, the spatial data is embedded in the report definition.</span></span> <span data-ttu-id="99cce-198">Чтобы динамически получать данные при обработке отчета, необходимо загрузить на сервер отчетов шейп-файл ESRI с расширением SHP и его файл поддержки с расширением DBF.</span><span class="sxs-lookup"><span data-stu-id="99cce-198">To retrieve the data dynamically when the report is processed, you must upload the ESRI .shp file and its .dbf support file to the report server.</span></span> <span data-ttu-id="99cce-199">Дополнительные сведения см. в статье "Инструкция. Передача файла или отчета (диспетчер отчетов)" в [документации по службам Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) , входящей в состав электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99cce-199">For more information, see " How to: Upload a File or Report (Report Manager)" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-a-report-dataset-field-as-a-source-of-spatial-data"></a><a name="DatasetField"></a> <span data-ttu-id="99cce-200">Указание поля набора данных отчета в качестве источника пространственных данных</span><span class="sxs-lookup"><span data-stu-id="99cce-200">To specify a report dataset field as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="99cce-201">Щелкните карту, чтобы отобразить панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-201">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="99cce-202">Щелкните правой кнопкой мыши слой и выберите пункт **Данные слоя**.</span><span class="sxs-lookup"><span data-stu-id="99cce-202">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="99cce-203">Выберите в списке **Использовать пространственные данные из**пункт **Поле пространственных данных в наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="99cce-203">In **Use spatial data from**, select **Spatial field in a dataset**.</span></span>  
  
4.  <span data-ttu-id="99cce-204">Выберите в списке **Имя набора данных**имя набора данных в отчете, который содержит необходимые пространственные данные.</span><span class="sxs-lookup"><span data-stu-id="99cce-204">In **Dataset name**, click the name of a dataset in the report that contains that spatial data that you want.</span></span>  
  
5.  <span data-ttu-id="99cce-205">Выберите в списке **Имя пространственного поля**имя поля в наборе данных, содержащего пространственные данные.</span><span class="sxs-lookup"><span data-stu-id="99cce-205">In **Spatial field name**, click the name of the field in the dataset that contains spatial data.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-add-a-tile-layer"></a><a name="TileLayer"></a> <span data-ttu-id="99cce-206">Добавление мозаичного слоя</span><span class="sxs-lookup"><span data-stu-id="99cce-206">To add a tile layer</span></span>  
  
1.  <span data-ttu-id="99cce-207">Щелкните карту, чтобы отобразить панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-207">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="99cce-208">Нажмите на панели инструментов кнопку **Добавить слой** и выберите в раскрывающемся списке пункт **Мозаичный слой**.</span><span class="sxs-lookup"><span data-stu-id="99cce-208">On the toolbar, click the **Add Layer** button, and from the drop-down list, click **Tile Layer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="99cce-209"> Дополнительные сведения об использовании в отчете мозаичных элементов Bing Map см. в разделах [Дополнительные условия использования](https://go.microsoft.com/fwlink/?LinkId=151371) и [Заявление о конфиденциальности](https://go.microsoft.com/fwlink/?LinkId=151372).</span><span class="sxs-lookup"><span data-stu-id="99cce-209">For more information about the use of Bing map tiles in your report, see [Additional Terms of Use](https://go.microsoft.com/fwlink/?LinkId=151371) and [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=151372).</span></span>  
  
3.  <span data-ttu-id="99cce-210">Щелкните правой кнопкой мыши мозаичный слой на панели "Карта", а затем выберите **Свойства мозаичных элементов**.</span><span class="sxs-lookup"><span data-stu-id="99cce-210">Right-click the tile layer in the Map pane, and then click **Tile Properties**.</span></span>  
  
4.  <span data-ttu-id="99cce-211">Выберите в окне **Параметры мозаичных элементов**стиль мозаичных элементов.</span><span class="sxs-lookup"><span data-stu-id="99cce-211">In **Tile options**, select a tile style.</span></span> <span data-ttu-id="99cce-212">Если мозаичные элементы Bing Map доступны, слой в области конструктора обновляется с применением выбранного стиля.</span><span class="sxs-lookup"><span data-stu-id="99cce-212">If the Bing map tiles are available, the layer on the design surface updates with the style that you select.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="99cce-213">Мозаичный слой можно также добавить при добавлении слоя многоугольников, линий или точек с помощью мастера создания карты или слоя карты.</span><span class="sxs-lookup"><span data-stu-id="99cce-213">A tile layer can also be added when you add a polygon, line, or point layer in the Map or Map Layer wizard.</span></span> <span data-ttu-id="99cce-214">Выберите на странице **Параметры пространственных данных и представления карты** параметр **Добавить в данное представление карты мозаичный фон Bing Map**.</span><span class="sxs-lookup"><span data-stu-id="99cce-214">On the **Choose spatial data and map view options** page, select the option **Add a Bing Maps background for this map view**.</span></span>  

##  <a name="to-change-the-drawing-order-of-a-layer"></a><a name="DrawingOrder"></a> <span data-ttu-id="99cce-215">Изменение порядка отрисовки слоев</span><span class="sxs-lookup"><span data-stu-id="99cce-215">To change the drawing order of a layer</span></span>  
  
1.  <span data-ttu-id="99cce-216">Щелкните карту, чтобы отобразить панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-216">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="99cce-217">Щелкните слой на панели «Карта», чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="99cce-217">Click the layer in the Map pane to select it.</span></span>  
  
3.  <span data-ttu-id="99cce-218">Нажмите на панели инструментов панели «Карта» стрелку вверх или вниз, чтобы изменить порядок отрисовки каждого слоя.</span><span class="sxs-lookup"><span data-stu-id="99cce-218">On the Map pane toolbar, click the up or down arrow to change the drawing order of each layer.</span></span>  

##  <a name="to-change-the-transparency-of-a-polygon-line-or-point-layer"></a><a name="Transparency"></a> <span data-ttu-id="99cce-219">Изменение прозрачности слоя многоугольников, линий или точек</span><span class="sxs-lookup"><span data-stu-id="99cce-219">To change the transparency of a polygon, line, or point layer</span></span>  
  
1.  <span data-ttu-id="99cce-220">Щелкните карту, чтобы отобразить панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-220">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="99cce-221">Щелкните правой кнопкой мыши слой и выберите пункт **Данные слоя**.</span><span class="sxs-lookup"><span data-stu-id="99cce-221">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="99cce-222">Нажмите кнопку `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="99cce-222">Click `Visibility`.</span></span>  
  
4.  <span data-ttu-id="99cce-223">Введите на странице **Параметры прозрачности**значение, выражающее процент прозрачности (например: **40**).</span><span class="sxs-lookup"><span data-stu-id="99cce-223">In **Transparency options**, type a value that represents the percentage transparency, for example, **40**.</span></span> <span data-ttu-id="99cce-224">Нулевое (0) значение прозрачности означает, что слой непрозрачен.</span><span class="sxs-lookup"><span data-stu-id="99cce-224">Zero (0) % transparency means that the layer is opaque.</span></span> <span data-ttu-id="99cce-225">При прозрачности, равной 100 %, слой не будет отображаться в отчете.</span><span class="sxs-lookup"><span data-stu-id="99cce-225">100% transparency means that you will not see the layer in the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-change-the-transparency-of-a-tile-layer"></a><a name="TileTransparency"></a> <span data-ttu-id="99cce-226">Изменение прозрачности мозаичного слоя</span><span class="sxs-lookup"><span data-stu-id="99cce-226">To change the transparency of a tile layer</span></span>  
  
1.  <span data-ttu-id="99cce-227">Щелкните карту, чтобы отобразить панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-227">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="99cce-228">Щелкните правой кнопкой мыши слой, затем выберите пункт **Свойства мозаики**.</span><span class="sxs-lookup"><span data-stu-id="99cce-228">Right-click the layer, and then click **Tile Properties**.</span></span>  
  
3.  <span data-ttu-id="99cce-229">Нажмите кнопку `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="99cce-229">Click `Visibility`.</span></span>  
  
4.  <span data-ttu-id="99cce-230">Введите на странице **Параметры прозрачности**значение, выражающее процент прозрачности (например: **40**).</span><span class="sxs-lookup"><span data-stu-id="99cce-230">In **Transparency options**, type a value that represents the percentage transparency, for example, **40**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-a-secure-connection-for-a-tile-layer"></a><a name="Secure"></a> <span data-ttu-id="99cce-231">Указание безопасного соединения для мозаичного слоя</span><span class="sxs-lookup"><span data-stu-id="99cce-231">To specify a secure connection for a tile layer</span></span>  
  
1.  <span data-ttu-id="99cce-232">Щелкните карту, чтобы отобразить панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="99cce-232">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="99cce-233">На панели «Карта» щелкните мозаичный слой, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="99cce-233">In the Map pane, click the tile layer to select it.</span></span> <span data-ttu-id="99cce-234">На панели свойств отображаются свойства этого мозаичного слоя.</span><span class="sxs-lookup"><span data-stu-id="99cce-234">The Properties pane displays the tile layer properties.</span></span>  
  
3.  <span data-ttu-id="99cce-235">На панели "Свойства" задайте для параметра UseSecureConnection значение **True**.</span><span class="sxs-lookup"><span data-stu-id="99cce-235">In the Properties pane, set UseSecureConnection to **True**.</span></span>  
  
 <span data-ttu-id="99cce-236">При соединении с веб-службой карт Bing для получения мозаичных элементов для этого слоя будет использоваться HTTP-служба протокола SSL.</span><span class="sxs-lookup"><span data-stu-id="99cce-236">The connection for the Bing Maps Web service will use the HTTP SSL (Secure Sockets Layer) service to retrieve Bing map tiles for this layer.</span></span>  

##  <a name="to-specify-the-language-for-tile-labels"></a><a name="Language"></a> <span data-ttu-id="99cce-237">Выбор языка для меток мозаичных элементов</span><span class="sxs-lookup"><span data-stu-id="99cce-237">To specify the language for tile labels</span></span>  
  
1.  <span data-ttu-id="99cce-238">По умолчанию для стилей мозаичных элементов, использующихся для отображения меток язык определяется локалью по умолчанию для построителя отчетов.</span><span class="sxs-lookup"><span data-stu-id="99cce-238">By default, for tile styles that display labels, the language is determined from the default locale for Report Builder.</span></span> <span data-ttu-id="99cce-239">Языковые настройки для меток мозаичных элементов можно изменить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="99cce-239">You can customize the language setting for tile labels in the following ways.</span></span>  
  
    -   <span data-ttu-id="99cce-240">Чтобы выбрать карту, щелкните карту за пределами окна просмотра.</span><span class="sxs-lookup"><span data-stu-id="99cce-240">Click the map outside the viewport to select the map.</span></span> <span data-ttu-id="99cce-241">На панели "Свойства" выберите для свойства TileLanguage в раскрывающемся списке значение культуры.</span><span class="sxs-lookup"><span data-stu-id="99cce-241">In the Properties pane, for the TileLanguage property, select a culture value from the drop-down list.</span></span>  
  
    -   <span data-ttu-id="99cce-242">Чтобы выбрать отчет, щелкните фон отчета.</span><span class="sxs-lookup"><span data-stu-id="99cce-242">Click the report background to select the report.</span></span> <span data-ttu-id="99cce-243">На панели "Свойства" для свойства Language выберите в раскрывающемся списке значение культуры.</span><span class="sxs-lookup"><span data-stu-id="99cce-243">In the Properties pane, from for the Language property, select a culture value from the drop-down list.</span></span>  
  
     <span data-ttu-id="99cce-244">Порядок приоритета при определении языка: свойство отчета TileLanguage, локаль по умолчанию для построителя отчетов, свойство карты TileLanguage.</span><span class="sxs-lookup"><span data-stu-id="99cce-244">The order of precedence for setting the tile label language is: report property Language, default locale for Report Builder, and map property TileLanguage.</span></span>  

##  <a name="to-conditionally-hide-a-layer-based-on-viewport-zoom-level"></a><a name="ConditionalHide"></a> <span data-ttu-id="99cce-245">Скрытие слоя по условию с учетом масштаба области просмотра</span><span class="sxs-lookup"><span data-stu-id="99cce-245">To conditionally hide a layer based on viewport zoom level</span></span>  
  
1.  <span data-ttu-id="99cce-246">Задайте `Visibility` параметры для управления отображением слоя карт.</span><span class="sxs-lookup"><span data-stu-id="99cce-246">Set `Visibility` options to control the display for a map layer.</span></span>  
  
    -   <span data-ttu-id="99cce-247">На панели "Слои карты" выберите слой, щелкнув его правой кнопкой мыши, затем на панели инструментов "Слои карты" щелкните "Свойства", чтобы открыть диалоговое окно **Свойства слоя карты**.</span><span class="sxs-lookup"><span data-stu-id="99cce-247">In the Map Layers pane, right-click a layer to select it, and on the Map Layers toolbar, click Properties to open **Map Layer Properties**.</span></span>  
  
    -   <span data-ttu-id="99cce-248">Нажмите кнопку `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="99cce-248">Click `Visibility`.</span></span>  
  
    -   <span data-ttu-id="99cce-249">В разделе «Видимость слоя» выберите **Отображать или скрывать в зависимости от масштаба**.</span><span class="sxs-lookup"><span data-stu-id="99cce-249">In Layer visibility, select **Show or hide based on zoom value**.</span></span>  
  
    -   <span data-ttu-id="99cce-250">Введите минимальное и максимальное значения масштаба, при которых отображается слой.</span><span class="sxs-lookup"><span data-stu-id="99cce-250">Enter minimum and maximum zoom values for when display the layer.</span></span>  
  
    -   <span data-ttu-id="99cce-251">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="99cce-251">Optional.</span></span> <span data-ttu-id="99cce-252">Введите значение прозрачности.</span><span class="sxs-lookup"><span data-stu-id="99cce-252">Enter a value for transparency.</span></span>  
  
     <span data-ttu-id="99cce-253">Можно также скрывать слой по условию.</span><span class="sxs-lookup"><span data-stu-id="99cce-253">You can also conditionally hide the layer.</span></span> <span data-ttu-id="99cce-254">Дополнительные сведения см. в разделе [Скрытие элемента (построитель отчетов и службы SSRS)](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="99cce-254">For more information, see [Hide an Item &#40;Report Builder and SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="99cce-255">См. также:</span><span class="sxs-lookup"><span data-stu-id="99cce-255">See Also</span></span>  
 <span data-ttu-id="99cce-256">[Карты (построитель отчетов и службы SSRS)](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="99cce-256">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="99cce-257">[Устранение неполадок в отчетах: отчеты-карты (построитель отчетов и службы SSRS)](troubleshoot-reports-map-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="99cce-257">[Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;](troubleshoot-reports-map-reports-report-builder-and-ssrs.md)</span></span>  
