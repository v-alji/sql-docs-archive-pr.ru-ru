---
title: ^ (битовое исключающее ИЛИ) (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ^ (bitwise exclusive OR operator)
- bitwise exclusive OR (^)
ms.assetid: 6ac53cab-29c4-4835-9f87-371b058b2f38
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d86c3d810e9e5572af93c97f82c2275db2c979b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666191"
---
# <a name="-bitwise-exclusive-or-ssis-expression"></a><span data-ttu-id="a41f5-102">^ (битовое исключающее ИЛИ) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="a41f5-102">^ (Bitwise Exclusive OR) (SSIS Expression)</span></span>
  <span data-ttu-id="a41f5-103">Выполняет побитовую исключающую операцию ИЛИ для двух целочисленных значений.</span><span class="sxs-lookup"><span data-stu-id="a41f5-103">Performs a bitwise exclusive OR operation of two integer values.</span></span> <span data-ttu-id="a41f5-104">Она сравнивает каждый бит первого операнда с соответствующим битом второго операнда.</span><span class="sxs-lookup"><span data-stu-id="a41f5-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="a41f5-105">Если один из битов равен 0, а второй равен 1, соответствующий бит результата устанавливается в 1.</span><span class="sxs-lookup"><span data-stu-id="a41f5-105">If one bit is 0 and the other bit is 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="a41f5-106">Если оба бита равны 0 или оба бита равны 1, соответствующий бит результата равен 0.</span><span class="sxs-lookup"><span data-stu-id="a41f5-106">If both bits are 0 or both bits are 1, the corresponding result bit is set to 0.</span></span>  
  
 <span data-ttu-id="a41f5-107">Оба условия должны относиться либо к целым числам со знаком, либо к беззнаковым целым числам.</span><span class="sxs-lookup"><span data-stu-id="a41f5-107">Both conditions must be a signed integer data type or both conditions must be an unsigned integer data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a41f5-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a41f5-108">Syntax</span></span>  
  
```  
  
integer_expression1 ^ integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a41f5-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a41f5-109">Arguments</span></span>  
 <span data-ttu-id="a41f5-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="a41f5-110">*integer_expression1, integer_expression2*</span></span>  
 <span data-ttu-id="a41f5-111">Любое допустимое выражение: либо целое число со знаком, либо беззнаковое целое число.</span><span class="sxs-lookup"><span data-stu-id="a41f5-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="a41f5-112">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a41f5-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a41f5-113">Типы результата</span><span class="sxs-lookup"><span data-stu-id="a41f5-113">Result Types</span></span>  
 <span data-ttu-id="a41f5-114">Определяются типами данных обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="a41f5-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="a41f5-115">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a41f5-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a41f5-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="a41f5-116">Remarks</span></span>  
 <span data-ttu-id="a41f5-117">Если значение любого из условий — NULL, то результат выражения тоже будет NULL.</span><span class="sxs-lookup"><span data-stu-id="a41f5-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="a41f5-118">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="a41f5-118">Expression Examples</span></span>  
 <span data-ttu-id="a41f5-119">Этот пример выполняет битовую монопольную операцию ИЛИ над переменными **NumberA** и **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="a41f5-119">This example performs a bitwise exclusive OR operation between variables **NumberA** and **NumberB**.</span></span> <span data-ttu-id="a41f5-120">**NumberA** содержит 3 (00000011), а **NumberB** — 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="a41f5-120">**NumberA** contains 3 (00000011) and **NumberB** contains 7 (00000111).</span></span>  
  
```  
@NumberA ^ @NumberB  
```  
  
 <span data-ttu-id="a41f5-121">Результатом вычисления выражения будет 4 (00000100).</span><span class="sxs-lookup"><span data-stu-id="a41f5-121">The expression evaluates to 4 (00000100).</span></span>  
  
 <span data-ttu-id="a41f5-122">00000011</span><span class="sxs-lookup"><span data-stu-id="a41f5-122">00000011</span></span>  
  
 <span data-ttu-id="a41f5-123">00000111</span><span class="sxs-lookup"><span data-stu-id="a41f5-123">00000111</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="a41f5-124">00000100</span><span class="sxs-lookup"><span data-stu-id="a41f5-124">00000100</span></span>  
  
 <span data-ttu-id="a41f5-125">Этот пример производит побитовую исключающую операцию ИЛИ между столбцами **ReorderPoint** и **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="a41f5-125">This example performs a bitwise exclusive OR operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint ^ SafetyStockLevel  
```  
  
 <span data-ttu-id="a41f5-126">Если **ReorderPoint** имеет значение 10, а **SafetyStockLevel** — значение 8, результат вычисления выражения равен 2 (00000010).</span><span class="sxs-lookup"><span data-stu-id="a41f5-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 2 (00000010).</span></span>  
  
 <span data-ttu-id="a41f5-127">00001010</span><span class="sxs-lookup"><span data-stu-id="a41f5-127">00001010</span></span>  
  
 <span data-ttu-id="a41f5-128">00001000</span><span class="sxs-lookup"><span data-stu-id="a41f5-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="a41f5-129">00000010</span><span class="sxs-lookup"><span data-stu-id="a41f5-129">00000010</span></span>  
  
 <span data-ttu-id="a41f5-130">Этот пример выполняет побитовую исключающую операцию ИЛИ между двумя целыми числами.</span><span class="sxs-lookup"><span data-stu-id="a41f5-130">This example performs a bitwise exclusive OR operation between two integers.</span></span>  
  
```  
3 ^ 5   
```  
  
 <span data-ttu-id="a41f5-131">Результатом выполнения выражения будет 6 (00000110).</span><span class="sxs-lookup"><span data-stu-id="a41f5-131">The expression evaluates to 6 (00000110).</span></span>  
  
 <span data-ttu-id="a41f5-132">00000011</span><span class="sxs-lookup"><span data-stu-id="a41f5-132">00000011</span></span>  
  
 <span data-ttu-id="a41f5-133">00000101</span><span class="sxs-lookup"><span data-stu-id="a41f5-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="a41f5-134">00000110</span><span class="sxs-lookup"><span data-stu-id="a41f5-134">00000110</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a41f5-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="a41f5-135">See Also</span></span>  
 <span data-ttu-id="a41f5-136">[&#124;&#124; (логическое ИЛИ) (выражение служб SSIS)](logical-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="a41f5-136">[&#124;&#124; &#40;Logical OR&#41; &#40;SSIS Expression&#41;](logical-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="a41f5-137">[&#124; (битовое включающее ИЛИ) (выражение служб SSIS)](bitwise-inclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="a41f5-137">[&#124; &#40;Bitwise Inclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-inclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="a41f5-138">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="a41f5-138">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="a41f5-139">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="a41f5-139">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
