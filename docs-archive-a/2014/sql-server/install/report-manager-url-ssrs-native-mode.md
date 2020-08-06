---
title: URL-адрес диспетчер отчетов (собственный режим служб SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.rsconfigtool.reportmanagervirtualdirectory.f1
ms.assetid: 45768952-23a6-45a5-b541-e7bf192b4a78
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ec43c91bb2d24bb96cc6541d93311ce6dd234ed4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665777"
---
# <a name="report-manager-url-ssrs-native-mode"></a><span data-ttu-id="eb248-102">URL-адрес диспетчера отчетов (службы Reporting Services в собственном режиме)</span><span class="sxs-lookup"><span data-stu-id="eb248-102">Report Manager URL (SSRS Native Mode)</span></span>
  <span data-ttu-id="eb248-103">Настроить или изменить URL-адрес для доступа к диспетчеру отчетов можно на странице «URL-адрес диспетчера отчетов».</span><span class="sxs-lookup"><span data-stu-id="eb248-103">Use the Report Manager URL page to configure or modify the URL used to access Report Manager.</span></span> <span data-ttu-id="eb248-104">По умолчанию на этой странице наследуется префикс, IP-адрес и порт, соответствующие URL-адресу веб-службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="eb248-104">By default, the Report Manager URL inherits the prefix, IP address, and port of the Report Server Web service URL.</span></span> <span data-ttu-id="eb248-105">Это связано с тем, что диспетчер отчетов предоставляет клиентский доступ к веб-службе, которая запускается под управлением той же службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="eb248-105">This is because Report Manager provides front-end access to the Web service that runs within the same Report Server service.</span></span> <span data-ttu-id="eb248-106">Если нужно изолировать приложения друг от друга и пользоваться диспетчером отчетов для доступа к веб-службе сервера отчетов на другом компьютере, то в файле RSReportServer.config укажите для диспетчера отчетов другой экземпляр.</span><span class="sxs-lookup"><span data-stu-id="eb248-106">If you are isolating the service applications and using Report Manager to access a Report Server Web service on a different computer, you must edit RSReportServer.config file to point Report Manager to a different instance.</span></span> <span data-ttu-id="eb248-107">Дополнительные сведения о настройке подключения диспетчер отчетов к удаленному серверу отчетов см. в разделе [диспетчер конфигурации служб Reporting Services &#40;в основном режиме&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="eb248-107">For more information about configuring a Report Manager connection to a remote report server, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
 [!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="eb248-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим.</span><span class="sxs-lookup"><span data-stu-id="eb248-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
 <span data-ttu-id="eb248-109">Если настройка сервера отчетов выполняется для работы в режиме интеграции с SharePoint, то создавать URL-адрес диспетчера отчетов не нужно.</span><span class="sxs-lookup"><span data-stu-id="eb248-109">If you are configuring the report server to run in SharePoint integrated mode, do not create a Report Manager URL.</span></span> <span data-ttu-id="eb248-110">Диспетчер отчетов не поддерживается на сервере отчетов, работающем в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="eb248-110">Report Manager is not supported on a report server that runs in SharePoint integrated mode.</span></span> <span data-ttu-id="eb248-111">Если для диспетчера отчетов URL-адрес уже существует, то после настройки конфигурации сервера отчетов для работы в режиме интеграции с SharePoint он становится недоступен.</span><span class="sxs-lookup"><span data-stu-id="eb248-111">If a URL already exists for Report Manager, it will become unavailable after you configure the report server to run in SharePoint integrated mode.</span></span>  
  
 <span data-ttu-id="eb248-112">Чтобы открыть эту страницу, запустите диспетчер конфигурации служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и выберите на панели навигации пункт **URL-адрес диспетчера отчетов** .</span><span class="sxs-lookup"><span data-stu-id="eb248-112">To open this page, start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager and click **Report Manager URL** in the navigation pane.</span></span> <span data-ttu-id="eb248-113">Дополнительные сведения о запуске Configuration Manager см. в разделе [диспетчер конфигурации служб Reporting Services &#40;основном режиме&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="eb248-113">For more information about how to start the Configuration Manager, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb248-114">Если диспетчер отчетов не включен, настройка параметров на этой странице будет невозможна.</span><span class="sxs-lookup"><span data-stu-id="eb248-114">If Report Manager is not enabled, you cannot set options on this page.</span></span> <span data-ttu-id="eb248-115">Дополнительные сведения о включении диспетчер отчетов см. в разделе [диспетчер конфигурации служб Reporting Services &#40;основном режиме&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="eb248-115">For more information about enabling Report Manager, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="eb248-116">Варианты</span><span class="sxs-lookup"><span data-stu-id="eb248-116">Options</span></span>  
 <span data-ttu-id="eb248-117">**Виртуальный каталог**</span><span class="sxs-lookup"><span data-stu-id="eb248-117">**Virtual Directory**</span></span>  
 <span data-ttu-id="eb248-118">Указывает имя виртуального каталога диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="eb248-118">Specifies the virtual directory name for Report Manager.</span></span> <span data-ttu-id="eb248-119">Каждый экземпляр диспетчера отчетов на одном компьютере может иметь только одно имя виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="eb248-119">You can only have one virtual directory name for each Report Manager instance on the same computer.</span></span>  
  
 <span data-ttu-id="eb248-120">**URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="eb248-120">**URLs**</span></span>  
 <span data-ttu-id="eb248-121">Отображает URL-адрес, определенный для текущего экземпляра диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="eb248-121">Displays the URL defined for the current Report Manager instance.</span></span>  
  
 <span data-ttu-id="eb248-122">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="eb248-122">**Advanced**</span></span>  
 <span data-ttu-id="eb248-123">Введите дополнительный URL-адрес для текущего экземпляра диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="eb248-123">Add an additional URL for the current Report Manager instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb248-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="eb248-124">See Also</span></span>  
 <span data-ttu-id="eb248-125">[Настройка URL-адреса &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="eb248-125">[Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="eb248-126">[URL-адреса в файлах конфигурации &#40;Configuration Manager SSRS&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="eb248-126">[URLs in Configuration Files  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="eb248-127">Настройка URL-адресов сервера отчетов (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="eb248-127">Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
  
  
