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
# <a name="spatial-reference-identifiers-srids"></a>идентификаторы пространственных ссылок (SRID)
  У каждого пространственного экземпляра имеется идентификатор пространственной ссылки (SRID). Идентификатор SRID соответствует системе пространственных ссылок, основанной на конкретном эллипсоиде, используемом для плоского или сферического сопоставления.  
  
> [!IMPORTANT]  
>  Подробное описание и примеры использования возможностей обработки пространственных данных, добавленных в [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], в том числе нового идентификатора пространственной ссылки SRID, можно получить, загрузив технический документ [Новые возможности обработки пространственных данных в SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).  
  
 Пространственный столбец может содержать объекты с различными идентификаторами SRID. Однако при выполнении операций над собственными данными при помощи методов работы с пространственными данными [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может использовать только пространственные экземпляры с одним и тем же индексом пространственной ссылки SRID. Результат любого пространственного метода, извлеченный на основе двух экземпляров с пространственными данными, допустим только в случае, если эти экземпляры имеют один и тот же идентификатор SRID, основанный на одних и тех же единице измерения, исходной точке и проекции, использованных для определения координат экземпляров. Наиболее распространенными единицами измерения идентификатора SRID являются метры или квадратные метры.  
  
 Если идентификаторы SRID двух пространственных экземпляров различаются, в результате применения к этим экземплярам методов работы с типами данных `geometry` или `geography` будет возвращено значение NULL. Например, чтобы при следующем условии предиката получить результат, отличный от значения NULL, два экземпляра типа `geometry`, `geometry1` и `geometry2`, должны иметь один и тот же идентификатор SRID:  
  
 `geometry1.STIntersects(geometry2) = 1`  
  
> [!NOTE]  
>  Система идентификации пространственных ссылок определена стандартом [Европейской группы Petroleum Survey (EPSG)](https://go.microsoft.com/fwlink/?LinkId=99349) , представляющим собой набор стандартов, разработанных для картографии, геодезии и хранилищ геодезических данных. Владельцем данного стандарта является комитет Oil and Gas Producers (OGP) Surveying and Positioning Committee.  
  
## <a name="see-also"></a>См. также:  
 [Основные сведения о типах пространственных данных](spatial-data-types-overview.md)  
  
  