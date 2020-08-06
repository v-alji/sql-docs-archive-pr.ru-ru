---
title: Развертывание модуля доставки | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], deploying
- Extension element
- deploying [Reporting Services], extensions
ms.assetid: 4436ce48-397d-42c7-9b5d-2a267e2a1b2c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f4a4e33266c8d3a27ce2a4ab5f568bdee349720f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669309"
---
# <a name="deploying-a-delivery-extension"></a><span data-ttu-id="a6b48-102">Развертывание модуля доставки</span><span class="sxs-lookup"><span data-stu-id="a6b48-102">Deploying a Delivery Extension</span></span>
  <span data-ttu-id="a6b48-103">Сведения о конфигурации модулей доставки предоставляются в виде XML-файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a6b48-103">Delivery extensions supply their configuration information in the form of an XML configuration file.</span></span> <span data-ttu-id="a6b48-104">XML-файл соответствует схеме XML, определенной для модулей доставки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-104">The XML file conforms to the XML schema defined for delivery extensions.</span></span> <span data-ttu-id="a6b48-105">Модули доставки предоставляют инфраструктуру для настройки и изменения файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a6b48-105">Delivery extensions provide infrastructure for setting and modifying the configuration file.</span></span>  
  
 <span data-ttu-id="a6b48-106">В случае замены или обновления модуля доставки все подписки, с которыми он связан, остаются действительными.</span><span class="sxs-lookup"><span data-stu-id="a6b48-106">If a delivery extension is replaced or upgraded, all subscriptions that reference the delivery extension remain valid.</span></span>  
  
 <span data-ttu-id="a6b48-107">После записи и компиляции модуля доставки службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] в библиотеку [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] необходимо скопировать модуль в соответствующий каталог и добавить запись в соответствующий файл конфигурации [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], чтобы сервер отчетов мог найти этот модуль.</span><span class="sxs-lookup"><span data-stu-id="a6b48-107">After you have written and compiled your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension into a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] library, you must copy the extension to the appropriate directory and add an entry to the appropriate [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration file so the report server can locate it.</span></span>  
  
## <a name="configuration-file-extension-element"></a><span data-ttu-id="a6b48-108">Элемент Extension в файле конфигурации</span><span class="sxs-lookup"><span data-stu-id="a6b48-108">Configuration-File Extension Element</span></span>  
 <span data-ttu-id="a6b48-109">Модули доставки, развернутые на сервере отчетов, необходимо указывать в файле конфигурации как элементы `Extension`.</span><span class="sxs-lookup"><span data-stu-id="a6b48-109">Delivery extensions that you deploy to the report server need to be entered as `Extension` elements in the configuration file.</span></span> <span data-ttu-id="a6b48-110">Файлом конфигурации для сервера отчетов является RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="a6b48-110">The configuration file for the report server is RSReportServer.config.</span></span>  
  
 <span data-ttu-id="a6b48-111">В приведенной ниже таблице описаны атрибуты для элемента `Extension` модулей доставки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-111">The following table describes the attributes for the `Extension` element for delivery extensions.</span></span>  
  
|<span data-ttu-id="a6b48-112">attribute</span><span class="sxs-lookup"><span data-stu-id="a6b48-112">Attribute</span></span>|<span data-ttu-id="a6b48-113">Description</span><span class="sxs-lookup"><span data-stu-id="a6b48-113">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="a6b48-114">Уникальное имя модуля (например, «Электронная почта сервера отчетов» для модуля доставки по электронной почте или «Общие папки сервера отчетов» для модуля доставки в общие папки).</span><span class="sxs-lookup"><span data-stu-id="a6b48-114">A unique name for the extension (for example, "Report Server E-Mail" for the e-mail delivery extension or "Report Server FileShare" for the file share delivery extension).</span></span> <span data-ttu-id="a6b48-115">Длина атрибута `Name` не должна превышать 255 символов.</span><span class="sxs-lookup"><span data-stu-id="a6b48-115">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="a6b48-116">Имя должно быть уникальным среди всех элементов, вложенных в элемент `Extension` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a6b48-116">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="a6b48-117">Если присутствует повторяющееся имя, сервер отчетов возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="a6b48-117">If a duplicate name is present, the report server returns an error.</span></span>|  
|`Type`|<span data-ttu-id="a6b48-118">Список с разделителями-запятыми, содержащий полное пространство имен и имя сборки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-118">A comma-separated list that includes the fully qualified namespace along with the name of the assembly.</span></span>|  
|`Visible`|<span data-ttu-id="a6b48-119">Значение `false` показывает, что модуль доставки не должен быть видимым в пользовательских интерфейсах.</span><span class="sxs-lookup"><span data-stu-id="a6b48-119">A value of `false` indicates that the delivery extension should not be visible in user interfaces.</span></span> <span data-ttu-id="a6b48-120">Если атрибут не указан, по умолчанию используется значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a6b48-120">If the attribute is not included, the default value is `true`.</span></span>|  
  
 <span data-ttu-id="a6b48-121">Дополнительные сведения о файле RSReportServer.config см. в разделе [Файлы конфигурации служб Reporting Services](../../report-server/reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="a6b48-121">For more information about the RSReportServer.config file, see [Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md).</span></span>  
  
## <a name="deploying-the-extension-to-the-report-server"></a><span data-ttu-id="a6b48-122">Развертывание модуля на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="a6b48-122">Deploying the Extension to the Report Server</span></span>  
 <span data-ttu-id="a6b48-123">С помощью модулей доставки сервер отчетов обрабатывает и доставляет уведомления или отчеты.</span><span class="sxs-lookup"><span data-stu-id="a6b48-123">The report server uses delivery extensions for processing and delivering notifications or reports.</span></span> <span data-ttu-id="a6b48-124">Сборка модуля доставки развертывается на сервере отчетов как закрытая сборка.</span><span class="sxs-lookup"><span data-stu-id="a6b48-124">You should deploy your delivery extension assembly to the report server as a private assembly.</span></span> <span data-ttu-id="a6b48-125">Нужно также внести запись в файл конфигурации сервера отчетов RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="a6b48-125">You also need to make an entry in the report server configuration file, RSReportServer.config.</span></span>  
  
#### <a name="to-deploy-a-deliver-extension-assembly-to-a-report-server"></a><span data-ttu-id="a6b48-126">Развертывание сборки модуля доставки на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="a6b48-126">To deploy a deliver extension assembly to a report server</span></span>  
  
1.  <span data-ttu-id="a6b48-127">Скопируйте сборку из промежуточной папки в каталог bin сервера отчетов, на котором будет использоваться модуль доставки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-127">Copy your assembly from your staging location to the bin directory of the report server on which you want to use the delivery extension.</span></span> <span data-ttu-id="a6b48-128">По умолчанию каталог bin сервера отчетов находится в папке%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="a6b48-128">The default location of the report server bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer\bin.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a6b48-129">При попытке перезаписать существующую сборку модуля доставки необходимо сначала остановить службу сервера отчетов, а затем скопировать обновленную сборку.</span><span class="sxs-lookup"><span data-stu-id="a6b48-129">If you are attempting to overwrite an existing delivery extension assembly, you must first stop the Report Server service before copying the updated assembly.</span></span> <span data-ttu-id="a6b48-130">После окончания копирования сборки перезапустите службу.</span><span class="sxs-lookup"><span data-stu-id="a6b48-130">Restart your service after the assembly is through copying.</span></span>  
  
2.  <span data-ttu-id="a6b48-131">Скопировав файл сборки, откройте файл RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="a6b48-131">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="a6b48-132">Файл RSReportServer.config находится в папке%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> Каталог \Reporting Services\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="a6b48-132">The RSReportServer.config file is located in the %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer directory.</span></span> <span data-ttu-id="a6b48-133">Необходимо создать запись в файле конфигурации для файла сборки модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-133">You need to make an entry in the configuration file for your delivery extension assembly file.</span></span> <span data-ttu-id="a6b48-134">Файл конфигурации можно открыть с помощью [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] или простого текстового редактора, например Блокнота.</span><span class="sxs-lookup"><span data-stu-id="a6b48-134">You can open the configuration file with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="a6b48-135">Найдите в файле RSReportServer.config элемент `Delivery`.</span><span class="sxs-lookup"><span data-stu-id="a6b48-135">Locate the `Delivery` element in the RSReportServer.config file.</span></span> <span data-ttu-id="a6b48-136">Запись для созданного модуля доставки должна находиться в следующем разделе файла:</span><span class="sxs-lookup"><span data-stu-id="a6b48-136">An entry for your newly created delivery extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Delivery>  
          <Your extension configuration information goes here>  
       </Delivery>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="a6b48-137">Добавьте запись для модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-137">Add an entry for your delivery extension.</span></span> <span data-ttu-id="a6b48-138">В новую запись должен входить элемент `Extension` со значениями параметров `Name` и `Type`. Запись может выглядеть, например следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a6b48-138">Your entry should include an `Extension` element with values for `Name` and `Type`, and might look like the following:</span></span>  
  
    ```  
    <Extension Name="My Delivery Extension Name" Type="CompanyName.ExtensionName.MyDeliveryExtensionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="a6b48-139">Значение атрибута `Name` является уникальным именем модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-139">The value for `Name` is the unique name of the delivery extension.</span></span> <span data-ttu-id="a6b48-140">Значением атрибута `Type` является список с разделителями-запятыми, который содержит запись для полного пространства имен класса, в котором реализован интерфейс <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>, за которым следует имя сборки (не включая расширение DLL для файла).</span><span class="sxs-lookup"><span data-stu-id="a6b48-140">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="a6b48-141">По умолчанию модули доставки являются видимыми.</span><span class="sxs-lookup"><span data-stu-id="a6b48-141">By default, delivery extensions are visible.</span></span> <span data-ttu-id="a6b48-142">Чтобы скрыть модуль от пользовательских интерфейсов, таких как диспетчер отчетов, добавьте атрибут `Visible` к элементу `Extension` и задайте для него значение `false`.</span><span class="sxs-lookup"><span data-stu-id="a6b48-142">To hide an extension from user interfaces, such as Report Manager, add a `Visible` attribute to the `Extension` element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="a6b48-143">Наконец, добавьте для пользовательской сборки группу кода, которая предоставляет модулю доставки разрешение `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="a6b48-143">Finally, add a code group for your custom assembly that grants `FullTrust` permission for your delivery extension.</span></span> <span data-ttu-id="a6b48-144">Это можно сделать, добавив группу кода в файл rssrvpolicy.config, расположенный по умолчанию в%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="a6b48-144">You do this by adding the code group to the rssrvpolicy.config file located by default in %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer.</span></span> <span data-ttu-id="a6b48-145">Пример группы кода показан ниже.</span><span class="sxs-lookup"><span data-stu-id="a6b48-145">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my delivery extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<InstanceName>\Reporting Services\ReportServer\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
     <span data-ttu-id="a6b48-146">URL-членство — это лишь одно из множества условий членства, которые можно выбрать для модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-146">URL membership is only one of many membership conditions you might choose for your delivery extension.</span></span> <span data-ttu-id="a6b48-147">Дополнительные сведения об управлении доступом для кода в [!INCLUDE[ssRS](../../../includes/ssrs.md)]см. в разделе [Безопасная разработка (службы Reporting Services)](../secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="a6b48-147">For more information about code access security in [!INCLUDE[ssRS](../../../includes/ssrs.md)], see.[Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="deploying-the-extension-to-report-manager"></a><span data-ttu-id="a6b48-148">Развертывание модуля в диспетчере отчетов</span><span class="sxs-lookup"><span data-stu-id="a6b48-148">Deploying the Extension to Report Manager</span></span>  
 <span data-ttu-id="a6b48-149">Если модуль доставки реализует интерфейс <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl>, то этот модуль можно использовать со страницей «Подписка диспетчера отчетов».</span><span class="sxs-lookup"><span data-stu-id="a6b48-149">If your delivery extension implements the <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> interface, your delivery extension can be used with the Report Manager Subscription page.</span></span> <span data-ttu-id="a6b48-150">Чтобы сделать доступным пользовательский интерфейс подписки, необходимо выполнить развертывание модуля в диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="a6b48-150">To make the subscription user interface available, you need to deploy your extension to Report Manager.</span></span>  
  
#### <a name="to-deploy-a-deliver-extension-assembly-to-report-manager"></a><span data-ttu-id="a6b48-151">Развертывание сборки модуля доставки в диспетчере отчетов</span><span class="sxs-lookup"><span data-stu-id="a6b48-151">To deploy a deliver extension assembly to Report Manager</span></span>  
  
1.  <span data-ttu-id="a6b48-152">Скопируйте сборку из промежуточной папки в каталог bin диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a6b48-152">Copy your assembly from your staging location to the bin directory of Report Manager.</span></span> <span data-ttu-id="a6b48-153">Расположением диспетчер отчетов каталога bin по умолчанию является%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Сервицес\репортманажер\бин.</span><span class="sxs-lookup"><span data-stu-id="a6b48-153">The default location of the Report Manager bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportManager\bin.</span></span>  
  
2.  <span data-ttu-id="a6b48-154">Скопировав файл сборки, откройте файл RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="a6b48-154">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="a6b48-155">Файл RSReportServer.config находится в папке%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> Каталог \Reporting Services\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="a6b48-155">The RSReportServer.config file is located in the %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer directory.</span></span> <span data-ttu-id="a6b48-156">Необходимо создать запись в файле конфигурации для файла сборки модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-156">You need to make an entry in the configuration file for your delivery extension assembly file.</span></span> <span data-ttu-id="a6b48-157">Файл конфигурации можно открыть с помощью среды Visual Studio .NET или воспользоваться простым текстовым редактором (таким как Блокнот).</span><span class="sxs-lookup"><span data-stu-id="a6b48-157">You can open the configuration file with Visual Studio .NET or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="a6b48-158">Найдите в файле RSReportServer.config элемент `DeliveryUI`.</span><span class="sxs-lookup"><span data-stu-id="a6b48-158">Locate the `DeliveryUI` element in the RSReportServer.config file.</span></span> <span data-ttu-id="a6b48-159">Запись для созданного модуля доставки должна находиться в следующем разделе файла:</span><span class="sxs-lookup"><span data-stu-id="a6b48-159">An entry for your newly created delivery extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <DeliveryUI>  
          <Your extension configuration information goes here>  
       </DeliveryUI>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="a6b48-160">Добавьте запись для модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-160">Add an entry for your delivery extension.</span></span> <span data-ttu-id="a6b48-161">В новую запись должен входить элемент `Extension` со значениями параметров `Name` и `Type`. Запись может выглядеть, например, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a6b48-161">Your entry should include an `Extension` element with values for `Name` and `Type` and might look like the following:</span></span>  
  
    ```  
    <Extension Name="My Delivery Extension Name" Type="CompanyName.ExtensionName.MyDeliveryUIExtensionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="a6b48-162">Значение атрибута `Name` является уникальным именем модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-162">The value for `Name` is the unique name of the delivery extension.</span></span> <span data-ttu-id="a6b48-163">Значением атрибута `Type` является список с разделителями-запятыми, который содержит запись для полного пространства имен класса, в котором реализован интерфейс <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl>, за которым следует имя сборки (не включая расширение DLL для файла).</span><span class="sxs-lookup"><span data-stu-id="a6b48-163">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> interface, followed by the name of your assembly (not including the .dll file extension).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a6b48-164">Значение атрибута `Name` должно быть идентичным соответствующим записям в файле конфигурации сервера отчетов и диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a6b48-164">The value of the `Name` attribute must be identical for both the Report Server and Report Manager configuration file entries.</span></span> <span data-ttu-id="a6b48-165">Если они отличаются друг от друга, то конфигурация сервера будет недопустимой.</span><span class="sxs-lookup"><span data-stu-id="a6b48-165">If they are not identical, your server configuration is not valid.</span></span>  
  
     <span data-ttu-id="a6b48-166">Наконец, добавьте для пользовательской сборки группу кода, которая предоставляет модулю доставки разрешение `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="a6b48-166">Finally, add a code group for your custom assembly that grants `FullTrust` permission for your delivery extension.</span></span> <span data-ttu-id="a6b48-167">Это можно сделать, добавив группу кода в файл RSmgrpolicy.config, расположенный по умолчанию в папке C:\Program Files\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportManager.</span><span class="sxs-lookup"><span data-stu-id="a6b48-167">You do this by adding the code group to the RSmgrpolicy.config file located by default in C:\Program Files\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportManager.</span></span> <span data-ttu-id="a6b48-168">Пример группы кода показан ниже.</span><span class="sxs-lookup"><span data-stu-id="a6b48-168">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my delivery UI extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<InstanceName>\Reporting Services\ReportManager\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
     <span data-ttu-id="a6b48-169">URL-членство — это лишь одно из множества условий членства, которые можно выбрать для модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-169">URL membership is only one of many membership conditions you might choose for your delivery extension.</span></span> <span data-ttu-id="a6b48-170">Дополнительные сведения об обеспечении безопасности доступа к коду в см. в [!INCLUDE[ssRS](../../../includes/ssrs.md)] разделе [безопасность разработки &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="a6b48-170">For more information about code access security in [!INCLUDE[ssRS](../../../includes/ssrs.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="a6b48-171">Проверка развертывания</span><span class="sxs-lookup"><span data-stu-id="a6b48-171">Verifying the Deployment</span></span>  
 <span data-ttu-id="a6b48-172">Проверить, успешно ли был развернут модуль доставки на сервере отчетов, можно с помощью метода веб-службы <xref:ReportService2010.ReportingService2010.ListExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6b48-172">You can verify whether your delivery extension was deployed successfully to the report server by using the Web service <xref:ReportService2010.ReportingService2010.ListExtensions%2A> method.</span></span> <span data-ttu-id="a6b48-173">Можно также открыть диспетчер отчетов и убедиться, что модуль включен в список доступных модулей доставки для подписки.</span><span class="sxs-lookup"><span data-stu-id="a6b48-173">You can also open Report Manager and verify that your extension is included in the list of available delivery extensions for a subscription.</span></span> <span data-ttu-id="a6b48-174">Дополнительные сведения о диспетчер отчетов и подписках см. в разделе [подписки и доставка &#40;Reporting Services&#41;](../../subscriptions/subscriptions-and-delivery-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="a6b48-174">For more information about Report Manager and subscriptions, see [Subscriptions and Delivery &#40;Reporting Services&#41;](../../subscriptions/subscriptions-and-delivery-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6b48-175">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6b48-175">See Also</span></span>  
 <span data-ttu-id="a6b48-176">[Реализация модуля доставки](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="a6b48-176">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="a6b48-177">Библиотека модулей служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a6b48-177">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
