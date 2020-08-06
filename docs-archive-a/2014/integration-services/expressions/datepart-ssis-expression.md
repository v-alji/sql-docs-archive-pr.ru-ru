---
title: DATEPART (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEPART
- DATEPART function
ms.assetid: 3e590094-fc49-4144-805f-fdc1bf2fe509
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aed7146c74c6738ba979f422bd65b7e1b539e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731917"
---
# <a name="datepart-ssis-expression"></a><span data-ttu-id="a0c55-102">DATEPART (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="a0c55-102">DATEPART (SSIS Expression)</span></span>
  <span data-ttu-id="a0c55-103">Возвращает целое число, обозначающее раздел даты.</span><span class="sxs-lookup"><span data-stu-id="a0c55-103">Returns an integer representing a datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0c55-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0c55-104">Syntax</span></span>  
  
```  
  
DATEPART(datepart, date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="a0c55-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a0c55-105">Arguments</span></span>  
 <span data-ttu-id="a0c55-106">*datepart*</span><span class="sxs-lookup"><span data-stu-id="a0c55-106">*datepart*</span></span>  
 <span data-ttu-id="a0c55-107">Параметр, который указывает, для какой части даты вернуть новое значение.</span><span class="sxs-lookup"><span data-stu-id="a0c55-107">Is the parameter that specifies for which part of the date to return a new value.</span></span>  
  
 <span data-ttu-id="a0c55-108">*date*</span><span class="sxs-lookup"><span data-stu-id="a0c55-108">*date*</span></span>  
 <span data-ttu-id="a0c55-109">Выражение, возвращающее допустимую дату или строку в формате даты.</span><span class="sxs-lookup"><span data-stu-id="a0c55-109">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a0c55-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="a0c55-110">Result Types</span></span>  
 <span data-ttu-id="a0c55-111">DT_I4</span><span class="sxs-lookup"><span data-stu-id="a0c55-111">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0c55-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="a0c55-112">Remarks</span></span>  
 <span data-ttu-id="a0c55-113">DATEPART возвращает NULL при аргументе NULL.</span><span class="sxs-lookup"><span data-stu-id="a0c55-113">DATEPART returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="a0c55-114">Литерал даты должен быть явно приведен к одному из типов данных даты.</span><span class="sxs-lookup"><span data-stu-id="a0c55-114">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="a0c55-115">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a0c55-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="a0c55-116">В следующей таблице перечислены части дат и сокращения, распознаваемые средством оценки выражений.</span><span class="sxs-lookup"><span data-stu-id="a0c55-116">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span> <span data-ttu-id="a0c55-117">Имена частей даты обрабатываются без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="a0c55-117">Datepart names are not case sensitive.</span></span>  
  
|<span data-ttu-id="a0c55-118">часть_даты</span><span class="sxs-lookup"><span data-stu-id="a0c55-118">Datepart</span></span>|<span data-ttu-id="a0c55-119">Сокращения</span><span class="sxs-lookup"><span data-stu-id="a0c55-119">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="a0c55-120">Год</span><span class="sxs-lookup"><span data-stu-id="a0c55-120">Year</span></span>|<span data-ttu-id="a0c55-121">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="a0c55-121">yy, yyyy</span></span>|  
|<span data-ttu-id="a0c55-122">Квартал</span><span class="sxs-lookup"><span data-stu-id="a0c55-122">Quarter</span></span>|<span data-ttu-id="a0c55-123">qq, q</span><span class="sxs-lookup"><span data-stu-id="a0c55-123">qq, q</span></span>|  
|<span data-ttu-id="a0c55-124">Месяц</span><span class="sxs-lookup"><span data-stu-id="a0c55-124">Month</span></span>|<span data-ttu-id="a0c55-125">mm, m</span><span class="sxs-lookup"><span data-stu-id="a0c55-125">mm, m</span></span>|  
|<span data-ttu-id="a0c55-126">День года</span><span class="sxs-lookup"><span data-stu-id="a0c55-126">Dayofyear</span></span>|<span data-ttu-id="a0c55-127">dy, y</span><span class="sxs-lookup"><span data-stu-id="a0c55-127">dy, y</span></span>|  
|<span data-ttu-id="a0c55-128">День</span><span class="sxs-lookup"><span data-stu-id="a0c55-128">Day</span></span>|<span data-ttu-id="a0c55-129">dd, d</span><span class="sxs-lookup"><span data-stu-id="a0c55-129">dd, d</span></span>|  
|<span data-ttu-id="a0c55-130">Неделя</span><span class="sxs-lookup"><span data-stu-id="a0c55-130">Week</span></span>|<span data-ttu-id="a0c55-131">wk, ww</span><span class="sxs-lookup"><span data-stu-id="a0c55-131">wk, ww</span></span>|  
|<span data-ttu-id="a0c55-132">День недели</span><span class="sxs-lookup"><span data-stu-id="a0c55-132">Weekday</span></span>|<span data-ttu-id="a0c55-133">dw</span><span class="sxs-lookup"><span data-stu-id="a0c55-133">dw</span></span>|  
|<span data-ttu-id="a0c55-134">Час</span><span class="sxs-lookup"><span data-stu-id="a0c55-134">Hour</span></span>|<span data-ttu-id="a0c55-135">Hh</span><span class="sxs-lookup"><span data-stu-id="a0c55-135">Hh</span></span>|  
|<span data-ttu-id="a0c55-136">Минута</span><span class="sxs-lookup"><span data-stu-id="a0c55-136">Minute</span></span>|<span data-ttu-id="a0c55-137">mi, n</span><span class="sxs-lookup"><span data-stu-id="a0c55-137">mi, n</span></span>|  
|<span data-ttu-id="a0c55-138">Секунда</span><span class="sxs-lookup"><span data-stu-id="a0c55-138">Second</span></span>|<span data-ttu-id="a0c55-139">ss, s</span><span class="sxs-lookup"><span data-stu-id="a0c55-139">ss, s</span></span>|  
|<span data-ttu-id="a0c55-140">Миллисекунда</span><span class="sxs-lookup"><span data-stu-id="a0c55-140">Millisecond</span></span>|<span data-ttu-id="a0c55-141">Ms</span><span class="sxs-lookup"><span data-stu-id="a0c55-141">Ms</span></span>|  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="a0c55-142">Примеры выражений служб SSIS</span><span class="sxs-lookup"><span data-stu-id="a0c55-142">SSIS Expression Examples</span></span>  
 <span data-ttu-id="a0c55-143">Этот пример возвращает целое число, которое представляет месяц в литерале даты.</span><span class="sxs-lookup"><span data-stu-id="a0c55-143">This example returns the integer that represents the month in a date literal.</span></span> <span data-ttu-id="a0c55-144">Если формат даты «мм/дд/гггг», то этот пример возвращает 11.</span><span class="sxs-lookup"><span data-stu-id="a0c55-144">If the date is in mm/dd/yyyy" format, this example returns 11.</span></span>  
  
```  
DATEPART("month", (DT_DBTIMESTAMP)"11/04/2002")  
```  
  
 <span data-ttu-id="a0c55-145">Этот пример возвращает целое число, представляющее день в столбце **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="a0c55-145">This example returns the integer that represents the day in the **ModifiedDate** column.</span></span>  
  
```  
DATEPART("dd", ModifiedDate)  
```  
  
 <span data-ttu-id="a0c55-146">Этот пример возвращает целое число, представляющее год в текущей дате.</span><span class="sxs-lookup"><span data-stu-id="a0c55-146">This example returns the integer that represents the year of the current date.</span></span>  
  
```  
DATEPART("yy",GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0c55-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0c55-147">See Also</span></span>  
 <span data-ttu-id="a0c55-148">[DATEADD (выражение служб SSIS)](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="a0c55-148">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="a0c55-149">[DATEDIFF (выражение служб SSIS)](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="a0c55-149">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="a0c55-150">[DAY (выражение служб SSIS)](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="a0c55-150">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="a0c55-151">[MONTH (выражение служб SSIS)](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="a0c55-151">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="a0c55-152">[YEAR (выражение служб SSIS)](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="a0c55-152">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="a0c55-153">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="a0c55-153">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
