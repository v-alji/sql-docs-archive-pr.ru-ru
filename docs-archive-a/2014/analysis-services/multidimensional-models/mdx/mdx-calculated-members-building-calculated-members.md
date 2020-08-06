---
title: Создание вычисляемых элементов в многомерных выражениях (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], calculated members
- calculated members [MDX]
- Multidimensional Expressions [Analysis Services], calculated members
- queries [MDX], calculated members
ms.assetid: 9322e8b8-43e1-4e02-a7d1-e41a586a5bb8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30dc6562ec394065cf2f177608d4e5679cbd7df3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658448"
---
# <a name="building-calculated-members-in-mdx-mdx"></a><span data-ttu-id="bd912-102">Создание вычисляемых элементов в многомерных выражениях (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="bd912-102">Building Calculated Members in MDX (MDX)</span></span>
  <span data-ttu-id="bd912-103">В многомерных выражениях вычисляемым называется элемент, разрешаемый путем вычисления многомерного выражения, возвращающего значение.</span><span class="sxs-lookup"><span data-stu-id="bd912-103">In Multidimensional Expressions (MDX), a calculated member is a member that is resolved by calculating an MDX expression to return a value.</span></span> <span data-ttu-id="bd912-104">В этом определении кроется огромный потенциал.</span><span class="sxs-lookup"><span data-stu-id="bd912-104">This innocuous definition covers an incredible amount of ground.</span></span> <span data-ttu-id="bd912-105">Возможность создания и использования вычисляемых элементов в многомерных запросах дает широкие возможности для манипулирования данными.</span><span class="sxs-lookup"><span data-stu-id="bd912-105">The ability to construct and use calculated members in an MDX query provides a great deal of manipulation capability for multidimensional data.</span></span>  
  
 <span data-ttu-id="bd912-106">Вычисляемый элемент можно создать в любом месте иерархии.</span><span class="sxs-lookup"><span data-stu-id="bd912-106">You can create calculated members at any point within a hierarchy.</span></span> <span data-ttu-id="bd912-107">Кроме того, вычисляемые элементы могут зависеть не только от существующих элементов куба, но и от других вычисляемых элементов, определенных в том же многомерном выражении.</span><span class="sxs-lookup"><span data-stu-id="bd912-107">You can also create calculated members that depend not only on existing members in a cube, but also on other calculated members defined in the same MDX expression.</span></span>  
  
 <span data-ttu-id="bd912-108">При определении вычисляемого элемента для него можно задать один из следующих контекстов.</span><span class="sxs-lookup"><span data-stu-id="bd912-108">You can define a calculated member to have one of the following contexts:</span></span>  
  
-   <span data-ttu-id="bd912-109">**Область запроса.** Для создания вычисляемого элемента, определяемого как часть многомерного запроса, область которого, следовательно, ограничена этим запросом, применяется ключевое слово WITH.</span><span class="sxs-lookup"><span data-stu-id="bd912-109">**Query-scoped** To create a calculated member that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="bd912-110">После создания вычисляемый элемент можно использовать в инструкции многомерных выражений SELECT.</span><span class="sxs-lookup"><span data-stu-id="bd912-110">You can then use the calculated member within an MDX SELECT statement.</span></span> <span data-ttu-id="bd912-111">Этот подход позволяет изменять вычисляемый элемент, созданный при помощи ключевого слова WITH, не изменяя инструкцию SELECT.</span><span class="sxs-lookup"><span data-stu-id="bd912-111">Using this approach, the calculated member created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="bd912-112">Дополнительные сведения о создании вычисляемых элементов с помощью ключевого слова WITH см. в разделе [Создание вычисляемых элементов с областью действия запроса (многомерные выражения)](mdx-calculated-members-query-scoped-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="bd912-112">For more information about how to use the WITH keyword to create calculated members, see [Creating Query-Scoped Calculated Members &#40;MDX&#41;](mdx-calculated-members-query-scoped-calculated-members.md).</span></span>  
  
-   <span data-ttu-id="bd912-113">**Область сеанса.** Для создания вычисляемого элемента, область которого шире контекста запроса и распространяется на весь сеанс многомерных выражений, применяется инструкция CREATE MEMBER.</span><span class="sxs-lookup"><span data-stu-id="bd912-113">**Session-scoped** To create a calculated member whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use the CREATE MEMBER statement.</span></span> <span data-ttu-id="bd912-114">Вычисляемый элемент, определенный при помощи инструкции CREATE MEMBER, доступен для всех многомерных запросов текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="bd912-114">A calculated member defined by using the CREATE MEMBER statement is available to all MDX queries in that session.</span></span> <span data-ttu-id="bd912-115">Например, инструкцию CREATE MEMBER имеет смысл использовать в клиентском приложении, которое постоянно использует один и тот же набор в различных запросах.</span><span class="sxs-lookup"><span data-stu-id="bd912-115">The CREATE MEMBER statement makes sense, for example, in a client application that consistently reuses the same set in a variety of queries.</span></span>  
  
     <span data-ttu-id="bd912-116">Дополнительные сведения о создании вычисляемых элементов в сеансе с помощью инструкции CREATE MEMBER см. в разделе [Создание вычисляемых элементов с областью действия сеанса (многомерные выражения)](mdx-calculated-members-session-scoped-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="bd912-116">For more information about how to use the CREATE MEMBER statement to create calculated members in a session, see [Creating Session-Scoped Calculated Members &#40;MDX&#41;](mdx-calculated-members-session-scoped-calculated-members.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd912-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd912-117">See Also</span></span>  
 <span data-ttu-id="bd912-118">[Инструкция CREATE MEMBER &#40;&#41;многомерных выражений](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="bd912-118">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 <span data-ttu-id="bd912-119">[Ссылка на функцию многомерных выражений &#40;&#41;многомерных выражений](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="bd912-119">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 [<span data-ttu-id="bd912-120">Инструкция SELECT (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="bd912-120">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
