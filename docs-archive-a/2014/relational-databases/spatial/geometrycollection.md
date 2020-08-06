---
title: GeometryCollection | Документация Майкрософт
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- GeomCollection geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 4445c0d9-a66b-4d7c-88e4-a66fa6f7d9fd
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 71d2234a9b73b7647554e364fe3864f089a47a0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668194"
---
# <a name="geometrycollection"></a><span data-ttu-id="18ec7-102">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="18ec7-102">GeometryCollection</span></span>
  <span data-ttu-id="18ec7-103">Тип данных `GeometryCollection` представляет собой коллекцию экземпляров `geometry` или `geography`.</span><span class="sxs-lookup"><span data-stu-id="18ec7-103">A `GeometryCollection` is a collection of zero or more `geometry` or `geography` instances.</span></span> <span data-ttu-id="18ec7-104">Коллекция `GeometryCollection` может быть пустой.</span><span class="sxs-lookup"><span data-stu-id="18ec7-104">A `GeometryCollection` can be empty.</span></span>  
  
## <a name="geometrycollection-instances"></a><span data-ttu-id="18ec7-105">Экземпляры GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="18ec7-105">GeometryCollection Instances</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="18ec7-106">Принимаемые экземпляры</span><span class="sxs-lookup"><span data-stu-id="18ec7-106">Accepted Instances</span></span>  
 <span data-ttu-id="18ec7-107">Чтобы экземпляр `GeometryCollection` был принимаемым, он должен быть пустым экземпляром `GeometryCollection` или все экземпляры, составляющие экземпляр `GeometryCollection`, должны быть принимаемыми экземплярами.</span><span class="sxs-lookup"><span data-stu-id="18ec7-107">For a `GeometryCollection` instance to be accepted, it must either be an empty `GeometryCollection` instance or all the instances comprising the `GeometryCollection` instance must be accepted instances.</span></span> <span data-ttu-id="18ec7-108">В следующем примере показаны принимаемые экземпляры.</span><span class="sxs-lookup"><span data-stu-id="18ec7-108">The following example shows accepted instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
 <span data-ttu-id="18ec7-109">В следующем примере возникает исключение `System.FormatException`, так как экземпляр `LinesString` в экземпляре `GeometryCollection` не является принимаемым.</span><span class="sxs-lookup"><span data-stu-id="18ec7-109">The following example throws a `System.FormatException` because the `LinesString` instance in the `GeometryCollection` instance is not accepted.</span></span>  
  
```  
DECLARE @g geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1), POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
### <a name="valid-instances"></a><span data-ttu-id="18ec7-110">Допустимые экземпляры</span><span class="sxs-lookup"><span data-stu-id="18ec7-110">Valid Instances</span></span>  
 <span data-ttu-id="18ec7-111">Экземпляр `GeometryCollection` является допустимым, если допустимы все экземпляры, составляющие экземпляр `GeometryCollection`.</span><span class="sxs-lookup"><span data-stu-id="18ec7-111">A `GeometryCollection` instance is valid when all instances that comprise the `GeometryCollection` instance are valid.</span></span> <span data-ttu-id="18ec7-112">В следующем примере показаны три допустимых экземпляра `GeometryCollection` и один недопустимый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="18ec7-112">The following shows three valid `GeometryCollection` instances and one instance that is not valid.</span></span>  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g4 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, 1 -5, -5 5, -5 -1, -1 -1)))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 <span data-ttu-id="18ec7-113">`@g4` не является допустимым, так как экземпляр `Polygon` в экземпляре `GeometryCollection` не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="18ec7-113">`@g4` is not valid because the `Polygon` instance in the `GeometryCollection` instance is not valid.</span></span>  
  
 <span data-ttu-id="18ec7-114">Дополнительные сведения о принимаемых и допустимых экземплярах см. в разделах [Point](point.md), [MultiPoint](multipoint.md), [LineString](linestring.md), [MultiLineString](multilinestring.md), [Polygon](polygon.md)и [MultiPolygon](multipolygon.md).</span><span class="sxs-lookup"><span data-stu-id="18ec7-114">For more information on accepted and valid instances, see [Point](point.md), [MultiPoint](multipoint.md), [LineString](linestring.md), [MultiLineString](multilinestring.md), [Polygon](polygon.md), and [MultiPolygon](multipolygon.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="18ec7-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="18ec7-115">Examples</span></span>  
 <span data-ttu-id="18ec7-116">В следующем примере создается коллекция экземпляров `geometry``GeometryCollection` ; значения по оси Z в объекте с идентификатором SRID 1 содержат один экземпляр `Point` и один экземпляр `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="18ec7-116">The following example instantiates a `geometry``GeometryCollection` with Z values in SRID 1 containing a `Point` instance and a `Polygon` instance.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomCollFromText('GEOMETRYCOLLECTION(POINT(3 3 1), POLYGON((0 0 2, 1 10 3, 1 0 4, 0 0 2)))', 1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="18ec7-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="18ec7-117">See Also</span></span>  
 [<span data-ttu-id="18ec7-118">Пространственные данные (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="18ec7-118">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
