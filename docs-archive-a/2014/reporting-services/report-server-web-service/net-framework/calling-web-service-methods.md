---
title: Вызов методов веб-служб | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Web service [Reporting Services], calls
- calling Web service
- Report Server Web service, SOAP
- XML Web service [Reporting Services], calls
- Report Server Web service, calls
- XML Web service [Reporting Services], SOAP
- SOAP [Reporting Services], calls
ms.assetid: f6f0c6e3-8bb5-4c44-9d19-1872edc72746
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 87f1485b4e3c0ed064e42bb3b411fece96eba8d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730142"
---
# <a name="calling-web-service-methods"></a><span data-ttu-id="347ff-102">Вызов методов веб-служб</span><span class="sxs-lookup"><span data-stu-id="347ff-102">Calling Web Service Methods</span></span>
  <span data-ttu-id="347ff-103">При использовании [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] класса прокси для вызова операций веб-службы это выполняется с помощью методов этого класса.</span><span class="sxs-lookup"><span data-stu-id="347ff-103">When you use a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proxy class to call Web service operations, you do so by using the methods of that class.</span></span> <span data-ttu-id="347ff-104">Эти методы работают аналогично любому другому методу в классе из библиотеки классов платформы [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="347ff-104">These methods respond like any other method of a class in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library.</span></span> <span data-ttu-id="347ff-105">Все методы веб-служб доступны для открытого доступа, при котором необходимо указывать соответствующее число аргументов и типы аргументов.</span><span class="sxs-lookup"><span data-stu-id="347ff-105">All Web service methods have public access and require you to supply the appropriate number of arguments and argument types.</span></span> <span data-ttu-id="347ff-106">После создания экземпляра класса-посредника в проекте можно вызывать методы для выполнения операций с отчетами на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="347ff-106">After you have created an instance of the proxy class in your project, you can call the methods to perform reporting operations via the report server.</span></span> <span data-ttu-id="347ff-107">В следующем коде на языке C# показано использование метода <xref:ReportService2010.ReportingService2010.ListChildren%2A> класса прокси <xref:ReportService2010.ReportingService2010>.</span><span class="sxs-lookup"><span data-stu-id="347ff-107">The following C# code illustrates the use of the <xref:ReportService2010.ReportingService2010.ListChildren%2A> method of the <xref:ReportService2010.ReportingService2010> proxy class.</span></span> <span data-ttu-id="347ff-108">Этот код используется для рекурсивного вызова веб-службы, которая возвращает массив объектов <xref:ReportService2010.CatalogItem>, содержащий список всех элементов в базе данных сервера отчетов:</span><span class="sxs-lookup"><span data-stu-id="347ff-108">The code is used to make a recursive call to the Web service that returns an array of <xref:ReportService2010.CatalogItem> objects that contains a list of all items in the report server database:</span></span>  
  
```vb  
Dim rs As New ReportingService2010()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
Dim items As CatalogItem() = rs.ListChildren("/", True)  
```  
  
```csharp  
ReportingService2010 rs = new ReportingService2010();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
CatalogItem[] items = rs.ListChildren("/", true);  
```  
  
## <a name="see-also"></a><span data-ttu-id="347ff-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="347ff-109">See Also</span></span>  
 <span data-ttu-id="347ff-110">[Создание приложений с помощью веб-службы и .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="347ff-110">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="347ff-111">[Веб-служба сервера отчетов](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="347ff-111">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="347ff-112">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="347ff-112">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
