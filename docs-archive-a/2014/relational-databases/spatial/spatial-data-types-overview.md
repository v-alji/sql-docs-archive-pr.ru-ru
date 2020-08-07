---
title: Общие сведения о пространственных типах данных | Документация Майкрософт
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry data type [SQL Server], understanding
- geography data type [SQL Server], spatial data
- planar spatial data [SQL Server], geometry data type
- spatial data types [SQL Server]
ms.assetid: 1615db50-69de-4778-8be6-4e058c00ccd4
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: c0548d974e83bfe2b1e103d4458b17078fba8014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735149"
---
# <a name="spatial-data-types-overview"></a><span data-ttu-id="83626-102">Основные сведения о типах пространственных данных</span><span class="sxs-lookup"><span data-stu-id="83626-102">Spatial Data Types Overview</span></span>
  <span data-ttu-id="83626-103">Существует два типа пространственных данных.</span><span class="sxs-lookup"><span data-stu-id="83626-103">There are two types of spatial data.</span></span> <span data-ttu-id="83626-104">Тип данных `geometry` поддерживает планарные или эвклидовы данные (система координат для плоской Земли).</span><span class="sxs-lookup"><span data-stu-id="83626-104">The `geometry` data type supports planar, or Euclidean (flat-earth), data.</span></span> <span data-ttu-id="83626-105">Тип данных `geometry` соответствует спецификации «Simple Features for SQL» консорциума OGC версии 1.1.0 и стандарту SQL MM (стандарт ISO).</span><span class="sxs-lookup"><span data-stu-id="83626-105">The `geometry` data type both conforms to the Open Geospatial Consortium (OGC) Simple Features for SQL Specification version 1.1.0 and is compliant with SQL MM (ISO standard).</span></span>

 <span data-ttu-id="83626-106">Кроме того, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поддерживает тип данных `geography`, который используется для хранения эллиптических данных, таких как координаты GPS широты и долготы.</span><span class="sxs-lookup"><span data-stu-id="83626-106">In addition, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supports the `geography` data type, which stores ellipsoidal (round-earth) data, such as GPS latitude and longitude coordinates.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="83626-107">Подробное описание и примеры использования функций обработки пространственных данных, реализованные в [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], в том числе улучшения пространственных типов данных, можно получить, загрузив технический документ [Новые функции обработки пространственных данных в SQL Server с рабочим названием "Denali"](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="83626-107">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including enhancements to the spatial data types, download the white paper, [New Spatial Features in SQL Server Code-Named "Denali"](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

##  <a name="spatial-data-objects"></a><a name="objects"></a> <span data-ttu-id="83626-108">Объекты пространственных данных</span><span class="sxs-lookup"><span data-stu-id="83626-108">Spatial Data Objects</span></span>
 <span data-ttu-id="83626-109">Типы данных `geometry` и `geography` поддерживают шестнадцать объектов пространственных данных или типов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="83626-109">The `geometry` and `geography` data types support sixteen spatial data objects, or instance types.</span></span> <span data-ttu-id="83626-110">Однако только одиннадцать из этих типов экземпляров являются *материализуемыми*. Такие экземпляры можно создавать в базе данных и работать с ними.</span><span class="sxs-lookup"><span data-stu-id="83626-110">However, only eleven of these instance types are *instantiable*; you can create and work with these instances (or instantiate them) in a database.</span></span> <span data-ttu-id="83626-111">Эти экземпляры наследуют определенные свойства от родительских типов данных, которые отличают их как `Points` , **LineString, объекта CircularString**,, `CompoundCurves` `Polygons` `CurvePolygons` или как несколько `geometry` `geography` экземпляров или в `GeometryCollection` .</span><span class="sxs-lookup"><span data-stu-id="83626-111">These instances derive certain properties from their parent data types that distinguish them as `Points`, **LineStrings, CircularStrings**, `CompoundCurves`, `Polygons`, `CurvePolygons` or as multiple `geometry` or `geography` instances in a `GeometryCollection`.</span></span> <span data-ttu-id="83626-112">Тип `Geography` имеет дополнительный тип экземпляра `FullGlobe`.</span><span class="sxs-lookup"><span data-stu-id="83626-112">`Geography` type has an additional instance type, `FullGlobe`.</span></span>

 <span data-ttu-id="83626-113">На рисунке ниже изображена иерархия `geometry`, на которой основаны типы данных `geometry` и `geography`.</span><span class="sxs-lookup"><span data-stu-id="83626-113">The figure below depicts the `geometry` hierarchy upon which the `geometry` and `geography` data types are based.</span></span> <span data-ttu-id="83626-114">Допускающие создание экземпляров типы `geometry` и `geography` обозначены синим цветом.</span><span class="sxs-lookup"><span data-stu-id="83626-114">The instantiable types of `geometry` and `geography` are indicated in blue.</span></span>

 <span data-ttu-id="83626-115">![Иерархия типа geometry](../../database-engine/media/geom-hierarchy.gif "Иерархия типа geometry")</span><span class="sxs-lookup"><span data-stu-id="83626-115">![Hierarchy of the geometry type](../../database-engine/media/geom-hierarchy.gif "Hierarchy of the geometry type")</span></span>

 <span data-ttu-id="83626-116">Как показано на рисунке, десять допускающих создание экземпляров типов `geometry` `geography` данных и — это `Point` ,,,, `MultiPoint` `LineString` `CircularString` `MultiLineString` , `CompoundCurve` , `Polygon` , `CurvePolygon` , `MultiPolygon` и `GeometryCollection` .</span><span class="sxs-lookup"><span data-stu-id="83626-116">As the figure indicates, the ten instantiable types of the `geometry` and `geography` data types are `Point`, `MultiPoint`, `LineString`, `CircularString`, `MultiLineString`, `CompoundCurve`, `Polygon`, `CurvePolygon`, `MultiPolygon`, and `GeometryCollection`.</span></span> <span data-ttu-id="83626-117">Есть один дополнительный тип, допускающий создание экземпляров, для типа данных geography: `FullGlobe`.</span><span class="sxs-lookup"><span data-stu-id="83626-117">There is one additional instantiable type for the geography data type: `FullGlobe`.</span></span> <span data-ttu-id="83626-118">`geometry`Типы и `geography` могут распознать определенный экземпляр, если он является правильно сформированным экземпляром, даже если экземпляр не определен явным образом.</span><span class="sxs-lookup"><span data-stu-id="83626-118">The `geometry` and `geography` types can recognize a specific instance as long as it is a well-formed instance, even if the instance is not defined explicitly.</span></span> <span data-ttu-id="83626-119">Например, если `Point` экземпляр определен явным образом с помощью метода STPointFromText () `geometry` и `geography` распознает экземпляр как `Point` , при условии, что входные данные метода имеют правильный формат.</span><span class="sxs-lookup"><span data-stu-id="83626-119">For example, if you define a `Point` instance explicitly using the STPointFromText() method, `geometry` and `geography` recognize the instance as a `Point`, as long as the method input is well-formed.</span></span> <span data-ttu-id="83626-120">Если определить такой же экземпляр с помощью метода `STGeomFromText()`, то оба типа данных `geometry` и `geography` будут распознавать экземпляр как `Point`.</span><span class="sxs-lookup"><span data-stu-id="83626-120">If you define the same instance using the `STGeomFromText()` method, both the `geometry` and `geography` data types recognize the instance as a `Point`.</span></span>

 <span data-ttu-id="83626-121">Подтипы для типов geometry и geography делятся на простые типы и типы-коллекции.</span><span class="sxs-lookup"><span data-stu-id="83626-121">The subtypes for geometry and geography types are divided into simple and collection types.</span></span>  <span data-ttu-id="83626-122">Некоторые методы, например `STNumCurves()` , работают только с простыми типами.</span><span class="sxs-lookup"><span data-stu-id="83626-122">Some methods like `STNumCurves()` work only with simple types.</span></span>

 <span data-ttu-id="83626-123">Простые типы:</span><span class="sxs-lookup"><span data-stu-id="83626-123">Simple types include:</span></span>

-   [<span data-ttu-id="83626-124">Point</span><span class="sxs-lookup"><span data-stu-id="83626-124">Point</span></span>](../spatial/point.md)

-   [<span data-ttu-id="83626-125">LineString</span><span class="sxs-lookup"><span data-stu-id="83626-125">LineString</span></span>](../spatial/linestring.md)

-   [<span data-ttu-id="83626-126">CircularString</span><span class="sxs-lookup"><span data-stu-id="83626-126">CircularString</span></span>](../spatial/circularstring.md)

-   [<span data-ttu-id="83626-127">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="83626-127">CompoundCurve</span></span>](../spatial/compoundcurve.md)

-   [<span data-ttu-id="83626-128">Многоугольник</span><span class="sxs-lookup"><span data-stu-id="83626-128">Polygon</span></span>](../spatial/polygon.md)

-   [<span data-ttu-id="83626-129">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="83626-129">CurvePolygon</span></span>](../spatial/curvepolygon.md)

 <span data-ttu-id="83626-130">Типы-коллекции:</span><span class="sxs-lookup"><span data-stu-id="83626-130">Collection types include:</span></span>

-   [<span data-ttu-id="83626-131">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="83626-131">MultiPoint</span></span>](../spatial/multipoint.md)

-   [<span data-ttu-id="83626-132">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="83626-132">MultiLineString</span></span>](../spatial/multilinestring.md)

-   [<span data-ttu-id="83626-133">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="83626-133">MultiPolygon</span></span>](../spatial/multipolygon.md)

-   [<span data-ttu-id="83626-134">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="83626-134">GeometryCollection</span></span>](../spatial/geometrycollection.md)


##  <a name="differences-between-the-geometry-and-geography-data-types"></a><a name="differences"></a> <span data-ttu-id="83626-135">Различия между типами данных geometry и geography</span><span class="sxs-lookup"><span data-stu-id="83626-135">Differences Between the geometry and geography Data Types</span></span>
 <span data-ttu-id="83626-136">Два типа пространственных данных часто демонстрируют одинаковое поведение, однако у них имеется ряд ключевых различий в способе хранения и управления данными.</span><span class="sxs-lookup"><span data-stu-id="83626-136">The two types of spatial data often behave quite similarly, but there are some key differences in how the data is stored and manipulated.</span></span>

### <a name="how-connecting-edges-are-defined"></a><span data-ttu-id="83626-137">Определение границ соединения</span><span class="sxs-lookup"><span data-stu-id="83626-137">How connecting edges are defined</span></span>
 <span data-ttu-id="83626-138">Определяющими данными для типов `LineString` и `Polygon` могут быть только вершины.</span><span class="sxs-lookup"><span data-stu-id="83626-138">The defining data for `LineString` and `Polygon` types are vertices only.</span></span>  <span data-ttu-id="83626-139">Границей соединения между двумя вершинами в типе geometry является прямая линия.</span><span class="sxs-lookup"><span data-stu-id="83626-139">The connecting edge between two vertices in a geometry type is a straight line.</span></span>  <span data-ttu-id="83626-140">Однако границей соединения между двумя вершинами в типе geography является короткая большая эллиптическая кривая, проложенная между вершинами.</span><span class="sxs-lookup"><span data-stu-id="83626-140">However, the connecting edge between two vertices in a geography type is a short great elliptic arc between the two vertices.</span></span>  <span data-ttu-id="83626-141">Большой эллипс представляет собой пересечение эллипсоида с плоскостью, проходящей через его центр, а большая эллиптическая кривая представляет собой сегмент кривой на большом эллипсе.</span><span class="sxs-lookup"><span data-stu-id="83626-141">A great ellipse is the intersection of the ellipsoid with a plane through its center and a great elliptic arc is an arc segment on the great ellipse.</span></span>

### <a name="how-circular-arc-segments-are-defined"></a><span data-ttu-id="83626-142">Определение сегментов дуги</span><span class="sxs-lookup"><span data-stu-id="83626-142">How circular arc segments are defined</span></span>
 <span data-ttu-id="83626-143">Сегменты дуги для типов geometry определяются на декартовой координатной плоскости XY (значения Z не учитываются).</span><span class="sxs-lookup"><span data-stu-id="83626-143">Circular arc segments for geometry types are defined on the XY Cartesian coordinate plane (Z values are ignored).</span></span> <span data-ttu-id="83626-144">Сегменты дуги для типов geography определяются сегментами кривой на эталонной сфере.</span><span class="sxs-lookup"><span data-stu-id="83626-144">Circular arc segments for geography types are defined by curve segments on a reference sphere.</span></span> <span data-ttu-id="83626-145">Любую параллель на эталонной сфере можно определить двумя взаимодополняющими дугами, где точки для обеих дуг имеют постоянный угол широты.</span><span class="sxs-lookup"><span data-stu-id="83626-145">Any parallel on the reference sphere can be defined by two complementary circular arcs where the points for both arcs have a constant latitude angle.</span></span>

### <a name="measurements-in-spatial-data-types"></a><span data-ttu-id="83626-146">Измерения в пространственных типах данных</span><span class="sxs-lookup"><span data-stu-id="83626-146">Measurements in spatial data types</span></span>
 <span data-ttu-id="83626-147">В планарной модели (или модели плоской Земли) измерение расстояний и площадей проводятся в таких же единицах измерения, в каких представляются координаты.</span><span class="sxs-lookup"><span data-stu-id="83626-147">In the planar, or flat-earth, system, measurements of distances and areas are given in the same unit of measurement as coordinates.</span></span> <span data-ttu-id="83626-148">При использовании типа данных `geometry` расстояние между точками (2, 2) и (5, 6) составляет 5 единиц, независимо от используемых единиц.</span><span class="sxs-lookup"><span data-stu-id="83626-148">Using the `geometry` data type, the distance between (2, 2) and (5, 6) is 5 units, regardless of the units used.</span></span>

 <span data-ttu-id="83626-149">В эллиптической модели, или модели круглой Земли, координаты указываются в градусах долготы и широты.</span><span class="sxs-lookup"><span data-stu-id="83626-149">In the ellipsoidal, or round-earth system, coordinates are given in degrees of latitude and longitude.</span></span> <span data-ttu-id="83626-150">Однако длины и площади обычно измеряются в метрах и квадратных метрах, хотя измерения могут зависеть от идентификатора пространственной ссылки (SRID) экземпляра `geography`.</span><span class="sxs-lookup"><span data-stu-id="83626-150">However, lengths and areas are usually measured in meters and square meters, though the measurement may depend on the spatial reference identifier (SRID) of the `geography` instance.</span></span> <span data-ttu-id="83626-151">Самой распространенной единицей измерения типа данных `geography` является метр.</span><span class="sxs-lookup"><span data-stu-id="83626-151">The most common unit of measurement for the `geography` data type is meters.</span></span>

### <a name="orientation-of-spatial-data"></a><span data-ttu-id="83626-152">Ориентация пространственных данных</span><span class="sxs-lookup"><span data-stu-id="83626-152">Orientation of spatial data</span></span>
 <span data-ttu-id="83626-153">В планарной системе ориентация кольца многоугольника является несущественным фактором.</span><span class="sxs-lookup"><span data-stu-id="83626-153">In the planar system, the ring orientation of a polygon is not an important factor.</span></span> <span data-ttu-id="83626-154">Например, многоугольник ((0, 0), (10, 0), (0, 20), (0, 0)) идентичен многоугольнику ((0, 0), (0, 20), (10, 0), (0, 0)).</span><span class="sxs-lookup"><span data-stu-id="83626-154">For example, a polygon described by ((0, 0), (10, 0), (0, 20), (0, 0)) is the same as a polygon described by ((0, 0), (0, 20), (10, 0), (0, 0)).</span></span> <span data-ttu-id="83626-155">Спецификация «Simple Features for SQL» консорциума OGC не определяет положение кольца, а [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] его не учитывает.</span><span class="sxs-lookup"><span data-stu-id="83626-155">The OGC Simple Features for SQL Specification does not dictate a ring ordering, and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not enforce ring ordering.</span></span>

 <span data-ttu-id="83626-156">В эллиптической модели без указания ориентации многоугольник не определен или является неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="83626-156">In an ellipsoidal system, a polygon has no meaning, or is ambiguous, without an orientation.</span></span> <span data-ttu-id="83626-157">Например, описывает ли кольцо вокруг экватора северное или южное полушарие?</span><span class="sxs-lookup"><span data-stu-id="83626-157">For example, does a ring around the equator describe the northern or southern hemisphere?</span></span> <span data-ttu-id="83626-158">При использовании типа данных `geography` для хранения пространственного экземпляра необходимо указать ориентацию кольца и точно описать расположение экземпляра.</span><span class="sxs-lookup"><span data-stu-id="83626-158">If we use the `geography` data type to store the spatial instance, we must specify the orientation of the ring and accurately describe the location of the instance.</span></span> <span data-ttu-id="83626-159">Внутренняя часть многоугольника в эллиптической модели определяется правилом левой руки.</span><span class="sxs-lookup"><span data-stu-id="83626-159">The interior of the polygon in an ellipsoidal system is defined by the left-hand rule.</span></span>

 <span data-ttu-id="83626-160">Если уровень совместимости равен 100 или ниже, то [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] `geography` тип данных имеет следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="83626-160">When the compatibility level is 100 or below in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] then the `geography` data type has the following restrictions:</span></span>

-   <span data-ttu-id="83626-161">Любой экземпляр `geography` должен лежать в пределах одного полушария.</span><span class="sxs-lookup"><span data-stu-id="83626-161">Each `geography` instance must fit inside a single hemisphere.</span></span> <span data-ttu-id="83626-162">Не допускается сохранение пространственных объектов больше размера полушария.</span><span class="sxs-lookup"><span data-stu-id="83626-162">No spatial objects larger than a hemisphere can be stored.</span></span>

-   <span data-ttu-id="83626-163">Любой экземпляр `geography` в представлении консорциума OGC Well-Known Text (WKT) или Well-Known Binary (WKB), порождающий объект больше полушария, приводит к возникновению исключения `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="83626-163">Any `geography` instance from an Open Geospatial Consortium (OGC) Well-Known Text (WKT) or Well-Known Binary (WKB) representation that produces an object larger than a hemisphere throws an `ArgumentException`.</span></span>

-   <span data-ttu-id="83626-164">`geography`Методы типа данных, требующие ввода двух `geography` экземпляров, таких как STIntersection (), STUnion (), STDifference () и STSymDifference (), возвращают значение null, если результаты методов не умещаются в одном полушарии.</span><span class="sxs-lookup"><span data-stu-id="83626-164">The `geography` data type methods that require the input of two `geography` instances, such as STIntersection(), STUnion(), STDifference(), and STSymDifference(), will return null if the results from the methods do not fit inside a single hemisphere.</span></span> <span data-ttu-id="83626-165">Метод STBuffer() также возвращает значение NULL, если выходные данные выходят за пределы одного полушария.</span><span class="sxs-lookup"><span data-stu-id="83626-165">STBuffer() will also return null if the output exceeds a single hemisphere.</span></span>

 <span data-ttu-id="83626-166">В [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] тип `FullGlobe` представляет разновидность Polygon, охватывающую весь земной шар.</span><span class="sxs-lookup"><span data-stu-id="83626-166">In [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], `FullGlobe` is a special type of Polygon that covers the entire globe.</span></span> <span data-ttu-id="83626-167">Объект `FullGlobe` имеет площадь, но не имеет границ и вершин.</span><span class="sxs-lookup"><span data-stu-id="83626-167">`FullGlobe` has an area, but no borders or vertices.</span></span>

### <a name="outer-and-inner-rings-not-important-in-geography-data-type"></a><span data-ttu-id="83626-168">Для типа данных geography внешнее и внутреннее кольца не важны.</span><span class="sxs-lookup"><span data-stu-id="83626-168">Outer and inner rings not important in geography data type</span></span>
 <span data-ttu-id="83626-169">OGC простые функции для спецификации SQL обсуждают внешние кольца и внутренние кольца, но это различие имеет немало смысла для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` типа данных. любое кольцо многоугольника может быть занято внешним кольцом.</span><span class="sxs-lookup"><span data-stu-id="83626-169">The OGC Simple Features for SQL Specification discusses outer rings and inner rings, but this distinction makes little sense for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` data type; any ring of a polygon can be taken to be the outer ring.</span></span>

 <span data-ttu-id="83626-170">Дополнительные сведения о спецификациях OGC см. в одном из следующих источников:</span><span class="sxs-lookup"><span data-stu-id="83626-170">For more information on OGC specifications, see the following:</span></span>

-   [<span data-ttu-id="83626-171">Спецификации OGC, простой доступ к функциям, часть 1 — общая архитектура</span><span class="sxs-lookup"><span data-stu-id="83626-171">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span></span>](https://go.microsoft.com/fwlink/?LinkId=93627)

-   [<span data-ttu-id="83626-172">Спецификации OGC, простой доступ к функциям, часть 2 — параметры SQL</span><span class="sxs-lookup"><span data-stu-id="83626-172">OGC Specifications, Simple Feature Access Part 2 - SQL Options</span></span>](https://go.microsoft.com/fwlink/?LinkId=93628)


##  <a name="circular-arc-segments"></a><a name="circular"></a> <span data-ttu-id="83626-173">Сегменты дуги</span><span class="sxs-lookup"><span data-stu-id="83626-173">Circular Arc Segments</span></span>
 <span data-ttu-id="83626-174">Три типа, допускающих создание экземпляров, могут принимать сегменты дуги: `CircularString`, `CompoundCurve` и `CurvePolygon`.</span><span class="sxs-lookup"><span data-stu-id="83626-174">Three instantiable types can take circular arc segments: `CircularString`, `CompoundCurve`, and `CurvePolygon`.</span></span>  <span data-ttu-id="83626-175">Сегмент дуги определяется тремя точками на двумерной плоскости, при этом третья точка не может совпадать с первой.</span><span class="sxs-lookup"><span data-stu-id="83626-175">A circular arc segment is defined by three points in a two dimensional plane and the third point cannot be the same as the first point.</span></span>

 <span data-ttu-id="83626-176">Фигуры A и B являются типичными сегментами дуги.</span><span class="sxs-lookup"><span data-stu-id="83626-176">Figures A and B show typical circular arc segments.</span></span> <span data-ttu-id="83626-177">Обратите внимание, что каждая из трех точек лежит на периметре круга.</span><span class="sxs-lookup"><span data-stu-id="83626-177">Note how each of the three points lie on the perimeter of a circle.</span></span>

 <span data-ttu-id="83626-178">Фигуры C и D демонстрируют, как можно определить сегмент линии с помощью сегмента дуги.</span><span class="sxs-lookup"><span data-stu-id="83626-178">Figures C and D show how a line segment can be defined as a circular arc segment.</span></span>  <span data-ttu-id="83626-179">Обратите внимание, что для определения сегмента дуги по-прежнему требуются три точки, тогда как обычный сегмент линии можно определить с помощью двух точек.</span><span class="sxs-lookup"><span data-stu-id="83626-179">Note that three points are still needed to define the circular arc segment unlike a regular line segment which can be defined by just two points.</span></span>

 <span data-ttu-id="83626-180">Методы, работающие с типами сегментов дуги, для приближения дуги используют сегменты прямой линии. Количество сегментов, используемых для приближения дуги, зависит от длины и кривизны дуги. Значения Z можно сохранять для каждого типа сегмента дуги. Однако методы не используют значения Z в своих вычислениях.</span><span class="sxs-lookup"><span data-stu-id="83626-180">Methods operating on circular arc segment types use straight line segments to approximate the circular arc. The number of line segments used to approximate the arc will depend on the length and curvature of the arc. Z values can be stored for each of the circular arc segment types; however, methods will not use the Z values in their calculations.</span></span>

> [!NOTE]
>  <span data-ttu-id="83626-181">Если для сегментов дуги даются значения Z, они должны совпадать для всех точек сегмента дуги. Только в этом случае они могут быть приняты в качестве ввода.</span><span class="sxs-lookup"><span data-stu-id="83626-181">If Z values are given for circular arc segments then they must be the same for all points in the circular arc segment for it to be accepted for input.</span></span> <span data-ttu-id="83626-182">Например: `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` принимается, но `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` не принимается.</span><span class="sxs-lookup"><span data-stu-id="83626-182">For example: `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` is accepted, but `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` is not accepted.</span></span>

### <a name="linestring-and-circularstring-comparison"></a><span data-ttu-id="83626-183">Сравнение типов LineString и CircularString</span><span class="sxs-lookup"><span data-stu-id="83626-183">LineString and CircularString comparison</span></span>
 <span data-ttu-id="83626-184">На следующей диаграмме показаны одинаковые равнобедренные треугольники (треугольник A для определения треугольника использует сегменты линии, а треугольник B — сегменты дуги).</span><span class="sxs-lookup"><span data-stu-id="83626-184">The following diagram shows identical isosceles triangles (triangle A uses line segments to define the triangle and triangle B uses circular arc segments to defined the triangle):</span></span>

 ![](../../database-engine/media/7e382f76-59da-4b62-80dc-caf93e637c14.png "7e382f76-59da-4b62-80dc-caf93e637c14")

 <span data-ttu-id="83626-185">В следующем примере показано, как сохранить эти равнобедренные треугольники с помощью экземпляра `LineString` и экземпляра `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="83626-185">This example shows how to store the above isosceles triangles using both a `LineString` instance and `CircularString` instance:</span></span>

```sql
DECLARE @g1 geometry;
DECLARE @g2 geometry;
SET @g1 = geometry::STGeomFromText('LINESTRING(1 1, 5 1, 3 5, 1 1)', 0);
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(1 1, 3 1, 5 1, 4 3, 3 5, 2 3, 1 1)', 0);
IF @g1.STIsValid() = 1 AND @g2.STIsValid() = 1
  BEGIN
      SELECT @g1.ToString(), @g2.ToString()
      SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length]
  END
```

 <span data-ttu-id="83626-186">Обратите внимание, что экземпляру `CircularString` требуется семь точек для определения треугольника, тогда как экземпляру `LineString` для этого достаточно всего четырех точек.</span><span class="sxs-lookup"><span data-stu-id="83626-186">Notice that a `CircularString` instance requires seven points to define the triangle, but a `LineString` instance requires only four points to define the triangle.</span></span> <span data-ttu-id="83626-187">Причиной этого является то, что экземпляр `CircularString` хранит сегменты дуги, а не сегменты линии.</span><span class="sxs-lookup"><span data-stu-id="83626-187">The reason for this is that a `CircularString` instance stores circular arc segments and not line segments.</span></span> <span data-ttu-id="83626-188">Поэтому сторонами треугольника, хранящегося в экземпляре `CircularString`, являются ABC, CDE и EFA, а сторонами треугольника, хранящегося в экземпляре `LineString`, — AC, CE и EA.</span><span class="sxs-lookup"><span data-stu-id="83626-188">So the sides of the triangle stored in the `CircularString` instance are ABC, CDE, and EFA whereas the sides of the triangle stored in the `LineString` instance are AC, CE, and EA.</span></span>

 <span data-ttu-id="83626-189">Рассмотрим следующий фрагмент кода:</span><span class="sxs-lookup"><span data-stu-id="83626-189">Consider the following code snippet:</span></span>

```sql
SET @g1 = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 4 0)', 0);
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(0 0, 2 2, 4 0)', 0);
SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length];
```

 <span data-ttu-id="83626-190">Этот фрагмент выдаст следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="83626-190">This snippet will produce the following results:</span></span>

```
LS LengthCS Length
5.65685...6.28318...
```

 <span data-ttu-id="83626-191">На следующем рисунке показано, как каждый тип хранится (красная линия отображается `LineString``@g1` , синяя линия показана `CircularString``@g2` ):</span><span class="sxs-lookup"><span data-stu-id="83626-191">The following illustration shows how each type is stored (red line shows `LineString``@g1`, blue line shows `CircularString``@g2`):</span></span>

 ![](../../database-engine/media/e52157b5-5160-4a4b-8560-50cdcf905b76.png "e52157b5-5160-4a4b-8560-50cdcf905b76")

 <span data-ttu-id="83626-192">Как показано на рисунке выше, объекты `CircularString` используют меньшее число точек для хранения границ кривой и обеспечивают большую точность, чем объекты `LineString`.</span><span class="sxs-lookup"><span data-stu-id="83626-192">As the illustration above shows, `CircularString` instances use fewer points to store curve boundaries with greater precision than `LineString` instances.</span></span> <span data-ttu-id="83626-193">Объекты `CircularString` полезны для хранения круговых границ, например область поиска радиусом в двадцать миль от указанной точки.</span><span class="sxs-lookup"><span data-stu-id="83626-193">`CircularString` instances are useful for storing circular boundaries like a twenty-mile search radius from a specific point.</span></span> <span data-ttu-id="83626-194">Объекты `LineString` хорошо подходят для хранения линейных границ, например городского квартала.</span><span class="sxs-lookup"><span data-stu-id="83626-194">`LineString` instances are good for storing boundaries that are linear like a square city block.</span></span>

### <a name="linestring-and-compoundcurve-comparison"></a><span data-ttu-id="83626-195">Сравнение типов LineString и CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="83626-195">LineString and CompoundCurve comparison</span></span>
 <span data-ttu-id="83626-196">В следующем примере кода показано, как одна и та же фигура сохраняется с помощью экземпляров `LineString` и `CompoundCurve`:</span><span class="sxs-lookup"><span data-stu-id="83626-196">The following code examples show how to store the same figure using `LineString` and `CompoundCurve` instances:</span></span>

```sql
SET @g = geometry::Parse('LINESTRING(2 2, 4 2, 4 4, 2 4, 2 2)');
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2), (4 2, 4 4), (4 4, 2 4), (2 4, 2 2))');
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2, 4 4, 2 4, 2 2))');
```

 <span data-ttu-id="83626-197">or</span><span class="sxs-lookup"><span data-stu-id="83626-197">or</span></span>

 <span data-ttu-id="83626-198">В этих примерах фигура может храниться как экземпляр `LineString` или как экземпляр `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="83626-198">In the examples above, either a `LineString` instance or a `CompoundCurve` instance could store the figure.</span></span>  <span data-ttu-id="83626-199">В следующем примере тип `CompoundCurve` используется для хранения среза круговой диаграммы:</span><span class="sxs-lookup"><span data-stu-id="83626-199">This next example uses a `CompoundCurve` to store a pie slice:</span></span>

```sql
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(2 2, 1 3, 0 2),(0 2, 1 0, 2 2))');
```

 <span data-ttu-id="83626-200">Экземпляр `CompoundCurve` может хранить сегмент дуги (2 2, 1 3, 0 2) непосредственно, в то время как экземпляру `LineString` пришлось бы преобразовать кривую в несколько сегментов строки меньшего размера.</span><span class="sxs-lookup"><span data-stu-id="83626-200">A `CompoundCurve` instance can store the circular arc segment (2 2, 1 3, 0 2) directly whereas a `LineString` instance would have to convert the curve into several smaller line segments.</span></span>

### <a name="circularstring-and-compoundcurve-comparison"></a><span data-ttu-id="83626-201">Сравнение типов CircularString и CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="83626-201">CircularString and CompoundCurve comparison</span></span>
 <span data-ttu-id="83626-202">В следующем примере кода показано, как можно сохранить срезы круговой диаграммы в экземпляре `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="83626-202">The following code example shows how the pie slice can be stored in a `CircularString` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)');
SELECT @g.ToString(), @g.STLength();
```

 <span data-ttu-id="83626-203">Для хранения среза круговой диаграммы с помощью экземпляра `CircularString` требуется три точки для каждого сегмента линии.</span><span class="sxs-lookup"><span data-stu-id="83626-203">To store the pie slice using a `CircularString` instance requires that three points be used for each line segment.</span></span>  <span data-ttu-id="83626-204">Если промежуточная точка неизвестна, необходимо либо вычислить ее, либо сдублировать конечную точку сегмента линии, как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="83626-204">If an intermediate point is not known, it either has to be calculated or the endpoint of the line segment has to be doubled as the following snippet shows:</span></span>

```sql
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 3 6.3246, 3 6.3246, 0 7, -3 6.3246, 0 0, 0 0)');
```

 <span data-ttu-id="83626-205">`CompoundCurve`экземпляры допускают как `LineString` `CircularString` компоненты, так и те, что должны быть известны только две точки сегмента круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="83626-205">`CompoundCurve` instances allow both `LineString` and `CircularString` components so that only two points to the line segments of the pie slice need to be known.</span></span>  <span data-ttu-id="83626-206">В этом примере кода показано, как использовать тип `CompoundCurve` для хранения той же фигуры:</span><span class="sxs-lookup"><span data-stu-id="83626-206">This code example shows how to use a `CompoundCurve` to store the same figure:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING( 3 6.3246, 0 7, -3 6.3246), (-3 6.3246, 0 0, 3 6.3246))');
SELECT @g.ToString(), @g.STLength();
```

### <a name="polygon-and-curvepolygon-comparison"></a><span data-ttu-id="83626-207">Сравнение типов Polygon и CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="83626-207">Polygon and CurvePolygon comparison</span></span>
 <span data-ttu-id="83626-208">Экземпляры `CurvePolygon` могут использовать экземпляры `CircularString` и `CompoundCurve` для определения внешних и внутренних колец.</span><span class="sxs-lookup"><span data-stu-id="83626-208">`CurvePolygon` instances can use `CircularString` and `CompoundCurve` instances when defining their exterior and interior rings.</span></span>  <span data-ttu-id="83626-209">Экземпляры `Polygon` не могут использовать типы сегментов дуги: `CircularString` и `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="83626-209">`Polygon` instances cannot use the circular arc segment types: `CircularString` and `CompoundCurve`.</span></span>


## <a name="see-also"></a><span data-ttu-id="83626-210">См. также:</span><span class="sxs-lookup"><span data-stu-id="83626-210">See Also</span></span>
 <span data-ttu-id="83626-211">[Пространственные данные &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [метод типа данных geometry](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) Справочник по [методу типа данных geography](/sql/t-sql/spatial-geography/spatial-types-geography) [STNumCurves &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type) [STNumCurves &#40;География тип данных&#41;](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type) [STGeomFromText &#40;Geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type) [STGeomFromText &#40;тип данных geography&#41;](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)</span><span class="sxs-lookup"><span data-stu-id="83626-211">[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [geometry Data Type Method Reference](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) [geography Data Type Method Reference](/sql/t-sql/spatial-geography/spatial-types-geography) [STNumCurves &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type) [STNumCurves &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type) [STGeomFromText &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type) [STGeomFromText &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)</span></span>


