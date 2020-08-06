---
title: MultiLineString | Документация Майкрософт
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiLineString geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 95deeefe-d6c5-4a11-b347-379e4486e7b7
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: fdd093d99d055df8e15fc22e3e570e6805e35d6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668184"
---
# <a name="multilinestring"></a><span data-ttu-id="10b03-102">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="10b03-102">MultiLineString</span></span>
  <span data-ttu-id="10b03-103">`MultiLineString`— Это коллекция из нуля или более `geometry` экземпляров или **geographyLineString** .</span><span class="sxs-lookup"><span data-stu-id="10b03-103">A `MultiLineString` is a collection of zero or more `geometry` or **geographyLineString** instances.</span></span>  
  
## <a name="multilinestring-instances"></a><span data-ttu-id="10b03-104">Экземпляры MultiLineString</span><span class="sxs-lookup"><span data-stu-id="10b03-104">MultiLineString instances</span></span>  
 <span data-ttu-id="10b03-105">На рисунке ниже приведены примеры экземпляров `MultiLineString`.</span><span class="sxs-lookup"><span data-stu-id="10b03-105">The illustration below shows examples of `MultiLineString` instances.</span></span>  
  
 <span data-ttu-id="10b03-106">![Примеры объектов MultiLineString типа geometry](../../database-engine/media/multilinestring.gif "Примеры объектов MultiLineString типа geometry")</span><span class="sxs-lookup"><span data-stu-id="10b03-106">![Examples of geometry MultiLineString instances](../../database-engine/media/multilinestring.gif "Examples of geometry MultiLineString instances")</span></span>  
  
 <span data-ttu-id="10b03-107">На рисунке представлены:</span><span class="sxs-lookup"><span data-stu-id="10b03-107">As shown in the illustration:</span></span>  
  
-   <span data-ttu-id="10b03-108">На рисунке 1 показан простой `MultiLineString` экземпляр, граница которого состоит из четырех конечных точек двух `LineString` элементов.</span><span class="sxs-lookup"><span data-stu-id="10b03-108">Figure 1 is a simple `MultiLineString` instance whose boundary is the four endpoints of its two `LineString` elements.</span></span>  
  
-   <span data-ttu-id="10b03-109">Изображение 2 представляет простой экземпляр `MultiLineString`, поскольку пересекаются только конечные точки элементов `LineString`.</span><span class="sxs-lookup"><span data-stu-id="10b03-109">Figure 2 is a simple `MultiLineString` instance because only the endpoints of the `LineString` elements intersect.</span></span> <span data-ttu-id="10b03-110">Граница образована двумя неперекрывающимися конечными точками.</span><span class="sxs-lookup"><span data-stu-id="10b03-110">The boundary is the two non-overlapping endpoints.</span></span>  
  
-   <span data-ttu-id="10b03-111">Изображение 3 представляет непростой экземпляр `MultiLineString`, поскольку имеется пересечение внутренней части одного из элементов `LineString` этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="10b03-111">Figure 3 is a nonsimple `MultiLineString` instance because the interior of one of its `LineString` elements is intersected.</span></span> <span data-ttu-id="10b03-112">Границей данного экземпляра `MultiLineString` являются четыре конечные точки.</span><span class="sxs-lookup"><span data-stu-id="10b03-112">The boundary of this `MultiLineString` instance is the four endpoints.</span></span>  
  
-   <span data-ttu-id="10b03-113">На рисунке 4 представлен отличный от простого незамкнутый экземпляр объекта `MultiLineString`.</span><span class="sxs-lookup"><span data-stu-id="10b03-113">Figure 4 is a nonsimple, nonclosed `MultiLineString` instance.</span></span>  
  
-   <span data-ttu-id="10b03-114">Изображение 5 представляет простой, незамкнутый экземпляр `MultiLineString`.</span><span class="sxs-lookup"><span data-stu-id="10b03-114">Figure 5 is a simple, nonclosed `MultiLineString`.</span></span> <span data-ttu-id="10b03-115">Он не закрыт, поскольку его `LineStrings` элементы не закрыты.</span><span class="sxs-lookup"><span data-stu-id="10b03-115">It is not closed because its `LineStrings` elements are not closed.</span></span> <span data-ttu-id="10b03-116">Экземпляр является простым, поскольку внутренние стороны экземпляров `LineStrings` не пересекаются.</span><span class="sxs-lookup"><span data-stu-id="10b03-116">It is simple because none of the interiors of any of the `LineStrings` instances intersect.</span></span>  
  
-   <span data-ttu-id="10b03-117">Изображение 6 представляет простой, замкнутый экземпляр `MultiLineString`.</span><span class="sxs-lookup"><span data-stu-id="10b03-117">Figure 6 is a simple, closed `MultiLineString` instance.</span></span> <span data-ttu-id="10b03-118">Экземпляр является замкнутым, поскольку все его элементы замкнуты.</span><span class="sxs-lookup"><span data-stu-id="10b03-118">It is closed because all its elements are closed.</span></span> <span data-ttu-id="10b03-119">Экземпляр является простым, поскольку внутренние области его элементов не пересекаются.</span><span class="sxs-lookup"><span data-stu-id="10b03-119">It is simple because none of its elements intersect at the interiors.</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="10b03-120">Правильные экземпляры</span><span class="sxs-lookup"><span data-stu-id="10b03-120">Accepted instances</span></span>  
 <span data-ttu-id="10b03-121">Чтобы экземпляр `MultiLineString` был принят, он должен либо быть пустым, либо содержать только принимаемые экземпляры `LineString`.</span><span class="sxs-lookup"><span data-stu-id="10b03-121">For a `MultiLineString` instance to be accepted it must either be empty or comprised of only `LineString` intances that are accepted.</span></span> <span data-ttu-id="10b03-122">Дополнительные сведения о принятых `LineString` экземплярах см. в разделе [LineString](../spatial/linestring.md).</span><span class="sxs-lookup"><span data-stu-id="10b03-122">For more information on accepted `LineString` instances, see [LineString](../spatial/linestring.md).</span></span> <span data-ttu-id="10b03-123">В следующих примерах показаны принятые экземпляры `MultiLineString`.</span><span class="sxs-lookup"><span data-stu-id="10b03-123">The following are examples of accepted `MultiLineString` instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
```  
  
 <span data-ttu-id="10b03-124">Следующий пример формирует исключение `System.FormatException`, так как второй экземпляр `LineString` недействителен.</span><span class="sxs-lookup"><span data-stu-id="10b03-124">The following example throws a `System.FormatException` because the second `LineString` instance is not valid.</span></span>  
  
```  
DECLARE @g geometry = 'MULTILINESTRING((1 1, 3 5),(-5 3))';  
```  
  
### <a name="valid-instances"></a><span data-ttu-id="10b03-125">Допустимые экземпляры</span><span class="sxs-lookup"><span data-stu-id="10b03-125">Valid instances</span></span>  
 <span data-ttu-id="10b03-126">Чтобы экземпляр `MultiLineString` был действителен, он должен соответствовать следующим критериям.</span><span class="sxs-lookup"><span data-stu-id="10b03-126">For a `MultiLineString` instance to be valid it must meet the following criteria:</span></span>  
  
1.  <span data-ttu-id="10b03-127">Все экземпляры, составляющие экземпляр `MultiLineString`, должны быть действительными экземплярами `LineString`.</span><span class="sxs-lookup"><span data-stu-id="10b03-127">All instances comprising the `MultiLineString` instance must be valid `LineString` instances.</span></span>  
  
2.  <span data-ttu-id="10b03-128">Никакие два экземпляра `LineString`, составляющие экземпляр `MultiLineString`, не могут перекрывать сами себя на интервале.</span><span class="sxs-lookup"><span data-stu-id="10b03-128">No two `LineString` instances comprising the `MultiLineString` instance may overlap over an interval.</span></span> <span data-ttu-id="10b03-129">Экземпляры `LineString` могут взаимодействовать или соприкасаться только с собой или с другими экземплярами `LineString` в конечном числе точек.</span><span class="sxs-lookup"><span data-stu-id="10b03-129">The `LineString` instances can only intersect or touch themselves or other `LineString` instances at a finite number of points.</span></span>  
  
 <span data-ttu-id="10b03-130">В следующем примере показаны три действительных экземпляра `MultiLineString` и один экземпляр `MultiLineString`, который недействителен.</span><span class="sxs-lookup"><span data-stu-id="10b03-130">The following example shows three valid `MultiLineString` instances and one `MultiLineString` instance that is not valid.</span></span>  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 <span data-ttu-id="10b03-131">Значение `@g4` является недействительным, так как второй экземпляр `LineString` пересекается с первым экземпляром `LineString` на интервале.</span><span class="sxs-lookup"><span data-stu-id="10b03-131">`@g4` is not valid because the second `LineString` instance overlaps the first `LineString` instance at an interval.</span></span> <span data-ttu-id="10b03-132">Они соприкасаются в бесконечном количестве точек.</span><span class="sxs-lookup"><span data-stu-id="10b03-132">They touch at an infinite number of points.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="10b03-133">Примеры</span><span class="sxs-lookup"><span data-stu-id="10b03-133">Examples</span></span>  
 <span data-ttu-id="10b03-134">В следующем примере создается простой экземпляр `geometry``MultiLineString` , содержащий два элемента `LineString` со значением SRID 0.</span><span class="sxs-lookup"><span data-stu-id="10b03-134">The following example creates a simple `geometry``MultiLineString` instance containing two `LineString` elements with the SRID 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
```  
  
 <span data-ttu-id="10b03-135">Чтобы создать экземпляр с другим значением SRID, используйте функции `STGeomFromText()` или `STMLineStringFromText()`.</span><span class="sxs-lookup"><span data-stu-id="10b03-135">To instantiate this instance with a different SRID, use `STGeomFromText()` or `STMLineStringFromText()`.</span></span> <span data-ttu-id="10b03-136">Можно также использовать функцию `Parse()` , а затем изменить SRID, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="10b03-136">You can also use `Parse()` and then modify the SRID, as shown in the following example.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
SET @g.STSrid = 13;  
```  
  
## <a name="see-also"></a><span data-ttu-id="10b03-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="10b03-137">See Also</span></span>  
 <span data-ttu-id="10b03-138">[STLength (тип данных geometry)](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="10b03-138">[STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) </span></span>  
 <span data-ttu-id="10b03-139">[STIsClosed (тип данных geometry)](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="10b03-139">[STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) </span></span>  
 <span data-ttu-id="10b03-140">[LineString](../spatial/linestring.md) </span><span class="sxs-lookup"><span data-stu-id="10b03-140">[LineString](../spatial/linestring.md) </span></span>  
 [<span data-ttu-id="10b03-141">Пространственные данные (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="10b03-141">Spatial Data &#40;SQL Server&#41;</span></span>](../spatial/spatial-data-sql-server.md)  
  
  
