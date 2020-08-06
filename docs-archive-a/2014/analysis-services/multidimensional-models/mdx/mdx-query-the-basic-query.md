---
title: Базовый запрос многомерных выражений (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], SELECT statement
- queries [MDX], about queries
- cellsets [MDX]
- SELECT statement [MDX]
- cubes [Analysis Services], SELECT statement
ms.assetid: 4fa5a95a-fec9-4584-875c-dbf030c53e82
author: minewiskan
ms.author: owend
ms.openlocfilehash: b6b1a70753abe8e477bd1e522a37f4513cc12a52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666832"
---
# <a name="the-basic-mdx-query-mdx"></a><span data-ttu-id="43282-102">Базовый запрос многомерных выражений (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="43282-102">The Basic MDX Query (MDX)</span></span>
  <span data-ttu-id="43282-103">Базовый запрос многомерных выражений (MDX) — это наиболее часто используемый запрос в МНОГОМЕРных выражениях.</span><span class="sxs-lookup"><span data-stu-id="43282-103">The basic Multidimensional Expressions (MDX) query is the SELECT statement-the most frequently used query in MDX.</span></span> <span data-ttu-id="43282-104">Чтобы получить основательные знания о применении многомерных выражений для запроса многомерных данных, необходимо понять, как в инструкции многомерных выражений SELECT определяется результирующий набор, синтаксис инструкции SELECT и как с ее помощью создавать простые запросы.</span><span class="sxs-lookup"><span data-stu-id="43282-104">By understanding how an MDX SELECT statement must specify a result set, what the syntax of the SELECT statement is, and how to create a simple query using the SELECT statement, you will have a solid understanding of how to use MDX to query multidimensional data.</span></span>  
  
## <a name="specifying-a-result-set"></a><span data-ttu-id="43282-105">Указание результирующего набора</span><span class="sxs-lookup"><span data-stu-id="43282-105">Specifying a Result Set</span></span>  
 <span data-ttu-id="43282-106">В многомерном выражении инструкция SELECT указывает результирующий набор, содержащий подмножество многомерных данных, возвращаемое из куба.</span><span class="sxs-lookup"><span data-stu-id="43282-106">In MDX, the SELECT statement specifies a result set that contains a subset of multidimensional data that has been returned from a cube.</span></span> <span data-ttu-id="43282-107">Чтобы указать результирующий набор, запрос многомерных выражений должен содержать следующие данные.</span><span class="sxs-lookup"><span data-stu-id="43282-107">To specify a result set, an MDX query must contain the following information:</span></span>  
  
-   <span data-ttu-id="43282-108">Число осей, которое должно содержаться в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="43282-108">The number of axes that you want the result set to contain.</span></span> <span data-ttu-id="43282-109">В многомерном запросе можно указать до 128 осей.</span><span class="sxs-lookup"><span data-stu-id="43282-109">You can specify up to 128 axes in an MDX query.</span></span>  
  
-   <span data-ttu-id="43282-110">Набор элементов или кортежей, включаемых в каждую ось многомерного запроса.</span><span class="sxs-lookup"><span data-stu-id="43282-110">The set of members or tuples to include on each axis of the MDX query.</span></span>  
  
-   <span data-ttu-id="43282-111">Имя куба, задающего контекст многомерного запроса.</span><span class="sxs-lookup"><span data-stu-id="43282-111">The name of the cube that sets the context of the MDX query.</span></span>  
  
-   <span data-ttu-id="43282-112">Набор элементов или кортежей, включаемых в ось среза.</span><span class="sxs-lookup"><span data-stu-id="43282-112">The set of members or tuples to include on the slicer axis.</span></span> <span data-ttu-id="43282-113">Дополнительные сведения об осях среза и запроса см. в разделе [Ограничение запроса с помощью осей запроса и среза (многомерные выражения)](mdx-query-and-slicer-axes-restricting-the-query.md).</span><span class="sxs-lookup"><span data-stu-id="43282-113">For more information about slicer and query axes, see[Restricting the Query with Query and Slicer Axes &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md).</span></span>  
  
 <span data-ttu-id="43282-114">Для указания осей запроса куба, к которому направлен запрос, и осей среза в инструкции многомерных выражений SELECT используются следующие предложения.</span><span class="sxs-lookup"><span data-stu-id="43282-114">To identify the query axes, the cube that will be queried, and the slicer axis, the MDX SELECT statement uses the following clauses:</span></span>  
  
-   <span data-ttu-id="43282-115">Предложение SELECT, определяющее оси запроса в инструкции многомерных выражений SELECT.</span><span class="sxs-lookup"><span data-stu-id="43282-115">A SELECT clause that determines the query axes of an MDX SELECT statement.</span></span> <span data-ttu-id="43282-116">Дополнительные сведения о построении осей запроса в предложении SELECT см. в разделе [Определение содержимого оси запроса (многомерные выражения)](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="43282-116">For more information about the construction of query axes in a SELECT clause, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
-   <span data-ttu-id="43282-117">Предложение FROM, определяющее, к какому кубу будет направлен запрос.</span><span class="sxs-lookup"><span data-stu-id="43282-117">A FROM clause that determines which cube will be queried.</span></span> <span data-ttu-id="43282-118">Дополнительные сведения о предложении FROM см. в разделе [Инструкция SELECT (многомерные выражения)](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="43282-118">For more information about the FROM clause, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
-   <span data-ttu-id="43282-119">Необязательное предложение WHERE, определяющее, какие элементы или кортежи используются на оси среза для ограничения возвращаемых данных.</span><span class="sxs-lookup"><span data-stu-id="43282-119">An optional WHERE clause that determines which members or tuples to use on the slicer axis to restrict the data returned.</span></span> <span data-ttu-id="43282-120">Дополнительные сведения о построении осей среза в предложении WHERE см. в разделе [Определение содержимого оси среза (многомерные выражения)](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="43282-120">For more information about the construction of a slicer axis in a WHERE clause, see [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43282-121">Дополнительные сведения о различных предложениях инструкции SELECT см. в разделе [Инструкция SELECT (многомерные выражения)](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="43282-121">For more detailed information about the various clauses of the SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
## <a name="select-statement-syntax"></a><span data-ttu-id="43282-122">Синтаксис инструкции SELECT</span><span class="sxs-lookup"><span data-stu-id="43282-122">SELECT Statement Syntax</span></span>  
 <span data-ttu-id="43282-123">В следующей конструкции иллюстрируется синтаксис базовой инструкции SELECT с использованием предложений SELECT, FROM и WHERE:</span><span class="sxs-lookup"><span data-stu-id="43282-123">The following syntax shows a basic SELECT statement that includes the use of the SELECT, FROM, and WHERE clauses:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ]   
SELECT [ * | ( <SELECT query axis clause>   
    [ , <SELECT query axis clause> ... ] ) ]  
FROM <SELECT subcube clause>   
[ <SELECT slicer axis clause> ]  
[ <SELECT cell property list clause> ]  
```  
  
 <span data-ttu-id="43282-124">Инструкция многомерных выражений SELECT поддерживает дополнительный синтаксис, например: ключевое слово WITH, использование функций многомерных выражений для создания вычисляемых элементов, включаемых в ось запроса или среза, а также возможность возвращать значения свойств определенных ячеек как части запроса.</span><span class="sxs-lookup"><span data-stu-id="43282-124">The MDX SELECT statement supports optional syntax, such as the WITH keyword, the use of MDX functions to create calculated members for inclusion in an axis or slicer axis, and the ability to return the values of specific cell properties as part of the query.</span></span> <span data-ttu-id="43282-125">Дополнительные сведения об инструкции SELECT многомерных выражений см. в разделе [Инструкция SELECT (многомерные выражения)](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="43282-125">For more information about the MDX SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
### <a name="comparing-the-syntax-of-the-mdx-select-statement-to-sql"></a><span data-ttu-id="43282-126">Сравнение синтаксиса инструкции многомерных выражений SELECT с синтаксисом SQL</span><span class="sxs-lookup"><span data-stu-id="43282-126">Comparing the Syntax of the MDX SELECT Statement to SQL</span></span>  
 <span data-ttu-id="43282-127">Формат синтаксиса для инструкции многомерных выражений SELECT сходен с синтаксисом ее аналога в SQL.</span><span class="sxs-lookup"><span data-stu-id="43282-127">The syntax format for the MDX SELECT statement is similar to that of SQL syntax.</span></span> <span data-ttu-id="43282-128">Тем не менее есть несколько серьезных отличий.</span><span class="sxs-lookup"><span data-stu-id="43282-128">However, there are several fundamental differences:</span></span>  
  
-   <span data-ttu-id="43282-129">Синтаксис многомерных выражений различает наборы, окружающие кортежи или элементы с фигурными скобками (символами {и}). Дополнительные сведения о синтаксисе элементов, кортежей и наборов см. в разделе [Работа с элементами, кортежами и наборами &#40;&#41;многомерных выражений ](working-with-members-tuples-and-sets-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="43282-129">MDX syntax distinguishes sets by surrounding tuples or members with braces (the { and } characters.) For more information about member, tuple, and set syntax, see [Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span></span>  
  
-   <span data-ttu-id="43282-130">Запросы многомерных выражений могут содержать 0, 1,2 или до 128 осей запросов в инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="43282-130">MDX queries can have 0, 1, 2 or up to 128 query axes in the SELECT statement.</span></span> <span data-ttu-id="43282-131">Поведение всех осей одинаково, в отличие от SQL, где имеются значительные различия в поведении строк и столбцов в запросе.</span><span class="sxs-lookup"><span data-stu-id="43282-131">Each axis behaves in exactly the same way, unlike SQL where there are significant differences between how the rows and the columns of a query behave.</span></span>  
  
-   <span data-ttu-id="43282-132">Как и в SQL-запросе, предложение FROM указывает источник данных для запроса многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="43282-132">As with an SQL query, the FROM clause names the source of the data for the MDX query.</span></span> <span data-ttu-id="43282-133">Однако предложение многомерных выражений FROM ограничивается одним кубом.</span><span class="sxs-lookup"><span data-stu-id="43282-133">However, the MDX FROM clause is restricted to a single cube.</span></span> <span data-ttu-id="43282-134">Сведения из других кубов могут быть получены по значению с помощью функции LookupCube.</span><span class="sxs-lookup"><span data-stu-id="43282-134">Information from other cubes can be retrieved on a value-by-value basis by using the LookupCube function.</span></span>  
  
-   <span data-ttu-id="43282-135">Предложение WHERE определяет ось среза в многомерном запросе.</span><span class="sxs-lookup"><span data-stu-id="43282-135">The WHERE clause describes the slicer axis in an MDX query.</span></span> <span data-ttu-id="43282-136">Оно действует наподобие невидимой дополнительной оси в запросе, создавая срезы значений в ячейках результирующего набора, в то время как в SQL предложение WHERE не влияет напрямую на ось строк в запросе.</span><span class="sxs-lookup"><span data-stu-id="43282-136">It acts as something like an invisible, extra axis in the query, slicing the values that appear in the cells in the result set; unlike the SQL WHERE clause it does not directly affect what appears on the rows axis of the query.</span></span> <span data-ttu-id="43282-137">Функциональные возможности предложения SQL WHERE доступны через другие функции многомерных выражений, такие как функция FILTER.</span><span class="sxs-lookup"><span data-stu-id="43282-137">The functionality of the SQL WHERE clause is available through other MDX functions such as the FILTER function.</span></span>  
  
## <a name="select-statement-example"></a><span data-ttu-id="43282-138">Пример инструкции SELECT</span><span class="sxs-lookup"><span data-stu-id="43282-138">SELECT Statement Example</span></span>  
 <span data-ttu-id="43282-139">В следующем примере показан базовый запрос многомерных выражений на основе инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="43282-139">The following example shows a basic MDX query that uses the SELECT statement.</span></span> <span data-ttu-id="43282-140">Этот запрос возвращает результирующий набор, содержащий продажи за 2002 и 2003 годы и сумму налогов для юго-западных областей продаж.</span><span class="sxs-lookup"><span data-stu-id="43282-140">This query returns a result set that contains the 2002 and 2003 sales and tax amounts for the Southwest sales territories.</span></span>  
  
```  
SELECT  
    { [Measures].[Sales Amount],   
        [Measures].[Tax Amount] } ON COLUMNS,  
    { [Date].[Fiscal].[Fiscal Year].&[2002],   
        [Date].[Fiscal].[Fiscal Year].&[2003] } ON ROWS  
FROM [Adventure Works]  
WHERE ( [Sales Territory].[Southwest] )  
```  
  
 <span data-ttu-id="43282-141">В этом примере запрос содержит следующие сведения о результирующем наборе:</span><span class="sxs-lookup"><span data-stu-id="43282-141">In this example, the query defines the following result set information:</span></span>  
  
-   <span data-ttu-id="43282-142">Предложение SELECT задает оси запроса как элементы Sales Amount и Tax Amount в измерении Measures и как элементы 2002 и 2003 в измерении Date.</span><span class="sxs-lookup"><span data-stu-id="43282-142">The SELECT clause sets the query axes as the Sales Amount and Tax Amount members of the Measures dimension, and the 2002 and 2003 members of the Date dimension.</span></span>  
  
-   <span data-ttu-id="43282-143">Предложение FROM указывает, что источником данных является куб Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="43282-143">The FROM clause indicates that the data source is the Adventure Works cube.</span></span>  
  
-   <span data-ttu-id="43282-144">Предложение WHERE определяет ось среза как элемент Southwest измерения Sales Territory.</span><span class="sxs-lookup"><span data-stu-id="43282-144">The WHERE clause defines the slicer axis as the Southwest member of the Sales Territory dimension.</span></span>  
  
 <span data-ttu-id="43282-145">Обратите внимание, что в запросе используются псевдонимы осей COLUMNS и ROWS.</span><span class="sxs-lookup"><span data-stu-id="43282-145">Notice that the query example also uses the COLUMNS and ROWS axis aliases.</span></span> <span data-ttu-id="43282-146">Можно было бы обращаться к этим осям по их порядковым номерам.</span><span class="sxs-lookup"><span data-stu-id="43282-146">The ordinal positions for these axes could also have been used.</span></span> <span data-ttu-id="43282-147">В следующем примере иллюстрируется запрос многомерных выражений с использованием порядковых номеров осей:</span><span class="sxs-lookup"><span data-stu-id="43282-147">The following example shows how the MDX query could have been written to use the ordinal position of each axis:</span></span>  
  
```  
SELECT  
    { [Measures].[Sales Amount],   
        [Measures].[Tax Amount] } ON 0,  
    { [Date].[Fiscal].[Fiscal Year].&[2002],   
        [Date].[Fiscal].[Fiscal Year].&[2003] } ON 1  
FROM [Adventure Works]  
WHERE ( [Sales Territory].[Southwest] )  
```  
  
 <span data-ttu-id="43282-148">Дополнительные примеры см. в разделах [Определение содержимого оси запроса (многомерные выражения)](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) и [Определение содержимого оси среза (многомерные выражения)](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="43282-148">For more detailed examples, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md)and [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43282-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="43282-149">See Also</span></span>  
 <span data-ttu-id="43282-150">[Основные понятия в Analysis Services &#40;многомерных выражений&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="43282-150">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 [<span data-ttu-id="43282-151">Инструкция SELECT (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="43282-151">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
