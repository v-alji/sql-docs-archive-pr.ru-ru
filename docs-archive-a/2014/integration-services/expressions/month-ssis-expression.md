---
title: MONTH (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], MONTH
- MONTH function
ms.assetid: b5a47a11-c2ef-49bd-bd70-235632ff7bf6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d1f56906b4d25f2ba01f54fbdbc404d2c9ae4704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658911"
---
# <a name="month-ssis-expression"></a><span data-ttu-id="4d937-102">MONTH (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="4d937-102">MONTH (SSIS Expression)</span></span>
  <span data-ttu-id="4d937-103">Возвращает целое число, представляющее месяц указанной даты.</span><span class="sxs-lookup"><span data-stu-id="4d937-103">Returns an integer that represents the month datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d937-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d937-104">Syntax</span></span>  
  
```  
  
MONTH(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="4d937-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4d937-105">Arguments</span></span>  
 <span data-ttu-id="4d937-106">*date*</span><span class="sxs-lookup"><span data-stu-id="4d937-106">*date*</span></span>  
 <span data-ttu-id="4d937-107">Является датой в любом формате дат.</span><span class="sxs-lookup"><span data-stu-id="4d937-107">Is a date in any date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4d937-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="4d937-108">Result Types</span></span>  
 <span data-ttu-id="4d937-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="4d937-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d937-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="4d937-110">Remarks</span></span>  
 <span data-ttu-id="4d937-111">Функция MONTH возвращает значение NULL, если значение аргумента NULL.</span><span class="sxs-lookup"><span data-stu-id="4d937-111">MONTH returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="4d937-112">Литерал даты должен быть явно приведен к одному из типов данных даты.</span><span class="sxs-lookup"><span data-stu-id="4d937-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="4d937-113">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="4d937-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d937-114">Проверка выражения завершается ошибкой при явном приведении литерала даты к одному из следующих типов данных: DT_DBTIMESTAMPOFFSET и DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="4d937-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="4d937-115">Использование функции MONTH более компактно, но эквивалентно использованию функции DATEPART(«Month», date).</span><span class="sxs-lookup"><span data-stu-id="4d937-115">Using the MONTH function is briefer but equivalent to using DATEPART("Month", date).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="4d937-116">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="4d937-116">Expression Examples</span></span>  
 <span data-ttu-id="4d937-117">В этом примере возвращается номер месяца из литерала даты.</span><span class="sxs-lookup"><span data-stu-id="4d937-117">This example returns the number of the month in a date literal.</span></span> <span data-ttu-id="4d937-118">Если дата имеет формат «мм/дд/гггг», то этот пример возвращает 11.</span><span class="sxs-lookup"><span data-stu-id="4d937-118">If the date is in "mm/dd/yyyy" format, this example returns 11.</span></span>  
  
```  
MONTH((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="4d937-119">В этом примере возвращается целое число, представляющее месяц в столбце **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="4d937-119">This example returns the integer that represents the month in the **ModifiedDate** column.</span></span>  
  
```  
MONTH(ModifiedDate)  
```  
  
 <span data-ttu-id="4d937-120">В этом примере возвращается целое число, представляющее месяц текущей даты.</span><span class="sxs-lookup"><span data-stu-id="4d937-120">This example returns the integer that represents the month of the current date.</span></span>  
  
```  
MONTH(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d937-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="4d937-121">See Also</span></span>  
 <span data-ttu-id="4d937-122">[DATEADD (выражение служб SSIS)](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4d937-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="4d937-123">[DATEDIFF (выражение служб SSIS)](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4d937-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="4d937-124">[DATEPART (выражение служб SSIS)](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4d937-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="4d937-125">[DAY (выражение служб SSIS)](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4d937-125">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="4d937-126">[YEAR (выражение служб SSIS)](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4d937-126">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="4d937-127">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="4d937-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
