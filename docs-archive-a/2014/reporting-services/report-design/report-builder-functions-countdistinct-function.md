---
title: Функция CountDistinct (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 902c251e-e1e8-41d2-ac20-5bb6138ac410
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62fab53d4f26a874ac40e0a915c4242a41c72ce0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659440"
---
# <a name="countdistinct-function-report-builder-and-ssrs"></a><span data-ttu-id="069b5-102">Функция CountDistinct (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="069b5-102">CountDistinct Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="069b5-103">Возвращает количество уникальных значений, отличных от NULL, определяемое выражением, вычисляемым в контексте данной области.</span><span class="sxs-lookup"><span data-stu-id="069b5-103">Returns a count of all distinct non-null values specified by the expression, evaluated in the context of the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="069b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="069b5-104">Syntax</span></span>  
  
```  
  
CountDistinct(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="069b5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="069b5-105">Parameters</span></span>  
 <span data-ttu-id="069b5-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="069b5-106">*expression*</span></span>  
 <span data-ttu-id="069b5-107">(`Variant`) Выражение для выполнения статистической обработки.</span><span class="sxs-lookup"><span data-stu-id="069b5-107">(`Variant`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="069b5-108">*область*</span><span class="sxs-lookup"><span data-stu-id="069b5-108">*scope*</span></span>  
 <span data-ttu-id="069b5-109">(`String`) Необязательно.</span><span class="sxs-lookup"><span data-stu-id="069b5-109">(`String`) Optional.</span></span> <span data-ttu-id="069b5-110">Имя набора данных, группы или области данных, содержащих элементы отчета, к которым применяется агрегатная функция.</span><span class="sxs-lookup"><span data-stu-id="069b5-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="069b5-111">Если аргумент *scope* не задан, используется текущая область.</span><span class="sxs-lookup"><span data-stu-id="069b5-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="069b5-112">*рекурсивные*</span><span class="sxs-lookup"><span data-stu-id="069b5-112">*recursive*</span></span>  
 <span data-ttu-id="069b5-113">(**Перечислимый тип**) Необязательно.</span><span class="sxs-lookup"><span data-stu-id="069b5-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="069b5-114">`Simple` (по умолчанию) или `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="069b5-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="069b5-115">Указывает, нужно ли выполнять статистическую обработку рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="069b5-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="069b5-116">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="069b5-116">Return Type</span></span>  
 <span data-ttu-id="069b5-117">Возвращает значение типа `Integer`.</span><span class="sxs-lookup"><span data-stu-id="069b5-117">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="069b5-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="069b5-118">Remarks</span></span>  
 <span data-ttu-id="069b5-119">Значение *scope* должно быть строковой константой и не может быть выражением.</span><span class="sxs-lookup"><span data-stu-id="069b5-119">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="069b5-120">Для внешних агрегатов и агрегатов, в которых не задаются другие агрегаты, параметр *scope* должен ссылаться не текущую область или включающую область.</span><span class="sxs-lookup"><span data-stu-id="069b5-120">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="069b5-121">Для агрегатов, содержащих агрегаты, во вложенных агрегатах может указываться дочерняя область.</span><span class="sxs-lookup"><span data-stu-id="069b5-121">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="069b5-122">*Expression* может содержать вызовы вложенных агрегатных функций со следующими условиями и исключениями.</span><span class="sxs-lookup"><span data-stu-id="069b5-122">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="069b5-123">Параметр*Scope* для вложенных агрегатов должен совпадать с областью внешнего агрегата или входить в нее.</span><span class="sxs-lookup"><span data-stu-id="069b5-123">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="069b5-124">Одна область из всех уникальных областей в выражении должна быть дочерней относительно всех других областей.</span><span class="sxs-lookup"><span data-stu-id="069b5-124">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="069b5-125">Параметр*Scope* для вложенных агрегатов не может быть именем набора данных.</span><span class="sxs-lookup"><span data-stu-id="069b5-125">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="069b5-126">*Выражение* не должно содержать `First` `Last` функции,, `Previous` или `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="069b5-126">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="069b5-127">*Expression* не может содержать вложенные агрегаты, в которых указан параметр *recursive*.</span><span class="sxs-lookup"><span data-stu-id="069b5-127">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="069b5-128">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="069b5-128">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="069b5-129">Дополнительные сведения о рекурсивных агрегатах см. в разделе [Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="069b5-129">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="069b5-130">Пример</span><span class="sxs-lookup"><span data-stu-id="069b5-130">Example</span></span>  
 <span data-ttu-id="069b5-131">В приведенном ниже примере кода показано выражение, вычисляющее количество уникальных значений `Size` , отличных от NULL, для области по умолчанию и области родительской группы.</span><span class="sxs-lookup"><span data-stu-id="069b5-131">The following code example shows an expression that calculates the number of unique non-null values of `Size` for the default scope and for a parent group scope.</span></span> <span data-ttu-id="069b5-132">Выражение добавляется в ячейку строки, относящуюся к дочерней группе `GroupbySubcategory`.</span><span class="sxs-lookup"><span data-stu-id="069b5-132">The expression is added to a cell in a row that belongs to the child group `GroupbySubcategory`.</span></span> <span data-ttu-id="069b5-133">Родительской группой является `GroupbyCategory`.</span><span class="sxs-lookup"><span data-stu-id="069b5-133">The parent group is `GroupbyCategory`.</span></span> <span data-ttu-id="069b5-134">Выражение отображает результаты для группы `GroupbySubcategory` (область по умолчанию) и затем для группы `GroupbyCategory` (область родительской группы).</span><span class="sxs-lookup"><span data-stu-id="069b5-134">The expression displays the results for `GroupbySubcategory` (the default scope) and then for `GroupbyCategory` (the parent group scope).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="069b5-135">Выражения не должны содержать действительные возвраты каретки и разрывы строк; они включаются в пример кода для поддержки модулей подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="069b5-135">Expressions should not contain actual carriage returns and line breaks; these are included in the example code to support documentation renderers.</span></span> <span data-ttu-id="069b5-136">При копировании следующего примера удалите возвраты каретки изо всех строк.</span><span class="sxs-lookup"><span data-stu-id="069b5-136">If you copy the following example, remove carriage returns from each line.</span></span>  
  
```  
="Distinct count (Subcategory): " & CountDistinct(Fields!Size.Value) &   
"Distinct count (Category): " & CountDistinct(Fields!Size.Value,"GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="069b5-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="069b5-137">See Also</span></span>  
 <span data-ttu-id="069b5-138">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="069b5-138">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="069b5-139">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="069b5-139">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="069b5-140">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="069b5-140">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="069b5-141">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="069b5-141">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
