---
title: Пространство куба | Документация Майкрософт
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c3a012b4-9ca0-4fb8-9c26-5ecc0e2e2b2b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0a6a6da73815f06aa5ab80f6ad5a9d06227ed842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658456"
---
# <a name="cube-space"></a><span data-ttu-id="f61ed-102">Пространство куба</span><span class="sxs-lookup"><span data-stu-id="f61ed-102">Cube Space</span></span>
  <span data-ttu-id="f61ed-103">Пространство куба — это совокупность элементов иерархий атрибутов куба с мерами куба.</span><span class="sxs-lookup"><span data-stu-id="f61ed-103">Cube space is the product of the members of a cube's attribute hierarchies with the cube's measures.</span></span> <span data-ttu-id="f61ed-104">Поэтому пространство куба определяется комбинаторным сочетанием всех элементов иерархии атрибута в кубе и мер куба и определяет максимальный размер куба.</span><span class="sxs-lookup"><span data-stu-id="f61ed-104">Therefore, the cube space is determined by the combinatorial product of all attribute hierarchy members in the cube and the cube's measures and defines the maximum size of the cube.</span></span> <span data-ttu-id="f61ed-105">Важно иметь ввиду, что это пространство включает все возможные сочетания элементов иерархии атрибута, даже сочетания, которые могут показаться невозможными в реальном мире, например сочетания, где городом является Париж, а странами — Англия, Испания, Япония или Индия, и т. д.</span><span class="sxs-lookup"><span data-stu-id="f61ed-105">It is important to note that this space includes all possible combinations of attribute hierarchy members; even combinations that might be deem as impossible in the real world i.e. combinations where the city is Paris and the countries are England or Spain or Japan or India or elsewhere.</span></span>  
  
## <a name="autoexists-and-cube-space"></a><span data-ttu-id="f61ed-106">Автоматическая проверка существования и пространство куба</span><span class="sxs-lookup"><span data-stu-id="f61ed-106">Autoexists and cube space</span></span>  
 <span data-ttu-id="f61ed-107">Понятие *автоматическая проверка существования* ограничивает пространство куба ячейками, которые действительно существуют.</span><span class="sxs-lookup"><span data-stu-id="f61ed-107">The concept of *autoexists* limits this cube space to those cells that actually exist.</span></span> <span data-ttu-id="f61ed-108">Элементы иерархии атрибута в измерении могут не существовать с элементами другой иерархии атрибута в том же измерении.</span><span class="sxs-lookup"><span data-stu-id="f61ed-108">Members of an attribute hierarchy in a dimension may not exist with members of another attribute hierarchy in the same dimension.</span></span>  
  
 <span data-ttu-id="f61ed-109">Например, пространство куба, содержащего иерархию атрибута City, иерархию атрибута Country и меру Internet Sales Amount, включает только те элементы, которые существуют друг с другом.</span><span class="sxs-lookup"><span data-stu-id="f61ed-109">For example, if you have a cube that has a City attribute hierarchy, a Country attribute hierarchy, and an Internet Sales Amount measure, the space of this cube only includes those members that exist with each other.</span></span> <span data-ttu-id="f61ed-110">Например, если иерархия атрибута «City» содержит элементы «New York», «London», «Paris», «Tokyo» и «Melbourne», а иерархия атрибута «Country» содержит страны «США», «United Kingdom», «France», «Japan» и «Australia», то пространство куба не содержит ячейку на пересечении элементов «Paris» и «США».</span><span class="sxs-lookup"><span data-stu-id="f61ed-110">For example, if the City attribute hierarchy includes the cities New York, London, Paris, Tokyo, and Melbourne; and the Country attribute hierarchy includes the countries United States, United Kingdom, France, Japan, and Australia; then the space of the cube does not include the space (cell) at the intersection of Paris and United States.</span></span>  
  
 <span data-ttu-id="f61ed-111">Запрос к несуществующим ячейкам возвращает значение NULL, то есть они не могут содержать вычисления и нельзя определить вычисления, записывающие данные в это место пространства.</span><span class="sxs-lookup"><span data-stu-id="f61ed-111">When querying cells that do not exist, non-existing cells return nulls; that is, they cannot contain calculations and you cannot define a calculation that writes to this space.</span></span> <span data-ttu-id="f61ed-112">Например, следующая инструкция включает в себя несуществующие ячейки.</span><span class="sxs-lookup"><span data-stu-id="f61ed-112">For example, the following statement includes cells that do not exist.</span></span>  
  
```  
SELECT [Customer].[Gender].[Gender].Members ON COLUMNS,  
{[Customer].[Customer].[Aaron A. Allen]  
   ,[Customer].[Customer].[Abigail Clark]} ON ROWS   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f61ed-113">В следующем запросе применяется функция [Members (Set) (многомерные выражения)](/sql/mdx/members-set-mdx) для получения набора элементов иерархии атрибута Gender по оси столбцов и выполняется перекрестное соединение этого набора с заданным набором элементов из иерархии атрибута Customer по оси строк.</span><span class="sxs-lookup"><span data-stu-id="f61ed-113">This query uses the [Members (Set) (MDX)](/sql/mdx/members-set-mdx) function to return the set of members of the Gender attribute hierarchy on the column axis, and crosses this set with the specified set of members from the Customer attribute hierarchy on the row axis.</span></span>  
  
 <span data-ttu-id="f61ed-114">При выполнении предыдущего запроса ячейка на пересечении элементов [Aaron A. Allen] и [Female] отображает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f61ed-114">When you execute the previous query, the cell at the intersection of Aaron A. Allen and Female displays a null.</span></span> <span data-ttu-id="f61ed-115">Аналогично, значение NULL отображается в ячейке на пересечении элементов [Abigail Clark] и [Male].</span><span class="sxs-lookup"><span data-stu-id="f61ed-115">Similarly, the cell at the intersection of Abigail Clark and Male displays a null.</span></span> <span data-ttu-id="f61ed-116">Эти ячейки не существуют и не могут содержать значение, но запрос может вернуть несуществующие ячейки.</span><span class="sxs-lookup"><span data-stu-id="f61ed-116">These cells do not exist and cannot contain a value, but cells that do not exist can appear in the result returned by a query.</span></span>  
  
 <span data-ttu-id="f61ed-117">При использовании функции [Crossjoin (многомерные выражения)](/sql/mdx/crossjoin-mdx) для получения перекрестного произведения элементов иерархий атрибутов из иерархий атрибутов одного измерения автоматическое существование ограничивает возвращаемые кортежи набором действительно существующих кортежей, а не возвращает все декартово произведение.</span><span class="sxs-lookup"><span data-stu-id="f61ed-117">When you use the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function to return the cross-product of attribute hierarchy members from attribute hierarchies in the same dimension, auto-exists limits those tuples being returned to the set of tuples that actually exist, rather than returning a full Cartesian product.</span></span> <span data-ttu-id="f61ed-118">Выполните следующий запрос и изучите его результаты.</span><span class="sxs-lookup"><span data-stu-id="f61ed-118">For example, run and then examine the results from the execution of the following query.</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[State-Province].Members  
  ) ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f61ed-119">Обратите внимание, что 0 используется для обозначения оси столбцов, это сокращение для оси(0), являющейся осью столбцов.</span><span class="sxs-lookup"><span data-stu-id="f61ed-119">Notice that 0 is used to designate the column axis, which is shorthand for axis(0) - which is the column axis.</span></span>  
  
 <span data-ttu-id="f61ed-120">В предыдущем запросе возвращаются только ячейки для элементов каждой иерархии атрибута в запросе, которые существуют друг с другом.</span><span class="sxs-lookup"><span data-stu-id="f61ed-120">The previous query only returns cells for members from each attribute hierarchy in the query that exist with each other.</span></span> <span data-ttu-id="f61ed-121">Предыдущий запрос также может быть написан с помощью нового варианта \* для функции [ \* (перекрестного) (многомерные выражения)](/sql/mdx/crossjoin-mdx) .</span><span class="sxs-lookup"><span data-stu-id="f61ed-121">The previous query can also be written using the new \* variant of the [\* (Crossjoin) (MDX)](/sql/mdx/crossjoin-mdx) function.</span></span>  
  
```  
SELECT   
   [Customer].[Country].[United States] *   
      [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="f61ed-122">Предыдущий запрос можно переписать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f61ed-122">The previous query could also be written in the following manner:</span></span>  
  
```  
SELECT [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE (Measures.[Internet Sales Amount],  
   [Customer].[Country].[United States])  
```  
  
 <span data-ttu-id="f61ed-123">Значения ячеек будут совпадать, хотя метаданные в результирующем наборе будут разными.</span><span class="sxs-lookup"><span data-stu-id="f61ed-123">The cells values returned will be identical, although the metadata in the result set will be different.</span></span> <span data-ttu-id="f61ed-124">Например, в предыдущем запросе иерархия Country перемещена на ось среза (в предложении WHERE) и поэтому не представлена явно в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="f61ed-124">For example, with the previous query, the Country hierarchy was moved to the slicer axis (in the WHERE clause) and therefore does not appear explicitly in the result set.</span></span>  
  
 <span data-ttu-id="f61ed-125">Каждый из этих трех предыдущих запросов демонстрирует результат поведения автоматического существования в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f61ed-125">Each of these three previous queries demonstrates the effect of the auto-exists behavior in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="user-defined-hierarchies-and-cube-space"></a><span data-ttu-id="f61ed-126">Пользовательские иерархии и пространство куба</span><span class="sxs-lookup"><span data-stu-id="f61ed-126">User-Defined Hierarchies and Cube Space</span></span>  
 <span data-ttu-id="f61ed-127">В предыдущих примерах этого раздела позиции внутри пространства куба определялись с помощью иерархий атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f61ed-127">The previous examples in this topic define positions in cube space by using attribute hierarchies.</span></span> <span data-ttu-id="f61ed-128">Позицию в пространстве куба можно также определить с помощью пользовательских иерархий, определенных на основе иерархий атрибутов в измерении.</span><span class="sxs-lookup"><span data-stu-id="f61ed-128">However, you can also define a position in cube space by using user-defined hierarchies that have been defined based on attribute hierarchies in a dimension.</span></span> <span data-ttu-id="f61ed-129">Пользовательской называется иерархия иерархий атрибутов, сконструированная для упрощения обзора данных в кубе.</span><span class="sxs-lookup"><span data-stu-id="f61ed-129">A user-defined hierarchy is a hierarchy of attribute hierarchies designed to facilitate browsing of cube data by users.</span></span>  
  
 <span data-ttu-id="f61ed-130">Например, запрос `CROSSJOIN` в предыдущем разделе можно переписать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f61ed-130">For example, the `CROSSJOIN` query in the previous section could also have been written as follows:</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[Customer Geography].[State-Province].Members  
   )   
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="f61ed-131">В предыдущем запросе пользовательская иерархия Customer Geography в измерении Customer используется для определения позиции в пространстве куба, которая ранее определялась с помощью иерархии атрибута.</span><span class="sxs-lookup"><span data-stu-id="f61ed-131">In the previous query, the Customer Geography user-defined hierarchy within the Customer dimension is used to define the position in cube space that was previously defined by using an attribute hierarchy.</span></span> <span data-ttu-id="f61ed-132">С помощью иерархий атрибутов и пользовательских иерархий можно определить одинаковую позицию в пространстве куба.</span><span class="sxs-lookup"><span data-stu-id="f61ed-132">The identical position in cube space can be defined by using either attribute hierarchies or user-defined hierarchies.</span></span>  
  
##  <a name="attribute-relationships-and-cube-space"></a><a name="AttribRelationships"></a><span data-ttu-id="f61ed-133">Связи атрибутов и пространство куба</span><span class="sxs-lookup"><span data-stu-id="f61ed-133">Attribute Relationships and Cube Space</span></span>  
 <span data-ttu-id="f61ed-134">Определение связи атрибутов между связанными атрибутами увеличивает производительность запросов (облегчая создание соответствующих статистических обработок) и влияет на элемент связанной иерархии атрибута, который появляется с элементом иерархии атрибута.</span><span class="sxs-lookup"><span data-stu-id="f61ed-134">Defining attribute relationships between related attributes improves query performance (by facilitating the creation of appropriate aggregations) and affects the member of a related attribute hierarchy that appears with an attribute hierarchy member.</span></span> <span data-ttu-id="f61ed-135">Например, если определяется кортеж, содержащий элемент из иерархии атрибута City, и в кортеже не определен явно элемент иерархии атрибута Country, можно предположить, что элементом иерархии атрибута Country по умолчанию будет связанный элемент иерархии атрибута Country.</span><span class="sxs-lookup"><span data-stu-id="f61ed-135">For example, when you define a tuple that includes a member from the City attribute hierarchy and the tuple does not explicitly define the Country attribute hierarchy member, you might expect that the default Country attribute hierarchy member would be the related member of the Country attribute hierarchy.</span></span> <span data-ttu-id="f61ed-136">Тем не менее, это действительно так, только если определена связь атрибутов между иерархиями атрибутов City и Country.</span><span class="sxs-lookup"><span data-stu-id="f61ed-136">However, this is only true if an attribute relationship is defined between the City attribute hierarchy and the Country attribute hierarchy.</span></span>  
  
 <span data-ttu-id="f61ed-137">В следующем примере возвращается элемент из иерархии связанных атрибутов, который не включен явно в запрос.</span><span class="sxs-lookup"><span data-stu-id="f61ed-137">The following example returns the member of a related attribute hierarchy that is not included explicitly in the query.</span></span>  
  
```  
WITH MEMBER Measures.x AS   
   Customer.Country.CurrentMember.Name  
SELECT Measures.x ON 0,  
Customer.City.Members ON 1  
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f61ed-138">Обратите внимание, что `WITH` ключевое слово используется с функциями [CurrentMember (многомерные выражения)](/sql/mdx/current-mdx) и [Name (многомерные выражения)](/sql/mdx/members-string-mdx) для создания вычисляемого элемента для использования в запросе.</span><span class="sxs-lookup"><span data-stu-id="f61ed-138">Notice that the `WITH` keyword is used with the [CurrentMember (MDX)](/sql/mdx/current-mdx) and [Name (MDX)](/sql/mdx/members-string-mdx) functions to create a calculated member for use in the query.</span></span> <span data-ttu-id="f61ed-139">Дополнительные сведения см. в разделе [Базовый запрос многомерных выражений (многомерные выражения)](mdx-query-the-basic-query.md).</span><span class="sxs-lookup"><span data-stu-id="f61ed-139">For more information, see [The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md).</span></span>  
  
 <span data-ttu-id="f61ed-140">В предыдущем запросе возвращалось имя элемента иерархии атрибута Country, связанного с каждым элементом иерархии атрибута State.</span><span class="sxs-lookup"><span data-stu-id="f61ed-140">In the previous query, the name of the member of the Country attribute hierarchy that is associated with each member of the State attribute hierarchy is returned.</span></span> <span data-ttu-id="f61ed-141">Возвращается ожидаемый элемент Country (поскольку определена связь атрибутов City и Country).</span><span class="sxs-lookup"><span data-stu-id="f61ed-141">The expected Country member appears (because an attribute relationship is defined between the City and Country attributes).</span></span> <span data-ttu-id="f61ed-142">Тем не менее, если в этом измерении не определена связь атрибутов между иерархиями атрибутов, возвращается элемент «(Все)», как продемонстрировано в следующем запросе.</span><span class="sxs-lookup"><span data-stu-id="f61ed-142">However, if no attribute relationship were defined between attribute hierarchies in the same dimension, the (All) member would be returned, as illustrated in the following query.</span></span>  
  
```  
WITH MEMBER Measures.x AS   
   Customer.Education.Currentmember.Name  
SELECT Measures.x  ON 0,   
Customer.City.Members ON 1  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="f61ed-143">В предыдущем запросе возвращается элемент «(Все)» ("All Customers"), поскольку связь между атрибутами Education и City не определена.</span><span class="sxs-lookup"><span data-stu-id="f61ed-143">In the previous query, the (All) member ("All Customers") is returned, because there is no relationship between Education and City.</span></span> <span data-ttu-id="f61ed-144">Таким образом, элемент «(Все)» иерархии атрибута Education будет ее элементом по умолчанию, используемым в любом кортеже, где участвует иерархия атрибута City, в которой элемент Education явно не указан.</span><span class="sxs-lookup"><span data-stu-id="f61ed-144">Therefore, the (All) member of the Education attribute hierarchy would be the default member of the Education attribute hierarchy used in any tuple involving the City attribute hierarchy where an Education member is not explicitly provided.</span></span>  
  
## <a name="calculation-context"></a><span data-ttu-id="f61ed-145">Контекст вычисления</span><span class="sxs-lookup"><span data-stu-id="f61ed-145">Calculation Context</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f61ed-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="f61ed-146">See Also</span></span>  
 <span data-ttu-id="f61ed-147">[Основные понятия в Analysis Services &#40;многомерных выражений&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="f61ed-147">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="f61ed-148">[Кортежей](tuples.md) </span><span class="sxs-lookup"><span data-stu-id="f61ed-148">[Tuples](tuples.md) </span></span>  
 <span data-ttu-id="f61ed-149">[Автоматической проверки существования](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="f61ed-149">[Autoexists](autoexists.md) </span></span>  
 <span data-ttu-id="f61ed-150">[Работа с элементами, кортежами и наборами &#40;многомерных выражениях&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="f61ed-150">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="f61ed-151">[Визуальные итоги и невизуальные итоги](visual-totals-and-non-visual-totals.md) </span><span class="sxs-lookup"><span data-stu-id="f61ed-151">[Visual Totals and Non Visual Totals](visual-totals-and-non-visual-totals.md) </span></span>  
 <span data-ttu-id="f61ed-152">[Справочник по языку многомерных выражений &#40;&#41;многомерных выражений](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="f61ed-152">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="f61ed-153">Справочник по многомерным выражениям (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="f61ed-153">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
