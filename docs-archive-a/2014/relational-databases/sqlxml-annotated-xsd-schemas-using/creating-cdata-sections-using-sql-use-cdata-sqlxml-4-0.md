---
title: 'Создание разделов CDATA с помощью SQL: use-CDATA (SQLXML 4,0) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- markup characters [SQLXML]
- special characters [SQLXML]
- use-cdata annotation
- plain text [SQLXML]
- CDATA sections
- escaping blocks of text [SQLXML]
- annotated XSD schemas, CDATA sections
- sql:use-cdata
ms.assetid: 26d2b9dc-f857-44ff-bcd4-aaf64ff809d0
author: rothja
ms.author: jroth
ms.openlocfilehash: c0ba0787efbda400590a75f0f3529e3df8819e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667653"
---
# <a name="creating-cdata-sections-using-sqluse-cdata-sqlxml-40"></a><span data-ttu-id="7c8e8-102">Создание разделов CDATA с использованием sql:use-cdata (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7c8e8-102">Creating CDATA Sections Using sql:use-cdata (SQLXML 4.0)</span></span>
  <span data-ttu-id="7c8e8-103">В XML разделы CDATA используются для экранирования блоков текста, содержащих символы, которые в противном случае распознаются как символы разметки.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-103">In XML, CDATA sections are used to escape blocks of text that contain characters that would otherwise be recognized as markup characters.</span></span>  
  
 <span data-ttu-id="7c8e8-104">База данных в Майкрософт [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] иногда может содержать символы, которые обрабатываются синтаксическим анализатором XML как символы разметки, например угловые скобки ( \< and > ), символ "меньше или равно" (<=), а амперсанд (&) обрабатываются как символы разметки.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-104">A database in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can sometimes contain characters that are treated as markup characters by the XML parser; for example, angle brackets (\< and >), the less-than-or-equal-to symbol (<=), and the ampersand (&) are treated as markup characters.</span></span> <span data-ttu-id="7c8e8-105">Но специальные символы такого типа можно заключить в раздел CDATA во избежание их обработки в качестве символов разметки.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-105">However, you can wrap this type of special characters in a CDATA section to prevent them from being treated as markup characters.</span></span> <span data-ttu-id="7c8e8-106">Текст в разделе CDATA обрабатывается средством синтаксического анализа XML как простой текст.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-106">The text within the CDATA section is treated by the XML parser as plain text.</span></span>  
  
 <span data-ttu-id="7c8e8-107">Заметка `sql:use-cdata` используется для указания на то, что данные, возвращаемые [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], необходимо ввести в раздел CDATA (т. е. заметка указывает, должно ли значение из столбца, обозначенного заметкой `sql:field`, быть заключено в раздел CDATA).</span><span class="sxs-lookup"><span data-stu-id="7c8e8-107">The `sql:use-cdata` annotation is used to specify that the data returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should be wrapped in a CDATA section (that is, it indicates whether the value from a column that is specified by `sql:field` should be enclosed in a CDATA section).</span></span> <span data-ttu-id="7c8e8-108">Заметку `sql:use-cdata` можно задавать только для элементов, которые сопоставляются со столбцом базы данных.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-108">The `sql:use-cdata` annotation can be specified only on elements that map to a database column.</span></span>  
  
 <span data-ttu-id="7c8e8-109">Заметка `sql:use-cdata` имеет логическое значение (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="7c8e8-109">The `sql:use-cdata` annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="7c8e8-110">Допустимые значения: 0, 1, true и false.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-110">The acceptable values are 0, 1, true, and false.</span></span>  
  
 <span data-ttu-id="7c8e8-111">Эту заметку нельзя использовать с `sql:url-encode` или для типов атрибутов ID, IDREF, IDREFS, NMTOKEN и NMTOKENS.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-111">This annotation cannot be used with `sql:url-encode` or on the ID, IDREF, IDREFS, NMTOKEN, and NMTOKENS attribute types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7c8e8-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="7c8e8-112">Examples</span></span>  
 <span data-ttu-id="7c8e8-113">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-113">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="7c8e8-114">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="7c8e8-114">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqluse-cdata-on-an-element"></a><span data-ttu-id="7c8e8-115">A.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-115">A.</span></span> <span data-ttu-id="7c8e8-116">Указание заметки sql:use-cdata для элемента</span><span class="sxs-lookup"><span data-stu-id="7c8e8-116">Specifying sql:use-cdata on an element</span></span>  
 <span data-ttu-id="7c8e8-117">В следующей схеме `sql:use-cdata` для параметра в элементе задано значение 1 (true) **\<AddressLine1>** **\<Address>** .</span><span class="sxs-lookup"><span data-stu-id="7c8e8-117">In the following schema, `sql:use-cdata` is set to 1 (True) for the **\<AddressLine1>** within the **\<Address>** element.</span></span> <span data-ttu-id="7c8e8-118">В результате этого данные возвращаются в разделе CDATA.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-118">As a result, the data is returned in a CDATA section.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Address"   
               sql:relation="Person.Address"   
               sql:key-fields="AddressID" >  
   <xsd:complexType>  
        <xsd:sequence>  
          <xsd:element name="AddressID"  type="xsd:string" />  
          <xsd:element name="AddressLine1" type="xsd:string"   
                       sql:use-cdata="1" />  
        </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="7c8e8-119">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="7c8e8-119">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="7c8e8-120">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-120">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="7c8e8-121">Сохраните этот файл с именем UseCData.xml.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-121">Save the file as UseCData.xml.</span></span>  
  
2.  <span data-ttu-id="7c8e8-122">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-122">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="7c8e8-123">Сохраните этот файл под именем UseCDataT.xml в том же каталоге, в котором был сохранен файл UseCData.xml.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-123">Save the file as UseCDataT.xml in the same directory where you saved UseCData.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="UseCData.xml">  
            /Address[AddressID < 11]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="7c8e8-124">Путь к каталогу схемы сопоставления (файл UseCData.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-124">The directory path specified for the mapping schema (UseCData.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="7c8e8-125">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="7c8e8-125">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\UseCData.xml"  
    ```  
  
3.  <span data-ttu-id="7c8e8-126">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-126">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="7c8e8-127">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7c8e8-127">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="7c8e8-128">Ниже приведен частичный результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="7c8e8-128">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Address>   
    <AddressID>1</CustomerID>   
    <AddressLine1>   
      <![CDATA[ 1970 Napa Ct.  ]]>   
    </AddressLine1>   
  </Address>  
  <Address>  
    <AddressLine1>   
      <![CDATA[ 9833 Mt. Dias Blv. ]]>   
    </AddressLine1>   
  </Address>  
  ...  
</ROOT>  
```  
  
  
