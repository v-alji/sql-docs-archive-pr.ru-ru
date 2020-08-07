---
title: REPLICATE (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REPLICATE function
ms.assetid: e7a37b93-6d1d-42d5-9a65-de1790abf6a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9502df5bc20c6ad85f1f98fb57fe6b3cf431cc20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732817"
---
# <a name="replicate-ssis-expression"></a><span data-ttu-id="d6e2a-102">REPLICATE (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="d6e2a-102">REPLICATE (SSIS Expression)</span></span>
  <span data-ttu-id="d6e2a-103">Возвращает символьное выражение, которое было реплицировано, заданное количество раз.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-103">Returns a character expression that is replicated a number of times.</span></span> <span data-ttu-id="d6e2a-104">Аргумент *times* должен выдавать целое число.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-104">The *times* argument must evaluate to an integer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6e2a-105">Функция REPLICATE часто использует длинные строки, поэтому лучше ввести ограничение на длину выражения — 4 000 символов.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-105">The REPLICATE function frequently uses long strings, and therefore is more likely to incur the 4000-character limit on expression length.</span></span> <span data-ttu-id="d6e2a-106">Если результат вычисления выражения имеет тип данных служб Integration Services DT_WSTR или DT_STR, выражение будет усечено до 4000 символов.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-106">If the evaluation result of an expression has the Integration Services data type DT_WSTR or DT_STR, the expression will be truncated at 4000 characters.</span></span> <span data-ttu-id="d6e2a-107">Если тип результата вложенного выражения — DT_STR или DT_WSTR, это выражение также будет усечено до 4000 символов, независимо от типа результата всего выражения.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-107">If the result type of a sub-expression is DT_STR or DT_WSTR, that sub-expression likewise will be truncated to 4000 characters, regardless of the overall expression result type.</span></span> <span data-ttu-id="d6e2a-108">Последствия усечения могут быть корректно обработаны или могут вызвать предупреждение или ошибку.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-108">The consequences of truncation can be handled gracefully or cause a warning or an error.</span></span> <span data-ttu-id="d6e2a-109">Дополнительные сведения см. в разделе [Синтаксис (службы SSIS)](syntax-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="d6e2a-109">For more information, see [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6e2a-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6e2a-110">Syntax</span></span>  
  
```  
  
REPLICATE(character_expression,times)  
```  
  
## <a name="arguments"></a><span data-ttu-id="d6e2a-111">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d6e2a-111">Arguments</span></span>  
 <span data-ttu-id="d6e2a-112">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="d6e2a-112">*character_expression*</span></span>  
 <span data-ttu-id="d6e2a-113">Символьное выражение для репликации.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-113">Is a character expression to replicate.</span></span>  
  
 <span data-ttu-id="d6e2a-114">*times*</span><span class="sxs-lookup"><span data-stu-id="d6e2a-114">*times*</span></span>  
 <span data-ttu-id="d6e2a-115">Целочисленное выражение, которое определяет, сколько раз *character_expression* будет реплицировано.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-115">Is an integer expression that specifies the number of times *character_expression* is replicated.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d6e2a-116">Типы результата</span><span class="sxs-lookup"><span data-stu-id="d6e2a-116">Result Types</span></span>  
 <span data-ttu-id="d6e2a-117">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="d6e2a-117">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6e2a-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="d6e2a-118">Remarks</span></span>  
 <span data-ttu-id="d6e2a-119">Если *times* равно нулю, функция возвратит строку нулевой длины.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-119">If *times* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="d6e2a-120">Если *times* является отрицательным числом, то функция возвратит ошибку.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-120">If *times* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="d6e2a-121">Аргумент *times* также может использовать переменные и столбцы.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-121">The *times* argument can also use variables and columns.</span></span>  
  
 <span data-ttu-id="d6e2a-122">Функция REPLICATE работает только с типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-122">REPLICATE works only with the DT_WSTR data type.</span></span> <span data-ttu-id="d6e2a-123">Аргумент *character_expression* , являющийся строковым литералом или столбцом данных с типом данных DT_STR, неявно приведен к типу данных DT_WSTR до выполнения функции REPLICATE.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-123">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before REPLICATE performs its operation.</span></span> <span data-ttu-id="d6e2a-124">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-124">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="d6e2a-125">Дополнительные сведения см. в разделах [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md) и [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="d6e2a-125">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="d6e2a-126">Функция REPLICATE возвращает NULL, если значение любого из аргументов равно NULL.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-126">REPLICATE returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="d6e2a-127">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="d6e2a-127">Expression Examples</span></span>  
 <span data-ttu-id="d6e2a-128">Этот пример реплицирует строковый литерал три раза.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-128">This example replicates a string literal three times.</span></span> <span data-ttu-id="d6e2a-129">Результат — «Mountain BikeMountain BikeMountain Bike».</span><span class="sxs-lookup"><span data-stu-id="d6e2a-129">The return result is "Mountain BikeMountain BikeMountain Bike".</span></span>  
  
```  
REPLICATE("Mountain Bike", 3)  
```  
  
 <span data-ttu-id="d6e2a-130">Этот пример реплицирует значения в столбце **Name** значением из переменной **Times** .</span><span class="sxs-lookup"><span data-stu-id="d6e2a-130">This example replicates values in the **Name** column by the value in the **Times** variable.</span></span> <span data-ttu-id="d6e2a-131">Если **Times** равно 3 и **Name** равно «Touring Front Wheel», то результат будет — «Touring Front WheelTouring Front WheelTouring Front Wheel».</span><span class="sxs-lookup"><span data-stu-id="d6e2a-131">If **Times** is 3 and **Name** is Touring Front Wheel, the return result is Touring Front WheelTouring Front WheelTouring Front Wheel.</span></span>  
  
```  
REPLICATE(Name, @Times)  
```  
  
 <span data-ttu-id="d6e2a-132">Этот пример реплицирует значение в переменной **Name** значением из столбца **Times** .</span><span class="sxs-lookup"><span data-stu-id="d6e2a-132">This example replicates the value in the **Name** variable by the value in the **Times** column.</span></span> <span data-ttu-id="d6e2a-133">**Times** имеет нецелочисленный тип данных и выражение включает явное приведение к целочисленному типу данных.</span><span class="sxs-lookup"><span data-stu-id="d6e2a-133">**Times** has a non-integer data type and the expression includes an explicit cast to an integer data type.</span></span> <span data-ttu-id="d6e2a-134">Если **Name** содержит «Helmet» и **Times** равно 2, то результат будет — «HelmetHelmet».</span><span class="sxs-lookup"><span data-stu-id="d6e2a-134">If **Name** contains Helmet and **Times** is 2, the return result is "HelmetHelmet".</span></span>  
  
```  
REPLICATE(@Name, (DT_I4(Times))  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6e2a-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6e2a-135">See Also</span></span>  
 [<span data-ttu-id="d6e2a-136">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="d6e2a-136">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
