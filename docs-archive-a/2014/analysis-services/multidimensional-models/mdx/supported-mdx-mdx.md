---
title: Поддерживаемые многомерные выражения (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], statements
- MDX [Analysis Services], functions
ms.assetid: 308bc0b3-4fd6-4435-972b-5e40d9e3c99b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17e8df6a2aa6da6b88a07a2abdef99d6ea03d8eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737028"
---
# <a name="supported-mdx-mdx"></a><span data-ttu-id="77450-102">Поддержка многомерных выражений (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-102">Supported MDX (MDX)</span></span>
  <span data-ttu-id="77450-103">В скриптах многомерных выражений поддерживаются следующие инструкции и функции:</span><span class="sxs-lookup"><span data-stu-id="77450-103">The following statements and functions are supported within Multidimensional Expressions (MDX) Script:</span></span>  
  
 [<span data-ttu-id="77450-104">(Комментарий) (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-104">&#40;Comment&#41; &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="77450-105">-- (Комментарий) (MDX)</span><span class="sxs-lookup"><span data-stu-id="77450-105">-- &#40;Comment&#41; &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="77450-106">Комментарий (MDX)</span><span class="sxs-lookup"><span data-stu-id="77450-106">Comment &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="77450-107">Инструкция ALTER CUBE (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-107">ALTER CUBE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-alter-cube)  
  
> [!NOTE]  
>  <span data-ttu-id="77450-108">В сценариях многомерных выражений поддерживается только изменение элемента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77450-108">Only altering the default member is supported in MDX Scripting.</span></span>  
  
 [<span data-ttu-id="77450-109">Инструкция CALCULATE (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-109">CALCULATE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-calculate)  
  
 [<span data-ttu-id="77450-110">Инструкция CASE (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-110">CASE Statement &#40;MDX&#41;</span></span>](/sql/mdx/case-statement-mdx)  
  
 [<span data-ttu-id="77450-111">Инструкция CREATE CELL CALCULATION (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-111">CREATE CELL CALCULATION Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-cell-calculation)  
  
 [<span data-ttu-id="77450-112">Инструкция CREATE MEMBER (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-112">CREATE MEMBER Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-member)  
  
 [<span data-ttu-id="77450-113">Инструкция CREATE SET (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-113">CREATE SET Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-set)  
  
 [<span data-ttu-id="77450-114">Ключевое слово EXISTING (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-114">EXISTING Keyword &#40;MDX&#41;</span></span>](mdx-query-existing-keyword.md)  
  
 [<span data-ttu-id="77450-115">Инструкция FREEZE (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-115">FREEZE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-freeze)  
  
 [<span data-ttu-id="77450-116">Инструкция IF (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-116">IF Statement  &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-if)  
  
 [<span data-ttu-id="77450-117">Это (многомерное выражение)</span><span class="sxs-lookup"><span data-stu-id="77450-117">This &#40;MDX&#41;</span></span>](/sql/mdx/this-mdx)  
  
> [!NOTE]  
>  <span data-ttu-id="77450-118">В многомерных выражениях поддерживается присваивание значений следующим свойствам ячеек: `BACK_COLOR`, `FORE_COLOR`, `FORMAT_STRING`, `FONT_FLAGS`, `FONT_NAME` и `FONT_SIZE`.</span><span class="sxs-lookup"><span data-stu-id="77450-118">MDX supports assignment to the following cell properties: `BACK_COLOR`, `FORE_COLOR`, `FORMAT_STRING`, `FONT_FLAGS`, `FONT_NAME`, and `FONT_SIZE`.</span></span> <span data-ttu-id="77450-119">Дополнительные сведения см. в разделе [Использование свойств ячеек (многомерные выражения)](mdx-cell-properties-using-cell-properties.md).</span><span class="sxs-lookup"><span data-stu-id="77450-119">For more information, see [Using Cell Properties &#40;MDX&#41;](mdx-cell-properties-using-cell-properties.md).</span></span> <span data-ttu-id="77450-120">Многомерные выражения также поддерживают присваивание `NON_EMPTY_BEHAVIOR` свойству инструкции [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) .</span><span class="sxs-lookup"><span data-stu-id="77450-120">MDX also supports assignment to the `NON_EMPTY_BEHAVIOR` property of the [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) statement.</span></span>  
  
 [<span data-ttu-id="77450-121">Инструкция SCOPE (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-121">SCOPE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-scope)  
  
## <a name="see-also"></a><span data-ttu-id="77450-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="77450-122">See Also</span></span>  
 [<span data-ttu-id="77450-123">Базовый скрипт многомерных выражений (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="77450-123">The Basic MDX Script &#40;MDX&#41;</span></span>](the-basic-mdx-script-mdx.md)  
  
  
