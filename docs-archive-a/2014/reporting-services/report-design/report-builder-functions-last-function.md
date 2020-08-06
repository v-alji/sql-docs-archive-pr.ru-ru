---
title: Функция Last (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 123b78a0-d6c9-4f78-b0e7-73b21854a250
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c343e72e476d4a717ca551eedeb0f02650479ca4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659428"
---
# <a name="last-function-report-builder-and-ssrs"></a><span data-ttu-id="4983d-102">Функция Last (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4983d-102">Last Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4983d-103">Возвращает последнее значение указанного выражения для заданной области.</span><span class="sxs-lookup"><span data-stu-id="4983d-103">Returns the last value in the given scope of the specified expression.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="4983d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4983d-104">Syntax</span></span>  
  
```  
  
Last(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4983d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4983d-105">Parameters</span></span>  
 <span data-ttu-id="4983d-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="4983d-106">*expression*</span></span>  
 <span data-ttu-id="4983d-107">(`Variant` или `Binary`) Выражение, к которому применяется статистическая обработка, например `=Fields!Fieldname.Value`.</span><span class="sxs-lookup"><span data-stu-id="4983d-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!Fieldname.Value`.</span></span>  
  
 <span data-ttu-id="4983d-108">*область*</span><span class="sxs-lookup"><span data-stu-id="4983d-108">*scope*</span></span>  
 <span data-ttu-id="4983d-109">(`String`) (Необязательно) Имя набора данных, области данных или группы, содержащей элементы отчета, к которым применяется статистическая функция.</span><span class="sxs-lookup"><span data-stu-id="4983d-109">(`String`) (Optional) The name of a dataset, data region, or group that contains the report items to which to apply the function.</span></span> <span data-ttu-id="4983d-110">Если аргумент *scope* не задан, используется текущая область.</span><span class="sxs-lookup"><span data-stu-id="4983d-110">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="4983d-111">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="4983d-111">Return Type</span></span>  
 <span data-ttu-id="4983d-112">Определяется типом выражения.</span><span class="sxs-lookup"><span data-stu-id="4983d-112">Determined by the type of expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4983d-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="4983d-113">Remarks</span></span>  
 <span data-ttu-id="4983d-114">Функция `Last` возвращает конечное значение в набор данных после сортировки и фильтрации, примененных к заданной области.</span><span class="sxs-lookup"><span data-stu-id="4983d-114">The `Last` function returns the final value in a set of data after all sorting and filtering have been applied at the specified scope.</span></span>  
  
 <span data-ttu-id="4983d-115">Функция `Last` не может использоваться в критериях фильтра группирования с какой-либо областью, кроме текущей области (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4983d-115">The `Last` function cannot be used in group filter expressions with anything except the current (default) scope.</span></span>  
  
 <span data-ttu-id="4983d-116">Также можно использовать `Last` в верхнем колонтитуле страницы для возвращения последнего значения из коллекции `ReportItems` для страницы, чтобы произвести словарные заголовки в первой и последней записях страницы.</span><span class="sxs-lookup"><span data-stu-id="4983d-116">You can also use `Last` in a page header to return the last value from the `ReportItems` collection for a page in order to produce dictionary-style headings that display the first and last entries on a page.</span></span>  
  
 <span data-ttu-id="4983d-117">Значение *scope* должно быть строковой константой и не может быть выражением.</span><span class="sxs-lookup"><span data-stu-id="4983d-117">The value of *scope* must be a string constant andcannot be an expression.</span></span> <span data-ttu-id="4983d-118">Для внешних агрегатов и агрегатов, в которых не задаются другие агрегаты, параметр *scope* должен ссылаться не текущую область или включающую область.</span><span class="sxs-lookup"><span data-stu-id="4983d-118">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="4983d-119">Для агрегатов, содержащих агрегаты, во вложенных агрегатах может указываться дочерняя область.</span><span class="sxs-lookup"><span data-stu-id="4983d-119">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="4983d-120">*Expression* может содержать вызовы вложенных агрегатных функций со следующими условиями и исключениями.</span><span class="sxs-lookup"><span data-stu-id="4983d-120">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="4983d-121">Параметр*Scope* для вложенных агрегатов должен совпадать с областью внешнего агрегата или входить в нее.</span><span class="sxs-lookup"><span data-stu-id="4983d-121">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="4983d-122">Одна область из всех уникальных областей в выражении должна быть дочерней относительно всех других областей.</span><span class="sxs-lookup"><span data-stu-id="4983d-122">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="4983d-123">Параметр*Scope* для вложенных агрегатов не может быть именем набора данных.</span><span class="sxs-lookup"><span data-stu-id="4983d-123">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="4983d-124">*Выражение* не должно содержать `First` `Last` функции,, `Previous` или `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="4983d-124">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="4983d-125">*Expression* не может содержать вложенные агрегаты, в которых указан параметр *recursive*.</span><span class="sxs-lookup"><span data-stu-id="4983d-125">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="4983d-126">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="4983d-126">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="4983d-127">Дополнительные сведения о рекурсивных агрегатах см. в разделе [Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4983d-127">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4983d-128">Пример</span><span class="sxs-lookup"><span data-stu-id="4983d-128">Example</span></span>  
 <span data-ttu-id="4983d-129">Следующий пример кода предоставляет номер последнего продукта в группе или области данных `Category` .</span><span class="sxs-lookup"><span data-stu-id="4983d-129">The following code example returns the last product number in the `Category` group of a data region.</span></span>  
  
```  
=Last(Fields!ProductNumber.Value, "Category")  
```  
  
## <a name="see-also"></a><span data-ttu-id="4983d-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="4983d-130">See Also</span></span>  
 <span data-ttu-id="4983d-131">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4983d-131">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4983d-132">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4983d-132">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4983d-133">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4983d-133">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4983d-134">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4983d-134">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
