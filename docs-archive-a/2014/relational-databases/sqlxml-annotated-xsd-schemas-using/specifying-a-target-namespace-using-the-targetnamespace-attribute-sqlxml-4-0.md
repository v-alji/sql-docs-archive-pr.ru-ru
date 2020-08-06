---
title: Указание целевого пространства имен с помощью атрибута targetNamespace (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces [SQLXML], annotated XSD schemas
- targetNamespace attribute
- XSD schemas [SQLXML], target namespaces
- annotated XSD schemas, target namespaces
- xsd:targetNamespace
- attributeFormDefault attribute
- elementFormDefault attribute
- target namespaces [SQLXML]
ms.assetid: f3df9877-6672-4444-8245-2670063c9310
author: rothja
ms.author: jroth
ms.openlocfilehash: 823bcbf7f4906a2e1d2ced1ff58b681c0ca41a8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667643"
---
# <a name="specifying-a-target-namespace-using-the-targetnamespace-attribute-sqlxml-40"></a><span data-ttu-id="259cb-102">Задание целевого пространства имен с помощью атрибута targetNamespace (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="259cb-102">Specifying a Target Namespace Using the targetNamespace Attribute (SQLXML 4.0)</span></span>
  <span data-ttu-id="259cb-103">При написании XSD-схем можно использовать атрибут XSD **targetNamespace** , чтобы указать целевое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="259cb-103">In writing XSD schemas, you can use the XSD **targetNamespace** attribute to specify a target namespace.</span></span> <span data-ttu-id="259cb-104">В этом разделе описано, как работают атрибуты XSD **targetNamespace**, **elementFormDefault**и **attributeFormDefault** , как они влияют на создаваемый экземпляр XML и как задаются запросы XPath с пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="259cb-104">This topic describes how the XSD **targetNamespace**, **elementFormDefault**, and **attributeFormDefault** attributes work, how they affect the XML instance that is generated, and how XPath queries are specified with namespaces.</span></span>  
  
 <span data-ttu-id="259cb-105">Атрибут **xsd: targetNamespace** можно использовать для размещения элементов и атрибутов из пространства имен по умолчанию в другом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="259cb-105">You can use the **xsd:targetNamespace** attribute to place elements and attributes from the default namespace into a different namespace.</span></span> <span data-ttu-id="259cb-106">Можно указать, будут ли локально объявленные элементы и атрибуты схемы уточняться пространством имен, использоваться явно путем применения префикса либо использоваться неявно.</span><span class="sxs-lookup"><span data-stu-id="259cb-106">You can also specify whether the locally declared elements and attributes of the schema should appear qualified by a namespace, either explicitly by using a prefix or implicitly by default.</span></span> <span data-ttu-id="259cb-107">Вы можете использовать атрибуты **elementFormDefault** и **attributeFormDefault** в элементе, **\<xsd:schema>** чтобы глобально указать квалификацию локальных элементов и атрибутов, или можно использовать атрибут **Form** для указания отдельных элементов и атрибутов по отдельности.</span><span class="sxs-lookup"><span data-stu-id="259cb-107">You can use the **elementFormDefault** and **attributeFormDefault** attributes on the **\<xsd:schema>** element to globally specify the qualification of local elements and attributes, or you can use the **form** attribute to specify individual elements and attributes separately.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="259cb-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="259cb-108">Examples</span></span>  
 <span data-ttu-id="259cb-109">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="259cb-109">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="259cb-110">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="259cb-110">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-a-target-namespace"></a><span data-ttu-id="259cb-111">A.</span><span class="sxs-lookup"><span data-stu-id="259cb-111">A.</span></span> <span data-ttu-id="259cb-112">Указание целевого пространства имен</span><span class="sxs-lookup"><span data-stu-id="259cb-112">Specifying a target namespace</span></span>  
 <span data-ttu-id="259cb-113">Следующая схема XSD задает целевое пространство имен с помощью атрибута **xsd: targetNamespace** .</span><span class="sxs-lookup"><span data-stu-id="259cb-113">The following XSD schema specifies a target namespace by using the **xsd:targetNamespace** attribute.</span></span> <span data-ttu-id="259cb-114">Схема также задает для значений атрибута **elementFormDefault** и **attributeFormDefault** значение **"неполное"** (для этих атрибутов по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="259cb-114">The schema also sets the **elementFormDefault** and **attributeFormDefault** attribute values to **"unqualified"** (the default value for these attributes).</span></span> <span data-ttu-id="259cb-115">Это глобальное объявление и влияет на все локальные элементы ( **\<Order>** в схеме) и атрибуты (**CustomerID**, **ContactName**и **OrderID** в схеме).</span><span class="sxs-lookup"><span data-stu-id="259cb-115">This is a global declaration and affects all the local elements (**\<Order>** in the schema) and attributes (**CustomerID**, **ContactName**, and **OrderID** in the schema).</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:CO="urn:MyNamespace"   
            targetNamespace="urn:MyNamespace" >  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer"   
               sql:relation="Sales.Customer"   
               type="CO:CustomerType" />  
  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustOrders"  
                     type="CO:OrderType" />  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
        <xsd:attribute name="SalesPersonID"  type="xsd:string" />  
  </xsd:complexType>  
  <xsd:complexType name="OrderType" >  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name="CustomerID" type="xsd:string" />  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="259cb-116">В схеме:</span><span class="sxs-lookup"><span data-stu-id="259cb-116">In the schema:</span></span>  
  
-   <span data-ttu-id="259cb-117">Объявления типов **CustomerType** и **OrderType** являются глобальными и, следовательно, включаются в целевое пространство имен схемы.</span><span class="sxs-lookup"><span data-stu-id="259cb-117">The **CustomerType** and **OrderType** type declarations are global and, therefore, are included in the schema's target namespace.</span></span> <span data-ttu-id="259cb-118">В результате, если на эти типы имеется ссылка в объявлении **\<Customer>** элемента и его **\<Order>** дочернего элемента, указывается префикс, связанный с целевым пространством имен.</span><span class="sxs-lookup"><span data-stu-id="259cb-118">As a result, when these types are referenced in the declaration of **\<Customer>** element and its **\<Order>** child element, a prefix is specified that is associated with the target namespace.</span></span>  
  
-   <span data-ttu-id="259cb-119">**\<Customer>** Элемент также включается в целевое пространство имен схемы, поскольку это глобальный элемент в схеме.</span><span class="sxs-lookup"><span data-stu-id="259cb-119">The **\<Customer>** element is also included in the target namespace of the schema because it is a global element in the schema.</span></span>  
  
 <span data-ttu-id="259cb-120">Выполните следующий XPath-запрос к схеме:</span><span class="sxs-lookup"><span data-stu-id="259cb-120">Execute the following XPath query against the schema:</span></span>  
  
```  
(/CO:Customer[@CustomerID=1)   
```  
  
 <span data-ttu-id="259cb-121">Этот XPath-запрос создает следующий экземпляр документа (показаны только несколько заказов):</span><span class="sxs-lookup"><span data-stu-id="259cb-121">The XPath query generates this instance document (only a few of the orders are shown):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <y0:Customer xmlns:y0="urn:MyNamespace"   
      CustomerID="ALFKI" ContactName="Maria Anders">  
        <Order CustomerID="ALFKI" OrderID="10643" />   
        <Order CustomerID="ALFKI" OrderID="10692" />   
        ...  
  </y0:Customer>  
  </ROOT>  
```  
  
 <span data-ttu-id="259cb-122">Этот экземпляр документа определяет пространство имен urn: MyNamespace и связывает с ним префикс (y0).</span><span class="sxs-lookup"><span data-stu-id="259cb-122">This instance document defines the urn:MyNamespace namespace and associates a prefix (y0) to it.</span></span> <span data-ttu-id="259cb-123">Префикс применяется только к **\<Customer>** глобальному элементу.</span><span class="sxs-lookup"><span data-stu-id="259cb-123">The prefix is applied only to the **\<Customer>** global element.</span></span> <span data-ttu-id="259cb-124">(Элемент является глобальным, так как он объявлен как дочерний **\<xsd:schema>** элемент в схеме.)</span><span class="sxs-lookup"><span data-stu-id="259cb-124">(The element is global because it is declared as a child of **\<xsd:schema>** element in the schema.)</span></span>  
  
 <span data-ttu-id="259cb-125">Префикс не применяется к локальным элементам и атрибутам, так как в схеме значения атрибутов **elementFormDefault** и **attributeFormDefault** заданы как **неполные** .</span><span class="sxs-lookup"><span data-stu-id="259cb-125">The prefix is not applied to the local elements and attributes because the value of **elementFormDefault** and **attributeFormDefault** attributes is set to **"unqualified"** in the schema.</span></span> <span data-ttu-id="259cb-126">Обратите внимание, что **\<Order>** элемент является локальным, так как его объявление отображается в качестве дочернего элемента для **\<complexType>** элемента, определяющего **\<CustomerType>** элемент.</span><span class="sxs-lookup"><span data-stu-id="259cb-126">Note that the **\<Order>** element is local because its declaration appears as a child of the **\<complexType>** element that defines the **\<CustomerType>** element.</span></span> <span data-ttu-id="259cb-127">Аналогичным образом атрибуты (**CustomerID**, **OrderID**и **ContactName**) являются локальными, а не глобальными.</span><span class="sxs-lookup"><span data-stu-id="259cb-127">Similarly, the attributes (**CustomerID**, **OrderID**, and **ContactName**) are local, not global.</span></span>  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="259cb-128">Создание рабочего образца этой схемы</span><span class="sxs-lookup"><span data-stu-id="259cb-128">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="259cb-129">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="259cb-129">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="259cb-130">Сохраните файл с именем targetNameSpace.xml.</span><span class="sxs-lookup"><span data-stu-id="259cb-130">Save the file as targetNameSpace.xml.</span></span>  
  
2.  <span data-ttu-id="259cb-131">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="259cb-131">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="259cb-132">Сохраните файл с именем targetNameSpace.xml в тот же каталог, куда уже был сохранен файл targetNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="259cb-132">Save the file as targetNameSpaceT.xml in the same directory where you saved targetNamespace.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="targetNamespace.xml"  
                       xmlns:CO="urn:MyNamespace" >  
        /CO:Customer[@CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="259cb-133">Запрос XPath в шаблоне возвращает **\<Customer>** элемент для клиента с идентификатором CustomerID, равным 1.</span><span class="sxs-lookup"><span data-stu-id="259cb-133">The XPath query in the template returns the **\<Customer>** element for the customer with a CustomerID of 1.</span></span> <span data-ttu-id="259cb-134">Обратите внимание, что в запросе XPath префикс пространства имен указан для элемента запроса, а не для атрибута.</span><span class="sxs-lookup"><span data-stu-id="259cb-134">Note that the XPath query specifies the namespace prefix for the element in the query and not for the attribute.</span></span> <span data-ttu-id="259cb-135">(Как указано в схеме, локальные атрибуты не определены).</span><span class="sxs-lookup"><span data-stu-id="259cb-135">(Local attributes are not qualified, as specified in the schema.)</span></span>  
  
     <span data-ttu-id="259cb-136">Указанный для схемы сопоставления путь к каталогу (targetNamespace.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="259cb-136">The directory path specified for the mapping schema (targetNamespace.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="259cb-137">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="259cb-137">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\targetNamepsace.xml"  
    ```  
  
3.  <span data-ttu-id="259cb-138">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="259cb-138">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="259cb-139">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="259cb-139">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="259cb-140">Если схема задает атрибуты **elementFormDefault** и **attributeFormDefault** со значением **"квалифицированный"**, то в документе экземпляра будут определены все локальные элементы и атрибуты.</span><span class="sxs-lookup"><span data-stu-id="259cb-140">If the schema specifies **elementFormDefault** and **attributeFormDefault** attributes with value **"qualified"**, the instance document will have all of the local elements and attributes qualified.</span></span> <span data-ttu-id="259cb-141">Можно изменить предыдущую схему, чтобы включить эти атрибуты в **\<xsd:schema>** элемент, и снова выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="259cb-141">You can change the previous schema to include these attributes in the **\<xsd:schema>** element and execute the template again.</span></span> <span data-ttu-id="259cb-142">Так как атрибуты в экземпляре теперь также имеют квалификатор, XPath-запрос изменится так, чтобы включать префикс пространства имен.</span><span class="sxs-lookup"><span data-stu-id="259cb-142">Because the attributes are now also qualified in the instance, the XPath query will change to include the namespace prefix.</span></span>  
  
 <span data-ttu-id="259cb-143">Измененный XPath-запрос:</span><span class="sxs-lookup"><span data-stu-id="259cb-143">This is the revised XPath query:</span></span>  
  
```  
/CO:Customer[@CO:CustomerID=1]  
```  
  
 <span data-ttu-id="259cb-144">Возвращаемый XML-документ:</span><span class="sxs-lookup"><span data-stu-id="259cb-144">This is the XML document that is returned:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <y0:Customer xmlns:y0="urn:MyNamespace" CustomerID="1" SalesPersonID="280">  
      <Order SalesOrderID="43860" CustomerID="1" />   
      <Order SalesOrderID="44501" CustomerID="1" />   
      <Order SalesOrderID="45283" CustomerID="1" />   
      <Order SalesOrderID="46042" CustomerID="1" />   
   </y0:Customer>  
</ROOT>  
```  
  
  
