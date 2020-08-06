---
title: Идентификаторы пространственных ссылок | Документация Майкрософт
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Spatial Reference Identifiers (SRIDs)
- geodetic spatial data [SQL Server], identifiers
- SRID
ms.assetid: 0612658a-7d1b-4178-bdc2-42b914ea31a7
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 15db59b43731b9a39ff4bef78e3a6cb6929e9b47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665274"
---
# <a name="spatial-reference-identifiers-srids"></a><span data-ttu-id="7ea2e-102">идентификаторы пространственных ссылок (SRID)</span><span class="sxs-lookup"><span data-stu-id="7ea2e-102">Spatial Reference Identifiers (SRIDs)</span></span>
  <span data-ttu-id="7ea2e-103">У каждого пространственного экземпляра имеется идентификатор пространственной ссылки (SRID).</span><span class="sxs-lookup"><span data-stu-id="7ea2e-103">Each spatial instance has a spatial reference identifier (SRID).</span></span> <span data-ttu-id="7ea2e-104">Идентификатор SRID соответствует системе пространственных ссылок, основанной на конкретном эллипсоиде, используемом для плоского или сферического сопоставления.</span><span class="sxs-lookup"><span data-stu-id="7ea2e-104">The SRID corresponds to a spatial reference system based on the specific ellipsoid used for either flat-earth mapping or round-earth mapping.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7ea2e-105">Подробное описание и примеры использования возможностей обработки пространственных данных, добавленных в [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], в том числе нового идентификатора пространственной ссылки SRID, можно получить, загрузив технический документ [Новые возможности обработки пространственных данных в SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="7ea2e-105">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including a new SRID, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
 <span data-ttu-id="7ea2e-106">Пространственный столбец может содержать объекты с различными идентификаторами SRID.</span><span class="sxs-lookup"><span data-stu-id="7ea2e-106">A spatial column can contain objects with different SRIDs.</span></span> <span data-ttu-id="7ea2e-107">Однако при выполнении операций над собственными данными при помощи методов работы с пространственными данными [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может использовать только пространственные экземпляры с одним и тем же индексом пространственной ссылки SRID.</span><span class="sxs-lookup"><span data-stu-id="7ea2e-107">However, only spatial instances with the same SRID can be used when performing operations with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spatial data methods on your data.</span></span> <span data-ttu-id="7ea2e-108">Результат любого пространственного метода, извлеченный на основе двух экземпляров с пространственными данными, допустим только в случае, если эти экземпляры имеют один и тот же идентификатор SRID, основанный на одних и тех же единице измерения, исходной точке и проекции, использованных для определения координат экземпляров.</span><span class="sxs-lookup"><span data-stu-id="7ea2e-108">The result of any spatial method derived from two spatial data instances is valid only if those instances have the same SRID that is based on the same unit of measurement, datum, and projection used to determine the coordinates of the instances.</span></span> <span data-ttu-id="7ea2e-109">Наиболее распространенными единицами измерения идентификатора SRID являются метры или квадратные метры.</span><span class="sxs-lookup"><span data-stu-id="7ea2e-109">The most common units of measurement of a SRID are meters or square meters.</span></span>  
  
 <span data-ttu-id="7ea2e-110">Если идентификаторы SRID двух пространственных экземпляров различаются, в результате применения к этим экземплярам методов работы с типами данных `geometry` или `geography` будет возвращено значение NULL.</span><span class="sxs-lookup"><span data-stu-id="7ea2e-110">If two spatial instances do not have the same SRID, the results from a `geometry` or `geography` Data Type method used on the instances will return NULL.</span></span> <span data-ttu-id="7ea2e-111">Например, чтобы при следующем условии предиката получить результат, отличный от значения NULL, два экземпляра типа `geometry`, `geometry1` и `geometry2`, должны иметь один и тот же идентификатор SRID:</span><span class="sxs-lookup"><span data-stu-id="7ea2e-111">For example, for the following predicate term to return a non-NULL result, the two `geometry` instances, `geometry1` and `geometry2`, must have the same SRID:</span></span>  
  
 `geometry1.STIntersects(geometry2) = 1`  
  
> [!NOTE]  
>  <span data-ttu-id="7ea2e-112">Система идентификации пространственных ссылок определена стандартом [Европейской группы Petroleum Survey (EPSG)](https://go.microsoft.com/fwlink/?LinkId=99349) , представляющим собой набор стандартов, разработанных для картографии, геодезии и хранилищ геодезических данных.</span><span class="sxs-lookup"><span data-stu-id="7ea2e-112">The spatial reference identification system is defined by the [European Petroleum Survey Group (EPSG)](https://go.microsoft.com/fwlink/?LinkId=99349) standard, which is a set of standards developed for cartography, surveying, and geodetic data storage.</span></span> <span data-ttu-id="7ea2e-113">Владельцем данного стандарта является комитет Oil and Gas Producers (OGP) Surveying and Positioning Committee.</span><span class="sxs-lookup"><span data-stu-id="7ea2e-113">This standard is owned by the Oil and Gas Producers (OGP) Surveying and Positioning Committee.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea2e-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="7ea2e-114">See Also</span></span>  
 [<span data-ttu-id="7ea2e-115">Основные сведения о типах пространственных данных</span><span class="sxs-lookup"><span data-stu-id="7ea2e-115">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
  
  
