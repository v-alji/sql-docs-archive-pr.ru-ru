---
title: '&amp; (битовое И) (выражение служб SSIS) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- AND, bitwise AND
- '& (bitwise AND)'
- bitwise AND (&)
ms.assetid: 06d2958e-66a5-44d8-8bc4-56209ebe1ff2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fbf3c8ffcef079e25c82478947bc3b92a6b4be93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666190"
---
# <a name="amp-bitwise-and-ssis-expression"></a><span data-ttu-id="7f0d2-102">&amp; (битовое И) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="7f0d2-102">&amp; (Bitwise AND) (SSIS Expression)</span></span>
  <span data-ttu-id="7f0d2-103">Выполняет побитовую операцию И для двух целочисленных значений.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-103">Performs a bitwise AND operation of two integer values.</span></span> <span data-ttu-id="7f0d2-104">Она сравнивает каждый бит первого операнда с соответствующим битом второго операнда.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="7f0d2-105">Если оба бита равны 1, соответствующий бит результата равен 1.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-105">If both bits are 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="7f0d2-106">В противном случае соответствующий бит результата равен 0.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-106">Otherwise, the corresponding result bit is set to 0.</span></span>  
  
 <span data-ttu-id="7f0d2-107">Оба значения должны принадлежать целочисленному типу со знаком или без знака.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-107">Both conditions must be a signed integer type or both conditions must be an unsigned integer type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f0d2-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f0d2-108">Syntax</span></span>  
  
```  
  
integer_expression1 & integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="7f0d2-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7f0d2-109">Arguments</span></span>  
 <span data-ttu-id="7f0d2-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="7f0d2-110">*integer_expression1, integer_expression2*</span></span>  
 <span data-ttu-id="7f0d2-111">Любое допустимое выражение: либо целое число со знаком, либо беззнаковое целое число.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="7f0d2-112">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f0d2-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7f0d2-113">Типы результата</span><span class="sxs-lookup"><span data-stu-id="7f0d2-113">Result Types</span></span>  
 <span data-ttu-id="7f0d2-114">Определяются типами данных обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="7f0d2-115">Дополнительные сведения см. в разделе [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7f0d2-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f0d2-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="7f0d2-116">Remarks</span></span>  
 <span data-ttu-id="7f0d2-117">Если значение любого из условий — NULL, то результат выражения тоже будет NULL.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7f0d2-118">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="7f0d2-118">Expression Examples</span></span>  
 <span data-ttu-id="7f0d2-119">Этот пример выполняет битовую операцию И над столбцами **NumberA** и **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-119">This example performs a bitwise AND operation between the columns **NumberA** and **NumberB**.</span></span> <span data-ttu-id="7f0d2-120">Столбец**NumberA** содержит значение 3 (0000011), а столбец **NumberB** содержит значение 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="7f0d2-120">**NumberA** contains 3 (0000011) and column **NumberB** contains 7 (00000111).</span></span>  
  
```  
NumberA & NumberB  
```  
  
 <span data-ttu-id="7f0d2-121">Результат вычисления выражения равен 3 (00000011).</span><span class="sxs-lookup"><span data-stu-id="7f0d2-121">The expression evaluates to 3 (00000011).</span></span>  
  
 <span data-ttu-id="7f0d2-122">00000011</span><span class="sxs-lookup"><span data-stu-id="7f0d2-122">00000011</span></span>  
  
 <span data-ttu-id="7f0d2-123">00000111</span><span class="sxs-lookup"><span data-stu-id="7f0d2-123">00000111</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="7f0d2-124">00000011</span><span class="sxs-lookup"><span data-stu-id="7f0d2-124">00000011</span></span>  
  
 <span data-ttu-id="7f0d2-125">Этот пример выполняет побитовую операцию И между столбцами **ReorderPoint** и **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="7f0d2-125">This example performs a bitwise AND operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint & SafetyStockLevel  
```  
  
 <span data-ttu-id="7f0d2-126">Если **ReorderPoint** имеет значение 10, а **SafetyStockLevel** имеет значение 8, результат вычисления выражения равен 8 (00001000).</span><span class="sxs-lookup"><span data-stu-id="7f0d2-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 8 (00001000).</span></span>  
  
 <span data-ttu-id="7f0d2-127">00001010</span><span class="sxs-lookup"><span data-stu-id="7f0d2-127">00001010</span></span>  
  
 <span data-ttu-id="7f0d2-128">00001000</span><span class="sxs-lookup"><span data-stu-id="7f0d2-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="7f0d2-129">00001000</span><span class="sxs-lookup"><span data-stu-id="7f0d2-129">00001000</span></span>  
  
 <span data-ttu-id="7f0d2-130">Этот пример выполняет побитовую операцию И между двумя целыми числами.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-130">This example performs a bitwise AND operation between two integers.</span></span>  
  
```  
3 & 5   
```  
  
 <span data-ttu-id="7f0d2-131">Результат вычисления выражения равен 1(00000001).</span><span class="sxs-lookup"><span data-stu-id="7f0d2-131">The expression evaluates to 1(00000001).</span></span>  
  
 <span data-ttu-id="7f0d2-132">00000011</span><span class="sxs-lookup"><span data-stu-id="7f0d2-132">00000011</span></span>  
  
 <span data-ttu-id="7f0d2-133">00000101</span><span class="sxs-lookup"><span data-stu-id="7f0d2-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="7f0d2-134">00000001</span><span class="sxs-lookup"><span data-stu-id="7f0d2-134">00000001</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f0d2-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f0d2-135">See Also</span></span>  
 <span data-ttu-id="7f0d2-136">[&#124;&#124; (логическое И) (выражение служб SSIS)](logical-and-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="7f0d2-136">[&& &#40;Logical AND&#41; &#40;SSIS Expression&#41;](logical-and-ssis-expression.md) </span></span>  
 <span data-ttu-id="7f0d2-137">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="7f0d2-137">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="7f0d2-138">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="7f0d2-138">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
