---
title: '| (битовое включающее ИЛИ) (выражение служб SSIS) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '| (bitwise inclusive OR)'
- bitwise inclusive OR (|)
ms.assetid: 4dce9eb2-3680-4adc-81a3-816ea52cef49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 73d64886b433ffe5b4e06dc4870bbca06b2a53dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666184"
---
# <a name="-bitwise-inclusive-or-ssis-expression"></a><span data-ttu-id="762a7-102">| (битовое включающее ИЛИ) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="762a7-102">| (Bitwise Inclusive OR) (SSIS Expression)</span></span>
  <span data-ttu-id="762a7-103">Выполняет побитовую операцию ИЛИ для двух целочисленных значений.</span><span class="sxs-lookup"><span data-stu-id="762a7-103">Performs a bitwise OR operation of two integer values.</span></span> <span data-ttu-id="762a7-104">Она сравнивает каждый бит первого операнда с соответствующим битом второго операнда.</span><span class="sxs-lookup"><span data-stu-id="762a7-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="762a7-105">Если какой-либо из битов равен 1, соответствующий бит результата равен 1.</span><span class="sxs-lookup"><span data-stu-id="762a7-105">If either bit is 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="762a7-106">В противном случае соответствующий бит результата равен нулю (0).</span><span class="sxs-lookup"><span data-stu-id="762a7-106">Otherwise, the corresponding result bit is set to zero (0).</span></span>  
  
 <span data-ttu-id="762a7-107">Оба условия должны относиться либо к целым числам со знаком, либо к беззнаковым целым числам.</span><span class="sxs-lookup"><span data-stu-id="762a7-107">Both conditions must be a signed integer data type or both conditions must be an unsigned integer data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="762a7-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="762a7-108">Syntax</span></span>  
  
```  
  
integer_expression1 | integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="762a7-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="762a7-109">Arguments</span></span>  
 <span data-ttu-id="762a7-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="762a7-110">*integer_expression1 ,integer_ expression2*</span></span>  
 <span data-ttu-id="762a7-111">Любое допустимое выражение: либо целое число со знаком, либо беззнаковое целое число.</span><span class="sxs-lookup"><span data-stu-id="762a7-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="762a7-112">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="762a7-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="762a7-113">Типы результата</span><span class="sxs-lookup"><span data-stu-id="762a7-113">Result Types</span></span>  
 <span data-ttu-id="762a7-114">Определяются типами данных обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="762a7-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="762a7-115">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="762a7-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="762a7-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="762a7-116">Remarks</span></span>  
 <span data-ttu-id="762a7-117">Если значение любого из условий — NULL, то результат выражения тоже будет NULL.</span><span class="sxs-lookup"><span data-stu-id="762a7-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="762a7-118">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="762a7-118">Expression Examples</span></span>  
 <span data-ttu-id="762a7-119">В данном примере выполняется операция битового ИЛИ над переменными **NumberA** и **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="762a7-119">This example performs a bitwise inclusive OR operation between the variables **NumberA** and **NumberB**.</span></span> <span data-ttu-id="762a7-120">**NumberA** содержит 3 (00000011) а **NumberB** содержит 9 (00001001).</span><span class="sxs-lookup"><span data-stu-id="762a7-120">**NumberA** contains 3 (00000011) and **NumberB** contains 9 (00001001).</span></span>  
  
```  
@NumberA | @NumberB  
```  
  
 <span data-ttu-id="762a7-121">Результат устанавливается в 11 (00001011).</span><span class="sxs-lookup"><span data-stu-id="762a7-121">The expression evaluates to 11 (00001011).</span></span>  
  
 <span data-ttu-id="762a7-122">00000011</span><span class="sxs-lookup"><span data-stu-id="762a7-122">00000011</span></span>  
  
 <span data-ttu-id="762a7-123">00001001</span><span class="sxs-lookup"><span data-stu-id="762a7-123">00001001</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="762a7-124">00001011</span><span class="sxs-lookup"><span data-stu-id="762a7-124">00001011</span></span>  
  
 <span data-ttu-id="762a7-125">В данном примере выполняется операция побитового ИЛИ над столбцами **ReorderPoint** и **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="762a7-125">This example performs a bitwise inclusive OR operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint | SafetyStockLevel  
```  
  
 <span data-ttu-id="762a7-126">Если **ReorderPoint** имеет значение 10, а **SafetyStockLevel** — 8, результат вычисления выражения равен 10 (00001010).</span><span class="sxs-lookup"><span data-stu-id="762a7-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 10 (00001010).</span></span>  
  
 <span data-ttu-id="762a7-127">00001010</span><span class="sxs-lookup"><span data-stu-id="762a7-127">00001010</span></span>  
  
 <span data-ttu-id="762a7-128">00001000</span><span class="sxs-lookup"><span data-stu-id="762a7-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="762a7-129">00001010</span><span class="sxs-lookup"><span data-stu-id="762a7-129">00001010</span></span>  
  
 <span data-ttu-id="762a7-130">В данном примере выполняется операция побитового ИЛИ над двумя целочисленными значениями.</span><span class="sxs-lookup"><span data-stu-id="762a7-130">This example performs a bitwise inclusive OR operation between two integers.</span></span>  
  
```  
3 | 5   
```  
  
 <span data-ttu-id="762a7-131">Значение устанавливается равным 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="762a7-131">The expression evaluates to 7 (00000111).</span></span>  
  
 <span data-ttu-id="762a7-132">00000011</span><span class="sxs-lookup"><span data-stu-id="762a7-132">00000011</span></span>  
  
 <span data-ttu-id="762a7-133">00000101</span><span class="sxs-lookup"><span data-stu-id="762a7-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="762a7-134">00000111</span><span class="sxs-lookup"><span data-stu-id="762a7-134">00000111</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="762a7-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="762a7-135">See Also</span></span>  
 <span data-ttu-id="762a7-136">[&#124;&#124; (логическое ИЛИ) (выражение служб SSIS)](logical-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="762a7-136">[&#124;&#124; &#40;Logical OR&#41; &#40;SSIS Expression&#41;](logical-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="762a7-137">[^ (битовое исключающее ИЛИ) (выражение служб SSIS)](bitwise-exclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="762a7-137">[^ &#40;Bitwise Exclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-exclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="762a7-138">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="762a7-138">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="762a7-139">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="762a7-139">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
