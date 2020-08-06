---
title: Функция Count (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7b50b101-daf8-4fb0-ae04-57384755779f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3617e64d804b6b0f3d9522b5a089f418a942568a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667567"
---
# <a name="count-function-report-builder-and-ssrs"></a><span data-ttu-id="b1e59-102">Функция Count (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="b1e59-102">Count Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b1e59-103">Возвращает количество значений, отличных от NULL, определяемое выражением, вычисляемым в контексте данной области.</span><span class="sxs-lookup"><span data-stu-id="b1e59-103">Returns a count of non-null values specified by the expression, evaluated in the context of the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="b1e59-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1e59-104">Syntax</span></span>  
  
```  
  
Count(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1e59-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1e59-105">Parameters</span></span>  
 <span data-ttu-id="b1e59-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="b1e59-106">*expression*</span></span>  
 <span data-ttu-id="b1e59-107">(`Variant` или `Binary`) Выражение, к которому применяется статистическая обработка, например `=Fields!FieldName.Value`.</span><span class="sxs-lookup"><span data-stu-id="b1e59-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!FieldName.Value`.</span></span>  
  
 <span data-ttu-id="b1e59-108">*область*</span><span class="sxs-lookup"><span data-stu-id="b1e59-108">*scope*</span></span>  
 <span data-ttu-id="b1e59-109">(`String`) Имя набора данных, группы или области данных, содержащих элементы отчета, к которым применяется агрегатная функция.</span><span class="sxs-lookup"><span data-stu-id="b1e59-109">(`String`) The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="b1e59-110">Если аргумент *scope* не задан, используется текущая область.</span><span class="sxs-lookup"><span data-stu-id="b1e59-110">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="b1e59-111">*рекурсивные*</span><span class="sxs-lookup"><span data-stu-id="b1e59-111">*recursive*</span></span>  
 <span data-ttu-id="b1e59-112">(**Перечислимый тип**) Необязательно.</span><span class="sxs-lookup"><span data-stu-id="b1e59-112">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="b1e59-113">`Simple` (по умолчанию) или `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="b1e59-113">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="b1e59-114">Указывает, нужно ли выполнять статистическую обработку рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="b1e59-114">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="b1e59-115">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="b1e59-115">Return Type</span></span>  
 <span data-ttu-id="b1e59-116">Возвращает значение типа `Integer`.</span><span class="sxs-lookup"><span data-stu-id="b1e59-116">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1e59-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="b1e59-117">Remarks</span></span>  
 <span data-ttu-id="b1e59-118">Значение *scope* должно быть строковой константой и не может быть выражением.</span><span class="sxs-lookup"><span data-stu-id="b1e59-118">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="b1e59-119">Для внешних агрегатов и агрегатов, в которых не задаются другие агрегаты, параметр *scope* должен ссылаться не текущую область или включающую область.</span><span class="sxs-lookup"><span data-stu-id="b1e59-119">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="b1e59-120">Для агрегатов, содержащих агрегаты, во вложенных агрегатах может указываться дочерняя область.</span><span class="sxs-lookup"><span data-stu-id="b1e59-120">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="b1e59-121">*Expression* может содержать вызовы вложенных агрегатных функций со следующими условиями и исключениями.</span><span class="sxs-lookup"><span data-stu-id="b1e59-121">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="b1e59-122">Параметр*Scope* для вложенных агрегатов должен совпадать с областью внешнего агрегата или входить в нее.</span><span class="sxs-lookup"><span data-stu-id="b1e59-122">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="b1e59-123">Одна область из всех уникальных областей в выражении должна быть дочерней относительно всех других областей.</span><span class="sxs-lookup"><span data-stu-id="b1e59-123">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="b1e59-124">Параметр*Scope* для вложенных агрегатов не может быть именем набора данных.</span><span class="sxs-lookup"><span data-stu-id="b1e59-124">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="b1e59-125">*Выражение* не должно содержать `First` `Last` функции,, `Previous` или `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="b1e59-125">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="b1e59-126">*Expression* не может содержать вложенные агрегаты, в которых указан параметр *recursive*.</span><span class="sxs-lookup"><span data-stu-id="b1e59-126">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="b1e59-127">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="b1e59-127">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="b1e59-128">Дополнительные сведения о рекурсивных агрегатах см. в разделе [Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b1e59-128">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="b1e59-129">Пример</span><span class="sxs-lookup"><span data-stu-id="b1e59-129">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="b1e59-130">Description</span><span class="sxs-lookup"><span data-stu-id="b1e59-130">Description</span></span>  
 <span data-ttu-id="b1e59-131">В следующем примере кода показано выражение, вычисляющее число значений `Size` , отличных от NULL, для области по умолчанию и для области родительской группы.</span><span class="sxs-lookup"><span data-stu-id="b1e59-131">The following code example shows an expression that calculates the number of non-null values of `Size` for the default scope and for a parent group scope.</span></span> <span data-ttu-id="b1e59-132">Выражение добавляется в ячейку строки, относящуюся к дочерней группе `GroupbySubcategory`.</span><span class="sxs-lookup"><span data-stu-id="b1e59-132">The expression is added to a cell in a row that belongs to the child group `GroupbySubcategory`.</span></span> <span data-ttu-id="b1e59-133">Родительской группой является `GroupbyCategory`.</span><span class="sxs-lookup"><span data-stu-id="b1e59-133">The parent group is `GroupbyCategory`.</span></span> <span data-ttu-id="b1e59-134">Выражение отображает результаты для группы `GroupbySubcategory` (область по умолчанию) и затем для группы `GroupbyCategory` (область родительской группы).</span><span class="sxs-lookup"><span data-stu-id="b1e59-134">The expression displays the results for `GroupbySubcategory` (the default scope) and then for `GroupbyCategory` (the parent group scope).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1e59-135">Выражения не должны содержать действительные возвраты каретки и разрывы строк; эти символы включены в пример для поддержки модулей подготовки отчетов документации.</span><span class="sxs-lookup"><span data-stu-id="b1e59-135">Expressions should not contain actual carriage returns and line breaks; these are included in the example to support documentation renderers.</span></span> <span data-ttu-id="b1e59-136">При копировании следующего примера удалите возвраты каретки изо всех строк.</span><span class="sxs-lookup"><span data-stu-id="b1e59-136">If you copy the following example, remove carriage returns from each line.</span></span>  
  
## <a name="code"></a><span data-ttu-id="b1e59-137">Код</span><span class="sxs-lookup"><span data-stu-id="b1e59-137">Code</span></span>  
  
```  
="Count (Subcategory): " & Count(Fields!Size.Value) &   
"Count (Category): " & Count(Fields!Size.Value,"GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1e59-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="b1e59-138">See Also</span></span>  
 <span data-ttu-id="b1e59-139">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b1e59-139">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b1e59-140">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b1e59-140">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b1e59-141">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b1e59-141">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b1e59-142">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="b1e59-142">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
