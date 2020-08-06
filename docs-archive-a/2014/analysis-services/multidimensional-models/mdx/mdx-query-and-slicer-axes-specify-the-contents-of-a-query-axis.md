---
title: Указание содержимого оси запроса (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cellsets [MDX]
- query axis [MDX]
ms.assetid: c745ade0-738e-4a98-a3f0-3eabfd3eeba2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 28fd867b8f8caaf74e4dd704753c354368da2e89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734490"
---
# <a name="specifying-the-contents-of-a-query-axis-mdx"></a><span data-ttu-id="82b17-102">Определение содержимого оси запроса (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="82b17-102">Specifying the Contents of a Query Axis (MDX)</span></span>
  <span data-ttu-id="82b17-103">Оси запроса указывают границы набора ячеек, возвращаемого инструкцией многомерных выражений SELECT.</span><span class="sxs-lookup"><span data-stu-id="82b17-103">Query axes specify the edges of a cellset returned by a Multidimensional Expressions (MDX) SELECT statement.</span></span> <span data-ttu-id="82b17-104">Определение границ набора ячеек позволяет ограничить возвращаемые данные, видимые клиенту.</span><span class="sxs-lookup"><span data-stu-id="82b17-104">Specifying the edges of a cellset lets you restrict the returned data that is visible to the client.</span></span>  
  
 <span data-ttu-id="82b17-105">Для определения осей запроса используется инструкция `<SELECT query axis clause>` , связывающая набор с определенной осью запроса.</span><span class="sxs-lookup"><span data-stu-id="82b17-105">To specify query axes, you use the `<SELECT query axis clause>` to assign a set to a particular query axis.</span></span> <span data-ttu-id="82b17-106">Каждое значение в инструкции `<SELECT query axis clause>` определяет одну ось запроса.</span><span class="sxs-lookup"><span data-stu-id="82b17-106">Each `<SELECT query axis clause>` value defines one query axis.</span></span> <span data-ttu-id="82b17-107">Число осей в наборе данных равно числу значений `<SELECT query axis clause>` в инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="82b17-107">The number of axes in the dataset is equal to the number of `<SELECT query axis clause>` values in the SELECT statement.</span></span>  
  
## <a name="query-axis-syntax"></a><span data-ttu-id="82b17-108">Синтаксис определения оси запроса</span><span class="sxs-lookup"><span data-stu-id="82b17-108">Query Axis Syntax</span></span>  
 <span data-ttu-id="82b17-109">Для определения оси запроса в инструкции `<SELECT query axis clause>`используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="82b17-109">The following syntax shows the syntax for the `<SELECT query axis clause>`:</span></span>  
  
```  
  
<SELECT query axis clause> ::=  
   [ NON EMPTY ] Set_Expression [ <SELECT dimension property list clause> ] [<HAVING clause>]  
   ON {  
      Integer_Expression |   
      AXIS( Integer_Expression ) |   
      {COLUMNS | ROWS | PAGES | SECTIONS | CHAPTERS}     
      }  
  
```  
  
 <span data-ttu-id="82b17-110">У каждой оси запроса есть номер: ноль (0) для оси x, 1 для оси y, 2 для оси z и т. д.</span><span class="sxs-lookup"><span data-stu-id="82b17-110">Each query axis has a number: zero (0) for the x-axis, 1 for the y-axis, 2 for the z-axis, and so on.</span></span> <span data-ttu-id="82b17-111">В приведенном синтаксисе инструкции `<SELECT query axis clause>`значение `Integer_Expression` задает номер оси.</span><span class="sxs-lookup"><span data-stu-id="82b17-111">In the syntax for the `<SELECT query axis clause>`, the `Integer_Expression` value specifies the axis number.</span></span> <span data-ttu-id="82b17-112">В запросе многомерных выражений поддерживается до 128 осей, но очень редко в многомерных запросах встречается больше 5 осей.</span><span class="sxs-lookup"><span data-stu-id="82b17-112">An MDX query can support up to 128 specified axes, but very few MDX queries will use more than 5 axes.</span></span> <span data-ttu-id="82b17-113">Для первых 5 осей можно использовать псевдонимы COLUMNS, ROWS, PAGES, SECTIONS и CHAPTERS.</span><span class="sxs-lookup"><span data-stu-id="82b17-113">For the first 5 axes, the aliases COLUMNS, ROWS, PAGES, SECTIONS, and CHAPTERS can instead be used.</span></span>  
  
 <span data-ttu-id="82b17-114">В запросе многомерных выражений оси запроса не могут пропускаться.</span><span class="sxs-lookup"><span data-stu-id="82b17-114">An MDX query cannot skip query axes.</span></span> <span data-ttu-id="82b17-115">Это означает, что запрос, содержащий одну или несколько осей, не может не включать в себя промежуточные оси или оси с предыдущими номерами.</span><span class="sxs-lookup"><span data-stu-id="82b17-115">That is, a query that includes one or more query axes must not exclude lower-numbered or intermediate axes.</span></span> <span data-ttu-id="82b17-116">Например, не может быть запроса с осью ROWS, но без оси COLUMNS, или с осями COLUMNS и PAGES без оси ROWS.</span><span class="sxs-lookup"><span data-stu-id="82b17-116">For example, a query cannot have a ROWS axis without a COLUMNS axis, or have COLUMNS and PAGES axes without a ROWS axis.</span></span>  
  
 <span data-ttu-id="82b17-117">Можно, однако, указать предложение SELECT совсем без осей (то есть пустое предложение SELECT).</span><span class="sxs-lookup"><span data-stu-id="82b17-117">However, you can specify a SELECT clause without any axes (that is, an empty SELECT clause).</span></span> <span data-ttu-id="82b17-118">В этом случае все измерения будут измерениями среза, а запрос многомерных выражений выберет только одну ячейку.</span><span class="sxs-lookup"><span data-stu-id="82b17-118">In this case, all dimensions are slicer dimensions, and the MDX query selects one cell.</span></span>  
  
 <span data-ttu-id="82b17-119">В приведенном выше синтаксисе оси запроса каждое значение `Set_Expression` указывает набор, определяющий содержимое оси запроса.</span><span class="sxs-lookup"><span data-stu-id="82b17-119">In the query axis syntax previously shown, each `Set_Expression` value specifies the set that defines the contents of the query axis.</span></span> <span data-ttu-id="82b17-120">Дополнительные сведения о наборах см. в разделе [Работа с элементами, кортежами и наборами (многомерные выражения)](working-with-members-tuples-and-sets-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="82b17-120">For more information about sets, see [Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="82b17-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="82b17-121">Examples</span></span>  
 <span data-ttu-id="82b17-122">Следующая простая инструкция SELECT возвращает меру Internet Sales Amount по оси столбцов и использует функцию MDX MEMBERS для возвращения всех элементов из иерархии «Календарь» в измерении «Дата» по осям строк:</span><span class="sxs-lookup"><span data-stu-id="82b17-122">The following simple SELECT statement returns the measure Internet Sales Amount on the Columns axis, and uses the MDX MEMBERS function to return all the members from the Calendar hierarchy on the Date dimension on the Rows axis:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
{[Date].[Calendar].MEMBERS} ON ROWS  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="82b17-123">Два следующих запроса возвращают точно такие же результаты, но в них используются номера осей, а не псевдонимы:</span><span class="sxs-lookup"><span data-stu-id="82b17-123">The two following queries return exactly the same results but demonstrate the use of axis numbers rather than aliases:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON 0,  
{[Date].[Calendar].MEMBERS} ON 1  
FROM [Adventure Works]  
  
SELECT {[Measures].[Internet Sales Amount]} ON AXIS(0),  
{[Date].[Calendar].MEMBERS} ON AXIS(1)  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="82b17-124">Ключевое слово NON EMPTY, используемое до определения набора, представляет собой простой способ удаления пустых кортежей из осей.</span><span class="sxs-lookup"><span data-stu-id="82b17-124">The NON EMPTY keyword, used before the set definition, is an easy way to remove all empty tuples from an axis.</span></span> <span data-ttu-id="82b17-125">Например, в примерах, которые мы видели до сих пор, в Кубе нет данных с 2004 августа.</span><span class="sxs-lookup"><span data-stu-id="82b17-125">For example, in the examples we've seen so far there is no data in the cube from August 2004 onwards.</span></span> <span data-ttu-id="82b17-126">Чтобы удалить все строки из набора ячеек, в которых отсутствуют данные во всех столбцах, просто добавьте NON EMPTY до набора по оси строк следующим образом:</span><span class="sxs-lookup"><span data-stu-id="82b17-126">To remove all rows from the cellset that have no data in any column, simply add NON EMPTY before the set on the Rows axis definition as follows:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].MEMBERS} ON ROWS  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="82b17-127">NON EMPTY можно использовать для всех осей в запросе.</span><span class="sxs-lookup"><span data-stu-id="82b17-127">NON EMPTY can be used on all axes in a query.</span></span> <span data-ttu-id="82b17-128">Сравните результаты следующих двух запросов, в первом из которых не используется NON EMPTY, а второй использует NON EMPTY на обеих осях:</span><span class="sxs-lookup"><span data-stu-id="82b17-128">Compare the results of the following two queries, the first of which does not use NON EMPTY and the second of which does on both axes:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]}   
* [Promotion].[Promotion].[Promotion].MEMBERS  
ON COLUMNS,  
{[Date].[Calendar].[Calendar Year].MEMBERS} ON ROWS  
FROM [Adventure Works]  
WHERE([Product].[Subcategory].&[19])  
  
SELECT NON EMPTY {[Measures].[Internet Sales Amount]}   
* [Promotion].[Promotion].[Promotion].MEMBERS  
ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].[Calendar Year].MEMBERS} ON ROWS  
FROM [Adventure Works]  
WHERE([Product].[Subcategory].&[19])  
  
```  
  
 <span data-ttu-id="82b17-129">Предложение HAVING можно использовать для фильтрации содержимого осей на основе определенного критерия. Этот метод менее гибкий по сравнению с другими, дающими те же результаты (например использованием функции FILTER), однако отличается большей простотой использования.</span><span class="sxs-lookup"><span data-stu-id="82b17-129">The HAVING clause can be used to filter the contents of an axis based on a specific criteria; it is less flexible than other methods that can achieve the same results, such as the FILTER function, but it is simpler to use.</span></span> <span data-ttu-id="82b17-130">Ниже приведен пример, возвращающий только даты, в которых значение Internet Sales Amount больше 15 000 долларов США:</span><span class="sxs-lookup"><span data-stu-id="82b17-130">Here is an example that returns only those dates where Internet Sales Amount is greater than $15,000:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]}   
ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].[Date].MEMBERS}   
HAVING [Measures].[Internet Sales Amount]>15000  
ON ROWS  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="82b17-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="82b17-131">See Also</span></span>  
 [<span data-ttu-id="82b17-132">Определение содержимого оси среза (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="82b17-132">Specifying the Contents of a Slicer Axis &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
