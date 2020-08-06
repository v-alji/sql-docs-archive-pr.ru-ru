---
title: Создание вычисляемых ячеек с областью действия сеанса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- session-scoped calculated members [MDX]
ms.assetid: f2d14a89-6286-4e74-9afb-091076f93f21
author: minewiskan
ms.author: owend
ms.openlocfilehash: 199de07778a153cd1bc40b5033d364e5e0055bd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658453"
---
# <a name="creating-session-scoped-calculated-cells"></a><span data-ttu-id="e58d4-102">Создание вычисляемых ячеек с областью действия сеанса</span><span class="sxs-lookup"><span data-stu-id="e58d4-102">Creating Session-Scoped Calculated Cells</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="e58d4-103">Этот синтаксис больше не используется.</span><span class="sxs-lookup"><span data-stu-id="e58d4-103">This syntax has been deprecated.</span></span> <span data-ttu-id="e58d4-104">Вместо него используются присваивания языка многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="e58d4-104">You should use MDX assignments should instead.</span></span> <span data-ttu-id="e58d4-105">Дополнительные сведения о присваиваниях см. в разделе [Базовый скрипт многомерных выражений (многомерные выражения)](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="e58d4-105">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="e58d4-106">Чтобы создать вычисляемые ячейки, доступные для всех запросов одного и того же сеанса, можно использовать инструкцию [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) или инструкцию [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) .</span><span class="sxs-lookup"><span data-stu-id="e58d4-106">To create calculated cells that are available to all queries in the same session, you can use either the [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) statement or the [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) statement.</span></span> <span data-ttu-id="e58d4-107">Обе инструкции обеспечивают одинаковый результат.</span><span class="sxs-lookup"><span data-stu-id="e58d4-107">Both statements have the same result.</span></span>  
  
## <a name="create-cell-calculation-syntax"></a><span data-ttu-id="e58d4-108">Синтаксис CREATE CELL CALCULATION</span><span class="sxs-lookup"><span data-stu-id="e58d4-108">CREATE CELL CALCULATION Syntax</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e58d4-109">Этот синтаксис больше не используется.</span><span class="sxs-lookup"><span data-stu-id="e58d4-109">This syntax has been deprecated.</span></span> <span data-ttu-id="e58d4-110">Вместо него используются присваивания языка многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="e58d4-110">You should use MDX assignments should instead.</span></span> <span data-ttu-id="e58d4-111">Дополнительные сведения о присваиваниях см. в разделе [Базовый скрипт многомерных выражений (многомерные выражения)](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="e58d4-111">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="e58d4-112">Чтобы определить вычисляемую ячейку с областью действия сеанса с помощью инструкции CREATE CELL CALCULATION, используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e58d4-112">Use the following syntax to use the CREATE CELL CALCULATION statement to define a session-scoped calculated cell:</span></span>  
  
```  
CREATE CELL CALCULATION Cube_Expression.<CREATE CELL CALCULATION body clause>  
  
<CREATE CELL CALCULATION body clause> ::=CellCalc_Identifier FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
## <a name="alter-cube-syntax"></a><span data-ttu-id="e58d4-113">Синтаксис ALTER CUBE</span><span class="sxs-lookup"><span data-stu-id="e58d4-113">ALTER CUBE Syntax</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e58d4-114">Этот синтаксис больше не используется.</span><span class="sxs-lookup"><span data-stu-id="e58d4-114">This syntax has been deprecated.</span></span> <span data-ttu-id="e58d4-115">Вместо него используются присваивания языка многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="e58d4-115">You should use MDX assignments should instead.</span></span> <span data-ttu-id="e58d4-116">Дополнительные сведения о присваиваниях см. в разделе [Базовый скрипт многомерных выражений (многомерные выражения)](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="e58d4-116">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="e58d4-117">Для определения вычисляемой ячейки с областью действия сеанса с помощью инструкции ALTER CUBE используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e58d4-117">Use the following syntax to use the ALTER CUBE statement to define a session-scoped calculated cell:</span></span>  
  
```  
ALTER CUBE Cube_Identifier CREATE CELL CALCULATION  
FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
 <span data-ttu-id="e58d4-118">Значение выражения `String_Expression` содержит список ортогональных многомерных выражений набора с одним измерением, каждое из которых должно приводиться к одной из следующих категорий наборов:</span><span class="sxs-lookup"><span data-stu-id="e58d4-118">The `String_Expression` value contains a list of orthogonal, single-dimensional MDX set expressions, each of which must resolve to one of the categories of sets that are listed in the following table.</span></span>  
  
|<span data-ttu-id="e58d4-119">Категория</span><span class="sxs-lookup"><span data-stu-id="e58d4-119">Category</span></span>|<span data-ttu-id="e58d4-120">Описание</span><span class="sxs-lookup"><span data-stu-id="e58d4-120">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e58d4-121">Пустой набор</span><span class="sxs-lookup"><span data-stu-id="e58d4-121">Empty set</span></span>|<span data-ttu-id="e58d4-122">Выражение набора многомерных выражений, которое разрешается к пустому набору.</span><span class="sxs-lookup"><span data-stu-id="e58d4-122">An MDX set expression that resolves into an empty set.</span></span> <span data-ttu-id="e58d4-123">В этом случае областью вычисляемой ячейки является весь куб.</span><span class="sxs-lookup"><span data-stu-id="e58d4-123">In this case, the scope of the calculated cell is the whole cube.</span></span>|  
|<span data-ttu-id="e58d4-124">Одноэлементный набор</span><span class="sxs-lookup"><span data-stu-id="e58d4-124">Single member set</span></span>|<span data-ttu-id="e58d4-125">Выражение набора многомерных выражений, которое разрешается к единственному элементу.</span><span class="sxs-lookup"><span data-stu-id="e58d4-125">An MDX set expression that resolves into a single member.</span></span>|  
|<span data-ttu-id="e58d4-126">Набор элементов уровня</span><span class="sxs-lookup"><span data-stu-id="e58d4-126">Set of level members</span></span>|<span data-ttu-id="e58d4-127">Выражение набора многомерных выражений, которое разрешается к элементам одного уровня.</span><span class="sxs-lookup"><span data-stu-id="e58d4-127">An MDX set expression that resolves into the members of a single level.</span></span> <span data-ttu-id="e58d4-128">Примером этого является *Level_Expression*.`Members`</span><span class="sxs-lookup"><span data-stu-id="e58d4-128">An example of this is the *Level_Expression*.`Members`</span></span> <span data-ttu-id="e58d4-129">Функция многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="e58d4-129">MDX function.</span></span> <span data-ttu-id="e58d4-130">Чтобы включить вычисляемые элементы, используйте *Level_Expression*.`AllMembers`</span><span class="sxs-lookup"><span data-stu-id="e58d4-130">To include calculated members, use the *Level_Expression*.`AllMembers`</span></span> <span data-ttu-id="e58d4-131">Функция многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="e58d4-131">MDX function.</span></span><br /><br /> <span data-ttu-id="e58d4-132">Дополнительные сведения см. в разделе [AllMembers (многомерные выражения)](/sql/mdx/allmembers-mdx).</span><span class="sxs-lookup"><span data-stu-id="e58d4-132">For more information, see [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span></span>|  
|<span data-ttu-id="e58d4-133">Набор потомков</span><span class="sxs-lookup"><span data-stu-id="e58d4-133">Set of descendants</span></span>|<span data-ttu-id="e58d4-134">Выражение набора многомерных выражений, которое разрешается к потомкам одного элемента.</span><span class="sxs-lookup"><span data-stu-id="e58d4-134">An MDX set expression that resolves into the descendants of a specified member.</span></span> <span data-ttu-id="e58d4-135">Примером этого является `Descendants` функция многомерных выражений (*Member_Expression*, *Level_Expression*, *Desc_Flag*).</span><span class="sxs-lookup"><span data-stu-id="e58d4-135">An example of this is the `Descendants`(*Member_Expression*, *Level_Expression*, *Desc_Flag*) MDX function.</span></span><br /><br /> <span data-ttu-id="e58d4-136">Дополнительные сведения см. в разделе [Descendants (многомерные выражения)](/sql/mdx/descendants-mdx).</span><span class="sxs-lookup"><span data-stu-id="e58d4-136">For more information, see [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e58d4-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="e58d4-137">See Also</span></span>  
 [<span data-ttu-id="e58d4-138">Построение вычислений значений ячеек в многомерном выражении (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="e58d4-138">Building Cell Calculations in MDX &#40;MDX&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/calculations.md)  
  
  
