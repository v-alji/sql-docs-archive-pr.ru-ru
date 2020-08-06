---
title: Функция RunningValue (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6bee2f15-0e69-49c8-9689-b04544063b1d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 168073a0409455041f4ebe3aa4c5dcfc8fa129a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659409"
---
# <a name="runningvalue-function-report-builder-and-ssrs"></a><span data-ttu-id="1d827-102">Функция RunningValue (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="1d827-102">RunningValue Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1d827-103">Возвращает текущий агрегат всех числовых значений, отличных от NULL, заданных выражением, вычисляемым для данной области.</span><span class="sxs-lookup"><span data-stu-id="1d827-103">Returns a running aggregate of all non-null numeric values specified by the expression, evaluated for the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="1d827-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d827-104">Syntax</span></span>  
  
```  
  
RunningValue(expression, function, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d827-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d827-105">Parameters</span></span>  
 <span data-ttu-id="1d827-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="1d827-106">*expression*</span></span>  
 <span data-ttu-id="1d827-107">Выражение, к которому применяется статистическая обработка, например `[Quantity]`.</span><span class="sxs-lookup"><span data-stu-id="1d827-107">The expression on which to perform the aggregation, for example, `[Quantity]`.</span></span>  
  
 <span data-ttu-id="1d827-108">*function*</span><span class="sxs-lookup"><span data-stu-id="1d827-108">*function*</span></span>  
 <span data-ttu-id="1d827-109">(`Enum`) Имя агрегата функции для применения к выражению, например, `Sum`.</span><span class="sxs-lookup"><span data-stu-id="1d827-109">(`Enum`) The name of the aggregate function to apply to the expression, for example, `Sum`.</span></span> <span data-ttu-id="1d827-110">Этой функцией не может быть `RunningValue`, `RowNumber` или `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="1d827-110">This function cannot be `RunningValue`, `RowNumber`, or `Aggregate`.</span></span>  
  
 <span data-ttu-id="1d827-111">*область*</span><span class="sxs-lookup"><span data-stu-id="1d827-111">*scope*</span></span>  
 <span data-ttu-id="1d827-112">(`String`) Строковая константа, являющаяся именем набора данных, региона данных или группы или значением null (`Nothing` в [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), которая определяет контекст, в котором рассчитывается агрегат.</span><span class="sxs-lookup"><span data-stu-id="1d827-112">(`String`) A string constant that is the name of a dataset, data region, or group, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the context in which to evaluate the aggregation.</span></span> <span data-ttu-id="1d827-113">Значение `Nothing` указывает самый внешний контекст, обычно набор данных отчета.</span><span class="sxs-lookup"><span data-stu-id="1d827-113">`Nothing` specifies the outermost context, usually the report dataset.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="1d827-114">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="1d827-114">Return Type</span></span>  
 <span data-ttu-id="1d827-115">Определяется агрегатной функцией, указанной параметром *function* .</span><span class="sxs-lookup"><span data-stu-id="1d827-115">Determined by the aggregate function that is specified in the *function* parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d827-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="1d827-116">Remarks</span></span>  
 <span data-ttu-id="1d827-117">Это значение для функции `RunningValue` сбрасывается в 0 для каждого нового экземпляра этой области.</span><span class="sxs-lookup"><span data-stu-id="1d827-117">The value for `RunningValue` resets to 0 for each new instance of the scope.</span></span> <span data-ttu-id="1d827-118">Если указано группирование, то текущее значение сбрасывается при изменении выражения группы.</span><span class="sxs-lookup"><span data-stu-id="1d827-118">If a group is specified, the running value is reset when the group expression changes.</span></span> <span data-ttu-id="1d827-119">Если указана область данных, то текущее значение сбрасывается для каждого нового экземпляра области данных.</span><span class="sxs-lookup"><span data-stu-id="1d827-119">If a data region is specified, the running value is reset for each new instance of the data region.</span></span> <span data-ttu-id="1d827-120">Если указан набор данных, то текущее значение не сбрасывается по всему набору данных.</span><span class="sxs-lookup"><span data-stu-id="1d827-120">If a dataset is specified, the running value is not reset throughout the entire dataset.</span></span>  
  
 <span data-ttu-id="1d827-121">Функция `RunningValue` не может быть использована в выражении фильтра или сортировки.</span><span class="sxs-lookup"><span data-stu-id="1d827-121">`RunningValue` cannot be used in a filter or sort expression.</span></span>  
  
 <span data-ttu-id="1d827-122">Набор данных, для которого вычислено текущее значение, должен иметь такой же тип данных.</span><span class="sxs-lookup"><span data-stu-id="1d827-122">The set of data for which the running value is calculated must have the same data type.</span></span> <span data-ttu-id="1d827-123">Чтобы преобразовать данные, имеющие разные числовые типы, к одному и тому же типу, используйте функции преобразования, такие как `CInt`, `CDbl` или `CDec`.</span><span class="sxs-lookup"><span data-stu-id="1d827-123">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="1d827-124">Дополнительные сведения см. в разделе [Функции преобразования типов](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="1d827-124">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="1d827-125">Значением*Scope* не может быть выражение.</span><span class="sxs-lookup"><span data-stu-id="1d827-125">*Scope* cannot be an expression.</span></span>  
  
 <span data-ttu-id="1d827-126">*Expression* может содержать вызовы вложенных агрегатных функций со следующими условиями и исключениями.</span><span class="sxs-lookup"><span data-stu-id="1d827-126">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="1d827-127">Область для вложенных агрегатов должна совпадать с областью внешнего агрегата или входить в нее.</span><span class="sxs-lookup"><span data-stu-id="1d827-127">Scope for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="1d827-128">Одна область из всех уникальных областей в выражении должна быть дочерней относительно всех других областей.</span><span class="sxs-lookup"><span data-stu-id="1d827-128">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="1d827-129">Область для вложенных агрегатов не может быть именем набора данных.</span><span class="sxs-lookup"><span data-stu-id="1d827-129">Scope for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="1d827-130">*Выражение* не должно содержать `First` `Last` функции,, `Previous` или `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="1d827-130">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="1d827-131">*Expression* не может содержать вложенные агрегаты, в которых указан параметр *recursive*.</span><span class="sxs-lookup"><span data-stu-id="1d827-131">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="1d827-132">Для вычисления текущего значения числа строк используйте функцию `RowNumber`.</span><span class="sxs-lookup"><span data-stu-id="1d827-132">To calculate the running value of the number of rows, use `RowNumber`.</span></span> <span data-ttu-id="1d827-133">Дополнительные сведения см. в разделе [Функция RowNumber (построитель отчетов и службы SSRS)](report-builder-functions-rownumber-function.md).</span><span class="sxs-lookup"><span data-stu-id="1d827-133">For more information, see [RowNumber Function &#40;Report Builder and SSRS&#41;](report-builder-functions-rownumber-function.md).</span></span>  
  
 <span data-ttu-id="1d827-134">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="1d827-134">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="1d827-135">Дополнительные сведения о рекурсивных агрегатах см. в разделе [Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1d827-135">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1d827-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d827-136">Examples</span></span>  
 <span data-ttu-id="1d827-137">Следующий пример кода возвращает текущую сумму поля стоимости `Cost` в самой внешней области данных, которой является набор данных.</span><span class="sxs-lookup"><span data-stu-id="1d827-137">The following code example provides a running sum of the field named `Cost` in the outermost scope, which is the dataset.</span></span>  
  
```  
=RunningValue(Fields!Cost.Value, Sum, Nothing)  
```  
  
 <span data-ttu-id="1d827-138">Следующий пример кода выдает сумму с накоплением поля с названием `Score` в наборе данных с названием `DataSet1`.</span><span class="sxs-lookup"><span data-stu-id="1d827-138">The following code example provides a running sum of the field named `Score` in the dataset named `DataSet1`.</span></span>  
  
```  
=RunningValue(Fields!Score.Value,sum,"DataSet1")  
```  
  
 <span data-ttu-id="1d827-139">Следующий пример кода выдает сумму с накоплением поля с названием `Traffic Charges` во внешней области видимости.</span><span class="sxs-lookup"><span data-stu-id="1d827-139">The following code example provides a running sum of the field named `Traffic Charges` in the outermost scope.</span></span>  
  
```  
=RunningValue(Fields!Traffic Charges.Value, Sum, Nothing)  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d827-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="1d827-140">See Also</span></span>  
 <span data-ttu-id="1d827-141">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1d827-141">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1d827-142">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1d827-142">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1d827-143">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1d827-143">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1d827-144">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="1d827-144">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
