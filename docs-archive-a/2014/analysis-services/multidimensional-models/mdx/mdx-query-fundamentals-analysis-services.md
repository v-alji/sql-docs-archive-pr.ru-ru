---
title: Основные принципы запросов многомерных выражений (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- statements [MDX]
- Multidimensional Expressions [Analysis Services], statements
- Multidimensional Expressions [Analysis Services], queries
- MDX [Analysis Services], statements
- MDX queries [Analysis Services]
- MDX [Analysis Services], queries
- queries [MDX]
ms.assetid: a560383b-bb58-472e-95f5-65d03d8ea08b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1a2a9a4f564bc33cc7a1b41a1a4c766c7a76a2cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666833"
---
# <a name="mdx-query-fundamentals-analysis-services"></a><span data-ttu-id="31777-102">Основные принципы запросов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="31777-102">MDX Query Fundamentals (Analysis Services)</span></span>
  <span data-ttu-id="31777-103">В языке многомерных выражений можно обращаться с запросом к таким многомерным объектам, как кубы, и возвращать многомерные наборы ячеек, содержащие данные куба.</span><span class="sxs-lookup"><span data-stu-id="31777-103">Multidimensional Expressions (MDX) lets you query multidimensional objects, such as cubes, and return multidimensional cellsets that contain the cube's data.</span></span> <span data-ttu-id="31777-104">Этот раздел и его подразделы содержат общие сведения о многомерных запросах.</span><span class="sxs-lookup"><span data-stu-id="31777-104">This topic and its subtopics provide an overview of MDX queries.</span></span>  
  
 <span data-ttu-id="31777-105">Следующие разделы посвящены многомерным запросам и возвращаемым ими наборам ячеек. В них изложены более подробные сведения о базовом синтаксисе многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="31777-105">The following topics describe MDX queries and the cellsets they produce, and provide more detailed information about basic MDX syntax.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31777-106">Дополнительные сведения о проблемах производительности, связанных с запросами и вычислениями многомерных выражений, см. в подразделе «написание эффективных многомерных выражений» [руководства по SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="31777-106">For more information about performance issues related to MDX queries and calculations, see the section "Writing Efficient MDX" in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31777-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="31777-107">In This Section</span></span>  
  
|<span data-ttu-id="31777-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="31777-108">Topic</span></span>|<span data-ttu-id="31777-109">Описание</span><span class="sxs-lookup"><span data-stu-id="31777-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="31777-110">Базовый запрос многомерных выражений (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="31777-110">The Basic MDX Query &#40;MDX&#41;</span></span>](mdx-query-the-basic-query.md)|<span data-ttu-id="31777-111">Сведения о базовом синтаксисе инструкции многомерных выражений SELECT.</span><span class="sxs-lookup"><span data-stu-id="31777-111">Provides basic syntax information for the MDX SELECT statement.</span></span>|  
|[<span data-ttu-id="31777-112">Ограничение запроса с помощью осей запроса и среза (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="31777-112">Restricting the Query with Query and Slicer Axes &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-restricting-the-query.md)|<span data-ttu-id="31777-113">Основные сведения об осях запроса и среза и о том, как их указывать.</span><span class="sxs-lookup"><span data-stu-id="31777-113">Describes what query and slicer axes are and how to specify them.</span></span>|  
|[<span data-ttu-id="31777-114">Определение контекста куба в запросе (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="31777-114">Establishing Cube Context in a Query &#40;MDX&#41;</span></span>](establishing-cube-context-in-a-query-mdx.md)|<span data-ttu-id="31777-115">Назначение предложения FROM инструкции многомерных выражений SELECT.</span><span class="sxs-lookup"><span data-stu-id="31777-115">Provides a description of the purpose of the FROM clause in an MDX SELECT statement.</span></span>|  
|[<span data-ttu-id="31777-116">Построение именованных наборов в многомерных выражениях (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="31777-116">Building Named Sets in MDX &#40;MDX&#41;</span></span>](mdx-named-sets-building-named-sets.md)|<span data-ttu-id="31777-117">Назначение именованных наборов в многомерных выражениях, методы их создания и использования в многомерных запросах.</span><span class="sxs-lookup"><span data-stu-id="31777-117">Describes the purpose of named sets in MDX, and the techniques needed to create and use them in MDX queries.</span></span>|  
|[<span data-ttu-id="31777-118">Создание вычисляемых элементов в многомерных выражениях (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="31777-118">Building Calculated Members in MDX &#40;MDX&#41;</span></span>](mdx-calculated-members-building-calculated-members.md)|<span data-ttu-id="31777-119">Сведения о вычисляемых элементах в многомерных выражениях, включая методы их создания и использования в многомерных выражениях.</span><span class="sxs-lookup"><span data-stu-id="31777-119">Provides information about calculated members in MDX, including the techniques needed to create and use them in MDX expressions.</span></span>|  
|[<span data-ttu-id="31777-120">Построение вычислений значений ячеек в многомерном выражении (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="31777-120">Building Cell Calculations in MDX &#40;MDX&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/calculations.md)|<span data-ttu-id="31777-121">Подробные сведения о создании и использовании вычисляемых ячеек.</span><span class="sxs-lookup"><span data-stu-id="31777-121">Details the process of creating and using calculated cells.</span></span>|  
|[<span data-ttu-id="31777-122">Создание и использование значений свойств (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="31777-122">Creating and Using Property Values &#40;MDX&#41;</span></span>](../../creating-and-using-property-values-mdx.md)|<span data-ttu-id="31777-123">Процесс создания и использования свойств измерения, уровня, элемента и ячейки.</span><span class="sxs-lookup"><span data-stu-id="31777-123">Details the process of creating and using dimension, level, member, and cell properties.</span></span>|  
|[<span data-ttu-id="31777-124">Манипулирование данными (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="31777-124">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)|<span data-ttu-id="31777-125">Манипулирование данными с помощью детализации и свертки, сведения об этапах вычисления и порядке разрешения в языке многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="31777-125">Describes the basics behind manipulating data using drillthrough and rollup, and also describes pass order and solve order in MDX.</span></span>|  
|[<span data-ttu-id="31777-126">Изменение данных (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="31777-126">Modifying Data &#40;MDX&#41;</span></span>](mdx-data-modification-modifying-data.md)|<span data-ttu-id="31777-127">Использование обратной записи для временного или постоянного изменения многомерных данных.</span><span class="sxs-lookup"><span data-stu-id="31777-127">Describes how to use writebacks to temporarily or permanently change multidimensional data.</span></span>|  
|[<span data-ttu-id="31777-128">Переменные и параметры (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="31777-128">Using Variables and Parameters &#40;MDX&#41;</span></span>](using-variables-and-parameters-mdx.md)|<span data-ttu-id="31777-129">Использование переменных и параметров в запросах многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="31777-129">Describes how to use variables and parameters within MDX queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31777-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="31777-130">See Also</span></span>  
 [<span data-ttu-id="31777-131">Справочник по многомерным выражениям (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="31777-131">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
