---
title: Функция RowNumber (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9d718ba8-d323-49fb-aac8-e7013a117b75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9f3d16188138c2f268305fddb092d56be870a3f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659411"
---
# <a name="rownumber-function-report-builder-and-ssrs"></a><span data-ttu-id="aec33-102">Функция RowNumber (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="aec33-102">RowNumber Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="aec33-103">Возвращает текущее количество строк в указанной области.</span><span class="sxs-lookup"><span data-stu-id="aec33-103">Returns a running count of the number of rows for the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="aec33-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aec33-104">Syntax</span></span>  
  
```  
  
RowNumber(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aec33-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aec33-105">Parameters</span></span>  
 <span data-ttu-id="aec33-106">*область*</span><span class="sxs-lookup"><span data-stu-id="aec33-106">*scope*</span></span>  
 <span data-ttu-id="aec33-107">(`String`) Имя набора данных, области данных, группирования или значение NULL (`Nothing` в [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), указывающее контекст, в котором вычисляется количество строк.</span><span class="sxs-lookup"><span data-stu-id="aec33-107">(`String`) The name of a dataset, data region, or group, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the context in which to evaluate the number of rows.</span></span> <span data-ttu-id="aec33-108">Значение `Nothing` указывает самый внешний контекст, обычно набор данных отчета.</span><span class="sxs-lookup"><span data-stu-id="aec33-108">`Nothing` specifies the outermost context, usually the report dataset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aec33-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="aec33-109">Remarks</span></span>  
 <span data-ttu-id="aec33-110">`RowNumber`Возвращает выполняемое значение количества строк в указанной области, так же как функция [RunningValue](report-builder-functions-runningvalue-function.md) возвращает выполняющееся значение агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="aec33-110">`RowNumber` returns a running value of the count of rows within the specified scope, just as [RunningValue](report-builder-functions-runningvalue-function.md) returns the running value of an aggregate function.</span></span> <span data-ttu-id="aec33-111">При указании области указывается и момент, когда счетчик строк сбрасывается в значение 1.</span><span class="sxs-lookup"><span data-stu-id="aec33-111">When you specify a scope, you specify when to reset the row count to 1.</span></span>  
  
 <span data-ttu-id="aec33-112">Значение*scope* не может быть выражением.</span><span class="sxs-lookup"><span data-stu-id="aec33-112">*scope* cannot be an expression.</span></span> <span data-ttu-id="aec33-113">Значение*scope* должно быть содержащей областью.</span><span class="sxs-lookup"><span data-stu-id="aec33-113">*scope* must be a containing scope.</span></span> <span data-ttu-id="aec33-114">Типичными областями — от самой внешней до самой внутренней — являются набор данных отчета, область данных, группы строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="aec33-114">Typical scopes, from the outermost to the innermost containment, are report dataset, data region, row groups or column groups.</span></span>  
  
 <span data-ttu-id="aec33-115">Чтобы увеличить значения по столбцам, укажите область, являющуюся именем группы столбцов.</span><span class="sxs-lookup"><span data-stu-id="aec33-115">To increment values across columns, specify a scope that is the name of a column group.</span></span> <span data-ttu-id="aec33-116">Чтобы увеличить числа в строках, укажите область, являющуюся именем группы строк.</span><span class="sxs-lookup"><span data-stu-id="aec33-116">To increment numbers down rows, specify a scope that is the name of a row group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aec33-117">Не поддерживается включение агрегатов, которые в одном выражении указывают и группу строк, и группу столбцов.</span><span class="sxs-lookup"><span data-stu-id="aec33-117">Including aggregates that specify both a row group and a column group in a single expression is not supported.</span></span>  
  
 <span data-ttu-id="aec33-118">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="aec33-118">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="code-example"></a><span data-ttu-id="aec33-119">Пример кода</span><span class="sxs-lookup"><span data-stu-id="aec33-119">Code Example</span></span>  
 <span data-ttu-id="aec33-120">Ниже приведено выражение, которое можно использовать в свойстве `BackgroundColor` строки сведений области данных табликса, чтобы изменять цвет строк со сведениями для каждой группы, всегда начиная с белого.</span><span class="sxs-lookup"><span data-stu-id="aec33-120">The following is an expression that you can use for the `BackgroundColor` property of a Tablix data region detail row to alternate the color of detail rows for each group, always beginning with White.</span></span>  
  
```  
=IIF(RowNumber("GroupbyCategory") Mod 2, "White", "PaleGreen")  
```  
  
## <a name="see-also"></a><span data-ttu-id="aec33-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="aec33-121">See Also</span></span>  
 <span data-ttu-id="aec33-122">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aec33-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aec33-123">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aec33-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aec33-124">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aec33-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="aec33-125">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="aec33-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
