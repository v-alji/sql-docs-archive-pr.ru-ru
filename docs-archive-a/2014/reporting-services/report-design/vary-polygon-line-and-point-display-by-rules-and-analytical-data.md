---
title: Изменение вида многоугольников, линий и точек с помощью правил и аналитических данных (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapembeddedpolygonlayerproperties.general.f1
- sql12.rtp.rptdesigner.maplinelayerproperties.widthrules.f1
- sql12.rtp.rptdesigner.mapembeddedpointlayerproperties.general.f1
- "10538"
- "10537"
- MICROSOFT.REPORTDESIGNER.MAPMARKER.MARKERSTYLE
- sql12.rtp.rptdesigner.mapembeddedlinelayerproperties.general.f1
- "10531"
- "10536"
ms.assetid: 7f1f5584-37b4-4fa2-ae44-8988c5f0c744
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 20757988a82f9ace8f282e8586b81f45b7eab8a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733601"
---
# <a name="vary-polygon-line-and-point-display-by-rules-and-analytical-data-report-builder-and-ssrs"></a><span data-ttu-id="2a57e-102">Изменение параметров отображения многоугольников, линий и точек с помощью правил и аналитических данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="2a57e-102">Vary Polygon, Line, and Point Display by Rules and Analytical Data (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2a57e-103">Параметры отображения многоугольников, линий и точек слоя карты управляются настройками слоя, правилами для элементов слоя карты или переопределенными параметрами отдельных внедренных элементов слоя карты.</span><span class="sxs-lookup"><span data-stu-id="2a57e-103">The display options for polygons, lines, and points on a map layer are controlled by setting options for the layer, by setting rules for the map elements on the layer, or by overriding options for specific embedded map elements on a layer.</span></span>  
  
 <span data-ttu-id="2a57e-104">Параметры отображения применяются с определенными приоритетами, перечисленными далее от низшего к высшему.</span><span class="sxs-lookup"><span data-stu-id="2a57e-104">Display options apply in a specific precedence, listed from lowest to highest precedence:</span></span>  
  
1.  <span data-ttu-id="2a57e-105">Параметры, заданные для слоя многоугольников, линий или точек, применяются ко всем элементам этого слоя карты вне зависимости от того, внедрены ли они в определение отчета.</span><span class="sxs-lookup"><span data-stu-id="2a57e-105">Options set on a polygon layer, a line layer, and a point layer apply to all map elements on that layer, whether or not the map elements are embedded in the report definition.</span></span>  
  
2.  <span data-ttu-id="2a57e-106">Параметры, заданные для правил, применяются ко всем элементам слоя карты.</span><span class="sxs-lookup"><span data-stu-id="2a57e-106">Options set for rules apply to all map elements on a layer.</span></span> <span data-ttu-id="2a57e-107">Все параметры визуализации данных применяются только к элементам карты, связанным с пространственными данными.</span><span class="sxs-lookup"><span data-stu-id="2a57e-107">All data visualization options apply only to map elements that are associated with spatial data.</span></span> <span data-ttu-id="2a57e-108">Параметры визуализации данных требуют задания поля данных, на котором основаны изменения параметров отображения.</span><span class="sxs-lookup"><span data-stu-id="2a57e-108">A data visualization option requires you to specify a data field to base display variations on.</span></span> <span data-ttu-id="2a57e-109">Перед применением правил визуализации данных необходимо задать поля соответствия аналитических и пространственных данных.</span><span class="sxs-lookup"><span data-stu-id="2a57e-109">You must have set the match fields for the analytical and spatial data before you can apply data visualization rules.</span></span> <span data-ttu-id="2a57e-110">Дополнительные сведения см. в разделе [Карты (построитель отчетов и службы SSRS)](maps-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2a57e-110">For more information, see [Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="2a57e-111">Параметры, заданные для отдельных внедренных элементов карты.</span><span class="sxs-lookup"><span data-stu-id="2a57e-111">Options that you set for selected embedded map elements.</span></span> <span data-ttu-id="2a57e-112">Обратите внимание, что при переопределении параметров слоя изменения в определении отчета необратимы.</span><span class="sxs-lookup"><span data-stu-id="2a57e-112">Note that, when you override the layer options, the changes that you make to the report definition are permanent.</span></span> <span data-ttu-id="2a57e-113">Можно как изменять значения полей данных, так и переопределять параметры отображения для настройки внешнего вида отдельных многоугольников, линий и точек слоя.</span><span class="sxs-lookup"><span data-stu-id="2a57e-113">You can change the data field values as well as override display options to customize the way specific polygons, lines, and points appear on a layer.</span></span>  
  
 <span data-ttu-id="2a57e-114">Помимо управления отображением элементов слоя карты, можно управлять и прозрачностью слоя, что позволяет слоям, отрисованным раньше, просвечивать сквозь слои, отрисованные позже.</span><span class="sxs-lookup"><span data-stu-id="2a57e-114">In addition to controlling the display of map elements on a layer, you can control the layer transparency to allow layers that are drawn earlier to show through layers that are drawn later.</span></span> <span data-ttu-id="2a57e-115">Дополнительные сведения об изменении параметров, которые влияют на карты или слоя карты в целом, см. в разделе [Настройка данных и отображения карты или слоя карты (построитель отчетов и службы SSRS)](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2a57e-115">For more information about changing options that affect the map or the entire map layer, see [Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="understanding-rules"></a><a name="Rules"></a> <span data-ttu-id="2a57e-116">Основные сведения о правилах</span><span class="sxs-lookup"><span data-stu-id="2a57e-116">Understanding Rules</span></span>  
 <span data-ttu-id="2a57e-117">Обработчик отчетов поддерживает четыре типа правил, позволяющих автоматически настраивать параметры отображения элементов слоя карты.</span><span class="sxs-lookup"><span data-stu-id="2a57e-117">You can set four types of rules that enable the report processor to automatically adjust display properties for map elements on a layer.</span></span> <span data-ttu-id="2a57e-118">Правила различаются для элементов карты разных типов: многоугольников, линий и точек.</span><span class="sxs-lookup"><span data-stu-id="2a57e-118">Rules vary depending on the map element type: polygons, lines, or points.</span></span>  
  
-   <span data-ttu-id="2a57e-119">**Многоугольники.**</span><span class="sxs-lookup"><span data-stu-id="2a57e-119">**Polygons.**</span></span> <span data-ttu-id="2a57e-120">Различные цвета многоугольников.</span><span class="sxs-lookup"><span data-stu-id="2a57e-120">Vary polygon color.</span></span>  
  
    -   <span data-ttu-id="2a57e-121">**Центральные точки многоугольников.**</span><span class="sxs-lookup"><span data-stu-id="2a57e-121">**Polygon Center Points.**</span></span> <span data-ttu-id="2a57e-122">Различные цвета, размеры и типы маркеров, которые отображаются в центральной точке каждого многоугольника.</span><span class="sxs-lookup"><span data-stu-id="2a57e-122">For markers that display at the center point of each polygon, vary marker color, marker size, and marker type.</span></span>  
  
-   <span data-ttu-id="2a57e-123">**Линии.**</span><span class="sxs-lookup"><span data-stu-id="2a57e-123">**Lines.**</span></span> <span data-ttu-id="2a57e-124">Различные цвета и толщины линий.</span><span class="sxs-lookup"><span data-stu-id="2a57e-124">Vary line color and line width.</span></span>  
  
-   <span data-ttu-id="2a57e-125">**Точки.**</span><span class="sxs-lookup"><span data-stu-id="2a57e-125">**Points.**</span></span> <span data-ttu-id="2a57e-126">Различные цвета, размеры и типы маркеров, которые отображаются в каждой точке.</span><span class="sxs-lookup"><span data-stu-id="2a57e-126">For markers that display for each point, vary marker color, marker size, and marker type.</span></span>  
  
##  <a name="understanding-color-rules"></a><a name="Color"></a> <span data-ttu-id="2a57e-127">Основные сведения о правилах цветов</span><span class="sxs-lookup"><span data-stu-id="2a57e-127">Understanding Color Rules</span></span>  
 <span data-ttu-id="2a57e-128">Правила цвета применяются для заполнения многоугольников, линий и маркеров, представляющих точки или центральные точки многоугольников, определенным цветом.</span><span class="sxs-lookup"><span data-stu-id="2a57e-128">Color rules apply to fill colors for polygons, lines, and markers that represent points or polygon center points.</span></span>  
  
 <span data-ttu-id="2a57e-129">Правила цвета поддерживают четыре варианта использования.</span><span class="sxs-lookup"><span data-stu-id="2a57e-129">Color rules support four options:</span></span>  
  
-   <span data-ttu-id="2a57e-130">Применение стиля шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a57e-130">Apply template style.</span></span> <span data-ttu-id="2a57e-131">Тема, выбранная в мастере, определяет стиль шаблона слоя.</span><span class="sxs-lookup"><span data-stu-id="2a57e-131">The theme that you chose in the wizard defines the template style for the layer.</span></span> <span data-ttu-id="2a57e-132">Тема задает стиль шрифта, стиль границы и палитру.</span><span class="sxs-lookup"><span data-stu-id="2a57e-132">Theme sets the style for font, the border style, and the palette.</span></span>  
  
-   <span data-ttu-id="2a57e-133">Визуализация данных с помощью палитры цветов.</span><span class="sxs-lookup"><span data-stu-id="2a57e-133">Visualize data by using color palette.</span></span> <span data-ttu-id="2a57e-134">Палитра указывается по имени.</span><span class="sxs-lookup"><span data-stu-id="2a57e-134">You specify a palette by name.</span></span> <span data-ttu-id="2a57e-135">Обработчик отчетов задает цвет каждого элемента слоя карты, последовательно проходя по цветам палитры, а затем выбирая все более светлые оттенки каждого цвета палитры.</span><span class="sxs-lookup"><span data-stu-id="2a57e-135">The report processor sets the color of each map element in a layer by stepping through each color in the palette, and then applying successively lighter shades of each color in the palette.</span></span>  
  
-   <span data-ttu-id="2a57e-136">Визуализация данных с помощью диапазонов цветов.</span><span class="sxs-lookup"><span data-stu-id="2a57e-136">Visualize data by using color ranges.</span></span> <span data-ttu-id="2a57e-137">Указываются начальный, средний и конечный цвета.</span><span class="sxs-lookup"><span data-stu-id="2a57e-137">You specify a beginning, middle, and end color.</span></span> <span data-ttu-id="2a57e-138">Затем указываются параметры распределения.</span><span class="sxs-lookup"><span data-stu-id="2a57e-138">Then you specify distribution options.</span></span> <span data-ttu-id="2a57e-139">Обработчик отчетов использует значения параметров распределения для создания набора цветов, аналогичного используемому в карте температур.</span><span class="sxs-lookup"><span data-stu-id="2a57e-139">The report processor uses the distribution option values to create a set of colors that produces a display similar to a heat map.</span></span> <span data-ttu-id="2a57e-140">Карта температур отображает цвет, соответствующий температуре.</span><span class="sxs-lookup"><span data-stu-id="2a57e-140">A heat map displays color as related to temperature.</span></span> <span data-ttu-id="2a57e-141">Например, на шкале от 0 до 100 малые значения обозначаются синим цветом и представляют холод, а большие значения обозначаются красным цветом и представляют тепло.</span><span class="sxs-lookup"><span data-stu-id="2a57e-141">For example, on a scale of 0 to 100, low values are blue to represent cold and high values are red to represent hot.</span></span>  
  
-   <span data-ttu-id="2a57e-142">Визуализация данных с помощью пользовательских цветов.</span><span class="sxs-lookup"><span data-stu-id="2a57e-142">Visualize data by using custom colors.</span></span> <span data-ttu-id="2a57e-143">Указывается набор цветов.</span><span class="sxs-lookup"><span data-stu-id="2a57e-143">You specify a set of colors.</span></span> <span data-ttu-id="2a57e-144">Обработчик отчетов задает цвет каждого элемента слоя карты, последовательно проходя по заданным значениям.</span><span class="sxs-lookup"><span data-stu-id="2a57e-144">The report processor sets the color of each map element in the layer by stepping through the values that you specify.</span></span>  
  
 <span data-ttu-id="2a57e-145">Палитра по умолчанию содержит белый цвет.</span><span class="sxs-lookup"><span data-stu-id="2a57e-145">The default palette includes the color white.</span></span> <span data-ttu-id="2a57e-146">Чтобы избежать резкого контраста между белым цветом и другими цветами палитры, задавайте в качестве начального светлый цвет из палитры.</span><span class="sxs-lookup"><span data-stu-id="2a57e-146">To avoid the strong contrast between white and other colors in the palette, specify a start color that is a light color in the palette.</span></span>  
  
 <span data-ttu-id="2a57e-147">Для отображения элементов карты, не связанных с данными, без использования цвета задайте для элементов слоя карты значение по умолчанию **Без цвета** .</span><span class="sxs-lookup"><span data-stu-id="2a57e-147">To display map elements that are not associated with data as colorless, set **No Color** for the default color for map elements on the layer.</span></span>  
  
### <a name="color-scale"></a><span data-ttu-id="2a57e-148">Шкала цветов</span><span class="sxs-lookup"><span data-stu-id="2a57e-148">Color Scale</span></span>  
 <span data-ttu-id="2a57e-149">По умолчанию все значения правила цвета отображаются в шкале цветов, а также в первой легенде.</span><span class="sxs-lookup"><span data-stu-id="2a57e-149">By default, all color rule values appear in the color scale, in addition to appearing in the first legend.</span></span> <span data-ttu-id="2a57e-150">Шкала цветов предназначена для отображения одного диапазона цветов.</span><span class="sxs-lookup"><span data-stu-id="2a57e-150">The color scale is designed to display one range of colors.</span></span> <span data-ttu-id="2a57e-151">Выберите для отображения в ней цвета, соответствующие наиболее важным данным.</span><span class="sxs-lookup"><span data-stu-id="2a57e-151">Choose the most important data to display in the color scale.</span></span>  
  
 <span data-ttu-id="2a57e-152">Чтобы удалить ненужные значения из шкалы цветов, снимите соответствующий флажок для каждого правила цвета на каждом слое.</span><span class="sxs-lookup"><span data-stu-id="2a57e-152">To remove the values that you do not want in the color scale, clear the color scale option for every color rule on every layer.</span></span>  
  
##  <a name="understanding-line-width-rules"></a><a name="Width"></a> <span data-ttu-id="2a57e-153">Основные сведения о правилах толщины линии</span><span class="sxs-lookup"><span data-stu-id="2a57e-153">Understanding Line Width Rules</span></span>  
 <span data-ttu-id="2a57e-154">Правила толщины применяются к линиям.</span><span class="sxs-lookup"><span data-stu-id="2a57e-154">Width rules apply to lines.</span></span> <span data-ttu-id="2a57e-155">Правила толщины поддерживают два параметра использования.</span><span class="sxs-lookup"><span data-stu-id="2a57e-155">Width rules support two options:</span></span>  
  
-   <span data-ttu-id="2a57e-156">Использование толщины линий по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2a57e-156">Use a default line width.</span></span> <span data-ttu-id="2a57e-157">Толщина линий задается в пунктах.</span><span class="sxs-lookup"><span data-stu-id="2a57e-157">You specify the line width in points.</span></span>  
  
-   <span data-ttu-id="2a57e-158">Визуализация данных с использованием толщины линий.</span><span class="sxs-lookup"><span data-stu-id="2a57e-158">Visualize data by using line width.</span></span> <span data-ttu-id="2a57e-159">Задается минимальная и максимальная толщина линий, поле данных, в зависимости от которого изменяется толщина, а также параметры распределения, которые применяются к данным.</span><span class="sxs-lookup"><span data-stu-id="2a57e-159">You set the minimum and maximum widths for the line, specify the data field to use to vary the width, and then specify the distribution options to apply to that data.</span></span>  
  
##  <a name="understanding-marker-size-rules"></a><a name="Size"></a> <span data-ttu-id="2a57e-160">Основные сведения о правилах размера маркера</span><span class="sxs-lookup"><span data-stu-id="2a57e-160">Understanding Marker Size Rules</span></span>  
 <span data-ttu-id="2a57e-161">Правила размера применяются к маркерам, представляющим точки или центральные точки многоугольников.</span><span class="sxs-lookup"><span data-stu-id="2a57e-161">Size rules apply to markers that represent points or polygon center points.</span></span> <span data-ttu-id="2a57e-162">Правила размера поддерживают два варианта использования.</span><span class="sxs-lookup"><span data-stu-id="2a57e-162">Size rules support two options:</span></span>  
  
-   <span data-ttu-id="2a57e-163">Использование размера маркера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2a57e-163">Use a default marker size.</span></span> <span data-ttu-id="2a57e-164">Размер задается в пунктах.</span><span class="sxs-lookup"><span data-stu-id="2a57e-164">You specify the size in points.</span></span>  
  
-   <span data-ttu-id="2a57e-165">Визуализация данных при помощи размера.</span><span class="sxs-lookup"><span data-stu-id="2a57e-165">Visualize data by using size.</span></span> <span data-ttu-id="2a57e-166">Задается минимальный и максимальный размер маркера, поле данных, в зависимости от которого изменяется размер, а также параметры распределения, которые применяются к данным.</span><span class="sxs-lookup"><span data-stu-id="2a57e-166">You set the minimum and maximum sizes for the marker, specify the data field to use to vary the size, and then specify the distribution options to apply to that data.</span></span>  
  
##  <a name="understanding-marker-type-rules"></a><a name="Marker"></a> <span data-ttu-id="2a57e-167">Основные сведения о правилах типа маркера</span><span class="sxs-lookup"><span data-stu-id="2a57e-167">Understanding Marker Type Rules</span></span>  
 <span data-ttu-id="2a57e-168">Правила типа маркера применяются к маркерам, представляющим точки или центральные точки многоугольников.</span><span class="sxs-lookup"><span data-stu-id="2a57e-168">Marker type rules apply to markers that represent points or polygon center points.</span></span> <span data-ttu-id="2a57e-169">Правила типа маркера поддерживают два варианта использования.</span><span class="sxs-lookup"><span data-stu-id="2a57e-169">Marker type rules support two options:</span></span>  
  
-   <span data-ttu-id="2a57e-170">Использование типа маркера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2a57e-170">Use a default marker type.</span></span> <span data-ttu-id="2a57e-171">Указывается один из доступных типов маркеров.</span><span class="sxs-lookup"><span data-stu-id="2a57e-171">You specify one of the available marker types.</span></span>  
  
-   <span data-ttu-id="2a57e-172">Визуализация данных при помощи маркеров.</span><span class="sxs-lookup"><span data-stu-id="2a57e-172">Visualize data by using markers.</span></span> <span data-ttu-id="2a57e-173">Указывается набор маркеров и порядок их применения.</span><span class="sxs-lookup"><span data-stu-id="2a57e-173">You specify a set of markers and specify the order in which you want them used.</span></span> <span data-ttu-id="2a57e-174">Существуют маркеры следующих типов: `Circle`, `Diamond`, `Pentagon`, `PushPin`, `Rectangle`, `Star`, `Triangle`, `Trapezoid` и `Wedge`.</span><span class="sxs-lookup"><span data-stu-id="2a57e-174">Marker types include `Circle`, `Diamond`, `Pentagon`, `PushPin`, `Rectangle`, `Star`, `Triangle`, `Trapezoid`, and `Wedge`.</span></span>  
  
##  <a name="understanding-distribution-options"></a><a name="Distribution"></a> <span data-ttu-id="2a57e-175">Основные сведения о параметрах распределения</span><span class="sxs-lookup"><span data-stu-id="2a57e-175">Understanding Distribution Options</span></span>  
 <span data-ttu-id="2a57e-176">Чтобы создать распределение значений, данные разбиваются на диапазоны.</span><span class="sxs-lookup"><span data-stu-id="2a57e-176">To create a distribution of values, you can divide your data into ranges.</span></span> <span data-ttu-id="2a57e-177">Указывается тип распределения, число поддиапазонов, а также минимальные и максимальные значения диапазонов.</span><span class="sxs-lookup"><span data-stu-id="2a57e-177">You specify the distribution type, the number of subranges, and the minimum and maximum range values.</span></span>  
  
 <span data-ttu-id="2a57e-178">В следующем списке предполагается, что имеется три элемента карты и шесть связанных с ними аналитических значений в диапазоне от 1 до 9 999 со следующими значениями: 1, 10, 200, 2000, 4777, 8999.</span><span class="sxs-lookup"><span data-stu-id="2a57e-178">In the following list, assume that you have three map elements and six related analytical values that range from 1 to 9999 with the following values: 1, 10, 200, 2000, 4777, 8999.</span></span>  
  
-   <span data-ttu-id="2a57e-179">**Равноинтервальный.**</span><span class="sxs-lookup"><span data-stu-id="2a57e-179">**EqualInterval.**</span></span> <span data-ttu-id="2a57e-180">Создаются диапазоны, которые разбивают данные на равные интервалы.</span><span class="sxs-lookup"><span data-stu-id="2a57e-180">Create ranges that divide the data into equal range intervals.</span></span> <span data-ttu-id="2a57e-181">Например, три диапазона будут иметь границы 0-2999, 3000-5999, 6000-8999.</span><span class="sxs-lookup"><span data-stu-id="2a57e-181">For the example, the three ranges would be 0-2999, 3000-5999, 6000-8999.</span></span> <span data-ttu-id="2a57e-182">Поддиапазон 1: 1, 10, 200, 500.</span><span class="sxs-lookup"><span data-stu-id="2a57e-182">Subrange 1: 1, 10, 200, 500.</span></span> <span data-ttu-id="2a57e-183">Поддиапазон 2: 4777.</span><span class="sxs-lookup"><span data-stu-id="2a57e-183">Subrange 2: 4777.</span></span> <span data-ttu-id="2a57e-184">Поддиапазон 3: 8999.</span><span class="sxs-lookup"><span data-stu-id="2a57e-184">Subrange 3: 8999.</span></span> <span data-ttu-id="2a57e-185">Этот метод не учитывает распределение данных.</span><span class="sxs-lookup"><span data-stu-id="2a57e-185">This method does not take into account how the data is distributed.</span></span> <span data-ttu-id="2a57e-186">Очень большие или очень маленькие значения могут исказить результаты распределения.</span><span class="sxs-lookup"><span data-stu-id="2a57e-186">Very large values or very small values can skew the distribution results.</span></span>  
  
-   <span data-ttu-id="2a57e-187">**Равнораспределенный.**</span><span class="sxs-lookup"><span data-stu-id="2a57e-187">**EqualDistribution.**</span></span> <span data-ttu-id="2a57e-188">Порождаются диапазоны, которые делят данные так, что каждый диапазон содержит равное число элементов.</span><span class="sxs-lookup"><span data-stu-id="2a57e-188">Create ranges that divide that data so that each range has an equal number of items.</span></span> <span data-ttu-id="2a57e-189">Для данных в приведенном примере три диапазона будут иметь границы 0-10, 11-500, 501-8999.</span><span class="sxs-lookup"><span data-stu-id="2a57e-189">For the example data, the three ranges would be 0-10, 11-500, 501-8999.</span></span> <span data-ttu-id="2a57e-190">Поддиапазон 1: 1, 10.</span><span class="sxs-lookup"><span data-stu-id="2a57e-190">Subrange 1: 1, 10.</span></span> <span data-ttu-id="2a57e-191">Поддиапазон 2: 200, 500.</span><span class="sxs-lookup"><span data-stu-id="2a57e-191">Subrange 2: 200, 500.</span></span> <span data-ttu-id="2a57e-192">Поддиапазон 3: 4777, 8999.</span><span class="sxs-lookup"><span data-stu-id="2a57e-192">Subrange 3: 4777, 8999.</span></span> <span data-ttu-id="2a57e-193">Этот метод может исказить распределение за счет порождения очень крупных или очень малых диапазонов.</span><span class="sxs-lookup"><span data-stu-id="2a57e-193">This method can skew the distribution by creating divisions that span very large or very small ranges.</span></span>  
  
-   <span data-ttu-id="2a57e-194">**Оптимальный.**</span><span class="sxs-lookup"><span data-stu-id="2a57e-194">**Optimal.**</span></span> <span data-ttu-id="2a57e-195">Порождается распределение с автоматически сбалансированными поддиапазонами.</span><span class="sxs-lookup"><span data-stu-id="2a57e-195">Create ranges that automatically adjust distribution to create balanced subranges.</span></span> <span data-ttu-id="2a57e-196">Количество поддиапазонов определяется алгоритмом.</span><span class="sxs-lookup"><span data-stu-id="2a57e-196">The number of subranges is determined by the algorithm.</span></span>  
  
-   <span data-ttu-id="2a57e-197">**Пользовательский.**</span><span class="sxs-lookup"><span data-stu-id="2a57e-197">**Custom.**</span></span> <span data-ttu-id="2a57e-198">Укажите собственное количество диапазонов для управления распределением значений.</span><span class="sxs-lookup"><span data-stu-id="2a57e-198">Specify your own number of ranges to control the distribution of values.</span></span> <span data-ttu-id="2a57e-199">Для приведенных в примере данных можно задать три диапазона: 1–2, 3–8, 9.</span><span class="sxs-lookup"><span data-stu-id="2a57e-199">For the example data, you can specify ranges 3 ranges: 1-2, 3-8, 9.</span></span>  
  
 <span data-ttu-id="2a57e-200">Значения распределения используются правилами для изменения параметров отображения элементов карты.</span><span class="sxs-lookup"><span data-stu-id="2a57e-200">The distribution values are used by the rules to vary the map element display values.</span></span>  
  
##  <a name="understanding-legends-and-legend-items"></a><a name="Legends"></a> <span data-ttu-id="2a57e-201">Основные сведения об условных обозначениях и элементах условных обозначений</span><span class="sxs-lookup"><span data-stu-id="2a57e-201">Understanding Legends and Legend Items</span></span>  
 <span data-ttu-id="2a57e-202">Элементы условных обозначений автоматически создаются на основе правил, указанных для каждого слоя.</span><span class="sxs-lookup"><span data-stu-id="2a57e-202">Legend items are created automatically from the rules that you specify for each layer.</span></span> <span data-ttu-id="2a57e-203">Параметры правил определяют, сколько элементов создается и в каких условных обозначениях они отображаются.</span><span class="sxs-lookup"><span data-stu-id="2a57e-203">Rule options control how many items are created and which legend they appear in.</span></span> <span data-ttu-id="2a57e-204">По умолчанию все правила добавляются в первые условные обозначения.</span><span class="sxs-lookup"><span data-stu-id="2a57e-204">By default, all items for all rules are added to the first legend.</span></span> <span data-ttu-id="2a57e-205">Чтобы переместить элементы из первых условных обозначений, можно создать необходимое количество дополнительных условных обозначений и указать для каждого правила условные обозначения, которые должны отображать элементы, порождаемые этим правилом.</span><span class="sxs-lookup"><span data-stu-id="2a57e-205">To move items out of the first legend, create as many additional legends as you need, and for each rule, specify the legend to use to display the items that result from the rule.</span></span> <span data-ttu-id="2a57e-206">Чтобы скрыть элементы, основанные на правиле, укажите пустое имя условных обозначений.</span><span class="sxs-lookup"><span data-stu-id="2a57e-206">To hide items based on a rule, specify a blank legend name.</span></span>  
  
 <span data-ttu-id="2a57e-207">Для управления местом отображения условных обозначений используйте диалоговое окно «Свойства условных обозначений», которое позволяет указать положение условных обозначений относительно окна просмотра карты.</span><span class="sxs-lookup"><span data-stu-id="2a57e-207">To control where a legend appears, use the Legend Properties dialog box to specify a position relative to the map viewport.</span></span> <span data-ttu-id="2a57e-208">Дополнительные сведения см. в разделе [Изменение условных обозначений карты, цветовой шкалы и связанных правил (построитель отчетов и службы SSRS)](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2a57e-208">For more information, see [Change Map Legends, Color Scale, and Associated Rules &#40;Report Builder and SSRS&#41;](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="2a57e-209">Условные обозначения автоматически расширяются, чтобы отобразить заголовок или текст условных обозначений.</span><span class="sxs-lookup"><span data-stu-id="2a57e-209">Legends automatically expand to display the legend title or legend text.</span></span> <span data-ttu-id="2a57e-210">Чтобы форматировать текст элементов условных обозначений, используйте ключевые слова для условных обозначений карты и пользовательские форматы.</span><span class="sxs-lookup"><span data-stu-id="2a57e-210">To format the text of legend items, use map legend keywords and custom formats.</span></span> <span data-ttu-id="2a57e-211">Дополнительные сведения см. в разделе [Изменение условных обозначений карты, цветовой шкалы и связанных правил (построитель отчетов и службы SSRS)](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2a57e-211">For more information, see [Change Map Legends, Color Scale, and Associated Rules &#40;Report Builder and SSRS&#41;](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="2a57e-212">В следующей таблице показаны примеры различных доступных форматов.</span><span class="sxs-lookup"><span data-stu-id="2a57e-212">The following tables shows examples of different formats that you can use.</span></span>  
  
|<span data-ttu-id="2a57e-213">Ключевое слово и формат</span><span class="sxs-lookup"><span data-stu-id="2a57e-213">Keyword and Format</span></span>|<span data-ttu-id="2a57e-214">Description</span><span class="sxs-lookup"><span data-stu-id="2a57e-214">Description</span></span>|<span data-ttu-id="2a57e-215">Пример отображения текста в условных обозначениях</span><span class="sxs-lookup"><span data-stu-id="2a57e-215">Example of what appears as text in the legend</span></span>|  
|------------------------|-----------------|---------------------------------------------------|  
|`#FROMVALUE {C0}`|<span data-ttu-id="2a57e-216">Отображает итоговое значение в формате валюты без десятичных разрядов</span><span class="sxs-lookup"><span data-stu-id="2a57e-216">Displays the currency of the total value with no decimal places</span></span>|<span data-ttu-id="2a57e-217">$400</span><span class="sxs-lookup"><span data-stu-id="2a57e-217">$400</span></span>|  
|`#FROMVALUE {C2}`|<span data-ttu-id="2a57e-218">Отображает итоговое значение в формате валюты с двумя десятичными разрядами.</span><span class="sxs-lookup"><span data-stu-id="2a57e-218">Displays the currency of the total value to two decimal places.</span></span>|<span data-ttu-id="2a57e-219">$400,55</span><span class="sxs-lookup"><span data-stu-id="2a57e-219">$400.55</span></span>|  
|`#TOVALUE`|<span data-ttu-id="2a57e-220">Отображает действительное числовое значение поля данных.</span><span class="sxs-lookup"><span data-stu-id="2a57e-220">Displays the actual numeric value of the data field.</span></span>|<span data-ttu-id="2a57e-221">10000</span><span class="sxs-lookup"><span data-stu-id="2a57e-221">10000</span></span>|  
|`#FROMVALUE{N0} - #TOVALUE{N0}`|<span data-ttu-id="2a57e-222">Отображает текущее числовое значение начала и конца диапазона.</span><span class="sxs-lookup"><span data-stu-id="2a57e-222">Displays the actual numeric values of the beginning of the range and end of the range.</span></span>|<span data-ttu-id="2a57e-223">10–790</span><span class="sxs-lookup"><span data-stu-id="2a57e-223">10 - 790</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a57e-224">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a57e-224">See Also</span></span>  
 <span data-ttu-id="2a57e-225">[Изменение условных обозначений карты, цветовой шкалы и связанных правил (построитель отчетов и службы SSRS)](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2a57e-225">[Change Map Legends, Color Scale, and Associated Rules &#40;Report Builder and SSRS&#41;](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2a57e-226">[Карты (построитель отчетов и службы SSRS)](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2a57e-226">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2a57e-227">Мастер карт и мастер слоев карт (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="2a57e-227">Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;</span></span>](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md)  
  
  