---
title: RIGHT (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- RIGHT function
ms.assetid: 83e70e75-4be5-4783-a8cf-032f82afe16e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2584ee33ecbf0436c4e3dc6e92b957e60ae396ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732813"
---
# <a name="right-ssis-expression"></a><span data-ttu-id="7e103-102">RIGHT (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="7e103-102">RIGHT (SSIS Expression)</span></span>
  <span data-ttu-id="7e103-103">Возвращает указанное количество символов из крайней правой части заданного символьного выражения.</span><span class="sxs-lookup"><span data-stu-id="7e103-103">Returns the specified number of characters from the rightmost portion of the given character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e103-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e103-104">Syntax</span></span>  
  
```  
  
RIGHT(character_expression,integer_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7e103-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7e103-105">Arguments</span></span>  
 <span data-ttu-id="7e103-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="7e103-106">*character_expression*</span></span>  
 <span data-ttu-id="7e103-107">Символьное выражение, из которого извлекаются символы.</span><span class="sxs-lookup"><span data-stu-id="7e103-107">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="7e103-108">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="7e103-108">*integer_expression*</span></span>  
 <span data-ttu-id="7e103-109">Является целочисленным выражением, которое указывает количество возвращаемых символов.</span><span class="sxs-lookup"><span data-stu-id="7e103-109">Is an integer expression that indicates the number of characters to be returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7e103-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="7e103-110">Result Types</span></span>  
 <span data-ttu-id="7e103-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="7e103-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e103-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="7e103-112">Remarks</span></span>  
 <span data-ttu-id="7e103-113">Если *integer_expression* длиннее, чем *character_expression*, функция возвращает *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="7e103-113">If *integer_expression* is greater than the length of *character_expression*, the function returns *character_expression*.</span></span>  
  
 <span data-ttu-id="7e103-114">Если *integer_expression* равно нулю, функция возвращает строку нулевой длины.</span><span class="sxs-lookup"><span data-stu-id="7e103-114">If *integer_expression* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="7e103-115">Если *integer_expression* является отрицательным числом, функция возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="7e103-115">If *integer_expression* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="7e103-116">Аргумент *integer_expression* может принимать переменные и столбцы.</span><span class="sxs-lookup"><span data-stu-id="7e103-116">The *integer_expression* argument can take variables and columns.</span></span>  
  
 <span data-ttu-id="7e103-117">Функция RIGHT работает только с типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7e103-117">RIGHT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="7e103-118">Аргумент *character_expression* , являющийся строковым литералом или столбцом данных с типом данных DT_STR, неявно приведен к типу данных DT_WSTR до выполнения функции RIGHT.</span><span class="sxs-lookup"><span data-stu-id="7e103-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before RIGHT performs its operation.</span></span> <span data-ttu-id="7e103-119">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7e103-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="7e103-120">Дополнительные сведения см. в разделах [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md) и [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="7e103-120">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="7e103-121">RIGHT возвращает результат NULL, если любой из аргументов имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="7e103-121">RIGHT returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7e103-122">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="7e103-122">Expression Examples</span></span>  
 <span data-ttu-id="7e103-123">В следующем примере используется строковый литерал.</span><span class="sxs-lookup"><span data-stu-id="7e103-123">The following example uses a string literal.</span></span> <span data-ttu-id="7e103-124">Возвращаемым результатом является `"Bike"`.</span><span class="sxs-lookup"><span data-stu-id="7e103-124">The return result is `"Bike"`.</span></span>  
  
```  
RIGHT("Mountain Bike", 4)  
```  
  
 <span data-ttu-id="7e103-125">В следующем примере возвращается количество крайних правых символов, указанное в переменной `Times` из столбца `Name` .</span><span class="sxs-lookup"><span data-stu-id="7e103-125">The following example returns the number of rightmost characters that is specified in the `Times` variable, from the `Name` column.</span></span> <span data-ttu-id="7e103-126">Если `Name` имеет значение `Touring Front Wheel` , а `Times` равно 5, возвращается результат `"Wheel"`.</span><span class="sxs-lookup"><span data-stu-id="7e103-126">If `Name` is `Touring Front Wheel` and `Times` is 5, the return result is `"Wheel"`.</span></span>  
  
```  
RIGHT(Name, @Times)  
```  
  
 <span data-ttu-id="7e103-127">В следующем примере возвращается количество крайних правых символов, указанное в переменной `Times` из столбца `Name` .</span><span class="sxs-lookup"><span data-stu-id="7e103-127">The following example also returns the number of rightmost characters that is specified in the `Times` variable, from the `Name` column.</span></span> <span data-ttu-id="7e103-128">`Times` имеет нецелочисленный тип данных, и выражение включает явное приведение к типу данных DT_I2.</span><span class="sxs-lookup"><span data-stu-id="7e103-128">`Times` has a noninteger data type and the expression includes an explicit cast to the DT_I2 data type.</span></span> <span data-ttu-id="7e103-129">Если `Name` имеет значение `Touring Front Wheel` , а `Times` имеет значение `4.32`, возвращается результат `"heel"` , поскольку функция RIGHT округляет значение 4.32 до 4 и возвращает четыре крайних правых символа.</span><span class="sxs-lookup"><span data-stu-id="7e103-129">If `Name` is `Touring Front Wheel` and `Times` is `4.32`, the return result is `"heel"` because the RIGHT function converts the value of 4.32 to 4, and then returns the rightmost four characters.</span></span>  
  
```  
RIGHT(Name, (DT_I2)@Times))  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e103-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e103-130">See Also</span></span>  
 <span data-ttu-id="7e103-131">[LEFT (выражение SSIS)](left-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="7e103-131">[LEFT &#40;SSIS Expression&#41;](left-ssis-expression.md) </span></span>  
 [<span data-ttu-id="7e103-132">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="7e103-132">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
