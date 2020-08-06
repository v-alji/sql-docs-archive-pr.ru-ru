---
title: 'Скрытие элементов и атрибутов с помощью SQL: Hide | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- hiding elements
- element mapping [SQLXML], hiding attributes and elements
- hide annotation
- sql:hide
- table/view mapping [SQLXML], hiding attributes and elements
- table mapping [SQLXML], hiding attributes and elements
- hiding attributes
- annotated XSD schemas, hiding attributes and elements
- attribute mapping [SQLXML], hiding attributes and elements
- column mapping [SQLXML]
- element hiding [SQLXML]
- XSD schemas [SQLXML], hiding attributes and elements
- attribute hiding [SQLXML]
ms.assetid: 0978301b-f068-46b6-82b9-dc555161f52e
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a3beb48be1d9809b170faeafa964ba45156ac28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750568"
---
# <a name="hiding-elements-and-attributes-by-using-sqlhide"></a><span data-ttu-id="7b1b9-102">Скрытие элементов и атрибутов при помощи sql:hide</span><span class="sxs-lookup"><span data-stu-id="7b1b9-102">Hiding Elements and Attributes by Using sql:hide</span></span>
  <span data-ttu-id="7b1b9-103">При выполнении запроса XPath к схеме XSD результирующий XML-документ содержит элементы и атрибуты, указанные в схеме.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-103">When an XPath query is executed against an XSD schema, the resulting XML document has elements and attributes that are specified in the schema.</span></span> <span data-ttu-id="7b1b9-104">Заметка `sql:hide` позволяет указать, что некоторые элементы и атрибуты скрыты в схеме.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-104">You can specify that some elements and attributes be hidden in the schema by using the `sql:hide` annotation.</span></span> <span data-ttu-id="7b1b9-105">Это может оказаться полезным в тех случаях, когда критерий выбора запроса требует определенных элементов или атрибутов в схеме, но они не должны возвращаться в формируемом XML-документе.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-105">This is useful when the selection criteria of the query require particular elements or attributes in the schema, but you do not want them returned in the XML document that is generated.</span></span>  
  
 <span data-ttu-id="7b1b9-106">Заметка `sql:hide` имеет логическое значение (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="7b1b9-106">The `sql:hide` annotation takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="7b1b9-107">Допустимые значения: 0, 1, true и false.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-107">The acceptable values are 0, 1, true, and false.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7b1b9-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="7b1b9-108">Examples</span></span>  
 <span data-ttu-id="7b1b9-109">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-109">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="7b1b9-110">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="7b1b9-110">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlhide-on-an-attribute"></a><span data-ttu-id="7b1b9-111">A.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-111">A.</span></span> <span data-ttu-id="7b1b9-112">Указание sql:hide для атрибута</span><span class="sxs-lookup"><span data-stu-id="7b1b9-112">Specifying sql:hide on an attribute</span></span>  
 <span data-ttu-id="7b1b9-113">Схема XSD в этом примере состоит из **\<Person.Contact>** элемента с атрибутами **ContactID**, **FirstName**и **LastName** .</span><span class="sxs-lookup"><span data-stu-id="7b1b9-113">The XSD schema in this example consists of an **\<Person.Contact>** element with **ContactID**, **FirstName**, and **LastName** attributes.</span></span>  
  
 <span data-ttu-id="7b1b9-114">**\<Person.Contact>** Элемент имеет сложный тип и, следовательно, сопоставляется с таблицей с тем же именем (сопоставление по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7b1b9-114">The **\<Person.Contact>** element is of complex type and, therefore, maps to the table of the same name (default mapping).</span></span> <span data-ttu-id="7b1b9-115">Все атрибуты **\<Person.Contact>** элемента имеют простой тип и сопоставляются со столбцами с теми же именами в контакттабле в базе данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-115">All the attributes of **\<Person.Contact>** element are of simple type and map to columns with the same names in the Person.Contacttable in the AdventureWorks database.</span></span> <span data-ttu-id="7b1b9-116">В схеме `sql:hide` заметка задается в атрибуте **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="7b1b9-116">In the schema, the `sql:hide` annotation is specified on the **ContactID** attribute.</span></span> <span data-ttu-id="7b1b9-117">Если для этой схемы задан запрос XPath, то объект **ContactID** не возвращается в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-117">When an XPath query is specified against this schema, the **ContactID** is not returned in the XML document.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID"  sql:hide="true" />   
       <xsd:attribute name="FirstName"   type="xsd:string" />   
       <xsd:attribute name="LastName"    type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="7b1b9-118">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="7b1b9-118">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="7b1b9-119">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-119">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="7b1b9-120">Сохраните файл под именем Hide.xml.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-120">Save the file as Hide.xml.</span></span>  
  
2.  <span data-ttu-id="7b1b9-121">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-121">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="7b1b9-122">Сохраните файл под именем HideT.xml в том же каталоге, где был сохранен файл HideT.xml.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-122">Save the file as HideT.xml in the same directory where you saved Hide.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="Hide.xml">  
            /Person.Contact[@ContactID="1"]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="7b1b9-123">Путь к каталогу схемы сопоставления (файл Hide.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-123">The directory path specified for the mapping schema (Hide.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="7b1b9-124">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="7b1b9-124">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\Hide.xml"  
    ```  
  
3.  <span data-ttu-id="7b1b9-125">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-125">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="7b1b9-126">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7b1b9-126">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="7b1b9-127">Результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="7b1b9-127">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <Person.Contact FirstName="Gustavo" LastName="Achong" />   
</ROOT>  
```  
  
 <span data-ttu-id="7b1b9-128">Если для элемента была указана заметка `sql:hide`, то элемент и его атрибуты или дочерние элементы не будут отображены в созданном XML-документе.</span><span class="sxs-lookup"><span data-stu-id="7b1b9-128">When `sql:hide` is specified on an element, the element and its attributes or child elements do not appear in the XML document that is generated.</span></span> <span data-ttu-id="7b1b9-129">Ниже приведена другая схема XSD, в которой `sql:hide` задается **\<OD>** элемент:</span><span class="sxs-lookup"><span data-stu-id="7b1b9-129">Here is another XSD schema in which `sql:hide` is specified on the **\<OD>** element:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:annotation>  
    <xsd:documentation>  
      Sales.Customer-Sales.SalesOrderHeader-Sales.SalesOrderDetail Schema  
      Copyright 2004 Microsoft. All rights reserved.  
    </xsd:documentation>  
    <xsd:appinfo>  
      <sql:relationship name="CustomerOrder"  
         parent="Sales.Customer"  
                  parent-key="CustomerID"  
                  child-key="CustomerID"  
                  child="Sales.SalesOrderHeader" />  
       <sql:relationship name="OrderOrderDetails"  
                  parent="Sales.SalesOrderHeader"  
                  parent-key="SalesOrderID"  
                  child-key="SalesOrderID"  
                  child="Sales.SalesOrderDetail"/>  
    </xsd:appinfo>  
  </xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Sales.Customer">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
                     maxOccurs="unbounded"   
                     sql:relationship="CustomerOrder">  
          <xsd:complexType>  
            <xsd:sequence>  
               <xsd:element name="OD" sql:relation="Sales.SalesOrderDetail"                                       maxOccurs="unbounded"                                       sql:relationship="OrderOrderDetails"                                       sql:hide="1">  
                  <xsd:complexType>  
                    <xsd:attribute name="SalesOrderID" type="xsd:string"/>  
                    <xsd:attribute name="ProductID" type="xsd:string"/>  
                  </xsd:complexType>  
               </xsd:element>  
            </xsd:sequence>  
          <xsd:attribute name="CustomerID" type="xsd:string"/>  
          <xsd:attribute name="OID" sql:field="SalesOrderID"   
                                    type="xsd:string"/>  
          <xsd:attribute name="OrderDate" type="xsd:date"/>   
        </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
    <xsd:attribute name="CID" sql:field="CustomerID"   
                                type="xsd:string"/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="7b1b9-130">Если для этой схемы указан запрос XPath (например `/Customers[@CID="1"]` ,), создаваемый XML-документ не включает **\<OD>** элемент и его дочерние элементы, как показано в этом частичном результате:</span><span class="sxs-lookup"><span data-stu-id="7b1b9-130">When an XPath query (for example `/Customers[@CID="1"]`) is specified against this schema, the XML document that is generated does not include the **\<OD>** element and its children, as shown in this partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customers CID="1">  
    <Order CustomerID="1" OID="43860" OrderDate="2001-08-01" />   
    <Order CustomerID="1" OID="44501" OrderDate="2001-11-01" />   
    <Order CustomerID="1" OID="45283" OrderDate="2002-02-01" />   
    <Order CustomerID="1" OID="46042" OrderDate="2002-05-01" />   
  </Customers>  
</ROOT>  
```  
  
  
