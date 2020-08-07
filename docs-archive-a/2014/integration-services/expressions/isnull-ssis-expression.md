---
title: ISNULL (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- null values [Integration Services]
- ISNULL function
ms.assetid: 88dbf49e-1307-4dda-b9db-ff1632053550
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 51eda21b5c9b85c5f9cfd613d0d92df9729fe620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732829"
---
# <a name="isnull-ssis-expression"></a><span data-ttu-id="0ce9c-102">ISNULL (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="0ce9c-102">ISNULL (SSIS Expression)</span></span>
  <span data-ttu-id="0ce9c-103">Возвращает результат в виде логического выражения, в зависимости от того, имеет ли выражение значение NULL.</span><span class="sxs-lookup"><span data-stu-id="0ce9c-103">Returns a Boolean result based on whether an expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ce9c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ce9c-104">Syntax</span></span>  
  
```  
  
ISNULL(expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="0ce9c-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0ce9c-105">Arguments</span></span>  
 <span data-ttu-id="0ce9c-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="0ce9c-106">*expression*</span></span>  
 <span data-ttu-id="0ce9c-107">Допустимое выражение любого типа данных.</span><span class="sxs-lookup"><span data-stu-id="0ce9c-107">Is a valid expression of any data type.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0ce9c-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="0ce9c-108">Result Types</span></span>  
 <span data-ttu-id="0ce9c-109">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="0ce9c-109">DT_BOOL</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="0ce9c-110">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="0ce9c-110">Expression Examples</span></span>  
 <span data-ttu-id="0ce9c-111">Данный пример возвращает значение TRUE, если столбец **DiscontinuedDate** содержит значение NULL.</span><span class="sxs-lookup"><span data-stu-id="0ce9c-111">This example returns TRUE if the **DiscontinuedDate** column contains a null value.</span></span>  
  
```  
ISNULL(DiscontinuedDate)  
```  
  
 <span data-ttu-id="0ce9c-112">Данный пример возвращает «Unknown last name», если значение в столбце **LastName** равно NULL, в противном случае он возвращает значение из **LastName**.</span><span class="sxs-lookup"><span data-stu-id="0ce9c-112">This example returns "Unknown last name" if the value in the **LastName** column is null, otherwise it returns the value in **LastName**.</span></span>  
  
```  
ISNULL(LastName)? "Unknown last name":LastName  
```  
  
 <span data-ttu-id="0ce9c-113">Данный пример всегда возвращает значение TRUE, если столбец **DaysToManufacture** равен NULL, независимо от значения переменной в **AddDays**.</span><span class="sxs-lookup"><span data-stu-id="0ce9c-113">This example always returns TRUE if the **DaysToManufacture** column is null, regardless of the value of the variable **AddDays**.</span></span>  
  
```  
ISNULL(DaysToManufacture + @AddDays)  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ce9c-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="0ce9c-114">See Also</span></span>  
 <span data-ttu-id="0ce9c-115">[Функции (выражение служб SSIS)](functions-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="0ce9c-115">[Functions &#40;SSIS Expression&#41;](functions-ssis-expression.md) </span></span>  
 [<span data-ttu-id="0ce9c-116">COALESCE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0ce9c-116">COALESCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/coalesce-transact-sql)  
  
  
