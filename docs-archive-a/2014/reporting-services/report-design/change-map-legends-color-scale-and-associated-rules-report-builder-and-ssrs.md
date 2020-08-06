---
title: Изменение условных обозначений карт, цветовой шкалы и связанных правил (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.maprulesdistribution.f1
- "10512"
- "10539"
- "10533"
- sql12.rtp.rptdesigner.mappointlayerproperties.typerules.f1
- "10534"
- sql12.rtp.rptdesigner.maplegendproperties.general.f1
- sql12.rtp.rptdesigner.mapdistancescaleproperties.general.f1
- "10516"
- sql12.rtp.rptdesigner.mapcolorscaleproperties.labels.f1
- sql12.rtp.rptdesigner.maplegendtitleproperties.general.f1
- "10514"
- sql12.rtp.rptdesigner.shared.mapruleslegend.f1
- sql12.rtp.rptdesigner.mapcolorscaleproperties.general.f1
- sql12.rtp.rptdesigner.shared.embeddedlabels.f1
- "10513"
- sql12.rtp.rptdesigner.mappointlayerproperties.sizerules.f1
- sql12.rtp.rptdesigner.mapcolorscaletitleproperties.general.f1
- "10510"
- "10509"
- "10540"
- "10517"
ms.assetid: a1d691b2-c5ae-420f-af60-b7c54a7385a4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 17220c12e672ce49d3c5b1023f2a00db04e7613e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657517"
---
# <a name="change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs"></a><span data-ttu-id="40b8e-102">Изменение условных обозначений карты, цветовой шкалы и связанных правил (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="40b8e-102">Change Map Legends, Color Scale, and Associated Rules (Report Builder and SSRS)</span></span>
  <span data-ttu-id="40b8e-103">Карта может содержать условные обозначения, цветовую шкалу и шкалу расстояний.</span><span class="sxs-lookup"><span data-stu-id="40b8e-103">A map can contain map legends, a color scale, and a distance scale.</span></span> <span data-ttu-id="40b8e-104">Эти части карты помогают пользователям понять визуализацию данных на карте.</span><span class="sxs-lookup"><span data-stu-id="40b8e-104">These parts of a map help users interpret the data visualization on the map.</span></span>  
  
 <span data-ttu-id="40b8e-105">К условным обозначениям относятся следующие части карты.</span><span class="sxs-lookup"><span data-stu-id="40b8e-105">Legends include the following parts of a map:</span></span>  
  
-   <span data-ttu-id="40b8e-106">**Условные обозначения.** Помогают понять аналитические данные, управляющие отображением элементов карты на ее слое.</span><span class="sxs-lookup"><span data-stu-id="40b8e-106">**Map legend** Displays a guide to help interpret the analytical data that varies the display of a map elements on a map layer.</span></span> <span data-ttu-id="40b8e-107">Карта может содержать несколько условных обозначений.</span><span class="sxs-lookup"><span data-stu-id="40b8e-107">A map can have multiple legends.</span></span> <span data-ttu-id="40b8e-108">Для каждого слоя карты указываются соответствующие условные обозначения.</span><span class="sxs-lookup"><span data-stu-id="40b8e-108">For each map layer, you A specify which legend to use.</span></span> <span data-ttu-id="40b8e-109">Условные обозначения могут описывать несколько слоев карты.</span><span class="sxs-lookup"><span data-stu-id="40b8e-109">A legend can provide a guide to more than one map layer.</span></span>  
  
-   <span data-ttu-id="40b8e-110">**Цветовая шкала.** Помогает интерпретировать цвета на карте.</span><span class="sxs-lookup"><span data-stu-id="40b8e-110">**Color scale** Displays a guide to help interpret colors on the map.</span></span> <span data-ttu-id="40b8e-111">Цветовая шкала на карте одна.</span><span class="sxs-lookup"><span data-stu-id="40b8e-111">A map has one color scale.</span></span> <span data-ttu-id="40b8e-112">К цветовой шкале могут относиться данные с различных слоев.</span><span class="sxs-lookup"><span data-stu-id="40b8e-112">Multiple layers can provide the data for the color scale.</span></span>  
  
-   <span data-ttu-id="40b8e-113">**Шкала расстояний.** Помогает интерпретировать масштаб карты.</span><span class="sxs-lookup"><span data-stu-id="40b8e-113">**Distance scale** Displays a guide to help interpret the scale of the map.</span></span> <span data-ttu-id="40b8e-114">Шкала расстояний на карте одна.</span><span class="sxs-lookup"><span data-stu-id="40b8e-114">A map has one distance scale.</span></span> <span data-ttu-id="40b8e-115">Шкала расстояний определяет текущее значение масштаба окна просмотра карты.</span><span class="sxs-lookup"><span data-stu-id="40b8e-115">The current map viewport zoom value determines the distance scale.</span></span>  
  
 <span data-ttu-id="40b8e-116">![rs_MapElements](../media/rs-mapelements.gif "rs_MapElements")</span><span class="sxs-lookup"><span data-stu-id="40b8e-116">![rs_MapElements](../media/rs-mapelements.gif "rs_MapElements")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="to-change-the-position-of-a-legend-relative-to-the-viewport"></a><a name="Viewport"></a> <span data-ttu-id="40b8e-117">Изменение позиции условных обозначений относительно области просмотра</span><span class="sxs-lookup"><span data-stu-id="40b8e-117">To change the position of a legend relative to the viewport</span></span>  
  
#### <a name="to-change-the-position-of-a-legend-relative-to-the-viewport"></a><span data-ttu-id="40b8e-118">Изменение позиции условных обозначений относительно области просмотра</span><span class="sxs-lookup"><span data-stu-id="40b8e-118">To change the position of a legend relative to the viewport</span></span>  
  
1.  <span data-ttu-id="40b8e-119">В представление конструирования щелкните правой кнопкой мыши условные обозначения и откройте _\<report item->_ страницу **свойства** .</span><span class="sxs-lookup"><span data-stu-id="40b8e-119">In Design view, right-click the legend and open the _\<report item->_**Properties** page.</span></span>  
  
2.  <span data-ttu-id="40b8e-120">В разделе **Позиция**щелкните место, где должны отображаться условные обозначения относительно области отображения.</span><span class="sxs-lookup"><span data-stu-id="40b8e-120">In **Position**, click the location that specifies where to display the legend relative to the viewport.</span></span>  
  
3.  <span data-ttu-id="40b8e-121">Чтобы отобразить условные обозначения вне окна просмотра, выберите **Показать \<report item> внешнее окно просмотра**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-121">To display the legend outside the viewport, select **Show \<report item> outside viewport**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="40b8e-122">В режиме предварительного просмотра условные обозначения карты и цветовая шкала отображаются, только если существуют результаты правил, связанные с условными обозначениями.</span><span class="sxs-lookup"><span data-stu-id="40b8e-122">In preview, map legends and the color scale appear only when there are results from the rules related to that legend.</span></span> <span data-ttu-id="40b8e-123">Если отсутствуют элементы для отображения, в отчете, готовом для просмотра, условные обозначения не появляются.</span><span class="sxs-lookup"><span data-stu-id="40b8e-123">If there are no items to display, the legend does not appear in the rendered report.</span></span>  
  
  
  
##  <a name="to-change-the-layout-of-a-map-legend"></a><a name="MapLegend"></a> <span data-ttu-id="40b8e-124">Изменение макета условных обозначений карты</span><span class="sxs-lookup"><span data-stu-id="40b8e-124">To change the layout of a map legend</span></span>  
  
#### <a name="to-change-the-layout-of-a-map-legend"></a><span data-ttu-id="40b8e-125">Изменение макета условных обозначений карты</span><span class="sxs-lookup"><span data-stu-id="40b8e-125">To change the layout of a map legend</span></span>  
  
1.  <span data-ttu-id="40b8e-126">В режиме конструктора щелкните правой кнопкой мыши условные обозначения и откройте страницу **Свойства условных обозначений** .</span><span class="sxs-lookup"><span data-stu-id="40b8e-126">In Design view, right-click the legend and open the **Legend Properties** page.</span></span>  
  
2.  <span data-ttu-id="40b8e-127">В окне **Макет условных обозначений**, щелкните макет таблицы, которую необходимо использовать для условных обозначений.</span><span class="sxs-lookup"><span data-stu-id="40b8e-127">In **Legend layout**, click the table layout that you want to use for the legend.</span></span> <span data-ttu-id="40b8e-128">При щелчке различных параметров макет в области конструктора будет меняться.</span><span class="sxs-lookup"><span data-stu-id="40b8e-128">As you click different options, the layout on the design surface changes.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-show-or-hide-a-map-legend-title"></a><a name="MapLegendTitle"></a> <span data-ttu-id="40b8e-129">Отображение или скрытие заголовка условных обозначений карты</span><span class="sxs-lookup"><span data-stu-id="40b8e-129">To show or hide a map legend title</span></span>  
  
#### <a name="to-show-or-hide-a-map-legend-title"></a><span data-ttu-id="40b8e-130">Отображение или скрытие заголовка условных обозначений карты</span><span class="sxs-lookup"><span data-stu-id="40b8e-130">To show or hide a map legend title</span></span>  
  
-   <span data-ttu-id="40b8e-131">Щелкните правой кнопкой мыши условные обозначения карты в области конструктора и выберите команду **Показать заголовок условных обозначений**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-131">Right-click the map legend on the design surface, and then click **Show Legend Title**.</span></span>  
  
  
  
##  <a name="to-show-or-hide-a-color-scale-title"></a><a name="ColorScaleTitle"></a> <span data-ttu-id="40b8e-132">Отображение или скрытие заголовка цветовой шкалы</span><span class="sxs-lookup"><span data-stu-id="40b8e-132">To show or hide a color scale title</span></span>  
  
#### <a name="to-show-or-hide-a-color-scale-title"></a><span data-ttu-id="40b8e-133">Отображение или скрытие заголовка цветовой шкалы</span><span class="sxs-lookup"><span data-stu-id="40b8e-133">To show or hide a color scale title</span></span>  
  
-   <span data-ttu-id="40b8e-134">Щелкните правой кнопкой мыши цветовую шкалу в области конструктора и выберите команду **Показать заголовок цветовой шкалы**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-134">Right-click the color scale on the design surface, and then click **Show Color Scale Title**.</span></span>  
  
  
  
##  <a name="to-move-items-out-of-the-first-legend"></a><a name="MoveItems"></a> <span data-ttu-id="40b8e-135">Перемещение элементов из первых условных обозначений</span><span class="sxs-lookup"><span data-stu-id="40b8e-135">To move items out of the first legend</span></span>  
 <span data-ttu-id="40b8e-136">Можно создать необходимое количество условных обозначений, а потом изменить правила для каждого слоя карты, указав, в каких условных обозначениях должны отображаться результаты правила.</span><span class="sxs-lookup"><span data-stu-id="40b8e-136">Create as many additional legends as you need and then update the rules for each map layer specify which legend to display the rule results in.</span></span>  
  
#### <a name="to-create-a-new-legend"></a><span data-ttu-id="40b8e-137">Создание новых условных обозначений</span><span class="sxs-lookup"><span data-stu-id="40b8e-137">To create a new legend</span></span>  
  
-   <span data-ttu-id="40b8e-138">В режиме конструктора щелкните правой кнопкой мыши карту за пределами окна просмотра и выберите пункт **Добавить условные обозначения**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-138">In Design view, right-click the map outside the map viewport, and then click **Add Legend**.</span></span>  
  
     <span data-ttu-id="40b8e-139">На карте появятся новые условные обозначения.</span><span class="sxs-lookup"><span data-stu-id="40b8e-139">A new legend appears on the map.</span></span>  
  
#### <a name="to-display-rule-results-in-a-legend"></a><span data-ttu-id="40b8e-140">Отображение результатов правила в условных обозначениях</span><span class="sxs-lookup"><span data-stu-id="40b8e-140">To display rule results in a legend</span></span>  
  
1.  <span data-ttu-id="40b8e-141">В режиме конструктора щелкните карту, чтобы отобразилась панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="40b8e-141">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="40b8e-142">Щелкните правой кнопкой мыши слой, на котором находятся нужные данные, и выберите пункт _\<map element type\>_ **правило цвета**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-142">Right-click the layer that has the data that you want and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="40b8e-143">Выберите **Условные обозначения**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-143">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="40b8e-144">В раскрывающемся списке **Показать в условных обозначениях** щелкните имя условных обозначений карты, в которых должны отображаться результаты правила.</span><span class="sxs-lookup"><span data-stu-id="40b8e-144">In the **Show in this legend** drop-down list, click the name of the legend to display the rule results in.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-a-template-style"></a><a name="TemplateStyle"></a> <span data-ttu-id="40b8e-145">Изменение цвета элементов карты на основании стиля шаблона</span><span class="sxs-lookup"><span data-stu-id="40b8e-145">To vary map element colors based on a template style</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-a-template-style"></a><span data-ttu-id="40b8e-146">Изменение цвета элементов карты на основании стиля шаблона</span><span class="sxs-lookup"><span data-stu-id="40b8e-146">To vary map element colors based on a template style</span></span>  
  
1.  <span data-ttu-id="40b8e-147">В режиме конструктора щелкните карту, чтобы отобразилась панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="40b8e-147">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="40b8e-148">Щелкните правой кнопкой мыши слой, на котором находятся нужные данные, и выберите пункт _\<map element type\>_ **правило цвета**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-148">Right-click the layer that has the data that you want and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="40b8e-149">Щелкните **Применить стиль шаблона**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-149">Click **Apply template style**.</span></span>  
  
     <span data-ttu-id="40b8e-150">Стиль шаблона задает шрифта, стиль границы и цветовую палитру.</span><span class="sxs-lookup"><span data-stu-id="40b8e-150">A template style specifies font, border style, and color palette.</span></span> <span data-ttu-id="40b8e-151">Каждому элементу карты назначен свой цвет из цветовой палитры темы, заданной в мастере карты или мастере слоя карты.</span><span class="sxs-lookup"><span data-stu-id="40b8e-151">Each map element is assigned a different color from the color palette for the theme that was specified in the Map Wizard or Map Layer Wizard.</span></span> <span data-ttu-id="40b8e-152">Это единственный параметр, который влияет на слои, не имеющие связанных аналитических данных.</span><span class="sxs-lookup"><span data-stu-id="40b8e-152">This is the only option that applies to layers that do not have associated analytical data.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-color-palette"></a><a name="ColorPalette"></a> <span data-ttu-id="40b8e-153">Изменение цвета элементов карты на основании цветовой палитры</span><span class="sxs-lookup"><span data-stu-id="40b8e-153">To vary map element colors based on color palette</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-color-palette"></a><span data-ttu-id="40b8e-154">Изменение цвета элементов карты на основании цветовой палитры</span><span class="sxs-lookup"><span data-stu-id="40b8e-154">To vary map element colors based on color palette</span></span>  
  
1.  <span data-ttu-id="40b8e-155">В режиме конструктора щелкните карту, чтобы отобразилась панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="40b8e-155">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="40b8e-156">Щелкните правой кнопкой мыши слой, на котором находятся нужные данные, и выберите пункт _\<map element type\>_ **правило цвета**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-156">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="40b8e-157">Щелкните **Визуализация данных с помощью цветовой палитры**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-157">Click **Visualize data by using color palette**.</span></span>  
  
     <span data-ttu-id="40b8e-158">Этот параметр использует встроенную или пользовательскую палитру.</span><span class="sxs-lookup"><span data-stu-id="40b8e-158">This option uses a built-in or custom palette that you specify.</span></span> <span data-ttu-id="40b8e-159">На основании связанных аналитических данных каждому элементу карты назначается свой цвет или оттенок цвета из палитры.</span><span class="sxs-lookup"><span data-stu-id="40b8e-159">Based on related analytical data, each map element is assigned a different color or shade of color from the palette.</span></span>  
  
4.  <span data-ttu-id="40b8e-160">В **Поле данных**введите имя поля, содержащего аналитические данные, которые нужно выделить цветом.</span><span class="sxs-lookup"><span data-stu-id="40b8e-160">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="40b8e-161">В поле **Палитра**выберите из раскрывающегося списка имя палитры.</span><span class="sxs-lookup"><span data-stu-id="40b8e-161">In **Palette**, from the drop-down list, select the name of the palette to use.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-color-ranges"></a><a name="ColorRanges"></a> <span data-ttu-id="40b8e-162">Изменение цвета элементов карты на основании цветовых диапазонов</span><span class="sxs-lookup"><span data-stu-id="40b8e-162">To vary map element colors based on color ranges</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-color-ranges"></a><span data-ttu-id="40b8e-163">Изменение цвета элементов карты на основании цветовых диапазонов</span><span class="sxs-lookup"><span data-stu-id="40b8e-163">To vary map element colors based on color ranges</span></span>  
  
1.  <span data-ttu-id="40b8e-164">В режиме конструктора щелкните карту, чтобы отобразилась панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="40b8e-164">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="40b8e-165">Щелкните правой кнопкой мыши слой, на котором находятся нужные данные, и выберите пункт _\<map element type\>_ **правило цвета**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-165">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="40b8e-166">Щелкните **Визуализация данных с помощью цветовых диапазонов**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-166">Click **Visualize data by using color ranges**.</span></span>  
  
     <span data-ttu-id="40b8e-167">Этот параметр, в сочетании с начальным, средним и конечным цветами, заданными на этой странице, и параметрами, указанными на странице **Распределение** , разделяет связанные аналитические данные по диапазонам.</span><span class="sxs-lookup"><span data-stu-id="40b8e-167">This option, combined with the start, middle, and end colors that you specify on this page and the options that you specify on the **Distribution** page, divide the related analytical data into ranges.</span></span> <span data-ttu-id="40b8e-168">Обработчик отчетов назначает соответствующий цвет каждому элементу карты на основании связанных данных и диапазона, в который тот попадает.</span><span class="sxs-lookup"><span data-stu-id="40b8e-168">The report processor assigns the appropriate color to each map element based on the its associated data and the range that it falls into.</span></span>  
  
4.  <span data-ttu-id="40b8e-169">В **Поле данных**введите имя поля, содержащего аналитические данные, которые нужно выделить цветом.</span><span class="sxs-lookup"><span data-stu-id="40b8e-169">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="40b8e-170">В поле **Начальный цвет**укажите цвет, который нужно использовать для нижнего диапазона.</span><span class="sxs-lookup"><span data-stu-id="40b8e-170">In **Start color**, specify the color to use for the lowest range.</span></span>  
  
6.  <span data-ttu-id="40b8e-171">В поле **Средний цвет**укажите цвет, который нужно использовать для среднего диапазона.</span><span class="sxs-lookup"><span data-stu-id="40b8e-171">In **Middle color**, specify the color to use for the middle range.</span></span>  
  
7.  <span data-ttu-id="40b8e-172">В поле **Конечный цвет**укажите цвет, который нужно использовать для верхнего диапазона.</span><span class="sxs-lookup"><span data-stu-id="40b8e-172">In **End color**, specify the color to use for the highest range.</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-custom-colors"></a><a name="CustomColors"></a> <span data-ttu-id="40b8e-173">Изменение цвета элементов карты на основании пользовательских цветов</span><span class="sxs-lookup"><span data-stu-id="40b8e-173">To vary map element colors based on custom colors</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-custom-colors"></a><span data-ttu-id="40b8e-174">Изменение цвета элементов карты на основании пользовательских цветов</span><span class="sxs-lookup"><span data-stu-id="40b8e-174">To vary map element colors based on custom colors</span></span>  
  
1.  <span data-ttu-id="40b8e-175">В режиме конструктора щелкните карту, чтобы отобразилась панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="40b8e-175">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="40b8e-176">Щелкните правой кнопкой мыши слой, на котором находятся нужные данные, и выберите пункт _\<map element type\>_ **правило цвета**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-176">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="40b8e-177">Щелкните **Визуализация данных с помощью пользовательских цветов**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-177">Click **Visualize data by using custom colors**.</span></span>  
  
     <span data-ttu-id="40b8e-178">Этот параметр использует указанный пользователем список цветов.</span><span class="sxs-lookup"><span data-stu-id="40b8e-178">This option uses the list of colors that you specify.</span></span> <span data-ttu-id="40b8e-179">На основании связанных аналитических данных каждому элементу карты назначается цвет из списка.</span><span class="sxs-lookup"><span data-stu-id="40b8e-179">Based on related analytical data, each map element is assigned a color from the list.</span></span> <span data-ttu-id="40b8e-180">Если элементов карты больше, чем цветов в списке, то цвет не назначается.</span><span class="sxs-lookup"><span data-stu-id="40b8e-180">If there are more map elements than colors, no color is assigned.</span></span>  
  
4.  <span data-ttu-id="40b8e-181">В **Поле данных**введите имя поля, содержащего аналитические данные, которые нужно выделить цветом.</span><span class="sxs-lookup"><span data-stu-id="40b8e-181">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="40b8e-182">В окне **Пользовательские цвета**нажмите кнопку **Добавить** , чтобы указать пользовательский цвет.</span><span class="sxs-lookup"><span data-stu-id="40b8e-182">In **Custom colors**, click **Add** to specify each custom color.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-set-distribution-options-for-a-legend"></a><a name="DistributionOptions"></a> <span data-ttu-id="40b8e-183">Задание параметров распределения для условных обозначений</span><span class="sxs-lookup"><span data-stu-id="40b8e-183">To set distribution options for a legend</span></span>  
  
#### <a name="to-set-distribution-options-for-a-legend"></a><span data-ttu-id="40b8e-184">Задание параметров распределения для условных обозначений</span><span class="sxs-lookup"><span data-stu-id="40b8e-184">To set distribution options for a legend</span></span>  
  
1.  <span data-ttu-id="40b8e-185">В режиме конструктора щелкните карту, чтобы отобразилась панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="40b8e-185">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="40b8e-186">Щелкните правой кнопкой мыши слой, на котором находятся нужные данные, и выберите пункт _\<map element type\>_ **правило цвета**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-186">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="40b8e-187">Выберите параметр **визуализировать данные с помощью** \<rule type\> .</span><span class="sxs-lookup"><span data-stu-id="40b8e-187">Select the **Visualize data by using** \<rule type\> option.</span></span> <span data-ttu-id="40b8e-188">Чтобы использовать параметры распределения, нужно создать диапазоны на странице **Распределение** на основании аналитических данных, связанных со слоем.</span><span class="sxs-lookup"><span data-stu-id="40b8e-188">To use distribution options, you must create ranges on the **Distribution** page based on analytical data that is associated with the layer.</span></span>  
  
4.  <span data-ttu-id="40b8e-189">Щелкните **Распределение**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-189">Click **Distribution**.</span></span>  
  
5.  <span data-ttu-id="40b8e-190">Выберите один из следующих типов распределения.</span><span class="sxs-lookup"><span data-stu-id="40b8e-190">Select one of the following distribution types:</span></span>  
  
    -   <span data-ttu-id="40b8e-191">**Равноинтервальный**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-191">**EqualInterval**.</span></span> <span data-ttu-id="40b8e-192">Задает диапазоны, которые разбивают данные на равные интервалы.</span><span class="sxs-lookup"><span data-stu-id="40b8e-192">Specifies ranges that divide the data into equal range intervals.</span></span>  
  
    -   <span data-ttu-id="40b8e-193">**Равнораспределенный**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-193">**EqualDistribution**.</span></span> <span data-ttu-id="40b8e-194">Задает диапазоны, которые делят данные так, что каждый диапазон содержит равное число элементов.</span><span class="sxs-lookup"><span data-stu-id="40b8e-194">Specifies ranges that divide that data so that each range has an equal number of items.</span></span>  
  
    -   <span data-ttu-id="40b8e-195">**Оптимальный**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-195">**Optimal**.</span></span> <span data-ttu-id="40b8e-196">Задает распределение с автоматически сбалансированными поддиапазонами.</span><span class="sxs-lookup"><span data-stu-id="40b8e-196">Specifies ranges that automatically adjust distribution to create balanced subranges.</span></span>  
  
    -   <span data-ttu-id="40b8e-197">**Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-197">**Custom**.</span></span> <span data-ttu-id="40b8e-198">Укажите собственное количество диапазонов для управления распределением значений.</span><span class="sxs-lookup"><span data-stu-id="40b8e-198">Specify your own number of ranges to control the distribution of values.</span></span>  
  
     <span data-ttu-id="40b8e-199">Дополнительные сведения о параметрах распределения см. в разделе [Изменение параметров отображения многоугольников, линий и точек с помощью правил и аналитических данных &#40;построитель отчетов и службы SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="40b8e-199">For more information about distribution options, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
6.  <span data-ttu-id="40b8e-200">В поле **Количество поддиапазонов**введите необходимое число поддиапазонов.</span><span class="sxs-lookup"><span data-stu-id="40b8e-200">In **Number of subranges**, type the number of subranges to use.</span></span> <span data-ttu-id="40b8e-201">Для типа распределения **Оптимальный**количество поддиапазонов вычисляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="40b8e-201">When the distribution type is **Optimal**, the number of subranges is automatically calculated.</span></span>  
  
7.  <span data-ttu-id="40b8e-202">В поле **Начало диапазона**введите минимальное значение диапазона.</span><span class="sxs-lookup"><span data-stu-id="40b8e-202">In **Range start**, type a minimum range value.</span></span> <span data-ttu-id="40b8e-203">Все значения меньше этого числа — то же самое, что минимум диапазона.</span><span class="sxs-lookup"><span data-stu-id="40b8e-203">All values less than this number are the same as the range minimum.</span></span>  
  
8.  <span data-ttu-id="40b8e-204">В поле **Конец диапазона**введите максимальное значение диапазона.</span><span class="sxs-lookup"><span data-stu-id="40b8e-204">In **Range end**, type a maximum range value.</span></span> <span data-ttu-id="40b8e-205">Все значения больше этого числа — то же самое, что максимум диапазона.</span><span class="sxs-lookup"><span data-stu-id="40b8e-205">All values larger than this number are the same as the range maximum.</span></span>  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-contents-of-a-rule-legend"></a><a name="RuleLegend"></a> <span data-ttu-id="40b8e-206">Изменение содержимого условных обозначений правила</span><span class="sxs-lookup"><span data-stu-id="40b8e-206">To change the contents of a rule legend</span></span>  
  
#### <a name="to-change-the-contents-of-a-color-size-width-or-marker-type-legend"></a><span data-ttu-id="40b8e-207">Изменение содержимого условных обозначений: цвета, размера, ширины или типа маркера</span><span class="sxs-lookup"><span data-stu-id="40b8e-207">To change the contents of a color, size, width, or marker type legend</span></span>  
  
1.  <span data-ttu-id="40b8e-208">В режиме конструктора щелкните карту, чтобы отобразилась панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="40b8e-208">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="40b8e-209">Щелкните правой кнопкой мыши слой, на котором находятся нужные данные, и выберите пункт _\<map element type\>_ **правило**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-209">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="40b8e-210">Убедитесь, что выбран параметр **визуализировать данные с помощью** \<*rule type*> .</span><span class="sxs-lookup"><span data-stu-id="40b8e-210">Verify that **Visualize data by using** \<*rule type*> is selected.</span></span>  
  
4.  <span data-ttu-id="40b8e-211">Убедитесь, что в **Поле данных**выбраны аналитические данные, визуализируемые на слое.</span><span class="sxs-lookup"><span data-stu-id="40b8e-211">In **Data field**, verify that the analytical data that you are visualizing on the layer is selected.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="40b8e-212">Если в раскрывающемся списке нет полей, щелкните правой кнопкой слой и выберите пункт **Данные слоя** , чтобы открыть диалоговое окно "Свойства данных слоя карты", страницу "Аналитические данные" и убедитесь, что аналитические данные для этого слоя указаны.</span><span class="sxs-lookup"><span data-stu-id="40b8e-212">If no fields appear in the drop-down list, right-click the layer, and then click **Layer Data** to open the Map Layer Data Properties Dialog Box, Analytical Data page and verify that you have specified analytical data for this layer.</span></span>  
  
5.  <span data-ttu-id="40b8e-213">Выберите **Условные обозначения**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-213">Click **Legend**.</span></span>  
  
6.  <span data-ttu-id="40b8e-214">В поле **Показать в условных обозначениях**выберите условные обозначения карты, в которых должны отображаться результаты правила.</span><span class="sxs-lookup"><span data-stu-id="40b8e-214">In **Show in this legend**, select the map legend to use to display the rule results.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-contents-of-the-color-scale"></a><a name="ColorScale"></a> <span data-ttu-id="40b8e-215">Изменение содержимого цветовой шкалы</span><span class="sxs-lookup"><span data-stu-id="40b8e-215">To change the contents of the color scale</span></span>  
  
#### <a name="to-change-the-contents-of-the-color-scale-or-a-color-legend"></a><span data-ttu-id="40b8e-216">Изменение содержимого цветовой шкалы или условных обозначений цвета</span><span class="sxs-lookup"><span data-stu-id="40b8e-216">To change the contents of the color scale or a color legend</span></span>  
  
1.  <span data-ttu-id="40b8e-217">В режиме конструктора щелкните карту, чтобы отобразилась панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="40b8e-217">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="40b8e-218">Щелкните правой кнопкой мыши слой, на котором находятся нужные данные, и выберите пункт _\<map element type\>_ **правило цвета**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-218">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="40b8e-219">Выберите параметр правила цвета, который нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="40b8e-219">Select the color rule option to use.</span></span> <span data-ttu-id="40b8e-220">Для отображения элементов в условных обозначениях или цветовой шкале на карте необходимо выбрать один из **визуализаций данных с помощью** \<rule type> параметров.</span><span class="sxs-lookup"><span data-stu-id="40b8e-220">To display items in a map legend or color scale, you must select one of the **Visualize data by using** \<rule type> options.</span></span>  
  
4.  <span data-ttu-id="40b8e-221">Убедитесь, что в **Поле данных**выбраны аналитические данные, визуализируемые на слое.</span><span class="sxs-lookup"><span data-stu-id="40b8e-221">In **Data field**, verify that the analytical data that you are visualizing on the layer is selected.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="40b8e-222">Если в раскрывающемся списке нет полей, щелкните правой кнопкой слой и выберите пункт **Данные слоя** , чтобы открыть диалоговое окно "Свойства данных слоя карты", страницу "Аналитические данные" и убедитесь, что аналитические данные для этого слоя указаны.</span><span class="sxs-lookup"><span data-stu-id="40b8e-222">If no fields appear in the drop-down list, right-click the layer, and then click **Layer Data** to open the Map Layer Data Properties Dialog Box, Analytical Data page and verify that you have specified analytical data for this layer.</span></span>  
  
5.  <span data-ttu-id="40b8e-223">Выберите **Условные обозначения**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-223">Click **Legend**.</span></span>  
  
6.  <span data-ttu-id="40b8e-224">В поле **Параметры цветовой шкалы**, выберите **Отобразить на цветовой шкале** , чтобы отобразить результаты правила на цветовой шкале.</span><span class="sxs-lookup"><span data-stu-id="40b8e-224">In **Color scale options**, select **Show in color scale** to display the rule results in the color scale.</span></span> <span data-ttu-id="40b8e-225">Этот параметр можно указать для нескольких правил цвета.</span><span class="sxs-lookup"><span data-stu-id="40b8e-225">You can specify this option for more than one color rule.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-remove-all-items-from-a-legend"></a><a name="HideItems"></a> <span data-ttu-id="40b8e-226">Удаление всех элементов из условных обозначений</span><span class="sxs-lookup"><span data-stu-id="40b8e-226">To remove all items from a legend</span></span>  
  
#### <a name="to-hide-items-based-on-a-rule"></a><span data-ttu-id="40b8e-227">Скрытие элементов на основе правила</span><span class="sxs-lookup"><span data-stu-id="40b8e-227">To hide items based on a rule</span></span>  
  
1.  <span data-ttu-id="40b8e-228">В режиме конструктора щелкните карту, чтобы отобразилась панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="40b8e-228">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="40b8e-229">Щелкните правой кнопкой мыши слой, на котором находятся нужные данные, и выберите пункт _\<map element type\>_ **правило**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-229">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="40b8e-230">Выберите **Условные обозначения**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-230">Click **Legend**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-format-of-content-in-a-legend"></a><a name="ChangeFormatItems"></a> <span data-ttu-id="40b8e-231">Изменение формата содержимого в условных обозначениях</span><span class="sxs-lookup"><span data-stu-id="40b8e-231">To change the format of content in a legend</span></span>  
 <span data-ttu-id="40b8e-232">Задайте параметры условных обозначений для правила, связанного с условными обозначениями карты.</span><span class="sxs-lookup"><span data-stu-id="40b8e-232">Set legend options for the rule that is associated with the map legend.</span></span>  
  
#### <a name="to-change-the-format-of-content-in-a-legend"></a><span data-ttu-id="40b8e-233">Изменение формата содержимого в условных обозначениях</span><span class="sxs-lookup"><span data-stu-id="40b8e-233">To change the format of content in a legend</span></span>  
  
1.  <span data-ttu-id="40b8e-234">В режиме конструктора щелкните карту, чтобы отобразилась панель «Карта».</span><span class="sxs-lookup"><span data-stu-id="40b8e-234">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="40b8e-235">Щелкните правой кнопкой мыши слой, на котором находятся нужные данные, и выберите пункт _\<map element type\>_ **правило**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-235">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="40b8e-236">Выберите **Условные обозначения**.</span><span class="sxs-lookup"><span data-stu-id="40b8e-236">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="40b8e-237">В**Тексте условных обозначений** отображаются ключевые слова, которые определяют данные, отображаемые в условных обозначениях.</span><span class="sxs-lookup"><span data-stu-id="40b8e-237">**Legend text** displays keywords that specify which data appears in the legend.</span></span> <span data-ttu-id="40b8e-238">Ключевые слова карты и пользовательские форматы помогают управлять форматом текста условных обозначений.</span><span class="sxs-lookup"><span data-stu-id="40b8e-238">Use map keywords and custom formats to help control the format of legend text.</span></span> <span data-ttu-id="40b8e-239">Например, #FROMVALUE {C2} задает формат валюты с двумя десятичными разрядами.</span><span class="sxs-lookup"><span data-stu-id="40b8e-239">For example, #FROMVALUE {C2} specifies a currency format with two decimal places.</span></span> <span data-ttu-id="40b8e-240">Дополнительные сведения см. в разделе [Изменение параметров отображения многоугольников, линий и точек с помощью правил и аналитических данных (построитель отчетов и службы SSRS)](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="40b8e-240">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="40b8e-241">См. также:</span><span class="sxs-lookup"><span data-stu-id="40b8e-241">See Also</span></span>  
 <span data-ttu-id="40b8e-242">[Карты (построитель отчетов и службы SSRS)](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40b8e-242">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="40b8e-243">[Добавление, изменение или удаление карты или слоя карты &#40;построитель отчетов и службы SSRS&#41;](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40b8e-243">[Add, Change, or Delete a Map or Map Layer &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="40b8e-244">[Настройка данных и отображения карты или слоя карты (построитель отчетов и службы SSRS)](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40b8e-244">[Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="40b8e-245">[Устранение неполадок в отчетах: отчеты-карты (построитель отчетов и службы SSRS)](troubleshoot-reports-map-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40b8e-245">[Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;](troubleshoot-reports-map-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="40b8e-246">Мастер карт и мастер слоев карт (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="40b8e-246">Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;</span></span>](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md)  
  
  
