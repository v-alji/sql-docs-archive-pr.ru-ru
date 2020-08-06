---
title: Функция Max (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 61c4d6ff-6435-456a-9cbd-5113d2113e8a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 03cea448500a6219fef5c04f1cea528ddc11f693
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659422"
---
# <a name="max-function-report-builder-and-ssrs"></a><span data-ttu-id="38185-102">Функция Max (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="38185-102">Max Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="38185-103">Возвращает максимальное значение всех числовых значений, отличных от NULL, заданных выражением, вычисляемым в контексте данной области.</span><span class="sxs-lookup"><span data-stu-id="38185-103">Returns the maximum value of all non-null numeric values specified by the expression, in the context of the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="38185-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38185-104">Syntax</span></span>  
  
```  
  
Max(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38185-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="38185-105">Parameters</span></span>  
 <span data-ttu-id="38185-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="38185-106">*expression*</span></span>  
 <span data-ttu-id="38185-107">(`Variant`) Выражение для выполнения статистической обработки.</span><span class="sxs-lookup"><span data-stu-id="38185-107">(`Variant`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="38185-108">*область*</span><span class="sxs-lookup"><span data-stu-id="38185-108">*scope*</span></span>  
 <span data-ttu-id="38185-109">(`String`) Необязательно.</span><span class="sxs-lookup"><span data-stu-id="38185-109">(`String`) Optional.</span></span> <span data-ttu-id="38185-110">Имя набора данных, группы или области данных, содержащих элементы отчета, к которым применяется агрегатная функция.</span><span class="sxs-lookup"><span data-stu-id="38185-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="38185-111">Если аргумент *scope* не задан, используется текущая область.</span><span class="sxs-lookup"><span data-stu-id="38185-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="38185-112">*рекурсивные*</span><span class="sxs-lookup"><span data-stu-id="38185-112">*recursive*</span></span>  
 <span data-ttu-id="38185-113">(**Перечислимый тип**) Необязательно.</span><span class="sxs-lookup"><span data-stu-id="38185-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="38185-114">`Simple` (по умолчанию) или `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="38185-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="38185-115">Указывает, нужно ли выполнять статистическую обработку рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="38185-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="38185-116">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="38185-116">Return Type</span></span>  
 <span data-ttu-id="38185-117">Определяется типом выражения.</span><span class="sxs-lookup"><span data-stu-id="38185-117">Determined by the type of the expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38185-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="38185-118">Remarks</span></span>  
 <span data-ttu-id="38185-119">Данные в наборе, указанном в выражении, должны иметь один и тот же тип.</span><span class="sxs-lookup"><span data-stu-id="38185-119">The set of data specified in the expression must have the same data type.</span></span> <span data-ttu-id="38185-120">Чтобы преобразовать данные, имеющие разные числовые типы, к одному и тому же типу, используйте функции преобразования, такие как `CInt`, `CDbl` или `CDec`.</span><span class="sxs-lookup"><span data-stu-id="38185-120">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="38185-121">Дополнительные сведения см. в разделе [Функции преобразования типов](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="38185-121">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="38185-122">Значение *scope* должно быть строковой константой и не может быть выражением.</span><span class="sxs-lookup"><span data-stu-id="38185-122">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="38185-123">Для внешних агрегатов и агрегатов, в которых не задаются другие агрегаты, параметр *scope* должен ссылаться не текущую область или включающую область.</span><span class="sxs-lookup"><span data-stu-id="38185-123">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="38185-124">Для агрегатов, содержащих агрегаты, во вложенных агрегатах может указываться дочерняя область.</span><span class="sxs-lookup"><span data-stu-id="38185-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="38185-125">*Expression* может содержать вызовы вложенных агрегатных функций со следующими условиями и исключениями.</span><span class="sxs-lookup"><span data-stu-id="38185-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="38185-126">Параметр*Scope* для вложенных агрегатов должен совпадать с областью внешнего агрегата или входить в нее.</span><span class="sxs-lookup"><span data-stu-id="38185-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="38185-127">Одна область из всех уникальных областей в выражении должна быть дочерней относительно всех других областей.</span><span class="sxs-lookup"><span data-stu-id="38185-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="38185-128">Параметр*Scope* для вложенных агрегатов не может быть именем набора данных.</span><span class="sxs-lookup"><span data-stu-id="38185-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="38185-129">*Выражение* не должно содержать `First` `Last` функции,, `Previous` или `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="38185-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="38185-130">*Expression* не может содержать вложенные агрегаты, в которых указан параметр *recursive*.</span><span class="sxs-lookup"><span data-stu-id="38185-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="38185-131">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="38185-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="38185-132">Дополнительные сведения о рекурсивных агрегатах см. в разделе [Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="38185-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38185-133">Пример</span><span class="sxs-lookup"><span data-stu-id="38185-133">Example</span></span>  
 <span data-ttu-id="38185-134">Следующий пример кода возвращает наибольшее значение в группе или области данных `Year` .</span><span class="sxs-lookup"><span data-stu-id="38185-134">The following code example provides the highest total in the `Year` group or data region.</span></span>  
  
```  
=Max(Fields!OrderTotal.Value, "Year")  
```  
  
## <a name="see-also"></a><span data-ttu-id="38185-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="38185-135">See Also</span></span>  
 <span data-ttu-id="38185-136">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="38185-136">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="38185-137">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="38185-137">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="38185-138">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="38185-138">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="38185-139">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="38185-139">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
