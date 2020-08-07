---
title: Ограничитель запроса с помощью осей запроса и среза (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Multidimensional Expressions [Analysis Services], axes
- queries [MDX], axes
- axes [MDX]
- MDX [Analysis Services], axes
ms.assetid: a64b8172-cd73-42f9-8847-52e967b9697a
author: minewiskan
ms.author: owend
ms.openlocfilehash: ed4d50aa40d2915c60f887e64cdc3ef8a6d52c5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734486"
---
# <a name="restricting-the-query-with-query-and-slicer-axes-mdx"></a><span data-ttu-id="a0735-102">Ограничение запроса с помощью осей запроса и среза (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="a0735-102">Restricting the Query with Query and Slicer Axes (MDX)</span></span>
  <span data-ttu-id="a0735-103">При формировании инструкции многомерных выражений SELECT приложение обычно изучает куб и разбивает набор иерархий на два следующих подмножества.</span><span class="sxs-lookup"><span data-stu-id="a0735-103">When formulating a Multidimensional Expressions (MDX) SELECT statement, an application typically examines a cube and divides the set of hierarchies into two subsets:</span></span>  
  
-   <span data-ttu-id="a0735-104">**Оси запросов**— это набор иерархий, из которых данные извлекаются для нескольких элементов.</span><span class="sxs-lookup"><span data-stu-id="a0735-104">**Query axes**-the set of hierarchies from which data is retrieved for multiple members.</span></span> <span data-ttu-id="a0735-105">Дополнительные сведения об осях запроса см. в разделе [Определение содержимого оси запроса (многомерные выражения)](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="a0735-105">For more information about query axes, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
-   <span data-ttu-id="a0735-106">**Ось среза**— набор иерархий, из которых данные извлекаются для одного элемента.</span><span class="sxs-lookup"><span data-stu-id="a0735-106">**Slicer axis**-the set of hierarchies from which data is retrieved for a single member.</span></span> <span data-ttu-id="a0735-107">Дополнительные сведения об осях среза см. в разделе [Определение содержимого оси среза (многомерные выражения)](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="a0735-107">For more information about the slicer axis, see [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
 <span data-ttu-id="a0735-108">Поскольку оси запроса и среза можно построить из нескольких иерархий запрашиваемого куба, эти термины позволяют отличать иерархии, которые используются запрашиваемым кубом, от иерархий, созданных в кубе, возвращаемом многомерным запросом.</span><span class="sxs-lookup"><span data-stu-id="a0735-108">Because query and slicer axes can be constructed from multiple hierarchies of the cube to be queried, these terms are used to differentiate the hierarchies used by the cube that is to be queried from the hierarchies created in the cube returned by an MDX query.</span></span>  
  
 <span data-ttu-id="a0735-109">Пример использования осей запроса и среза см. в разделе [Оси запроса и среза. Простой пример (многомерные выражения)](mdx-query-and-slicer-axes-using-axes-in-a-simple-example.md).</span><span class="sxs-lookup"><span data-stu-id="a0735-109">To see a simple example using query and slicer axes, see [Using Query and Slicer Axes in a Simple Example &#40;MDX&#41;](mdx-query-and-slicer-axes-using-axes-in-a-simple-example.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0735-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0735-110">See Also</span></span>  
 <span data-ttu-id="a0735-111">[Работа с элементами, кортежами и наборами &#40;многомерных выражениях&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="a0735-111">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 [<span data-ttu-id="a0735-112">Основные принципы запросов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="a0735-112">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
