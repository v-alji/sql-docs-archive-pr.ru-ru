---
title: CurvePolygon | Документация Майкрософт
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e000a1d8-a049-4542-bfeb-943fd6ab3969
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b90fdbd9a0bc80dfc6a82416d0193b2951fe13ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655570"
---
# <a name="curvepolygon"></a><span data-ttu-id="d5e7d-102">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="d5e7d-102">CurvePolygon</span></span>
  <span data-ttu-id="d5e7d-103">`CurvePolygon` является топологически закрытой областью, определенной внешним ограничивающим кольцом, а также нулем или более внутренних колец.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-103">A `CurvePolygon` is a topologically closed surface defined by an exterior bounding ring and zero or more interior rings</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d5e7d-104">Подробное описание и примеры пространственных функций, появившихся в [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , включая `CurvePolygon` подтип, см. в техническом документе с [новыми пространственными функциями в SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="d5e7d-104">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including the `CurvePolygon` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
 <span data-ttu-id="d5e7d-105">Следующие критерии определяют атрибуты `CurvePolygon` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-105">The following criteria define attributes of a `CurvePolygon` instance:</span></span>  
  
-   <span data-ttu-id="d5e7d-106">Границы экземпляра `CurvePolygon` определяются внешним кольцом и всеми внутренними кольцами.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-106">The boundary of the `CurvePolygon` instance is defined by the exterior ring and all interior rings.</span></span>  
  
-   <span data-ttu-id="d5e7d-107">Внутреннее пространство экземпляра `CurvePolygon` ― это пространство между внешним кольцом и всеми внутренними кольцами.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-107">The interior of the `CurvePolygon` instance is the space between the exterior ring and all of the interior rings.</span></span>  
  
 <span data-ttu-id="d5e7d-108">Экземпляр `CurvePolygon` отличается от экземпляра `Polygon` тем, что экземпляр `CurvePolygon` может содержать следующие сегменты дуги: `CircularString` и `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-108">A `CurvePolygon` instance differs from a `Polygon` instance in that a `CurvePolygon` instance may contain the following circular arc segments: `CircularString` and `CompoundCurve`.</span></span>  
  
## <a name="compoundcurve-instances"></a><span data-ttu-id="d5e7d-109">Экземпляры CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="d5e7d-109">CompoundCurve instances</span></span>  
 <span data-ttu-id="d5e7d-110">На следующей иллюстрации показаны допустимые фигуры `CurvePolygon`.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-110">Illustration below shows valid `CurvePolygon` figures:</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="d5e7d-111">Правильные экземпляры</span><span class="sxs-lookup"><span data-stu-id="d5e7d-111">Accepted instances</span></span>  
 <span data-ttu-id="d5e7d-112">Чтобы экземпляр `CurvePolygon` был принят, он должен быть либо пустым, либо содержать только принимаемые кольца дуги.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-112">For a `CurvePolygon` instance to be accepted, it needs to be either empty or contain only circular arc rings that are accepted.</span></span> <span data-ttu-id="d5e7d-113">Принимаемое кольцо дуги удовлетворяет следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-113">An accepted circular arc ring meets the following requirements.</span></span>  
  
1.  <span data-ttu-id="d5e7d-114">Является принятым экземпляром `LineString`, `CircularString` или `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-114">Is an accepted `LineString`, `CircularString`, or `CompoundCurve` instance.</span></span> <span data-ttu-id="d5e7d-115">Дополнительные сведения о принятых экземплярах см. в разделах [LineString](linestring.md), [CircularString](circularstring.md)и [CompoundCurve](compoundcurve.md).</span><span class="sxs-lookup"><span data-stu-id="d5e7d-115">For more information on accepted instances, see [LineString](linestring.md), [CircularString](circularstring.md), and [CompoundCurve](compoundcurve.md).</span></span>  
  
2.  <span data-ttu-id="d5e7d-116">Имеет минимум четыре точки.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-116">Has at least four points.</span></span>  
  
3.  <span data-ttu-id="d5e7d-117">Начальная и конечная точки имеют одинаковые координаты X и Y.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-117">The start and end point have the same X and Y coordinates.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d5e7d-118">Значения Z и M пропускаются.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-118">Z and M values are ignored.</span></span>  
  
 <span data-ttu-id="d5e7d-119">В следующем примере показаны принятые экземпляры `CurvePolygon`.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-119">The following example shows accepted `CurvePolygon` instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON EMPTY';  
DECLARE @g2 geometry = 'CURVEPOLYGON((0 0, 0 0, 0 0, 0 0))';  
DECLARE @g3 geometry = 'CURVEPOLYGON((0 0 1, 0 0 2, 0 0 3, 0 0 3))'  
DECLARE @g4 geometry = 'CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))';  
DECLARE @g5 geography = 'CURVEPOLYGON((-122.3 47, 122.3 -47, 125.7 -49, 121 -38, -122.3 47))';  
```  
  
 <span data-ttu-id="d5e7d-120">`@g3` принимается, несмотря на то что начальная и конечная точки имеют различные значения Z, поскольку значения Z не учитываются.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-120">`@g3` is accepted even though the start and end points have different Z values because Z values are ignored.</span></span> <span data-ttu-id="d5e7d-121">Экземпляр `@g5` принимается, хотя экземпляр типа `geography` является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-121">`@g5` is accepted even though the `geography` type instance is not valid.</span></span>  
  
 <span data-ttu-id="d5e7d-122">Следующие примеры вызывают исключение `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-122">The following examples throw `System.FormatException`.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON((0 5, 0 0, 0 0, 0 0))';  
DECLARE @g2 geometry = 'CURVEPOLYGON((0 0, 0 0, 0 0))';  
```  
  
 <span data-ttu-id="d5e7d-123">`@g1` не принимается, поскольку не совпадают значения Y для начальной и конечной точек.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-123">`@g1` is not accepted because the start and end points do not have the same Y value.</span></span> <span data-ttu-id="d5e7d-124">`@g2` не принимается, поскольку кольцо содержит недостаточное число точек.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-124">`@g2` is not accepted because the ring does not have enough points.</span></span>  
  
### <a name="valid-instances"></a><span data-ttu-id="d5e7d-125">Допустимые экземпляры</span><span class="sxs-lookup"><span data-stu-id="d5e7d-125">Valid instances</span></span>  
 <span data-ttu-id="d5e7d-126">Чтобы экземпляр `CurvePolygon` был допустимым, внешние и внутренние кольца должны удовлетворять следующим критериям.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-126">For a `CurvePolygon` instance to be valid both exterior and interior rings must meet the following criteria:</span></span>  
  
1.  <span data-ttu-id="d5e7d-127">Они могут соприкасаться только в одной точке касания.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-127">They may only touch at single tangent points.</span></span>  
  
2.  <span data-ttu-id="d5e7d-128">Они не могут пересекать друг друга.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-128">They cannot cross each other.</span></span>  
  
3.  <span data-ttu-id="d5e7d-129">Каждое кольцо должно содержать минимум четыре точки.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-129">Each ring must contain at least four points.</span></span>  
  
4.  <span data-ttu-id="d5e7d-130">Каждое кольцо должно принадлежать к приемлемому типу кривой.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-130">Each ring must be an acceptable curve type.</span></span>  
  
 <span data-ttu-id="d5e7d-131">Кроме того, экземпляры `CurvePolygon` должны удовлетворять особым критериям в зависимости от того, к какому типу данных они принадлежат, `geometry` или `geography`.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-131">`CurvePolygon` instances also need to meet specific criteria depending on whether they are `geometry` or `geography` data types.</span></span>  
  
#### <a name="geometry-data-type"></a><span data-ttu-id="d5e7d-132">Тип данных Geometry</span><span class="sxs-lookup"><span data-stu-id="d5e7d-132">Geometry data type</span></span>  
 <span data-ttu-id="d5e7d-133">Допустимый экземпляр **geometryCurvePolygon** должен иметь следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="d5e7d-133">A valid **geometryCurvePolygon** instance must have the following attributes:</span></span>  
  
1.  <span data-ttu-id="d5e7d-134">Все внутренние кольца должны находиться в пределах внешнего кольца.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-134">All the interior rings must be contained within the exterior ring.</span></span>  
  
2.  <span data-ttu-id="d5e7d-135">Могут иметь несколько внутренних колец, но при этом одно внутреннее кольцо не может содержать другое внутреннее кольцо.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-135">May have multiple interior rings, but an interior ring cannot contain another interior ring.</span></span>  
  
3.  <span data-ttu-id="d5e7d-136">Кольцо не может пересекать само себя или другое кольцо.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-136">No ring can cross itself or another ring.</span></span>  
  
4.  <span data-ttu-id="d5e7d-137">Кольца могут соприкасаться только в одной точке (число точек, где точки соприкасаются, должно быть конечным).</span><span class="sxs-lookup"><span data-stu-id="d5e7d-137">Rings can only touch at single tangent points (number of points where rings touch must be finite).</span></span>  
  
5.  <span data-ttu-id="d5e7d-138">Внутренняя часть многоугольника должна быть замкнутой.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-138">The interior of the polygon must be connected.</span></span>  
  
 <span data-ttu-id="d5e7d-139">В приведенном ниже примере показаны допустимые экземпляры **geometryCurvePolygon** .</span><span class="sxs-lookup"><span data-stu-id="d5e7d-139">The following example shows valid **geometryCurvePolygon** instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON EMPTY';  
DECLARE @g2 geometry = 'CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))';  
SELECT @g1.STIsValid(), @g2.STIsValid();  
```  
  
 <span data-ttu-id="d5e7d-140">К экземплярам CurvePolygon применяются такие правила определения допустимости, как и к экземплярам Polygon, за исключением того, что экземпляры CurvePolygon могут принимать новые типы сегментов дуги.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-140">CurvePolygon instances have the same validity rules as Polygon instances with the exception that CurvePolygon instances may accept the new circular arc segment types.</span></span> <span data-ttu-id="d5e7d-141">Дополнительные примеры допустимых и недопустимых экземпляров приведены в разделе [Polygon](polygon.md).</span><span class="sxs-lookup"><span data-stu-id="d5e7d-141">For more examples of instances that are valid or not valid, see [Polygon](polygon.md).</span></span>  
  
#### <a name="geography-data-type"></a><span data-ttu-id="d5e7d-142">Тип данных Geography</span><span class="sxs-lookup"><span data-stu-id="d5e7d-142">Geography data type</span></span>  
 <span data-ttu-id="d5e7d-143">Допустимый экземпляр **geographyCurvePolygon** должен иметь следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="d5e7d-143">A valid **geographyCurvePolygon** instance must have the following attributes:</span></span>  
  
1.  <span data-ttu-id="d5e7d-144">Внутреннее пространство многоугольника соединяется с использованием правила левой руки.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-144">The interior of the polygon is connected using the left-hand rule.</span></span>  
  
2.  <span data-ttu-id="d5e7d-145">Кольцо не может пересекать само себя или другое кольцо.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-145">No ring can cross itself or another ring.</span></span>  
  
3.  <span data-ttu-id="d5e7d-146">Кольца могут соприкасаться только в одной точке (число точек, где точки соприкасаются, должно быть конечным).</span><span class="sxs-lookup"><span data-stu-id="d5e7d-146">Rings can only touch at single tangent points (number of points where rings touch must be finite).</span></span>  
  
4.  <span data-ttu-id="d5e7d-147">Внутренняя часть многоугольника должна быть замкнутой.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-147">The interior of the polygon must be connected.</span></span>  
  
 <span data-ttu-id="d5e7d-148">В следующем примере показан допустимый экземпляр CurvePolygon типа Geography.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-148">The following example shows a valid geography CurvePolygon instance.</span></span>  
  
```  
DECLARE @g geography = 'CURVEPOLYGON((-122.3 47, 122.3 47, 125.7 49, 121 38, -122.3 47))';  
SELECT @g.STIsValid();  
```  
  
## <a name="examples"></a><span data-ttu-id="d5e7d-149">Примеры</span><span class="sxs-lookup"><span data-stu-id="d5e7d-149">Examples</span></span>  
  
### <a name="a-instantiating-a-geometry-instance-with-an-empty-curvepolygon"></a><span data-ttu-id="d5e7d-150">A.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-150">A.</span></span> <span data-ttu-id="d5e7d-151">Создание экземпляра типа Geometry с пустым CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="d5e7d-151">Instantiating a Geometry Instance with an Empty CurvePolygon</span></span>  
 <span data-ttu-id="d5e7d-152">В этом примере показано, как создать пустой экземпляр `CurvePolygon`:</span><span class="sxs-lookup"><span data-stu-id="d5e7d-152">This example shows how to create an empty `CurvePolygon` instance:</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON EMPTY');  
```  
  
### <a name="b-declaring-and-instantiating-a-geometry-instance-with-a-curvepolygon-in-the-same-statement"></a><span data-ttu-id="d5e7d-153">Б.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-153">B.</span></span> <span data-ttu-id="d5e7d-154">Объявление и создание экземпляра типа Geometry с CurvePolygon в одной и той же инструкции</span><span class="sxs-lookup"><span data-stu-id="d5e7d-154">Declaring and Instantiating a Geometry Instance with a CurvePolygon in the Same Statement</span></span>  
 <span data-ttu-id="d5e7d-155">В этом фрагменте кода показывается объявление и инициализация экземпляра типа Geometry с `CurvePolygon` в одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-155">This code snippet shows how to declare and initialize a geometry instance with a `CurvePolygon` in the same statement:</span></span>  
  
```sql  
DECLARE @g geometry = 'CURVEPOLYGON(CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))'  
```  
  
### <a name="c-instantiating-a-geography-instance-with-a-curvepolygon"></a><span data-ttu-id="d5e7d-156">В.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-156">C.</span></span> <span data-ttu-id="d5e7d-157">Создание экземпляра типа Geometry с CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="d5e7d-157">Instantiating a Geography Instance with a CurvePolygon</span></span>  
 <span data-ttu-id="d5e7d-158">На примере следующего фрагмента кода показано объявление и создание экземпляра `geography` с `CurvePolygon`.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-158">This code snippet shows how to declare and initialize a `geography` instance with a `CurvePolygon`:</span></span>  
  
```sql  
DECLARE @g geography = 'CURVEPOLYGON(CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';  
```  
  
### <a name="d-storing-a-curvepolygon-with-only-an-exterior-bounding-ring"></a><span data-ttu-id="d5e7d-159">Г.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-159">D.</span></span> <span data-ttu-id="d5e7d-160">Сохранение CurvePolygon только с внешним ограничивающим кольцом</span><span class="sxs-lookup"><span data-stu-id="d5e7d-160">Storing a CurvePolygon with Only an Exterior Bounding Ring</span></span>  
 <span data-ttu-id="d5e7d-161">В этом примере показано сохранение простого круга в экземпляре `CurvePolygon` (для определения круга используется только внешнее ограничивающее кольцо):</span><span class="sxs-lookup"><span data-stu-id="d5e7d-161">This example shows how to store a simple circle in a `CurvePolygon` instance (only an exterior bounding ring is used to define the circle):</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))');  
SELECT @g.STArea() AS Area;  
```  
  
### <a name="e-storing-a-curvepolygon-containing-interior-rings"></a><span data-ttu-id="d5e7d-162">Д.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-162">E.</span></span> <span data-ttu-id="d5e7d-163">Сохранение CurvePolygon с внутренними кольцами</span><span class="sxs-lookup"><span data-stu-id="d5e7d-163">Storing a CurvePolygon Containing Interior Rings</span></span>  
 <span data-ttu-id="d5e7d-164">В этом примере в экземпляре `CurvePolygon` создается бублик (для определения бублика используются как внешнее ограничивающее кольцо, так и внутреннее кольцо):</span><span class="sxs-lookup"><span data-stu-id="d5e7d-164">This example creates a donut in a `CurvePolygon` instance (both an exterior bounding ring and an interior ring is used to define the donut):</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 4, 4 0, 8 4, 4 8, 0 4), CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))');  
SELECT @g.STArea() AS Area;  
```  
  
 <span data-ttu-id="d5e7d-165">В этом примере показано, как при использовании внутренних колец экземпляр `CurvePolygon` может быть допустимым и недопустимым.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-165">This example shows both a valid `CurvePolygon` instance and an invalid instance when using interior rings:</span></span>  
  
```sql  
DECLARE @g1 geometry, @g2 geometry;  
SET @g1 = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 5, 5 0, 0 -5, -5 0, 0 5), (-2 2, 2 2, 2 -2, -2 -2, -2 2))');  
IF @g1.STIsValid() = 1  
  BEGIN  
     SELECT @g1.STArea();  
  END  
SET @g2 = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 5, 5 0, 0 -5, -5 0, 0 5), (0 5, 5 0, 0 -5, -5 0, 0 5))');  
IF @g2.STIsValid() = 1  
  BEGIN  
     SELECT @g2.STArea();  
  END  
SELECT @g1.STIsValid() AS G1, @g2.STIsValid() AS G2;  
```  
  
 <span data-ttu-id="d5e7d-166">И в @g1, и в @g2 используется одинаковое внешнее ограничивающее кольцо: круг с радиусом 5, а в качестве внутреннего кольца в обоих экземплярах используется квадрат.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-166">Both @g1 and @g2 use the same exterior bounding ring: a circle with a radius of 5 and they both use a square for an interior ring.</span></span>  <span data-ttu-id="d5e7d-167">Но при этом экземпляр @g1 является допустимым, а @g2 ― нет.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-167">However, the instance @g1 is valid, but the instance @g2 is invalid.</span></span>  <span data-ttu-id="d5e7d-168">Недопустимость @g2 вызвана тем, что внутреннее кольцо делит внутреннее пространство, ограниченное внешним кольцом, на четыре отдельные области.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-168">The reason that @g2 is invalid is that the interior ring splits the interior space bounded by the exterior ring into four separate regions.</span></span>  <span data-ttu-id="d5e7d-169">На следующем чертеже показано, что произошло.</span><span class="sxs-lookup"><span data-stu-id="d5e7d-169">The following drawing shows what occurred:</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e7d-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5e7d-170">See Also</span></span>  
 <span data-ttu-id="d5e7d-171">[Polygon](polygon.md) </span><span class="sxs-lookup"><span data-stu-id="d5e7d-171">[Polygon](polygon.md) </span></span>  
 <span data-ttu-id="d5e7d-172">[CircularString](circularstring.md) </span><span class="sxs-lookup"><span data-stu-id="d5e7d-172">[CircularString](circularstring.md) </span></span>  
 <span data-ttu-id="d5e7d-173">[CompoundCurve](compoundcurve.md) </span><span class="sxs-lookup"><span data-stu-id="d5e7d-173">[CompoundCurve](compoundcurve.md) </span></span>  
 <span data-ttu-id="d5e7d-174">[Справочник по методам типа данных geometry](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d5e7d-174">[geometry Data Type Method Reference](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) </span></span>  
 <span data-ttu-id="d5e7d-175">[Справочник по методам типа данных geography](/sql/t-sql/spatial-geography/spatial-types-geography) </span><span class="sxs-lookup"><span data-stu-id="d5e7d-175">[geography Data Type Method Reference](/sql/t-sql/spatial-geography/spatial-types-geography) </span></span>  
 [<span data-ttu-id="d5e7d-176">Основные сведения о типах пространственных данных</span><span class="sxs-lookup"><span data-stu-id="d5e7d-176">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
  
  
