---
title: Создание вычислений для ячеек в МНОГОМЕРных выражениях (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- calculated cells [MDX]
- queries [MDX], cell calculations
- cells [MDX]
- MDX [Analysis Services], calculations
- calculation subcubes [MDX]
- calculated values [MDX]
- Multidimensional Expressions [Analysis Services], cell calculations
ms.assetid: 068aea63-d419-4791-a960-3d74e76f808e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9ab3219850c49c2ec16a12aab3ba7db67e9a8721
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734498"
---
# <a name="building-cell-calculations-in-mdx-mdx"></a><span data-ttu-id="f0451-102">Построение вычислений значений ячеек в многомерном выражении</span><span class="sxs-lookup"><span data-stu-id="f0451-102">Building Cell Calculations in MDX (MDX)</span></span>
  <span data-ttu-id="f0451-103">Многомерные выражения предоставляют целый ряд инструментов для формирования вычисляемых значений, таких как вычисляемые элементы, пользовательские свертки и пользовательские элементы.</span><span class="sxs-lookup"><span data-stu-id="f0451-103">Multidimensional Expressions (MDX) provides you with a number of tools for generating calculated values, such as calculated members, custom rollups, and custom members.</span></span> <span data-ttu-id="f0451-104">Однако по этой причине применить эти средства так, чтобы повлиять только на часть ячеек или на одну ячейку, будет трудно.</span><span class="sxs-lookup"><span data-stu-id="f0451-104">However, using these features to affect a specific set of cells, or a single cell for that matter, would be difficult.</span></span>  
  
 <span data-ttu-id="f0451-105">Чтобы формировать вычисляемые значения ячеек, надо воспользоваться имеющимися в многомерных выражениях возможностями вычисляемых ячеек.</span><span class="sxs-lookup"><span data-stu-id="f0451-105">To generated calculated values for specifically for cells, you need to use the calculated cells feature in MDX.</span></span> <span data-ttu-id="f0451-106">Вычисляемые ячейки позволяют выделить особый срез ячеек, который называется *вложенным кубом вычисления*, и применить формулу к каждой ячейке вложенного куба вычисления, удовлетворяющей дополнительному условию, применимому к любой ячейке.</span><span class="sxs-lookup"><span data-stu-id="f0451-106">Calculated cells let you define a specific slice of cells, called a *calculation subcube*, and apply a formula to each and every cell within the calculation subcube, subject to an optional condition that can be applied to each cell.</span></span>  
  
 <span data-ttu-id="f0451-107">Вычисляемые ячейки также предлагают сложные функциональные возможности, такие как формулы целенаправленного поиска, которые используются в ключевых показателях эффективности, а также формулы для анализа гипотез.</span><span class="sxs-lookup"><span data-stu-id="f0451-107">Calculated cells also offer complex functionality, such as goal-seeking formulas, as used in KPIs, or speculative analysis formulas.</span></span> <span data-ttu-id="f0451-108">Этот уровень функциональности поступает из функции порядка прохода в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , что позволяет выполнять рекурсивные проходы с вычисляемыми ячейками, при этом формулы вычисления применяются к конкретным проходам в порядке прохода.</span><span class="sxs-lookup"><span data-stu-id="f0451-108">This level of functionality comes from the pass order feature in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] that allows recursive passes to be made with calculated cells, with calculation formulas applied at specific passes in the pass order.</span></span> <span data-ttu-id="f0451-109">Дополнительные сведения о порядке прохода и порядке разрешения см. в разделе [Основные сведения о порядке этапов и порядке вычисления (многомерные выражения)](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span><span class="sxs-lookup"><span data-stu-id="f0451-109">For more information on pass order, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span></span>  
  
 <span data-ttu-id="f0451-110">При создании вычисляемые ячейки похожи как на именованные наборы, так и на вычисляемые элементы тем, что вычисляемые ячейки можно временно создать на время жизни одного сеанса или отдельного запроса; и они становятся глобально доступными как часть куба:</span><span class="sxs-lookup"><span data-stu-id="f0451-110">In terms of creation scope, calculated cells are similar to both named sets and calculated members in that calculated cells can be temporarily created for the lifetime of either a session or a single query, or made globally available as part of a cube:</span></span>  
  
-   <span data-ttu-id="f0451-111">**Область — запрос** . Для создания вычисляемой ячейки, которая определена как часть запроса многомерных выражений (поэтому ее область ограничена этим запросом), надо применить ключевое слово WITH.</span><span class="sxs-lookup"><span data-stu-id="f0451-111">**Query-scoped** To create a calculated cell that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="f0451-112">Затем можно использовать эту вычисляемую ячейку в операторе MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="f0451-112">You can then use the calculated cell within an MDX SELECT statement.</span></span> <span data-ttu-id="f0451-113">При таком подходе вычисляемую ячейку, которая создается с применением ключевого слова `WITH`, можно изменить, не нарушая инструкцию SELECT.</span><span class="sxs-lookup"><span data-stu-id="f0451-113">Using this approach, the calculated cell created by using the `WITH` keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="f0451-114">Дополнительные сведения о создании вычисляемых элементов с помощью ключевого слова WITH см. в разделе [Создание вычислений ячеек с областью действия запроса (многомерные выражения)](../../multidimensional-models-olap-logical-cube-objects/calculations.md).</span><span class="sxs-lookup"><span data-stu-id="f0451-114">For more information about how to use the WITH keyword to create calculated members, see [Creating Query-Scoped Cell Calculations &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md).</span></span>  
  
-   <span data-ttu-id="f0451-115">**Область — сеанс** . Чтобы создать вычисляемую ячейку, область которой шире контекста запроса (то есть область которой составляет время жизни сеанса многомерных выражений), можно воспользоваться инструкцией CREATE CELL CALCULATION или ALTER CUBE.</span><span class="sxs-lookup"><span data-stu-id="f0451-115">**Session-scoped** To create a calculated member whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use either the CREATE CELL CALCULATION or ALTER CUBE statement.</span></span>  
  
     <span data-ttu-id="f0451-116">Дополнительные сведения о применении инструкций CREATE CELL CALCULATION и ALTER CUBE для создания вычисляемых ячеек в сеансе см. в разделе [Создание вычисляемых ячеек с областью действия сеанса](mdx-cell-calculations-session-scoped-calculated-cells.md).</span><span class="sxs-lookup"><span data-stu-id="f0451-116">For more information about how to use either the CREATE CELL CALCULATION or ALTER CUBE statement to create calculated cells in a session, see [Creating Session-Scoped Calculated Cells](mdx-cell-calculations-session-scoped-calculated-cells.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0451-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="f0451-117">See Also</span></span>  
 <span data-ttu-id="f0451-118">[Инструкция ALTER CUBE &#40;&#41;многомерных выражений](/sql/mdx/mdx-data-definition-alter-cube) </span><span class="sxs-lookup"><span data-stu-id="f0451-118">[ALTER CUBE Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-alter-cube) </span></span>  
 <span data-ttu-id="f0451-119">[СОЗДАНИЕ инструкции вычисления ЯЧЕЙКИ &#40;многомерных выражениях&#41;](/sql/mdx/mdx-data-definition-create-cell-calculation) </span><span class="sxs-lookup"><span data-stu-id="f0451-119">[CREATE CELL CALCULATION Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-cell-calculation) </span></span>  
 <span data-ttu-id="f0451-120">[Создание вычислений ячеек с областью действия запроса &#40;многомерных выражениях&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="f0451-120">[Creating Query-Scoped Cell Calculations &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 [<span data-ttu-id="f0451-121">Основные принципы запросов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="f0451-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
