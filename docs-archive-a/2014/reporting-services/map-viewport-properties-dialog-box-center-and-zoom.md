---
title: Диалоговое окно "Свойства окна просмотра карт", центр и масштаб | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.centerandzoom.f1
- "10506"
ms.assetid: 642a06f5-293f-48e0-97a6-1489dbefa719
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 913c00773abf71ca627b8cc2a94a873484e8ab30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657568"
---
# <a name="map-viewport-properties-dialog-box-center-and-zoom"></a><span data-ttu-id="592e5-102">Диалоговое окно «Свойства окна просмотра карты», вкладка «Центрирование и масштабирование»</span><span class="sxs-lookup"><span data-stu-id="592e5-102">Map Viewport Properties Dialog Box, Center and Zoom</span></span>
  <span data-ttu-id="592e5-103">Вкладка **Центрирование и масштабирование** диалогового окна **Свойства окна просмотра карты** позволяет задать центральную точку и масштаб карты.</span><span class="sxs-lookup"><span data-stu-id="592e5-103">Select **Center and Zoom** for the **Map Viewport Properties** dialog box to set the center view and zoom factor for a map.</span></span> <span data-ttu-id="592e5-104">После указания источника данных и границ карты, включаемой в отчет, можно указать центр представления и масштаб карты для дальнейшего управления ее внешним видом.</span><span class="sxs-lookup"><span data-stu-id="592e5-104">After you specify a map data source and the boundaries of the map that you want to include in your report, you can specify the view center and the zoom factor to further control the map display.</span></span> <span data-ttu-id="592e5-105">Изменение параметров зависит от способа, используемого для указания значений центральной точки и масштаба.</span><span class="sxs-lookup"><span data-stu-id="592e5-105">Options change depending on which method you use to specify the center and zoom values.</span></span> <span data-ttu-id="592e5-106">Нажмите кнопку **Выражение** (*fx*), чтобы изменить выражение, задающее значение параметра.</span><span class="sxs-lookup"><span data-stu-id="592e5-106">Click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
## <a name="options"></a><span data-ttu-id="592e5-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="592e5-107">Options</span></span>  
 <span data-ttu-id="592e5-108">**Задать центр представления и масштаб**</span><span class="sxs-lookup"><span data-stu-id="592e5-108">**Set a view center and zoom level**</span></span>  
 <span data-ttu-id="592e5-109">Выберите этот параметр, чтобы указать пользовательские значения для центра представления и масштаба.</span><span class="sxs-lookup"><span data-stu-id="592e5-109">Choose this option to specify custom values for the view center and the zoom level.</span></span>  
  
 <span data-ttu-id="592e5-110">**Центрировать карту для показа слоя карты**</span><span class="sxs-lookup"><span data-stu-id="592e5-110">**Center map to show a map layer**</span></span>  
 <span data-ttu-id="592e5-111">Выберите этот параметр, чтобы указать слой и автоматически центрировать представление на данных карты.</span><span class="sxs-lookup"><span data-stu-id="592e5-111">Choose this option to specify a layer and automatically center the view on its map data.</span></span> <span data-ttu-id="592e5-112">Например, можно центрировать представление слоя LineLayer1.</span><span class="sxs-lookup"><span data-stu-id="592e5-112">For example, center the view on LineLayer1.</span></span>  
  
 <span data-ttu-id="592e5-113">**Центрировать карту для показа внедренного элемента карты**</span><span class="sxs-lookup"><span data-stu-id="592e5-113">**Center map to show an embedded map element**</span></span>  
 <span data-ttu-id="592e5-114">Выберите этот параметр, чтобы центрировать представление определенного элемента карты, привязанного к данным.</span><span class="sxs-lookup"><span data-stu-id="592e5-114">Choose this option to center the view on a specific data-bound map element.</span></span> <span data-ttu-id="592e5-115">Чтобы выбрать этот параметр, должна быть задана связь между пространственными и аналитическими данными.</span><span class="sxs-lookup"><span data-stu-id="592e5-115">The spatial data must have a relationship with analytical data to specify this option.</span></span>  
  
 <span data-ttu-id="592e5-116">Например, можно центрировать представление элемента карты с именем поля сопоставления [City] и значением сопоставления «Seattle».</span><span class="sxs-lookup"><span data-stu-id="592e5-116">For example, center the view on the map element where the name of the match field is [City] and the match value is "Seattle".</span></span>  
  
 <span data-ttu-id="592e5-117">**Центрировать карту для показа всех элементов карты, привязанных к данным**</span><span class="sxs-lookup"><span data-stu-id="592e5-117">**Center map to show all data-bound map elements**</span></span>  
 <span data-ttu-id="592e5-118">Выберите этот параметр, чтобы центрировать представление всех элементов слоя карты.</span><span class="sxs-lookup"><span data-stu-id="592e5-118">Choose this option to center the view on all map elements in the layer.</span></span> <span data-ttu-id="592e5-119">Чтобы выбрать этот параметр, должна быть задана связь между пространственными и аналитическими данными.</span><span class="sxs-lookup"><span data-stu-id="592e5-119">The spatial data must have a relationship with analytical data to specify this option.</span></span>  
  
 <span data-ttu-id="592e5-120">Например, можно центрировать представление многоугольного слоя пузырьков, который отображает города, причем размер пузырьков связан с их населением.</span><span class="sxs-lookup"><span data-stu-id="592e5-120">For example, center the view on the polygon bubble layer that shows cities and the bubble size is related to population.</span></span> <span data-ttu-id="592e5-121">При вычислении центра области просмотра учитываются только города с совпадающей численностью населения.</span><span class="sxs-lookup"><span data-stu-id="592e5-121">Only those cities with a matching population value are included when calculating the center for the viewport.</span></span>  
  
 <span data-ttu-id="592e5-122">**Параметры центрирования и масштабирования**</span><span class="sxs-lookup"><span data-stu-id="592e5-122">**Center and zoom options**</span></span>  
 <span data-ttu-id="592e5-123">Выберите параметр указания центра представления и масштаба.</span><span class="sxs-lookup"><span data-stu-id="592e5-123">Select an option to specify the view center and zoom level.</span></span>  
  
 <span data-ttu-id="592e5-124">**Центр представления (X) %**</span><span class="sxs-lookup"><span data-stu-id="592e5-124">**View center (X) %**</span></span>  
 <span data-ttu-id="592e5-125">Горизонтальная координата.</span><span class="sxs-lookup"><span data-stu-id="592e5-125">The horizontal coordinate.</span></span> <span data-ttu-id="592e5-126">Значение по умолчанию (50 %)</span><span class="sxs-lookup"><span data-stu-id="592e5-126">The default value, 50%.</span></span> <span data-ttu-id="592e5-127">центрирует представление посередине между минимальным и максимальным горизонтальными значениями.</span><span class="sxs-lookup"><span data-stu-id="592e5-127">centers the view at the midpoint between the minimum and maximum horizontal values.</span></span>  
  
 <span data-ttu-id="592e5-128">**Центр представления (Y) %**</span><span class="sxs-lookup"><span data-stu-id="592e5-128">**View center (Y) %**</span></span>  
 <span data-ttu-id="592e5-129">Вертикальная координата.</span><span class="sxs-lookup"><span data-stu-id="592e5-129">The vertical coordinate.</span></span> <span data-ttu-id="592e5-130">Значение по умолчанию (50 %) центрирует представление посередине между минимальным и максимальным вертикальными значениями.</span><span class="sxs-lookup"><span data-stu-id="592e5-130">The default value, 50%, centers the view at the midpoint between the minimum and maximum vertical values.</span></span>  
  
 <span data-ttu-id="592e5-131">**Масштаб (%)**</span><span class="sxs-lookup"><span data-stu-id="592e5-131">**Zoom level (%)**</span></span>  
 <span data-ttu-id="592e5-132">Масштаб.</span><span class="sxs-lookup"><span data-stu-id="592e5-132">The zoom factor.</span></span> <span data-ttu-id="592e5-133">Значение по умолчанию (100 %) указывает на отсутствие увеличения.</span><span class="sxs-lookup"><span data-stu-id="592e5-133">The default value, 100%, indicates no magnification.</span></span>  
  
 <span data-ttu-id="592e5-134">**Центрировать представление этого слоя**</span><span class="sxs-lookup"><span data-stu-id="592e5-134">**Center view on this layer**</span></span>  
 <span data-ttu-id="592e5-135">Укажите имя слоя.</span><span class="sxs-lookup"><span data-stu-id="592e5-135">Specify the name of the layer.</span></span>  
  
 <span data-ttu-id="592e5-136">**Центрировать представление элемента карты, удовлетворяющего этому условию**</span><span class="sxs-lookup"><span data-stu-id="592e5-136">**Center view on the map element that matches this condition**</span></span>  
 <span data-ttu-id="592e5-137">Отображаемое поле только для чтения используется для сопоставления данных карты и аналитических данных.</span><span class="sxs-lookup"><span data-stu-id="592e5-137">The read-only field that is displayed is used to match map data and analytical data.</span></span> <span data-ttu-id="592e5-138">Укажите значение, по которому будет выполняться сопоставление.</span><span class="sxs-lookup"><span data-stu-id="592e5-138">Specify the value that you want to match on.</span></span> <span data-ttu-id="592e5-139">Вид автоматически центрируется по данному элементу карты.</span><span class="sxs-lookup"><span data-stu-id="592e5-139">The view automatically centers on this map element.</span></span> <span data-ttu-id="592e5-140">Например, NAME = TEXAS.</span><span class="sxs-lookup"><span data-stu-id="592e5-140">For example, NAME = TEXAS.</span></span> <span data-ttu-id="592e5-141">По умолчанию для условия используется тип данных String, а сопоставление выполняется с учетом регистра символов.</span><span class="sxs-lookup"><span data-stu-id="592e5-141">By default, the data type for the condition is String and the match is case-sensitive.</span></span>  
  
 <span data-ttu-id="592e5-142">Для сопоставления с полем, имеющим другой тип данных, необходимо написать выражение, значение которого имеет соответствующий тип.</span><span class="sxs-lookup"><span data-stu-id="592e5-142">To match on a field that has a different data type, you must write an expression that evaluates to that data type.</span></span> <span data-ttu-id="592e5-143">Например, если поле сопоставления — 5-разрядный почтовый код, хранящийся как целое число, то для задания почтового кода нужно использовать выражение =98053.</span><span class="sxs-lookup"><span data-stu-id="592e5-143">For example, if the match field is a 5 digit postal code that is stored as an integer, then to specify the postal code 98053, you must use the expression =98053.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="592e5-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="592e5-144">See Also</span></span>  
 [<span data-ttu-id="592e5-145">Карты (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="592e5-145">Maps &#40;Report Builder and SSRS&#41;</span></span>](report-design/maps-report-builder-and-ssrs.md)  
  
  
