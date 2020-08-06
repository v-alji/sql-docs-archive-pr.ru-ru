---
title: Изменение модуля доставки отчетов Reporting Services по умолчанию | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Report Manager [Reporting Services], default delivery extension
ms.assetid: 5f6fee72-01bf-4f6c-85d2-7863c46c136b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cc1b3af2a4fe3038b761d0b48030062da06d354e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734921"
---
# <a name="change-the-default-reporting-services-delivery-extension"></a><span data-ttu-id="1144a-102">Изменение модуля доставки отчетов служб Reporting Services по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1144a-102">Change the Default Reporting Services Delivery Extension</span></span>
  <span data-ttu-id="1144a-103">Вы можете изменить настройки конфигурации [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] , чтобы сменить модуль доставки по умолчанию, который отображается в списке **Доставлено** , на странице определения подписки.</span><span class="sxs-lookup"><span data-stu-id="1144a-103">You can modify [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration settings to change the default delivery extension that appears in the **Delivered by** list of a subscription definition page.</span></span> <span data-ttu-id="1144a-104">Например, можно изменить конфигурацию так, чтобы при создании пользователями новой подписки по умолчанию выбиралась доставка в общую папку, а не доставка по почте.</span><span class="sxs-lookup"><span data-stu-id="1144a-104">For example you can modify the configuration so that when users create a new subscription, file share delivery is selected by default instead of e-mail delivery.</span></span> <span data-ttu-id="1144a-105">Можно также изменить порядок модулей доставки в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="1144a-105">You can also change the order the delivery extensions are listed in the user interface.</span></span>

 <span data-ttu-id="1144a-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] в собственном режиме | [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] в режиме интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="1144a-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode | [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>

 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="1144a-107">включают модуль доставки по электронной почте и модуль доставки в общую папку Windows.</span><span class="sxs-lookup"><span data-stu-id="1144a-107">includes E-mail and Windows File Share delivery are extensions.</span></span> <span data-ttu-id="1144a-108">У сервера отчетов могут быть дополнительные модули доставки, если развернуть пользовательские модули или модули сторонних производителей для поддержки пользовательской доставки.</span><span class="sxs-lookup"><span data-stu-id="1144a-108">Your report server might have additional delivery extensions if you have deployed custom or third-party extensions to support custom delivery.</span></span> <span data-ttu-id="1144a-109">Доступность модуля доставки зависит от того, развернут ли он на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="1144a-109">The availability of a delivery extension depends on whether it is deployed on a report server.</span></span>

## <a name="default-native-mode-report-server-configuration"></a><span data-ttu-id="1144a-110">Настройка сервера отчетов в собственном режиме по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1144a-110">Default Native mode report server configuration</span></span>
 <span data-ttu-id="1144a-111">Порядок, в котором модули доставки отображаются в списке **Доставлено** в диспетчере отчетов, основан на порядке записей модулей доставки в файле **RSReportServer.config** .</span><span class="sxs-lookup"><span data-stu-id="1144a-111">The order of a delivery extension appears in Report Manager in the **Delivered by** list is based on the order of the delivery extension entries in the **RSReportServer.config** file.</span></span> <span data-ttu-id="1144a-112">Например, на следующем рисунке электронная почта находится вначале в списке, и она выбрана по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1144a-112">For example the following image shows e-mail first in the list and it is selected by default.</span></span>

 <span data-ttu-id="1144a-113">![заданный по умолчанию список модулей доставки](../media/ssrs-default-delivery.png "заданный по умолчанию список модулей доставки")</span><span class="sxs-lookup"><span data-stu-id="1144a-113">![default list of delivery extensions](../media/ssrs-default-delivery.png "default list of delivery extensions")</span></span>

 <span data-ttu-id="1144a-114">Ниже приведен раздел **RSReportServer.config** по умолчанию, управляющий модулем доставки по умолчанию и порядком отображения модулей в диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="1144a-114">The following is the default section of **RSReportServer.config** that controls the default delivery extension and the order they are displayed in Report Manager.</span></span> <span data-ttu-id="1144a-115">Обратите внимание, что электронная почта отображается в файле первой и выбрана как параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1144a-115">Note that email appears first in the file and it is set as the default.</span></span>

```xml
<DeliveryUI>
     <Extension Name="Report Server Email" Type="Microsoft.ReportingServices.EmailDeliveryProvider.EmailDeliveryProviderControl,ReportingServicesEmailDeliveryProvider">
          <DefaultDeliveryExtension>True</DefaultDeliveryExtension>
               <Configuration>
               <RSEmailDPConfiguration>
                    <DefaultRenderingExtension>MHTML</DefaultRenderingExtension>
               </RSEmailDPConfiguration>
               </Configuration>
     </Extension>
     <Extension Name="Report Server FileShare" Type="Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl,ReportingServicesFileShareDeliveryProvider"/>
</DeliveryUI>
```

#### <a name="configure-file-share-delivery-as-the-default-delivery-extension-in-report-manager"></a><span data-ttu-id="1144a-116">Настройка доставки в общую папку в качестве модуля доставки по умолчанию диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="1144a-116">Configure File Share Delivery as the default delivery extension in Report Manager</span></span>

1.  <span data-ttu-id="1144a-117">В этой процедуре конфигурация изменяется так, чтобы доставка в общую папку была указана в качестве первого параметра в пользовательском интерфейсе и была параметром по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1144a-117">The steps in this procedure modify the configuration so that file share delivery is listed as the first option in the UI and it is the default selection.</span></span>

     <span data-ttu-id="1144a-118">Откройте файл RSReportServer.config в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="1144a-118">Open the RSReportServer.config file in a text editor.</span></span> <span data-ttu-id="1144a-119">Дополнительные сведения о файле конфигурации см. в разделе [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="1144a-119">For more information on the configuration file, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span> <span data-ttu-id="1144a-120">После изменения конфигурации пользовательский интерфейс будет выглядеть как на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="1144a-120">After the configuration changes, the UI will look like the following image:</span></span>

     <span data-ttu-id="1144a-121">![измененный список модулей доставки](../media/ssrs-modified-delivery.png "измененный список модулей доставки")</span><span class="sxs-lookup"><span data-stu-id="1144a-121">![modified list of delivery extensions](../media/ssrs-modified-delivery.png "modified list of delivery extensions")</span></span>

2.  <span data-ttu-id="1144a-122">Измените раздел DeliveryUI, как в следующем примере, и обратите внимание на основные изменения.</span><span class="sxs-lookup"><span data-stu-id="1144a-122">Modify the DeliveryUI section to look like the following sample and note the key changes of:</span></span>

    1.  <span data-ttu-id="1144a-123">Модуль доставки в общую папку находится перед модулем электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1144a-123">The FileShare extension is before the email extension.</span></span> <span data-ttu-id="1144a-124">Это приведет к изменению порядка модулей доставки в диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="1144a-124">This will change the order the extensions are listed in Report Manager.</span></span>

    2.  <span data-ttu-id="1144a-125">Модуль доставки в общую папку содержит тег DefaultExtension `<DefaultDeliveryExtension>True</DefaultDeliveryExtension>` , также был добавлен закрывающий тег модуля `</Extension>`.</span><span class="sxs-lookup"><span data-stu-id="1144a-125">The File share extension contains DefaultExtension tag `<DefaultDeliveryExtension>True</DefaultDeliveryExtension>` and the extension end tag was added `</Extension>`.</span></span>

    3.  <span data-ttu-id="1144a-126">Модуль доставки по почте больше не задан по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1144a-126">The email extension is no longer configured as the default.</span></span> `<DefaultDeliveryExtension>False</DefaultDeliveryExtension>`

    ```
    <DeliveryUI>
         <Extension Name="Report Server FileShare" Type="Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl,ReportingServicesFileShareDeliveryProvider">
              <DefaultDeliveryExtension>True</DefaultDeliveryExtension>
         </Extension>
         <Extension Name="Report Server Email" Type="Microsoft.ReportingServices.EmailDeliveryProvider.EmailDeliveryProviderControl,ReportingServicesEmailDeliveryProvider">
         <DefaultDeliveryExtension>False</DefaultDeliveryExtension>
         <Configuration>
              <RSEmailDPConfiguration>
                   <DefaultRenderingExtension>MHTML</DefaultRenderingExtension>
              </RSEmailDPConfiguration>
         </Configuration>
         </Extension>
    </DeliveryUI>
    ```

3.  <span data-ttu-id="1144a-127">Сохраните файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1144a-127">Save the configuration file.</span></span>

4.  <span data-ttu-id="1144a-128">В течение нескольких минут сервер отчетов перезагрузит файл конфигурации, и новые параметры вступят в силу.</span><span class="sxs-lookup"><span data-stu-id="1144a-128">Within a few minutes the report server will reload the configuration file and the new settings will take effect.</span></span> <span data-ttu-id="1144a-129">Вы можете перезапустить службу сервера отчетов для принудительной загрузки файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1144a-129">You can restart the report server service to force the loading of the configuration file.</span></span>

     <span data-ttu-id="1144a-130">Следующее событие записывается в журнал событий Windows при чтении конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1144a-130">The following event is written to the windows event log when the configuration is read.</span></span>

     <span data-ttu-id="1144a-131">**Идентификатор события:** 109</span><span class="sxs-lookup"><span data-stu-id="1144a-131">**Event ID:** 109</span></span>

     <span data-ttu-id="1144a-132">**Источник**: служба Windows для сервера отчетов (имя экземпляра)</span><span class="sxs-lookup"><span data-stu-id="1144a-132">**Source:** Report Server Windows Service (instance name)</span></span>

     <span data-ttu-id="1144a-133">Файл RSReportServer.config был изменен.</span><span class="sxs-lookup"><span data-stu-id="1144a-133">The RSReportServer.config file has been modified</span></span>

## <a name="sharepoint-mode-report-servers"></a><span data-ttu-id="1144a-134">Серверы отчетов в режиме интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="1144a-134">SharePoint mode report servers</span></span>
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="1144a-135">в режиме интеграции SharePoint сведения о модулях доставки хранятся в базах данных приложения-службы, а не в файле RsrReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="1144a-135">SharePoint mode stores extensions information in the SharePoint service application databases and not in the RsrReportServer.config file.</span></span> <span data-ttu-id="1144a-136">В режиме интеграции с SharePoint настройки модуля доставки изменяются с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1144a-136">In SharePoint mode, delivery extension configuration is modified using PowerShell.</span></span>

#### <a name="configure-the-default-delivery-extension"></a><span data-ttu-id="1144a-137">Настройка модуля доставки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1144a-137">Configure the default delivery extension</span></span>

1.  <span data-ttu-id="1144a-138">Откройте **консоль управления SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="1144a-138">Open the **SharePoint Management Shell**.</span></span>

2.  <span data-ttu-id="1144a-139">Этот шаг можно пропустить, если вам известно имя приложения-службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1144a-139">You can skip this step if you already know the name of your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="1144a-140">Используйте следующие команды PowerShell, чтобы получить список приложений-служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] в ферме SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1144a-140">Use the following PowerShell to list the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service applications in your SharePoint farm.</span></span>

    ```powershell
    Get-SPRSServiceApplication | Format-List *
    ```

3.  <span data-ttu-id="1144a-141">Выполните следующие команды PowerShell для проверки текущего модуля доставки по умолчанию для приложения-службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] "ssrsapp".</span><span class="sxs-lookup"><span data-stu-id="1144a-141">Run the following PowerShell to verify the current default delivery extension for the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service application "ssrsapp".</span></span>

    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -Like "ssrsapp*"};
    Get-SPRSExtension -Identity $app | Where {$_.ServerDirectivesXML -Like "<DefaultDelivery*"} | Format-List *
    ```

## <a name="see-also"></a><span data-ttu-id="1144a-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="1144a-142">See Also</span></span>
 <span data-ttu-id="1144a-143">Файл [конфигурации RSReportServer](../report-server/rsreportserver-config-configuration-file.md) [Конфигурация RSReportServer](../report-server/rsreportserver-config-configuration-file.md) файлового [ресурса доставка в Reporting Services](file-share-delivery-in-reporting-services.md) [доставки электронной почты в Reporting Services](e-mail-delivery-in-reporting-services.md) [настройка сервера отчетов для доставки электронной почты &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)</span><span class="sxs-lookup"><span data-stu-id="1144a-143">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) [File Share Delivery in Reporting Services](file-share-delivery-in-reporting-services.md) [E-Mail Delivery in Reporting Services](e-mail-delivery-in-reporting-services.md) [Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)</span></span>
