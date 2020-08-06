---
title: Контекст вычисления | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: aec8aa98-b77d-4f8f-9684-2618b1d8e970
author: minewiskan
ms.author: owend
ms.openlocfilehash: e6d14df51c6ec37fb96520af7acf207227ae4ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733213"
---
# <a name="calculation-context"></a><span data-ttu-id="8a1ea-102">Контекст вычисления</span><span class="sxs-lookup"><span data-stu-id="8a1ea-102">Calculation Context</span></span>
  <span data-ttu-id="8a1ea-103">Контекстом вычисления является известное подпространство куба, где оценивается выражение, а все координаты либо известны, либо могут получены с помощью выражения.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-103">The calculation context is the known subspace of the cube where an expression is evaluated and all coordinates are either explicitly known or can be derived from the expression.</span></span>  
  
## <a name="determining-the-calculation-context"></a><span data-ttu-id="8a1ea-104">Определение контекста вычисления</span><span class="sxs-lookup"><span data-stu-id="8a1ea-104">Determining the calculation context</span></span>  
 <span data-ttu-id="8a1ea-105">Любые набор, элемент, кортеж, числовая функция выполняются в контексте всего многомерного выражения или инструкции.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-105">Every set, member, tuple, or numeric function executes in the context of the entire MDX expression or statement.</span></span> <span data-ttu-id="8a1ea-106">Когда такой аргумент, как кортеж, передается в функцию, в явном виде задаются только некоторые координаты в пространстве куба.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-106">When an argument, such as a tuple, is passed to a function, only some of the coordinates in the cube space are explicitly provided.</span></span> <span data-ttu-id="8a1ea-107">Для получения остальных координат используется текущий контекст вычисления.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-107">The other coordinates are obtained based on the current calculation context.</span></span>  
  
 <span data-ttu-id="8a1ea-108">Контекст вычисления для неуказанных координат ячейки или элементов атрибута определяется в следующем порядке.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-108">The calculation context for unspecified cell coordinates and attribute members is determined in the following order:</span></span>  
  
1.  <span data-ttu-id="8a1ea-109">Предложение FROM (если применимо). В этом предложении можно или указать куб полностью, или указать вложенный куб в виде инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-109">The FROM clause (if applicable) - this clause can either specify an entire cube or can specify a subcube in the form of a SELECT statement.</span></span>  
  
2.  <span data-ttu-id="8a1ea-110">Предложение WHERE (если применимо). В этом предложении, которое также называется *осью среза*, можно указать набор, кортеж или элемент, ограничивающий элементы, которые возвращаются запросом по осям столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-110">The WHERE clause (if applicable) - this clause, which is also known as the *slicer axis*, on which you specify a set, tuple, or member that restricts the members returned on the column and row axis by a query.</span></span> <span data-ttu-id="8a1ea-111">Элемент по умолчанию каждой иерархии атрибута, который не указан явно по осям столбцов или строк, по существу является частью оси среза.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-111">Conceptually, the default member of every attribute hierarchy that is not explicitly specified on column or row axis is part of the slicer axis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8a1ea-112">Когда координаты ячейки для отдельного атрибута указаны и по оси среза, и по другой оси, координаты, указанные в функции, могут иметь преимущество при определении элементов набора по этой оси.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-112">When cell coordinates for a particular attribute are specified on both the slicer axis and on another axis, the coordinates specified in the function may take precedence in determining the members of the set on the axis.</span></span> <span data-ttu-id="8a1ea-113">Примерами таких функций являются [Filter (многомерные выражения)](/sql/mdx/filter-mdx) и [Order (многомерные выражения)](/sql/mdx/order-mdx) , результат можно отфильтровать или упорядочить по элементам атрибута, которые исключены из контекста вычисления предложением WHERE или инструкцией SELECT в предложении FROM.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-113">The [Filter (MDX)](/sql/mdx/filter-mdx) and [Order (MDX)](/sql/mdx/order-mdx) functions are examples of such functions - you can filter or order a result by attribute members that are excluded from the calculation context by the WHERE clause, or by a SELECT statement in the FROM clause.</span></span>  
  
3.  <span data-ttu-id="8a1ea-114">Именованные наборы и вычисляемые элементы, определенные в запросе или выражении.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-114">The named sets and calculated members defined in the query or expression.</span></span>  
  
4.  <span data-ttu-id="8a1ea-115">Кортежи и наборы, заданные по осям строк и столбцов и использующие элемент по умолчанию для атрибутов, которые не появляются по осям строк и столбцов и оси среза.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-115">The tuples and sets specified on the row and column axes, utilizing the default member for attributes that do not appear on the row, column, or slicer axis.</span></span>  
  
5.  <span data-ttu-id="8a1ea-116">Ячейки куба или вложенного куба на каждой оси, устраняющие пустые кортежи на оси и применяющие предложение HAVING.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-116">The cube or subcube cells on each axis, eliminating empty tuples on the axis and applying the HAVING clause.</span></span>  
  
6.  <span data-ttu-id="8a1ea-117">Дополнительные сведения см. в разделе [Определение контекста куба в запросе (многомерные выражения)](establishing-cube-context-in-a-query-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="8a1ea-117">For more information, see [Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md).</span></span>  
  
 <span data-ttu-id="8a1ea-118">В следующем запросе контекст вычисления для каждой оси строк ограничен элементом атрибута Country и элементом атрибута Calendar Year, указанным в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-118">In the following query, the calculation context for the row axis is restricted by the Country attribute member and the Calendar Year attribute member that are specified in the WHERE clause.</span></span>  
  
```  
SELECT Customer.City.City.Members ON 0  
FROM [Adventure Works]  
WHERE (Customer.Country.France, [Date].[Calendar].[Calendar Year].[CY 2004],  
   Measures.[Internet Sales Amount])  
```  
  
 <span data-ttu-id="8a1ea-119">Тем не менее, если изменить запрос, указав функцию `FILTER` по оси строк, и передать в функцию `FILTER` элемент иерархии атрибута Calendar Year, то этот элемент, который раньше использовался для определения контекста вычисления элементов набора по оси столбцов, можно изменить.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-119">However, if you modify this query by specifying the `FILTER` function on the row axis, and utilize a Calendar Year attribute hierarchy member in the `FILTER` function, then the attribute member from the Calendar Year attribute hierarchy that is used to provide the calculation context for the members of the set on the column axis can be modified.</span></span>  
  
```  
SELECT FILTER  
   (  
      Customer.City.City.Members,   
         ([Date].[Calendar].[Calendar Year].[CY 2003],  
            Measures.[Internet Order Quantity]) > 75   
   ) ON 0  
FROM [Adventure Works]  
WHERE (Customer.Country.France,  
   [Date].[Calendar].[Calendar Year].[CY 2004],  
   Measures.[Internet Sales Amount])  
```  
  
 <span data-ttu-id="8a1ea-120">В предыдущем запросе контекст вычисления ячеек в кортежах по оси столбцов фильтровался по элементу «CY 2003» иерархии атрибута Calendar Yea, даже если номинальным контекстом вычисления для иерархии атрибута Calendar Year является элемент «CY 2004».</span><span class="sxs-lookup"><span data-stu-id="8a1ea-120">In the previous query, the calculation context for the cells in the tuples that appear on the column axis is filtered by the CY 2003 member of the Calendar Year attribute hierarchy, even though the nominal calculation context for the Calendar Year attribute hierarchy is CY 2004.</span></span> <span data-ttu-id="8a1ea-121">Кроме того, он фильтруется по мере Internet Order Quantity (объемов заказов через Интернет).</span><span class="sxs-lookup"><span data-stu-id="8a1ea-121">Furthermore, it is filtered by the Internet Order Quantity measure.</span></span> <span data-ttu-id="8a1ea-122">Тем не менее, поскольку элементы набора по оси столбцов заданы, контекст вычисления значений элементов, которые отображаются на оси, опять определяется предложением WHERE.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-122">However, once the members of the set on the column axis is set, the calculation context for the values for the members that appear on the axis is again determined by the WHERE clause.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8a1ea-123">Чтобы увеличить производительность запроса, следует удалить элементы и кортежи как можно раньше в процессе разрешений.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-123">To increase query performance, you should eliminate members and tuples as early in the resolution process as possible.</span></span> <span data-ttu-id="8a1ea-124">Таким образом уменьшается время вычисления сложного запроса на конечном наборе элементов, поскольку запрос обрабатывает минимально возможное количество ячеек.</span><span class="sxs-lookup"><span data-stu-id="8a1ea-124">In this manner, complex query time calculations on the final set of members operate on the fewest cells possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a1ea-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a1ea-125">See Also</span></span>  
 <span data-ttu-id="8a1ea-126">[Определение контекста куба в запросе &#40;многомерных выражений&#41;](establishing-cube-context-in-a-query-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="8a1ea-126">[Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span></span>  
 <span data-ttu-id="8a1ea-127">[Основные принципы запросов многомерных выражений &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="8a1ea-127">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 [<span data-ttu-id="8a1ea-128">Основные понятия многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="8a1ea-128">Key Concepts in MDX &#40;Analysis Services&#41;</span></span>](../key-concepts-in-mdx-analysis-services.md)  
  
  
