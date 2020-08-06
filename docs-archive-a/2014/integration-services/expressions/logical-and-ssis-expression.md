---
title: '&amp;&amp; (логическое И) (выражение служб SSIS) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '&& (logical AND)'
- AND, logical AND
- logical AND (&&)
ms.assetid: a8cb3517-d5d1-4861-9f04-905c719185ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8d973d7d4e86f88f7ae88c820ed4e4a5c1ce526f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729669"
---
# <a name="ampamp-logical-and-ssis-expression"></a><span data-ttu-id="970f4-102">&amp;&amp; (логическое И) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="970f4-102">&amp;&amp; (Logical AND) (SSIS Expression)</span></span>
  <span data-ttu-id="970f4-103">Выполняет логическую операцию И.</span><span class="sxs-lookup"><span data-stu-id="970f4-103">Performs a logical AND operation.</span></span> <span data-ttu-id="970f4-104">Выражение принимает значение TRUE, если все условия имеют значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="970f4-104">The expression evaluates to TRUE if all conditions are TRUE.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="970f4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="970f4-105">Syntax</span></span>  
  
```  
  
boolean_expression1 && boolean_expression2  
```  
  
## <a name="arguments"></a><span data-ttu-id="970f4-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="970f4-106">Arguments</span></span>  
 <span data-ttu-id="970f4-107">*boolean_expression1, boolean_expression2*</span><span class="sxs-lookup"><span data-stu-id="970f4-107">*boolean _expression1, boolean_expression2*</span></span>  
 <span data-ttu-id="970f4-108">Любое допустимое выражение, результатом которого являются TRUE, FALSE или NULL</span><span class="sxs-lookup"><span data-stu-id="970f4-108">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="970f4-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="970f4-109">Result Types</span></span>  
 <span data-ttu-id="970f4-110">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="970f4-110">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="970f4-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="970f4-111">Remarks</span></span>  
 <span data-ttu-id="970f4-112">Следующая таблица демонстрирует результаты выполнения оператора &&.</span><span class="sxs-lookup"><span data-stu-id="970f4-112">The following table shows the result of the && operator.</span></span>  
  
|<span data-ttu-id="970f4-113">Результат</span><span class="sxs-lookup"><span data-stu-id="970f4-113">Result</span></span>|<span data-ttu-id="970f4-114">Выражение</span><span class="sxs-lookup"><span data-stu-id="970f4-114">Expression</span></span>|<span data-ttu-id="970f4-115">Выражение</span><span class="sxs-lookup"><span data-stu-id="970f4-115">Expression</span></span>|  
|------------|----------------|----------------|  
|<span data-ttu-id="970f4-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="970f4-116">TRUE</span></span>|<span data-ttu-id="970f4-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="970f4-117">TRUE</span></span>|<span data-ttu-id="970f4-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="970f4-118">TRUE</span></span>|  
|<span data-ttu-id="970f4-119">FALSE</span><span class="sxs-lookup"><span data-stu-id="970f4-119">FALSE</span></span>|<span data-ttu-id="970f4-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="970f4-120">TRUE</span></span>|<span data-ttu-id="970f4-121">FALSE</span><span class="sxs-lookup"><span data-stu-id="970f4-121">FALSE</span></span>|  
|<span data-ttu-id="970f4-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="970f4-122">FALSE</span></span>|<span data-ttu-id="970f4-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="970f4-123">FALSE</span></span>|<span data-ttu-id="970f4-124">FALSE</span><span class="sxs-lookup"><span data-stu-id="970f4-124">FALSE</span></span>|  
|<span data-ttu-id="970f4-125">NULL</span><span class="sxs-lookup"><span data-stu-id="970f4-125">NULL</span></span>|<span data-ttu-id="970f4-126">NULL</span><span class="sxs-lookup"><span data-stu-id="970f4-126">NULL</span></span>|<span data-ttu-id="970f4-127">NULL</span><span class="sxs-lookup"><span data-stu-id="970f4-127">NULL</span></span>|  
|<span data-ttu-id="970f4-128">NULL</span><span class="sxs-lookup"><span data-stu-id="970f4-128">NULL</span></span>|<span data-ttu-id="970f4-129">NULL</span><span class="sxs-lookup"><span data-stu-id="970f4-129">NULL</span></span>|<span data-ttu-id="970f4-130">TRUE</span><span class="sxs-lookup"><span data-stu-id="970f4-130">TRUE</span></span>|  
|<span data-ttu-id="970f4-131">FALSE</span><span class="sxs-lookup"><span data-stu-id="970f4-131">FALSE</span></span>|<span data-ttu-id="970f4-132">NULL</span><span class="sxs-lookup"><span data-stu-id="970f4-132">NULL</span></span>|<span data-ttu-id="970f4-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="970f4-133">FALSE</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="970f4-134">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="970f4-134">Expression Examples</span></span>  
 <span data-ttu-id="970f4-135">В этом примере используются столбцы **StandardCost** и **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="970f4-135">This example uses the **StandardCost** and the **ListPrice** columns.</span></span> <span data-ttu-id="970f4-136">Пример возвращает значение TRUE, если значение столбца **StandardCost** меньше 300 или значение столбца **ListPrice** больше 500.</span><span class="sxs-lookup"><span data-stu-id="970f4-136">The example evaluates to TRUE if the value of the **StandardCost** column is less than 300 and the **ListPrice** column is greater than 500.</span></span>  
  
```  
StandardCost < 300 && ListPrice > 500  
```  
  
 <span data-ttu-id="970f4-137">Этот пример использует переменные **SPrice** и **LPrice** вместо числовых литералов.</span><span class="sxs-lookup"><span data-stu-id="970f4-137">This example uses the variables **SPrice** and **LPrice** instead of literals.</span></span>  
  
```  
StandardCost < @SPrice && ListPrice > @LPrice  
```  
  
## <a name="see-also"></a><span data-ttu-id="970f4-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="970f4-138">See Also</span></span>  
 <span data-ttu-id="970f4-139">[& (битовое И) (выражение служб SSIS)](bitwise-and-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="970f4-139">[& &#40;Bitwise AND&#41; &#40;SSIS Expression&#41;](bitwise-and-ssis-expression.md) </span></span>  
 <span data-ttu-id="970f4-140">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="970f4-140">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="970f4-141">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="970f4-141">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
