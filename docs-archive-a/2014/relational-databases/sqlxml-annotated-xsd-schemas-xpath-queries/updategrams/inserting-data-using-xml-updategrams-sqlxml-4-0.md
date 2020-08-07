---
title: Вставка данных с помощью XML диаграмм обновления (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- xsi:nil attribute
- unique values
- <after> block
- id attribute
- data insertions [SQLXML]
- nil attribute
- <before> block
- updg:guid attribute
- multiple record insertions
- returnid attribute
- updategrams [SQLXML], inserting data
- updg:at-identity attribute
- invalid characters [SQLXML]
- updg:returnid attribute
- updg:id attribute
- namespaces [SQLXML], updategrams
- IDENTITY-type column
- guid attribute
- record insertion [SQLXML]
- null values [SQLXML]
- at-identity attribute
- xml data type [SQL Server], SQLXML
ms.assetid: 4dc48762-bc12-43fb-b356-ea1b9c1e287e
author: rothja
ms.author: jroth
ms.openlocfilehash: a80f2cb157e59f30ebcbff5c14abba1003de9e40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732449"
---
# <a name="inserting-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="e0066-102">Вставка данных с помощью диаграмм обновления XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e0066-102">Inserting Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="e0066-103">Диаграмма обновления указывает операцию вставки, когда экземпляр записи появляется в **\<after>** блоке, но не в соответствующем **\<before>** блоке.</span><span class="sxs-lookup"><span data-stu-id="e0066-103">An updategram indicates an insert operation when a record instance appears in the **\<after>** block but not in the corresponding **\<before>** block.</span></span> <span data-ttu-id="e0066-104">В этом случае диаграмма обновления вставляет запись в **\<after>** блок в базу данных.</span><span class="sxs-lookup"><span data-stu-id="e0066-104">In this case, the updategram inserts the record in the **\<after>** block into the database.</span></span>  
  
 <span data-ttu-id="e0066-105">Ниже приведен формат диаграммы обновления для операции вставки:</span><span class="sxs-lookup"><span data-stu-id="e0066-105">This is the updategram format for an insert operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema="SampleSchema.xml"]  >  
   [<updg:before>  
   </updg:before>]  
    <updg:after [updg:returnid="x y ...] >  
       <ElementName [updg:id="value"]   
                   [updg:at-identity="x"]   
                   [updg:guid="y"]  
                   attribute="value"   
                   attribute="value"  
                   ...  
       />  
      [<ElementName .../>... ]  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
## <a name="before-block"></a><span data-ttu-id="e0066-106">\<before>Блок</span><span class="sxs-lookup"><span data-stu-id="e0066-106">\<before> Block</span></span>  
 <span data-ttu-id="e0066-107">**\<before>** Блок можно опустить для операции вставки.</span><span class="sxs-lookup"><span data-stu-id="e0066-107">The **\<before>** block can be omitted for an insert operation.</span></span> <span data-ttu-id="e0066-108">Если необязательный `mapping-schema` атрибут не указан, то объект **\<ElementName>** , указанный в диаграмма обновления, сопоставляется с таблицей базы данных, а дочерние элементы или атрибуты сопоставляются со столбцами в таблице.</span><span class="sxs-lookup"><span data-stu-id="e0066-108">If the optional `mapping-schema` attribute is not specified, the **\<ElementName>** that is specified in the updategram maps to a database table and the child elements or attributes map to columns in the table.</span></span>  
  
## <a name="after-block"></a><span data-ttu-id="e0066-109">\<after>Блок</span><span class="sxs-lookup"><span data-stu-id="e0066-109">\<after> Block</span></span>  
 <span data-ttu-id="e0066-110">В блоке можно указать одну или несколько записей **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="e0066-110">You can specify one or more records in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="e0066-111">Если **\<after>** блок не предоставляет значение для определенного столбца, диаграмма обновления использует значение по умолчанию, указанное в схеме с заметками (если указана схема).</span><span class="sxs-lookup"><span data-stu-id="e0066-111">If the **\<after>** block does not supply a value for a particular column, the updategram uses the default value that is specified in the annotated schema (if a schema has been specified).</span></span> <span data-ttu-id="e0066-112">Если в схеме не указано значение по умолчанию для столбца, диаграмма обновления не указывает явное значение для этого столбца, а вместо этого присваивает [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] этому столбцу значение по умолчанию (если указано).</span><span class="sxs-lookup"><span data-stu-id="e0066-112">If the schema does not specify a default value for the column, the updategram does not specify any explicit value to this column and, instead, assigns the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default value (if specified) to this column.</span></span> <span data-ttu-id="e0066-113">Если не существует значения по умолчанию [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и столбец допускает значение NULL, то диаграмма обновления задает для столбца значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e0066-113">If there is no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default value and the column accepts a NULL value, the updategram sets the column value to NULL.</span></span> <span data-ttu-id="e0066-114">Если столбец не имеет значения по умолчанию и не допускает значение NULL, команда завершается ошибкой и диаграмма обновления возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="e0066-114">If the column neither has a default value nor accepts a NULL value, the command fails and the updategram returns an error.</span></span> <span data-ttu-id="e0066-115">Необязательный атрибут `updg:returnid` используется, чтобы возвратить значение идентификатора, формируемое системой при добавлении записи в таблицу со столбцом типа IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="e0066-115">The optional `updg:returnid` attribute is used to return the identity value that is generated by the system when a record is added in a table with an IDENTITY-type column.</span></span>  
  
## <a name="updgid-attribute"></a><span data-ttu-id="e0066-116">Атрибут updg:id</span><span class="sxs-lookup"><span data-stu-id="e0066-116">updg:id Attribute</span></span>  
 <span data-ttu-id="e0066-117">Если диаграмма обновления только добавляет записи, атрибут `updg:id` не требуется.</span><span class="sxs-lookup"><span data-stu-id="e0066-117">If the updategram is inserting only records, the updategram does not require the `updg:id` attribute.</span></span> <span data-ttu-id="e0066-118">Дополнительные сведения о `updg:id` см. в разделе [Обновление данных с помощью XML ДИАГРАММ обновления &#40;SQLXML 4,0&#41;](updating-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-118">For more information about `updg:id`, see [Updating Data Using XML Updategrams &#40;SQLXML 4.0&#41;](updating-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
## <a name="updgat-identity-attribute"></a><span data-ttu-id="e0066-119">Атрибут updg:at-identity</span><span class="sxs-lookup"><span data-stu-id="e0066-119">updg:at-identity Attribute</span></span>  
 <span data-ttu-id="e0066-120">Когда диаграмма обновления вставляет запись в таблицу со столбцом типа IDENTITY, она может зафиксировать назначенное системой значение с помощью необязательного атрибута `updg:at-identity`.</span><span class="sxs-lookup"><span data-stu-id="e0066-120">When an updategram inserts a record in a table that has an IDENTITY-type column, the updategram can capture the system assigned value by using the optional `updg:at-identity` attribute.</span></span> <span data-ttu-id="e0066-121">Диаграмма обновления может потом использовать это значение в последующих операциях.</span><span class="sxs-lookup"><span data-stu-id="e0066-121">The updategram can then use this value in subsequent operations.</span></span> <span data-ttu-id="e0066-122">При выполнении диаграммы обновления можно возвратить сформированное значение идентификатора, указав атрибут `updg:returnid`.</span><span class="sxs-lookup"><span data-stu-id="e0066-122">Upon execution of the updategram, you can return the identity value that is generated by specifying the `updg:returnid` attribute.</span></span>  
  
## <a name="updgguid-attribute"></a><span data-ttu-id="e0066-123">Атрибут updg:guid</span><span class="sxs-lookup"><span data-stu-id="e0066-123">updg:guid Attribute</span></span>  
 <span data-ttu-id="e0066-124">Атрибут `updg:guid` является необязательным атрибутом, формирующим идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="e0066-124">The `updg:guid` attribute is an optional attribute that generates a globally unique identifier.</span></span> <span data-ttu-id="e0066-125">Это значение остается в области для всего **\<sync>** блока, в котором он указан.</span><span class="sxs-lookup"><span data-stu-id="e0066-125">This value remains in scope for the entire **\<sync>** block in which it is specified.</span></span> <span data-ttu-id="e0066-126">Это значение можно использовать в любом месте **\<sync>** блока.</span><span class="sxs-lookup"><span data-stu-id="e0066-126">You can use this value anywhere in the **\<sync>** block.</span></span> <span data-ttu-id="e0066-127">Атрибут вызывает `NEWGUID()` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] функцию для создания уникального идентификатора.</span><span class="sxs-lookup"><span data-stu-id="e0066-127">The attribute calls the `NEWGUID()`[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] function to generate the unique identifier.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e0066-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="e0066-128">Examples</span></span>  
 <span data-ttu-id="e0066-129">Чтобы создать рабочие образцы с помощью следующих примеров, необходимо выполнить требования, указанные в [требованиях к запуску примеров SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-129">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
 <span data-ttu-id="e0066-130">При использовании примеров диаграмм обновления необходимо учитывать следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="e0066-130">Before using the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="e0066-131">В большинстве примеров используется сопоставление по умолчанию (то есть в диаграмме обновления схема сопоставления не задана).</span><span class="sxs-lookup"><span data-stu-id="e0066-131">Most of the examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="e0066-132">Дополнительные примеры диаграмм обновления, в которых используются схемы сопоставления, см. [в разделе Указание схемы сопоставления с заметками в диаграмма обновления &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-132">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="e0066-133">В большинстве примеров задействован образец базы данных [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0066-133">Most of the examples use the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="e0066-134">Все обновления применяются к таблицам в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="e0066-134">All the updates are applied to the tables in this database.</span></span>  
  
### <a name="a-inserting-a-record-by-using-an-updategram"></a><span data-ttu-id="e0066-135">A.</span><span class="sxs-lookup"><span data-stu-id="e0066-135">A.</span></span> <span data-ttu-id="e0066-136">Вставка записи с помощью диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="e0066-136">Inserting a record by using an updategram</span></span>  
 <span data-ttu-id="e0066-137">Эта диаграмма обновления с атрибутивной моделью вставляет запись в таблицу HumanResources.Employee в базе данных [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0066-137">This attribute-centric updategram inserts a record in the HumanResources.Employee table in the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="e0066-138">В этом примере диаграмма обновления не указывает схему сопоставления.</span><span class="sxs-lookup"><span data-stu-id="e0066-138">In this example, the updategram does not specify a mapping schema.</span></span> <span data-ttu-id="e0066-139">Следовательно, диаграмма обновления использует сопоставление по умолчанию, при котором имя элемента сопоставляется с именем таблицы, а атрибуты или дочерние элементы сопоставляются со столбцами таблицы.</span><span class="sxs-lookup"><span data-stu-id="e0066-139">Therefore, the updategram uses default mapping, in which the element name maps to a table name and the attributes or child elements map to columns in that table.</span></span>  
  
 <span data-ttu-id="e0066-140">Схема [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] для таблицы HumanResources.Department налагает ограничение «not null» на все столбцы.</span><span class="sxs-lookup"><span data-stu-id="e0066-140">The [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] schema for the HumanResources.Department table imposes a 'not null' restriction on all columns.</span></span> <span data-ttu-id="e0066-141">Следовательно, диаграмма обновления должна содержать значения, указанные для всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="e0066-141">Therefore, the updategram must include values specified for all columns.</span></span> <span data-ttu-id="e0066-142">Столбец DepartmentID является столбцом типа IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="e0066-142">The DepartmentID is an IDENTITY-type column.</span></span> <span data-ttu-id="e0066-143">Поэтому для него значения не указаны.</span><span class="sxs-lookup"><span data-stu-id="e0066-143">Therefore, no values are specified for it.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department   
            Name="New Product Research"   
            GroupName="Research and Development"   
            ModifiedDate="2010-08-31"/>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e0066-144">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="e0066-144">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e0066-145">Скопируйте приведенную выше диаграмму обновления и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-145">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e0066-146">Сохраните файл под именем MyUpdategram.xml.</span><span class="sxs-lookup"><span data-stu-id="e0066-146">Save the file as MyUpdategram.xml.</span></span>  
  
2.  <span data-ttu-id="e0066-147">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="e0066-147">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e0066-148">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-148">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e0066-149">При элементном сопоставлении диаграмма обновления выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e0066-149">In an element-centric mapping, the updategram looks like this:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department>  
            <Name> New Product Research </Name>  
            <GroupName> Research and Development </GroupName>  
            <ModifiedDate>2010-08-31</ModifiedDate>  
       </HumanResources.Department>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e0066-150">В диаграмме обновления со смешанной моделью (элементной и атрибутивной) элемент может иметь как атрибуты, так и вложенные элементы, как показано на следующей диаграмме обновления:</span><span class="sxs-lookup"><span data-stu-id="e0066-150">In a mixed-mode (element-centric and attribute-centric) updategram, an element can have both attributes and subelements, as shown in this updategram:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department   
            Name=" New Product Research "   
            <GroupName>Research and Development</GroupName>  
            <ModifiedDate>2010-08-31</ModifiedDate>  
       </HumanResources.Department>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
### <a name="b-inserting-multiple-records-by-using-an-updategram"></a><span data-ttu-id="e0066-151">Б.</span><span class="sxs-lookup"><span data-stu-id="e0066-151">B.</span></span> <span data-ttu-id="e0066-152">Вставка нескольких записей с помощью диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="e0066-152">Inserting multiple records by using an updategram</span></span>  
 <span data-ttu-id="e0066-153">Данная диаграмма обновления добавляет две новые записи о сменах в таблицу HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="e0066-153">This updategram adds two new shift records to the HumanResources.Shift table.</span></span> <span data-ttu-id="e0066-154">В диаграмма обновления не указан необязательный **\<before>** блок.</span><span class="sxs-lookup"><span data-stu-id="e0066-154">The updategram does not specify the optional **\<before>** block.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync>  
    <updg:after >  
       <HumanResources.Shift Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e0066-155">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="e0066-155">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e0066-156">Скопируйте приведенную выше диаграмму обновления и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-156">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e0066-157">Сохраните файл под именем Updategram-AddShifts.xml.</span><span class="sxs-lookup"><span data-stu-id="e0066-157">Save the file as Updategram-AddShifts.xml.</span></span>  
  
2.  <span data-ttu-id="e0066-158">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="e0066-158">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e0066-159">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-159">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e0066-160">Другой версией этого примера является диаграмма обновления, использующий два отдельных **\<after>** блока, а не один блок для вставки двух сотрудников.</span><span class="sxs-lookup"><span data-stu-id="e0066-160">Another version of this example is an updategram that uses two separate **\<after>** blocks instead of one block to insert the two employees.</span></span> <span data-ttu-id="e0066-161">Это допустимо и может быть закодировано следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e0066-161">This is valid and can be encoded as follows:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync>  
    <updg:after >  
       <HumanResources.Shift Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
    <updg:before>  
    </updg:before>  
    <updg:after >  
       <HumanResources.Shift Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
### <a name="c-working-with-valid-sql-server-characters-that-are-not-valid-in-xml"></a><span data-ttu-id="e0066-162">В.</span><span class="sxs-lookup"><span data-stu-id="e0066-162">C.</span></span> <span data-ttu-id="e0066-163">Работа с допустимыми символами SQL Server, не являющимися допустимыми в XML</span><span class="sxs-lookup"><span data-stu-id="e0066-163">Working with valid SQL Server characters that are not valid in XML</span></span>  
 <span data-ttu-id="e0066-164">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] имена таблиц могут содержать пробелы, как, например, таблица Order Details в базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="e0066-164">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], table names can include a space, such as the Order Details table in the Northwind database.</span></span> <span data-ttu-id="e0066-165">Однако это недопустимо в XML-символах, которые являются допустимыми [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] идентификаторами, но недопустимые идентификаторы XML могут быть закодированы с помощью "__xHHHH \_ \_ " в качестве значения кодировки, где HHHH обозначает шестнадцатеричный восьмеричный код UCS-2 для символа в наиболее значимом битовом порядке.</span><span class="sxs-lookup"><span data-stu-id="e0066-165">However, this is not valid in XML characters that are valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identifiers but not valid XML identifiers can be encoded using '__xHHHH\_\_' as the encoding value, where HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0066-166">В данном примере используется образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="e0066-166">This example uses the Northwind database.</span></span> <span data-ttu-id="e0066-167">Базу данных Northwind можно установить с помощью скрипта SQL, доступного для загрузки с этого [веб-сайта корпорации Майкрософт](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span><span class="sxs-lookup"><span data-stu-id="e0066-167">You can install the Northwind database by using an SQL script available for download from this [Microsoft Web site](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>  
  
 <span data-ttu-id="e0066-168">Кроме того, имя элемента должно быть заключено в квадратные скобки ([ ]).</span><span class="sxs-lookup"><span data-stu-id="e0066-168">Also, the element name must be enclosed within brackets ([ ]).</span></span> <span data-ttu-id="e0066-169">Поскольку символы [и] недопустимы в XML, их необходимо кодировать как _x005B \_ и _x005D \_ соответственно.</span><span class="sxs-lookup"><span data-stu-id="e0066-169">Because the characters [and] are not valid in XML, you must encode them as _x005B\_ and _x005D\_, respectively.</span></span> <span data-ttu-id="e0066-170">Если используется схема сопоставления, то можно предоставить имена элементов, не содержащие недопустимых символов, таких как пробелы.</span><span class="sxs-lookup"><span data-stu-id="e0066-170">(If you use a mapping schema, you can provide element names that do not contain characters that are not valid, such as white spaces.</span></span> <span data-ttu-id="e0066-171">Схема сопоставления выполняет необходимое сопоставление, следовательно, необязательно кодировать эти символы.</span><span class="sxs-lookup"><span data-stu-id="e0066-171">The mapping schema does the necessary mapping; therefore, you do not need to encode for these characters).</span></span>  
  
 <span data-ttu-id="e0066-172">Эта диаграмма обновления добавляет запись в таблицу Order Details в базе данных Northwind:</span><span class="sxs-lookup"><span data-stu-id="e0066-172">This updategram adds a record to the Order Details table in the Northwind database:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
      <_x005B_Order_x0020_Details_x005D_ OrderID="1"  
            ProductID="11"  
            UnitPrice="$1.0"  
            Quantity="1"  
            Discount="0.0" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e0066-173">Столбец UnitPrice в таблице Order Details имеет тип `money`.</span><span class="sxs-lookup"><span data-stu-id="e0066-173">The UnitPrice column in the Order Details table is of the `money` type.</span></span> <span data-ttu-id="e0066-174">Чтобы применить соответствующее преобразование типов (из типа `string` к типу `money`), необходимо добавить как часть значения символ доллара ($).</span><span class="sxs-lookup"><span data-stu-id="e0066-174">To apply the appropriate type conversion (from a `string` type to a `money` type), the dollar sign character ($) must be added as part of the value.</span></span> <span data-ttu-id="e0066-175">Если диаграмма обновления не указывает схему сопоставления, оценивается первый символ значения `string`.</span><span class="sxs-lookup"><span data-stu-id="e0066-175">If the updategram does not specify a mapping schema, the first character of the `string` value is evaluated.</span></span> <span data-ttu-id="e0066-176">Если первый символ — символ доллара ($), применяется соответствующее преобразование.</span><span class="sxs-lookup"><span data-stu-id="e0066-176">If the first character is a dollar sign ($), the appropriate conversion is applied.</span></span>  
  
 <span data-ttu-id="e0066-177">Если диаграмма обновления указывает схему сопоставления, где столбец помечен соответственно как `dt:type="fixed.14.4"` или `sql:datatype="money"`, то символ доллара ($) не требуется и преобразование обрабатывается сопоставлением.</span><span class="sxs-lookup"><span data-stu-id="e0066-177">If the updategram is specified against a mapping schema where the column is appropriately marked as either `dt:type="fixed.14.4"` or `sql:datatype="money"`, the dollar sign ($) is not required and the conversion is handled by the mapping.</span></span> <span data-ttu-id="e0066-178">Это рекомендуемый способ, который гарантирует, что соответствующее преобразование типов происходит.</span><span class="sxs-lookup"><span data-stu-id="e0066-178">This is the recommended way to ensure that the appropriate type conversion occurs.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e0066-179">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="e0066-179">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e0066-180">Скопируйте приведенную выше диаграмму обновления и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-180">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e0066-181">Сохраните файл под именем UpdategramSpacesInTableName.xml.</span><span class="sxs-lookup"><span data-stu-id="e0066-181">Save the file as UpdategramSpacesInTableName.xml.</span></span>  
  
2.  <span data-ttu-id="e0066-182">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="e0066-182">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e0066-183">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-183">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="d-using-the-at-identity-attribute-to-retrieve-the-value-that-has-been-inserted-in-the-identity-type-column"></a><span data-ttu-id="e0066-184">Г.</span><span class="sxs-lookup"><span data-stu-id="e0066-184">D.</span></span> <span data-ttu-id="e0066-185">Использование атрибута at-identity для получения значения, вставленного в столбец типа IDENTITY</span><span class="sxs-lookup"><span data-stu-id="e0066-185">Using the at-identity attribute to retrieve the value that has been inserted in the IDENTITY-type column</span></span>  
 <span data-ttu-id="e0066-186">Следующая диаграмма обновления вставляет две записи: одну в таблицу Sales.SalesOrderHeader, а другую — в таблицу Sales.SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="e0066-186">The following updategram inserts two records: one in the Sales.SalesOrderHeader table and another in the Sales.SalesOrderDetail table.</span></span>  
  
 <span data-ttu-id="e0066-187">Сначала диаграмма обновления добавляет запись в таблицу Sales.SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="e0066-187">First, the updategram adds a record to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="e0066-188">В этой таблице столбец SalesOrderID является столбцом типа IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="e0066-188">In this table, the SalesOrderID column is an IDENTITY-type column.</span></span> <span data-ttu-id="e0066-189">Поэтому при добавлении этой записи в таблицу диаграмма обновления использует атрибут `at-identity`, чтобы сохранить присвоенное столбцу SalesOrderID значение как «x» (значение заполнителя).</span><span class="sxs-lookup"><span data-stu-id="e0066-189">Therefore, when you add this record to the table, the updategram uses the `at-identity` attribute to capture the assigned SalesOrderID value as "x" (a placeholder value).</span></span> <span data-ttu-id="e0066-190">Затем используется задает эту `at-identity` переменную как значение атрибута SalesOrderID в \<Sales.SalesOrderDetail> элементе.</span><span class="sxs-lookup"><span data-stu-id="e0066-190">The updategam then specifies this `at-identity` variable as the value of SalesOrderID attribute in the \<Sales.SalesOrderDetail> element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
 <updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
   <Sales.SalesOrderHeader updg:at-identity="x"   
             RevisionNumber="1"  
             OrderDate="2001-07-01 00:00:00.000"  
             DueDate="2001-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             CustomerID="676"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="00001111-2222-3333-4444-556677889900"  
             ModifiedDate="2001-07-08 00:00:00.000" />  
      <Sales.SalesOrderDetail SalesOrderID="x"  
                LineNumber="1"  
                OrderQty="1"  
                ProductID="776"  
                SpecialOfferID="1"  
                UnitPrice="2429.9928"  
                UnitPriceDiscount="0.00"  
                rowguid="aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee"  
                ModifiedDate="2001-07-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e0066-191">Если необходимо вернуть значение идентификатора, формируемое атрибутом `updg:at-identity`, можно использовать атрибут `updg:returnid`.</span><span class="sxs-lookup"><span data-stu-id="e0066-191">If you want to return the identity value that is generated by the `updg:at-identity` attribute, you can use the `updg:returnid` attribute.</span></span> <span data-ttu-id="e0066-192">Ниже показана измененная диаграмма обновления, которая возвращает значение идентификатора.</span><span class="sxs-lookup"><span data-stu-id="e0066-192">The following is a revised updategram that returns this identity value.</span></span> <span data-ttu-id="e0066-193">Эта диаграмма обновления добавляет две записи заказа и две записи подробностей заказа, чтобы немного усложнить пример.</span><span class="sxs-lookup"><span data-stu-id="e0066-193">(This updategram adds two order records and two order detail records, just to make the example a little more complex.)</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
 <updg:sync>  
  <updg:before>  
  </updg:before>  
  <updg:after updg:returnid="x y" >  
       <HumanResources.Shift updg:at-identity="x" Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift updg:at-identity="y" Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
  </updg:after>  
 </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e0066-194">При выполнении диаграммы обновления она возвращает результат, подобный следующему, который содержит сформированное значение идентификатора (сформированное значение столбца ShiftID, используемого для идентификатора таблицы):</span><span class="sxs-lookup"><span data-stu-id="e0066-194">When the updategram is executed, it returns results similar to the following, which includes the identity value (the generated value of the ShiftID column used for table identity) that was generated:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">   
  <returnid>   
    <x>4</x>   
    <y>5</y>   
  </returnid>   
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e0066-195">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="e0066-195">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e0066-196">Скопируйте приведенную выше диаграмму обновления и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-196">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e0066-197">Сохраните файл под именем Updategram-returnId.xml.</span><span class="sxs-lookup"><span data-stu-id="e0066-197">Save the file as Updategram-returnId.xml.</span></span>  
  
2.  <span data-ttu-id="e0066-198">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="e0066-198">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e0066-199">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-199">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="e-using-the-updgguid-attribute-to-generate-a-unique-value"></a><span data-ttu-id="e0066-200">Д.</span><span class="sxs-lookup"><span data-stu-id="e0066-200">E.</span></span> <span data-ttu-id="e0066-201">Использование атрибута updg:guid для формирования уникального значения</span><span class="sxs-lookup"><span data-stu-id="e0066-201">Using the updg:guid attribute to generate a unique value</span></span>  
 <span data-ttu-id="e0066-202">В этом примере диаграмма обновления вставляет запись в таблицы Cust и CustOrder.</span><span class="sxs-lookup"><span data-stu-id="e0066-202">In this example, the updategram inserts a record in the Cust and CustOrder tables.</span></span> <span data-ttu-id="e0066-203">Также диаграмма обновления формирует уникальное значение атрибута CustomerID с помощью атрибута `updg:guid`.</span><span class="sxs-lookup"><span data-stu-id="e0066-203">Also, the updategram generates a unique value for the CustomerID attribute by using the `updg:guid` attribute.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after updg:returnid="x" >  
      <Cust updg:guid="x" >  
         <CustID>x</CustID>  
         <LastName>Fuller</LastName>  
      </Cust>  
      <CustOrder>  
         <CustID>x</CustID>  
         <OrderID>1</OrderID>  
      </CustOrder>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e0066-204">Диаграмма обновления указывает атрибут `returnid`.</span><span class="sxs-lookup"><span data-stu-id="e0066-204">The updategram specifies the `returnid` attribute.</span></span> <span data-ttu-id="e0066-205">В результате возвращается сформированное значение GUID:</span><span class="sxs-lookup"><span data-stu-id="e0066-205">As a result, the GUID that is generated is returned:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <returnid>  
    <x>7111BD1A-7F0B-4CEE-B411-260DADFEFA2A</x>   
  </returnid>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e0066-206">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="e0066-206">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e0066-207">Скопируйте приведенную выше диаграмму обновления и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-207">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e0066-208">Сохраните файл под именем Updategram-GenerateGuid.xml.</span><span class="sxs-lookup"><span data-stu-id="e0066-208">Save the file as Updategram-GenerateGuid.xml.</span></span>  
  
2.  <span data-ttu-id="e0066-209">Создайте следующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="e0066-209">Create these tables:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust (CustID uniqueidentifier, LastName varchar(20))  
    CREATE TABLE CustOrder (CustID uniqueidentifier, OrderID int)  
    ```  
  
3.  <span data-ttu-id="e0066-210">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="e0066-210">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e0066-211">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-211">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="f-specifying-a-schema-in-an-updategram"></a><span data-ttu-id="e0066-212">Е.</span><span class="sxs-lookup"><span data-stu-id="e0066-212">F.</span></span> <span data-ttu-id="e0066-213">Указание схемы в диаграмме обновления</span><span class="sxs-lookup"><span data-stu-id="e0066-213">Specifying a schema in an updategram</span></span>  
 <span data-ttu-id="e0066-214">Диаграмма обновления в этом примере вставляет запись в следующую таблицу:</span><span class="sxs-lookup"><span data-stu-id="e0066-214">The updategram in this example inserts a record into the following table:</span></span>  
  
```  
CustOrder(OrderID, EmployeeID, OrderType)  
```  
  
 <span data-ttu-id="e0066-215">В этой диаграмме обновления указана схема XSD (нет сопоставления по умолчанию элементов и атрибутов диаграммы обновления).</span><span class="sxs-lookup"><span data-stu-id="e0066-215">An XSD schema is specified in this updategram (that is, there is no default mapping of updategram elements and attributes).</span></span> <span data-ttu-id="e0066-216">Схема обеспечивает необходимое сопоставление элементов и атрибутов таблицам и столбцам базы данных.</span><span class="sxs-lookup"><span data-stu-id="e0066-216">The schema provides the necessary mapping of the elements and attributes to the database tables and columns.</span></span>  
  
 <span data-ttu-id="e0066-217">Следующая схема (CustOrderSchema.xml) описывает **\<CustOrder>** элемент, состоящий из атрибутов **OrderID** и **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="e0066-217">The following schema (CustOrderSchema.xml) describes a **\<CustOrder>** element that consists of the **OrderID** and **EmployeeID** attributes.</span></span> <span data-ttu-id="e0066-218">Чтобы сделать схему более интересной, атрибуту **EmployeeID** присваивается значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0066-218">To make the schema more interesting, a default value is assigned to the **EmployeeID** attribute.</span></span> <span data-ttu-id="e0066-219">В диаграмме обновления значение атрибута по умолчанию используется только для операций вставки, и только если диаграмма обновления не указывает этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="e0066-219">An updategram uses an attribute's default value only for insert operations, and then only if the updategram does not specify that attribute.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="CustOrder" >  
   <xsd:complexType>  
        <xsd:attribute name="OrderID"     type="xsd:integer" />   
        <xsd:attribute name="EmployeeID"  type="xsd:integer" />  
        <xsd:attribute name="OrderType  " type="xsd:integer" default="1"/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="e0066-220">Эта диаграмма обновления вставляет записи в таблицу CustOrder.</span><span class="sxs-lookup"><span data-stu-id="e0066-220">This updategram inserts a record into the CustOrder table.</span></span> <span data-ttu-id="e0066-221">Диаграмма обновления указывает только значения атрибутов OrderID и EmployeeID.</span><span class="sxs-lookup"><span data-stu-id="e0066-221">The updategram specifies only the OrderID and EmployeeID attribute values.</span></span> <span data-ttu-id="e0066-222">Она не указывает значение атрибута OrderType.</span><span class="sxs-lookup"><span data-stu-id="e0066-222">It does not specify the OrderType attribute value.</span></span> <span data-ttu-id="e0066-223">Поэтому в диаграмме обновления используется значение по умолчанию для атрибута EmployeeID, указанное в предшествующей схеме.</span><span class="sxs-lookup"><span data-stu-id="e0066-223">Therefore, the updategram uses the default value of the EmployeeID attribute that is specified in the preceding schema.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"  
             xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync mapping-schema='CustOrderSchema.xml'>  
<updg:after>  
       <CustOrder OrderID="98000" EmployeeID="1" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e0066-224">Дополнительные примеры диаграмм обновления, указывающие схему сопоставления, см. [в разделе Указание схемы сопоставления с заметками в диаграмма обновления &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-224">For more examples of updategrams that specify a mapping schema, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e0066-225">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="e0066-225">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e0066-226">Создайте эту таблицу в базе данных **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="e0066-226">Create this table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE CustOrder(  
                     OrderID int,   
                     EmployeeID int,   
                     OrderType int)  
    ```  
  
2.  <span data-ttu-id="e0066-227">Скопируйте приведенную выше схему и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-227">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="e0066-228">Сохраните файл под именем CustOrderSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="e0066-228">Save the file as CustOrderSchema.xml.</span></span>  
  
3.  <span data-ttu-id="e0066-229">Скопируйте приведенную выше диаграмму обновления и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-229">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e0066-230">Сохраните файл под именем CustOrderUpdategram.xml в той же папке, которая используется в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="e0066-230">Save the file as CustOrderUpdategram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="e0066-231">Создайте тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs) и воспользуйтесь им для выполнения диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="e0066-231">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="e0066-232">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-232">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e0066-233">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="e0066-233">This is the equivalent XDR schema:</span></span>  
  
```  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
 <ElementType name="CustOrder" >  
    <AttributeType name="OrderID" />  
    <AttributeType name="EmployeeID" />  
    <AttributeType name="OrderType" default="1" />  
    <attribute type="OrderID"  />  
    <attribute type="EmployeeID" />  
    <attribute type="OrderType" />  
  </ElementType>  
</Schema>  
```  
  
### <a name="g-using-the-xsinil-attribute-to-insert-null-values-in-a-column"></a><span data-ttu-id="e0066-234">Ж.</span><span class="sxs-lookup"><span data-stu-id="e0066-234">G.</span></span> <span data-ttu-id="e0066-235">Использование атрибута xsi:nil для вставки в столбец значений NULL</span><span class="sxs-lookup"><span data-stu-id="e0066-235">Using the xsi:nil attribute to insert null values in a column</span></span>  
 <span data-ttu-id="e0066-236">Если необходимо вставить значение NULL в соответствующий столбец таблицы, можно указать атрибут `xsi:nil` для элемента в диаграмме обновления.</span><span class="sxs-lookup"><span data-stu-id="e0066-236">If you want to insert a null value in the corresponding column in the table, you can specify the `xsi:nil` attribute on an element in an updategram.</span></span> <span data-ttu-id="e0066-237">Также необходимо указать атрибут XSD `nillable` в соответствующей схеме XSD.</span><span class="sxs-lookup"><span data-stu-id="e0066-237">In the corresponding XSD schema, the XSD `nillable` attribute also must be specified.</span></span>  
  
 <span data-ttu-id="e0066-238">В качестве примера рассмотрим следующую схему XSD.</span><span class="sxs-lookup"><span data-stu-id="e0066-238">For example, consider this XSD schema:</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="Student" sql:relation="Students">  
  <xsd:complexType>  
    <xsd:all>  
      <xsd:element name="fname" sql:field="first_name"   
                                type="xsd:string"   
                                 nillable="true"/>  
    </xsd:all>  
    <xsd:attribute name="SID"   
                        sql:field="StudentID"  
                        type="xsd:ID"/>      
    <xsd:attribute name="lname"       
                        sql:field="last_name"  
                        type="xsd:string"/>  
    <xsd:attribute name="minitial"    
                        sql:field="middle_initial"   
                        type="xsd:string"/>  
    <xsd:attribute name="years"       
                         sql:field="no_of_years"  
                         type="xsd:integer"/>  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="e0066-239">Схема XSD задает для элемента **значение обнуляемых = "true"** **\<fname>** .</span><span class="sxs-lookup"><span data-stu-id="e0066-239">The XSD schema specifies **nillable="true"** for the **\<fname>** element.</span></span> <span data-ttu-id="e0066-240">Следующая диаграмма обновления использует эту схему:</span><span class="sxs-lookup"><span data-stu-id="e0066-240">The following updategram uses this schema:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"  
      xmlns:updg="urn:schemas-microsoft-com:xml-updategram"  
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  
<updg:sync mapping-schema='StudentSchema.xml'>  
  <updg:before/>  
  <updg:after>  
    <Student SID="S00004" lname="Elmaci" minitial="" years="2">  
      <fname xsi:nil="true">  
    </fname>  
    </Student>  
  </updg:after>  
</updg:sync>  
  
</ROOT>  
```  
  
 <span data-ttu-id="e0066-241">Диаграмма обновления указывает на `xsi:nil` **\<fname>** элемент в **\<after>** блоке.</span><span class="sxs-lookup"><span data-stu-id="e0066-241">The updategram specifies `xsi:nil` for the **\<fname>** element in the **\<after>** block.</span></span> <span data-ttu-id="e0066-242">Поэтому при выполнении этой диаграммы обновления значение NULL вставляется для столбца first_name таблицы.</span><span class="sxs-lookup"><span data-stu-id="e0066-242">Therefore, when this updategram is executed, a value of NULL is inserted for the first_name column in the table.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e0066-243">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="e0066-243">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e0066-244">Создайте в базе данных **tempdb** следующую таблицу:</span><span class="sxs-lookup"><span data-stu-id="e0066-244">Create the following table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Students (  
       StudentID char(6)NOT NULL ,  
       first_name varchar(50),  
       last_name varchar(50),  
       middle_initial char(1),  
       no_of_years int NULL)  
    GO  
    ```  
  
2.  <span data-ttu-id="e0066-245">Скопируйте приведенную выше схему и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-245">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="e0066-246">Сохраните файл под именем StudentSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="e0066-246">Save the file as StudentSchema.xml.</span></span>  
  
3.  <span data-ttu-id="e0066-247">Скопируйте приведенную выше диаграмму обновления и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-247">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e0066-248">Сохраните файл под именем StudentUpdategram.xml в той же папке, которая использовалась на предыдущем шаге для сохранения файла StudentSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="e0066-248">Save the file as StudentUpdategram.xml in the same folder used in previous step to save StudentSchema.xml.</span></span>  
  
4.  <span data-ttu-id="e0066-249">Создайте тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs) и воспользуйтесь им для выполнения диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="e0066-249">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="e0066-250">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-250">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="h-specifying-namespaces-in-an-updategram"></a><span data-ttu-id="e0066-251">З.</span><span class="sxs-lookup"><span data-stu-id="e0066-251">H.</span></span> <span data-ttu-id="e0066-252">Указание пространств имен в диаграмме обновления</span><span class="sxs-lookup"><span data-stu-id="e0066-252">Specifying namespaces in an updategram</span></span>  
 <span data-ttu-id="e0066-253">Диаграмма обновления может содержать элементы, которые принадлежат пространству имен, объявленному в этом же элементе диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="e0066-253">In an updategram you can have elements that belong to a namespace declared in the same element in the updategram.</span></span> <span data-ttu-id="e0066-254">В этом случае соответствующая схема также должна объявлять то же пространство имен и элемент должен принадлежать этому целевому пространству имен.</span><span class="sxs-lookup"><span data-stu-id="e0066-254">In this case, the corresponding schema must also declare the same namespace and the element must belong to that target namespace.</span></span>  
  
 <span data-ttu-id="e0066-255">Например, в следующем диаграмма обновления (UpdateGram-ElementHavingNamespace.xml) **\<Order>** элемент принадлежит пространству имен, объявленному в элементе.</span><span class="sxs-lookup"><span data-stu-id="e0066-255">For example, in the following updategram (UpdateGram-ElementHavingNamespace.xml), the **\<Order>** element belongs to a namespace declared in the element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema='XSD-ElementHavingNameSpace.xml'>  
    <updg:after>  
       <x:Order  xmlns:x="http://server/xyz/schemas/"  
             updg:at-identity="SalesOrderID"   
             RevisionNumber="1"  
             OrderDate="2001-07-01 00:00:00.000"  
             DueDate="2001-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             CustomerID="676"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="00009999-8888-7777-6666-554433221100"  
             ModifiedDate="2001-07-08 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e0066-256">В этом случае схема должна тоже объявлять пространство имен, как показано в следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="e0066-256">In this case, the schema must also declare the namespace as shown in this schema:</span></span>  
  
 <span data-ttu-id="e0066-257">Следующая схема (XSD-ElementHavingNamespace.xml) показывает, как должен быть декларирован соответствующий элемент и атрибуты.</span><span class="sxs-lookup"><span data-stu-id="e0066-257">The following schema (XSD-ElementHavingNamespace.xml) shows how the corresponding element and attributes must be declared.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
     xmlns:dt="urn:schemas-microsoft-com:datatypes"   
     xmlns:sql="urn:schemas-microsoft-com:mapping-schema"    
     xmlns:x="http://server/xyz/schemas/"   
     targetNamespace="http://server/xyz/schemas/" >  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" type="x:Order_type"/>  
  <xsd:complexType name="Order_type">  
    <xsd:attribute name="SalesOrderID"  type="xsd:ID"/>  
    <xsd:attribute name="RevisionNumber" type="xsd:unsignedByte"/>  
    <xsd:attribute name="OrderDate" type="xsd:dateTime"/>  
    <xsd:attribute name="DueDate" type="xsd:dateTime"/>  
    <xsd:attribute name="ShipDate" type="xsd:dateTime"/>  
    <xsd:attribute name="Status" type="xsd:unsignedByte"/>  
    <xsd:attribute name="OnlineOrderFlag" type="xsd:boolean"/>  
    <xsd:attribute name="SalesOrderNumber" type="xsd:string"/>  
    <xsd:attribute name="PurchaseOrderNumber" type="xsd:string"/>  
    <xsd:attribute name="AccountNumber" type="xsd:string"/>  
    <xsd:attribute name="CustomerID" type="xsd:int"/>  
    <xsd:attribute name="ContactID" type="xsd:int"/>  
    <xsd:attribute name="SalesPersonID" type="xsd:int"/>  
    <xsd:attribute name="TerritoryID" type="xsd:int"/>  
    <xsd:attribute name="BillToAddressID" type="xsd:int"/>  
    <xsd:attribute name="ShipToAddressID" type="xsd:int"/>  
    <xsd:attribute name="ShipMethodID" type="xsd:int"/>  
    <xsd:attribute name="CreditCardID" type="xsd:int"/>  
    <xsd:attribute name="CreditCardApprovalCode" type="xsd:string"/>  
    <xsd:attribute name="CurrencyRateID" type="xsd:int"/>  
    <xsd:attribute name="SubTotal" type="xsd:decimal"/>  
    <xsd:attribute name="TaxAmt" type="xsd:decimal"/>  
    <xsd:attribute name="Freight" type="xsd:decimal"/>  
    <xsd:attribute name="TotalDue" type="xsd:decimal"/>  
    <xsd:attribute name="Comment" type="xsd:string"/>  
    <xsd:attribute name="rowguid" type="xsd:string"/>  
    <xsd:attribute name="ModifiedDate" type="xsd:dateTime"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e0066-258">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="e0066-258">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e0066-259">Скопируйте приведенную выше схему и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-259">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="e0066-260">Сохраните файл под именем XSD-ElementHavingNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="e0066-260">Save the file as XSD-ElementHavingNamespace.xml.</span></span>  
  
2.  <span data-ttu-id="e0066-261">Скопируйте приведенную выше диаграмму обновления и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-261">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e0066-262">Сохраните файл под именем Updategram-ElementHavingNamespace.xml в той же папке, в которой был сохранен файл XSD-ElementHavingnamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="e0066-262">Save the file as Updategram-ElementHavingNamespace.xml in the same folder used to save XSD-ElementHavingnamespace.xml.</span></span>  
  
3.  <span data-ttu-id="e0066-263">Создайте тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs) и воспользуйтесь им для выполнения диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="e0066-263">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="e0066-264">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-264">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="i-inserting-data-into-an-xml-data-type-column"></a><span data-ttu-id="e0066-265">И.</span><span class="sxs-lookup"><span data-stu-id="e0066-265">I.</span></span> <span data-ttu-id="e0066-266">Вставка данных в столбец типа данных XML</span><span class="sxs-lookup"><span data-stu-id="e0066-266">Inserting data into an XML data type column</span></span>  
 <span data-ttu-id="e0066-267">В [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] появился тип данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="e0066-267">The `xml` data type was introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="e0066-268">Диаграммы обновления можно использовать для вставки и обновления данных, хранимых в столбцах типа `xml` при следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="e0066-268">You can use updategrams to insert and update data stored in `xml` data type columns with the following provisions:</span></span>  
  
-   <span data-ttu-id="e0066-269">Столбец `xml` нельзя использовать для идентификации существующей строки.</span><span class="sxs-lookup"><span data-stu-id="e0066-269">The `xml` column cannot be used for identifying an existing row.</span></span> <span data-ttu-id="e0066-270">Поэтому его невозможно включить в раздел `updg:before` диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="e0066-270">Therefore, it cannot be included in the `updg:before` section of an updategram.</span></span>  
  
-   <span data-ttu-id="e0066-271">Пространства имен в пределах фрагмента XML, вставленного в столбец типа `xml`, будут сохранены, и декларации пространства имен будут добавлены в верхний элемент вставленного фрагмента.</span><span class="sxs-lookup"><span data-stu-id="e0066-271">Namespaces that are in scope of the XML fragment inserted into the `xml` column will be preserved and their namespace declarations are added to the top element of the inserted fragment.</span></span>  
  
 <span data-ttu-id="e0066-272">Например, в следующем диаграмма обновления (SampleUpdateGram.xml) **\<Desc>** элемент обновляет столбец ProductDescription в таблице Production>productModel в [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] образце базы данных.</span><span class="sxs-lookup"><span data-stu-id="e0066-272">For example, in the following updategram (SampleUpdateGram.xml), the **\<Desc>** element updates the ProductDescription column in the Production>productModel table in the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="e0066-273">Результатом этого диаграмма обновления является то, что XML-содержимое столбца ProductDescription обновляется с помощью XML-содержимого **\<Desc>** элемента.</span><span class="sxs-lookup"><span data-stu-id="e0066-273">The result of this updategram is that the XML contents of the ProductDescription column are update with the XML contents of the **\<Desc>** element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync mapping-schema="SampleSchema.xml" >  
       <updg:before>  
<ProductModel ProductModelID="19">  
   <Name>Mountain-100</Name>  
</ProductModel>  
    </updg:before>  
    <updg:after>  
 <ProductModel>  
    <Name>Mountain-100</Name>  
    <Desc><?xml-stylesheet href="ProductDescription.xsl" type="text/xsl"?>  
        <p1:ProductDescription xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription"   
              xmlns:wm="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"   
              xmlns:wf="http://www.adventure-works.com/schemas/OtherFeatures"   
              xmlns:html="http://www.w3.org/1999/xhtml"   
              xmlns="">  
  <p1:Summary>  
     <html:p>Insert Example</html:p>  
  </p1:Summary>  
  <p1:Manufacturer>  
    <p1:Name>AdventureWorks</p1:Name>  
    <p1:Copyright>2002</p1:Copyright>  
    <p1:ProductURL>HTTP://www.Adventure-works.com</p1:ProductURL>  
  </p1:Manufacturer>  
  <p1:Features>These are the product highlights.   
    <wm:Warranty>  
       <wm:WarrantyPeriod>3 years</wm:WarrantyPeriod>  
       <wm:Description>parts and labor</wm:Description>  
    </wm:Warranty>  
    <wm:Maintenance>  
       <wm:NoOfYears>10 years</wm:NoOfYears>  
       <wm:Description>maintenance contract available through your dealer or any AdventureWorks retail store.</wm:Description>  
    </wm:Maintenance>  
    <wf:wheel>High performance wheels.</wf:wheel>  
    <wf:saddle>  
      <html:i>Anatomic design</html:i> and made from durable leather for a full-day of riding in comfort.</wf:saddle>  
    <wf:pedal>  
       <html:b>Top-of-the-line</html:b> clipless pedals with adjustable tension.</wf:pedal>  
    <wf:BikeFrame>Each frame is hand-crafted in our Bothell facility to the optimum diameter and wall-thickness required of a premium mountain frame. The heat-treated welded aluminum frame has a larger diameter tube that absorbs the bumps.</wf:BikeFrame>  
    <wf:crankset> Triple crankset; alumunim crank arm; flawless shifting. </wf:crankset>  
   </p1:Features>  
   <p1:Picture>  
      <p1:Angle>front</p1:Angle>  
      <p1:Size>small</p1:Size>  
      <p1:ProductPhotoID>118</p1:ProductPhotoID>  
   </p1:Picture>  
   <p1:Specifications> These are the product specifications.  
     <Material>Almuminum Alloy</Material>  
     <Color>Available in most colors</Color>  
     <ProductLine>Mountain bike</ProductLine>  
     <Style>Unisex</Style>  
     <RiderExperience>Advanced to Professional riders</RiderExperience>  
   </p1:Specifications>  
  </p1:ProductDescription>  
 </Desc>  
      </ProductModel>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e0066-274">Диаграмма обновления ссылается на следующую схему XSD с заметками (SampleSchema.xml).</span><span class="sxs-lookup"><span data-stu-id="e0066-274">The updategram refers to the following annotated XSD schema (SampleSchema.xml).</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
           xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">   
  <xsd:element name="ProductModel"  sql:relation="Production.ProductModel" >  
     <xsd:complexType>  
       <xsd:sequence>  
          <xsd:element name="Name" type="xsd:string"></xsd:element>  
          <xsd:element name="Desc" sql:field="CatalogDescription" sql:datatype="xml">  
           <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="ProductDescription">  
                 <xsd:complexType>  
                   <xsd:sequence>  
                     <xsd:element name="Summary" type="xsd:anyType">  
                     </xsd:element>  
                   </xsd:sequence>  
                 </xsd:complexType>  
              </xsd:element>  
            </xsd:sequence>  
           </xsd:complexType>  
          </xsd:element>   
       </xsd:sequence>  
       <xsd:attribute name="ProductModelID" sql:field="ProductModelID"/>  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e0066-275">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="e0066-275">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e0066-276">Скопируйте приведенную выше схему и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-276">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="e0066-277">Сохраните файл под именем XSD-SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="e0066-277">Save the file as XSD-SampleSchema.xml.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0066-278">Так как диаграмма обновления поддерживает сопоставление по умолчанию, не существует способа идентифицировать начало и конец типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="e0066-278">Because updategrams support default mapping, there is no way to identify the beginning and ending of the `xml` data type.</span></span> <span data-ttu-id="e0066-279">Это фактически означает, что при вставке или обновлении таблиц с помощью столбцов типа `xml` необходима схема сопоставления.</span><span class="sxs-lookup"><span data-stu-id="e0066-279">This effectively means that a mapping schema is required when inserting or updating tables with `xml` data type columns.</span></span> <span data-ttu-id="e0066-280">Если схема не предоставляется, SQLXML возвращает ошибку, указывающую, что один из столбцов пропущен в таблице.</span><span class="sxs-lookup"><span data-stu-id="e0066-280">When a schema is not provided, SQLXML returns an error indicating that one of the columns is missing from the table.</span></span>  
  
2.  <span data-ttu-id="e0066-281">Скопируйте приведенную выше диаграмму обновления и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e0066-281">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e0066-282">Сохраните файл под именем SampleUpdategram.xml в том же каталоге, где был сохранен файл SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="e0066-282">Save the file as SampleUpdategram.xml in the same folder used to save SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="e0066-283">Создайте тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs) и воспользуйтесь им для выполнения диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="e0066-283">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="e0066-284">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e0066-284">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0066-285">См. также:</span><span class="sxs-lookup"><span data-stu-id="e0066-285">See Also</span></span>  
 [<span data-ttu-id="e0066-286">Вопросы безопасности диаграмма обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e0066-286">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
