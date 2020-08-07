---
title: SIGN (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- positive values [Integration Services]
- SIGN function
- negative values
ms.assetid: 1547db08-4329-4781-91c2-36898ed71b15
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a34992b0029cd378274e38ce4e37fcd313d2b788
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732801"
---
# <a name="sign-ssis-expression"></a><span data-ttu-id="adcef-102">SIGN (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="adcef-102">SIGN (SSIS Expression)</span></span>
  <span data-ttu-id="adcef-103">Возвращает знак числового выражения в виде положительного (+1), нулевого (0) или отрицательного (-1) числа.</span><span class="sxs-lookup"><span data-stu-id="adcef-103">Returns the positive (+1), negative (-1), or zero (0) sign of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adcef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adcef-104">Syntax</span></span>  
  
```  
  
SIGN(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="adcef-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="adcef-105">Arguments</span></span>  
 <span data-ttu-id="adcef-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="adcef-106">*numeric_expression*</span></span>  
 <span data-ttu-id="adcef-107">Является допустимым числовым выражением со знаком.</span><span class="sxs-lookup"><span data-stu-id="adcef-107">Is a valid signed numeric expression.</span></span> <span data-ttu-id="adcef-108">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="adcef-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="adcef-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="adcef-109">Result Types</span></span>  
 <span data-ttu-id="adcef-110">DT_I4</span><span class="sxs-lookup"><span data-stu-id="adcef-110">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adcef-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="adcef-111">Remarks</span></span>  
 <span data-ttu-id="adcef-112">Функция SIGN возвращает результат NULL, если аргумент имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="adcef-112">SIGN returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="adcef-113">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="adcef-113">Expression Examples</span></span>  
 <span data-ttu-id="adcef-114">Этот пример возвращает знак числового литерала.</span><span class="sxs-lookup"><span data-stu-id="adcef-114">This example returns the sign of a numeric literal.</span></span> <span data-ttu-id="adcef-115">Возвращается результат -1.</span><span class="sxs-lookup"><span data-stu-id="adcef-115">The return result is -1.</span></span>  
  
```  
SIGN(-123.45)  
```  
  
 <span data-ttu-id="adcef-116">Этот пример возвращает знак результата вычитания значения столбца **StandardCost** из значения столбца **DealerPrice** .</span><span class="sxs-lookup"><span data-stu-id="adcef-116">This example returns the sign of the result of subtracting the **StandardCost** column from the **DealerPrice** column.</span></span>  
  
```  
SIGN(DealerPrice - StandardCost)  
```  
  
## <a name="see-also"></a><span data-ttu-id="adcef-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="adcef-117">See Also</span></span>  
 [<span data-ttu-id="adcef-118">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="adcef-118">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
