---
title: 'Исключение элементов схемы из результирующего XML-документа с помощью SQL: сопоставлено (SQLXML 4,0) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- annotated XSD schemas, excluding schema elements
- mapped annotation
- table mapping [SQLXML], excluding schema elements
- sql:mapped
- excluding schema elements
- element mapping [SQLXML], excluding schema elements
- column mapping [SQLXML]
- XSD schemas [SQLXML], excluding schema elements
- attribute mapping [SQLXML], excluding schema elements
- table/view mapping [SQLXML], excluding schema elements
ms.assetid: 7d2649dd-0038-4a2c-b16d-f80f7c306966
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c79ae005b9630fcbfcd16bfc22c2aeb21b7bf9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664120"
---
# <a name="excluding-schema-elements-from-the-resulting-xml-document-using-sqlmapped-sqlxml-40"></a><span data-ttu-id="4bbfa-102">Исключение элементов схемы из результирующего XML-документа с помощью sql:mapped (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4bbfa-102">Excluding Schema Elements from the Resulting XML Document Using sql:mapped (SQLXML 4.0)</span></span>
  <span data-ttu-id="4bbfa-103">В результате сопоставления по умолчанию каждый элемент и атрибут в схеме XSD будет сопоставлен с таблицей и столбцом в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-103">Every element and attribute in the XSD schema maps to a database table/view and column because of the default mapping.</span></span> <span data-ttu-id="4bbfa-104">Если в схеме XSD нужно создать элемент, не сопоставленный никакой таблице, никакому представлению или столбцу базы данных и не фигурирующий в XML, нужно создать для него заметку `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-104">If you want to create an element in the XSD schema that does not map to any database table (view) or column and that does not appear in the XML, you can specify the `sql:mapped` annotation.</span></span>  
  
 <span data-ttu-id="4bbfa-105">Заметка `sql:mapped` особенно полезна, если схему нельзя изменять или она используется для проверки XML из других источников (при этом содержит данные, не хранящиеся в вашей базе данных).</span><span class="sxs-lookup"><span data-stu-id="4bbfa-105">The `sql:mapped` annotation is especially useful if the schema cannot be modified or if the schema is used to validate XML from other sources and yet contains data that is not stored in your database.</span></span> <span data-ttu-id="4bbfa-106">Заметка `sql:mapped` отличается от `sql:is-constant` тем, что несопоставленные элементы и атрибуты не фигурируют в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-106">The `sql:mapped` annotation differs from `sql:is-constant` in that the unmapped elements and attributes do not appear in the XML document.</span></span>  
  
 <span data-ttu-id="4bbfa-107">Заметка `sql:mapped` имеет логическое значение (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="4bbfa-107">The `sql:mapped` annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="4bbfa-108">Допустимые значения: 0, 1, true и false.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-108">The acceptable values are 0, 1, true, and false.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4bbfa-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="4bbfa-109">Examples</span></span>  
 <span data-ttu-id="4bbfa-110">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-110">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="4bbfa-111">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="4bbfa-111">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlmapped-annotation"></a><span data-ttu-id="4bbfa-112">A.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-112">A.</span></span> <span data-ttu-id="4bbfa-113">Задание заметки sql:mapped</span><span class="sxs-lookup"><span data-stu-id="4bbfa-113">Specifying the sql:mapped annotation</span></span>  
 <span data-ttu-id="4bbfa-114">Предположим, существует схема XSD, полученная из другого источника.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-114">Assume you have an XSD schema from some other source.</span></span> <span data-ttu-id="4bbfa-115">Эта схема XSD состоит из **\<Person.Contact>** элемента с атрибутами **ContactID**, **FirstName**, **LastName**и **HomeAddress** .</span><span class="sxs-lookup"><span data-stu-id="4bbfa-115">This XSD schema consists of an **\<Person.Contact>** element with **ContactID**, **FirstName**, **LastName**, and **HomeAddress** attributes.</span></span>  
  
 <span data-ttu-id="4bbfa-116">При сопоставлении этой схемы XSD с таблицей Person. Contact в базе данных AdventureWorks в `sql:mapped` атрибуте **HomeAddress** указывается, потому что в таблице Employees не хранятся домашние адреса сотрудников.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-116">In mapping this XSD schema to the Person.Contact table in the AdventureWorks database, `sql:mapped` is specified on the **HomeAddress** attribute because the Employees table does not store the home addresses of employees.</span></span> <span data-ttu-id="4bbfa-117">В результате этот атрибут не сопоставлен с базой данных и не возвращается в результирующем XML-документе в ответ на запрос XPath к схеме сопоставления.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-117">As a result, this attribute is not mapped to the database and is not returned in the resulting XML document when an XPath query is specified against the mapping schema.</span></span>  
  
 <span data-ttu-id="4bbfa-118">Для остальной части схемы используется сопоставление по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-118">Default mapping takes place for the rest of the schema.</span></span> <span data-ttu-id="4bbfa-119">**\<Person.Contact>** Элемент сопоставляется с таблицей Person. Contact, и все атрибуты сопоставляются со столбцами с тем же именем в таблице Person. Contact.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-119">The **\<Person.Contact>** element maps to the Person.Contact table, and all the attributes map to the columns with the same name in the Person.Contact table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:attribute name="ContactID"   type="xsd:string"/>  
      <xsd:attribute name="FirstName"    type="xsd:string" />  
      <xsd:attribute name="LastName"     type="xsd:string" />  
      <xsd:attribute name="HomeAddress" type="xsd:string"   
                     sql:mapped="false" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="4bbfa-120">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="4bbfa-120">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="4bbfa-121">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-121">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="4bbfa-122">Сохраните файл под именем sql-mapped.xml.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-122">Save the file as sql-mapped.xml.</span></span>  
  
2.  <span data-ttu-id="4bbfa-123">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-123">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="4bbfa-124">Сохраните файл под именем sql-mappedT.xml в том же каталоге, где был сохранен файл sql-mapped.xml.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-124">Save the file as sql-mappedT.xml in the same directory where you saved sql-mapped.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-mapped.xml">  
            /Person.Contact[@ContactID < 10]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="4bbfa-125">Путь к каталогу для схемы сопоставления (MySchema.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-125">The directory path specified for the mapping schema (MySchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="4bbfa-126">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="4bbfa-126">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\sql-mapped.xml"  
    ```  
  
3.  <span data-ttu-id="4bbfa-127">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-127">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4bbfa-128">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4bbfa-128">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="4bbfa-129">Результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="4bbfa-129">This is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel" />   
  <Person.Contact ContactID="3" FirstName="Kim" LastName="Abercrombie" />   
  <Person.Contact ContactID="4" FirstName="Humberto" LastName="Acevedo" />   
  <Person.Contact ContactID="5" FirstName="Pilar" LastName="Ackerman" />   
  <Person.Contact ContactID="6" FirstName="Frances" LastName="Adams" />   
  <Person.Contact ContactID="7" FirstName="Margaret" LastName="Smith" />   
  <Person.Contact ContactID="8" FirstName="Carla" LastName="Adams" />   
  <Person.Contact ContactID="9" FirstName="Jay" LastName="Adams" />   
</ROOT>  
```  
  
 <span data-ttu-id="4bbfa-130">Обратите внимание, что поля ContactID, FirstName и LastName присутствуют, а HomeAddress — нет, потому что в схеме сопоставления было задано значение 0 для атрибута `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="4bbfa-130">Note that the ContactID, FirstName, and LastName are present, but HomeAddress is not because the mapping schema specified 0 for the `sql:mapped` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bbfa-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="4bbfa-131">See Also</span></span>  
 [<span data-ttu-id="4bbfa-132">Сопоставление элементов и атрибутов XSD с таблицами и столбцами по умолчанию &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4bbfa-132">Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
  
  
