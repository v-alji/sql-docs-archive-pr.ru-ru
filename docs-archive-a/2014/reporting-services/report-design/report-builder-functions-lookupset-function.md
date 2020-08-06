---
title: Функция LookupSet (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7685acfd-1c8d-420c-993c-903236fbe1ff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4edc7a17f2aa3813e8aa73e538594b5df3aeabc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659426"
---
# <a name="lookupset-function-report-builder-and-ssrs"></a><span data-ttu-id="0e344-102">Функция LookupSet (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="0e344-102">LookupSet Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0e344-103">Возвращает набор совпадающих значений для заданного имени из набора данных, содержащего пары «имя-значение».</span><span class="sxs-lookup"><span data-stu-id="0e344-103">Returns the set of matching values for the specified name from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="0e344-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e344-104">Syntax</span></span>  
  
```  
  
LookupSet(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e344-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0e344-105">Parameters</span></span>  
 <span data-ttu-id="0e344-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="0e344-106">*source_expression*</span></span>  
 <span data-ttu-id="0e344-107">(`Variant`) Выражение, вычисляемое в текущей области и указывающее имя или ключ для поиска.</span><span class="sxs-lookup"><span data-stu-id="0e344-107">(`Variant`) An expression that is evaluated in the current scope and that specifies the name or key to look up.</span></span> <span data-ttu-id="0e344-108">Например, `=Fields!ID.Value`.</span><span class="sxs-lookup"><span data-stu-id="0e344-108">For example, `=Fields!ID.Value`.</span></span>  
  
 <span data-ttu-id="0e344-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="0e344-109">*destination_expression*</span></span>  
 <span data-ttu-id="0e344-110">(`Variant`) Выражение, вычисляемое для каждой строки в наборе данных и указывающее имя или ключ для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="0e344-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="0e344-111">Например, `=Fields!CustomerID.Value`.</span><span class="sxs-lookup"><span data-stu-id="0e344-111">For example, `=Fields!CustomerID.Value`.</span></span>  
  
 <span data-ttu-id="0e344-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="0e344-112">*result_expression*</span></span>  
 <span data-ttu-id="0e344-113">( `Variant` ) Выражение, вычисляемое для строки в наборе данных, где *source_expression*  =  *destination_expression*, который указывает извлекаемое значение.</span><span class="sxs-lookup"><span data-stu-id="0e344-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="0e344-114">Например, `=Fields!PhoneNumber.Value`.</span><span class="sxs-lookup"><span data-stu-id="0e344-114">For example, `=Fields!PhoneNumber.Value`.</span></span>  
  
 <span data-ttu-id="0e344-115">*набор данных*</span><span class="sxs-lookup"><span data-stu-id="0e344-115">*dataset*</span></span>  
 <span data-ttu-id="0e344-116">Константа, задающая имя набора данных в отчете.</span><span class="sxs-lookup"><span data-stu-id="0e344-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="0e344-117">Например, «ContactInformation».</span><span class="sxs-lookup"><span data-stu-id="0e344-117">For example, "ContactInformation".</span></span>  
  
## <a name="return"></a><span data-ttu-id="0e344-118">Возвращает</span><span class="sxs-lookup"><span data-stu-id="0e344-118">Return</span></span>  
 <span data-ttu-id="0e344-119">Возвращает значение `VariantArray` или `Nothing`, если совпадения нет.</span><span class="sxs-lookup"><span data-stu-id="0e344-119">Returns a `VariantArray`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e344-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="0e344-120">Remarks</span></span>  
 <span data-ttu-id="0e344-121">Функция `LookupSet` служит для извлечения набора значений из указанного набора данных, состоящего из пар «имя-значение» со связью «один ко многим».</span><span class="sxs-lookup"><span data-stu-id="0e344-121">Use `LookupSet` to retrieve a set of values from the specified dataset for a name/value pair where there is a 1-to-many relationship.</span></span> <span data-ttu-id="0e344-122">Например, функция `LookupSet` позволяет извлечь по идентификатору пользователя в таблице все связанные с ним телефонные номера из набора данных, не привязанного к этой области данных.</span><span class="sxs-lookup"><span data-stu-id="0e344-122">For example, for a customer identifier in a table, you can use `LookupSet` to retrieve all the associated phone numbers for that customer from a dataset that is not bound to the data region.</span></span>  
  
 <span data-ttu-id="0e344-123">Функция `LookupSet` выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0e344-123">`LookupSet` does the following:</span></span>  
  
-   <span data-ttu-id="0e344-124">Вычисляет исходное выражение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="0e344-124">Evaluates the source expression in the current scope.</span></span>  
  
-   <span data-ttu-id="0e344-125">Вычисляет целевое выражение для каждой строки указанного набора данных после применения фильтров с учетом заданных для него параметров сортировки.</span><span class="sxs-lookup"><span data-stu-id="0e344-125">Evaluates the destination expression for each row of the specified dataset after filters have been applied, based on the collation of the specified dataset.</span></span>  
  
-   <span data-ttu-id="0e344-126">При каждом совпадении исходного и целевого выражений вычисляет результирующее выражение для этой строки в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="0e344-126">For each match of source expression and destination expression, evaluates the result expression for that row in the dataset.</span></span>  
  
-   <span data-ttu-id="0e344-127">Возвращает набор результирующих значений выражения.</span><span class="sxs-lookup"><span data-stu-id="0e344-127">Returns the set of result expression values.</span></span>  
  
 <span data-ttu-id="0e344-128">Для извлечения единственного значения для указанного имени из набора данных, состоящего из пар "имя-значение" со связью "один к одному", используйте [функцию Lookup (построитель отчетов и службы SSRS)](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="0e344-128">To retrieve a single value from a dataset with name/value pairs for a specified name where there is a 1-to-1 relationship, use [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span> <span data-ttu-id="0e344-129">Для вызова `Lookup` набора значений используйте [функцию много&#40;построитель отчетов и службы SSRS&#41;](report-builder-functions-multilookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="0e344-129">To call `Lookup` for a set of values, use [Multilookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-multilookup-function.md).</span></span>  
  
 <span data-ttu-id="0e344-130">Применяются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="0e344-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="0e344-131">Функция `LookupSet` вычисляется после применения всех выражений фильтров.</span><span class="sxs-lookup"><span data-stu-id="0e344-131">`LookupSet` is evaluated after all filter expressions are applied.</span></span>  
  
-   <span data-ttu-id="0e344-132">Поддерживается только один уровень уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="0e344-132">Only one level of lookup is supported.</span></span> <span data-ttu-id="0e344-133">Исходное, целевое и результирующее выражения не могут включать в себя ссылки на функцию уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="0e344-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="0e344-134">Исходное и результирующее выражения должны возвращать один и тот же тип данных.</span><span class="sxs-lookup"><span data-stu-id="0e344-134">Source and destination expressions must evaluate to the same data type.</span></span>  
  
-   <span data-ttu-id="0e344-135">Исходное, целевое и результирующее выражения не могут включать в себя ссылки на переменные отчета или группы.</span><span class="sxs-lookup"><span data-stu-id="0e344-135">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="0e344-136">Функцию `LookupSet` нельзя использовать в качестве выражения для следующих элементов отчета:</span><span class="sxs-lookup"><span data-stu-id="0e344-136">`LookupSet` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="0e344-137">динамические строки соединения для источника данных;</span><span class="sxs-lookup"><span data-stu-id="0e344-137">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="0e344-138">вычисляемые поля в наборе данных;</span><span class="sxs-lookup"><span data-stu-id="0e344-138">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="0e344-139">параметры запроса в наборе данных;</span><span class="sxs-lookup"><span data-stu-id="0e344-139">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="0e344-140">фильтры в наборе данных;</span><span class="sxs-lookup"><span data-stu-id="0e344-140">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="0e344-141">параметры отчета;</span><span class="sxs-lookup"><span data-stu-id="0e344-141">Report parameters.</span></span>  
  
    -   <span data-ttu-id="0e344-142">Свойство Report.Language.</span><span class="sxs-lookup"><span data-stu-id="0e344-142">The Report.Language property.</span></span>  
  
 <span data-ttu-id="0e344-143">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="0e344-143">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e344-144">Пример</span><span class="sxs-lookup"><span data-stu-id="0e344-144">Example</span></span>  
 <span data-ttu-id="0e344-145">В следующем примере предположим, что таблица привязана к набору данных, включающему идентификатор территории продаж TerritoryGroupID.</span><span class="sxs-lookup"><span data-stu-id="0e344-145">In the following example, assume the table is bound to a dataset that includes a sales territory identifier TerritoryGroupID.</span></span> <span data-ttu-id="0e344-146">Отдельный набор данных с именем Stores содержит список всех складов на данной территории и включает идентификатор ID и название склада StoreName.</span><span class="sxs-lookup"><span data-stu-id="0e344-146">A separate dataset called "Stores" contains the list of all stores in a territory and includes the territory identifier ID and the name of the store StoreName.</span></span>  
  
 <span data-ttu-id="0e344-147">В следующем выражении функция `LookupSet` сравнивает значение TerritoryGroupID со значением ID для каждой из строк набора данных Stores.</span><span class="sxs-lookup"><span data-stu-id="0e344-147">In the following expression, `LookupSet` compares the value TerritoryGroupID to ID for each row in the dataset called "Stores".</span></span> <span data-ttu-id="0e344-148">Для каждого совпадения значение поля StoreName в этой строке добавляется в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="0e344-148">For each match, the value of the StoreName field for that row is added to the result set.</span></span>  
  
```  
=LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores")  
```  
  
## <a name="example"></a><span data-ttu-id="0e344-149">Пример</span><span class="sxs-lookup"><span data-stu-id="0e344-149">Example</span></span>  
 <span data-ttu-id="0e344-150">Поскольку функция `LookupSet` возвращает коллекцию объектов, результирующее выражение невозможно непосредственно отобразить в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="0e344-150">Because `LookupSet` returns a collection of objects, you cannot display the result expression directly in a text box.</span></span> <span data-ttu-id="0e344-151">Значения объектов коллекции можно склеить в одну строку.</span><span class="sxs-lookup"><span data-stu-id="0e344-151">You can concatenate the value of each object in the collection as a string.</span></span>  
  
 <span data-ttu-id="0e344-152">Функция [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]`Join` позволяет создать из набора объектов строку с разделителями.</span><span class="sxs-lookup"><span data-stu-id="0e344-152">Use the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] function `Join` create a delimited string from a set of objects.</span></span> <span data-ttu-id="0e344-153">Для объединения объектов в одну строку используйте в качестве разделителя запятую.</span><span class="sxs-lookup"><span data-stu-id="0e344-153">Use a comma as a separator to combine the objects in a single line.</span></span> <span data-ttu-id="0e344-154">В некоторых модулях подготовки можно использовать в качестве разделителя перевод строки [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] (`vbCrLF`).</span><span class="sxs-lookup"><span data-stu-id="0e344-154">In some renderers, you might use a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] line feed (`vbCrLF`) as a separator to list each value on a new line.</span></span>  
  
 <span data-ttu-id="0e344-155">Следующее выражение, когда оно используется как свойство Value для текстового поля, использует `Join` для создания списка.</span><span class="sxs-lookup"><span data-stu-id="0e344-155">The following expression, when it is used as the Value property for a text box, uses `Join` to create a list.</span></span>  
  
```  
=Join(LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores"),",")  
```  
  
## <a name="example"></a><span data-ttu-id="0e344-156">Пример</span><span class="sxs-lookup"><span data-stu-id="0e344-156">Example</span></span>  
 <span data-ttu-id="0e344-157">Для текстовых полей, подготовка которых к просмотру выполняется лишь несколько раз, можно добавить пользовательский код формирования HTML для отображения значений в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="0e344-157">For text boxes that only render a few times, you might choose to add custom code to generate HTML to display values in a text box.</span></span> <span data-ttu-id="0e344-158">HTML в текстовом поле требует дополнительной обработки, поэтому плохо подходит для текстовых полей, подготовка которых выполняется тысячи раз.</span><span class="sxs-lookup"><span data-stu-id="0e344-158">HTML in a text box requires extra processing, so this would not be a good choice for a text box that is rendered thousands of times.</span></span>  
  
 <span data-ttu-id="0e344-159">Скопируйте следующие функции [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] в блок кода.</span><span class="sxs-lookup"><span data-stu-id="0e344-159">Copy the following [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to a Code block in a report definition.</span></span> <span data-ttu-id="0e344-160">Функция**MakeList** принимает массив объектов, возвращаемый из *result_expression* , и строит неупорядоченный список с помощью тегов HTML.</span><span class="sxs-lookup"><span data-stu-id="0e344-160">**MakeList** takes the object array that is returned in *result_expression* and builds an unordered list by using HTML tags.</span></span> <span data-ttu-id="0e344-161">Свойство**Length** возвращает число элементов в массиве объектов.</span><span class="sxs-lookup"><span data-stu-id="0e344-161">**Length** returns the number of items in the object array.</span></span>  
  
```  
Function MakeList(ByVal items As Object()) As String  
   If items Is Nothing Then  
      Return Nothing  
   End If  
  
   Dim builder As System.Text.StringBuilder =   
      New System.Text.StringBuilder()  
   builder.Append("<ul>")  
  
   For Each item As Object In items  
      builder.Append("<li>")  
      builder.Append(item)  
   Next  
   builder.Append("</ul>")  
  
   Return builder.ToString()  
End Function  
  
Function Length(ByVal items as Object()) as Integer  
   If items is Nothing Then  
      Return 0  
   End If  
   Return items.Length  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="0e344-162">Пример</span><span class="sxs-lookup"><span data-stu-id="0e344-162">Example</span></span>  
 <span data-ttu-id="0e344-163">Для формирования HTML необходимо вызвать функцию.</span><span class="sxs-lookup"><span data-stu-id="0e344-163">To generate the HTML, you must call the function.</span></span> <span data-ttu-id="0e344-164">Вставьте следующее выражение в свойство Value текстового поля и задайте для типа разметки текста значение HTML.</span><span class="sxs-lookup"><span data-stu-id="0e344-164">Paste the following expression in the Value property for the text box and set the markup type for text to HTML.</span></span> <span data-ttu-id="0e344-165">Дополнительные сведения см. в разделе [Добавление HTML в отчет (построитель отчетов и службы SSRS)](add-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0e344-165">For more information, see [Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
```  
=Code.MakeList(LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores"))  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e344-166">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e344-166">See Also</span></span>  
 <span data-ttu-id="0e344-167">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0e344-167">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0e344-168">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0e344-168">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0e344-169">[Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0e344-169">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0e344-170">Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="0e344-170">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
