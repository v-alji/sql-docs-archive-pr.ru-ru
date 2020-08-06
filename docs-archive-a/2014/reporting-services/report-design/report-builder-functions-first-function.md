---
title: Функция First (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d0914520-30c5-4d63-9b59-8d9342ed63b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2cd8578a1d9a17030d603457d4eaadf107316bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659431"
---
# <a name="first-function-report-builder-and-ssrs"></a><span data-ttu-id="40619-102">Функция First (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="40619-102">First Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="40619-103">Возвращает первое значение указанного выражения для заданной области.</span><span class="sxs-lookup"><span data-stu-id="40619-103">Returns the first value in the given scope of the specified expression.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="40619-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40619-104">Syntax</span></span>  
  
```  
  
First(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40619-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="40619-105">Parameters</span></span>  
 <span data-ttu-id="40619-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="40619-106">*expression*</span></span>  
 <span data-ttu-id="40619-107">(`Variant` или `Binary`) Выражение, к которому применяется статистическая обработка, например `=Fields!FieldName.Value`.</span><span class="sxs-lookup"><span data-stu-id="40619-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!FieldName.Value`.</span></span>  
  
 <span data-ttu-id="40619-108">*область*</span><span class="sxs-lookup"><span data-stu-id="40619-108">*scope*</span></span>  
 <span data-ttu-id="40619-109">(`String`) Необязательно.</span><span class="sxs-lookup"><span data-stu-id="40619-109">(`String`) Optional.</span></span> <span data-ttu-id="40619-110">Имя набора данных, группы или области данных, содержащих элементы отчета, к которым применяется агрегатная функция.</span><span class="sxs-lookup"><span data-stu-id="40619-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="40619-111">Если аргумент *scope* не задан, используется текущая область.</span><span class="sxs-lookup"><span data-stu-id="40619-111">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="40619-112">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="40619-112">Return Type</span></span>  
 <span data-ttu-id="40619-113">Определяется типом выражения.</span><span class="sxs-lookup"><span data-stu-id="40619-113">Determined by the type of expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40619-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="40619-114">Remarks</span></span>  
 <span data-ttu-id="40619-115">Функция `First` возвращает первое значение в наборе данных после того, как для указанной области были применены сортировка и фильтрация.</span><span class="sxs-lookup"><span data-stu-id="40619-115">The `First` function returns the first value in a set of data after all sorting and filtering have been applied at the specified scope.</span></span>  
  
 <span data-ttu-id="40619-116">Функция `First` не может использоваться в критериях фильтра группирования с какой-либо областью, кроме текущей области (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="40619-116">The `First` function cannot be used in group filter expressions with anything except the current (default) scope.</span></span>  
  
 <span data-ttu-id="40619-117">Функцию `First` можно также использовать в заголовке странице, чтобы вернуть первое значение набора `ReportItems` для страницы, с целью создания словарных заголовков, в которых отображаются первая и последняя записи страницы.</span><span class="sxs-lookup"><span data-stu-id="40619-117">You can also use `First` in a page header to return the first value from the `ReportItems` collection for a page in order to produce dictionary-style headings that display the first and last entries on a page.</span></span>  
  
 <span data-ttu-id="40619-118">Значение *scope* должно быть строковой константой и не может быть выражением.</span><span class="sxs-lookup"><span data-stu-id="40619-118">The value of *scope* must be a string constant andcannot be an expression.</span></span> <span data-ttu-id="40619-119">Для внешних агрегатов и агрегатов, в которых не задаются другие агрегаты, параметр *scope* должен ссылаться не текущую область или включающую область.</span><span class="sxs-lookup"><span data-stu-id="40619-119">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="40619-120">Для агрегатов, содержащих агрегаты, во вложенных агрегатах может указываться дочерняя область.</span><span class="sxs-lookup"><span data-stu-id="40619-120">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="40619-121">*Expression* может содержать вызовы вложенных агрегатных функций со следующими условиями и исключениями.</span><span class="sxs-lookup"><span data-stu-id="40619-121">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="40619-122">Параметр*Scope* для вложенных агрегатов должен совпадать с областью внешнего агрегата или входить в нее.</span><span class="sxs-lookup"><span data-stu-id="40619-122">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="40619-123">Одна область из всех уникальных областей в выражении должна быть дочерней относительно всех других областей.</span><span class="sxs-lookup"><span data-stu-id="40619-123">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="40619-124">Параметр*Scope* для вложенных агрегатов не может быть именем набора данных.</span><span class="sxs-lookup"><span data-stu-id="40619-124">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="40619-125">*Выражение* не должно содержать `First` `Last` функции,, `Previous` или `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="40619-125">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="40619-126">*Expression* не может содержать вложенные агрегаты, в которых указан параметр *recursive*.</span><span class="sxs-lookup"><span data-stu-id="40619-126">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="40619-127">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="40619-127">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="40619-128">Дополнительные сведения о рекурсивных агрегатах см. в разделе [Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="40619-128">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="40619-129">Пример</span><span class="sxs-lookup"><span data-stu-id="40619-129">Example</span></span>  
 <span data-ttu-id="40619-130">Следующий пример кода возвращает первый номер продукта в группировании или области данных `Category` :</span><span class="sxs-lookup"><span data-stu-id="40619-130">The following code example returns the first product number in the `Category` group of a data region:</span></span>  
  
```  
=First(Fields!ProductNumber.Value, "Category")  
```  
  
## <a name="see-also"></a><span data-ttu-id="40619-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="40619-131">See Also</span></span>  
 <span data-ttu-id="40619-132">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40619-132">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="40619-133">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40619-133">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="40619-134">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40619-134">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="40619-135">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="40619-135">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
