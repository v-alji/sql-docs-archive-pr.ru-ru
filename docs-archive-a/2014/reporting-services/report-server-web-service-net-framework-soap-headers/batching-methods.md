---
title: Методы пакетной обработки | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- methods [Reporting Services], batches
- BatchHeader SOAP header
- Web service [Reporting Services], methods
- Report Server Web service, batching
- batches [Reporting Services]
- XML Web service [Reporting Services], methods
- locking [Reporting Services]
- multiple Web service methods
ms.assetid: 86435534-c9fe-4b49-b88c-7fb6d21976b0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c778da186fdbbfaed17b9635d9ca7309a369552b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667556"
---
# <a name="batching-methods"></a><span data-ttu-id="b24e5-102">Методы пакетной работы</span><span class="sxs-lookup"><span data-stu-id="b24e5-102">Batching Methods</span></span>
  <span data-ttu-id="b24e5-103">Использование заголовков SOAP в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] позволяет включать в одну операцию несколько методов веб-служб.</span><span class="sxs-lookup"><span data-stu-id="b24e5-103">The use of SOAP headers in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enables you to include multiple Web service methods in a single operation.</span></span> <span data-ttu-id="b24e5-104">Методы выполняются в области одной транзакции базы данных, в порядке их вызова.</span><span class="sxs-lookup"><span data-stu-id="b24e5-104">Methods run within the scope of a single database transaction, in the order in which they are called.</span></span>  
  
 <span data-ttu-id="b24e5-105">Одним из преимуществ использования пакетных методов с множественными операциями является возможность реализации отката.</span><span class="sxs-lookup"><span data-stu-id="b24e5-105">Rollback is one advantage of using multiple-method batch operations.</span></span> <span data-ttu-id="b24e5-106">Если во время выполнения пакета в любом из вызовов методов возникнет ошибка, то сервер отчетов прекратит выполнение пакета и выполнит откат любых предыдущих операций.</span><span class="sxs-lookup"><span data-stu-id="b24e5-106">If an error occurs on any of the method calls while a batch is running, the report server stops running the batch and rolls back any previous operations.</span></span> <span data-ttu-id="b24e5-107">Это полезно в том случае, если выполнение вызова метода зависит от успешного завершения других вызовов метода в данном пакете.</span><span class="sxs-lookup"><span data-stu-id="b24e5-107">This is useful when a method call depends on the successful completion of other method calls in that batch.</span></span>  
  
 <span data-ttu-id="b24e5-108">Веб-служба не предоставляет семантики блокировки для пакетных операций с несколькими методами.</span><span class="sxs-lookup"><span data-stu-id="b24e5-108">The Web service does not provide locking semantics for multiple-method batch operations.</span></span> <span data-ttu-id="b24e5-109">Строки в базе данных сервера отчетов не блокируются для обновления до тех пор, пока сообщение не будет отправлено на сервер и не будет вызвана команда Execute.</span><span class="sxs-lookup"><span data-stu-id="b24e5-109">Rows in the report server database are not locked for updating until the message is sent to the server and the Execute command is called.</span></span>  
  
 <span data-ttu-id="b24e5-110">Также не существует управления параллелизмом, которое гарантировало бы неизменность базы данных с момента последнего считывания.</span><span class="sxs-lookup"><span data-stu-id="b24e5-110">There are also no concurrency controls to guarantee that the database has not changed since the data was last read.</span></span> <span data-ttu-id="b24e5-111">Если два клиента изменяют один и тот же элемент, тот более позднее обновление будет успешно выполнено в случае, если параметры все еще действительны (например, если элемент не был переименован).</span><span class="sxs-lookup"><span data-stu-id="b24e5-111">If two clients modify the same item, the last update succeeds if the parameters are still valid (for example, the item has not been renamed).</span></span>  
  
 <span data-ttu-id="b24e5-112">В следующем примере метод <xref:ReportService2005.ReportingService2005.CreateFolder%2A> вызывается три раза; данные вызовы выполняются как один пакет.</span><span class="sxs-lookup"><span data-stu-id="b24e5-112">The following example calls the <xref:ReportService2005.ReportingService2005.CreateFolder%2A> method three times and runs these calls as a single batch.</span></span> <span data-ttu-id="b24e5-113">Если любой из вызовов метода <xref:ReportService2005.ReportingService2005.CreateFolder%2A> завершается неудачно, то отменяется весь пакет.</span><span class="sxs-lookup"><span data-stu-id="b24e5-113">If any of the calls to <xref:ReportService2005.ReportingService2005.CreateFolder%2A> fail, the entire batch is canceled.</span></span>  
  
```vb  
Imports System  
Imports System.Web.Services.Protocols  
Imports myNamespace.MyReferenceName  
  
Class Sample  
    Sub Main(args() As String)  
        Dim rs As New ReportingService2005()  
        rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
      ' Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2005.asmx"  
  
        Dim bh As New BatchHeader()  
  
        bh.BatchId = service.CreateBatch()  
        rs.BatchHeaderValue = bh  
        rs.CreateFolder("New Folder1", "/", Nothing)  
        rs.CreateFolder("New Folder2", "/", Nothing)  
        rs.CreateFolder("New Folder3", "/", Nothing)  
  
        Console.WriteLine("Creating folders...")  
        rs.BatchHeaderValue = bh  
        rs.ExecuteBatch()  
        Console.WriteLine("Folders created successfully.")  
  
        rs.BatchHeaderValue = Nothing  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Web.Services.Protocols;   
using myNamespace.MyReferenceName;  
  
class Sample  
{  
    static void Main(string[] args)  
    {  
        ReportingService2005 rs = new ReportingService2005();  
        rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
      // Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2005.asmx"  
  
        BatchHeader bh = new BatchHeader();  
  
        bh1.BatchID = service.CreateBatch();  
        rs.BatchHeaderValue = bh;  
        rs.CreateFolder("New Folder1", "/", null);  
        rs.CreateFolder("New Folder2", "/", null);  
        rs.CreateFolder("New Folder3", "/", null);  
  
        Console.WriteLine("Creating folders...");  
        rs.BatchHeaderValue = bh1;  
        rs.ExecuteBatch();  
        Console.WriteLine("Folders created successfully.");  
  
        rs.BatchHeaderValue = null;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b24e5-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="b24e5-114">See Also</span></span>  
 <xref:ReportService2005.ReportingService2005.CancelBatch%2A>   
 <xref:ReportService2005.ReportingService2005.CreateBatch%2A>   
 <span data-ttu-id="b24e5-115">[Технический справочник &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b24e5-115">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="b24e5-116">Использование заголовков SOAP служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b24e5-116">Using Reporting Services SOAP Headers</span></span>](using-reporting-services-soap-headers.md)  
  
  
