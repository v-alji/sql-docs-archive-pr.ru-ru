---
title: CircularString | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 9fe06b03-d98c-4337-9f89-54da98f49f9f
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: c701cdc2e8538a5b91093e17714fd9f6508d1c4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655577"
---
# <a name="circularstring"></a><span data-ttu-id="84fa1-102">CircularString</span><span class="sxs-lookup"><span data-stu-id="84fa1-102">CircularString</span></span>
  <span data-ttu-id="84fa1-103">Объект `CircularString` — это коллекция, состоящая из нуля или большего количества непрерывных круговых сегментов дуги.</span><span class="sxs-lookup"><span data-stu-id="84fa1-103">A `CircularString` is a collection of zero or more continuous circular arc segments.</span></span> <span data-ttu-id="84fa1-104">Сегмент дуги — это сегмент кривой, определяемый тремя точками на двумерной плоскости; первая точка не может совпадать с третьей.</span><span class="sxs-lookup"><span data-stu-id="84fa1-104">A circular arc segment is a curved segment defined by three points in a two-dimensional plane; the first point cannot be the same as the third point.</span></span> <span data-ttu-id="84fa1-105">Если все три точки сегмента дуги лежат на одной прямой, сегмент дуги считается линейным сегментом.</span><span class="sxs-lookup"><span data-stu-id="84fa1-105">If all three points of a circular arc segment are collinear, the arc segment is treated as a line segment.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="84fa1-106">Подробное описание и примеры новых пространственных функций, появившихся в [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , включая `CircularString` подтип, см. в техническом документе [новые функции пространственных данных в SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="84fa1-106">For a detailed description and examples of the new spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including the `CircularString` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

## <a name="circularstring-instances"></a><span data-ttu-id="84fa1-107">Экземпляры CircularString</span><span class="sxs-lookup"><span data-stu-id="84fa1-107">CircularString instances</span></span>
 <span data-ttu-id="84fa1-108">На следующем рисунке показаны допустимые экземпляры `CircularString`.</span><span class="sxs-lookup"><span data-stu-id="84fa1-108">The drawing below shows valid `CircularString` instances:</span></span>

 ![](../../database-engine/media/5ff17e34-b578-4873-9d33-79500940d0bc.png "5ff17e34-b578-4873-9d33-79500940d0bc")

### <a name="accepted-instances"></a><span data-ttu-id="84fa1-109">Правильные экземпляры</span><span class="sxs-lookup"><span data-stu-id="84fa1-109">Accepted instances</span></span>
 <span data-ttu-id="84fa1-110">`CircularString`Экземпляр принимает значение, если он пуст или содержит нечетное число точек, n, где n > 1.</span><span class="sxs-lookup"><span data-stu-id="84fa1-110">A `CircularString` instance is accepted if it is either empty or contains an odd number of points, n, where n > 1.</span></span> <span data-ttu-id="84fa1-111">Следующие экземпляры `CircularString` правильные.</span><span class="sxs-lookup"><span data-stu-id="84fa1-111">The following `CircularString` instances are accepted.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 2 0, 1 1)';
```

 <span data-ttu-id="84fa1-112">Пример `@g3` показывает, что экземпляр `CircularString` может быть правильным, но недопустимым.</span><span class="sxs-lookup"><span data-stu-id="84fa1-112">`@g3` shows that `CircularString` instance may be accepted, but not valid.</span></span> <span data-ttu-id="84fa1-113">Следующее объявление экземпляра CircularString неверно.</span><span class="sxs-lookup"><span data-stu-id="84fa1-113">The following CircularString instance declaration is not accepted.</span></span> <span data-ttu-id="84fa1-114">Это объявление вызывает исключение `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="84fa1-114">This declaration throws a `System.FormatException`.</span></span>

```sql
DECLARE @g geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1)';
```

### <a name="valid-instances"></a><span data-ttu-id="84fa1-115">Допустимые экземпляры</span><span class="sxs-lookup"><span data-stu-id="84fa1-115">Valid instances</span></span>
 <span data-ttu-id="84fa1-116">Допустимый экземпляр `CircularString` должен быть пуст или иметь следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="84fa1-116">A valid `CircularString` instance must be empty or have the following attributes:</span></span>

-   <span data-ttu-id="84fa1-117">Он должен содержать хотя бы один сегмент дуги (то есть не менее трех точек).</span><span class="sxs-lookup"><span data-stu-id="84fa1-117">It must contain at least one circular arc segment (that is, have a minimum of three points).</span></span>

-   <span data-ttu-id="84fa1-118">Последняя конечная точка каждого из отрезков дуги в последовательности, кроме последнего, должна совпадать с первой конечной точкой следующего сегмента в последовательности.</span><span class="sxs-lookup"><span data-stu-id="84fa1-118">The last endpoint for each circular arc segment in the sequence, except for the last segment, must be the first endpoint for the next segment in the sequence.</span></span>

-   <span data-ttu-id="84fa1-119">Количество точек должно быть нечетным.</span><span class="sxs-lookup"><span data-stu-id="84fa1-119">It must have an odd number of points.</span></span>

-   <span data-ttu-id="84fa1-120">Он не должен перекрываться собой.</span><span class="sxs-lookup"><span data-stu-id="84fa1-120">It cannot overlap itself over an interval.</span></span>

-   <span data-ttu-id="84fa1-121">Хотя экземпляры `CircularString` могут содержать линейные сегменты, эти линейные сегменты должны определяться тремя лежащими на одной прямой точками.</span><span class="sxs-lookup"><span data-stu-id="84fa1-121">Although `CircularString` instances may contain line segments, these line segments must be defined by three collinear points.</span></span>

 <span data-ttu-id="84fa1-122">В следующем примере показаны допустимые экземпляры `CircularString`.</span><span class="sxs-lookup"><span data-stu-id="84fa1-122">The following example shows valid `CircularString` instances.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1, 0 1)';
DECLARE @g4 geometry = 'CIRCULARSTRING(1 1, 2 2, 2 2)';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(),@g4.STIsValid();
```

 <span data-ttu-id="84fa1-123">Для определения окружности экземпляр `CircularString` должен содержать как минимум два сегмента дуги.</span><span class="sxs-lookup"><span data-stu-id="84fa1-123">A `CircularString` instance must contain at least two circular arc segments to define a complete circle.</span></span> <span data-ttu-id="84fa1-124">Для определения окружности экземпляр `CircularString` не может содержать один сегмент дуги (например, (1 1, 3 1, 1 1)).</span><span class="sxs-lookup"><span data-stu-id="84fa1-124">A `CircularString` instance cannot use a single circular arc segment (such as (1 1, 3 1, 1 1)) to define a complete circle.</span></span> <span data-ttu-id="84fa1-125">Для определения окружности используйте (1 1, 2 2, 3 1, 2 0, 1 1).</span><span class="sxs-lookup"><span data-stu-id="84fa1-125">Use (1 1, 2 2, 3 1, 2 0, 1 1) to define the circle.</span></span>

 <span data-ttu-id="84fa1-126">В следующем примере показаны недопустимые экземпляры CircularString.</span><span class="sxs-lookup"><span data-stu-id="84fa1-126">The following example shows CircularString instances that are not valid.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING(1 1, 2 0, 1 1)';
DECLARE @g2 geometry = 'CIRCULARSTRING(0 0, 0 0, 0 0)';
SELECT @g1.STIsValid(), @g2.STIsValid();
```

### <a name="instances-with-collinear-points"></a><span data-ttu-id="84fa1-127">Экземпляры с точками, лежащими на прямой</span><span class="sxs-lookup"><span data-stu-id="84fa1-127">Instances with collinear points</span></span>
 <span data-ttu-id="84fa1-128">Сегмент дуги будет считаться линейным сегментом в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="84fa1-128">In the following cases a circular arc segment will be treated as a line segment:</span></span>

-   <span data-ttu-id="84fa1-129">Когда все три точки лежат на одной прямой (например, (1 3, 4 4, 7 5)).</span><span class="sxs-lookup"><span data-stu-id="84fa1-129">When all three points are collinear (for example, (1 3, 4 4, 7 5)).</span></span>

-   <span data-ttu-id="84fa1-130">Когда первая и средняя точки совпадают, а третья точка отличается от них (например, (1 3, 1 3, 7 5)).</span><span class="sxs-lookup"><span data-stu-id="84fa1-130">When the first and middle point are the same, but the third point is different (for example, (1 3, 1 3, 7 5)).</span></span>

-   <span data-ttu-id="84fa1-131">Когда средняя и последняя точки совпадают, а первая точка отличается от них (например, (1 3, 4 4, 4 4)).</span><span class="sxs-lookup"><span data-stu-id="84fa1-131">When the middle and last point are the same, but the first point is different (for example, (1 3, 4 4, 4 4)).</span></span>

## <a name="examples"></a><span data-ttu-id="84fa1-132">Примеры</span><span class="sxs-lookup"><span data-stu-id="84fa1-132">Examples</span></span>

### <a name="a-instantiating-a-geometry-instance-with-an-empty-circularstring"></a><span data-ttu-id="84fa1-133">A.</span><span class="sxs-lookup"><span data-stu-id="84fa1-133">A.</span></span> <span data-ttu-id="84fa1-134">Создание экземпляра Geometry с пустым экземпляром CircularString</span><span class="sxs-lookup"><span data-stu-id="84fa1-134">Instantiating a Geometry Instance with an Empty CircularString</span></span>
 <span data-ttu-id="84fa1-135">В этом примере показано, как создать пустой экземпляр `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="84fa1-135">This example shows how to create an empty `CircularString` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING EMPTY');
```

### <a name="b-instantiating-a-geometry-instance-using-a-circularstring-with-one-circular-arc-segment"></a><span data-ttu-id="84fa1-136">Б.</span><span class="sxs-lookup"><span data-stu-id="84fa1-136">B.</span></span> <span data-ttu-id="84fa1-137">Создание экземпляра Geometry с экземпляром CircularString, содержащим один сегмент дуги</span><span class="sxs-lookup"><span data-stu-id="84fa1-137">Instantiating a Geometry Instance Using a CircularString with One Circular Arc Segment</span></span>
 <span data-ttu-id="84fa1-138">В следующем примере показывается создание экземпляра `CircularString` с одним сегментом дуги (полукруга):</span><span class="sxs-lookup"><span data-stu-id="84fa1-138">The following example shows how to create a `CircularString` instance with a single circular arc segment (half-circle):</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry:: STGeomFromText('CIRCULARSTRING(2 0, 1 1, 0 0)', 0);
SELECT @g.ToString();
```

### <a name="c-instantiating-a-geometry-instance-using-a-circularstring-with-multiple-circular-arc-segments"></a><span data-ttu-id="84fa1-139">В.</span><span class="sxs-lookup"><span data-stu-id="84fa1-139">C.</span></span> <span data-ttu-id="84fa1-140">Создание экземпляра Geometry с помощью экземпляра CircularString с несколькими сегментами дуги</span><span class="sxs-lookup"><span data-stu-id="84fa1-140">Instantiating a Geometry Instance Using a CircularString with Multiple Circular Arc Segments</span></span>
 <span data-ttu-id="84fa1-141">В следующем примере показывается создание экземпляра `CircularString` с несколькими сегментами дуги (окружности):</span><span class="sxs-lookup"><span data-stu-id="84fa1-141">The following example shows how to create a `CircularString` instance with more than one circular arc segment (full circle):</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING(2 1, 1 2, 0 1, 1 0, 2 1)');
SELECT 'Circumference = ' + CAST(@g.STLength() AS NVARCHAR(10));  
```

 <span data-ttu-id="84fa1-142">Выводятся следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="84fa1-142">This produces the following output:</span></span>

```
Circumference = 6.28319
```

 <span data-ttu-id="84fa1-143">Сравните вывод, получаемый при использовании `LineString` вместо `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="84fa1-143">Compare the output when `LineString` is used instead of `CircularString`:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(2 1, 1 2, 0 1, 1 0, 2 1)', 0);
SELECT 'Perimeter = ' + CAST(@g.STLength() AS NVARCHAR(10));
```

 <span data-ttu-id="84fa1-144">Выводятся следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="84fa1-144">This produces the following output:</span></span>

```
Perimeter = 5.65685
```

 <span data-ttu-id="84fa1-145">Обратите внимание, что значение для этого `CircularString` примера — близкое к 2&#x03c0; (2 \* PI), то есть фактическая длина окружности.</span><span class="sxs-lookup"><span data-stu-id="84fa1-145">Notice that the value for the `CircularString` example is close to 2&#x03c0; (2 \* pi), which is the actual circumference of the circle.</span></span>

### <a name="d-declaring-and-instantiating-a-geometry-instance-with-a-circularstring-in-the-same-statement"></a><span data-ttu-id="84fa1-146">Г.</span><span class="sxs-lookup"><span data-stu-id="84fa1-146">D.</span></span> <span data-ttu-id="84fa1-147">Объявление и создание экземпляра Geometry с экземпляром CircularString в одной инструкции</span><span class="sxs-lookup"><span data-stu-id="84fa1-147">Declaring and Instantiating a Geometry Instance with a CircularString in the Same Statement</span></span>
 <span data-ttu-id="84fa1-148">В этом фрагменте кода показывается объявление и создание экземпляра `geometry` с экземпляром `CircularString` в одной инструкции:</span><span class="sxs-lookup"><span data-stu-id="84fa1-148">This snippet shows how to declare and instantiate a `geometry` instance with a `CircularString` in the same statement:</span></span>

```sql
DECLARE @g geometry = 'CIRCULARSTRING(0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)';
```

### <a name="e-instantiating-a-geography-instance-with-a-circularstring"></a><span data-ttu-id="84fa1-149">Д.</span><span class="sxs-lookup"><span data-stu-id="84fa1-149">E.</span></span> <span data-ttu-id="84fa1-150">Создание экземпляра Geography с экземпляром CircularString</span><span class="sxs-lookup"><span data-stu-id="84fa1-150">Instantiating a Geography Instance with a CircularString</span></span>
 <span data-ttu-id="84fa1-151">В следующем примере показывается объявление и создание экземпляра `geography` с экземпляром `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="84fa1-151">The following example shows how to declare and instantiate a `geography` instance with a `CircularString`:</span></span>

```sql
DECLARE @g geography = 'CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653)';
```

### <a name="f-instantiating-a-geometry-instance-with-a-circularstring-that-is-a-straight-line"></a><span data-ttu-id="84fa1-152">Е.</span><span class="sxs-lookup"><span data-stu-id="84fa1-152">F.</span></span> <span data-ttu-id="84fa1-153">Создание экземпляра Geometry с экземпляром CircularString, представляющим прямую</span><span class="sxs-lookup"><span data-stu-id="84fa1-153">Instantiating a Geometry Instance with a CircularString that is a Straight Line</span></span>
 <span data-ttu-id="84fa1-154">В следующем примере показывается создание экземпляра `CircularString`, представляющего прямую:</span><span class="sxs-lookup"><span data-stu-id="84fa1-154">The following example shows how to create a `CircularString` instance that is a straight line:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('CIRCULARSTRING(0 0, 1 2, 2 4)', 0);
```

## <a name="see-also"></a><span data-ttu-id="84fa1-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="84fa1-155">See Also</span></span>
 <span data-ttu-id="84fa1-156">[Общие сведения о типах пространственных данных](spatial-data-types-overview.md) . [CompoundCurve](compoundcurve.md) [MakeValid &#40;тип данных geography&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type) [MakeValid &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type) [STIsValid &#40;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) тип данных geometry&#41;STIsValid &#40;[Geography](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) тип данных&#41;STLength &#40;тип данных geometry [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [&#41;STStartPoint &#40;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) геометрическая тип данных&#41;STEndpoint &#40;тип данных geometry [&#41;STPointN &#40;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [тип данных](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [LineString](linestring.md) Geometry [&#41;STNumPoints &#40;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STPointN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type)</span><span class="sxs-lookup"><span data-stu-id="84fa1-156">[Spatial Data Types Overview](spatial-data-types-overview.md) [CompoundCurve](compoundcurve.md) [MakeValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type) [MakeValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [LineString](linestring.md)</span></span>


