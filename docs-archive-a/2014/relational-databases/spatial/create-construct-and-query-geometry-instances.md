---
title: Создание и конструирование геометрических экземпляров и отправка запросов к ним | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- planar spatial data [SQL Server], getting started
- geometry data type [SQL Server], getting started
ms.assetid: c6b5c852-37d2-48d0-a8ad-e43bb80d6514
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 539f3f8bb1d9a1c277d6317cc571cf8bcb281833
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655571"
---
# <a name="create-construct-and-query-geometry-instances"></a><span data-ttu-id="c4262-102">Создание, конструирование и запрос экземпляров geometry</span><span class="sxs-lookup"><span data-stu-id="c4262-102">Create, Construct, and Query geometry Instances</span></span>
  <span data-ttu-id="c4262-103">Планарный пространственный тип данных `geometry` представляет данные в евклидовой (плоской) системе координат.</span><span class="sxs-lookup"><span data-stu-id="c4262-103">The planar spatial data type, `geometry`, represents data in a Euclidean (flat) coordinate system.</span></span> <span data-ttu-id="c4262-104">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]этот тип реализован как тип данных среды CLR.</span><span class="sxs-lookup"><span data-stu-id="c4262-104">This type is implemented as a common language runtime (CLR) data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c4262-105">Тип `geometry` является стандартным и доступен в каждой базе данных.</span><span class="sxs-lookup"><span data-stu-id="c4262-105">The `geometry` type is predefined and available in each database.</span></span> <span data-ttu-id="c4262-106">В таблице можно создать столбцы типа `geometry` и обращаться с данными `geometry` так же, как и с данными других типов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="c4262-106">You can create table columns of type `geometry` and operate on `geometry` data in the same manner as you would use other CLR types.</span></span>  
  
 <span data-ttu-id="c4262-107">Тип данных `geometry` (плоский), поддерживаемый [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], соответствует спецификации Open Geospatial Consortium (OGC) «Простые объекты для SQL» версии 1.1.0.</span><span class="sxs-lookup"><span data-stu-id="c4262-107">The `geometry` data type (planar) supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conforms to the Open Geospatial Consortium (OGC) Simple Features for SQL Specification version 1.1.0.</span></span>  
  
 <span data-ttu-id="c4262-108">Дополнительные сведения о спецификациях OGC см. в одном из следующих источников:</span><span class="sxs-lookup"><span data-stu-id="c4262-108">For more information on OGC specifications, see the following:</span></span>  
  
-   [<span data-ttu-id="c4262-109">Спецификации OGC, простой доступ к функциям, часть 1 — общая архитектура</span><span class="sxs-lookup"><span data-stu-id="c4262-109">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span></span>](https://go.microsoft.com/fwlink/?LinkId=93628)  
  
-   [<span data-ttu-id="c4262-110">Спецификации OGC, простой доступ к функциям, часть 2 — параметры SQL</span><span class="sxs-lookup"><span data-stu-id="c4262-110">OGC Specifications, Simple Feature Access Part 2 - SQL Options</span></span>](https://go.microsoft.com/fwlink/?LinkId=93629)  
  
 <span data-ttu-id="c4262-111">Служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает подмножество существующего стандарта GML 3.1, определенного по следующей схеме: [https://schemas.microsoft.com/sqlserver/profiles/gml/SpatialGML.xsd](https://go.microsoft.com/fwlink/?LinkId=230959).</span><span class="sxs-lookup"><span data-stu-id="c4262-111">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports a subset of the existing GML 3.1 standard which is defined in the following schema: [https://schemas.microsoft.com/sqlserver/profiles/gml/SpatialGML.xsd](https://go.microsoft.com/fwlink/?LinkId=230959).</span></span>  
  
##  <a name="creating-or-constructing-a-new-geometry-instance"></a><a name="creating"></a> <span data-ttu-id="c4262-112">Создание или построение нового экземпляра геометрического объекта</span><span class="sxs-lookup"><span data-stu-id="c4262-112">Creating or constructing a new geometry instance</span></span>  
  
###  <a name="creating-a-new-geometry-instance-from-an-existing-instance"></a><a name="existing"></a> <span data-ttu-id="c4262-113">Создание нового экземпляра геометрического объекта из существующего экземпляра</span><span class="sxs-lookup"><span data-stu-id="c4262-113">Creating a New geometry Instance from an Existing Instance</span></span>  
 <span data-ttu-id="c4262-114">Тип данных `geometry` содержит множество встроенных методов, с помощью которых можно создавать новые объекты `geometry` на основе существующих.</span><span class="sxs-lookup"><span data-stu-id="c4262-114">The `geometry` data type provides numerous built-in methods you can use to create new `geometry` instances based on existing instances.</span></span>  
  
 <span data-ttu-id="c4262-115">**Создание буфера вокруг геометрического объекта**</span><span class="sxs-lookup"><span data-stu-id="c4262-115">**To create a buffer around a geometry**</span></span>  
 [<span data-ttu-id="c4262-116">STBuffer (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-116">STBuffer &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stbuffer-geometry-data-type)  
  
 [<span data-ttu-id="c4262-117">BufferWithTolerance (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-117">BufferWithTolerance &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/bufferwithtolerance-geometry-data-type)  
  
 <span data-ttu-id="c4262-118">**Создание упрощенной версии геометрического объекта**</span><span class="sxs-lookup"><span data-stu-id="c4262-118">**To create a simplified version of a geometry**</span></span>  
 [<span data-ttu-id="c4262-119">Reduce (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-119">Reduce &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/reduce-geometry-data-type)  
  
 <span data-ttu-id="c4262-120">**Создание выпуклой оболочки геометрического объекта**</span><span class="sxs-lookup"><span data-stu-id="c4262-120">**To create the convex hull of a geometry**</span></span>  
 [<span data-ttu-id="c4262-121">STConvexHull (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-121">STConvexHull &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stconvexhull-geometry-data-type)  
  
 <span data-ttu-id="c4262-122">**Создание геометрического объекта на основе пересечения двух геометрических объектов**</span><span class="sxs-lookup"><span data-stu-id="c4262-122">**To create a geometry from the intersection of two geometries**</span></span>  
 [<span data-ttu-id="c4262-123">STIntersection (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-123">STIntersection &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stintersection-geometry-data-type)  
  
 <span data-ttu-id="c4262-124">**Создание геометрического объекта основе объединения двух геометрических объектов**</span><span class="sxs-lookup"><span data-stu-id="c4262-124">**To create a geometry from the union of two geometries**</span></span>  
 [<span data-ttu-id="c4262-125">STUnion (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-125">STUnion &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stunion-geometry-data-type)  
  
 <span data-ttu-id="c4262-126">**Создание геометрического объекта на основе точек, в которых один геометрический объект не перекрывается другими**</span><span class="sxs-lookup"><span data-stu-id="c4262-126">**To create a geometry from the points where one geometry does not overlap another**</span></span>  
 [<span data-ttu-id="c4262-127">STDifference (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-127">STDifference &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdifference-geometry-data-type)  
  
 <span data-ttu-id="c4262-128">**Создание геометрического объекта на основе точек, в которых два геометрических объекта не перекрываются**</span><span class="sxs-lookup"><span data-stu-id="c4262-128">**To create a geometry from the points where two geometries do not overlap**</span></span>  
 [<span data-ttu-id="c4262-129">STSymDifference (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-129">STSymDifference &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stsymdifference-geometry-data-type)  
  
 <span data-ttu-id="c4262-130">**Создание произвольного экземпляра Point, принадлежащего существующему геометрическому объекту**</span><span class="sxs-lookup"><span data-stu-id="c4262-130">**To create an arbitrary Point instance that lies on an existing geometry**</span></span>  
 [<span data-ttu-id="c4262-131">STPointOnSurface (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-131">STPointOnSurface &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-well-known-text-input"></a><a name="wkt"></a> <span data-ttu-id="c4262-132">Построение экземпляра геометрического объекта на основе входных данных в формате Well-Known Text</span><span class="sxs-lookup"><span data-stu-id="c4262-132">Constructing a geometry Instance from Well-Known Text Input</span></span>  
 <span data-ttu-id="c4262-133">В типе данных `geometry` предусмотрено несколько встроенных методов, позволяющих создать экземпляр типа geometry на основе представления WKT спецификации консорциума OGC.</span><span class="sxs-lookup"><span data-stu-id="c4262-133">The `geometry` data type provides several built-in methods that generate a geometry from the Open Geospatial Consortium (OGC) WKT representation.</span></span> <span data-ttu-id="c4262-134">Стандарт WKT представляет собой текстовую строку, позволяющую осуществлять обмен геометрическими данными в текстовой форме.</span><span class="sxs-lookup"><span data-stu-id="c4262-134">The WKT standard is a text string that allows geometry data to be exchanged in textual form.</span></span>  
  
 <span data-ttu-id="c4262-135">**Создание экземпляра геометрического объекта любого типа на основе входных данных формата WKT**</span><span class="sxs-lookup"><span data-stu-id="c4262-135">**To construct any type of geometry instance from WKT input**</span></span>  
 [<span data-ttu-id="c4262-136">STGeomFromText (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-136">STGeomFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type)  
  
 [<span data-ttu-id="c4262-137">Parse (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-137">Parse &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/parse-geometry-data-type)  
  
 <span data-ttu-id="c4262-138">**Создание геометрического объекта Point на основе входных данных формата WKT**</span><span class="sxs-lookup"><span data-stu-id="c4262-138">**To construct a geometry Point instance from WKT input**</span></span>  
 [<span data-ttu-id="c4262-139">STPointFromText (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-139">STPointFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointfromtext-geometry-data-type)  
  
 <span data-ttu-id="c4262-140">**Создание геометрического объекта MultiPoint на основе входных данных формата WKT**</span><span class="sxs-lookup"><span data-stu-id="c4262-140">**To construct a geometry MultiPoint instance from WKT input**</span></span>  
 [<span data-ttu-id="c4262-141">STMPointFromText (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-141">STMPointFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpointfromtext-geometry-data-type)  
  
 <span data-ttu-id="c4262-142">**Создание геометрического объекта LineString на основе входных данных формата WKT**</span><span class="sxs-lookup"><span data-stu-id="c4262-142">**To construct a geometry LineString instance from WKT input**</span></span>  
 [<span data-ttu-id="c4262-143">STLineFromText (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-143">STLineFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stlinefromtext-geometry-data-type)  
  
 <span data-ttu-id="c4262-144">**Создание геометрического объекта MultiLineString на основе входных данных формата WKT**</span><span class="sxs-lookup"><span data-stu-id="c4262-144">**To construct a geometry MultiLineString instance from WKT input**</span></span>  
 [<span data-ttu-id="c4262-145">STMLineFromText (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-145">STMLineFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmlinefromtext-geometry-data-type)  
  
 <span data-ttu-id="c4262-146">**Создание геометрического объекта Polygon на основе входных данных формата WKT**</span><span class="sxs-lookup"><span data-stu-id="c4262-146">**To construct a geometry Polygon instance from WKT input**</span></span>  
 [<span data-ttu-id="c4262-147">STPolyFromText (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-147">STPolyFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpolyfromtext-geometry-data-type)  
  
 <span data-ttu-id="c4262-148">**Создание геометрического объекта MultiPolygon на основе входных данных формата WKT**</span><span class="sxs-lookup"><span data-stu-id="c4262-148">**To construct a geometry MultiPolygon instance from WKT input**</span></span>  
 [<span data-ttu-id="c4262-149">STMPolyFromText (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-149">STMPolyFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpolyfromtext-geometry-data-type)  
  
 <span data-ttu-id="c4262-150">**Создание геометрического объекта GeometryCollection на основе входных данных формата WKT**</span><span class="sxs-lookup"><span data-stu-id="c4262-150">**To construct a geometry GeometryCollection instance from WKT input**</span></span>  
 [<span data-ttu-id="c4262-151">STGeomCollFromText (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-151">STGeomCollFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomcollfromtext-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-well-known-binary-input"></a><a name="wkb"></a> <span data-ttu-id="c4262-152">Построение экземпляра геометрического объекта на основе входных данных в формате Well-Known Binary Input</span><span class="sxs-lookup"><span data-stu-id="c4262-152">Constructing a geometry Instance from Well-Known Binary Input</span></span>  
 <span data-ttu-id="c4262-153">WKB представляет собой описанный консорциумом OGC двоичный формат, позволяющий осуществлять обмен данными типа `geometry` между клиентскими приложениями и базой данных SQL.</span><span class="sxs-lookup"><span data-stu-id="c4262-153">WKB is a binary format specified by the Open Geospatial Consortium (OGC) that permits `geometry` data to be exchanged between a client application and an SQL database.</span></span> <span data-ttu-id="c4262-154">Следующие функции допускают создание геометрических объектов на основе входных данных формата WKB.</span><span class="sxs-lookup"><span data-stu-id="c4262-154">The following functions accept WKB input to construct geometries:</span></span>  
  
 <span data-ttu-id="c4262-155">**Создание экземпляра геометрического объекта любого типа на основе входных данных формата WKB**</span><span class="sxs-lookup"><span data-stu-id="c4262-155">**To construct any type of geometry instance from WKB input**</span></span>  
 [<span data-ttu-id="c4262-156">STGeomFromWKB (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-156">STGeomFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomfromwkb-geometry-data-type)  
  
 <span data-ttu-id="c4262-157">**Создание геометрического объекта Point на основе входных данных формата WKB**</span><span class="sxs-lookup"><span data-stu-id="c4262-157">**To construct a geometry Point instance from WKB input**</span></span>  
 [<span data-ttu-id="c4262-158">STPointFromWKB (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-158">STPointFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointfromwkb-geometry-data-type)  
  
 <span data-ttu-id="c4262-159">**Создание геометрического объекта MultiPoint на основе входных данных формата WKB**</span><span class="sxs-lookup"><span data-stu-id="c4262-159">**To construct a geometry MultiPoint instance from WKB input**</span></span>  
 [<span data-ttu-id="c4262-160">STMPointFromWKB (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-160">STMPointFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpointfromwkb-geometry-data-type)  
  
 <span data-ttu-id="c4262-161">**Создание геометрического объекта LineString на основе входных данных формата WKB**</span><span class="sxs-lookup"><span data-stu-id="c4262-161">**To construct a geometry LineString instance from WKB input**</span></span>  
 [<span data-ttu-id="c4262-162">STLineFromWKB (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-162">STLineFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stlinefromwkb-geometry-data-type)  
  
 <span data-ttu-id="c4262-163">**Создание геометрического объекта MultiLineString на основе входных данных формата WKB**</span><span class="sxs-lookup"><span data-stu-id="c4262-163">**To construct a geometry MultiLineString instance from WKB input**</span></span>  
 [<span data-ttu-id="c4262-164">STMLineFromWKB (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-164">STMLineFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmlinefromwkb-geometry-data-type)  
  
 <span data-ttu-id="c4262-165">**Создание геометрического объекта Polygon на основе входных данных формата WKB**</span><span class="sxs-lookup"><span data-stu-id="c4262-165">**To construct a geometry Polygon instance from WKB input**</span></span>  
 [<span data-ttu-id="c4262-166">STPolyFromWKB (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-166">STPolyFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpolyfromwkb-geometry-data-type)  
  
 <span data-ttu-id="c4262-167">**Создание геометрического объекта MultiPolygon на основе входных данных формата WKB**</span><span class="sxs-lookup"><span data-stu-id="c4262-167">**To construct a geometry MultiPolygon instance from WKB input**</span></span>  
 [<span data-ttu-id="c4262-168">STMPolyFromWKB (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-168">STMPolyFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpolyfromwkb-geometry-data-type)  
  
 <span data-ttu-id="c4262-169">**Создание геометрического объекта GeometryCollection на основе входных данных формата WKB**</span><span class="sxs-lookup"><span data-stu-id="c4262-169">**To construct a geometry GeometryCollection instance from WKB input**</span></span>  
 [<span data-ttu-id="c4262-170">STGeomCollFromWKB (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-170">STGeomCollFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomcollfromwkb-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-gml-text-input"></a><a name="gml"></a> <span data-ttu-id="c4262-171">Построение экземпляра геометрического объекта на основе входных данных в формате GML Text</span><span class="sxs-lookup"><span data-stu-id="c4262-171">Constructing a geometry Instance from GML Text Input</span></span>  
 <span data-ttu-id="c4262-172">`geometry`Тип данных предоставляет метод, создающий `geometry` экземпляр из GML, XML-представление геометрических объектов.</span><span class="sxs-lookup"><span data-stu-id="c4262-172">The `geometry` data type provides a method that generates a `geometry` instance from GML, an XML representation of geometric objects.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c4262-173">поддерживает подмножество GML.</span><span class="sxs-lookup"><span data-stu-id="c4262-173">supports a subset of GML.</span></span>  
  
 <span data-ttu-id="c4262-174">**Создание экземпляра геометрического объекта любого типа на основе входных данных формата GML**</span><span class="sxs-lookup"><span data-stu-id="c4262-174">**To construct any type of geometry instance from GML input**</span></span>  
 [<span data-ttu-id="c4262-175">GeomFromGml (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-175">GeomFromGml &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/geomfromgml-geometry-data-type)  
  
  
  
##  <a name="returning-well-known-text-and-well-known-binary-from-a-geometry-instance"></a><a name="returning"></a> <span data-ttu-id="c4262-176">Получение данных в формате Well-Known Text и Well-Known Binary из геометрического экземпляра</span><span class="sxs-lookup"><span data-stu-id="c4262-176">Returning Well-Known Text and Well-Known Binary from a geometry Instance</span></span>  
 <span data-ttu-id="c4262-177">Можно использовать следующие методы для получения данных экземпляра `geometry` в формате WKT или формате WKB:</span><span class="sxs-lookup"><span data-stu-id="c4262-177">You can use the following methods to return either the WKT or WKB format of a `geometry` instance:</span></span>  
  
 <span data-ttu-id="c4262-178">**Получение WKT-представления экземпляра геометрического объекта**</span><span class="sxs-lookup"><span data-stu-id="c4262-178">**To return the WKT representation of a geometry instance**</span></span>  
 [<span data-ttu-id="c4262-179">STAsText (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-179">STAsText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stastext-geometry-data-type)  
  
 [<span data-ttu-id="c4262-180">ToString (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-180">ToString &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/tostring-geometry-data-type)  
  
 <span data-ttu-id="c4262-181">**Получение WKT-представления экземпляра геометрического объекта, включая значения Z и M**</span><span class="sxs-lookup"><span data-stu-id="c4262-181">**To return the WKT representation of a geometry instance including any Z and M values**</span></span>  
 [<span data-ttu-id="c4262-182">AsTextZM (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-182">AsTextZM &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/astextzm-geometry-data-type)  
  
 <span data-ttu-id="c4262-183">**Получение WKB-представления экземпляра геометрического объекта**</span><span class="sxs-lookup"><span data-stu-id="c4262-183">**To return the WKB representation of a geometry instance**</span></span>  
 [<span data-ttu-id="c4262-184">STAsBinary (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-184">STAsBinary &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stasbinary-geometry-data-type)  
  
 <span data-ttu-id="c4262-185">**Получение GML-представления экземпляра геометрического объекта**</span><span class="sxs-lookup"><span data-stu-id="c4262-185">**To return a GML representation of a geometry instance**</span></span>  
 [<span data-ttu-id="c4262-186">AsGml (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-186">AsGml &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/asgml-geometry-data-type)  
  
  
  
##  <a name="querying-the-properties-and-behaviors-of-geometry-instances"></a><a name="querying"></a> <span data-ttu-id="c4262-187">Запрос свойств и режимов геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="c4262-187">Querying the Properties and Behaviors of geometry Instances</span></span>  
 <span data-ttu-id="c4262-188">`geometry`У всех экземпляров есть ряд свойств, которые можно получить с помощью методов, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предоставляемых.</span><span class="sxs-lookup"><span data-stu-id="c4262-188">All `geometry` instances have a number of properties that can be retrieved through methods that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides.</span></span> <span data-ttu-id="c4262-189">В следующих разделах описаны свойства и поведение геометрических типов данных, а также методы для запросов к ним.</span><span class="sxs-lookup"><span data-stu-id="c4262-189">The following topics define the properties and behaviors of geometry types, and the methods for querying each one.</span></span>  
  
###  <a name="validity-instance-type-and-geometrycollection-information"></a><a name="valid"></a> <span data-ttu-id="c4262-190">Допустимость, тип экземпляра и сведения GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="c4262-190">Validity, Instance Type, and GeometryCollection Information</span></span>  
 <span data-ttu-id="c4262-191">Как только экземпляр `geometry` сформирован, при помощи следующих методов можно определить правильность его формата, получить тип этого экземпляра или, в случае экземпляра-коллекции, получить определенный экземпляр `geometry`.</span><span class="sxs-lookup"><span data-stu-id="c4262-191">Once a `geometry` instance is constructed, you can use the following methods to determine if it is well-formed, return the instance type, or, if it is a collection instance, return a specific `geometry` instance.</span></span>  
  
 <span data-ttu-id="c4262-192">**Получение типа геометрического объекта**</span><span class="sxs-lookup"><span data-stu-id="c4262-192">**To return the instance type of a geometry**</span></span>  
 [<span data-ttu-id="c4262-193">STGeometryType (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-193">STGeometryType &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeometrytype-geometry-data-type)  
  
 <span data-ttu-id="c4262-194">**Определение принадлежности геометрического объекта к заданному типу**</span><span class="sxs-lookup"><span data-stu-id="c4262-194">**To determine if a geometry is a given instance type**</span></span>  
 [<span data-ttu-id="c4262-195">InstanceOf (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-195">InstanceOf &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/instanceof-geometry-data-type)  
  
 <span data-ttu-id="c4262-196">**Проверка соответствия формата экземпляра геометрического объекта его типу**</span><span class="sxs-lookup"><span data-stu-id="c4262-196">**To determine if a geometry instance is well-formed for its instance type**</span></span>  
 [<span data-ttu-id="c4262-197">STIsValid (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-197">STIsValid &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)  
  
 <span data-ttu-id="c4262-198">**Преобразование экземпляра геометрического объекта в экземпляр геометрический объект правильного формата с каким-либо типом экземпляра**</span><span class="sxs-lookup"><span data-stu-id="c4262-198">**To convert a geometry instance to a well-formed geometry instance with an instance type**</span></span>  
 [<span data-ttu-id="c4262-199">MakeValid (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-199">MakeValid &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type)  
  
 <span data-ttu-id="c4262-200">**Получение количества геометрических экземпляров в экземпляре геометрической коллекции**</span><span class="sxs-lookup"><span data-stu-id="c4262-200">**To return the number of geometries in a geometry collection instance**</span></span>  
 [<span data-ttu-id="c4262-201">STNumGeometries (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-201">STNumGeometries &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stnumgeometries-geometry-data-type)  
  
 <span data-ttu-id="c4262-202">Получение определенного геометрического объекта из экземпляра геометрической коллекции</span><span class="sxs-lookup"><span data-stu-id="c4262-202">To return a specific geometry in a geometry collection instance</span></span>  
 <span data-ttu-id="c4262-203">[STGeometryN (тип данных geometry)](/sql/t-sql/spatial-geometry/stgeometryn-geometry-data-type)STGeometryN (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-203">[STGeometryN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeometryn-geometry-data-type)STGeometryN (geometry Data type)</span></span>  
  
  
  
###  <a name="number-of-points"></a><a name="number"></a> <span data-ttu-id="c4262-204">Число точек</span><span class="sxs-lookup"><span data-stu-id="c4262-204">Number of Points</span></span>  
 <span data-ttu-id="c4262-205">Все непустые `geometry` экземпляры состоят из *точек*.</span><span class="sxs-lookup"><span data-stu-id="c4262-205">All nonempty `geometry` instances are comprised of *points*.</span></span> <span data-ttu-id="c4262-206">Эти точки представляют координаты X и Y на плоскости, где вычерчиваются геометрические объекты.</span><span class="sxs-lookup"><span data-stu-id="c4262-206">These points represent the X- and Y-coordinates of the plane on which the geometries are drawn.</span></span> <span data-ttu-id="c4262-207">`geometry` предоставляет многочисленные встроенные методы для создания запросов к точкам экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c4262-207">`geometry` provides numerous built-in methods for querying the points of an instance.</span></span>  
  
 <span data-ttu-id="c4262-208">**Получение числа точек, образующих экземпляр**</span><span class="sxs-lookup"><span data-stu-id="c4262-208">**To return the number of points that comprise an instance**</span></span>  
 [<span data-ttu-id="c4262-209">STNumPoints (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-209">STNumPoints &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type)  
  
 <span data-ttu-id="c4262-210">**Получение выбранной точки в экземпляре**</span><span class="sxs-lookup"><span data-stu-id="c4262-210">**To return a specific point in an instance**</span></span>  
 [<span data-ttu-id="c4262-211">STPointN</span><span class="sxs-lookup"><span data-stu-id="c4262-211">STPointN</span></span>](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)  
  
 <span data-ttu-id="c4262-212">**Произвольная точка, принадлежащая экземпляру**</span><span class="sxs-lookup"><span data-stu-id="c4262-212">**To return an arbitrary point that lies on an instance**</span></span>  
 [<span data-ttu-id="c4262-213">STPointOnSurface</span><span class="sxs-lookup"><span data-stu-id="c4262-213">STPointOnSurface</span></span>](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)  
  
 <span data-ttu-id="c4262-214">**Получение начальной точки экземпляра**</span><span class="sxs-lookup"><span data-stu-id="c4262-214">**To return the start point of an instance**</span></span>  
 [<span data-ttu-id="c4262-215">STStartPoint</span><span class="sxs-lookup"><span data-stu-id="c4262-215">STStartPoint</span></span>](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type)  
  
 <span data-ttu-id="c4262-216">**Получение конечной точки экземпляра**</span><span class="sxs-lookup"><span data-stu-id="c4262-216">**To return the end point of an instance**</span></span>  
 [<span data-ttu-id="c4262-217">STEndpoint</span><span class="sxs-lookup"><span data-stu-id="c4262-217">STEndpoint</span></span>](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type)  
  
 <span data-ttu-id="c4262-218">**Координата по оси X экземпляра Point**</span><span class="sxs-lookup"><span data-stu-id="c4262-218">**To return the X-coordinate of a Point instance**</span></span>  
 [<span data-ttu-id="c4262-219">STX (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="c4262-219">STX &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stx-geometry-data-type)  
  
 <span data-ttu-id="c4262-220">**Координата по оси Y экземпляра Point**</span><span class="sxs-lookup"><span data-stu-id="c4262-220">**To return the Y-coordinate of a Point instance**</span></span>  
 [<span data-ttu-id="c4262-221">STY</span><span class="sxs-lookup"><span data-stu-id="c4262-221">STY</span></span>](/sql/t-sql/spatial-geometry/sty-geometry-data-type)  
  
 <span data-ttu-id="c4262-222">**Определение геометрического центра экземпляра Polygon, CurvePolygon или MultiPolygon**</span><span class="sxs-lookup"><span data-stu-id="c4262-222">**To return the geometric center point of a Polygon, CurvePolygon, or MultiPolygon instance**</span></span>  
 [<span data-ttu-id="c4262-223">STCentroid</span><span class="sxs-lookup"><span data-stu-id="c4262-223">STCentroid</span></span>](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type)  
  
  
  
###  <a name="dimension"></a><a name="dimension"></a> <span data-ttu-id="c4262-224">Измерение</span><span class="sxs-lookup"><span data-stu-id="c4262-224">Dimension</span></span>  
 <span data-ttu-id="c4262-225">Непустой объект `geometry` может иметь 0, 1 или 2 измерения.</span><span class="sxs-lookup"><span data-stu-id="c4262-225">A nonempty `geometry` instance can be 0-, 1-, or 2-dimensional.</span></span> <span data-ttu-id="c4262-226">Объекты `geometries`, имеющие 0 измерений, например `Point` и `MultiPoint`, не имеют ни длины, ни площади.</span><span class="sxs-lookup"><span data-stu-id="c4262-226">Zero-dimensional `geometries`, such as `Point` and `MultiPoint`, have no length or area.</span></span> <span data-ttu-id="c4262-227">Одномерные объекты, такие как `LineString, CircularString, CompoundCurve` и `MultiLineString`, имеют длину.</span><span class="sxs-lookup"><span data-stu-id="c4262-227">One-dimensional objects, such as `LineString, CircularString, CompoundCurve`, and `MultiLineString`, have length.</span></span> <span data-ttu-id="c4262-228">Двумерные объекты, такие как `Polygon`, `CurvePolygon` и `MultiPolygon`, имеют длину и площадь.</span><span class="sxs-lookup"><span data-stu-id="c4262-228">Two-dimensional instances, such as `Polygon`, `CurvePolygon`, and `MultiPolygon`, have area and length.</span></span> <span data-ttu-id="c4262-229">Пустые экземпляры имеют измерение -1, а экземпляр `GeometryCollection` имеет площадь, зависящую от типов его содержимого.</span><span class="sxs-lookup"><span data-stu-id="c4262-229">Empty instances will report a dimension of -1, and a `GeometryCollection` will report an area dependent on the types of its contents.</span></span>  
  
 <span data-ttu-id="c4262-230">**Получение измерения экземпляра**</span><span class="sxs-lookup"><span data-stu-id="c4262-230">**To return the dimension of an instance**</span></span>  
 [<span data-ttu-id="c4262-231">STDimension</span><span class="sxs-lookup"><span data-stu-id="c4262-231">STDimension</span></span>](/sql/t-sql/spatial-geometry/stdimension-geometry-data-type)  
  
 <span data-ttu-id="c4262-232">**Получение длины экземпляра**</span><span class="sxs-lookup"><span data-stu-id="c4262-232">**To return the length of an instance**</span></span>  
 [<span data-ttu-id="c4262-233">STLength</span><span class="sxs-lookup"><span data-stu-id="c4262-233">STLength</span></span>](/sql/t-sql/spatial-geometry/stlength-geometry-data-type)  
  
 <span data-ttu-id="c4262-234">**Получение площади экземпляра**</span><span class="sxs-lookup"><span data-stu-id="c4262-234">**To return the area of an instance**</span></span>  
 [<span data-ttu-id="c4262-235">STArea</span><span class="sxs-lookup"><span data-stu-id="c4262-235">STArea</span></span>](/sql/t-sql/spatial-geometry/starea-geometry-data-type)  
  
  
  
###  <a name="empty"></a><a name="empty"></a> <span data-ttu-id="c4262-236">Пустой</span><span class="sxs-lookup"><span data-stu-id="c4262-236">Empty</span></span>  
 <span data-ttu-id="c4262-237">*Пустой* `geometry` экземпляр не имеет точек.</span><span class="sxs-lookup"><span data-stu-id="c4262-237">An *empty*`geometry` instance does not have any points.</span></span> <span data-ttu-id="c4262-238">Длина пустых экземпляров `LineString, CircularString`, `CompoundCurve` и `MultiLineString` равна нулю.</span><span class="sxs-lookup"><span data-stu-id="c4262-238">The length of empty `LineString, CircularString`, `CompoundCurve`, and `MultiLineString` instances is zero.</span></span> <span data-ttu-id="c4262-239">Площадь пустых экземпляров `Polygon`, `CurvePolygon` и `MultiPolygon` равна нулю.</span><span class="sxs-lookup"><span data-stu-id="c4262-239">The area of empty `Polygon`, `CurvePolygon`, and `MultiPolygon` instances is 0.</span></span>  
  
 <span data-ttu-id="c4262-240">**Проверка, является ли экземпляр пустым**</span><span class="sxs-lookup"><span data-stu-id="c4262-240">**To determine if an instance is empty**</span></span>  
 <span data-ttu-id="c4262-241">[STIsEmpty](/sql/t-sql/spatial-geometry/stisempty-geometry-data-type).</span><span class="sxs-lookup"><span data-stu-id="c4262-241">[STIsEmpty](/sql/t-sql/spatial-geometry/stisempty-geometry-data-type).</span></span>  
  
  
  
###  <a name="simple"></a><a name="simple"></a> <span data-ttu-id="c4262-242">Простой</span><span class="sxs-lookup"><span data-stu-id="c4262-242">Simple</span></span>  
 <span data-ttu-id="c4262-243">`geometry`Чтобы экземпляр был *простым*, он должен соответствовать обоим следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="c4262-243">For a `geometry` of the instance to be *simple*, it must meet both of these requirements:</span></span>  
  
-   <span data-ttu-id="c4262-244">Каждая фигура экземпляра не должна пересекать саму себя, за исключением конечных точек.</span><span class="sxs-lookup"><span data-stu-id="c4262-244">Each figure of the instance must not intersect itself, except at its endpoints.</span></span>  
  
-   <span data-ttu-id="c4262-245">Никакие две фигуры экземпляра не могут пересекаться в точке, не находящейся на их границах.</span><span class="sxs-lookup"><span data-stu-id="c4262-245">No two figures of the instance can intersect each other at a point that is not in both of their boundaries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4262-246">Пустые геометрические фигуры всегда являются простыми.</span><span class="sxs-lookup"><span data-stu-id="c4262-246">Empty geometries are always simple.</span></span>  
  
 <span data-ttu-id="c4262-247">**Определение, является ли экземпляр простым**</span><span class="sxs-lookup"><span data-stu-id="c4262-247">**To determine if an instance is simple**</span></span>  
 <span data-ttu-id="c4262-248">[STIsSimple](/sql/t-sql/spatial-geometry/stissimple-geometry-data-type).</span><span class="sxs-lookup"><span data-stu-id="c4262-248">[STIsSimple](/sql/t-sql/spatial-geometry/stissimple-geometry-data-type).</span></span>  
  
  
  
###  <a name="boundary-interior-and-exterior"></a><a name="boundary"></a> <span data-ttu-id="c4262-249">Граница, внутренняя и внешняя область</span><span class="sxs-lookup"><span data-stu-id="c4262-249">Boundary, Interior, and Exterior</span></span>  
 <span data-ttu-id="c4262-250">*Внутренняя* часть `geometry` экземпляра — это пространство, занимаемое экземпляром, а *наружное* пространство не занято.</span><span class="sxs-lookup"><span data-stu-id="c4262-250">The *interior* of a `geometry` instance is the space occupied by the instance, and the *exterior* is the space not occupied it.</span></span>  
  
 <span data-ttu-id="c4262-251">*Граница* определяется в OGC следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c4262-251">*Boundary* is defined by the OGC as follows:</span></span>  
  
-   <span data-ttu-id="c4262-252">Экземпляры `Point` и `MultiPoint` не имеют границы.</span><span class="sxs-lookup"><span data-stu-id="c4262-252">`Point` and `MultiPoint` instances do not have a boundary.</span></span>  
  
-   <span data-ttu-id="c4262-253">Границы `LineString` и `MultiLineString` образуются начальными и конечными точками, за исключением тех, которые появляются четное число раз.</span><span class="sxs-lookup"><span data-stu-id="c4262-253">`LineString` and `MultiLineString` boundaries are formed by the start points and end points, removing those that occur an even number of times.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 1, 0 0, 1 0, 0 1), (1 1, 1 0))');  
SELECT @g.STBoundary().ToString();  
```  
  
 <span data-ttu-id="c4262-254">Граница экземпляра `Polygon` или `MultiPolygon` — это совокупность его колец.</span><span class="sxs-lookup"><span data-stu-id="c4262-254">The boundary of a `Polygon` or `MultiPolygon` instance is the set of its rings.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POLYGON((0 0, 3 0, 3 3, 0 3, 0 0), (1 1, 1 2, 2 2, 2 1, 1 1))');  
SELECT @g.STBoundary().ToString();  
```  
  
 <span data-ttu-id="c4262-255">**Получение границы экземпляра**</span><span class="sxs-lookup"><span data-stu-id="c4262-255">**To return the boundary of an instance**</span></span>  
 [<span data-ttu-id="c4262-256">STBoundary</span><span class="sxs-lookup"><span data-stu-id="c4262-256">STBoundary</span></span>](/sql/t-sql/spatial-geometry/stboundary-geometry-data-type)  
  
  
  
###  <a name="envelope"></a><a name="envelope"></a> <span data-ttu-id="c4262-257">Огибающая</span><span class="sxs-lookup"><span data-stu-id="c4262-257">Envelope</span></span>  
 <span data-ttu-id="c4262-258">*Конверт* `geometry` экземпляра, который также называется *ограничивающим*прямоугольником, представляет собой прямоугольно-ориентированное окно, сформированное с помощью координат (X, Y) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c4262-258">The *envelope* of a `geometry` instance, also known as the *bounding box*, is the axis-aligned rectangle formed by the minimum and maximum (X,Y) coordinates of the instance.</span></span>  
  
 <span data-ttu-id="c4262-259">**Получение огибающей экземпляра**</span><span class="sxs-lookup"><span data-stu-id="c4262-259">**To return the envelope of an instance**</span></span>  
 [<span data-ttu-id="c4262-260">STEnvelope</span><span class="sxs-lookup"><span data-stu-id="c4262-260">STEnvelope</span></span>](/sql/t-sql/spatial-geometry/stenvelope-geometry-data-type)  
  
  
  
###  <a name="closure"></a><a name="closure"></a> <span data-ttu-id="c4262-261">Замыкание</span><span class="sxs-lookup"><span data-stu-id="c4262-261">Closure</span></span>  
 <span data-ttu-id="c4262-262">*Закрытый* `geometry` экземпляр — это фигура, начальная и конечная точки которой одинаковы.</span><span class="sxs-lookup"><span data-stu-id="c4262-262">A *closed*`geometry` instance is a figure whose start points and end points are the same.</span></span> <span data-ttu-id="c4262-263">Экземпляры `Polygon` считаются замкнутыми.</span><span class="sxs-lookup"><span data-stu-id="c4262-263">`Polygon` instances are considered closed.</span></span> <span data-ttu-id="c4262-264">Экземпляры `Point` не замкнуты.</span><span class="sxs-lookup"><span data-stu-id="c4262-264">`Point` instances are not closed.</span></span>  
  
 <span data-ttu-id="c4262-265">Кольцо — это простой замкнутый экземпляр `LineString`.</span><span class="sxs-lookup"><span data-stu-id="c4262-265">A ring is a simple, closed `LineString` instance.</span></span>  
  
 <span data-ttu-id="c4262-266">**Определение, является ли экземпляр замкнутым**</span><span class="sxs-lookup"><span data-stu-id="c4262-266">**To determine if an instance is closed**</span></span>  
 [<span data-ttu-id="c4262-267">STIsClosed</span><span class="sxs-lookup"><span data-stu-id="c4262-267">STIsClosed</span></span>](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type)  
  
 <span data-ttu-id="c4262-268">**Определение, является ли экземпляр кольцом**</span><span class="sxs-lookup"><span data-stu-id="c4262-268">**To determine if an instance is a ring**</span></span>  
 [<span data-ttu-id="c4262-269">STIsRing</span><span class="sxs-lookup"><span data-stu-id="c4262-269">STIsRing</span></span>](/sql/t-sql/spatial-geometry/stisring-geometry-data-type)  
  
 <span data-ttu-id="c4262-270">**Получение внешнего кольца экземпляра Polygon**</span><span class="sxs-lookup"><span data-stu-id="c4262-270">**To return the exterior ring of a Polygon instance**</span></span>  
 [<span data-ttu-id="c4262-271">STExteriorRing</span><span class="sxs-lookup"><span data-stu-id="c4262-271">STExteriorRing</span></span>](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type)  
  
 <span data-ttu-id="c4262-272">**Получение числа внутренних колец в экземпляре Polygon**</span><span class="sxs-lookup"><span data-stu-id="c4262-272">**To return the number of interior rings in a Polygon**</span></span>  
 [<span data-ttu-id="c4262-273">STNumInteriorRing</span><span class="sxs-lookup"><span data-stu-id="c4262-273">STNumInteriorRing</span></span>](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type)  
  
 <span data-ttu-id="c4262-274">**Получение конкретного внутреннего кольца в экземпляре Polygon**</span><span class="sxs-lookup"><span data-stu-id="c4262-274">**To return a specified interior ring of a Polygon**</span></span>  
 [<span data-ttu-id="c4262-275">STInteriorRingN</span><span class="sxs-lookup"><span data-stu-id="c4262-275">STInteriorRingN</span></span>](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type)  
  
  
  
###  <a name="spatial-reference-id-srid"></a><a name="srid"></a> <span data-ttu-id="c4262-276">Идентификатор пространственной ссылки (SRID)</span><span class="sxs-lookup"><span data-stu-id="c4262-276">Spatial Reference ID (SRID)</span></span>  
 <span data-ttu-id="c4262-277">Идентификатор пространственной ссылки (SRID) — это идентификатор, указывающий, в какой системе координат представлен экземпляр `geometry`.</span><span class="sxs-lookup"><span data-stu-id="c4262-277">The spatial reference ID (SRID) is an identifier specifying which coordinate system the `geometry` instance is represented in.</span></span> <span data-ttu-id="c4262-278">Два экземпляра с разными идентификаторами SRID несравнимы.</span><span class="sxs-lookup"><span data-stu-id="c4262-278">Two instances with different SRIDs are incomparable.</span></span>  
  
 <span data-ttu-id="c4262-279">**Задание или возврат идентификатора SRID экземпляра**</span><span class="sxs-lookup"><span data-stu-id="c4262-279">**To set or return the SRID of an instance**</span></span>  
 [<span data-ttu-id="c4262-280">STSrid</span><span class="sxs-lookup"><span data-stu-id="c4262-280">STSrid</span></span>](/sql/t-sql/spatial-geometry/stsrid-geometry-data-type)  
  
 <span data-ttu-id="c4262-281">Это свойство можно изменять.</span><span class="sxs-lookup"><span data-stu-id="c4262-281">This property can be modified.</span></span>  
  
  
  
##  <a name="determining-relationships-between-geometry-instances"></a><a name="rel"></a> <span data-ttu-id="c4262-282">Определение связей между геометрическими объектами</span><span class="sxs-lookup"><span data-stu-id="c4262-282">Determining Relationships between geometry Instances</span></span>  
 <span data-ttu-id="c4262-283">Тип данных `geometry` предоставляет множество встроенных методов, с помощью которых можно определить связи между двумя объектами типа `geometry`.</span><span class="sxs-lookup"><span data-stu-id="c4262-283">The `geometry` data type provides many built-in methods you can use to determine relationships between two `geometry` instances.</span></span>  
  
 <span data-ttu-id="c4262-284">**Определение возможного наличия одинакового набора точек в двух объектах**</span><span class="sxs-lookup"><span data-stu-id="c4262-284">**To determine if two instances comprise the same point set**</span></span>  
 [<span data-ttu-id="c4262-285">STEquals</span><span class="sxs-lookup"><span data-stu-id="c4262-285">STEquals</span></span>](/sql/t-sql/spatial-geometry/stequals-geometry-data-type)  
  
 <span data-ttu-id="c4262-286">**Определение отсутствия перекрытия двух объектов**</span><span class="sxs-lookup"><span data-stu-id="c4262-286">**To determine if two instances are disjoint**</span></span>  
 [<span data-ttu-id="c4262-287">STDisjoint</span><span class="sxs-lookup"><span data-stu-id="c4262-287">STDisjoint</span></span>](/sql/t-sql/spatial-geometry/stdisjoint-geometry-data-type)  
  
 <span data-ttu-id="c4262-288">**Определение пересечения двух объектов**</span><span class="sxs-lookup"><span data-stu-id="c4262-288">**To determine if two instances intersect**</span></span>  
 [<span data-ttu-id="c4262-289">STIntersects</span><span class="sxs-lookup"><span data-stu-id="c4262-289">STIntersects</span></span>](/sql/t-sql/spatial-geometry/stintersects-geometry-data-type)  
  
 <span data-ttu-id="c4262-290">**Определение соприкосновений двух экземпляров**</span><span class="sxs-lookup"><span data-stu-id="c4262-290">**To determine if two instances touch**</span></span>  
 [<span data-ttu-id="c4262-291">STTouches</span><span class="sxs-lookup"><span data-stu-id="c4262-291">STTouches</span></span>](/sql/t-sql/spatial-geometry/sttouches-geometry-data-type)  
  
 <span data-ttu-id="c4262-292">**Определение перекрещивания двух экземпляров**</span><span class="sxs-lookup"><span data-stu-id="c4262-292">**To determine if two instances overlap**</span></span>  
 [<span data-ttu-id="c4262-293">STOverlaps</span><span class="sxs-lookup"><span data-stu-id="c4262-293">STOverlaps</span></span>](/sql/t-sql/spatial-geometry/stoverlaps-geometry-data-type)  
  
 <span data-ttu-id="c4262-294">**Определение пересечения двух экземпляров**</span><span class="sxs-lookup"><span data-stu-id="c4262-294">**To determine if two instances cross**</span></span>  
 [<span data-ttu-id="c4262-295">STCrosses</span><span class="sxs-lookup"><span data-stu-id="c4262-295">STCrosses</span></span>](/sql/t-sql/spatial-geometry/stcrosses-geometry-data-type)  
  
 <span data-ttu-id="c4262-296">**Определение нахождения одного экземпляра в другом**</span><span class="sxs-lookup"><span data-stu-id="c4262-296">**To determine if one instance is within another**</span></span>  
 [<span data-ttu-id="c4262-297">STWithin</span><span class="sxs-lookup"><span data-stu-id="c4262-297">STWithin</span></span>](/sql/t-sql/spatial-geometry/stwithin-geometry-data-type)  
  
 <span data-ttu-id="c4262-298">**Определение содержания одного экземпляра другим**</span><span class="sxs-lookup"><span data-stu-id="c4262-298">**To determine if one instance contains another**</span></span>  
 [<span data-ttu-id="c4262-299">STContains</span><span class="sxs-lookup"><span data-stu-id="c4262-299">STContains</span></span>](/sql/t-sql/spatial-geometry/stcontains-geometry-data-type)  
  
 <span data-ttu-id="c4262-300">**Определение перекрещивания одного экземпляра с другим**</span><span class="sxs-lookup"><span data-stu-id="c4262-300">**To determine if one instance overlaps another**</span></span>  
 [<span data-ttu-id="c4262-301">STOverlaps</span><span class="sxs-lookup"><span data-stu-id="c4262-301">STOverlaps</span></span>](/sql/t-sql/spatial-geometry/stoverlaps-geometry-data-type)  
  
 <span data-ttu-id="c4262-302">**Определение пространственной связи двух экземпляров**</span><span class="sxs-lookup"><span data-stu-id="c4262-302">**To determine if two instances are spatially related**</span></span>  
 [<span data-ttu-id="c4262-303">STRelate</span><span class="sxs-lookup"><span data-stu-id="c4262-303">STRelate</span></span>](/sql/t-sql/spatial-geometry/strelate-geometry-data-type)  
  
 <span data-ttu-id="c4262-304">**Определение кратчайшего пути между точками двух геометрических экземпляров**</span><span class="sxs-lookup"><span data-stu-id="c4262-304">**To determine the shortest distance between points in two geometries**</span></span>  
 [<span data-ttu-id="c4262-305">STDistance</span><span class="sxs-lookup"><span data-stu-id="c4262-305">STDistance</span></span>](/sql/t-sql/spatial-geometry/stdistance-geometry-data-type)  
  
  
  
##  <a name="geometry-instances-default-to-zero-srid"></a><a name="defaultsrid"></a> <span data-ttu-id="c4262-306">Значение по умолчанию, равное 0, для идентификаторов SRID экземпляров геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="c4262-306">geometry Instances Default to Zero SRID</span></span>  
 <span data-ttu-id="c4262-307">Идентификатор SRID для экземпляров `geometry` в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеет значение по умолчанию, равное 0.</span><span class="sxs-lookup"><span data-stu-id="c4262-307">The default SRID for `geometry` instances in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is 0.</span></span> <span data-ttu-id="c4262-308">При работе с пространственными данными типа `geometry` конкретный идентификатор SRID пространственного экземпляра для выполнения вычислений не требуется. Таким образом, экземпляры могут находиться в неопределенном двумерном пространстве.</span><span class="sxs-lookup"><span data-stu-id="c4262-308">With `geometry` spatial data, the specific SRID of the spatial instance is not required to perform calculations; thus, instances can reside in undefined planar space.</span></span> <span data-ttu-id="c4262-309">Чтобы указать неопределенное двумерное пространство в вычислениях методов работы с типом данных `geometry`, в компоненте [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] используется значение SRID, равное 0.</span><span class="sxs-lookup"><span data-stu-id="c4262-309">To indicate undefined planar space in the calculations of `geometry` data type methods, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses SRID 0.</span></span>  
  
##  <a name="examples"></a><a name="examples"></a> <span data-ttu-id="c4262-310">Примеры</span><span class="sxs-lookup"><span data-stu-id="c4262-310">Examples</span></span>  
 <span data-ttu-id="c4262-311">В следующих двух примерах иллюстрируется добавление и запрос геометрических данных.</span><span class="sxs-lookup"><span data-stu-id="c4262-311">The following two examples show how to add and query geometry data.</span></span>  
  
-   <span data-ttu-id="c4262-312">В первом примере создается таблица со столбцом идентификаторов и столбцом `geometry` типа `GeomCol1`.</span><span class="sxs-lookup"><span data-stu-id="c4262-312">The first example creates a table with an identity column and a `geometry` column `GeomCol1`.</span></span> <span data-ttu-id="c4262-313">Третий столбец обрабатывает столбец `geometry` для представления в формате известного текста (WKT) OGC, используя метод `STAsText()` .</span><span class="sxs-lookup"><span data-stu-id="c4262-313">A third column renders the `geometry` column into its Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation, and uses the `STAsText()` method.</span></span> <span data-ttu-id="c4262-314">Затем вставляются две строки: одна строка содержит объект `LineString` типа `geometry`, а другая — объект `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="c4262-314">Two rows are then inserted: one row contains a `LineString` instance of `geometry`, and one row contains a `Polygon` instance.</span></span>  
  
    ```  
    IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
        DROP TABLE dbo.SpatialTable;  
    GO  
  
    CREATE TABLE SpatialTable   
        ( id int IDENTITY (1,1),  
        GeomCol1 geometry,   
        GeomCol2 AS GeomCol1.STAsText() );  
    GO  
  
    INSERT INTO SpatialTable (GeomCol1)  
    VALUES (geometry::STGeomFromText('LINESTRING (100 100, 20 180, 180 180)', 0));  
  
    INSERT INTO SpatialTable (GeomCol1)  
    VALUES (geometry::STGeomFromText('POLYGON ((0 0, 150 0, 150 150, 0 150, 0 0))', 0));  
    GO  
    ```  
  
-   <span data-ttu-id="c4262-315">Во втором примере метод `STIntersection()` используется для получения точек, в которых пересекаются два вставленные ранее объекта `geometry` .</span><span class="sxs-lookup"><span data-stu-id="c4262-315">The second example uses the `STIntersection()` method to return the points where the two previously inserted `geometry` instances intersect.</span></span>  
  
    ```  
    DECLARE @geom1 geometry;  
    DECLARE @geom2 geometry;  
    DECLARE @result geometry;  
  
    SELECT @geom1 = GeomCol1 FROM SpatialTable WHERE id = 1;  
    SELECT @geom2 = GeomCol1 FROM SpatialTable WHERE id = 2;  
    SELECT @result = @geom1.STIntersection(@geom2);  
    SELECT @result.STAsText();  
    ```  
  
  
  
## <a name="see-also"></a><span data-ttu-id="c4262-316">См. также:</span><span class="sxs-lookup"><span data-stu-id="c4262-316">See Also</span></span>  
 [<span data-ttu-id="c4262-317">Пространственные данные (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c4262-317">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
