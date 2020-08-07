---
title: DAY (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- DAY function
- dates [Integration Services], DAY
ms.assetid: d8447187-49df-45b7-a98e-142ad44fd3e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b7acac3f3949cbbd07adbe6382ea3d875f94cb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731913"
---
# <a name="day-ssis-expression"></a><span data-ttu-id="105ac-102">DAY (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="105ac-102">DAY (SSIS Expression)</span></span>
  <span data-ttu-id="105ac-103">Возвращает целое число, представляющее день указанной даты.</span><span class="sxs-lookup"><span data-stu-id="105ac-103">Returns an integer that represents the day datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="105ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="105ac-104">Syntax</span></span>  
  
```  
  
DAY(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="105ac-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="105ac-105">Arguments</span></span>  
 <span data-ttu-id="105ac-106">*date*</span><span class="sxs-lookup"><span data-stu-id="105ac-106">*date*</span></span>  
 <span data-ttu-id="105ac-107">Выражение, возвращающее допустимую дату или строку в формате даты.</span><span class="sxs-lookup"><span data-stu-id="105ac-107">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="105ac-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="105ac-108">Result Types</span></span>  
 <span data-ttu-id="105ac-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="105ac-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="105ac-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="105ac-110">Remarks</span></span>  
 <span data-ttu-id="105ac-111">Функция DAY возвращает значение NULL, если значение аргумента NULL.</span><span class="sxs-lookup"><span data-stu-id="105ac-111">DAY returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="105ac-112">Литерал даты должен быть явно приведен к одному из типов данных даты.</span><span class="sxs-lookup"><span data-stu-id="105ac-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="105ac-113">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="105ac-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="105ac-114">Проверка выражения завершается ошибкой при явном приведении литерала даты к одному из следующих типов данных: DT_DBTIMESTAMPOFFSET и DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="105ac-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="105ac-115">Использование функции DAY более компактно, но эквивалентно использованию функции DATEPART("Day", date).</span><span class="sxs-lookup"><span data-stu-id="105ac-115">Using the DAY function is briefer but equivalent to using DATEPART("Day", date).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="105ac-116">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="105ac-116">Expression Examples</span></span>  
 <span data-ttu-id="105ac-117">В этом примере возвращается номер дня из литерала даты.</span><span class="sxs-lookup"><span data-stu-id="105ac-117">This example returns the number of the day in a date literal.</span></span> <span data-ttu-id="105ac-118">Если дата имеет формат «мм/дд/гггг», будет возвращено значение 23.</span><span class="sxs-lookup"><span data-stu-id="105ac-118">If the date format is in "mm/dd/yyyy" format, this example returns 23.</span></span>  
  
```  
DAY((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="105ac-119">Этот пример возвращает целое число, представляющее день в столбце **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="105ac-119">This example returns the integer that represents the day in the **ModifiedDate** column.</span></span>  
  
```  
DAY(ModifiedDate)  
```  
  
 <span data-ttu-id="105ac-120">В этом примере возвращается целое число, представляющее день текущей даты.</span><span class="sxs-lookup"><span data-stu-id="105ac-120">This example returns the integer that represents the day of the current date.</span></span>  
  
```  
DAY(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="105ac-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="105ac-121">See Also</span></span>  
 <span data-ttu-id="105ac-122">[DATEADD (выражение служб SSIS)](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="105ac-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="105ac-123">[DATEDIFF (выражение служб SSIS)](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="105ac-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="105ac-124">[DATEPART (выражение служб SSIS)](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="105ac-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="105ac-125">[MONTH (выражение служб SSIS)](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="105ac-125">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="105ac-126">[YEAR (выражение служб SSIS)](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="105ac-126">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="105ac-127">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="105ac-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
