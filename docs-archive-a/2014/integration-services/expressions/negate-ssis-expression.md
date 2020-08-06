---
title: '- (инверсия) (выражение служб SSIS) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '- (negative)'
- negative operator (-)
ms.assetid: f0118dfc-aced-4de2-953e-5ebf9c962b8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2a2d8ba292f2d24633598ab080ddf75ded5e8bd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735489"
---
# <a name="--negate-ssis-expression"></a><span data-ttu-id="46049-102">- (инверсия) (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="46049-102">- (Negate) (SSIS Expression)</span></span>
  <span data-ttu-id="46049-103">Инвертирует числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="46049-103">Negates a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46049-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46049-104">Syntax</span></span>  
  
```  
  
-numeric_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="46049-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="46049-105">Arguments</span></span>  
 <span data-ttu-id="46049-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="46049-106">*numeric_expression*</span></span>  
 <span data-ttu-id="46049-107">Любое допустимое выражение любого числового типа данных.</span><span class="sxs-lookup"><span data-stu-id="46049-107">Is any valid expression of any numeric data type.</span></span> <span data-ttu-id="46049-108">Поддерживаются только типы данных со знаком.</span><span class="sxs-lookup"><span data-stu-id="46049-108">Only signed numeric data types are supported.</span></span> <span data-ttu-id="46049-109">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="46049-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="46049-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="46049-110">Result Types</span></span>  
 <span data-ttu-id="46049-111">Возвращает тип данных *numeric_expression*.</span><span class="sxs-lookup"><span data-stu-id="46049-111">Returns the data type of *numeric_expression*.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="46049-112">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="46049-112">Expression Examples</span></span>  
 <span data-ttu-id="46049-113">В этом примере знак переменной **Counter** изменяется на противоположный, и к ней прибавляется число 50.</span><span class="sxs-lookup"><span data-stu-id="46049-113">This example negates the value of the **Counter** variable and adds the numeric literal 50.</span></span>  
  
```  
-@Counter + 50  
```  
  
## <a name="see-also"></a><span data-ttu-id="46049-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="46049-114">See Also</span></span>  
 <span data-ttu-id="46049-115">[Очередность и ассоциативность операторов](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="46049-115">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="46049-116">Операторы (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="46049-116">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
