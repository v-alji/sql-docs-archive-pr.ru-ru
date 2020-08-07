---
title: Создание именованных наборов в многомерных выражениях (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Multidimensional Expressions [Analysis Services], named sets
- named sets [MDX]
- sets [MDX]
- MDX [Analysis Services], named sets
- queries [MDX], named sets
- set expressions [MDX]
ms.assetid: 213b0035-e96d-4ba0-83f2-ded206905603
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91296f8c5d47afb15c67f0b60435c7f961734573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730973"
---
# <a name="building-named-sets-in-mdx-mdx"></a><span data-ttu-id="60f5e-102">Построение именованных наборов в многомерных выражениях</span><span class="sxs-lookup"><span data-stu-id="60f5e-102">Building Named Sets in MDX (MDX)</span></span>
  <span data-ttu-id="60f5e-103">Выражение набора может быть длинной и сложной декларацией, которую трудно проследить и понять.</span><span class="sxs-lookup"><span data-stu-id="60f5e-103">A set expression can be a lengthy and complex declaration, and therefore be difficult to follow or understand.</span></span> <span data-ttu-id="60f5e-104">Или выражение набора может использоваться настолько часто, что его повторное определение может стать утомительным.</span><span class="sxs-lookup"><span data-stu-id="60f5e-104">Or, a set expression may be used so frequently that repeatedly defining the set becomes burdensome.</span></span> <span data-ttu-id="60f5e-105">Чтобы облегчить работу с длинными, сложными или часто используемыми выражениями, в многомерных выражениях можно определить такое выражение, как *именованный набор*.</span><span class="sxs-lookup"><span data-stu-id="60f5e-105">To help make working with a lengthy, complex or commonly used expression easier, Multidimensional Expressions (MDX) lets you such an expression as a *named set*.</span></span>  
  
 <span data-ttu-id="60f5e-106">В сущности, именованный набор представляет собой выражение набора, которому назначен псевдоним.</span><span class="sxs-lookup"><span data-stu-id="60f5e-106">Basically, a named set is a set expression to which an alias has been assigned.</span></span> <span data-ttu-id="60f5e-107">В именованный набор могут входить любые элементы или функции, которые могут обычно включаться в набор.</span><span class="sxs-lookup"><span data-stu-id="60f5e-107">A named set can incorporate any members or functions that can ordinarily be incorporated into a set.</span></span> <span data-ttu-id="60f5e-108">Псевдоним набора рассматривается в многомерных выражениях как выражение набора, поэтому этот псевдоним может использоваться везде, где допустимы выражения набора.</span><span class="sxs-lookup"><span data-stu-id="60f5e-108">Because MDX treats the named set alias as a set expression, you can use that alias anywhere a set expression is accepted.</span></span>  
  
 <span data-ttu-id="60f5e-109">Именованный набор можно определить в одном из следующих контекстов:</span><span class="sxs-lookup"><span data-stu-id="60f5e-109">You can define a named set to have one of the following contexts:</span></span>  
  
-   <span data-ttu-id="60f5e-110">**Контекст запроса.** Чтобы создать именованный набор, который определен как часть запроса многомерных выражений, с областью, ограниченной этим запросом, используется ключевое слово WITH.</span><span class="sxs-lookup"><span data-stu-id="60f5e-110">**Query-scoped** To create a named set that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="60f5e-111">Затем именованный набор можно использовать внутри инструкции MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="60f5e-111">You can then use the named set within an MDX SELECT statement.</span></span> <span data-ttu-id="60f5e-112">При таком подходе именованный набор, созданный с использованием ключевого слова WITH, может быть изменен без изменений в инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="60f5e-112">Using this approach, the named set created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="60f5e-113">Дополнительные сведения об использовании ключевого слова WITH для создания именованных наборов см. в разделе [Создание именованных наборов с областью действия запроса (многомерные выражения)](mdx-named-sets-creating-query-scoped-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="60f5e-113">For more information about how to use the WITH keyword to create named sets, see [Creating Query-Scoped Named Sets &#40;MDX&#41;](mdx-named-sets-creating-query-scoped-named-sets.md).</span></span>  
  
-   <span data-ttu-id="60f5e-114">**Контекст сеанса.** Чтобы создать именованный набор, область которого шире контекста запроса, то есть набор, действующий в течение сеанса многомерных выражений, следует использовать инструкцию CREATE SET.</span><span class="sxs-lookup"><span data-stu-id="60f5e-114">**Session-scoped** To create a named set whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use the CREATE SET statement.</span></span> <span data-ttu-id="60f5e-115">Именованный набор, определенный с использованием инструкции CREATE SET, доступен для всех запросов многомерных выражений в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="60f5e-115">A named set defined by using the CREATE SET statement is available to all MDX queries in that session.</span></span> <span data-ttu-id="60f5e-116">Например, инструкция CREATE SET полезна в клиентском приложении, в котором набор многократно применяется в разнообразных запросах.</span><span class="sxs-lookup"><span data-stu-id="60f5e-116">The CREATE SET statement makes sense, for example, in a client application that consistently reuses a set in a variety of queries.</span></span>  
  
     <span data-ttu-id="60f5e-117">Дополнительные сведения об использовании инструкции CREATE SET для создания именованных наборов см. в разделе [Создание именованных наборов с областью действия сеанса (многомерные выражения)](mdx-named-sets-creating-session-scoped-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="60f5e-117">For more information about how to use the CREATE SET statement to create named sets in a session, see [Creating Session-Scoped Named Sets &#40;MDX&#41;](mdx-named-sets-creating-session-scoped-named-sets.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f5e-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="60f5e-118">See Also</span></span>  
 <span data-ttu-id="60f5e-119">[Инструкция SELECT &#40;&#41;многомерных выражений](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="60f5e-119">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 <span data-ttu-id="60f5e-120">[Инструкция CREATE SET &#40;многомерных выражениях&#41;](/sql/mdx/mdx-data-definition-create-set) </span><span class="sxs-lookup"><span data-stu-id="60f5e-120">[CREATE SET Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-set) </span></span>  
 [<span data-ttu-id="60f5e-121">Основные принципы запросов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="60f5e-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
