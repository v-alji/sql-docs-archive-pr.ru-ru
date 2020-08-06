---
title: Реализация интерфейса IRenderingExtension | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- IRenderingExtension interface
- rendering extensions [Reporting Services], IRenderingExtension interface
ms.assetid: 74b2f2b7-6796-42da-ab7d-b05891ad4001
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f57c4aa41ccfed165b69581cbf3917e4dfbb4960
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664749"
---
# <a name="implementing-the-irenderingextension-interface"></a><span data-ttu-id="92b72-102">Реализация интерфейса IRenderingExtension</span><span class="sxs-lookup"><span data-stu-id="92b72-102">Implementing the IRenderingExtension Interface</span></span>
  <span data-ttu-id="92b72-103">Модуль подготовки отчетов извлекает результаты из определения отчета, объединенного с реальными данными, и преобразует результирующие данные в формат, готовый к применению.</span><span class="sxs-lookup"><span data-stu-id="92b72-103">The rendering extension takes the results from a report definition that is combined with the actual data and renders the resulting data to a format that is useable.</span></span> <span data-ttu-id="92b72-104">Преобразование объединенных данных и форматирование осуществляется при помощи класса среды CLR, который реализует интерфейс <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension>.</span><span class="sxs-lookup"><span data-stu-id="92b72-104">The transformation of the combined data and formatting is done by using a common language runtime (CLR) class that implements <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension>.</span></span> <span data-ttu-id="92b72-105">Модель объекта преобразуется в формат вывода, который предназначен для средства просмотра, принтера или другого приложения вывода.</span><span class="sxs-lookup"><span data-stu-id="92b72-105">This transforms the object model into an output format that is consumable by a viewer, printer, or other output target.</span></span>  
  
 <span data-ttu-id="92b72-106">Интерфейс <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> имеет три метода, которые должны быть реализованы.</span><span class="sxs-lookup"><span data-stu-id="92b72-106">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> has three methods that must be coded:</span></span>  
  
-   <span data-ttu-id="92b72-107"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> подготавливает отчет к просмотру.</span><span class="sxs-lookup"><span data-stu-id="92b72-107"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> - renders the report.</span></span>  
  
-   <span data-ttu-id="92b72-108"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> подготавливает к просмотру определенный поток из отчета.</span><span class="sxs-lookup"><span data-stu-id="92b72-108"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> - renders a specific stream from the report.</span></span>  
  
-   <span data-ttu-id="92b72-109"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> возвращает дополнительные сведения, такие как значки, которые требуются отчету.</span><span class="sxs-lookup"><span data-stu-id="92b72-109"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> - gets additional information, such as icons, that are required for the report.</span></span>  
  
 <span data-ttu-id="92b72-110">В следующих разделах данные методы обсуждаются более подробно.</span><span class="sxs-lookup"><span data-stu-id="92b72-110">The following sections discuss these methods in more detail.</span></span>  
  
## <a name="render-method"></a><span data-ttu-id="92b72-111">Метод Render</span><span class="sxs-lookup"><span data-stu-id="92b72-111">Render Method</span></span>  
 <span data-ttu-id="92b72-112">Метод <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> содержит аргументы, представляющие следующие объекты.</span><span class="sxs-lookup"><span data-stu-id="92b72-112">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> method contains arguments that represent the following objects:</span></span>  
  
-   <span data-ttu-id="92b72-113">*report* — отчет, который необходимо подготовить.</span><span class="sxs-lookup"><span data-stu-id="92b72-113">The *report* that you want to render.</span></span> <span data-ttu-id="92b72-114">Данный объект содержит свойства, данные и сведения о макете отчета.</span><span class="sxs-lookup"><span data-stu-id="92b72-114">This object contains properties, data, and layout information for the report.</span></span> <span data-ttu-id="92b72-115">Report — это корневой узел дерева модели объектов отчета.</span><span class="sxs-lookup"><span data-stu-id="92b72-115">The report is the root of the report object model tree.</span></span>  
  
-   <span data-ttu-id="92b72-116">Параметр *ServerParameters* одержит объект словаря строк с параметрами сервера отчетов (если такие существуют).</span><span class="sxs-lookup"><span data-stu-id="92b72-116">The *ServerParameters* that contain the string dictionary object, with the parameters for the report server, if any.</span></span>  
  
-   <span data-ttu-id="92b72-117">Параметр *deviceInfo* содержит параметры устройства.</span><span class="sxs-lookup"><span data-stu-id="92b72-117">The *deviceInfo* parameter that contain the device settings.</span></span> <span data-ttu-id="92b72-118">Дополнительные сведения см. разделе [Передача параметров сведений об устройстве модулям подготовки отчетов](../../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="92b72-118">For more information, see [Passing Device Information Settings to Rendering Extensions](../../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
-   <span data-ttu-id="92b72-119">Параметр *clientCapabilities* содержит объект словаря <xref:System.Collections.Specialized.NameValueCollection> со сведениями о клиенте, для которого выполняется отрисовка.</span><span class="sxs-lookup"><span data-stu-id="92b72-119">The *clientCapabilities* parameter that contains a <xref:System.Collections.Specialized.NameValueCollection> dictionary object that has information about the client to which you are rendering.</span></span>  
  
-   <span data-ttu-id="92b72-120">Параметр *RenderProperties* содержит сведения о результате отрисовки.</span><span class="sxs-lookup"><span data-stu-id="92b72-120">The *RenderProperties* that contains information about the rendering result.</span></span>  
  
-   <span data-ttu-id="92b72-121">Параметр *createAndRegisterStream* — это функция-делегат, которую можно вызвать для получения потока, в который будет осуществляться отрисовка.</span><span class="sxs-lookup"><span data-stu-id="92b72-121">The *createAndRegisterStream* is a delegate function to be called to get a stream to render into.</span></span>  
  
### <a name="deviceinfo-parameter"></a><span data-ttu-id="92b72-122">Параметр deviceInfo</span><span class="sxs-lookup"><span data-stu-id="92b72-122">deviceInfo Parameter</span></span>  
 <span data-ttu-id="92b72-123">Параметр *deviceInfo* содержит параметры отрисовки, а не параметры отчета.</span><span class="sxs-lookup"><span data-stu-id="92b72-123">The *deviceInfo* parameter contains rendering parameters, not report parameters.</span></span> <span data-ttu-id="92b72-124">Данные параметры передаются модулю подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="92b72-124">These rendering parameters are passed to the rendering extension.</span></span> <span data-ttu-id="92b72-125">Значения *deviceInfo* преобразуются сервером отчетов в объект <xref:System.Collections.Specialized.NameValueCollection>.</span><span class="sxs-lookup"><span data-stu-id="92b72-125">The *deviceInfo* values are converted into a <xref:System.Collections.Specialized.NameValueCollection> object by the report server.</span></span> <span data-ttu-id="92b72-126">Элементы в параметре *deviceInfo* рассматриваются как значения без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="92b72-126">Items in the *deviceInfo* parameter are treated as case-insensitive values.</span></span> <span data-ttu-id="92b72-127">Если запрос на отрисовку поступил в результате доступа по URL-адресу, то параметры URL-адреса в формате `rc:key=value` преобразовываются в пары "ключ-значение" в объекте словаря *deviceInfo*.</span><span class="sxs-lookup"><span data-stu-id="92b72-127">If the render request came as a result of URL access, the URL parameters in the form `rc:key=value` are converted to key/value pairs in the *deviceInfo* dictionary object.</span></span> <span data-ttu-id="92b72-128">Код обнаружения браузера также предоставляет следующие элементы в словаре *clientCapabilities*: EcmaScriptVersion, JavaScript, MajorVersion, MinorVersion, Win32, Type и AcceptLanguage.</span><span class="sxs-lookup"><span data-stu-id="92b72-128">The browser detection code also provides the following items in the *clientCapabilities* dictionary: EcmaScriptVersion, JavaScript, MajorVersion, MinorVersion, Win32, Type, and AcceptLanguage.</span></span> <span data-ttu-id="92b72-129">Любая пара "имя-значение" в параметре *deviceInfo*, которую не удается распознать модулю подготовки отчетов, не учитывается.</span><span class="sxs-lookup"><span data-stu-id="92b72-129">Any name/value pair in the *deviceInfo* parameter that is not understood by the rendering extension is ignored.</span></span> <span data-ttu-id="92b72-130">В следующем образце кода показывается образец метода <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>, возвращающего значки:</span><span class="sxs-lookup"><span data-stu-id="92b72-130">The following code sample shows a sample <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method that retrieves icons:</span></span>  
  
```csharp  
public void GetRenderingResource (CreateStream createStreamCallback, NameValueCollection deviceInfo)  
{  
    string[] iconTagValues = deviceInfo.GetValues("Icon");  
    if ((iconTagValues != null) && (iconTagValues.Length > 0) )  
    {  
        // Create a stream to output to.  
        Stream outputStream = createStreamCallback(m_iconResourceName, "gif", null, "image/gif", false);  
        // Get the GIF image for one of the buttons on the toolbar  
        Image requiredImage = (Image) m_resourcemanager.GetObject(m_iconResourceName  
        // Write the image to the output stream  
        requiredImage.Save(outputStream, requiredImage.RawFormat);  
    }  
    return;  
}  
```  
  
## <a name="renderstream-method"></a><span data-ttu-id="92b72-131">Метод RenderStream</span><span class="sxs-lookup"><span data-stu-id="92b72-131">RenderStream Method</span></span>  
 <span data-ttu-id="92b72-132">Метод <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> подготавливает к просмотру определенный поток из отчета.</span><span class="sxs-lookup"><span data-stu-id="92b72-132">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> method renders a particular stream from the report.</span></span> <span data-ttu-id="92b72-133">Все потоки создаются при начальном вызове метода <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A>, однако изначально потоки не возвращаются клиенту.</span><span class="sxs-lookup"><span data-stu-id="92b72-133">All streams are created during the initial <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> call, but the streams are not returned to the client initially.</span></span> <span data-ttu-id="92b72-134">Данный метод используется для вторичных потоков (например, при подготовке отчетов в формате HTML) или дополнительных страниц многостраничного модуля подготовки отчетов (например, модуль подготовки изображений или модуль подготовки EMF).</span><span class="sxs-lookup"><span data-stu-id="92b72-134">This method is used for secondary streams, such as images in HTML rendering, or additional pages of a multi-page rendering extension, such as Image/EMF.</span></span>  
  
## <a name="getrenderingresource-method"></a><span data-ttu-id="92b72-135">Метод GetRenderingResource</span><span class="sxs-lookup"><span data-stu-id="92b72-135">GetRenderingResource Method</span></span>  
 <span data-ttu-id="92b72-136">Метод <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> получает данные, не выполняя полную подготовку отчета.</span><span class="sxs-lookup"><span data-stu-id="92b72-136">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method retrieves the information without executing an entire rendering of the report.</span></span> <span data-ttu-id="92b72-137">В некоторых случаях отчету необходимы данные, которые не требуют подготовки отчета.</span><span class="sxs-lookup"><span data-stu-id="92b72-137">There are times when the report requires information that does not require the report itself to be rendered.</span></span> <span data-ttu-id="92b72-138">Например, если требуется значок, связанный с модулем подготовки отчетов, используйте параметр *DeviceInfo* , содержащий один тег **\<Icon>** .</span><span class="sxs-lookup"><span data-stu-id="92b72-138">For example, if you need the icon associated with the rendering extension, use the *deviceInfo* parameter containing the single tag **\<Icon>**.</span></span> <span data-ttu-id="92b72-139">В подобных случаях можно использовать метод <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>.</span><span class="sxs-lookup"><span data-stu-id="92b72-139">In these cases, you can use the <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92b72-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="92b72-140">See Also</span></span>  
 <span data-ttu-id="92b72-141">[Реализация модуля подготовки отчетов](implementing-a-rendering-extension.md) </span><span class="sxs-lookup"><span data-stu-id="92b72-141">[Implementing a Rendering Extension](implementing-a-rendering-extension.md) </span></span>  
 [<span data-ttu-id="92b72-142">Общие сведения о модулях подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="92b72-142">Rendering Extensions Overview</span></span>](rendering-extensions-overview.md)  
  
  
