---
title: 'Извлечение невостребованных данных с помощью SQL: overflow-field (SQLXML 4,0) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- unconsumed data
- storing unconsumed data
- retrieving unconsumed data
- annotated XSD schemas, unconsumed data
- overflow data [SQLXML]
- sql:overflow-field
ms.assetid: 8526998d-b47d-4a32-8dc2-7f50a8d11097
author: rothja
ms.author: jroth
ms.openlocfilehash: 796fda9428954c5f18c5d37b353de9fd4122551e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667644"
---
# <a name="retrieving-unconsumed-data-using-the-sqloverflow-field-sqlxml-40"></a><span data-ttu-id="11940-102">Получение невостребованных данных с помощью sql:overflow-field (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="11940-102">Retrieving Unconsumed Data Using the sql:overflow-field (SQLXML 4.0)</span></span>
  <span data-ttu-id="11940-103">Когда в базу данных с помощью функции OPENXML [!INCLUDE[tsql](../../includes/tsql-md.md)] вставляются записи из XML-документа, все невостребованные данные из исходного XML-документа могут быть сохранены в столбце.</span><span class="sxs-lookup"><span data-stu-id="11940-103">When records are inserted in a database from an XML document by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] OPENXML function, all the unconsumed data from the source XML document can be stored in a column.</span></span> <span data-ttu-id="11940-104">При считывании данных из базы данных с помощью схем с заметками можно указывать атрибут `sql:overflow-field` для идентификации столбца таблицы, в котором хранятся перегруженные данные.</span><span class="sxs-lookup"><span data-stu-id="11940-104">When you retrieve data from a database by using annotated schemas, you can specify the `sql:overflow-field` attribute to identify the column in the table in which the overflow data is stored.</span></span> <span data-ttu-id="11940-105">`sql:overflow-field`Атрибут может быть указан в **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="11940-105">The `sql:overflow-field` attribute can be specified on **\<element>**.</span></span>  
  
 <span data-ttu-id="11940-106">Затем эти данные можно получить одним из трех способов.</span><span class="sxs-lookup"><span data-stu-id="11940-106">This data is then retrieved in these ways:</span></span>  
  
-   <span data-ttu-id="11940-107">Атрибуты, сохраненные в столбце переполнения, добавляются к элементу, который содержит заметку `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="11940-107">Attributes stored in the overflow column are added to the element that contains the `sql:overflow-field` annotation.</span></span>  
  
-   <span data-ttu-id="11940-108">Дочерние элементы и их потомки, хранимые в столбце переполнения базы данных, добавляются в качестве дочерних элементов вслед за содержимым, которое явным образом указывается в схеме.</span><span class="sxs-lookup"><span data-stu-id="11940-108">The child elements and their descendents, stored in the overflow column in the database, are added as child elements following the content that is explicitly specified in the schema.</span></span> <span data-ttu-id="11940-109">(Порядок не сохраняется.)</span><span class="sxs-lookup"><span data-stu-id="11940-109">(No order is preserved.)</span></span>  
  
## <a name="examples"></a><span data-ttu-id="11940-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="11940-110">Examples</span></span>  
 <span data-ttu-id="11940-111">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="11940-111">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="11940-112">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="11940-112">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqloverflow-field-for-an-element"></a><span data-ttu-id="11940-113">A.</span><span class="sxs-lookup"><span data-stu-id="11940-113">A.</span></span> <span data-ttu-id="11940-114">Указание sql:overflow-field для элемента</span><span class="sxs-lookup"><span data-stu-id="11940-114">Specifying sql:overflow-field for an element</span></span>  
 <span data-ttu-id="11940-115">В данном примере предполагается, что был выполнен следующий скрипт, а значит, в базе данных tempdb имеется таблица Customers2:</span><span class="sxs-lookup"><span data-stu-id="11940-115">This example assumes that the following script has been run so that a table named Customers2 exists in the tempdb database:</span></span>  
  
```  
USE tempdb  
CREATE TABLE Customers2 (  
CustomerID       VARCHAR(10),   
ContactName    VARCHAR(30),   
AddressOverflow    NVARCHAR(500))  
  
GO  
INSERT INTO Customers2 VALUES (  
'ALFKI',   
'Joe',  
'<Address>  
  <Address1>Maple St.</Address1>  
  <Address2>Apt. E105</Address2>  
  <City>Seattle</City>  
  <State>WA</State>  
  <Zip>98147</Zip>  
 </Address>')  
GO  
```  
  
 <span data-ttu-id="11940-116">Кроме того, необходимо создать виртуальный каталог для базы данных tempdb, а также виртуальное имя шаблона `template` типа с именем template.</span><span class="sxs-lookup"><span data-stu-id="11940-116">In addition, you must create a virtual directory for the tempdb database-and a template virtual name of `template` type named "template".</span></span>  
  
 <span data-ttu-id="11940-117">В следующем примере схема сопоставления получает невостребованные данные, которые сохраняются в столбце AddressOverflow таблицы Customers2:</span><span class="sxs-lookup"><span data-stu-id="11940-117">In the following example, the mapping schema retrieves the unconsumed data that is stored in the AddressOverflow column of the Customers2 table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Customers2" sql:overflow-field="AddressOverflow" >  
    <xsd:complexType>  
      <xsd:attribute name="CustomerID"  type="xsd:integer"/>  
      <xsd:attribute name="ContactName"  type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="11940-118">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="11940-118">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="11940-119">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="11940-119">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="11940-120">Сохраните этот файл под именем Overflow.xml.</span><span class="sxs-lookup"><span data-stu-id="11940-120">Save the file as Overflow.xml.</span></span>  
  
2.  <span data-ttu-id="11940-121">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="11940-121">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="11940-122">Сохраните файл под именем OverflowT.xml в том же каталоге, где был сохранен файл Overflow.xml.</span><span class="sxs-lookup"><span data-stu-id="11940-122">Save the file as OverflowT.xml in the same directory where you saved Overflow.xml.</span></span> <span data-ttu-id="11940-123">Запрос из шаблона выбирает все записи из таблицы Customers2.</span><span class="sxs-lookup"><span data-stu-id="11940-123">The query in the template selects the records in the Customers2 table.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="Overflow.xml">  
            /Customers2  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="11940-124">Путь к каталогу для схемы сопоставления (Overflow.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="11940-124">The directory path specified for the mapping schema (Overflow.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="11940-125">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="11940-125">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\Overflow.xml"  
    ```  
  
3.  <span data-ttu-id="11940-126">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="11940-126">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="11940-127">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="11940-127">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="11940-128">Результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="11940-128">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customers2 CustomerID="ALFKI" ContactName="Joe">  
    <Address1>Maple St.</Address1>   
    <Address2>Apt. E105</Address2>   
    <City>Seattle</City>   
    <State>WA</State>   
    <Zip>98147</Zip>   
  </Customers2>  
</ROOT>  
```  
  
  
