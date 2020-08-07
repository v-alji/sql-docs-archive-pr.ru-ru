---
title: Конечные точки веб-службы сервера отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- management endpoints [Reporting Services]
- Web service [Reporting Services], endpoints
- endpoints [Reporting Services]
- execution endpoints [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: f3f5d85f-9359-4508-bc5a-7f78a3cf7421
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70281c5171eb37d9888d663542a7850820c81bea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733549"
---
# <a name="report-server-web-service-endpoints"></a><span data-ttu-id="f42d3-102">Конечные точки веб-службы сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="f42d3-102">Report Server Web Service Endpoints</span></span>
  <span data-ttu-id="f42d3-103">Веб-служба сервера отчетов предоставляет несколько конечных точек для управления сервером отчетов, а также для выполнения отчетов и перемещения по ним.</span><span class="sxs-lookup"><span data-stu-id="f42d3-103">The Report Server Web service provides several endpoints for managing a report server as well as executing and navigating reports.</span></span>  
  
## <a name="the-management-endpoints"></a><span data-ttu-id="f42d3-104">Конечные точки управления</span><span class="sxs-lookup"><span data-stu-id="f42d3-104">The Management Endpoints</span></span>  
 <span data-ttu-id="f42d3-105">Для управления объектами на сервере отчетов доступны три конечные точки — <xref:ReportService2005>, <xref:ReportService2006> и <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="f42d3-105">There are three endpoints available for managing objects on a report server, <xref:ReportService2005>, <xref:ReportService2006>, and <xref:ReportService2010>.</span></span> <span data-ttu-id="f42d3-106">Конечная точка <xref:ReportService2005> используется для управления объектами на сервере отчетов, настроенном для работы в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="f42d3-106">The <xref:ReportService2005> endpoint is used for managing objects on a report server that is configured for native mode.</span></span> <span data-ttu-id="f42d3-107">Конечная точка <xref:ReportService2006> используется для управления объектами на сервере отчетов, настроенном для работы в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f42d3-107">The <xref:ReportService2006> endpoint is used for managing objects on a report server that is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="f42d3-108">Конечная точка <xref:ReportService2010> объединяет функциональные возможности конечных точек <xref:ReportService2005> и <xref:ReportService2006> и может управлять объектами на сервере отчетов, настроенном для работы в собственном режиме или режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f42d3-108">The <xref:ReportService2010> endpoint merges the functionalities of <xref:ReportService2005> and <xref:ReportService2006> and can manage objects on a report server that are configured for either native or SharePoint integrated mode.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f42d3-109">Если сервер отчетов настроен для работы в режиме интеграции с SharePoint, API из пространства имен <xref:ReportService2005> будут возвращать ошибку `rsOperationNotSupportedSharePointMode`.</span><span class="sxs-lookup"><span data-stu-id="f42d3-109">When a report server is configured for SharePoint integrated mode, the <xref:ReportService2005> APIs will return an `rsOperationNotSupportedSharePointMode` error.</span></span> <span data-ttu-id="f42d3-110">Если сервер отчетов настроен для работы в собственном режиме, API из пространства имен <xref:ReportService2006> будут возвращать ошибку `rsOperationNotSupportedNativeMode`.</span><span class="sxs-lookup"><span data-stu-id="f42d3-110">If the report server is configured for native mode, the <xref:ReportService2006> APIs will return an `rsOperationNotSupportedNativeMode` error.</span></span> <span data-ttu-id="f42d3-111">Аналогично, если зависящие от режима API-интерфейсы в <xref:ReportService2010> используются в непредусмотренных режимах, они вернут соответствующие ошибки.</span><span class="sxs-lookup"><span data-stu-id="f42d3-111">Similarly, when mode-specific APIs in <xref:ReportService2010> are used on unintended modes, the APIs will return the respective errors.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f42d3-112">Конечные точки <xref:ReportService2005> и <xref:ReportService2006> являются устаревшими в [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f42d3-112">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="f42d3-113">Конечная точка <xref:ReportService2010> содержит функциональные возможности обеих конечных точек, а также содержит дополнительные функции управления.</span><span class="sxs-lookup"><span data-stu-id="f42d3-113">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
 <span data-ttu-id="f42d3-114">Если сервер отчетов настроен для работы в собственном режиме или в режиме интеграции с SharePoint, WSDL-файл для управления конечной точкой доступен по одному из следующих URL-адресов:</span><span class="sxs-lookup"><span data-stu-id="f42d3-114">If the report server is configured for native mode or SharePoint integrate mode, the WSDL for the management endpoint can be accessed using one of the following URL:</span></span>  
  
```  
http://<Server Name>/ReportServer/ReportService2010.asmx?wsdl  
```  
  
 <span data-ttu-id="f42d3-115">Дополнительные сведения см. в разделе [Доступ к API-интерфейсу SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="f42d3-115">For more information, see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
## <a name="the-execution-endpoint"></a><span data-ttu-id="f42d3-116">Конечная точка выполнения</span><span class="sxs-lookup"><span data-stu-id="f42d3-116">The Execution Endpoint</span></span>  
 <span data-ttu-id="f42d3-117">Конечная точка <xref:ReportExecution2005> упрощает для разработчиков настройку обработки отчетов и подготовку отчетов к просмотру с сервера отчетов, работающего в собственном режиме и в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f42d3-117">The <xref:ReportExecution2005> endpoint makes it easy for developers to customize report processing and rendering from a report server in both native and SharePoint integrated modes.</span></span> <span data-ttu-id="f42d3-118">Эта конечная точка содержит классы и методы, которые существовали в прежних версиях веб-службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="f42d3-118">The endpoint includes classes and methods that existed in earlier versions of the Report Server Web service.</span></span> <span data-ttu-id="f42d3-119">Кроме того, в веб-службу сервера отчетов было добавлено несколько новых классов и методов, доступных через конечную точку выполнения.</span><span class="sxs-lookup"><span data-stu-id="f42d3-119">In addition, many new classes and methods have been added to the Report Server Web service that are exposed through the execution endpoint.</span></span>  
  
 <span data-ttu-id="f42d3-120">WSDL-файл для конечной точки управления доступен по следующему URL-адресу:</span><span class="sxs-lookup"><span data-stu-id="f42d3-120">The WSDL for the management endpoint can be accessed using the following URL:</span></span>  
  
```  
http://<Server Name>/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 <span data-ttu-id="f42d3-121">Если сервер отчетов настроен в режиме интеграции с SharePoint, WSDL-файл доступен по следующему URL-адресу:</span><span class="sxs-lookup"><span data-stu-id="f42d3-121">If the report server is configured for SharePoint integrate mode, the WSDL can be accessed using the following URL:</span></span>  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 <span data-ttu-id="f42d3-122">Дополнительные сведения см. в разделе [Доступ к API-интерфейсу SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="f42d3-122">For more information, please see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
## <a name="sharepoint-proxy-endpoints"></a><span data-ttu-id="f42d3-123">Конечные точки-посредники SharePoint</span><span class="sxs-lookup"><span data-stu-id="f42d3-123">SharePoint Proxy Endpoints</span></span>  
 <span data-ttu-id="f42d3-124">Если сервер отчетов настроен в режиме интеграции с SharePoint и установлена надстройка служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], то на сервере SharePoint устанавливается набор конечных точек-посредников.</span><span class="sxs-lookup"><span data-stu-id="f42d3-124">When a report server is configured for SharePoint integrated mode and the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in has been installed, a set of proxy endpoints are installed on the SharePoint server.</span></span> <span data-ttu-id="f42d3-125">Конечные точки-посредники являются главным API для разработки решений отчетов, если сервер отчетов настроен для работы в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f42d3-125">The proxy endpoints are the primary API for developing report solutions when a report server is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="f42d3-126">Во время разработки на основе конечных точек-посредников надстройка служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] управляет обменом учетными данными между сервером SharePoint и сервером отчетов в режиме проверки подлинности с доверенной учетной записью.</span><span class="sxs-lookup"><span data-stu-id="f42d3-126">When developing against the proxy endpoints, the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in manages the exchange of credentials between the SharePoint server and the report server in Trusted account authentication mode.</span></span> <span data-ttu-id="f42d3-127">Во время разработки с использованием конечных точек сервера отчетов вызывающее приложение должно управлять обменом учетными данными в режиме проверки подлинности с доверенной учетной записью.</span><span class="sxs-lookup"><span data-stu-id="f42d3-127">When developing against the report server endpoints, the calling application will have to manage the credential exchange in Trusted account authentication mode.</span></span> <span data-ttu-id="f42d3-128">В следующей таблице перечислены конечные точки, которые устанавливаются с надстройкой служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f42d3-128">The following table lists the endpoints that are installed with the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in.</span></span>  
  
|<span data-ttu-id="f42d3-129">Конечная точка-посредник</span><span class="sxs-lookup"><span data-stu-id="f42d3-129">Proxy Endpoint</span></span>|<span data-ttu-id="f42d3-130">Описание</span><span class="sxs-lookup"><span data-stu-id="f42d3-130">Description</span></span>|  
|--------------------|-----------------|  
|<xref:ReportService2006>|<span data-ttu-id="f42d3-131">Предоставляет интерфейсы API для управления сервером отчетов, настроенным для работы в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f42d3-131">Provides the APIs for managing a report server that is configured for SharePoint integrate mode.</span></span> <span data-ttu-id="f42d3-132">**Примечание.**  Эта конечная точка является устаревшей в [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f42d3-132">**Note:**  This endpoint is deprecated in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span></span>|  
|<xref:ReportService2010>|<span data-ttu-id="f42d3-133">Предоставляет API-интерфейсы для управления сервером отчетов, настроенным для работы в собственном режиме или в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f42d3-133">Provides the APIs for managing a report server that is configured for either native or SharePoint integrated mode.</span></span>|  
|<xref:ReportExecution2005>|<span data-ttu-id="f42d3-134">Предоставляет интерфейсы API для выполнения отчетов и перемещению по ним.</span><span class="sxs-lookup"><span data-stu-id="f42d3-134">Provides the APIs for running and navigating reports.</span></span>|  
|<xref:ReportServiceAuthentication>|<span data-ttu-id="f42d3-135">Предоставляет интерфейсы API для проверки подлинности пользователей на сервере отчетов, если веб-приложение SharePoint настроено для проверки подлинности с помощью форм.</span><span class="sxs-lookup"><span data-stu-id="f42d3-135">Provides the APIs for authenticating users against a report server when the SharePoint Web application is configured for Forms Authentication.</span></span>|  
  
 <span data-ttu-id="f42d3-136">Далее приведены примеры URL-адресов для ссылок на конечные точки-посредники на сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f42d3-136">The following are example URLs for referencing the proxy endpoints on a SharePoint site.</span></span>  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportService2010.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportServiceAuthentication.asmx  
```  
  
## <a name="see-also"></a><span data-ttu-id="f42d3-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="f42d3-137">See Also</span></span>  
 [<span data-ttu-id="f42d3-138">Создание приложений с помощью веб-службы и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f42d3-138">Building Applications Using the Web Service and the .NET Framework</span></span>](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
