---
title: Ключевое слово EXISTING (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- EXISTING
helpviewer_keywords:
- Existing keyword
ms.assetid: 651ee9ac-04ef-4316-87c9-a3df5ac27d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: 115444c832fe8fe9b258a0c23b97b97553f32e8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655399"
---
# <a name="existing-keyword-mdx"></a><span data-ttu-id="0ffe0-102">Ключевое слово EXISTING (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="0ffe0-102">EXISTING Keyword (MDX)</span></span>
  <span data-ttu-id="0ffe0-103">Указывает, что заданный набор должен вычисляться принудительно в текущем контексте.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-103">Forces a specified set to be evaluated within the current context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ffe0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ffe0-104">Syntax</span></span>  
  
```  
  
Existing Set_Expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="0ffe0-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0ffe0-105">Arguments</span></span>  
 <span data-ttu-id="0ffe0-106">*Set_Expression*</span><span class="sxs-lookup"><span data-stu-id="0ffe0-106">*Set_Expression*</span></span>  
 <span data-ttu-id="0ffe0-107">Допустимое многомерное выражение набора.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-107">A valid Multidimensional Expressions (MDX) set expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ffe0-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="0ffe0-108">Remarks</span></span>  
 <span data-ttu-id="0ffe0-109">По умолчанию наборы вычисляются в контексте куба, который содержит их элементы.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-109">By default, sets are evaluated within the context of the cube that contains the members of the set.</span></span> <span data-ttu-id="0ffe0-110">Ключевое слово `Existing` указывает на то, что заданный набор должен вычисляться в текущем контексте.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-110">The `Existing` keyword forces a specified set to be evaluated within the current context instead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ffe0-111">Пример</span><span class="sxs-lookup"><span data-stu-id="0ffe0-111">Example</span></span>  
 <span data-ttu-id="0ffe0-112">В следующем примере возвращается количество посредников, продажи которых снизились по сравнению с предыдущим периодом, на основании выбранных пользователем значений элемента State-Province, вычисленных с помощью функции `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-112">The following example returns the count of the resellers whose sales have declined over the previous time period, based on user-selected State-Province member values evaluated using the `Aggregate` function.</span></span> <span data-ttu-id="0ffe0-113">Ключевое слово [Hierarchize (многомерные выражения)](/sql/mdx/hierarchize-mdx) и [DrilldownLevel (многомерные выражения)](/sql/mdx/drilldownlevel-mdx) используются для возвращения показателей падения продаж для категорий продуктов в измерении Product.</span><span class="sxs-lookup"><span data-stu-id="0ffe0-113">The [Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) and [DrilldownLevel (MDX)](/sql/mdx/drilldownlevel-mdx) functions are used to return values for declining sales for product categories in the Product dimension.</span></span> <span data-ttu-id="0ffe0-114">`Existing`Ключевое слово заставляет набор в `Filter` функции вычисляться в текущем контексте, т. е. для элементов Вашингтон и Орегон иерархии атрибута «Штат-провинция».</span><span class="sxs-lookup"><span data-stu-id="0ffe0-114">The `Existing` keyword forces the set in the `Filter` function to be evaluated in the current context - that is, for the Washington and Oregon members of the State-Province attribute hierarchy.</span></span>  
  
```  
WITH MEMBER Measures.[Declining Reseller Sales] AS  
   Count  
      (Filter  
         (Existing  
            (Reseller.Reseller.Reseller)  
         , [Measures].[Reseller Sales Amount] <   
            ([Measures].[Reseller Sales Amount]  
               ,[Date].Calendar.PrevMember  
            )  
        )  
      )  
MEMBER [Geography].[State-Province].x AS   
   Aggregate   
      ( {[Geography].[State-Province].&[WA]&[US]  
         , [Geography].[State-Province].&[OR]&[US] }   
      )  
SELECT NON EMPTY HIERARCHIZE   
      (AddCalculatedMembers   
         (   
            {DrillDownLevel  
               ({[Product].[All Products]}  
               )  
            }   
         )   
      ) DIMENSION PROPERTIES PARENT_UNIQUE_NAME ON COLUMNS   
FROM [Adventure Works]  
WHERE   
      ( [Geography].[State-Province].x  
        , [Date].[Calendar].[Calendar Quarter].&[2003]&[4]  
        ,[Measures].[Declining Reseller Sales]  
      )  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ffe0-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="0ffe0-115">See Also</span></span>  
 <span data-ttu-id="0ffe0-116">[Count &#40;Set&#41; &#40;многомерных выражений&#41;](/sql/mdx/count-set-mdx) </span><span class="sxs-lookup"><span data-stu-id="0ffe0-116">[Count &#40;Set&#41; &#40;MDX&#41;](/sql/mdx/count-set-mdx) </span></span>  
 <span data-ttu-id="0ffe0-117">[AddCalculatedMembers &#40;&#41;многомерных выражений](/sql/mdx/addcalculatedmembers-mdx) </span><span class="sxs-lookup"><span data-stu-id="0ffe0-117">[AddCalculatedMembers &#40;MDX&#41;](/sql/mdx/addcalculatedmembers-mdx) </span></span>  
 <span data-ttu-id="0ffe0-118">[Статистическая обработка &#40;многомерных выражений&#41;](/sql/mdx/aggregate-mdx) </span><span class="sxs-lookup"><span data-stu-id="0ffe0-118">[Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) </span></span>  
 <span data-ttu-id="0ffe0-119">[Фильтрация &#40;&#41;многомерных выражений](/sql/mdx/filter-mdx) </span><span class="sxs-lookup"><span data-stu-id="0ffe0-119">[Filter &#40;MDX&#41;](/sql/mdx/filter-mdx) </span></span>  
 <span data-ttu-id="0ffe0-120">[Свойства &#40;&#41;многомерных выражений](/sql/mdx/properties-mdx) </span><span class="sxs-lookup"><span data-stu-id="0ffe0-120">[Properties &#40;MDX&#41;](/sql/mdx/properties-mdx) </span></span>  
 <span data-ttu-id="0ffe0-121">[DrilldownLevel &#40;&#41;многомерных выражений](/sql/mdx/drilldownlevel-mdx) </span><span class="sxs-lookup"><span data-stu-id="0ffe0-121">[DrilldownLevel &#40;MDX&#41;](/sql/mdx/drilldownlevel-mdx) </span></span>  
 <span data-ttu-id="0ffe0-122">[Hierarchize &#40;&#41;многомерных выражений](/sql/mdx/hierarchize-mdx) </span><span class="sxs-lookup"><span data-stu-id="0ffe0-122">[Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) </span></span>  
 [<span data-ttu-id="0ffe0-123">Справочник по функциям многомерных выражений (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="0ffe0-123">MDX Function Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-function-reference-mdx)  
  
  
