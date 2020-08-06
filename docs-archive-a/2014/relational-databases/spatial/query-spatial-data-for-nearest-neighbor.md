---
title: Запросы к пространственным данным для поиска ближайшего соседа | Документация Майкрософт
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 7af4ad5d-484e-45b4-aa16-83c33b358bb6
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 644b3e5cfdaeff7457639bc2da77260b64011735
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668174"
---
# <a name="query-spatial-data-for-nearest-neighbor"></a><span data-ttu-id="9dc65-102">Запросы пространственных данных для ближайшего соседа</span><span class="sxs-lookup"><span data-stu-id="9dc65-102">Query Spatial Data for Nearest Neighbor</span></span>
  <span data-ttu-id="9dc65-103">При работе с пространственными данными часто применяется запрос ближайшего соседа.</span><span class="sxs-lookup"><span data-stu-id="9dc65-103">A common query used with spatial data is the Nearest Neighbor query.</span></span> <span data-ttu-id="9dc65-104">Запрос ближайшего соседа находит пространственные объекты, расположенные ближе всего к указанному пространственному объекту.</span><span class="sxs-lookup"><span data-stu-id="9dc65-104">Nearest Neighbor queries are used to find the closest spatial objects to a specific spatial object.</span></span> <span data-ttu-id="9dc65-105">Например, компонент поиска магазинов на веб-сайте часто должен находить магазины, которые расположены ближе всего к текущему положению клиента.</span><span class="sxs-lookup"><span data-stu-id="9dc65-105">For example a store locater for a Web site often must find the closest store locations to a customer location.</span></span>  
  
 <span data-ttu-id="9dc65-106">Запросы ближайшего соседа могут формулироваться в ряде различных допустимых форматов запроса, но если запрос ближайшего соседа использует пространственный индекс, то должен применяться следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="9dc65-106">A Nearest Neighbor query can be written in a variety of valid query formats, but for the Nearest Neighbor query to use a spatial index the following syntax must be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dc65-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9dc65-107">Syntax</span></span>  
  
```vb  
SELECT TOP ( number )  
        [ WITH TIES ]  
        [ * | expression ]   
        [, ...]  
    FROM spatial_table_reference, ...   
        [ WITH   
            (   
                [ INDEX ( index_ref ) ]   
                [ , SPATIAL_WINDOW_MAX_CELLS = <value>]   
                [ ,... ]   
            )   
        ]  
    WHERE   
        column_ref.STDistance ( @spatial_ object )   
            {   
                [ IS NOT NULL ] | [ < const ] | [ > const ]   
                | [ <= const ] | [ >= const ] | [ <> const ] ]   
            }  
            [ AND { other_predicate } ]   
    }  
    ORDER BY column_ref.STDistance ( @spatial_ object ) [ ,...n ]  
[ ; ]  
  
```  
  
## <a name="nearest-neighbor-query-and-spatial-indexes"></a><span data-ttu-id="9dc65-108">Запросы ближайшего соседа и пространственные индексы</span><span class="sxs-lookup"><span data-stu-id="9dc65-108">Nearest Neighbor Query and Spatial Indexes</span></span>  
 <span data-ttu-id="9dc65-109">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при выполнении запросов ближайшего соседа к столбцам пространственных данных часто применяются предложения `TOP` и `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="9dc65-109">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `TOP` and `ORDER BY` clauses are used to perform a Nearest Neighbor query on spatial data columns.</span></span> <span data-ttu-id="9dc65-110">Предложение `ORDER BY` содержит вызов метода `STDistance()` для типа данных пространственного столбца.</span><span class="sxs-lookup"><span data-stu-id="9dc65-110">The `ORDER BY` clause contains a call to the `STDistance()` method for the spatial column data type.</span></span> <span data-ttu-id="9dc65-111">Предложение `TOP` задает количество возвращаемых запросом объектов.</span><span class="sxs-lookup"><span data-stu-id="9dc65-111">The `TOP` clause indicates the number of objects to return for the query.</span></span>  
  
 <span data-ttu-id="9dc65-112">Для того чтобы запрос ближайшего соседа использовал пространственный индекс, должны выполняться следующие требования.</span><span class="sxs-lookup"><span data-stu-id="9dc65-112">The following requirements must be met for a Nearest Neighbor query to use a spatial index:</span></span>  
  
1.  <span data-ttu-id="9dc65-113">В одном из пространственных столбцов должен иметься пространственный индекс, а метод `STDistance()` должен использовать этот столбец в предложениях `WHERE` и `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="9dc65-113">A spatial index must be present on one of the spatial columns and the `STDistance()` method must use that column in the `WHERE` and `ORDER BY` clauses.</span></span>  
  
2.  <span data-ttu-id="9dc65-114">Предложение `TOP` не может содержать инструкцию `PERCENT`.</span><span class="sxs-lookup"><span data-stu-id="9dc65-114">The `TOP` clause cannot contain a `PERCENT` statement.</span></span>  
  
3.  <span data-ttu-id="9dc65-115">Предложение `WHERE` должно содержать метод `STDistance()`.</span><span class="sxs-lookup"><span data-stu-id="9dc65-115">The `WHERE` clause must contain a `STDistance()` method.</span></span>  
  
4.  <span data-ttu-id="9dc65-116">Если в предложении `WHERE` имеется несколько предикатов, то предикат, содержащий метод `STDistance()`, должен соединяться с другими предикатами условием `AND`.</span><span class="sxs-lookup"><span data-stu-id="9dc65-116">If there are multiple predicates in the `WHERE` clause then the predicate containing `STDistance()` method must be connected by an `AND` conjunction to the other predicates.</span></span> <span data-ttu-id="9dc65-117">Метод `STDistance()` не может входить в необязательную часть предложения `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="9dc65-117">The `STDistance()` method cannot be in an optional part of the `WHERE` clause.</span></span>  
  
5.  <span data-ttu-id="9dc65-118">Первое выражение в предложении `ORDER BY` должно вызывать метод `STDistance()`.</span><span class="sxs-lookup"><span data-stu-id="9dc65-118">The first expression in the `ORDER BY` clause must use the `STDistance()` method.</span></span>  
  
6.  <span data-ttu-id="9dc65-119">В первом выражении `STDistance()` в предложении `ORDER BY` должен использоваться порядок сортировки `ASC`.</span><span class="sxs-lookup"><span data-stu-id="9dc65-119">Sort order for the first `STDistance()` expression in the `ORDER BY` clause must be `ASC`.</span></span>  
  
7.  <span data-ttu-id="9dc65-120">Все строки, для которых `STDistance` возвращает `NULL`, должны исключаться фильтром.</span><span class="sxs-lookup"><span data-stu-id="9dc65-120">All the rows for which `STDistance` returns `NULL` must be filtered out.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="9dc65-121">Методы, принимающие в качестве аргументов типы данных `geography` или `geometry`, возвращают значение `NULL`, если идентификаторы SRID для типов не совпадают.</span><span class="sxs-lookup"><span data-stu-id="9dc65-121">Methods that take `geography` or `geometry` data types as arguments will return `NULL` if the SRIDs are not the same for the types.</span></span>  
  
 <span data-ttu-id="9dc65-122">В запросах ближайшего соседа рекомендуется использовать новые тесселяции пространственных индексов.</span><span class="sxs-lookup"><span data-stu-id="9dc65-122">It is recommended that the new spatial index tessellations be used for indexes used in Nearest Neighbor queries.</span></span> <span data-ttu-id="9dc65-123">Дополнительные сведения о тесселяциях пространственных индексов см. в разделе [Пространственные данные (SQL Server)](spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9dc65-123">For more information on spatial index tessellations, see [Spatial Data &#40;SQL Server&#41;](spatial-data-sql-server.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dc65-124">Пример</span><span class="sxs-lookup"><span data-stu-id="9dc65-124">Example</span></span>  
 <span data-ttu-id="9dc65-125">В следующем примере кода показывается запрос ближайшего соседа, в котором может применяться пространственный индекс.</span><span class="sxs-lookup"><span data-stu-id="9dc65-125">The following code example shows a Nearest Neighbor query that can use a spatial index.</span></span> <span data-ttu-id="9dc65-126">В примере используется таблица `Person.Address` базы данных `AdventureWorks2012` .</span><span class="sxs-lookup"><span data-stu-id="9dc65-126">The example uses the `Person.Address` table in `AdventureWorks2012` database.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
DECLARE @g geography = 'POINT(-121.626 47.8315)';  
SELECT TOP(7) SpatialLocation.ToString(), City FROM Person.Address  
WHERE SpatialLocation.STDistance(@g) IS NOT NULL  
ORDER BY SpatialLocation.STDistance(@g);  
  
```  
  
 <span data-ttu-id="9dc65-127">Создание пространственного индекса на столбце SpatialLocation для демонстрации того, как запрос ближайшего соседа использует пространственный индекс.</span><span class="sxs-lookup"><span data-stu-id="9dc65-127">Create a spatial index on the column SpatialLocation to see how a Nearest Neighbor query uses a spatial index.</span></span> <span data-ttu-id="9dc65-128">Дополнительные сведения о создании пространственных индексов см. в разделе [Create, Modify, and Drop Spatial Indexes](create-modify-and-drop-spatial-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="9dc65-128">For more information on creating spatial indexes, see [Create, Modify, and Drop Spatial Indexes](create-modify-and-drop-spatial-indexes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dc65-129">Пример</span><span class="sxs-lookup"><span data-stu-id="9dc65-129">Example</span></span>  
 <span data-ttu-id="9dc65-130">В следующем примере кода показывается запрос ближайшего соседа, в котором не может применяться пространственный индекс.</span><span class="sxs-lookup"><span data-stu-id="9dc65-130">The following code example shows a Nearest Neighbor query that cannot use a spatial index.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
DECLARE @g geography = 'POINT(-121.626 47.8315)';  
SELECT TOP(7) SpatialLocation.ToString(), City FROM Person.Address  
ORDER BY SpatialLocation.STDistance(@g);  
  
```  
  
 <span data-ttu-id="9dc65-131">В запросе отсутствует предложение `WHERE`, использующее `STDistance()` указанным в разделе синтаксиса образом, поэтому данный запрос не может использовать пространственный индекс.</span><span class="sxs-lookup"><span data-stu-id="9dc65-131">The query lacks a `WHERE` clause that uses `STDistance()` in a form specified in the syntax section so the query cannot use a spatial index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dc65-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="9dc65-132">See Also</span></span>  
 [<span data-ttu-id="9dc65-133">Пространственные данные (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9dc65-133">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
