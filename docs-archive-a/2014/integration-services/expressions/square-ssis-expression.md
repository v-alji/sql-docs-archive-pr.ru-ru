---
title: SQUARE (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQUARE
- square values
ms.assetid: cecf1bb2-3d55-40a6-9688-ed67bcc150b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 09955e708aae707a88aa7821d2a72651a3a44d59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732789"
---
# <a name="square-ssis-expression"></a><span data-ttu-id="c518b-102">SQUARE (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="c518b-102">SQUARE (SSIS Expression)</span></span>
  <span data-ttu-id="c518b-103">Возвращает квадрат числового выражения.</span><span class="sxs-lookup"><span data-stu-id="c518b-103">Returns the square of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c518b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c518b-104">Syntax</span></span>  
  
```  
  
SQUARE(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c518b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c518b-105">Arguments</span></span>  
 <span data-ttu-id="c518b-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="c518b-106">*numeric_expression*</span></span>  
 <span data-ttu-id="c518b-107">Числовое выражение любого типа числовых данных.</span><span class="sxs-lookup"><span data-stu-id="c518b-107">Is a numeric expression of any numeric data type.</span></span> <span data-ttu-id="c518b-108">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c518b-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c518b-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="c518b-109">Result Types</span></span>  
 <span data-ttu-id="c518b-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="c518b-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c518b-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="c518b-111">Remarks</span></span>  
 <span data-ttu-id="c518b-112">Функция SQUARE возвращает значение NULL, если аргумент принимает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c518b-112">SQUARE returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="c518b-113">Перед операцией возведения в квадрат аргумент приводится к типу данных DT_R8.</span><span class="sxs-lookup"><span data-stu-id="c518b-113">The argument is cast to the DT_R8 data type before the square operation.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c518b-114">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="c518b-114">Expression Examples</span></span>  
 <span data-ttu-id="c518b-115">Этот пример возвращает квадрат числа 12.</span><span class="sxs-lookup"><span data-stu-id="c518b-115">This example returns the square of 12.</span></span> <span data-ttu-id="c518b-116">Возвращается результат 144.</span><span class="sxs-lookup"><span data-stu-id="c518b-116">The return result is 144.</span></span>  
  
```  
SQUARE(12)  
```  
  
 <span data-ttu-id="c518b-117">Этот пример возвращает квадрат результата вычитания значений в двух столбцах.</span><span class="sxs-lookup"><span data-stu-id="c518b-117">This example returns the square of the result of subtracting values in two columns.</span></span> <span data-ttu-id="c518b-118">Если **Value1** содержит число 12, а **Value2** содержит число 4, функция SQUARE возвращает 64.</span><span class="sxs-lookup"><span data-stu-id="c518b-118">If **Value1** contains 12 and **Value2** contains 4, the SQUARE function returns 64.</span></span>  
  
```  
SQUARE(Value1 - Value2)  
```  
  
 <span data-ttu-id="c518b-119">Этот пример возвращает длину третьей стороны прямоугольного треугольника путем применения функции SQUARE к двум переменным, а затем вычисления квадратного корня из суммы получившихся значений.</span><span class="sxs-lookup"><span data-stu-id="c518b-119">This example returns the length of the third side of a right angle triangle by applying the SQUARE function to two variables and then calculating the square root of their sum.</span></span> <span data-ttu-id="c518b-120">Если **Side1** содержит 3, а **Side2** содержит 4, функция SQRT возвращает 5.</span><span class="sxs-lookup"><span data-stu-id="c518b-120">If **Side1** contains 3 and **Side2** contains 4, the SQRT function returns 5.</span></span>  
  
```  
SQRT(SQUARE(@Side1) + SQUARE(@Side2))  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c518b-121">В выражениях имена переменных всегда содержат префикс \@.</span><span class="sxs-lookup"><span data-stu-id="c518b-121">In expressions, variable names always include the \@ prefix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c518b-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="c518b-122">See Also</span></span>  
 [<span data-ttu-id="c518b-123">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="c518b-123">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
