---
title: Примеры групповой загрузки XML (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- overflow-field annotation
- ConnectionCommand property
- XMLFragment property
- relationship chains [SQLXML]
- multiple table bulk loading
- examples [SQLXML], XML Bulk Load
- overflow data [SQLXML]
- sql:datatype
- transaction mode [SQLXML]
- CheckConstraints property
- sql:overflow-field
- XML Bulk Load [SQLXML], examples
- TempFilePath property
- datatype annotation
- Transaction property
- KeepIdentity property
- Execute method
- streaming XML data
- xml data type [SQL Server], SQLXML
- bulk load [SQLXML], examples
ms.assetid: 970e4553-b41d-4a12-ad50-0ee65d1f305d
author: rothja
ms.author: jroth
ms.openlocfilehash: c7eaec77ef068efd28c4da65833afa5047b222f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728129"
---
# <a name="xml-bulk-load-examples-sqlxml-40"></a><span data-ttu-id="eea3f-102">Примеры массовой загрузки XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="eea3f-102">XML Bulk Load Examples (SQLXML 4.0)</span></span>
  <span data-ttu-id="eea3f-103">Следующие примеры демонстрируют функцию массовой загрузки XML в Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eea3f-103">The following examples illustrate the XML Bulk Load functionality in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eea3f-104">Каждый из примеров предоставляет собой схему XSD и эквивалентную ей схему XDR.</span><span class="sxs-lookup"><span data-stu-id="eea3f-104">Each example provides an XSD schema and its equivalent XDR schema.</span></span>  
  
## <a name="bulk-loader-script-validateandbulkloadvbs"></a><span data-ttu-id="eea3f-105">Скрипт массового загрузчика (ValidateAndBulkload.vbs)</span><span class="sxs-lookup"><span data-stu-id="eea3f-105">Bulk Loader Script (ValidateAndBulkload.vbs)</span></span>  
 <span data-ttu-id="eea3f-106">Следующий скрипт, написанный в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript), загружает XML-документ в XML DOM; проверяет его на соответствие схеме; и, если документ является допустимым, выполняет пакетную загрузку XML для загрузки XML в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] таблицу.</span><span class="sxs-lookup"><span data-stu-id="eea3f-106">The following script, written in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript), loads an XML document into the XML DOM; validates it against a schema; and, if the document is valid, executes an XML bulk load to load the XML into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="eea3f-107">Этот скрипт можно использовать с каждым из примеров, которые ссылаются на него далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="eea3f-107">This script can be used with each of the individual examples that refer to it later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eea3f-108">Массовая загрузка XML не выдает предупреждений и ошибок, если передача содержимого из файла данных не была выполнена.</span><span class="sxs-lookup"><span data-stu-id="eea3f-108">XML Bulk Load does not throw a warning or an error if no content is uploaded from the data file.</span></span> <span data-ttu-id="eea3f-109">Поэтому рекомендуется перед выполнением операции массовой загрузки проверить файл XML-данных.</span><span class="sxs-lookup"><span data-stu-id="eea3f-109">Therefore, it is a good practice to validate your XML data file prior to executing a bulk load operation.</span></span>  
  
```  
Dim FileValid  
  
set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=MyServer;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
  
'Validate the data file prior to bulkload  
Dim sOutput   
sOutput = ValidateFile("SampleXMLData.xml", "", "SampleSchema.xml")  
WScript.Echo sOutput  
  
If FileValid Then  
   ' Check constraints and initiate transaction (if needed)  
   ' objBL.CheckConstraints = True  
   ' objBL.Transaction=True  
  'Execute XML bulkload using file.  
  objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
  set objBL=Nothing  
End If  
  
Function ValidateFile(strXmlFile,strUrn,strXsdFile)  
  
   ' Create a schema cache and add SampleSchema.xml to it.  
   Dim xs, fso, sAppPath  
   Set fso = CreateObject("Scripting.FileSystemObject")   
   Set xs = CreateObject("MSXML2.XMLSchemaCache.6.0")  
   sAppPath = fso.GetFolder(".")   
   xs.Add strUrn, sAppPath & "\" & strXsdFile  
  
   ' Create an XML DOMDocument object.  
   Dim xd   
   Set xd = CreateObject("MSXML2.DOMDocument.6.0")  
  
   ' Assign the schema cache to the DOM document.  
   ' schemas collection.  
   Set xd.schemas = xs  
  
   ' Load XML document as DOM document.  
   xd.async = False  
   xd.Load sAppPath & "\" & strXmlFile  
  
   ' Return validation results in message to the user.  
   If xd.parseError.errorCode <> 0 Then  
        ValidateFile = "Validation failed on " & _  
             strXmlFile & vbCrLf & _  
             "=======" & vbCrLf & _  
             "Reason: " & xd.parseError.reason & _  
             vbCrLf & "Source: " & _  
             xd.parseError.srcText & _  
             vbCrLf & "Line: " & _  
             xd.parseError.Line & vbCrLf  
             FileValid = False  
    Else  
        ValidateFile = "Validation succeeded for " & _  
             strXmlFile & vbCrLf & _  
             "========" & _  
             vbCrLf & "Contents to be bulkloaded" & vbCrLf  
             FileValid = True  
    End If  
End Function  
```  
  
## <a name="a-bulk-loading-xml-in-a-table"></a><span data-ttu-id="eea3f-110">A.</span><span class="sxs-lookup"><span data-stu-id="eea3f-110">A.</span></span> <span data-ttu-id="eea3f-111">Массовая загрузка XML-данных в таблицу</span><span class="sxs-lookup"><span data-stu-id="eea3f-111">Bulk loading XML in a table</span></span>  
 <span data-ttu-id="eea3f-112">В этом примере устанавливается соединение с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , указанным в свойстве ConnectionString (MyServer).</span><span class="sxs-lookup"><span data-stu-id="eea3f-112">This example establishes a connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is specified in the ConnectionString property (MyServer).</span></span> <span data-ttu-id="eea3f-113">В примере также указывается свойство Еррорлогфиле.</span><span class="sxs-lookup"><span data-stu-id="eea3f-113">The example also specifies the ErrorLogFile property.</span></span> <span data-ttu-id="eea3f-114">Поэтому ошибочный вывод сохраняется в указанном файле («C:\error.log»), для которого также можно указать другое место.</span><span class="sxs-lookup"><span data-stu-id="eea3f-114">Therefore, the error output is saved in the specified file ("C:\error.log"), which you might also decide to change to a different location.</span></span> <span data-ttu-id="eea3f-115">Кроме того, обратите внимание, что метод Execute имеет в качестве параметров файл схемы сопоставления (SampleSchema.xml) и XML-файл данных (SampleXMLData.xml).</span><span class="sxs-lookup"><span data-stu-id="eea3f-115">Notice also that the Execute method has as its parameters both the mapping schema file (SampleSchema.xml) and the XML data file (SampleXMLData.xml).</span></span> <span data-ttu-id="eea3f-116">При выполнении групповой загрузки таблица Cust, созданная в базе данных **tempdb** , будет содержать новые записи на основе содержимого XML-файла данных.</span><span class="sxs-lookup"><span data-stu-id="eea3f-116">When the bulk load executes, the Cust table you have created in **tempdb** database will contain new records based upon the contents of the XML data file.</span></span>  
  
#### <a name="to-test-a-sample-bulk-load"></a><span data-ttu-id="eea3f-117">Проверка образца массовой загрузки</span><span class="sxs-lookup"><span data-stu-id="eea3f-117">To test a sample bulk load</span></span>  
  
1.  <span data-ttu-id="eea3f-118">Создайте такую таблицу:</span><span class="sxs-lookup"><span data-stu-id="eea3f-118">Create this table:</span></span>  
  
    ```  
    CREATE TABLE Cust(CustomerID  int PRIMARY KEY,  
                      CompanyName varchar(20),  
                      City        varchar(20));  
    GO  
    ```  
  
2.  <span data-ttu-id="eea3f-119">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-119">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="eea3f-120">Добавьте в этот файл следующую схему XSD.</span><span class="sxs-lookup"><span data-stu-id="eea3f-120">To this file, add the following XSD schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
       <xsd:element name="ROOT" sql:is-constant="1" >  
         <xsd:complexType>  
           <xsd:sequence>  
             <xsd:element name="Customers" sql:relation="Cust" maxOccurs="unbounded">  
               <xsd:complexType>  
                 <xsd:sequence>  
                   <xsd:element name="CustomerID"  type="xsd:integer" />  
                   <xsd:element name="CompanyName" type="xsd:string" />  
                   <xsd:element name="City"        type="xsd:string" />  
                 </xsd:sequence>  
               </xsd:complexType>  
             </xsd:element>  
           </xsd:sequence>  
          </xsd:complexType>  
         </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="eea3f-121">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-121">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="eea3f-122">Добавьте в этот файл следующий XML-документ.</span><span class="sxs-lookup"><span data-stu-id="eea3f-122">To this file, add the following XML document:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Sean Chai</CompanyName>  
        <City>New York</City>  
      </Customers>  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Tom Johnston</CompanyName>  
         <City>Los Angeles</City>  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Institute of Art</CompanyName>  
        <City>Chicago</City>  
      </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="eea3f-123">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="eea3f-123">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="eea3f-124">Добавьте в этот файл код VBScript, приведенный в начале этого раздела.</span><span class="sxs-lookup"><span data-stu-id="eea3f-124">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="eea3f-125">Измените строку соединения, указав соответствующее имя сервера.</span><span class="sxs-lookup"><span data-stu-id="eea3f-125">Modify the connection string to provide the appropriate server name.</span></span> <span data-ttu-id="eea3f-126">Укажите соответствующий путь для файлов, указанных в качестве параметров метода Execute.</span><span class="sxs-lookup"><span data-stu-id="eea3f-126">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
5.  <span data-ttu-id="eea3f-127">Выполните код VBScript.</span><span class="sxs-lookup"><span data-stu-id="eea3f-127">Execute the VBScript code.</span></span> <span data-ttu-id="eea3f-128">При массовой загрузке XML-данные загружаются в таблицу Cust.</span><span class="sxs-lookup"><span data-stu-id="eea3f-128">XML Bulk Load loads the XML into the Cust table.</span></span>  
  
 <span data-ttu-id="eea3f-129">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="eea3f-129">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers"  sql:relation="Cust" >  
      <element type="CustomerID"  sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City"        sql:field="City" />  
  
   </ElementType>  
</Schema>  
```  
  
## <a name="b-bulk-loading-xml-data-in-multiple-tables"></a><span data-ttu-id="eea3f-130">Б.</span><span class="sxs-lookup"><span data-stu-id="eea3f-130">B.</span></span> <span data-ttu-id="eea3f-131">Массовая загрузка XML-данных в несколько таблиц</span><span class="sxs-lookup"><span data-stu-id="eea3f-131">Bulk loading XML data in multiple tables</span></span>  
 <span data-ttu-id="eea3f-132">В этом примере XML-документ состоит из **\<Customer>** **\<Order>** элементов и.</span><span class="sxs-lookup"><span data-stu-id="eea3f-132">In this example, the XML document consists of the **\<Customer>** and **\<Order>** elements.</span></span>  
  
```  
<ROOT>  
  <Customers>  
    <CustomerID>1111</CustomerID>  
    <CompanyName>Sean Chai</CompanyName>  
    <City>NY</City>  
    <Order OrderID="1" />  
    <Order OrderID="2" />  
  </Customers>  
  <Customers>  
    <CustomerID>1112</CustomerID>  
    <CompanyName>Tom Johnston</CompanyName>  
     <City>LA</City>    
    <Order OrderID="3" />  
  </Customers>  
  <Customers>  
    <CustomerID>1113</CustomerID>  
    <CompanyName>Institute of Art</CompanyName>  
    <Order OrderID="4" />  
  </Customers>  
</ROOT>  
```  
  
 <span data-ttu-id="eea3f-133">В этом примере производится Глобальная загрузка XML-данных в две таблицы: **cust** и **CustOrder**.</span><span class="sxs-lookup"><span data-stu-id="eea3f-133">This example bulk loads the XML data into two tables, **Cust** and **CustOrder**:</span></span>  
  
```  
Cust(CustomerID, CompanyName, City)  
CustOrder(OrderID, CustomerID)  
```  
  
 <span data-ttu-id="eea3f-134">Следующая схема XML определяет XML-представление этих таблиц.</span><span class="sxs-lookup"><span data-stu-id="eea3f-134">The following XSD schema defines the XML view of these tables.</span></span> <span data-ttu-id="eea3f-135">Схема указывает связь «родители-потомки» между **\<Customer>** **\<Order>** элементами и.</span><span class="sxs-lookup"><span data-stu-id="eea3f-135">The schema specifies the parent-child relationship between the **\<Customer>** and **\<Order>** elements.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="ROOT" sql:is-constant="1" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Customers" sql:relation="Cust" >  
          <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="CustomerID"  type="xsd:integer" />  
              <xsd:element name="CompanyName" type="xsd:string" />  
              <xsd:element name="City"        type="xsd:string" />  
              <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
                <xsd:complexType>  
                  <xsd:attribute name="OrderID" type="xsd:integer" />  
                </xsd:complexType>  
              </xsd:element>  
             </xsd:sequence>  
          </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="eea3f-136">При выполнении операции XML-загрузки используется связь «первичный ключ-внешний ключ», указанная выше между **\<Cust>** элементами и, **\<CustOrder>** для выполнения групповой загрузки данных в обе таблицы.</span><span class="sxs-lookup"><span data-stu-id="eea3f-136">XML Bulk Load uses the primary key/foreign key relationship specified above between the **\<Cust>** and **\<CustOrder>** elements to bulk load the data into both tables.</span></span>  
  
#### <a name="to-test-a-sample-bulk-load"></a><span data-ttu-id="eea3f-137">Проверка образца массовой загрузки</span><span class="sxs-lookup"><span data-stu-id="eea3f-137">To test a sample bulk load</span></span>  
  
1.  <span data-ttu-id="eea3f-138">Создайте две таблицы в базе данных **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="eea3f-138">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust(  
           CustomerID  int PRIMARY KEY,  
           CompanyName varchar(20),  
           City        varchar(20));  
    CREATE TABLE CustOrder(        OrderID     int PRIMARY KEY,   
            CustomerID int FOREIGN KEY REFERENCES Cust(CustomerID));  
    ```  
  
2.  <span data-ttu-id="eea3f-139">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-139">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="eea3f-140">Добавьте в этот файл схему XSD, приведенную в данном примере.</span><span class="sxs-lookup"><span data-stu-id="eea3f-140">Add the XSD schema that is provided in this example to the file.</span></span>  
  
3.  <span data-ttu-id="eea3f-141">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleData.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-141">Create a file in your preferred text or XML editor, and save it as SampleData.xml.</span></span> <span data-ttu-id="eea3f-142">Добавьте в этот файл XML-документ, приведенный ранее в данном примере.</span><span class="sxs-lookup"><span data-stu-id="eea3f-142">Add the XML document that was provided earlier in this example to the file.</span></span>  
  
4.  <span data-ttu-id="eea3f-143">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="eea3f-143">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="eea3f-144">Добавьте в этот файл код VBScript, приведенный в начале этого раздела.</span><span class="sxs-lookup"><span data-stu-id="eea3f-144">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="eea3f-145">Измените строку соединения, указав соответствующие имена сервера и базы данных.</span><span class="sxs-lookup"><span data-stu-id="eea3f-145">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="eea3f-146">Укажите соответствующий путь для файлов, указанных в качестве параметров метода Execute.</span><span class="sxs-lookup"><span data-stu-id="eea3f-146">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
5.  <span data-ttu-id="eea3f-147">Выполните приведенный выше код VBScript.</span><span class="sxs-lookup"><span data-stu-id="eea3f-147">Execute the VBScript code above.</span></span> <span data-ttu-id="eea3f-148">При массовой загрузке XML-данные загружаются в таблицы Cust и CustOrder.</span><span class="sxs-lookup"><span data-stu-id="eea3f-148">XML Bulk Load loads the XML document into the Cust and CustOrder tables.</span></span>  
  
 <span data-ttu-id="eea3f-149">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="eea3f-149">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust" >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
<sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
</Schema>  
```  
  
## <a name="c-using-chain-relationships-in-the-schema-to-bulk-load-xml"></a><span data-ttu-id="eea3f-150">В.</span><span class="sxs-lookup"><span data-stu-id="eea3f-150">C.</span></span> <span data-ttu-id="eea3f-151">Использование цепочечных связей в схеме для массовой загрузки XML</span><span class="sxs-lookup"><span data-stu-id="eea3f-151">Using chain relationships in the schema to bulk load XML</span></span>  
 <span data-ttu-id="eea3f-152">Этот пример показывает, как связь M:N, указанная в схеме сопоставления, используется для массовой XML-загрузки данных, представляющих связь M:N.</span><span class="sxs-lookup"><span data-stu-id="eea3f-152">This example illustrates how the M:N relationship that is specified in the mapping schema is used by XML Bulk Load to load data in a table that represents an M:N relationship.</span></span>  
  
 <span data-ttu-id="eea3f-153">В качестве примера рассмотрим следующую схему XSD.</span><span class="sxs-lookup"><span data-stu-id="eea3f-153">For example, consider this XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrderOD"  
          parent="Ord"  
          parent-key="OrderID"  
          child="OrderDetail"  
          child-key="OrderID" />  
  
    <sql:relationship name="ODProduct"  
          parent="OrderDetail"  
          parent-key="ProductID"  
          child="Product"  
          child-key="ProductID"   
          inverse="true"/>  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="ROOT" sql:is-constant="1" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Ord"   
                     sql:key-fields="OrderID" >  
          <xsd:complexType>  
            <xsd:sequence>  
             <xsd:element name="Product"  
                          sql:relation="Product"   
                          sql:key-fields="ProductID"  
                          sql:relationship="OrderOD ODProduct">  
               <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
               </xsd:complexType>  
             </xsd:element>  
           </xsd:sequence>  
           <xsd:attribute name="OrderID"   type="xsd:integer" />   
           <xsd:attribute name="CustomerID"   type="xsd:string" />  
         </xsd:complexType>  
       </xsd:element>  
      </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="eea3f-154">Схема задает **\<Order>** элемент с **\<Product>** дочерним элементом.</span><span class="sxs-lookup"><span data-stu-id="eea3f-154">The schema specifies an **\<Order>** element with a **\<Product>** child element.</span></span> <span data-ttu-id="eea3f-155">**\<Order>** Элемент сопоставляется с таблицей **\<Product>** наведением, а элемент сопоставляется с таблицей Product в базе данных.</span><span class="sxs-lookup"><span data-stu-id="eea3f-155">The **\<Order>** element maps to Ord table and the **\<Product>** element maps to the Product table in the database.</span></span> <span data-ttu-id="eea3f-156">Отношение цепочки, указанное в **\<Product>** элементе, определяет связь M:N, представленную таблицей OrderDetail.</span><span class="sxs-lookup"><span data-stu-id="eea3f-156">The chain relationship specified on the **\<Product>** element identifies a M:N relationship represented by the OrderDetail table.</span></span> <span data-ttu-id="eea3f-157">(в заказ может входить множество продуктов, а продукт может входить во множество заказов).</span><span class="sxs-lookup"><span data-stu-id="eea3f-157">(An order can include many products, and a product can be included in many orders.)</span></span>  
  
 <span data-ttu-id="eea3f-158">При массовой загрузке XML-документа с этой схемой записи добавляются к таблицам Ord, Product и OrderDetail.</span><span class="sxs-lookup"><span data-stu-id="eea3f-158">When you are bulk loading an XML document with this schema, records are added to the Ord, Product, and OrderDetail tables.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="eea3f-159">Проверка рабочего образца</span><span class="sxs-lookup"><span data-stu-id="eea3f-159">To test a working sample</span></span>  
  
1.  <span data-ttu-id="eea3f-160">Создайте три таблицы.</span><span class="sxs-lookup"><span data-stu-id="eea3f-160">Create three tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int  PRIMARY KEY,  
             CustomerID  varchar(5));  
    GO  
    CREATE TABLE Product (  
             ProductID   int PRIMARY KEY,  
             ProductName varchar(20));  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID));  
    GO  
    ```  
  
2.  <span data-ttu-id="eea3f-161">Сохраните схему, приведенную выше в этом примере, в файле SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-161">Save the schema that is provided above in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="eea3f-162">Сохраните следующий образец XML-данных в файле SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-162">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="1" CustomerID="ALFKI">  
        <Product ProductID="1" ProductName="Chai" />  
        <Product ProductID="2" ProductName="Chang" />  
      </Order>  
      <Order OrderID="2" CustomerID="ANATR">  
        <Product ProductID="3" ProductName="Aniseed Syrup" />  
        <Product ProductID="4" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="eea3f-163">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="eea3f-163">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="eea3f-164">Добавьте в этот файл код VBScript, приведенный в начале этого раздела.</span><span class="sxs-lookup"><span data-stu-id="eea3f-164">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="eea3f-165">Измените строку соединения, указав соответствующие имена сервера и базы данных.</span><span class="sxs-lookup"><span data-stu-id="eea3f-165">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="eea3f-166">Раскомментируйте в этом примере следующие строки исходного кода.</span><span class="sxs-lookup"><span data-stu-id="eea3f-166">Uncomment the following lines from the source code for this example.</span></span>  
  
    ```  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    ```  
  
5.  <span data-ttu-id="eea3f-167">Выполните код VBScript.</span><span class="sxs-lookup"><span data-stu-id="eea3f-167">Execute the VBScript code.</span></span> <span data-ttu-id="eea3f-168">Массовая загрузка XML загружает XML-документ в таблицы Ord и Product.</span><span class="sxs-lookup"><span data-stu-id="eea3f-168">XML Bulk Load loads the XML document into the Ord and Product tables.</span></span>  
  
## <a name="d-bulk-loading-in-identity-type-columns"></a><span data-ttu-id="eea3f-169">Г.</span><span class="sxs-lookup"><span data-stu-id="eea3f-169">D.</span></span> <span data-ttu-id="eea3f-170">Массовая загрузка в столбцы типа идентификаторов</span><span class="sxs-lookup"><span data-stu-id="eea3f-170">Bulk loading in identity type columns</span></span>  
 <span data-ttu-id="eea3f-171">Этот пример показывает, каким образом при массовой загрузке обрабатываются столбцы идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="eea3f-171">This example illustrates how bulk load handles identity type columns.</span></span> <span data-ttu-id="eea3f-172">В этом примере выполняется массовая загрузка данных в три таблицы (Ord, Product и OrderDetail).</span><span class="sxs-lookup"><span data-stu-id="eea3f-172">In the example, data is bulk loaded into three tables (Ord, Product, and OrderDetail).</span></span>  
  
 <span data-ttu-id="eea3f-173">В таблицах имеются следующие данные.</span><span class="sxs-lookup"><span data-stu-id="eea3f-173">In these tables:</span></span>  
  
-   <span data-ttu-id="eea3f-174">OrderID в таблице Ord является столбцом типа идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="eea3f-174">OrderID in the Ord table is an identity type column</span></span>  
  
-   <span data-ttu-id="eea3f-175">ProductID в таблице Product является столбцом типа идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="eea3f-175">ProductID in the Product table is an identity type column.</span></span>  
  
-   <span data-ttu-id="eea3f-176">Столбцы OrderID и ProductID в таблице OrderDetail являются внешними ключевыми столбцами, ссылающимися на соответствующие первичные ключевые столбцы в таблицах Ord и Product.</span><span class="sxs-lookup"><span data-stu-id="eea3f-176">OrderID and ProductID columns in the OrderDetail are foreign key columns referring to corresponding primary key columns in the Ord and Product tables.</span></span>  
  
 <span data-ttu-id="eea3f-177">Ниже перечислены схемы таблиц для этого примера.</span><span class="sxs-lookup"><span data-stu-id="eea3f-177">The following are the table schemas for this example:</span></span>  
  
```  
Ord (OrderID, CustomerID)  
Product (ProductID, ProductName)  
OrderDetail (OrderID, ProductID)  
```  
  
 <span data-ttu-id="eea3f-178">В этом примере массовой загрузки XML свойство KeepIdentity объектной модели BulkLoad имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="eea3f-178">In this example of XML Bulk Load, the KeepIdentity property of the BulkLoad object model is set to false.</span></span> <span data-ttu-id="eea3f-179">Поэтому [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] формирует значения идентификаторов для столбцов ProductID и OrderID соответственно (пропускаются любые значения, указанные в документах для массовой загрузки).</span><span class="sxs-lookup"><span data-stu-id="eea3f-179">Therefore, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] generates identity values for the ProductID and OrderID columns in the Product and Ord tables, respectively (any values provided in the documents to be bulk loaded are ignored).</span></span>  
  
 <span data-ttu-id="eea3f-180">В этом случае массовая загрузка XML идентифицирует связь «первичный-внешний ключ» между таблицами.</span><span class="sxs-lookup"><span data-stu-id="eea3f-180">In this case, XML Bulk Load identifies the primary key/foreign key relationship among tables.</span></span> <span data-ttu-id="eea3f-181">Сначала массовая загрузка вставляет записи в таблицы с первичным ключом, а затем распространяет значения идентификаторов, сформированные [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] на таблицы с внешними ключевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="eea3f-181">Bulk Load first inserts records in the tables with the primary key, then propagates the identity value generated by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to the tables with foreign key columns.</span></span> <span data-ttu-id="eea3f-182">В следующем примере массовая загрузка XML вставляет данные в таблице в следующем порядке.</span><span class="sxs-lookup"><span data-stu-id="eea3f-182">In the following example, XML Bulk Load inserts data in tables in this order:</span></span>  
  
1.  <span data-ttu-id="eea3f-183">Продукт</span><span class="sxs-lookup"><span data-stu-id="eea3f-183">Product</span></span>  
  
2.  <span data-ttu-id="eea3f-184">Ord</span><span class="sxs-lookup"><span data-stu-id="eea3f-184">Ord</span></span>  
  
3.  <span data-ttu-id="eea3f-185">OrderDetail</span><span class="sxs-lookup"><span data-stu-id="eea3f-185">OrderDetail</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eea3f-186">Чтобы распространить на внешние ключи значения идентификаторов, сформированные в таблицах Products и Orders, логика обработки требует от массовой загрузки XML отслеживания этих значений для последующей вставки в таблицу OrderDetails.</span><span class="sxs-lookup"><span data-stu-id="eea3f-186">In order to propagate identity values generated in the Products and Orders tables, the processing logic requires XML Bulk Load to keep track of these values for later insertion into the OrderDetails table.</span></span> <span data-ttu-id="eea3f-187">Для этого массовая загрузка XML создает промежуточные таблицы, заполняет эти таблицы данными и впоследствии удаляет их.</span><span class="sxs-lookup"><span data-stu-id="eea3f-187">To do that, XML Bulk Load creates intermediate tables, populates the data in these tables, and later removes them.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="eea3f-188">Проверка рабочего образца</span><span class="sxs-lookup"><span data-stu-id="eea3f-188">To test a working sample</span></span>  
  
1.  <span data-ttu-id="eea3f-189">Создайте следующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="eea3f-189">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int identity(1,1)  PRIMARY KEY,  
             CustomerID  varchar(5));  
    GO  
    CREATE TABLE Product (  
             ProductID   int identity(1,1) PRIMARY KEY,  
             ProductName varchar(20));  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID));  
    GO  
    ```  
  
2.  <span data-ttu-id="eea3f-190">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-190">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="eea3f-191">Добавьте в этот файл следующую схему XSD.</span><span class="sxs-lookup"><span data-stu-id="eea3f-191">Add this XSD schema to this file.</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
     <xsd:annotation>  
       <xsd:appinfo>  
        <sql:relationship name="OrderOD"  
              parent="Ord"  
              parent-key="OrderID"  
              child="OrderDetail"  
              child-key="OrderID" />  
        <sql:relationship name="ODProduct"  
              parent="OrderDetail"  
              parent-key="ProductID"  
              child="Product"  
              child-key="ProductID"   
              inverse="true"/>  
       </xsd:appinfo>  
     </xsd:annotation>  
  
      <xsd:element name="Order" sql:relation="Ord"   
                                sql:key-fields="OrderID" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="Product" sql:relation="Product"   
                         sql:key-fields="ProductID"  
                         sql:relationship="OrderOD ODProduct">  
              <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
              </xsd:complexType>  
            </xsd:element>  
         </xsd:sequence>  
            <xsd:attribute name="OrderID"   type="xsd:integer" />   
            <xsd:attribute name="CustomerID"   type="xsd:string" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="eea3f-192">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-192">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="eea3f-193">Добавьте следующий XML-документ.</span><span class="sxs-lookup"><span data-stu-id="eea3f-193">Add the following XML document.</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="11" CustomerID="ALFKI">  
        <Product ProductID="11" ProductName="Chai" />  
        <Product ProductID="22" ProductName="Chang" />  
      </Order>  
      <Order OrderID="22" CustomerID="ANATR">  
         <Product ProductID="33" ProductName="Aniseed Syrup" />  
        <Product ProductID="44" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="eea3f-194">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="eea3f-194">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="eea3f-195">Добавьте следующий код VBScript в этот файл.</span><span class="sxs-lookup"><span data-stu-id="eea3f-195">To this file, add the following VBScript code.</span></span> <span data-ttu-id="eea3f-196">Измените строку соединения, указав соответствующие имена сервера и базы данных.</span><span class="sxs-lookup"><span data-stu-id="eea3f-196">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="eea3f-197">Укажите соответствующий путь для файлов, которые служат параметрами `Execute` метода.</span><span class="sxs-lookup"><span data-stu-id="eea3f-197">Specify the appropriate path for the files that serve as parameters to the `Execute` method.</span></span>  
  
    ```  
    Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "C:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction = False  
    objBL.KeepIdentity = False  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    Set objBL = Nothing  
    MsgBox "Done."  
    ```  
  
5.  <span data-ttu-id="eea3f-198">Выполните код VBScript.</span><span class="sxs-lookup"><span data-stu-id="eea3f-198">Execute the VBScript code.</span></span> <span data-ttu-id="eea3f-199">Массовая загрузка XML загрузит данные в соответствующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="eea3f-199">The XML Bulk Load will load the data into the appropriate tables.</span></span>  
  
## <a name="e-generating-table-schemas-before-bulk-loading"></a><span data-ttu-id="eea3f-200">Д.</span><span class="sxs-lookup"><span data-stu-id="eea3f-200">E.</span></span> <span data-ttu-id="eea3f-201">Формирование схем таблиц перед массовой загрузкой</span><span class="sxs-lookup"><span data-stu-id="eea3f-201">Generating table schemas before bulk loading</span></span>  
 <span data-ttu-id="eea3f-202">При необходимости массовая загрузка XML может создать таблицы, если они не существовали до начала массовой загрузки.</span><span class="sxs-lookup"><span data-stu-id="eea3f-202">XML Bulk Load can optionally generate the tables if they do not exist before bulk loading.</span></span> <span data-ttu-id="eea3f-203">Установка для свойства SchemaGen объекта Склксмлбулклоад значения TRUE.</span><span class="sxs-lookup"><span data-stu-id="eea3f-203">Setting the SchemaGen property of the SQLXMLBulkLoad object to TRUE does this.</span></span> <span data-ttu-id="eea3f-204">При необходимости можно также запросить возможность выполнения групповой загрузки XML, чтобы удалить все существующие таблицы и создать их повторно, задав для свойства Сгдроптаблес значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="eea3f-204">You can also optionally request XML Bulk Load to drop any existing tables and re-create them by setting the SGDropTables property to TRUE.</span></span> <span data-ttu-id="eea3f-205">Следующий пример на языке VBScript показывает использование этих свойств.</span><span class="sxs-lookup"><span data-stu-id="eea3f-205">The following VBScript example illustrates the use of these properties.</span></span>  
  
 <span data-ttu-id="eea3f-206">Кроме того, в этом примере присваивается значение TRUE двум дополнительным свойствам.</span><span class="sxs-lookup"><span data-stu-id="eea3f-206">Also, this example sets two additional properties to TRUE:</span></span>  
  
-   <span data-ttu-id="eea3f-207">CheckConstraints.</span><span class="sxs-lookup"><span data-stu-id="eea3f-207">CheckConstraints.</span></span> <span data-ttu-id="eea3f-208">Присвоение этому свойству значения TRUE гарантирует, что данные, вставляемые в таблицы, не нарушают ограничений, указанных для таблиц (в данном случае ограничений PRIMARY KEY/FOREIGN KEY, определенных между таблицами Cust и CustOrder).</span><span class="sxs-lookup"><span data-stu-id="eea3f-208">Setting this property to TRUE ensures that the data being inserted into the tables does not violate any constraints that have been specified on the tables (in this case the PRIMARY KEY/FOREIGN KEY constraints specified between the Cust and CustOrder tables).</span></span> <span data-ttu-id="eea3f-209">При нарушении ограничений массовая загрузка завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="eea3f-209">If there is a constraint violation, the bulk load fails.</span></span>  
  
-   <span data-ttu-id="eea3f-210">XMLFragment.</span><span class="sxs-lookup"><span data-stu-id="eea3f-210">XMLFragment.</span></span> <span data-ttu-id="eea3f-211">Этому свойству должно быть присвоено значение TRUE, так как образец XML-документа (источник данных) не содержит единственного элемента верхнего уровня (и, таким образом, является фрагментом).</span><span class="sxs-lookup"><span data-stu-id="eea3f-211">This property must be set to TRUE because the sample XML document (data source) contains no single, top-level element (and is thus a fragment).</span></span>  
  
 <span data-ttu-id="eea3f-212">Код на языке VBScript.</span><span class="sxs-lookup"><span data-stu-id="eea3f-212">This is the VBScript code:</span></span>  
  
```  
Dim objBL   
Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
  
objBL.CheckConstraints=true  
objBL.XMLFragment = True  
objBL.SchemaGen = True  
objBL.SGDropTables = True  
  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
Set objBL = Nothing  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="eea3f-213">Проверка рабочего образца</span><span class="sxs-lookup"><span data-stu-id="eea3f-213">To test a working sample</span></span>  
  
1.  <span data-ttu-id="eea3f-214">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-214">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="eea3f-215">Добавьте в этот файл схему XSD, приведенную в предыдущем примере «Использование цепочечных связей в схеме для массовой загрузки XML».</span><span class="sxs-lookup"><span data-stu-id="eea3f-215">Add the XSD schema that is provided in the earlier example, "Using chain relationships in the schema to bulk load XML", to the file.</span></span>  
  
2.  <span data-ttu-id="eea3f-216">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-216">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="eea3f-217">Добавьте в этот файл XML-документ, приведенный в предыдущем примере «Использование цепочечных связей в схеме для массовой загрузки XML».</span><span class="sxs-lookup"><span data-stu-id="eea3f-217">Add the XML document that is provided in the earlier example, "Using chain relationships in the schema to bulk load XML", to the file.</span></span> <span data-ttu-id="eea3f-218">Удалите \<ROOT> элемент из документа (чтобы сделать его фрагментом).</span><span class="sxs-lookup"><span data-stu-id="eea3f-218">Remove the \<ROOT> element from the document (to make it a fragment).</span></span>  
  
3.  <span data-ttu-id="eea3f-219">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="eea3f-219">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="eea3f-220">Добавьте в этот файл код VBScript из этого примера.</span><span class="sxs-lookup"><span data-stu-id="eea3f-220">To this file, add the VBScript code in this example.</span></span> <span data-ttu-id="eea3f-221">Измените строку соединения, указав соответствующие имена сервера и базы данных.</span><span class="sxs-lookup"><span data-stu-id="eea3f-221">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="eea3f-222">Укажите соответствующий путь для файлов, указанных в качестве параметров метода Execute.</span><span class="sxs-lookup"><span data-stu-id="eea3f-222">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
4.  <span data-ttu-id="eea3f-223">Выполните код VBScript.</span><span class="sxs-lookup"><span data-stu-id="eea3f-223">Execute the VBScript code.</span></span> <span data-ttu-id="eea3f-224">Массовая загрузка XML создает необходимые таблицы на основе заданной схемы сопоставления и выполняет массовую загрузку данных в нее.</span><span class="sxs-lookup"><span data-stu-id="eea3f-224">The XML Bulk Load creates the necessary tables on the basis of the mapping schema that is provided and bulk loads the data in it.</span></span>  
  
## <a name="f-bulk-loading-from-a-stream"></a><span data-ttu-id="eea3f-225">Е.</span><span class="sxs-lookup"><span data-stu-id="eea3f-225">F.</span></span> <span data-ttu-id="eea3f-226">Массовая загрузка из потока</span><span class="sxs-lookup"><span data-stu-id="eea3f-226">Bulk loading from a stream</span></span>  
 <span data-ttu-id="eea3f-227">Метод Execute модели объектов с массовым загрузкой XML принимает два параметра.</span><span class="sxs-lookup"><span data-stu-id="eea3f-227">The Execute method of the XML Bulk Load object model takes two parameters.</span></span> <span data-ttu-id="eea3f-228">Первый параметр — это файл схемы сопоставления.</span><span class="sxs-lookup"><span data-stu-id="eea3f-228">The first parameter is the mapping schema file.</span></span> <span data-ttu-id="eea3f-229">Второй параметр представляет XML-данные, которые предстоит загрузить в базу данных.</span><span class="sxs-lookup"><span data-stu-id="eea3f-229">The second parameter provides the XML data that is to be loaded in the database.</span></span> <span data-ttu-id="eea3f-230">Существует два способа передачи XML-данных методу Execute при выполнении операции XML-загрузки.</span><span class="sxs-lookup"><span data-stu-id="eea3f-230">There are two ways to pass the XML data to the Execute method of XML Bulk Load:</span></span>  
  
-   <span data-ttu-id="eea3f-231">Указать имя файла в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="eea3f-231">Specify the file name as the parameter.</span></span>  
  
-   <span data-ttu-id="eea3f-232">Передать поток, содержащий XML-данные.</span><span class="sxs-lookup"><span data-stu-id="eea3f-232">Pass a stream that contains the XML data.</span></span>  
  
 <span data-ttu-id="eea3f-233">В этом примере показано, как выполнить массовую загрузку данных из потока.</span><span class="sxs-lookup"><span data-stu-id="eea3f-233">This example illustrates how to bulk load from a stream.</span></span>  
  
 <span data-ttu-id="eea3f-234">Сначала код VBScript выполняет инструкцию SELECT для получения данных о заказчике из таблицы Customers в базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="eea3f-234">VBScript first executes a SELECT statement to retrieve customer information from the Customers table in the Northwind database.</span></span> <span data-ttu-id="eea3f-235">Поскольку в инструкции SELECT указано предложение FOR XML (с параметром ELEMENTS), запрос возвращает XML-документ, состоящий из следующих элементов.</span><span class="sxs-lookup"><span data-stu-id="eea3f-235">Because the FOR XML clause is specified (with the ELEMENTS option) in the SELECT statement, the query returns an element-centric XML document of this form:</span></span>  
  
```  
<Customer>  
  <CustomerID>..</CustomerID>  
  <CompanyName>..</CompanyName>  
  <City>..</City>  
</Customer>  
...  
```  
  
 <span data-ttu-id="eea3f-236">Затем скрипт передает XML в виде потока в метод Execute в качестве второго параметра.</span><span class="sxs-lookup"><span data-stu-id="eea3f-236">The script then passes the XML as a stream to the Execute method as its second parameter.</span></span> <span data-ttu-id="eea3f-237">Метод Execute выполняет массовый загрузку данных в таблицу Cust.</span><span class="sxs-lookup"><span data-stu-id="eea3f-237">The Execute method bulk loads the data into the Cust table.</span></span>  
  
 <span data-ttu-id="eea3f-238">Так как этот скрипт задает для свойства SchemaGen значение TRUE, а свойству Сгдроптаблес — значение TRUE, при выполнении операции XML-загрузки в указанной базе данных создается таблица Cust.</span><span class="sxs-lookup"><span data-stu-id="eea3f-238">Because this script sets the SchemaGen property to TRUE and SGDropTables property to TRUE, XML Bulk Load creates the Cust table in the specified database.</span></span> <span data-ttu-id="eea3f-239">(если таблица уже существует, то она будет удалена и создана повторно).</span><span class="sxs-lookup"><span data-stu-id="eea3f-239">(If the table already exists, it first drops the table and then re-creates it.)</span></span>  
  
 <span data-ttu-id="eea3f-240">Пример на языке VBScript.</span><span class="sxs-lookup"><span data-stu-id="eea3f-240">This is the VBScript example:</span></span>  
  
```  
Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
Set objCmd = CreateObject("ADODB.Command")  
Set objConn = CreateObject("ADODB.Connection")  
Set objStrmOut = CreateObject ("ADODB.Stream")  
  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile     = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.SchemaGen        = True  
objBL.SGDropTables     = True  
objBL.XMLFragment      = True  
' Open a connection to the instance of SQL Server to get the source data.  
  
objConn.Open "provider=SQLOLEDB;server=(local);database=tempdb;integrated security=SSPI"  
Set objCmd.ActiveConnection = objConn  
objCmd.CommandText = "SELECT CustomerID, CompanyName, City FROM Customers FOR XML AUTO, ELEMENTS"  
  
' Open the return stream and execute the command.  
Const adCRLF = -1  
Const adExecuteStream = 1024  
objStrmOut.Open  
objStrmOut.LineSeparator = adCRLF  
objCmd.Properties("Output Stream").Value = objStrmOut  
objCmd.Execute , , adExecuteStream  
objStrmOut.Position = 0  
  
' Execute bulk load. Read source XML data from the stream.  
objBL.Execute "SampleSchema.xml", objStrmOut  
  
Set objBL = Nothing  
```  
  
 <span data-ttu-id="eea3f-241">Следующая схема сопоставления XSD предоставляет необходимые сведения для создания таблицы.</span><span class="sxs-lookup"><span data-stu-id="eea3f-241">The following XSD mapping schema provides the necessary information to create the table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="ROOT" sql:is-constant="true" >  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element ref="Customers"/>  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="Customers" sql:relation="Cust" >  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element name="CustomerID"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(5)"/>  
      <xsd:element name="CompanyName"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(40)"/>  
      <xsd:element name="City"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(40)"/>  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="eea3f-242">Эквивалентная схема XDR.</span><span class="sxs-lookup"><span data-stu-id="eea3f-242">This is equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
    </ElementType>  
</Schema>  
```  
  
### <a name="opening-a-stream-on-an-existing-file"></a><span data-ttu-id="eea3f-243">Открытие потока для существующего файла</span><span class="sxs-lookup"><span data-stu-id="eea3f-243">Opening a Stream on an Existing File</span></span>  
 <span data-ttu-id="eea3f-244">Можно также открыть поток в существующем XML-файле данных и передать его в качестве параметра методу Execute (вместо передачи имени файла в качестве параметра).</span><span class="sxs-lookup"><span data-stu-id="eea3f-244">You can also open a stream on an existing XML data file and pass the stream as a parameter to the Execute method (instead of passing the file name as the parameter).</span></span>  
  
 <span data-ttu-id="eea3f-245">Пример передачи потока на языке Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="eea3f-245">This is a Visual Basic example of passing a stream as the parameter:</span></span>  
  
```  
Private Sub Form_Load()  
Dim objBL As New SQLXMLBulkLoad  
Dim objStrm As New ADODB.Stream  
Dim objFileSystem As New Scripting.FileSystemObject  
Dim objFile As Scripting.TextStream  
  
MsgBox "Begin BulkLoad..."  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.SchemaGen = True  
objBL.SGDropTables = True  
' Here again a stream is specified that contains the source data   
' (instead of the file name). But this is just an illustration.  
' Usually this is useful if you have an XML data   
' stream that is created by some other means that you want to bulk   
' load. This example starts with an XML text file, so it may not be the   
' best to use a stream (you can specify the file name directly).  
' Here you could have specified the file name itself.   
Set objFile = objFileSystem.OpenTextFile("c:\SampleData.xml")  
objStrm.Open  
objStrm.WriteText objFile.ReadAll  
objStrm.Position = 0  
objBL.Execute "c:\SampleSchema.xml", objStrm  
  
Set objBL = Nothing  
MsgBox "Done."  
End Sub  
```  
  
 <span data-ttu-id="eea3f-246">Чтобы протестировать приложение, используйте XML-документ в файле (SampleData.xml) и схему XSD, приведенную в этом примере.</span><span class="sxs-lookup"><span data-stu-id="eea3f-246">To test the application, use the following XML document in a file (SampleData.xml) and the XSD schema that is provided in this example:</span></span>  
  
 <span data-ttu-id="eea3f-247">Источник XML-данных (SampleData.xml):</span><span class="sxs-lookup"><span data-stu-id="eea3f-247">This is the XML source data (SampleData.xml):</span></span>  
  
```  
<ROOT>  
  <Customers>  
    <CustomerID>1111</CustomerID>  
    <CompanyName>Hanari Carnes</CompanyName>  
    <City>NY</City>  
    <Order OrderID="1" />  
    <Order OrderID="2" />  
  </Customers>  
  
  <Customers>  
    <CustomerID>1112</CustomerID>  
    <CompanyName>Toms Spezialitten</CompanyName>  
     <City>LA</City>  
    <Order OrderID="3" />  
  </Customers>  
  <Customers>  
    <CustomerID>1113</CustomerID>  
    <CompanyName>Victuailles en stock</CompanyName>  
    <Order CustomerID= "4444" OrderID="4" />  
</Customers>  
</ROOT>  
```  
  
 <span data-ttu-id="eea3f-248">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="eea3f-248">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
             <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
</Schema>  
```  
  
## <a name="g-bulk-loading-in-overflow-columns"></a><span data-ttu-id="eea3f-249">Ж.</span><span class="sxs-lookup"><span data-stu-id="eea3f-249">G.</span></span> <span data-ttu-id="eea3f-250">Массовая загрузка в столбцы переполнения</span><span class="sxs-lookup"><span data-stu-id="eea3f-250">Bulk loading in overflow columns</span></span>  
 <span data-ttu-id="eea3f-251">Если в схеме сопоставления при помощи заметки `sql:overflow-field` задан столбец переполнения, массовая загрузка XML скопирует все невостребованные данные из исходного документа в этот столбец.</span><span class="sxs-lookup"><span data-stu-id="eea3f-251">If the mapping schema specifies an overflow column by using the `sql:overflow-field` annotation, XML Bulk Load copies all unconsumed data from the source document into this column.</span></span>  
  
 <span data-ttu-id="eea3f-252">Рассмотрим следующую схему XSD.</span><span class="sxs-lookup"><span data-stu-id="eea3f-252">Consider this XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Customers" sql:relation="Cust"  
                                sql:overflow-field="OverflowColumn" >  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="CustomerID"  type="xsd:integer" />  
       <xsd:element name="CompanyName" type="xsd:string" />  
       <xsd:element name="City"        type="xsd:string" />  
       <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
         <xsd:complexType>  
          <xsd:attribute name="OrderID" type="xsd:integer" />  
          <xsd:attribute name="CustomerID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="eea3f-253">Схема определяет столбец переполнения (OverflowColumn) для таблицы Cust.</span><span class="sxs-lookup"><span data-stu-id="eea3f-253">The schema identifies an overflow column (OverflowColumn) for the Cust table.</span></span> <span data-ttu-id="eea3f-254">В результате все неиспользованные XML-данные для каждого **\<Customer>** элемента добавляются в этот столбец.</span><span class="sxs-lookup"><span data-stu-id="eea3f-254">As a result, all unconsumed XML data for each **\<Customer>** element is added to this column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eea3f-255">Все абстрактные элементы (элементы, для которых указан **абстрактный = "true"** ) и все запрещенные атрибуты (атрибуты, для которых указано **запрещенное = "true"** ) считаются переполнением при выполнении групповой загрузки XML и добавляются в столбец переполнения, если они указаны.</span><span class="sxs-lookup"><span data-stu-id="eea3f-255">All abstract elements (elements for which **abstract="true"** is specified) and all prohibited attributes (attributes for which **prohibited="true"** is specified) are considered overflow by XML Bulk Load and are added to the overflow column, if specified.</span></span> <span data-ttu-id="eea3f-256">(в противном случае они пропускаются).</span><span class="sxs-lookup"><span data-stu-id="eea3f-256">(Otherwise, they are ignored.)</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="eea3f-257">Проверка рабочего образца</span><span class="sxs-lookup"><span data-stu-id="eea3f-257">To test a working sample</span></span>  
  
1.  <span data-ttu-id="eea3f-258">Создайте две таблицы в базе данных **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="eea3f-258">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust (  
                  CustomerID     int         PRIMARY KEY,  
                  CompanyName    varchar(20) NOT NULL,  
                  City           varchar(20) DEFAULT 'Seattle',  
                  OverflowColumn nvarchar(200));  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID    int PRIMARY KEY,  
                  CustomerID int FOREIGN KEY   
                                 REFERENCES Cust(CustomerID));  
    GO  
    ```  
  
2.  <span data-ttu-id="eea3f-259">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-259">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="eea3f-260">Добавьте в этот файл схему XSD, приведенную в данном примере.</span><span class="sxs-lookup"><span data-stu-id="eea3f-260">Add the XSD schema that is provided in this example to the file.</span></span>  
  
3.  <span data-ttu-id="eea3f-261">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-261">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="eea3f-262">Добавьте в этот файл следующий XML-документ.</span><span class="sxs-lookup"><span data-stu-id="eea3f-262">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City><![CDATA[NY]]> </City>  
        <Junk>garbage in overflow</Junk>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
         <![CDATA[LA]]>   
        <!-- <xyz><address>111 Maple, Seattle</address></xyz>   -->  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="eea3f-263">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="eea3f-263">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="eea3f-264">Добавьте в этот файл следующий код на языке VBScript.</span><span class="sxs-lookup"><span data-stu-id="eea3f-264">To this file, add the following Microsoft Visual Basic Scripting Edition (VBScript) code.</span></span> <span data-ttu-id="eea3f-265">Измените строку соединения, указав соответствующие имена сервера и базы данных.</span><span class="sxs-lookup"><span data-stu-id="eea3f-265">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="eea3f-266">Укажите соответствующий путь для файлов, указанных в качестве параметров метода Execute.</span><span class="sxs-lookup"><span data-stu-id="eea3f-266">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="eea3f-267">Выполните код VBScript.</span><span class="sxs-lookup"><span data-stu-id="eea3f-267">Execute the VBScript code.</span></span>  
  
 <span data-ttu-id="eea3f-268">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="eea3f-268">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"   
                       sql:overflow-field="OverflowColumn"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
             <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
</Schema>  
```  
  
## <a name="h-specifying-the-file-path-for-temp-files-in-transaction-mode"></a><span data-ttu-id="eea3f-269">З.</span><span class="sxs-lookup"><span data-stu-id="eea3f-269">H.</span></span> <span data-ttu-id="eea3f-270">Задание пути к файлу для временных файлов в режиме транзакции</span><span class="sxs-lookup"><span data-stu-id="eea3f-270">Specifying the file path for temp files in transaction mode</span></span>  
 <span data-ttu-id="eea3f-271">При выполнении групповой загрузки в режиме транзакций (т. е. Если свойство Transaction имеет значение TRUE) необходимо также задать свойство TempFilePath, если выполняется одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="eea3f-271">When you are bulk loading in transaction mode (that is, when the Transaction property is set to TRUE), you also must set the TempFilePath property when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="eea3f-272">Выполняется массовая загрузка на удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="eea3f-272">You are bulk loading to a remote server.</span></span>  
  
-   <span data-ttu-id="eea3f-273">Для хранения временных файлов, созданных в режиме транзакции, необходимо использовать другой локальный диск или папку (отличный от пути, указанного переменной среды TEMP).</span><span class="sxs-lookup"><span data-stu-id="eea3f-273">You want to use an alternate local drive or folder (one other than the path that is specified by the TEMP environment variable) to store the temporary files that are created in the transaction mode.</span></span>  
  
 <span data-ttu-id="eea3f-274">Например, следующий код на языке VBScript выполняет массовую загрузку данных из файла SampleXMLData.xml в таблицы базы данных в режиме транзакции.</span><span class="sxs-lookup"><span data-stu-id="eea3f-274">For example, the following VBScript code bulk loads data from the SampleXMLData.xml file into the database tables in transaction mode.</span></span> <span data-ttu-id="eea3f-275">Свойство TempFilePath задано, чтобы задать путь для временных файлов, создаваемых в режиме транзакции.</span><span class="sxs-lookup"><span data-stu-id="eea3f-275">The TempFilePath property is specified to set the path for the temporary files that are generated in transaction mode.</span></span>  
  
```  
set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.Transaction=True  
objBL.TempFilePath="\\Server\MyDir"  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
set objBL=Nothing  
```  
  
> [!NOTE]  
>  <span data-ttu-id="eea3f-276">Путь к временному файлу должен быть общей папкой, доступной из учетной записи службы целевого экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и учетной записи, от которой запущено приложение массовой загрузки.</span><span class="sxs-lookup"><span data-stu-id="eea3f-276">The temporary file path must be a shared location that is accessible to the service account of the target instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and to the account that is running the bulk load application.</span></span> <span data-ttu-id="eea3f-277">Если вы не выполняете многозагрузку на локальном сервере, путь к временному файлу должен быть путем в формате UNC (например, \\ \servername\sharename).</span><span class="sxs-lookup"><span data-stu-id="eea3f-277">Unless you are bulk loading on a local server, the temporary file path must be a UNC path (such as \\\servername\sharename).</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="eea3f-278">Проверка рабочего образца</span><span class="sxs-lookup"><span data-stu-id="eea3f-278">To test a working sample</span></span>  
  
1.  <span data-ttu-id="eea3f-279">Создайте эту таблицу в базе данных **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="eea3f-279">Create this table in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust (     CustomerID uniqueidentifier,   
          LastName  varchar(20));  
    GO  
    ```  
  
2.  <span data-ttu-id="eea3f-280">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-280">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="eea3f-281">Добавьте в этот файл следующую схему XSD.</span><span class="sxs-lookup"><span data-stu-id="eea3f-281">Add the following XSD schema to the file:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:attribute name="CustomerID"  type="xsd:string" />  
         <xsd:attribute name="LastName" type="xsd:string" />  
       </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="eea3f-282">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-282">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="eea3f-283">Добавьте в этот файл следующий XML-документ.</span><span class="sxs-lookup"><span data-stu-id="eea3f-283">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
    <Customers CustomerID="6F9619FF-8B86-D011-B42D-00C04FC964FF"   
               LastName="Smith" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="eea3f-284">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="eea3f-284">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="eea3f-285">Добавьте следующий код VBScript в этот файл.</span><span class="sxs-lookup"><span data-stu-id="eea3f-285">To this file, add the following VBScript code.</span></span> <span data-ttu-id="eea3f-286">Измените строку соединения, указав соответствующие имена сервера и базы данных.</span><span class="sxs-lookup"><span data-stu-id="eea3f-286">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="eea3f-287">Укажите соответствующий путь для файлов, указанных в качестве параметров метода Execute.</span><span class="sxs-lookup"><span data-stu-id="eea3f-287">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span> <span data-ttu-id="eea3f-288">Также укажите соответствующий путь для свойства TempFilePath.</span><span class="sxs-lookup"><span data-stu-id="eea3f-288">Also specify the appropriate path for the TempFilePath property.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    objBL.TempFilePath="\\server\folder"  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="eea3f-289">Выполните код VBScript.</span><span class="sxs-lookup"><span data-stu-id="eea3f-289">Execute the VBScript code.</span></span>  
  
     <span data-ttu-id="eea3f-290">Схема должна указывать соответствующий `sql:datatype` атрибуту **CustomerID** , если значение для **CustomerID** указано как идентификатор GUID, включающий фигурные скобки ({и}), например:</span><span class="sxs-lookup"><span data-stu-id="eea3f-290">The schema must specify the corresponding `sql:datatype` for the **CustomerID** attribute when the value for **CustomerID** is specified as a GUID that includes braces ({ and }), such as:</span></span>  
  
    ```  
    <ROOT>  
    <Customers CustomerID="{6F9619FF-8B86-D011-B42D-00C04FC964FF}"   
               LastName="Smith" />  
    </ROOT>  
    ```  
  
     <span data-ttu-id="eea3f-291">Обновленная схема:</span><span class="sxs-lookup"><span data-stu-id="eea3f-291">This is the updated schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:attribute name="CustomerID"  type="xsd:string"   
                        sql:datatype="uniqueidentifier" />  
         <xsd:attribute name="LastName" type="xsd:string" />  
       </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
     <span data-ttu-id="eea3f-292">Если `sql:datatype` указан параметр, идентифицирующий тип столбца как `uniqueidentifier` , операция групповой загрузки удаляет фигурные скобки ({и}) из значения **CustomerID** перед вставкой в столбец.</span><span class="sxs-lookup"><span data-stu-id="eea3f-292">When `sql:datatype` is specified identifying the column type as `uniqueidentifier`, the bulk load operation removes the braces ({ and }) from the **CustomerID** value before inserting it in the column.</span></span>  
  
 <span data-ttu-id="eea3f-293">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="eea3f-293">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
<ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
</ElementType>  
<ElementType name="Customers" sql:relation="Cust" >  
  <AttributeType name="CustomerID"  sql:datatype="uniqueidentifier" />  
  <AttributeType name="LastName"   />  
  
  <attribute type="CustomerID" />  
  <attribute type="LastName"   />  
</ElementType>  
</Schema>  
```  
  
## <a name="i-using-an-existing-database-connection-with-the-connectioncommand-property"></a><span data-ttu-id="eea3f-294">И.</span><span class="sxs-lookup"><span data-stu-id="eea3f-294">I.</span></span> <span data-ttu-id="eea3f-295">Использование существующего подключения к базе данных со свойством ConnectionCommand</span><span class="sxs-lookup"><span data-stu-id="eea3f-295">Using an existing database connection with the ConnectionCommand property</span></span>  
 <span data-ttu-id="eea3f-296">Для массовой загрузки XML можно использовать существующее соединение ADO.</span><span class="sxs-lookup"><span data-stu-id="eea3f-296">You can use an existing ADO connection to bulk load XML.</span></span> <span data-ttu-id="eea3f-297">Это может оказаться полезным в том случае, если массовая загрузка XML — лишь одна из многих операций, которые выполняются над источником данных.</span><span class="sxs-lookup"><span data-stu-id="eea3f-297">This is useful if XML Bulk Load is just one of many operations that will be performed on a data source.</span></span>  
  
 <span data-ttu-id="eea3f-298">Свойство ConnectionCommand позволяет использовать существующее соединение ADO с помощью объекта команды ADO.</span><span class="sxs-lookup"><span data-stu-id="eea3f-298">The ConnectionCommand property enables you to use an existing ADO connection by using an ADO command object.</span></span> <span data-ttu-id="eea3f-299">Это продемонстрировано в следующем примере на языке Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="eea3f-299">This is illustrated in the following Visual Basic example:</span></span>  
  
```  
Private Sub Form_Load()  
Dim objBL As New SQLXMLBulkLoad4  
Dim objCmd As New ADODB.Command  
Dim objConn As New ADODB.Connection  
  
'Open a connection to an instance of SQL Server.  
objConn.Open "provider=SQLOLEDB;data source=(local);database=tempdb;integrated security=SSPI"  
'Ask the Command object to use the connection just established.  
Set objCmd.ActiveConnection = objConn  
  
'Tell Bulk Load to use the active command object that is using the Connection obj.  
objBL.ConnectionCommand = objCmd  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
'The Transaction property must be set to True if you use ConnectionCommand.  
objBL.Transaction = True  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
Set objBL = Nothing  
End Sub  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="eea3f-300">Проверка рабочего образца</span><span class="sxs-lookup"><span data-stu-id="eea3f-300">To test a working sample</span></span>  
  
1.  <span data-ttu-id="eea3f-301">Создайте две таблицы в базе данных **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="eea3f-301">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust(  
                   CustomerID   varchar(5) PRIMARY KEY,  
                   CompanyName  varchar(30),  
                   City         varchar(20));  
    GO  
    CREATE TABLE CustOrder(  
                   CustomerID  varchar(5) references Cust (CustomerID),  
                   OrderID     varchar(5) PRIMARY KEY);  
    GO  
    ```  
  
2.  <span data-ttu-id="eea3f-302">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-302">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="eea3f-303">Добавьте в этот файл следующую схему XSD.</span><span class="sxs-lookup"><span data-stu-id="eea3f-303">Add the following XSD schema to the file:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
    <xsd:annotation>  
      <xsd:appinfo>  
        <sql:relationship name="CustCustOrder"  
              parent="Cust"  
              parent-key="CustomerID"  
              child="CustOrder"  
              child-key="CustomerID" />  
      </xsd:appinfo>  
    </xsd:annotation>  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:sequence>  
           <xsd:element name="CustomerID"  type="xsd:integer" />  
           <xsd:element name="CompanyName" type="xsd:string" />  
           <xsd:element name="City"        type="xsd:string" />  
           <xsd:element name="Order"   
                              sql:relation="CustOrder"  
                              sql:relationship="CustCustOrder" >  
             <xsd:complexType>  
              <xsd:attribute name="OrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:integer" />  
             </xsd:complexType>  
           </xsd:element>  
         </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="eea3f-304">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-304">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="eea3f-305">Добавьте в этот файл следующий XML-документ.</span><span class="sxs-lookup"><span data-stu-id="eea3f-305">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
         <City>LA</City>  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="eea3f-306">Создайте приложение на языке Visual Basic (стандартное EXE приложение) и предшествующий код.</span><span class="sxs-lookup"><span data-stu-id="eea3f-306">Create a Visual Basic (Standard EXE) application and the preceding code.</span></span> <span data-ttu-id="eea3f-307">Добавьте эти ссылки в проект:</span><span class="sxs-lookup"><span data-stu-id="eea3f-307">Add these references to the project:</span></span>  
  
    ```  
    Microsoft XML BulkLoad for SQL Server 4.0 Type Library  
    Microsoft ActiveX Data objects 2.6 Library  
    ```  
  
5.  <span data-ttu-id="eea3f-308">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="eea3f-308">Execute the application.</span></span>  
  
 <span data-ttu-id="eea3f-309">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="eea3f-309">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
         <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
</Schema>  
```  
  
## <a name="j-bulk-loading-in-xml-data-type-columns"></a><span data-ttu-id="eea3f-310">К.</span><span class="sxs-lookup"><span data-stu-id="eea3f-310">J.</span></span> <span data-ttu-id="eea3f-311">Массовая загрузка XML-данных в столбцы типа данных xml</span><span class="sxs-lookup"><span data-stu-id="eea3f-311">Bulk loading in xml Data Type columns</span></span>  
 <span data-ttu-id="eea3f-312">Если схема сопоставления задает столбец [типа данных XML](/sql/t-sql/xml/xml-transact-sql) с помощью аннотации, то при выполнении `sql:datatype="xml"` XML-загрузки можно скопировать дочерние элементы XML для сопоставленного поля из исходного документа в этот столбец.</span><span class="sxs-lookup"><span data-stu-id="eea3f-312">If the mapping schema specifies a [xml data type](/sql/t-sql/xml/xml-transact-sql) column by using the `sql:datatype="xml"` annotation, XML Bulk Load can copy XML child elements for the mapped field from the source document into this column.</span></span>  
  
 <span data-ttu-id="eea3f-313">Рассмотрим следующую схему XSD, которая сопоставляет представление таблицы Production.ProductModel в образце базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="eea3f-313">Consider the following XSD schema, which maps a view of the Production.ProductModel table in the AdventureWorks sample database.</span></span> <span data-ttu-id="eea3f-314">В этой таблице поле CatalogDescription `xml` типа данных сопоставляется с **\<Desc>** элементом с помощью `sql:field` `sql:datatype="xml"` заметок и.</span><span class="sxs-lookup"><span data-stu-id="eea3f-314">In this table, the CatalogDescription field of `xml` data type is mapped to a **\<Desc>** element using the `sql:field` and `sql:datatype="xml"` annotations.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
           xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">   
  <xsd:element name="ProductModel"  sql:relation="Production.ProductModel" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Name" type="xs:string"></xsd:element>  
        <xsd:element name="Desc" sql:field="CatalogDescription" sql:datatype="xml">  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element name="ProductDescription">  
              <xsd:complexType>  
                <xsd:sequence>  
                  <xsd:element name="Summary" type="xs:anyType"/>  
                </xsd:sequence>  
              </xsd:complexType>  
            </xsd:element>  
          </xsd:sequence>  
        </xsd:complexType>  
        </xsd:element>   
     </xsd:sequence>  
     <xsd:attribute name="ProductModelID" sql:field="ProductModelID" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="eea3f-315">Проверка рабочего образца</span><span class="sxs-lookup"><span data-stu-id="eea3f-315">To test a working sample</span></span>  
  
1.  <span data-ttu-id="eea3f-316">Проверьте, что установлен образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="eea3f-316">Verify that the AdventureWorks sample database is installed.</span></span>  
  
2.  <span data-ttu-id="eea3f-317">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-317">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="eea3f-318">Скопируйте приведенную выше схему XSD, вставьте ее в файл и сохраните его.</span><span class="sxs-lookup"><span data-stu-id="eea3f-318">Copy the XSD schema above and paste it into the file and save it.</span></span>  
  
3.  <span data-ttu-id="eea3f-319">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="eea3f-319">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="eea3f-320">Скопируйте следующий XML-документ, вставьте его в файл и сохраните его в той же папке, которая была использована в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="eea3f-320">Copy the following XML document below and paste it into the file and save it in the same folder as was used for the previous step.</span></span>  
  
    ```  
    <ProductModel ProductModelID="2005">  
        <Name>Mountain-100 (2005 model)</Name>  
        <Desc><?xml-stylesheet href="ProductDescription.xsl" type="text/xsl"?>  
            <p1:ProductDescription xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription"   
                  xmlns:wm="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"   
                  xmlns:wf="http://www.adventure-works.com/schemas/OtherFeatures"   
                  xmlns:html="http://www.w3.org/1999/xhtml"   
                  xmlns="">  
                <p1:Summary>  
                    <html:p>Our top-of-the-line competition mountain bike.   
          Performance-enhancing options include the innovative HL Frame,   
          super-smooth front suspension, and traction for all terrain.  
                            </html:p>  
                </p1:Summary>  
                <p1:Manufacturer>  
                    <p1:Name>AdventureWorks</p1:Name>  
                    <p1:Copyright>2002-2005</p1:Copyright>  
                    <p1:ProductURL>HTTP://www.Adventure-works.com</p1:ProductURL>  
                </p1:Manufacturer>  
                <p1:Features>These are the product highlights.   
                     <wm:Warranty>  
                        <wm:WarrantyPeriod>3 years</wm:WarrantyPeriod>  
                        <wm:Description>parts and labor</wm:Description>  
                    </wm:Warranty><wm:Maintenance>  
                        <wm:NoOfYears>10 years</wm:NoOfYears>  
                        <wm:Description>maintenance contract available through your dealer or any AdventureWorks retail store.</wm:Description>  
                    </wm:Maintenance><wf:wheel>High performance wheels.</wf:wheel><wf:saddle>  
                        <html:i>Anatomic design</html:i> and made from durable leather for a full-day of riding in comfort.</wf:saddle><wf:pedal>  
                        <html:b>Top-of-the-line</html:b> clipless pedals with adjustable tension.</wf:pedal><wf:BikeFrame>Each frame is hand-crafted in our Bothell facility to the optimum diameter   
          and wall-thickness required of a premium mountain frame.   
          The heat-treated welded aluminum frame has a larger diameter tube that absorbs the bumps.</wf:BikeFrame><wf:crankset> Triple crankset; alumunim crank arm; flawless shifting. </wf:crankset></p1:Features>  
                <!-- add one or more of these elements... one for each specific product in this product model -->  
                <p1:Picture>  
                    <p1:Angle>front</p1:Angle>  
                    <p1:Size>small</p1:Size>  
                    <p1:ProductPhotoID>118</p1:ProductPhotoID>  
                </p1:Picture>  
                <!-- add any tags in <specifications> -->  
                <p1:Specifications> These are the product specifications.  
                       <Material>Almuminum Alloy</Material><Color>Available in most colors</Color><ProductLine>Mountain bike</ProductLine><Style>Unisex</Style><RiderExperience>Advanced to Professional riders</RiderExperience></p1:Specifications>  
            </p1:ProductDescription>  
        </Desc>  
    </ProductModel>  
    ```  
  
4.  <span data-ttu-id="eea3f-321">В текстовом редакторе или редакторе XML по своему выбору создайте файл и сохраните его под именем BulkloadXml.vbs.</span><span class="sxs-lookup"><span data-stu-id="eea3f-321">Create a file in your preferred text or XML editor, and save it as BulkloadXml.vbs.</span></span> <span data-ttu-id="eea3f-322">Скопируйте следующий код VBScript и вставьте его в файл.</span><span class="sxs-lookup"><span data-stu-id="eea3f-322">Copy the following VBScript code and paste it into the file.</span></span> <span data-ttu-id="eea3f-323">Сохраните в той же папке, которая была использована для предыдущих файлов XML-данных и схемы.</span><span class="sxs-lookup"><span data-stu-id="eea3f-323">Save it in the same folder as was used for the previous XML data and schema files.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=MyServer;database=AdventureWorks;integrated security=SSPI"  
  
    Dim fso, sAppPath  
    Set fso = CreateObject("Scripting.FileSystemObject")   
    sAppPath = fso.GetFolder(".")   
  
    objBL.ErrorLogFile = sAppPath & "\error.log"  
  
    'Execute XML bulkload using file.  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="eea3f-324">Выполните скрипт BulkloadXml.vbs.</span><span class="sxs-lookup"><span data-stu-id="eea3f-324">Execute the BulkloadXml.vbs script.</span></span>  
  
  
