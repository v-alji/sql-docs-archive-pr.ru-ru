---
title: Роль протокола SOAP в службах Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- SOAP [Reporting Services], role in Reporting Services
- Report Server Web service, SOAP
- XML Web service [Reporting Services], SOAP
ms.assetid: f229c3ef-f2ca-448f-98f1-b8df350b9992
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05445eb1c95c5761595944867b6d0c20a6f1a412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732417"
---
# <a name="the-role-of-soap-in-reporting-services"></a><span data-ttu-id="9b196-102">The Role of SOAP in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9b196-102">The Role of SOAP in Reporting Services</span></span>
  <span data-ttu-id="9b196-103">Веб-служба сервера отчетов использует обмен сообщениями по протоколу SOAP для отправки текстовых команд по сети.</span><span class="sxs-lookup"><span data-stu-id="9b196-103">The Report Server Web service uses Simple Object Access Protocol (SOAP) messaging to send text-based commands over a network.</span></span> <span data-ttu-id="9b196-104">Эти команды имеют вид XML-текста, передаваемого через Интернет по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="9b196-104">These commands take the form of XML text that is sent over the World Wide Web using HTTP.</span></span> <span data-ttu-id="9b196-105">Использование протокола связи SOAP в веб-службе сервера отчетов позволяет приложениям и компонентам обмениваться данными с сервером отчетов, используя широко признанную открытую инфраструктуру.</span><span class="sxs-lookup"><span data-stu-id="9b196-105">By using SOAP as its communication protocol, the Report Server Web service allows applications and components to exchange data with the report server using an open and widely accepted infrastructure.</span></span> <span data-ttu-id="9b196-106">Стандарт SOAP определен на веб-сайте www.w3.org/TR/SOAP.</span><span class="sxs-lookup"><span data-stu-id="9b196-106">The SOAP standard is defined at www.w3.org/TR/SOAP.</span></span>  
  
 <span data-ttu-id="9b196-107">В качестве клиента SOAP может выступать любое приложение, которое поддерживает протокол SOAP и может отправлять SOAP-запросы.</span><span class="sxs-lookup"><span data-stu-id="9b196-107">Any client application can act as a SOAP client as long as it is SOAP-aware and can send SOAP requests.</span></span> <span data-ttu-id="9b196-108">Примером такого клиента SOAP является диспетчер отчетов.</span><span class="sxs-lookup"><span data-stu-id="9b196-108">Report Manager is one such SOAP client.</span></span> <span data-ttu-id="9b196-109">Он предоставляет интерфейс к базе данных сервера отчетов, в которой хранятся все отчеты и относящееся к ним содержимое.</span><span class="sxs-lookup"><span data-stu-id="9b196-109">It provides an interface to the report server database in which all reports and report-related content is stored.</span></span> <span data-ttu-id="9b196-110">Пользователи этого приложения могут просматривать папки и отчеты в пространстве имен сервера отчетов и работать с отчетами.</span><span class="sxs-lookup"><span data-stu-id="9b196-110">End users can use the application to browse through and manage reports and folders in the report server namespace.</span></span> <span data-ttu-id="9b196-111">Диспетчер отчетов построен на инфраструктуре веб-службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9b196-111">Report Manager is built on the Report Server Web service infrastructure.</span></span>  
  
 <span data-ttu-id="9b196-112">Сервер отчетов выступает в роли сервера SOAP — службы, которая поддерживает протокол SOAP, может принимать запросы от клиентов SOAP и формировать необходимые ответные сообщения.</span><span class="sxs-lookup"><span data-stu-id="9b196-112">A report server acts as a SOAP server, a SOAP-aware service that can accept requests from SOAP clients and create appropriate responses.</span></span> <span data-ttu-id="9b196-113">Сервер обрабатывает запросы и посылает клиенту закодированные ответные сообщения.</span><span class="sxs-lookup"><span data-stu-id="9b196-113">The server handles the requests and sends encoded responses back to the client.</span></span>  
  
 <span data-ttu-id="9b196-114">Сообщения SOAP в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] могут принимать множество различных форм в зависимости от типа запроса, выполненного клиентом.</span><span class="sxs-lookup"><span data-stu-id="9b196-114">SOAP messages in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] take many different forms, depending on the type of request made by the client.</span></span> <span data-ttu-id="9b196-115">В следующем примере показан простой запрос клиента SOAP для удаления элемента из базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9b196-115">The following example represents a simple SOAP client request to remove an item from the report server database.</span></span>  
  
```  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <soap:Body>  
        <DeleteItem xmlns="https://www.microsoft.com/sql/ReportingServer">  
            <item>/Samples/Report1</item>  
        </DeleteItem>  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="9b196-116">Протокол SOAP требует, чтобы сообщения помещались в элемент `Envelope`, а большая часть сообщения располагалась в элементе `Body`.</span><span class="sxs-lookup"><span data-stu-id="9b196-116">The SOAP itself requires that messages be put into an `Envelope` element, with the bulk of the message inside a `Body` element.</span></span> <span data-ttu-id="9b196-117">В этом примере элемент Body содержит вызов метода <xref:ReportService2010.ReportingService2010.DeleteItem%2A>, который принимает строковый параметр, представляющий путь к удаляемому элементу.</span><span class="sxs-lookup"><span data-stu-id="9b196-117">In this example, the body contains a call to the <xref:ReportService2010.ReportingService2010.DeleteItem%2A> method, which takes a string parameter representing the path of the item to delete.</span></span> <span data-ttu-id="9b196-118">Вы можете создать [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] клиентский прокси-класс, который инкапсулирует все операции SOAP в методы.</span><span class="sxs-lookup"><span data-stu-id="9b196-118">You can create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] client proxy class that encapsulates all SOAP operations into methods.</span></span> <span data-ttu-id="9b196-119">Следующий [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] метод представляет пример SOAP, заданный ранее.</span><span class="sxs-lookup"><span data-stu-id="9b196-119">The following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] method represents the SOAP example given earlier.</span></span>  
  
```  
public void DeleteItem(string item);  
```  
  
 <span data-ttu-id="9b196-120">Ответ от сервера имеет приблизительно следующий вид:</span><span class="sxs-lookup"><span data-stu-id="9b196-120">The response from the server might look like the following:</span></span>  
  
```  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <soap:Body>  
        <DeleteItemResponse xmlns="https://www.microsoft.com/sql/ReportingServer" />  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="9b196-121">Метод <xref:ReportService2010.ReportingService2010.DeleteItem%2A> не имеет возвращаемого значения, поэтому возвращается пустой ответ.</span><span class="sxs-lookup"><span data-stu-id="9b196-121">The <xref:ReportService2010.ReportingService2010.DeleteItem%2A> method has no return value, so an empty response is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b196-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b196-122">See Also</span></span>  
 <span data-ttu-id="9b196-123">[Доступ к API SOAP](accessing-the-soap-api.md) </span><span class="sxs-lookup"><span data-stu-id="9b196-123">[Accessing the SOAP API](accessing-the-soap-api.md) </span></span>  
 <span data-ttu-id="9b196-124">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="9b196-124">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="9b196-125">[Сервер отчетов Reporting Services](../reporting-services-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b196-125">[Reporting Services Report Server](../reporting-services-report-server.md) </span></span>  
 [<span data-ttu-id="9b196-126">Веб-службы сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="9b196-126">Report Server Web Service</span></span>](report-server-web-service.md)  
  
  
