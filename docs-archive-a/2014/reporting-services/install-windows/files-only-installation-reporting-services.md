---
title: Установка в режиме "только файлы" (службы Reporting Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- files-only installation [Reporting Services]
- installation options [Reporting Services]
ms.assetid: bdc74a8f-046c-4aa0-bfbd-4f1711dfb9ce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ec5c595dce3e292d37117453ccbbc6d19f8b87d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732429"
---
# <a name="files-only-installation-reporting-services"></a><span data-ttu-id="19d91-102">Установка в режиме «только файлы» (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="19d91-102">Files-Only Installation (Reporting Services)</span></span>
  <span data-ttu-id="19d91-103">Режим установки*только файлы* означает установку [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , при которой программа установки создает структуру папок для программных файлов [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , копирует файлы на диск, регистрирует на локальном компьютере службу сервера отчетов, настраивает учетную запись службы, предоставляет ей разрешения на доступ к файлам и регистрирует поставщик WMI [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="19d91-103">*Files-only installation* refers to a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation where Setup creates the folder structure for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] program files, copies the files to disk, registers the Report Server service on the local computer, configures the service account, grants files permissions to the service account, and registers the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] WMI provider.</span></span>  
  
 <span data-ttu-id="19d91-104">Установка в режиме "только файлы" включает следующие компоненты служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] : службу сервера отчетов (которая включает веб-службу сервера отчетов, работающую в фоновом режиме, и диспетчер отчетов), построитель отчетов, средство настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и программы командной строки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (rsconfig.exe, rskeymgmt.exe и rs.exe).</span><span class="sxs-lookup"><span data-stu-id="19d91-104">A files-only installation includes the following [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features: Report Server service (which hosts the Report Server Web service, background processing application, and Report Manager), Report Builder, the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool, and the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] command line utilities (rsconfig.exe, rskeymgmt.exe and rs.exe).</span></span> <span data-ttu-id="19d91-105">Этот режим не затрагивает среду [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], среду [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] и другие общие компоненты, которые должны быть выбраны для установки как отдельные элементы.</span><span class="sxs-lookup"><span data-stu-id="19d91-105">It does not apply to shared features such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], which must be specified as separate items if you want to install them.</span></span>  
  
 <span data-ttu-id="19d91-106">В отличие от других режимов, в режиме «только файлы» сервер отчетов не готов к запуску сразу же после окончания установки.</span><span class="sxs-lookup"><span data-stu-id="19d91-106">In contrast with other installation modes, a report server that is installed in files-only mode is not operational when Setup is finished.</span></span> <span data-ttu-id="19d91-107">Чтобы перевести сервер отчетов в режим "в сети" с помощью [диспетчера конфигурации служб Reporting Services (собственный режим)](../../sql-server/install/reporting-services-configuration-manager-native-mode.md), необходима дополнительная настройка.</span><span class="sxs-lookup"><span data-stu-id="19d91-107">Additional configuration will be required to bring the report server online by using the [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
## <a name="when-to-select-files-only-installation-mode"></a><span data-ttu-id="19d91-108">Случаи, в которых следует выбирать режим «только файлы»</span><span class="sxs-lookup"><span data-stu-id="19d91-108">When to Select Files-Only Installation Mode</span></span>  
 <span data-ttu-id="19d91-109">Установка в режиме «только файлы» должна производиться в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="19d91-109">A files-only installation must be performed when:</span></span>  
  
-   <span data-ttu-id="19d91-110">Необходимо подключить сервер отчетов к удаленной базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="19d91-110">You want to connect the report server to a remote report server database.</span></span>  
  
-   <span data-ttu-id="19d91-111">Сервер отчетов должен быть установлен как именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="19d91-111">You want to install the report server as a named instance.</span></span>  
  
-   <span data-ttu-id="19d91-112">Существуют требования к развертыванию, включающие специальную настройку или функциональность, и необходим полный контроль над процессом настройки сервера.</span><span class="sxs-lookup"><span data-stu-id="19d91-112">You have deployment requirements that include using custom settings or functionality, and you want full control over when and how the server is configured.</span></span>  
  
-   <span data-ttu-id="19d91-113">Установка отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , включающего службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19d91-113">Installing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster that includes [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="how-to-perform-a-files-only-installation"></a><span data-ttu-id="19d91-114">Установка в режиме «только файлы»</span><span class="sxs-lookup"><span data-stu-id="19d91-114">How to Perform a Files-Only Installation</span></span>  
 <span data-ttu-id="19d91-115">Службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]по умолчанию устанавливаются в режиме «только файлы».</span><span class="sxs-lookup"><span data-stu-id="19d91-115">Files-only installation is the default for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="19d91-116">Этот режим можно указать с помощью командной строки или выбрать в мастере установки.</span><span class="sxs-lookup"><span data-stu-id="19d91-116">You can specify a files-only installation through the command line or in the Installation wizard.</span></span> <span data-ttu-id="19d91-117">Пошаговые инструкции приводятся в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="19d91-117">The following topics provide step-by-step instructions:</span></span>  
  
-   <span data-ttu-id="19d91-118">[Установите SQL Server 2014 с помощью мастера установки &#40;&#41;установки ](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md).</span><span class="sxs-lookup"><span data-stu-id="19d91-118">[Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
-   <span data-ttu-id="19d91-119">[Установите SQL Server 2014 из командной строки](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="19d91-119">[Install SQL Server 2014 from the Command Prompt](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
#### <a name="example-command-line-script"></a><span data-ttu-id="19d91-120">Пример скрипта командной строки</span><span class="sxs-lookup"><span data-stu-id="19d91-120">Example Command Line Script</span></span>  
 <span data-ttu-id="19d91-121">Для ясности в примере приведен аргумент /RSINSTALLMODE="FilesOnlyMode".</span><span class="sxs-lookup"><span data-stu-id="19d91-121">For clarity, the example includes /RSINSTALLMODE="FilesOnlyMode".</span></span> <span data-ttu-id="19d91-122">Однако, поскольку режим «только файлы» является режимом по умолчанию, с тем же результатом этот аргумент можно не указывать.</span><span class="sxs-lookup"><span data-stu-id="19d91-122">However, because files-only mode is the default, you can omit this and still get a files-only mode installation.</span></span>  
  
```  
setup /q /ACTION=install /FEATURES=RS /InstanceName=MSSQLSERVER /RSSVCACCOUNT="NT AUTHORITY\NETWORK SERVICE" /RSINSTALLMODE="FilesOnlyMode"  
```  
  
#### <a name="installation-wizard"></a><span data-ttu-id="19d91-123">Мастер установки</span><span class="sxs-lookup"><span data-stu-id="19d91-123">Installation Wizard</span></span>  
 <span data-ttu-id="19d91-124">При выборе служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] на странице выбора компонентов программа установки открывает страницу настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , позволяя указать режим установки.</span><span class="sxs-lookup"><span data-stu-id="19d91-124">When you select [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in the Feature Selection page, Setup provides a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration page that enables you to specify the installation mode.</span></span> <span data-ttu-id="19d91-125">Чтобы выбрать установку в режиме "только файлы", на странице настройки службы **выберите параметр** Установить, но не настраивать сервер отчетов [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="19d91-125">To specify a files-only installation, select **Install but do not configure the report server** on the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19d91-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="19d91-126">See Also</span></span>  
 <span data-ttu-id="19d91-127">[Проверка установки служб Reporting Services](verify-a-reporting-services-installation.md) </span><span class="sxs-lookup"><span data-stu-id="19d91-127">[Verify a Reporting Services Installation](verify-a-reporting-services-installation.md) </span></span>  
 <span data-ttu-id="19d91-128">[Настройка учетной записи службы сервера отчетов (диспетчер конфигурации служб SSRS)](configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="19d91-128">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="19d91-129">[Настройка URL-адресов сервера отчетов (диспетчер конфигурации служб SSRS)](configure-report-server-urls-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="19d91-129">[Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](configure-report-server-urls-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="19d91-130">[Настройка подключения к базе данных сервера отчетов &#40;службы SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="19d91-130">[Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="19d91-131">[Reporting Services установки в режиме интеграции с SharePoint &#40;SharePoint 2010 и SharePoint 2013&#41;](install-reporting-services-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="19d91-131">[Reporting Services SharePoint Mode Installation &#40;SharePoint 2010 and SharePoint 2013&#41;](install-reporting-services-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="19d91-132">[Установка сервера отчетов служб Reporting Services в собственном режиме](install-reporting-services-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="19d91-132">[Install Reporting Services Native Mode Report Server](install-reporting-services-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="19d91-133">Инструментальные средства служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="19d91-133">Reporting Services Tools</span></span>](../tools/reporting-services-tools.md)  
  
  
