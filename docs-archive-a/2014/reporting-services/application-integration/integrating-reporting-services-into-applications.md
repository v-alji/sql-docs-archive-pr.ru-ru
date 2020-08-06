---
title: Интеграция служб Reporting Services в приложения | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- integrating reports [Reporting Services]
- custom applications [SSRS]
- Reporting Services, application integration
- application integration [Reporting Services]
- reports [Reporting Services], integrating
ms.assetid: 49eb539c-d89b-4291-839a-0ec1a65cd270
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ab92008c5beb4d931e8e781857d766bb56a1efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654929"
---
# <a name="integrating-reporting-services-into-applications"></a><span data-ttu-id="dbb7d-102">Интеграция служб Reporting Services в приложения</span><span class="sxs-lookup"><span data-stu-id="dbb7d-102">Integrating Reporting Services into Applications</span></span>
  <span data-ttu-id="dbb7d-103">Службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] представляют собой открытую и расширяемую платформу создания отчетов, которая позволяет предоставить разработчикам всеобъемлющий набор API для разработки решений.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-103">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is an open and extensible reporting platform designed to provide developers with a comprehensive set of APIs for developing solutions.</span></span>  
  
 <span data-ttu-id="dbb7d-104">Существует три варианта интеграции [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в пользовательские приложения: веб-служба сервера отчетов, также известная как [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API SOAP, элементы управления ReportViewer для [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] и доступ по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-104">There are three options for integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into custom applications: the Report Server Web service, also known as the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP API, the ReportViewer controls for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)], and URL access.</span></span> <span data-ttu-id="dbb7d-105">В каждом из этих вариантов реализуется отдельный подход к интеграции служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в приложения.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-105">Each option provides a different approach for integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your applications.</span></span>  
  
## <a name="report-server-web-service"></a><span data-ttu-id="dbb7d-106">веб-служба сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="dbb7d-106">Report Server Web Service</span></span>  
 <span data-ttu-id="dbb7d-107">Веб-служба сервера отчетов является основным интерфейсом разработки приложений служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbb7d-107">The Report Server Web service is the primary interface for developing against [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="dbb7d-108">Эта веб-служба предоставляет все необходимые методы для интеграции служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в приложения, независимо от того, ведется ли разработка кода для управления каталогом отчетов или для подготовки отчетов в поддерживаемом формате.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-108">Whether you are developing code to manage your report catalog or developing code to render reports to a supported format, the Web service exposes all the necessary methods to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your applications.</span></span> <span data-ttu-id="dbb7d-109">Примером такого приложения может служить диспетчер отчетов, входящий в комплект поставки службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]; в нем веб-служба используется для управления базой данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-109">An example of one such application is Report Manager, which is included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]; it uses the Web service to manage the report server database.</span></span>  
  
## <a name="reportviewer-controls-for-visual-studio"></a><span data-ttu-id="dbb7d-110">Элементы управления ReportViewer для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dbb7d-110">ReportViewer Controls for Visual Studio</span></span>  
 <span data-ttu-id="dbb7d-111">Элементы управления ReportViewer, включенные в состав [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)], используются для интеграции средств просмотра отчетов в приложения.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-111">The ReportViewer controls included with [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] are used for integrating report viewing into your applications.</span></span> <span data-ttu-id="dbb7d-112">Имеется два элемента управления: один для приложений на основе Windows Forms, а другой — для приложений Web Forms.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-112">There are two controls: one for Windows Forms-based applications and one for Web Forms applications.</span></span> <span data-ttu-id="dbb7d-113">Каждый элемент управления обеспечивает возможность просмотра отчетов, развернутых на сервере отчетов, а также возможность отображения отчетов, существующих в среде, где сервер отчетов пока еще не установлен.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-113">Each control provides the capability for viewing reports that have been deployed to a report server as well as the ability to render reports that exist in an environment where a report server has not been installed.</span></span>  
  
## <a name="url-access"></a><span data-ttu-id="dbb7d-114">Доступ по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="dbb7d-114">URL Access</span></span>  
 <span data-ttu-id="dbb7d-115">Доступ по URL-адресу представляет собой еще один метод интеграции средств просмотра отчетов в приложения; он используется в случаях, когда применение элементов управления ReportViewer не представляется возможным.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-115">URL access is another option for integrating report viewing into your applications if the ReportViewer controls are not an option.</span></span> <span data-ttu-id="dbb7d-116">Метод доступа по URL-адресу также позволяет отправлять пользователям ссылки на отчеты по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-116">In addition, URL access is useful for sending links to reports to users via e-mail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dbb7d-117">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="dbb7d-117">In This Section</span></span>  
 [<span data-ttu-id="dbb7d-118">Интеграция служб Reporting Services по протоколу SOAP</span><span class="sxs-lookup"><span data-stu-id="dbb7d-118">Integrating Reporting Services Using SOAP</span></span>](../application-integration/integrating-reporting-services-using-soap.md)  
 <span data-ttu-id="dbb7d-119">Описывает способ интеграции средств навигации по отчетам и управления отчетами служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в существующие бизнес-приложения с помощью веб-службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-119">Describes how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation and management into your existing business applications using the Report Server Web service.</span></span>  
  
 [<span data-ttu-id="dbb7d-120">Интеграция служб Reporting Services с помощью элементов управления ReportViewer</span><span class="sxs-lookup"><span data-stu-id="dbb7d-120">Integrating Reporting Services Using the ReportViewer Controls</span></span>](../application-integration/integrating-reporting-services-using-reportviewer-controls.md)  
 <span data-ttu-id="dbb7d-121">Описывает способ интеграции средств просмотра отчетов в существующие приложения с помощью элементов управления ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-121">Describes how to integrate report viewing into your existing applications using the ReportViewer controls.</span></span>  
  
 [<span data-ttu-id="dbb7d-122">Интеграция служб Reporting Services с помощью доступа по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="dbb7d-122">Integrating Reporting Services Using URL Access</span></span>](../application-integration/integrating-reporting-services-using-url-access.md)  
 <span data-ttu-id="dbb7d-123">Описывает способ интеграции средств навигации по отчетам служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в существующие бизнес-приложения с помощью доступа по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="dbb7d-123">Describes how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation into your existing business applications using URL access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb7d-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="dbb7d-124">See Also</span></span>  
 <span data-ttu-id="dbb7d-125">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="dbb7d-125">[Report Manager  &#40;SSRS Native Mode&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="dbb7d-126">[Выбор между доступом по URL-адресу и SOAP](../../../2014/reporting-services/application-integration/choosing-between-url-access-and-soap.md) </span><span class="sxs-lookup"><span data-stu-id="dbb7d-126">[Choosing Between URL Access and SOAP](../../../2014/reporting-services/application-integration/choosing-between-url-access-and-soap.md) </span></span>  
 <span data-ttu-id="dbb7d-127">[Технический справочник &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dbb7d-127">[Technical Reference &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="dbb7d-128">Веб-службы сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="dbb7d-128">Report Server Web Service</span></span>](../report-server-web-service/report-server-web-service.md)  
  
  
