---
title: LOG (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- base-10 logarithms
- LOG function
ms.assetid: f7fccace-c178-4e13-bde9-7dc4ef1d98fa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0de84c1a92f94507bcc69c47cc4d9b6cda50a4f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666178"
---
# <a name="log-ssis-expression"></a><span data-ttu-id="08019-102">LOG (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="08019-102">LOG (SSIS Expression)</span></span>
  <span data-ttu-id="08019-103">Возвращает десятичный логарифм числового выражения.</span><span class="sxs-lookup"><span data-stu-id="08019-103">Returns the base-10 logarithm of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08019-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08019-104">Syntax</span></span>  
  
```  
  
LOG(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="08019-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="08019-105">Arguments</span></span>  
 <span data-ttu-id="08019-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="08019-106">*numeric_expression*</span></span>  
 <span data-ttu-id="08019-107">Допустимое ненулевое и неотрицательное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="08019-107">Is a valid nonzero or nonnegative numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="08019-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="08019-108">Result Types</span></span>  
 <span data-ttu-id="08019-109">DT_R8</span><span class="sxs-lookup"><span data-stu-id="08019-109">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08019-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="08019-110">Remarks</span></span>  
 <span data-ttu-id="08019-111">Перед вычислением логарифма аргумент *numeric_expression* приводится к типу DT_R8.</span><span class="sxs-lookup"><span data-stu-id="08019-111">The *numeric expression* is cast to the DT_R8 data type before the logarithm is computed.</span></span> <span data-ttu-id="08019-112">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="08019-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="08019-113">Если вычисленное значение *numeric_expression* является нулем или отрицательным значением, возвращается результат NULL.</span><span class="sxs-lookup"><span data-stu-id="08019-113">If *numeric_expression* evaluates to zero or a negative value, the return result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="08019-114">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="08019-114">Expression Examples</span></span>  
 <span data-ttu-id="08019-115">В этом примере используется числовой литерал.</span><span class="sxs-lookup"><span data-stu-id="08019-115">This example uses a numeric literal.</span></span> <span data-ttu-id="08019-116">Функция возвращает значение 1,988291341907488.</span><span class="sxs-lookup"><span data-stu-id="08019-116">The function returns the value 1.988291341907488.</span></span>  
  
```  
LOG(97.34)  
```  
  
 <span data-ttu-id="08019-117">Этот пример использует столбец **Length**.</span><span class="sxs-lookup"><span data-stu-id="08019-117">This example uses the column **Length**.</span></span> <span data-ttu-id="08019-118">Если значением столбца является 101,24, функция возвращает 2,005352136486217.</span><span class="sxs-lookup"><span data-stu-id="08019-118">If the column is 101.24, the function returns 2.005352136486217.</span></span>  
  
```  
LOG(Length)   
```  
  
 <span data-ttu-id="08019-119">Этот пример использует переменную **Length**.</span><span class="sxs-lookup"><span data-stu-id="08019-119">This example uses the variable **Length**.</span></span> <span data-ttu-id="08019-120">Тип данных переменной должен быть numeric либо выражение должно включать явное приведение к типу данных [!INCLUDE[ssIS](../../includes/ssis-md.md)] numeric.</span><span class="sxs-lookup"><span data-stu-id="08019-120">The variable must have a numeric data type or the expression must include an explicit cast to a numeric [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type.</span></span> <span data-ttu-id="08019-121">При параметре **Length** равном 234,567 функция возвращает 2,370266913465859.</span><span class="sxs-lookup"><span data-stu-id="08019-121">If **Length** is 234.567, the function returns 2.370266913465859.</span></span>  
  
```  
LOG(@Length)   
```  
  
## <a name="see-also"></a><span data-ttu-id="08019-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="08019-122">See Also</span></span>  
 <span data-ttu-id="08019-123">[EXP (выражение служб SSIS)](exp-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="08019-123">[EXP &#40;SSIS Expression&#41;](exp-ssis-expression.md) </span></span>  
 <span data-ttu-id="08019-124">[LN (выражение служб SSIS)](ln-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="08019-124">[LN &#40;SSIS Expression&#41;](ln-ssis-expression.md) </span></span>  
 [<span data-ttu-id="08019-125">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="08019-125">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
