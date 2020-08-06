---
title: 'Указание связей с помощью SQL: Relationship (SQLXML 4,0) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREFS relationships [SQLXML]
- parent attribute [SQLXML]
- element relationships [SQLXML]
- multiple element relationships
- attribute relationships [SQLXML]
- sql:relationship
- relationship chains [SQLXML]
- IDREF relationships [SQLXML]
- parent-child relationships [SQLXML]
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- relationships [SQLXML], specifying
- unnamed relationships
- ID relationships [SQLXML]
- hierarchical relationships [SQLXML]
- named relationships [SQLXML]
ms.assetid: 98820afa-74e1-4e62-b336-6111a3dede4c
author: rothja
ms.author: jroth
ms.openlocfilehash: 42c703de9d564580eb0baa1349a45b193109c87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664117"
---
# <a name="specifying-relationships-using-sqlrelationship-sqlxml-40"></a><span data-ttu-id="dc789-102">Указание связей при помощи sql:relationship (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="dc789-102">Specifying Relationships Using sql:relationship (SQLXML 4.0)</span></span>
  <span data-ttu-id="dc789-103">Элементы в XML-документе могут участвовать в связях.</span><span class="sxs-lookup"><span data-stu-id="dc789-103">The elements in an XML document can be related.</span></span> <span data-ttu-id="dc789-104">Элементы могут иметь иерархическую вложенность, и между ними могут быть заданы связи ID, IDREF или IDREFS.</span><span class="sxs-lookup"><span data-stu-id="dc789-104">The elements can be nested hierarchically, and ID, IDREF, or IDREFS relationships can be specified between the elements.</span></span>  
  
 <span data-ttu-id="dc789-105">Например, в схеме XSD **\<Customer>** элемент содержит **\<Order>** дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="dc789-105">For example, in an XSD schema, a **\<Customer>** element contains **\<Order>** child elements.</span></span> <span data-ttu-id="dc789-106">Когда схема сопоставляется с базой данных AdventureWorks, **\<Customer>** элемент сопоставляется с таблицей Sales. Customer, а **\<Order>** элемент сопоставляется с таблицей Sales. SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="dc789-106">When the schema is mapped to the AdventureWorks database, the **\<Customer>** element maps to the Sales.Customer table and the **\<Order>** element maps to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="dc789-107">Базовые таблицы Sales.Customer и Sales.SalesOrderHeader связаны, так как заказчики размещают заказы.</span><span class="sxs-lookup"><span data-stu-id="dc789-107">These underlying tables, Sales.Customer and Sales.SalesOrderHeader, are related because customers place orders.</span></span> <span data-ttu-id="dc789-108">CustomerID в таблице Sales.SalesOrderHeader представляет собой внешний ключ, ссылающийся на первичный ключ CustomerID в таблице Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="dc789-108">The CustomerID in the Sales.SalesOrderHeader table is a foreign key referring to the CustomerID primary key in the Sales.Customer table.</span></span> <span data-ttu-id="dc789-109">Можно установить эти связи между соответствующими элементами схемы при помощи заметки `sql:relationship`.</span><span class="sxs-lookup"><span data-stu-id="dc789-109">You can establish these relationships among mapping schema elements by using the `sql:relationship` annotation.</span></span>  
  
 <span data-ttu-id="dc789-110">В аннотированной схеме XDR заметка `sql:relationship` обеспечивает иерархическую вложенность элементов схемы на основе связей между внешним и первичным ключом между базовыми таблицами, с которыми сопоставляется элемент.</span><span class="sxs-lookup"><span data-stu-id="dc789-110">In the annotated XSD schema, the `sql:relationship` annotation is used to nest the schema elements hierarchically, on the basis of primary key and foreign key relationships among the underlying tables to which the elements map.</span></span> <span data-ttu-id="dc789-111">При указании заметки `sql:relationship`, необходимо задать следующие данные.</span><span class="sxs-lookup"><span data-stu-id="dc789-111">In specifying the `sql:relationship` annotation, you must identify the following:</span></span>  
  
-   <span data-ttu-id="dc789-112">Родительская таблица (Sales.Customer) и дочерняя таблица (Sales.SalesOrderHeader).</span><span class="sxs-lookup"><span data-stu-id="dc789-112">The parent table (Sales.Customer) and the child table (Sales.SalesOrderHeader).</span></span>  
  
-   <span data-ttu-id="dc789-113">Столбец или столбцы, представляющие связь между родительской и дочерней таблицами.</span><span class="sxs-lookup"><span data-stu-id="dc789-113">The column or columns that compose the relationship between the parent and child tables.</span></span> <span data-ttu-id="dc789-114">Например, столбец CustomerID, который присутствует как в родительской, так и в дочерней таблицах.</span><span class="sxs-lookup"><span data-stu-id="dc789-114">For example, the CustomerID column, which appears in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="dc789-115">Эти сведения используются для правильного создания иерархии.</span><span class="sxs-lookup"><span data-stu-id="dc789-115">This information is used to generate the proper hierarchy.</span></span>  
  
 <span data-ttu-id="dc789-116">Для указания имен таблиц и необходимых сведений о соединении для заметки `sql:relationship` должны быть определены следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="dc789-116">To provide the table names and the necessary join information, the following attributes are specified on the `sql:relationship` annotation.</span></span> <span data-ttu-id="dc789-117">Эти атрибуты являются допустимыми только с **\<sql:relationship>** элементом.</span><span class="sxs-lookup"><span data-stu-id="dc789-117">These attributes are valid only with the **\<sql:relationship>** element:</span></span>  
  
 <span data-ttu-id="dc789-118">**имя**;</span><span class="sxs-lookup"><span data-stu-id="dc789-118">**Name**</span></span>  
 <span data-ttu-id="dc789-119">Указывает уникальное имя связи.</span><span class="sxs-lookup"><span data-stu-id="dc789-119">Specifies the unique name of the relationship.</span></span>  
  
 <span data-ttu-id="dc789-120">**Parent**</span><span class="sxs-lookup"><span data-stu-id="dc789-120">**Parent**</span></span>  
 <span data-ttu-id="dc789-121">Задает родительскую связь (таблицу).</span><span class="sxs-lookup"><span data-stu-id="dc789-121">Specifies the parent relation (table).</span></span> <span data-ttu-id="dc789-122">Это необязательный атрибут. Если он не указан, то имя родительской таблицы будет получено из дочерней иерархии в документе.</span><span class="sxs-lookup"><span data-stu-id="dc789-122">This is an optional attribute; if the attribute is not specified, the parent table name is obtained from information in the child hierarchy in the document.</span></span> <span data-ttu-id="dc789-123">Если схема указывает две иерархии «родители-потомки», использующие те же **\<sql:relationship>** , но разные родительские элементы, то родительский атрибут не указывается в **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="dc789-123">If the schema specifies two parent-child hierarchies that use the same **\<sql:relationship>** but different parent elements, you do not specify the parent attribute in **\<sql:relationship>**.</span></span> <span data-ttu-id="dc789-124">Эти сведения будут получены из иерархии в схеме.</span><span class="sxs-lookup"><span data-stu-id="dc789-124">This information is obtained from the hierarchy in the schema.</span></span>  
  
 <span data-ttu-id="dc789-125">**parent-key**</span><span class="sxs-lookup"><span data-stu-id="dc789-125">**parent-key**</span></span>  
 <span data-ttu-id="dc789-126">Указывает родительский ключ для родителя.</span><span class="sxs-lookup"><span data-stu-id="dc789-126">Specifies the parent key of the parent.</span></span> <span data-ttu-id="dc789-127">Если родительский ключ состоит из нескольких столбцов, то они должны быть перечислены через пробелы.</span><span class="sxs-lookup"><span data-stu-id="dc789-127">If the parent key is composed of multiple columns, values are specified with a space between them.</span></span> <span data-ttu-id="dc789-128">Между значениями, заданными для ключа, состоящего из нескольких столбцов, и соответствующего дочернего ключа, существует позиционное сопоставление.</span><span class="sxs-lookup"><span data-stu-id="dc789-128">There is a positional mapping between the values that are specified for the multicolumn key and for the corresponding child key.</span></span>  
  
 <span data-ttu-id="dc789-129">**Дочерний**</span><span class="sxs-lookup"><span data-stu-id="dc789-129">**Child**</span></span>  
 <span data-ttu-id="dc789-130">Задает дочернюю связь (таблицу).</span><span class="sxs-lookup"><span data-stu-id="dc789-130">Specifies the child relation (table).</span></span>  
  
 <span data-ttu-id="dc789-131">**child-key**</span><span class="sxs-lookup"><span data-stu-id="dc789-131">**child-key**</span></span>  
 <span data-ttu-id="dc789-132">Задает дочерний ключ потомка, который ссылается на атрибут parent-key родителя.</span><span class="sxs-lookup"><span data-stu-id="dc789-132">Specifies the child key in the child referring to parent-key in parent.</span></span> <span data-ttu-id="dc789-133">Если дочерний ключ состоит из нескольких атрибутов (столбцов), то значения атрибута child-key должны быть перечислены через пробелы.</span><span class="sxs-lookup"><span data-stu-id="dc789-133">If the child key is composed of multiple attributes (columns), the child-key values are specified with a space between them.</span></span> <span data-ttu-id="dc789-134">Между значениями, заданными для ключа, состоящего из нескольких столбцов, и соответствующего родительского ключа, существует позиционное сопоставление.</span><span class="sxs-lookup"><span data-stu-id="dc789-134">There is a positional mapping between the values that are specified for the multicolumn key and for the corresponding parent key.</span></span>  
  
 <span data-ttu-id="dc789-135">**Inverse**</span><span class="sxs-lookup"><span data-stu-id="dc789-135">**Inverse**</span></span>  
 <span data-ttu-id="dc789-136">Этот атрибут, указанный в **\<sql:relationship>** , используется диаграмм обновления.</span><span class="sxs-lookup"><span data-stu-id="dc789-136">This attribute specified on **\<sql:relationship>** is used by updategrams.</span></span> <span data-ttu-id="dc789-137">Дополнительные сведения см. в разделе [Указание атрибута SQL: инверсии в SQL: relationship](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="dc789-137">For more information, see [Specifying the sql:inverse Attribute on sql:relationship](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="dc789-138">`sql:key-fields`Заметка должна быть указана в элементе, содержащем дочерний элемент, который **\<sql:relationship>** определен между элементом и дочерним элементом и не предоставляет первичный ключ таблицы, указанной в родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="dc789-138">The `sql:key-fields` annotation must be specified in an element that contains a child element, that has a **\<sql:relationship>** defined between the element and the child, and that does not provide the primary key of the table specified in the parent element.</span></span> <span data-ttu-id="dc789-139">Даже если схема не указывает **\<sql:relationship>** , необходимо указать `sql:key-fields` для создания соответствующей иерархии.</span><span class="sxs-lookup"><span data-stu-id="dc789-139">Even if the schema does not specify **\<sql:relationship>**, you must specify `sql:key-fields` to produce the proper hierarchy.</span></span> <span data-ttu-id="dc789-140">Дополнительные сведения см. в разделе [Определение ключевых столбцов с помощью SQL: Key-Fields](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="dc789-140">For more information, see [Identifying Key Columns by Using sql:key-fields](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="dc789-141">Чтобы правильно организовать вложенность в результатах, рекомендуется во всех схемах определять заметку `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="dc789-141">To produce proper nesting in the result, it is recommended that `sql:key-fields` are specified in all schemas.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="dc789-142">Примеры</span><span class="sxs-lookup"><span data-stu-id="dc789-142">Examples</span></span>  
 <span data-ttu-id="dc789-143">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="dc789-143">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="dc789-144">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="dc789-144">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlrelationship-annotation-on-an-element"></a><span data-ttu-id="dc789-145">A.</span><span class="sxs-lookup"><span data-stu-id="dc789-145">A.</span></span> <span data-ttu-id="dc789-146">Определение заметки sql:relationship для элемента</span><span class="sxs-lookup"><span data-stu-id="dc789-146">Specifying the sql:relationship annotation on an element</span></span>  
 <span data-ttu-id="dc789-147">Следующие помеченные схемы XSD включают **\<Customer>** элементы и **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="dc789-147">The following annotated XSD schema includes **\<Customer>** and **\<Order>** elements.</span></span> <span data-ttu-id="dc789-148">**\<Order>** Элемент является дочерним элементом **\<Customer>** элемента.</span><span class="sxs-lookup"><span data-stu-id="dc789-148">The **\<Order>** element is a child element of the **\<Customer>** element.</span></span>  
  
 <span data-ttu-id="dc789-149">В схеме `sql:relationship` заметка задается в **\<Order>** дочернем элементе.</span><span class="sxs-lookup"><span data-stu-id="dc789-149">In the schema, the `sql:relationship` annotation is specified on the **\<Order>** child element.</span></span> <span data-ttu-id="dc789-150">Сама связь определяется в **\<xsd:appinfo>** элементе.</span><span class="sxs-lookup"><span data-stu-id="dc789-150">The relationship itself is defined in the **\<xsd:appinfo>** element.</span></span>  
  
 <span data-ttu-id="dc789-151">**\<relationship>** Элемент идентифицирует CustomerID в таблице Sales. SalesOrderHeader как внешний ключ, который ссылается на первичный ключ CustomerID в таблице Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="dc789-151">The **\<relationship>** element identifies CustomerID in the Sales.SalesOrderHeader table as a foreign key that refers to the CustomerID primary key in the Sales.Customer table.</span></span> <span data-ttu-id="dc789-152">Таким образом, заказы, принадлежащие клиенту, отображаются как дочерний элемент этого **\<Customer>** элемента.</span><span class="sxs-lookup"><span data-stu-id="dc789-152">Therefore, orders that belong to a customer appear as a child element of that **\<Customer>** element.</span></span>  
  
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
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                    sql:relationship="CustOrders" >  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="dc789-153">В предыдущей схеме используется именованная связь.</span><span class="sxs-lookup"><span data-stu-id="dc789-153">The previous schema uses a named relationship.</span></span> <span data-ttu-id="dc789-154">Можно также указать неименованную связь.</span><span class="sxs-lookup"><span data-stu-id="dc789-154">You can also specify an unnamed relationship.</span></span> <span data-ttu-id="dc789-155">Результаты будут одинаковы.</span><span class="sxs-lookup"><span data-stu-id="dc789-155">The results are same.</span></span>  
  
 <span data-ttu-id="dc789-156">Ниже приведена новый вариант схемы, в которой определена неименованная связь.</span><span class="sxs-lookup"><span data-stu-id="dc789-156">This is the revised schema in which an unnamed relationship is specified:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer"  type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader">  
           <xsd:annotation>  
            <xsd:appinfo>  
              <sql:relationship   
                parent="Sales.Customer"  
                parent-key="CustomerID"  
                child="Sales.SalesOrderHeader"  
                child-key="CustomerID" />  
            </xsd:appinfo>  
           </xsd:annotation>  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="dc789-157">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="dc789-157">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="dc789-158">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="dc789-158">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="dc789-159">Сохраните файл под именем sql-relationship.xml.</span><span class="sxs-lookup"><span data-stu-id="dc789-159">Save the file as sql-relationship.xml.</span></span>  
  
2.  <span data-ttu-id="dc789-160">Скопируйте приведенный ниже шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="dc789-160">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="dc789-161">Сохраните файл под именем sql-relationshipT.xml в том же каталоге, где был сохранен файл sql-relationship.xml.</span><span class="sxs-lookup"><span data-stu-id="dc789-161">Save the file as sql-relationshipT.xml in the same directory where you saved sql-relationship.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-relationship.xml">  
            /Customer[@CustomerID=1]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="dc789-162">Путь к каталогу схемы сопоставления (файл sql-relationship.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="dc789-162">The directory path specified for the mapping schema (sql-relationship.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="dc789-163">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="dc789-163">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\sql-relationship.xml"  
    ```  
  
3.  <span data-ttu-id="dc789-164">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="dc789-164">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="dc789-165">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="dc789-165">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="dc789-166">Результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="dc789-166">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer CustomerID="1">   
    <Order OrderID="43860" CustomerID="1" />   
    <Order OrderID="44501" CustomerID="1" />   
    <Order OrderID="45283" CustomerID="1" />   
    <Order OrderID="46042" CustomerID="1" />   
  </Customer>   
</ROOT>  
```  
  
### <a name="b-specifying-a-relationship-chain"></a><span data-ttu-id="dc789-167">Б.</span><span class="sxs-lookup"><span data-stu-id="dc789-167">B.</span></span> <span data-ttu-id="dc789-168">Указание цепочки связей</span><span class="sxs-lookup"><span data-stu-id="dc789-168">Specifying a relationship chain</span></span>  
 <span data-ttu-id="dc789-169">Для данного примера предположим, что в следующем XML-документе нужно использовать данные, полученные из базы данных AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="dc789-169">For this example, assume that you want the following XML document using data obtained from the AdventureWorks database:</span></span>  
  
```  
<Order SalesOrderID="43659">  
  <Product Name="Mountain Bike Socks, M"/>   
  <Product Name="Sport-100 Helmet, Blue"/>  
  ...  
</Order>  
...  
```  
  
 <span data-ttu-id="dc789-170">Для каждого заказа в таблице Sales. SalesOrderHeader XML-документ содержит один **\<Order>** элемент.</span><span class="sxs-lookup"><span data-stu-id="dc789-170">For each order in the Sales.SalesOrderHeader table, the XML document has one **\<Order>** element.</span></span> <span data-ttu-id="dc789-171">Каждый **\<Order>** элемент имеет список **\<Product>** дочерних элементов, по одному для каждого продукта, запрошенного в заказе.</span><span class="sxs-lookup"><span data-stu-id="dc789-171">And each **\<Order>** element has a list of **\<Product>** child elements, one for each product requested in the order.</span></span>  
  
 <span data-ttu-id="dc789-172">Чтобы указать схему XSD, которая будет создавать эту иерархию, необходимо указать две связи: Ордерод и ODProduct.</span><span class="sxs-lookup"><span data-stu-id="dc789-172">To specify an XSD schema that will produce this hierarchy, you must specify two relationships: OrderOD and ODProduct.</span></span> <span data-ttu-id="dc789-173">Связь OrderOD определяет связь типа «родитель-потомок» между таблицами Sales.SalesOrderHeader и Sales.SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="dc789-173">The OrderOD relationship specifies the parent-child relationship between the Sales.SalesOrderHeader and Sales.SalesOrderDetail tables.</span></span> <span data-ttu-id="dc789-174">Связь ODProduct определяет связь между таблицами Sales.SalesOrderDetail и Production.Product.</span><span class="sxs-lookup"><span data-stu-id="dc789-174">The ODProduct relationship specifies the relationship between the Sales.SalesOrderDetail and Production.Product tables.</span></span>  
  
 <span data-ttu-id="dc789-175">В следующей схеме `msdata:relationship` заметка **\<Product>** элемента определяет два значения: Ордерод и ODProduct.</span><span class="sxs-lookup"><span data-stu-id="dc789-175">In the following schema, the `msdata:relationship` annotation on the **\<Product>** element specifies two values: OrderOD and ODProduct.</span></span> <span data-ttu-id="dc789-176">Порядок следования этих значений важен.</span><span class="sxs-lookup"><span data-stu-id="dc789-176">The order in which these values are specified is important.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <msdata:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  
    <msdata:relationship name="ODProduct"  
          parent="Sales.SalesOrderDetail"  
          parent-key="ProductID"  
          child="Production.Product"  
          child-key="ProductID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Order" msdata:relation="Sales.SalesOrderHeader"   
               msdata:key-fields="SalesOrderID" type="OrderType" />  
   <xsd:complexType name="OrderType" >  
     <xsd:sequence>  
        <xsd:element name="Product" msdata:relation="Production.Product"   
                     msdata:key-fields="ProductID"  
                     msdata:relationship="OrderOD ODProduct">  
          <xsd:complexType>  
             <xsd:attribute name="Name" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="SalesOrderID"   type="xsd:integer" />   
    </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="dc789-177">Вместо указания именованной связи можно задать анонимную связь.</span><span class="sxs-lookup"><span data-stu-id="dc789-177">Instead of specifying a named relationship, you can specify an anonymous relationship.</span></span> <span data-ttu-id="dc789-178">В этом случае все содержимое **\<annotation>** ... **\</annotation>** , описывающее две связи, отображается как дочерний элемент **\<Product>** .</span><span class="sxs-lookup"><span data-stu-id="dc789-178">In this case, the entire contents of **\<annotation>**...**\</annotation>**, which describes the two relationships, appear as a child element of **\<Product>**.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Order" msdata:relation="Sales.SalesOrderHeader"   
               msdata:key-fields="SalesOrderID" type="OrderType" />  
  
   <xsd:complexType name="OrderType" >  
     <xsd:sequence>  
        <xsd:element name="Product" msdata:relation="Production.Product"   
                     msdata:key-fields="ProductID" >  
         <xsd:annotation>  
          <xsd:appinfo>  
           <msdata:relationship   
               parent="Sales.SalesOrderHeader"  
               parent-key="SalesOrderID"  
               child="Sales.SalesOrderDetail"  
               child-key="SalesOrderID" />  
  
           <msdata:relationship   
               parent="Sales.SalesOrderDetail"  
               parent-key="ProductID"  
               child="Production.Product"  
               child-key="ProductID" />  
         </xsd:appinfo>  
       </xsd:annotation>  
       <xsd:complexType>  
          <xsd:attribute name="Name" type="xsd:string" />  
       </xsd:complexType>  
     </xsd:element>  
   </xsd:sequence>  
   <xsd:attribute name="SalesOrderID"   type="xsd:integer" />   
  </xsd:complexType>  
 </xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="dc789-179">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="dc789-179">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="dc789-180">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="dc789-180">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="dc789-181">Сохраните файл под именем relationshipChain.xml.</span><span class="sxs-lookup"><span data-stu-id="dc789-181">Save the file as relationshipChain.xml.</span></span>  
  
2.  <span data-ttu-id="dc789-182">Скопируйте приведенный ниже шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="dc789-182">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="dc789-183">Сохраните файл под именем relationshipChainT.xml в том же каталоге, где был сохранен файл relationshipChain.xml.</span><span class="sxs-lookup"><span data-stu-id="dc789-183">Save the file as relationshipChainT.xml in the same directory where you saved relationshipChain.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="relationshipChain.xml">  
            /Order  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="dc789-184">Путь к каталогу для схемы сопоставления (файл relationshipChain.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="dc789-184">The directory path specified for the mapping schema (relationshipChain.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="dc789-185">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="dc789-185">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationshipChain.xml"  
    ```  
  
3.  <span data-ttu-id="dc789-186">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="dc789-186">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="dc789-187">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="dc789-187">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="dc789-188">Результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="dc789-188">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Order SalesOrderID="43659">  
    <Product Name="Mountain Bike Socks, M" />   
    <Product Name="Sport-100 Helmet, Blue" />   
    <Product Name="AWC Logo Cap" />   
    <Product Name="Long-Sleeve Logo Jersey, M" />   
    <Product Name="Long-Sleeve Logo Jersey, XL" />   
    ...  
  </Order>  
  ...  
</ROOT>  
```  
  
### <a name="c-specifying-the-relationship-annotation-on-an-attribute"></a><span data-ttu-id="dc789-189">В.</span><span class="sxs-lookup"><span data-stu-id="dc789-189">C.</span></span> <span data-ttu-id="dc789-190">Задание заметки relationship для атрибута</span><span class="sxs-lookup"><span data-stu-id="dc789-190">Specifying the relationship annotation on an attribute</span></span>  
 <span data-ttu-id="dc789-191">Схема в этом примере включает \<Customer> элемент с \<CustomerID> дочерним элементом и атрибутом ОРДЕРИДЛИСТ типа IDREFS.</span><span class="sxs-lookup"><span data-stu-id="dc789-191">The schema in this example includes a \<Customer> element with a \<CustomerID> child element and an OrderIDList attribute of IDREFS type.</span></span> <span data-ttu-id="dc789-192">\<Customer>Элемент сопоставляется с таблицей Sales. Customer в базе данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="dc789-192">The \<Customer> element maps to the Sales.Customer table in the AdventureWorks database.</span></span> <span data-ttu-id="dc789-193">По умолчанию область этого сопоставления применяется ко всем дочерним элементам или атрибутам, если только `sql:relation` не указан в дочернем элементе или атрибуте, в этом случае соответствующая связь типа "первичный ключ — внешний ключ" должна быть определена с помощью \<relationship> элемента.</span><span class="sxs-lookup"><span data-stu-id="dc789-193">By default, the scope of this mapping applies to all the child elements or attributes unless `sql:relation` is specified on the child element or attribute, in which case, the appropriate primary-key/foreign-key relationship must be defined using the \<relationship> element.</span></span> <span data-ttu-id="dc789-194">Дочерний элемент или атрибут, который указывает другую таблицу при помощи заметки `relation`, должен также содержать заметку `relationship`.</span><span class="sxs-lookup"><span data-stu-id="dc789-194">And the child element or attribute, which specifies the different table using the `relation` annotation, must also specify the `relationship` annotation.</span></span>  
  
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
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="CustomerID"   type="xsd:string" />   
     </xsd:sequence>  
     <xsd:attribute name="OrderIDList"   
                     type="xsd:IDREFS"   
                     sql:relation="Sales.SalesOrderHeader"   
                     sql:field="SalesOrderID"  
                     sql:relationship="CustOrders" >  
        </xsd:attribute>  
    </xsd:complexType>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="dc789-195">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="dc789-195">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="dc789-196">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="dc789-196">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="dc789-197">Сохраните файл под именем relationship-on-attribute.xml.</span><span class="sxs-lookup"><span data-stu-id="dc789-197">Save the file as relationship-on-attribute.xml.</span></span>  
  
2.  <span data-ttu-id="dc789-198">Скопируйте следующий шаблон и вставьте его в файл.</span><span class="sxs-lookup"><span data-stu-id="dc789-198">Copy the following template and paste it into a file.</span></span> <span data-ttu-id="dc789-199">Сохраните файл под именем relationship-on-attributeT.xml в том же каталоге, где был сохранен файл relationship-on-attribute.xml.</span><span class="sxs-lookup"><span data-stu-id="dc789-199">Save the file as relationship-on-attributeT.xml in the same directory where you saved relationship-on-attribute.xml.</span></span> <span data-ttu-id="dc789-200">Запрос в шаблоне выберет клиента со значением идентификатора ContactID, равным 1.</span><span class="sxs-lookup"><span data-stu-id="dc789-200">The query in the template selects a customer with the CustomerID of 1.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="relationship-on-attribute.xml">  
        /Customer[CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="dc789-201">Путь к каталогу схемы сопоставления (файл relationship-on-attribute.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="dc789-201">The directory path specified for the mapping schema (relationship-on-attribute.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="dc789-202">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="dc789-202">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-on-attribute.xml"  
    ```  
  
3.  <span data-ttu-id="dc789-203">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="dc789-203">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="dc789-204">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="dc789-204">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="dc789-205">Результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="dc789-205">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer OrderIDList="43860 44501 45283 46042">  
    <CustomerID>1</CustomerID>   
  </Customer>  
</ROOT>  
```  
  
### <a name="d-specifying-sqlrelationship-on-multiple-elements"></a><span data-ttu-id="dc789-206">Г.</span><span class="sxs-lookup"><span data-stu-id="dc789-206">D.</span></span> <span data-ttu-id="dc789-207">Задание sql:relationship для нескольких элементов</span><span class="sxs-lookup"><span data-stu-id="dc789-207">Specifying sql:relationship on multiple elements</span></span>  
 <span data-ttu-id="dc789-208">В этом примере схема XSD с заметками содержит **\<Customer>** элементы, **\<Order>** и **\<OrderDetail>** .</span><span class="sxs-lookup"><span data-stu-id="dc789-208">In this example, the annotated XSD schema contains the **\<Customer>**, **\<Order>**, and **\<OrderDetail>** elements.</span></span>  
  
 <span data-ttu-id="dc789-209">**\<Order>** Элемент является дочерним элементом **\<Customer>** элемента.</span><span class="sxs-lookup"><span data-stu-id="dc789-209">The **\<Order>** element is a child element of the **\<Customer>** element.</span></span> <span data-ttu-id="dc789-210">**\<sql:relationship>** в **\<Order>** дочернем элементе задано значение, поэтому заказы, принадлежащие клиенту, отображаются в виде дочерних элементов **\<Customer>** .</span><span class="sxs-lookup"><span data-stu-id="dc789-210">**\<sql:relationship>** is specified on the **\<Order>** child element; therefore, orders that belong to a customer appear as child elements of **\<Customer>**.</span></span>  
  
 <span data-ttu-id="dc789-211">**\<Order>** Элемент включает **\<OrderDetail>** дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="dc789-211">The **\<Order>** element includes the **\<OrderDetail>** child element.</span></span> <span data-ttu-id="dc789-212">**\<sql:relationship>** задается для **\<OrderDetail>** дочернего элемента, поэтому сведения о заказе, относящиеся к заказу, отображаются как дочерние элементы этого **\<Order>** элемента.</span><span class="sxs-lookup"><span data-stu-id="dc789-212">**\<sql:relationship>** is specified on **\<OrderDetail>** child element, so the order details that pertain to an order appear as child elements of that **\<Order>** element.</span></span>  
  
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
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="OrderDate" type="xsd:date" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="CustomerID" type="xsd:string" />  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="dc789-213">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="dc789-213">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="dc789-214">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="dc789-214">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="dc789-215">Сохраните файл под именем relationship-multiple-elements.xml.</span><span class="sxs-lookup"><span data-stu-id="dc789-215">Save the file as relationship-multiple-elements.xml.</span></span>  
  
2.  <span data-ttu-id="dc789-216">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="dc789-216">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="dc789-217">Сохраните файл под именем relationship-multiple-elementsT.xml в том же каталоге, где был сохранен файл relationship-multiple-elements.xml.</span><span class="sxs-lookup"><span data-stu-id="dc789-217">Save the file as relationship-multiple-elementsT.xml in the same directory where you saved relationship-multiple-elements.xml.</span></span> <span data-ttu-id="dc789-218">Запрос в шаблоне возвращает сведения о заказчиках со значением CustomerID, равным 1, и SalesOrderID, равным 43860.</span><span class="sxs-lookup"><span data-stu-id="dc789-218">The query in the template returns order information for a customer with the CustomerID of 1 and SalesOrderID of 43860.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="relationship-multiple-elements.xml">  
        /Customer[@CustomerID=1]/Order[@SalesOrderID=43860]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="dc789-219">Путь к каталогу схемы сопоставления (файл relationship-multiple-elements.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="dc789-219">The directory path specified for the mapping schema (relationship-multiple-elements.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="dc789-220">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="dc789-220">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-multiple-elements.xml"  
    ```  
  
3.  <span data-ttu-id="dc789-221">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="dc789-221">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="dc789-222">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="dc789-222">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="dc789-223">Результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="dc789-223">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="43860" OrderDate="2001-08-01" CustomerID="1">  
     <OrderDetail SalesOrderID="43860" ProductID="761" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="770" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="758" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="765" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="732" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="762" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="738" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="768" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="753" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="729" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="763" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="756" OrderQty="1" />   
  </Order>  
</ROOT>  
```  
  
### <a name="e-specifying-the-sqlrelationship-without-the-parent-attribute"></a><span data-ttu-id="dc789-224">Д.</span><span class="sxs-lookup"><span data-stu-id="dc789-224">E.</span></span> <span data-ttu-id="dc789-225">Указание \<sql:relationship> без родительского атрибута</span><span class="sxs-lookup"><span data-stu-id="dc789-225">Specifying the \<sql:relationship> without the parent attribute</span></span>  
 <span data-ttu-id="dc789-226">В этом примере показано, как указать **\<sql:relationship>** без **родительского** атрибута.</span><span class="sxs-lookup"><span data-stu-id="dc789-226">This example illustrates specifying the **\<sql:relationship>** without the **parent** attribute.</span></span> <span data-ttu-id="dc789-227">Предположим, имеется следующая таблица сотрудников.</span><span class="sxs-lookup"><span data-stu-id="dc789-227">For example, assume you have the following employee tables:</span></span>  
  
```  
Emp1(SalesPersonID, FirstName, LastName, ReportsTo)  
Emp2(SalesPersonID, FirstName, LastName, ReportsTo)  
```  
  
 <span data-ttu-id="dc789-228">В следующем XML-представлении **\<Emp1>** элементы и **\<Emp2>** сопоставляются с таблицами Sales. Emp1 и Sales. Emp2:</span><span class="sxs-lookup"><span data-stu-id="dc789-228">The following XML view has the **\<Emp1>** and **\<Emp2>** elements mapping to the Sales.Emp1 and Sales.Emp2 tables:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="EmpOrders"  
          parent-key="SalesPersonID"  
          child="Sales.SalesOrderHeader"  
          child-key="SalesPersonID" />  
     </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Emp1" sql:relation="Sales.Emp1" type="EmpType" />  
  <xsd:element name="Emp2" sql:relation="Sales.Emp2" type="EmpType" />  
   <xsd:complexType name="EmpType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"   
                     sql:relationship="EmpOrders" >  
          <xsd:complexType>  
             <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
             <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="SalesPersonID"   type="xsd:integer" />   
        <xsd:attribute name="LastName"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="dc789-229">В схеме **\<Emp1>** элемент и элемент **\<Emp2>** имеют тип `EmpType` .</span><span class="sxs-lookup"><span data-stu-id="dc789-229">In the schema, both the **\<Emp1>** element and **\<Emp2>** element are of type `EmpType`.</span></span> <span data-ttu-id="dc789-230">Тип `EmpType` описывает **\<Order>** дочерний элемент и соответствующий объект **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="dc789-230">The type `EmpType` describes an **\<Order>** child element and the corresponding **\<sql:relationship>**.</span></span> <span data-ttu-id="dc789-231">В этом случае отсутствует один родительский элемент, который может быть идентифицирован в **\<sql:relationship>** с помощью **родительского** атрибута.</span><span class="sxs-lookup"><span data-stu-id="dc789-231">In this case, there is no single parent that can be identified in **\<sql:relationship>** by using the **parent** attribute.</span></span> <span data-ttu-id="dc789-232">В этом случае **родительский** атрибут не указывается в параметре **\<sql:relationship>** ; сведения о **родительском** атрибуте получаются из иерархии схемы.</span><span class="sxs-lookup"><span data-stu-id="dc789-232">In this situation, you don't specify the **parent** attribute in **\<sql:relationship>**; the **parent** attribute information is obtained from the hierarchy in the schema.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="dc789-233">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="dc789-233">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="dc789-234">Создайте следующие таблицы в базе данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="dc789-234">Create these tables in the AdventureWorks database:</span></span>  
  
    ```  
    USE AdventureWorks  
    CREATE TABLE Sales.Emp1 (  
           SalesPersonID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    Go  
    CREATE TABLE Sales.Emp2 (  
           SalesPersonID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    Go  
    ```  
  
2.  <span data-ttu-id="dc789-235">Добавьте следующий образец данных в таблицы.</span><span class="sxs-lookup"><span data-stu-id="dc789-235">Add this sample data in the tables:</span></span>  
  
    ```  
    INSERT INTO Sales.Emp1 values (279, 'Nancy', 'Devolio',NULL)  
    INSERT INTO Sales.Emp1 values (282, 'Andrew', 'Fuller',1)  
    INSERT INTO Sales.Emp1 values (276, 'Janet', 'Leverling',1)  
    INSERT INTO Sales.Emp2 values (277, 'Margaret', 'Peacock',3)  
    INSERT INTO Sales.Emp2 values (283, 'Steven', 'Devolio',4)  
    INSERT INTO Sales.Emp2 values (275, 'Nancy', 'Buchanan',5)  
    INSERT INTO Sales.Emp2 values (281, 'Michael', 'Suyama',6)  
    ```  
  
3.  <span data-ttu-id="dc789-236">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="dc789-236">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="dc789-237">Сохраните файл под именем relationship-noparent.xml.</span><span class="sxs-lookup"><span data-stu-id="dc789-237">Save the file as relationship-noparent.xml.</span></span>  
  
4.  <span data-ttu-id="dc789-238">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="dc789-238">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="dc789-239">Сохраните файл под именем relationship-noparentT.xml в том же каталоге, где был сохранен файл relationship-noparent.xml.</span><span class="sxs-lookup"><span data-stu-id="dc789-239">Save the file as relationship-noparentT.xml in the same directory where you saved relationship-noparent.xml.</span></span> <span data-ttu-id="dc789-240">Запрос в шаблоне выбирает все \<Emp1> элементы (таким образом, родительский элемент — Emp1).</span><span class="sxs-lookup"><span data-stu-id="dc789-240">The query in the template selects all the \<Emp1> elements (therefore, the parent is Emp1).</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="relationship-noparent.xml">  
            /Emp1  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="dc789-241">Путь к каталогу схемы сопоставления (файл relationship-noparent.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="dc789-241">The directory path specified for the mapping schema (relationship-noparent.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="dc789-242">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="dc789-242">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-noparent.xml"  
    ```  
  
5.  <span data-ttu-id="dc789-243">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="dc789-243">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="dc789-244">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="dc789-244">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="dc789-245">Вот частичный результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="dc789-245">Here is a partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<Emp1 SalesPersonID="276" LastName="Leverling">  
  <Order SalesOrderID="43663" CustomerID="510" />   
  <Order SalesOrderID="43666" CustomerID="511" />   
  <Order SalesOrderID="43859" CustomerID="259" />  
  ...  
</Emp1>  
```  
  
  
