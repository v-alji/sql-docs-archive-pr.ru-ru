---
title: MultiPolygon | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPolygon geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 2c5db358-2a16-49d9-aac5-a74e86813932
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: f18fd2485c9b2e62586d9f3e81f76f6cf680dbfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668180"
---
# <a name="multipolygon"></a><span data-ttu-id="00124-102">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="00124-102">MultiPolygon</span></span>
  <span data-ttu-id="00124-103">Экземпляр `MultiPolygon` представляет собой коллекцию экземпляров `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="00124-103">A `MultiPolygon` instance is a collection of zero or more `Polygon` instances.</span></span>

## <a name="polygon-instances"></a><span data-ttu-id="00124-104">Экземпляры многоугольников</span><span class="sxs-lookup"><span data-stu-id="00124-104">Polygon Instances</span></span>
 <span data-ttu-id="00124-105">На рисунке ниже приведены примеры экземпляров `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="00124-105">The illustration below shows examples of `MultiPolygon` instances.</span></span>

 <span data-ttu-id="00124-106">![Примеры экземпляров MultiPolygon типа geometry](../../database-engine/media/multipolygon.gif "Примеры экземпляров MultiPolygon типа geometry")</span><span class="sxs-lookup"><span data-stu-id="00124-106">![Examples of geometry MultiPolygon instances](../../database-engine/media/multipolygon.gif "Examples of geometry MultiPolygon instances")</span></span>

 <span data-ttu-id="00124-107">На рисунке представлены:</span><span class="sxs-lookup"><span data-stu-id="00124-107">As shown in the illustration:</span></span>

-   <span data-ttu-id="00124-108">1 — экземпляр типа `MultiPolygon` с двумя элементами `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="00124-108">Figure 1 is a `MultiPolygon` instance with two `Polygon` elements.</span></span> <span data-ttu-id="00124-109">Граница определяется двумя внешними кольцами и тремя внутренними кольцами.</span><span class="sxs-lookup"><span data-stu-id="00124-109">The boundary is defined by the two exterior rings and the three interior rings.</span></span>

-   <span data-ttu-id="00124-110">2 — экземпляр типа `MultiPolygon` с двумя элементами `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="00124-110">Figure 2 is a `MultiPolygon` instance with two `Polygon` elements.</span></span> <span data-ttu-id="00124-111">Граница определяется двумя внешними кольцами и тремя внутренними кольцами.</span><span class="sxs-lookup"><span data-stu-id="00124-111">The boundary is defined by the two exterior rings and the three interior rings.</span></span> <span data-ttu-id="00124-112">Два элемента `Polygon` пересекаются в точке касания.</span><span class="sxs-lookup"><span data-stu-id="00124-112">The two `Polygon` elements intersect at a tangent point.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="00124-113">Принимаемые экземпляры</span><span class="sxs-lookup"><span data-stu-id="00124-113">Accepted Instances</span></span>
 <span data-ttu-id="00124-114">Экземпляр `MultiPolygon` является принимаемым, если истинно одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="00124-114">A `MultiPolygon` instance is accepted one of the following conditions is met.</span></span>

-   <span data-ttu-id="00124-115">Это пустой экземпляр `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="00124-115">It is an empty `MultiPolygon` instance.</span></span>

-   <span data-ttu-id="00124-116">Все экземпляры, составляющие экземпляр `MultiPolygon`, являются принимаемыми экземплярами `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="00124-116">All instances comprising the `MultiPolygon` instance are accepted `Polygon` instances.</span></span> <span data-ttu-id="00124-117">Дополнительные сведения о принятых `Polygon` экземплярах см. в разделе [многоугольник](../spatial/polygon.md).</span><span class="sxs-lookup"><span data-stu-id="00124-117">For more information on accepted `Polygon` instances, see [Polygon](../spatial/polygon.md).</span></span>

 <span data-ttu-id="00124-118">В следующих примерах показаны принимаемые экземпляры `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="00124-118">The following examples show accepted `MultiPolygon` instances.</span></span>

```
DECLARE @g1 geometry = 'MULTIPOLYGON EMPTY';
DECLARE @g2 geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
DECLARE @g3 geometry = 'MULTIPOLYGON(((2 2, 2 -2, -2 -2, -2 2, 2 2)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
```

 <span data-ttu-id="00124-119">В следующем примере показан экземпляр MultiPolygon, который вызывает исключение `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="00124-119">The following example shows a MultiPolygon instance that will throw a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3)))';
```

 <span data-ttu-id="00124-120">Второй экземпляр в MultiPolygon — это экземпляр LineString, не является принимаемым экземпляром Polygon.</span><span class="sxs-lookup"><span data-stu-id="00124-120">The second instance in the MultiPolygon is a LineString instance and not an accepted Polygon instance.</span></span>

### <a name="valid-instances"></a><span data-ttu-id="00124-121">Допустимые экземпляры</span><span class="sxs-lookup"><span data-stu-id="00124-121">Valid Instances</span></span>
 <span data-ttu-id="00124-122">Экземпляр `MultiPolygon` является допустимым, если это пустой экземпляр `MultiPolygon` или удовлетворяет следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="00124-122">A `MultiPolygon` instance is valid if it is an empty `MultiPolygon` instance or if it meets the following criteria.</span></span>

1.  <span data-ttu-id="00124-123">Все экземпляры, составляющие экземпляр `MultiPolygon`, являются допустимыми экземплярами `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="00124-123">All of the instances comprising the `MultiPolygon` instance are valid `Polygon` instances.</span></span> <span data-ttu-id="00124-124">Допустимые `Polygon` экземпляры см. в разделе [многоугольник](../spatial/polygon.md).</span><span class="sxs-lookup"><span data-stu-id="00124-124">For valid `Polygon` instances, see [Polygon](../spatial/polygon.md).</span></span>

2.  <span data-ttu-id="00124-125">Никакие экземпляры `Polygon`, составляющие экземпляр `MultiPolygon`, не перекрываются.</span><span class="sxs-lookup"><span data-stu-id="00124-125">None of the `Polygon` instances comprising the `MultiPolygon` instance overlap.</span></span>

 <span data-ttu-id="00124-126">В следующем примере показаны два допустимых экземпляра `MultiPolygon` и один недопустимый экземпляр `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="00124-126">The following example shows two valid `MultiPolygon` instances and one invalid `MultiPolygon` instance.</span></span>

```
DECLARE @g1 geometry = 'MULTIPOLYGON EMPTY';
DECLARE @g2 geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
DECLARE @g3 geometry = 'MULTIPOLYGON(((2 2, 2 -2, -2 -2, -2 2, 2 2)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="00124-127">Объект `@g2` допустим, поскольку два экземпляра `Polygon` имеют только общую точку касания.</span><span class="sxs-lookup"><span data-stu-id="00124-127">`@g2` is valid because the two `Polygon` instances touch only at a tangent point.</span></span> <span data-ttu-id="00124-128">Объект `@g3` недопустим, поскольку внутренние области экземпляров `Polygon` перекрываются.</span><span class="sxs-lookup"><span data-stu-id="00124-128">`@g3` is not valid because the interiors of the two `Polygon` instances overlap each other.</span></span>

## <a name="examples"></a><span data-ttu-id="00124-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="00124-129">Examples</span></span>
 <span data-ttu-id="00124-130">Следующий пример демонстрирует создание экземпляра `geometry``MultiPolygon` и возвращает второй компонент в формате Well-Known Text (WKT).</span><span class="sxs-lookup"><span data-stu-id="00124-130">The following example shows the creation of a `geometry``MultiPolygon` instance and returns the Well-Known Text (WKT) of the second component.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('MULTIPOLYGON(((0 0, 0 3, 3 3, 3 0, 0 0), (1 1, 1 2, 2 1, 1 1)), ((9 9, 9 10, 10 9, 9 9)))');
SELECT @g.STGeometryN(2).STAsText();
```

 <span data-ttu-id="00124-131">В данном примере создается пустой экземпляр `MultiPolygon` .</span><span class="sxs-lookup"><span data-stu-id="00124-131">This example instantiates an empty `MultiPolygon` instance.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('MULTIPOLYGON EMPTY');
```

## <a name="see-also"></a><span data-ttu-id="00124-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="00124-132">See Also</span></span>
 <span data-ttu-id="00124-133">[Polygon](../spatial/polygon.md) [STArea &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STCentroid &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [пространственные данные](../spatial/spatial-data-sql-server.md) &#40;SQL Server</span><span class="sxs-lookup"><span data-stu-id="00124-133">[Polygon](../spatial/polygon.md) [STArea &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STCentroid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)</span></span>


