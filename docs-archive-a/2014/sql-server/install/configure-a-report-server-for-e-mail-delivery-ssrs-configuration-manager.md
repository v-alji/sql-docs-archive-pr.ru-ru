---
title: Настройка сервера отчетов для доставки электронной почты (службы SSRS Configuration Manager) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], distributing
- report servers [Reporting Services], e-mail delivery
- remote SMTP service [Reporting Services]
- distributing reports [Reporting Services], e-mail
- CDO
- Collaboration Data Objects
- SMTP settings [Reporting Services]
- e-mail [Reporting Services]
- sending reports
- mail [Reporting Services]
- local SMTP service [Reporting Services]
ms.assetid: b838f970-d11a-4239-b164-8d11f4581d83
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3122dbbb5debc90afa73ca0f8ab0d8e23d38a0ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665782"
---
# <a name="configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager"></a><span data-ttu-id="9dc51-102">Настройка сервера отчетов для работы с электронной почтой (диспетчер конфигурации служб Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="9dc51-102">Configure a Report Server for E-Mail Delivery (SSRS Configuration Manager)</span></span>


  <span data-ttu-id="9dc51-103">Службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] включают модуль доставки по электронной почте, позволяющий распространять отчеты с помощью электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9dc51-103">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] includes an e-mail delivery extension so that you can distribute reports through e-mail.</span></span> <span data-ttu-id="9dc51-104">В зависимости от того, каким образом определена электронная подписка, рассылка может включать уведомление, ссылку, вложение или внедренный отчет.</span><span class="sxs-lookup"><span data-stu-id="9dc51-104">Depending on how you define the e-mail subscription, a delivery might consist of a notification, link, attachment, or embedded report.</span></span> <span data-ttu-id="9dc51-105">Модуль доставки по электронной почте работает с существующими технологиями почтовых серверов.</span><span class="sxs-lookup"><span data-stu-id="9dc51-105">The e-mail delivery extension works with your existing mail server technology.</span></span> <span data-ttu-id="9dc51-106">Почтовый сервер должен быть либо SMTP-сервером, либо перенаправителем.</span><span class="sxs-lookup"><span data-stu-id="9dc51-106">The mail server must be an SMTP server or forwarder.</span></span> <span data-ttu-id="9dc51-107">Сервер отчетов соединяется с SMTP-сервером через объекты данных совместной работы (библиотека cdosys.dll), предоставляемых операционной системой.</span><span class="sxs-lookup"><span data-stu-id="9dc51-107">The report server connects to an SMTP server through Collaboration Data Objects (CDO) libraries (cdosys.dll) that are provided by the operating system.</span></span>  
  
 <span data-ttu-id="9dc51-108">Модуль доставки электронной почты сервера отчетов не настроен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9dc51-108">The report server e-mail delivery extension is not configured by default.</span></span> <span data-ttu-id="9dc51-109">Для минимальной настройки модуля следует воспользоваться диспетчером настройки служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="9dc51-109">You must use the Reporting Services Configuration Manager to minimally configure the extension.</span></span> <span data-ttu-id="9dc51-110">Чтобы указать дополнительные свойства, необходимо изменить файл конфигурации `RSReportServer.config` .</span><span class="sxs-lookup"><span data-stu-id="9dc51-110">To set advanced properties, you must edit the `RSReportServer.config` file.</span></span> <span data-ttu-id="9dc51-111">Если нельзя настроить сервер отчетов на использование этого модуля, то вместо этого можно доставлять отчеты в общую папку.</span><span class="sxs-lookup"><span data-stu-id="9dc51-111">If you cannot configure the report server to use this extension, you can deliver reports to a shared folder instead.</span></span> <span data-ttu-id="9dc51-112">Дополнительные сведения см. в разделе [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="9dc51-112">For more information, see [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md).</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="9dc51-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим</span><span class="sxs-lookup"><span data-stu-id="9dc51-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
 
  
##  <a name="configuration-requirements"></a><a name="bkmk_configuration_requirements"></a><span data-ttu-id="9dc51-114">Требования к конфигурации</span><span class="sxs-lookup"><span data-stu-id="9dc51-114">Configuration Requirements</span></span>  
  
-   <span data-ttu-id="9dc51-115">Доставка сервером отчетов по электронной почте реализована на основе объектов данных совместной работы и требует локального или удаленного SMTP-сервера или перенаправителя.</span><span class="sxs-lookup"><span data-stu-id="9dc51-115">Report server e-mail delivery is implemented on Collaboration Data Objects (CDO) and requires a local or remote Simple Mail Transfer Protocol (SMTP) server or SMTP forwarder.</span></span> <span data-ttu-id="9dc51-116">Протокол SMTP поддерживается не для всех операционных систем Windows.</span><span class="sxs-lookup"><span data-stu-id="9dc51-116">SMTP is not supported on all Windows operating systems.</span></span> <span data-ttu-id="9dc51-117">В частности, он не поддерживается в выпуске Windows Server 2008 для платформы Itanium.</span><span class="sxs-lookup"><span data-stu-id="9dc51-117">If you are using the Itanium-based edition of Windows Server 2008, SMTP is not supported.</span></span> <span data-ttu-id="9dc51-118">Дополнительные сведения о параметрах конфигурации, предоставляемых объектами CDO, см. в MSDN, в статье [CoClass конфигурации](https://go.microsoft.com/fwlink/?LinkId=98237) .</span><span class="sxs-lookup"><span data-stu-id="9dc51-118">For more information about configuration options provided through CDO, see [Configuration CoClass](https://go.microsoft.com/fwlink/?LinkId=98237) on MSDN.</span></span>  
  
-   <span data-ttu-id="9dc51-119">Учетная запись службы сервера отчетов должна иметь разрешение на отправку почты через SMTP-сервер.</span><span class="sxs-lookup"><span data-stu-id="9dc51-119">The Report Server service account must have permission on the SMTP server to send mail.</span></span>  
  
-   <span data-ttu-id="9dc51-120">Модуль доставки по электронной почте использует во вложениях электронной почты кодировку UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9dc51-120">The e-mail delivery extension uses UTF-8 encoding in e-mail attachments.</span></span> <span data-ttu-id="9dc51-121">Она не может быть изменена: модуль подготовки HTML поддерживает только UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9dc51-121">You cannot modify the encoding; the HTML rendering extension only supports UTF-8.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9dc51-122">Модуль доставки по электронной почте по умолчанию не поддерживает цифровые подписи или шифрование в исходящих сообщениях почты.</span><span class="sxs-lookup"><span data-stu-id="9dc51-122">The default e-mail delivery extension does not provide support for digitally signing or encrypting outgoing mail messages.</span></span>  
  
 
  
##  <a name="configuring-a-report-server-for-local-or-remote-smtp-service"></a><a name="bkmk_configure_for_local_or_remote_SMTP"></a><span data-ttu-id="9dc51-123">Настройка сервера отчетов для локальной или удаленной службы SMTP</span><span class="sxs-lookup"><span data-stu-id="9dc51-123">Configuring a Report Server for Local or Remote SMTP Service</span></span>  
 <span data-ttu-id="9dc51-124">Для поддержки рассылки по электронной почте можно использовать локальную службу SMTP, удаленный сервер или SMTP-перенаправитель.</span><span class="sxs-lookup"><span data-stu-id="9dc51-124">You can use a local SMTP service or a remote SMTP server or forwarder to support e-mail delivery.</span></span> <span data-ttu-id="9dc51-125">Если есть доступ к существующему удаленному SMTP-серверу, следует рассмотреть возможность его использования.</span><span class="sxs-lookup"><span data-stu-id="9dc51-125">If you have access to an existing remote SMTP server, you should consider using it.</span></span> <span data-ttu-id="9dc51-126">Если SMTP-сервер недоступен или впоследствии возникают ошибки при доставке отчетов, которые можно объяснить сбоями подключения к компьютеру, следует перейти к использованию локальной службы SMTP.</span><span class="sxs-lookup"><span data-stu-id="9dc51-126">If there is no SMTP server available or if you subsequently encounter report delivery errors that can be attributed to computer connection failures, you should switch to using a local SMTP service.</span></span> <span data-ttu-id="9dc51-127">Более подробные сведения о настройке сервера отчета для работы с локальной или удаленной службой приводятся ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9dc51-127">Details about how to configure a report server for local or remote service are provided further on in this topic.</span></span>  
  
  
  
##  <a name="setting-configuration-options-for-e-mail-delivery"></a><a name="bkmk_setting_email_delivery"></a><span data-ttu-id="9dc51-128">Установка параметров конфигурации для доставки электронной почты</span><span class="sxs-lookup"><span data-stu-id="9dc51-128">Setting Configuration Options for E-Mail Delivery</span></span>  
 <span data-ttu-id="9dc51-129">Прежде чем будет можно использовать рассылку сервера отчетов по электронной почте, следует установить значения конфигурации, указывающие, какой SMTP-сервер использовать.</span><span class="sxs-lookup"><span data-stu-id="9dc51-129">Before you can use Report Server e-mail delivery, you must set configuration values that provide information about which SMTP server to use.</span></span>  
  
 <span data-ttu-id="9dc51-130">Для настройки сервера отчетов для доставки электронной почты выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9dc51-130">To configure a report server for e-mail delivery, do the following:</span></span>  
  
-   <span data-ttu-id="9dc51-131">Воспользуйтесь диспетчером конфигурации служб Reporting Services, если вы задаете SMTP-сервер и учетную запись, имеющую разрешение на отправку сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9dc51-131">Use the Reporting Services Configuration Manager if you are specifying just an SMTP server and a user account that has permission to send e-mail.</span></span> <span data-ttu-id="9dc51-132">Это минимальные установки, необходимые для настройки модуля доставки электронной почты сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9dc51-132">These are the minimum settings that are required for configuring the Report Server e-mail delivery extension.</span></span> <span data-ttu-id="9dc51-133">Дополнительные сведения см. в разделе [Параметры электронной почты — Configuration Manager &#40;служб SSRS в собственном режиме&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) и [Доставка электронной почты в Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="9dc51-133">For more information, see [E-mail Settings - Configuration Manager &#40;SSRS Native Mode&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) and [E-Mail Delivery in Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="9dc51-134">С помощью текстового редактора укажите дополнительные параметры в файле конфигурации RSreportserver.config (необязательно).</span><span class="sxs-lookup"><span data-stu-id="9dc51-134">(Optionally) Use a text editor to specify additional settings in the RSreportserver.config file.</span></span> <span data-ttu-id="9dc51-135">Этот файл содержит все параметры конфигурации доставки отчетов по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="9dc51-135">This file contains all of the configuration settings for Report Server e-mail delivery.</span></span> <span data-ttu-id="9dc51-136">Задание дополнительных установок в этих файлах необходимо, если используется локальный SMTP-сервер или если доставка сообщений электронной почты ограничивается определенными узлами.</span><span class="sxs-lookup"><span data-stu-id="9dc51-136">Specifying additional settings in these files is required if you are using a local SMTP server or if you are restricting e-mail delivery to specific hosts.</span></span> <span data-ttu-id="9dc51-137">Дополнительные сведения о поиске и изменении файлов конфигурации см. в разделе [изменение файла конфигурации Reporting Services &#40;RSreportserver.config&#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) в Электронная документация на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9dc51-137">For more information about finding and modifying configuration files, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9dc51-138">Параметры электронной почты сервера отчетов основаны на объектах CDO.</span><span class="sxs-lookup"><span data-stu-id="9dc51-138">Report server e-mail settings are based on CDO.</span></span> <span data-ttu-id="9dc51-139">Если необходимы дальнейшие подробности о конкретных параметрах, можно обратиться к документации по приложениям CDO.</span><span class="sxs-lookup"><span data-stu-id="9dc51-139">If you want more detail about specific settings, you can refer to the CDO production documentation.</span></span>  
  

  
##  <a name="example-report-server-e-mail-configuration"></a><a name="bkmk_example_config_file"></a><span data-ttu-id="9dc51-140">Пример конфигурации электронной почты сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="9dc51-140">Example Report Server E-Mail Configuration</span></span>  
 <span data-ttu-id="9dc51-141">В следующем примере иллюстрируются параметры файла RSreportserver.config для удаленного SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="9dc51-141">The following example illustrates the settings in the RSreportserver.config file for a remote SMTP server.</span></span> <span data-ttu-id="9dc51-142">Описания параметров и их допустимых значений см. в разделе [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Onlэлектронной документации поe or the CDO product documentation.</span><span class="sxs-lookup"><span data-stu-id="9dc51-142">To read about the setting descriptions and valid values, see [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or the CDO product documentation.</span></span>  
  
```  
<RSEmailDPConfiguration>  
     <SMTPServer>mySMTPServer.Adventure-Works.com</SMTPServer>  
     <SMTPServerPort></SMTPServerPort>  
     <SMTPAccountName></SMTPAccountName>  
     <SMTPConnectionTimeout></SMTPConnectionTimeout>  
     <SMTPServerPickupDirectory></SMTPServerPickupDirectory>  
     <SMTPUseSSL></SMTPUseSSL>  
     <SendUsing>2</SendUsing>  
     <SMTPAuthenticate></SMTPAuthenticate>  
     <From>my-rs-email-account@Adventure-Works.com</From>  
     <EmbeddedRenderFormats>  
          <RenderingExtension>MHTML</RenderingExtension>  
     </EmbeddedRenderFormats>  
     <PrivilegedUserRenderFormats></PrivilegedUserRenderFormats>  
     <ExcludedRenderFormats>  
          <RenderingExtension>HTMLOWC</RenderingExtension>  
          <RenderingExtension>NULL</RenderingExtension>  
     </ExcludedRenderFormats>  
     <SendEmailToUserAlias>True</SendEmailToUserAlias>  
     <DefaultHostName></DefaultHostName>  
     <PermittedHosts>  
          <HostName>Adventure-Works.com</HostName>  
          <HostName>hotmail.com</HostName>  
     </PermittedHosts>  
</RSEmailDPConfiguration>  
```  
  

  
##  <a name="configuration-options-for-setting-the-to-field-in-a-message"></a><a name="bkmk_setting_TO_field"></a><span data-ttu-id="9dc51-143">Параметры конфигурации для поля "Кому" в сообщении</span><span class="sxs-lookup"><span data-stu-id="9dc51-143">Configuration Options for Setting the To: Field in a Message</span></span>  
 <span data-ttu-id="9dc51-144">Пользовательские подписки, создаваемые в соответствии с разрешениями, предоставленными задачей « **Управление отдельными подписками** », содержат предварительно заданное имя пользователя, основанное на учетной записи пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="9dc51-144">User-defined subscriptions that are created according to the permissions granted by the **Manage individual subscriptions** task contain a pre-set user name that is based on the domain user account.</span></span> <span data-ttu-id="9dc51-145">Когда пользователь создает подписку, имя получателя в поле **Кому:** подставляется автоматически; используется учетная запись пользователя домена, создающего подписку.</span><span class="sxs-lookup"><span data-stu-id="9dc51-145">When the user creates the subscription, the recipient name in the **To:** field is self-addressed using the domain user account of the person creating the subscription.</span></span>  
  
 <span data-ttu-id="9dc51-146">Если использовать SMTP-сервер или перенаправитель, который использует учетные записи электронной почты, отличающиеся от учетной записи пользователя домена, то во время доставки отчета произойдет ошибка, когда SMTP-сервер попытается доставить отчет этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="9dc51-146">If you are using an SMTP server or forwarder that uses e-mail accounts that are different from the domain user account, the report delivery will fail when the SMTP server tries to deliver the report to that user.</span></span>  
  
 <span data-ttu-id="9dc51-147">Чтобы обойти эту проблему, можно изменить настройки конфигурации так, чтобы пользователь мог ввести имя в поле **Кому:**</span><span class="sxs-lookup"><span data-stu-id="9dc51-147">To workaround this issue, you can modify configuration settings that allow users to enter a name in the **To:** field:</span></span>  
  
1.  <span data-ttu-id="9dc51-148">Откройте файл RSReportServer.config в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="9dc51-148">Open RSReportServer.config with a text editor.</span></span>  
  
2.  <span data-ttu-id="9dc51-149">Задайте для параметра `SendEmailToUserAlias` значение `False`.</span><span class="sxs-lookup"><span data-stu-id="9dc51-149">Set `SendEmailToUserAlias` to `False`.</span></span>  
  
3.  <span data-ttu-id="9dc51-150">Установите параметр `DefaultHostName` в DNS-имя или IP-адрес SMTP-сервера или перенаправителя.</span><span class="sxs-lookup"><span data-stu-id="9dc51-150">Set `DefaultHostName` to the Domain Name System (DNS) name or IP address of the SMTP server or forwarder.</span></span>  
  
4.  <span data-ttu-id="9dc51-151">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="9dc51-151">Save the file.</span></span>  
  
  
  
##  <a name="configuration-options-for-remote-smtp-service"></a><a name="bkmk_options_remote_SMTP"></a><span data-ttu-id="9dc51-152">Параметры конфигурации для удаленной службы SMTP</span><span class="sxs-lookup"><span data-stu-id="9dc51-152">Configuration Options for Remote SMTP Service</span></span>  
 <span data-ttu-id="9dc51-153">Соединение между сервером отчетов и локальным SMTP-сервером или перенаправителем определяется следующими параметрами конфигурации:</span><span class="sxs-lookup"><span data-stu-id="9dc51-153">The connection between the report server and an SMTP server or forwarder is determined by the following configuration settings:</span></span>  
  
-   <span data-ttu-id="9dc51-154">`SendUsing` указывает метод отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="9dc51-154">`SendUsing` specifies a method for sending messages.</span></span> <span data-ttu-id="9dc51-155">Возможен выбор между сетевой службой SMTP или локальным каталогом сбора службы SMTP.</span><span class="sxs-lookup"><span data-stu-id="9dc51-155">You can choose between a network SMTP service or a local SMTP service pickup directory.</span></span> <span data-ttu-id="9dc51-156">Чтобы использовать удаленную SMTP-службу, этому параметру в файле конфигурации RSReportServer.config должно быть присвоено значение **2** .</span><span class="sxs-lookup"><span data-stu-id="9dc51-156">To use a remote SMTP service, this value must be set to **2** in the RSReportServer.config file.</span></span>  
  
-   <span data-ttu-id="9dc51-157">`SMTPServer` указывает удаленный сервер или перенаправитель SMTP.</span><span class="sxs-lookup"><span data-stu-id="9dc51-157">`SMTPServer` specifies the remote SMTP server or forwarder.</span></span> <span data-ttu-id="9dc51-158">Это значение обязательное, если нужно использовать удаленный сервер или перенаправитель SMTP.</span><span class="sxs-lookup"><span data-stu-id="9dc51-158">This value is a required value if you are using a remote SMTP server or forwarder.</span></span>  
  
-   <span data-ttu-id="9dc51-159">`From`задает значение, отображаемое в строке **от:** сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9dc51-159">`From` sets the value that appears in the **From:** line of an e-mail message.</span></span> <span data-ttu-id="9dc51-160">Это значение обязательное, если нужно использовать удаленный сервер или перенаправитель SMTP.</span><span class="sxs-lookup"><span data-stu-id="9dc51-160">This value is a required value if you are using a remote SMTP server or forwarder.</span></span>  
  
 <span data-ttu-id="9dc51-161">Другие значения, которые используются для удаленной службы SMTP, включают следующее (обратите внимание, что указывать их необязательно, если не нужно заменять ими значения по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9dc51-161">Other values that are used for remote SMTP service include the following (note that you do not need to specify these values unless you want to override the default values).</span></span>  
  
-   <span data-ttu-id="9dc51-162">Параметр**SMTPServerPort** настроен для использования порта 25.</span><span class="sxs-lookup"><span data-stu-id="9dc51-162">**SMTPServerPort** is configured for port 25.</span></span>  
  
-   <span data-ttu-id="9dc51-163">Параметр**SMTPAuthenticate** указывает, как сервер отчетов подключается к удаленному SMTP-серверу.</span><span class="sxs-lookup"><span data-stu-id="9dc51-163">**SMTPAuthenticate** specifies how the report server connects to the remote SMTP server.</span></span> <span data-ttu-id="9dc51-164">Значение по умолчанию равно 0 (отсутствие проверки подлинности).</span><span class="sxs-lookup"><span data-stu-id="9dc51-164">The default value is 0 (or no authentication).</span></span> <span data-ttu-id="9dc51-165">В этом случае соединение осуществляется через анонимный доступ.</span><span class="sxs-lookup"><span data-stu-id="9dc51-165">In this case, the connection is made through Anonymous access.</span></span> <span data-ttu-id="9dc51-166">Может потребоваться, чтобы сервер отчетов и SMTP-сервер были элементами одного домена (в зависимости от конфигурации домена).</span><span class="sxs-lookup"><span data-stu-id="9dc51-166">Depending on your domain configuration, the report server and the SMTP server may need to be members of the same domain.</span></span>  
  
     <span data-ttu-id="9dc51-167">Для отправки электронной почты в списки рассылки с ограничениями (например, в списки рассылки, принимающие входящие сообщения только от учетных записей, прошедших проверку подлинности) установите значение **SMTPAuthenticate** равным **2**.</span><span class="sxs-lookup"><span data-stu-id="9dc51-167">To send e-mail to restricted distribution lists (for example, distribution lists that accept incoming messages only from authenticated accounts), set **SMTPAuthenticate** to **2**.</span></span>  
  

  
##  <a name="configuration-options-for-local-smtp-service"></a><a name="bkmk_options_local_SMTP"></a><span data-ttu-id="9dc51-168">Параметры конфигурации для локальной службы SMTP</span><span class="sxs-lookup"><span data-stu-id="9dc51-168">Configuration Options for Local SMTP Service</span></span>  
 <span data-ttu-id="9dc51-169">Настройка локальной службы SMTP полезна при тестировании или диагностике работы с электронной почтой сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9dc51-169">Configuring a local SMTP service is useful if you are testing or troubleshooting report server e-mail delivery.</span></span> <span data-ttu-id="9dc51-170">Локальная служба SMTP по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="9dc51-170">The local SMTP service is not enabled by default.</span></span> <span data-ttu-id="9dc51-171">Инструкции по включению см. в разделе [Настройка сервера отчетов для доставки электронной почты (SSRS Configuration Manager)](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) и [параметров электронной почты — Configuration Manager &#40;служб SSRS в основном режиме&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9dc51-171">For instructions on how to enable it, see [Configure a Report Server for E-Mail Delivery (SSRS Configuration Manager)](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [E-mail Settings - Configuration Manager &#40;SSRS Native Mode&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="9dc51-172">Соединение между сервером отчетов и локальным сервером или перенаправителем SMTP определяется следующими параметрами конфигурации:</span><span class="sxs-lookup"><span data-stu-id="9dc51-172">The connection between the report server and a local SMTP server or forwarder is determined by the following configuration settings:</span></span>  
  
-   <span data-ttu-id="9dc51-173">`SendUsing` получает значение **1**.</span><span class="sxs-lookup"><span data-stu-id="9dc51-173">`SendUsing` is set to **1**.</span></span>  
  
-   <span data-ttu-id="9dc51-174">В качестве значения**SMTPServerPickupDirectory** указана папка на локальном жестком диске.</span><span class="sxs-lookup"><span data-stu-id="9dc51-174">**SMTPServerPickupDirectory** is set to a folder on the local drive.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9dc51-175">Убедитесь, что параметр не задан, `SMTPServer` Если используется локальный SMTP-сервер.</span><span class="sxs-lookup"><span data-stu-id="9dc51-175">Be sure that you do not set `SMTPServer` if you are using a local SMTP server.</span></span>  
  
-   <span data-ttu-id="9dc51-176">`From`задает значение, отображаемое в строке **от:** сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9dc51-176">`From` sets the value that appears in the **From:** line of an e-mail message.</span></span> <span data-ttu-id="9dc51-177">Это значение обязательно.</span><span class="sxs-lookup"><span data-stu-id="9dc51-177">This value is required.</span></span>  
  
 
  
##  <a name="to-configure-report-server-e-mail-using-the-reporting-services-configuration-manager"></a><a name="bkmk_use_configuration_manager"></a><span data-ttu-id="9dc51-178">Настройка электронной почты сервера отчетов с помощью диспетчер конфигурации служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9dc51-178">To configure report server e-mail using the Reporting Services Configuration Manager</span></span>  
  
1.  <span data-ttu-id="9dc51-179">Убедитесь, что у службы Windows сервера отчетов есть разрешения `Send As` на SMTP-сервере.</span><span class="sxs-lookup"><span data-stu-id="9dc51-179">Verify that the Report Server Windows service has `Send As` permissions on the SMTP server.</span></span>  
  
2.  <span data-ttu-id="9dc51-180">Запустите диспетчер конфигурации служб Reporting Services и подключитесь к экземпляру сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9dc51-180">Start the Reporting Services Configuration Manager and connect to the report server instance.</span></span>  
  
3.  <span data-ttu-id="9dc51-181">На странице «Настройки электронной почты» введите имя SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="9dc51-181">On the Email Settings page, enter the name of the SMTP server.</span></span> <span data-ttu-id="9dc51-182">Это значение может быть IP-адресом, UNC-именем компьютера в корпоративной сети или полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="9dc51-182">This value can be an IP address, a UNC name of a computer on your corporate intranet, or a fully qualified domain name.</span></span>  
  
4.  <span data-ttu-id="9dc51-183">В поле **Адрес отправителя**введите имя учетной записи, имеющей разрешение на отправку электронной почты с SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="9dc51-183">In **Sender Address**, enter the name an account that has permission to send e-mail from the SMTP server.</span></span>  
  
5.  <span data-ttu-id="9dc51-184">Щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="9dc51-184">Click **Apply**.</span></span>  
  

  
##  <a name="to-configure-a-remote-smtp-service-for-the-report-server"></a><a name="bkmk_confiugre_remote_SMTP"></a><span data-ttu-id="9dc51-185">Настройка удаленной службы SMTP для сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="9dc51-185">To configure a remote SMTP Service for the report server</span></span>  
  
1.  <span data-ttu-id="9dc51-186">Убедитесь, что у службы Windows сервера отчетов есть разрешения `Send As` на SMTP-сервере.</span><span class="sxs-lookup"><span data-stu-id="9dc51-186">Verify that the Report Server Windows service has `Send As` permissions on the SMTP server.</span></span>  
  
2.  <span data-ttu-id="9dc51-187">Откройте файл RSReportServer.config в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="9dc51-187">Open the RSReportServer.config file in a text editor.</span></span>  
  
3.  <span data-ttu-id="9dc51-188">Убедитесь, что `UrlRoot` для параметра <> задан URL-адрес сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9dc51-188">Verify that <`UrlRoot`> is set to the report server URL address.</span></span> <span data-ttu-id="9dc51-189">Это значение устанавливается при настройке сервера отчетов так, что оно должно быть уже заполнено.</span><span class="sxs-lookup"><span data-stu-id="9dc51-189">This value is set when you configure the report server and it should be filled in already.</span></span> <span data-ttu-id="9dc51-190">Если оно не установлено, введите URL-адрес сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9dc51-190">If it is not set, type the report server URL address.</span></span>  
  
4.  <span data-ttu-id="9dc51-191">В разделе Доставка найдите <`ReportServerEmail`>.</span><span class="sxs-lookup"><span data-stu-id="9dc51-191">In the Delivery section, find <`ReportServerEmail`>.</span></span>  
  
5.  <span data-ttu-id="9dc51-192">В <`SMTPServer`> введите имя SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="9dc51-192">In <`SMTPServer`>, type the name of the SMTP server.</span></span> <span data-ttu-id="9dc51-193">Это значение может быть IP-адресом, UNC-именем компьютера в корпоративной сети или полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="9dc51-193">This value can be an IP address, a UNC name of a computer on your corporate intranet, or a fully qualified domain name.</span></span>  
  
6.  <span data-ttu-id="9dc51-194">Убедитесь, что `SendUsing` для параметра <> задано значение 2.</span><span class="sxs-lookup"><span data-stu-id="9dc51-194">Verify that <`SendUsing`> is set to 2.</span></span> <span data-ttu-id="9dc51-195">Если задано другое значение, сервер отчетов не настроен для использования удаленной службы SMTP.</span><span class="sxs-lookup"><span data-stu-id="9dc51-195">If it is set another value, the report server is not configured to use a remote SMTP service.</span></span>  
  
7.  <span data-ttu-id="9dc51-196">В <`From`> введите имя учетной записи, имеющей разрешение на отправку электронной почты с SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="9dc51-196">In <`From`>, type the name an account that has permission to send e-mail from the SMTP server.</span></span>  
  
8.  <span data-ttu-id="9dc51-197">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="9dc51-197">Save the file.</span></span>  
  
     <span data-ttu-id="9dc51-198">Сервер отчетов автоматически будет использовать новые настройки; нет необходимости перезапускать службу.</span><span class="sxs-lookup"><span data-stu-id="9dc51-198">The report server will use the new settings automatically; you do not need to restart the service.</span></span> <span data-ttu-id="9dc51-199">Можно указать дополнительные настройки SMTP для последующей конфигурации использования SMTP-сервера для доставки электронной почты на сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="9dc51-199">You can specify additional SMTP settings to further configure how the SMTP server is used for report server e-mail delivery.</span></span> <span data-ttu-id="9dc51-200">Дополнительные сведения см. в статье [Configurэлектронной документации поg a Report Server for E-Mail Delivery](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) и [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Onlэлектронной документации поe.</span><span class="sxs-lookup"><span data-stu-id="9dc51-200">For more information, see [Configuring a Report Server for E-Mail Delivery](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  

  
##  <a name="to-configure-a-local-smtp-service-for-the-report-server"></a><a name="bkmk_confiugre_local_SMTP"></a><span data-ttu-id="9dc51-201">Настройка локальной службы SMTP для сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="9dc51-201">To configure a local SMTP Service for the report server</span></span>  
  
1.  <span data-ttu-id="9dc51-202">На панели управления выберите **Установка и удаление программ**.</span><span class="sxs-lookup"><span data-stu-id="9dc51-202">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="9dc51-203">Выберите пункт **Установка компонентов Windows** , чтобы запустить мастер компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="9dc51-203">Click **Add/Remove Windows Components** to start the Windows Component Wizard.</span></span>  
  
3.  <span data-ttu-id="9dc51-204">Выберите пункт **Сервер приложений** и нажмите кнопку **Подробности**.</span><span class="sxs-lookup"><span data-stu-id="9dc51-204">Select **Application Server** and click **Details**.</span></span>  
  
4.  <span data-ttu-id="9dc51-205">Выберите пункт **службы IIS** и нажмите кнопку **Подробности**.</span><span class="sxs-lookup"><span data-stu-id="9dc51-205">Select **Internet Information Services (IIS)** and click **Details**.</span></span>  
  
5.  <span data-ttu-id="9dc51-206">Установите флажок **Служба SMTP** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9dc51-206">Select the **SMTP Service** checkbox and click **OK**.</span></span>  
  
6.  <span data-ttu-id="9dc51-207">В мастере компонентов Windows нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9dc51-207">On the Windows Component Wizard, click **Next**.</span></span> <span data-ttu-id="9dc51-208">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9dc51-208">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="9dc51-209">Убедитесь в том, что служба запущена, в консоли **Службы** .</span><span class="sxs-lookup"><span data-stu-id="9dc51-209">Verify that the service is running in the **Services** console.</span></span>  
  
8.  <span data-ttu-id="9dc51-210">Откройте файл **RSReportServer.config** в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="9dc51-210">Open the **RSReportServer.config** file in a text editor.</span></span>  
  
9. <span data-ttu-id="9dc51-211">Убедитесь, что параметр `<UrlRoot>` настроен на URL-адрес сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9dc51-211">Verify that `<UrlRoot>` is set to the report server URL address.</span></span> <span data-ttu-id="9dc51-212">Это значение устанавливается при настройке сервера отчетов так, что оно должно быть уже заполнено.</span><span class="sxs-lookup"><span data-stu-id="9dc51-212">This value is set when you configure the report server and it should be filled in already.</span></span> <span data-ttu-id="9dc51-213">Если оно не установлено, введите URL-адрес сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9dc51-213">If it is not set, type the report server URL address.</span></span>  
  
10. <span data-ttu-id="9dc51-214">В разделе Delivery найдите параметр `<ReportServerEmail>.`</span><span class="sxs-lookup"><span data-stu-id="9dc51-214">In the Delivery section, find `<ReportServerEmail>.`</span></span>  
  
11. <span data-ttu-id="9dc51-215">В `<SMTPServer>`удалите значения параметра, но не удаляйте теги.</span><span class="sxs-lookup"><span data-stu-id="9dc51-215">In `<SMTPServer>`, clear any values for this setting, but do not delete the tags.</span></span>  
  
12. <span data-ttu-id="9dc51-216">Присвойте параметру `<SendUsing>` значение 1.</span><span class="sxs-lookup"><span data-stu-id="9dc51-216">Set `<SendUsing>` to 1.</span></span> <span data-ttu-id="9dc51-217">Если задано другое значение, сервер отчетов не настроен для использования локальной службы SMTP.</span><span class="sxs-lookup"><span data-stu-id="9dc51-217">If it is set another value, the report server is not configured to use a local SMTP service.</span></span>  
  
13. <span data-ttu-id="9dc51-218">В качестве значения `<SMTPServerPickupDirectory>` задайте папку на локальном жестком диске.</span><span class="sxs-lookup"><span data-stu-id="9dc51-218">Set `<SMTPServerPickupDirectory>` to a folder on the local drive.</span></span>  
  
14. <span data-ttu-id="9dc51-219">В качестве значения параметра `<From>` укажите учетную запись, имеющей разрешение на отправку электронной почты с SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="9dc51-219">Set `<From>` to an account that has permission to send e-mail from the SMTP server.</span></span>  
  
15. <span data-ttu-id="9dc51-220">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="9dc51-220">Save the file.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="9dc51-221">См. также:</span><span class="sxs-lookup"><span data-stu-id="9dc51-221">See Also</span></span>  
 [<span data-ttu-id="9dc51-222">Использование диспетчера конфигурации служб Reporting Services (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="9dc51-222">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
