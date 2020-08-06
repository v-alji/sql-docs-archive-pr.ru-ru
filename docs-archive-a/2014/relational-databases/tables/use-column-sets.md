---
title: Использование наборов столбцов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- sparse columns, column sets
- column sets
ms.assetid: a4f9de95-dc8f-4ad8-b957-137e32bfa500
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9cb496137c3986b78a55862e434c153d354a42ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668727"
---
# <a name="use-column-sets"></a><span data-ttu-id="11a44-102">Использование наборов столбцов</span><span class="sxs-lookup"><span data-stu-id="11a44-102">Use Column Sets</span></span>
  <span data-ttu-id="11a44-103">В таблицах, использующих разреженные столбцы, можно назначить набор столбцов, который будет возвращать все разреженные столбцы в таблице.</span><span class="sxs-lookup"><span data-stu-id="11a44-103">Tables that use sparse columns can designate a column set to return all sparse columns in the table.</span></span> <span data-ttu-id="11a44-104">Набор столбцов — это нетипизированное XML-представление, которое объединяет на выходе все разреженные столбцы таблицы в структурированном виде.</span><span class="sxs-lookup"><span data-stu-id="11a44-104">A column set is an untyped XML representation that combines all the sparse columns of a table into a structured output.</span></span> <span data-ttu-id="11a44-105">Набор столбцов похож на вычисляемые столбцы тем, что набор столбцов физически не хранится в таблице.</span><span class="sxs-lookup"><span data-stu-id="11a44-105">A column set is like a calculated column in that the column set is not physically stored in the table.</span></span> <span data-ttu-id="11a44-106">Набор столбцов отличается от вычисляемого столбца тем, что он может быть напрямую обновлен.</span><span class="sxs-lookup"><span data-stu-id="11a44-106">A column set differs from a calculated column in that the column set is directly updatable.</span></span>  
  
 <span data-ttu-id="11a44-107">Наборы столбцов следует использовать в том случае, если в таблице существует большое число столбцов и работать с ними по отдельности неудобно.</span><span class="sxs-lookup"><span data-stu-id="11a44-107">You should consider using column sets when the number of columns in a table is large, and operating on them individually is cumbersome.</span></span> <span data-ttu-id="11a44-108">У приложений может возрасти производительность, если они будут выбирать и вставлять данные в таблицы, имеющие много столбцов, с помощью наборов столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-108">Applications might see some performance improvement when they select and insert data by using column sets on tables that have lots of columns.</span></span> <span data-ttu-id="11a44-109">Однако производительность наборов столбцов может уменьшиться, если для столбцов в таблице было определено большое количество индексов.</span><span class="sxs-lookup"><span data-stu-id="11a44-109">However, the performance of column sets can be reduced when many indexes are defined on the columns in the table.</span></span> <span data-ttu-id="11a44-110">Это происходит из-за увеличения объема памяти, необходимого для плана выполнения.</span><span class="sxs-lookup"><span data-stu-id="11a44-110">This is because the amount of memory that is required for an execution plan increases.</span></span>  
  
 <span data-ttu-id="11a44-111">Определить набор столбцов можно с помощью ключевых слов *<имя_набора_столбцов>* FOR ALL_SPARSE_COLUMNS в инструкциях [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) и [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="11a44-111">To define a column set, use the *<column_set_name>* FOR ALL_SPARSE_COLUMNS keywords in the[CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) or [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) statements.</span></span>  
  
## <a name="guidelines-for-using-column-sets"></a><span data-ttu-id="11a44-112">Рекомендации по использованию наборов столбцов</span><span class="sxs-lookup"><span data-stu-id="11a44-112">Guidelines for Using Column Sets</span></span>  
 <span data-ttu-id="11a44-113">При использовании наборов столбцов следует учитывать следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="11a44-113">When you use column sets, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="11a44-114">Разреженные столбцы и набор столбцов могут быть созданы в рамках одной и той же инструкции.</span><span class="sxs-lookup"><span data-stu-id="11a44-114">Sparse columns and a column set can be added as part of the same statement.</span></span>  
  
-   <span data-ttu-id="11a44-115">Набор столбцов нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="11a44-115">The column set cannot be changed.</span></span> <span data-ttu-id="11a44-116">Чтобы изменить набор столбцов, его нужно удалить и создать повторно.</span><span class="sxs-lookup"><span data-stu-id="11a44-116">To change a column set, you must delete and re-create the column set.</span></span>  
  
-   <span data-ttu-id="11a44-117">Набор столбцов не может быть добавлен в таблицу, если в ней уже содержатся разреженные столбцы.</span><span class="sxs-lookup"><span data-stu-id="11a44-117">A column set cannot be added to a table if that table already contains sparse columns.</span></span>  
  
-   <span data-ttu-id="11a44-118">Набор столбцов может быть добавлен в таблицу, если в ней нет разреженных столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-118">A column set can be added to a table that does not include any sparse columns.</span></span> <span data-ttu-id="11a44-119">Если впоследствии в таблицу будут добавлены разреженные столбцы, они появятся в наборе столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-119">If sparse columns are later added to the table, they will appear in the column set.</span></span>  
  
-   <span data-ttu-id="11a44-120">В таблице может содержаться только один набор столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-120">Only one column set is allowed per table.</span></span>  
  
-   <span data-ttu-id="11a44-121">Набор столбцов является дополнительной функцией, он не требуется для использования разреженных столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-121">A column set is optional and is not required to use sparse columns.</span></span>  
  
-   <span data-ttu-id="11a44-122">Для набора столбцов нельзя определить ограничения или значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="11a44-122">Constraints or default values cannot be defined on a column set.</span></span>  
  
-   <span data-ttu-id="11a44-123">Вычисляемые столбцы не могут содержать столбцы набора столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-123">Computed columns cannot contain column set columns.</span></span>  
  
-   <span data-ttu-id="11a44-124">Распределенные запросы не поддерживаются в таблицах, содержащих наборы столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-124">Distributed queries are not supported on tables that contain column sets.</span></span>  
  
-   <span data-ttu-id="11a44-125">Репликация не поддерживает наборы столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-125">Replication does not support column sets.</span></span>  
  
-   <span data-ttu-id="11a44-126">Система отслеживания измененных данных не поддерживает наборы столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-126">Change data capture does not support column sets.</span></span>  
  
-   <span data-ttu-id="11a44-127">Набор столбцов не может быть частью никакого вида индексов.</span><span class="sxs-lookup"><span data-stu-id="11a44-127">A column set cannot be part of any kind of index.</span></span> <span data-ttu-id="11a44-128">Это касается XML-индексов, полнотекстовых индексов и индексированных представлений.</span><span class="sxs-lookup"><span data-stu-id="11a44-128">This includes XML indexes, full-text indexes, and indexed views.</span></span> <span data-ttu-id="11a44-129">Набор столбцов не может быть добавлен как включенный столбец в любой индекс.</span><span class="sxs-lookup"><span data-stu-id="11a44-129">A column set cannot be added as an included column in any index.</span></span>  
  
-   <span data-ttu-id="11a44-130">Набор столбцов не может быть использован в критерии фильтра фильтруемого индекса или статистике фильтрации.</span><span class="sxs-lookup"><span data-stu-id="11a44-130">A column set cannot be used in the filter expression of a filtered index or filtered statistics.</span></span>  
  
-   <span data-ttu-id="11a44-131">Если представление содержит набор столбцов, в представлении он будет отображен как XML-столбец.</span><span class="sxs-lookup"><span data-stu-id="11a44-131">When a view includes a column set, the column set appears in the view as an XML column.</span></span>  
  
-   <span data-ttu-id="11a44-132">Набор столбцов не может быть включен в определение индексированного представления.</span><span class="sxs-lookup"><span data-stu-id="11a44-132">A column set cannot be included in an indexed view definition.</span></span>  
  
-   <span data-ttu-id="11a44-133">Секционированные представления, включающие таблицы, в которых содержатся наборы столбцов, могут быть обновлены, если секционированные представления упоминают разреженные столбцы по именам.</span><span class="sxs-lookup"><span data-stu-id="11a44-133">Partitioned views that include tables that contain column sets are updatable when the partitioned view specifies the sparse columns by name.</span></span> <span data-ttu-id="11a44-134">Секционированное представление не может быть обновлено, если оно ссылается на набор столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-134">A partitioned view is not updatable when it references the column set.</span></span>  
  
-   <span data-ttu-id="11a44-135">Не допускается использование уведомлений о запросах, ссылающихся на наборы столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-135">Query notifications that refer to column sets are not permitted.</span></span>  
  
-   <span data-ttu-id="11a44-136">Предел размера XML-данных — 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="11a44-136">XML data has a size limit of 2 GB.</span></span> <span data-ttu-id="11a44-137">Если сумма данных в строке во всех разреженных столбцах, содержащих значения, отличные от значений NULL, превышает этот предел, запрос или операция DML выдаст ошибку.</span><span class="sxs-lookup"><span data-stu-id="11a44-137">If the combined data of all the nonnull sparse columns in a row exceeds this limit, the query or DML operation will produce an error.</span></span>  
  
-   <span data-ttu-id="11a44-138">Сведения о данных, возвращаемых функцией COLUMNS_UPDATED, см. в разделе [Использование разреженных столбцов](use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="11a44-138">For information about the data that is returned by the COLUMNS_UPDATED function, see [Use Sparse Columns](use-sparse-columns.md).</span></span>  
  
## <a name="guidelines-for-selecting-data-from-a-column-set"></a><span data-ttu-id="11a44-139">Рекомендации по выбору данных из набора столбцов</span><span class="sxs-lookup"><span data-stu-id="11a44-139">Guidelines for Selecting Data from a Column Set</span></span>  
 <span data-ttu-id="11a44-140">Следует учитывать следующие рекомендации при выборе данных из набора столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-140">Consider the following guidelines for selecting data from a column set:</span></span>  
  
-   <span data-ttu-id="11a44-141">Фактически, набор столбцов — это тип обновляемого, вычисляемого XML-столбца, в котором набор базовых реляционных столбцов собирается в единое XML-представление.</span><span class="sxs-lookup"><span data-stu-id="11a44-141">Conceptually, a column set is a type of updatable, computed XML column that aggregates a set of underlying relational columns into a single XML representation.</span></span> <span data-ttu-id="11a44-142">Набор столбцов поддерживает только свойство ALL_SPARSE_COLUMNS.</span><span class="sxs-lookup"><span data-stu-id="11a44-142">The column set only supports the ALL_SPARSE_COLUMNS property.</span></span> <span data-ttu-id="11a44-143">Это свойство используется для сбора всех значений, отличных от значения NULL, из всех разреженных столбцов в определенной строке.</span><span class="sxs-lookup"><span data-stu-id="11a44-143">This property is used to aggregate all nonnull values from all sparse columns for a particular row.</span></span>  
  
-   <span data-ttu-id="11a44-144">В редакторе таблиц среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] наборы столбцов отображаются как изменяемые XML-поля.</span><span class="sxs-lookup"><span data-stu-id="11a44-144">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] table editor, column sets are displayed as an editable XML field.</span></span> <span data-ttu-id="11a44-145">Наборы столбцов определяются с помощью следующего формата:</span><span class="sxs-lookup"><span data-stu-id="11a44-145">Define column sets in the format:</span></span>  
  
    ```  
    <column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...  
    ```  
  
     <span data-ttu-id="11a44-146">Далее приводятся примеры значений набора столбцов:</span><span class="sxs-lookup"><span data-stu-id="11a44-146">Examples of column set values are as follows:</span></span>  
  
    -   `<sparseProp1>10</sparseProp1><sparseProp3>20</sparseProp3>`  
  
    -   `<DocTitle>Bicycle Parts List</DocTitle><Region>West</Region>`  
  
-   <span data-ttu-id="11a44-147">Разреженные столбцы, содержащие значения NULL, не включаются в XML-представление набора столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-147">Sparse columns that contain null values are omitted from the XML representation for the column set.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="11a44-148">Добавление набора столбцов изменяет поведение запросов SELECT \*.</span><span class="sxs-lookup"><span data-stu-id="11a44-148">Adding a column set changes the behavior of SELECT \* queries.</span></span> <span data-ttu-id="11a44-149">Запрос будет возвращать набор столбцов как XML-столбец, а не как отдельные разреженные столбцы.</span><span class="sxs-lookup"><span data-stu-id="11a44-149">The query will return the column set as an XML column and not return the individual sparse columns.</span></span> <span data-ttu-id="11a44-150">Разработчики схем и приложений должны учитывать это, чтобы не нарушить работу существующих приложений.</span><span class="sxs-lookup"><span data-stu-id="11a44-150">Schema designers and software developers must be careful not to break existing applications.</span></span>  
  
## <a name="inserting-or-modifying-data-in-a-column-set"></a><span data-ttu-id="11a44-151">Вставка или изменение данных в наборе столбцов</span><span class="sxs-lookup"><span data-stu-id="11a44-151">Inserting or Modifying Data in a Column Set</span></span>  
 <span data-ttu-id="11a44-152">Управлять данными в разреженных столбцах можно с помощью имен индивидуальных столбцов либо ссылаясь на имя набора столбцов и указывая значения набора столбцов, используя XML-формат набора столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-152">Data manipulation of a sparse column can be performed by using the name of the individual columns, or by referencing the name of the column set and specifying the values of the column set by using the XML format of the column set.</span></span> <span data-ttu-id="11a44-153">Разреженные столбцы могут быть расположены в XML-столбце в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="11a44-153">Sparse columns can appear in any order in the XML column.</span></span>  
  
 <span data-ttu-id="11a44-154">При вставке или обновлении значений разреженных столбцов с помощью набора XML-столбцов производится неявное преобразование значений, вставляемых в лежащие в основе разреженные столбцы, из типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="11a44-154">When sparse column values are inserted or updated by using the XML column set, the values that are inserted into the underlying sparse columns are implicitly converted from the `xml` data type.</span></span> <span data-ttu-id="11a44-155">Для числовых столбцов пустые значения в XML-столбцах преобразуются в пустые строки.</span><span class="sxs-lookup"><span data-stu-id="11a44-155">In the case of numeric columns, a blank value in the XML for the numeric column converts to an empty string.</span></span> <span data-ttu-id="11a44-156">Поэтому в числовые столбцы вставляются значения 0, как это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="11a44-156">This causes a zero to be inserted into the numeric column as shown in the following example.</span></span>  
  
```  
CREATE TABLE t (i int SPARSE, cs xml column_set FOR ALL_SPARSE_COLUMNS);  
GO  
INSERT t(cs) VALUES ('<i/>');  
GO  
SELECT i FROM t;  
GO  
```  
  
 <span data-ttu-id="11a44-157">В этом примере для столбца `i`не было указано значение, однако было вставлено значение `0` .</span><span class="sxs-lookup"><span data-stu-id="11a44-157">In this example, no value was specified for the column `i`, but the value `0` was inserted.</span></span>  
  
## <a name="using-the-sql_variant-data-type"></a><span data-ttu-id="11a44-158">Использование типа данных sql_variant</span><span class="sxs-lookup"><span data-stu-id="11a44-158">Using the sql_variant Data Type</span></span>  
 <span data-ttu-id="11a44-159">Тип данных `sql_variant` может хранить несколько разных типов данных, например `int`, `char` и `date`.</span><span class="sxs-lookup"><span data-stu-id="11a44-159">The `sql_variant` date type can store multiple different data types, such as `int`, `char`, and `date`.</span></span> <span data-ttu-id="11a44-160">Наборы столбцов выводят сведения о типе данных (например, масштаб, точность или сведения о локали), связанном со значением `sql_variant`, в виде атрибутов в формируемом XML-столбце.</span><span class="sxs-lookup"><span data-stu-id="11a44-160">Column sets output the data type information such as scale, precision, and locale information that is associated with a `sql_variant` value as attributes in the generated XML column.</span></span> <span data-ttu-id="11a44-161">Если нужно предоставить эти атрибуты в сформированной пользователем XML-инструкции в качестве входных данных для операции вставки или обновления в наборе столбцов, то некоторые из этих атрибутов будут обязательными, а для некоторых других атрибутов будут назначены значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="11a44-161">If you try to provide these attributes in a custom-generated XML statement as an input for an insert or update operation on a column set, some of these attributes are required and some of them are assigned a default value.</span></span> <span data-ttu-id="11a44-162">В следующей таблице перечисляются типы данных и значения по умолчанию, которые формирует сервер, если значения предоставлены не были.</span><span class="sxs-lookup"><span data-stu-id="11a44-162">The following table lists the data types and the default values that the server generates when the value is not provided.</span></span>  
  
|<span data-ttu-id="11a44-163">Тип данных</span><span class="sxs-lookup"><span data-stu-id="11a44-163">Data type</span></span>|<span data-ttu-id="11a44-164">localeID\*</span><span class="sxs-lookup"><span data-stu-id="11a44-164">localeID\*</span></span>|<span data-ttu-id="11a44-165">sqlCompareOptions</span><span class="sxs-lookup"><span data-stu-id="11a44-165">sqlCompareOptions</span></span>|<span data-ttu-id="11a44-166">sqlCollationVersion</span><span class="sxs-lookup"><span data-stu-id="11a44-166">sqlCollationVersion</span></span>|<span data-ttu-id="11a44-167">SqlSortId</span><span class="sxs-lookup"><span data-stu-id="11a44-167">SqlSortId</span></span>|<span data-ttu-id="11a44-168">Максимальная длина</span><span class="sxs-lookup"><span data-stu-id="11a44-168">Maximum length</span></span>|<span data-ttu-id="11a44-169">Точность</span><span class="sxs-lookup"><span data-stu-id="11a44-169">Precision</span></span>|<span data-ttu-id="11a44-170">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="11a44-170">Scale</span></span>|  
|---------------|----------------|-----------------------|-------------------------|---------------|--------------------|---------------|-----------|  
|<span data-ttu-id="11a44-171">`char`, `varchar`, `binary`</span><span class="sxs-lookup"><span data-stu-id="11a44-171">`char`, `varchar`, `binary`</span></span>|<span data-ttu-id="11a44-172">-1</span><span class="sxs-lookup"><span data-stu-id="11a44-172">-1</span></span>|<span data-ttu-id="11a44-173">'Default'</span><span class="sxs-lookup"><span data-stu-id="11a44-173">'Default'</span></span>|<span data-ttu-id="11a44-174">0</span><span class="sxs-lookup"><span data-stu-id="11a44-174">0</span></span>|<span data-ttu-id="11a44-175">0</span><span class="sxs-lookup"><span data-stu-id="11a44-175">0</span></span>|<span data-ttu-id="11a44-176">8000</span><span class="sxs-lookup"><span data-stu-id="11a44-176">8000</span></span>|<span data-ttu-id="11a44-177">Неприменимо\*\*</span><span class="sxs-lookup"><span data-stu-id="11a44-177">Not applicable\*\*</span></span>|<span data-ttu-id="11a44-178">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-178">Not applicable</span></span>|  
|`nvarchar`|<span data-ttu-id="11a44-179">-1</span><span class="sxs-lookup"><span data-stu-id="11a44-179">-1</span></span>|<span data-ttu-id="11a44-180">'Default'</span><span class="sxs-lookup"><span data-stu-id="11a44-180">'Default'</span></span>|<span data-ttu-id="11a44-181">0</span><span class="sxs-lookup"><span data-stu-id="11a44-181">0</span></span>|<span data-ttu-id="11a44-182">0</span><span class="sxs-lookup"><span data-stu-id="11a44-182">0</span></span>|<span data-ttu-id="11a44-183">4000</span><span class="sxs-lookup"><span data-stu-id="11a44-183">4000</span></span>|<span data-ttu-id="11a44-184">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-184">Not applicable</span></span>|<span data-ttu-id="11a44-185">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-185">Not applicable</span></span>|  
|<span data-ttu-id="11a44-186">`decimal`, `float`, `real`</span><span class="sxs-lookup"><span data-stu-id="11a44-186">`decimal`, `float`, `real`</span></span>|<span data-ttu-id="11a44-187">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-187">Not applicable</span></span>|<span data-ttu-id="11a44-188">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-188">Not applicable</span></span>|<span data-ttu-id="11a44-189">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-189">Not applicable</span></span>|<span data-ttu-id="11a44-190">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-190">Not applicable</span></span>|<span data-ttu-id="11a44-191">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-191">Not applicable</span></span>|<span data-ttu-id="11a44-192">18</span><span class="sxs-lookup"><span data-stu-id="11a44-192">18</span></span>|<span data-ttu-id="11a44-193">0</span><span class="sxs-lookup"><span data-stu-id="11a44-193">0</span></span>|  
|<span data-ttu-id="11a44-194">`integer`, `bigint`, `tinyint`, `smallint`</span><span class="sxs-lookup"><span data-stu-id="11a44-194">`integer`, `bigint`, `tinyint`, `smallint`</span></span>|<span data-ttu-id="11a44-195">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-195">Not applicable</span></span>|<span data-ttu-id="11a44-196">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-196">Not applicable</span></span>|<span data-ttu-id="11a44-197">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-197">Not applicable</span></span>|<span data-ttu-id="11a44-198">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-198">Not applicable</span></span>|<span data-ttu-id="11a44-199">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-199">Not applicable</span></span>|<span data-ttu-id="11a44-200">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-200">Not applicable</span></span>|<span data-ttu-id="11a44-201">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-201">Not applicable</span></span>|  
|`datetime2`|<span data-ttu-id="11a44-202">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-202">Not applicable</span></span>|<span data-ttu-id="11a44-203">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-203">Not applicable</span></span>|<span data-ttu-id="11a44-204">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-204">Not applicable</span></span>|<span data-ttu-id="11a44-205">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-205">Not applicable</span></span>|<span data-ttu-id="11a44-206">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-206">Not applicable</span></span>|<span data-ttu-id="11a44-207">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-207">Not applicable</span></span>|<span data-ttu-id="11a44-208">7</span><span class="sxs-lookup"><span data-stu-id="11a44-208">7</span></span>|  
|`datetime offset`|<span data-ttu-id="11a44-209">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-209">Not applicable</span></span>|<span data-ttu-id="11a44-210">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-210">Not applicable</span></span>|<span data-ttu-id="11a44-211">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-211">Not applicable</span></span>|<span data-ttu-id="11a44-212">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-212">Not applicable</span></span>|<span data-ttu-id="11a44-213">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-213">Not applicable</span></span>|<span data-ttu-id="11a44-214">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-214">Not applicable</span></span>|<span data-ttu-id="11a44-215">7</span><span class="sxs-lookup"><span data-stu-id="11a44-215">7</span></span>|  
|<span data-ttu-id="11a44-216">`datetime`, `date`, `smalldatetime`</span><span class="sxs-lookup"><span data-stu-id="11a44-216">`datetime`, `date`, `smalldatetime`</span></span>|<span data-ttu-id="11a44-217">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-217">Not applicable</span></span>|<span data-ttu-id="11a44-218">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-218">Not applicable</span></span>|<span data-ttu-id="11a44-219">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-219">Not applicable</span></span>|<span data-ttu-id="11a44-220">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-220">Not applicable</span></span>|<span data-ttu-id="11a44-221">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-221">Not applicable</span></span>|<span data-ttu-id="11a44-222">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-222">Not applicable</span></span>|<span data-ttu-id="11a44-223">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-223">Not applicable</span></span>|  
|<span data-ttu-id="11a44-224">`money`, `smallmoney`</span><span class="sxs-lookup"><span data-stu-id="11a44-224">`money`, `smallmoney`</span></span>|<span data-ttu-id="11a44-225">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-225">Not applicable</span></span>|<span data-ttu-id="11a44-226">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-226">Not applicable</span></span>|<span data-ttu-id="11a44-227">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-227">Not applicable</span></span>|<span data-ttu-id="11a44-228">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-228">Not applicable</span></span>|<span data-ttu-id="11a44-229">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-229">Not applicable</span></span>|<span data-ttu-id="11a44-230">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-230">Not applicable</span></span>|<span data-ttu-id="11a44-231">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-231">Not applicable</span></span>|  
|`time`|<span data-ttu-id="11a44-232">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-232">Not applicable</span></span>|<span data-ttu-id="11a44-233">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-233">Not applicable</span></span>|<span data-ttu-id="11a44-234">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-234">Not applicable</span></span>|<span data-ttu-id="11a44-235">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-235">Not applicable</span></span>|<span data-ttu-id="11a44-236">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-236">Not applicable</span></span>|<span data-ttu-id="11a44-237">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="11a44-237">Not applicable</span></span>|<span data-ttu-id="11a44-238">7</span><span class="sxs-lookup"><span data-stu-id="11a44-238">7</span></span>|  
  
 <span data-ttu-id="11a44-239">\*  Значение localeID, равное -1, означает локаль по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="11a44-239">\*  localeID -1 means the default locale.</span></span> <span data-ttu-id="11a44-240">Локаль английского языка — 1033.</span><span class="sxs-lookup"><span data-stu-id="11a44-240">The English locale is 1033.</span></span>  
  
 <span data-ttu-id="11a44-241">\*\* Неприменимо — во время операции выбора из набора столбцов нет никаких выходных значений для этих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="11a44-241">\*\*  Not applicable = No values are output for these attributes during a select operation on the column set.</span></span> <span data-ttu-id="11a44-242">Формируется ошибка, если в XML-представлении, предоставленном для набора столбцов в операции вставки или обновления, вызывающий указал значение для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="11a44-242">Generates an error when a value is specified for this attribute by the caller in the XML representation provided for a column set in an insert or update operation.</span></span>  
  
## <a name="security"></a><span data-ttu-id="11a44-243">Безопасность</span><span class="sxs-lookup"><span data-stu-id="11a44-243">Security</span></span>  
 <span data-ttu-id="11a44-244">Модель безопасности набора столбцов работает схожим образом с моделью безопасности между таблицами и столбцами.</span><span class="sxs-lookup"><span data-stu-id="11a44-244">The security model for a column set works similar to the security model that exists between table and columns.</span></span> <span data-ttu-id="11a44-245">Наборы столбцов могут быть визуализированы как минитаблица; операции выбора для данной минитаблицы имеют вид SELECT \*.</span><span class="sxs-lookup"><span data-stu-id="11a44-245">Column sets can be visualized as a minitable and a select operation is like a SELECT \* operation on this minitable.</span></span> <span data-ttu-id="11a44-246">Однако связь между набором столбцов и разреженными столбцами — это связь группирования, а не просто контейнер.</span><span class="sxs-lookup"><span data-stu-id="11a44-246">But, the relationship between column set to sparse columns is a grouping relationship instead of strictly a container.</span></span> <span data-ttu-id="11a44-247">Модель безопасности проверяет безопасность столбцов в наборе столбцов и выполняет операции DENY над базовыми разреженными столбцами.</span><span class="sxs-lookup"><span data-stu-id="11a44-247">The security model checks the security on the column set column, and honors the DENY operations on the underlying sparse columns.</span></span> <span data-ttu-id="11a44-248">Далее приводятся дополнительные характеристики модели безопасности.</span><span class="sxs-lookup"><span data-stu-id="11a44-248">Additional characteristics of the security model are as follows:</span></span>  
  
-   <span data-ttu-id="11a44-249">Права доступа могут быть предоставлены и отменены на столбец в наборе столбцов так же, как и на любой другой столбец в таблице.</span><span class="sxs-lookup"><span data-stu-id="11a44-249">Security permissions can be granted and revoked from the column set column, similar to any other column in the table.</span></span>  
  
-   <span data-ttu-id="11a44-250">Выполнение инструкции GRANT или REVOKE для разрешений SELECT, INSERT, UPDATE, DELETE и REFERENCES для столбца в наборе столбцов не распространяется на базовые столбцы-участники этого набора.</span><span class="sxs-lookup"><span data-stu-id="11a44-250">A GRANT or REVOKE of SELECT, INSERT, UPDATE, DELETE, and REFERENCES permission on a column set column does not propagate to the underlying member columns of that set.</span></span> <span data-ttu-id="11a44-251">Оно применяется только к столбцу в наборе столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-251">It applies only to the usage of the column set column.</span></span> <span data-ttu-id="11a44-252">Разрешение DENY для набора столбцов распространяется на базовые разреженные столбцы таблицы.</span><span class="sxs-lookup"><span data-stu-id="11a44-252">DENY permission on a column set does propagate to the underlying sparse columns of the table.</span></span>  
  
-   <span data-ttu-id="11a44-253">Чтобы выполнять инструкции SELECT, INSERT, UPDATE и DELETE над столбцами в наборе столбцов, пользователь должен иметь необходимые разрешения на столбец набора столбцов, а также соответствующее разрешение на все разреженные столбцы в таблице.</span><span class="sxs-lookup"><span data-stu-id="11a44-253">Executing SELECT, INSERT, UPDATE, and DELETE statements on the column set column require that the user has corresponding permissions on the column set column, and also the corresponding permission on all the sparse columns in the table.</span></span> <span data-ttu-id="11a44-254">Поскольку набор столбцов представляет все разреженные столбцы в таблице, пользователь должен обладать разрешением на все разреженные столбцы, включая и те, которые не будут изменены.</span><span class="sxs-lookup"><span data-stu-id="11a44-254">Because the column set represents all the sparse columns in the table, you must have permission on all the sparse columns, and this includes sparse columns that you might not be changing.</span></span>  
  
-   <span data-ttu-id="11a44-255">Выполнение инструкции REVOKE над разреженным столбцом или набором столбцов устанавливает для него параметры безопасности, заданные по умолчанию для его родительского объекта.</span><span class="sxs-lookup"><span data-stu-id="11a44-255">Executing a REVOKE statement on a sparse column or column set defaults the security to their parent object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="11a44-256">Примеры</span><span class="sxs-lookup"><span data-stu-id="11a44-256">Examples</span></span>  
 <span data-ttu-id="11a44-257">В следующих примерах в таблице документа содержится обычный набор столбцов `DocID` и `Title`.</span><span class="sxs-lookup"><span data-stu-id="11a44-257">In the following examples, a document table contains the common set of columns `DocID` and `Title`.</span></span> <span data-ttu-id="11a44-258">Производственной группе необходимы столбцы `ProductionSpecification` и `ProductionLocation` для всех рабочих документов.</span><span class="sxs-lookup"><span data-stu-id="11a44-258">The Production group wants a `ProductionSpecification` and `ProductionLocation` column for all production documents.</span></span> <span data-ttu-id="11a44-259">Группе сбыта необходим столбец `MarketingSurveyGroup` для документов сбыта.</span><span class="sxs-lookup"><span data-stu-id="11a44-259">The Marketing group wants a `MarketingSurveyGroup` column for marketing documents.</span></span>  
  
### <a name="a-creating-a-table-that-has-a-column-set"></a><span data-ttu-id="11a44-260">A.</span><span class="sxs-lookup"><span data-stu-id="11a44-260">A.</span></span> <span data-ttu-id="11a44-261">Создание таблицы с набором столбцов</span><span class="sxs-lookup"><span data-stu-id="11a44-261">Creating a table that has a column set</span></span>  
 <span data-ttu-id="11a44-262">В следующем примере создается таблица, в которой используются разреженные столбцы и содержится набор столбцов `SpecialPurposeColumns`.</span><span class="sxs-lookup"><span data-stu-id="11a44-262">The following example creates the table that uses sparse columns and includes the column set `SpecialPurposeColumns`.</span></span> <span data-ttu-id="11a44-263">В этом примере в таблицу вставляются две строки, а затем из таблицы выбираются данные.</span><span class="sxs-lookup"><span data-stu-id="11a44-263">The example inserts two rows into the table, and then selects data from the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11a44-264">Эта таблица насчитывает лишь пять столбцов, что упрощает ее отображение и чтение.</span><span class="sxs-lookup"><span data-stu-id="11a44-264">This table has only five columns to make it easier to display and read.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
CREATE TABLE DocumentStoreWithColumnSet  
    (DocID int PRIMARY KEY,  
     Title varchar(200) NOT NULL,  
     ProductionSpecification varchar(20) SPARSE NULL,  
     ProductionLocation smallint SPARSE NULL,  
     MarketingSurveyGroup varchar(20) SPARSE NULL,  
     MarketingProgramID int SPARSE NULL,  
     SpecialPurposeColumns XML COLUMN_SET FOR ALL_SPARSE_COLUMNS);  
GO  
```  
  
### <a name="b-inserting-data-to-a-table-by-using-the-names-of-the-sparse-columns"></a><span data-ttu-id="11a44-265">Б.</span><span class="sxs-lookup"><span data-stu-id="11a44-265">B.</span></span> <span data-ttu-id="11a44-266">Вставка данных в таблицу с использованием имен разреженных столбцов</span><span class="sxs-lookup"><span data-stu-id="11a44-266">Inserting data to a table by using the names of the sparse columns</span></span>  
 <span data-ttu-id="11a44-267">В следующих примерах в таблицу, созданную в примере А, вставляются две строки. В примерах используются имена разреженных столбцов; набор столбцов не упоминается.</span><span class="sxs-lookup"><span data-stu-id="11a44-267">The following examples insert two rows into the table that is created in example A. The examples use the names of the sparse columns and do not reference the column set.</span></span>  
  
```  
INSERT DocumentStoreWithColumnSet (DocID, Title, ProductionSpecification, ProductionLocation)  
VALUES (1, 'Tire Spec 1', 'AXZZ217', 27);  
GO  
  
INSERT DocumentStoreWithColumnSet (DocID, Title, MarketingSurveyGroup)  
VALUES (2, 'Survey 2142', 'Men 25 - 35');  
GO  
```  
  
### <a name="c-inserting-data-to-a-table-by-using-the-name-of-the-column-set"></a><span data-ttu-id="11a44-268">В.</span><span class="sxs-lookup"><span data-stu-id="11a44-268">C.</span></span> <span data-ttu-id="11a44-269">Вставка данных в таблицу с использованием имени набора столбцов</span><span class="sxs-lookup"><span data-stu-id="11a44-269">Inserting data to a table by using the name of the column set</span></span>  
 <span data-ttu-id="11a44-270">В следующем примере в таблицу, созданную в примере А, вставляется третья строка. В этот раз имена разреженных столбцов не используются.</span><span class="sxs-lookup"><span data-stu-id="11a44-270">The following example inserts a third row into the table that is created in example A. This time the names of the sparse columns are not used.</span></span> <span data-ttu-id="11a44-271">Вместо этого используется имя набора столбцов, а операция вставки предоставляет значения для двух из четырех разреженных столбцов в формате XML.</span><span class="sxs-lookup"><span data-stu-id="11a44-271">Instead, the name of the column set is used, and the insert provides the values for two of the four sparse columns in XML format.</span></span>  
  
```  
INSERT DocumentStoreWithColumnSet (DocID, Title, SpecialPurposeColumns)  
VALUES (3, 'Tire Spec 2', '<ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>');  
GO  
```  
  
### <a name="d-observing-the-results-of-a-column-set-when-select--is-used"></a><span data-ttu-id="11a44-272">Г.</span><span class="sxs-lookup"><span data-stu-id="11a44-272">D.</span></span> <span data-ttu-id="11a44-273">Рассмотрение результатов для набора столбцов при выполнении инструкции SELECT \*</span><span class="sxs-lookup"><span data-stu-id="11a44-273">Observing the results of a column set when SELECT \* is used</span></span>  
 <span data-ttu-id="11a44-274">В следующем примере из таблицы, содержащей набор столбцов, выбираются все столбцы.</span><span class="sxs-lookup"><span data-stu-id="11a44-274">The following example selects all the columns from the table that contains a column set.</span></span> <span data-ttu-id="11a44-275">Возвращается XML-столбец, содержащий сочетание значений разреженных столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-275">It returns an XML column with the combined values of the sparse columns.</span></span> <span data-ttu-id="11a44-276">Разреженные столбцы не возвращаются индивидуально.</span><span class="sxs-lookup"><span data-stu-id="11a44-276">It does not return the sparse columns individually.</span></span>  
  
```  
SELECT DocID, Title, SpecialPurposeColumns FROM DocumentStoreWithColumnSet ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        SpecialPurposeColumns`  
  
 `1      Tire Spec 1  <ProductionSpecification>AXZZ217</ProductionSpecification><ProductionLocation>27</ProductionLocation>`  
  
 `2      Survey 2142  <MarketingSurveyGroup>Men 25 - 35</MarketingSurveyGroup>`  
  
 `3      Tire Spec 2  <ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>`  
  
### <a name="e-observing-the-results-of-selecting-the-column-set-by-name"></a><span data-ttu-id="11a44-277">Д.</span><span class="sxs-lookup"><span data-stu-id="11a44-277">E.</span></span> <span data-ttu-id="11a44-278">Рассмотрение результатов выбора набора столбцов с использованием его имени</span><span class="sxs-lookup"><span data-stu-id="11a44-278">Observing the results of selecting the column set by name</span></span>  
 <span data-ttu-id="11a44-279">Поскольку производственному отделу не нужны маркетинговые данные, в этом примере для ограничения выходных данных добавляется предложение `WHERE` .</span><span class="sxs-lookup"><span data-stu-id="11a44-279">Because the Production department is not interested in the marketing data, this example adds a `WHERE` clause to restrict the output.</span></span> <span data-ttu-id="11a44-280">В этом примере используется имя набора столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-280">The example uses the name of the column set.</span></span>  
  
```  
SELECT DocID, Title, SpecialPurposeColumns  
FROM DocumentStoreWithColumnSet  
WHERE ProductionSpecification IS NOT NULL ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        SpecialPurposeColumns`  
  
 `1     Tire Spec 1  <ProductionSpecification>AXZZ217</ProductionSpecification><ProductionLocation>27</ProductionLocation>`  
  
 `3     Tire Spec 2  <ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>`  
  
### <a name="f-observing-the-results-of-selecting-sparse-columns-by-name"></a><span data-ttu-id="11a44-281">Е.</span><span class="sxs-lookup"><span data-stu-id="11a44-281">F.</span></span> <span data-ttu-id="11a44-282">Рассмотрение результатов выбора разреженных столбцов с использованием их имен</span><span class="sxs-lookup"><span data-stu-id="11a44-282">Observing the results of selecting sparse columns by name</span></span>  
 <span data-ttu-id="11a44-283">Несмотря на то, что таблица содержит набор столбцов, можно выполнять запросы из таблицы с использованием имен отдельных столбцов. Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="11a44-283">When a table contains a column set, you can still query the table by using the individual column names as shown in the following example.</span></span>  
  
```  
SELECT DocID, Title, ProductionSpecification, ProductionLocation   
FROM DocumentStoreWithColumnSet  
WHERE ProductionSpecification IS NOT NULL ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        ProductionSpecification ProductionLocation`  
  
 `1     Tire Spec 1  AXZZ217                 27`  
  
 `3     Tire Spec 2  AXW9R411                38`  
  
### <a name="g-updating-a-table-by-using-a-column-set"></a><span data-ttu-id="11a44-284">Ж.</span><span class="sxs-lookup"><span data-stu-id="11a44-284">G.</span></span> <span data-ttu-id="11a44-285">Обновление таблицы с помощью набора столбцов</span><span class="sxs-lookup"><span data-stu-id="11a44-285">Updating a table by using a column set</span></span>  
 <span data-ttu-id="11a44-286">В следующем примере третья запись обновляется новыми значениями для обоих разреженных столбцов, использующихся в этой строке.</span><span class="sxs-lookup"><span data-stu-id="11a44-286">The following example updates the third record with new values for both sparse columns that are used by that row.</span></span>  
  
```  
UPDATE DocumentStoreWithColumnSet  
SET SpecialPurposeColumns = '<ProductionSpecification>ZZ285W</ProductionSpecification><ProductionLocation>38</ProductionLocation>'  
WHERE DocID = 3 ;  
GO  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="11a44-287">Инструкция UPDATE, использующая набор столбцов, обновляет все разреженные столбцы в таблице.</span><span class="sxs-lookup"><span data-stu-id="11a44-287">An UPDATE statement that uses a column set updates all the sparse columns in the table.</span></span> <span data-ttu-id="11a44-288">Для всех разреженных столбцов, которые не были упомянуты, устанавливается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="11a44-288">Sparse columns that are not referenced are updated to NULL.</span></span>  
  
 <span data-ttu-id="11a44-289">В следующем примере обновляется третья запись, однако значение указывается только для одного из двух заполненных столбцов.</span><span class="sxs-lookup"><span data-stu-id="11a44-289">The following example updates the third record, but only specifies the value of one of the two populated columns.</span></span> <span data-ttu-id="11a44-290">Второй столбец, `ProductionLocation` , не включен в инструкцию `UPDATE` , и для него устанавливается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="11a44-290">The second column `ProductionLocation` is not included in the `UPDATE` statement and is updated to NULL.</span></span>  
  
```  
UPDATE DocumentStoreWithColumnSet  
SET SpecialPurposeColumns = '<ProductionSpecification>ZZ285W</ProductionSpecification>'  
WHERE DocID = 3 ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="11a44-291">См. также:</span><span class="sxs-lookup"><span data-stu-id="11a44-291">See Also</span></span>  
 [<span data-ttu-id="11a44-292">Использование разреженных столбцов</span><span class="sxs-lookup"><span data-stu-id="11a44-292">Use Sparse Columns</span></span>](use-sparse-columns.md)  
  
  
