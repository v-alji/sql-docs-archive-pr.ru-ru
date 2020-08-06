---
title: '! (логическое НЕ) (выражение служб SSIS) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logical Not (!)
- '! (logical Not)'
ms.assetid: d5c4d1e1-7be4-4d25-bcd9-5b6ddb53b3b3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bbf313930575e864f1556952425567fca96db15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658915"
---
# <a name="-logical-not-ssis-expression"></a><span data-ttu-id="a23e8-103">!</span><span class="sxs-lookup"><span data-stu-id="a23e8-103">!</span></span> <span data-ttu-id="a23e8-104">(логическое НЕ) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="a23e8-104">(Logical Not) (SSIS Expression)</span></span>
  <span data-ttu-id="a23e8-105">Инвертирует логический операнд.</span><span class="sxs-lookup"><span data-stu-id="a23e8-105">Negates a Boolean operand.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a23e8-106">!</span><span class="sxs-lookup"><span data-stu-id="a23e8-106">The !</span></span> <span data-ttu-id="a23e8-107">Оператор «!» не может использоваться вместе с другими операторами.</span><span class="sxs-lookup"><span data-stu-id="a23e8-107">operator cannot be used in conjunction with other operators.</span></span> <span data-ttu-id="a23e8-108">Например, нельзя объединить оператор «!»</span><span class="sxs-lookup"><span data-stu-id="a23e8-108">For example, you cannot combine the !</span></span> <span data-ttu-id="a23e8-109">и оператор > в один оператор «!>»</span><span class="sxs-lookup"><span data-stu-id="a23e8-109">and the > operators into the !>.</span></span> <span data-ttu-id="a23e8-110">.</span><span class="sxs-lookup"><span data-stu-id="a23e8-110">operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a23e8-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a23e8-111">Syntax</span></span>  
  
```  
  
!boolean_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a23e8-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a23e8-112">Arguments</span></span>  
 <span data-ttu-id="a23e8-113">*boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="a23e8-113">*boolean_expression*</span></span>  
 <span data-ttu-id="a23e8-114">Является любое допустимое выражение, результатом которого является логическое значение.</span><span class="sxs-lookup"><span data-stu-id="a23e8-114">Is any valid expression that evaluates to a Boolean.</span></span> <span data-ttu-id="a23e8-115">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a23e8-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a23e8-116">Типы результата</span><span class="sxs-lookup"><span data-stu-id="a23e8-116">Result Types</span></span>  
 <span data-ttu-id="a23e8-117">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="a23e8-117">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a23e8-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="a23e8-118">Remarks</span></span>  
 <span data-ttu-id="a23e8-119">Следующая таблица демонстрирует результаты выполнения «!»</span><span class="sxs-lookup"><span data-stu-id="a23e8-119">The following table shows the result of the !</span></span> <span data-ttu-id="a23e8-120">.</span><span class="sxs-lookup"><span data-stu-id="a23e8-120">operation.</span></span>  
  
|<span data-ttu-id="a23e8-121">Исходное логическое выражение</span><span class="sxs-lookup"><span data-stu-id="a23e8-121">Original Boolean expression</span></span>|<span data-ttu-id="a23e8-122">После выполнения оператора «!»</span><span class="sxs-lookup"><span data-stu-id="a23e8-122">After applying the !</span></span> <span data-ttu-id="a23e8-123">оператор</span><span class="sxs-lookup"><span data-stu-id="a23e8-123">operator</span></span>|  
|---------------------------------|------------------------------------|  
|<span data-ttu-id="a23e8-124">TRUE</span><span class="sxs-lookup"><span data-stu-id="a23e8-124">TRUE</span></span>|<span data-ttu-id="a23e8-125">FALSE</span><span class="sxs-lookup"><span data-stu-id="a23e8-125">FALSE</span></span>|  
|<span data-ttu-id="a23e8-126">NULL</span><span class="sxs-lookup"><span data-stu-id="a23e8-126">NULL</span></span>|<span data-ttu-id="a23e8-127">NULL</span><span class="sxs-lookup"><span data-stu-id="a23e8-127">NULL</span></span>|  
|<span data-ttu-id="a23e8-128">FALSE</span><span class="sxs-lookup"><span data-stu-id="a23e8-128">FALSE</span></span>|<span data-ttu-id="a23e8-129">TRUE</span><span class="sxs-lookup"><span data-stu-id="a23e8-129">TRUE</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="a23e8-130">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="a23e8-130">Expression Examples</span></span>  
 <span data-ttu-id="a23e8-131">В результате выполнения данного выражения получается значение FALSE, если столбец **Color** имеет значение "red".</span><span class="sxs-lookup"><span data-stu-id="a23e8-131">This example evaluates to FALSE if the **Color** column value is "red".</span></span>  
  
```  
!(Color == "red")  
```  
  
 <span data-ttu-id="a23e8-132">В результате выполнения данного выражения получается значение TRUE, если значение переменной **MonthNumber** совпадает со значением переменной, представляющей номер текущего месяца.</span><span class="sxs-lookup"><span data-stu-id="a23e8-132">This example evaluates to TRUE if the value of the **MonthNumber** variable is the same as the integer that represents the current month.</span></span> <span data-ttu-id="a23e8-133">Дополнительные сведения см. в разделе [MONTH (выражение служб SSIS)](month-ssis-expression.md) and [GETDATE (выражение служб SSIS)](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="a23e8-133">For more information, see [MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) and [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
!(@MonthNumber != MONTH(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="a23e8-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="a23e8-134">See Also</span></span>  
 <span data-ttu-id="a23e8-135">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="a23e8-135">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="a23e8-136">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="a23e8-136">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
