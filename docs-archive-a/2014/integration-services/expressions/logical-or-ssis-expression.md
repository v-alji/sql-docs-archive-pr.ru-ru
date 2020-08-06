---
title: '|| (логическое ИЛИ) (выражение служб SSIS) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- OR operator
- logical OR (||)
- '|| (logical OR)'
ms.assetid: a3c07c09-f121-4187-9617-b01adcf843c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 72d4a1c7b54856675f0faa7f5f58452cb8bca450
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729670"
---
# <a name="-logical-or-ssis-expression"></a><span data-ttu-id="f3d58-102">|| (логическое ИЛИ) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="f3d58-102">|| (Logical OR) (SSIS Expression)</span></span>
  <span data-ttu-id="f3d58-103">Выполняет логическую операцию ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="f3d58-103">Performs a logical OR operation.</span></span> <span data-ttu-id="f3d58-104">Выражение принимает значение TRUE, если одно или оба условия имеют значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="f3d58-104">The expression evaluates to TRUE if one or both conditions are TRUE.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3d58-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3d58-105">Syntax</span></span>  
  
```  
  
boolean_expression1 || boolean_expression2  
```  
  
## <a name="arguments"></a><span data-ttu-id="f3d58-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f3d58-106">Arguments</span></span>  
 <span data-ttu-id="f3d58-107">*boolean_expression1, boolean_expression2*</span><span class="sxs-lookup"><span data-stu-id="f3d58-107">*boolean_expression1, boolean_expression2*</span></span>  
 <span data-ttu-id="f3d58-108">Любое допустимое выражение, результатом которого являются TRUE, FALSE или NULL</span><span class="sxs-lookup"><span data-stu-id="f3d58-108">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f3d58-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="f3d58-109">Result Types</span></span>  
 <span data-ttu-id="f3d58-110">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="f3d58-110">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3d58-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3d58-111">Remarks</span></span>  
 <span data-ttu-id="f3d58-112">Следующая таблица демонстрирует результаты выполнения оператора ||:</span><span class="sxs-lookup"><span data-stu-id="f3d58-112">The following table shows the result of the || operator.</span></span>  
  
|<span data-ttu-id="f3d58-113">Результат</span><span class="sxs-lookup"><span data-stu-id="f3d58-113">Result</span></span>|<span data-ttu-id="f3d58-114">Выражение</span><span class="sxs-lookup"><span data-stu-id="f3d58-114">Expression</span></span>|<span data-ttu-id="f3d58-115">Выражение</span><span class="sxs-lookup"><span data-stu-id="f3d58-115">Expression</span></span>|  
|------------|----------------|----------------|  
|<span data-ttu-id="f3d58-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="f3d58-116">TRUE</span></span>|<span data-ttu-id="f3d58-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="f3d58-117">TRUE</span></span>|<span data-ttu-id="f3d58-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="f3d58-118">TRUE</span></span>|  
|<span data-ttu-id="f3d58-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="f3d58-119">TRUE</span></span>|<span data-ttu-id="f3d58-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="f3d58-120">TRUE</span></span>|<span data-ttu-id="f3d58-121">FALSE</span><span class="sxs-lookup"><span data-stu-id="f3d58-121">FALSE</span></span>|  
|<span data-ttu-id="f3d58-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="f3d58-122">FALSE</span></span>|<span data-ttu-id="f3d58-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="f3d58-123">FALSE</span></span>|<span data-ttu-id="f3d58-124">FALSE</span><span class="sxs-lookup"><span data-stu-id="f3d58-124">FALSE</span></span>|  
|<span data-ttu-id="f3d58-125">NULL</span><span class="sxs-lookup"><span data-stu-id="f3d58-125">NULL</span></span>|<span data-ttu-id="f3d58-126">NULL</span><span class="sxs-lookup"><span data-stu-id="f3d58-126">NULL</span></span>|<span data-ttu-id="f3d58-127">NULL</span><span class="sxs-lookup"><span data-stu-id="f3d58-127">NULL</span></span>|  
|<span data-ttu-id="f3d58-128">TRUE</span><span class="sxs-lookup"><span data-stu-id="f3d58-128">TRUE</span></span>|<span data-ttu-id="f3d58-129">NULL</span><span class="sxs-lookup"><span data-stu-id="f3d58-129">NULL</span></span>|<span data-ttu-id="f3d58-130">TRUE</span><span class="sxs-lookup"><span data-stu-id="f3d58-130">TRUE</span></span>|  
|<span data-ttu-id="f3d58-131">NULL</span><span class="sxs-lookup"><span data-stu-id="f3d58-131">NULL</span></span>|<span data-ttu-id="f3d58-132">NULL</span><span class="sxs-lookup"><span data-stu-id="f3d58-132">NULL</span></span>|<span data-ttu-id="f3d58-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="f3d58-133">FALSE</span></span>|  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="f3d58-134">Примеры выражений служб SSIS</span><span class="sxs-lookup"><span data-stu-id="f3d58-134">SSIS Expression Examples</span></span>  
 <span data-ttu-id="f3d58-135">В этом примере используются столбцы **StandardCost** и **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="f3d58-135">This example uses the **StandardCost** and **ListPrice** columns.</span></span> <span data-ttu-id="f3d58-136">Пример возвращает значение TRUE, если значение столбца **StandardCost** меньше 300 или значение столбца **ListPrice** больше 500.</span><span class="sxs-lookup"><span data-stu-id="f3d58-136">The example evaluates to TRUE if the value of the **StandardCost** column is less than 300 or the **ListPrice** column is greater than 500.</span></span>  
  
```  
StandardCost < 300 || ListPrice > 500  
```  
  
 <span data-ttu-id="f3d58-137">Этот пример использует переменные **SPrice** и **LPrice** вместо числовых литералов.</span><span class="sxs-lookup"><span data-stu-id="f3d58-137">This example uses the variables **SPrice** and **LPrice** instead of numeric literals.</span></span>  
  
```  
StandardCost < @SPrice || ListPrice > @LPrice  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3d58-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3d58-138">See Also</span></span>  
 <span data-ttu-id="f3d58-139">[&#124; (битовое включающее ИЛИ) (выражение служб SSIS)](bitwise-inclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f3d58-139">[&#124; &#40;Bitwise Inclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-inclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="f3d58-140">[^ (битовое исключающее ИЛИ) (выражение служб SSIS)](bitwise-exclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f3d58-140">[^ &#40;Bitwise Exclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-exclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="f3d58-141">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="f3d58-141">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="f3d58-142">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="f3d58-142">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
