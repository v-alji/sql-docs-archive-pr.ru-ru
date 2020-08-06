---
title: Исполнение SQL-запросов (поставщик SQLXMLOLEDB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXMLOLEDB Provider
- xml root property [SQLXML]
- SQLXMLOLEDB Provider, executing SQL queries
- SQL queries [SQLXML]
ms.assetid: 50334cf5-9c87-4c00-9beb-e08577c4fa82
author: rothja
ms.author: jroth
ms.openlocfilehash: a1e2cc87f90700e3b81a5a2ec3dd80f219a9b1d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665968"
---
# <a name="executing-sql-queries-sqlxmloledb-provider"></a><span data-ttu-id="63fd2-102">Выполнение запросов SQL (поставщик SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="63fd2-102">Executing SQL Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="63fd2-103">Этот пример показывает использование следующих свойств SQLXMLOLEDB, определяемых поставщиком.</span><span class="sxs-lookup"><span data-stu-id="63fd2-103">This example illustrates the use of the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="63fd2-104">клиентсидексмл</span><span class="sxs-lookup"><span data-stu-id="63fd2-104">ClientSideXML</span></span>  
  
-   <span data-ttu-id="63fd2-105">xml root</span><span class="sxs-lookup"><span data-stu-id="63fd2-105">xml root</span></span>  
  
 <span data-ttu-id="63fd2-106">В этом образце клиентского приложения ADO на стороне клиента выполняется простой SQL-запрос.</span><span class="sxs-lookup"><span data-stu-id="63fd2-106">In this client-side ADO sample application, a simple SQL query is executed on the client.</span></span> <span data-ttu-id="63fd2-107">Так как свойство Клиентсидексмл имеет значение true, инструкция SELECT без предложения FOR XML отправляется на сервер.</span><span class="sxs-lookup"><span data-stu-id="63fd2-107">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="63fd2-108">Сервер выполняет запрос и возвращает клиенту набор строк.</span><span class="sxs-lookup"><span data-stu-id="63fd2-108">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="63fd2-109">Затем клиент применяет к набору строк преобразование FOR XML и создает XML-документ.</span><span class="sxs-lookup"><span data-stu-id="63fd2-109">The client then applies the FOR XML transformation to the rowset and produces an XML document.</span></span>  
  
 <span data-ttu-id="63fd2-110">Свойство Root XML предоставляет один корневой элемент верхнего уровня для создаваемого XML-документа.</span><span class="sxs-lookup"><span data-stu-id="63fd2-110">The xml root property provides the single top-level root element for the XML document that is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63fd2-111">В коде необходимо задать имя экземпляра Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="63fd2-111">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="63fd2-112">Кроме того, в данном примере задается использование собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SQLNCLI11) для поставщика данных, для которого необходимо установить дополнительное клиентское сетевое ПО.</span><span class="sxs-lookup"><span data-stu-id="63fd2-112">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider, which requires additional network client software to be installed.</span></span> <span data-ttu-id="63fd2-113">Дополнительные сведения см. в разделе [требования к системе для SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="63fd2-113">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI ;"  
oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
oTestCommand.CommandText = "SELECT TOP 10 FirstName, LastName FROM Person.Contact FOR XML AUTO"  
oTestStream.Open  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("xml root") = "root"  
oTestCommand.Execute , , adExecuteStream  
  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
  
