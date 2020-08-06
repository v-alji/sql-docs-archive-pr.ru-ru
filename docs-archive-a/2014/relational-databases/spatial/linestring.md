---
title: LineString | Документация Майкрософт
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- LineString geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: e50d0b86-8b31-4285-be71-ad05c7712cbd
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 5a0f77959cfe4492eca6c38951ba2868452d41ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668192"
---
# <a name="linestring"></a><span data-ttu-id="e53a2-102">LineString</span><span class="sxs-lookup"><span data-stu-id="e53a2-102">LineString</span></span>
  <span data-ttu-id="e53a2-103">`LineString` является одномерным объектом, представляющим последовательность точек и соединяющих их линейных сегментов.</span><span class="sxs-lookup"><span data-stu-id="e53a2-103">A `LineString` is a one-dimensional object representing a sequence of points and the line segments connecting them.</span></span>

## <a name="linestring-instances"></a><span data-ttu-id="e53a2-104">Экземпляры LineString</span><span class="sxs-lookup"><span data-stu-id="e53a2-104">LineString Instances</span></span>
 <span data-ttu-id="e53a2-105">На рисунке ниже приведены примеры экземпляров `LineString`.</span><span class="sxs-lookup"><span data-stu-id="e53a2-105">The illustration below shows examples of `LineString` instances.</span></span>

 <span data-ttu-id="e53a2-106">![Примеры объектов LineString типа geometry](../../database-engine/media/linestring.gif "Примеры объектов LineString типа geometry")</span><span class="sxs-lookup"><span data-stu-id="e53a2-106">![Examples of geometry LineString instances](../../database-engine/media/linestring.gif "Examples of geometry LineString instances")</span></span>

 <span data-ttu-id="e53a2-107">На рисунке представлены:</span><span class="sxs-lookup"><span data-stu-id="e53a2-107">As shown in the illustration:</span></span>

-   <span data-ttu-id="e53a2-108">на рисунке 1 представлен простой незамкнутый экземпляр объекта `LineString`;</span><span class="sxs-lookup"><span data-stu-id="e53a2-108">Figure 1 is a simple, nonclosed `LineString` instance.</span></span>

-   <span data-ttu-id="e53a2-109">на рисунке 2 представлен отличный от простого незамкнутый экземпляр объекта `LineString`;</span><span class="sxs-lookup"><span data-stu-id="e53a2-109">Figure 2 is a nonsimple, nonclosed `LineString` instance.</span></span>

-   <span data-ttu-id="e53a2-110">на рисунке 3 продемонстрирован простой замкнутый экземпляр объекта `LineString`, представляющий собой кольцо;</span><span class="sxs-lookup"><span data-stu-id="e53a2-110">Figure 3 is a closed, simple `LineString` instance, and therefore is a ring.</span></span>

-   <span data-ttu-id="e53a2-111">на рисунке 4 продемонстрирован замкнутый непростой экземпляр объекта `LineString`, не являющийся кольцом.</span><span class="sxs-lookup"><span data-stu-id="e53a2-111">Figure 4 is a closed, nonsimple `LineString` instance, and therefore is not a ring.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="e53a2-112">Принимаемые экземпляры</span><span class="sxs-lookup"><span data-stu-id="e53a2-112">Accepted Instances</span></span>
 <span data-ttu-id="e53a2-113">Принятые экземпляры `LineString` могут быть введены в переменную геометрии, но они могут быть недействительными экземплярами `LineString`.</span><span class="sxs-lookup"><span data-stu-id="e53a2-113">Accepted `LineString` instances can be input into a geometry variable, but they may not be valid `LineString` instances.</span></span> <span data-ttu-id="e53a2-114">Для принятия экземпляра `LineString` должны соблюдаться следующие критерии.</span><span class="sxs-lookup"><span data-stu-id="e53a2-114">The following criteria must be met for a `LineString` instance to be accepted.</span></span> <span data-ttu-id="e53a2-115">Экземпляр должен быть сформирован по меньшей мере двумя точками или же должен быть пустым.</span><span class="sxs-lookup"><span data-stu-id="e53a2-115">The instance must be formed of at least two points or it must be empty.</span></span> <span data-ttu-id="e53a2-116">Следующие экземпляры LineString допустимы.</span><span class="sxs-lookup"><span data-stu-id="e53a2-116">The following LineString instances are accepted.</span></span>

```
DECLARE @g1 geometry = 'LINESTRING EMPTY';
DECLARE @g2 geometry = 'LINESTRING(1 1,2 3,4 8, -6 3)';
DECLARE @g3 geometry = 'LINESTRING(1 1, 1 1)';
```

 <span data-ttu-id="e53a2-117">`@g3` показывает, что, хотя экземпляр `LineString` допустим, он недействителен.</span><span class="sxs-lookup"><span data-stu-id="e53a2-117">`@g3` shows that a `LineString` instance can be accepted, but not valid.</span></span>

 <span data-ttu-id="e53a2-118">Следующий экземпляр `LineString` недопустим.</span><span class="sxs-lookup"><span data-stu-id="e53a2-118">The following `LineString` instance is not accepted.</span></span> <span data-ttu-id="e53a2-119">Он выдаст исключение `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="e53a2-119">It will throw a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'LINESTRING(1 1)';
```

### <a name="valid-instances"></a><span data-ttu-id="e53a2-120">Допустимые экземпляры</span><span class="sxs-lookup"><span data-stu-id="e53a2-120">Valid Instances</span></span>
 <span data-ttu-id="e53a2-121">Чтобы экземпляр `LineString` был действителен, он должен соответствовать следующим критериям.</span><span class="sxs-lookup"><span data-stu-id="e53a2-121">For a `LineString` instance to be valid it must meet the following criteria.</span></span>

1.  <span data-ttu-id="e53a2-122">Экземпляр `LineString` должен быть принят.</span><span class="sxs-lookup"><span data-stu-id="e53a2-122">The `LineString` instance must be accepted.</span></span>

2.  <span data-ttu-id="e53a2-123">Если экземпляр `LineString` не является пустым, он должен содержать по меньшей мере две различные точки.</span><span class="sxs-lookup"><span data-stu-id="e53a2-123">If a `LineString` instance is not empty then it must contain at least two distinct points.</span></span>

3.  <span data-ttu-id="e53a2-124">Экземпляр `LineString` не может перекрывать сам себя на интервале из двух или более последовательных точек.</span><span class="sxs-lookup"><span data-stu-id="e53a2-124">The `LineString` instance cannot overlap itself over an interval of two or more consecutive points.</span></span>

 <span data-ttu-id="e53a2-125">Следующие экземпляры `LineString` являются действительными.</span><span class="sxs-lookup"><span data-stu-id="e53a2-125">The following `LineString` instances are valid.</span></span>

```
DECLARE @g1 geometry= 'LINESTRING EMPTY';
DECLARE @g2 geometry= 'LINESTRING(1 1, 3 3)';
DECLARE @g3 geometry= 'LINESTRING(1 1, 3 3, 2 4, 2 0)';
DECLARE @g4 geometry= 'LINESTRING(1 1, 3 3, 2 4, 2 0, 1 1)';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();

```

 <span data-ttu-id="e53a2-126">Следующие экземпляры `LineString` не являются действительными.</span><span class="sxs-lookup"><span data-stu-id="e53a2-126">The following `LineString` instances are not valid.</span></span>

```
DECLARE @g1 geometry = 'LINESTRING(1 4, 3 4, 2 4, 2 0)';
DECLARE @g2 geometry = 'LINESTRING(1 1, 1 1)';
SELECT @g1.STIsValid(), @g2.STIsValid();
```

> [!WARNING]
>  <span data-ttu-id="e53a2-127">Определение пересечений `LineString` основано на расчетах с плавающей запятой, которые не являются точными.</span><span class="sxs-lookup"><span data-stu-id="e53a2-127">The detection of `LineString` overlaps is based on floating-point calculations, which are not exact.</span></span>

## <a name="examples"></a><span data-ttu-id="e53a2-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="e53a2-128">Examples</span></span>
 <span data-ttu-id="e53a2-129">В следующем примере показано, как создать экземпляр `geometry``LineString` с тремя точками и значением SRID, равным 0:</span><span class="sxs-lookup"><span data-stu-id="e53a2-129">The following example shows how to create a `geometry``LineString` instance with three points and an SRID of 0:</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(1 1, 2 4, 3 9)', 0);
```

 <span data-ttu-id="e53a2-130">Каждая точка экземпляра `LineString` может содержать значения Z (уровень) и M (мера).</span><span class="sxs-lookup"><span data-stu-id="e53a2-130">Each point in the `LineString` instance may contain Z (elevation) and M (measure) values.</span></span> <span data-ttu-id="e53a2-131">В данном примере значения М добавляются к экземпляру `LineString` , созданному в примере выше.</span><span class="sxs-lookup"><span data-stu-id="e53a2-131">This example adds M values to the `LineString` instance created in the example above.</span></span> <span data-ttu-id="e53a2-132">M и Z могут принимать значения NULL.</span><span class="sxs-lookup"><span data-stu-id="e53a2-132">M and Z can be null values.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(1 1 NULL 0, 2 4 NULL 12.3, 3 9 NULL 24.5)', 0);
```

 <span data-ttu-id="e53a2-133">В следующем примере показано, как создать экземпляр `geometry LineString` с двумя одинаковыми точками.</span><span class="sxs-lookup"><span data-stu-id="e53a2-133">The following example shows how to create a `geometry LineString` instance with two points that are the same.</span></span> <span data-ttu-id="e53a2-134">Вызов `IsValid` указывает, что экземпляр `LineString` не является действительным, а вызов `MakeValid` преобразует экземпляр `LineString` в `Point`.</span><span class="sxs-lookup"><span data-stu-id="e53a2-134">A call to `IsValid` indicates that the `LineString` instance is not valid and a call to `MakeValid` will convert the `LineString` instance into a `Point`.</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::STGeomFromText('LINESTRING(1 3, 1 3)',0);
IF @g.STIsValid() = 1
  BEGIN
     SELECT @g.ToString() + ' is a valid LineString.';  
  END
ELSE
  BEGIN
     SELECT @g.ToString() + ' is not a valid LineString.';
     SET @g = @g.MakeValid();
     SELECT @g.ToString() + ' is a valid Point.';  
  END

```

 <span data-ttu-id="e53a2-135">Вышеприведенный фрагмент кода вернет следующее:</span><span class="sxs-lookup"><span data-stu-id="e53a2-135">The above code snippet will return the following:</span></span>

```
LINESTRING(1 3, 1 3) is not a valid LineString
POINT(1 3) is a valid Point.
```

## <a name="see-also"></a><span data-ttu-id="e53a2-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="e53a2-136">See Also</span></span>
 <span data-ttu-id="e53a2-137">[STLength &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) тип данных geometry&#41;STNumPoints [&#40;геометрическая](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) тип данных&#41;STIsRing [&#40;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) Geometry Data Type&#41;[STIsClosed &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;тип данных geometry&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [пространственные данные &#40;](../spatial/spatial-data-sql-server.md) SQL Server</span><span class="sxs-lookup"><span data-stu-id="e53a2-137">[STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)</span></span>


