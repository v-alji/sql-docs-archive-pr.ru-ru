---
title: Многоугольник | Документация Майкрософт
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry subtypes [SQL Server]
- Polygon geometry subtype [SQL Server]
ms.assetid: b6a21c3c-fdb8-4187-8229-1c488454fdfb
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 040bb8a2558cc57b1b99a3ce984bec3c8925bc0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668176"
---
# <a name="polygon"></a><span data-ttu-id="d5939-102">Многоугольник</span><span class="sxs-lookup"><span data-stu-id="d5939-102">Polygon</span></span>
  <span data-ttu-id="d5939-103">`Polygon` представляет собой двухмерную поверхность, хранимую в виде последовательности точек, определяющих внешнее ограничивающее кольцо, и внутренних колец (последние могут отсутствовать).</span><span class="sxs-lookup"><span data-stu-id="d5939-103">A `Polygon` is a two-dimensional surface stored as a sequence of points defining an exterior bounding ring and zero or more interior rings.</span></span>

## <a name="polygon-instances"></a><span data-ttu-id="d5939-104">Экземпляры многоугольников</span><span class="sxs-lookup"><span data-stu-id="d5939-104">Polygon instances</span></span>
 <span data-ttu-id="d5939-105">Каждый экземпляр `Polygon` должен быть сформирован на основе кольца, содержащего не менее трех уникальных точек.</span><span class="sxs-lookup"><span data-stu-id="d5939-105">A `Polygon` instance can be formed from a ring that has at least three distinct points.</span></span> <span data-ttu-id="d5939-106">Экземпляр `Polygon` может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="d5939-106">A `Polygon` instance can also be empty.</span></span>

 <span data-ttu-id="d5939-107">Внешнее и любое внутреннее кольца экземпляра `Polygon` определяют его границы.</span><span class="sxs-lookup"><span data-stu-id="d5939-107">The exterior and any interior rings of a `Polygon` define its boundary.</span></span> <span data-ttu-id="d5939-108">Пространство внутри колец определяет внутреннюю сторону экземпляра `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="d5939-108">The space within the rings defines the interior of the `Polygon`.</span></span>

 <span data-ttu-id="d5939-109">На рисунке ниже приведены примеры экземпляров `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="d5939-109">The illustration below shows examples of `Polygon` instances.</span></span>

 <span data-ttu-id="d5939-110">![Примеры экземпляров Polygon типа geometry](../../database-engine/media/polygon.gif "Примеры экземпляров Polygon типа geometry")</span><span class="sxs-lookup"><span data-stu-id="d5939-110">![Examples of geometry Polygon instances](../../database-engine/media/polygon.gif "Examples of geometry Polygon instances")</span></span>

 <span data-ttu-id="d5939-111">На рисунке представлены:</span><span class="sxs-lookup"><span data-stu-id="d5939-111">As shown in the illustration:</span></span>

1.  <span data-ttu-id="d5939-112">на рисунке 1 представлен экземпляр `Polygon`, граница которого определяется внешним кольцом;</span><span class="sxs-lookup"><span data-stu-id="d5939-112">Figure 1 is a `Polygon` instance whose boundary is defined by an exterior ring.</span></span>

2.  <span data-ttu-id="d5939-113">на рисунке 2 представлен экземпляр `Polygon`, граница которого определяется внешним и двумя внутренними кольцами.</span><span class="sxs-lookup"><span data-stu-id="d5939-113">Figure 2 is a `Polygon` instance whose boundary is defined by an exterior ring and two interior rings.</span></span> <span data-ttu-id="d5939-114">Область внутри внутренних колец является частью внешней стороны экземпляра `Polygon`;</span><span class="sxs-lookup"><span data-stu-id="d5939-114">The area inside the interior rings is part of the exterior of the `Polygon` instance.</span></span>

3.  <span data-ttu-id="d5939-115">на рисунке 3 представлен допустимый экземпляр `Polygon`, поскольку внутренние кольца пересекаются в одной точке касания.</span><span class="sxs-lookup"><span data-stu-id="d5939-115">Figure 3 is a valid `Polygon` instance because its interior rings intersect at a single tangent point.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="d5939-116">Правильные экземпляры</span><span class="sxs-lookup"><span data-stu-id="d5939-116">Accepted instances</span></span>
 <span data-ttu-id="d5939-117">Правильные экземпляры `Polygon` — это экземпляры, которые можно сохранить в переменной `geometry` или `geography`, не вызывая исключения.</span><span class="sxs-lookup"><span data-stu-id="d5939-117">Accepted `Polygon` instances are instances that can be stored in a `geometry` or `geography` variable without throwing an exception.</span></span> <span data-ttu-id="d5939-118">Следующие экземпляры `Polygon` являются правильными:</span><span class="sxs-lookup"><span data-stu-id="d5939-118">The following are accepted `Polygon` instances:</span></span>

-   <span data-ttu-id="d5939-119">Пустой экземпляр `Polygon`</span><span class="sxs-lookup"><span data-stu-id="d5939-119">An Empty `Polygon` instance</span></span>

-   <span data-ttu-id="d5939-120">Экземпляр `Polygon` с правильным внешним кольцом и с нулем или более корректных внутренних колец</span><span class="sxs-lookup"><span data-stu-id="d5939-120">A `Polygon` instance that has an acceptable exterior ring and zero or more acceptable interior rings</span></span>

 <span data-ttu-id="d5939-121">Чтобы кольцо было правильным, должны выполняться следующие требования.</span><span class="sxs-lookup"><span data-stu-id="d5939-121">The following criteria are needed for a ring to be acceptable.</span></span>

-   <span data-ttu-id="d5939-122">Экземпляр `LineString` должен быть принят.</span><span class="sxs-lookup"><span data-stu-id="d5939-122">The `LineString` instance must be accepted.</span></span>

-   <span data-ttu-id="d5939-123">Экземпляр `LineString` должен иметь не менее четырех точек.</span><span class="sxs-lookup"><span data-stu-id="d5939-123">The `LineString` instance must have at least four points.</span></span>

-   <span data-ttu-id="d5939-124">Начальная и конечная точки экземпляра `LineString` должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="d5939-124">The starting and ending points of the `LineString` instance must be the same.</span></span>

 <span data-ttu-id="d5939-125">В следующем примере показаны принятые экземпляры `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="d5939-125">The following example shows accepted `Polygon` instances.</span></span>

```
DECLARE @g1 geometry = 'POLYGON EMPTY';
DECLARE @g2 geometry = 'POLYGON((1 1, 3 3, 3 1, 1 1))';
DECLARE @g3 geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(0 0, 3 0, 3 3, 0 3, 0 0))';
DECLARE @g4 geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(3 0, 6 0, 6 3, 3 3, 3 0))';
DECLARE @g5 geometry = 'POLYGON((1 1, 1 1, 1 1, 1 1))';
```

 <span data-ttu-id="d5939-126">На примере `@g4` и `@g5` видно, что может приниматься такой экземпляр `Polygon`, который является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="d5939-126">As `@g4` and `@g5` show an accepted `Polygon` instance may not be a valid `Polygon` instance.</span></span> <span data-ttu-id="d5939-127">`@g5` также показывает, что экземпляр Polygon должен содержать только кольцо с любыми четырьмя точками.</span><span class="sxs-lookup"><span data-stu-id="d5939-127">`@g5` also shows that a Polygon instance needs to only contain a ring with any four points to be accepted.</span></span>

 <span data-ttu-id="d5939-128">Следующие примеры формируют исключение `System.FormatException`, так как экземпляры `Polygon` некорректны.</span><span class="sxs-lookup"><span data-stu-id="d5939-128">The following examples throw a `System.FormatException` because the `Polygon` instances are not accepted.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((1 1, 3 3, 1 1))';
DECLARE @g2 geometry = 'POLYGON((1 1, 3 3, 3 1, 1 5))';
```

 <span data-ttu-id="d5939-129">Экземпляр `@g1` не принимается, поскольку экземпляр `LineString` для внешнего кольца содержит недостаточное число точек.</span><span class="sxs-lookup"><span data-stu-id="d5939-129">`@g1` is not accepted because the `LineString` instance for the exterior ring does not contain enough points.</span></span> <span data-ttu-id="d5939-130">Экземпляр `@g2` не принимается, поскольку начальная точка внешнего кольца экземпляра `LineString` не совпадает с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="d5939-130">`@g2` is not accepted because the starting point of the exterior ring `LineString` instance is not the same as the ending point.</span></span> <span data-ttu-id="d5939-131">В следующем примере внешнее кольцо корректно, а внутреннее — нет.</span><span class="sxs-lookup"><span data-stu-id="d5939-131">The following example has an acceptable exterior ring, but the interior ring is not acceptable.</span></span> <span data-ttu-id="d5939-132">Это также вызовет исключение `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="d5939-132">This also throws a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(0 0, 3 0, 0 0))';
```

### <a name="valid-instances"></a><span data-ttu-id="d5939-133">Допустимые экземпляры</span><span class="sxs-lookup"><span data-stu-id="d5939-133">Valid instances</span></span>
 <span data-ttu-id="d5939-134">Внутренние кольца экземпляра `Polygon` могут соприкасаться как сами с собой, так и друг с другом в точках одной касательной, но если внутренние кольца экземпляра `Polygon` пересекаются, экземпляр недействителен.</span><span class="sxs-lookup"><span data-stu-id="d5939-134">The interior rings of a `Polygon` can touch both themselves and each other at single tangent points, but if the interior rings of a `Polygon` cross, the instance is not valid.</span></span>

 <span data-ttu-id="d5939-135">В следующем примере показаны допустимые экземпляры `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="d5939-135">The following example shows valid `Polygon` instances.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20))';
DECLARE @g2 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0))';
DECLARE @g3 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 0 10, -5 -10, -10 0))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="d5939-136">`@g3` является допустимым, так как два внутренних кольца соприкасаются в одной точке и не пересекаются.</span><span class="sxs-lookup"><span data-stu-id="d5939-136">`@g3` is valid because the two interior rings touch at a single point and do not cross each other.</span></span> <span data-ttu-id="d5939-137">В следующем примере показаны недопустимые экземпляры `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="d5939-137">The following example shows `Polygon` instances that are not valid.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (20 0, 0 10, 0 -20, 20 0))';
DECLARE @g2 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (5 0, 1 5, 1 -5, 5 0))';
DECLARE @g3 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 0 10, 0 -10, -10 0))';
DECLARE @g4 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 1 5, 0 -10, -10 0))';
DECLARE @g5 geometry = 'POLYGON((10 0, 0 10, 0 -10, 10 0), (-20 -20, -20 20, 20 20, 20 -20, -20 -20) )';
DECLARE @g6 geometry = 'POLYGON((1 1, 1 1, 1 1, 1 1))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid(), @g5.STIsValid(), @g6.STIsValid();
```

 <span data-ttu-id="d5939-138">`@g1` является недопустимым, поскольку внутреннее кольцо касается внешнего в двух местах.</span><span class="sxs-lookup"><span data-stu-id="d5939-138">`@g1` is not valid because the inner ring touches the exterior ring in two places.</span></span> <span data-ttu-id="d5939-139">`@g2` является недопустимым, поскольку второе внутреннее кольцо находится внутри первого внутреннего кольца.</span><span class="sxs-lookup"><span data-stu-id="d5939-139">`@g2` is not valid because the second inner ring in within the interior of the first inner ring.</span></span> <span data-ttu-id="d5939-140">`@g3` является недопустимым, поскольку два внутренних кольца касаются в нескольких последовательных точках.</span><span class="sxs-lookup"><span data-stu-id="d5939-140">`@g3` is not valid because the two inner rings touch at multiple consecutive points.</span></span> <span data-ttu-id="d5939-141">`@g4` является недопустимым, поскольку внутренние области двух внутренних колец перекрываются.</span><span class="sxs-lookup"><span data-stu-id="d5939-141">`@g4` is not valid because the interiors of the two inner rings overlap.</span></span> <span data-ttu-id="d5939-142">`@g5` является недопустимым, поскольку внешнее кольцо не является первым.</span><span class="sxs-lookup"><span data-stu-id="d5939-142">`@g5` is not valid because the exterior ring is not the first ring.</span></span> <span data-ttu-id="d5939-143">`@g6` является недопустимым, поскольку кольцо не содержит хотя бы трех различных точек.</span><span class="sxs-lookup"><span data-stu-id="d5939-143">`@g6` is not valid because the ring does not have at least three distinct points.</span></span>

## <a name="examples"></a><span data-ttu-id="d5939-144">Примеры</span><span class="sxs-lookup"><span data-stu-id="d5939-144">Examples</span></span>
 <span data-ttu-id="d5939-145">В следующем примере создается простой экземпляр `geometry``Polygon` с отверстием и значением SRID, равным 10.</span><span class="sxs-lookup"><span data-stu-id="d5939-145">The following example creates a simple `geometry``Polygon` instance with a hole and SRID 10.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STPolyFromText('POLYGON((0 0, 0 3, 3 3, 3 0, 0 0), (1 1, 1 2, 2 1, 1 1))', 10);
```

 <span data-ttu-id="d5939-146">Экземпляр, являющийся недопустимым, может быть введен и преобразован в допустимый экземпляр типа `geometry` .</span><span class="sxs-lookup"><span data-stu-id="d5939-146">Aninstance that is not valid may be entered and converted to a valid `geometry` instance.</span></span> <span data-ttu-id="d5939-147">В следующем примере экземпляра `Polygon`внутреннее и внешнее кольца перекрещиваются, и экземпляр является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="d5939-147">In the following example of a `Polygon`, the interior and exterior rings overlap and the instance is not valid.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('POLYGON((1 0, 0 1, 1 2, 2 1, 1 0), (2 0, 1 1, 2 2, 3 1, 2 0))');
```

 <span data-ttu-id="d5939-148">В следующем примере недопустимый экземпляр преобразуется в допустимый с помощью метода `MakeValid()`.</span><span class="sxs-lookup"><span data-stu-id="d5939-148">In the following example, the invalid instance is made valid with `MakeValid()`.</span></span>

```
SET @g = @g.MakeValid();
SELECT @g.ToString();
```

 <span data-ttu-id="d5939-149">Экземпляром `geometry` , полученным в приведенном выше примере, является `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="d5939-149">The `geometry` instance returned from the above example is a `MultiPolygon`.</span></span>

```
MULTIPOLYGON (((2 0, 3 1, 2 2, 1.5 1.5, 2 1, 1.5 0.5, 2 0)), ((1 0, 1.5 0.5, 1 1, 1.5 1.5, 1 2, 0 1, 1 0)))
```

 <span data-ttu-id="d5939-150">Еще один пример преобразования недопустимого экземпляра в допустимый экземпляр geometry.</span><span class="sxs-lookup"><span data-stu-id="d5939-150">Here is another example of converting an invalid instance to a valid geometry instance.</span></span> <span data-ttu-id="d5939-151">В следующем примере создается экземпляр `Polygon` с тремя одинаковыми точками:</span><span class="sxs-lookup"><span data-stu-id="d5939-151">In the following example the `Polygon` instance has been created using three points that are exactly the same:</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::Parse('POLYGON((1 3, 1 3, 1 3, 1 3))');
SET @g = @g.MakeValid();
SELECT @g.ToString()
```

 <span data-ttu-id="d5939-152">Экземпляр geometry, возвращаемый выше, — это `Point(1 3)`.</span><span class="sxs-lookup"><span data-stu-id="d5939-152">The geometry instance returned above is a `Point(1 3)`.</span></span>  <span data-ttu-id="d5939-153">Если задан экземпляр `Polygon``POLYGON((1 3, 1 5, 1 3, 1 3))` , функция `MakeValid()` вернет `LINESTRING(1 3, 1 5)`.</span><span class="sxs-lookup"><span data-stu-id="d5939-153">If the `Polygon` given is `POLYGON((1 3, 1 5, 1 3, 1 3))` then `MakeValid()` would return `LINESTRING(1 3, 1 5)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5939-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5939-154">See Also</span></span>
 <span data-ttu-id="d5939-155">[STArea &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STExteriorRing &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type) [STNumInteriorRing &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type) [STInteriorRingN &#40;](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type) тип данных geometry&#41;[STCentroid &#40;геометрическая тип данных](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [&#41;STPointOnSurface &#40;тип данных](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) Geometry&#41;[многоугольные](../spatial/polygon.md) [пространственные данные &#40;SQL Server](../spatial/spatial-data-sql-server.md)&#41;[STIsValid &#40;geography тип данных&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STIsValid &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)</span><span class="sxs-lookup"><span data-stu-id="d5939-155">[STArea &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STExteriorRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type) [STNumInteriorRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type) [STInteriorRingN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type) [STCentroid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [MultiPolygon](../spatial/polygon.md) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)</span></span>


