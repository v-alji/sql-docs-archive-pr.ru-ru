---
title: 'Создание допустимых атрибутов типа ID, IDREF и IDREFS с помощью SQL: prefix (SQLXML 4,0) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREFS relationships [SQLXML]
- annotated XSD schemas, ID type attribute
- IDREF type attribute [SQLXML]
- annotated XSD schemas, IDREFS type attribute
- ID type attribute [SQLXML]
- sql:prefix
- prefix annotation
- IDREF relationships [SQLXML]
- IDREFS type attribute [SQLXML]
- annotated XSD schemas, IDREF type attribute
- ID relationships [SQLXML]
ms.assetid: 1c7f77d3-81f3-4820-bb63-c4aaa4ea9aa1
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9e63bebd0cebbfeed75ea5cbe2ea62683234fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664121"
---
# <a name="creating-valid-id-idref-and-idrefs-type-attributes-using-sqlprefix-sqlxml-40"></a><span data-ttu-id="e9e1e-102">Создание допустимых атрибутов типа ID, IDREF и IDREFS с использованием sql:prefix (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e9e1e-102">Creating Valid ID, IDREF, and IDREFS Type Attributes Using sql:prefix (SQLXML 4.0)</span></span>
  <span data-ttu-id="e9e1e-103">Атрибут может быть задан как атрибут типа ID.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-103">An attribute can be specified to be an ID type attribute.</span></span> <span data-ttu-id="e9e1e-104">Атрибуты, заданные как IDREF или IDREFS, могут затем использоваться для ссылки на атрибуты типа ID, создавая ссылки между документами.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-104">Attributes specified as IDREF or IDREFS can then be used to refer to the ID type attributes, enabling links between documents.</span></span>  
  
 <span data-ttu-id="e9e1e-105">ID, IDREF и IDREFS соответствуют связям PK/FK («первичный ключ-внешний ключ») в базе данных, не считая некоторых отличий.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-105">ID, IDREF, and IDREFS correspond to PK/FK (primary key/foreign key) relationships in the database, with few differences.</span></span> <span data-ttu-id="e9e1e-106">В XML-документе значения атрибутов типа ID должны быть различными.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-106">In an XML document, the values of ID type attributes must be distinct.</span></span> <span data-ttu-id="e9e1e-107">Если атрибуты **CustomerID** и **OrderID** указаны в XML-документе как тип идентификатора, эти значения должны быть разными.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-107">If **CustomerID** and **OrderID** attributes are specified as ID type in an XML document, these values must be distinct.</span></span> <span data-ttu-id="e9e1e-108">Но в базе данных столбцы CustomerID и OrderID могут иметь одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-108">However, in a database, CustomerID and OrderID columns can have the same values.</span></span> <span data-ttu-id="e9e1e-109">(Например, в базе данных допустимы значения CustomerID = 1 и OrderID = 1.)</span><span class="sxs-lookup"><span data-stu-id="e9e1e-109">(For example, CustomerID = 1 and OrderID = 1 are valid in the database).</span></span>  
  
 <span data-ttu-id="e9e1e-110">Чтобы атрибуты ID, IDREF и IDREFS были допустимыми, должны выполняться следующие условия.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-110">For the ID, IDREF, and IDREFS attributes to be valid:</span></span>  
  
-   <span data-ttu-id="e9e1e-111">Значение атрибута ID должно быть уникальным в пределах XML-документа.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-111">The value of ID must be unique within the XML document.</span></span>  
  
-   <span data-ttu-id="e9e1e-112">Для каждого атрибута IDREF и IDREFS в XML-документе должны присутствовать значения ID, на которые ссылается этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-112">For every IDREF and IDREFS, the referenced ID values must be in the XML document.</span></span>  
  
-   <span data-ttu-id="e9e1e-113">Значение атрибутов ID, IDREF и IDREFS должно быть именованным токеном.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-113">The value of an ID, IDREF, and IDREFS must be a named token.</span></span> <span data-ttu-id="e9e1e-114">(Например, целочисленное значение 101 не может быть значением ID.)</span><span class="sxs-lookup"><span data-stu-id="e9e1e-114">(For example, the integer value 101 cannot be an ID value.)</span></span>  
  
-   <span data-ttu-id="e9e1e-115">Атрибуты типа ID, IDREF и IDREFS не могут быть сопоставлены столбцам типа `text`, `ntext`, `image` или любого другого двоичного типа (например, `timestamp`).</span><span class="sxs-lookup"><span data-stu-id="e9e1e-115">The attributes of ID, IDREF, and IDREFS type cannot be mapped to columns of the type `text`, `ntext`, or `image` or any other binary data type (for example, `timestamp`).</span></span>  
  
 <span data-ttu-id="e9e1e-116">Если XML-документ содержит несколько значений ID, необходимо использовать заметку `sql:prefix` для обеспечения уникальности значений.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-116">If an XML document contains multiple IDs, use the `sql:prefix` annotation to ensure that the values are unique.</span></span>  
  
 <span data-ttu-id="e9e1e-117">Обратите внимание, что заметку `sql:prefix` невозможно использовать с атрибутом неизменности XSD.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-117">Note that `sql:prefix` annotation cannot be used with XSD fixed attribute.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e9e1e-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="e9e1e-118">Examples</span></span>  
 <span data-ttu-id="e9e1e-119">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-119">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="e9e1e-120">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e9e1e-120">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-id-and-idrefs-types"></a><span data-ttu-id="e9e1e-121">A.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-121">A.</span></span> <span data-ttu-id="e9e1e-122">Задание типов ID и IDREFS</span><span class="sxs-lookup"><span data-stu-id="e9e1e-122">Specifying ID and IDREFS types</span></span>  
 <span data-ttu-id="e9e1e-123">В следующей схеме **\<Customer>** элемент состоит из **\<Order>** дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-123">In the following schema, the **\<Customer>** element consists of the **\<Order>** child element.</span></span> <span data-ttu-id="e9e1e-124">**\<Order>** Элемент также имеет дочерний элемент — **\<OrderDetail>** элемент.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-124">The **\<Order>** element also has a child element, the **\<OrderDetail>** element.</span></span>  
  
 <span data-ttu-id="e9e1e-125">Атрибут **ордеридлист** атрибута **\<Customer>** является атрибутом типа IDREFS, который ссылается на атрибут **OrderID** **\<Order>** элемента.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-125">The **OrderIDList** attribute of **\<Customer>** is an IDREFS type attribute that refers to the **OrderID** attribute of the **\<Order>** element.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
                 parent="Sales.Customer"  
                 parent-key="CustomerID"  
                 child="Sales.SalesOrderHeader"  
                 child-key="CustomerID" />  
    <sql:relationship name="OrderOrderDetail"  
                 parent="Sales.SalesOrderHeader"  
                 parent-key="SalesOrderID"  
                 child="Sales.SalesOrderDetail"  
                 child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"    
               sql:relationship="CustOrders" maxOccurs="unbounded" >  
          <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OrderDetail"   
                             sql:relation="Sales.SalesOrderDetail"   
                   sql:relationship="OrderOrderDetail"   
                   maxOccurs="unbounded" >  
                  <xsd:complexType>  
                   <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                   <xsd:attribute name="ProductID" type="xsd:string" />  
                   <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  </xsd:complexType>  
               </xsd:element>  
             </xsd:sequence>  
             <xsd:attribute name="SalesOrderID"   
                            type="xsd:ID" sql:prefix="ord-" />  
             <xsd:attribute name="OrderDate" type="xsd:date" />  
             <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
    <xsd:attribute name="CustomerID" type="xsd:string" />  
    <xsd:attribute name="OrderIDList" type="xsd:IDREFS"   
                   sql:relation="Sales.SalesOrderHeader" sql:field="SalesOrderID"  
                   sql:relationship="CustOrders" sql:prefix="ord-">  
    </xsd:attribute>  
  </xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e9e1e-126">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="e9e1e-126">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e9e1e-127">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-127">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="e9e1e-128">Сохраните файл под именем sqlPrefix.xml.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-128">Save the file as sqlPrefix.xml.</span></span>  
  
2.  <span data-ttu-id="e9e1e-129">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-129">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="e9e1e-130">Сохраните файл под именем sqlPrefixT.xml в том же каталоге, в котором был сохранен файл sqlPrefix.xml.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-130">Save the file as sqlPrefixT.xml in the same directory where you saved sqlPrefix.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="sqlPrefix.xml">  
        /Customer[@CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e9e1e-131">Путь к каталогу для схемы сопоставления (sqlPrefix.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-131">The directory path specified for the mapping schema (sqlPrefix.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e9e1e-132">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="e9e1e-132">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\sqlPrefix.xml"  
    ```  
  
3.  <span data-ttu-id="e9e1e-133">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="e9e1e-133">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e9e1e-134">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e9e1e-134">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e9e1e-135">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="e9e1e-135">This is the partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" OrderIDList="ord-43860 ord-44501 ord-45283 ord-46042">  
    <Order SalesOrderID="ord-43860" OrderDate="2001-08-01" CustomerID="1">  
      <OrderDetail SalesOrderID="43860" ProductID="729" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="732" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="738" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="753" OrderQty="2" />   
      ...  
    </Order>  
    ...  
 </Customer>  
</ROOT>  
```  
  
  
