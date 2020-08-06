---
title: DATEDIFF (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- DATEDIFF statement
- dates [Integration Services], DATEDIFF
ms.assetid: 449b327f-47c7-4709-8bc6-4ee9a35cc330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 33edf2a152f70bb8c5bbd1f69cb87354e099b246
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731921"
---
# <a name="datediff-ssis-expression"></a><span data-ttu-id="b43bc-102">DATEDIFF (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="b43bc-102">DATEDIFF (SSIS Expression)</span></span>
  <span data-ttu-id="b43bc-103">Возвращает числовое значение границ дат или времени между двумя указанными датами.</span><span class="sxs-lookup"><span data-stu-id="b43bc-103">Returns the number of date and time boundaries crossed between two specified dates.</span></span> <span data-ttu-id="b43bc-104">Параметр *datepart* указывает границы даты и времени, которые необходимо сравнить.</span><span class="sxs-lookup"><span data-stu-id="b43bc-104">The *datepart* parameter identifies which date and time boundaries to compare.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b43bc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b43bc-105">Syntax</span></span>  
  
```  
  
DATEDIFF(datepart, startdate, endate)  
```  
  
## <a name="arguments"></a><span data-ttu-id="b43bc-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b43bc-106">Arguments</span></span>  
 <span data-ttu-id="b43bc-107">*datepart*</span><span class="sxs-lookup"><span data-stu-id="b43bc-107">*datepart*</span></span>  
 <span data-ttu-id="b43bc-108">Параметр, который указывает, какую часть даты сравнивать и для какой вернуть значение.</span><span class="sxs-lookup"><span data-stu-id="b43bc-108">Is the parameter that specifies which part of the date to compare and return a value for.</span></span>  
  
 <span data-ttu-id="b43bc-109">*startdate*</span><span class="sxs-lookup"><span data-stu-id="b43bc-109">*startdate*</span></span>  
 <span data-ttu-id="b43bc-110">Начальная дата периода.</span><span class="sxs-lookup"><span data-stu-id="b43bc-110">Is the start date of the interval.</span></span>  
  
 <span data-ttu-id="b43bc-111">*endate*</span><span class="sxs-lookup"><span data-stu-id="b43bc-111">*endate*</span></span>  
 <span data-ttu-id="b43bc-112">Конечная дата периода.</span><span class="sxs-lookup"><span data-stu-id="b43bc-112">Is the end date of the interval.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b43bc-113">Типы результата</span><span class="sxs-lookup"><span data-stu-id="b43bc-113">Result Types</span></span>  
 <span data-ttu-id="b43bc-114">DT_I4</span><span class="sxs-lookup"><span data-stu-id="b43bc-114">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b43bc-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="b43bc-115">Remarks</span></span>  
 <span data-ttu-id="b43bc-116">В следующей таблице перечислены части дат и сокращения, распознаваемые средством оценки выражений.</span><span class="sxs-lookup"><span data-stu-id="b43bc-116">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span>  
  
|<span data-ttu-id="b43bc-117">часть_даты</span><span class="sxs-lookup"><span data-stu-id="b43bc-117">Datepart</span></span>|<span data-ttu-id="b43bc-118">Сокращения</span><span class="sxs-lookup"><span data-stu-id="b43bc-118">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="b43bc-119">Год</span><span class="sxs-lookup"><span data-stu-id="b43bc-119">Year</span></span>|<span data-ttu-id="b43bc-120">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="b43bc-120">yy, yyyy</span></span>|  
|<span data-ttu-id="b43bc-121">Квартал</span><span class="sxs-lookup"><span data-stu-id="b43bc-121">Quarter</span></span>|<span data-ttu-id="b43bc-122">qq, q</span><span class="sxs-lookup"><span data-stu-id="b43bc-122">qq, q</span></span>|  
|<span data-ttu-id="b43bc-123">Месяц</span><span class="sxs-lookup"><span data-stu-id="b43bc-123">Month</span></span>|<span data-ttu-id="b43bc-124">mm, m</span><span class="sxs-lookup"><span data-stu-id="b43bc-124">mm, m</span></span>|  
|<span data-ttu-id="b43bc-125">День года</span><span class="sxs-lookup"><span data-stu-id="b43bc-125">Dayofyear</span></span>|<span data-ttu-id="b43bc-126">dy, y</span><span class="sxs-lookup"><span data-stu-id="b43bc-126">dy, y</span></span>|  
|<span data-ttu-id="b43bc-127">День</span><span class="sxs-lookup"><span data-stu-id="b43bc-127">Day</span></span>|<span data-ttu-id="b43bc-128">dd, d</span><span class="sxs-lookup"><span data-stu-id="b43bc-128">dd, d</span></span>|  
|<span data-ttu-id="b43bc-129">Неделя</span><span class="sxs-lookup"><span data-stu-id="b43bc-129">Week</span></span>|<span data-ttu-id="b43bc-130">wk, ww</span><span class="sxs-lookup"><span data-stu-id="b43bc-130">wk, ww</span></span>|  
|<span data-ttu-id="b43bc-131">День недели</span><span class="sxs-lookup"><span data-stu-id="b43bc-131">Weekday</span></span>|<span data-ttu-id="b43bc-132">dw, w</span><span class="sxs-lookup"><span data-stu-id="b43bc-132">dw, w</span></span>|  
|<span data-ttu-id="b43bc-133">Час</span><span class="sxs-lookup"><span data-stu-id="b43bc-133">Hour</span></span>|<span data-ttu-id="b43bc-134">Hh</span><span class="sxs-lookup"><span data-stu-id="b43bc-134">Hh</span></span>|  
|<span data-ttu-id="b43bc-135">Минута</span><span class="sxs-lookup"><span data-stu-id="b43bc-135">Minute</span></span>|<span data-ttu-id="b43bc-136">mi, n</span><span class="sxs-lookup"><span data-stu-id="b43bc-136">mi, n</span></span>|  
|<span data-ttu-id="b43bc-137">Секунда</span><span class="sxs-lookup"><span data-stu-id="b43bc-137">Second</span></span>|<span data-ttu-id="b43bc-138">ss, s</span><span class="sxs-lookup"><span data-stu-id="b43bc-138">ss, s</span></span>|  
|<span data-ttu-id="b43bc-139">Миллисекунда</span><span class="sxs-lookup"><span data-stu-id="b43bc-139">Millisecond</span></span>|<span data-ttu-id="b43bc-140">Ms</span><span class="sxs-lookup"><span data-stu-id="b43bc-140">Ms</span></span>|  
  
 <span data-ttu-id="b43bc-141">DATEDIFF возвращает NULL, если хотя бы один аргумент имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b43bc-141">DATEDIFF returns a null result if any argument is null.</span></span>  
  
 <span data-ttu-id="b43bc-142">Литерал даты должен быть явно приведен к одному из типов данных даты.</span><span class="sxs-lookup"><span data-stu-id="b43bc-142">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="b43bc-143">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="b43bc-143">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="b43bc-144">Произойдет ошибка при передаче недопустимой даты, а также в случае, если единица времени или даты не является строкой или если дата начала либо конца не является датой.</span><span class="sxs-lookup"><span data-stu-id="b43bc-144">An error occurs if a date is not valid, if the date or time unit is not a string, if the start date is not a date, or if the end date is not a date.</span></span>  
  
 <span data-ttu-id="b43bc-145">Если конечная дата является более ранней, чем начальная, то функция возвращает отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="b43bc-145">If the end date is earlier than the start date, the function returns a negative number.</span></span> <span data-ttu-id="b43bc-146">Если начальные и конечные даты равны друг другу или находятся в одном интервале, то функция возвращает ноль.</span><span class="sxs-lookup"><span data-stu-id="b43bc-146">If the start and end dates are equal or fall within the same interval, the function returns zero.</span></span>  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="b43bc-147">Примеры выражений служб SSIS</span><span class="sxs-lookup"><span data-stu-id="b43bc-147">SSIS Expression Examples</span></span>  
 <span data-ttu-id="b43bc-148">Этот пример вычисляет количество дней между двумя литералами даты.</span><span class="sxs-lookup"><span data-stu-id="b43bc-148">This example calculates the number of days between two date literals.</span></span> <span data-ttu-id="b43bc-149">Если дата имеет формат «мм/дд/гггг», то эта функция возвращает 7.</span><span class="sxs-lookup"><span data-stu-id="b43bc-149">If the date is in "mm/dd/yyyy" format, the function returns 7.</span></span>  
  
```  
DATEDIFF("dd", (DT_DBTIMESTAMP)"8/1/2003", (DT_DBTIMESTAMP)"8/8/2003")  
```  
  
 <span data-ttu-id="b43bc-150">Этот пример возвращает количество месяцев между литералом даты и текущей датой.</span><span class="sxs-lookup"><span data-stu-id="b43bc-150">This example returns the number of months between a date literal and the current date.</span></span>  
  
```  
DATEDIFF("mm", (DT_DBTIMESTAMP)"8/1/2003",GETDATE())  
```  
  
 <span data-ttu-id="b43bc-151">Этот пример возвращает количество недель между датой в столбце **ModifiedDate** и переменной **YearEndDate** .</span><span class="sxs-lookup"><span data-stu-id="b43bc-151">This example returns the number of weeks between the date in the **ModifiedDate** column and the **YearEndDate** variable.</span></span> <span data-ttu-id="b43bc-152">Если **YearEndDate** имеет `date` тип данных, явное приведение не требуется.</span><span class="sxs-lookup"><span data-stu-id="b43bc-152">If **YearEndDate** has a `date` data type, no explicit casting is required.</span></span>  
  
```  
DATEDIFF("Week", ModifiedDate,@YearEndDate)  
```  
  
## <a name="see-also"></a><span data-ttu-id="b43bc-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="b43bc-153">See Also</span></span>  
 <span data-ttu-id="b43bc-154">[DATEADD (выражение служб SSIS)](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b43bc-154">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="b43bc-155">[DATEPART (выражение служб SSIS)](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b43bc-155">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="b43bc-156">[DAY (выражение служб SSIS)](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b43bc-156">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="b43bc-157">[MONTH (выражение служб SSIS)](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b43bc-157">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="b43bc-158">[YEAR (выражение служб SSIS)](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b43bc-158">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="b43bc-159">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="b43bc-159">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
