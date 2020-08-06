---
title: CEILING (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- smallest integer great than or equal to expression
- CEILING function [SSIS]
ms.assetid: c35bd4ee-1ab6-46ab-89a7-cf771527faa2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd2f9f455226925d6bf00842e80a8713e6c72771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669007"
---
# <a name="ceiling-ssis-expression"></a><span data-ttu-id="0b684-102">CEILING (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="0b684-102">CEILING (SSIS Expression)</span></span>
  <span data-ttu-id="0b684-103">Возвращает наименьшее целое число, большее или равное данному числовому выражению.</span><span class="sxs-lookup"><span data-stu-id="0b684-103">Returns the smallest integer that is greater than or equal to a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b684-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b684-104">Syntax</span></span>  
  
```  
  
CEILING(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="0b684-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0b684-105">Arguments</span></span>  
 <span data-ttu-id="0b684-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="0b684-106">*numeric_expression*</span></span>  
 <span data-ttu-id="0b684-107">Допустимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="0b684-107">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0b684-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="0b684-108">Result Types</span></span>  
 <span data-ttu-id="0b684-109">Тип данных числового выражения, переданного функции.</span><span class="sxs-lookup"><span data-stu-id="0b684-109">The data type of the numeric expression submitted to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b684-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="0b684-110">Remarks</span></span>  
 <span data-ttu-id="0b684-111">Функция CEILING возвращает NULL, если аргумент имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="0b684-111">CEILING returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="0b684-112">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="0b684-112">Expression Examples</span></span>  
 <span data-ttu-id="0b684-113">В этих примерах функция CEILING применяется к положительным, отрицательным значениям и к нулю.</span><span class="sxs-lookup"><span data-stu-id="0b684-113">These examples apply the CEILING function to positive, negative, and zero values.</span></span>  
  
```  
CEILING(123.74)  
```  
  
 <span data-ttu-id="0b684-114">Возвращает значение 124,00</span><span class="sxs-lookup"><span data-stu-id="0b684-114">Returns 124.00</span></span>  
  
```  
CEILING(-124.27)  
```  
  
 <span data-ttu-id="0b684-115">Возвращает значение −124,00</span><span class="sxs-lookup"><span data-stu-id="0b684-115">Returns -124.00</span></span>  
  
```  
CEILING(0.00)  
```  
  
 <span data-ttu-id="0b684-116">Возвращает значение 0,00</span><span class="sxs-lookup"><span data-stu-id="0b684-116">Returns 0.00</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b684-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b684-117">See Also</span></span>  
 <span data-ttu-id="0b684-118">[FLOOR (выражение служб SSIS)](floor-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="0b684-118">[FLOOR &#40;SSIS Expression&#41;](floor-ssis-expression.md) </span></span>  
 [<span data-ttu-id="0b684-119">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="0b684-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
