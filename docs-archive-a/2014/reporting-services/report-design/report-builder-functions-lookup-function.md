---
title: Функция подстановки (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e60e5bab-b286-4897-9685-9ff12703517d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 053fefff51e4b4e338e262664bd7570280c92540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659423"
---
# <a name="lookup-function-report-builder-and-ssrs"></a><span data-ttu-id="d9685-102">Функция подстановки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d9685-102">Lookup Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d9685-103">Возвращает первое совпадающее значение для заданного имени из набора данных, содержащего пары «имя-значение».</span><span class="sxs-lookup"><span data-stu-id="d9685-103">Returns the first matching value for the specified name from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="d9685-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9685-104">Syntax</span></span>  
  
```  
  
Lookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9685-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9685-105">Parameters</span></span>  
 <span data-ttu-id="d9685-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="d9685-106">*source_expression*</span></span>  
 <span data-ttu-id="d9685-107">(`Variant`) Выражение, вычисляемое в текущей области и указывающее имя или ключ для поиска.</span><span class="sxs-lookup"><span data-stu-id="d9685-107">(`Variant`) An expression that is evaluated in the current scope and that specifies the name or key to look up.</span></span> <span data-ttu-id="d9685-108">Например, `=Fields!ProdID.Value`.</span><span class="sxs-lookup"><span data-stu-id="d9685-108">For example, `=Fields!ProdID.Value`.</span></span>  
  
 <span data-ttu-id="d9685-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="d9685-109">*destination_expression*</span></span>  
 <span data-ttu-id="d9685-110">(`Variant`) Выражение, вычисляемое для каждой строки в наборе данных и указывающее имя или ключ для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="d9685-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="d9685-111">Например, `=Fields!ProductID.Value`.</span><span class="sxs-lookup"><span data-stu-id="d9685-111">For example, `=Fields!ProductID.Value`.</span></span>  
  
 <span data-ttu-id="d9685-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="d9685-112">*result_expression*</span></span>  
 <span data-ttu-id="d9685-113">( `Variant` ) Выражение, вычисляемое для строки в наборе данных, где *source_expression*  =  *destination_expression*, который указывает извлекаемое значение.</span><span class="sxs-lookup"><span data-stu-id="d9685-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="d9685-114">Например, `=Fields!ProductName.Value`.</span><span class="sxs-lookup"><span data-stu-id="d9685-114">For example, `=Fields!ProductName.Value`.</span></span>  
  
 <span data-ttu-id="d9685-115">*набор данных*</span><span class="sxs-lookup"><span data-stu-id="d9685-115">*dataset*</span></span>  
 <span data-ttu-id="d9685-116">Константа, задающая имя набора данных в отчете.</span><span class="sxs-lookup"><span data-stu-id="d9685-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="d9685-117">Например, «Продукты».</span><span class="sxs-lookup"><span data-stu-id="d9685-117">For example, "Products".</span></span>  
  
## <a name="return"></a><span data-ttu-id="d9685-118">Возвращает</span><span class="sxs-lookup"><span data-stu-id="d9685-118">Return</span></span>  
 <span data-ttu-id="d9685-119">Возвращает значение `Variant` или `Nothing`, если совпадения нет.</span><span class="sxs-lookup"><span data-stu-id="d9685-119">Returns a `Variant`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9685-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="d9685-120">Remarks</span></span>  
 <span data-ttu-id="d9685-121">Функция `Lookup` позволяет извлечь значение из указанного набора данных, состоящего из пар «имя-значение» с отношением один к одному.</span><span class="sxs-lookup"><span data-stu-id="d9685-121">Use `Lookup` to retrieve the value from the specified dataset for a name/value pair where there is a 1-to-1 relationship.</span></span> <span data-ttu-id="d9685-122">Например, для поля ID в таблице функция `Lookup` может быть использована для поиска соответствующего поля Name в наборе данных, не привязанном к области данных.</span><span class="sxs-lookup"><span data-stu-id="d9685-122">For example, for an ID field in a table, you can use `Lookup` to retrieve the corresponding Name field from a dataset that is not bound to the data region.</span></span>  
  
 <span data-ttu-id="d9685-123">Функция `Lookup` выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d9685-123">`Lookup` does the following:</span></span>  
  
-   <span data-ttu-id="d9685-124">Вычисляет исходное выражение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="d9685-124">Evaluates the source expression in the current scope.</span></span>  
  
-   <span data-ttu-id="d9685-125">Вычисляет целевое выражение для каждой строки указанного набора данных после применения фильтров с учетом заданных для него параметров сортировки.</span><span class="sxs-lookup"><span data-stu-id="d9685-125">Evaluates the destination expression for each row of the specified dataset after filters have been applied, based on the collation of the specified dataset.</span></span>  
  
-   <span data-ttu-id="d9685-126">При первом совпадении исходного и целевого выражений вычисляет результирующее выражение для этой строки в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="d9685-126">On the first match of source expression and destination expression, evaluates the result expression for that row in the dataset.</span></span>  
  
-   <span data-ttu-id="d9685-127">Возвращает результирующее значение выражения.</span><span class="sxs-lookup"><span data-stu-id="d9685-127">Returns the result expression value.</span></span>  
  
 <span data-ttu-id="d9685-128">Для получения множества значений по одному имени или ключевому полю, если существует отношение связь "один ко многим", пользуйтесь [функцией LookupSet (построитель отчетов и службы SSRS)](report-builder-functions-lookupset-function.md).</span><span class="sxs-lookup"><span data-stu-id="d9685-128">To retrieve multiple values for a single name or key field where there is a 1-to-many relationship, use [LookupSet Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookupset-function.md).</span></span> <span data-ttu-id="d9685-129">Для вызова `Lookup` набора значений используйте [функцию много&#40;построитель отчетов и службы SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="d9685-129">To call `Lookup` for a set of values, use [Multilookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span>  
  
 <span data-ttu-id="d9685-130">Применяются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="d9685-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="d9685-131">Функция `Lookup` вычисляется после применения всех выражений фильтров.</span><span class="sxs-lookup"><span data-stu-id="d9685-131">`Lookup` is evaluated after all filter expressions are applied.</span></span>  
  
-   <span data-ttu-id="d9685-132">Поддерживается только один уровень уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="d9685-132">Only one level of lookup is supported.</span></span> <span data-ttu-id="d9685-133">Исходное, целевое и результирующее выражения не могут включать в себя ссылки на функцию уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="d9685-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="d9685-134">Исходное и результирующее выражения должны возвращать один и тот же тип данных.</span><span class="sxs-lookup"><span data-stu-id="d9685-134">Source and destination expressions must evaluate to the same data type.</span></span> <span data-ttu-id="d9685-135">Возвращаемый тип совпадает с типом данных вычисленного результирующего выражения.</span><span class="sxs-lookup"><span data-stu-id="d9685-135">The return type is the same as the data type of the evaluated result expression.</span></span>  
  
-   <span data-ttu-id="d9685-136">Исходное, целевое и результирующее выражения не могут включать в себя ссылки на переменные отчета или группы.</span><span class="sxs-lookup"><span data-stu-id="d9685-136">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="d9685-137">Функцию `Lookup` нельзя использовать в качестве выражения для следующих элементов отчета:</span><span class="sxs-lookup"><span data-stu-id="d9685-137">`Lookup` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="d9685-138">динамические строки соединения для источника данных;</span><span class="sxs-lookup"><span data-stu-id="d9685-138">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="d9685-139">вычисляемые поля в наборе данных;</span><span class="sxs-lookup"><span data-stu-id="d9685-139">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="d9685-140">параметры запроса в наборе данных;</span><span class="sxs-lookup"><span data-stu-id="d9685-140">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="d9685-141">фильтры в наборе данных;</span><span class="sxs-lookup"><span data-stu-id="d9685-141">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="d9685-142">параметры отчета;</span><span class="sxs-lookup"><span data-stu-id="d9685-142">Report parameters.</span></span>  
  
    -   <span data-ttu-id="d9685-143">Свойство Report.Language.</span><span class="sxs-lookup"><span data-stu-id="d9685-143">The Report.Language property.</span></span>  
  
 <span data-ttu-id="d9685-144">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="d9685-144">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9685-145">Пример</span><span class="sxs-lookup"><span data-stu-id="d9685-145">Example</span></span>  
 <span data-ttu-id="d9685-146">В следующем примере предположим, что таблица привязана к набору данных, включающему в себя поле для идентификатора продукта ProductID.</span><span class="sxs-lookup"><span data-stu-id="d9685-146">In the following example, assume that a table is bound to a dataset that includes a field for the product identifier ProductID.</span></span> <span data-ttu-id="d9685-147">Отдельный набор данных с именем Product содержит соответствующий идентификатор продукта ID и его название Name.</span><span class="sxs-lookup"><span data-stu-id="d9685-147">A separate dataset called "Product" contains the corresponding product identifier ID and the product name Name.</span></span>  
  
 <span data-ttu-id="d9685-148">В следующем выражении функция `Lookup` сравнивает значение ProductID со значением ID для каждой из строк набора данных Product и, при совпадении, возвращает значение поля Name для этой строки.</span><span class="sxs-lookup"><span data-stu-id="d9685-148">In the following expression, `Lookup` compares the value of ProductID to ID in each row of the dataset called "Product" and, when a match is found, returns the value of the Name field for that row.</span></span>  
  
```  
=Lookup(Fields!ProductID.Value, Fields!ID.Value, Fields!Name.Value, "Product")  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9685-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="d9685-149">See Also</span></span>  
 <span data-ttu-id="d9685-150">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d9685-150">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d9685-151">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d9685-151">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d9685-152">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d9685-152">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d9685-153">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d9685-153">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
