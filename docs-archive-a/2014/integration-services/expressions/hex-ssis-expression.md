---
title: HEX (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- hexadecimal data
- HEX function
ms.assetid: f5d471ee-aeef-421c-b6e1-55b9676c3842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 640ae38ec5d2cd5ffb448e9aebde5ba5ceba2684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736632"
---
# <a name="hex-ssis-expression"></a><span data-ttu-id="5e0cc-102">HEX (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="5e0cc-102">HEX (SSIS Expression)</span></span>
  <span data-ttu-id="5e0cc-103">Возвращает строку, представляющую собой шестнадцатеричное значение целого числа.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-103">Returns a string representing the hexadecimal value of an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e0cc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e0cc-104">Syntax</span></span>  
  
```  
  
HEX(integer_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="5e0cc-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5e0cc-105">Arguments</span></span>  
 <span data-ttu-id="5e0cc-106">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="5e0cc-106">*integer_expression*</span></span>  
 <span data-ttu-id="5e0cc-107">Целое со знаком или беззнаковое целое.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-107">Is a signed or unsigned integer.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5e0cc-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="5e0cc-108">Result Types</span></span>  
 <span data-ttu-id="5e0cc-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="5e0cc-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e0cc-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="5e0cc-110">Remarks</span></span>  
 <span data-ttu-id="5e0cc-111">HEX возвращает значение null, если *integer_expression* имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-111">HEX returns null if *integer_expression* is null.</span></span>  
  
 <span data-ttu-id="5e0cc-112">Аргумент *integer_expression* должен выдавать целое число.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-112">The *integer_expression* argument must evaluate to an integer.</span></span> <span data-ttu-id="5e0cc-113">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5e0cc-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="5e0cc-114">Возвращаемый результат не включает квалификаторы, например префикс 0х.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-114">The return result does not include qualifiers such as the 0x prefix.</span></span> <span data-ttu-id="5e0cc-115">Для включения префикса используйте оператор + (сцепление).</span><span class="sxs-lookup"><span data-stu-id="5e0cc-115">To include a prefix, use the + (Concatenate) operator.</span></span> <span data-ttu-id="5e0cc-116">Дополнительные сведения см. в разделе [+ (Объединение) (выражение SSIS)](concatenate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="5e0cc-116">For more information, see [+ &#40;Concatenate&#41; &#40;SSIS Expression&#41;](concatenate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="5e0cc-117">Буквы A–F, используемые в шестнадцатеричной нотации, записываются в верхнем регистре.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-117">The letters A - F, used in HEX notations, appear as uppercase characters.</span></span>  
  
 <span data-ttu-id="5e0cc-118">Длина возвращаемой строки для целых типов данных:</span><span class="sxs-lookup"><span data-stu-id="5e0cc-118">The length of the resulting string for integer data types is as follows:</span></span>  
  
-   <span data-ttu-id="5e0cc-119">DT_I1 и DT_UI1 возвращают строку не более 2 символов.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-119">DT_I1 and DT_UI1 return a string with a maximum length of 2.</span></span>  
  
-   <span data-ttu-id="5e0cc-120">DT_I2 и DT_UI2 возвращают строку не более 4 символов.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-120">DT_I2 and DT_UI2 return a string with a maximum length of 4.</span></span>  
  
-   <span data-ttu-id="5e0cc-121">DT_I4 и DT_UI4 возвращают строку не более 8 символов.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-121">DT_I4 and DT_UI4 return a string with a maximum length of 8.</span></span>  
  
-   <span data-ttu-id="5e0cc-122">DT_I8 и DT_UI8 возвращают строку длиной не более 16 символов.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-122">DT_I8 and DT_UI8 return a string with a maximum length of 16.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="5e0cc-123">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="5e0cc-123">Expression Examples</span></span>  
 <span data-ttu-id="5e0cc-124">В этом примере используется числовой литерал.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-124">This example uses a numeric literal.</span></span> <span data-ttu-id="5e0cc-125">Функция возвращает значение 190.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-125">The function returns the value 190.</span></span>  
  
```  
HEX(400)   
```  
  
 <span data-ttu-id="5e0cc-126">Этот пример использует столбец **ReorderPoint** .</span><span class="sxs-lookup"><span data-stu-id="5e0cc-126">This example uses the **ReorderPoint** column.</span></span> <span data-ttu-id="5e0cc-127">Тип данных этого столбца — `smallint`.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-127">The column data type is `smallint`.</span></span> <span data-ttu-id="5e0cc-128">Если значение **ReorderPoint** равно 750, функция возвращает 2EE.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-128">If **ReorderPoint** is 750, the function returns 2EE.</span></span>  
  
```  
HEX(ReorderPoint)   
```  
  
 <span data-ttu-id="5e0cc-129">Этот пример использует системную переменную **LocaleID**.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-129">This example uses **LocaleID**, a system variable.</span></span> <span data-ttu-id="5e0cc-130">Если значение **LocaleID** равно 1049, функция возвращает 419.</span><span class="sxs-lookup"><span data-stu-id="5e0cc-130">If **LocaleID** is 1033, the function returns 409.</span></span>  
  
```  
HEX(@LocaleID)  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e0cc-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="5e0cc-131">See Also</span></span>  
 [<span data-ttu-id="5e0cc-132">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="5e0cc-132">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
