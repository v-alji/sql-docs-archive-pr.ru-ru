---
title: Использование осей запросов и срезов в простом примере (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- query axis [MDX]
ms.assetid: 85bcb26f-5971-4153-b334-61f8d8b475b5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 324f082fd6659592e56af65680bd4aa623c625d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666246"
---
# <a name="using-query-and-slicer-axes-in-a-simple-example-mdx"></a><span data-ttu-id="2ff04-102">Оси запроса и среза. Простой пример (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="2ff04-102">Using Query and Slicer Axes in a Simple Example (MDX)</span></span>
  <span data-ttu-id="2ff04-103">Пример в этом разделе демонстрирует простейший метод указания и использования осей запроса и среза.</span><span class="sxs-lookup"><span data-stu-id="2ff04-103">The simple example presented in this topic illustrates the basics of specifying and using query and slicer axes.</span></span>  
  
## <a name="the-cube"></a><span data-ttu-id="2ff04-104">Куб</span><span class="sxs-lookup"><span data-stu-id="2ff04-104">The Cube</span></span>  
 <span data-ttu-id="2ff04-105">Куб TestCube имеет два измерения: Route и Time.</span><span class="sxs-lookup"><span data-stu-id="2ff04-105">A cube, named TestCube, has two simple dimensions named Route and Time.</span></span> <span data-ttu-id="2ff04-106">Каждому из них соответствует только одна пользовательская иерархия (Route и Time соответственно).</span><span class="sxs-lookup"><span data-stu-id="2ff04-106">Each dimension has only one user hierarchy, named Route and Time respectively.</span></span> <span data-ttu-id="2ff04-107">Поскольку меры куба относятся к измерению Measures, куб имеет всего три измерения.</span><span class="sxs-lookup"><span data-stu-id="2ff04-107">Because the measures of the cube are part of the Measures dimension, this cube has three dimensions in all.</span></span>  
  
## <a name="the-query"></a><span data-ttu-id="2ff04-108">Запрос</span><span class="sxs-lookup"><span data-stu-id="2ff04-108">The Query</span></span>  
 <span data-ttu-id="2ff04-109">Запрос должен возвращать матрицу, в которой меру «Пакеты» можно сравнивать по маршрутам и времени.</span><span class="sxs-lookup"><span data-stu-id="2ff04-109">The query is to provide a matrix in which the Packages measure can be compared across routes and times.</span></span>  
  
 <span data-ttu-id="2ff04-110">В следующем примере запроса многомерных выражений иерархии Route и Time являются осями запроса, а измерение Measures — осью среза.</span><span class="sxs-lookup"><span data-stu-id="2ff04-110">In the following MDX query example, the Route and Time hierarchies are the query axes, and the Measures dimension is the slicer axis.</span></span> <span data-ttu-id="2ff04-111">Функция [Members](/sql/mdx/members-set-mdx) указывает, что в многомерном запросе для формирования набора будут использоваться элементы иерархии или уровня.</span><span class="sxs-lookup"><span data-stu-id="2ff04-111">The [Members](/sql/mdx/members-set-mdx) function indicates that MDX will use the members of the hierarchy or level to construct a set.</span></span> <span data-ttu-id="2ff04-112">Благодаря функции `Members` в многомерном запросе не нужно явно указывать каждый элемент каждой конкретной иерархии или уровня.</span><span class="sxs-lookup"><span data-stu-id="2ff04-112">The use of the `Members` function means that you do not have to explicitly state each member of a specific hierarchy or level in an MDX query.</span></span>  
  
```  
SELECT  
   { Route.nonground.Members } ON COLUMNS,  
   { Time.[1st half].Members } ON ROWS  
FROM TestCube  
WHERE ( [Measures].[Packages] )  
```  
  
## <a name="the-results"></a><span data-ttu-id="2ff04-113">Результаты</span><span class="sxs-lookup"><span data-stu-id="2ff04-113">The Results</span></span>  
 <span data-ttu-id="2ff04-114">Запрос возвращает таблицу значений меры Packages для каждого пересечения осей измерений COLUMNS и ROWS.</span><span class="sxs-lookup"><span data-stu-id="2ff04-114">The result is a grid that identifies the value of the Packages measure at each intersection of the COLUMNS and ROWS axis dimensions.</span></span> <span data-ttu-id="2ff04-115">Таблица должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2ff04-115">The following table shows how this grid would look.</span></span>  
  
||<span data-ttu-id="2ff04-116">air</span><span class="sxs-lookup"><span data-stu-id="2ff04-116">air</span></span>|<span data-ttu-id="2ff04-117">по морю</span><span class="sxs-lookup"><span data-stu-id="2ff04-117">sea</span></span>|  
|-|---------|---------|  
|<span data-ttu-id="2ff04-118">Первый квартал</span><span class="sxs-lookup"><span data-stu-id="2ff04-118">1st quarter</span></span>|<span data-ttu-id="2ff04-119">60</span><span class="sxs-lookup"><span data-stu-id="2ff04-119">60</span></span>|<span data-ttu-id="2ff04-120">50</span><span class="sxs-lookup"><span data-stu-id="2ff04-120">50</span></span>|  
|<span data-ttu-id="2ff04-121">Второй квартал</span><span class="sxs-lookup"><span data-stu-id="2ff04-121">2nd quarter</span></span>|<span data-ttu-id="2ff04-122">45</span><span class="sxs-lookup"><span data-stu-id="2ff04-122">45</span></span>|<span data-ttu-id="2ff04-123">45</span><span class="sxs-lookup"><span data-stu-id="2ff04-123">45</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ff04-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="2ff04-124">See Also</span></span>  
 <span data-ttu-id="2ff04-125">[Указание содержимого оси запроса &#40;многомерных выражениях&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) </span><span class="sxs-lookup"><span data-stu-id="2ff04-125">[Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) </span></span>  
 [<span data-ttu-id="2ff04-126">Определение содержимого оси среза (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="2ff04-126">Specifying the Contents of a Slicer Axis &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
