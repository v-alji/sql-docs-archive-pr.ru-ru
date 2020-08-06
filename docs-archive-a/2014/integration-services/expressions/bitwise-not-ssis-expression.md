---
title: ~ (битовое НЕ) (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- bitwise NOT (~)
- ~ (bitwise NOT)
ms.assetid: e4413ddd-0d0e-40c3-9c76-b5ce323218ec
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 75745a0650c1744064f2a671659879e11464514e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666183"
---
# <a name="-bitwise-not-ssis-expression"></a><span data-ttu-id="810c5-102">~ (битовое НЕ) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="810c5-102">~ (Bitwise Not) (SSIS Expression)</span></span>
  <span data-ttu-id="810c5-103">Выполняет битовую инверсию целого числа.</span><span class="sxs-lookup"><span data-stu-id="810c5-103">Performs a bitwise negation of an integer.</span></span> <span data-ttu-id="810c5-104">Этот оператор может быть применен к целочисленному типу данных со знаком или без знака.</span><span class="sxs-lookup"><span data-stu-id="810c5-104">This operator can be applied to signed and unsigned integer data types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="810c5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="810c5-105">Syntax</span></span>  
  
```  
  
~integer_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="810c5-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="810c5-106">Arguments</span></span>  
 <span data-ttu-id="810c5-107">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="810c5-107">*integer_expression*</span></span>  
 <span data-ttu-id="810c5-108">Любое допустимое выражение целочисленного типа данных.</span><span class="sxs-lookup"><span data-stu-id="810c5-108">Is any valid expression of an integer data type.</span></span> <span data-ttu-id="810c5-109">*integer*_*expression* — целое число, которое преобразуется в двоичное число для побитовой операции.</span><span class="sxs-lookup"><span data-stu-id="810c5-109">*integer*_*expression* is an integer that is transformed into a binary number for the bitwise operation.</span></span> <span data-ttu-id="810c5-110">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="810c5-110">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="810c5-111">Типы результата</span><span class="sxs-lookup"><span data-stu-id="810c5-111">Result Types</span></span>  
 <span data-ttu-id="810c5-112">Возвращает тип данных *integer_expression*.</span><span class="sxs-lookup"><span data-stu-id="810c5-112">Returns the data type of *integer_expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="810c5-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="810c5-113">Remarks</span></span>  
 <span data-ttu-id="810c5-114">None</span><span class="sxs-lookup"><span data-stu-id="810c5-114">None</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="810c5-115">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="810c5-115">Expression Examples</span></span>  
 <span data-ttu-id="810c5-116">Этот пример выполняет операцию битового ~ (NOT) над числом 170 (0000 0000 1010 1010).</span><span class="sxs-lookup"><span data-stu-id="810c5-116">This example performs a bitwise ~ (NOT) operation on the number 170 (0000 0000 1010 1010).</span></span> <span data-ttu-id="810c5-117">Число целого типа со знаком.</span><span class="sxs-lookup"><span data-stu-id="810c5-117">The number is a signed integer.</span></span>  
  
```  
  
~ 170  
```  
  
 <span data-ttu-id="810c5-118">Результат вычисления выражения — 170 (1111111101010101).</span><span class="sxs-lookup"><span data-stu-id="810c5-118">The expression evaluates to -170 (1111111101010101).</span></span>  
  
 <span data-ttu-id="810c5-119">0000000010101010</span><span class="sxs-lookup"><span data-stu-id="810c5-119">0000000010101010</span></span>  
  
 ---------------------\-  
  
 <span data-ttu-id="810c5-120">1111111101010101</span><span class="sxs-lookup"><span data-stu-id="810c5-120">1111111101010101</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="810c5-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="810c5-121">See Also</span></span>  
 <span data-ttu-id="810c5-122">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="810c5-122">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="810c5-123">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="810c5-123">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
