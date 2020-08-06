---
title: SUBSTRING (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SUBSTRING function
- part of expression returned [Integration Services]
ms.assetid: 3a46748a-f5f8-4a6c-9108-673666754068
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba53676bc6d13ed34892f48fca3b70372cb30604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732778"
---
# <a name="substring-ssis-expression"></a><span data-ttu-id="041fe-102">SUBSTRING (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="041fe-102">SUBSTRING (SSIS Expression)</span></span>
  <span data-ttu-id="041fe-103">Возвращает часть символьного выражения, начинающегося с указанной позиции и имеющего указанную длину.</span><span class="sxs-lookup"><span data-stu-id="041fe-103">Returns the part of a character expression that starts at the specified position and has the specified length.</span></span> <span data-ttu-id="041fe-104">Параметр *position* и параметр *length* должны иметь значение, выраженное целым числом.</span><span class="sxs-lookup"><span data-stu-id="041fe-104">The *position* parameter and the *length* parameter must evaluate to integers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="041fe-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="041fe-105">Syntax</span></span>  
  
```  
  
SUBSTRING(character_expression, position, length)  
```  
  
## <a name="arguments"></a><span data-ttu-id="041fe-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="041fe-106">Arguments</span></span>  
 <span data-ttu-id="041fe-107">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="041fe-107">*character_expression*</span></span>  
 <span data-ttu-id="041fe-108">Символьное выражение, из которого извлекаются символы.</span><span class="sxs-lookup"><span data-stu-id="041fe-108">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="041fe-109">*position*</span><span class="sxs-lookup"><span data-stu-id="041fe-109">*position*</span></span>  
 <span data-ttu-id="041fe-110">Является целым числом, указывающим, где начинается подстрока.</span><span class="sxs-lookup"><span data-stu-id="041fe-110">Is an integer that specifies where the substring begins.</span></span>  
  
 <span data-ttu-id="041fe-111">*length*</span><span class="sxs-lookup"><span data-stu-id="041fe-111">*length*</span></span>  
 <span data-ttu-id="041fe-112">Является целым числом, указывающим длину подстроки в виде числа символов.</span><span class="sxs-lookup"><span data-stu-id="041fe-112">Is an integer that specifies the length of the substring as number of characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="041fe-113">Типы результата</span><span class="sxs-lookup"><span data-stu-id="041fe-113">Result Types</span></span>  
 <span data-ttu-id="041fe-114">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="041fe-114">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="041fe-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="041fe-115">Remarks</span></span>  
 <span data-ttu-id="041fe-116">SUBSTRING использует однобазовый индекс.</span><span class="sxs-lookup"><span data-stu-id="041fe-116">SUBSTRING uses a one-based index.</span></span> <span data-ttu-id="041fe-117">Если параметр *position* имеет значение 1, то подстрока начинается с первого символа в значении параметра *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="041fe-117">If *position* is 1, the substring begins with the first character in *character_expression*.</span></span>  
  
 <span data-ttu-id="041fe-118">Функция SUBSTRING работает только типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="041fe-118">SUBSTRING works only with the DT_WSTR data type.</span></span> <span data-ttu-id="041fe-119">Аргумент *character_expression* , являющийся строковым литералом или столбцом данных с типом данных DT_STR, неявно приведен к типу данных DT_WSTR до выполнения функции SUBSTRING.</span><span class="sxs-lookup"><span data-stu-id="041fe-119">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before SUBSTRING performs its operation.</span></span> <span data-ttu-id="041fe-120">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="041fe-120">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="041fe-121">Дополнительные сведения см. в разделах [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md) и [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="041fe-121">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="041fe-122">Функция SUBSTRING возвращает нулевой результат при нулевом аргументе.</span><span class="sxs-lookup"><span data-stu-id="041fe-122">SUBSTRING returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="041fe-123">Переменные и столбцы могут использовать все аргументы выражения.</span><span class="sxs-lookup"><span data-stu-id="041fe-123">All arguments in the expression can use variables and columns.</span></span>  
  
 <span data-ttu-id="041fe-124">Аргумент *length* может превышать длину строки.</span><span class="sxs-lookup"><span data-stu-id="041fe-124">The *length* argument can exceed the length of the string.</span></span> <span data-ttu-id="041fe-125">В этом случае функция возвращает остаток строки.</span><span class="sxs-lookup"><span data-stu-id="041fe-125">In that case, the function returns the remainder of the string.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="041fe-126">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="041fe-126">Expression Examples</span></span>  
 <span data-ttu-id="041fe-127">Этот пример возвращает из строкового литерала два символа, начинающихся с 4.</span><span class="sxs-lookup"><span data-stu-id="041fe-127">This example returns two characters, beginning with character 4, from a string literal.</span></span> <span data-ttu-id="041fe-128">Возвращаемый результат — «ph».</span><span class="sxs-lookup"><span data-stu-id="041fe-128">The return result is "ph".</span></span>  
  
```  
SUBSTRING("elephant",4,2)  
```  
  
 <span data-ttu-id="041fe-129">Этот пример возвращает остаток строкового литерала, начиная с четвертого символа.</span><span class="sxs-lookup"><span data-stu-id="041fe-129">This example returns the remainder of a string literal, beginning at the fourth character.</span></span> <span data-ttu-id="041fe-130">Возвращаемый результат — «phant».</span><span class="sxs-lookup"><span data-stu-id="041fe-130">The return result is "phant".</span></span> <span data-ttu-id="041fe-131">Превышение аргументом *length* размера строки не является ошибкой.</span><span class="sxs-lookup"><span data-stu-id="041fe-131">It is not an error for the *length* argument to exceed the length of the string.</span></span>  
  
```  
SUBSTRING ("elephant",4,50)  
```  
  
 <span data-ttu-id="041fe-132">Этот пример возвращает первую букву из столбца **MiddleName** .</span><span class="sxs-lookup"><span data-stu-id="041fe-132">This example returns the first letter from the **MiddleName** column.</span></span>  
  
```  
SUBSTRING(MiddleName,1,1)  
```  
  
 <span data-ttu-id="041fe-133">Этот пример использует переменные в аргументах *position* и *length* .</span><span class="sxs-lookup"><span data-stu-id="041fe-133">This example uses variables in the *position* and *length* arguments.</span></span> <span data-ttu-id="041fe-134">Если **Start** равно 1, и **Length** равно 5, то функция возвращает первые пять символов столбца **Name** .</span><span class="sxs-lookup"><span data-stu-id="041fe-134">If **Start** is 1 and **Length** is 5, the function returns the first five characters in the **Name** column.</span></span>  
  
```  
SUBSTRING(Name,@Start,@Length)  
```  
  
 <span data-ttu-id="041fe-135">Этот пример возвращает четыре последних символа переменной **PostalCode** , начиная с шестого символа.</span><span class="sxs-lookup"><span data-stu-id="041fe-135">This example returns the last four characters from the **PostalCode** variable beginning at the sixth character.</span></span>  
  
```  
SUBSTRING (@PostalCode,6,4)  
```  
  
 <span data-ttu-id="041fe-136">Этот пример возвращает строку с нулевой длиной из строкового литерала.</span><span class="sxs-lookup"><span data-stu-id="041fe-136">This example returns a zero-length string from a string literal.</span></span>  
  
```  
SUBSTRING ("Redmond",4,0)  
```  
  
## <a name="see-also"></a><span data-ttu-id="041fe-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="041fe-137">See Also</span></span>  
 [<span data-ttu-id="041fe-138">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="041fe-138">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
