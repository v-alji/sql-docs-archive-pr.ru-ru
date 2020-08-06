---
title: Использование схем XSD с заметками в запросах (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML]
- inline schemas [SQLXML]
- XPath queries [SQLXML], annotated XSD schemas in queries
- queries [SQLXML], annotated XSD schemas
- retrieving data
- mapping schema [SQLXML], queries
- multiple inline schemas
- annotated XSD schemas, queries
- XSD schemas [SQLXML], queries
- templates [SQLXML], annotated XSD schemas in queries
ms.assetid: 927a30a2-eae8-420d-851d-551c5f884f3c
author: rothja
ms.author: jroth
ms.openlocfilehash: c3038ea234f707da7a87a030cb4110510f5a77c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665942"
---
# <a name="using-annotated-xsd-schemas-in-queries-sqlxml-40"></a><span data-ttu-id="70fa0-102">Использование схем XSD с заметками в запросах (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="70fa0-102">Using Annotated XSD Schemas in Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="70fa0-103">Для получения данных из базы данных путем указания запроса XPath в шаблоне к схеме XSD можно задавать запросы к аннотированным схемам.</span><span class="sxs-lookup"><span data-stu-id="70fa0-103">You can specify queries against an annotated schema to retrieve data from the database by specifying XPath queries in a template against the XSD schema.</span></span>  
  
 <span data-ttu-id="70fa0-104">**\<sql:xpath-query>** Элемент позволяет указать запрос XPath к XML-представлению, определяемому схемой с заметками.</span><span class="sxs-lookup"><span data-stu-id="70fa0-104">The **\<sql:xpath-query>** element allows you to specify an XPath query against the XML view that is defined by the annotated schema.</span></span> <span data-ttu-id="70fa0-105">Схема с заметками, в которой будет выполняться запрос XPath, определяется с помощью `mapping-schema` атрибута **\<sql:xpath-query>** элемента.</span><span class="sxs-lookup"><span data-stu-id="70fa0-105">The annotated schema against which the XPath query is to be executed is identified by using the `mapping-schema` attribute of the **\<sql:xpath-query>** element.</span></span>  
  
 <span data-ttu-id="70fa0-106">Шаблоны являются допустимыми XML-документами, которые содержат один или несколько запросов.</span><span class="sxs-lookup"><span data-stu-id="70fa0-106">Templates are valid XML documents that contain one or more queries.</span></span> <span data-ttu-id="70fa0-107">Запросы FOR XML и XPath возвращают фрагмент документа.</span><span class="sxs-lookup"><span data-stu-id="70fa0-107">The FOR XML and XPath queries return a document fragment.</span></span> <span data-ttu-id="70fa0-108">Шаблоны выполняют функцию контейнеров для фрагментов документов. Таким образом, они обеспечивают возможность указания единственного элемента верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="70fa0-108">Templates act as containers for the document fragments; templates thus provide a way to specify a single, top-level element.</span></span>  
  
 <span data-ttu-id="70fa0-109">В примерах из этого раздела шаблоны задают запрос XPath по схеме с заметками для получения данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="70fa0-109">The examples in this topic use templates to specify an XPath query against an annotated schema to retrieve data from the database.</span></span>  
  
 <span data-ttu-id="70fa0-110">В качестве примера рассмотрим следующую аннотированную схему.</span><span class="sxs-lookup"><span data-stu-id="70fa0-110">For example, consider this annotated schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID" type="xsd:string" />   
       <xsd:attribute name="FirstName" type="xsd:string" />   
       <xsd:attribute name="LastName"  type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="70fa0-111">Для иллюстрации эта схема XSD хранится в файле Schema2.xml.</span><span class="sxs-lookup"><span data-stu-id="70fa0-111">For the purpose of illustration, this XSD schema is stored in file named Schema2.xml.</span></span> <span data-ttu-id="70fa0-112">Затем можно выполнить запрос XPath к аннотированной схеме, определенной в следующем файле шаблона (Schema2T.xml).</span><span class="sxs-lookup"><span data-stu-id="70fa0-112">You could then have an XPath query against the annotated schema specified in the following template file (Schema2T.xml):</span></span>  
  
```  
<sql:xpath-query   
     xmlns:sql="urn:schemas-microsoft-com:xmlsql"  
     >  
          Person.Contact[@ContactID="1"]  
</sql:xpath-query>  
```  
  
 <span data-ttu-id="70fa0-113">Затем можно создать и запустить тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить запрос, содержащийся в файле шаблона.</span><span class="sxs-lookup"><span data-stu-id="70fa0-113">You can then create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the query as part of a template file.</span></span> <span data-ttu-id="70fa0-114">Дополнительные сведения см. [в разделе схемы XDR с Заметками &#40;не рекомендуется в SQLXML 4,0&#41;](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="70fa0-114">For more information, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="using-inline-mapping-schemas"></a><span data-ttu-id="70fa0-115">Использование встроенных схем сопоставления</span><span class="sxs-lookup"><span data-stu-id="70fa0-115">Using Inline Mapping Schemas</span></span>  
 <span data-ttu-id="70fa0-116">Аннотированную схему можно включить непосредственно в шаблон, а затем выполнить определенный в шаблоне запрос XPath к встроенной схеме.</span><span class="sxs-lookup"><span data-stu-id="70fa0-116">An annotated schema can be included directly in a template, and then an XPath query can be specified in the template against the inline schema.</span></span> <span data-ttu-id="70fa0-117">Шаблон может также быть диаграммой обновления.</span><span class="sxs-lookup"><span data-stu-id="70fa0-117">The template can also be an updategram.</span></span>  
  
 <span data-ttu-id="70fa0-118">Шаблон может включать несколько встроенных схем.</span><span class="sxs-lookup"><span data-stu-id="70fa0-118">A template can include multiple inline schemas.</span></span> <span data-ttu-id="70fa0-119">Чтобы использовать встроенную схему, включенную в шаблон, укажите атрибут **ID** с уникальным значением в **\<xsd:schema>** элементе, а затем используйте **#idvalue** для ссылки на встроенную схему.</span><span class="sxs-lookup"><span data-stu-id="70fa0-119">To use an inline schema that is included in a template, specify the **id** attribute with a unique value on the **\<xsd:schema>** element, and then use **#idvalue** to reference the inline schema.</span></span> <span data-ttu-id="70fa0-120">Атрибут **ID** идентичен поведению **SQL: ID** ({URN: schemas-microsoft-com: XML-SQL} ID), используемому в схемах XDR.</span><span class="sxs-lookup"><span data-stu-id="70fa0-120">The **id** attribute is identical in behavior to the **sql:id** ({urn:schemas-microsoft-com:xml-sql}id) used in XDR schemas.</span></span>  
  
 <span data-ttu-id="70fa0-121">Например, следующий шаблон определяет две встроенные аннотированные схемы.</span><span class="sxs-lookup"><span data-stu-id="70fa0-121">For example, the following template specifies two inline-annotated schemas:</span></span>  
  
```  
<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'>  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
        xmlns:ms='urn:schemas-microsoft-com:mapping-schema'  
        id='InLineSchema1' sql:is-mapping-schema='1'>  
  <xsd:element name='Employees' ms:relation='HumanResources.Employee'>  
    <xsd:complexType>  
      <xsd:attribute name='LoginID'   
                     type='xsd:string'/>  
      <xsd:attribute name='Title'   
                     type='xsd:string'/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
        xmlns:ms='urn:schemas-microsoft-com:mapping-schema'  
        id='InLineSchema2' sql:is-mapping-schema='1'>  
  <xsd:element name='Contacts' ms:relation='Person.Contact'>  
    <xsd:complexType>  
  
      <xsd:attribute name='ContactID'   
                     type='xsd:string' />  
      <xsd:attribute name='FirstName'   
                     type='xsd:string' />  
      <xsd:attribute name='LastName'   
                     type='xsd:string' />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
  
<sql:xpath-query xmlns:sql='urn:schemas-microsoft-com:xml-sql'   
        mapping-schema='#InLineSchema1'>  
    /Employees[@LoginID='adventure-works\guy1']  
</sql:xpath-query>  
  
<sql:xpath-query xmlns:sql='urn:schemas-microsoft-com:xml-sql'   
        mapping-schema='#InLineSchema2'>  
    /Contacts[@ContactID='1']  
</sql:xpath-query>  
</ROOT>  
```  
  
 <span data-ttu-id="70fa0-122">В шаблоне также задано два запроса XPath.</span><span class="sxs-lookup"><span data-stu-id="70fa0-122">The template also specifies two XPath queries.</span></span> <span data-ttu-id="70fa0-123">Каждый из **\<xpath-query>** элементов однозначно определяет схему сопоставления, указывая `mapping-schema` атрибут.</span><span class="sxs-lookup"><span data-stu-id="70fa0-123">Each of the **\<xpath-query>** elements uniquely identifies the mapping schema by specifying the `mapping-schema` attribute.</span></span>  
  
 <span data-ttu-id="70fa0-124">При указании встроенной схемы в шаблоне `sql:is-mapping-schema` заметка также должна быть указана в **\<xsd:schema>** элементе.</span><span class="sxs-lookup"><span data-stu-id="70fa0-124">When you specify an inline schema in the template, the `sql:is-mapping-schema` annotation must also be specified on the **\<xsd:schema>** element.</span></span> <span data-ttu-id="70fa0-125">Заметка `sql:is-mapping-schema` имеет логическое значение (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="70fa0-125">The `sql:is-mapping-schema` takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="70fa0-126">Встроенная схема с **SQL: schema-Mapping-Schema = "1"** рассматривается как встроенная схема с заметками и не возвращается в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="70fa0-126">An inline schema with **sql:is-mapping-schema="1"** is treated as inline annotated schema and is not returned in the XML document.</span></span>  
  
 <span data-ttu-id="70fa0-127">Заметка `sql:is-mapping-schema` принадлежит пространству имен шаблона `urn:schemas-microsoft-com:xml-sql`.</span><span class="sxs-lookup"><span data-stu-id="70fa0-127">The `sql:is-mapping-schema` annotation belongs to the template namespace `urn:schemas-microsoft-com:xml-sql`.</span></span>  
  
 <span data-ttu-id="70fa0-128">Чтобы протестировать этот пример, сохраните шаблон (InlineSchemaTemplate.xml) в локальном каталоге, а затем создайте и выполните тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs) для запуска шаблона.</span><span class="sxs-lookup"><span data-stu-id="70fa0-128">To test this example, save the template (InlineSchemaTemplate.xml) in a local directory and then create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="70fa0-129">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="70fa0-129">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="70fa0-130">Помимо указания `mapping-schema` атрибута для **\<sql:xpath-query>** элемента в шаблоне (при наличии запроса XPath) или для **\<updg:sync>** элемента в диаграмма обновления, можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="70fa0-130">In addition to specifying the `mapping-schema` attribute on the **\<sql:xpath-query>** element in a template (when there is an XPath query), or on **\<updg:sync>** element in an updategram, you can do the following:</span></span>  
  
-   <span data-ttu-id="70fa0-131">Укажите `mapping-schema` атрибут **\<ROOT>** элемента (глобальное объявление) в шаблоне.</span><span class="sxs-lookup"><span data-stu-id="70fa0-131">Specify the `mapping-schema` attribute on the **\<ROOT>** element (global declaration) in the template.</span></span> <span data-ttu-id="70fa0-132">Теперь эта схема сопоставления стала схемой по умолчанию и будет использоваться всеми узлами XPath и диаграммами обновления без явного указания заметки `mapping-schema`.</span><span class="sxs-lookup"><span data-stu-id="70fa0-132">This mapping schema then becomes the default schema that will be used by all XPath and updategram nodes that have no explicit `mapping-schema` annotation.</span></span>  
  
-   <span data-ttu-id="70fa0-133">Укажите атрибут `mapping schema` с помощью объекта `Command` ADO.</span><span class="sxs-lookup"><span data-stu-id="70fa0-133">Specify the `mapping schema` attribute by using the ADO `Command` object.</span></span>  
  
 <span data-ttu-id="70fa0-134">`mapping-schema`Атрибут, указанный в **\<xpath-query>** элементе или, **\<updg:sync>** имеет наивысший приоритет; объект ADO `Command` имеет самый низкий приоритет.</span><span class="sxs-lookup"><span data-stu-id="70fa0-134">The `mapping-schema` attribute that is specified on the **\<xpath-query>** or **\<updg:sync>** element has the highest precedence; the ADO `Command` object has the lowest precedence.</span></span>  
  
 <span data-ttu-id="70fa0-135">Обратите внимание, что если вы укажете запрос XPath в шаблоне и не укажете схему сопоставления, в которой выполняется запрос XPath, запрос XPath рассматривается как запрос типа **DBOBJECT** .</span><span class="sxs-lookup"><span data-stu-id="70fa0-135">Note that if you specify an XPath query in a template and do not specify a mapping schema against which the XPath query is executed, the XPath query is treated as a **dbobject** type query.</span></span> <span data-ttu-id="70fa0-136">Например, рассмотрим следующий шаблон.</span><span class="sxs-lookup"><span data-stu-id="70fa0-136">For example, consider this template:</span></span>  
  
```  
<sql:xpath-query   
     xmlns:sql="urn:schemas-microsoft-com:xmlsql">  
          Production.ProductPhoto[@ProductPhotoID='100']/@LargePhoto  
</sql:xpath-query>  
```  
  
 <span data-ttu-id="70fa0-137">В шаблоне определяется запрос XPath, но не задаются схемы сопоставления.</span><span class="sxs-lookup"><span data-stu-id="70fa0-137">The template specifies an XPath query but it does not specify a mapping schema.</span></span> <span data-ttu-id="70fa0-138">Поэтому этот запрос рассматривается как запрос типа **DBOBJECT** , в котором Production. ProductPhoto — это имя таблицы, а @ProductPhotoID = "100" — это предикат, который находит фотографию продукта со значением идентификатора 100.</span><span class="sxs-lookup"><span data-stu-id="70fa0-138">Therefore, this query is treated as a **dbobject** type query in which Production.ProductPhoto is the table name and @ProductPhotoID='100' is a predicate that finds a product photo with the ID value of 100.</span></span> <span data-ttu-id="70fa0-139">@LargePhotoстолбец, из которого извлекается значение.</span><span class="sxs-lookup"><span data-stu-id="70fa0-139">@LargePhoto is the column from which to retrieve the value.</span></span>  
  
  
