---
title: Функция Avg (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f1276c4c-bb44-44c0-a1bf-386a0c340003
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cfa9d3517e3b3b0c2e4e01853ffa30295ec343df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736058"
---
# <a name="avg-function-report-builder-and-ssrs"></a><span data-ttu-id="05070-102">Функция Avg (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="05070-102">Avg Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="05070-103">Возвращает среднее значение всех числовых значений, отличных от NULL, заданных выражением, вычисляемым для данной области.</span><span class="sxs-lookup"><span data-stu-id="05070-103">Returns the average of all non-null numeric values specified by the expression, evaluated in the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="05070-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05070-104">Syntax</span></span>  
  
```  
  
Avg(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05070-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="05070-105">Parameters</span></span>  
 <span data-ttu-id="05070-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="05070-106">*expression*</span></span>  
 <span data-ttu-id="05070-107">(`Float`) Выражение для выполнения статистической обработки.</span><span class="sxs-lookup"><span data-stu-id="05070-107">(`Float`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="05070-108">*область*</span><span class="sxs-lookup"><span data-stu-id="05070-108">*scope*</span></span>  
 <span data-ttu-id="05070-109">(`String`) Необязательно.</span><span class="sxs-lookup"><span data-stu-id="05070-109">(`String`) Optional.</span></span> <span data-ttu-id="05070-110">Имя набора данных, группы или области данных, содержащих элементы отчета, к которым применяется агрегатная функция.</span><span class="sxs-lookup"><span data-stu-id="05070-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="05070-111">Если аргумент *scope* не задан, используется текущая область.</span><span class="sxs-lookup"><span data-stu-id="05070-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="05070-112">*рекурсивные*</span><span class="sxs-lookup"><span data-stu-id="05070-112">*recursive*</span></span>  
 <span data-ttu-id="05070-113">(**Перечислимый тип**) Необязательно.</span><span class="sxs-lookup"><span data-stu-id="05070-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="05070-114">`Simple` (по умолчанию) или `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="05070-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="05070-115">Указывает, нужно ли выполнять статистическую обработку рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="05070-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="05070-116">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="05070-116">Return Type</span></span>  
 <span data-ttu-id="05070-117">Возвращает значение типа `Decimal` для десятичных выражений и `Double` — для всех остальных выражений.</span><span class="sxs-lookup"><span data-stu-id="05070-117">Returns a `Decimal` for decimal expressions and a `Double` for all other expressions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05070-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="05070-118">Remarks</span></span>  
 <span data-ttu-id="05070-119">Данные в наборе, указанном в выражении, должны иметь один и тот же тип.</span><span class="sxs-lookup"><span data-stu-id="05070-119">The set of data specified in the expression must have the same data type.</span></span> <span data-ttu-id="05070-120">Чтобы преобразовать данные, имеющие разные числовые типы, к одному и тому же типу, используйте функции преобразования, такие как `CInt`, `CDbl` или `CDec`.</span><span class="sxs-lookup"><span data-stu-id="05070-120">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="05070-121">Дополнительные сведения см. в разделе [Функции преобразования типов](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="05070-121">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="05070-122">Значение *scope* должно быть строковой константой и не может быть выражением.</span><span class="sxs-lookup"><span data-stu-id="05070-122">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="05070-123">Для внешних агрегатов и агрегатов, в которых не задаются другие агрегаты, параметр *scope* должен ссылаться не текущую область или включающую область.</span><span class="sxs-lookup"><span data-stu-id="05070-123">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="05070-124">Для агрегатов, содержащих агрегаты, во вложенных агрегатах может указываться дочерняя область.</span><span class="sxs-lookup"><span data-stu-id="05070-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="05070-125">*Expression* может содержать вызовы вложенных агрегатных функций со следующими условиями и исключениями.</span><span class="sxs-lookup"><span data-stu-id="05070-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="05070-126">Параметр*Scope* для вложенных агрегатов должен совпадать с областью внешнего агрегата или входить в нее.</span><span class="sxs-lookup"><span data-stu-id="05070-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="05070-127">Одна область из всех уникальных областей в выражении должна быть дочерней относительно всех других областей.</span><span class="sxs-lookup"><span data-stu-id="05070-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="05070-128">Параметр*Scope* для вложенных агрегатов не может быть именем набора данных.</span><span class="sxs-lookup"><span data-stu-id="05070-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="05070-129">*Выражение* не должно содержать `First` `Last` функции,, `Previous` или `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="05070-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="05070-130">*Expression* не может содержать вложенные агрегаты, в которых указан параметр *recursive*.</span><span class="sxs-lookup"><span data-stu-id="05070-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="05070-131">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="05070-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="05070-132">Дополнительные сведения о рекурсивных агрегатах см. в разделе [Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05070-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="05070-133">Пример</span><span class="sxs-lookup"><span data-stu-id="05070-133">Example</span></span>  
 <span data-ttu-id="05070-134">Следующие 2 примера кода предоставляют среднее всех значений в поле `Cost` , содержащемся в наборе данных с именем `Inventory`.</span><span class="sxs-lookup"><span data-stu-id="05070-134">The following two code examples provide an average of all values in the `Cost` field contained in a dataset named `Inventory`.</span></span>  
  
```  
=Avg(Fields!Cost.Value, "Inventory")   
  OR    
=Avg (CDbl(Fields!Cost.Value), "Inventory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="05070-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="05070-135">See Also</span></span>  
 <span data-ttu-id="05070-136">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="05070-136">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="05070-137">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="05070-137">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="05070-138">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="05070-138">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="05070-139">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="05070-139">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
