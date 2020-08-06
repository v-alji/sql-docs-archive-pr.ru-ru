---
title: 'Запрос URL-ссылок на данные большого двоичного объекта с помощью SQL: Encoded (SQLXML 4,0) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:encode
- encode annotation
- URL references to BLOB data [SQLXML]
- references to BLOB data [SQLXML]
- annotated XSD schemas, URL references to BLOB data
- requesting URL references to BLOB data
- BLOBs, URL references
- Base 64-encoded format
ms.assetid: 2f8cd93b-c636-462b-8291-167197233ee0
author: rothja
ms.author: jroth
ms.openlocfilehash: 8a9f5edcfab4a9d7307327d97bc2099c78c666c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667645"
---
# <a name="requesting-url-references-to-blob-data-using-sqlencode-sqlxml-40"></a><span data-ttu-id="de76d-102">Получение URL-ссылок на данные BLOB с использованием sql:encode (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="de76d-102">Requesting URL References to BLOB Data Using sql:encode (SQLXML 4.0)</span></span>
  <span data-ttu-id="de76d-103">В схеме XSD с заметками, когда атрибут (или элемент) сопоставляется со столбцом BLOB в Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], данные внутри XML возвращаются в формате Base 64.</span><span class="sxs-lookup"><span data-stu-id="de76d-103">In an annotated XSD schema, when an attribute (or element) is mapped to a BLOB column in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data is returned in Base 64-encoded format within XML.</span></span>  
  
 <span data-ttu-id="de76d-104">Если требуется возвратить ссылку на эти данные (идентификатор URI), которую впоследствии можно будет использовать для получения данных BLOB в двоичном формате, укажите заметку `sql:encode`.</span><span class="sxs-lookup"><span data-stu-id="de76d-104">If you want a reference to the data (a URI) to be returned that can be used later to retrieve the BLOB data in a binary format, specify the `sql:encode` annotation.</span></span> <span data-ttu-id="de76d-105">Заметку `sql:encode` можно указывать для атрибута или элемента простого типа.</span><span class="sxs-lookup"><span data-stu-id="de76d-105">You can specify `sql:encode` on an attribute or element of simple type.</span></span>  
  
 <span data-ttu-id="de76d-106">Задайте заметку `sql:encode`, чтобы указать, что необходимо вернуть URL-адрес поля вместо значения поля.</span><span class="sxs-lookup"><span data-stu-id="de76d-106">Specify the `sql:encode` annotation to indicate that a URL to the field should be returned instead of the value of the field.</span></span> <span data-ttu-id="de76d-107">При формировании одноэлементного выбора в URL-адресе заметка `sql:encode` зависит от первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="de76d-107">`sql:encode` depends on the primary key to generate a singleton select in the URL.</span></span> <span data-ttu-id="de76d-108">Первичный ключ можно указать при помощи заметки `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="de76d-108">The primary key can be specified using the `sql:key-fields` annotation.</span></span>  
  
 <span data-ttu-id="de76d-109">Заметке `sql:encode` можно назначить значение «url» или «default».</span><span class="sxs-lookup"><span data-stu-id="de76d-109">The `sql:encode` annotation can be assigned the "url" or the "default" value.</span></span> <span data-ttu-id="de76d-110">Значение «default» возвращает данные в формате Base 64.</span><span class="sxs-lookup"><span data-stu-id="de76d-110">A value of "default" returns data in Base 64-encoded format.</span></span>  
  
 <span data-ttu-id="de76d-111">Заметку `sql:encode` нельзя использовать с `sql:use-cdata` или для типов атрибутов ID, IDREF, IDREFS, NMTOKEN и NMTOKENS.</span><span class="sxs-lookup"><span data-stu-id="de76d-111">The `sql:encode` annotation cannot be used with `sql:use-cdata` or on the ID, IDREF, IDREFS, NMTOKEN, or NMTOKENS attribute types.</span></span> <span data-ttu-id="de76d-112">Его также можно использовать с атрибутом **fixed** XSD.</span><span class="sxs-lookup"><span data-stu-id="de76d-112">It can also not be used with XSD **fixed** attribute.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de76d-113">Столбцы типа BLOB невозможно использовать, как часть ключа или внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="de76d-113">BLOB-type columns cannot be used as a part of a key or foreign key.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="de76d-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="de76d-114">Examples</span></span>  
 <span data-ttu-id="de76d-115">Чтобы создать рабочие образцы на основе следующих примеров, необходимо выполнить определенные требования.</span><span class="sxs-lookup"><span data-stu-id="de76d-115">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="de76d-116">Дополнительные сведения см. в разделе [требования для запуска примеров SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="de76d-116">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlencode-to-obtain-a-url-reference-to-blob-data"></a><span data-ttu-id="de76d-117">A.</span><span class="sxs-lookup"><span data-stu-id="de76d-117">A.</span></span> <span data-ttu-id="de76d-118">Указание заметки sql:encode для получения URL-ссылки на данные BLOB</span><span class="sxs-lookup"><span data-stu-id="de76d-118">Specifying sql:encode to obtain a URL reference to BLOB data</span></span>  
 <span data-ttu-id="de76d-119">В этом примере схема сопоставления задает `sql:encode` атрибут **LargePhoto** для получения ссылки URI на определенную фотографию продукта (вместо извлечения двоичных данных в формате Base 64).</span><span class="sxs-lookup"><span data-stu-id="de76d-119">In this example, the mapping schema specifies `sql:encode` on the **LargePhoto** attribute to retrieve the URI reference to a specific product photo (instead of retrieving the binary data in Base 64-encoded format).</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="ProductPhoto" sql:relation="Production.ProductPhoto"   
               sql:key-fields="ProductPhotoID" >  
   <xsd:complexType>  
      <xsd:attribute name="ProductPhotoID"  type="xsd:int"  />  
     <xsd:attribute name="LargePhoto" type="xsd:string" sql:encode="url" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="de76d-120">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="de76d-120">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="de76d-121">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="de76d-121">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="de76d-122">Сохраните файл с именем sqlEncode.xml.</span><span class="sxs-lookup"><span data-stu-id="de76d-122">Save the file as sqlEncode.xml.</span></span>  
  
2.  <span data-ttu-id="de76d-123">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="de76d-123">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="de76d-124">Сохраните файл под именем sqlEncodeT.xml в том же каталоге, где был сохранен файл sqlEncode.xml.</span><span class="sxs-lookup"><span data-stu-id="de76d-124">Save the file as sqlEncodeT.xml in the same directory where you saved sqlEncode.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sqlEncode.xml">  
            /ProductPhoto[@ProductPhotoID=100]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="de76d-125">Путь к каталогу схемы сопоставления (файл sqlEncode.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="de76d-125">The directory path specified for the mapping schema (sqlEncode.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="de76d-126">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="de76d-126">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\sqlEncode.xml"  
    ```  
  
3.  <span data-ttu-id="de76d-127">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="de76d-127">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="de76d-128">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="de76d-128">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="de76d-129">Результат:</span><span class="sxs-lookup"><span data-stu-id="de76d-129">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <ProductPhoto ProductPhotoID="100"  
                 LargePhoto="dbobject/Production.ProductPhoto[@ProductPhotoID="100"]/@LargePhoto" />   
</ROOT>  
```  
  
  
