---
title: Работа с элементами, кортежами и наборами (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], tuples
- member keys [MDX]
- MDX [Analysis Services], sets
- calculated members [MDX]
- members [MDX]
- Multidimensional Expressions [Analysis Services], members
- named sets [MDX]
- Multidimensional Expressions [Analysis Services], tuples
- member functions [MDX]
- sets [MDX]
- MDX [Analysis Services], members
- member names [MDX]
- Multidimensional Expressions [Analysis Services], sets
- tuple functions
- tuples
- set functions [MDX]
ms.assetid: b6ec2439-caef-46d3-9fd7-5f4526cee334
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ce3bf2d5ad7df2b1cd74897b3b49c7cef97e8ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655396"
---
# <a name="working-with-members-tuples-and-sets-mdx"></a><span data-ttu-id="f1b87-102">Работа с элементами, кортежами и наборами (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="f1b87-102">Working with Members, Tuples, and Sets (MDX)</span></span>
  <span data-ttu-id="f1b87-103">Многомерные выражения предоставляют функции, возвращающие один или более элементов, кортежей или наборов, или действуют на элемент, кортеж или набор.</span><span class="sxs-lookup"><span data-stu-id="f1b87-103">MDX provides numerous functions that return one or more members, tuples, or sets; or that act upon a member, tuple, or set.</span></span>  
  
## <a name="member-functions"></a><span data-ttu-id="f1b87-104">Функции элементов</span><span class="sxs-lookup"><span data-stu-id="f1b87-104">Member Functions</span></span>  
 <span data-ttu-id="f1b87-105">В языке многомерных выражений есть несколько функций для получения элементов из других многомерных сущностей, таких как измерения, уровни или кортежи.</span><span class="sxs-lookup"><span data-stu-id="f1b87-105">MDX provides several functions for retrieving members from other MDX entities, such as from dimensions, levels, sets, or tuples.</span></span> <span data-ttu-id="f1b87-106">Например, функция [FirstChild](/sql/mdx/firstchild-mdx) действует на элемент и возвращает элемент.</span><span class="sxs-lookup"><span data-stu-id="f1b87-106">For example, the [FirstChild](/sql/mdx/firstchild-mdx) function is a function that acts upon a member and returns a member.</span></span>  
  
 <span data-ttu-id="f1b87-107">Чтобы найти первый потомок измерения времени, можно указать его явно, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f1b87-107">To obtain the first child member of the Time dimension, you can explicitly state the member, as in the following example.</span></span>  
  
```  
SELECT [Date].[Calendar Year].[CY 2001] on 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="f1b87-108">Или же можно найти этот же элемент с помощью функции `FirstChild`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f1b87-108">You can also use the `FirstChild` function to return the same member, as in the following example.</span></span>  
  
```  
SELECT [Date].[Calendar Year].FirstChild on 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="f1b87-109">Дополнительные сведения о функциях элементов в многомерных выражениях см. в разделе [Справочник по функциям многомерных выражений (многомерные выражения)](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f1b87-109">For more information about MDX member functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="tuple-functions"></a><span data-ttu-id="f1b87-110">функции кортежей</span><span class="sxs-lookup"><span data-stu-id="f1b87-110">Tuple Functions</span></span>  
 <span data-ttu-id="f1b87-111">В языке многомерных выражений есть несколько функций, возвращающих кортежи. Эти функции можно использовать в любом месте, где допускаются кортежи.</span><span class="sxs-lookup"><span data-stu-id="f1b87-111">MDX provides several functions that return tuples, and they can be used anywhere that a tuple is accepted.</span></span> <span data-ttu-id="f1b87-112">Например, функция [Item (кортеж) (многомерные выражения)](/sql/mdx/item-tuple-mdx) может использоваться для получения первого кортежа из набора, что удобно, если известно, что набор состоит из единственного кортежа, который нужно передать функции, требующей кортеж в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="f1b87-112">For example, the [Item &#40;Tuple&#41; &#40;MDX&#41;](/sql/mdx/item-tuple-mdx) function can be used to extract the first tuple from set, which is very useful when you know that a set is composed of a single tuple and you want to supply that tuple to a function that requires a tuple.</span></span>  
  
 <span data-ttu-id="f1b87-113">В следующем примере возвращается первый кортеж из набора кортежей по оси столбцов.</span><span class="sxs-lookup"><span data-stu-id="f1b87-113">The following example returns the first tuple from within the set of tuples on the column axis.</span></span>  
  
```  
SELECT {  
   ([Measures].[Reseller Sales Amount]  
      ,[Date].[Calendar Year].[CY 2003]  
   )  
, ([Measures].[Reseller Sales Amount]  
      ,[Date].[Calendar Year].[CY 2004]  
   )  
}.Item(0)  
ON COLUMNS   
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="f1b87-114">Дополнительные сведения о функциях кортежей см. в разделе [Справочник по функциям многомерных выражений (многомерные выражения)](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f1b87-114">For more information about tuple functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="set-functions"></a><span data-ttu-id="f1b87-115">Функции наборов</span><span class="sxs-lookup"><span data-stu-id="f1b87-115">Set Functions</span></span>  
 <span data-ttu-id="f1b87-116">В языке многомерных выражений есть несколько функций, возвращающих наборы.</span><span class="sxs-lookup"><span data-stu-id="f1b87-116">MDX provides several functions that return sets.</span></span> <span data-ttu-id="f1b87-117">Чтобы извлечь набор, не обязательно явно перечислять все кортежи в квадратных скобках.</span><span class="sxs-lookup"><span data-stu-id="f1b87-117">Explicitly typing tuples and enclosing them in braces is not the only way to retrieve a set.</span></span> <span data-ttu-id="f1b87-118">Дополнительные сведения о функциях элементов, возвращающих наборы, см. в разделе [Основные понятия многомерных выражений (службы Analysis Services)](../key-concepts-in-mdx-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="f1b87-118">For more information about the members function to return a set, see [Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md).</span></span> <span data-ttu-id="f1b87-119">Существует множество дополнительных функций над наборами.</span><span class="sxs-lookup"><span data-stu-id="f1b87-119">There are many additional set functions.</span></span>  
  
 <span data-ttu-id="f1b87-120">Оператор «двоеточие» (:) позволяет использовать естественный порядок элементов для создания набора.</span><span class="sxs-lookup"><span data-stu-id="f1b87-120">The colon operator lets you use the natural order of members to create a set.</span></span> <span data-ttu-id="f1b87-121">Например, набор, представленный в следующем примере, содержит четыре кортежа: с первого по четвертый квартал календарного 2002 г.</span><span class="sxs-lookup"><span data-stu-id="f1b87-121">For example, the set shown in the following example contains tuples for the 1st through the 4th quarter of calendar year 2002.</span></span>  
  
```  
SELECT   
   {[Calendar Quarter].[Q1 CY 2002]:[Calendar Quarter].[Q4 CY 2002]}   
ON 0  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="f1b87-122">Такой же набор можно создать, не используя оператор двоеточия, а указав кортежи, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f1b87-122">If you do not use the colon operator to create the set, you can create the same set of members by specifying the tuples in the following example.</span></span>  
  
```  
SELECT {  
   [Calendar Quarter].[Q1 CY 2002],   
   [Calendar Quarter].[Q2 CY 2002],   
   [Calendar Quarter].[Q3 CY 2002],   
   [Calendar Quarter].[Q4 CY 2002]  
   } ON 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="f1b87-123">Оператор «двоеточие» (:) является инклюзивной функцией.</span><span class="sxs-lookup"><span data-stu-id="f1b87-123">The colon operator is an inclusive function.</span></span> <span data-ttu-id="f1b87-124">Результирующий набор содержит элементы, указанные с обеих сторон оператора двоеточия.</span><span class="sxs-lookup"><span data-stu-id="f1b87-124">The members on both sides of the colon operator are included in the resulting set.</span></span>  
  
 <span data-ttu-id="f1b87-125">Дополнительные сведения о функциях наборов см. в разделе [Справочник по функциям многомерных выражений (многомерные выражения)](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f1b87-125">For more information about set functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="array-functions"></a><span data-ttu-id="f1b87-126">Функции массивов</span><span class="sxs-lookup"><span data-stu-id="f1b87-126">Array Functions</span></span>  
 <span data-ttu-id="f1b87-127">Функции массивов обрабатывают набор и возвращают массив.</span><span class="sxs-lookup"><span data-stu-id="f1b87-127">An array function acts upon a set and returns an array.</span></span> <span data-ttu-id="f1b87-128">Дополнительные сведения о функциях массивов см. в разделе [Справочник по функциям многомерных выражений (многомерные выражения)](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f1b87-128">For more information about array functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="hierarchy-functions"></a><span data-ttu-id="f1b87-129">Функции иерархий</span><span class="sxs-lookup"><span data-stu-id="f1b87-129">Hierarchy Functions</span></span>  
 <span data-ttu-id="f1b87-130">Функции иерархий возвращают иерархию, обрабатывая элемент, уровень, иерархию или строку.</span><span class="sxs-lookup"><span data-stu-id="f1b87-130">A hierarchy function returns a hierarchy by acting upon a member, level, hierarchy, or string.</span></span> <span data-ttu-id="f1b87-131">Дополнительные сведения о функциях иерархий см. в разделе [Справочник по функциям многомерных выражений (многомерные выражения)](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f1b87-131">For more information about hierarchy functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="level-functions"></a><span data-ttu-id="f1b87-132">Функции уровней</span><span class="sxs-lookup"><span data-stu-id="f1b87-132">Level Functions</span></span>  
 <span data-ttu-id="f1b87-133">Функции уровней возвращают уровень, обрабатывая элемент, уровень или строку.</span><span class="sxs-lookup"><span data-stu-id="f1b87-133">A level function returns a level by acting upon a member, level, or string.</span></span> <span data-ttu-id="f1b87-134">Дополнительные сведения о функциях уровней см. в разделе [Справочник по функциям многомерных выражений (многомерные выражения)](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f1b87-134">For more information about level functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="logical-functions"></a><span data-ttu-id="f1b87-135">Логические функции</span><span class="sxs-lookup"><span data-stu-id="f1b87-135">Logical Functions</span></span>  
 <span data-ttu-id="f1b87-136">Логическая функция обрабатывает многомерное выражение, возвращая информацию о кортежах, элементах или наборах в выражении.</span><span class="sxs-lookup"><span data-stu-id="f1b87-136">A logical function acts upon a MDX expression to return information about the tuples, members, or sets in the expression.</span></span> <span data-ttu-id="f1b87-137">Например, функция [IsEmpty (многомерные выражения)](/sql/mdx/isempty-mdx) оценивает, возвращает ли выражение значение пустой ячейки.</span><span class="sxs-lookup"><span data-stu-id="f1b87-137">For example, the [IsEmpty &#40;MDX&#41;](/sql/mdx/isempty-mdx) function evaluates whether an expression has returned an empty cell value.</span></span> <span data-ttu-id="f1b87-138">Дополнительные сведения о логических функциях см. в разделе [Справочник по функциям многомерных выражений (многомерные выражения)](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f1b87-138">For more information about logical functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="numeric-functions"></a><span data-ttu-id="f1b87-139">Числовые функции</span><span class="sxs-lookup"><span data-stu-id="f1b87-139">Numeric Functions</span></span>  
 <span data-ttu-id="f1b87-140">Числовая функция обрабатывает многомерное выражение, возвращая скалярную величину.</span><span class="sxs-lookup"><span data-stu-id="f1b87-140">A numeric function acts upon a MDX expression to return a scalar value.</span></span> <span data-ttu-id="f1b87-141">Например, функция [Aggregate (многомерные выражения)](/sql/mdx/aggregate-mdx) возвращает скалярную величину, вычисляемую с помощью статистической обработки мер по кортежам в заданном наборе.</span><span class="sxs-lookup"><span data-stu-id="f1b87-141">For example, the [Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) function returns a scalar value calculated by aggregating measures over the tuples in a specified set.</span></span> <span data-ttu-id="f1b87-142">Дополнительные сведения о числовых функциях см. в разделе [Справочник по функциям многомерных выражений (многомерные выражения)](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f1b87-142">For more information about numeric functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="string-functions"></a><span data-ttu-id="f1b87-143">Строковые функции</span><span class="sxs-lookup"><span data-stu-id="f1b87-143">String Functions</span></span>  
 <span data-ttu-id="f1b87-144">Строковая функция обрабатывает многомерное выражение, возвращая строку.</span><span class="sxs-lookup"><span data-stu-id="f1b87-144">A string function acts upon a MDX expression to return a string.</span></span> <span data-ttu-id="f1b87-145">Например, функция [UniqueName (многомерные выражения)](/sql/mdx/uniquename-mdx) возвращает строковое значение, включающее в себя уникальное имя измерения, иерархии, уровня или элемента.</span><span class="sxs-lookup"><span data-stu-id="f1b87-145">For example, the [UniqueName &#40;MDX&#41;](/sql/mdx/uniquename-mdx) function returns a string value containing the unique name of a dimension, hierarchy, level, or member.</span></span> <span data-ttu-id="f1b87-146">Дополнительные сведения о строковых функциях см. в разделе [Справочник по функциям многомерных выражений (многомерные выражения)](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f1b87-146">For more information about string functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b87-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="f1b87-147">See Also</span></span>  
 <span data-ttu-id="f1b87-148">[Основные понятия в Analysis Services &#40;многомерных выражений&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="f1b87-148">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="f1b87-149">[Основные принципы запросов многомерных выражений &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="f1b87-149">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 [<span data-ttu-id="f1b87-150">Справочник по функциям многомерных выражений (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="f1b87-150">MDX Function Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-function-reference-mdx)  
  
  
