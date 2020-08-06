---
title: Синтаксис и примеры фильтра модели (Analysis Services — интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filter syntax [data mining]
- filters [data mining]
- filters [Analysis Services]
ms.assetid: c729d9b3-8fda-405e-9497-52b2d7493eae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7ca200d179c0fe81b948793a4b4478f71502657
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728970"
---
# <a name="model-filter-syntax-and-examples-analysis-services---data-mining"></a><span data-ttu-id="9ecc7-102">Синтаксис и примеры фильтра модели (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="9ecc7-102">Model Filter Syntax and Examples (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="9ecc7-103">В этом разделе приводятся сведения о синтаксисе фильтров моделей, а также образцы критериев.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-103">This section provides detailed information about the syntax for model filters, together with sample expressions.</span></span>  
  
 
  
##  <a name="filter-syntax"></a><a name="bkmk_Syntax"></a> <span data-ttu-id="9ecc7-104">Filter Syntax</span><span class="sxs-lookup"><span data-stu-id="9ecc7-104">Filter Syntax</span></span>  
 <span data-ttu-id="9ecc7-105">Критерии фильтра обычно эквивалентны содержимому предложения WHERE.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-105">Filter expressions generally are equivalent to the content of a WHERE clause.</span></span> <span data-ttu-id="9ecc7-106">Можно соединить несколько условий с помощью логических операторов `AND`, `OR` и `NOT`.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-106">You can connect multiple conditions by using the logical operators `AND`, `OR`, and `NOT`.</span></span>  
  
 <span data-ttu-id="9ecc7-107">Во вложенных таблицах также можно использовать операторы `EXISTS` и `NOT EXISTS`.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-107">In nested tables, you can also use the `EXISTS` and `NOT EXISTS` operators.</span></span> <span data-ttu-id="9ecc7-108">Условие `EXISTS` принимает значение `true`, если вложенный запрос возвращает, по крайней мере, одну строку.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-108">An `EXISTS` condition evaluates to `true` if the subquery returns at least one row.</span></span> <span data-ttu-id="9ecc7-109">Это может быть удобно в тех случаях, когда необходимо ограничить модель вариантами, содержащими определенное значение во вложенной таблице, например покупатели, купившие товар по крайней мере один раз.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-109">This is useful in cases where you want to restrict the model to cases that contain a particular value in the nested table: for example, customers who have purchased an item at least once.</span></span>  
  
 <span data-ttu-id="9ecc7-110">Условие `NOT EXISTS` принимает значение `true`, если условие, указанное во вложенном запросе, не существует.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-110">A `NOT EXISTS` condition evaluates to `true` if the condition specified in the subquery does not exist.</span></span> <span data-ttu-id="9ecc7-111">Например, можно создать для модели ограничение, касающееся клиентов, которые не покупали определенный товар.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-111">An example is when you want to restrict the model to customers who have never purchased a particular item.</span></span>  
  
 <span data-ttu-id="9ecc7-112">Общий синтаксис выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9ecc7-112">The general syntax is as follows:</span></span>  
  
```  
<filter>::=<predicate list>  | ( <predicate list> )  
<predicate list>::= <predicate> | [<logical_operator> <predicate list>]   
<logical_operator::= AND| OR  
<predicate>::= NOT <predicate>|( <predicate> ) <avPredicate> | <nestedTablePredicate> | ( <predicate> )   
<avPredicate>::= <columnName> <operator> <scalar> | <columnName> IS [NOT] NULL  
<operator>::= = | != | <> | > | >= | < | <=  
<nestedTablePredicate>::= EXISTS (<subquery>)  
<subquery>::=SELECT * FROM <columnName>[ WHERE  <predicate list> ]  
```  
  
 <span data-ttu-id="9ecc7-113">*Фильтрация*</span><span class="sxs-lookup"><span data-stu-id="9ecc7-113">*filter*</span></span>  
 <span data-ttu-id="9ecc7-114">Содержит один или несколько предикатов, соединенных логическими операторами.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-114">Contains one or more predicates, connected by logical operators.</span></span>  
  
 <span data-ttu-id="9ecc7-115">*predicate list*</span><span class="sxs-lookup"><span data-stu-id="9ecc7-115">*predicate list*</span></span>  
 <span data-ttu-id="9ecc7-116">Один или несколько критериев фильтра, разделенных логическими операторами.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-116">One or more valid filter expressions, separated by logical operators.</span></span>  
  
 <span data-ttu-id="9ecc7-117">*columnName*</span><span class="sxs-lookup"><span data-stu-id="9ecc7-117">*columnName*</span></span>  
 <span data-ttu-id="9ecc7-118">Имя столбца структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-118">The name of a mining structure column.</span></span>  
  
 <span data-ttu-id="9ecc7-119">логический оператор</span><span class="sxs-lookup"><span data-stu-id="9ecc7-119">logical operator</span></span>  
 <span data-ttu-id="9ecc7-120">`AND`, `OR`, `NOT`</span><span class="sxs-lookup"><span data-stu-id="9ecc7-120">`AND`, `OR`, `NOT`</span></span>  
  
 <span data-ttu-id="9ecc7-121">*avPredicate*</span><span class="sxs-lookup"><span data-stu-id="9ecc7-121">*avPredicate*</span></span>  
 <span data-ttu-id="9ecc7-122">Критерий фильтра, применимый только к скалярному столбцу структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-122">Filter expression that can be applied to scalar mining structure column only.</span></span> <span data-ttu-id="9ecc7-123">Критерий *avPredicate* может быть использован и в фильтрах моделей, и в фильтрах вложенных таблиц.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-123">An *avPredicate* expression can be used in both model filters or nested table filters.</span></span>  
  
 <span data-ttu-id="9ecc7-124">Критерий, в котором используется любой из перечисленных ниже операторов, может быть применен только к непрерывному столбцу.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-124">An expression that uses any of the following operators can only be applied to a continuous column.</span></span> <span data-ttu-id="9ecc7-125">:</span><span class="sxs-lookup"><span data-stu-id="9ecc7-125">:</span></span>  
  
-   <span data-ttu-id="9ecc7-126">**\<**(меньше)</span><span class="sxs-lookup"><span data-stu-id="9ecc7-126">**\<** (less than)</span></span>  
  
-   <span data-ttu-id="9ecc7-127">**>**(больше)</span><span class="sxs-lookup"><span data-stu-id="9ecc7-127">**>** (greater than)</span></span>  
  
-   <span data-ttu-id="9ecc7-128">**>=**(больше или равно)</span><span class="sxs-lookup"><span data-stu-id="9ecc7-128">**>=** (greater than or equal to)</span></span>  
  
-   <span data-ttu-id="9ecc7-129">**\<=**(меньше или равно)</span><span class="sxs-lookup"><span data-stu-id="9ecc7-129">**\<=** (less than or equal to)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ecc7-130">Вне зависимости от типа данных эти операторы не могут быть применены к столбцам, имеющим тип `Discrete`, `Discretized` или `Key`.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-130">Regardless of the data type, these operators cannot be applied to a column that has the type `Discrete`, `Discretized`, or `Key`.</span></span>  
  
 <span data-ttu-id="9ecc7-131">Выражение, в котором используется любой из перечисленных ниже операторов, может быть применен к непрерывному, дискретному, дискретизированному или ключевому столбцу.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-131">An expression that uses any of the following operators can be applied to a continuous, discrete, discretized, or key column:</span></span>  
  
-   <span data-ttu-id="9ecc7-132">**=** прошлом</span><span class="sxs-lookup"><span data-stu-id="9ecc7-132">**=** (equals)</span></span>  
  
-   <span data-ttu-id="9ecc7-133">**! =** (не равно)</span><span class="sxs-lookup"><span data-stu-id="9ecc7-133">**!=** (not equal to)</span></span>  
  
-   <span data-ttu-id="9ecc7-134">**ИМЕЕТ ЗНАЧЕНИЕ NULL**</span><span class="sxs-lookup"><span data-stu-id="9ecc7-134">**IS NULL**</span></span>  
  
 <span data-ttu-id="9ecc7-135">Если критерий *avPredicate*применяется к дискретизированному столбцу, то в фильтре может использоваться любое значение из конкретного сегмента.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-135">If the argument, *avPredicate*, applies to a discretized column, the value used in the filter can be any value in a specific bucket.</span></span>  
  
 <span data-ttu-id="9ecc7-136">Иными словами, условие не определяется как `AgeDisc = '25-35'`. Вместо этого вычисляется, а затем используется значение из этого интервала.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-136">In other words, you do not define the condition as `AgeDisc = '25-35'`, but instead compute and then use a value from that interval.</span></span>  
  
 <span data-ttu-id="9ecc7-137">Пример:  `AgeDisc = 27`  означает любое значение в том же интервале, что и 27. В данном случае этот интервал 25–35.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-137">Example:  `AgeDisc = 27`  means any value in the same interval as 27, which in this case is 25-35.</span></span>  
  
 <span data-ttu-id="9ecc7-138">*nestedTablePredicate*</span><span class="sxs-lookup"><span data-stu-id="9ecc7-138">*nestedTablePredicate*</span></span>  
 <span data-ttu-id="9ecc7-139">Критерий фильтра, применяющийся к вложенной таблице.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-139">Filter expression that applies to a nested table.</span></span> <span data-ttu-id="9ecc7-140">Может использоваться только в фильтрах модели.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-140">Can be used in model filters only.</span></span>  
  
 <span data-ttu-id="9ecc7-141">Аргумент вложенного запроса критерия для аргумента *nestedTablePredicate*может применяться только к столбцу структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9ecc7-141">The sub-query argument of the argument, *nestedTablePredicate*, can only apply to a table mining structure column</span></span>  
  
 <span data-ttu-id="9ecc7-142">вложенный запрос</span><span class="sxs-lookup"><span data-stu-id="9ecc7-142">subquery</span></span>  
 <span data-ttu-id="9ecc7-143">Инструкция SELECT, за которой следует допустимый предикат или список предикатов.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-143">A SELECT statement followed by a valid predicate or list of predicates.</span></span>  
  
 <span data-ttu-id="9ecc7-144">Все предикаты должны иметь тип, описанный в *avPredicates*.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-144">All the predicates must be of the type described in *avPredicates*.</span></span> <span data-ttu-id="9ecc7-145">Кроме того, предикаты должны ссылаться только на столбцы, включенные в текущую вложенную таблицу, определяемую аргументом *columnName*.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-145">Furthermore, the predicates can refer only to columns that are included in the current nested table, identified by the argument, *columnName*.</span></span>  
  
### <a name="limitations-on-filter-syntax"></a><span data-ttu-id="9ecc7-146">Ограничения синтаксиса фильтра</span><span class="sxs-lookup"><span data-stu-id="9ecc7-146">Limitations on Filter Syntax</span></span>  
 <span data-ttu-id="9ecc7-147">На фильтры налагаются следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-147">The following restrictions apply to filters:</span></span>  
  
-   <span data-ttu-id="9ecc7-148">Фильтр может содержать только простые предикаты.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-148">A filter can contain only simple predicates.</span></span> <span data-ttu-id="9ecc7-149">Они включают математические операторы, скалярные переменные и имена столбцов.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-149">These include mathematical operators, scalars, and column names.</span></span>  
  
-   <span data-ttu-id="9ecc7-150">В синтаксисе фильтров не допускаются определяемые пользователем функции.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-150">User-defined functions are not supported in the filter syntax.</span></span>  
  
-   <span data-ttu-id="9ecc7-151">Операторы, не являющиеся логическими, например знаки плюса и минуса, не поддерживаются в синтаксисе фильтров.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-151">Non-Boolean operators, such as the plus or minus signs, are not supported in the filter syntax.</span></span>  
  
## <a name="examples-of-filters"></a><span data-ttu-id="9ecc7-152">Примеры фильтров</span><span class="sxs-lookup"><span data-stu-id="9ecc7-152">Examples of Filters</span></span>  
 <span data-ttu-id="9ecc7-153">В следующих примерах демонстрируется применение фильтров к модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-153">The following examples demonstrate the use of filters applied to a mining model.</span></span> <span data-ttu-id="9ecc7-154">Если критерий фильтра создается в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], в окне **Свойство** , на панели **Выражение** диалогового окна "Фильтр", то будет видна только строка, которая появляется за ключевыми словами WITH FILTER.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-154">If you create the filter expression by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Property** window and the **Expression** pane of the filter dialog box, you would see only the string that appears after the WITH FILTER keywords.</span></span> <span data-ttu-id="9ecc7-155">Определение структуры интеллектуального анализа данных было включено, чтобы легче понять типы столбцов и методы их использования.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-155">Here, the definition of the mining structure is included to make it easier to understand the column type and usage.</span></span>  
  
###  <a name="example-1-typical-case-level-filtering"></a><a name="bkmk_Ex1"></a> <span data-ttu-id="9ecc7-156">Пример 1. Обычная фильтрация на уровне вариантов</span><span class="sxs-lookup"><span data-stu-id="9ecc7-156">Example 1: Typical Case-Level Filtering</span></span>  
 <span data-ttu-id="9ecc7-157">В этом примере показан простой фильтр, который ограничивает варианты, используемые в модели, пользователями, имеющими профессию архитектора и возраст старше 30 лет.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-157">This example shows a simple filter that restricts the cases used in the model to customers whose occupation is architect and whose age is over 30.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_1  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH FILTER (Age > 30 AND Occupation='Architect')  
```  
  

  
###  <a name="example-2-case-level-filtering-using-nested-table-attributes"></a><a name="bkmk_Ex2"></a> <span data-ttu-id="9ecc7-158">Пример 2. Фильтрация на уровне вариантов с использованием атрибутов вложенной таблицы</span><span class="sxs-lookup"><span data-stu-id="9ecc7-158">Example 2: Case-Level Filtering using Nested Table Attributes</span></span>  
 <span data-ttu-id="9ecc7-159">Если в структуре интеллектуального анализа данных содержатся вложенные таблицы, осуществлять фильтрацию можно по существованию значения во всей таблице либо по конкретным строкам вложенной таблицы, в которых содержится конкретное значение.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-159">If your mining structure contains nested tables, you can either filter on the existence of a value in a nested table, or filter on nested table rows that contain a specific value.</span></span> <span data-ttu-id="9ecc7-160">В этом примере для модели ограничиваются только покупатели старше 30 лет, которые совершили по крайней мере одну покупку, включающую молоко.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-160">This example restricts the cases used for the model to customers over the age of 30 who made at least one purchase that included milk.</span></span>  
  
 <span data-ttu-id="9ecc7-161">В этом примере показано, что в фильтре могут использоваться столбцы, которых нет в модели.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-161">As this example shows, it is not necessary that the filter use only columns that are included in the model.</span></span> <span data-ttu-id="9ecc7-162">Вложенная таблица **Products** является частью структуры интеллектуального анализа данных, но не включена в модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-162">The nested table **Products** is part of the mining structure, but is not included in the mining model.</span></span> <span data-ttu-id="9ecc7-163">Несмотря на это, фильтры могут применяться к значениям и атрибутам этой вложенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-163">However, you can still filter on values and attributes in the nested table.</span></span> <span data-ttu-id="9ecc7-164">Чтобы просматривать сведения о таких вариантах, необходимо включить детализацию.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-164">To view the details of these cases, drillthrough must be enabled.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_2  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH DRILLTHROUGH,   
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk')  
)  
```  
  
 
  
###  <a name="example-3-case-level-filtering-on-multiple-nested-table-attributes"></a><a name="bkmk_Ex3"></a> <span data-ttu-id="9ecc7-165">Пример 3. Фильтрация на уровне вариантов по нескольким атрибутам вложенной таблицы</span><span class="sxs-lookup"><span data-stu-id="9ecc7-165">Example 3: Case-Level Filtering on Multiple Nested Table Attributes</span></span>  
 <span data-ttu-id="9ecc7-166">В этом примере показан фильтр, состоящий из трех частей: условия, применяемого к таблице вариантов, второго условия, касающегося атрибута вложенной таблицы, и третьего условия, касающегося определенного значения в одном из столбцов вложенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-166">This example shows a three-part filter: a condition applies to the case table, another condition to an attribute in the nested table, and another condition on a specific value in one of the nested table columns.</span></span>  
  
 <span data-ttu-id="9ecc7-167">Первое условие фильтра, `Age > 30`, применяется к столбцу в таблице вариантов.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-167">The first condition in the filter, `Age > 30`, applies to a column in the case table.</span></span> <span data-ttu-id="9ecc7-168">Остальные условия применяются к вложенной таблице.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-168">The remaining conditions apply to the nested table.</span></span>  
  
 <span data-ttu-id="9ecc7-169">Второе условие, `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`, проверяет наличие во вложенной таблице по крайней мере одной покупки, включающей молоко.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-169">The second condition, `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`, checks for the presence of at least one purchase in the nested table that included milk.</span></span> <span data-ttu-id="9ecc7-170">Третье условие, `Quantity>=2`, обозначает, что заказчик должен был купить по крайней мере две упаковки молока за одну транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-170">The third condition, `Quantity>=2`, means that the customer must have purchased at least two units of milk in a single transaction.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_3  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
)  
)  
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk'  AND Quantity >= 2)   
)  
```  
  

  
###  <a name="example-4-case-level-filtering-on-absence-of-nested-table-attributes"></a><a name="bkmk_Ex4"></a> <span data-ttu-id="9ecc7-171">Пример 4. Фильтрация на уровне вариантов по отсутствию атрибутов вложенной таблицы</span><span class="sxs-lookup"><span data-stu-id="9ecc7-171">Example 4: Case-Level Filtering On Absence of Nested Table Attributes</span></span>  
 <span data-ttu-id="9ecc7-172">В этом примере показано, как можно ограничить выбор вариантов покупателями, которые не приобретали определенный товар, с помощью фильтрации по атрибута во вложенной таблице.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-172">This example shows how to limit cases to customer who did not purchase a specific item, by filtering on the absence of an attribute in the nested table.</span></span> <span data-ttu-id="9ecc7-173">В этом примере модель обучается на данных о клиентах старше 30 лет, которые никогда не покупали молоко.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-173">In this example, the model is trained using customers over the age of 30 who have never bought milk.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_4  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName  
)  
)  
FILTER (Age > 30 AND NOT EXISTS (SELECT * FROM Products WHERE ProductName='Milk') )  
```  
  

  
###  <a name="example-5-filtering-on-multiple-nested-table-values"></a><a name="bkmk_Ex5"></a> <span data-ttu-id="9ecc7-174">Пример 5. Фильтрация по нескольким значениям вложенной таблицы</span><span class="sxs-lookup"><span data-stu-id="9ecc7-174">Example 5: Filtering on Multiple Nested Table Values</span></span>  
 <span data-ttu-id="9ecc7-175">Целью этого примера является демонстрация фильтрации во вложенной таблице.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-175">The purpose of the example is to show nested table filtering.</span></span> <span data-ttu-id="9ecc7-176">Фильтр вложенной таблицы применяется после фильтра вариантов и ограничивает только строки вложенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-176">The nested table filter is applied after the case filter, and only restricts nested table rows.</span></span>  
  
 <span data-ttu-id="9ecc7-177">В этой модели может содержаться несколько вариантов с пустыми вложенными таблицами, поскольку инструкция EXISTS не была указана.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-177">This model could contain multiple cases with empty nested tables because EXISTS is not specified.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_5  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
WITH DRILLTHROUGH  
```  
  

  
###  <a name="example-6-filtering-on-nested-table-attributes-and-exists"></a><a name="bkmk_Ex6"></a> <span data-ttu-id="9ecc7-178">Пример 6. Фильтрация по атрибутам вложенной таблицы с инструкцией EXISTS</span><span class="sxs-lookup"><span data-stu-id="9ecc7-178">Example 6: Filtering on Nested Table Attributes and EXISTS</span></span>  
 <span data-ttu-id="9ecc7-179">В этом примере фильтр для вложенной таблицы ограничивает строки, в которых содержится либо молоко, либо бутилированная вода.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-179">In this example, the filter on the nested table restricts the rows to those that contain either milk or bottled water.</span></span> <span data-ttu-id="9ecc7-180">Затем происходит фильтрация вариантов в модели с помощью инструкции `EXISTS`.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-180">Then, the cases in the model are restricted by using an `EXISTS` statement.</span></span> <span data-ttu-id="9ecc7-181">Это гарантирует, что вложенная таблица не будет пустой.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-181">This makes sure that the nested table is not empty.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_6  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
FILTER (EXISTS (Products))  
```  
  

  
###  <a name="example-7-complex-filter-combinations"></a><a name="bkmk_Ex7"></a> <span data-ttu-id="9ecc7-182">Пример 7. Сложные сочетания фильтров</span><span class="sxs-lookup"><span data-stu-id="9ecc7-182">Example 7: Complex Filter Combinations</span></span>  
 <span data-ttu-id="9ecc7-183">Сценарий для этой модели напоминает сценарий из примера 4, но здесь он более сложный.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-183">The scenario for this model resembles that of Example 4, but is far more complex.</span></span> <span data-ttu-id="9ecc7-184">Вложенная таблица **ProductsOnSale**имеет условие фильтра `(OnSale)` , означающее, что значение **onsale** должно быть `true` для продукта, указанного в поле **ProductName**.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-184">The nested table, **ProductsOnSale**, has the filter condition `(OnSale)` meaning that the value of **OnSale** must be `true` for the product listed in **ProductName**.</span></span> <span data-ttu-id="9ecc7-185">Здесь **OnSale** — это столбец структуры.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-185">Here, **OnSale** is a structure column.</span></span>  
  
 <span data-ttu-id="9ecc7-186">Вторая часть фильтра для **ProductsNotOnSale**повторяет этот синтаксис, но фильтрует по продуктам, для которых значение **onsale** равно `not true``(!OnSale)` .</span><span class="sxs-lookup"><span data-stu-id="9ecc7-186">The second part of the filter, for **ProductsNotOnSale**, repeats this syntax, but filters on products for which the value of **OnSale** is `not true``(!OnSale)`.</span></span>  
  
 <span data-ttu-id="9ecc7-187">Затем эти условия объединяются, а на таблицу вариантов накладывается одно дополнительное ограничение.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-187">Finally, the conditions are combined and one additional restriction is added to the case table.</span></span> <span data-ttu-id="9ecc7-188">В результате прогнозируются покупки продуктов в списке **ProductsNotOnSale** на основе вариантов, включенных в список **ProductsOnSale** , для покупателей старше 25 лет.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-188">The result is to predict purchases of products in the **ProductsNotOnSale** list, based on the cases that are included in the **ProductsOnSale** list, for all customers over the age of 25.</span></span>  
  
 `ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_7`  
  
 `(`  
  
 `CustomerId,`  
  
 `Age,`  
  
 `Occupation,`  
  
 `MaritalStatus,`  
  
 `ProductsOnSale`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(OnSale),`  
  
 `ProductsNotOnSale PREDICT ONLY`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(!OnSale)`  
  
 `)`  
  
 `WITH DRILLTHROUGH,`  
  
 `FILTER (EXISTS (ProductsOnSale) AND EXISTS(ProductsNotOnSale) AND Age > 25)`  
  
  
  
###  <a name="example-8-filtering-on-dates"></a><a name="bkmk_Ex8"></a> <span data-ttu-id="9ecc7-189">Пример 8. Фильтрация по датам</span><span class="sxs-lookup"><span data-stu-id="9ecc7-189">Example 8: Filtering on Dates</span></span>  
 <span data-ttu-id="9ecc7-190">Входные столбцы можно фильтровать по датам, так же как и по любым другим данным.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-190">You can filter input columns on dates, as you would any other data.</span></span> <span data-ttu-id="9ecc7-191">Даты, содержащиеся в столбце типа «дата/время», являются непрерывными значениями, поэтому можно указать диапазон дат, используя операторы, такие как «больше» (>) и «меньше» (<).</span><span class="sxs-lookup"><span data-stu-id="9ecc7-191">Dates contained in a column of type date/time are continuous values; therefore, you can specify a date range by using operators such as greater than (>) or less than (<).</span></span> <span data-ttu-id="9ecc7-192">Если источник данных представляет даты не как непрерывный тип данных, а как дискретные или текстовые значения, то выполнять фильтрацию по диапазону дат нельзя, необходимо указывать отдельные дискретные значения.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-192">If your data source does not represent dates by a Continuous data type, but as discrete or text values, you cannot filter on a date range, but must specify individual discrete values.</span></span>  
  
 <span data-ttu-id="9ecc7-193">Однако нельзя задать фильтр по столбцу дат в модели временных рядов в том случае, если столбец дат, используемый для фильтрации, также является ключевым столбцом для модели.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-193">However, you cannot create a filter on the date column in a time series model if the date column used for the filter is also the key column for the model.</span></span> <span data-ttu-id="9ecc7-194">Это связано с тем, что в моделях временных рядов и в моделях кластеризации последовательностей столбец дат может обрабатываться как тип `KeyTime` или тип `KeySequence`.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-194">That is because, in time series models and sequence clustering models, the date column might be handled as type `KeyTime` or `KeySequence`.</span></span>  
  
 <span data-ttu-id="9ecc7-195">Если необходимо выполнить фильтрацию по непрерывно расположенным датам в модели временных рядов, то можно создать копию столбца в структуре интеллектуального анализа данных и выполнить фильтрацию в модели по этому новому столбцу.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-195">If you need to filter on continuous dates in a time series model, you can create a copy of the column in the mining structure, and filter the model on the new column.</span></span>  
  
 <span data-ttu-id="9ecc7-196">Например, следующее выражение представляет фильтр для столбца дат типа `Continuous`, добавленного в модель прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-196">For example, the following expression represents a filter on a date column of type `Continuous` that has been added to the Forecasting model.</span></span>  
  
 `=[DateCopy] > '12:31:2003:00:00:00'`  
  
> [!NOTE]  
>  <span data-ttu-id="9ecc7-197">Следует заметить, что любые дополнительные столбцы, добавленные в модель, могут повлиять на результат.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-197">Note that any extra columns that you add to the model might affect the results.</span></span> <span data-ttu-id="9ecc7-198">В связи с этим, если этот столбец не должен быть использован при вычислении рядов, его следует добавить только в структуру интеллектуального анализа данных, но не в модель.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-198">Therefore, if you do not want the column to be used in computation of the series, you should add the column only to the mining structure, and not to the model.</span></span> <span data-ttu-id="9ecc7-199">Также для столбца можно установить флаг модели `PredictOnly` или `Ignore`.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-199">You can also set the model flag on the column to `PredictOnly` or to `Ignore`.</span></span> <span data-ttu-id="9ecc7-200">Дополнительные сведения см. в разделе [Флаги моделирования (интеллектуальный анализ данных)](modeling-flags-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9ecc7-200">For more information, see [Modeling Flags &#40;Data Mining&#41;](modeling-flags-data-mining.md).</span></span>  
  
 <span data-ttu-id="9ecc7-201">Для других типов моделей даты можно использовать в качестве входных критериев или условий критерия, как и в любых других столбцах.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-201">For other model types, you can use dates as input criteria or filter criteria just like you would in any other column.</span></span> <span data-ttu-id="9ecc7-202">Однако, если необходимо использовать определенный уровень гранулярности, который не поддерживается типом данных `Continuous`, можно создать производное значение в источнике данных, использовав выражения для извлечения единицы, которая будет использоваться при фильтрации и анализе.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-202">However, if you need to use a specific level of granularity that is not supported by a `Continuous` data type, you can create a derived value in the data source by using expressions to extract the unit to use in filtering and analysis.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="9ecc7-203">Если в качестве условия фильтра вы указываете даты, следует использовать формат `mm/dd/yyyy`, независимо от формата даты для используемой операционной системы.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-203">When you specify a dates as filter criteria, you must use the following format, regardless of the date format for the current OS: `mm/dd/yyyy`.</span></span> <span data-ttu-id="9ecc7-204">Любой другой формат приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-204">Any other format results in an error.</span></span>  
  
 <span data-ttu-id="9ecc7-205">Например, если необходимо фильтровать результаты центра обработки вызовов, чтобы отображались только данные за выходные, то можно создать выражение в представлении источника данных, извлекающее название дня недели для каждой даты, а затем использовать название дня в качестве входных данных или как дискретное значение при фильтрации.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-205">For example, if you want to filter your call center results to show only weekends, you can create an expression in the data source view that extracts the weekday name for each date, and then use that weekday name value for input or as a discrete value in filtering.</span></span> <span data-ttu-id="9ecc7-206">Однако следует помнить, что повторяющиеся значения также могут повлиять на модель, поэтому следует использовать только один из столбцов и не использовать совместно столбец дат и производное значение.</span><span class="sxs-lookup"><span data-stu-id="9ecc7-206">Just remember that repeating values can affect the model, so you should use only one of the columns, not the date column plus the derived value.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="9ecc7-207">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ecc7-207">See Also</span></span>  
 <span data-ttu-id="9ecc7-208">[Фильтры для моделей интеллектуального анализа данных &#40;Analysis Services интеллектуального анализа&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="9ecc7-208">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="9ecc7-209">Тестирование и проверка (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="9ecc7-209">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
  
