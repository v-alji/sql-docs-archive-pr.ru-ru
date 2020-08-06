---
title: Создание вложенных кубов в многомерных выражениях (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], subcubes
- subcubes [MDX]
- filtered views [MDX]
- MDX [Analysis Services], subcubes
- Multidimensional Expressions [Analysis Services], subcubes
- CREATE SUBCUBE statement
ms.assetid: 5403a62b-99ac-4d83-b02a-89bf78bf0f46
author: minewiskan
ms.author: owend
ms.openlocfilehash: 653b4d30aa86f52179c7b13619ac4347aa65c339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665634"
---
# <a name="building-subcubes-in-mdx-mdx"></a><span data-ttu-id="2f374-102">Построение вложенных кубов в многомерных выражениях (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="2f374-102">Building Subcubes in MDX (MDX)</span></span>
  <span data-ttu-id="2f374-103">Вложенный куб — это подмножество куба, полученное на основании отфильтрованного представления базовых данных.</span><span class="sxs-lookup"><span data-stu-id="2f374-103">A subcube is a subset of a cube on representing a filtered view of the underlying data.</span></span> <span data-ttu-id="2f374-104">Ограничивая куб до вложенного куба, можно повысить производительность запросов.</span><span class="sxs-lookup"><span data-stu-id="2f374-104">By limiting the cube to a subcube, you can improve query performance.</span></span>  
  
 <span data-ttu-id="2f374-105">Для определения вложенного куба предназначена инструкция [CREATE SUBCUBE](/sql/mdx/mdx-data-definition-create-subcube) , описанная в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="2f374-105">To define a subcube, you use the [CREATE SUBCUBE](/sql/mdx/mdx-data-definition-create-subcube) statement, as described in this topic.</span></span>  
  
## <a name="create-subcube-syntax"></a><span data-ttu-id="2f374-106">Синтаксис инструкции CREATE SUBCUBE</span><span class="sxs-lookup"><span data-stu-id="2f374-106">CREATE SUBCUBE Syntax</span></span>  
 <span data-ttu-id="2f374-107">Чтобы создать вложенный куб, используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="2f374-107">Use the following syntax to create a subcube:</span></span>  
  
```  
CREATE SUBCUBE Subcube_Identifier AS Subcube_Expression  
```  
  
 <span data-ttu-id="2f374-108">Синтаксис инструкции CREATE SUBCUBE очень прост.</span><span class="sxs-lookup"><span data-stu-id="2f374-108">The CREATE SUBCUBE syntax is fairly simple.</span></span> <span data-ttu-id="2f374-109">Аргумент *Subcube_Identifier* указывает куб, из которого создается данный вложенный куб.</span><span class="sxs-lookup"><span data-stu-id="2f374-109">The *Subcube_Identifier* parameter identifies the cube on which the subcube will be based.</span></span> <span data-ttu-id="2f374-110">Аргумент *Subcube_Expression* определяет часть куба, которая станет вложенным кубом.</span><span class="sxs-lookup"><span data-stu-id="2f374-110">The *Subcube_Expression* parameter selects the part of the cube that will become the subcube</span></span>  
  
 <span data-ttu-id="2f374-111">После создания вложенного куба он становится контекстом для всех запросов многомерных выражений либо до закрытия сеанса, либо до выполнения инструкции [DROP SUBCUBE](/sql/mdx/mdx-data-definition-drop-subcube) .</span><span class="sxs-lookup"><span data-stu-id="2f374-111">After you create a subcube, that subcube becomes the context for all MDX queries until either the session closes or you run the [DROP SUBCUBE](/sql/mdx/mdx-data-definition-drop-subcube) statement.</span></span>  
  
### <a name="what-a-subcube-contains"></a><span data-ttu-id="2f374-112">Содержимое вложенного куба</span><span class="sxs-lookup"><span data-stu-id="2f374-112">What a Subcube Contains</span></span>  
 <span data-ttu-id="2f374-113">Хотя инструкция CREATE SUBCUBE довольно проста в использовании, она не указывает явно все элементы, которые войдут во вложенный куб.</span><span class="sxs-lookup"><span data-stu-id="2f374-113">Although the CREATE SUBCUBE statement is fairly simple to use, the statement itself does not explicitly show all the members that become part of a subcube.</span></span> <span data-ttu-id="2f374-114">При определении вложенного куба применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="2f374-114">In defining a subcube, the following rules apply:</span></span>  
  
-   <span data-ttu-id="2f374-115">При включении во вложенный куб элемента иерархии `(All)` туда включаются все элементы этой иерархии.</span><span class="sxs-lookup"><span data-stu-id="2f374-115">If you include the `(All)` member of a hierarchy, you include every member of that hierarchy.</span></span>  
  
-   <span data-ttu-id="2f374-116">При включении во вложенный куб какого-либо элемента туда включаются все его предки и потомки.</span><span class="sxs-lookup"><span data-stu-id="2f374-116">If you include any member, you include that member's ascendants and descendants.</span></span>  
  
-   <span data-ttu-id="2f374-117">При включении во вложенный куб всех элементов какого-либо уровня туда включаются все элементы из данной иерархии.</span><span class="sxs-lookup"><span data-stu-id="2f374-117">If you include every member from a level, you include all members from the hierarchy.</span></span> <span data-ttu-id="2f374-118">Элементы других иерархий не включаются во вложенный куб, если они не существуют с элементами данного уровня (например, в случае несбалансированной иерархии — города, в котором нет клиентов).</span><span class="sxs-lookup"><span data-stu-id="2f374-118">Members from other hierarchies will be excluded if those members do not exist with members from the level (for example, an unbalanced hierarchy such as a city that does not contain customers).</span></span>  
  
-   <span data-ttu-id="2f374-119">Вложенный куб всегда содержит все элементы `(All)` из данного куба.</span><span class="sxs-lookup"><span data-stu-id="2f374-119">A subcube will always contain every `(All)` member from the cube.</span></span>  
  
 <span data-ttu-id="2f374-120">Кроме того, во вложенном кубе визуально подсчитываются статистические значения.</span><span class="sxs-lookup"><span data-stu-id="2f374-120">Additionally, aggregate values within the subcube are visually totaled.</span></span> <span data-ttu-id="2f374-121">Пусть вложенный куб содержит значения `USA`, `WA`и `OR`.</span><span class="sxs-lookup"><span data-stu-id="2f374-121">For example, a subcube contains `USA`, `WA`, and `OR`.</span></span> <span data-ttu-id="2f374-122">Статистическое значение для параметра `USA` будет суммой `{WA,OR}` , поскольку `WA` и `OR` — единственные штаты, определенные во вложенном кубе.</span><span class="sxs-lookup"><span data-stu-id="2f374-122">The aggregate value for `USA` will be the sum of `{WA,OR}` because `WA` and `OR` are the only states defined by the subcube.</span></span> <span data-ttu-id="2f374-123">Все прочие штаты будут проигнорированы.</span><span class="sxs-lookup"><span data-stu-id="2f374-123">All other states will be ignored.</span></span>  
  
 <span data-ttu-id="2f374-124">Кроме того, явные ссылки на ячейки вне вложенного куба возвращают значения ячеек, вычисленные в контексте всего куба.</span><span class="sxs-lookup"><span data-stu-id="2f374-124">Also, explicit references to cells outside the subcube return cell values that are evaluated in the context of the whole cube.</span></span> <span data-ttu-id="2f374-125">Пусть создан вложенный куб, ограниченный текущим годом.</span><span class="sxs-lookup"><span data-stu-id="2f374-125">For example, you create a subcube that is limited to the current year.</span></span> <span data-ttu-id="2f374-126">После этого можно при помощи функции [ParallelPeriod](/sql/mdx/parallelperiod-mdx) сравнить текущий год с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="2f374-126">You then use the [ParallelPeriod](/sql/mdx/parallelperiod-mdx) function to compare the current year to the previous year.</span></span> <span data-ttu-id="2f374-127">Разница в значениях будет возвращена, даже если значение предыдущего года находится за пределами вложенного куба.</span><span class="sxs-lookup"><span data-stu-id="2f374-127">The difference in values will be returned even though the previous year's value lies outside the subcube.</span></span>  
  
 <span data-ttu-id="2f374-128">Наконец, если оригинальный контекст не заменяется, функции наборов, значения которых рассчитаны в подзапросе выборки, вычисляются в контексте этого подзапроса.</span><span class="sxs-lookup"><span data-stu-id="2f374-128">Finally, if the original context is not overwritten, set functions evaluated in a subselect are evaluated in the context of the subselect.</span></span> <span data-ttu-id="2f374-129">Если контекст заменяется, функции наборов вычисляются в контексте всего куба.</span><span class="sxs-lookup"><span data-stu-id="2f374-129">If the context is overwritten, set functions are evaluated in the context of the whole cube.</span></span>  
  
## <a name="create-subcube-example"></a><span data-ttu-id="2f374-130">Пример инструкции CREATE SUBCUBE</span><span class="sxs-lookup"><span data-stu-id="2f374-130">CREATE SUBCUBE Example</span></span>  
 <span data-ttu-id="2f374-131">В следующем примере создается вложенный куб, ограничивающий куб «Бюджет» счетами 4200 и 4300.</span><span class="sxs-lookup"><span data-stu-id="2f374-131">The following example creates a subcube that restricts the Budget cube to only accounts 4200 and 4300:</span></span>  
  
 `CREATE SUBCUBE Budget AS SELECT {[Account].[Account].&[4200], [Account].[Account].&[4300] } ON 0 FROM Budget`  
  
 <span data-ttu-id="2f374-132">После создания вложенного куба для сеанса, все последующие запросы будут выполняться для этого вложенного куба, а не для всего куба.</span><span class="sxs-lookup"><span data-stu-id="2f374-132">Having created a subcube for the session, any subsequent queries will be against the subcube, not the whole cube.</span></span> <span data-ttu-id="2f374-133">Например, при выполнении следующего запроса</span><span class="sxs-lookup"><span data-stu-id="2f374-133">For example, you run the following query.</span></span> <span data-ttu-id="2f374-134">будут возвращены только элементы счетов 4200 и 4300.</span><span class="sxs-lookup"><span data-stu-id="2f374-134">This query will only return members from accounts 4200 and 4300.</span></span>  
  
 `SELECT [Account].[Account].Members ON 0, Measures.Members ON 1 FROM Budget`  
  
## <a name="see-also"></a><span data-ttu-id="2f374-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="2f374-135">See Also</span></span>  
 <span data-ttu-id="2f374-136">[Определение контекста куба в запросе &#40;многомерных выражений&#41;](establishing-cube-context-in-a-query-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="2f374-136">[Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span></span>  
 [<span data-ttu-id="2f374-137">Основные принципы запросов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="2f374-137">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
