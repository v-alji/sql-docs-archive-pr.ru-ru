---
title: CODEPOINT (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CODEPOINT function
- leftmost character of expression
ms.assetid: 0783d05e-7f35-42fb-a2c4-9621c46effd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bf05cc0838763ba9e22707af57892133d449da07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655273"
---
# <a name="codepoint-ssis-expression"></a><span data-ttu-id="f2f09-102">CODEPOINT (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="f2f09-102">CODEPOINT (SSIS Expression)</span></span>
  <span data-ttu-id="f2f09-103">Возвращает кодовую точку в Юникоде крайнего левого символа указанного символьного выражения.</span><span class="sxs-lookup"><span data-stu-id="f2f09-103">Returns the Unicode code point of the leftmost character of a character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f09-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2f09-104">Syntax</span></span>  
  
```  
  
CODEPOINT(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="f2f09-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f2f09-105">Arguments</span></span>  
 <span data-ttu-id="f2f09-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="f2f09-106">*character_expression*</span></span>  
 <span data-ttu-id="f2f09-107">Символьное выражение, чей крайний левый символ будет вычислен.</span><span class="sxs-lookup"><span data-stu-id="f2f09-107">Is a character expression whose leftmost character will be evaluated.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f2f09-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="f2f09-108">Result Types</span></span>  
 <span data-ttu-id="f2f09-109">DT_UI2</span><span class="sxs-lookup"><span data-stu-id="f2f09-109">DT_UI2</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2f09-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f2f09-110">Remarks</span></span>  
 <span data-ttu-id="f2f09-111">Параметр*character_expression* должен иметь тип данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="f2f09-111">*character_expression* must have the DT_WSTR data type.</span></span>  
  
 <span data-ttu-id="f2f09-112">Функция CODEPOINT возвращает результат NULL, если параметр *character_expression* выражен значением NULL или пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="f2f09-112">CODEPOINT returns a null result if *character_expression* is null or an empty string.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="f2f09-113">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="f2f09-113">Expression Examples</span></span>  
 <span data-ttu-id="f2f09-114">В данном примере используется строковый литерал.</span><span class="sxs-lookup"><span data-stu-id="f2f09-114">This example uses a string literal.</span></span> <span data-ttu-id="f2f09-115">Возвращенный результат 77 — кодовая точка Юникод для M.</span><span class="sxs-lookup"><span data-stu-id="f2f09-115">The return result is 77, the Unicode code point for M.</span></span>  
  
```  
CODEPOINT("Mountain Bike")  
```  
  
 <span data-ttu-id="f2f09-116">В данном примере используется переменная.</span><span class="sxs-lookup"><span data-stu-id="f2f09-116">This example uses a variable.</span></span> <span data-ttu-id="f2f09-117">Если **Name** — «Touring Front Wheel», то возвращается результат 84 — код Юникод для T.</span><span class="sxs-lookup"><span data-stu-id="f2f09-117">If **Name** is Touring Front Wheel, the return result is 84, the Unicode code point for T.</span></span>  
  
```  
CODEPOINT(@Name)  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2f09-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2f09-118">See Also</span></span>  
 [<span data-ttu-id="f2f09-119">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="f2f09-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
