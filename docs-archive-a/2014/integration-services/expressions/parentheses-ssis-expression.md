---
title: () (скобки) (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- () (parentheses operator)
- evaluation order [Integration Services]
- parentheses operator ()
ms.assetid: 931e10eb-1707-4121-b2f1-43565561119f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e390e10e485bd9cc22480300b6a9c33098bda8f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740157"
---
# <a name="-parentheses-ssis-expression"></a><span data-ttu-id="28777-102">() (скобки) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="28777-102">() (Parentheses) (SSIS Expression)</span></span>
  <span data-ttu-id="28777-103">Определяет порядок вычисления выражений.</span><span class="sxs-lookup"><span data-stu-id="28777-103">Identifies the evaluation order of expressions.</span></span> <span data-ttu-id="28777-104">Выражения, взятые в скобки, имеют самый высокий приоритет вычисления.</span><span class="sxs-lookup"><span data-stu-id="28777-104">Expressions enclosed in parentheses have the highest evaluation precedence.</span></span> <span data-ttu-id="28777-105">Вложенные выражения в скобках вычисляются от внутреннего к внешнему.</span><span class="sxs-lookup"><span data-stu-id="28777-105">Nested expressions enclosed in parentheses are evaluated in inner-to-outer order.</span></span>  
  
 <span data-ttu-id="28777-106">Кроме того, скобки применяются для того, чтобы облегчить чтение сложных выражений.</span><span class="sxs-lookup"><span data-stu-id="28777-106">Parentheses are also used to make complex expressions easier to understand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28777-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28777-107">Syntax</span></span>  
  
```  
  
(expression)  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="28777-108">Аргументы</span><span class="sxs-lookup"><span data-stu-id="28777-108">Arguments</span></span>  
 <span data-ttu-id="28777-109">*expression*</span><span class="sxs-lookup"><span data-stu-id="28777-109">*expression*</span></span>  
 <span data-ttu-id="28777-110">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="28777-110">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="28777-111">Типы результата</span><span class="sxs-lookup"><span data-stu-id="28777-111">Result Types</span></span>  
 <span data-ttu-id="28777-112">Тип данных *expression*.</span><span class="sxs-lookup"><span data-stu-id="28777-112">The data type of *expression*.</span></span> <span data-ttu-id="28777-113">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="28777-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="28777-114">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="28777-114">Expression Examples</span></span>  
 <span data-ttu-id="28777-115">В этом примере показано изменение приоритета операторов с помощью скобок.</span><span class="sxs-lookup"><span data-stu-id="28777-115">This example shows how the use of parenthesis modifies the precedence of operators.</span></span> <span data-ttu-id="28777-116">Значение для первого выражения — 100, для второго — 31.</span><span class="sxs-lookup"><span data-stu-id="28777-116">The first expression evaluates to 100, whereas the second one evaluates to 31.</span></span>  
  
```  
(5 + 5) * (4 + 6)  
5 + 5 * 4 + 6  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="28777-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="28777-117">See Also</span></span>  
 <span data-ttu-id="28777-118">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="28777-118">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="28777-119">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="28777-119">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
