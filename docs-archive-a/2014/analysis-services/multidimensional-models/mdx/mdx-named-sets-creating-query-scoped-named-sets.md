---
title: Создание именованных наборов с областью действия запроса (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- query-scoped named sets [MDX]
- WITH keyword
ms.assetid: 78bc1e9a-1bc4-4a5a-ab0b-cf430c8fbfe1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6eccb4e20fca03079a04a0219b07f6411b80a433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730958"
---
# <a name="creating-query-scoped-named-sets-mdx"></a><span data-ttu-id="56672-102">Создание именованных наборов с областью действия запроса (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="56672-102">Creating Query-Scoped Named Sets (MDX)</span></span>
  <span data-ttu-id="56672-103">Если именованный набор нужен только в одном запросе многомерных выражений, этот набор можно определить с помощью ключевого слова WITH.</span><span class="sxs-lookup"><span data-stu-id="56672-103">If a named set is only required for a single Multidimensional Expressions (MDX) query, you can define that named set by using the WITH keyword.</span></span> <span data-ttu-id="56672-104">Именованный набор, созданный с использованием ключевого слова WITH, уничтожается после выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="56672-104">A named set that is created by using the WITH keyword no longer exists after the query has finished running.</span></span>  
  
 <span data-ttu-id="56672-105">Как уже обсуждалось в этом разделе, ключевое слово WITH имеет достаточно гибкую функциональность и даже позволяет использовать функции для определения именованного набора.</span><span class="sxs-lookup"><span data-stu-id="56672-105">As discussed in this topic, the syntax of the WITH keyword is quite flexible, even accommodating the use of functions to define the named set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56672-106">Дополнительные сведения об именованных наборах см. в разделе [Построение именованных наборов в многомерных выражениях](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="56672-106">For more information about named sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
## <a name="with-keyword-syntax"></a><span data-ttu-id="56672-107">Синтаксис ключевого слова WITH</span><span class="sxs-lookup"><span data-stu-id="56672-107">WITH Keyword Syntax</span></span>  
 <span data-ttu-id="56672-108">Чтобы указать ключевое слово WITH в инструкции SELECT многомерного выражения, используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="56672-108">Use the following syntax to add the WITH keyword to a MDX SELECT statement:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ]   
SELECT [ * | ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]  
FROM <SELECT subcube clause>   
[ <SELECT slicer axis clause> ]  
[ <SELECT cell property list clause> ]  
  
<SELECT WITH clause> ::=  
   ( SET Set_Identifier AS 'Set_Expression')  
  
```  
  
 <span data-ttu-id="56672-109">В синтаксисе с ключевым словом WITH параметр `Set_Identifier` — это псевдоним именованного набора.</span><span class="sxs-lookup"><span data-stu-id="56672-109">In the syntax for the WITH keyword, the `Set_Identifier` parameter contains the alias for the named set.</span></span> <span data-ttu-id="56672-110">Параметр `Set_Expression` содержит выражение набора, на который ссылается псевдоним именованного набора.</span><span class="sxs-lookup"><span data-stu-id="56672-110">The `Set_Expression` parameter contains the set expression to which the named set alias refers.</span></span>  
  
## <a name="with-keyword-example"></a><span data-ttu-id="56672-111">Пример использования ключевого слова WITH</span><span class="sxs-lookup"><span data-stu-id="56672-111">WITH Keyword Example</span></span>  
 <span data-ttu-id="56672-112">В следующем запросе многомерных выражений извлекаются сведения о продажах вин Шардоне и Шабли из образца базы данных `FoodMart 2000` для служб Microsoft SQL Server 2000 Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="56672-112">The following MDX query examines the unit sales of the various Chardonnay and Chablis wines in `FoodMart 2000`, the sample database for Microsoft SQL Server 2000 Analysis Services.</span></span> <span data-ttu-id="56672-113">Этот запрос возвращает достаточно простой результирующий набор, однако является очень длинным и громоздким с точки зрения его обслуживания.</span><span class="sxs-lookup"><span data-stu-id="56672-113">This query, although fairly simple in terms of the result set, is lengthy and unwieldy when you have to maintenance such a query.</span></span>  
  
```  
SELECT  
   {[Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chablis Wine]} ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
```  
  
 <span data-ttu-id="56672-114">Чтобы упростить обслуживание предыдущего запроса многомерных выражений, с помощью ключевого слова WITH можно создать именованный набор.</span><span class="sxs-lookup"><span data-stu-id="56672-114">To make the previous MDX query easier to maintain, you can create a named set for the query by using the WITH keyword.</span></span> <span data-ttu-id="56672-115">В следующем примере показано, как создать именованный набор `[ChardonnayChablis]`при помощи ключевого слова WITH, делая инструкцию SELECT короче и проще.</span><span class="sxs-lookup"><span data-stu-id="56672-115">The following code shows how to use the WITH keyword to create a named set, `[ChardonnayChablis]`, and how the named set makes the SELECT statement shorter and easier to maintain.</span></span>  
  
```  
WITH SET [ChardonnayChablis] AS  
   {[Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chablis Wine]}  
  
SELECT  
   [ChardonnayChablis] ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
```  
  
### <a name="using-functions-together-with-the-with-keyword"></a><span data-ttu-id="56672-116">Использование функций с ключевым словом WITH</span><span class="sxs-lookup"><span data-stu-id="56672-116">Using Functions Together with the WITH Keyword</span></span>  
 <span data-ttu-id="56672-117">Хотя можно явно определять каждый элемент именованного набора, при таком подходе инструкция получается слишком длинной.</span><span class="sxs-lookup"><span data-stu-id="56672-117">Although you can explicitly define each member of a named set, this approach can produce a lengthy statement.</span></span> <span data-ttu-id="56672-118">Чтобы упростить создание и обслуживание именованного набора, для определения элементов используются функции многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="56672-118">To make the creation and maintenance of a named set easier, you can use MDX functions to define the members.</span></span>  
  
 <span data-ttu-id="56672-119">Например, в следующем запросе многомерных выражений для создания именованного набора [используются функции многомерных выражений](/sql/mdx/filter-mdx)Filter [,](/sql/mdx/current-mdx)CurrentMember [и](/sql/mdx/members-string-mdx) Name `[ChardonnayChablis]` и функция языка VBA InStr.</span><span class="sxs-lookup"><span data-stu-id="56672-119">For example, the following MDX query example uses the [Filter](/sql/mdx/filter-mdx), [CurrentMember](/sql/mdx/current-mdx), and [Name](/sql/mdx/members-string-mdx) MDX functions and the InStr VBA function to create the `[ChardonnayChablis]` named set.</span></span> <span data-ttu-id="56672-120">Эта версия именованного набора `[ChardonnayChablis]` идентична явно определенному набору, показанному ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="56672-120">This version of the `[ChardonnayChablis]` named set is the same as the explicitly defined version shown previously in this topic.</span></span>  
  
```  
WITH SET [ChardonnayChablis] AS  
   'Filter([Product].Members, (InStr(1, [Product].CurrentMember.Name, "chardonnay") <> 0) OR (InStr(1, [Product].CurrentMember.Name, "chablis") <> 0))'  
  
SELECT  
   [ChardonnayChablis] ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="56672-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="56672-121">See Also</span></span>  
 <span data-ttu-id="56672-122">[Инструкция SELECT &#40;&#41;многомерных выражений](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="56672-122">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 [<span data-ttu-id="56672-123">Создание именованных наборов с областью действия сеанса (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="56672-123">Creating Session-Scoped Named Sets &#40;MDX&#41;</span></span>](mdx-named-sets-creating-session-scoped-named-sets.md)  
  
  
