---
title: ABS (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ABS function
- absolute positive value
ms.assetid: 156747f6-e016-44cf-9a9f-ae8e4a1b4f17
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f429dda94282646ef769a1c393f9fa54b56e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666197"
---
# <a name="abs-ssis-expression"></a><span data-ttu-id="76944-102">ABS (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="76944-102">ABS (SSIS Expression)</span></span>
  <span data-ttu-id="76944-103">Возвращает абсолютное положительное значение числового выражения.</span><span class="sxs-lookup"><span data-stu-id="76944-103">Returns the absolute, positive value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76944-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76944-104">Syntax</span></span>  
  
```  
  
ABS(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="76944-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="76944-105">Arguments</span></span>  
 <span data-ttu-id="76944-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="76944-106">*numeric_expression*</span></span>  
 <span data-ttu-id="76944-107">Является числовым выражением со знаком или без знака.</span><span class="sxs-lookup"><span data-stu-id="76944-107">Is a signed or unsigned numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="76944-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="76944-108">Result Types</span></span>  
 <span data-ttu-id="76944-109">Тип данных числового выражения, переданного функции.</span><span class="sxs-lookup"><span data-stu-id="76944-109">The data type of the numeric expression submitted to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76944-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="76944-110">Remarks</span></span>  
 <span data-ttu-id="76944-111">Функция ABS возвращает NULL, если аргумент имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="76944-111">ABS returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="76944-112">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="76944-112">Expression Examples</span></span>  
 <span data-ttu-id="76944-113">В этих примерах функция ABS применяется к положительному и отрицательному числам.</span><span class="sxs-lookup"><span data-stu-id="76944-113">These examples apply the ABS function to a positive and a negative number.</span></span> <span data-ttu-id="76944-114">В обоих случаях возвращается 1,23.</span><span class="sxs-lookup"><span data-stu-id="76944-114">Both return 1.23.</span></span>  
  
```  
ABS(-1.23)  
ABS(1.23)  
```  
  
 <span data-ttu-id="76944-115">В этом примере функция ABS применяется к разности значений переменных **HighTemperature** и **LowTempature**.</span><span class="sxs-lookup"><span data-stu-id="76944-115">This example applies the ABS function to an expression that subtracts values in the variables **HighTemperature** and **LowTempature**.</span></span>  
  
```  
ABS(@HighTemperature - @LowTemperature)  
```  
  
## <a name="see-also"></a><span data-ttu-id="76944-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="76944-116">See Also</span></span>  
 [<span data-ttu-id="76944-117">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="76944-117">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
