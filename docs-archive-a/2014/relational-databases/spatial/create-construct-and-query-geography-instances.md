---
title: Создание и конструирование географических экземпляров и отправка запросов к ним | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geography data type [SQL Server]
- geodetic data type [SQL Server]
- geography data type [SQL Server], about geography data type
ms.assetid: b585851e-d15b-411f-adeb-aeabeb777c0b
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: d744457cc517a6172cca96b27eae1f456deca24e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655573"
---
# <a name="create-construct-and-query-geography-instances"></a><span data-ttu-id="0d695-102">Создание, проектирование и создание запросов к экземплярам типа данных geography</span><span class="sxs-lookup"><span data-stu-id="0d695-102">Create, Construct, and Query geography Instances</span></span>
  <span data-ttu-id="0d695-103">Тип пространственных данных `geography` представляет данные в системе координат круглой земли.</span><span class="sxs-lookup"><span data-stu-id="0d695-103">The geography spatial data type, `geography`, represents data in a round-earth coordinate system.</span></span> <span data-ttu-id="0d695-104">Этот тип реализован как тип данных среды CLR .NET в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d695-104">This type is implemented as a .NET common language runtime (CLR) data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0d695-105">Тип данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `geography` хранит данные для эллипсоидальной (сферической) Земли, такие как координаты широты и долготы GPS.</span><span class="sxs-lookup"><span data-stu-id="0d695-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `geography` data type stores ellipsoidal (round-earth) data, such as GPS latitude and longitude coordinates.</span></span>  
  
 <span data-ttu-id="0d695-106">Тип `geography` является стандартным и доступен в каждой базе данных.</span><span class="sxs-lookup"><span data-stu-id="0d695-106">The `geography` type is predefined and available in each database.</span></span> <span data-ttu-id="0d695-107">В таблице можно создать столбцы типа `geography` и обращаться с данными `geography` так же, как с данными других предусмотренных в системе типов.</span><span class="sxs-lookup"><span data-stu-id="0d695-107">You can create table columns of type `geography` and operate on `geography` data in the same manner as you would use other system-supplied types.</span></span>  
  
##  <a name="creating-or-constructing-a-new-geography-instance"></a><a name="creating"></a> <span data-ttu-id="0d695-108">Создание или построение нового экземпляра географического объекта</span><span class="sxs-lookup"><span data-stu-id="0d695-108">Creating or constructing a new geography instance</span></span>  
  
###  <a name="creating-a-new-geography-instance-from-an-existing-instance"></a><a name="existing"></a> <span data-ttu-id="0d695-109">Создание нового экземпляра географического объекта из существующего экземпляра</span><span class="sxs-lookup"><span data-stu-id="0d695-109">Creating a New geography Instance from an Existing Instance</span></span>  
 <span data-ttu-id="0d695-110">Тип данных `geography` содержит множество встроенных методов, с помощью которых можно создавать новые объекты `geography` на основе существующих.</span><span class="sxs-lookup"><span data-stu-id="0d695-110">The `geography` data type provides numerous built-in methods you can use to create new `geography` instances based on existing instances.</span></span>  
  
 <span data-ttu-id="0d695-111">**Создание буфера вокруг географического объекта**</span><span class="sxs-lookup"><span data-stu-id="0d695-111">**To create a buffer around a geography**</span></span>  
 [<span data-ttu-id="0d695-112">STBuffer (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-112">STBuffer &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stbuffer-geography-data-type)  
  
 <span data-ttu-id="0d695-113">**Создание буфера вокруг географического объекта с допуском**</span><span class="sxs-lookup"><span data-stu-id="0d695-113">**To create a buffer around a geography, allowing for a tolerance**</span></span>  
 [<span data-ttu-id="0d695-114">BufferWithTolerance (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-114">BufferWithTolerance &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/bufferwithtolerance-geography-data-type)  
  
 <span data-ttu-id="0d695-115">**Создание географического объекта из пересечения двух географических объектов**</span><span class="sxs-lookup"><span data-stu-id="0d695-115">**To create a geography from the intersection of two geography instances**</span></span>  
 [<span data-ttu-id="0d695-116">STIntersection (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-116">STIntersection &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stintersection-geography-data-type)  
  
 <span data-ttu-id="0d695-117">**Создание географического объекта из объединения двух географических объектов**</span><span class="sxs-lookup"><span data-stu-id="0d695-117">**To create a geography from the union of two geography instances**</span></span>  
 [<span data-ttu-id="0d695-118">STUnion (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-118">STUnion &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stunion-geography-data-type)  
  
 <span data-ttu-id="0d695-119">**Создание географического объекта из точек, в которых один объект не пересекается с другим**</span><span class="sxs-lookup"><span data-stu-id="0d695-119">**To create a geography from the points where one geography does not overlap another**</span></span>  
 [<span data-ttu-id="0d695-120">STDifference (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-120">STDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdifference-geography-data-type)  
  
###  <a name="constructing-a-geography-instance-from-well-known-text-input"></a><a name="wkt"></a> <span data-ttu-id="0d695-121">Построение экземпляра географического объекта на основе входных данных в формате Well-Known Text</span><span class="sxs-lookup"><span data-stu-id="0d695-121">Constructing a geography Instance from Well-Known Text Input</span></span>  
 <span data-ttu-id="0d695-122">Тип данных `geography` предоставляет несколько встроенных методов, позволяющих создать экземпляр типа geography на основе представления Open Geospatial Consortium (OGC) WKT.</span><span class="sxs-lookup"><span data-stu-id="0d695-122">The `geography` data type provides several built-in methods that generate a geography from the Open Geospatial Consortium (OGC) WKT representation.</span></span> <span data-ttu-id="0d695-123">Стандарт WKT представляет собой текстовую строку, позволяющую осуществлять обмен географическими данными в текстовой форме.</span><span class="sxs-lookup"><span data-stu-id="0d695-123">The WKT standard is a text string that allows geography data to be exchanged in textual form.</span></span>  
  
 <span data-ttu-id="0d695-124">**Создание экземпляра географического объекта любого типа на основе входных данных в формате WKT**</span><span class="sxs-lookup"><span data-stu-id="0d695-124">**To construct any type of geography instance from WKT input**</span></span>  
 [<span data-ttu-id="0d695-125">STGeomFromText (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-125">STGeomFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)  
  
 [<span data-ttu-id="0d695-126">Parse (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-126">Parse &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/parse-geography-data-type)  
  
 <span data-ttu-id="0d695-127">**Создание экземпляра географического объекта Point на основе входных данных в формате WKT**</span><span class="sxs-lookup"><span data-stu-id="0d695-127">**To construct a geography Point instance from WKT input**</span></span>  
 [<span data-ttu-id="0d695-128">STPointFromText (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-128">STPointFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpointfromtext-geography-data-type)  
  
 <span data-ttu-id="0d695-129">**Создание экземпляра географического объекта MultiPoint на основе входных данных в формате WKT**</span><span class="sxs-lookup"><span data-stu-id="0d695-129">**To construct a geography MultiPoint instance from WKT input**</span></span>  
 [<span data-ttu-id="0d695-130">STMPointFromText (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-130">STMPointFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpointfromtext-geography-data-type)  
  
 <span data-ttu-id="0d695-131">**Создание экземпляра географического объекта LineString на основе входных данных в формате WKT**</span><span class="sxs-lookup"><span data-stu-id="0d695-131">**To construct a geography LineString instance from WKT input**</span></span>  
 <span data-ttu-id="0d695-132">STLineFromText (географический тип данных)</span><span class="sxs-lookup"><span data-stu-id="0d695-132">STLineFromText (geography Data Type)</span></span>  
  
 <span data-ttu-id="0d695-133">**Создание экземпляра географического объекта MultiLineString на основе входных данных в формате WKT**</span><span class="sxs-lookup"><span data-stu-id="0d695-133">**To construct a geography MultiLineString instance from WKT input**</span></span>  
 [<span data-ttu-id="0d695-134">STMLineFromText (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-134">STMLineFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmlinefromtext-geography-data-type)  
  
 <span data-ttu-id="0d695-135">**Создание экземпляра географического объекта Polygon на основе входных данных в формате WKT**</span><span class="sxs-lookup"><span data-stu-id="0d695-135">**To construct a geography Polygon instance from WKT input**</span></span>  
 [<span data-ttu-id="0d695-136">STPolyFromText (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-136">STPolyFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpolyfromtext-geography-data-type)  
  
 <span data-ttu-id="0d695-137">**Создание экземпляра географического объекта MultiPolygon на основе входных данных в формате WKT**</span><span class="sxs-lookup"><span data-stu-id="0d695-137">**To construct a geography MultiPolygon instance from WKT input**</span></span>  
 [<span data-ttu-id="0d695-138">STMPolyFromText (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-138">STMPolyFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpolyfromtext-geography-data-type)  
  
 <span data-ttu-id="0d695-139">**Создание экземпляра географического объекта GeometryCollection на основе входных данных в формате WKT**</span><span class="sxs-lookup"><span data-stu-id="0d695-139">**To construct a geography GeometryCollection instance from WKT input**</span></span>  
 [<span data-ttu-id="0d695-140">STGeomCollFromText (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-140">STGeomCollFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomcollfromtext-geography-data-type)  
  
###  <a name="constructing-a-geography-instance-from-well-known-binary-input"></a><a name="wkb"></a> <span data-ttu-id="0d695-141">Построение экземпляра географического объекта на основе входных данных в формате Well-Known Binary</span><span class="sxs-lookup"><span data-stu-id="0d695-141">Constructing a geography Instance from Well-Known Binary Input</span></span>  
 <span data-ttu-id="0d695-142">WKB представляет собой описанный консорциумом OGC двоичный формат, позволяющий осуществлять обмен данными типа `Geography` между клиентскими приложениями и базой данных SQL.</span><span class="sxs-lookup"><span data-stu-id="0d695-142">WKB is a binary format specified by the OGC that permits `Geography` data to be exchanged between a client application and an SQL database.</span></span> <span data-ttu-id="0d695-143">С помощью следующих функций создаются экземпляры географических объектов на основе входных данных WKB:</span><span class="sxs-lookup"><span data-stu-id="0d695-143">The following functions accept WKB input to construct geography instances:</span></span>  
  
 <span data-ttu-id="0d695-144">**Создание экземпляра географического объекта любого типа на основе входных данных в формате WKB**</span><span class="sxs-lookup"><span data-stu-id="0d695-144">**To construct any type of geography instance from WKB input**</span></span>  
 [<span data-ttu-id="0d695-145">STGeomFromWKB (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-145">STGeomFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomfromwkb-geography-data-type)  
  
 <span data-ttu-id="0d695-146">**Создание экземпляра географического объекта Point на основе входных данных в формате WKB**</span><span class="sxs-lookup"><span data-stu-id="0d695-146">**To construct a geography Point instance from WKB input**</span></span>  
 [<span data-ttu-id="0d695-147">STPointFromWKB (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-147">STPointFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpointfromwkb-geography-data-type)  
  
 <span data-ttu-id="0d695-148">**Создание экземпляра географического объекта MultiPoint на основе входных данных в формате WKB**</span><span class="sxs-lookup"><span data-stu-id="0d695-148">**To construct a geography MultiPoint instance from WKB input**</span></span>  
 [<span data-ttu-id="0d695-149">STMPointFromWKB (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-149">STMPointFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpointfromwkb-geography-data-type)  
  
 <span data-ttu-id="0d695-150">**Создание экземпляра географического объекта LineString на основе входных данных в формате WKB**</span><span class="sxs-lookup"><span data-stu-id="0d695-150">**To construct a geography LineString instance from WKB input**</span></span>  
 [<span data-ttu-id="0d695-151">STLineFromWKB (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-151">STLineFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stlinefromwkb-geography-data-type)  
  
 <span data-ttu-id="0d695-152">**Создание экземпляра географического объекта MultiLineString на основе входных данных в формате WKB**</span><span class="sxs-lookup"><span data-stu-id="0d695-152">**To construct a geography MultiLineString instance from WKB input**</span></span>  
 [<span data-ttu-id="0d695-153">STMLineFromWKB (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-153">STMLineFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmlinefromwkb-geography-data-type)  
  
 <span data-ttu-id="0d695-154">**Создание экземпляра географического объекта Polygon на основе входных данных в формате WKB**</span><span class="sxs-lookup"><span data-stu-id="0d695-154">**To construct a geography Polygon instance from WKB input**</span></span>  
 [<span data-ttu-id="0d695-155">STPolyFromWKB (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-155">STPolyFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpolyfromwkb-geography-data-type)  
  
 <span data-ttu-id="0d695-156">**Создание экземпляра географического объекта MultiPolygon на основе входных данных в формате WKB**</span><span class="sxs-lookup"><span data-stu-id="0d695-156">**To construct a geography MultiPolygon instance from WKB input**</span></span>  
 [<span data-ttu-id="0d695-157">STMPolyFromWKB (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-157">STMPolyFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpolyfromwkb-geography-data-type)  
  
 <span data-ttu-id="0d695-158">**Создание экземпляра географического объекта GeometryCollection на основе входных данных в формате WKB**</span><span class="sxs-lookup"><span data-stu-id="0d695-158">**To construct a geography GeometryCollection instance from WKB input**</span></span>  
 <span data-ttu-id="0d695-159">[STGeomCollFromWKB (тип данных geography)](/sql/t-sql/spatial-geography/stgeomcollfromwkb-geography-data-type)STGeomCollFromWKB (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-159">[STGeomCollFromWKB &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomcollfromwkb-geography-data-type)STGeomCollFromWKB (geography Data Type)</span></span>  
  
###  <a name="constructing-a-geography-instance-from-gml-text-input"></a><a name="gml"></a> <span data-ttu-id="0d695-160">Построение экземпляра географического объекта на основе входных данных в формате GML Text</span><span class="sxs-lookup"><span data-stu-id="0d695-160">Constructing a geography Instance from GML Text Input</span></span>  
 <span data-ttu-id="0d695-161">`geography`Тип данных предоставляет метод, создающий `geography` экземпляр из GML, XML-представление `geography` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0d695-161">The `geography` data type provides a method that generates a `geography` instance from GML, an XML representation of a `geography` instance.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0d695-162">поддерживает подмножество GML.</span><span class="sxs-lookup"><span data-stu-id="0d695-162">supports a subset of GML.</span></span>  
  
 <span data-ttu-id="0d695-163">Дополнительные сведения о языке GML см. в спецификации OGC: [Спецификации OGC, географический язык разметки.](https://go.microsoft.com/fwlink/?LinkId=93629)</span><span class="sxs-lookup"><span data-stu-id="0d695-163">For more information on Geography Markup Language, see the OGC Specification: [OGC Specifications, Geography Markup Language.](https://go.microsoft.com/fwlink/?LinkId=93629)</span></span>  
  
 <span data-ttu-id="0d695-164">**Создание экземпляра географического объекта любого типа на основе входных данных в формате GML**</span><span class="sxs-lookup"><span data-stu-id="0d695-164">**To construct any type of geography instance from GML input**</span></span>  
 [<span data-ttu-id="0d695-165">GeomFromGML (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-165">GeomFromGML &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/geomfromgml-geography-data-type)  
  
##  <a name="returning-well-known-text-and-well-known-binary-from-a-geography-instance"></a><a name="returning"></a> <span data-ttu-id="0d695-166">Получение данных в формате Well-Known Text и Well-Known Binary из экземпляра географического объекта</span><span class="sxs-lookup"><span data-stu-id="0d695-166">Returning Well-Known Text and Well-Known Binary from a geography Instance</span></span>  
 <span data-ttu-id="0d695-167">Можно использовать следующие методы для получения данных экземпляра `geography` в формате WKT или формате WKB:</span><span class="sxs-lookup"><span data-stu-id="0d695-167">You can use the following methods to return either the WKT or WKB format of a `geography` instance:</span></span>  
  
 <span data-ttu-id="0d695-168">**Возврат WKT-представления экземпляра географического объекта**</span><span class="sxs-lookup"><span data-stu-id="0d695-168">**To return the WKT representation of a geography instance**</span></span>  
 [<span data-ttu-id="0d695-169">STAsText (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-169">STAsText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stastext-geography-data-type)  
  
 [<span data-ttu-id="0d695-170">ToString (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-170">ToString &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/tostring-geography-data-type)  
  
 <span data-ttu-id="0d695-171">**Получение представления экземпляра географического объекта в формате WKT, включая все значения Z и M**</span><span class="sxs-lookup"><span data-stu-id="0d695-171">**To return the WKT representation of a geography instance including any Z and M values**</span></span>  
 [<span data-ttu-id="0d695-172">AsTextZM (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-172">AsTextZM &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/astextzm-geography-data-type)  
  
 <span data-ttu-id="0d695-173">**Возврат WKB-представления экземпляра географического объекта**</span><span class="sxs-lookup"><span data-stu-id="0d695-173">**To return the WKB representation of a geography instance**</span></span>  
 [<span data-ttu-id="0d695-174">STAsBinary (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-174">STAsBinary &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stasbinary-geography-data-type)  
  
 <span data-ttu-id="0d695-175">**Возврат GML-представления экземпляра географического объекта**</span><span class="sxs-lookup"><span data-stu-id="0d695-175">**To return a GML representation of a geography instance**</span></span>  
 [<span data-ttu-id="0d695-176">AsGml (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-176">AsGml &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/asgml-geography-data-type)  
  
##  <a name="querying-the-properties-and-behaviors-of-geography-instances"></a><a name="query"></a> <span data-ttu-id="0d695-177">Выполнение запроса к свойствам и методам экземпляров географических объектов</span><span class="sxs-lookup"><span data-stu-id="0d695-177">Querying the Properties and Behaviors of geography Instances</span></span>  
 <span data-ttu-id="0d695-178">`geography`У всех экземпляров есть ряд свойств, которые можно получить с помощью методов, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предоставляемых.</span><span class="sxs-lookup"><span data-stu-id="0d695-178">All `geography` instances have a number of properties that can be retrieved through methods that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides.</span></span> <span data-ttu-id="0d695-179">В следующих разделах определяются свойства и поведение географических типов, а также методы запросов к каждому из них.</span><span class="sxs-lookup"><span data-stu-id="0d695-179">The following topics define the properties and behaviors of geography types, and the methods for querying each one.</span></span>  
  
###  <a name="validity-instance-type-and-geometrycollection-information"></a><a name="valid"></a> <span data-ttu-id="0d695-180">Допустимость, тип экземпляра и сведения GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="0d695-180">Validity, Instance Type, and GeometryCollection Information</span></span>  
 <span data-ttu-id="0d695-181">Когда экземпляр `geography` создан, можно использовать следующие методы, чтобы получить типа экземпляра или, если это экземпляр `GeometryCollection`, конкретный экземпляр `geography`.</span><span class="sxs-lookup"><span data-stu-id="0d695-181">After a `geography` instance is constructed, you can use the following methods to return the instance type, or if it is a `GeometryCollection` instance, return a specific `geography` instance.</span></span>  
  
 <span data-ttu-id="0d695-182">**Возврат типа географического экземпляра**</span><span class="sxs-lookup"><span data-stu-id="0d695-182">**To return the instance type of a geography**</span></span>  
 [<span data-ttu-id="0d695-183">STGeometryType (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-183">STGeometryType &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeometrytype-geography-data-type)  
  
 <span data-ttu-id="0d695-184">**Определение принадлежности географического экземпляра к заданному типу**</span><span class="sxs-lookup"><span data-stu-id="0d695-184">**To determine if a geography is a given instance type**</span></span>  
 [<span data-ttu-id="0d695-185">InstanceOf (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-185">InstanceOf &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/instanceof-geography-data-type)  
  
 <span data-ttu-id="0d695-186">**Проверка соответствия формата экземпляра географического объекта его типу**</span><span class="sxs-lookup"><span data-stu-id="0d695-186">**To determine if a geography instance is well-formed for its instance type**</span></span>  
 [<span data-ttu-id="0d695-187">STNumGeometries (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-187">STNumGeometries &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stnumgeometries-geography-data-type)  
  
 <span data-ttu-id="0d695-188">**Возврат конкретного географического экземпляра из экземпляра GeometryCollection**</span><span class="sxs-lookup"><span data-stu-id="0d695-188">**To return a specific geography in a GeometryCollection instance**</span></span>  
 <span data-ttu-id="0d695-189">[STGeometryN (тип данных geography)](/sql/t-sql/spatial-geography/stgeometryn-geography-data-type)STGeometryN (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-189">[STGeometryN &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeometryn-geography-data-type)STGeometryN (geography Data Type)</span></span>  
  
###  <a name="number-of-points"></a><a name="number"></a> <span data-ttu-id="0d695-190">Число точек</span><span class="sxs-lookup"><span data-stu-id="0d695-190">Number of Points</span></span>  
 <span data-ttu-id="0d695-191">Все непустые `geography` экземпляры состоят из *точек*.</span><span class="sxs-lookup"><span data-stu-id="0d695-191">All nonempty `geography` instances are comprised of *points*.</span></span> <span data-ttu-id="0d695-192">Данные точки представляют координаты широты и долготы, соответствующие месту создания экземпляров `geography`.</span><span class="sxs-lookup"><span data-stu-id="0d695-192">These points represent the latitude and longitude coordinates of the earth on which the `geography` instances are drawn.</span></span> <span data-ttu-id="0d695-193">В типе данных `geography` предусмотрены многочисленные встроенные методы запросов к точкам экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0d695-193">The data type `geography` provides numerous built-in methods for querying the points of an instance.</span></span>  
  
 <span data-ttu-id="0d695-194">**Получение числа точек, образующих экземпляр**</span><span class="sxs-lookup"><span data-stu-id="0d695-194">**To return the number of points that comprise an instance**</span></span>  
 [<span data-ttu-id="0d695-195">STNumPoints (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-195">STNumPoints &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stnumpoints-geography-data-type)  
  
 <span data-ttu-id="0d695-196">**Получение выбранной точки в экземпляре**</span><span class="sxs-lookup"><span data-stu-id="0d695-196">**To return a specific point in an instance**</span></span>  
 [<span data-ttu-id="0d695-197">STPointN (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="0d695-197">STPointN &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)  
  
 <span data-ttu-id="0d695-198">**Получение начальной точки экземпляра**</span><span class="sxs-lookup"><span data-stu-id="0d695-198">**To return the start point of an instance**</span></span>  
 [<span data-ttu-id="0d695-199">STStartPoint (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-199">STStartPoint &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/ststartpoint-geography-data-type)  
  
 <span data-ttu-id="0d695-200">**Получение конечной точки экземпляра**</span><span class="sxs-lookup"><span data-stu-id="0d695-200">**To return the end point of an instance**</span></span>  
 [<span data-ttu-id="0d695-201">STEndpoint (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-201">STEndpoint &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stendpoint-geography-data-type)  
  
###  <a name="dimension"></a><a name="dimension"></a> <span data-ttu-id="0d695-202">Измерение</span><span class="sxs-lookup"><span data-stu-id="0d695-202">Dimension</span></span>  
 <span data-ttu-id="0d695-203">Непустой объект `geography` может иметь 0, 1 или 2 измерения.</span><span class="sxs-lookup"><span data-stu-id="0d695-203">A nonempty `geography` instance can be 0-, 1-, or 2-dimensional.</span></span> <span data-ttu-id="0d695-204">Экземпляры с нулевым измерением `geography` , такие как `Point` и `MultiPoint` , не имеют длины или площади.</span><span class="sxs-lookup"><span data-stu-id="0d695-204">Zero-dimensional `geography` instances, such as `Point` and `MultiPoint`, have no length or area.</span></span> <span data-ttu-id="0d695-205">Одномерные объекты, такие как `LineString, CircularString`, `CompoundCurve` и `MultiLineString`, имеют длину.</span><span class="sxs-lookup"><span data-stu-id="0d695-205">One-dimensional objects, such as `LineString, CircularString`, `CompoundCurve`, and `MultiLineString`, have length.</span></span> <span data-ttu-id="0d695-206">Двумерные объекты, такие как `Polygon, CurvePolygon` и `MultiPolygon`, имеют длину и площадь.</span><span class="sxs-lookup"><span data-stu-id="0d695-206">Two-dimensional instances, such as `Polygon, CurvePolygon`, and `MultiPolygon`, have area and length.</span></span> <span data-ttu-id="0d695-207">В отчете пустых экземпляров указывается измерение -1, а в отчетах `GeometryCollection` — максимальное измерение содержимого.</span><span class="sxs-lookup"><span data-stu-id="0d695-207">Empty instances report a dimension of -1, and a `GeometryCollection` reports the maximum dimension of its contents.</span></span>  
  
 <span data-ttu-id="0d695-208">**Получение измерения экземпляра**</span><span class="sxs-lookup"><span data-stu-id="0d695-208">**To return the dimension of an instance**</span></span>  
 [<span data-ttu-id="0d695-209">STDimension (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-209">STDimension &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdimension-geography-data-type)  
  
 <span data-ttu-id="0d695-210">**Получение длины экземпляра**</span><span class="sxs-lookup"><span data-stu-id="0d695-210">**To return the length of an instance**</span></span>  
 [<span data-ttu-id="0d695-211">STLength (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-211">STLength &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stlength-geography-data-type)  
  
 <span data-ttu-id="0d695-212">**Получение площади экземпляра**</span><span class="sxs-lookup"><span data-stu-id="0d695-212">**To return the area of an instance**</span></span>  
 [<span data-ttu-id="0d695-213">STArea (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-213">STArea &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/starea-geography-data-type)  
  
###  <a name="empty"></a><a name="empty"></a> <span data-ttu-id="0d695-214">Пустой</span><span class="sxs-lookup"><span data-stu-id="0d695-214">Empty</span></span>  
 <span data-ttu-id="0d695-215">*Пустой* `geography` экземпляр не имеет точек.</span><span class="sxs-lookup"><span data-stu-id="0d695-215">An *empty*`geography` instance does not have any points.</span></span> <span data-ttu-id="0d695-216">Длина пустых экземпляров `LineString, CircularString`, `CompoundCurve` и `MultiLineString` равна 0.</span><span class="sxs-lookup"><span data-stu-id="0d695-216">The length of empty `LineString, CircularString`, `CompoundCurve`, and `MultiLineString` instances is 0.</span></span> <span data-ttu-id="0d695-217">Площадь пустых экземпляров `Polygon, CurvePolygon` и `MultiPolygon` равна 0.</span><span class="sxs-lookup"><span data-stu-id="0d695-217">The area of empty `Polygon, CurvePolygon` and `MultiPolygon` instances is 0.</span></span>  
  
 <span data-ttu-id="0d695-218">**Проверка, является ли экземпляр пустым**</span><span class="sxs-lookup"><span data-stu-id="0d695-218">**To determine if an instance is empty**</span></span>  
 [<span data-ttu-id="0d695-219">STIsEmpty (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-219">STIsEmpty &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stisempty-geography-data-type)  
  
###  <a name="closure"></a><a name="closure"></a> <span data-ttu-id="0d695-220">Замыкание</span><span class="sxs-lookup"><span data-stu-id="0d695-220">Closure</span></span>  
 <span data-ttu-id="0d695-221">*Закрытый* `geography` экземпляр — это фигура, начальная и конечная точки которой одинаковы.</span><span class="sxs-lookup"><span data-stu-id="0d695-221">A *closed*`geography` instance is a figure whose start points and end points are the same.</span></span> <span data-ttu-id="0d695-222">Экземпляры `Polygon` считаются замкнутыми.</span><span class="sxs-lookup"><span data-stu-id="0d695-222">`Polygon` instances are considered closed.</span></span> <span data-ttu-id="0d695-223">Экземпляры `Point` не замкнуты.</span><span class="sxs-lookup"><span data-stu-id="0d695-223">`Point` instances are not closed.</span></span>  
  
 <span data-ttu-id="0d695-224">Кольцо — это простой замкнутый экземпляр `LineString`.</span><span class="sxs-lookup"><span data-stu-id="0d695-224">A ring is a simple, closed `LineString` instance.</span></span>  
  
 <span data-ttu-id="0d695-225">**Определение, является ли экземпляр замкнутым**</span><span class="sxs-lookup"><span data-stu-id="0d695-225">**To determine if an instance is closed**</span></span>  
 [<span data-ttu-id="0d695-226">STIsClosed (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-226">STIsClosed &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stisclosed-geography-data-type)  
  
 <span data-ttu-id="0d695-227">**Получение количества колец экземпляра объекта Polygon**</span><span class="sxs-lookup"><span data-stu-id="0d695-227">**To return the number of rings in a Polygon instance**</span></span>  
 [<span data-ttu-id="0d695-228">NumRings (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-228">NumRings &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/numrings-geography-data-type)  
  
 <span data-ttu-id="0d695-229">**Получение указанного кольца какого-либо географического объекта**</span><span class="sxs-lookup"><span data-stu-id="0d695-229">**To return a specified ring of a geography instance**</span></span>  
 [<span data-ttu-id="0d695-230">RingN (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-230">RingN &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/ringn-geography-data-type)  
  
###  <a name="spatial-reference-id-srid"></a><a name="srid"></a> <span data-ttu-id="0d695-231">Идентификатор пространственной ссылки (SRID)</span><span class="sxs-lookup"><span data-stu-id="0d695-231">Spatial Reference ID (SRID)</span></span>  
 <span data-ttu-id="0d695-232">Идентификатор пространственной ссылки (SRID) представляет собой идентификатор, указывающий на систему эллиптических координат, в которой находится экземпляр `geography`.</span><span class="sxs-lookup"><span data-stu-id="0d695-232">The spatial reference ID (SRID) is an identifier specifying which ellipsoidal coordinate system the `geography` instance is represented in.</span></span> <span data-ttu-id="0d695-233">Сравнение двух экземпляров `geography` с различными идентификаторами SRID невозможно.</span><span class="sxs-lookup"><span data-stu-id="0d695-233">Two `geography` instances with different SRIDs cannot be compared.</span></span>  
  
 <span data-ttu-id="0d695-234">**Задание или возврат идентификатора SRID экземпляра**</span><span class="sxs-lookup"><span data-stu-id="0d695-234">**To set or return the SRID of an instance**</span></span>  
 [<span data-ttu-id="0d695-235">STSrid (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-235">STSrid &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stsrid-geography-data-type)  
  
 <span data-ttu-id="0d695-236">Это свойство можно изменять.</span><span class="sxs-lookup"><span data-stu-id="0d695-236">This property can be modified.</span></span>  
  
##  <a name="determining-relationships-between-geography-instances"></a><a name="rel"></a> <span data-ttu-id="0d695-237">Определение связей между экземплярами географических объектов</span><span class="sxs-lookup"><span data-stu-id="0d695-237">Determining Relationships between geography Instances</span></span>  
 <span data-ttu-id="0d695-238">Тип данных `geography` предоставляет множество встроенных методов, с помощью которых можно определить связи между двумя объектами типа `geography`.</span><span class="sxs-lookup"><span data-stu-id="0d695-238">The `geography` data type provides many built-in methods you can use to determine relationships between two `geography` instances.</span></span>  
  
 <span data-ttu-id="0d695-239">**Определение возможного наличия одинакового набора точек в двух объектах**</span><span class="sxs-lookup"><span data-stu-id="0d695-239">**To determine if two instances comprise the same point set**</span></span>  
 [<span data-ttu-id="0d695-240">STEquals (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="0d695-240">STEquals &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stequals-geometry-data-type)  
  
 <span data-ttu-id="0d695-241">**Определение отсутствия перекрытия двух объектов**</span><span class="sxs-lookup"><span data-stu-id="0d695-241">**To determine if two instances are disjoint**</span></span>  
 [<span data-ttu-id="0d695-242">STDisjoint (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="0d695-242">STDisjoint &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdisjoint-geometry-data-type)  
  
 <span data-ttu-id="0d695-243">**Определение пересечения двух объектов**</span><span class="sxs-lookup"><span data-stu-id="0d695-243">**To determine if two instances intersect**</span></span>  
 [<span data-ttu-id="0d695-244">STIntersects (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="0d695-244">STIntersects &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stintersects-geometry-data-type)  
  
 <span data-ttu-id="0d695-245">**Определение точки или точек пересечения двух объектов**</span><span class="sxs-lookup"><span data-stu-id="0d695-245">**To determine the point or points where two instances intersect**</span></span>  
 [<span data-ttu-id="0d695-246">STIntersection (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-246">STIntersection &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stintersection-geography-data-type)  
  
 <span data-ttu-id="0d695-247">**Определение кратчайшего расстояния между точками двух географических объектов**</span><span class="sxs-lookup"><span data-stu-id="0d695-247">**To determine the shortest distance between points in two geography instances**</span></span>  
 [<span data-ttu-id="0d695-248">STDistance (тип данных geometry)</span><span class="sxs-lookup"><span data-stu-id="0d695-248">STDistance &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdistance-geometry-data-type)  
  
 <span data-ttu-id="0d695-249">**Определение разницы в точках между двумя географическими объектами**</span><span class="sxs-lookup"><span data-stu-id="0d695-249">**To determine the difference in points between two geography instances**</span></span>  
 [<span data-ttu-id="0d695-250">STDifference (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-250">STDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdifference-geography-data-type)  
  
 <span data-ttu-id="0d695-251">**Получение симметрической разницы (или уникальных точек) между двумя экземплярами географических объектов**</span><span class="sxs-lookup"><span data-stu-id="0d695-251">**To derive the symmetric difference, or unique points, of one geography instance compared with another instance**</span></span>  
 [<span data-ttu-id="0d695-252">STSymDifference (тип данных geography)</span><span class="sxs-lookup"><span data-stu-id="0d695-252">STSymDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stsymdifference-geography-data-type)  
  
##  <a name="geography-instances-must-use-supported-srid"></a><a name="supportedsrid"></a> <span data-ttu-id="0d695-253">Обязательное использование поддерживаемых SRID в экземплярах географических объектах</span><span class="sxs-lookup"><span data-stu-id="0d695-253">geography Instances Must Use Supported SRID</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0d695-254">поддерживаются идентификаторы SRID, основанные на стандартах EPSG.</span><span class="sxs-lookup"><span data-stu-id="0d695-254">supports SRIDs based on the EPSG standards.</span></span> <span data-ttu-id="0d695-255">При выполнении вычислений или применении методов работы с географическими пространственными данными должны использоваться поддерживаемые [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] идентификаторы SRID для экземпляров `geography`.</span><span class="sxs-lookup"><span data-stu-id="0d695-255">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-supported SRID for `geography` instances must be used when performing calculations or using methods with geography spatial data.</span></span> <span data-ttu-id="0d695-256">Заданный SRID должен соответствовать одному из идентификаторов SRID, отображенных в представлении каталога **sys.spatial_reference_systems** .</span><span class="sxs-lookup"><span data-stu-id="0d695-256">The SRID must match one of the SRIDs displayed in the **sys.spatial_reference_systems** catalog view.</span></span> <span data-ttu-id="0d695-257">Как было упомянуто ранее, результаты вычислений на пространственных данных с использованием типа данных `geography` зависят от эллипсоида, использованного при создании рабочих данных, поскольку каждому эллипсоиду назначается отдельный идентификатор пространственной ссылки (SRID).</span><span class="sxs-lookup"><span data-stu-id="0d695-257">As mentioned previously, when you perform calculations on your spatial data using the `geography` data type, your results will depend on which ellipsoid was used in the creation of your data, as each ellipsoid is assigned a specific spatial reference identifier (SRID).</span></span>  
  
 <span data-ttu-id="0d695-258">При применении методов к экземплярам `geography` в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используется значение идентификатора SRID по умолчанию, равное 4326, соответствующее системе пространственных ссылок WGS 84.</span><span class="sxs-lookup"><span data-stu-id="0d695-258">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the default SRID of 4326, which maps to the WGS 84 spatial reference system, when using methods on `geography` instances.</span></span> <span data-ttu-id="0d695-259">Если используются данные системы пространственных ссылок, отличной от WGS 84 (или если значение SRID отличается от 4326), для собственных географических пространственных данных необходимо определить отдельный идентификатор SRID.</span><span class="sxs-lookup"><span data-stu-id="0d695-259">If you use data from a spatial reference system other than WGS 84 (or SRID 4326), you will need to determine the specific SRID for your geography spatial data.</span></span>  
  
##  <a name="examples"></a><a name="examples"></a> <span data-ttu-id="0d695-260">Примеры</span><span class="sxs-lookup"><span data-stu-id="0d695-260">Examples</span></span>  
 <span data-ttu-id="0d695-261">В следующих примерах иллюстрируется добавление и запрос географических данных.</span><span class="sxs-lookup"><span data-stu-id="0d695-261">The following examples show how to add and query geography data.</span></span>  
  
-   <span data-ttu-id="0d695-262">В первом примере создается таблица со столбцом идентификаторов и столбцом `geography` типа `GeogCol1`.</span><span class="sxs-lookup"><span data-stu-id="0d695-262">The first example creates a table with an identity column and a `geography` column `GeogCol1`.</span></span> <span data-ttu-id="0d695-263">Третий столбец обрабатывает столбец `geography` для представления в формате известного текста (WKT) OGC, используя метод `STAsText()` .</span><span class="sxs-lookup"><span data-stu-id="0d695-263">A third column renders the `geography` column into its Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation, and uses the `STAsText()` method.</span></span> <span data-ttu-id="0d695-264">Затем вставляются две строки: одна строка содержит объект `LineString` типа `geography`, а другая — объект `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="0d695-264">Two rows are then inserted: one row contains a `LineString` instance of `geography`, and one row contains a `Polygon` instance.</span></span>  
  
    ```  
    IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
        DROP TABLE dbo.SpatialTable;  
    GO  
  
    CREATE TABLE SpatialTable   
        ( id int IDENTITY (1,1),  
        GeogCol1 geography,   
        GeogCol2 AS GeogCol1.STAsText() );  
    GO  
  
    INSERT INTO SpatialTable (GeogCol1)  
    VALUES (geography::STGeomFromText('LINESTRING(-122.360 47.656, -122.343 47.656)', 4326));  
  
    INSERT INTO SpatialTable (GeogCol1)  
    VALUES (geography::STGeomFromText('POLYGON((-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))', 4326));  
    GO  
    ```  
  
-   <span data-ttu-id="0d695-265">Во втором примере метод `STIntersection()` используется для получения точек, в которых пересекаются два вставленные ранее объекта `geography` .</span><span class="sxs-lookup"><span data-stu-id="0d695-265">The second example uses the `STIntersection()` method to return the points where the two previously inserted `geography` instances intersect.</span></span>  
  
    ```  
    DECLARE @geog1 geography;  
    DECLARE @geog2 geography;  
    DECLARE @result geography;  
  
    SELECT @geog1 = GeogCol1 FROM SpatialTable WHERE id = 1;  
    SELECT @geog2 = GeogCol1 FROM SpatialTable WHERE id = 2;  
    SELECT @result = @geog1.STIntersection(@geog2);  
    SELECT @result.STAsText();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0d695-266">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d695-266">See Also</span></span>  
 [<span data-ttu-id="0d695-267">Пространственные данные (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0d695-267">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
