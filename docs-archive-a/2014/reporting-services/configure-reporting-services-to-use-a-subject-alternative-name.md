---
title: Настройка Reporting Services для использования альтернативного имени субъекта | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ce458f9f-4b4f-4a58-aa75-9a90dda1e622
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0312d2d1fff8f854eb2ffb8d0dad2563212ee23b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739539"
---
# <a name="configure-reporting-services-to-use-a-subject-alternative-name"></a><span data-ttu-id="0098e-102">Настройка Reporting Services для использования альтернативного имени субъекта</span><span class="sxs-lookup"><span data-stu-id="0098e-102">Configure Reporting Services to Use a Subject Alternative Name</span></span>
  <span data-ttu-id="0098e-103">В этом разделе объясняется, как настроить [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS), чтобы использовать альтернативное имя субъекта (SAN), изменив файл rsreportserver.config и используя средство Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="0098e-103">This topic explains how to configure [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS) to use a subject alternative name (SAN) by modifying the rsreportserver.config file and using the Netsh.exe tool.</span></span>

||
|-|
|<span data-ttu-id="0098e-104">**[!INCLUDE[applies](../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="0098e-104">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Native mode</span></span>|

 <span data-ttu-id="0098e-105">Инструкции применяются к URL-адресу службы отчетов, а также URL-адресу веб-службы.</span><span class="sxs-lookup"><span data-stu-id="0098e-105">The instructions apply to the Reporting Service URL as well as a Web Service URL.</span></span>

 <span data-ttu-id="0098e-106">Чтобы использовать SAN, SSL-сертификат должен быть зарегистрирован на сервере, подписан и иметь закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="0098e-106">To use a SAN, the SSL certificate must be registered on the server, signed, and have the private key.</span></span> <span data-ttu-id="0098e-107">Самозаверяющий сертификат использовать невозможно.</span><span class="sxs-lookup"><span data-stu-id="0098e-107">You cannot use a self-signed certificate</span></span>

 <span data-ttu-id="0098e-108">URL-адреса в [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] можно настроить для использования SSL-сертификата.</span><span class="sxs-lookup"><span data-stu-id="0098e-108">URLs in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] can be configured to use an SSL certificate.</span></span> <span data-ttu-id="0098e-109">Обычно сертификат имеет только имя субъекта, которое позволяет ему использовать только один URL-адрес для сеанса SSL.</span><span class="sxs-lookup"><span data-stu-id="0098e-109">A certificate normally has just a subject name, which allows only one URL for an SSL (Secure Sockets Layer) session.</span></span> <span data-ttu-id="0098e-110">SAN — это дополнительное поле в сертификате, которое позволяет службе SSL прослушивать и быть допустимой для многих URL-адресов, а также совместно использовать порт SSL с другими приложениями.</span><span class="sxs-lookup"><span data-stu-id="0098e-110">The SAN is an additional field in the certificate that allows an SSL service to listen and be valid for many URLs, and to share the SSL port with other applications.</span></span> <span data-ttu-id="0098e-111">SAN выглядит следующим образом: www.s2.com.</span><span class="sxs-lookup"><span data-stu-id="0098e-111">The SAN looks something like the following: www.s2.com.</span></span>

 <span data-ttu-id="0098e-112">Дополнительные сведения о параметрах SSL см. в статье [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Настройка соединений SSL для сервера отчетов, работающего в собственном режиме [](security/configure-ssl-connections-on-a-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="0098e-112">For more information about SSL settings for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Configure SSL Connections on a Native Mode Report Server](security/configure-ssl-connections-on-a-native-mode-report-server.md).</span></span>

### <a name="configure-ssrs-to-use-a-subject-alternative-name-for-web-service-url"></a><span data-ttu-id="0098e-113">Настройка SSRS для использования альтернативного имени субъекта для URL-адреса веб-службы</span><span class="sxs-lookup"><span data-stu-id="0098e-113">Configure SSRS to use a subject alternative name for Web Service URL</span></span>

1.  <span data-ttu-id="0098e-114">Запустите диспетчер конфигурации служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="0098e-114">Start Reporting Services Configuration Manager.</span></span>

     <span data-ttu-id="0098e-115">Дополнительные сведения см. в разделе [Использование диспетчера конфигурации служб Reporting Services (собственный режим)](../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="0098e-115">For more information, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>

2.  <span data-ttu-id="0098e-116">Выберите на странице **URL-адрес веб-службы** порт SSL и SSL-сертификат.</span><span class="sxs-lookup"><span data-stu-id="0098e-116">On the **Web Service URL** page, select an SSL port and SSL Certificate.</span></span>

     <span data-ttu-id="0098e-117">![Диспетчер конфигурации служб Reporting Services](media/reportingservices-configurationmanager.png "Диспетчер конфигурации служб Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="0098e-117">![Reporting Services Configuration Manager](media/reportingservices-configurationmanager.png "Reporting Services Configuration Manager")</span></span>

     <span data-ttu-id="0098e-118">Диспетчер конфигурации зарегистрирует SSL-сертификат для порта.</span><span class="sxs-lookup"><span data-stu-id="0098e-118">The configuration manager registers the SSL certificate for the port.</span></span>

3.  <span data-ttu-id="0098e-119">Откройте файл rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="0098e-119">Open the rsreportserver.config file.</span></span>

     <span data-ttu-id="0098e-120">Файл для служб SSRS в собственном режиме находится в следующей папке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0098e-120">For SSRS Native mode, the file is located by default in the following folder.</span></span>

    ```
    \Program Files\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer
    ```

4.  <span data-ttu-id="0098e-121">Скопируйте раздел URL-адреса для приложения веб-службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="0098e-121">Copy the URL section for the Report Server Web Service application.</span></span>

     <span data-ttu-id="0098e-122">Например, далее указан исходный раздел URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="0098e-122">For example, the following is the original URL section.</span></span>

    ```
        <URL>
         <UrlString>https://localhost:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>

    ```

     <span data-ttu-id="0098e-123">Ниже указан измененный раздел URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="0098e-123">The following is the modified URL section.</span></span>

    ```
    <URL>
         <UrlString>https://www.s1.com:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>
        <URL>
         <UrlString>https://www.s2.com:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>

    ```

5.  <span data-ttu-id="0098e-124">Сохраните файл rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="0098e-124">Save the rsreportserver.config file.</span></span>

6.  <span data-ttu-id="0098e-125">Откройте командную строку от имени администратора и запустите средство Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="0098e-125">Start a command prompt as an administrator, and run the Netsh.exe tool.</span></span>

    ```
    C:\windows\system32\netsh
    ```

7.  <span data-ttu-id="0098e-126">Переключитесь в контекст HTTP, введя следующее.</span><span class="sxs-lookup"><span data-stu-id="0098e-126">Switch to the http context by typing the following.</span></span>

    ```
    Netsh>http
    ```

8.  <span data-ttu-id="0098e-127">Отобразите существующие urlacl, введя следующее.</span><span class="sxs-lookup"><span data-stu-id="0098e-127">Show the existing urlacls by typing the following.</span></span>

    ```
    Netsh http>show urlacl
    ```

     <span data-ttu-id="0098e-128">Появится запись, аналогичная следующей.</span><span class="sxs-lookup"><span data-stu-id="0098e-128">An entry such as the following appears.</span></span>

    ```
    Reserved URL            : https:// www.s1.com:443/ReportServer/
        User: NT SERVICE\ReportServer
            Listen: Yes
            Delegate: No
            SDDL: D:(A;;GX;;;S-1-5-80-1234567890-123456789-123456789-123456789-1234567890)
    ```

     <span data-ttu-id="0098e-129">urlacl — это DACL (список управления доступом на уровне пользователей) для зарезервированного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="0098e-129">An urlacl is a DACL (Discretionary Access Control List) for a reserved URL.</span></span>

9. <span data-ttu-id="0098e-130">Создайте альтернативное имя субъекта с тем же пользователем и SDDL как существующую запись, введя следующее.</span><span class="sxs-lookup"><span data-stu-id="0098e-130">Create a new entry for the subject alternative name, with the same user and SDDL as the existing entry, by typing the following.</span></span>

    ```
    netsh http>add urlacl  url=https://www.s2.com:443/ReportServer  
    user="NT Service\ReportServer" sddl=D:(A;;GX;;;S-1-5-80-1234567980-12346579-123456789-123456789-1234567890)

    ```

10. <span data-ttu-id="0098e-131">Щелкните на странице **Состояние сервера отчетов** диспетчера конфигурации Reporting Services кнопку **Остановить** , а затем нажмите **Запустить** , чтобы перезапустить сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="0098e-131">On the **Report Server Status** page of the Reporting Services Configuration Manager, Click **Stop** and then click **Start** to restart the report server.</span></span>

## <a name="see-also"></a><span data-ttu-id="0098e-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="0098e-132">See Also</span></span>
 <span data-ttu-id="0098e-133">[Файл конфигурации RSReportServer](report-server/rsreportserver-config-configuration-file.md) [Диспетчер конфигурации служб Reporting Services &#40;в собственном режиме&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md) [изменения файла конфигурации Reporting Services &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) [Настройка url-адресов сервера отчетов &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)</span><span class="sxs-lookup"><span data-stu-id="0098e-133">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) [Reporting Services Configuration Manager &#40;Native Mode&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)</span></span>


