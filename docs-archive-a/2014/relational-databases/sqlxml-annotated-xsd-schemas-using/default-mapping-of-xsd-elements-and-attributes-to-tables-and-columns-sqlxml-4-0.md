---
title: Сопоставление элементов и атрибутов XSD с таблицами и столбцами по умолчанию (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XSD schemas [SQLXML], mapping attributes and elements
- mapping schema [SQLXML], default mapping
- element mapping [SQLXML], default mapping
- element mapping [SQLXML]
- table mapping [SQLXML]
- annotated XSD schemas, mapping attributes and elements
- table/view mapping [SQLXML]
- column mapping [SQLXML]
- attribute mapping [SQLXML], default mapping
- default schema mapping
- table mapping [SQLXML], default mapping
- testing XPath query against schema
- xml data type [SQL Server], SQLXML
- table/view mapping [SQLXML], default mapping
- element/attribute mapping [SQLXML]
ms.assetid: 9a18e92a-6cfb-4a14-993a-663a95aabb63
author: rothja
ms.author: jroth
ms.openlocfilehash: 0bccec2413e8a0a6e13283a0f3e5f63ab61e934b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664119"
---
# <a name="default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-40"></a><span data-ttu-id="fc02d-102">Сопоставление элементов и атрибутов XSD с таблицами и столбцами по умолчанию (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="fc02d-102">Default Mapping of XSD Elements and Attributes to Tables and Columns (SQLXML 4.0)</span></span>
  <span data-ttu-id="fc02d-103">По умолчанию элемент сложного типа в аннотированной схеме XSD сопоставляется с одноименной таблицей (представлением) в указанной базе данных, а элемент или атрибут простого типа — с одноименным столбцом этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="fc02d-103">By default, an element of complex type in an XSD annotated schema maps to the table (view) with the same name in the specified database, and an element or attribute of simple type maps to the column with the same name in the table.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="fc02d-104">Примеры</span><span class="sxs-lookup"><span data-stu-id="fc02d-104">Examples</span></span>  
 <span data-ttu-id="fc02d-105">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="fc02d-105">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="fc02d-106">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="fc02d-106">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-default-mapping"></a><span data-ttu-id="fc02d-107">A.</span><span class="sxs-lookup"><span data-stu-id="fc02d-107">A.</span></span> <span data-ttu-id="fc02d-108">Указание сопоставления по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fc02d-108">Specifying default mapping</span></span>  
 <span data-ttu-id="fc02d-109">В этом примере в схеме XSD не задано никаких заметок.</span><span class="sxs-lookup"><span data-stu-id="fc02d-109">In this example, no annotations are specified in the XSD schema.</span></span> <span data-ttu-id="fc02d-110">**\<Person.Contact>** Элемент имеет сложный тип и, следовательно, по умолчанию сопоставляется с таблицей Person. Contact в базе данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="fc02d-110">The **\<Person.Contact>** element is of complex type and, therefore, maps by default to the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="fc02d-111">Все атрибуты (ContactID, FirstName, LastName) **\<Person.Contact>** элемента имеют простой тип и сопоставляются по умолчанию со столбцами с теми же именами в таблице Person. Contact.</span><span class="sxs-lookup"><span data-stu-id="fc02d-111">All the attributes (ContactID, FirstName, LastName) of the **\<Person.Contact>** element are of simple type and map by default to columns with the same names in the Person.Contact table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID"  type="xsd:string" />   
       <xsd:attribute name="FirstName"   type="xsd:string" />   
       <xsd:attribute name="LastName"    type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="fc02d-112">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="fc02d-112">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="fc02d-113">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="fc02d-113">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="fc02d-114">Сохраните файл под именем MySchema.xml.</span><span class="sxs-lookup"><span data-stu-id="fc02d-114">Save the file as MySchema.xml.</span></span>  
  
2.  <span data-ttu-id="fc02d-115">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="fc02d-115">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="fc02d-116">Сохраните файл под именем MySchemaT.xml в том же каталоге, где был сохранен файл MySchema.xml.</span><span class="sxs-lookup"><span data-stu-id="fc02d-116">Save the file as MySchemaT.xml in the same directory where you saved MySchema.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchema.xml">  
            /Person.Contact  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="fc02d-117">Путь к каталогу для схемы сопоставления (MySchema.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="fc02d-117">The directory path specified for the mapping schema (MySchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="fc02d-118">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="fc02d-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchema.xml"  
    ```  
  
3.  <span data-ttu-id="fc02d-119">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="fc02d-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="fc02d-120">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="fc02d-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="fc02d-121">Частичный результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="fc02d-121">Here is the partial result set:</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8" ?>  
<ROOT>  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong"/>  
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel"/>  
   ...  
</ROOT>  
```  
  
### <a name="b-mapping-an-xml-element-to-a-database-column"></a><span data-ttu-id="fc02d-122">Б.</span><span class="sxs-lookup"><span data-stu-id="fc02d-122">B.</span></span> <span data-ttu-id="fc02d-123">Сопоставление XML-элемента со столбцом базы данных</span><span class="sxs-lookup"><span data-stu-id="fc02d-123">Mapping an XML element to a database column</span></span>  
 <span data-ttu-id="fc02d-124">Так как не использовано ни одной заметки, в этом примере также имеет место сопоставление по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc02d-124">In this example, default mapping also takes place because no annotations are used.</span></span> <span data-ttu-id="fc02d-125">**\<Person.Contact>** Элемент имеет сложный тип и сопоставляется с таблицей с тем же именем в базе данных.</span><span class="sxs-lookup"><span data-stu-id="fc02d-125">The **\<Person.Contact>** element is of complex type and maps to the table with the same name in the database.</span></span> <span data-ttu-id="fc02d-126">Элементы **\<FirstName>** и **\<LastName>** атрибут **EmployeeID** имеют простой тип и, следовательно, сопоставляются со столбцами с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="fc02d-126">The elements **\<FirstName>** and **\<LastName>** and the **EmployeeID** attribute are of simple type and, therefore, map to the columns with the same names.</span></span> <span data-ttu-id="fc02d-127">Единственная разница между этим и предыдущим примером заключается в том, что для сопоставления полей FirstName и LastName используются элементы.</span><span class="sxs-lookup"><span data-stu-id="fc02d-127">The only difference between this and the previous example are that elements are used for mapping the FirstName and LastName fields.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="FirstName" type="xsd:string" />   
        <xsd:element name="LastName" type="xsd:string" />   
      </xsd:sequence>  
      <xsd:attribute name="ContactID" type="xsd:integer" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="fc02d-128">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="fc02d-128">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="fc02d-129">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="fc02d-129">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="fc02d-130">Сохраните файл под именем MySchemaElements.xml.</span><span class="sxs-lookup"><span data-stu-id="fc02d-130">Save the file as MySchemaElements.xml.</span></span>  
  
2.  <span data-ttu-id="fc02d-131">Создайте следующий шаблон (MySchemaElementsT.xml) и сохраните его в том же каталоге, что и на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="fc02d-131">Create the following template (MySchemaElementsT.xml), and save it in the same directory used in the previous step.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchemaElements.xml">  
            /Person.Contact  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="fc02d-132">Путь к каталогу для схемы сопоставления задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="fc02d-132">The directory path specified for the mapping schema is relative to the directory where the template is saved.</span></span> <span data-ttu-id="fc02d-133">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="fc02d-133">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchemaElements.xml"  
    ```  
  
3.  <span data-ttu-id="fc02d-134">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="fc02d-134">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="fc02d-135">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="fc02d-135">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="fc02d-136">Частичный результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="fc02d-136">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1">  
    <FirstName>Gustavo</FirstName>  
    <LastName>Achong</LastName>  
  </Person.Contact>  
   ...  
</ROOT>  
```  
  
### <a name="c-mapping-an-xml-element-to-an-xml-data-type-column"></a><span data-ttu-id="fc02d-137">В.</span><span class="sxs-lookup"><span data-stu-id="fc02d-137">C.</span></span> <span data-ttu-id="fc02d-138">Сопоставление XML-элемента со столбцом типа данных XML</span><span class="sxs-lookup"><span data-stu-id="fc02d-138">Mapping an XML element to an XML data type column</span></span>  
 <span data-ttu-id="fc02d-139">Так как не использовано ни одной заметки, в этом примере также имеет место сопоставление по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc02d-139">In this example, default mapping also takes place because no annotations are used.</span></span> <span data-ttu-id="fc02d-140">**\<Production.ProductModel>** Элемент имеет сложный тип и сопоставляется с таблицей с тем же именем в базе данных.</span><span class="sxs-lookup"><span data-stu-id="fc02d-140">The **\<Production.ProductModel>** element is of complex type and maps to the table with the same name in the database.</span></span> <span data-ttu-id="fc02d-141">Атрибут **ProductModelID** имеет простой тип и, следовательно, сопоставляется со столбцами с теми же именами.</span><span class="sxs-lookup"><span data-stu-id="fc02d-141">The **ProductModelID** attribute is of simple type and, therefore, map to the columns with the same names.</span></span> <span data-ttu-id="fc02d-142">Единственное различие между этим и предыдущим примерами состоит в том, что **\<Instructions>** элемент сопоставляется со столбцом, использующим `xml` тип данных с помощью `xsd:anyType` типа.</span><span class="sxs-lookup"><span data-stu-id="fc02d-142">The only difference between this and the previous examples is that the **\<Instructions>** element is mapping to a column that uses the `xml` data type by using the `xsd:anyType` type.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Production.ProductModel">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Instructions" type="xsd:anyType" />   
      </xsd:sequence>  
      <xsd:attribute name="ProductModelID" type="xsd:integer" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="fc02d-143">В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] появился тип данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="fc02d-143">The `xml` data type was introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="fc02d-144">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="fc02d-144">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="fc02d-145">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="fc02d-145">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="fc02d-146">Сохраните файл под именем MySchemaXmlAnyElements.xml.</span><span class="sxs-lookup"><span data-stu-id="fc02d-146">Save the file as MySchemaXmlAnyElements.xml.</span></span>  
  
2.  <span data-ttu-id="fc02d-147">Создайте следующий шаблон (MySchemaXmlAnyElementsT.xml) и сохраните его в том же каталоге, что и на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="fc02d-147">Create the following template (MySchemaXmlAnyElementsT.xml), and save it in the same directory used in the previous step.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchemaXmlAnyElements.xml">  
            /Production.ProductModel[@ProductModelID=7]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="fc02d-148">Путь к каталогу для схемы сопоставления задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="fc02d-148">The directory path specified for the mapping schema is relative to the directory where the template is saved.</span></span> <span data-ttu-id="fc02d-149">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="fc02d-149">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchemaXmlAnyElements.xml"  
    ```  
  
3.  <span data-ttu-id="fc02d-150">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="fc02d-150">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="fc02d-151">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="fc02d-151">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="fc02d-152">Частичный результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="fc02d-152">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductModel ProductModelID="7">  
    <Instructions>  
      <root xmlns="http:  
//schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstru  
ctions">  
...  
      </root>  
    <Instructions>  
  </Production.ProductModel>  
</ROOT>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc02d-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc02d-153">See Also</span></span>  
 <span data-ttu-id="fc02d-154">[Рекомендации по безопасности схемы с заметками &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="fc02d-154">[Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="fc02d-155">[Данные XML (SQL Server)](../xml/xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fc02d-155">[XML Data &#40;SQL Server&#41;](../xml/xml-data-sql-server.md) </span></span>  
 [<span data-ttu-id="fc02d-156">Поддержка типов данных xml в SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="fc02d-156">xml Data Type Support in SQLXML 4.0</span></span>](../sqlxml/xml-data-type-support-in-sqlxml-4-0.md)  
  
  
