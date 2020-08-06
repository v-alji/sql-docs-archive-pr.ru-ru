---
title: 'Определение ключевых столбцов с помощью SQL: Key-Fields (SQLXML 4,0) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nesting XML results
- proper nesting in results [SQLXML]
- sql:key-fields
- XSD schemas [SQLXML], key columns
- identifying key columns [SQLXML]
- annotated XSD schemas, key columns
- key columns [SQLXML]
- relationships [SQLXML], key columns
- hierarchical relationships [SQLXML]
- key-fields annotation
ms.assetid: 1a5ad868-8602-45c4-913d-6fbb837eebb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 0ab12b34874a54bad2e08a96d08ebd0cc994f946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750563"
---
# <a name="identifying-key-columns-using-sqlkey-fields-sqlxml-40"></a><span data-ttu-id="f2794-102">Идентификация ключевых столбцов с использованием sql:key-fields (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f2794-102">Identifying Key Columns Using sql:key-fields (SQLXML 4.0)</span></span>
  <span data-ttu-id="f2794-103">При указании запроса XPath к схеме XSD в большинстве случаев необходимы ключевые сведения, чтобы правильно организовать вложенность в результатах.</span><span class="sxs-lookup"><span data-stu-id="f2794-103">When an XPath query is specified against an XSD schema, key information is required in most cases to obtain proper nesting in the result.</span></span> <span data-ttu-id="f2794-104">Указание заметки `sql:key-fields` представляет собой один из способов, который гарантирует формирование надлежащей иерархии.</span><span class="sxs-lookup"><span data-stu-id="f2794-104">Specifying the `sql:key-fields` annotation is a way of ensuring that the appropriate hierarchy is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2794-105">Чтобы гарантировать надлежащую вложенность, рекомендуется указывать заметки `sql:key-fields` для элементов, которые сопоставляются с таблицами.</span><span class="sxs-lookup"><span data-stu-id="f2794-105">To ensure proper nesting, it is recommended that you specify `sql:key-fields` for elements that map to tables.</span></span> <span data-ttu-id="f2794-106">Формируемый XML-код является зависимым от упорядочения базового результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="f2794-106">The XML produced is sensitive to the ordering of the underlying result set.</span></span> <span data-ttu-id="f2794-107">Если заметка `sql:key-fields` не указана, то результирующий XML-код может оказаться не сформированным надлежащим образом.</span><span class="sxs-lookup"><span data-stu-id="f2794-107">If `sql:key-fields` is not specified, the XML generated might not be formed properly.</span></span>  
  
 <span data-ttu-id="f2794-108">Значение `sql:key-fields` идентифицирует столбцы, которые уникальным образом обозначают строки в связи.</span><span class="sxs-lookup"><span data-stu-id="f2794-108">The value of `sql:key-fields` identifies the column(s) that uniquely identify the rows in the relation.</span></span> <span data-ttu-id="f2794-109">Если для уникальной идентификации строки требуется более одного столбца, то значения столбцов разделяются пробелами.</span><span class="sxs-lookup"><span data-stu-id="f2794-109">If more than one column is required to uniquely identify a row, the column values are delimited by spaces.</span></span>  
  
 <span data-ttu-id="f2794-110">Примечание следует использовать, `sql:key-fields` когда элемент содержит объект **\<sql:relationship>** , определенный между элементом и дочерним элементом, но не предоставляющий первичный ключ таблицы, указанный в родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="f2794-110">You must use the `sql:key-fields` annotation when an element contains a **\<sql:relationship>** that is defined between the element and a child element but does not provide the primary key of the table that is specified in the parent element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f2794-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="f2794-111">Examples</span></span>  
 <span data-ttu-id="f2794-112">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="f2794-112">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="f2794-113">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="f2794-113">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-producing-the-appropriate-nesting-when-sqlrelationship-does-not-provide-sufficient-information"></a><span data-ttu-id="f2794-114">A.</span><span class="sxs-lookup"><span data-stu-id="f2794-114">A.</span></span> <span data-ttu-id="f2794-115">Создание подходящего вложения, если не \<sql:relationship> предоставляет достаточно сведений</span><span class="sxs-lookup"><span data-stu-id="f2794-115">Producing the appropriate nesting when \<sql:relationship> does not provide sufficient information</span></span>  
 <span data-ttu-id="f2794-116">В этом примере показано, где необходимо указывать `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="f2794-116">This example shows where `sql:key-fields` must be specified.</span></span>  
  
 <span data-ttu-id="f2794-117">Рассмотрим следующую схему.</span><span class="sxs-lookup"><span data-stu-id="f2794-117">Consider the following schema.</span></span> <span data-ttu-id="f2794-118">Схема задает иерархию между **\<Order>** элементами и, **\<Customer>** в которых **\<Order>** элемент является родительским, а **\<Customer>** элемент — дочерним.</span><span class="sxs-lookup"><span data-stu-id="f2794-118">The schema specifies a hierarchy between the **\<Order>** and **\<Customer>** elements in which the **\<Order>** element is the parent and the **\<Customer>** element is a child.</span></span>  
  
 <span data-ttu-id="f2794-119">**\<sql:relationship>** Тег используется для указания связи «родители-потомки».</span><span class="sxs-lookup"><span data-stu-id="f2794-119">The **\<sql:relationship>** tag is used to specify the parent-child relationship.</span></span> <span data-ttu-id="f2794-120">Он идентифицирует столбец CustomerID в таблице Sales.SalesOrderHeader как родительский ключ, который ссылается на дочерний ключ CustomerID таблицы Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="f2794-120">It identifies CustomerID in the Sales.SalesOrderHeader table as the parent key that refers to the CustomerID child key in the Sales.Customer table.</span></span> <span data-ttu-id="f2794-121">Сведения, предоставленные в **\<sql:relationship>** , недостаточно для уникальной идентификации строк в родительской таблице (Sales. SalesOrderHeader).</span><span class="sxs-lookup"><span data-stu-id="f2794-121">The information provided in **\<sql:relationship>** is not sufficient to uniquely identify rows in the parent table (Sales.SalesOrderHeader).</span></span> <span data-ttu-id="f2794-122">Поэтому без заметки `sql:key-fields` формируемая иерархия является неточной.</span><span class="sxs-lookup"><span data-stu-id="f2794-122">Therefore, without the `sql:key-fields` annotation, the hierarchy that is generated is inaccurate.</span></span>  
  
 <span data-ttu-id="f2794-123">В `sql:key-fields` указанном параметре в **\<Order>** аннотации уникально определяются строки в родительской таблице (Sales. SalesOrderHeader), а ее дочерние элементы отображаются под родительским элементом.</span><span class="sxs-lookup"><span data-stu-id="f2794-123">With `sql:key-fields` specified on **\<Order>**, the annotation uniquely identifies the rows in the parent (Sales.SalesOrderHeader table), and its child elements appear below its parent.</span></span>  
  
 <span data-ttu-id="f2794-124">Схема:</span><span class="sxs-lookup"><span data-stu-id="f2794-124">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrdCust"  
        parent="Sales.SalesOrderHeader"  
        parent-key="CustomerID"  
        child="Sales.Customer"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
               sql:key-fields="SalesOrderID">  
   <xsd:complexType>  
     <xsd:sequence>  
     <xsd:element name="Customer" sql:relation="Sales.Customer"   
                       sql:relationship="OrdCust"  >  
       <xsd:complexType>  
         <xsd:attribute name="CustID" sql:field="CustomerID" />  
         <xsd:attribute name="SoldBy" sql:field="SalesPersonID" />  
       </xsd:complexType>  
     </xsd:element>  
     </xsd:sequence>  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name= "CustomerID" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="f2794-125">Создание рабочего образца этой схемы</span><span class="sxs-lookup"><span data-stu-id="f2794-125">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="f2794-126">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="f2794-126">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="f2794-127">Сохраните файл под именем KeyFields1.xml.</span><span class="sxs-lookup"><span data-stu-id="f2794-127">Save the file as KeyFields1.xml.</span></span>  
  
2.  <span data-ttu-id="f2794-128">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="f2794-128">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="f2794-129">Сохраните файл под именем KeyFields1T.xml в том же каталоге, в котором был сохранен файл KeyFields1.xml.</span><span class="sxs-lookup"><span data-stu-id="f2794-129">Save the file as KeyFields1T.xml in the same directory where you saved KeyFields1.xml.</span></span> <span data-ttu-id="f2794-130">Запрос XPath в шаблоне возвращает все **\<Order>** элементы с идентификатором CustomerID меньше 3.</span><span class="sxs-lookup"><span data-stu-id="f2794-130">The XPath query in the template returns all the **\<Order>** elements with a CustomerID of less than 3.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="KeyFields1.xml">  
            /Order[@CustomerID < 3]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="f2794-131">Путь к каталогу для схемы сопоставления (KeyFields1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="f2794-131">The directory path specified for the mapping schema (KeyFields1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="f2794-132">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="f2794-132">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields1.xml"  
    ```  
  
3.  <span data-ttu-id="f2794-133">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="f2794-133">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="f2794-134">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f2794-134">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="f2794-135">Ниже приведен частичный результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="f2794-135">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
    <Order SalesOrderID="43860" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="44501" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="45283" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    .....  
</ROOT>  
```  
  
### <a name="b-specifying-sqlkey-fields-to-produce-proper-nesting-in-the-result"></a><span data-ttu-id="f2794-136">Б.</span><span class="sxs-lookup"><span data-stu-id="f2794-136">B.</span></span> <span data-ttu-id="f2794-137">Указание sql:key-fields для получения правильной вложенности в результате</span><span class="sxs-lookup"><span data-stu-id="f2794-137">Specifying sql:key-fields to produce proper nesting in the result</span></span>  
 <span data-ttu-id="f2794-138">В следующей схеме иерархия не указана с помощью **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="f2794-138">In the following schema, there is no hierarchy specified using **\<sql:relationship>**.</span></span> <span data-ttu-id="f2794-139">В схеме все еще требуется указать заметку `sql:key-fields`, чтобы уникальным образом идентифицировать сотрудников в таблице HumanResources.Employee.</span><span class="sxs-lookup"><span data-stu-id="f2794-139">The schema still requires specifying the `sql:key-fields` annotation to uniquely identify employees in the HumanResources.Employee table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="HumanResources.Employee" sql:key-fields="EmployeeID" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Title">  
          <xsd:complexType>  
            <xsd:simpleContent>  
              <xsd:extension base="xsd:string">  
                 <xsd:attribute name="EmployeeID" type="xsd:integer" />  
              </xsd:extension>  
            </xsd:simpleContent>  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
   </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="f2794-140">Создание рабочего образца этой схемы</span><span class="sxs-lookup"><span data-stu-id="f2794-140">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="f2794-141">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="f2794-141">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="f2794-142">Сохраните файл под именем KeyFields2.xml.</span><span class="sxs-lookup"><span data-stu-id="f2794-142">Save the file as KeyFields2.xml.</span></span>  
  
2.  <span data-ttu-id="f2794-143">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="f2794-143">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="f2794-144">Сохраните файл под именем KeyFields2T.xml в том же каталоге, в котором был сохранен файл KeyFields2.xml.</span><span class="sxs-lookup"><span data-stu-id="f2794-144">Save the file as KeyFields2T.xml in the same directory where you saved KeyFields2.xml.</span></span> <span data-ttu-id="f2794-145">Запрос XPath в шаблоне возвращает все **\<HumanResources.Employee>** элементы:</span><span class="sxs-lookup"><span data-stu-id="f2794-145">The XPath query in the template returns all the **\<HumanResources.Employee>** elements:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="KeyFields2.xml">  
        /HumanResources.Employee  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="f2794-146">Путь к каталогу для схемы сопоставления (KeyFields2.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="f2794-146">The directory path specified for the mapping schema (KeyFields2.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="f2794-147">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="f2794-147">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields2.xml"  
    ```  
  
3.  <span data-ttu-id="f2794-148">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="f2794-148">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="f2794-149">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f2794-149">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="f2794-150">Результат:</span><span class="sxs-lookup"><span data-stu-id="f2794-150">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <HumanResources.Employee>  
    <Title EmployeeID="1">Production Technician - WC60</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="2">Marketing Assistant</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="3">Engineering Manager</Title>   
  </HumanResources.Employee>  
  ...  
</ROOT>  
```  
  
  
