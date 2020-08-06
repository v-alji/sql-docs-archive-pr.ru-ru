---
title: MultiPoint | Документация Майкрософт
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPoint geometry subtype [SQL Server]
ms.assetid: 2aaab211-3aba-4dbd-90b7-095d997b1f62
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b741071b7986aceea4e49d4fde8293ef2c96fc2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668181"
---
# <a name="multipoint"></a><span data-ttu-id="39e96-102">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="39e96-102">MultiPoint</span></span>
  <span data-ttu-id="39e96-103">Экземпляр `MultiPoint` представляет собой коллекцию точек.</span><span class="sxs-lookup"><span data-stu-id="39e96-103">A `MultiPoint` is a collection of zero or more points.</span></span> <span data-ttu-id="39e96-104">Граница у экземпляра `MultiPoint` отсутствует.</span><span class="sxs-lookup"><span data-stu-id="39e96-104">The boundary of a `MultiPoint` instance is empty.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="39e96-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="39e96-105">Examples</span></span>  
 <span data-ttu-id="39e96-106">В следующем примере создается экземпляр `geometry MultiPoint` со значением SRID, равным 23, и двумя точками, с координатами (2, 3) и (7, 8), и значением Z, равным 9,5.</span><span class="sxs-lookup"><span data-stu-id="39e96-106">The following example creates a `geometry MultiPoint` instance with SRID 23 and two points: one point with the coordinates (2, 3), one point with the coordinates (7, 8), and a Z value of 9.5.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 <span data-ttu-id="39e96-107">Данный экземпляр `MultiPoint` может быть также выражен посредством `STMPointFromText()` , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="39e96-107">This `MultiPoint` instance can also be expressed using `STMPointFromText()` as shown below.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STMPointFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 <span data-ttu-id="39e96-108">В следующем примере метод `STGeometryN()` используется с целью получения описания первой точки коллекции.</span><span class="sxs-lookup"><span data-stu-id="39e96-108">The following example uses the method `STGeometryN()` to retrieve a description of the first point in the collection.</span></span>  
  
```  
SELECT @g.STGeometryN(1).STAsText();  
```  
  
## <a name="see-also"></a><span data-ttu-id="39e96-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="39e96-109">See Also</span></span>  
 <span data-ttu-id="39e96-110">[Точки](point.md) </span><span class="sxs-lookup"><span data-stu-id="39e96-110">[Point](point.md) </span></span>  
 [<span data-ttu-id="39e96-111">Пространственные данные (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="39e96-111">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
