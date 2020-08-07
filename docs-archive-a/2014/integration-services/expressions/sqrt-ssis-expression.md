---
title: SQRT (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQRT function
- square root of given expression
ms.assetid: 54a75389-c501-4e22-87b8-905f66d6a3a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9efa3f8da2e5280692aa65a25610211aba2fa40f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732793"
---
# <a name="sqrt-ssis-expression"></a><span data-ttu-id="60f52-102">SQRT (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="60f52-102">SQRT (SSIS Expression)</span></span>
  <span data-ttu-id="60f52-103">Возвращает квадратный корень числового выражения.</span><span class="sxs-lookup"><span data-stu-id="60f52-103">Returns the square root of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60f52-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60f52-104">Syntax</span></span>  
  
```  
  
SQRT(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="60f52-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="60f52-105">Arguments</span></span>  
 <span data-ttu-id="60f52-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="60f52-106">*numeric_expression*</span></span>  
 <span data-ttu-id="60f52-107">Числовое выражение любого типа числовых данных.</span><span class="sxs-lookup"><span data-stu-id="60f52-107">Is a numeric expression of any numeric data type.</span></span> <span data-ttu-id="60f52-108">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="60f52-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="60f52-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="60f52-109">Result Types</span></span>  
 <span data-ttu-id="60f52-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="60f52-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60f52-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="60f52-111">Remarks</span></span>  
 <span data-ttu-id="60f52-112">Функция SQRT возвращает значение NULL, если аргумент равен NULL.</span><span class="sxs-lookup"><span data-stu-id="60f52-112">SQRT returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="60f52-113">Если аргумент имеет отрицательное значение, то функция SQRT завершается неудачей.</span><span class="sxs-lookup"><span data-stu-id="60f52-113">SQRT fails if the argument is a negative value.</span></span>  
  
 <span data-ttu-id="60f52-114">Перед вычислением квадратного корня аргумент приводится к типу данных DT_R8.</span><span class="sxs-lookup"><span data-stu-id="60f52-114">The argument is cast to the DT_R8 data type before the square root operation.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="60f52-115">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="60f52-115">Expression Examples</span></span>  
 <span data-ttu-id="60f52-116">В этом примере вычисляется квадратный корень из числа.</span><span class="sxs-lookup"><span data-stu-id="60f52-116">This example returns the square root of a numeric literal.</span></span> <span data-ttu-id="60f52-117">Возвращается значение 12.</span><span class="sxs-lookup"><span data-stu-id="60f52-117">The return result is 12.</span></span>  
  
```  
SQRT(144)  
```  
  
 <span data-ttu-id="60f52-118">В этом примере вычисляется квадратный корень из выражения, которое составлено из разности значений в столбцах **Value1** и **Value2** .</span><span class="sxs-lookup"><span data-stu-id="60f52-118">This example returns the square root of an expression, the result of subtracting values in the **Value1** and **Value2** columns.</span></span>  
  
```  
SQRT(Value1 - Value2)  
```  
  
 <span data-ttu-id="60f52-119">В этом примере вычисляется гипотенуза прямоугольного треугольника путем вычисления квадратов двух переменных с помощью функции SQUARE и последующего вычисления квадратного корня их суммы.</span><span class="sxs-lookup"><span data-stu-id="60f52-119">This example returns the length of the third side of a right triangle by applying the SQUARE function to two variables and then calculating the square root of their sum.</span></span> <span data-ttu-id="60f52-120">Если **Side1** содержит 3, а **Side2** содержит 4, функция SQRT возвращает 5.</span><span class="sxs-lookup"><span data-stu-id="60f52-120">If **Side1** contains 3 and **Side2** contains 4, the SQRT function returns 5.</span></span>  
  
```  
SQRT(SQUARE(@Side1) + SQUARE(@Side2))  
```  
  
> [!NOTE]  
>  <span data-ttu-id="60f52-121">В выражениях имена переменных всегда содержат префикс \@.</span><span class="sxs-lookup"><span data-stu-id="60f52-121">In expressions, variable names always include the \@ prefix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f52-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="60f52-122">See Also</span></span>  
 [<span data-ttu-id="60f52-123">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="60f52-123">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
