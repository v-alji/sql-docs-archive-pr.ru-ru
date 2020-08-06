---
title: GETDATE (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- current date
- GETDATE function
- dates [Integration Services], GETDATE
ms.assetid: 6d20ec93-3244-4d63-baf6-70eff7bd598c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0acb384a8c3c3dfdae55c7172f341f9e32765e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658316"
---
# <a name="getdate-ssis-expression"></a><span data-ttu-id="b4058-102">GETDATE (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="b4058-102">GETDATE (SSIS Expression)</span></span>
  <span data-ttu-id="b4058-103">Возвращает текущее системное время в формате DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="b4058-103">Returns the current date of the system in a DT_DBTIMESTAMP format.</span></span> <span data-ttu-id="b4058-104">Функция GETDATE не имеет аргументов.</span><span class="sxs-lookup"><span data-stu-id="b4058-104">The GETDATE function takes no arguments.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4058-105">Длина строки результата, возвращаемой функцией GETDATE, равна 29 символам.</span><span class="sxs-lookup"><span data-stu-id="b4058-105">The length of the return result from the GETDATE function is 29 characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4058-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4058-106">Syntax</span></span>  
  
```  
  
GETDATE()  
```  
  
## <a name="arguments"></a><span data-ttu-id="b4058-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b4058-107">Arguments</span></span>  
 <span data-ttu-id="b4058-108">None</span><span class="sxs-lookup"><span data-stu-id="b4058-108">None</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b4058-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="b4058-109">Result Types</span></span>  
 <span data-ttu-id="b4058-110">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="b4058-110">DT_DBTIMESTAMP</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="b4058-111">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="b4058-111">Expression Examples</span></span>  
 <span data-ttu-id="b4058-112">Этот пример возвращает текущий год.</span><span class="sxs-lookup"><span data-stu-id="b4058-112">This example returns the year of the current date.</span></span>  
  
```  
DATEPART("year",GETDATE())  
```  
  
 <span data-ttu-id="b4058-113">Этот пример возвращает число дней от даты в столбце **ModifiedDate** до текущей даты.</span><span class="sxs-lookup"><span data-stu-id="b4058-113">This example returns the number of days between a date in the **ModifiedDate** column and the current date.</span></span>  
  
```  
DATEDIFF("dd",ModifiedDate,GETDATE())  
```  
  
 <span data-ttu-id="b4058-114">Этот пример добавляет три месяца к текущей дате.</span><span class="sxs-lookup"><span data-stu-id="b4058-114">This example adds three months to the current date.</span></span>  
  
```  
DATEADD("Month",3,GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4058-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4058-115">See Also</span></span>  
 <span data-ttu-id="b4058-116">[GETUTCDATE (выражение служб SSIS)](getutcdate-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b4058-116">[GETUTCDATE &#40;SSIS Expression&#41;](getutcdate-ssis-expression.md) </span></span>  
 [<span data-ttu-id="b4058-117">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="b4058-117">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
