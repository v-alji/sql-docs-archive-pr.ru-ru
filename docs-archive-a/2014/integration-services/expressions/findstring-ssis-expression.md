---
title: FINDSTRING (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- FINDSTRING function
ms.assetid: c83cb1b1-3c52-4496-b518-4c9253b9336d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 72f2ff21cb179ce565e60c6550b8ecc2618a5adb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658916"
---
# <a name="findstring-ssis-expression"></a><span data-ttu-id="e6cfa-102">FINDSTRING (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="e6cfa-102">FINDSTRING (SSIS Expression)</span></span>
  <span data-ttu-id="e6cfa-103">Возвращает местоположение заданного вхождения строки в символьном выражении.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-103">Returns the location of the specified occurrence of a string within a character expression.</span></span> <span data-ttu-id="e6cfa-104">Возвращаемый результат является относительным положением вхождения в выражении, нумерация символов которого начинается с единицы.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-104">The return result is the one-based index of the occurrence.</span></span> <span data-ttu-id="e6cfa-105">Значением параметра строки должно быть символьное выражение, а значением параметра вхождения должно быть целое число.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-105">The string parameter must evaluate to a character expression, and the occurrence parameter must evaluate to an integer.</span></span> <span data-ttu-id="e6cfa-106">Если строка не найдена, возвращается значение 0.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-106">If the string is not found, the return value is 0.</span></span> <span data-ttu-id="e6cfa-107">Если строка встречается меньшее количество раз, чем определено аргументом, то возвращается значение 0.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-107">If the string occurs fewer times than the occurrence argument specifies, the return value is 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6cfa-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6cfa-108">Syntax</span></span>  
  
```  
  
FINDSTRING(character_expression, searchstring, occurrence)  
```  
  
## <a name="arguments"></a><span data-ttu-id="e6cfa-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e6cfa-109">Arguments</span></span>  
 <span data-ttu-id="e6cfa-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="e6cfa-110">*character_expression*</span></span>  
 <span data-ttu-id="e6cfa-111">Символьная строка, в которой производится поиск.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-111">Is the character string to search in.</span></span>  
  
 <span data-ttu-id="e6cfa-112">*searchstring*</span><span class="sxs-lookup"><span data-stu-id="e6cfa-112">*searchstring*</span></span>  
 <span data-ttu-id="e6cfa-113">Искомая символьная строка.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-113">Is the character string to search for.</span></span>  
  
 <span data-ttu-id="e6cfa-114">*occurrence*</span><span class="sxs-lookup"><span data-stu-id="e6cfa-114">*occurrence*</span></span>  
 <span data-ttu-id="e6cfa-115">Целое число со знаком или без него, указывающее, какое по порядку вхождение *searchstring* следует искать.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-115">Is a signed or unsigned integer specifying which occurrence of *searchstring* to report.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e6cfa-116">Типы результата</span><span class="sxs-lookup"><span data-stu-id="e6cfa-116">Result Types</span></span>  
 <span data-ttu-id="e6cfa-117">DT_I4</span><span class="sxs-lookup"><span data-stu-id="e6cfa-117">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6cfa-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6cfa-118">Remarks</span></span>  
 <span data-ttu-id="e6cfa-119">Функция FINDSTRING работает только с типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-119">FINDSTRING works only with the DT_WSTR data type.</span></span>  <span data-ttu-id="e6cfa-120">Аргументы*character_expression* и *searchstring* , которые являются строковыми литералами или столбцами данных, содержащими данные типа DT_STR, неявно приводятся к типу данных DT_WSTR до того, как функция FINDSTRING выполнит свою операцию.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-120">*character_expression* and *searchstring* arguments that are string literals or data columns with the DT_STR data type are implicitly cast to the DT_WSTR data type before FINDSTRING performs its operation.</span></span> <span data-ttu-id="e6cfa-121">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-121">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="e6cfa-122">Дополнительные сведения см. в разделах [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md) и [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="e6cfa-122">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="e6cfa-123">Функция FINDSTRING возвращает NULL, если или *character_expression* , или *searchstring* равен NULL.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-123">FINDSTRING returns null if either *character_expression* or *searchstring* are null.</span></span>  
  
 <span data-ttu-id="e6cfa-124">Для получения относительного положения первого вхождения в аргументе *occurrence* следует использовать 1, для второго вхождения — 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-124">Use a value of 1 in the *occurrence* argument to get the index of the first occurrence, 2 for the second occurrence and so forth.</span></span>  
  
 <span data-ttu-id="e6cfa-125">Аргумент *occurrence* должен быть целым числом, значение которого больше 0.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-125">The *occurrence* must be an integer with a value greater than 0.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="e6cfa-126">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="e6cfa-126">Expression Examples</span></span>  
 <span data-ttu-id="e6cfa-127">В данном примере используется строковый литерал.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-127">This example uses a string literal.</span></span> <span data-ttu-id="e6cfa-128">Он возвращает значение 11.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-128">It returns the value 11.</span></span>  
  
```  
FINDSTRING("New York, NY, NY", "NY", 1)   
```  
  
 <span data-ttu-id="e6cfa-129">В данном примере используется строковый литерал.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-129">This example uses a string literal.</span></span> <span data-ttu-id="e6cfa-130">Так как строка «NY» встретилась меньше двух раз, то возвращается значение 0.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-130">Because the string "NY" occurs only two times, the return result is 0.</span></span>  
  
```  
FINDSTRING("New York, NY, NY", "NY", 3)   
```  
  
 <span data-ttu-id="e6cfa-131">В этом примере используется столбец **Name** .</span><span class="sxs-lookup"><span data-stu-id="e6cfa-131">This example uses the **Name** column.</span></span> <span data-ttu-id="e6cfa-132">Он возвращает местоположение значения n в столбце **Name** .</span><span class="sxs-lookup"><span data-stu-id="e6cfa-132">It returns the location of the value n in the **Name** column.</span></span> <span data-ttu-id="e6cfa-133">Возвращаемый результат зависит от значения в столбце **Name**.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-133">The return result varies depending on the value in **Name**.</span></span> <span data-ttu-id="e6cfa-134">Если **Name** содержит Anderson, функция возвращает значение 8.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-134">If **Name** contains Anderson, the function returns 8.</span></span>  
  
```  
FINDSTRING(Name,"n", 2)   
```  
  
 <span data-ttu-id="e6cfa-135">В этом примере используются столбцы **Name** и **Size** .</span><span class="sxs-lookup"><span data-stu-id="e6cfa-135">This example uses the **Name** and **Size** columns.</span></span> <span data-ttu-id="e6cfa-136">Он возвращает местоположение самого левого символа значения **Size** в столбце **Name** .</span><span class="sxs-lookup"><span data-stu-id="e6cfa-136">It returns the location of the leftmost character of the **Size** value in the **Name** column.</span></span> <span data-ttu-id="e6cfa-137">Возвращаемый результат зависит от значений столбца.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-137">The return result varies depending on column values.</span></span> <span data-ttu-id="e6cfa-138">Если **Name** содержит Mountain,500Red,42 и **Size** содержит 42, возвращаемый результат равен 17.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-138">If **Name** contains Mountain,500Red,42 and **Size** contains 42, the return result is 17.</span></span>  
  
```  
FINDSTRING(Name,Size,1)   
```  
  
## <a name="see-also"></a><span data-ttu-id="e6cfa-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6cfa-139">See Also</span></span>  
 <span data-ttu-id="e6cfa-140">[REPLACE (выражение служб SSIS)](replace-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e6cfa-140">[REPLACE &#40;SSIS Expression&#41;](replace-ssis-expression.md) </span></span>  
 [<span data-ttu-id="e6cfa-141">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="e6cfa-141">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
