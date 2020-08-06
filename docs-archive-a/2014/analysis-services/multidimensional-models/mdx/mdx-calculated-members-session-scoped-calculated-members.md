---
title: Создание вычисляемых элементов с областью действия сеанса (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- CREATE MEMBER statement
- session-scoped calculated members [MDX]
ms.assetid: 2875ed89-2c26-4645-8ed9-8848479d110f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8fe7a9f137d8b74eaa5bad104dbfdb471dd14588
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666835"
---
# <a name="creating-session-scoped-calculated-members-mdx"></a><span data-ttu-id="ec720-102">Создание вычисляемых элементов с областью действия сеанса (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="ec720-102">Creating Session-Scoped Calculated Members (MDX)</span></span>
  <span data-ttu-id="ec720-103">Для создания вычисляемых элементов, доступных в сеансе многомерных выражений, используется инструкция [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) .</span><span class="sxs-lookup"><span data-stu-id="ec720-103">To create a calculated member that is available throughout a Multidimensional Expressions (MDX) session, you use the [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) statement.</span></span> <span data-ttu-id="ec720-104">Вычисляемый элемент, созданный с помощью инструкции CREATE MEMBER, удаляется только при закрытии сеанса многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="ec720-104">A calculated member that is created by using the CREATE MEMBER statement will not be removed until after the MDX session closes.</span></span>  
  
 <span data-ttu-id="ec720-105">Как показано в этом разделе, синтаксис инструкции CREATE MEMBER достаточно прост.</span><span class="sxs-lookup"><span data-stu-id="ec720-105">As discussed in this topic, the syntax of the CREATE MEMBER statement is straightforward and easy to use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec720-106">Дополнительные сведения о создании вычисляемых элементов см. в разделе [Создание вычисляемых элементов в многомерных выражениях (многомерные выражения)](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="ec720-106">For more information about calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="create-member-syntax"></a><span data-ttu-id="ec720-107">Синтаксис инструкции CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="ec720-107">CREATE MEMBER Syntax</span></span>  
 <span data-ttu-id="ec720-108">Чтобы включить инструкцию CREATE MEMBER в инструкцию многомерных выражений, используйте следующее синтаксическое выражение:</span><span class="sxs-lookup"><span data-stu-id="ec720-108">Use the following syntax to add the CREATE MEMBER statement to the MDX statement:</span></span>  
  
```  
CREATE [SESSION] MEMBER [<cube-name>.]<fully-qualified-member-name> AS <expression> [,<property-definition-list>]  
<cube name> ::= CURRENTCUBE | <Cube Name>  
<property-definition-list> ::= <property-definition>  
  | <property-definition>, <property-definition-list>  
<property-definition> ::= <property-identifier> = <property-value>  
<property-identifier> ::= VISIBLE | SOLVEORDER | SOLVE_ORDER | FORMAT_STRING | NON_EMPTY_BEHAVIOR <ole db member properties>  
```  
  
 <span data-ttu-id="ec720-109">В инструкции CREATE MEMBER аргумент `fully-qualified-member-name` — это полное имя вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="ec720-109">In the syntax for the CREATE MEMBER statement, the `fully-qualified-member-name` value is the fully qualified name of the calculated member.</span></span> <span data-ttu-id="ec720-110">Полное имя включает в себя измерение или уровень, с которым связан вычисляемый элемент.</span><span class="sxs-lookup"><span data-stu-id="ec720-110">The fully qualified name includes the dimension or level to which the calculated member is associated.</span></span> <span data-ttu-id="ec720-111">Аргумент `expression` возвращает значение вычисляемого элемента после определения значения выражения.</span><span class="sxs-lookup"><span data-stu-id="ec720-111">The `expression` value returns the value of the calculated member after the expression value has been evaluated,.</span></span>  
  
## <a name="create-member-example"></a><span data-ttu-id="ec720-112">Пример инструкции CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="ec720-112">CREATE MEMBER Example</span></span>  
 <span data-ttu-id="ec720-113">В следующем примере вычисляемый элемент `LastFourStores` создается с помощью инструкции CREATE MEMBER.</span><span class="sxs-lookup"><span data-stu-id="ec720-113">The following example uses the CREATE MEMBER statement to create the `LastFourStores` calculated member.</span></span> <span data-ttu-id="ec720-114">Этот вычисляемый элемент возвращает количество товара, проданного четырьмя последними магазинами. Он доступен в течение всего сеанса куба.</span><span class="sxs-lookup"><span data-stu-id="ec720-114">This calculated member returns the sum of units sold for the last four stores, and will be available throughout the whole session of the cube.</span></span>  
  
```  
Create Session Member [Store].[Measures].LastFourStores as   
sum(([Stores].[ByLocation].Lag(3) :  
[Stores].[ByLocation].NextMember), [Measures].[Units Sold])  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec720-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="ec720-115">See Also</span></span>  
 [<span data-ttu-id="ec720-116">Создание вычисляемых элементов с областью действия запроса (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="ec720-116">Creating Query-Scoped Calculated Members &#40;MDX&#41;</span></span>](mdx-calculated-members-query-scoped-calculated-members.md)  
  
  
