---
title: Указание содержимого оси среза (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- filtering data [MDX]
ms.assetid: c56b0a70-cdec-427f-990e-425290344e7d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8620c54970ea14a2ac01c85262a372d2b3db0d68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728878"
---
# <a name="specifying-the-contents-of-a-slicer-axis-mdx"></a><span data-ttu-id="cf28e-102">Определение содержимого оси среза (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="cf28e-102">Specifying the Contents of a Slicer Axis (MDX)</span></span>
  <span data-ttu-id="cf28e-103">Ось среза фильтрует данные, возвращаемые инструкцией многомерных выражений SELECT. При этом возвращаются только данные, пересекающиеся с заданными элементами.</span><span class="sxs-lookup"><span data-stu-id="cf28e-103">The slicer axis filters the data returned by the Multidimensional Expressions (MDX) SELECT statement, restricting the returned data so that only data intersecting with the specified members will be returned.</span></span> <span data-ttu-id="cf28e-104">Может рассматриваться как дополнительная невидимая ось в запросе.</span><span class="sxs-lookup"><span data-stu-id="cf28e-104">It can be thought of as an invisible extra axis in a query.</span></span> <span data-ttu-id="cf28e-105">Ось среза определяется в предложении WHERE инструкции многомерных выражений SELECT.</span><span class="sxs-lookup"><span data-stu-id="cf28e-105">The slicer axis is defined in the WHERE clause of the SELECT statement in MDX.</span></span>  
  
## <a name="slicer-axis-syntax"></a><span data-ttu-id="cf28e-106">Синтаксис определения оси среза</span><span class="sxs-lookup"><span data-stu-id="cf28e-106">Slicer Axis Syntax</span></span>  
 <span data-ttu-id="cf28e-107">Для явного определения оси среза используется следующий синтаксис в инструкции многомерных выражений `<SELECT slicer axis clause>` .</span><span class="sxs-lookup"><span data-stu-id="cf28e-107">To explicitly specify a slicer axis, you  using the `<SELECT slicer axis clause>` in MDX, as described in the following syntax:</span></span>  
  
```  
<SELECT slicer axis clause> ::=  WHERE Set_Expression  
```  
  
 <span data-ttu-id="cf28e-108">В приведенном синтаксисе определения оси среза аргумент `Set_Expression` может принимать либо кортежное выражение, интерпретируемое как набор при вычислении предложения, либо выражение набора.</span><span class="sxs-lookup"><span data-stu-id="cf28e-108">In the slicer axis syntax shown, `Set_Expression` can take either a tuple expression, which is treated as a set for the purposes of evaluating the clause, or a set expression.</span></span> <span data-ttu-id="cf28e-109">Если задано выражение набора, язык многомерных выражений пытается вычислить набор с использованием статистического вычисления по результирующим ячейкам в каждом кортеже набора.</span><span class="sxs-lookup"><span data-stu-id="cf28e-109">If a set expression is specified, MDX will try to evaluate the set, aggregating the result cells in every tuple along the set.</span></span> <span data-ttu-id="cf28e-110">Иными словами, используется функция [Aggregate](/sql/mdx/aggregate-mdx) для набора, при этом каждая мера статистически обрабатывается с помощью связанной статистической функции.</span><span class="sxs-lookup"><span data-stu-id="cf28e-110">In other words, MDX will try to use the [Aggregate](/sql/mdx/aggregate-mdx) function on the set, aggregating each measure by its associated aggregation function.</span></span> <span data-ttu-id="cf28e-111">Кроме того, если выражение набора нельзя выразить в виде перекрестного соединения элементов иерархии атрибутов, при вычислении в языке многомерных выражений ячейки, находящиеся за пределами выражения набора, с помощью которого определена ось среза, интерпретируются как имеющие значения NULL.</span><span class="sxs-lookup"><span data-stu-id="cf28e-111">Also, if the set expression cannot be expressed as a crossjoin of attribute hierarchy members, MDX treats cells that fall outside of the set expression for the slicer as null for evaluation purposes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cf28e-112">В отличие от предложения WHERE в SQL, в котором предложение WHERE инструкции MDX SELECT напрямую не выполняет фильтрацию результатов запросов по оси строк.</span><span class="sxs-lookup"><span data-stu-id="cf28e-112">Unlike the WHERE clause in SQL, the WHERE clause of an MDX SELECT statement never directly filters what is returned on the Rows axis of a query.</span></span> <span data-ttu-id="cf28e-113">Для фильтрации данных, отображаемых по оси строк или столбцов запроса, можно использовать различные функции MDX, например FILTER, NONEMPTY и TOPCOUNT.</span><span class="sxs-lookup"><span data-stu-id="cf28e-113">To filter what appears on the Rows or Columns axis of a query, you can use a variety of MDX functions, for example FILTER, NONEMPTY and TOPCOUNT.</span></span>  
  
### <a name="implicit-slicer-axis"></a><span data-ttu-id="cf28e-114">Неявная ось среза</span><span class="sxs-lookup"><span data-stu-id="cf28e-114">Implicit Slicer Axis</span></span>  
 <span data-ttu-id="cf28e-115">Если элемент иерархии в кубе не включен явно в ось запроса, элемент по умолчанию этой иерархии неявно включается в ось среза.</span><span class="sxs-lookup"><span data-stu-id="cf28e-115">If a member from a hierarchy within the cube is not explicitly included in a query axis, the default member from that hierarchy is implicitly included in the slicer axis.</span></span> <span data-ttu-id="cf28e-116">Дополнительные сведения об элементах по умолчанию см. в разделе [Определение элемента по умолчанию](../attribute-properties-define-a-default-member.md).</span><span class="sxs-lookup"><span data-stu-id="cf28e-116">For more information about default members, see [Define a Default Member](../attribute-properties-define-a-default-member.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cf28e-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="cf28e-117">Examples</span></span>  
 <span data-ttu-id="cf28e-118">Следующий запрос не содержит предложения WHERE и возвращает значение меры Internet Sales Amount для всех календарных лет:</span><span class="sxs-lookup"><span data-stu-id="cf28e-118">The following query does not include a WHERE clause, and returns the value of the Internet Sales Amount measure for all Calendar Years:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="cf28e-119">Добавление предложения WHERE, которое выполняется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cf28e-119">Adding a WHERE clause, as follows:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Country].&[United States])  
  
```  
  
 <span data-ttu-id="cf28e-120">не изменяет возвращаемые результаты запроса по оси строк или столбцов, а изменяет значения, возвращаемые для каждой ячейки.</span><span class="sxs-lookup"><span data-stu-id="cf28e-120">does not change what is returned on Rows or Columns in the query; it changes the values returned for each cell.</span></span> <span data-ttu-id="cf28e-121">В этом примере запрос отсекается таким образом, чтобы результаты содержали значение меры Internet Sales Amount для всех календарных лет только для клиентов, проживающих в США. К предложению WHERE можно добавить различные элементы из разных иерархий.</span><span class="sxs-lookup"><span data-stu-id="cf28e-121">In this example, the query is sliced so that it returns the value of Internet Sales Amount for all Calendar Years but only for Customers who live in the United States.Multiple members from different hierarchies can be added to the WHERE clause.</span></span> <span data-ttu-id="cf28e-122">В следующем запросе отображается значение Internet Sales Amount для всех календарных лет для клиентов, проживающих в США, которые приобрели продукты категории Bikes:</span><span class="sxs-lookup"><span data-stu-id="cf28e-122">The following query shows the value of Internet Sales Amount for all Calendar Years for Customers who live in the United States and who bought Products in the Category Bikes:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Country].&[United States], [Product].[Category].&[1])  
```  
  
 <span data-ttu-id="cf28e-123">При включении нескольких элементов из одной иерархии необходимо включить набор в предложение WHERE.</span><span class="sxs-lookup"><span data-stu-id="cf28e-123">If you want to use multiple members from the same hierarchy, you need to include a set in the WHERE clause.</span></span> <span data-ttu-id="cf28e-124">Например, в следующем запросе отображается значение Internet Sales Amount для всех календарных лет для клиентов, которые приобрели продукты категории Bikes и проживают в США или Великобритании:</span><span class="sxs-lookup"><span data-stu-id="cf28e-124">For example, the following query shows the value of Internet Sales Amount for all Calendar Years for Customers who bought Products in the Category Bikes and live in either the United States or the United Kingdom:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE(  
{[Customer].[Customer Geography].[Country].&[United States]  
, [Customer].[Customer Geography].[Country].&[United Kingdom]}  
, [Product].[Category].&[1])  
  
```  
  
 <span data-ttu-id="cf28e-125">Как упоминалось выше, при использовании набора в предложении WHERE значения для всех элементов набора будут агрегированы.</span><span class="sxs-lookup"><span data-stu-id="cf28e-125">As mentioned above, using a set in the WHERE clause will implicitly aggregate values for all members in the set.</span></span> <span data-ttu-id="cf28e-126">В этом случае в каждой ячейке запроса будут показаны агрегированные значения для США и Великобритании.</span><span class="sxs-lookup"><span data-stu-id="cf28e-126">In this case, the query shows aggregated values for the United States and the United Kingdom in each cell.</span></span>  
  
  
