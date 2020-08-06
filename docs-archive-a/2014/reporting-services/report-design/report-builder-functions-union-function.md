---
title: Функция Union (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c87e16fe-c12a-4c9d-a9df-7a94e229fd04
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c80926be53254ec512b2189c4b67e8cd5885733f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659404"
---
# <a name="union-function-report-builder-and-ssrs"></a><span data-ttu-id="0905b-102">Функция Union (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="0905b-102">Union Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0905b-103">Возвращает объединение всех числовых значений, отличных от NULL, заданных выражением, вычисляемым для данной области.</span><span class="sxs-lookup"><span data-stu-id="0905b-103">Returns the union of all the non-null numeric values specified by the expression, evaluated in the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="0905b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0905b-104">Syntax</span></span>  
  
```  
  
Union(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0905b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0905b-105">Parameters</span></span>  
 <span data-ttu-id="0905b-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="0905b-106">*expression*</span></span>  
 <span data-ttu-id="0905b-107">(`SqlGeometry` или `SqlGeography`) Выражение, к которому применяется статистическая обработка.</span><span class="sxs-lookup"><span data-stu-id="0905b-107">(`SqlGeometry` or `SqlGeography`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="0905b-108">*область*</span><span class="sxs-lookup"><span data-stu-id="0905b-108">*scope*</span></span>  
 <span data-ttu-id="0905b-109">(`String`) Необязательно.</span><span class="sxs-lookup"><span data-stu-id="0905b-109">(`String`) Optional.</span></span> <span data-ttu-id="0905b-110">Имя набора данных, группы или области данных, содержащих элементы отчета, к которым применяется агрегатная функция.</span><span class="sxs-lookup"><span data-stu-id="0905b-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="0905b-111">Если аргумент *scope* не задан, используется текущая область.</span><span class="sxs-lookup"><span data-stu-id="0905b-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="0905b-112">*рекурсивные*</span><span class="sxs-lookup"><span data-stu-id="0905b-112">*recursive*</span></span>  
 <span data-ttu-id="0905b-113">(**Перечислимый тип**) Необязательно.</span><span class="sxs-lookup"><span data-stu-id="0905b-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="0905b-114">`Simple` (по умолчанию) или `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="0905b-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="0905b-115">Указывает, нужно ли выполнять статистическую обработку рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="0905b-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return"></a><span data-ttu-id="0905b-116">Возвращает</span><span class="sxs-lookup"><span data-stu-id="0905b-116">Return</span></span>  
 <span data-ttu-id="0905b-117">Возвращает пространственный объект, или `SqlGeometry`, или `SqlGeography`, в зависимости от типа выражения.</span><span class="sxs-lookup"><span data-stu-id="0905b-117">Returns a spatial object, either `SqlGeometry` or `SqlGeography`, based on the expression type.</span></span> <span data-ttu-id="0905b-118">Дополнительные сведения о `SqlGeometry` и `SqlGeography` пространственных типах данных см. в разделе [Общие сведения о типах пространственных данных](../../relational-databases/spatial/spatial-data-types-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0905b-118">For more information about `SqlGeometry` and `SqlGeography` spatial data types, see [Spatial Data Types Overview](../../relational-databases/spatial/spatial-data-types-overview.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0905b-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="0905b-119">Remarks</span></span>  
 <span data-ttu-id="0905b-120">Данные в наборе, указанном в выражении, должны иметь один и тот же тип.</span><span class="sxs-lookup"><span data-stu-id="0905b-120">The set of data specified in the expression must have the same data type.</span></span>  
  
 <span data-ttu-id="0905b-121">Значение *scope* должно быть строковой константой и не может быть выражением.</span><span class="sxs-lookup"><span data-stu-id="0905b-121">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="0905b-122">Для внешних агрегатов и агрегатов, в которых не задаются другие агрегаты, параметр *scope* должен ссылаться не текущую область или включающую область.</span><span class="sxs-lookup"><span data-stu-id="0905b-122">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="0905b-123">Области наборов данных не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="0905b-123">Dataset scopes are not supported.</span></span> <span data-ttu-id="0905b-124">Для агрегатов, содержащих агрегаты, во вложенных агрегатах может указываться дочерняя область.</span><span class="sxs-lookup"><span data-stu-id="0905b-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="0905b-125">*Expression* может содержать вызовы вложенных агрегатных функций со следующими условиями и исключениями.</span><span class="sxs-lookup"><span data-stu-id="0905b-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="0905b-126">Параметр*Scope* для вложенных агрегатов должен совпадать с областью внешнего агрегата или входить в нее.</span><span class="sxs-lookup"><span data-stu-id="0905b-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="0905b-127">Одна область из всех уникальных областей в выражении должна быть дочерней относительно всех других областей.</span><span class="sxs-lookup"><span data-stu-id="0905b-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="0905b-128">Параметр*Scope* для вложенных агрегатов не может быть именем набора данных.</span><span class="sxs-lookup"><span data-stu-id="0905b-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="0905b-129">*Выражение* не должно содержать `First` `Last` функции,, `Previous` или `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="0905b-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="0905b-130">*Expression* не может содержать вложенные агрегаты, в которых указан параметр *recursive*.</span><span class="sxs-lookup"><span data-stu-id="0905b-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="0905b-131">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="0905b-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="0905b-132">Дополнительные сведения о рекурсивных агрегатах см. в разделе [Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0905b-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0905b-133">Пример</span><span class="sxs-lookup"><span data-stu-id="0905b-133">Example</span></span>  
 <span data-ttu-id="0905b-134">Следующая таблица содержит примеры выражений `SqlGeometry` и результирующих выражений `Union` в формате WKT (Well Known Text) для пространственных данных.</span><span class="sxs-lookup"><span data-stu-id="0905b-134">The following table shows examples of `SqlGeometry` expressions and `Union` result expression, shown in WKT (Well Known Text) format for spatial data.</span></span>  
  
|<span data-ttu-id="0905b-135">Поле с пространственными данными</span><span class="sxs-lookup"><span data-stu-id="0905b-135">Field with spatial data</span></span>|<span data-ttu-id="0905b-136">Пример</span><span class="sxs-lookup"><span data-stu-id="0905b-136">Example</span></span>|<span data-ttu-id="0905b-137">Результат Union</span><span class="sxs-lookup"><span data-stu-id="0905b-137">Union result</span></span>|  
|-----------------------------|-------------|------------------|  
|<span data-ttu-id="0905b-138">[PointLocation]</span><span class="sxs-lookup"><span data-stu-id="0905b-138">[PointLocation]</span></span>|<span data-ttu-id="0905b-139">POINT(1 2)</span><span class="sxs-lookup"><span data-stu-id="0905b-139">POINT(1 2)</span></span><br /><br /> <span data-ttu-id="0905b-140">POINT(3 4)</span><span class="sxs-lookup"><span data-stu-id="0905b-140">POINT(3 4)</span></span>|<span data-ttu-id="0905b-141">MULTIPOINT((1 2), (3 4))</span><span class="sxs-lookup"><span data-stu-id="0905b-141">MULTIPOINT((1 2), (3 4))</span></span>|  
|<span data-ttu-id="0905b-142">[PathDefinition]</span><span class="sxs-lookup"><span data-stu-id="0905b-142">[PathDefinition]</span></span>|<span data-ttu-id="0905b-143">LINESTRING(1 2, 3 4)</span><span class="sxs-lookup"><span data-stu-id="0905b-143">LINESTRING(1 2, 3 4)</span></span><br /><br /> <span data-ttu-id="0905b-144">LINESTRING(5 6, 7 8)</span><span class="sxs-lookup"><span data-stu-id="0905b-144">LINESTRING(5 6, 7 8)</span></span>|<span data-ttu-id="0905b-145">MULTILINESTRING((7 8, 5 6), (3 4, 1 2))</span><span class="sxs-lookup"><span data-stu-id="0905b-145">MULTILINESTRING((7 8, 5 6), (3 4, 1 2))</span></span>|  
|<span data-ttu-id="0905b-146">[PolygonDefinition]</span><span class="sxs-lookup"><span data-stu-id="0905b-146">[PolygonDefinition]</span></span>|<span data-ttu-id="0905b-147">POLYGON((1 2, 3 4, 5 2, 1 2))</span><span class="sxs-lookup"><span data-stu-id="0905b-147">POLYGON((1 2, 3 4, 5 2, 1 2))</span></span><br /><br /> <span data-ttu-id="0905b-148">POLYGON((-1 2, -3 4, -5 2, -1 2))</span><span class="sxs-lookup"><span data-stu-id="0905b-148">POLYGON((-1 2, -3 4, -5 2, -1 2))</span></span>|<span data-ttu-id="0905b-149">MULTIPOLYGON(((1 2, 5 2, 3 4, 1 2)), ((-5 2, -1 2, -3 4, -5 2)))</span><span class="sxs-lookup"><span data-stu-id="0905b-149">MULTIPOLYGON(((1 2, 5 2, 3 4, 1 2)), ((-5 2, -1 2, -3 4, -5 2)))</span></span>|  
  
```  
=Union(Fields!PointLocation.Value)  
=Union(Fields!PathDefinition.Value)  
=Union(Fields!PolygonDefinition.Value, "Group1")  
```  
  
## <a name="see-also"></a><span data-ttu-id="0905b-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="0905b-150">See Also</span></span>  
 <span data-ttu-id="0905b-151">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0905b-151">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0905b-152">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0905b-152">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0905b-153">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0905b-153">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0905b-154">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="0905b-154">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
