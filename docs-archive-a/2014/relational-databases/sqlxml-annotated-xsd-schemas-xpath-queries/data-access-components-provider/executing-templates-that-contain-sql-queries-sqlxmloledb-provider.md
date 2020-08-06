---
title: Исполнение шаблонов, содержащих SQL-запросы (поставщик SQLXMLOLEDB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- templates [SQLXML]
- SQLXMLOLEDB Provider, executing template files
- templates [SQLXML], SQL queries
- XML templates [SQLXML]
- SQL queries [SQLXML]
ms.assetid: ff2bc36f-e3fb-4d8f-8e3a-2680a39eda11
author: rothja
ms.author: jroth
ms.openlocfilehash: c3d3bc340612286e211d85f52a3d914d1d1b6b9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665254"
---
# <a name="executing-templates-that-contain-sql-queries-sqlxmloledb-provider"></a><span data-ttu-id="d7dac-102">Выполнение шаблонов, содержащих SQL-запросы (поставщик SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="d7dac-102">Executing Templates That Contain SQL Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="d7dac-103">В этом примере показано использование свойства Клиентсидексмл, зависящего от поставщика SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="d7dac-103">This example illustrates the use of the SQLXMLOLEDB Provider-specific property ClientSideXML.</span></span> <span data-ttu-id="d7dac-104">В этом образце клиентского приложения ADO на сервере выполняется XML-шаблон, содержащий SQL-запрос.</span><span class="sxs-lookup"><span data-stu-id="d7dac-104">In this client-side ADO sample application, an XML template that consists of an SQL query is executed on the server.</span></span>  
  
 <span data-ttu-id="d7dac-105">Так как свойство Клиентсидексмл имеет значение true, инструкция SELECT без предложения FOR XML отправляется на сервер.</span><span class="sxs-lookup"><span data-stu-id="d7dac-105">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="d7dac-106">Сервер выполняет запрос и возвращает клиенту набор строк.</span><span class="sxs-lookup"><span data-stu-id="d7dac-106">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="d7dac-107">Затем клиент применяет к набору строк преобразование FOR XML и создает XML-документ.</span><span class="sxs-lookup"><span data-stu-id="d7dac-107">The client then applies the FOR XML transformation to the rowset and produces an XML document.</span></span>  
  
 <span data-ttu-id="d7dac-108">XML-шаблон предоставляет один корневой элемент верхнего уровня ( \<ROOT> ) для создаваемого XML-документа, поэтому свойство Root XML не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="d7dac-108">The XML template provides a single top-level root element (\<ROOT>) for the XML document that is generated; therefore, the xml root property is not provided.</span></span>  
  
 <span data-ttu-id="d7dac-109">Для выполнения шаблонов XML должен быть указан диалект {5d531cb2-e6ed-11d2-b252-00c04f681b71}.</span><span class="sxs-lookup"><span data-stu-id="d7dac-109">To execute XML templates, the dialect {5d531cb2-e6ed-11d2-b252-00c04f681b71} must be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7dac-110">В коде необходимо задать имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="d7dac-110">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="d7dac-111">Кроме того, в этом примере в качестве поставщика данных определено использование собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SQLNCLI11), для которого необходимо установить дополнительное клиентское сетевое ПО.</span><span class="sxs-lookup"><span data-stu-id="d7dac-111">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="d7dac-112">Дополнительные сведения см. в разделе [требования к системе для SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="d7dac-112">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
  
Sub Main()  
  Dim oTestStream As New ADODB.Stream  
  Dim oTestConnection As New ADODB.Connection  
  Dim oTestCommand As New ADODB.Command  
  oTestConnection.Open "Provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Data Source=SqlServerName;Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
  
  Set oTestCommand.ActiveConnection = oTestConnection  
  oTestCommand.Properties("ClientSideXML") = True  
  oTestCommand.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'> " & _  
        " <sql:query> " & _  
        "   SELECT TOP 10 FirstName, LastName FROM Person.Contact FOR XML AUTO " & _  
        "   </sql:query> " & _  
        " </ROOT> "  
  oTestStream.Open  
  ' You need the dialect if you are executing   
  ' XML templates (not for SQL queries).  
  oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  oTestCommand.Properties("Output Stream").Value = oTestStream  
  oTestCommand.Execute , , adExecuteStream  
  
  oTestStream.Position = 0  
  oTestStream.Charset = "utf-8"  
  Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
  
Sub Form_Load()  
  Main  
End Sub  
```  
  
  
