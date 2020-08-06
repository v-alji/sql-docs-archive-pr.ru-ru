---
title: Точка | Документация Майкрософт
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Point geometry subtype [SQL Server]
- geometry data type [SQL Server], spatial data
ms.assetid: 2a596ec4-8b2f-4962-bcb4-e5c8f77edad5
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4b12069d84e00738e3ddac8c414f33903f4f0999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668177"
---
# <a name="point"></a><span data-ttu-id="a2f0e-102">Точка</span><span class="sxs-lookup"><span data-stu-id="a2f0e-102">Point</span></span>
  <span data-ttu-id="a2f0e-103">В пространственных данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] экземпляр `Point` является объектом без измерения, представляющим отдельное месторасположение, и может содержать значения Z (уровень) и M (мера).</span><span class="sxs-lookup"><span data-stu-id="a2f0e-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spatial data, a `Point` is a 0-dimensional object representing a single location and may contain Z (elevation) and M (measure) values.</span></span>  
  
## <a name="geography-data-type"></a><span data-ttu-id="a2f0e-104">Тип данных Geography</span><span class="sxs-lookup"><span data-stu-id="a2f0e-104">Geography Data Type</span></span>  
 <span data-ttu-id="a2f0e-105">Тип Point для типа данных geography представляет единичное расположение, где *Lat* представляет широту, а *Long* — долготу.</span><span class="sxs-lookup"><span data-stu-id="a2f0e-105">The Point type for the geography data type represents a single location where *Lat* represents latitude and *Long* represents longitude.</span></span> <span data-ttu-id="a2f0e-106">Значения широты и долготы измеряются в градусах.</span><span class="sxs-lookup"><span data-stu-id="a2f0e-106">The values for latitude and longitude are measured in degrees.</span></span> <span data-ttu-id="a2f0e-107">Значения широты всегда находятся в интервале [-90, 90]. Все значения, находящиеся вне этого диапазона, вызывают исключение.</span><span class="sxs-lookup"><span data-stu-id="a2f0e-107">Values for latitude always lie in the interval [-90, 90], and values that are inputted outside this range will throw an exception.</span></span> <span data-ttu-id="a2f0e-108">Значения долготы всегда находятся в интервале [-180, 180]. Все значения, находящиеся вне этого диапазона, преобразуются в соответствующие значения в его пределах.</span><span class="sxs-lookup"><span data-stu-id="a2f0e-108">Values for longitude always lie in the interval (-180, 180], and values inputted outside this range are wrapped around to fit in this range.</span></span> <span data-ttu-id="a2f0e-109">Например, если введено значение долготы 190, то оно будет преобразовано в значение -170.</span><span class="sxs-lookup"><span data-stu-id="a2f0e-109">For example, if 190 is inputted for longitude, then it will be wrapped to the value -170.</span></span> <span data-ttu-id="a2f0e-110">*SRID* представляет идентификатор пространственной ссылки экземпляра **geography** , который необходимо вернуть.</span><span class="sxs-lookup"><span data-stu-id="a2f0e-110">*SRID* represents the spatial reference ID of the **geography** instance that you wish to return.</span></span>  
  
## <a name="geometry-data-type"></a><span data-ttu-id="a2f0e-111">Тип данных Geometry</span><span class="sxs-lookup"><span data-stu-id="a2f0e-111">Geometry Data Type</span></span>  
 <span data-ttu-id="a2f0e-112">Тип элемента для геометрических типов данных представляет собой единое место, где *X* представляет координату x создаваемого экземпляра Point, а *Y* — координату Y создаваемого экземпляра Point.</span><span class="sxs-lookup"><span data-stu-id="a2f0e-112">The Point type for the geometry data type represents a single location where *X* represents the X-coordinate of the Point being generated and *Y* represents the Y-coordinate of the Point being generated.</span></span> <span data-ttu-id="a2f0e-113">*SRID* представляет идентификатор пространственной ссылки экземпляра **geometry** , который необходимо вернуть.</span><span class="sxs-lookup"><span data-stu-id="a2f0e-113">*SRID* represents the spatial reference ID of the **geometry** instance that you wish to return.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a2f0e-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="a2f0e-114">Examples</span></span>  
 <span data-ttu-id="a2f0e-115">В следующем примере показано создание экземпляра `geometry Point`, представляющего точку (3, 4) со значением SRID, равным 0.</span><span class="sxs-lookup"><span data-stu-id="a2f0e-115">The following example creates a `geometry Point`instance representing the point (3, 4) with an SRID of 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POINT (3 4)', 0);  
```  
  
 <span data-ttu-id="a2f0e-116">В следующем примере показано создание экземпляра `geometry``Point` , представляющего точку (3, 4) со значениями Z (уровень) и M (мера), равными соответственно 7 и 2,5, и значением SRID по умолчанию, равным 0.</span><span class="sxs-lookup"><span data-stu-id="a2f0e-116">The next example creates a `geometry``Point` instance representing the point (3, 4) with a Z (elevation) value of 7, an M (measure) value of 2.5, and the default SRID of 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POINT(3 4 7 2.5)');  
```  
  
 <span data-ttu-id="a2f0e-117">В последнем примере возвращаются значения X, Y, Z и M для экземпляра `geometry``Point` .</span><span class="sxs-lookup"><span data-stu-id="a2f0e-117">The final example returns the X, Y, Z, and M values for the `geometry``Point` instance.</span></span>  
  
```  
SELECT @g.STX;  
SELECT @g.STY;  
SELECT @g.Z;  
SELECT @g.M;  
```  
  
 <span data-ttu-id="a2f0e-118">Для Z и M может быть явно указано значение NULL, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a2f0e-118">Z and M values may be explicitly specified as NULL, as shown in the following example.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POINT(3 4 NULL NULL)');  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2f0e-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2f0e-119">See Also</span></span>  
 <span data-ttu-id="a2f0e-120">[MultiPoint](multipoint.md) </span><span class="sxs-lookup"><span data-stu-id="a2f0e-120">[MultiPoint](multipoint.md) </span></span>  
 <span data-ttu-id="a2f0e-121">[STX &#40;типа данных geometry&#41;](/sql/t-sql/spatial-geometry/stx-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="a2f0e-121">[STX &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stx-geometry-data-type) </span></span>  
 <span data-ttu-id="a2f0e-122">[STY (тип данных geometry)](/sql/t-sql/spatial-geometry/sty-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="a2f0e-122">[STY &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/sty-geometry-data-type) </span></span>  
 [<span data-ttu-id="a2f0e-123">Пространственные данные (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a2f0e-123">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
