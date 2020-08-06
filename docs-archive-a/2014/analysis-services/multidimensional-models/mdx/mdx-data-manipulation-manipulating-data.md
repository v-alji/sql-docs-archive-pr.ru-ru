---
title: Обработка данных (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], data manipulation
- data manipulation [MDX]
- Multidimensional Expressions [Analysis Services], data manipulation
ms.assetid: 4865192e-f46b-4ce5-b51c-9e08dbad5b85
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1a1de8b9a3431d79573cd916fa7273b6d8fa7f0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664579"
---
# <a name="manipulating-data-mdx"></a><span data-ttu-id="565c3-102">Манипулирование данными (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="565c3-102">Manipulating Data (MDX)</span></span>

<span data-ttu-id="565c3-103">С помощью многомерных выражений можно осуществлять самые различные операции с данными.</span><span class="sxs-lookup"><span data-stu-id="565c3-103">Multidimensional Expressions (MDX) can be used to manipulate the data in a variety of ways.</span></span> <span data-ttu-id="565c3-104">В статье, приведенной в этой статье, рассматриваются некоторые более сложные концепции обработки данных в языке многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="565c3-104">The article listed in this article cover some of the more advanced concepts of data manipulation in the MDX language.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="565c3-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="565c3-105">In This Section</span></span>

|<span data-ttu-id="565c3-106">Раздел</span><span class="sxs-lookup"><span data-stu-id="565c3-106">Topic</span></span>|<span data-ttu-id="565c3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="565c3-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="565c3-108">Извлечение данных из источника с помощью функции DRILLTHROUGH (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="565c3-108">Using DRILLTHROUGH to Retrieve Source Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-retrieve-source-data-using-drillthrough.md)|<span data-ttu-id="565c3-109">Рассматриваются вопросы применения инструкции многомерных выражений [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough) для извлечения наборов строк исходных данных, применимых к ячейке в источнике многомерных данных</span><span class="sxs-lookup"><span data-stu-id="565c3-109">Discusses the use of the MDX [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough) statement to retrieve the rowsets of source data applicable to a cell in a multidimensional data source</span></span>|  
|[<span data-ttu-id="565c3-110">Работа с функцией RollupChildren (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="565c3-110">Working with the RollupChildren Function &#40;MDX&#41;</span></span>](mdx-data-manipulation-rollupchildren-function.md)|<span data-ttu-id="565c3-111">Обсуждается влияние [RollupChildrenности](/sql/mdx/rollupchildren-mdx) многомерных выражений</span><span class="sxs-lookup"><span data-stu-id="565c3-111">Discusses the impact of the MDX [RollupChildren](/sql/mdx/rollupchildren-mdx)</span></span>
|[<span data-ttu-id="565c3-112">Основные сведения о порядке этапов и порядке вычисления (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="565c3-112">Understanding Pass Order and Solve Order &#40;MDX&#41;</span></span>](mdx-data-manipulation-understanding-pass-order-and-solve-order.md)|<span data-ttu-id="565c3-113">Подробно рассматривается концепция порядка разрешения и вопросы его влияния на выражения, инструкции и скрипты многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="565c3-113">Details the concepts of solve order, and how this feature affects MDX expressions, statements, and scripts.</span></span>|  

<!-- ??

|[Script for Search and Replace] function on the analysis of multidimensional data.|

GeneMi is removing this commented row because it is unclear what article its link meant to link to.
Also, I had to add its leading '|' character, for consistency to aid bulk automated updated to our markdown source code.

GeneMi , 2019/01/19
-->

## <a name="see-also"></a><span data-ttu-id="565c3-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="565c3-114">See Also</span></span>

[<span data-ttu-id="565c3-115">Основные принципы запросов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="565c3-115">MDX Query Fundamentals (Analysis Services)</span></span>](mdx-query-fundamentals-analysis-services.md)
