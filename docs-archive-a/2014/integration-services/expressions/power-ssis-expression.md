---
title: POWER (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- POWER function
ms.assetid: db48ae65-bfa6-4db1-8d3c-d0d4f8a399bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e1f5742f482ae52620ec11d95b84cb3d06199fab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664999"
---
# <a name="power-ssis-expression"></a><span data-ttu-id="3ccf4-102">POWER (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="3ccf4-102">POWER (SSIS Expression)</span></span>
  <span data-ttu-id="3ccf4-103">Возвращает результат возведения числового выражения в степень.</span><span class="sxs-lookup"><span data-stu-id="3ccf4-103">Returns the result of raising a numeric expression to a power.</span></span> <span data-ttu-id="3ccf4-104">Показатель степени должен быть целым числом.</span><span class="sxs-lookup"><span data-stu-id="3ccf4-104">The power parameter must evaluate to an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ccf4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ccf4-105">Syntax</span></span>  
  
```  
  
POWER(numeric_expression,power)  
```  
  
## <a name="arguments"></a><span data-ttu-id="3ccf4-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3ccf4-106">Arguments</span></span>  
 <span data-ttu-id="3ccf4-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="3ccf4-107">*numeric_expression*</span></span>  
 <span data-ttu-id="3ccf4-108">Допустимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="3ccf4-108">Is a valid numeric expression.</span></span>  
  
 <span data-ttu-id="3ccf4-109">*power*</span><span class="sxs-lookup"><span data-stu-id="3ccf4-109">*power*</span></span>  
 <span data-ttu-id="3ccf4-110">Допустимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="3ccf4-110">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3ccf4-111">Типы результата</span><span class="sxs-lookup"><span data-stu-id="3ccf4-111">Result Types</span></span>  
 <span data-ttu-id="3ccf4-112">DT_R8</span><span class="sxs-lookup"><span data-stu-id="3ccf4-112">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ccf4-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="3ccf4-113">Remarks</span></span>  
 <span data-ttu-id="3ccf4-114">Перед выполнением операции возведения в степень аргументы *numeric_expression* и *power* приводятся к типу DT_R8.</span><span class="sxs-lookup"><span data-stu-id="3ccf4-114">The *numeric_expression* and *power* arguments are cast to the DT_R8 data type before the power is computed.</span></span> <span data-ttu-id="3ccf4-115">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="3ccf4-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="3ccf4-116">В случае если результатом *numeric_expression* является ноль, а *power* меньше ноля, средство оценки выражений возвращает ошибку, а выходному параметру присваивается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="3ccf4-116">If *numeric_expression* evaluates to zero and *power* is negative, the expression evaluator returns an error and sets the return result to null.</span></span>  
  
 <span data-ttu-id="3ccf4-117">В случае если результатом *numeric_expression* или *power* является неопределенное значение, выходному параметру присваивается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="3ccf4-117">If *numeric_expression* or *power* evaluate to indeterminate results, the return result is null.</span></span>  
  
 <span data-ttu-id="3ccf4-118">Аргумент *power* может быть дробным.</span><span class="sxs-lookup"><span data-stu-id="3ccf4-118">The *power* argument can be a fraction.</span></span> <span data-ttu-id="3ccf4-119">Например, показатель степени может иметь значение 0,5.</span><span class="sxs-lookup"><span data-stu-id="3ccf4-119">For example, you can use the value 0.5 as the power.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="3ccf4-120">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="3ccf4-120">Expression Examples</span></span>  
 <span data-ttu-id="3ccf4-121">В этом примере используется числовой литерал.</span><span class="sxs-lookup"><span data-stu-id="3ccf4-121">This example uses a numeric literal.</span></span> <span data-ttu-id="3ccf4-122">Функция возводит число 4 в степень 3 и возвращает 64.</span><span class="sxs-lookup"><span data-stu-id="3ccf4-122">The function raises 4 to the power of 3 and returns 64.</span></span>  
  
```  
POWER(4,3)  
```  
  
 <span data-ttu-id="3ccf4-123">Данный пример использует столбец со значением параметра **Length** и переменную **DimensionCount** .</span><span class="sxs-lookup"><span data-stu-id="3ccf4-123">This example uses the **Length** column and the **DimensionCount** variable.</span></span> <span data-ttu-id="3ccf4-124">Если параметр **Length** имеет значение 8, а параметр **DimensionCount** значение 2, функция возвращает 64.</span><span class="sxs-lookup"><span data-stu-id="3ccf4-124">If **Length** is 8, and **DimensionCount** is 2, the return result is 64.</span></span>  
  
```  
POWER(Length, @DimensionCount)   
```  
  
## <a name="see-also"></a><span data-ttu-id="3ccf4-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="3ccf4-125">See Also</span></span>  
 [<span data-ttu-id="3ccf4-126">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="3ccf4-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
