---
title: 'Создание элементов констант с помощью SQL: является константой (SQLXML 4,0) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- sql:is-constant
- XSD schemas [SQLXML], constant elements
- element mapping [SQLXML], constant elements
- is-constant annotation
- constant elements [SQLXML]
- annotated XSD schemas, constant elements
ms.assetid: 940eea1b-54f5-445f-b844-c894d9f3941b
author: rothja
ms.author: jroth
ms.openlocfilehash: 8deedd8547d6bc3f0154eedb889ad908750f071a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733726"
---
# <a name="creating-constant-elements-using-sqlis-constant-sqlxml-40"></a><span data-ttu-id="e7e9e-102">Создание постоянных элементов при помощи sql:is-constant (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e7e9e-102">Creating Constant Elements Using sql:is-constant (SQLXML 4.0)</span></span>
  <span data-ttu-id="e7e9e-103">Чтобы задать постоянный элемент, т. е. элемент в схеме XSD, не сопоставленный ни с одной таблицей или столбцом базы данных, можно использовать `sql:is-constant` заметку.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-103">To specify a constant element-that is, an element in the XSD schema that does not map to any database table or column-you can use the `sql:is-constant` annotation.</span></span> <span data-ttu-id="e7e9e-104">Эта заметка имеет логическое значение (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="e7e9e-104">This annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="e7e9e-105">Допустимые значения: 0, 1, true и false.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-105">The acceptable values are 0, 1, true, and false.</span></span> <span data-ttu-id="e7e9e-106">Заметка `sql:is-constant` может быть указана для элемента, не имеющего атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-106">The `sql:is-constant` annotation can be specified on an element that does not have any attributes.</span></span> <span data-ttu-id="e7e9e-107">Если она задана для элемента, имеющего значение true (или 1), то этот элемент не будет сопоставлен с базой данных, но будет по-прежнему отображаться в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-107">If it is specified on an element with the value true (or 1), that element is not mapped to the database but still appears in the XML document.</span></span>  
  
 <span data-ttu-id="e7e9e-108">Заметка `sql:is-constant` может использоваться для следующих задач.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-108">The `sql:is-constant` annotation can be used for:</span></span>  
  
-   <span data-ttu-id="e7e9e-109">Добавление элемента верхнего уровня в XML-документ.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-109">Adding a top-level element to the XML document.</span></span> <span data-ttu-id="e7e9e-110">XML-документ должен содержать единственный элемент верхнего уровня (корневой элемент).</span><span class="sxs-lookup"><span data-stu-id="e7e9e-110">XML requires a single top-level element (root element) for the document.</span></span>  
  
-   <span data-ttu-id="e7e9e-111">Создание элементов контейнера, таких как **\<Orders>** элемент, который упаковывает все заказы.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-111">Creating container elements, such as an **\<Orders>** element that wraps all orders.</span></span>  
  
 <span data-ttu-id="e7e9e-112">`sql:is-constant`Заметку можно добавить к **\<complexType>** элементу.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-112">The `sql:is-constant` annotation can be added to a **\<complexType>** element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e7e9e-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="e7e9e-113">Examples</span></span>  
 <span data-ttu-id="e7e9e-114">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-114">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="e7e9e-115">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e7e9e-115">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlis-constant-to-add-a-container-element"></a><span data-ttu-id="e7e9e-116">A.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-116">A.</span></span> <span data-ttu-id="e7e9e-117">Указание sql:is-constant для добавления элемента контейнера</span><span class="sxs-lookup"><span data-stu-id="e7e9e-117">Specifying sql:is-constant to add a container element</span></span>  
 <span data-ttu-id="e7e9e-118">В этой схеме XSD с заметками **\<CustomerOrders>** определяется как постоянный элемент, указывая `sql:is-constant` атрибут со значением 1.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-118">In this annotated XSD schema, **\<CustomerOrders>** is defined as a constant element by specifying the `sql:is-constant` attribute with a value of 1.</span></span> <span data-ttu-id="e7e9e-119">Таким образом, **\<CustomerOrders>** не сопоставляется ни с одной таблицей или столбцом базы данных.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-119">Therefore, **\<CustomerOrders>** is not mapped to any database table or column.</span></span> <span data-ttu-id="e7e9e-120">Этот постоянный элемент состоит из **\<Order>** дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-120">This constant element consists of the **\<Order>** child elements.</span></span>  
  
 <span data-ttu-id="e7e9e-121">Хотя не **\<CustomerOrders>** сопоставляется ни с одной таблицей или столбцом базы данных, он по-прежнему отображается в результирующем XML как элемент контейнера, содержащий **\<Order>** дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-121">Although **\<CustomerOrders>** does not map to any database table or column, it still appears in the resulting XML as a container element containing the **\<Order>** child elements.</span></span>  
  
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
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="CustomerOrders" sql:is-constant="1" >  
          <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"  
                           sql:relationship="CustOrders"   
                           maxOccurs="unbounded" >  
                <xsd:complexType>  
                   <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                   <xsd:attribute name="OrderDate" type="xsd:date" />  
                   <xsd:attribute name="CustomerID" type="xsd:string" />  
                </xsd:complexType>  
              </xsd:element>  
            </xsd:sequence>  
           </xsd:complexType>  
          </xsd:element>  
         </xsd:sequence>  
          <xsd:attribute name="CustomerID" type="xsd:string" />  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e7e9e-122">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="e7e9e-122">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e7e9e-123">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-123">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="e7e9e-124">Сохраните файл под именем isConstant.xml.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-124">Save the file as isConstant.xml.</span></span>  
  
2.  <span data-ttu-id="e7e9e-125">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-125">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="e7e9e-126">Сохраните файл под именем isConstantT.xml в том же каталоге, где был сохранен файл isConstant.xml.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-126">Save the file as isConstantT.xml in the same directory where you saved isConstant.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="isConstant.xml">  
            Customer[@CustomerID=1]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e7e9e-127">Путь к каталогу схемы сопоставления (файл isConstant.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-127">The directory path specified for the mapping schema (isConstant.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e7e9e-128">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="e7e9e-128">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\isConstant.xml"  
    ```  
  
3.  <span data-ttu-id="e7e9e-129">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-129">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e7e9e-130">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e7e9e-130">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e7e9e-131">Ниже приведен частичный результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="e7e9e-131">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
<Customer CustomerID="1">   
  <CustomerOrders>   
    <Order SalesOrderID="43860" OrderDate="2001-08-01" CustomerID="1" />   
    <Order SalesOrderID="44501" OrderDate="2001-11-01" CustomerID="1" />   
    <Order SalesOrderID="45283" OrderDate="2002-02-01" CustomerID="1" />   
    <Order SalesOrderID="46042" OrderDate="2002-05-01" CustomerID="1" />   
    ...  
  </CustomerOrders>   
</Customer>   
</ROOT>  
```  
  
  
