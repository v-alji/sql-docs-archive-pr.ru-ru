---
title: 'SQL: сопоставлено (SQLXML 4,0) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapped annotation
- element mapping [SQLXML], XML Bulk Load
- attribute mapping [SQLXML], XML Bulk Load
- overflow data [SQLXML]
- sql:mapped
- column mapping [SQLXML]
ms.assetid: 7042741e-ce4d-4912-9c4a-d77194a028fc
author: rothja
ms.author: jroth
ms.openlocfilehash: 2cbccf271e069cd87860af672fed6c4bab462b41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664102"
---
# <a name="sqlmapped-sqlxml-40"></a><span data-ttu-id="39fe3-102">sql:mapped, заметка (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="39fe3-102">sql:mapped (SQLXML 4.0)</span></span>
  <span data-ttu-id="39fe3-103">При выполнении групповой загрузки XML `sql:mapped` заметка в схеме XSD обрабатывается, как ожидалось, то есть если схема сопоставления указывает `sql:mapped="false"` на какой-либо элемент или атрибут, при выполнении XML-загрузки не выполняется попытка сохранить связанные данные в соответствующем столбце.</span><span class="sxs-lookup"><span data-stu-id="39fe3-103">XML Bulk Load processes the `sql:mapped` annotation in the XSD schema as expected-that is, if the mapping schema specifies `sql:mapped="false"` for any element or attribute, XML Bulk Load does not attempt to store the associated data in the corresponding column.</span></span>  
  
 <span data-ttu-id="39fe3-104">Операция массовой загрузки XML пропускает несопоставляемые элементы и атрибуты (потому что они не описаны в схеме или помечены в схеме XSD заметкой `sql:mapped="false"`).</span><span class="sxs-lookup"><span data-stu-id="39fe3-104">XML Bulk Load ignores elements and attributes that are not mapped (either because they are not described in the schema, or because they are annotated in the XSD schema with `sql:mapped="false"`).</span></span> <span data-ttu-id="39fe3-105">Все несопоставляемые данные сохраняются в столбце переполнения, если он указан с помощью элемента `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="39fe3-105">All unmapped data goes into the overflow column, if such a column is specified by using `sql:overflow-field`.</span></span>  
  
 <span data-ttu-id="39fe3-106">В качестве примера рассмотрим следующую схему XSD.</span><span class="sxs-lookup"><span data-stu-id="39fe3-106">For example, consider this XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="ROOT" sql:is-constant="1">  
<xsd:complexType>  
<xsd:sequence>  
  <xsd:element name="Customers" sql:relation="Cust"  
                                sql:overflow-field="OverflowColumn" >  
   <xsd:complexType>  
       <xsd:attribute name="CustomerID"  type="xsd:integer" />  
       <xsd:attribute name="CompanyName" type="xsd:string" />  
       <xsd:attribute name="City"        type="xsd:string" />  
       <xsd:attribute name="HomePhone"   type="xsd:string"   
                                       sql:mapped="false" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:sequence>  
</xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="39fe3-107">Поскольку атрибут **HomePhone** указывает, что при `sql:mapped="false"` XML-загрузке не выполняется привязка этого атрибута к соответствующему столбцу.</span><span class="sxs-lookup"><span data-stu-id="39fe3-107">Because the **HomePhone** attribute specifies `sql:mapped="false"`, XML Bulk Load does not map this attribute to the corresponding column.</span></span> <span data-ttu-id="39fe3-108">Схема XSD определяет столбец переполнения (**оверфловколумн**), в котором при выполнении групповой загрузки XML эти невостребованные данные сохраняются.</span><span class="sxs-lookup"><span data-stu-id="39fe3-108">The XSD schema identifies an overflow column (**OverflowColumn**) in which XML Bulk Load stores this unconsumed data.</span></span>  
  
### <a name="to-test-a-working-sample"></a><span data-ttu-id="39fe3-109">Проверка рабочего образца</span><span class="sxs-lookup"><span data-stu-id="39fe3-109">To test a working sample</span></span>  
  
1.  <span data-ttu-id="39fe3-110">Создайте в базе данных **tempdb** следующую таблицу:</span><span class="sxs-lookup"><span data-stu-id="39fe3-110">Create the following table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust  
              (CustomerID     int         PRIMARY KEY,  
               CompanyName    varchar(20) NOT NULL,  
               City           varchar(20) DEFAULT 'Seattle',  
               OverflowColumn nvarchar(200))  
    GO  
    ```  
  
2.  <span data-ttu-id="39fe3-111">Сохраните схему, приведенную в этом примере, в файле SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="39fe3-111">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="39fe3-112">Сохраните следующий образец XML-данных в файле SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="39fe3-112">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1111" CompanyName="Sean Chai"   
                 City="NY" HomePhone="111-1111" />  
      <Customers CustomerID="1112" CompanyName="Dont Know"   
                 City="LA" HomePhone="222-2222" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="39fe3-113">Чтобы выполнить массовую загрузку XML-данных, сохраните этот пример на языке [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) в файле Sample.vbs и выполните его.</span><span class="sxs-lookup"><span data-stu-id="39fe3-113">To execute XML Bulk Load, save and execute this [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example as Sample.vbs:</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints=True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
 <span data-ttu-id="39fe3-114">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="39fe3-114">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
   <ElementType name="Customers" sql:relation="Cust"  
                             sql:overflow-field="OverflowColumn" >  
      <AttributeType name="CustomerID" />  
      <AttributeType name="CompanyName"  />  
      <AttributeType name="City"  />  
      <AttributeType name="HomePhone" />  
      <attribute type="CustomerID"  />  
      <attribute type="CompanyName"  />  
      <attribute type="City" />  
      <attribute type="HomePhone" sql:map-field="0" />  
   </ElementType>  
</Schema>  
```  
  
  
