---
title: Обновление данных с помощью диаграмм обновления XML (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREF type attribute [SQLXML]
- before attribute
- <sync> block
- <after> block
- id attribute
- <before> block
- updg:after attribute
- mapping-schema attribute
- IDREFS type attribute [SQLXML]
- updg:id attribute
- multiple record updates
- after attribute
- updategrams [SQLXML], updating data
- updg:before attribute
- record updates [SQLXML]
ms.assetid: 90ef8a33-5ae3-4984-8259-608d2f1d727f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6b019478868b61f293eda824d9b302099728dec4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665956"
---
# <a name="updating-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="4d90b-102">Обновление данных при помощи диаграмм обновления XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4d90b-102">Updating Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="4d90b-103">При обновлении существующих данных необходимо указать оба **\<before>** **\<after>** блока и.</span><span class="sxs-lookup"><span data-stu-id="4d90b-103">When you update existing data, you must specify both the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="4d90b-104">Элементы, указанные в **\<before>** **\<after>** блоках и, описывают требуемое изменение.</span><span class="sxs-lookup"><span data-stu-id="4d90b-104">The elements specified in the **\<before>** and **\<after>** blocks describe the desired change.</span></span> <span data-ttu-id="4d90b-105">Диаграмма обновления использует элементы, указанные в **\<before>** блоке, для обнаружения существующих записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4d90b-105">The updategram uses the element(s) that are specified in the **\<before>** block to identify the existing record(s) in the database.</span></span> <span data-ttu-id="4d90b-106">Соответствующие элементы в **\<after>** блоке указывают, как должны выглядеть записи после выполнения операции обновления.</span><span class="sxs-lookup"><span data-stu-id="4d90b-106">The corresponding element(s) in the **\<after>** block indicate how the records should look after executing the update operation.</span></span> <span data-ttu-id="4d90b-107">На основе этих сведений диаграмма обновления создает инструкцию SQL, которая соответствует **\<after>** блоку.</span><span class="sxs-lookup"><span data-stu-id="4d90b-107">From this information, the updategram creates an SQL statement that matches the **\<after>** block.</span></span> <span data-ttu-id="4d90b-108">Затем диаграмма обновления использует эту инструкцию для обновления базы данных.</span><span class="sxs-lookup"><span data-stu-id="4d90b-108">The updategram then uses this statement to update the database.</span></span>  
  
 <span data-ttu-id="4d90b-109">Ниже представлен формат диаграммы обновления для операции обновления.</span><span class="sxs-lookup"><span data-stu-id="4d90b-109">This is the updategram format for an update operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync [mapping-schema="SampleSchema.xml"]  >  
   <updg:before>  
      <ElementName [updg:id="value"] .../>  
      [<ElementName [updg:id="value"] .../> ... ]  
   </updg:before>  
   <updg:after>  
      <ElementName [updg:id="value"] ... />  
      [<ElementName [updg:id="value"] .../> ...]  
   </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 `<updg:before>`  
 <span data-ttu-id="4d90b-110">Элементы в **\<before>** блоке обозначают существующие записи в таблицах базы данных.</span><span class="sxs-lookup"><span data-stu-id="4d90b-110">The elements in the **\<before>** block identify existing records in the database tables.</span></span>  
  
 `<updg:after>`  
 <span data-ttu-id="4d90b-111">Элементы в **\<after>** блоке описывают, как записи, указанные в **\<before>** блоке, должны выглядеть после применения обновлений.</span><span class="sxs-lookup"><span data-stu-id="4d90b-111">The elements in the **\<after>** block describe how the records specified in the **\<before>** block should look after the updates are applied.</span></span>  
  
 <span data-ttu-id="4d90b-112">Атрибут `mapping-schema` указывает схему сопоставления, которая будет использоваться диаграммной обновления.</span><span class="sxs-lookup"><span data-stu-id="4d90b-112">The `mapping-schema` attribute identifies the mapping schema to be used by the updategram.</span></span> <span data-ttu-id="4d90b-113">Если диаграмма обновления указывает схему сопоставления, имена элементов и атрибутов, указанных в **\<before>** блоках и, **\<after>** должны совпадать с именами в схеме.</span><span class="sxs-lookup"><span data-stu-id="4d90b-113">If the updategram specifies a mapping schema, the element and attribute names specified in the **\<before>** and **\<after>** blocks must match the names in the schema.</span></span> <span data-ttu-id="4d90b-114">Схема сопоставления сопоставляет эти имена элементов или атрибутов с именами таблиц и столбцов в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4d90b-114">The mapping schema maps these element or attribute names to the database table and column names.</span></span>  
  
 <span data-ttu-id="4d90b-115">Если в диаграмме обновления не указана схема, используется сопоставление по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d90b-115">If an updategram does not specify a schema, the updategam uses default mapping.</span></span> <span data-ttu-id="4d90b-116">В сопоставлении по умолчанию, **\<ElementName>** указанное в диаграмма обновления, сопоставляется с таблицей базы данных, а дочерние элементы или атрибуты сопоставляются со столбцами базы данных.</span><span class="sxs-lookup"><span data-stu-id="4d90b-116">In default mapping, the **\<ElementName>** specified in the updategram maps to the database table and the child elements or attributes map to the database columns.</span></span>  
  
 <span data-ttu-id="4d90b-117">Элемент в **\<before>** блоке должен совпадать только с одной строкой таблицы в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4d90b-117">An element in the **\<before>** block must match with only one table row in the database.</span></span> <span data-ttu-id="4d90b-118">Если элемент либо соответствует нескольким строкам таблицы, либо не совпадает ни с одной строкой таблицы, диаграмма обновления возвращает ошибку и отменяет весь **\<sync>** блок.</span><span class="sxs-lookup"><span data-stu-id="4d90b-118">If the element either matches multiple table rows or does not match any table row, the updategram returns an error and cancels the entire **\<sync>** block.</span></span>  
  
 <span data-ttu-id="4d90b-119">Диаграмма обновления может включать несколько **\<sync>** блоков.</span><span class="sxs-lookup"><span data-stu-id="4d90b-119">An updategram can include multiple **\<sync>** blocks.</span></span> <span data-ttu-id="4d90b-120">Каждый **\<sync>** блок рассматривается как транзакция.</span><span class="sxs-lookup"><span data-stu-id="4d90b-120">Each **\<sync>** block is treated as a transaction.</span></span> <span data-ttu-id="4d90b-121">Каждый **\<sync>** блок может иметь несколько **\<before>** **\<after>** блоков и.</span><span class="sxs-lookup"><span data-stu-id="4d90b-121">Each **\<sync>** block can have multiple **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="4d90b-122">Например, при обновлении двух существующих записей можно указать две **\<before>** **\<after>** пары и, по одной для каждой обновляемой записи.</span><span class="sxs-lookup"><span data-stu-id="4d90b-122">For example, if you are updating two of the existing records, you could specify two **\<before>** and **\<after>** pairs, one for each record being updated.</span></span>  
  
## <a name="using-the-updgid-attribute"></a><span data-ttu-id="4d90b-123">Использование атрибута updg:id</span><span class="sxs-lookup"><span data-stu-id="4d90b-123">Using the updg:id Attribute</span></span>  
 <span data-ttu-id="4d90b-124">Если в блоках и задано несколько элементов **\<before>** **\<after>** , используйте `updg:id` атрибут для пометки строк в **\<before>** **\<after>** блоках и.</span><span class="sxs-lookup"><span data-stu-id="4d90b-124">When multiple elements are specified in the **\<before>** and **\<after>** blocks, use the `updg:id` attribute to mark rows in the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="4d90b-125">Эта информация используется логикой обработки для определения записи в **\<before>** блочных парах с записью в **\<after>** блоке.</span><span class="sxs-lookup"><span data-stu-id="4d90b-125">The processing logic uses this information to determine what record in the **\<before>** block pairs with what record in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="4d90b-126">Атрибут `updg:id` является необязательным (хотя его рекомендуется указывать) при соблюдении одного из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="4d90b-126">The `updg:id` attribute is not necessary (although recommended) if either of the following exists:</span></span>  
  
-   <span data-ttu-id="4d90b-127">Для элементов в указанной схеме сопоставления определен атрибут `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="4d90b-127">The elements in the specified mapping schema have the `sql:key-fields` attribute defined on them.</span></span>  
  
-   <span data-ttu-id="4d90b-128">Для ключевых полей в диаграмме обновления указано одно или несколько значений.</span><span class="sxs-lookup"><span data-stu-id="4d90b-128">There is one or more specific value supplied for the key field(s) in the updategram.</span></span>  
  
 <span data-ttu-id="4d90b-129">Если это так, диаграмма обновления использует ключевые столбцы, заданные в, `sql:key-fields` для связывания элементов в **\<before>** **\<after>** блоках и.</span><span class="sxs-lookup"><span data-stu-id="4d90b-129">If either is the case, the updategram uses the key columns that are specified in the `sql:key-fields` to pair the elements in the **\<before>** and **\<after>** blocks.</span></span>  
  
 <span data-ttu-id="4d90b-130">Если в схеме сопоставления не указаны ключевые столбцы (через `sql:key-fields`) или диаграмма обновления обновляет значение ключевого столбца, то необходимо указать `updg:id`.</span><span class="sxs-lookup"><span data-stu-id="4d90b-130">If the mapping schema does not identify key columns (by using `sql:key-fields`) or if the updategram is updating a key column value, you must specify `updg:id`.</span></span>  
  
 <span data-ttu-id="4d90b-131">Записи, идентифицированные в **\<before>** **\<after>** блоках и, не обязательно должны находиться в том же порядке.</span><span class="sxs-lookup"><span data-stu-id="4d90b-131">The records that are identified in the **\<before>** and **\<after>** blocks do not have to be in the same order.</span></span> <span data-ttu-id="4d90b-132">`updg:id`Атрибут принудительно вызывает связь между элементами, заданными в **\<before>** **\<after>** блоках и.</span><span class="sxs-lookup"><span data-stu-id="4d90b-132">The `updg:id` attribute forces the association between the elements that are specified in the **\<before>** and **\<after>** blocks.</span></span>  
  
 <span data-ttu-id="4d90b-133">Если указать один элемент в **\<before>** блоке и только один соответствующий элемент в **\<after>** блоке, использование не `updg:id` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="4d90b-133">If you specify one element in the **\<before>** block and only one corresponding element in the **\<after>** block, using `updg:id` is not necessary.</span></span> <span data-ttu-id="4d90b-134">Во избежание недоразумений рекомендуется указывать `updg:id` в любом случае.</span><span class="sxs-lookup"><span data-stu-id="4d90b-134">However, it is recommended that you specify `updg:id` anyway to avoid ambiguity.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4d90b-135">Примеры</span><span class="sxs-lookup"><span data-stu-id="4d90b-135">Examples</span></span>  
 <span data-ttu-id="4d90b-136">При использовании примеров диаграмм обновления необходимо учитывать следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="4d90b-136">Before you use the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="4d90b-137">В большинстве примеров используется сопоставление по умолчанию (то есть в диаграмме обновления схема сопоставления не задана).</span><span class="sxs-lookup"><span data-stu-id="4d90b-137">Most of the examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="4d90b-138">Дополнительные примеры диаграмм обновления, в которых используются схемы сопоставления, см. [в разделе Указание схемы сопоставления с заметками в диаграмма обновления &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4d90b-138">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="4d90b-139">В большинстве примеров задействован образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4d90b-139">Most of the examples use the AdventureWorks sample database.</span></span> <span data-ttu-id="4d90b-140">Все обновления применяются к таблицам в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="4d90b-140">All the updates are applied to the tables in this database.</span></span> <span data-ttu-id="4d90b-141">Базу данных AdventureWorks можно восстановить.</span><span class="sxs-lookup"><span data-stu-id="4d90b-141">You can restore the AdventureWorks database.</span></span>  
  
### <a name="a-updating-a-record"></a><span data-ttu-id="4d90b-142">A.</span><span class="sxs-lookup"><span data-stu-id="4d90b-142">A.</span></span> <span data-ttu-id="4d90b-143">Обновление записи</span><span class="sxs-lookup"><span data-stu-id="4d90b-143">Updating a record</span></span>  
 <span data-ttu-id="4d90b-144">Следующая диаграмма обновления используется для изменения фамилии сотрудника в таблице Person.Contact базы данных AdventureWorks на Fuller.</span><span class="sxs-lookup"><span data-stu-id="4d90b-144">The following updategram updates the employee last name to Fuller in the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="4d90b-145">В диаграмме обновления не задана схема сопоставления, поэтому применяется сопоставление по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d90b-145">The updategram does not specify any mapping schema; therefore, the updategram uses default mapping.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" />  
</updg:before>  
<updg:after>  
   <Person.Contact LastName="Abel-Achong" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="4d90b-146">Запись, описанная в **\<before>** блоке, представляет текущую запись в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4d90b-146">The record described in the **\<before>** block represents the current record in the database.</span></span> <span data-ttu-id="4d90b-147">Диаграмма обновления использует все значения столбцов, указанные в **\<before>** блоке, для поиска записи.</span><span class="sxs-lookup"><span data-stu-id="4d90b-147">The updategram uses all of the column values specified in the **\<before>** block to search for the record.</span></span> <span data-ttu-id="4d90b-148">В этом диаграмма обновления **\<before>** блок предоставляет только столбец ContactID, поэтому диаграмма обновления использует только значение для поиска записи.</span><span class="sxs-lookup"><span data-stu-id="4d90b-148">In this updategram, the **\<before>** block provides only the ContactID column; therefore, the updategram uses only the value to search for the record.</span></span> <span data-ttu-id="4d90b-149">Если добавить в этот блок значение LastName, то диаграмма обновления будет производить поиск по обоим значениям — ContactID и LastName.</span><span class="sxs-lookup"><span data-stu-id="4d90b-149">If you were to add the LastName value to this block, the updategram would use both the ContactID and LastName values to search.</span></span>  
  
 <span data-ttu-id="4d90b-150">В этом диаграмма обновления **\<after>** блок содержит только значение столбца LastName, так как это единственное изменяемое значение.</span><span class="sxs-lookup"><span data-stu-id="4d90b-150">In this updategram, the **\<after>** block provides only the LastName column value because this is the only value that is being changed.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="4d90b-151">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="4d90b-151">To test the updategram</span></span>  
  
1.  <span data-ttu-id="4d90b-152">Скопируйте приведенный выше шаблон диаграммы обновления и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="4d90b-152">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="4d90b-153">Сохраните файл под именем UpdateLastName.xml.</span><span class="sxs-lookup"><span data-stu-id="4d90b-153">Save the file as UpdateLastName.xml.</span></span>  
  
2.  <span data-ttu-id="4d90b-154">Создайте тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs) и воспользуйтесь им для выполнения диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="4d90b-154">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="4d90b-155">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4d90b-155">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="b-updating-multiple-records-by-using-the-updgid-attribute"></a><span data-ttu-id="4d90b-156">Б.</span><span class="sxs-lookup"><span data-stu-id="4d90b-156">B.</span></span> <span data-ttu-id="4d90b-157">Обновление нескольких записей с помощью атрибута updg:id</span><span class="sxs-lookup"><span data-stu-id="4d90b-157">Updating multiple records by using the updg:id attribute</span></span>  
 <span data-ttu-id="4d90b-158">В данном примере диаграмма обновления выполняет два обновления в таблице HumanResources.Shift в базе данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4d90b-158">In this example, the updategram performs two updates on the HumanResources.Shift table in the AdventureWorks database:</span></span>  
  
-   <span data-ttu-id="4d90b-159">Имя исходной дневной смены, начинающейся в 7:00, меняется с «Day» на «Early Morning».</span><span class="sxs-lookup"><span data-stu-id="4d90b-159">It changes the name of the original day shift that starts at 7:00AM from "Day" to "Early Morning".</span></span>  
  
-   <span data-ttu-id="4d90b-160">Также добавляется имя новой смены, «Late Morning», которая начинается в 10:00.</span><span class="sxs-lookup"><span data-stu-id="4d90b-160">It inserts a new shift named "Late Morning" that starts at 10:00AM.</span></span>  
  
 <span data-ttu-id="4d90b-161">В диаграмма обновления `updg:id` атрибут создает связи между элементами в **\<before>** **\<after>** блоках и.</span><span class="sxs-lookup"><span data-stu-id="4d90b-161">In the updategram, the `updg:id` attribute creates associations between elements in the **\<before>** and **\<after>** blocks.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift updg:id="x" Name="Day" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift updg:id="y" Name="Late Morning"   
                            StartTime="1900-01-01 10:00:00.000"  
                            EndTime="1900-01-01 18:00:00.000"  
                            ModifiedDate="2004-06-01 00:00:00.000"/>  
      <HumanResources.Shift updg:id="x" Name="Early Morning" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="4d90b-162">Обратите внимание, что `updg:id` атрибут связывает первый экземпляр \<HumanResources.Shift> элемента в **\<before>** блоке со вторым экземпляром \<HumanResources.Shift> элемента в **\<after>** блоке.</span><span class="sxs-lookup"><span data-stu-id="4d90b-162">Notice how the `updg:id` attribute pairs the first instance of the \<HumanResources.Shift> element in the **\<before>** block with the second instance of the \<HumanResources.Shift> element in the **\<after>** block.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="4d90b-163">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="4d90b-163">To test the updategram</span></span>  
  
1.  <span data-ttu-id="4d90b-164">Скопируйте приведенный выше шаблон диаграммы обновления и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="4d90b-164">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="4d90b-165">Сохраните файл под именем UpdateMultipleRecords.xml.</span><span class="sxs-lookup"><span data-stu-id="4d90b-165">Save the file as UpdateMultipleRecords.xml.</span></span>  
  
2.  <span data-ttu-id="4d90b-166">Создайте тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs) и воспользуйтесь им для выполнения диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="4d90b-166">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="4d90b-167">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4d90b-167">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="c-specifying-multiple-before-and-after-blocks"></a><span data-ttu-id="4d90b-168">В.</span><span class="sxs-lookup"><span data-stu-id="4d90b-168">C.</span></span> <span data-ttu-id="4d90b-169">Указание нескольких \<before> \<after> блоков и</span><span class="sxs-lookup"><span data-stu-id="4d90b-169">Specifying multiple \<before> and \<after> blocks</span></span>  
 <span data-ttu-id="4d90b-170">Чтобы избежать неоднозначности, можно написать диаграмма обновления в примере б с помощью нескольких **\<before>** **\<after>** пар блоков и.</span><span class="sxs-lookup"><span data-stu-id="4d90b-170">To avoid ambiguity, you can write the updategram in Example B by using multiple **\<before>** and **\<after>** block pairs.</span></span> <span data-ttu-id="4d90b-171">Указание **\<before>** **\<after>** пар и является одним из способов указания нескольких обновлений с минимальными путаницами.</span><span class="sxs-lookup"><span data-stu-id="4d90b-171">Specifying **\<before>** and **\<after>** pairs is one way of specifying multiple updates with a minimum of confusion.</span></span> <span data-ttu-id="4d90b-172">Кроме того, если каждый **\<before>** блок и **\<after>** указывает не более одного элемента, использовать атрибут не нужно `updg:id` .</span><span class="sxs-lookup"><span data-stu-id="4d90b-172">Also, if each of the **\<before>** and **\<after>** blocks specify at most one element, you do not have to use the `updg:id` attribute.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d90b-173">Чтобы сформировать пару, **\<after>** тег должен следовать непосредственно за соответствующим **\<before>** тегом.</span><span class="sxs-lookup"><span data-stu-id="4d90b-173">To form a pair, the **\<after>** tag must immediately follow its corresponding **\<before>** tag.</span></span>  
  
 <span data-ttu-id="4d90b-174">В следующем диаграмма обновления первая **\<before>** и **\<after>** пара обновляет имя смены для дня сдвига.</span><span class="sxs-lookup"><span data-stu-id="4d90b-174">In the following updategram, the first **\<before>** and **\<after>** pair updates the shift name for the day shift.</span></span> <span data-ttu-id="4d90b-175">Вторая пара вставляет запись для новой смены.</span><span class="sxs-lookup"><span data-stu-id="4d90b-175">The second pair inserts a new shift record.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="1" Name="Day" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="Early Morning" />  
    </updg:after>  
    <updg:before>  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="Late Morning"   
                            StartTime="1900-01-01 10:00:00.000"  
                            EndTime="1900-01-01 18:00:00.000"  
                            ModifiedDate="2004-06-01 00:00:00.000"/>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="4d90b-176">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="4d90b-176">To test the updategram</span></span>  
  
1.  <span data-ttu-id="4d90b-177">Скопируйте приведенный выше шаблон диаграммы обновления и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="4d90b-177">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="4d90b-178">Сохраните файл под именем UpdateMultipleBeforeAfter.xml.</span><span class="sxs-lookup"><span data-stu-id="4d90b-178">Save the file as UpdateMultipleBeforeAfter.xml.</span></span>  
  
2.  <span data-ttu-id="4d90b-179">Создайте тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs) и воспользуйтесь им для выполнения диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="4d90b-179">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="4d90b-180">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4d90b-180">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="d-specifying-multiple-sync-blocks"></a><span data-ttu-id="4d90b-181">Г.</span><span class="sxs-lookup"><span data-stu-id="4d90b-181">D.</span></span> <span data-ttu-id="4d90b-182">Указание нескольких \<sync> блоков</span><span class="sxs-lookup"><span data-stu-id="4d90b-182">Specifying multiple \<sync> blocks</span></span>  
 <span data-ttu-id="4d90b-183">В диаграмма обновления можно указать несколько **\<sync>** блоков.</span><span class="sxs-lookup"><span data-stu-id="4d90b-183">You can specify multiple **\<sync>** blocks in an updategram.</span></span> <span data-ttu-id="4d90b-184">Каждый **\<sync>** указанный блок является независимой транзакцией.</span><span class="sxs-lookup"><span data-stu-id="4d90b-184">Each **\<sync>** block that is specified is an independent transaction.</span></span>  
  
 <span data-ttu-id="4d90b-185">В следующем диаграмма обновления первый **\<sync>** блок обновляет запись в таблице Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="4d90b-185">In the following updategram, the first **\<sync>** block updates a record in the Sales.Customer table.</span></span> <span data-ttu-id="4d90b-186">Для простоты в диаграмме обновления указаны только обязательные значения столбцов: идентификатор (CustomerID) и обновляемое значение (SalesPersonID).</span><span class="sxs-lookup"><span data-stu-id="4d90b-186">For the sake of simplicity, the updategram specifies only the required column values; the identity value (CustomerID) and the value being updated (SalesPersonID).</span></span>  
  
 <span data-ttu-id="4d90b-187">Второй **\<sync>** блок добавляет две записи в таблицу Sales. SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="4d90b-187">The second **\<sync>** block adds two records to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="4d90b-188">В этой таблице SalesOrderID является столбцом типа IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="4d90b-188">For this table, SalesOrderID is an IDENTITY-type column.</span></span> <span data-ttu-id="4d90b-189">Таким образом, диаграмма обновления не задает значение SalesOrderID в каждом из \<Sales.SalesOrderHeader> элементов.</span><span class="sxs-lookup"><span data-stu-id="4d90b-189">Therefore, the updategram does not specify the value of SalesOrderID in each of the \<Sales.SalesOrderHeader> elements.</span></span>  
  
 <span data-ttu-id="4d90b-190">Указание нескольких **\<sync>** блоков полезно, поскольку если второму **\<sync>** блоку (транзакции) не удается добавить записи в таблицу Sales. SalesOrderHeader, первый **\<sync>** блок по-прежнему может обновить запись клиента в таблице Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="4d90b-190">Specifying multiple **\<sync>** blocks is useful because if the second **\<sync>** block (a transaction) fails to add records to Sales.SalesOrderHeader table, the first **\<sync>** block can still update the customer record in the Sales.Customer table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
      <Sales.Customer CustomerID="1" SalesPersonID="280" />  
    </updg:before>  
    <updg:after>  
      <Sales.Customer CustomerID="1" SalesPersonID="283" />  
    </updg:after>  
  </updg:sync>  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
   <Sales.SalesOrderHeader   
             CustomerID="1"  
             RevisionNumber="1"  
             OrderDate="2004-07-01 00:00:00.000"  
             DueDate="2004-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="01010101-2222-3333-4444-556677889900"  
             ModifiedDate="2004-07-08 00:00:00.000" />  
   <Sales.SalesOrderHeader  
             CustomerID="1"  
             RevisionNumber="1"  
             OrderDate="2004-07-01 00:00:00.000"  
             DueDate="2004-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="1000.0000"  
             TaxAmt="0.0000"  
             Freight="0.0000"  
             rowguid="10101010-2222-3333-4444-556677889900"  
             ModifiedDate="2004-07-09 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="4d90b-191">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="4d90b-191">To test the updategram</span></span>  
  
1.  <span data-ttu-id="4d90b-192">Скопируйте приведенный выше шаблон диаграммы обновления и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="4d90b-192">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="4d90b-193">Сохраните файл под именем UpdateMultipleSyncs.xml.</span><span class="sxs-lookup"><span data-stu-id="4d90b-193">Save the file as UpdateMultipleSyncs.xml.</span></span>  
  
2.  <span data-ttu-id="4d90b-194">Создайте тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs) и воспользуйтесь им для выполнения диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="4d90b-194">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="4d90b-195">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4d90b-195">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="e-using-a-mapping-schema"></a><span data-ttu-id="4d90b-196">Д.</span><span class="sxs-lookup"><span data-stu-id="4d90b-196">E.</span></span> <span data-ttu-id="4d90b-197">Использование схемы сопоставления</span><span class="sxs-lookup"><span data-stu-id="4d90b-197">Using a mapping schema</span></span>  
 <span data-ttu-id="4d90b-198">В данном примере диаграмма обновления указывает на схему сопоставления с помощью атрибута `mapping-schema`</span><span class="sxs-lookup"><span data-stu-id="4d90b-198">In this example, the updategram specifies a mapping schema by using the `mapping-schema` attribute.</span></span> <span data-ttu-id="4d90b-199">(сопоставление по умолчанию отсутствует; это означает, что сопоставление элементов и атрибутов в диаграмме обновления с таблицами и столбцами базы данных производится согласно схеме сопоставления).</span><span class="sxs-lookup"><span data-stu-id="4d90b-199">(There is no default mapping; that is, the mapping schema provides the necessary mapping of elements and attributes in the updategram to the database tables and columns.)</span></span>  
  
 <span data-ttu-id="4d90b-200">Элементы и атрибуты диаграммы обновления ссылаются на элементы и атрибуты схемы сопоставления.</span><span class="sxs-lookup"><span data-stu-id="4d90b-200">The elements and attributes specified in the updategram refer to the elements and attributes in the mapping schema.</span></span>  
  
 <span data-ttu-id="4d90b-201">Следующая схема сопоставления XSD содержит **\<Customer>** элементы, **\<Order>** и **\<OD>** , которые сопоставляются с таблицами Sales. Customer, Sales. SalesOrderHeader и Sales. SalesOrderDetail в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4d90b-201">The following XSD mapping schema has **\<Customer>**, **\<Order>**, and **\<OD>** elements that map to the Sales.Customer, Sales.SalesOrderHeader, and Sales.SalesOrderDetail tables in the database.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustomerOrder"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  
    <sql:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustomerOrder" >  
           <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OD"   
                             sql:relation="Sales.SalesOrderDetail"  
                             sql:relationship="OrderOD" >  
                 <xsd:complexType>  
                  <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                  <xsd:attribute name="ProductID" type="xsd:integer" />  
                  <xsd:attribute name="UnitPrice" type="xsd:decimal" />  
                  <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  <xsd:attribute name="UnitPriceDiscount" type="xsd:decimal" />   
                 </xsd:complexType>  
                </xsd:element>  
              </xsd:sequence>  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="OrderDate" type="xsd:date" />  
           </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="4d90b-202">Эта диаграмма сопоставления (UpdategramMappingSchema.xml) указывается в следующей диаграмме обновления.</span><span class="sxs-lookup"><span data-stu-id="4d90b-202">This mapping schema (UpdategramMappingSchema.xml) is specified in the following updategram.</span></span> <span data-ttu-id="4d90b-203">Диаграмма обновления добавляет элемент, содержащий сведения об определенном заказе, в таблицу Sales.SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="4d90b-203">The updategram adds an order detail item in the Sales.SalesOrderDetail table for a specific order.</span></span> <span data-ttu-id="4d90b-204">Диаграмма обновления включает вложенные элементы: **\<OD>** элемент, вложенный в **\<Order>** элемент.</span><span class="sxs-lookup"><span data-stu-id="4d90b-204">The updategram includes nested elements: an **\<OD>** element nested inside an **\<Order>** element.</span></span> <span data-ttu-id="4d90b-205">Связь «первичный ключ-внешний ключ» между этими элементами указывается в схеме сопоставления.</span><span class="sxs-lookup"><span data-stu-id="4d90b-205">The primary key/foreign key relationship between these two elements is specified in the mapping schema.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="UpdategramMappingSchema.xml" >  
    <updg:before>  
       <Order SalesOrderID="43659" />  
    </updg:before>  
    <updg:after>  
      <Order SalesOrderID="43659" >  
          <OD ProductID="776" UnitPrice="2329.0000"  
              OrderQty="2" UnitPriceDiscount="0.0" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="4d90b-206">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="4d90b-206">To test the updategram</span></span>  
  
1.  <span data-ttu-id="4d90b-207">Скопируйте приведенную выше схему сопоставления и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="4d90b-207">Copy the mapping schema above and paste it into a text file.</span></span> <span data-ttu-id="4d90b-208">Сохраните файл под именем UpdategramMappingSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="4d90b-208">Save the file as UpdategramMappingSchema.xml.</span></span>  
  
2.  <span data-ttu-id="4d90b-209">Скопируйте приведенный выше шаблон диаграммы обновления и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="4d90b-209">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="4d90b-210">Сохраните файл под именем UpdateWithMappingSchema.xml в той же папке, в которой сохранена схема сопоставления (UpdategramMappingSchema.xml).</span><span class="sxs-lookup"><span data-stu-id="4d90b-210">Save the file as UpdateWithMappingSchema.xml in the same folder as was used to save the mapping schema (UpdategramMappingSchema.xml).</span></span>  
  
3.  <span data-ttu-id="4d90b-211">Создайте тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs) и воспользуйтесь им для выполнения диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="4d90b-211">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="4d90b-212">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4d90b-212">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="4d90b-213">Дополнительные примеры диаграмм обновления, в которых используются схемы сопоставления, см. [в разделе Указание схемы сопоставления с заметками в диаграмма обновления &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4d90b-213">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
### <a name="f-using-a-mapping-schema-with-idrefs-attributes"></a><span data-ttu-id="4d90b-214">Е.</span><span class="sxs-lookup"><span data-stu-id="4d90b-214">F.</span></span> <span data-ttu-id="4d90b-215">Использование схемы сопоставления с атрибутами IDREFS</span><span class="sxs-lookup"><span data-stu-id="4d90b-215">Using a mapping schema with IDREFS attributes</span></span>  
 <span data-ttu-id="4d90b-216">В данном примере показано, каким образом диаграммы обновления используют атрибуты IDREFS в схеме сопоставления для обновления записей в нескольких таблицах.</span><span class="sxs-lookup"><span data-stu-id="4d90b-216">This example illustrates how updategrams use the IDREFS attributes in the mapping schema to update records in multiple tables.</span></span> <span data-ttu-id="4d90b-217">В этом примере предполагается, что база данных состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="4d90b-217">For this example, assume that the database consists of the following tables:</span></span>  
  
-   <span data-ttu-id="4d90b-218">Student(StudentID, LastName)</span><span class="sxs-lookup"><span data-stu-id="4d90b-218">Student(StudentID, LastName)</span></span>  
  
-   <span data-ttu-id="4d90b-219">Course(CourseID, CourseName)</span><span class="sxs-lookup"><span data-stu-id="4d90b-219">Course(CourseID, CourseName)</span></span>  
  
-   <span data-ttu-id="4d90b-220">Enrollment(StudentID, CourseID)</span><span class="sxs-lookup"><span data-stu-id="4d90b-220">Enrollment(StudentID, CourseID)</span></span>  
  
 <span data-ttu-id="4d90b-221">Поскольку один студент может быть записан на несколько разных курсов, а на курс может быть записано много студентов, третья таблица Enrollment должна представлять связь M:N.</span><span class="sxs-lookup"><span data-stu-id="4d90b-221">Because a student can enroll in many courses and a course can have many students, the third table, the Enrollment table, is required to represent this M:N relationship.</span></span>  
  
 <span data-ttu-id="4d90b-222">Следующая схема сопоставления XSD обеспечивает XML-представление таблиц с помощью **\<Student>** **\<Course>** элементов, и **\<Enrollment>** .</span><span class="sxs-lookup"><span data-stu-id="4d90b-222">The following XSD mapping schema provides an XML view of the tables by using the **\<Student>**, **\<Course>**, and **\<Enrollment>** elements.</span></span> <span data-ttu-id="4d90b-223">Атрибуты **IDREFS** в схеме сопоставления определяют связь между этими элементами.</span><span class="sxs-lookup"><span data-stu-id="4d90b-223">The **IDREFS** attributes in the mapping schema specify the relationship between these elements.</span></span> <span data-ttu-id="4d90b-224">Атрибут **студентидлист** **\<Course>** элемента является атрибутом типа **IDREFS** , который ссылается на столбец StudentId в таблице регистрации.</span><span class="sxs-lookup"><span data-stu-id="4d90b-224">The **StudentIDList** attribute on the **\<Course>** element is an **IDREFS** type attribute that refers to the StudentID column in the Enrollment table.</span></span> <span data-ttu-id="4d90b-225">Аналогичным образом атрибут **енролледин** **\<Student>** элемента — это атрибут типа **IDREFS** , который ссылается на столбец CourseID в таблице регистрации.</span><span class="sxs-lookup"><span data-stu-id="4d90b-225">Likewise, the **EnrolledIn** attribute on the **\<Student>** element is an **IDREFS** type attribute that refers to the CourseID column in the Enrollment table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="StudentEnrollment"  
          parent="Student"  
          parent-key="StudentID"  
          child="Enrollment"  
          child-key="StudentID" />  
  
    <sql:relationship name="CourseEnrollment"  
          parent="Course"  
          parent-key="CourseID"  
          child="Enrollment"  
          child-key="CourseID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Course" sql:relation="Course"   
                             sql:key-fields="CourseID" >  
    <xsd:complexType>  
    <xsd:attribute name="CourseID"  type="xsd:string" />   
    <xsd:attribute name="CourseName"   type="xsd:string" />   
    <xsd:attribute name="StudentIDList" sql:relation="Enrollment"  
                 sql:field="StudentID"  
                 sql:relationship="CourseEnrollment"   
                                     type="xsd:IDREFS" />  
  
    </xsd:complexType>  
  </xsd:element>  
  <xsd:element name="Student" sql:relation="Student" >  
    <xsd:complexType>  
    <xsd:attribute name="StudentID"  type="xsd:string" />   
    <xsd:attribute name="LastName"   type="xsd:string" />   
    <xsd:attribute name="EnrolledIn" sql:relation="Enrollment"  
                 sql:field="CourseID"  
                 sql:relationship="StudentEnrollment"   
                                     type="xsd:IDREFS" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="4d90b-226">Если указать эту схему в диаграмме обновления и добавить запись в таблицу Course, то диаграмма обновления вставит новую запись о курсе в таблицу Course.</span><span class="sxs-lookup"><span data-stu-id="4d90b-226">Whenever you specify this schema in an updategram and insert a record in the Course table, the updategram inserts a new course record in the Course table.</span></span> <span data-ttu-id="4d90b-227">Если указать один или несколько идентификаторов студентов в атрибуте StudentIDList, то диаграмма обновления также добавит запись в таблицу Enrollment для каждого нового студента.</span><span class="sxs-lookup"><span data-stu-id="4d90b-227">If you specify one or more new student IDs for the StudentIDList attribute, the updategram also inserts a record in the Enrollment table for the each new student.</span></span> <span data-ttu-id="4d90b-228">Диаграмма обновления обеспечивает отсутствие повторяющих друг друга записей в таблицу Enrollment.</span><span class="sxs-lookup"><span data-stu-id="4d90b-228">The updategram ensures that no duplicates are added to the Enrollment table.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="4d90b-229">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="4d90b-229">To test the updategram</span></span>  
  
1.  <span data-ttu-id="4d90b-230">Создайте эти таблицы в базе данных в виртуальном корневом каталоге:</span><span class="sxs-lookup"><span data-stu-id="4d90b-230">Create these tables in the database that is specified in the virtual root:</span></span>  
  
    ```  
    CREATE TABLE Student(StudentID varchar(10) primary key,   
                         LastName varchar(25))  
    CREATE TABLE Course(CourseID varchar(10) primary key,   
                        CourseName varchar(25))  
    CREATE TABLE Enrollment(StudentID varchar(10)   
                                      references Student(StudentID),  
                           CourseID varchar(10)   
                                      references Course(CourseID))  
    ```  
  
2.  <span data-ttu-id="4d90b-231">Добавьте следующий образец данных:</span><span class="sxs-lookup"><span data-stu-id="4d90b-231">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Student VALUES ('S1','Davoli')  
    INSERT INTO Student VALUES ('S2','Fuller')  
  
    INSERT INTO Course VALUES  ('CS101', 'C Programming')  
    INSERT INTO Course VALUES  ('CS102', 'Understanding XML')  
  
    INSERT INTO Enrollment VALUES ('S1', 'CS101')  
    INSERT INTO Enrollment VALUES ('S1', 'CS102')  
    ```  
  
3.  <span data-ttu-id="4d90b-232">Скопируйте приведенную выше схему сопоставления и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="4d90b-232">Copy the mapping schema above and paste it into a text file.</span></span> <span data-ttu-id="4d90b-233">Сохраните файл под именем SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="4d90b-233">Save the file as SampleSchema.xml.</span></span>  
  
4.  <span data-ttu-id="4d90b-234">Сохраните диаграмму обновления (SampleUpdategram) в той же папке, что и схему сопоставления в предыдущем шаге</span><span class="sxs-lookup"><span data-stu-id="4d90b-234">Save the updategram (SampleUpdategram) in the same folder used to save the mapping schema in the previous step.</span></span> <span data-ttu-id="4d90b-235">(эта диаграмма обновления удаляет студента с идентификатором StudentID="1" из курса CS102).</span><span class="sxs-lookup"><span data-stu-id="4d90b-235">(This updategram drops a student with StudentID="1" from the CS102 course.)</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101 CS102" />  
        </updg:before>  
        <updg:after >  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
5.  <span data-ttu-id="4d90b-236">Создайте тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs) и воспользуйтесь им для выполнения диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="4d90b-236">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="4d90b-237">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4d90b-237">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
6.  <span data-ttu-id="4d90b-238">Сохраните и выполните следующую диаграмму обновления, как описано на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="4d90b-238">Save and execute the following updategram as described in the previous steps.</span></span> <span data-ttu-id="4d90b-239">Диаграмма обновления снова записывает студента с идентификатором StudentID="1" на курс CS102 путем добавления записи в таблицу Enrollment.</span><span class="sxs-lookup"><span data-stu-id="4d90b-239">The updategram adds the student with StudentID="1" back into the CS102 course by adding a record in the Enrollment table.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101" />  
        </updg:before>  
        <updg:after >  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101 CS102" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
7.  <span data-ttu-id="4d90b-240">Сохраните и выполните следующую диаграмму обновления, как описано на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="4d90b-240">Save and execute this next updategram as described in the previous steps.</span></span> <span data-ttu-id="4d90b-241">Эта диаграмма обновления добавляет трех новых студентов и регистрирует их на курс CS101.</span><span class="sxs-lookup"><span data-stu-id="4d90b-241">This updategram inserts three new students and enrolls them in the CS101 course.</span></span> <span data-ttu-id="4d90b-242">Связь IDREFS вставляет запись в таблицу Enrollment.</span><span class="sxs-lookup"><span data-stu-id="4d90b-242">Again, the IDREFS relationship inserts records in the Enrollment table.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
           <Course updg:id="y" CourseID="CS101"   
                               CourseName="C Programming" />  
        </updg:before>  
        <updg:after >  
           <Student updg:id="x1" StudentID="S3" LastName="Leverling" />  
           <Student updg:id="x2" StudentID="S4" LastName="Pecock" />  
           <Student updg:id="x3" StudentID="S5" LastName="Buchanan" />  
           <Course updg:id="y" CourseID="CS101"  
                               CourseName="C Programming"  
                               StudentIDList="S3 S4 S5" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
 <span data-ttu-id="4d90b-243">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="4d90b-243">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ElementType name="Enrollment" sql:relation="Enrollment" sql:key-fields="StudentID CourseID">  
    <AttributeType name="StudentID" dt:type="id" />  
    <AttributeType name="CourseID" dt:type="id" />  
  
    <attribute type="StudentID" />  
    <attribute type="CourseID" />  
  </ElementType>  
  <ElementType name="Course" sql:relation="Course" sql:key-fields="CourseID">  
    <AttributeType name="CourseID" dt:type="id" />  
    <AttributeType name="CourseName" />  
  
    <attribute type="CourseID" />  
    <attribute type="CourseName" />  
  
    <AttributeType name="StudentIDList" dt:type="idrefs" />  
    <attribute type="StudentIDList" sql:relation="Enrollment" sql:field="StudentID" >  
        <sql:relationship  
                key-relation="Course"  
                key="CourseID"  
                foreign-relation="Enrollment"  
                foreign-key="CourseID" />  
    </attribute>  
  
  </ElementType>  
  <ElementType name="Student" sql:relation="Student">  
    <AttributeType name="StudentID" dt:type="id" />  
     <AttributeType name="LastName" />  
  
    <attribute type="StudentID" />  
    <attribute type="LastName" />  
  
    <AttributeType name="EnrolledIn" dt:type="idrefs" />  
    <attribute type="EnrolledIn" sql:relation="Enrollment" sql:field="CourseID" >  
        <sql:relationship  
                key-relation="Student"  
                key="StudentID"  
                foreign-relation="Enrollment"  
                foreign-key="StudentID" />  
    </attribute>  
  
    <element type="Enrollment" sql:relation="Enrollment" >  
        <sql:relationship key-relation="Student"  
                          key="StudentID"  
                          foreign-relation="Enrollment"  
                          foreign-key="StudentID" />  
    </element>  
  </ElementType>  
  
</Schema>  
```  
  
 <span data-ttu-id="4d90b-244">Дополнительные примеры диаграмм обновления, в которых используются схемы сопоставления, см. [в разделе Указание схемы сопоставления с заметками в диаграмма обновления &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4d90b-244">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d90b-245">См. также:</span><span class="sxs-lookup"><span data-stu-id="4d90b-245">See Also</span></span>  
 [<span data-ttu-id="4d90b-246">Вопросы безопасности диаграмма обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4d90b-246">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
