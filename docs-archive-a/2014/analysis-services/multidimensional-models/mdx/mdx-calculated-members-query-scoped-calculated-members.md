---
title: Создание вычисляемых элементов с областью действия запроса (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- WITH keyword
- query-scoped calculated members [MDX]
ms.assetid: c4507149-e67b-4e5d-9192-cc911acd9adc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c0b3e7184f3cc6abd189344bbce1b6e1f948ebb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658452"
---
# <a name="creating-query-scoped-calculated-members-mdx"></a><span data-ttu-id="8fe3a-102">Создание вычисляемых элементов с областью действия запроса (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="8fe3a-102">Creating Query-Scoped Calculated Members (MDX)</span></span>
  <span data-ttu-id="8fe3a-103">Если вычисляемый элемент используется только в одном многомерном запросе, его можно определить с помощью ключевого слова WITH.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-103">If a calculated member is only required for a single Multidimensional Expressions (MDX) query, you can define that calculated member by using the WITH keyword.</span></span> <span data-ttu-id="8fe3a-104">Вычисляемый элемент, созданный с помощью ключевого слова WITH, удаляется сразу после выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-104">A calculated member that is created by using the WITH keyword no longer exists after the query has finished running.</span></span>  
  
 <span data-ttu-id="8fe3a-105">Синтаксис ключевого слова WITH является достаточно гибким и позволяет создавать один вычисляемый элемент на основе другого.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-105">As discussed in this topic, the syntax of the WITH keyword is quite flexible, even allowing a calculated member to be based on another calculated member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8fe3a-106">Дополнительные сведения о создании вычисляемых элементов см. в разделе [Создание вычисляемых элементов в многомерных выражениях (многомерные выражения)](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="8fe3a-106">For more information about calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="with-keyword-syntax"></a><span data-ttu-id="8fe3a-107">Синтаксис ключевого слова WITH</span><span class="sxs-lookup"><span data-stu-id="8fe3a-107">WITH Keyword Syntax</span></span>  
 <span data-ttu-id="8fe3a-108">Для добавления ключевого слова WITH в инструкцию многомерных выражений SELECT используется следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-108">Use the following syntax to add the WITH keyword to an MDX SELECT statement:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ] SELECT [ * | ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]FROM <SELECT subcube clause> [ <SELECT slicer axis clause> ][ <SELECT cell property list clause> ]  
<SELECT WITH clause> ::=  
   ( [ CALCULATED ] MEMBER <CREATE MEMBER body clause>) | <CREATE MEMBER body clause> ::= Member_Identifier AS 'MDX_Expression'  
   [ <CREATE MEMBER property clause> [ , <CREATE MEMBER property clause> ... ] ]  
<CREATE MEMBER property clause> ::=  
   ( MemberProperty_Identifier = Scalar_Expression )  
  
```  
  
 <span data-ttu-id="8fe3a-109">В синтаксисе ключевого слова WITH аргумент `Member_Identifier` — это полное имя вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-109">In the syntax for the WITH keyword, the `Member_Identifier` value is the fully qualified name of the calculated member.</span></span> <span data-ttu-id="8fe3a-110">Полное имя включает в себя измерение или уровень, с которым связан вычисляемый элемент.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-110">This fully qualified name includes the dimension or level to which the calculated member is associated.</span></span> <span data-ttu-id="8fe3a-111">Аргумент `MDX_Expression` возвращает значение вычисляемого элемента после определения значения выражения.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-111">The `MDX_Expression` value returns the value of the calculated member after the expression value has been evaluated.</span></span> <span data-ttu-id="8fe3a-112">По желанию можно задать значения внутренних свойств ячейки для вычисляемого элемента, указав имя свойства ячейки в значении `MemberProperty_Identifier` , а значение свойства — в значении `Scalar_Expression` .</span><span class="sxs-lookup"><span data-stu-id="8fe3a-112">The values of intrinsic cell properties for a calculated member can be optionally specified by supplying the name of the cell property in the `MemberProperty_Identifier` value and the value of the cell property in the `Scalar_Expression` value.</span></span>  
  
## <a name="with-keyword-examples"></a><span data-ttu-id="8fe3a-113">Примеры использования ключевого слова WITH</span><span class="sxs-lookup"><span data-stu-id="8fe3a-113">WITH Keyword Examples</span></span>  
 <span data-ttu-id="8fe3a-114">В следующем многомерном запросе определяется вычисляемый элемент `[Measures].[Special Discount]`, который рассчитывает особую скидку, исходя из начальной суммы скидки.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-114">The following MDX query defines a calculated member, `[Measures].[Special Discount]`, calculating a special discount based on the original discount amount.</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Special Discount] AS  
   [Measures].[Discount Amount] * 1.5  
SELECT   
   [Measures].[Special Discount] on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
```  
  
 <span data-ttu-id="8fe3a-115">Вычисляемые элементы можно также создавать в любой точке иерархии.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-115">You can also create calculated members at any point within a hierarchy.</span></span> <span data-ttu-id="8fe3a-116">Например, в следующем многомерном запросе определяется вычисляемый элемент `[BigSeller]` для гипотетического куба продаж.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-116">For example, the following MDX query defines the `[BigSeller]` calculated member for a hypothetical Sales cube.</span></span> <span data-ttu-id="8fe3a-117">С помощью этого вычисляемого элемента выясняется, продал ли заданный магазин хотя бы 100,00 бутылок пива и вина.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-117">This calculated member determines whether a specified store has at least 100.00 in unit sales for beer and wine.</span></span> <span data-ttu-id="8fe3a-118">Однако в запросе вычисляемый элемент `[BigSeller]` создается не как потомок измерения `[Product]` , а как потомок элемента `[Beer and Wine]` .</span><span class="sxs-lookup"><span data-stu-id="8fe3a-118">However, the query creates the `[BigSeller]` calculated member not as a child member of the `[Product]` dimension, but instead as a child member of the `[Beer and Wine]` member.</span></span>  
  
```  
WITH   
   MEMBER [Product].[Beer and Wine].[BigSeller] AS  
  IIf([Product].[Beer and Wine] > 100, "Yes","No")  
SELECT  
   {[Product].[BigSeller]} ON COLUMNS,  
   Store.[Store Name].Members ON ROWS  
FROM Sales  
  
```  
  
 <span data-ttu-id="8fe3a-119">Вычисляемые элементы не обязательно должны зависеть только от существующих элементов куба.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-119">Calculated members do not have to depend only on existing members in a cube.</span></span> <span data-ttu-id="8fe3a-120">Вычисляемые элементы также могут создаваться на основе других вычисляемых элементов, определяемых в том же многомерном выражении.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-120">Calculated member can also be based on other calculated members defined in the same MDX expression.</span></span> <span data-ttu-id="8fe3a-121">Например, в следующем многомерном запросе значение, созданное в первом вычисляемом элементе `[Measures].[Special Discount]`, используется для формирования значения второго вычисляемого элемента `[Measures].[Special Discounted Amount]`.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-121">For example, the following MDX query uses the value created in the first calculated member, `[Measures].[Special Discount]`, to generate the value of the second calculated member, `[Measures].[Special Discounted Amount]`.</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Special Discount] AS  
   [Measures].[Discount Percentage] * 1.5,   
   FORMAT_STRING = 'Percent'  
  
   MEMBER [Measures].[Special Discounted Amount] AS  
   [Measures].[Reseller Average Unit Price] * [Measures].[Special Discount],   
   FORMAT_STRING = 'Currency'  
  
SELECT   
   {[Measures].[Special Discount], [Measures].[Special Discounted Amount]} on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="8fe3a-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="8fe3a-122">See Also</span></span>  
 <span data-ttu-id="8fe3a-123">[Ссылка на функцию многомерных выражений &#40;&#41;многомерных выражений](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="8fe3a-123">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 <span data-ttu-id="8fe3a-124">[Инструкция SELECT &#40;&#41;многомерных выражений](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="8fe3a-124">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 [<span data-ttu-id="8fe3a-125">Создание вычисляемых элементов с областью действия сеанса (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="8fe3a-125">Creating Session-Scoped Calculated Members &#40;MDX&#41;</span></span>](mdx-calculated-members-session-scoped-calculated-members.md)  
  
  
