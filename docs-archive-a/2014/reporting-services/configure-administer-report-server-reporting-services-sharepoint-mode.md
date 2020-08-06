---
title: Настройка и администрирование сервера отчетов (Reporting Services в режиме интеграции с SharePoint) | Документация Майкрософт
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 846e86d0-fbbb-426c-97f9-f179cd42b390
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ce7c1f524eec4785ddbc25d95c641d070ecbf408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739560"
---
# <a name="configuration-and-administration-of-a-report-server-reporting-services-sharepoint-mode"></a><span data-ttu-id="06276-102">Настройка и администрирование сервера отчетов (режим интеграции с SharePoint служб Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="06276-102">Configuration and Administration of a Report Server (Reporting Services SharePoint Mode)</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="06276-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] — это Серверная платформа для создания отчетов, которая предоставляет полный спектр готовых к использованию средств и служб для создания, развертывания и управления отчетами в Организации, а также функций программирования, позволяющих расширять и настраивать функции отчетов.</span><span class="sxs-lookup"><span data-stu-id="06276-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] is a server-based reporting platform that provides a full range of ready-to-use tools and services to help you create, deploy, and manage reports for your organization, as well as programming features that enable you to extend and customize your reporting functionality.</span></span> <span data-ttu-id="06276-104">Среду создания отчетов можно интегрировать с продуктами SharePoint, чтобы пользоваться всеми преимуществами среды совместной работы, которые обеспечивает сайт SharePoint.</span><span class="sxs-lookup"><span data-stu-id="06276-104">You can integrate your reporting environment with a SharePoint product to experience the benefits of using the collaborative environment provided by SharePoint sites.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="06276-105">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="06276-105">In this section</span></span>  
 <span data-ttu-id="06276-106">В следующих разделах можно ознакомиться с основными понятиями, сценариями развертывания, процедурами и прочими сведениями, относящимися к интеграции среды служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] с продуктами или технологиями SharePoint.</span><span class="sxs-lookup"><span data-stu-id="06276-106">Use the following sections to help you understand concepts, deployment scenarios, procedures, and more for integrating your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] environment with a SharePoint product or technology:</span></span>  
  
-   <span data-ttu-id="06276-107">Параметры меню в библиотеке документов SharePoint</span><span class="sxs-lookup"><span data-stu-id="06276-107">Menu options in a SharePoint document library</span></span>  
  
    -   [<span data-ttu-id="06276-108">Диспетчер предупреждений данных для пользователей SharePoint</span><span class="sxs-lookup"><span data-stu-id="06276-108">Data Alert Manager for SharePoint Users</span></span>](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md)  
  
    -   [<span data-ttu-id="06276-109">Создание подписок для серверов отчетов, работающих в режиме интеграции с SharePoint, и управление этими подписками</span><span class="sxs-lookup"><span data-stu-id="06276-109">Create and Manage Subscriptions for SharePoint Mode Report Servers</span></span>](subscriptions/create-and-manage-subscriptions-for-sharepoint-mode-report-servers.md)  
  
    -   [<span data-ttu-id="06276-110">Обновление учетных данных в источниках данных отчетов с сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="06276-110">Update Credentials in Report Data Sources from a SharePoint Site</span></span>](report-data/update-credentials-in-report-data-sources-from-a-sharepoint-site.md)  
  
    -   [<span data-ttu-id="06276-111">Управление общими наборами данных</span><span class="sxs-lookup"><span data-stu-id="06276-111">Manage Shared Datasets</span></span>](report-data/manage-shared-datasets.md)  
  
    -   [<span data-ttu-id="06276-112">Настройка параметров опубликованного отчета (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="06276-112">Set Parameters on a Published Report &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](report-design/set-parameters-on-a-published-report-sharepoint-integrated-mode.md)  
  
    -   [<span data-ttu-id="06276-113">Установка параметров обработки (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="06276-113">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
    -   [<span data-ttu-id="06276-114">Параметры обновления кэша (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="06276-114">Cache Refresh Options &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/cache-refresh-options-report-manager.md)  
  
-   [<span data-ttu-id="06276-115">Reporting Services компонентов семейства веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="06276-115">Reporting Services Site Collection Features</span></span>](../../2014/reporting-services/reporting-services-site-collection-features.md)  
  
-   [<span data-ttu-id="06276-116">Активация функций интеграции семейства веб-сайтов с сервером отчетов и Power View в SharePoint</span><span class="sxs-lookup"><span data-stu-id="06276-116">Activate the Report Server and Power View Integration Features in SharePoint</span></span>](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md)  
  
-   [<span data-ttu-id="06276-117">Страницы "Параметры сайта" и "Возможности сайта" служб Reporting Services (режим интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="06276-117">Reporting Services Site Settings and Site Features&#40;SharePoint Mode&#41;</span></span>](../../2014/reporting-services/reporting-services-site-settings-and-site-features-sharepoint-mode.md)  
  
-   [<span data-ttu-id="06276-118">активировать функции синхронизации файлов сервера отчетов в центре администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="06276-118">Activate the Report Server File Sync Feature in SharePoint Central Administration</span></span>](../../2014/reporting-services/activate-report-server-file-sync-feature-sharepoint-central-administration.md)  
  
-   [<span data-ttu-id="06276-119">Добавление типов содержимого сервера отчетов в библиотеку &#40;Reporting Services в режиме интеграции с SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="06276-119">Add Report Server Content Types to a Library &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/add-reporting-services-content-types-to-a-sharepoint-library.md)  
  
-   [<span data-ttu-id="06276-120">Локальный режим и Отчеты, созданные в подключенном режиме, в средстве просмотра отчетов (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="06276-120">Local Mode vs. Connected Mode Reports in the Report Viewer &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../../2014/reporting-services/local-vs-connected-mode-report-viewer-reporting-services-sharepoint-mode.md)  
  
-   [<span data-ttu-id="06276-121">Отправка документов в библиотеку SharePoint (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="06276-121">Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../../2014/reporting-services/upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md)  
  
-   [<span data-ttu-id="06276-122">Установка параметров обработки (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="06276-122">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
 <span data-ttu-id="06276-123">Дополнительные общие сведения о службах [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] см. в разделе [Службы Reporting Services (SSRS)](create-deploy-and-manage-mobile-and-paginated-reports.md) электронной документации по [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06276-123">For more general information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Reporting Services &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="06276-124">Дополнительные сведения о других компонентах, средствах и ресурсах [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] см. в [электронной документации по SQL Server](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="06276-124">For information about other [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components, tools, and resources, see [SQL Server Books Online](../index.yml).</span></span>  
  
  
