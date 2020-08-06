---
title: (Остаток от деления) (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '% (modulo operator)'
- remainder of division operation
- modulo operator (%)
ms.assetid: e2920821-2f5b-4c76-8db8-8b9eddf4606f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2e23152fca9c9f2c7c3ac11490a56b03d1a1f9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658913"
---
# <a name="modulo-ssis-expression"></a><span data-ttu-id="b802c-102">(Остаток от деления) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="b802c-102">(Modulo) (SSIS Expression)</span></span>
  <span data-ttu-id="b802c-103">Вычисляет целочисленный остаток после деления первого числового выражения на второе.</span><span class="sxs-lookup"><span data-stu-id="b802c-103">Provides the integer remainder after dividing the first numeric expression by the second one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b802c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b802c-104">Syntax</span></span>  
  
```  
  
dividend % divisor  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="b802c-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b802c-105">Arguments</span></span>  
 <span data-ttu-id="b802c-106">*dividend*</span><span class="sxs-lookup"><span data-stu-id="b802c-106">*dividend*</span></span>  
 <span data-ttu-id="b802c-107">Делимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="b802c-107">Is the numeric expression to divide.</span></span> <span data-ttu-id="b802c-108">*dividend* может быть любым допустимым числовым выражением.</span><span class="sxs-lookup"><span data-stu-id="b802c-108">*dividend* can be any valid numeric expression.</span></span> <span data-ttu-id="b802c-109">Дополнительные сведения см. в разделе [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="b802c-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md)</span></span>  
  
 <span data-ttu-id="b802c-110">*divisor*</span><span class="sxs-lookup"><span data-stu-id="b802c-110">*divisor*</span></span>  
 <span data-ttu-id="b802c-111">Числовое выражение, на которое делится делимое.</span><span class="sxs-lookup"><span data-stu-id="b802c-111">Is the numeric expression to divide the dividend by.</span></span> <span data-ttu-id="b802c-112">*divisor* может быть любым допустимым числовым выражением, отличным от нуля.</span><span class="sxs-lookup"><span data-stu-id="b802c-112">*divisor* can be any valid numeric expression except zero.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b802c-113">Типы результата</span><span class="sxs-lookup"><span data-stu-id="b802c-113">Result Types</span></span>  
 <span data-ttu-id="b802c-114">Определяются типами данных обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="b802c-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="b802c-115">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b802c-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b802c-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="b802c-116">Remarks</span></span>  
 <span data-ttu-id="b802c-117">Оба выражения должны соответствовать целочисленному типу данных со знаком или без знака.</span><span class="sxs-lookup"><span data-stu-id="b802c-117">Both expressions must evaluate to signed or unsigned integer data types.</span></span>  
  
 <span data-ttu-id="b802c-118">Если один из операндов равен NULL, то результатом является значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b802c-118">If either operand is null, the result is null.</span></span>  
  
 <span data-ttu-id="b802c-119">Нулевой остаток от деления — недопустимый аргумент.</span><span class="sxs-lookup"><span data-stu-id="b802c-119">Modulo zero is not legal.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="b802c-120">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="b802c-120">Expression Examples</span></span>  
 <span data-ttu-id="b802c-121">Этот пример вычисляет модули из двух числовых литералов.</span><span class="sxs-lookup"><span data-stu-id="b802c-121">This example computes the modulus from two numeric literals.</span></span> <span data-ttu-id="b802c-122">Результат 3.</span><span class="sxs-lookup"><span data-stu-id="b802c-122">The result is 3.</span></span>  
  
```  
42 % 13  
```  
  
 <span data-ttu-id="b802c-123">Этот пример вычисляет модуль от столбца **SalesQuota** и числового литерала.</span><span class="sxs-lookup"><span data-stu-id="b802c-123">This example computes the modulus from the **SalesQuota** column and a numeric literal.</span></span>  
  
```  
SalesQuota % 12  
```  
  
 <span data-ttu-id="b802c-124">Этот пример вычисляет модуль из двух числовых переменных **Sales$** и **Month**.</span><span class="sxs-lookup"><span data-stu-id="b802c-124">This example computes the modulus from two numeric variables **Sales$** and **Month**.</span></span> <span data-ttu-id="b802c-125">Переменная **Sales$** должна быть заключена в квадратные скобки, так как имя включает символ $.</span><span class="sxs-lookup"><span data-stu-id="b802c-125">The variable **Sales$** must be enclosed in brackets because the name includes the $ character.</span></span> <span data-ttu-id="b802c-126">Дополнительные сведения см. в разделе [Идентификаторы (службы SSIS)](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="b802c-126">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
@[Sales$] % @Month  
```  
  
 <span data-ttu-id="b802c-127">Этот пример использует оператор остатка от деления, чтобы определить, является ли значение переменной **Value** четным или нечетным, и использует оператор условия, чтобы вернуть строку, описывающую результат.</span><span class="sxs-lookup"><span data-stu-id="b802c-127">This example uses the modulo operator to determine if the value of the **Value** variable is even or odd, and uses the conditional operator to return a string that describes the result.</span></span> <span data-ttu-id="b802c-128">Дополнительные сведения см. в разделе [? : (условный) (выражение служб SSIS)](conditional-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="b802c-128">For more information, see [? : &#40;Conditional&#41; &#40;SSIS Expression&#41;](conditional-ssis-expression.md).</span></span>  
  
```  
@Value % 2 == 0? "even":"odd"  
```  
  
## <a name="see-also"></a><span data-ttu-id="b802c-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="b802c-129">See Also</span></span>  
 <span data-ttu-id="b802c-130">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="b802c-130">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="b802c-131">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="b802c-131">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
