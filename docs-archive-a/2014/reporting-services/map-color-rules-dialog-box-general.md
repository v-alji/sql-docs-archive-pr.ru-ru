---
title: Диалоговое окно «Правила цвета карт», «общие» | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10541"
- sql12.rtp.rptdesigner.shared.mapcolorrulesgeneral.f1
ms.assetid: 14ff5fc1-4cf8-4a45-9d98-47a1bf1c52c4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0dffc6c0b31400cb4eb9cecbbada1a52f8f41443
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668086"
---
# <a name="map-color-rules-dialog-box-general"></a><span data-ttu-id="89f6c-102">Диалоговое окно «Правила цвета карты» — «Общие»</span><span class="sxs-lookup"><span data-stu-id="89f6c-102">Map Color Rules Dialog Box, General</span></span>
  <span data-ttu-id="89f6c-103">Перейдите на страницу **Общие** в диалоговом окне **Свойства правил цвета** , чтобы определить параметры цвета для элементов карты на данном слое.</span><span class="sxs-lookup"><span data-stu-id="89f6c-103">Select **General** on the **Color Rules Properties** dialog box to define color options for map elements on this layer.</span></span> <span data-ttu-id="89f6c-104">Элементы карты включают многоугольники, линии и точки.</span><span class="sxs-lookup"><span data-stu-id="89f6c-104">Map elements include polygons, lines, and points.</span></span> <span data-ttu-id="89f6c-105">Правила цвета можно применить, если создана связь между элементами карты на основе пространственных и аналитических данных из поля набора данных либо из поля источника пространственных данных.</span><span class="sxs-lookup"><span data-stu-id="89f6c-105">Color rules can be applied when you have created a relationship between map elements based on spatial data and analytical data from a dataset field or from a spatial data source field.</span></span>  
  
 <span data-ttu-id="89f6c-106">Чтобы отобразить все элементы карты на слое при помощи цветного градиента с разными первичными и вторичными цветами, используйте страницу **Заливка** диалогового окна «Свойства многоугольников карты».</span><span class="sxs-lookup"><span data-stu-id="89f6c-106">To display all map elements on a layer by specifying a decorative gradient with different primary and secondary colors, use the **Fill** page of the Map Polygon Properties Dialog Box.</span></span> <span data-ttu-id="89f6c-107">Правила цвета имеют приоритет над свойствами отображения для слоя.</span><span class="sxs-lookup"><span data-stu-id="89f6c-107">Color rules take precedence over display properties for a layer.</span></span> <span data-ttu-id="89f6c-108">Дополнительные сведения см. в разделе [Настройка данных и отображения карты или слоя карты (построитель отчетов и службы SSRS)](report-design/customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="89f6c-108">For more information, see [Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](report-design/customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="89f6c-109">Варианты</span><span class="sxs-lookup"><span data-stu-id="89f6c-109">Options</span></span>  
 <span data-ttu-id="89f6c-110">**Применить стиль шаблона**</span><span class="sxs-lookup"><span data-stu-id="89f6c-110">**Apply template style**</span></span>  
 <span data-ttu-id="89f6c-111">Выберите этот параметр, чтобы использовать цвета на основе темы, выбранной в мастере или заданной в свойствах слоя «Многоугольник», «Линия» или «Точка».</span><span class="sxs-lookup"><span data-stu-id="89f6c-111">Select this option to use color based on the theme that was chosen in the wizard or set in the Polygon, Line, or Point layer properties.</span></span> <span data-ttu-id="89f6c-112">Тема задает параметры по умолчанию для цвета, шрифта и границ для карты.</span><span class="sxs-lookup"><span data-stu-id="89f6c-112">A theme sets default options for color, font, and borders for the map.</span></span> <span data-ttu-id="89f6c-113">Для данного параметра правила назначения цветов каждому элементу карты не используются.</span><span class="sxs-lookup"><span data-stu-id="89f6c-113">For this option, no rule is applied to assign colors to each map element.</span></span>  
  
 <span data-ttu-id="89f6c-114">**Отобразить данные при помощи палитры цветов**</span><span class="sxs-lookup"><span data-stu-id="89f6c-114">**Visualize data by using color palette**</span></span>  
 <span data-ttu-id="89f6c-115">Выберите данный параметр, чтобы отображать аналитические данные при помощи цветов из определенной палитры цветов.</span><span class="sxs-lookup"><span data-stu-id="89f6c-115">Select this option to visualize analytical data by using colors from a specific color palette.</span></span>  
  
 <span data-ttu-id="89f6c-116">**Отобразить данные при помощи диапазонов цвета**</span><span class="sxs-lookup"><span data-stu-id="89f6c-116">**Visualize data by using color ranges**</span></span>  
 <span data-ttu-id="89f6c-117">Выберите данный параметр, чтобы отображать аналитические данные при помощи диапазона цветов для каждого элемента карты.</span><span class="sxs-lookup"><span data-stu-id="89f6c-117">Select this option to visualize analytical data by using a range of colors for each map element.</span></span> <span data-ttu-id="89f6c-118">Например, если установить «Красный» в качестве исходного цвета, «Желтый» в качестве промежуточного и «Зеленый» в качестве конечного цвета, значения в нижнем диапазоне будут красными, в середине — желтыми и в верхнем диапазоне — зелеными.</span><span class="sxs-lookup"><span data-stu-id="89f6c-118">For example, when you specify Red as a start color, Yellow as a middle color, and Green as an end color, values in the low range are Red, values in the middle range are Yellow, and values in the top range are Green.</span></span>  
  
 <span data-ttu-id="89f6c-119">**Отобразить данные при помощи пользовательских цветов**</span><span class="sxs-lookup"><span data-stu-id="89f6c-119">**Visualize data by using custom colors**</span></span>  
 <span data-ttu-id="89f6c-120">Выберите данный параметр, чтобы отображать аналитические данные при помощи определенного списка цветов.</span><span class="sxs-lookup"><span data-stu-id="89f6c-120">Select this option to visualize analytical data by specifying your own list of colors.</span></span>  
  
 <span data-ttu-id="89f6c-121">**Поле данных**</span><span class="sxs-lookup"><span data-stu-id="89f6c-121">**Data field**</span></span>  
 <span data-ttu-id="89f6c-122">Данный параметр доступен при выборе одного из параметров **Отобразить данные** .</span><span class="sxs-lookup"><span data-stu-id="89f6c-122">This option appears when you select one of the **Visualize data** options.</span></span>  
  
 <span data-ttu-id="89f6c-123">В раскрывающемся списке выберите нужное поле аналитических данных.</span><span class="sxs-lookup"><span data-stu-id="89f6c-123">Select the analytical data field to use from the drop-down list.</span></span> <span data-ttu-id="89f6c-124">В зависимости от источника пространственных данных список отображает поля из источника пространственных данных и из набора данных отчета, который имеет связь между пространственными и аналитическими данными.</span><span class="sxs-lookup"><span data-stu-id="89f6c-124">Depending on the source of spatial data, the list displays fields from the spatial data source and from a report dataset that has a relationship between the spatial data and analytical data.</span></span> <span data-ttu-id="89f6c-125">Чтобы создать такую связь, задайте параметры данных на странице «Аналитические данные» для выбранного слоя карты.</span><span class="sxs-lookup"><span data-stu-id="89f6c-125">To create such a relationship, set the data options on the Analytical Data page for the selected map layer.</span></span>  
  
 <span data-ttu-id="89f6c-126">**Задания**</span><span class="sxs-lookup"><span data-stu-id="89f6c-126">**Palette**</span></span>  
 <span data-ttu-id="89f6c-127">Введите или выберите имя палитры цветов.</span><span class="sxs-lookup"><span data-stu-id="89f6c-127">Type or select the name of the color palette.</span></span>  
  
 <span data-ttu-id="89f6c-128">**Исходный цвет**</span><span class="sxs-lookup"><span data-stu-id="89f6c-128">**Start color**</span></span>  
 <span data-ttu-id="89f6c-129">Укажите цвет, который будет использоваться для данных в нижней области диапазона данных.</span><span class="sxs-lookup"><span data-stu-id="89f6c-129">Specify the color to use for data at the low end of the data range.</span></span>  
  
 <span data-ttu-id="89f6c-130">**Промежуточный цвет**</span><span class="sxs-lookup"><span data-stu-id="89f6c-130">**Middle color**</span></span>  
 <span data-ttu-id="89f6c-131">Укажите цвет, который будет использоваться для данных в средней области диапазона данных.</span><span class="sxs-lookup"><span data-stu-id="89f6c-131">Specify the color to use for data in the middle of the data range.</span></span> <span data-ttu-id="89f6c-132">Выберите **Без цвета** , чтобы удалить данный диапазон.</span><span class="sxs-lookup"><span data-stu-id="89f6c-132">Select **No Color** to remove this range.</span></span>  
  
 <span data-ttu-id="89f6c-133">**Конечный цвет**</span><span class="sxs-lookup"><span data-stu-id="89f6c-133">**End color**</span></span>  
 <span data-ttu-id="89f6c-134">Укажите цвет, который будет использоваться для данных в верхней области диапазона данных.</span><span class="sxs-lookup"><span data-stu-id="89f6c-134">Specify the color to use for data at the high end of the data range.</span></span>  
  
 <span data-ttu-id="89f6c-135">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="89f6c-135">**Add**</span></span>  
 <span data-ttu-id="89f6c-136">Нажмите кнопку **Добавить** , чтобы добавить цвета для правила цвета.</span><span class="sxs-lookup"><span data-stu-id="89f6c-136">Click **Add** to specify your own colors for the color rule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f6c-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="89f6c-137">See Also</span></span>  
 <span data-ttu-id="89f6c-138">[Карты (построитель отчетов и службы SSRS)](report-design/maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="89f6c-138">[Maps &#40;Report Builder and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="89f6c-139">Изменение условных обозначений карты, цветовой шкалы и связанных правил (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="89f6c-139">Change Map Legends, Color Scale, and Associated Rules &#40;Report Builder and SSRS&#41;</span></span>](report-design/change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md)  
  
  
