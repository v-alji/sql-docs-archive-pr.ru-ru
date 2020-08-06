---
title: Передача параметров сведений об устройстве для модулей подготовки отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- device information settings [Reporting Services]
- Render method
- Report Server Web service, device information settings
- Web service [Reporting Services], device information settings
- XML Web service [Reporting Services], device information settings
- passing device information [Reporting Services]
- rendering extensions [Reporting Services], device information settings
- rendering [Reporting Services], settings
- device information settings [Reporting Services], about device information settings
- extensions [Reporting Services], device information settings
ms.assetid: fe718939-7efe-4c7f-87cb-5f5b09caeff4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ea50de3955ab152cbd92d5fd50ef8b2281a67eb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730130"
---
# <a name="passing-device-information-settings-to-rendering-extensions"></a><span data-ttu-id="46cc2-102">Передача настроек сведений об устройстве модулям подготовки отчетов к просмотру</span><span class="sxs-lookup"><span data-stu-id="46cc2-102">Passing Device Information Settings to Rendering Extensions</span></span>
  <span data-ttu-id="46cc2-103">В службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]настройки сведений об устройстве используются для передачи параметров подготовки к просмотру модуля подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="46cc2-103">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], device information settings are used to pass rendering parameters to a rendering extension.</span></span> <span data-ttu-id="46cc2-104">Настройки веб-службы сервера отчетов передаются как XML-элемент **DeviceInfo** и обрабатываются сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="46cc2-104">Settings in the Report Server Web service are passed as a **DeviceInfo** XML element and processed by the report server.</span></span> <span data-ttu-id="46cc2-105">Поскольку у настроек сведений об устройстве есть значения по умолчанию, в процессе подготовки к просмотру эти аргументы являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="46cc2-105">Because device information settings have default values, they are considered optional arguments in the rendering process.</span></span> <span data-ttu-id="46cc2-106">Однако настройки сведений об устройстве можно использовать для настройки процесса подготовки к просмотру и переопределения значений по умолчанию, передаваемых сервером.</span><span class="sxs-lookup"><span data-stu-id="46cc2-106">However, you can use device information settings to customize rendering and to override the default values that are supplied by the server.</span></span>  
  
 <span data-ttu-id="46cc2-107">Настройки сведений об устройстве можно задавать различными способами.</span><span class="sxs-lookup"><span data-stu-id="46cc2-107">You can specify device information settings in a variety of ways.</span></span> <span data-ttu-id="46cc2-108">Для задания программным путем можно использовать метод Render.</span><span class="sxs-lookup"><span data-stu-id="46cc2-108">Programmatically, you can use the Render method.</span></span> <span data-ttu-id="46cc2-109">Если доступ к отчету осуществляется по URL-адресу, сведения об устройстве можно задать как параметры URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="46cc2-109">If you are accessing a report through its URL, you can specify device information as URL parameters.</span></span> <span data-ttu-id="46cc2-110">Можно также редактировать настройки сведений об устройстве в файлах конфигурации служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] , чтобы задать глобальные значения параметров подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="46cc2-110">You can also edit the device information settings in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration files to specify rendering parameters globally.</span></span> <span data-ttu-id="46cc2-111">Дополнительные сведения об указании глобальных параметров подготовки отчетов см. в разделе [Настройка параметров модулей подготовки отчетов в RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="46cc2-111">For more information about specifying rendering parameters globally, see [Customize Rendering Extension Parameters in RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md).</span></span>  
  
## <a name="passing-device-information-using-the-render-method"></a><span data-ttu-id="46cc2-112">Передача сведений об устройстве с помощью метода Render</span><span class="sxs-lookup"><span data-stu-id="46cc2-112">Passing Device Information Using the Render Method</span></span>  
 <span data-ttu-id="46cc2-113">Для передачи сведений об устройстве в модуль подготовки отчетов используется метод <xref:ReportExecution2005.ReportExecutionService.Render%2A>.</span><span class="sxs-lookup"><span data-stu-id="46cc2-113">To pass device information settings to a rendering extension, use the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method.</span></span> <span data-ttu-id="46cc2-114">Например, при подготовке к просмотру в формате HTML методу <xref:ReportExecution2005.ReportExecutionService.Render%2A> можно передать следующую строку в формате XML для создания фрагмента HTML:</span><span class="sxs-lookup"><span data-stu-id="46cc2-114">For example, the following XML string can be passed to the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method to create an HTML fragment when rendering to HTML.</span></span>  
  
```  
<DeviceInfo>  
   <HTMLFragment>True</HTMLFragment>  
</DeviceInfo>  
```  
  
 <span data-ttu-id="46cc2-115">При подготовке отчета в виде фрагмента HTML содержимое отчета находится в элементе TABLE, а элементы HTML и BODY не используются.</span><span class="sxs-lookup"><span data-stu-id="46cc2-115">When a report is rendered as an HTML fragment, the content of the report is contained within a TABLE element without the use of an HTML or BODY element.</span></span> <span data-ttu-id="46cc2-116">Фрагмент HTML можно использовать для внедрения отчета в существующий HTML-документ.</span><span class="sxs-lookup"><span data-stu-id="46cc2-116">You can use the HTML fragment to incorporate the report into an existing HTML document.</span></span> <span data-ttu-id="46cc2-117">Дополнительные сведения о параметрах сведений об устройстве для вывода в формате HTML см. в разделе [Настройки сведений об устройстве HTML](../../html-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="46cc2-117">For more information about device information settings for HTML output, see [HTML Device Information Settings](../../html-device-information-settings.md).</span></span>  
  
## <a name="passing-device-information-using-url-access"></a><span data-ttu-id="46cc2-118">Передача сведений об устройстве с помощью доступа через URL-адрес</span><span class="sxs-lookup"><span data-stu-id="46cc2-118">Passing Device Information Using URL Access</span></span>  
 <span data-ttu-id="46cc2-119">Настройки сведений об устройстве можно также передать с помощью доступа по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="46cc2-119">You can also pass device information settings through URL access.</span></span> <span data-ttu-id="46cc2-120">Настройки сведений об устройстве передаются как параметры URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="46cc2-120">Device information settings are passed as URL parameters.</span></span> <span data-ttu-id="46cc2-121">Чтобы создать готовый для просмотра отчет без панели инструментов средства просмотра HTML-страниц, можно передать серверу отчетов следующую строку доступа к URL-адресу:</span><span class="sxs-lookup"><span data-stu-id="46cc2-121">The following URL access string can be passed to the report server to generate a rendered report without the HTML viewer toolbar.</span></span>  
  
```  
http://<Server Name>/reportserver?/SampleReports/Sales Order Detail&rs:Command=Render&rs:Format=HTML4.0&rc:Toolbar=False  
```  
  
 <span data-ttu-id="46cc2-122">Дополнительные сведения см. в разделе [Указание настроек сведений об устройстве в URL-адресе](../../specify-device-information-settings-in-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="46cc2-122">For more information, see [Specify Device Information Settings in a URL](../../specify-device-information-settings-in-a-url.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46cc2-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="46cc2-123">See Also</span></span>  
 <span data-ttu-id="46cc2-124">[Настройки сведений об устройстве для модулей подготовки отчетов &#40;Reporting Services&#41;](../../device-information-settings-for-rendering-extensions-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="46cc2-124">[Device Information Settings for Rendering Extensions &#40;Reporting Services&#41;](../../device-information-settings-for-rendering-extensions-reporting-services.md) </span></span>  
 <span data-ttu-id="46cc2-125">[Настройка параметров модуля подготовки отчетов в RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="46cc2-125">[Customize Rendering Extension Parameters in RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="46cc2-126">Создание приложений с помощью веб-службы и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="46cc2-126">Building Applications Using the Web Service and the .NET Framework</span></span>](building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
