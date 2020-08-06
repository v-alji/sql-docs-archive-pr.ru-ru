---
title: FLOOR (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- largest integer less than or equal to expression
- FLOOR function [SSIS]
ms.assetid: 168084db-badd-40f2-87b4-1f5bc45c3e24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b638c9a7215d120c562e416cdecee463f031ad2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658917"
---
# <a name="floor-ssis-expression"></a><span data-ttu-id="fa6a9-102">FLOOR (выражение службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="fa6a9-102">FLOOR (SSIS Expression)</span></span>
  <span data-ttu-id="fa6a9-103">Возвращает наибольшее целое число, меньшее или равное числовому выражению.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-103">Returns the largest integer that is less than or equal to a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa6a9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa6a9-104">Syntax</span></span>  
  
```  
  
FLOOR(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="fa6a9-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fa6a9-105">Arguments</span></span>  
 <span data-ttu-id="fa6a9-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="fa6a9-106">*numeric_expression*</span></span>  
 <span data-ttu-id="fa6a9-107">Допустимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-107">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="fa6a9-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="fa6a9-108">Result Types</span></span>  
 <span data-ttu-id="fa6a9-109">Числовой тип данных выражения аргумента.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-109">The numeric data type of the argument expression.</span></span> <span data-ttu-id="fa6a9-110">Результат представляет собой целую часть вычисляемого значения и имеет тот же тип данных, что и *numeric_expression.*</span><span class="sxs-lookup"><span data-stu-id="fa6a9-110">The result is the integer portion of the calculated value in the same data type as *numeric_expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa6a9-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa6a9-111">Remarks</span></span>  
 <span data-ttu-id="fa6a9-112">Функция FLOOR возвращает NULL, если аргумент имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-112">FLOOR returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="fa6a9-113">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="fa6a9-113">Expression Examples</span></span>  
 <span data-ttu-id="fa6a9-114">В этих примерах функция FLOOR применяется к положительному, отрицательному и нулевому значениям.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-114">These examples apply the FLOOR function to positive, negative, and zero values.</span></span>  
  
```  
FLOOR(123.45)  
```  
  
 <span data-ttu-id="fa6a9-115">Возвращает значение 123,00</span><span class="sxs-lookup"><span data-stu-id="fa6a9-115">Returns 123.00</span></span>  
  
```  
FLOOR(-123.45)  
```  
  
 <span data-ttu-id="fa6a9-116">Возвращает значение −124,00</span><span class="sxs-lookup"><span data-stu-id="fa6a9-116">Returns -124.00</span></span>  
  
```  
FLOOR(0.00)  
```  
  
 <span data-ttu-id="fa6a9-117">Возвращает значение 0,00</span><span class="sxs-lookup"><span data-stu-id="fa6a9-117">Returns 0.00</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6a9-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="fa6a9-118">See Also</span></span>  
 <span data-ttu-id="fa6a9-119">[CEILING (выражение служб SSIS)](ceiling-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="fa6a9-119">[CEILING &#40;SSIS Expression&#41;](ceiling-ssis-expression.md) </span></span>  
 [<span data-ttu-id="fa6a9-120">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="fa6a9-120">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
