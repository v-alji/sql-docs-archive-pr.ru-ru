---
title: CompoundCurve | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: ae357f9b-e3e2-4cdf-af02-012acda2e466
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 6a899bbe9a17a64083592e1078e8cac93365f02b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655575"
---
# <a name="compoundcurve"></a><span data-ttu-id="bc350-102">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="bc350-102">CompoundCurve</span></span>
  <span data-ttu-id="bc350-103">Объект `CompoundCurve` — это набор из нуля или большего количества непрерывных экземпляров `CircularString` или `LineString` геометрического или географического типов.</span><span class="sxs-lookup"><span data-stu-id="bc350-103">A `CompoundCurve` is a collection of zero or more continuous `CircularString` or `LineString` instances of either geometry or geography types.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="bc350-104">Подробное описание и примеры новых пространственных функций в этом выпуске, включая `CompoundCurve` подтип, см. в техническом документе, [новые функции пространственных данных в SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="bc350-104">For a detailed description and examples of the new spatial features in this release, including the `CompoundCurve` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

 <span data-ttu-id="bc350-105">Можно создать пустой экземпляр `CompoundCurve`, но, чтобы экземпляр `CompoundCurve` был допустимым, он должен удовлетворять следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="bc350-105">An empty `CompoundCurve` instance can be instantiated, but for a `CompoundCurve` to be valid it must meet the following criteria:</span></span>

1.  <span data-ttu-id="bc350-106">Должен содержать хотя бы один экземпляр `CircularString` или `LineString`.</span><span class="sxs-lookup"><span data-stu-id="bc350-106">It must contain at least one `CircularString` or `LineString` instance.</span></span>

2.  <span data-ttu-id="bc350-107">Последовательность экземпляров `CircularString` или `LineString` должна быть непрерывной.</span><span class="sxs-lookup"><span data-stu-id="bc350-107">The sequence of `CircularString` or `LineString` instances must be continuous.</span></span>

 <span data-ttu-id="bc350-108">Если объект `CompoundCurve` содержит последовательность из нескольких `CircularString` экземпляров и `LineString` , конечная точка для каждого экземпляра, за исключением последнего экземпляра, должна быть начальной конечной точкой для следующего экземпляра в последовательности.</span><span class="sxs-lookup"><span data-stu-id="bc350-108">If a `CompoundCurve` contains a sequence of multiple `CircularString` and `LineString` instances, the ending endpoint for every instance except for the last instance must be the starting endpoint for the next instance in the sequence.</span></span> <span data-ttu-id="bc350-109">Это означает, что, если конечная точка предыдущего экземпляра в последовательности — (4 3 7 2), начальной точкой следующего экземпляра в последовательности также должна быть (4 3 7 2).</span><span class="sxs-lookup"><span data-stu-id="bc350-109">This means that if the ending point of a prior instance in the sequence is (4 3 7 2), the starting point for the next instance in the sequence must be (4 3 7 2).</span></span> <span data-ttu-id="bc350-110">Обратите внимание, что значения Z (высота) и M (мера) этих точек также должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="bc350-110">Note that Z(elevation) and M(measure) values for the point must also be the same.</span></span> <span data-ttu-id="bc350-111">Если такие две точки отличаются друг от друга, формируется исключение `System.FormatException` .</span><span class="sxs-lookup"><span data-stu-id="bc350-111">If there is a difference in the two points, a `System.FormatException` is thrown.</span></span> <span data-ttu-id="bc350-112">Точки в объектах `CircularString` могут не иметь значение Z или M.</span><span class="sxs-lookup"><span data-stu-id="bc350-112">Points in a `CircularString` do not have to have a Z or M value.</span></span> <span data-ttu-id="bc350-113">Если значения Z или M не заданы для конечной точки предыдущего экземпляра, начальная точка следующего экземпляра также не может иметь значения Z или M.</span><span class="sxs-lookup"><span data-stu-id="bc350-113">If no Z or M values are given for the ending point of the prior instance, the starting point of the next instance cannot include Z or M values.</span></span> <span data-ttu-id="bc350-114">Если конечная точка для предыдущей последовательности — (4 3), начальной точкой для следующей последовательности также должна быть (4 3) и не может быть (4 3 7 2).</span><span class="sxs-lookup"><span data-stu-id="bc350-114">If the ending point for the prior sequence is (4 3), the starting point for the next sequence must be (4 3); it cannot be (4 3 7 2).</span></span> <span data-ttu-id="bc350-115">Все точки в экземпляре `CompoundCurve` должны либо не иметь значения Z, либо иметь одинаковые значения Z.</span><span class="sxs-lookup"><span data-stu-id="bc350-115">All points in a `CompoundCurve` instance must have either no Z value or the same Z value.</span></span>

## <a name="compoundcurve-instances"></a><span data-ttu-id="bc350-116">Экземпляры CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="bc350-116">CompoundCurve instances</span></span>
 <span data-ttu-id="bc350-117">На следующей иллюстрации показаны допустимые типы `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="bc350-117">The following illustration shows valid `CompoundCurve` types.</span></span>

 ![](../../database-engine/media/f278742e-b861-4555-8b51-3d972b7602bf.png "f278742e-b861-4555-8b51-3d972b7602bf")

### <a name="accepted-instances"></a><span data-ttu-id="bc350-118">Правильные экземпляры</span><span class="sxs-lookup"><span data-stu-id="bc350-118">Accepted instances</span></span>
 <span data-ttu-id="bc350-119">Экземпляр `CompoundCurve` является правильным, если он пустой или удовлетворяет следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="bc350-119">`CompoundCurve` instance is accepted if it is an empty instance or meets the following criteria.</span></span>

1.  <span data-ttu-id="bc350-120">Все экземпляры, содержащиеся в `CompoundCurve`, — это правильные экземпляры сегментов окружности.</span><span class="sxs-lookup"><span data-stu-id="bc350-120">All the instances contained by `CompoundCurve` instance are accepted circular arc segment instances.</span></span> <span data-ttu-id="bc350-121">Дополнительные сведения о допустимых экземплярах сегментов окружности см. в разделах [LineString](linestring.md) и [CircularString](circularstring.md).</span><span class="sxs-lookup"><span data-stu-id="bc350-121">For more information on accepted circular arc segment instances, see [LineString](linestring.md) and [CircularString](circularstring.md).</span></span>

2.  <span data-ttu-id="bc350-122">Все сегменты окружности в экземпляре `CompoundCurve` соединены.</span><span class="sxs-lookup"><span data-stu-id="bc350-122">All of the circular arc segments in the `CompoundCurve` instance are connected.</span></span> <span data-ttu-id="bc350-123">Первая точка каждого последующего сегмента совпадает с последней точкой предыдущего сегмента.</span><span class="sxs-lookup"><span data-stu-id="bc350-123">The first point for each succeeding circular arc segment is the same as the last point on the preceding circular arc segment.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="bc350-124">Это касается и координат Z и M.</span><span class="sxs-lookup"><span data-stu-id="bc350-124">This includes the Z and M coordinates.</span></span> <span data-ttu-id="bc350-125">То есть все четыре координаты (X, Y, Z и M) должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="bc350-125">So, all four coordinates X, Y, Z, and M must be the same.</span></span>

3.  <span data-ttu-id="bc350-126">Ни один из вложенных экземпляров не является пустым.</span><span class="sxs-lookup"><span data-stu-id="bc350-126">None of the contained instances are empty instances.</span></span>

 <span data-ttu-id="bc350-127">В следующем примере показаны принятые экземпляры `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="bc350-127">The following example shows accepted `CompoundCurve` instances.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE EMPTY';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (-1 0, 2 0))';
```

 <span data-ttu-id="bc350-128">В следующем примере показаны неправильные экземпляры `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="bc350-128">The following example shows `CompoundCurve` instances that are not accepted.</span></span> <span data-ttu-id="bc350-129">Эти экземпляры формируют исключение `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="bc350-129">These instances throw `System.FormatException`.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE(CIRCULARSTRING EMPTY)';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (1 0, 2 0))';
```

### <a name="valid-instances"></a><span data-ttu-id="bc350-130">Допустимые экземпляры</span><span class="sxs-lookup"><span data-stu-id="bc350-130">Valid instances</span></span>
 <span data-ttu-id="bc350-131">Экземпляр `CompoundCurve` допустим, если удовлетворяет следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="bc350-131">A `CompoundCurve` instance is valid if it meets the following criteria.</span></span>

1.  <span data-ttu-id="bc350-132">Экземпляр `CompoundCurve` является правильным.</span><span class="sxs-lookup"><span data-stu-id="bc350-132">The `CompoundCurve` instance is accepted.</span></span>

2.  <span data-ttu-id="bc350-133">Все экземпляры сегментов окружности, содержащиеся в экземпляре `CompoundCurve`, допустимы.</span><span class="sxs-lookup"><span data-stu-id="bc350-133">All circular arc segment instances contained by the `CompoundCurve` instance are valid instances.</span></span>

 <span data-ttu-id="bc350-134">В следующем примере показаны допустимые экземпляры `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="bc350-134">The following example shows valid `CompoundCurve` instances.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE EMPTY';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (-1 0, 2 0))';
DECLARE @g3 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 1 1, 1 1), (1 1, 3 5, 5 4))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();

```

 <span data-ttu-id="bc350-135">Экземпляр `@g3` допустим, так как допустим экземпляр `CircularString`.</span><span class="sxs-lookup"><span data-stu-id="bc350-135">`@g3` is valid because the `CircularString` instance is valid.</span></span> <span data-ttu-id="bc350-136">Дополнительные сведения о допустимости `CircularString` экземпляра см. в разделе [CircularString](circularstring.md).</span><span class="sxs-lookup"><span data-stu-id="bc350-136">For more information on the validity of the `CircularString` instance, see [CircularString](circularstring.md).</span></span>

 <span data-ttu-id="bc350-137">В следующем примере показаны недопустимые экземпляры `CompoundCurve` .</span><span class="sxs-lookup"><span data-stu-id="bc350-137">The following example shows `CompoundCurve` instances that are not valid.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 1 1, 1 1), (1 1, 3 5, 5 4, 3 5))';
DECLARE @g2 geometry = 'COMPOUNDCURVE((1 1, 1 1))';
DECLARE @g3 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 2 3, 1 1))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="bc350-138">`@g1` недопустим, поскольку второй экземпляр не является допустимым LineString.</span><span class="sxs-lookup"><span data-stu-id="bc350-138">`@g1` is not valid because the second instance is not a valid LineString instance.</span></span> <span data-ttu-id="bc350-139">Экземпляр `@g2` недопустим, поскольку экземпляр `LineString` является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="bc350-139">`@g2` is not valid because the `LineString` instance is not valid.</span></span> <span data-ttu-id="bc350-140">Экземпляр `@g3` недопустим, поскольку экземпляр `CircularString` является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="bc350-140">`@g3` is not valid because the `CircularString` instance is not valid.</span></span> <span data-ttu-id="bc350-141">Дополнительные сведения о допустимых `CircularString` `LineString` экземплярах и см. в разделе [CircularString](circularstring.md) и [LineString](linestring.md).</span><span class="sxs-lookup"><span data-stu-id="bc350-141">For more information on valid `CircularString` and `LineString` instances, see [CircularString](circularstring.md) and [LineString](linestring.md).</span></span>

## <a name="examples"></a><span data-ttu-id="bc350-142">Примеры</span><span class="sxs-lookup"><span data-stu-id="bc350-142">Examples</span></span>

### <a name="a-instantiating-a-geometry-instance-with-an-empty-compooundcurve"></a><span data-ttu-id="bc350-143">A.</span><span class="sxs-lookup"><span data-stu-id="bc350-143">A.</span></span> <span data-ttu-id="bc350-144">Создание экземпляра geometry с пустым экземпляром CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="bc350-144">Instantiating a geometry instance with an empty CompooundCurve</span></span>
 <span data-ttu-id="bc350-145">В следующем примере показано, как создать пустой экземпляр `CompoundCurve` .</span><span class="sxs-lookup"><span data-stu-id="bc350-145">The following example shows how to create an empty `CompoundCurve` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE EMPTY');
```

### <a name="b-declaring-and-instantiating-a-geometry-instance-using-a-compoundcurve-in-the-same-statement"></a><span data-ttu-id="bc350-146">Б.</span><span class="sxs-lookup"><span data-stu-id="bc350-146">B.</span></span> <span data-ttu-id="bc350-147">Объявление и создание экземпляра geometry с экземпляром CompoundCurve в одной инструкции</span><span class="sxs-lookup"><span data-stu-id="bc350-147">Declaring and instantiating a geometry instance using a CompoundCurve in the same statement</span></span>
 <span data-ttu-id="bc350-148">В следующем примере показано, как объявить и инициализировать экземпляр `geometry` с `CompoundCurve`в одной инструкции:</span><span class="sxs-lookup"><span data-stu-id="bc350-148">The following example shows how to declare and initialize a `geometry` instance with a `CompoundCurve`in the same statement:</span></span>

```sql
DECLARE @g geometry = 'COMPOUNDCURVE ((2 2, 0 0),CIRCULARSTRING (0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0))';
```

### <a name="c-instantiating-a-geography-instance-with-a-compoundcurve"></a><span data-ttu-id="bc350-149">В.</span><span class="sxs-lookup"><span data-stu-id="bc350-149">C.</span></span> <span data-ttu-id="bc350-150">Создание экземпляра geography с экземпляром CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="bc350-150">Instantiating a geography instance with a CompoundCurve</span></span>
 <span data-ttu-id="bc350-151">В следующем примере показано объявление и создание экземпляра `geography` с экземпляром `CompoundCurve`:</span><span class="sxs-lookup"><span data-stu-id="bc350-151">The following example shows how to declare and initialize a `geography` instance with a `CompoundCurve`:</span></span>

```sql
DECLARE @g geography = 'COMPOUNDCURVE(CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';
```

### <a name="d-storing-a-square-in-a-compoundcurve-instance"></a><span data-ttu-id="bc350-152">Г.</span><span class="sxs-lookup"><span data-stu-id="bc350-152">D.</span></span> <span data-ttu-id="bc350-153">Хранение квадрата в экземпляре CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="bc350-153">Storing a square in a CompoundCurve instance</span></span>
 <span data-ttu-id="bc350-154">В следующем примере показаны два способа использования экземпляра `CompoundCurve` для хранения квадрата.</span><span class="sxs-lookup"><span data-stu-id="bc350-154">The following example uses two different ways to use a `CompoundCurve` instance to store a square.</span></span>

```sql
DECLARE @g1 geometry, @g2 geometry;
SET @g1 = geometry::Parse('COMPOUNDCURVE((1 1, 1 3), (1 3, 3 3),(3 3, 3 1), (3 1, 1 1))');
SET @g2 = geometry::Parse('COMPOUNDCURVE((1 1, 1 3, 3 3, 3 1, 1 1))');
SELECT @g1.STLength(), @g2.STLength();
```

 <span data-ttu-id="bc350-155">Длина экземпляров `@g1` и `@g2` одинакова.</span><span class="sxs-lookup"><span data-stu-id="bc350-155">The lengths for both `@g1` and `@g2` are the same.</span></span> <span data-ttu-id="bc350-156">На этом примере видно, что экземпляр `CompoundCurve` может хранить один или несколько экземпляров `LineString`.</span><span class="sxs-lookup"><span data-stu-id="bc350-156">Notice from the example that a `CompoundCurve` instance can store one or more instances of `LineString`.</span></span>

### <a name="e-instantiating-a-geometry-instance-using-a-compoundcurve-with-multiple-circularstrings"></a><span data-ttu-id="bc350-157">Д.</span><span class="sxs-lookup"><span data-stu-id="bc350-157">E.</span></span> <span data-ttu-id="bc350-158">Создание экземпляра geometry с помощью экземпляра CompoundCurve с несколькими экземплярами CircularString</span><span class="sxs-lookup"><span data-stu-id="bc350-158">Instantiating a geometry instance using a CompoundCurve with multiple CircularStrings</span></span>
 <span data-ttu-id="bc350-159">В следующем примере показано, как использовать два разных экземпляра `CircularString` для инициализации `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="bc350-159">The following example shows how to use two different `CircularString` instances to initialize a `CompoundCurve`.</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), CIRCULARSTRING(4 2, 2 4, 0 2))');
SELECT @g.STLength();
```

 <span data-ttu-id="bc350-160">В результате получается следующий результат: 12,566370... эквивалентно 4&#x03c0; (4 \* PI).</span><span class="sxs-lookup"><span data-stu-id="bc350-160">This produces the following output: 12.566370... which is the equivalent of 4&#x03c0; (4 \* pi).</span></span> <span data-ttu-id="bc350-161">Экземпляр `CompoundCurve` в этом примере хранит окружность с радиусом 2.</span><span class="sxs-lookup"><span data-stu-id="bc350-161">The `CompoundCurve` instance in the example stores a circle with a radius of 2.</span></span> <span data-ttu-id="bc350-162">В двух предыдущих примерах кода использование экземпляра `CompoundCurve`не требовалось.</span><span class="sxs-lookup"><span data-stu-id="bc350-162">Both of the previous code examples did not have to use a `CompoundCurve`.</span></span> <span data-ttu-id="bc350-163">В первом примере было бы проще использовать экземпляр `LineString` , а во втором было бы проще использовать экземпляр `CircularString` .</span><span class="sxs-lookup"><span data-stu-id="bc350-163">For the first example a `LineString` instance would have been simpler, and a `CircularString` instance would have been simpler for the second example.</span></span> <span data-ttu-id="bc350-164">В следующем примере показано, когда следует использовать экземпляр `CompoundCurve` .</span><span class="sxs-lookup"><span data-stu-id="bc350-164">However, the next example shows where a `CompoundCurve` provides a better alternative.</span></span>

### <a name="f-using-a-compoundcurve-to-store-a-semicircle"></a><span data-ttu-id="bc350-165">Е.</span><span class="sxs-lookup"><span data-stu-id="bc350-165">F.</span></span> <span data-ttu-id="bc350-166">Использование экземпляра CompoundCurve для хранения полуокружности</span><span class="sxs-lookup"><span data-stu-id="bc350-166">Using a CompoundCurve to store a semicircle</span></span>
 <span data-ttu-id="bc350-167">В следующем примере экземпляр `CompoundCurve` используется для хранения полукруга.</span><span class="sxs-lookup"><span data-stu-id="bc350-167">The following example uses a `CompoundCurve` instance to store a semicircle.</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 0 2))');
SELECT @g.STLength();
```

### <a name="g-storing-multiple-circularstring-and-linestring-instances-in-a-compoundcurve"></a><span data-ttu-id="bc350-168">Ж.</span><span class="sxs-lookup"><span data-stu-id="bc350-168">G.</span></span> <span data-ttu-id="bc350-169">Хранение нескольких экземпляров CircularString и LineString в экземпляре CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="bc350-169">Storing multiple CircularString and LineString instances in a CompoundCurve</span></span>
 <span data-ttu-id="bc350-170">В следующем примере показано, как можно хранить несколько экземпляров `CircularString` и `LineString` с помощью `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="bc350-170">The following example shows how multiple `CircularString` and `LineString` instances can be stored by using a `CompoundCurve`.</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::Parse('COMPOUNDCURVE((3 5, 3 3), CIRCULARSTRING(3 3, 5 1, 7 3), (7 3, 7 5), CIRCULARSTRING(7 5, 5 7, 3 5))');
SELECT @g.STLength();
```

### <a name="h-storing-instances-with-z-and-m-values"></a><span data-ttu-id="bc350-171">З.</span><span class="sxs-lookup"><span data-stu-id="bc350-171">H.</span></span> <span data-ttu-id="bc350-172">Хранение экземпляров со значениями Z и M</span><span class="sxs-lookup"><span data-stu-id="bc350-172">Storing instances with Z and M values</span></span>
 <span data-ttu-id="bc350-173">В следующем примере показано, как использовать экземпляр `CompoundCurve` для хранения последовательности экземпляров `CircularString` и `LineString` со значениями Z и M.</span><span class="sxs-lookup"><span data-stu-id="bc350-173">The following example shows how to use a `CompoundCurve` instance to store a sequence of `CircularString` and `LineString` instances with both Z and M values.</span></span>

```sql
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(7 5 4 2, 5 7 4 2, 3 5 4 2), (3 5 4 2, 8 7 4 2))');
```

### <a name="i-illustrating-why-circularstring-instances-must-be-explicitly-declared"></a><span data-ttu-id="bc350-174">И.</span><span class="sxs-lookup"><span data-stu-id="bc350-174">I.</span></span> <span data-ttu-id="bc350-175">Почему необходимо объявлять экземпляры CircularString явно</span><span class="sxs-lookup"><span data-stu-id="bc350-175">Illustrating why CircularString instances must be explicitly declared</span></span>
 <span data-ttu-id="bc350-176">В следующем примере показано, почему экземпляры `CircularString` должны быть явно объявлены.</span><span class="sxs-lookup"><span data-stu-id="bc350-176">The following example shows why `CircularString` instances must be explicitly declared.</span></span> <span data-ttu-id="bc350-177">Программист желает хранить окружность в экземпляре `CompoundCurve` .</span><span class="sxs-lookup"><span data-stu-id="bc350-177">The programmer is trying to store a circle in a `CompoundCurve` instance.</span></span>

```sql
DECLARE @g1 geometry;  
DECLARE @g2 geometry;
SET @g1 = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 2 4, 0 2))');
SELECT 'Circle One', @g1.STLength() AS Perimeter;  -- gives an inaccurate amount
SET @g2 = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), CIRCULARSTRING(4 2, 2 4, 0 2))');
SELECT 'Circle Two', @g2.STLength() AS Perimeter;  -- now we get an accurate amount
```

 <span data-ttu-id="bc350-178">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bc350-178">The output is as follows:</span></span>

```
Circle One11.940039...
Circle Two12.566370...
```

 <span data-ttu-id="bc350-179">Периметр круга 2 составляет примерно 4&#x03c0; (4 \* PI), то есть фактическое значение периметра.</span><span class="sxs-lookup"><span data-stu-id="bc350-179">The perimeter for Circle Two is approximately 4&#x03c0; (4 \* pi), which is the actual value for the perimeter.</span></span> <span data-ttu-id="bc350-180">Напротив, значение периметра окружности 1 очень неточное.</span><span class="sxs-lookup"><span data-stu-id="bc350-180">However, the perimeter for Circle One is significantly inaccurate.</span></span> <span data-ttu-id="bc350-181">Экземпляр `CompoundCurve` окружности 1 хранит один сегмент окружности (ABC) и два линейных сегмента (CD, DA).</span><span class="sxs-lookup"><span data-stu-id="bc350-181">Circle One's `CompoundCurve` instance stores one circular arc segment (ABC) and two line segments (CD, DA).</span></span> <span data-ttu-id="bc350-182">Экземпляр `CompoundCurve` должен хранить два сегмента окружности (ABC, CDA), чтобы определять окружности.</span><span class="sxs-lookup"><span data-stu-id="bc350-182">The `CompoundCurve` instance has to store two circular arc segments (ABC, CDA) to define a circle.</span></span> <span data-ttu-id="bc350-183">Экземпляр `LineString` определяет второй набор точек (4 2, 2 4, 0 2) в экземпляре `CompoundCurve` окружности 1.</span><span class="sxs-lookup"><span data-stu-id="bc350-183">A `LineString` instance defines the second set of points (4 2, 2 4, 0 2) in Circle One's `CompoundCurve` instance.</span></span> <span data-ttu-id="bc350-184">Необходимо явно объявить экземпляр `CircularString` в экземпляре `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="bc350-184">You have to explicitly declare a `CircularString` instance inside a `CompoundCurve`.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc350-185">См. также:</span><span class="sxs-lookup"><span data-stu-id="bc350-185">See Also</span></span>
 <span data-ttu-id="bc350-186">[STIsValid &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STLength &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [LineString](linestring.md) [CircularString](circularstring.md) [пространственные типы данных](spatial-data-types-overview.md) . [точка](point.md) обзора</span><span class="sxs-lookup"><span data-stu-id="bc350-186">[STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [LineString](linestring.md) [CircularString](circularstring.md) [Spatial Data Types Overview](spatial-data-types-overview.md) [Point](point.md)</span></span>


