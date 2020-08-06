---
title: 'SQL: limit-field и SQL: limit-value (SQLXML 4,0) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- limiting values [SQLXML]
- limit-value annotation
- limit-field annotation
- sql:limit-field
- sql:limit-value
- filtering [SQLXML]
ms.assetid: 402c21cf-9566-463f-a928-f94270c11db3
author: rothja
ms.author: jroth
ms.openlocfilehash: a6d0383aece7a2bafa5d21b76d0c4da9cb057984
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664103"
---
# <a name="sqllimit-field-and-sqllimit-value-sqlxml-40"></a><span data-ttu-id="7086d-102">Заметки sql:limit-field и sql:limit-value (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7086d-102">sql:limit-field and sql:limit-value (SQLXML 4.0)</span></span>
  <span data-ttu-id="7086d-103">Массовая загрузка XML обрабатывает заметки `sql:limit-field` и `sql:limit-value` в соответствии с их определением.</span><span class="sxs-lookup"><span data-stu-id="7086d-103">XML Bulk Load processes the `sql:limit-field` and `sql:limit-value` annotations per their definition.</span></span> <span data-ttu-id="7086d-104">Дополнительные сведения см. в разделе [Фильтрация значений с помощью SQL: limit-field и SQL: limit-value &#40;SQLXML 4,0&#41;](annotation-interpretation-sql-limit-field-and-sql-limit-value.md).</span><span class="sxs-lookup"><span data-stu-id="7086d-104">For more information, see [Filtering Values Using sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;](annotation-interpretation-sql-limit-field-and-sql-limit-value.md).</span></span>  
  
 <span data-ttu-id="7086d-105">Например, пусть база данных содержит следующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="7086d-105">For example, suppose a database contains the following tables:</span></span>  
  
-   <span data-ttu-id="7086d-106">Customer (CustomerID, CompanyName)</span><span class="sxs-lookup"><span data-stu-id="7086d-106">Customer (CustomerID, CompanyName)</span></span>  
  
-   <span data-ttu-id="7086d-107">Адреса (CustomerID, AddressType, StreetAddress)</span><span class="sxs-lookup"><span data-stu-id="7086d-107">Addresses (CustomerID, StreetAddress, AddressType)</span></span>  
  
 <span data-ttu-id="7086d-108">Клиент может иметь много адресов, с каждым из которых связан тип адреса (например, адрес доставки или адрес для выставления счетов).</span><span class="sxs-lookup"><span data-stu-id="7086d-108">A customer can have many addresses, and each address has an address type associated with it (for example, a shipping address or a billing address).</span></span>  
  
 <span data-ttu-id="7086d-109">А теперь обратите внимание на XML-представление этих таблиц, заданное в следующей схеме XSD с заметками:</span><span class="sxs-lookup"><span data-stu-id="7086d-109">Now consider this XML view of these tables as specified in the following annotated XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustAddr"  
        parent="Customer"  
        parent-key="CustomerID"  
        child="Address"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Customer" >  
   <xsd:complexType>  
        <xsd:attribute name="CustomerID"   type="xsd:int" />   
        <xsd:attribute name="CompanyName"  type="xsd:string" />  
        <xsd:attribute name="BillTo"   
                       type="xsd:string"   
                       sql:relation="Address"   
                       sql:field="StreetAddress"  
                       sql:limit-field="AddressType"  
                       sql:limit-value="billing"  
                       sql:relationship="CustAddr" >  
        </xsd:attribute>  
        <xsd:attribute name="ShipTo"   
                       type="xsd:string"   
                       sql:relation="Address"   
                       sql:field="StreetAddress"  
                       sql:limit-field="AddressType"  
                       sql:limit-value="shipping"  
                       sql:relationship="CustAddr" >  
        </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="7086d-110">После получения этой схемы и XML-данных массовая загрузка XML вставляет значение, указанное для атрибута BillTo в столбце StreetAddress таблицы CustAddress наряду со значением «billing» для столбца AddressType.</span><span class="sxs-lookup"><span data-stu-id="7086d-110">Upon receiving this schema and XML data, XML Bulk Load inserts the value that is specified for the BillTo attribute into the StreetAddress column of the CustAddress table along with the "billing" value for the AddressType column.</span></span>  
  
 <span data-ttu-id="7086d-111">Аналогично массовая загрузка XML вставляет значение, указанное для атрибута ShipTo в столбце StreetAddress наряду со значением «shipping» для столбца AddressType.</span><span class="sxs-lookup"><span data-stu-id="7086d-111">Similarly, XML Bulk Load inserts the value that is specified for the ShipTo attribute into the StreetAddress column along with the "shipping" value in the AddressType column.</span></span>  
  
### <a name="to-test-a-working-sample"></a><span data-ttu-id="7086d-112">Проверка рабочего образца</span><span class="sxs-lookup"><span data-stu-id="7086d-112">To test a working sample</span></span>  
  
1.  <span data-ttu-id="7086d-113">Сохраните схему, приведенную в этом примере, в файле SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="7086d-113">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
2.  <span data-ttu-id="7086d-114">Создайте следующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="7086d-114">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Customer(  
                     CustomerID     int         PRIMARY KEY,  
                     CompanyName    varchar(20) NOT NULL)  
    GO  
    CREATE TABLE Address(  
                      CustomerID     int        FOREIGN KEY REFERENCES   
                                                 Customer(CustomerID),   
                      StreetAddress  varchar(50),  
                      AddressType    varchar(10))  
    GO  
    ```  
  
3.  <span data-ttu-id="7086d-115">Сохраните следующие образцы данных в файле SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="7086d-115">Save the following sample data as SampleXMLData.xml:</span></span>  
  
    ```  
    <Customer CustomerID="1111" CompanyName="Sean Chai" City="NY"   
                 BillTo="111 Maple (Billing) "   
                 ShipTo="111 Maple (Shipping)" />  
    <Customer CustomerID="1112" CompanyName="Dont Know" City="LA"   
                 BillTo="222 Spruce (Billing)"   
                 ShipTo="222 Spruce (Shipping)" />  
    ```  
  
4.  <span data-ttu-id="7086d-116">Чтобы выполнить массовую загрузку XML-данных, сохраните этот пример на языке [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) в файле Sample.vbs и выполните его.</span><span class="sxs-lookup"><span data-stu-id="7086d-116">To execute XML Bulk Load, save and execute this [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example as Sample.vbs:</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.XMLFragment = True  
    objBL.CheckConstraints=True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
 <span data-ttu-id="7086d-117">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="7086d-117">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="Customer" sql:relation="Customer" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="CompanyName" />  
    <AttributeType name="BillTo" />  
    <AttributeType name="ShipTo" />  
  
    <attribute type="CustomerID" />  
    <attribute type="CompanyName" />  
    <attribute type="BillTo"   
                sql:limit-field="AddressType"  
                sql:limit-value="billing"  
                sql:field="StreetAddress"  
                sql:relation="Address" >  
                <sql:relationship   
                        key="CustomerID"  
                        key-relation="Customer"  
                        foreign-relation="Address"  
                        foreign-key="CustomerID" />  
    </attribute>  
    <attribute type="ShipTo"   
                sql:limit-field="AddressType"  
                sql:limit-value="shipping"  
                sql:field="StreetAddress"  
                sql:relation="Address" >  
                <sql:relationship   
                     key="CustomerID"  
                     key-relation="Customer"  
                     foreign-relation="Address"  
                     foreign-key="CustomerID" />  
    </attribute>  
</ElementType>  
</Schema>  
```  
  
  
