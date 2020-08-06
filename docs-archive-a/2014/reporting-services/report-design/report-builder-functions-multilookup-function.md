---
title: Функция Multilookup (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1fec079e-33b3-4e4d-92b3-6b4d06a49a77
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2f2aff7a2a39e1a072cf4b05f0a04e12ced529af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659421"
---
# <a name="multilookup-function-report-builder-and-ssrs"></a><span data-ttu-id="9360b-102">Функция Multilookup (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9360b-102">Multilookup Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9360b-103">Возвращает набор первых подходящих значений для указанного набора имен из набора данных, содержащего пары «имя-значение».</span><span class="sxs-lookup"><span data-stu-id="9360b-103">Returns the set of first-match values for the specified set of names from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="9360b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9360b-104">Syntax</span></span>  
  
```  
  
Multilookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9360b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9360b-105">Parameters</span></span>  
 <span data-ttu-id="9360b-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="9360b-106">*source_expression*</span></span>  
 <span data-ttu-id="9360b-107">(`VariantArray`) Выражение, вычисляемое в текущей области и указывающее набор имен или ключей для поиска.</span><span class="sxs-lookup"><span data-stu-id="9360b-107">(`VariantArray`) An expression that is evaluated in the current scope and that specifies the set of names or keys to look up.</span></span> <span data-ttu-id="9360b-108">Например, для многозначного параметра `=Parameters!IDs.value`.</span><span class="sxs-lookup"><span data-stu-id="9360b-108">For example, for a multivalue parameter, `=Parameters!IDs.value`.</span></span>  
  
 <span data-ttu-id="9360b-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="9360b-109">*destination_expression*</span></span>  
 <span data-ttu-id="9360b-110">(`Variant`) Выражение, вычисляемое для каждой строки в наборе данных и указывающее имя или ключ для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="9360b-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="9360b-111">Например, `=Fields!ID.Value`.</span><span class="sxs-lookup"><span data-stu-id="9360b-111">For example, `=Fields!ID.Value`.</span></span>  
  
 <span data-ttu-id="9360b-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="9360b-112">*result_expression*</span></span>  
 <span data-ttu-id="9360b-113">( `Variant` ) Выражение, вычисляемое для строки в наборе данных, где *source_expression*  =  *destination_expression*, который указывает извлекаемое значение.</span><span class="sxs-lookup"><span data-stu-id="9360b-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="9360b-114">Например, `=Fields!Name.Value`.</span><span class="sxs-lookup"><span data-stu-id="9360b-114">For example, `=Fields!Name.Value`.</span></span>  
  
 <span data-ttu-id="9360b-115">*набор данных*</span><span class="sxs-lookup"><span data-stu-id="9360b-115">*dataset*</span></span>  
 <span data-ttu-id="9360b-116">Константа, задающая имя набора данных в отчете.</span><span class="sxs-lookup"><span data-stu-id="9360b-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="9360b-117">Например, «Colors».</span><span class="sxs-lookup"><span data-stu-id="9360b-117">For example, "Colors".</span></span>  
  
## <a name="return"></a><span data-ttu-id="9360b-118">Возвращает</span><span class="sxs-lookup"><span data-stu-id="9360b-118">Return</span></span>  
 <span data-ttu-id="9360b-119">Возвращает значение `VariantArray` или `Nothing`, если совпадения нет.</span><span class="sxs-lookup"><span data-stu-id="9360b-119">Returns a `VariantArray`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9360b-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="9360b-120">Remarks</span></span>  
 <span data-ttu-id="9360b-121">Функция `Multilookup` служит для извлечения набора значений из набора данных, содержащего пары «имя-значение» со связью «один к одному».</span><span class="sxs-lookup"><span data-stu-id="9360b-121">Use `Multilookup` to retrieve a set of values from a dataset for name-value pairs where each pair has a 1-to-1 relationship.</span></span> <span data-ttu-id="9360b-122">Функция `MultiLookup` является эквивалентом функции `Lookup` для набора имен или ключей.</span><span class="sxs-lookup"><span data-stu-id="9360b-122">`MultiLookup` is the equivalent of calling `Lookup` for a set of names or keys.</span></span> <span data-ttu-id="9360b-123">Например, для параметра с несколькими значениями на основе идентификаторов первичных ключей функция `Multilookup` может быть использована в выражении в текстовом поле таблицы для извлечения связанных значений из набора данных, не привязанного к параметру или таблице.</span><span class="sxs-lookup"><span data-stu-id="9360b-123">For example, for a multivalue parameter that is based on primary key identifiers, you can use `Multilookup` in an expression in a text box in a table to retrieve associated values from a dataset that is not bound to the parameter or to the table.</span></span>  
  
 <span data-ttu-id="9360b-124">Функция `Multilookup` выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9360b-124">`Multilookup` does the following:</span></span>  
  
-   <span data-ttu-id="9360b-125">вычисляет исходное выражение в текущей области и создает массив объектов типа variant;</span><span class="sxs-lookup"><span data-stu-id="9360b-125">Evaluates the source expression in the current scope and generates an array of variant objects.</span></span>  
  
-   <span data-ttu-id="9360b-126">для всех объектов массива вызывается [функция Lookup (построитель отчетов и службы SSRS)](report-builder-functions-lookup-function.md), а результаты добавляются к массиву возвращаемых значений;</span><span class="sxs-lookup"><span data-stu-id="9360b-126">For each object in the array, calls [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md) and adds the result to the return array.</span></span>  
  
-   <span data-ttu-id="9360b-127">возвращает набор результатов.</span><span class="sxs-lookup"><span data-stu-id="9360b-127">Returns the set of results.</span></span>  
  
 <span data-ttu-id="9360b-128">Для извлечения единственного значения для указанного имени из набора данных, состоящего из пар "имя-значение" со связью "один к одному", используйте [функцию Lookup (построитель отчетов и службы SSRS)](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="9360b-128">To retrieve a single value from a dataset with name-value pairs for a specified name where there is a 1-to-1 relationship, use [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span> <span data-ttu-id="9360b-129">Для извлечения нескольких значений для имени из набора данных, состоящего из пар "имя-значение" со связью "один ко многим", используйте [функцию LookupSet (построитель отчетов и службы SSRS)](report-builder-functions-lookupset-function.md).</span><span class="sxs-lookup"><span data-stu-id="9360b-129">To retrieve multiple values from a dataset with name-value pairs for a name where there is a 1-to-many relationship, use [LookupSet Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookupset-function.md).</span></span>  
  
 <span data-ttu-id="9360b-130">Применяются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="9360b-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="9360b-131">Функция `Multilookup` вычисляется после применения всех критериев фильтра.</span><span class="sxs-lookup"><span data-stu-id="9360b-131">`Multilookup` is evaluated after all filter expressions are applied</span></span>  
  
-   <span data-ttu-id="9360b-132">Поддерживается только один уровень уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="9360b-132">Only one level of look-up is supported.</span></span> <span data-ttu-id="9360b-133">Исходное, целевое и результирующее выражения не могут включать в себя ссылки на функцию уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="9360b-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="9360b-134">Исходное и результирующее выражения должны возвращать один и тот же тип данных.</span><span class="sxs-lookup"><span data-stu-id="9360b-134">Source and destination expressions must evaluate to the same data type.</span></span>  
  
-   <span data-ttu-id="9360b-135">Исходное, целевое и результирующее выражения не могут включать в себя ссылки на переменные отчета или группы.</span><span class="sxs-lookup"><span data-stu-id="9360b-135">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="9360b-136">Функцию `Multilookup` нельзя использовать в качестве выражения для следующих элементов отчета:</span><span class="sxs-lookup"><span data-stu-id="9360b-136">`Multilookup` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="9360b-137">динамические строки соединения для источника данных;</span><span class="sxs-lookup"><span data-stu-id="9360b-137">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="9360b-138">вычисляемые поля в наборе данных;</span><span class="sxs-lookup"><span data-stu-id="9360b-138">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="9360b-139">параметры запроса в наборе данных;</span><span class="sxs-lookup"><span data-stu-id="9360b-139">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="9360b-140">фильтры в наборе данных;</span><span class="sxs-lookup"><span data-stu-id="9360b-140">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="9360b-141">параметры отчета;</span><span class="sxs-lookup"><span data-stu-id="9360b-141">Report parameters.</span></span>  
  
    -   <span data-ttu-id="9360b-142">Свойство Report.Language.</span><span class="sxs-lookup"><span data-stu-id="9360b-142">The Report.Language property.</span></span>  
  
 <span data-ttu-id="9360b-143">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="9360b-143">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9360b-144">Пример</span><span class="sxs-lookup"><span data-stu-id="9360b-144">Example</span></span>  
 <span data-ttu-id="9360b-145">Предположим, набор данных Category содержит поле CategoryList, которое содержит список идентификаторов категорий с разделителями-запятыми, например «2, 4, 2, 1».</span><span class="sxs-lookup"><span data-stu-id="9360b-145">Assume a dataset called "Category" contains the field CategoryList, which is a field that contains a comma-separated list of category identifers, for example, "2, 4, 2, 1".</span></span>  
  
 <span data-ttu-id="9360b-146">Набор данных «CategoryNames» содержит идентификатор и название категории, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9360b-146">The dataset CategoryNames contains the category identifier and category name, as shown in the following table.</span></span>  
  
|<span data-ttu-id="9360b-147">ID</span><span class="sxs-lookup"><span data-stu-id="9360b-147">ID</span></span>|<span data-ttu-id="9360b-148">Имя</span><span class="sxs-lookup"><span data-stu-id="9360b-148">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="9360b-149">1</span><span class="sxs-lookup"><span data-stu-id="9360b-149">1</span></span>|<span data-ttu-id="9360b-150">Accessories</span><span class="sxs-lookup"><span data-stu-id="9360b-150">Accessories</span></span>|  
|<span data-ttu-id="9360b-151">2</span><span class="sxs-lookup"><span data-stu-id="9360b-151">2</span></span>|<span data-ttu-id="9360b-152">Bikes</span><span class="sxs-lookup"><span data-stu-id="9360b-152">Bikes</span></span>|  
|<span data-ttu-id="9360b-153">3</span><span class="sxs-lookup"><span data-stu-id="9360b-153">3</span></span>|<span data-ttu-id="9360b-154">Clothing</span><span class="sxs-lookup"><span data-stu-id="9360b-154">Clothing</span></span>|  
|<span data-ttu-id="9360b-155">4</span><span class="sxs-lookup"><span data-stu-id="9360b-155">4</span></span>|<span data-ttu-id="9360b-156">Components</span><span class="sxs-lookup"><span data-stu-id="9360b-156">Components</span></span>|  
  
 <span data-ttu-id="9360b-157">Для поиска имен, соответствующих списку идентификаторов, используйте функцию `Multilookup`.</span><span class="sxs-lookup"><span data-stu-id="9360b-157">To look up the names that correspond to the list of  identifiers, use `Multilookup`.</span></span> <span data-ttu-id="9360b-158">Сначала необходимо разбить список на массив строк, вызвать  функцию `Multilookup` для извлечения названий категорий и объединить результаты в строку.</span><span class="sxs-lookup"><span data-stu-id="9360b-158">You must first split the list into a string array, call `Multilookup` to retrieve the category names, and concatenate the results into a string.</span></span>  
  
 <span data-ttu-id="9360b-159">Следующее выражение при помещении текстового поля в область данных, привязанную к набору данных Category, отображает «Bikes, Components, Bikes, Accessories».</span><span class="sxs-lookup"><span data-stu-id="9360b-159">The following expression, when placed in a text box in a data region bound to the Category dataset, displays "Bikes, Components, Bikes, Accessories":</span></span>  
  
```  
=Join(MultiLookup(Split(Fields!CategoryList.Value,","),  
   Fields!CategoryID.Value,Fields!CategoryName.Value,"Category")),  
   ", ")  
```  
  
## <a name="example"></a><span data-ttu-id="9360b-160">Пример</span><span class="sxs-lookup"><span data-stu-id="9360b-160">Example</span></span>  
 <span data-ttu-id="9360b-161">Предположим, в наборе данных с именем ProductColors есть поле идентификатора цвета ColorID и поле значения цвета Color, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9360b-161">Assume a dataset ProductColors contains a color identifier field ColorID and a color value field Color, as shown in the following table.</span></span>  
  
|<span data-ttu-id="9360b-162">ColorID</span><span class="sxs-lookup"><span data-stu-id="9360b-162">ColorID</span></span>|<span data-ttu-id="9360b-163">Color</span><span class="sxs-lookup"><span data-stu-id="9360b-163">Color</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="9360b-164">1</span><span class="sxs-lookup"><span data-stu-id="9360b-164">1</span></span>|<span data-ttu-id="9360b-165">Красный</span><span class="sxs-lookup"><span data-stu-id="9360b-165">Red</span></span>|  
|<span data-ttu-id="9360b-166">2</span><span class="sxs-lookup"><span data-stu-id="9360b-166">2</span></span>|<span data-ttu-id="9360b-167">Синий</span><span class="sxs-lookup"><span data-stu-id="9360b-167">Blue</span></span>|  
|<span data-ttu-id="9360b-168">3</span><span class="sxs-lookup"><span data-stu-id="9360b-168">3</span></span>|<span data-ttu-id="9360b-169">Зеленый</span><span class="sxs-lookup"><span data-stu-id="9360b-169">Green</span></span>|  
  
 <span data-ttu-id="9360b-170">Предположим, параметр с несколькими значениями *MyColors* не привязан к доступным значениям набора данных.</span><span class="sxs-lookup"><span data-stu-id="9360b-170">Assume the multivalue parameter *MyColors* is not bound to a dataset for its available values.</span></span> <span data-ttu-id="9360b-171">По умолчанию для параметра заданы значения 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="9360b-171">The default values for the parameter are set to 2 and 3.</span></span> <span data-ttu-id="9360b-172">Следующее выражение при помещении в текстовое поле таблицы объединяет несколько выбранных значений параметра в список с разделителями-запятыми и отображает «Blue, Green».</span><span class="sxs-lookup"><span data-stu-id="9360b-172">The following expression, when placed in a text box in a table, concatenates the multiple selected values for the parameter into a comma-separated list and displays "Blue, Green".</span></span>  
  
```  
=Join(MultiLookup(Parameters!MyColors.Value,Fields!ColorID.Value,Fields!Color.Value,"ProductColors"),", ")  
```  
  
## <a name="see-also"></a><span data-ttu-id="9360b-173">См. также:</span><span class="sxs-lookup"><span data-stu-id="9360b-173">See Also</span></span>  
 <span data-ttu-id="9360b-174">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9360b-174">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9360b-175">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9360b-175">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9360b-176">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9360b-176">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9360b-177">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9360b-177">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
