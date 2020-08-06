---
title: DATEADD (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEADD
- dates [Integration Services]
- DATEADD function
ms.assetid: fa5c37b1-2ddc-4857-8f8e-f6d5643b654f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9feb288318bdf9705928cb930f175f5c170c384e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736638"
---
# <a name="dateadd-ssis-expression"></a><span data-ttu-id="de1c1-102">DATEADD (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="de1c1-102">DATEADD (SSIS Expression)</span></span>
  <span data-ttu-id="de1c1-103">Возвращает новое значение DT_DBTIMESTAMP после добавления числа, представляющего дату или интервал времени, к указанной части даты.</span><span class="sxs-lookup"><span data-stu-id="de1c1-103">Returns a new DT_DBTIMESTAMP value after adding a number that represents a date or time interval to the specified datepart in a date.</span></span> <span data-ttu-id="de1c1-104">Числовой параметр должен выражаться целым числом, а параметр даты — допустимой датой.</span><span class="sxs-lookup"><span data-stu-id="de1c1-104">The number parameter must evaluate to an integer, and the date parameter must evaluate to a valid date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de1c1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de1c1-105">Syntax</span></span>  
  
```  
  
DATEADD(datepart, number, date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="de1c1-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="de1c1-106">Arguments</span></span>  
 <span data-ttu-id="de1c1-107">*datepart*</span><span class="sxs-lookup"><span data-stu-id="de1c1-107">*datepart*</span></span>  
 <span data-ttu-id="de1c1-108">Параметр, задающий, к какому разделу даты следует прибавить число.</span><span class="sxs-lookup"><span data-stu-id="de1c1-108">Is the parameter that specifies which part of the date to add a number to.</span></span>  
  
 <span data-ttu-id="de1c1-109">*number*</span><span class="sxs-lookup"><span data-stu-id="de1c1-109">*number*</span></span>  
 <span data-ttu-id="de1c1-110">Значение, используемое для увеличения *datepart*.</span><span class="sxs-lookup"><span data-stu-id="de1c1-110">Is the value used to increment *datepart*.</span></span> <span data-ttu-id="de1c1-111">Оно должно быть целочисленным, т.е. известным при синтаксическом анализе выражения.</span><span class="sxs-lookup"><span data-stu-id="de1c1-111">The value must be an integer value that is known when the expression is parsed.</span></span>  
  
 <span data-ttu-id="de1c1-112">*date*</span><span class="sxs-lookup"><span data-stu-id="de1c1-112">*date*</span></span>  
 <span data-ttu-id="de1c1-113">Выражение, возвращающее допустимую дату или строку в формате даты.</span><span class="sxs-lookup"><span data-stu-id="de1c1-113">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="de1c1-114">Типы результата</span><span class="sxs-lookup"><span data-stu-id="de1c1-114">Result Types</span></span>  
 <span data-ttu-id="de1c1-115">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="de1c1-115">DT_DBTIMESTAMP</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de1c1-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="de1c1-116">Remarks</span></span>  
 <span data-ttu-id="de1c1-117">В следующей таблице перечислены части дат и сокращения, распознаваемые средством оценки выражений.</span><span class="sxs-lookup"><span data-stu-id="de1c1-117">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span> <span data-ttu-id="de1c1-118">Имена частей даты обрабатываются без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="de1c1-118">Datepart names are not case sensitive.</span></span>  
  
|<span data-ttu-id="de1c1-119">часть_даты</span><span class="sxs-lookup"><span data-stu-id="de1c1-119">Datepart</span></span>|<span data-ttu-id="de1c1-120">Сокращения</span><span class="sxs-lookup"><span data-stu-id="de1c1-120">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="de1c1-121">Год</span><span class="sxs-lookup"><span data-stu-id="de1c1-121">Year</span></span>|<span data-ttu-id="de1c1-122">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="de1c1-122">yy, yyyy</span></span>|  
|<span data-ttu-id="de1c1-123">Квартал</span><span class="sxs-lookup"><span data-stu-id="de1c1-123">Quarter</span></span>|<span data-ttu-id="de1c1-124">qq, q</span><span class="sxs-lookup"><span data-stu-id="de1c1-124">qq, q</span></span>|  
|<span data-ttu-id="de1c1-125">Месяц</span><span class="sxs-lookup"><span data-stu-id="de1c1-125">Month</span></span>|<span data-ttu-id="de1c1-126">mm, m</span><span class="sxs-lookup"><span data-stu-id="de1c1-126">mm, m</span></span>|  
|<span data-ttu-id="de1c1-127">День года</span><span class="sxs-lookup"><span data-stu-id="de1c1-127">Dayofyear</span></span>|<span data-ttu-id="de1c1-128">dy, y</span><span class="sxs-lookup"><span data-stu-id="de1c1-128">dy, y</span></span>|  
|<span data-ttu-id="de1c1-129">День</span><span class="sxs-lookup"><span data-stu-id="de1c1-129">Day</span></span>|<span data-ttu-id="de1c1-130">dd, d</span><span class="sxs-lookup"><span data-stu-id="de1c1-130">dd, d</span></span>|  
|<span data-ttu-id="de1c1-131">Неделя</span><span class="sxs-lookup"><span data-stu-id="de1c1-131">Week</span></span>|<span data-ttu-id="de1c1-132">wk, ww</span><span class="sxs-lookup"><span data-stu-id="de1c1-132">wk, ww</span></span>|  
|<span data-ttu-id="de1c1-133">День недели</span><span class="sxs-lookup"><span data-stu-id="de1c1-133">Weekday</span></span>|<span data-ttu-id="de1c1-134">dw, w</span><span class="sxs-lookup"><span data-stu-id="de1c1-134">dw, w</span></span>|  
|<span data-ttu-id="de1c1-135">Час</span><span class="sxs-lookup"><span data-stu-id="de1c1-135">Hour</span></span>|<span data-ttu-id="de1c1-136">Hh</span><span class="sxs-lookup"><span data-stu-id="de1c1-136">Hh</span></span>|  
|<span data-ttu-id="de1c1-137">Минута</span><span class="sxs-lookup"><span data-stu-id="de1c1-137">Minute</span></span>|<span data-ttu-id="de1c1-138">mi, n</span><span class="sxs-lookup"><span data-stu-id="de1c1-138">mi, n</span></span>|  
|<span data-ttu-id="de1c1-139">Секунда</span><span class="sxs-lookup"><span data-stu-id="de1c1-139">Second</span></span>|<span data-ttu-id="de1c1-140">ss, s</span><span class="sxs-lookup"><span data-stu-id="de1c1-140">ss, s</span></span>|  
|<span data-ttu-id="de1c1-141">Миллисекунда</span><span class="sxs-lookup"><span data-stu-id="de1c1-141">Millisecond</span></span>|<span data-ttu-id="de1c1-142">Ms</span><span class="sxs-lookup"><span data-stu-id="de1c1-142">Ms</span></span>|  
  
 <span data-ttu-id="de1c1-143">Аргумент *number* должен быть доступен при синтаксическом анализе выражения.</span><span class="sxs-lookup"><span data-stu-id="de1c1-143">The *number* argument must be available when the expression is parsed.</span></span> <span data-ttu-id="de1c1-144">Он может быть константой или переменной.</span><span class="sxs-lookup"><span data-stu-id="de1c1-144">The argument can be a constant or a variable.</span></span> <span data-ttu-id="de1c1-145">Нельзя использовать значения столбцов, поскольку они неизвестны при синтаксическом анализе выражения.</span><span class="sxs-lookup"><span data-stu-id="de1c1-145">You cannot use column values because the values are not known when the expression is parsed.</span></span>  
  
 <span data-ttu-id="de1c1-146">Аргумент *datepart* необходимо заключать в кавычки.</span><span class="sxs-lookup"><span data-stu-id="de1c1-146">The *datepart* argument must be enclosed by quotation marks.</span></span>  
  
 <span data-ttu-id="de1c1-147">Литерал даты должен быть явно приведен к одному из типов данных даты.</span><span class="sxs-lookup"><span data-stu-id="de1c1-147">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="de1c1-148">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="de1c1-148">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="de1c1-149">Функция DATEADD возвращает результат NULL, если значением аргумента является NULL.</span><span class="sxs-lookup"><span data-stu-id="de1c1-149">DATEADD returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="de1c1-150">Ошибки возникают в тех случаях, когда дата недопустима, единица даты и времени не является строкой или приращение не является статическим целым числом.</span><span class="sxs-lookup"><span data-stu-id="de1c1-150">Errors occur if a date is invalid, if the date or time unit is not a string, or if the increment is not a static integer.</span></span>  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="de1c1-151">Примеры выражений служб SSIS</span><span class="sxs-lookup"><span data-stu-id="de1c1-151">SSIS Expression Examples</span></span>  
 <span data-ttu-id="de1c1-152">В этом примере добавляется один месяц к текущей дате.</span><span class="sxs-lookup"><span data-stu-id="de1c1-152">This example adds one month to the current date.</span></span>  
  
```  
DATEADD("Month", 1,GETDATE())  
```  
  
 <span data-ttu-id="de1c1-153">В этом примере добавляется 21 день к датам в столбце **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="de1c1-153">This example adds 21 days to the dates in the **ModifiedDate** column.</span></span>  
  
```  
DATEADD("day", 21, ModifiedDate)  
```  
  
 <span data-ttu-id="de1c1-154">В этом примере добавляются два года к литеральной дате.</span><span class="sxs-lookup"><span data-stu-id="de1c1-154">This example adds 2 years to a literal date.</span></span>  
  
```  
DATEADD("yyyy", 2, (DT_DBTIMESTAMP)"8/6/2003")  
```  
  
## <a name="see-also"></a><span data-ttu-id="de1c1-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="de1c1-155">See Also</span></span>  
 <span data-ttu-id="de1c1-156">[DATEDIFF (выражение служб SSIS)](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="de1c1-156">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="de1c1-157">[DATEPART (выражение служб SSIS)](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="de1c1-157">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="de1c1-158">[DAY (выражение служб SSIS)](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="de1c1-158">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="de1c1-159">[MONTH (выражение служб SSIS)](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="de1c1-159">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="de1c1-160">[YEAR (выражение служб SSIS)](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="de1c1-160">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="de1c1-161">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="de1c1-161">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
