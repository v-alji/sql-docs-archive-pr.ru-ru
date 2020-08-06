---
title: Явное сопоставление элементов и атрибутов XSD с таблицами и столбцами (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- XPath queries [SQLXML], annotated XSD schemas in queries
- sql:field
- row mapping [SQLXML]
- attribute mapping [SQLXML], explicit mapping
- field annotation
- XSD schemas [SQLXML], mapping attributes and elements
- names [SQLXML]
- relation annotation
- table/view mapping [SQLXML], explicit mapping
- sql:relation
- mapping schema [SQLXML], explicit mapping
- annotated XSD schemas, mapping attributes and elements
- column mapping [SQLXML]
- element mapping [SQLXML], explicit mapping
- table mapping [SQLXML], explicit mapping
- element/attribute mapping [SQLXML]
ms.assetid: 7a5ebeb6-7322-4141-a307-ebcf95976146
author: rothja
ms.author: jroth
ms.openlocfilehash: f3400682b5f28835ca039912aab058691929a6c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656266"
---
# <a name="explicit-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-40"></a><span data-ttu-id="99592-102">Явное сопоставление элементов и атрибутов XSD с таблицами и столбцами (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="99592-102">Explicit Mapping of XSD Elements and Attributes to Tables and Columns (SQLXML 4.0)</span></span>
  <span data-ttu-id="99592-103">При использовании схемы XSD для представления реляционных баз данных в виде XML элементы и атрибуты схемы должны быть сопоставлены с таблицами и столбцами базы данных.</span><span class="sxs-lookup"><span data-stu-id="99592-103">When using an XSD schema to provide an XML view of the relational database , the elements and attributes of the schema must be mapped to tables and columns of the database.</span></span> <span data-ttu-id="99592-104">Строки таблицы или представления базы данных будут сопоставлены с элементами в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="99592-104">The rows in the database table/view will map to elements in the XML document.</span></span> <span data-ttu-id="99592-105">Значения столбцов базы данных сопоставляются с атрибутами и элементами.</span><span class="sxs-lookup"><span data-stu-id="99592-105">The column values in the database map to attributes or elements.</span></span>  
  
 <span data-ttu-id="99592-106">При запросах XPath к схеме XSD c заметками данные для элементов и атрибутов схемы берутся из таблиц и столбцов, которым они сопоставлены. </span><span class="sxs-lookup"><span data-stu-id="99592-106">When XPath queries are specified against the annotated XSD schema, the data for the elements and attributes in the schema is retrieved from the tables and columns to which they map.</span></span> <span data-ttu-id="99592-107">Для получения единичного значения из базы данных сопоставление, заданное схемой XSD, должно содержать спецификации и связей, и полей. </span><span class="sxs-lookup"><span data-stu-id="99592-107">To obtain a single value from the database, the mapping specified in the XSD schema must have both relation and field specification.</span></span> <span data-ttu-id="99592-108">Если имя элемента или атрибута не совпадает с именем таблицы, представления или столбца, которому оно сопоставлено, для задания сопоставления элемента или атрибута в XML-документе и таблицы (представления) или столбца базы данных используются заметки `sql:relation` и `sql:field`. </span><span class="sxs-lookup"><span data-stu-id="99592-108">If the name of an element/attribute is not the same name as the table/view or column name to which it maps, the `sql:relation` and `sql:field` annotations are used to specify the mapping between an element or attribute in an XML document and the table (view) or column in a database.</span></span>  
  
## <a name="sql-relation"></a><span data-ttu-id="99592-109">sql-relation</span><span class="sxs-lookup"><span data-stu-id="99592-109">sql-relation</span></span>  
 <span data-ttu-id="99592-110">Заметка `sql:relation` добавляется для сопоставления узла XML в схеме XSD и таблицы базы данных.</span><span class="sxs-lookup"><span data-stu-id="99592-110">The `sql:relation` annotation is added to map an XML node in the XSD schema to a database table.</span></span> <span data-ttu-id="99592-111">Имя таблицы (представления) задано как значение заметки `sql:relation`.</span><span class="sxs-lookup"><span data-stu-id="99592-111">The name of a table (view) is specified as the value of the `sql:relation` annotation.</span></span>  
  
 <span data-ttu-id="99592-112">Если для элемента задана заметка `sql:relation`, ее область действия охватывает все атрибуты и дочерние элементы, описанные в определении сложного типа этого элемента, сокращая, таким образом, усилия по написанию заметок.</span><span class="sxs-lookup"><span data-stu-id="99592-112">When `sql:relation` is specified on an element, the scope of this annotation applies to all attributes and child elements that are described in the complex type definition of that element, therefore providing a shortcut in writing annotations.</span></span>  
  
 <span data-ttu-id="99592-113">`sql:relation`Аннотация также полезна, если идентификаторы, допустимые в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , недопустимы в XML.</span><span class="sxs-lookup"><span data-stu-id="99592-113">The `sql:relation` annotation is also useful when identifiers that are valid in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are not valid in XML.</span></span> <span data-ttu-id="99592-114">Например, «Order Details» — допустимое имя таблицы в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но не в XML.</span><span class="sxs-lookup"><span data-stu-id="99592-114">For example, "Order Details" is a valid table name in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but not in XML.</span></span> <span data-ttu-id="99592-115">В этих случаях заметка `sql:relation` может использоваться для указания сопоставления, например следующим образом.</span><span class="sxs-lookup"><span data-stu-id="99592-115">In such cases, the `sql:relation` annotation can be used to specify the mapping, for example:</span></span>  
  
```  
<xsd:element name="OD" sql:relation="[Order Details]">  
```  
  
## <a name="sql-field"></a><span data-ttu-id="99592-116">sql-field</span><span class="sxs-lookup"><span data-stu-id="99592-116">sql-field</span></span>  
 <span data-ttu-id="99592-117">Заметка `sql-field` сопоставляет атрибут или элемент столбцу базы данных.</span><span class="sxs-lookup"><span data-stu-id="99592-117">The `sql-field` annotation maps an element or attribute to a database column.</span></span> <span data-ttu-id="99592-118">Заметка `sql:field` добавляется для сопоставления узла XML в схеме и столбца базы данных.</span><span class="sxs-lookup"><span data-stu-id="99592-118">The `sql:field` annotation is added to map an XML node in the schema to a database column.</span></span> <span data-ttu-id="99592-119">Нельзя задавать заметку `sql:field` на элементе с пустым содержимым.</span><span class="sxs-lookup"><span data-stu-id="99592-119">You cannot specify `sql:field` on an empty content element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="99592-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="99592-120">Examples</span></span>  
 <span data-ttu-id="99592-121">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="99592-121">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="99592-122">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="99592-122">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlrelation-and-sqlfield-annotations"></a><span data-ttu-id="99592-123">A.</span><span class="sxs-lookup"><span data-stu-id="99592-123">A.</span></span> <span data-ttu-id="99592-124">Задание заметок sql:relation и sql:field</span><span class="sxs-lookup"><span data-stu-id="99592-124">Specifying the sql:relation and sql:field annotations</span></span>  
 <span data-ttu-id="99592-125">В этом примере схема XSD состоит из **\<Contact>** элемента сложного типа с **\<FName>** **\<LName>** дочерними элементами и атрибутом **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="99592-125">In this example, the XSD schema consists of an **\<Contact>** element of complex type with **\<FName>** and **\<LName>** child elements and the **ContactID** attribute.</span></span>  
  
 <span data-ttu-id="99592-126">`sql:relation`Заметка сопоставляет **\<Contact>** элемент с таблицей Person. Contact в базе данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="99592-126">The `sql:relation` annotation maps the **\<Contact>** element to the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="99592-127">`sql:field`Заметка сопоставляет **\<FName>** элемент столбцу FirstName и **\<LName>** элементу со столбцом LastName.</span><span class="sxs-lookup"><span data-stu-id="99592-127">The `sql:field` annotation maps the **\<FName>** element to the FirstName column and the **\<LName>** element to the LastName column.</span></span>  
  
 <span data-ttu-id="99592-128">Для атрибута **ContactID** не задана Аннотация.</span><span class="sxs-lookup"><span data-stu-id="99592-128">No annotation is specified for the **ContactID** attribute.</span></span> <span data-ttu-id="99592-129">Поэтому атрибут по умолчанию сопоставляется со столбцом с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="99592-129">This results in a default mapping of the attribute to the column with the same name.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Contact" sql:relation="Person.Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"  
                     sql:field="FirstName"   
                     type="xsd:string" />   
        <xsd:element name="LName"    
                     sql:field="LastName"    
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ContactID"   
                       type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="99592-130">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="99592-130">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="99592-131">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="99592-131">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="99592-132">Сохраните файл под именем MySchema-annotated.xml.</span><span class="sxs-lookup"><span data-stu-id="99592-132">Save the file as MySchema-annotated.xml.</span></span>  
  
2.  <span data-ttu-id="99592-133">Скопируйте приведенный ниже шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="99592-133">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="99592-134">Сохраните файл под именем MySchema-annotatedT.xml в том же каталоге, где был сохранен файл MySchema-annotated.xml.</span><span class="sxs-lookup"><span data-stu-id="99592-134">Save the file as MySchema-annotatedT.xml in the same directory where you saved MySchema-annotated.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="MySchema-annotated.xml">  
        /Contact  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="99592-135">Путь к каталогу схемы сопоставления (файл MySchema-annotated.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="99592-135">The directory path specified for the mapping schema (MySchema-annotated.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="99592-136">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="99592-136">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchema-annotated.xml"  
    ```  
  
3.  <span data-ttu-id="99592-137">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="99592-137">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="99592-138">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="99592-138">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="99592-139">Частичный результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="99592-139">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
 <Contact ContactID="1">   
    <FName>Gustavo</FName>   
    <LName>Achong</LName>   
 </Contact>   
  .....  
</ROOT>  
```  
  
  
