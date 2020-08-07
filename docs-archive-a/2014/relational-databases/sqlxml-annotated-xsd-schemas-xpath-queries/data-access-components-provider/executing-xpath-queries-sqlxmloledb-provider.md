---
title: Исполнение запросов XPath (поставщик SQLXMLOLEDB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing XPath queries
- queries [SQLXML], SQLXMLOLEDB Provider
- Base Path property
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- Mapping Schema property
ms.assetid: 19063222-dc9c-48ae-a55f-778103674a9e
author: rothja
ms.author: jroth
ms.openlocfilehash: 667bc8dfd95c37c0a10c0bc68f3007e7d04533e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732481"
---
# <a name="executing-xpath-queries-sqlxmloledb-provider"></a><span data-ttu-id="7fd56-102">Выполнение запросов XPath (поставщик SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="7fd56-102">Executing XPath Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="7fd56-103">Этот пример показывает использование следующих свойств SQLXMLOLEDB, определяемых поставщиком.</span><span class="sxs-lookup"><span data-stu-id="7fd56-103">This example illustrates the use of the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   `ClientSideXML`  
  
-   `Base Path`  
  
-   `Mapping Schema`  
  
 <span data-ttu-id="7fd56-104">В этом образце клиентского приложения ADO запрос XPath (корневой) задается для схемы сопоставления XSD (MySchema.xml).</span><span class="sxs-lookup"><span data-stu-id="7fd56-104">In this sample ADO application, an XPath query (root) is specified against an XSD mapping schema (MySchema.xml).</span></span> <span data-ttu-id="7fd56-105">Схема содержит **\<Contacts>** элемент с атрибутами **ContactID**, **FirstName**и **LastName** .</span><span class="sxs-lookup"><span data-stu-id="7fd56-105">The schema has a **\<Contacts>** element with **ContactID**, **FirstName**, and **LastName** attributes.</span></span> <span data-ttu-id="7fd56-106">В схеме выполняется сопоставление по умолчанию: имя элемента сопоставляется с таблицей с тем же именем, а атрибуты простого типа сопоставляются со столбцами с теми же именами.</span><span class="sxs-lookup"><span data-stu-id="7fd56-106">In the schema, default mapping takes place: an element name maps to the table with the same name, and attributes of simple type map to the columns with the same names.</span></span>  
  
```  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
   xmlns:sql='urn:schemas-microsoft-com:mapping-schema'>  
 <xsd:element name= 'root' sql:is-constant='1'>   
    <xsd:complexType>  
       <xsd:sequence>  
         <xsd:element ref = 'Contacts'/>  
       </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
  <xsd:element name='Contacts' sql:relation='Person.Contact'>   
     <xsd:complexType>  
          <xsd:attribute name='ContactID' type='xsd:integer' />  
          <xsd:attribute name='FirstName' type='xsd:string'/>   
          <xsd:attribute name='LastName' type='xsd:string' />   
     </xsd:complexType>  
   </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="7fd56-107">Свойство схемы сопоставления предоставляет схему сопоставления, в которой выполняется запрос XPath.</span><span class="sxs-lookup"><span data-stu-id="7fd56-107">The Mapping Schema property provides the mapping schema against which the XPath query is executed.</span></span> <span data-ttu-id="7fd56-108">Схема сопоставления может являться схемой XSD или XDR.</span><span class="sxs-lookup"><span data-stu-id="7fd56-108">The mapping schema can be an XSD or XDR schema.</span></span> <span data-ttu-id="7fd56-109">Свойство базового пути содержит путь к схеме сопоставления.</span><span class="sxs-lookup"><span data-stu-id="7fd56-109">The Base Path property provides the file path to the mapping schema.</span></span>  
  
 <span data-ttu-id="7fd56-110">Свойство Клиентсидексмл имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="7fd56-110">The ClientSideXML property is set to True.</span></span> <span data-ttu-id="7fd56-111">Поэтому XML-документ формируется на клиенте.</span><span class="sxs-lookup"><span data-stu-id="7fd56-111">Therefore, the XML document is generated on the client.</span></span>  
  
 <span data-ttu-id="7fd56-112">Запрос XPath задается непосредственно в приложении.</span><span class="sxs-lookup"><span data-stu-id="7fd56-112">In the application, an XPath query is specified directly.</span></span> <span data-ttu-id="7fd56-113">Следовательно, должен быть включен диалект XPath {ec2a4293-e898-11d2-b1b7-00c04f680c56}.</span><span class="sxs-lookup"><span data-stu-id="7fd56-113">Therefore, the XPath dialect {ec2a4293-e898-11d2-b1b7-00c04f680c56} must be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7fd56-114">В коде необходимо задать имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="7fd56-114">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="7fd56-115">Кроме того, в этом примере в качестве поставщика данных определено использование собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SQLNCLI11), для которого необходимо установить дополнительное клиентское сетевое ПО.</span><span class="sxs-lookup"><span data-stu-id="7fd56-115">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="7fd56-116">Дополнительные сведения см. в разделе [требования к системе для SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="7fd56-116">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security= SSPI;"  
  
oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
  
oTestCommand.CommandText = "root"  
oTestStream.Open  
oTestCommand.Dialect = "{ec2a4293-e898-11d2-b1b7-00c04f680c56}"  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\XPathDirect\"  
oTestCommand.Properties("Mapping Schema").Value = "mySchema.xml"  
oTestCommand.Properties("Output Encoding") = "utf-8"  
oTestCommand.Execute , , adExecuteStream  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
  
