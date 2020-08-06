---
title: Диалоговое окно "Свойства окна просмотра карт" — "Общие" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.general.f1
- "10505"
ms.assetid: 6c9c773e-5c56-4571-95ed-8a157cfdfe52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d760d6a0572cbbd1bd948eab382c0727eb276c4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654896"
---
# <a name="map-viewport-properties-dialog-box-general"></a><span data-ttu-id="4bcbe-102">Диалоговое окно «Свойства окна просмотра карты», вкладка «Общие»</span><span class="sxs-lookup"><span data-stu-id="4bcbe-102">Map Viewport Properties Dialog Box, General</span></span>
  <span data-ttu-id="4bcbe-103">Перейдите на вкладку **Общие** диалогового окна **Свойства окна просмотра карты** , чтобы изменить параметры системы координат, проекции и границ.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-103">Select **General** on the **Map Viewport Properties** dialog box to change the coordinate system, the projection, and the boundary options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4bcbe-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="4bcbe-104">Options</span></span>  
 <span data-ttu-id="4bcbe-105">**Система координат**</span><span class="sxs-lookup"><span data-stu-id="4bcbe-105">**Coordinate system**</span></span>  
 <span data-ttu-id="4bcbe-106">Укажите тип координат, в которых заданы данные карты.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-106">Indicate the type of coordinate system that the map data uses.</span></span>  
  
-   <span data-ttu-id="4bcbe-107">**Планарные** Выберите этот параметр, если данные карты заданы в координатах X и Y (например, в планах построек).</span><span class="sxs-lookup"><span data-stu-id="4bcbe-107">**Planar** Choose this option when map data is in X and Y coordinates, for example, for building plans.</span></span>  
  
-   <span data-ttu-id="4bcbe-108">**Географические** Выберите этот параметр, если данные карты заданы широтой и долготой (например положения городов).</span><span class="sxs-lookup"><span data-stu-id="4bcbe-108">**Geographic** Choose this option when map data is in longitude and latitude coordinates, for example, for city locations.</span></span>  
  
 <span data-ttu-id="4bcbe-109">**Проекция**</span><span class="sxs-lookup"><span data-stu-id="4bcbe-109">**Projection**</span></span>  
 <span data-ttu-id="4bcbe-110">Укажите метод проецирования географических координат на плоскую поверхность.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-110">Specify the method to use to project geographic coordinates onto a two-dimensional surface.</span></span> <span data-ttu-id="4bcbe-111">Выберите проекцию, совместимую с визуализируемыми данными.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-111">Choose a projection that is compatible with the data that you are visualizing.</span></span> <span data-ttu-id="4bcbe-112">Проекция оказывает влияние на четыре пространственных свойства: площадь, форму, расстояние и направление.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-112">The four spatial properties that are affected by projection are area, shape, distance, and direction.</span></span> <span data-ttu-id="4bcbe-113">Выбор проекции для представления земной поверхности определяется центром представления, границами карты и масштабом.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-113">For views of the earth, a good choice of projection depends on the center view, the map boundaries, and the zoom factor.</span></span>  
  
 <span data-ttu-id="4bcbe-114">Каждая из следующих проекций не изменяет одно или несколько пространственных свойств.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-114">Each of the following projections preserves one or more of these spatial properties:</span></span>  
  
-   <span data-ttu-id="4bcbe-115">**Равнопрямоугольная** Выберите этот параметр, чтобы использовать значения широты и долготы в качестве прямоугольных координат.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-115">**Equirectangular** Choose this option to use longitude and latitude as rectangular coordinates.</span></span>  
  
-   <span data-ttu-id="4bcbe-116">**Меркатор** Эта популярная проекция пригодна для небольших участков, для уменьшения искажений в районе экватора или при добавлении слоя карты к существующему мозаичному слою, использующему проекцию Меркатора.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-116">**Mercator** Choose this popular projection for smaller areas, for less distortion around the equator, or when you want to add a map layer with an existing tile layer that uses the Mercator projection.</span></span>  
  
-   <span data-ttu-id="4bcbe-117">**Робинсон** Выберите этот параметр, чтобы уменьшить искажения больших областей, простирающихся от экватора к полюсам.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-117">**Robinson** Choose this option for less distortion of large areas that span from the equator to the poles.</span></span> <span data-ttu-id="4bcbe-118">Разработана Артуром Робинсоном в 1963 г.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-118">Developed by Arthur H. Robinson in 1963.</span></span>  
  
-   <span data-ttu-id="4bcbe-119">**Фэйи** Выберите этот параметр, чтобы уменьшить искажения больших областей, простирающихся от экватора к полюсам.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-119">**Fahey** Choose this option for less distortion of large areas that span from the equator to the poles.</span></span> <span data-ttu-id="4bcbe-120">Разработана Лоуренсом Фэйи в 1975 г.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-120">Developed by Lawrence Fahey in 1975.</span></span>  
  
-   <span data-ttu-id="4bcbe-121">**Эккерт1** Выберите этот параметр, чтобы использовать параллели, равноудаленые по широте, а меридианы будут представлены прямыми линиями.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-121">**Eckert1** Choose this option to use equally spaced parallels in latitude and straight lines for meridians in longitude.</span></span>  
  
-   <span data-ttu-id="4bcbe-122">**Эккерт3** Выберите этот параметр, чтобы использовать параллели, равноудаленные по широте, а меридианы будут представлены изогнутыми линиями.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-122">**Eckert3** Choose this option to use equally spaced parallels in latitude and curved lines for meridians in longitude.</span></span>  
  
-   <span data-ttu-id="4bcbe-123">**Хаммер-Айтофф** Эта проекция используется для схем в полярных координатах и карт мира.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-123">**HammerAitoff** Choose this option for polar maps or world maps.</span></span>  
  
-   <span data-ttu-id="4bcbe-124">**Вагнер3** Эта проекция используется для карт мира.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-124">**Wagner3** Choose this option for world maps.</span></span>  
  
-   <span data-ttu-id="4bcbe-125">**Бонн** Выберите этот параметр, чтобы отображать мир, как в атласе.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-125">**Bonne** Choose this option to view the world as it appears in an atlas.</span></span>  
  
 <span data-ttu-id="4bcbe-126">**Параметры разрыва страниц**</span><span class="sxs-lookup"><span data-stu-id="4bcbe-126">**Page break options**</span></span>  
 <span data-ttu-id="4bcbe-127">Выберите необходимые параметры, чтобы указать, как размещается содержимое на странице отчета.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-127">Select options to indicate how content is fitted to a report page.</span></span>  
  
 <span data-ttu-id="4bcbe-128">**Параметры границ**</span><span class="sxs-lookup"><span data-stu-id="4bcbe-128">**Boundary options**</span></span>  
 <span data-ttu-id="4bcbe-129">Укажите нижнюю и верхнюю границы значений координат, определяющих, какая часть карты будет отображена в отчете.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-129">Specify the lower and upper boundaries for coordinates to control which part of the map appears in the report.</span></span>  
  
 <span data-ttu-id="4bcbe-130">**Минимальное значение X**</span><span class="sxs-lookup"><span data-stu-id="4bcbe-130">**Minimum X**</span></span>  
 <span data-ttu-id="4bcbe-131">Наименьшее значение X.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-131">Lowest X value.</span></span> <span data-ttu-id="4bcbe-132">Доступно только для типа координат **Планарные** .</span><span class="sxs-lookup"><span data-stu-id="4bcbe-132">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="4bcbe-133">**Максимальное значение X**</span><span class="sxs-lookup"><span data-stu-id="4bcbe-133">**Maximum X**</span></span>  
 <span data-ttu-id="4bcbe-134">Наибольшее значение X.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-134">Highest X value.</span></span> <span data-ttu-id="4bcbe-135">Доступно только для типа координат **Планарные** .</span><span class="sxs-lookup"><span data-stu-id="4bcbe-135">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="4bcbe-136">**Минимальное значение Y**</span><span class="sxs-lookup"><span data-stu-id="4bcbe-136">**Minimum Y**</span></span>  
 <span data-ttu-id="4bcbe-137">Наименьшее значение Y.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-137">Lowest Y value.</span></span> <span data-ttu-id="4bcbe-138">Доступно только для типа координат **Планарные** .</span><span class="sxs-lookup"><span data-stu-id="4bcbe-138">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="4bcbe-139">**Максимальное значение Y**</span><span class="sxs-lookup"><span data-stu-id="4bcbe-139">**Maximum Y**</span></span>  
 <span data-ttu-id="4bcbe-140">Наибольшее значение Y.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-140">Highest Y value.</span></span> <span data-ttu-id="4bcbe-141">Доступно только для типа координат **Планарные** .</span><span class="sxs-lookup"><span data-stu-id="4bcbe-141">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="4bcbe-142">**Минимальная долгота**</span><span class="sxs-lookup"><span data-stu-id="4bcbe-142">**Minimum Longitude**</span></span>  
 <span data-ttu-id="4bcbe-143">Наименьшее значение долготы.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-143">Lowest longitude value.</span></span> <span data-ttu-id="4bcbe-144">Доступно только для типа координат **Географические** .</span><span class="sxs-lookup"><span data-stu-id="4bcbe-144">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="4bcbe-145">**Максимальная долгота**</span><span class="sxs-lookup"><span data-stu-id="4bcbe-145">**Maximum Longitude**</span></span>  
 <span data-ttu-id="4bcbe-146">Наибольшее значение долготы.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-146">Highest longitude value.</span></span> <span data-ttu-id="4bcbe-147">Доступно только для типа координат **Географические** .</span><span class="sxs-lookup"><span data-stu-id="4bcbe-147">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="4bcbe-148">**Минимальная широта**</span><span class="sxs-lookup"><span data-stu-id="4bcbe-148">**Minimum Latitude**</span></span>  
 <span data-ttu-id="4bcbe-149">Наименьшее значение широты.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-149">Lowest latitude value.</span></span> <span data-ttu-id="4bcbe-150">Доступно только для типа координат **Географические** .</span><span class="sxs-lookup"><span data-stu-id="4bcbe-150">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="4bcbe-151">**Максимальная широта**</span><span class="sxs-lookup"><span data-stu-id="4bcbe-151">**Maximum Latitude**</span></span>  
 <span data-ttu-id="4bcbe-152">Наибольшее значение широты.</span><span class="sxs-lookup"><span data-stu-id="4bcbe-152">Highest latitude value.</span></span> <span data-ttu-id="4bcbe-153">Доступно только для типа координат **Географические** .</span><span class="sxs-lookup"><span data-stu-id="4bcbe-153">Available for **Geographic** only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bcbe-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="4bcbe-154">See Also</span></span>  
 [<span data-ttu-id="4bcbe-155">Карты (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4bcbe-155">Maps &#40;Report Builder and SSRS&#41;</span></span>](report-design/maps-report-builder-and-ssrs.md)  
  
  
