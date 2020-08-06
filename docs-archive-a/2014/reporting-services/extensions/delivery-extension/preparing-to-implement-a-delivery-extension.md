---
title: Подготовка к реализации модуля доставки | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- interfaces [Reporting Services]
- delivery extensions [Reporting Services], implementing
ms.assetid: aee1608d-374f-4ad3-bc23-fe07fdaa52b7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bbf98286e6ed35542d8117b4b87b5ff3425def69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669302"
---
# <a name="preparing-to-implement-a-delivery-extension"></a><span data-ttu-id="aaaae-102">Подготовка к реализации модуля доставки</span><span class="sxs-lookup"><span data-stu-id="aaaae-102">Preparing to Implement a Delivery Extension</span></span>
  <span data-ttu-id="aaaae-103">Перед реализацией модуля доставки служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] следует определить реализуемые интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="aaaae-103">Before you implement your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, you should define the interfaces to implement.</span></span> <span data-ttu-id="aaaae-104">Вначале необходимо решить, как будет использоваться модуль доставки, какие параметры будут необходимы для модуля и какие функции будет необходимо реализовать для доставки уведомлений об отчетах.</span><span class="sxs-lookup"><span data-stu-id="aaaae-104">You first need to decide how your delivery extension will be used, what settings your delivery extension will require, and the specific functionality you will need to implement in order to deliver report notifications.</span></span>  
  
 <span data-ttu-id="aaaae-105">Каждый модуль доставки служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] должен предоставлять следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="aaaae-105">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension must provide the following functionality:</span></span>  
  
-   <span data-ttu-id="aaaae-106">реализацию интерфейса <xref:Microsoft.ReportingServices.Interfaces.IExtension>, который представляет модуль и локализованное имя модуля;</span><span class="sxs-lookup"><span data-stu-id="aaaae-106">An <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface implementation that represents the extension and a localized extension name.</span></span>  
  
-   <span data-ttu-id="aaaae-107">реализацию интерфейса <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>, который создает модуль доставки, используемый для доставки пользователям уведомлений об отчетах;</span><span class="sxs-lookup"><span data-stu-id="aaaae-107">An <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> implementation that creates a delivery extension that can be used to deliver report notifications to end users.</span></span>  
  
-   <span data-ttu-id="aaaae-108">возможность обработки пользовательских данных для подписки.</span><span class="sxs-lookup"><span data-stu-id="aaaae-108">The ability to process specific user data for a subscription.</span></span>  
  
 <span data-ttu-id="aaaae-109">Каждый модуль доставки можно улучшить, добавив следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="aaaae-109">Each delivery extension can be enhanced to include the following functionality:</span></span>  
  
-   <span data-ttu-id="aaaae-110">реализацию пользовательского элемента управления [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], которая дает пользователям возможность использовать диспетчер отчетов для создания подписок на отчеты, использующих модуль доставки.</span><span class="sxs-lookup"><span data-stu-id="aaaae-110">An [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] user control implementation that enables end users to use Report Manager to create report subscriptions that use the delivery extension.</span></span>  
  
 <span data-ttu-id="aaaae-111">В следующей таблице описаны доступные интерфейсы и классы для модулей доставки.</span><span class="sxs-lookup"><span data-stu-id="aaaae-111">The following table describes the available interfaces and classes for delivery extensions.</span></span>  
  
|<span data-ttu-id="aaaae-112">Интерфейс или класс</span><span class="sxs-lookup"><span data-stu-id="aaaae-112">Interface or class</span></span>|<span data-ttu-id="aaaae-113">Description</span><span class="sxs-lookup"><span data-stu-id="aaaae-113">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="aaaae-114"><xref:Microsoft.ReportingServices.Interfaces.IExtension> Интерфейс</span><span class="sxs-lookup"><span data-stu-id="aaaae-114"><xref:Microsoft.ReportingServices.Interfaces.IExtension> Interface</span></span>|<span data-ttu-id="aaaae-115">Представляет модуль в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaaae-115">Represents an extension in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|<span data-ttu-id="aaaae-116"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> Интерфейс</span><span class="sxs-lookup"><span data-stu-id="aaaae-116"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> Interface</span></span>|<span data-ttu-id="aaaae-117">Представляет модуль доставки в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaaae-117">Represents a delivery extension in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|<span data-ttu-id="aaaae-118"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> Интерфейс</span><span class="sxs-lookup"><span data-stu-id="aaaae-118"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> Interface</span></span>|<span data-ttu-id="aaaae-119">Содержит сведения о сервере отчетов, которые необходимы модулям доставки (например, список доступных модулей подготовки отчетов).</span><span class="sxs-lookup"><span data-stu-id="aaaae-119">Contains information about the report server that is required by delivery extensions (for example, a list of the available rendering extensions).</span></span>|  
|<span data-ttu-id="aaaae-120">Класс <xref:Microsoft.ReportingServices.Interfaces.Setting></span><span class="sxs-lookup"><span data-stu-id="aaaae-120"><xref:Microsoft.ReportingServices.Interfaces.Setting> Class</span></span>|<span data-ttu-id="aaaae-121">Представляет параметр модуля.</span><span class="sxs-lookup"><span data-stu-id="aaaae-121">Represents a setting for an extension.</span></span>|  
|<span data-ttu-id="aaaae-122">Класс <xref:Microsoft.ReportingServices.Interfaces.Notification></span><span class="sxs-lookup"><span data-stu-id="aaaae-122"><xref:Microsoft.ReportingServices.Interfaces.Notification> Class</span></span>|<span data-ttu-id="aaaae-123">Содержит сведения о подписке, используемые модулями доставки для доставки отчетов.</span><span class="sxs-lookup"><span data-stu-id="aaaae-123">Contains subscription information that delivery extensions use to deliver reports.</span></span>|  
|<span data-ttu-id="aaaae-124">Класс <xref:Microsoft.ReportingServices.Interfaces.Report></span><span class="sxs-lookup"><span data-stu-id="aaaae-124"><xref:Microsoft.ReportingServices.Interfaces.Report> Class</span></span>|<span data-ttu-id="aaaae-125">Представляет сведения об отчете и методы, которые позволяют модулям доставки доставлять пользователям отчеты.</span><span class="sxs-lookup"><span data-stu-id="aaaae-125">Represents report-specific information and methods that enable delivery extensions to deliver reports to users.</span></span>|  
|<span data-ttu-id="aaaae-126">Класс <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile></span><span class="sxs-lookup"><span data-stu-id="aaaae-126"><xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> Class</span></span>|<span data-ttu-id="aaaae-127">Представляет выходной файл модуля подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="aaaae-127">Represents the output from a rendering extension.</span></span> <span data-ttu-id="aaaae-128">Объект <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> содержит имя связанного файла и сведения о типе, необходимые модулю доставки для обработки потока, возвращаемого модулем подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="aaaae-128">A <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object contains the associated file name and type information that is required by the delivery extension in order to process the stream returned by the rendering extension.</span></span>|  
|<span data-ttu-id="aaaae-129"><xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> Интерфейс</span><span class="sxs-lookup"><span data-stu-id="aaaae-129"><xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> Interface</span></span>|<span data-ttu-id="aaaae-130">Пользовательский элемент управления, служащий средством получения данных о подписке, относящихся к модулю доставки, от пользователя в диспетчере отчетов (например, адрес электронной почты или путь в общую папку).</span><span class="sxs-lookup"><span data-stu-id="aaaae-130">A user control that represents the means to retrieve delivery extension-specific subscription information from the user in Report Manager (for example, an e-mail address or the path to a file share).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aaaae-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="aaaae-131">See Also</span></span>  
 <span data-ttu-id="aaaae-132">[Модули служб Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="aaaae-132">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="aaaae-133">[Реализация модуля доставки](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="aaaae-133">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="aaaae-134">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="aaaae-134">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
