---
title: Доступ к интерфейсу API SOAP | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- XML Web service [Reporting Services], WSDL
- Web service [Reporting Services], SOAP
- calling Web service
- SOAP [Reporting Services], accessing
- Report Server Web service, SOAP
- Web service [Reporting Services], WSDL
- WSDL [Reporting Services]
- XML Web service [Reporting Services], SOAP
- Report Server Web service, WSDL
- referencing WSDL
ms.assetid: 63bb870a-4dbf-46bd-8921-78f8ebe5fd75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6e8a0c21bb53deff746cfd916b6ae2c96fa0de19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667552"
---
# <a name="accessing-the-soap-api"></a><span data-ttu-id="f1ecf-102">Доступ к API-интерфейсу SOAP</span><span class="sxs-lookup"><span data-stu-id="f1ecf-102">Accessing the SOAP API</span></span>
  <span data-ttu-id="f1ecf-103">Веб-служба сервера отчетов использует протокол SOAP по протоколу HTTP и выступает в роли интерфейса связи между клиентскими программами и сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-103">The Report Server Web service uses Simple Object Access Protocol (SOAP) over HTTP and acts as a communications interface between client programs and the report server.</span></span> <span data-ttu-id="f1ecf-104">Веб-служба предоставляет две конечные точки — одну для выполнения отчетов и другую для управления отчетами. Веб-служба состоит из методов и набора объектов сложного типа, которые можно использовать для доступа ко всем функциональным возможностям служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1ecf-104">The Web service provides two endpoints - one for report execution and one for report management - and consists of methods and a set of complex type objects that you can use to access the complete functionality of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="f1ecf-105">Для вызова службы следует создать ссылку на язык описания веб-служб (WSDL) служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-105">To call the service, you must reference the Reporting Services Web Services Description Language (WSDL).</span></span>  
  
## <a name="referencing-the-reporting-services-wsdl"></a><span data-ttu-id="f1ecf-106">Создание ссылок на язык WSDL для служб Reporting Services </span><span class="sxs-lookup"><span data-stu-id="f1ecf-106">Referencing the Reporting Services WSDL</span></span>  
 <span data-ttu-id="f1ecf-107">Для успешного вызова веб-службы следует знать способ доступа к данной службе, поддерживаемые ей операции, параметры, ожидаемые этой службой, а также данные, которые она возвращает</span><span class="sxs-lookup"><span data-stu-id="f1ecf-107">To call a Web service successfully, you must know how to access the service, what operations the service supports, what parameters the service expects, and what the service returns.</span></span> <span data-ttu-id="f1ecf-108">С помощью языка WSDL эти данные предоставляются в XML-документе, который может быть считан или обработан компьютером.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-108">WSDL provides this information in an XML document that can be read or processed by a computer.</span></span>  
  
 <span data-ttu-id="f1ecf-109">Веб-службы сервера отчетов доступны в трех различных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-109">The Report Server Web services are exposed in three different endpoints.</span></span> <span data-ttu-id="f1ecf-110">Имя WSDL-файла у каждой конечной точки свое.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-110">The name of the WSDL file is different for each endpoint.</span></span> <span data-ttu-id="f1ecf-111">Конечная точка <xref:ReportService2010> содержит методы для управления объектами в сервере отчетов как в собственном режиме, так и в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-111">The <xref:ReportService2010> endpoint contains methods for managing objects in a Report Server in either native or SharePoint integrated mode.</span></span> <span data-ttu-id="f1ecf-112">Обратиться к WSDL-файлу данной конечной точки можно по адресу `ReportService2010.asmx?wsdl.`.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-112">The WSDL for this endpoint is accessed through `ReportService2010.asmx?wsdl.`</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1ecf-113">Конечные точки <xref:ReportService2005> и <xref:ReportService2006> являются устаревшими в [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1ecf-113">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="f1ecf-114">Конечная точка <xref:ReportService2010> содержит функциональные возможности обеих конечных точек, а также содержит дополнительные функции управления.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-114">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
-   <span data-ttu-id="f1ecf-115">Конечная точка <xref:ReportExecution2005> позволяет разработчикам программным образом обрабатывать и подготавливать к просмотру отчеты на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-115">The <xref:ReportExecution2005> endpoint allows developers to programmatically process and render reports in a Report Server.</span></span> <span data-ttu-id="f1ecf-116">Обратиться к WSDL-файлу данной конечной точки можно по адресу `ReportExecution2005.asmx?wsdl`</span><span class="sxs-lookup"><span data-stu-id="f1ecf-116">The WSDL for this endpoint is accessed through `ReportExecution2005.asmx?wsdl`.</span></span>  
  
 <span data-ttu-id="f1ecf-117">WSDL может использоваться пакетами разработки, поддерживающими SOAP и веб-службы, например [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] пакетом SDK.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-117">WSDL can be consumed by development kits that support SOAP and Web services, such as the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="f1ecf-118">В следующем примере показывается формат URL-адреса управляющего WSDL-файла служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f1ecf-118">The following example shows the format of the URL to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] management WSDL file:</span></span>  
  
```  
http://server/reportserver/ReportService2010.asmx?wsdl  
```  
  
 <span data-ttu-id="f1ecf-119">В следующей таблице описывается каждый элемент URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-119">The following table describes each element in the URL.</span></span>  
  
|<span data-ttu-id="f1ecf-120">Элемент URL-адреса</span><span class="sxs-lookup"><span data-stu-id="f1ecf-120">URL element</span></span>|<span data-ttu-id="f1ecf-121">Описание</span><span class="sxs-lookup"><span data-stu-id="f1ecf-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f1ecf-122">*server*</span><span class="sxs-lookup"><span data-stu-id="f1ecf-122">*server*</span></span>|<span data-ttu-id="f1ecf-123">Имя сервера, на котором развернут сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-123">The name of the server on which the report server is deployed.</span></span>|  
|<span data-ttu-id="f1ecf-124">*ReportServer*</span><span class="sxs-lookup"><span data-stu-id="f1ecf-124">*reportserver*</span></span>|<span data-ttu-id="f1ecf-125">Имя папки, в которой содержится веб-служба XML.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-125">The name of the folder that contains the XML Web service.</span></span> <span data-ttu-id="f1ecf-126">Данный элемент настраивается во время установки.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-126">This is configured during setup.</span></span>|  
|<span data-ttu-id="f1ecf-127">*\<endpoint name>ASMX*</span><span class="sxs-lookup"><span data-stu-id="f1ecf-127">*\<endpoint name>.asmx*</span></span>|<span data-ttu-id="f1ecf-128">Имя конечной точки веб-службы.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-128">The name of the web service endpoint.</span></span>|  
  
 <span data-ttu-id="f1ecf-129">Дополнительные сведения о формате WSDL см. в спецификации языка WSDL см. на веб-сайте консорциума W3C: http://www.w3.org/TR/wsdl.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-129">For more information about the WSDL format, see the World Wide Web Consortium (W3C) WSDL specification at http://www.w3.org/TR/wsdl.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ecf-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="f1ecf-130">See Also</span></span>  
 <span data-ttu-id="f1ecf-131">[Создание приложений с помощью веб-службы и .NET Framework](net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="f1ecf-131">[Building Applications Using the Web Service and the .NET Framework](net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="f1ecf-132">Веб-службы сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="f1ecf-132">Report Server Web Service</span></span>](report-server-web-service.md)  
  
  
