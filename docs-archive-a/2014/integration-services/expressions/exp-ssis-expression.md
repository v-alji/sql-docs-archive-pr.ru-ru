---
title: EXP (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- exponential functions
- EXP function
ms.assetid: 4cd96d3c-58c9-4a67-a6f6-b72758232912
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 150c92355ab3e0d3a028c98defe2e2fa9a1bf8ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665002"
---
# <a name="exp-ssis-expression"></a><span data-ttu-id="11922-102">EXP (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="11922-102">EXP (SSIS Expression)</span></span>
  <span data-ttu-id="11922-103">Возвращает значение экспоненты основания е числового выражения.</span><span class="sxs-lookup"><span data-stu-id="11922-103">Returns the exponent to base e of a numeric expression.</span></span> <span data-ttu-id="11922-104">Функция EXP дополняет действие функции LN и иногда называется обратным логарифмом.</span><span class="sxs-lookup"><span data-stu-id="11922-104">The EXP function complements the action of the LN function and is sometimes referred to as the antilogarithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11922-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11922-105">Syntax</span></span>  
  
```  
  
EXP(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="11922-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="11922-106">Arguments</span></span>  
 <span data-ttu-id="11922-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="11922-107">*numeric_expression*</span></span>  
 <span data-ttu-id="11922-108">Допустимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="11922-108">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="11922-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="11922-109">Result Types</span></span>  
 <span data-ttu-id="11922-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="11922-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11922-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="11922-111">Remarks</span></span>  
 <span data-ttu-id="11922-112">Перед вычислением степени числовое выражение приводится к типу данных DT_R8.</span><span class="sxs-lookup"><span data-stu-id="11922-112">The numeric expression is cast to the DT_R8 data type before the exponent is computed.</span></span> <span data-ttu-id="11922-113">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="11922-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="11922-114">Возвращаемый результат всегда является положительным числом.</span><span class="sxs-lookup"><span data-stu-id="11922-114">The return result is always a positive number.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="11922-115">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="11922-115">Expression Examples</span></span>  
 <span data-ttu-id="11922-116">В этих примерах функция EXP применяется к положительным значениям, отрицательным значениям и к нулю.</span><span class="sxs-lookup"><span data-stu-id="11922-116">These examples apply the EXP function to positive and negative values and to zero.</span></span>  
  
```  
EXP(74)  
```  
  
 <span data-ttu-id="11922-117">Возвращает 1.373382979540176E+32.</span><span class="sxs-lookup"><span data-stu-id="11922-117">Returns 1.373382979540176E+32.</span></span>  
  
```  
EXP(-27)  
```  
  
 <span data-ttu-id="11922-118">Возвращает 1.879528816539083E-12.</span><span class="sxs-lookup"><span data-stu-id="11922-118">Returns 1.879528816539083E-12.</span></span>  
  
```  
EXP(0)  
```  
  
 <span data-ttu-id="11922-119">Возвращает значение 1.</span><span class="sxs-lookup"><span data-stu-id="11922-119">Returns 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11922-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="11922-120">See Also</span></span>  
 <span data-ttu-id="11922-121">[LOG (выражение служб SSIS)](log-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="11922-121">[LOG &#40;SSIS Expression&#41;](log-ssis-expression.md) </span></span>  
 [<span data-ttu-id="11922-122">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="11922-122">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
