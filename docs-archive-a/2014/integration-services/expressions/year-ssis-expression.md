---
title: YEAR (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], YEAR
- YEAR function
ms.assetid: 9d88dead-ace8-44b9-b8e2-916c1842e155
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 181375d489fbf7abf0718386efacf4167ba555d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666718"
---
# <a name="year-ssis-expression"></a><span data-ttu-id="ffef8-102">YEAR (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="ffef8-102">YEAR (SSIS Expression)</span></span>
  <span data-ttu-id="ffef8-103">Возвращает целое число, представляющее год указанной даты.</span><span class="sxs-lookup"><span data-stu-id="ffef8-103">Returns an integer that represents the year datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffef8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffef8-104">Syntax</span></span>  
  
```  
  
YEAR(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="ffef8-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ffef8-105">Arguments</span></span>  
 <span data-ttu-id="ffef8-106">*date*</span><span class="sxs-lookup"><span data-stu-id="ffef8-106">*date*</span></span>  
 <span data-ttu-id="ffef8-107">Является датой в любом формате дат.</span><span class="sxs-lookup"><span data-stu-id="ffef8-107">Is a date in any date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ffef8-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="ffef8-108">Result Types</span></span>  
 <span data-ttu-id="ffef8-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="ffef8-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffef8-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="ffef8-110">Remarks</span></span>  
 <span data-ttu-id="ffef8-111">Функция YEAR возвращает значение NULL, если аргумент — NULL.</span><span class="sxs-lookup"><span data-stu-id="ffef8-111">YEAR returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="ffef8-112">Литерал даты должен быть явно приведен к одному из типов данных даты.</span><span class="sxs-lookup"><span data-stu-id="ffef8-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="ffef8-113">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ffef8-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ffef8-114">Проверка выражения завершается ошибкой при явном приведении литерала даты к одному из следующих типов данных: DT_DBTIMESTAMPOFFSET и DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="ffef8-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="ffef8-115">Функция YEAR является более компактным, но эквивалентным вариантом функции DATEPART("Year", date).</span><span class="sxs-lookup"><span data-stu-id="ffef8-115">Using the YEAR function is briefer but equivalent to using the DATEPART("Year", date) function.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ffef8-116">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="ffef8-116">Expression Examples</span></span>  
 <span data-ttu-id="ffef8-117">Этот пример возвращает год из литерала даты.</span><span class="sxs-lookup"><span data-stu-id="ffef8-117">This example returns the number of the year in a date literal.</span></span> <span data-ttu-id="ffef8-118">Если дата представлена в формате «мм/дд/гггг», то результатом данного примера будет «2002».</span><span class="sxs-lookup"><span data-stu-id="ffef8-118">If the date is in mm/dd/yyyy format, this example returns "2002".</span></span>  
  
```  
YEAR((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="ffef8-119">Этот пример возвращает целое число, которое представляет собой год столбца **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="ffef8-119">This example returns the integer that represents the year in the **ModifiedDate** column.</span></span>  
  
```  
YEAR(ModifiedDate)  
```  
  
 <span data-ttu-id="ffef8-120">Этот пример возвращает целое число, представляющее год в текущей дате.</span><span class="sxs-lookup"><span data-stu-id="ffef8-120">This example returns the integer that represents the year of the current date.</span></span>  
  
```  
YEAR(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="ffef8-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="ffef8-121">See Also</span></span>  
 <span data-ttu-id="ffef8-122">[DATEADD (выражение служб SSIS)](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ffef8-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="ffef8-123">[DATEDIFF (выражение служб SSIS)](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ffef8-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="ffef8-124">[DATEPART (выражение служб SSIS)](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ffef8-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="ffef8-125">[DAY (выражение служб SSIS)](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ffef8-125">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="ffef8-126">[MONTH (выражение служб SSIS)](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ffef8-126">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 [<span data-ttu-id="ffef8-127">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="ffef8-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
