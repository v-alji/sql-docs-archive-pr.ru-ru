---
title: Проблемы обновления Reporting Services (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Report Manager [Reporting Services], upgrade issues
- Reporting Services, upgrades
- upgrading Reporting Services
- report servers [Reporting Services], upgrade issues
ms.assetid: d9663f25-98d7-4508-ae3c-55a7277211bd
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 569afe735d68a724c0b4cc61ad2b7767088c2b30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668611"
---
# <a name="reporting-services-upgrade-issues-upgrade-advisor"></a><span data-ttu-id="2b0e2-102">Проблемы обновления служб Reporting Services (помощник по обновлению)</span><span class="sxs-lookup"><span data-stu-id="2b0e2-102">Reporting Services Upgrade Issues (Upgrade Advisor)</span></span>
  <span data-ttu-id="2b0e2-103">В следующих разделах описываются [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] проблемы, которые могут повлиять на обновление до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b0e2-103">The following topics describe the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] issues that might affect your upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="2b0e2-104">В следующих разделах описаны действия, позволяющие смягчить воздействие этих изменений на рабочую среду.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-104">The topics describe actions that you can take to mitigate the effect of these changes on your environment.</span></span>  
  
 <span data-ttu-id="2b0e2-105">Помощник по обновлению анализирует установленный экземпляр сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-105">Upgrade Advisor analyzes a report server installation.</span></span> <span data-ttu-id="2b0e2-106">Если установлены только клиентские компоненты (например, единственным установленным на компьютер компонентом служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] является конструктор отчетов), никаких сообщений о проблемах не появится.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-106">If only client components are installed (for example, if Report Designer is the only [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] component installed on the computer), no issues will be reported.</span></span>  
  
 <span data-ttu-id="2b0e2-107">В зависимости от конфигурации установленного экземпляра могут встретиться дополнительные проблемы, о которых помощник по обновлению не сообщает.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-107">Depending on how you configured your installation, you may encounter additional issues that are not reported by Upgrade Advisor.</span></span> <span data-ttu-id="2b0e2-108">Эти проблемы не помешают успешному обновлению служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], но могут повлиять на работу отчетов и приложений после завершения обновления.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-108">These issues do not prevent a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] upgrade from succeeding, but they may affect how reports and applications run after an upgrade is finished.</span></span> <span data-ttu-id="2b0e2-109">Дополнительные сведения о таких проблемах см. в разделе «Обратная совместимость служб Reporting Services» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b0e2-109">To learn about these issues, see "Reporting Services Backward Compatibility" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="2b0e2-110">Если невозможно использовать программу установки для обновления имеющегося экземпляра служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], можно установить новый экземпляр служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и перенести на него существующий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-110">If you cannot use Setup to upgrade a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation, you can install a new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance and migrate your existing installation to the new instance.</span></span> <span data-ttu-id="2b0e2-111">Дополнительные сведения см. в разделе "обновление и миграция Reporting Services" [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] электронной документации, [обновление и миграция Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="2b0e2-111">For more information, see "Upgrade and Migrate Reporting Services" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online, [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
 <span data-ttu-id="2b0e2-112">В следующих разделах описываются известные проблемы, о которых может сообщать помощник по обновлению, и объясняется, как изменить существующий экземпляр, чтобы обеспечить возможность обновления.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-112">The following topics describe known issues that are reported by Upgrade Advisor, and explain how you can modify your existing installation to allow an upgrade to occur.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2b0e2-113">Чтобы выполнить анализ экземпляра служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], необходимо установить советник по переходу на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-113">Upgrade Advisor must be installed on the report server to analyze an instance of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="2b0e2-114">Службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] не поддерживают удаленный анализ.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-114">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not support remote analysis.</span></span>  
>   
>  <span data-ttu-id="2b0e2-115">Дополнительные сведения см. в разделе [Установка помощника по обновлению](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="2b0e2-115">For more information, see [Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b0e2-116">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2b0e2-116">In This Section</span></span>  
  
-   [<span data-ttu-id="2b0e2-117">Клиентские сертификаты на веб-сайте сервера отчетов &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-117">Client certificates on the report server web site &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/client-certificates-on-the-report-server-web-site-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-118">На сервере отчетов обнаружены пользовательские расширения &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-118">Custom extensions were detected on the report server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/custom-extensions-were-detected-on-the-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-119">На сервере отчетов обнаружены пользовательские элементы отчета &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-119">Custom report items were detected on the report server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/custom-report-items-were-detected-on-the-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-120">Не обнаружены компоненты обратной совместимости IIS &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-120">IIS backward compatibility components were not detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/iis-backward-compatibility-components-were-not-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-121">&#40;советник по переходу обнаружено ограничение IP-адресов&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-121">IP address restriction detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/ip-address-restriction-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-122">На сайте сервера отчетов обнаружены фильтры ISAPI &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-122">ISAPI filters detected on the report server site &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/isapi-filters-detected-on-the-report-server-site-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-123">На компьютере сервера отчетов обнаружены устаревшие расширения &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-123">Obsolete extensions were detected on the report server computer &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/obsolete-extensions-were-detected-on-the-report-server-computer-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-124">База данных сервера отчетов не настроена &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-124">Report server database is not configured &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/report-server-database-is-not-configured-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-125">SQL Server 2005 &#40;советник по обновлению обнаружена группа веб-служб сервера отчетов&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-125">SQL Server 2005 Report Server Web Service group detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/sql-server-2005-report-server-web-service-group-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-126">Не указаны виртуальные каталоги &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-126">Virtual directories are unspecified &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/virtual-directories-are-unspecified-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-127">В виртуальном каталоге имеется неподдерживаемый метод проверки подлинности &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-127">Virtual directory has unsupported authentication method &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/virtual-directory-has-unsupported-authentication-method-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-128">Изменения в ограничениях ресурсов ЦП и памяти для SQL Server Standard и советника по обновлению Enterprise &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-128">Changes to CPU and memory limits for SQL Server Standard and Enterprise &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/cpu-memory-limits-changes-sql-server-standard-enterprise-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-129">&#40;советник по переходу на ферму SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-129">Domain accounts required for SharePoint farm &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/domain-accounts-required-for-sharepoint-farm-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-130">Прямой просмотр &#40;советник по переходу сервера отчетов&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-130">Direct Browsing to Report Server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/direct-browsing-to-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-131">Microsoft SharePoint 2007 установлен &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-131">Microsoft SharePoint 2007 is Installed &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/microsoft-sharepoint-2007-is-installed-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-132">Microsoft SQL Server Reporting Services общая служба SharePoint устанавливается параллельно &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-132">Microsoft SQL Server Reporting Services SharePoint Shared Service is Installed Side by Side &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/sql-server-reporting-services-sharepoint-shared-service-side-by-side-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-133">&#40;советник по переходу ядро СУБД сервера несовместим&#41;</span><span class="sxs-lookup"><span data-stu-id="2b0e2-133">Incompatible Database Engine Server Collation &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/incompatible-database-engine-server-collation-upgrade-advisor.md)  
  
-   [<span data-ttu-id="2b0e2-134">Другие проблемы обновления служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2b0e2-134">Other Reporting Services Upgrade Issues</span></span>](../../../2014/sql-server/install/other-reporting-services-upgrade-issues.md)  
  
  
