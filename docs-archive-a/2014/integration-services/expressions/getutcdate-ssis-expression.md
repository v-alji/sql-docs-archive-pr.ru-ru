---
title: GETUTCDATE (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], GETUTCDATE
- current date
- UTC time
- GETUTCDATE function
ms.assetid: 2282339c-c24f-493e-8e66-181ea8af5ad0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f157ab5641e521a42cb3c96c96446b31de5dfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732853"
---
# <a name="getutcdate-ssis-expression"></a><span data-ttu-id="154cb-102">GETUTCDATE (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="154cb-102">GETUTCDATE (SSIS Expression)</span></span>
  <span data-ttu-id="154cb-103">Возвращает текущую дату системы в формате времени UTC (универсальное время, или время по Гринвичу), используя формат DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="154cb-103">Returns the current date of the system in UTC time (Universal Time Coordinate or Greenwich Mean Time) using a DT_DBTIMESTAMP format.</span></span> <span data-ttu-id="154cb-104">Функция GETUTCDATE не имеет аргументов.</span><span class="sxs-lookup"><span data-stu-id="154cb-104">The GETUTCDATE function takes no arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="154cb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="154cb-105">Syntax</span></span>  
  
```  
  
GETUTCDATE()  
```  
  
## <a name="arguments"></a><span data-ttu-id="154cb-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="154cb-106">Arguments</span></span>  
 <span data-ttu-id="154cb-107">None</span><span class="sxs-lookup"><span data-stu-id="154cb-107">None</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="154cb-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="154cb-108">Result Types</span></span>  
 <span data-ttu-id="154cb-109">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="154cb-109">DT_DBTIMESTAMP</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="154cb-110">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="154cb-110">Expression Examples</span></span>  
 <span data-ttu-id="154cb-111">Этот пример возвращает год текущей даты времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="154cb-111">This example returns the year of the current date in UTC time.</span></span>  
  
```  
DATEPART("year",GETUTCDATE())  
```  
  
 <span data-ttu-id="154cb-112">Этот пример возвращает количество дней между датой в столбце **ModifiedDate** и текущей датой в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="154cb-112">This example returns the number of days between a date in the **ModifiedDate** column and the current UTC date.</span></span>  
  
```  
DATEDIFF("dd",ModifiedDate,GETUTCDATE())  
```  
  
 <span data-ttu-id="154cb-113">Этот пример добавляет три месяца к текущей дате в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="154cb-113">This example adds three months to the current UTC date.</span></span>  
  
```  
DATEADD("Month",3,GETUTCDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="154cb-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="154cb-114">See Also</span></span>  
 <span data-ttu-id="154cb-115">[GETDATE (выражение служб SSIS)](getdate-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="154cb-115">[GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md) </span></span>  
 [<span data-ttu-id="154cb-116">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="154cb-116">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
