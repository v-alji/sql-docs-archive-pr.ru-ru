---
title: LN (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- LN function
- natural logarithm of expression [Integration Services]
ms.assetid: 55d7b657-b5fd-4753-9c81-54ed7575e720
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c06d6e246cfa51f8e84eb93ab7eb73eab40c392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666182"
---
# <a name="ln-ssis-expression"></a><span data-ttu-id="75421-102">LN (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="75421-102">LN (SSIS Expression)</span></span>
  <span data-ttu-id="75421-103">Возвращает натуральный логарифм числового выражения.</span><span class="sxs-lookup"><span data-stu-id="75421-103">Returns the natural logarithm of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75421-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75421-104">Syntax</span></span>  
  
```  
  
LN(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="75421-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="75421-105">Arguments</span></span>  
 <span data-ttu-id="75421-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="75421-106">*numeric_expression*</span></span>  
 <span data-ttu-id="75421-107">Допустимые положительные числовые выражения.</span><span class="sxs-lookup"><span data-stu-id="75421-107">Is a valid non-zero and non-negative numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="75421-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="75421-108">Result Types</span></span>  
 <span data-ttu-id="75421-109">DT_R8</span><span class="sxs-lookup"><span data-stu-id="75421-109">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75421-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="75421-110">Remarks</span></span>  
 <span data-ttu-id="75421-111">Перед вычислением логарифма аргумент numeric expression приводится к типу DT_R8.</span><span class="sxs-lookup"><span data-stu-id="75421-111">The numeric expression is cast to the DT_R8 data type before the logarithm is computed.</span></span> <span data-ttu-id="75421-112">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="75421-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="75421-113">Если вычисленное значение *numeric_expression* является нулем или отрицательным значением, возвращается результат NULL.</span><span class="sxs-lookup"><span data-stu-id="75421-113">If *numeric_expression* evaluates to zero or a negative value, the return result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="75421-114">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="75421-114">Expression Examples</span></span>  
 <span data-ttu-id="75421-115">В этом примере используется числовой литерал.</span><span class="sxs-lookup"><span data-stu-id="75421-115">This example uses a numeric literal.</span></span> <span data-ttu-id="75421-116">Функция возвращает значение 3,737766961828337.</span><span class="sxs-lookup"><span data-stu-id="75421-116">The function returns the value 3.737766961828337.</span></span>  
  
```  
LN(42)  
```  
  
 <span data-ttu-id="75421-117">Этот пример использует столбец **Length**.</span><span class="sxs-lookup"><span data-stu-id="75421-117">This example uses the column **Length**.</span></span> <span data-ttu-id="75421-118">Если значение столбца равно 53.99, функция возвращает значение 3.9887988442302.</span><span class="sxs-lookup"><span data-stu-id="75421-118">If the column value is 53.99, the function returns 3.9887988442302.</span></span>  
  
```  
LN(Length)   
```  
  
 <span data-ttu-id="75421-119">Этот пример использует переменную **Length**.</span><span class="sxs-lookup"><span data-stu-id="75421-119">This example uses the variable **Length**.</span></span> <span data-ttu-id="75421-120">Переменная должна иметь числовой тип данных, или выражение должно содержать явное приведение к числовому типу данных.</span><span class="sxs-lookup"><span data-stu-id="75421-120">The variable must have a numeric data type or the expression must include an explicit cast to a numeric data type.</span></span> <span data-ttu-id="75421-121">При параметре **Length** равном 234,567 функция возвращает 5,45774126708797.</span><span class="sxs-lookup"><span data-stu-id="75421-121">If **Length** is 234.567, the function returns 5.45774126708797.</span></span>  
  
```  
LN(@Length)   
```  
  
## <a name="see-also"></a><span data-ttu-id="75421-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="75421-122">See Also</span></span>  
 <span data-ttu-id="75421-123">[LOG (выражение служб SSIS)](log-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="75421-123">[LOG &#40;SSIS Expression&#41;](log-ssis-expression.md) </span></span>  
 [<span data-ttu-id="75421-124">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="75421-124">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
