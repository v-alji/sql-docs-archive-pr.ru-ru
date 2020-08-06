---
title: NULL (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- NULL function
- null values [Integration Services]
ms.assetid: df144237-3fbb-41ac-8624-efd92b6522b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e14cd51b4e245ca6984a4c62eae2b9d5536ab1f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655272"
---
# <a name="null-ssis-expression"></a><span data-ttu-id="5efe3-102">NULL (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="5efe3-102">NULL (SSIS Expression)</span></span>
  <span data-ttu-id="5efe3-103">Возвращает значение NULL запрошенного типа данных.</span><span class="sxs-lookup"><span data-stu-id="5efe3-103">Returns a null value of a requested data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5efe3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5efe3-104">Syntax</span></span>  
  
```  
  
NULL(typespec)  
```  
  
## <a name="arguments"></a><span data-ttu-id="5efe3-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5efe3-105">Arguments</span></span>  
 <span data-ttu-id="5efe3-106">*typespec*</span><span class="sxs-lookup"><span data-stu-id="5efe3-106">*typespec*</span></span>  
 <span data-ttu-id="5efe3-107">Допустимый тип данных.</span><span class="sxs-lookup"><span data-stu-id="5efe3-107">Is a valid data type.</span></span> <span data-ttu-id="5efe3-108">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5efe3-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5efe3-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="5efe3-109">Result Types</span></span>  
 <span data-ttu-id="5efe3-110">Любой допустимый тип данных со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="5efe3-110">Any valid data type with a null value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5efe3-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="5efe3-111">Remarks</span></span>  
 <span data-ttu-id="5efe3-112">Функция NULL возвращает NULL, если аргумент NULL.</span><span class="sxs-lookup"><span data-stu-id="5efe3-112">NULL returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="5efe3-113">Для некоторых типов данных чтобы запросить значения NULL, необходимы параметры.</span><span class="sxs-lookup"><span data-stu-id="5efe3-113">Parameters are required to request a null value for some data types.</span></span> <span data-ttu-id="5efe3-114">В следующей таблице приведены эти типы данных и их параметры.</span><span class="sxs-lookup"><span data-stu-id="5efe3-114">The following table lists these data types and their parameters.</span></span>  
  
|<span data-ttu-id="5efe3-115">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5efe3-115">Data type</span></span>|<span data-ttu-id="5efe3-116">Параметр</span><span class="sxs-lookup"><span data-stu-id="5efe3-116">Parameter</span></span>|<span data-ttu-id="5efe3-117">Пример</span><span class="sxs-lookup"><span data-stu-id="5efe3-117">Example</span></span>|  
|---------------|---------------|-------------|  
|<span data-ttu-id="5efe3-118">DT_STR</span><span class="sxs-lookup"><span data-stu-id="5efe3-118">DT_STR</span></span>|<span data-ttu-id="5efe3-119">*charcount*</span><span class="sxs-lookup"><span data-stu-id="5efe3-119">*charcount*</span></span><br /><br /> <span data-ttu-id="5efe3-120">*codepage*</span><span class="sxs-lookup"><span data-stu-id="5efe3-120">*codepage*</span></span>|<span data-ttu-id="5efe3-121">(DT_STR,30,1252) приводит 30 символов к типу данных DT_STR, используя кодовую страницу 1252.</span><span class="sxs-lookup"><span data-stu-id="5efe3-121">(DT_STR,30,1252) casts 30 characters to the DT_STR data type using the 1252 code page.</span></span>|  
|<span data-ttu-id="5efe3-122">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="5efe3-122">DT_WSTR</span></span>|<span data-ttu-id="5efe3-123">*charcount*</span><span class="sxs-lookup"><span data-stu-id="5efe3-123">*charcount*</span></span>|<span data-ttu-id="5efe3-124">(DT_WSTR,20) приводит 20 символов к типу данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="5efe3-124">(DT_WSTR,20) casts 20 characters to the DT_WSTR data type.</span></span>|  
|<span data-ttu-id="5efe3-125">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="5efe3-125">DT_BYTES</span></span>|<span data-ttu-id="5efe3-126">*bytecount*</span><span class="sxs-lookup"><span data-stu-id="5efe3-126">*bytecount*</span></span>|<span data-ttu-id="5efe3-127">(DT_BYTES,50) приводит 50 байт к типу данных DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="5efe3-127">(DT_BYTES,50) casts 50 bytes to the DT_BYTES data type.</span></span>|  
|<span data-ttu-id="5efe3-128">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="5efe3-128">DT_DECIMAL</span></span>|<span data-ttu-id="5efe3-129">*масштаб*</span><span class="sxs-lookup"><span data-stu-id="5efe3-129">*scale*</span></span>|<span data-ttu-id="5efe3-130">(DT_DECIMAL,2) приводит числовое значение к типу данных DT_DECIMAL, используя масштаб 2.</span><span class="sxs-lookup"><span data-stu-id="5efe3-130">(DT_DECIMAL,2) casts a numeric value to the DT_DECIMAL data type using a scale of 2.</span></span>|  
|<span data-ttu-id="5efe3-131">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="5efe3-131">DT_NUMERIC</span></span>|<span data-ttu-id="5efe3-132">*precision*</span><span class="sxs-lookup"><span data-stu-id="5efe3-132">*precision*</span></span><br /><br /> <span data-ttu-id="5efe3-133">*масштаб*</span><span class="sxs-lookup"><span data-stu-id="5efe3-133">*scale*</span></span>|<span data-ttu-id="5efe3-134">(DT_NUMERIC,10,3) приводит числовое значение к типу данных DT_NUMERIC, используя точность 10 и масштаб 3.</span><span class="sxs-lookup"><span data-stu-id="5efe3-134">(DT_NUMERIC,10,3) casts a numeric value to the DT_NUMERIC data type using a precision of 10 and a scale of 3.</span></span>|  
|<span data-ttu-id="5efe3-135">DT_TEXT</span><span class="sxs-lookup"><span data-stu-id="5efe3-135">DT_TEXT</span></span>|<span data-ttu-id="5efe3-136">*codepage*</span><span class="sxs-lookup"><span data-stu-id="5efe3-136">*codepage*</span></span>|<span data-ttu-id="5efe3-137">(DT_TEXT,1252) приводит значение к типу данных DT_TEXT, используя кодовую страницу 1252.</span><span class="sxs-lookup"><span data-stu-id="5efe3-137">(DT_TEXT,1252) casts a value to the DT_TEXT data type using the 1252 code page.</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="5efe3-138">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="5efe3-138">Expression Examples</span></span>  
 <span data-ttu-id="5efe3-139">Эти примеры возвращают значение NULL следующих типов данных: DT_STR, DT_DATE и DT_BOOL.</span><span class="sxs-lookup"><span data-stu-id="5efe3-139">These examples return the null value of the data types: DT_STR, DT_DATE, and DT_BOOL.</span></span>  
  
```  
NULL(DT_STR,10,1252)  
NULL(DT_DATE)  
NULL(DT_BOOL)  
```  
  
## <a name="see-also"></a><span data-ttu-id="5efe3-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="5efe3-140">See Also</span></span>  
 <span data-ttu-id="5efe3-141">[ISNULL (выражение служб SSIS)](null-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5efe3-141">[ISNULL &#40;SSIS Expression&#41;](null-ssis-expression.md) </span></span>  
 [<span data-ttu-id="5efe3-142">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="5efe3-142">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
