---
title: Интеграция служб Reporting Services с использованием протокола SOAP | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, application integration
- SOAP [Reporting Services]
- SOAP [Reporting Services], about report integration
- integrating reports [Reporting Services]
- Web service [Reporting Services], application integration
ms.assetid: 6bc17af5-883c-4bfa-87d9-48cd7056d145
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7b6fffd65b22900d7c505c4b50ec290b95fe9ab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654923"
---
# <a name="integrating-reporting-services-using-soap"></a><span data-ttu-id="e3aa5-102">Интеграция служб Reporting Services по протоколу SOAP</span><span class="sxs-lookup"><span data-stu-id="e3aa5-102">Integrating Reporting Services Using SOAP</span></span>
  <span data-ttu-id="e3aa5-103">[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API SOAP предоставляет несколько конечных точек веб-службы для разработки пользовательских решений для создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="e3aa5-103">The [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP API provides several Web service endpoints for developing custom reporting solutions.</span></span> <span data-ttu-id="e3aa5-104">Конечные точки в данный момент делятся на две категории: управления и выполнения.</span><span class="sxs-lookup"><span data-stu-id="e3aa5-104">The endpoints currently fall into two categories: management and execution.</span></span> <span data-ttu-id="e3aa5-105">Функции управления реализованы с помощью конечных точек <xref:ReportService2005>, <xref:ReportService2006> и <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="e3aa5-105">The management functionality is exposed through the <xref:ReportService2005>, <xref:ReportService2006>, and <xref:ReportService2010> endpoints.</span></span> <span data-ttu-id="e3aa5-106">Конечная точка <xref:ReportService2005> используется для управления сервером отчетов, настроенным для работы в собственном режиме; конечная точка <xref:ReportService2006> используется для управления сервером отчетов, настроенным для работы в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e3aa5-106">The <xref:ReportService2005> endpoint is used for managing a report server that is configured in native mode and the <xref:ReportService2006> endpoint is used for managing a report server that is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="e3aa5-107">Конечная точка <xref:ReportService2010> объединяет функциональные возможности конечных точек <xref:ReportService2005> и <xref:ReportService2006> и может управлять сервером отчетов, настроенном для работы в собственном режиме или режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e3aa5-107">The <xref:ReportService2010> merges the functionalities of <xref:ReportService2005> and <xref:ReportService2006> and can manage a report server that is configured for either native or SharePoint integrated mode.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3aa5-108">Конечные точки <xref:ReportService2005> и <xref:ReportService2006> являются устаревшими в [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3aa5-108">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="e3aa5-109">Конечная точка <xref:ReportService2010> содержит функциональные возможности обеих конечных точек, а также содержит дополнительные функции управления.</span><span class="sxs-lookup"><span data-stu-id="e3aa5-109">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
 <span data-ttu-id="e3aa5-110">Функциональные возможности выполнения реализуются посредством конечной точки <xref:ReportExecution2005>, которая используется, если сервер отчетов настроен как на работу в собственном режиме, так и на работу в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e3aa5-110">The execution functionality is exposed through the <xref:ReportExecution2005> endpoint and it is used when the report server is configured in native or SharePoint integrated mode.</span></span> <span data-ttu-id="e3aa5-111">В следующих разделах показывается, как данные конечные точки могут быть использованы для разработки решений по созданию отчетов в [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, SharePoint и веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="e3aa5-111">The following topics show how these endpoints can be used for developing reporting solutions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, SharePoint, and Web applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3aa5-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="e3aa5-112">In This Section</span></span>  
 [<span data-ttu-id="e3aa5-113">Использование API SOAP в приложении Windows</span><span class="sxs-lookup"><span data-stu-id="e3aa5-113">Using the SOAP API in a Windows Application</span></span>](integrating-reporting-services-using-soap-windows-application.md)  
 <span data-ttu-id="e3aa5-114">Описывает, как можно использовать API-интерфейс SOAP для интеграции служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в среду Windows.</span><span class="sxs-lookup"><span data-stu-id="e3aa5-114">Describes how to use the SOAP API to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Windows environment.</span></span>  
  
 [<span data-ttu-id="e3aa5-115">Использование API SOAP в веб-приложении</span><span class="sxs-lookup"><span data-stu-id="e3aa5-115">Using the SOAP API in a Web Application</span></span>](integrating-reporting-services-using-soap-web-application.md)  
 <span data-ttu-id="e3aa5-116">Описывает, как можно использовать API-интерфейс SOAP для интеграции служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в веб-среду.</span><span class="sxs-lookup"><span data-stu-id="e3aa5-116">Describes how to use the SOAP API to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Web environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3aa5-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3aa5-117">See Also</span></span>  
 <span data-ttu-id="e3aa5-118">[Интеграция Reporting Services в приложения](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="e3aa5-118">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="e3aa5-119">[Веб-служба сервера отчетов](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="e3aa5-119">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 [<span data-ttu-id="e3aa5-120">Создание приложений с помощью веб-службы и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e3aa5-120">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
