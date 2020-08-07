---
title: UPPER (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- UPPER function
- converting lowercase to uppercase
- uppercase characters [Integration Services]
- lowercase characters
ms.assetid: d33985f7-1048-4023-83e4-274090acda78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 181e231d735a8e98cd2bce10c692e35668a686f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732753"
---
# <a name="upper-ssis-expression"></a><span data-ttu-id="f524f-102">UPPER (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="f524f-102">UPPER (SSIS Expression)</span></span>
  <span data-ttu-id="f524f-103">Возвращает символьное выражение после преобразования символов в нижнем регистре в символы верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="f524f-103">Returns a character expression after converting lowercase characters to uppercase characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f524f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f524f-104">Syntax</span></span>  
  
```  
  
UPPER(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="f524f-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f524f-105">Arguments</span></span>  
 <span data-ttu-id="f524f-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="f524f-106">*character_expression*</span></span>  
 <span data-ttu-id="f524f-107">Символьное выражение для преобразования в верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="f524f-107">Is a character expression to convert to uppercase characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f524f-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="f524f-108">Result Types</span></span>  
 <span data-ttu-id="f524f-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="f524f-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f524f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f524f-110">Remarks</span></span>  
 <span data-ttu-id="f524f-111">Функция UPPER работает только с типом данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="f524f-111">UPPER works only with the DT_WSTR data type.</span></span> <span data-ttu-id="f524f-112">Аргумент *character_expression* , являющийся строковым литералом или столбцом данных с типом данных DT_STR, неявно приведен к типу данных DT_WSTR до выполнения функции UPPER.</span><span class="sxs-lookup"><span data-stu-id="f524f-112">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before UPPER performs its operation.</span></span> <span data-ttu-id="f524f-113">Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="f524f-113">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="f524f-114">Дополнительные сведения см. в разделах [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md) и [Приведение (выражение служб SSIS)](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f524f-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="f524f-115">Функция UPPER возвращает значение NULL, если аргумент имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f524f-115">UPPER returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="f524f-116">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="f524f-116">Expression Examples</span></span>  
 <span data-ttu-id="f524f-117">Этот пример преобразует строковый литерал в верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="f524f-117">This example converts a string literal to uppercase characters.</span></span> <span data-ttu-id="f524f-118">Возвращаемый результат — «HELLO».</span><span class="sxs-lookup"><span data-stu-id="f524f-118">The return result is "HELLO".</span></span>  
  
```  
UPPER("hello")  
```  
  
 <span data-ttu-id="f524f-119">Этот пример преобразует первый символ столбца **FirstName** в символ верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="f524f-119">This example converts the first character in the **FirstName** column to an uppercase character.</span></span> <span data-ttu-id="f524f-120">Если значение **FirstName** — «anna», возвращается результат «A».</span><span class="sxs-lookup"><span data-stu-id="f524f-120">If **FirstName** is anna, the return result is "A".</span></span> <span data-ttu-id="f524f-121">Дополнительные сведения см. в разделе [SUBSTRING (выражение служб SSIS)](substring-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f524f-121">For more information, see [SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md).</span></span>  
  
```  
UPPER(SUBSTRING(FirstName, 1, 1))  
```  
  
 <span data-ttu-id="f524f-122">Этот пример преобразует значение переменной **PostalCode** в верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="f524f-122">This example converts the value in the **PostalCode** variable to uppercase characters.</span></span> <span data-ttu-id="f524f-123">Если значение **PostalCode** — «k4b1s2», возвращается результат «K4B1S2».</span><span class="sxs-lookup"><span data-stu-id="f524f-123">If **PostalCode** is k4b1s2, the return result is "K4B1S2".</span></span>  
  
```  
UPPER(@PostalCode)  
```  
  
## <a name="see-also"></a><span data-ttu-id="f524f-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="f524f-124">See Also</span></span>  
 <span data-ttu-id="f524f-125">[LOWER (выражение служб SSIS)](lower-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f524f-125">[LOWER &#40;SSIS Expression&#41;](lower-ssis-expression.md) </span></span>  
 [<span data-ttu-id="f524f-126">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="f524f-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
