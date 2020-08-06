---
title: Настройка параметров модулей подготовки отчетов в RSReportServer.Config | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- configuration options [Reporting Services]
- DeviceInfo settings
- rendering extensions [Reporting Services], overriding behaviors
- parameters [Reporting Services], report rendering
- overriding report rendering behavior
- extensions [Reporting Services], rendering
ms.assetid: 3bf7ab2b-70bb-41c8-acda-227994d15aed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35a01e12fa4016d03717b008e4241c3be5e55236
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750535"
---
# <a name="customize-rendering-extension-parameters-in-rsreportserverconfig"></a><span data-ttu-id="125e2-102">Настройка параметров модулей подготовки отчетов в RSReportServer.Config</span><span class="sxs-lookup"><span data-stu-id="125e2-102">Customize Rendering Extension Parameters in RSReportServer.Config</span></span>
  <span data-ttu-id="125e2-103">В файле конфигурации RSReportServer можно указать параметры модулей подготовки отчетов, чтобы изменить заданный по умолчанию способ подготовки к просмотру отчетов, запускаемых на сервере отчетов служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="125e2-103">You can specify rendering extension parameters in the RSReportServer configuration file to override default report rendering behavior for reports that run on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server.</span></span> <span data-ttu-id="125e2-104">Изменять параметры модуля подготовки отчетов можно для достижения следующих целей.</span><span class="sxs-lookup"><span data-stu-id="125e2-104">You can modify rendering extension parameters to achieve the following objectives:</span></span>  
  
-   <span data-ttu-id="125e2-105">Изменение имени модуля подготовки отчетов в списке «Экспорт» панели инструментов отчета (например, чтобы заменить «Веб-архив» на «MHTML») или отображение этого имени на другом языке.</span><span class="sxs-lookup"><span data-stu-id="125e2-105">Change how the rendering extension name appears in the Export list of the report toolbar (for example, to change "Web archive" to "MHTML"), or localize the name to a different language.</span></span>  
  
-   <span data-ttu-id="125e2-106">Создание нескольких экземпляров одного модуля подготовки отчетов для обеспечения различных вариантов представления отчета (например, варианты модуля подготовки изображений портретной и альбомной ориентации).</span><span class="sxs-lookup"><span data-stu-id="125e2-106">Create multiple instances of the same rendering extension to support different report presentation options (for example, a portrait and landscape mode version of the Image rendering extension).</span></span>  
  
-   <span data-ttu-id="125e2-107">Изменение параметров по умолчанию модуля подготовки отчетов на другие значения (например, в модуле подготовки изображений в качестве формата вывода по умолчанию используется TIFF; параметры можно изменить таким образом, чтобы вместо этого использовался формат EMF).</span><span class="sxs-lookup"><span data-stu-id="125e2-107">Change the default rendering extension parameters to use different values (for example, the Image rendering extension uses TIFF as the default output format; you can modify the extension parameters to use EMF instead).</span></span>  
  
 <span data-ttu-id="125e2-108">Изменение параметров модуля подготовки отчетов влияет только на операции подготовки к просмотру на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="125e2-108">Changing the rendering extension parameters only affects rendering operations on the report server.</span></span> <span data-ttu-id="125e2-109">Невозможно изменить настройки модуля подготовки отчетов, используемые для предварительного просмотра отчета в конструкторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="125e2-109">You cannot override rendering extension settings in report preview in Report Designer.</span></span>  
  
 <span data-ttu-id="125e2-110">Указание параметров модуля подготовки отчетов в файлах конфигурации влияет на все модули подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="125e2-110">Specifying rendering extension parameters in the configuration files affects rendering extensions globally.</span></span> <span data-ttu-id="125e2-111">Настройки в файлах конфигурации используются вместо значений по умолчанию всегда, когда применяется определенный модуль подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="125e2-111">The settings in the configuration files are used in place of default values whenever a particular rendering extension is used.</span></span> <span data-ttu-id="125e2-112">Если требуется задать параметры модуля подготовки отчетов для определенного отчета или операции подготовки к просмотру, следует указать сведения об устройстве программно с помощью метода <xref:ReportExecution2005.ReportExecutionService.Render%2A> или указав настройки сведений об устройстве в URL-адресе отчета.</span><span class="sxs-lookup"><span data-stu-id="125e2-112">If you want to set rendering extension parameters for a specific report or render operation, you must specify device information programmatically using the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method or by specifying device information settings on a report URL.</span></span> <span data-ttu-id="125e2-113">Дополнительные сведения об указании настроек сведений об устройстве для операции подготовки к просмотру, а также полный список этих настроек см. в разделе [Передача настроек сведений об устройстве модулям подготовки отчетов к просмотру](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="125e2-113">For more information about specifying device information settings for a render operation, and to view the complete list of device information settings, see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
## <a name="finding-and-modifying-rsreportserverconfig"></a><span data-ttu-id="125e2-114">Поиск и изменение файла RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="125e2-114">Finding and Modifying RSReportServer.config</span></span>  
 <span data-ttu-id="125e2-115">Параметры конфигурации форматов вывода для отчета указывается в виде параметров модуля подготовки отчетов в файле конфигурации RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="125e2-115">Configuration settings for report output formats are specified as rendering extension parameters in the RSReportServer.config file.</span></span> <span data-ttu-id="125e2-116">Чтобы указать в файлах конфигурации параметры модуля подготовки отчетов, необходимо знать, как определить XML-структуры, задающие параметры подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="125e2-116">To specify rendering extension parameters in the configuration files, you must know how to define the XML structures that set rendering parameters.</span></span> <span data-ttu-id="125e2-117">Существует две XML-структуры, которые можно изменять.</span><span class="sxs-lookup"><span data-stu-id="125e2-117">There are two XML structures that you can modify:</span></span>  
  
-   <span data-ttu-id="125e2-118">Элемент `OverrideNames` задает отображаемые имя и язык модуля подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="125e2-118">The `OverrideNames` element defines the display name and language of the rendering extension.</span></span>  
  
-   <span data-ttu-id="125e2-119">XML-структура `DeviceInfo` определяет настройки сведений об устройстве, используемых модулем подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="125e2-119">The `DeviceInfo` XML structure defines the device information settings that are used by a rendering extension.</span></span> <span data-ttu-id="125e2-120">Большинство параметров модуля подготовки отчетов определены как настройки сведений об устройстве.</span><span class="sxs-lookup"><span data-stu-id="125e2-120">Most rendering extension parameters are specified as device information settings.</span></span>  
  
 <span data-ttu-id="125e2-121">Для изменения этого файла можно использовать текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="125e2-121">You can use a text editor to modify the file.</span></span> <span data-ttu-id="125e2-122">Файл RSReportServer.config находится в папке \Reporting Services\Report Server\Bin.</span><span class="sxs-lookup"><span data-stu-id="125e2-122">The RSReportServer.config file can be found in the \Reporting Services\Report Server\Bin folder.</span></span> <span data-ttu-id="125e2-123">Дополнительные сведения об изменении файлов конфигурации см. в разделе [Изменение файла конфигурации служб Reporting Services (RSreportserver.config)](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="125e2-123">For more information about modifying configuration files, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span>  
  
## <a name="changing-the-display-name"></a><span data-ttu-id="125e2-124">Изменение отображаемого имени</span><span class="sxs-lookup"><span data-stu-id="125e2-124">Changing the Display Name</span></span>  
 <span data-ttu-id="125e2-125">Отображаемое имя модуля подготовки отчетов указывается в списке «Экспорт» панели инструментов отчета.</span><span class="sxs-lookup"><span data-stu-id="125e2-125">The display name for a rendering extension appears in the Export list of the report toolbar.</span></span> <span data-ttu-id="125e2-126">Среди примеров отображаемых имен по умолчанию есть веб-архив, TIFF-файл и файл Acrobat (PDF-файл).</span><span class="sxs-lookup"><span data-stu-id="125e2-126">Examples of default display names include Web archive, TIFF file, and Acrobat (PDF) file.</span></span> <span data-ttu-id="125e2-127">Отображаемое имя по умолчанию можно заменить произвольным значением, указав в файлах конфигурации элемент `OverrideNames`.</span><span class="sxs-lookup"><span data-stu-id="125e2-127">You can replace the default display name with a custom value by specifying the `OverrideNames` element in the configuration files.</span></span> <span data-ttu-id="125e2-128">Кроме того, если пользователь определяет два экземпляра одного модуля подготовки отчетов, элемент `OverrideNames` можно использовать, чтобы различать эти экземпляры в списке «Экспорт».</span><span class="sxs-lookup"><span data-stu-id="125e2-128">In addition, if you are defining two instances of a single rendering extension, you can use the `OverrideNames` element to distinguish each instance in the Export list.</span></span>  
  
 <span data-ttu-id="125e2-129">Поскольку отображаемые имена локализованы, при замене отображаемого имени по умолчанию пользовательским значением следует установить атрибут `Language`.</span><span class="sxs-lookup"><span data-stu-id="125e2-129">Because display names are localized, you must set the `Language` attribute if you are replacing the default display name with a custom value.</span></span> <span data-ttu-id="125e2-130">Иначе любое указанное имя не будет обрабатываться.</span><span class="sxs-lookup"><span data-stu-id="125e2-130">Otherwise, any name that you specify will be ignored.</span></span> <span data-ttu-id="125e2-131">Указанное значение языка должно быть допустимым для компьютера, на котором выполняется сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="125e2-131">The language value that you set must be valid for the report server computer.</span></span> <span data-ttu-id="125e2-132">Например, если сервер отчетов выполняется под управлением французской операционной системы, в качестве значения атрибута следует указать «fr-FR».</span><span class="sxs-lookup"><span data-stu-id="125e2-132">For example, if the report server is running on a French operating system, you should specify "fr-FR" as the attribute value.</span></span>  
  
 <span data-ttu-id="125e2-133">В следующем примере показано, как задать пользовательское имя на сервере отчетов английской версии.</span><span class="sxs-lookup"><span data-stu-id="125e2-133">The following example illustrates how to provide a custom name on an English report server:</span></span>  
  
```  
<Extension Name="XML" Type="Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport,Microsoft.ReportingServices.DataRendering">  
   <OverrideNames>  
     <Name Language="en-US">My Custom Display Name for XML Rendering</Name>  
   </OverrideNames>  
</Extension>  
```  
  
## <a name="changing-device-information-settings"></a><span data-ttu-id="125e2-134">Изменение настроек сведений об устройстве</span><span class="sxs-lookup"><span data-stu-id="125e2-134">Changing Device Information Settings</span></span>  
 <span data-ttu-id="125e2-135">Чтобы изменить настройки сведений об устройстве, используемые по умолчанию уже развернутым на сервере отчетов модулем подготовки отчетов, следует ввести в файлы конфигурации XML-структуру `DeviceInfo`.</span><span class="sxs-lookup"><span data-stu-id="125e2-135">To modify default device information settings that are used by a rendering extension that is already deployed on your report server, you must type the `DeviceInfo` XML structure into the configuration files.</span></span> <span data-ttu-id="125e2-136">Для каждого модуля подготовки к просмотру существуют уникальные для него настройки сведений об устройстве.</span><span class="sxs-lookup"><span data-stu-id="125e2-136">Every rendering extension supports device information settings that are unique to that extension.</span></span> <span data-ttu-id="125e2-137">Полный список настроек сведений об устройстве см. в разделе [Передача настроек сведений об устройстве модулям подготовки отчетов к просмотру](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="125e2-137">To view the complete list of device information settings, see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
 <span data-ttu-id="125e2-138">В следующем примере показано, как выглядит структура и синтаксис XML-кода, изменяющего значения по умолчанию для модуля подготовки изображений:</span><span class="sxs-lookup"><span data-stu-id="125e2-138">The following example provides an illustration of the XML structure and syntax that modifies the default settings of the Image rendering extension:</span></span>  
  
```  
<Render>  
    <Extension Name="IMAGE (EMF)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">Image (EMF)</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <ColorDepth>32</ColorDepth>  
                <DpiX>300</DpiX>  
                <DpiY>300</DpiY>  
                <OutputFormat>EMF</OutputFormat>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
</Render>  
```  
  
## <a name="configuring-multiple-entries-for-a-rendering-extension"></a><span data-ttu-id="125e2-139">Настройка нескольких записей для модуля подготовки к просмотру</span><span class="sxs-lookup"><span data-stu-id="125e2-139">Configuring Multiple Entries for a Rendering Extension</span></span>  
 <span data-ttu-id="125e2-140">Чтобы поддерживать возможность работы с различными представлениями отчета, можно создать несколько экземпляров одного модуля подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="125e2-140">You can create multiple instances of the same rendering extension to support different report presentation options.</span></span> <span data-ttu-id="125e2-141">Сочетание значений параметров может быть разным для каждого из определенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="125e2-141">Each instance that you define can have a different combination of parameter values.</span></span> <span data-ttu-id="125e2-142">Определяя новые экземпляры существующего модуля подготовки отчетов, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="125e2-142">When defining new instances of an existing rendering extension, be sure to do the following:</span></span>  
  
-   <span data-ttu-id="125e2-143">Указать уникальное имя для модуля.</span><span class="sxs-lookup"><span data-stu-id="125e2-143">Specify a unique name for the extension.</span></span>  
  
     <span data-ttu-id="125e2-144">Каждый экземпляр должен иметь уникальное значение атрибута `Name`.</span><span class="sxs-lookup"><span data-stu-id="125e2-144">Each instance must have a unique value for the `Name` attribute.</span></span> <span data-ttu-id="125e2-145">В следующем примере для того, чтобы экземпляры можно было различить, им присвоены имена «IMAGE (EMF Landscape)» и «IMAGE (EMF Portrait)».</span><span class="sxs-lookup"><span data-stu-id="125e2-145">The following example uses the names "IMAGE (EMF Landscape)" and "IMAGE (EMF Portrait)" to distinguish between the two instances.</span></span>  
  
     <span data-ttu-id="125e2-146">Соблюдайте осторожность при изменении имени уже развернутого модуля подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="125e2-146">Use caution when changing the name of a rendering extension that is already deployed.</span></span> <span data-ttu-id="125e2-147">Разработчики, указывающие модули подготовки отчетов программно, используют имена модулей, чтобы обозначить, какой экземпляр нужен для определенной операции подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="125e2-147">Developers who specify rendering extensions programmatically use the extension name to identify which instance to use for a particular render operation.</span></span> <span data-ttu-id="125e2-148">Если на сервере отчетов работают пользовательские приложения служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , убедитесь, что разработчику известно об изменениях, вносимых в существующие имена модулей, или о добавлении нового имени.</span><span class="sxs-lookup"><span data-stu-id="125e2-148">If you are running custom [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] applications on your report server, make sure that the developer knows if you modify an existing extension name or add a new one.</span></span>  
  
-   <span data-ttu-id="125e2-149">Укажите такое уникальное отображаемое имя, чтобы пользователи могли понять, каковы различия между любыми форматами вывода.</span><span class="sxs-lookup"><span data-stu-id="125e2-149">Specify a unique display name so that users can understand the differences for each output format.</span></span>  
  
     <span data-ttu-id="125e2-150">При настройке нескольких версий одного модуля задайте каждой из них уникальное имя, указав значение для `OverrideNames`.</span><span class="sxs-lookup"><span data-stu-id="125e2-150">If you are configuring multiple versions of the same extension, you can give each version a unique name by providing a value for `OverrideNames`.</span></span> <span data-ttu-id="125e2-151">В противном случае в списке возможных режимов экспорта на панели инструментов отчета все версии этого модуля будут отображаться под одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="125e2-151">Otherwise, all versions of the extension will appear to have the same name in the Export options list on the report toolbar.</span></span>  
  
 <span data-ttu-id="125e2-152">В следующем образце показано, как добиться, чтобы используемый по умолчанию модуль подготовки к просмотру изображений (осуществляющий вывод в формате TIFF) выводил отчет в формате EMF в портретной ориентации наряду со вторым экземпляром, выводящим отчеты в формате EMF в альбомной ориентации.</span><span class="sxs-lookup"><span data-stu-id="125e2-152">The following example illustrates how to use the default Image rendering extension (which produces TIFF output) to output EMF in Portrait mode alongside a second instance that outputs reports in EMF in Landscape mode.</span></span> <span data-ttu-id="125e2-153">Обратите внимание, что каждое имя модуля уникально.</span><span class="sxs-lookup"><span data-stu-id="125e2-153">Notice that each extension name is unique.</span></span> <span data-ttu-id="125e2-154">Помните, что при тестировании этого образца следует выбирать отчеты, не содержащие таких интерактивных возможностей, как скрытие/отображение параметров, матрицы или ссылки на детализированные отчеты (в модуле подготовки к просмотру изображений интерактивные возможности не работают):</span><span class="sxs-lookup"><span data-stu-id="125e2-154">When testing this example, remember to choose reports that do not contain interactive features such as show/hide options, matrices, or drillthrough links (interactive features do not work in the Image rendering extension):</span></span>  
  
```  
<Render>  
    <Extension Name="IMAGE (EMF Landscape)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">EMF in Landscape Mode</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <OutputFormat>EMF</OutputFormat>  
                <PageHeight>8.5in</PageHeight>  
                <PageWidth>11in</PageWidth>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
    <Extension Name="IMAGE (EMF Portrait)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">EMF in Portait Mode</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <OutputFormat>EMF</OutputFormat>  
                <PageHeight>11in</PageHeight>  
                <PageWidth>8.5in</PageWidth>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
</Render>  
```  
  
## <a name="see-also"></a><span data-ttu-id="125e2-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="125e2-155">See Also</span></span>  
 <span data-ttu-id="125e2-156">[Файл конфигурации RSReportServer](report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="125e2-156">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="125e2-157">[Файл конфигурации RSReportDesigner](report-server/rsreportdesigner-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="125e2-157">[RSReportDesigner Configuration File](report-server/rsreportdesigner-configuration-file.md) </span></span>  
 <span data-ttu-id="125e2-158">[Настройки сведений об устройстве CSV](csv-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="125e2-158">[CSV Device Information Settings](csv-device-information-settings.md) </span></span>  
 <span data-ttu-id="125e2-159">[Настройки сведений об устройстве Excel](excel-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="125e2-159">[Excel Device Information Settings](excel-device-information-settings.md) </span></span>  
 <span data-ttu-id="125e2-160">[Настройки сведений об устройстве HTML](html-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="125e2-160">[HTML Device Information Settings](html-device-information-settings.md) </span></span>  
 <span data-ttu-id="125e2-161">[Настройки сведений об устройстве вывода изображений](image-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="125e2-161">[Image Device Information Settings](image-device-information-settings.md) </span></span>  
 <span data-ttu-id="125e2-162">[Настройки сведений об устройстве MHTML](mhtml-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="125e2-162">[MHTML Device Information Settings](mhtml-device-information-settings.md) </span></span>  
 <span data-ttu-id="125e2-163">[Настройки сведений об устройстве PDF](pdf-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="125e2-163">[PDF Device Information Settings](pdf-device-information-settings.md) </span></span>  
 [<span data-ttu-id="125e2-164">Настройки сведений об устройстве XML</span><span class="sxs-lookup"><span data-stu-id="125e2-164">XML Device Information Settings</span></span>](xml-device-information-settings.md)  
  
  
