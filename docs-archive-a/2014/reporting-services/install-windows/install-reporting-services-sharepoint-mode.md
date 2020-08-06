---
title: Reporting Services установки в режиме интеграции с SharePoint (SharePoint 2010 и SharePoint 2013) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- default configuration [Reporting Services]
- installing Reporting Services, SharePoint integrated mode
- installation options [Reporting Services]
ms.assetid: ac6cba68-2665-4a39-8fa3-cb7d7e6723c0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c27b6f9fbeebcc896b1a6097cb51e8d2e15924bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655549"
---
# <a name="reporting-services-sharepoint-mode-installation-sharepoint-2010-and-sharepoint-2013"></a><span data-ttu-id="80bd5-102">Установка служб Reporting Services в режиме интеграции с SharePoint (SharePoint 2010 и SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="80bd5-102">Reporting Services SharePoint Mode Installation (SharePoint 2010 and SharePoint 2013)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="80bd5-103">в режиме интеграции с SharePoint — это набор серверных компонентов, обеспечивающих создание и доставку отчетов, основанных на [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)] продуктах SharePoint и.</span><span class="sxs-lookup"><span data-stu-id="80bd5-103">in SharePoint mode is a collection of server components that provide report generation and delivery, based on [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[msCoName](../../includes/msconame-md.md)] SharePoint products.</span></span>  
  
 <span data-ttu-id="80bd5-104">Выполнение служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в режиме SharePoint обеспечивает функции [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] и предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="80bd5-104">Running [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode provides the [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] and data alerting features.</span></span> <span data-ttu-id="80bd5-105">Дополнительные сведения о функциях в режиме интеграции с SharePoint см. в разделе "Поддержка функций и различия в поведении по режиму сервера" раздела [Reporting Services сервер отчетов](../reporting-services-report-server.md) .</span><span class="sxs-lookup"><span data-stu-id="80bd5-105">For more information regarding features in SharePoint mode, see the section "Feature Support and Behavior Differences by Server Mode" in [Reporting Services Report Server](../reporting-services-report-server.md)</span></span>  
  
 <span data-ttu-id="80bd5-106">Для служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в режиме SharePoint требуются две базовые установки.</span><span class="sxs-lookup"><span data-stu-id="80bd5-106">There are two fundamental installations needed for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode:</span></span>  
  
|<span data-ttu-id="80bd5-107">Установка</span><span class="sxs-lookup"><span data-stu-id="80bd5-107">Installation</span></span>|<span data-ttu-id="80bd5-108">Описание</span><span class="sxs-lookup"><span data-stu-id="80bd5-108">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="80bd5-109">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Надстройка для продуктов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="80bd5-109">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span>|<span data-ttu-id="80bd5-110">Эта надстройка устанавливает страницы пользовательского интерфейса и компоненты служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] на сервер клиентского веб-интерфейса SharePoint.</span><span class="sxs-lookup"><span data-stu-id="80bd5-110">The add-in installs the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] user interface (UI) pages and features on a SharePoint web front-end server.</span></span> <span data-ttu-id="80bd5-111">В компоненты пользовательского интерфейса входят [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], страницы в центре администрирования SharePoint, страницы компонентов, используемые в библиотеках документов SharePoint, и страницы предупреждений об изменении данных служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80bd5-111">The UI features include [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], administration pages in SharePoint Central Administration, feature pages used within SharePoint document libraries, and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Data Alerting pages.</span></span>|  
|<span data-ttu-id="80bd5-112">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Сервер отчетов, установленный в режиме интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="80bd5-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server installed in SharePoint Mode</span></span>|<span data-ttu-id="80bd5-113">Сервер отчетов обеспечивает обработку и подготовку данных и отчетов, а также обработку подписок и предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="80bd5-113">The report server handles the data and report processing and rendering as well subscription and Data Alert processing.</span></span> <span data-ttu-id="80bd5-114">Сервер отчетов в режиме SharePoint формируется и устанавливается в виде общей службы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="80bd5-114">The SharePoint mode report server is architected and installed as a SharePoint Shared Service.</span></span>|  
  
 <span data-ttu-id="80bd5-115">Для установки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] используется установочный носитель [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80bd5-115">To install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], use the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation media.</span></span>  
  
 <span data-ttu-id="80bd5-116">Инструкции по расширенным сценариям развертывания см. в разделе [Контрольный список развертывания: Reporting Services, Power View и PowerPivot для SharePoint](../../sql-server/install/deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) и [Контрольный список развертывания: Установите Reporting Services в существующую ферму SharePoint](../../sql-server/install/deployment-checklist-install-reporting-services-existing-sharepoint-farm.md).</span><span class="sxs-lookup"><span data-stu-id="80bd5-116">For instructions on advanced deployment scenarios, see [Deployment Checklist: Reporting Services, Power View, and PowerPivot for SharePoint](../../sql-server/install/deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) and [Deployment Checklist: Install Reporting Services into an Existing SharePoint Farm](../../sql-server/install/deployment-checklist-install-reporting-services-existing-sharepoint-farm.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80bd5-117">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="80bd5-117">In This Section</span></span>  
 [<span data-ttu-id="80bd5-118">Поддерживаемые сочетания SharePoint и Reporting Services Server и надстроек &#40;SQL Server 2014&#41;</span><span class="sxs-lookup"><span data-stu-id="80bd5-118">Supported Combinations of SharePoint and Reporting Services Server and Add-in &#40;SQL Server 2014&#41;</span></span>](supported-combinations-of-sharepoint-and-reporting-services-server.md)  
  
 [<span data-ttu-id="80bd5-119">Установка служб Reporting Services в режиме SharePoint для SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="80bd5-119">Install Reporting Services SharePoint Mode for SharePoint 2013</span></span>](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md)  
  
 [<span data-ttu-id="80bd5-120">Установка Reporting Services режима SharePoint для SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="80bd5-120">Install Reporting Services SharePoint Mode for SharePoint 2010</span></span>](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md)  
  
 [<span data-ttu-id="80bd5-121">Установка или удаление надстройки Reporting Services для SharePoint &#40;SharePoint 2010 и SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="80bd5-121">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
 [<span data-ttu-id="80bd5-122">Где найти надстройку службы Reporting Services для продуктов SharePoint</span><span class="sxs-lookup"><span data-stu-id="80bd5-122">Where to find the Reporting Services add-in for SharePoint Products</span></span>](where-to-find-the-reporting-services-add-in-for-sharepoint-products.md)  
  
 [<span data-ttu-id="80bd5-123">Добавление дополнительного сервера отчетов в ферму (горизонтально масштабируемые службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="80bd5-123">Add an Additional Report Server to a Farm &#40;SSRS Scale-out&#41;</span></span>](add-an-additional-report-server-to-a-farm-ssrs-scale-out.md)  
  
 [<span data-ttu-id="80bd5-124">Добавление дополнительного клиентского веб-интерфейса служб Reporting Services в ферме</span><span class="sxs-lookup"><span data-stu-id="80bd5-124">Add an Additional Reporting Services Web Front-end to a Farm</span></span>](add-an-additional-reporting-services-web-front-end-to-a-farm.md)  
  
 [<span data-ttu-id="80bd5-125">Настройка электронной почты для приложения служб Reporting Services (SharePoint 2010 и SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="80bd5-125">Configure E-mail for a Reporting Services Service Application &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](configure-e-mail-for-a-reporting-services-service-application.md)  
  
 [<span data-ttu-id="80bd5-126">Подготовка подписок и предупреждений для приложений служб SSRS</span><span class="sxs-lookup"><span data-stu-id="80bd5-126">Provision Subscriptions and Alerts for SSRS Service Applications</span></span>](provision-subscriptions-and-alerts-for-ssrs-service-applications.md)  
  
 [<span data-ttu-id="80bd5-127">Служба Claims to Windows Token Service &#40;C2WTS&#41; и Reporting Services</span><span class="sxs-lookup"><span data-stu-id="80bd5-127">Claims to Windows Token Service &#40;C2WTS&#41; and Reporting Services</span></span>](../../sql-server/install/claims-to-windows-token-service-c2wts-and-reporting-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="80bd5-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="80bd5-128">See Also</span></span>  
 <span data-ttu-id="80bd5-129">[Архитектура и рабочий процесс предупреждений об изменении данных](../reporting-services-data-alerts.md#AlertingWF) </span><span class="sxs-lookup"><span data-stu-id="80bd5-129">[Data Alerts Architecture and Workflow](../reporting-services-data-alerts.md#AlertingWF) </span></span>  
 [<span data-ttu-id="80bd5-130">Диспетчер предупреждений данных для оповещения администраторов</span><span class="sxs-lookup"><span data-stu-id="80bd5-130">Data Alert Manager for Alerting Administrators</span></span>](../data-alert-manager-for-alerting-administrators.md)  
  
  
