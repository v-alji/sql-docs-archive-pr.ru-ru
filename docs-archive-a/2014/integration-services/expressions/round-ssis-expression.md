---
title: ROUND (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- rounding expressions
- ROUND function [SSIS]
ms.assetid: 376f1947-4fc5-4611-ad86-823e4db1b468
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d77045787eafbc3dd402db9982d8d7a98190bc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732806"
---
# <a name="round-ssis-expression"></a><span data-ttu-id="c5340-102">ROUND (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="c5340-102">ROUND (SSIS Expression)</span></span>
  <span data-ttu-id="c5340-103">Возвращает числовое выражение, округленное до указанной длины или точности.</span><span class="sxs-lookup"><span data-stu-id="c5340-103">Returns a numeric expression that is rounded to the specified length or precision.</span></span> <span data-ttu-id="c5340-104">Параметр длины должен иметь целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="c5340-104">The length parameter must evaluate to an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5340-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5340-105">Syntax</span></span>  
  
```  
  
ROUND(numeric_expression,length)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c5340-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c5340-106">Arguments</span></span>  
 <span data-ttu-id="c5340-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="c5340-107">*numeric_expression*</span></span>  
 <span data-ttu-id="c5340-108">Является выражением допустимого числового типа.</span><span class="sxs-lookup"><span data-stu-id="c5340-108">Is an expression of a valid numeric type.</span></span> <span data-ttu-id="c5340-109">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c5340-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="c5340-110">*length*</span><span class="sxs-lookup"><span data-stu-id="c5340-110">*length*</span></span>  
 <span data-ttu-id="c5340-111">Является целочисленным выражением.</span><span class="sxs-lookup"><span data-stu-id="c5340-111">Is an integer expression.</span></span> <span data-ttu-id="c5340-112">Это точность, до которой должно быть округлено значение *numeric_expression* .</span><span class="sxs-lookup"><span data-stu-id="c5340-112">It is the precision to which *numeric_expression* is rounded.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c5340-113">Типы результата</span><span class="sxs-lookup"><span data-stu-id="c5340-113">Result Types</span></span>  
 <span data-ttu-id="c5340-114">Того же типа, что и *numeric*_*expression.*</span><span class="sxs-lookup"><span data-stu-id="c5340-114">The same type as *numeric*_*expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5340-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="c5340-115">Remarks</span></span>  
 <span data-ttu-id="c5340-116">Аргумент *length* должен иметь положительное целочисленное значение либо ноль.</span><span class="sxs-lookup"><span data-stu-id="c5340-116">The *length* argument must evaluate to a positive integer or zero.</span></span>  
  
 <span data-ttu-id="c5340-117">ROUND возвращает результат NULL, если аргумент имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c5340-117">ROUND returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c5340-118">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="c5340-118">Expression Examples</span></span>  
 <span data-ttu-id="c5340-119">Эти примеры округляют числовые величины до трех знаков.</span><span class="sxs-lookup"><span data-stu-id="c5340-119">These examples round numeric literals to a length of three.</span></span> <span data-ttu-id="c5340-120">Первый возвращенный результат — 137.1570, второй — 137.1580.</span><span class="sxs-lookup"><span data-stu-id="c5340-120">The first return result is 137.1570, the second 137.1580.</span></span>  
  
```  
ROUND(137.1574,3)  
ROUND(137.1575,3)  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5340-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="c5340-121">See Also</span></span>  
 [<span data-ttu-id="c5340-122">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="c5340-122">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
