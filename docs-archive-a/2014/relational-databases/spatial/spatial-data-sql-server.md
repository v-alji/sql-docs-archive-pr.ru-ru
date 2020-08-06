---
title: Пространственные данные (SQL Server) | Документация Майкрософт
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geography data type [SQL Server], spatial storage design
- planar spatial data [SQL Server], designing
- spatial data types [SQL Server]
- geodetic spatial data [SQL Server]
- geometry data type [SQL Server], spatial storage design
- spatial storage [SQL Server]
- geodetic spatial data [SQL Server], designing
ms.assetid: 41a132a1-09e2-4426-b9df-225270cb8e15
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4d491420a9eca7c35b89b254a03381c6467c834c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668172"
---
# <a name="spatial-data-sql-server"></a><span data-ttu-id="94116-102">Пространственные данные (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="94116-102">Spatial Data (SQL Server)</span></span>
  <span data-ttu-id="94116-103">Пространственные данные представляют сведения о физическом расположении и форме геометрических объектов.</span><span class="sxs-lookup"><span data-stu-id="94116-103">Spatial data represents information about the physical location and shape of geometric objects.</span></span> <span data-ttu-id="94116-104">Этими объектами могут быть точки расположения или более сложные объекты, такие как страны, дороги или озера.</span><span class="sxs-lookup"><span data-stu-id="94116-104">These objects can be point locations or more complex objects such as countries, roads, or lakes.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="94116-105">поддерживает два пространственных типа данных: `geometry` и `geography`.</span><span class="sxs-lookup"><span data-stu-id="94116-105">supports two spatial data types: the `geometry` data type and the `geography` data type.</span></span>  
  
-   <span data-ttu-id="94116-106">Тип `geometry` представляет данные в Евклидовой (плоской) системе координат.</span><span class="sxs-lookup"><span data-stu-id="94116-106">The `geometry` type represents data in a Euclidean (flat) coordinate system.</span></span>  
  
-   <span data-ttu-id="94116-107">Тип `geography` представляет данные в системе координат круглой земли.</span><span class="sxs-lookup"><span data-stu-id="94116-107">The `geography` type represents data in a round-earth coordinate system.</span></span>  
  
 <span data-ttu-id="94116-108">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]оба эти типа данных реализованы как типы данных среды CLR платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="94116-108">Both data types are implemented as .NET common language runtime (CLR) data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="94116-109">Подробное описание и примеры использования новых возможностей обработки пространственных данных в [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]можно получить, загрузив технический документ [Новые функции обработки пространственных данных в SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="94116-109">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="94116-110">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="94116-110">Related Tasks</span></span>  
 [<span data-ttu-id="94116-111">Создание, конструирование и запрос экземпляров geometry</span><span class="sxs-lookup"><span data-stu-id="94116-111">Create, Construct, and Query geometry Instances</span></span>](create-construct-and-query-geometry-instances.md)  
 <span data-ttu-id="94116-112">Описывает методы, которые можно использовать с экземплярами типа данных geometry.</span><span class="sxs-lookup"><span data-stu-id="94116-112">Describes the methods that you can use with instances of the geometry data type.</span></span>  
  
 [<span data-ttu-id="94116-113">Создание, проектирование и создание запросов к экземплярам типа данных geography</span><span class="sxs-lookup"><span data-stu-id="94116-113">Create, Construct, and Query geography Instances</span></span>](create-construct-and-query-geography-instances.md)  
 <span data-ttu-id="94116-114">Описывает методы, которые можно использовать с экземплярами типа данных geography.</span><span class="sxs-lookup"><span data-stu-id="94116-114">Describes the methods that you can use with instances of the geography data type.</span></span>  
  
 [<span data-ttu-id="94116-115">Запросы пространственных данных для ближайшего соседа</span><span class="sxs-lookup"><span data-stu-id="94116-115">Query Spatial Data for Nearest Neighbor</span></span>](query-spatial-data-for-nearest-neighbor.md)  
 <span data-ttu-id="94116-116">Описывает общий шаблон запроса, используемый для поиска пространственных объектов, расположенных ближе всего к указанному пространственному объекту.</span><span class="sxs-lookup"><span data-stu-id="94116-116">Describes the common query pattern that is used to find the closest spatial objects to a specific spatial object.</span></span>  
  
 [<span data-ttu-id="94116-117">Создание, изменение и удаление пространственных индексов</span><span class="sxs-lookup"><span data-stu-id="94116-117">Create, Modify, and Drop Spatial Indexes</span></span>](create-modify-and-drop-spatial-indexes.md)  
 <span data-ttu-id="94116-118">Содержит сведения о создании, изменении и удалении пространственного индекса.</span><span class="sxs-lookup"><span data-stu-id="94116-118">Provides information about creating, altering, and dropping a spatial index.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="94116-119">См. также</span><span class="sxs-lookup"><span data-stu-id="94116-119">Related Content</span></span>  
 [<span data-ttu-id="94116-120">Основные сведения о типах пространственных данных</span><span class="sxs-lookup"><span data-stu-id="94116-120">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
 <span data-ttu-id="94116-121">Описываются пространственные типы данных.</span><span class="sxs-lookup"><span data-stu-id="94116-121">Introduces the spatial data types.</span></span>  
  
-   [<span data-ttu-id="94116-122">Point</span><span class="sxs-lookup"><span data-stu-id="94116-122">Point</span></span>](point.md)  
  
-   [<span data-ttu-id="94116-123">LineString</span><span class="sxs-lookup"><span data-stu-id="94116-123">LineString</span></span>](linestring.md)  
  
-   [<span data-ttu-id="94116-124">CircularString</span><span class="sxs-lookup"><span data-stu-id="94116-124">CircularString</span></span>](circularstring.md)  
  
-   [<span data-ttu-id="94116-125">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="94116-125">CompoundCurve</span></span>](compoundcurve.md)  
  
-   [<span data-ttu-id="94116-126">Многоугольник</span><span class="sxs-lookup"><span data-stu-id="94116-126">Polygon</span></span>](polygon.md)  
  
-   [<span data-ttu-id="94116-127">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="94116-127">CurvePolygon</span></span>](curvepolygon.md)  
  
-   [<span data-ttu-id="94116-128">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="94116-128">MultiPoint</span></span>](multipoint.md)  
  
-   [<span data-ttu-id="94116-129">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="94116-129">MultiLineString</span></span>](multilinestring.md)  
  
-   [<span data-ttu-id="94116-130">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="94116-130">MultiPolygon</span></span>](multipolygon.md)  
  
-   [<span data-ttu-id="94116-131">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="94116-131">GeometryCollection</span></span>](geometrycollection.md)  
  
 [<span data-ttu-id="94116-132">Общие сведения о пространственных индексах</span><span class="sxs-lookup"><span data-stu-id="94116-132">Spatial Indexes Overview</span></span>](spatial-indexes-overview.md)  
 <span data-ttu-id="94116-133">Описываются пространственные индексы, тесселяция и схемы тесселяции.</span><span class="sxs-lookup"><span data-stu-id="94116-133">Introduces spatial indexes and describes tessellation and tessellation schemes.</span></span>  
  
  
