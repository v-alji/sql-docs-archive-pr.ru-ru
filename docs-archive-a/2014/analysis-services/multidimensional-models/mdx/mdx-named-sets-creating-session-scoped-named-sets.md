---
title: Создание именованных наборов с областью действия сеанса (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- CREATE SET statement
- session-scoped named sets [MDX]
ms.assetid: b751e1e4-6d4c-4d36-a28d-ffdaaee0f1c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: d35bd61dcc59eca8bcb920ed99f2e791631047c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734501"
---
# <a name="creating-session-scoped-named-sets-mdx"></a><span data-ttu-id="25fcb-102">Создание именованных наборов с областью действия сеанса (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="25fcb-102">Creating Session-Scoped Named Sets (MDX)</span></span>
  <span data-ttu-id="25fcb-103">Для создания именованного набора, доступного в сеансе многомерных выражений, используется инструкция [CREATE SET](/sql/mdx/mdx-data-definition-create-set) .</span><span class="sxs-lookup"><span data-stu-id="25fcb-103">To create a named set that is available throughout a Multidimensional Expressions (MDX) session, you use the [CREATE SET](/sql/mdx/mdx-data-definition-create-set) statement.</span></span> <span data-ttu-id="25fcb-104">Именованный набор, созданный с помощью инструкции CREATE SET, удаляется только при закрытии сеанса многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="25fcb-104">A named set that is created by using the CREATE SET statement will not be removed until after the MDX session closes.</span></span>  
  
 <span data-ttu-id="25fcb-105">Синтаксис ключевого слова WITH достаточно прост.</span><span class="sxs-lookup"><span data-stu-id="25fcb-105">As discussed in this topic, the syntax of the WITH keyword is straightforward and easy to use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25fcb-106">Дополнительные сведения об именованных наборах см. в разделе [Построение именованных наборов в многомерных выражениях](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="25fcb-106">For more information about named sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
## <a name="create-set-syntax"></a><span data-ttu-id="25fcb-107">Синтаксис инструкции CREATE SET</span><span class="sxs-lookup"><span data-stu-id="25fcb-107">CREATE SET Syntax</span></span>  
 <span data-ttu-id="25fcb-108">При обращении к инструкции CREATE SET используется следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="25fcb-108">Use the following syntax for the CREATE SET statement:</span></span>  
  
```  
CREATE SESSION SET [CURRENTCUBE. | <cube name>.]<Set Identifier> AS <Set Expression>  
```  
  
 <span data-ttu-id="25fcb-109">В синтаксисе инструкции CREATE SET параметр `cube name` представляет собой имя куба, содержащего элементы именованного набора.</span><span class="sxs-lookup"><span data-stu-id="25fcb-109">In the CREATE SET syntax, the `cube name` parameter contains the name of the cube that contains the members for the named set.</span></span> <span data-ttu-id="25fcb-110">Если параметр `cube name` не указан, то в качестве куба, содержащего элементы именованного набора, используется текущий куб.</span><span class="sxs-lookup"><span data-stu-id="25fcb-110">If the `cube name` parameter is not specified, the current cube will be used as the cube that contains the member for the named set.</span></span> <span data-ttu-id="25fcb-111">Кроме того, параметр `Set_Identifier` содержит псевдоним именованного набора, а параметр `Set_Expression` — выражение набора, на который будет ссылаться заданный псевдоним именованного набора.</span><span class="sxs-lookup"><span data-stu-id="25fcb-111">Also, the `Set_Identifier` parameter contains the alias for the named set, and the `Set_Expression` parameter contains the set expression to which the named set alias will refer.</span></span>  
  
## <a name="create-set-example"></a><span data-ttu-id="25fcb-112">Пример инструкции CREATE SET</span><span class="sxs-lookup"><span data-stu-id="25fcb-112">CREATE SET Example</span></span>  
 <span data-ttu-id="25fcb-113">В следующем примере иллюстрируется использование инструкции CREATE SET для создания именованного набора `SetCities_2_3` на основе куба Store.</span><span class="sxs-lookup"><span data-stu-id="25fcb-113">The following example uses the CREATE SET statement to create the `SetCities_2_3` named set based on the Store cube.</span></span> <span data-ttu-id="25fcb-114">Элементы именованного набора `SetCities_2_3` — это магазины в городе 2 и городе 3.</span><span class="sxs-lookup"><span data-stu-id="25fcb-114">The members of the `SetCities_2_3` named set are the stores within City 2 and City 3.</span></span>  
  
```  
create Session set [Store].[SetCities_2_3] as  
{[Data Stores].[ByLocation].[State].&[CA].&[City 02],  
[Data Stores].[ByLocation].[State].&[NH].&[City 03]}  
```  
  
 <span data-ttu-id="25fcb-115">При создании именованного набора `SetCities_2_3` с помощью инструкции CREATE SET он остается доступным в течение текущего сеанса многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="25fcb-115">By using the CREATE SET statement to define the `SetCities_2_3` named set, this named set remains available for the length of the current MDX session.</span></span> <span data-ttu-id="25fcb-116">Следующий пример — это допустимый запрос, возвращающий элементы городов 2 и 3. Его можно выполнять в любой момент после создания именованного набора `SetCities_2_3` до завершения сеанса.</span><span class="sxs-lookup"><span data-stu-id="25fcb-116">The following example is a valid query that would return City 2 and City 3 members, and that could be run anytime after you create the `SetCities_2_3` named set and before the session closes.</span></span>  
  
```  
select SetCities_2_3 on 0 from [Store]  
```  
  
## <a name="see-also"></a><span data-ttu-id="25fcb-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="25fcb-117">See Also</span></span>  
 [<span data-ttu-id="25fcb-118">Создание именованных наборов с областью действия запроса (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="25fcb-118">Creating Query-Scoped Named Sets &#40;MDX&#41;</span></span>](mdx-named-sets-creating-query-scoped-named-sets.md)  
  
  
