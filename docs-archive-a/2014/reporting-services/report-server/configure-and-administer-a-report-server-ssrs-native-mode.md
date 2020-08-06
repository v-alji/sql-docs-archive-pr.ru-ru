---
title: Настройка и администрирование сервера отчетов (службы SSRS в собственном режиме) | Документы Майкрософт
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, components
- deploying [Reporting Services], component options
- report servers [Reporting Services], component options
- configuration options [Reporting Services]
- administering Reporting Services
- components [Reporting Services], configuring
- configuring servers [Reporting Services]
ms.assetid: cfec012b-56f1-4346-9814-247acf22351c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5164fd2f9170cb092a45394f64f06d7622253f2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665816"
---
# <a name="configure-and-administer-a-report-server-ssrs-native-mode"></a><span data-ttu-id="2ebc0-102">Настройка и администрирование сервера отчетов (службы Reporting Services в собственном режиме)</span><span class="sxs-lookup"><span data-stu-id="2ebc0-102">Configure and Administer a Report Server (SSRS Native Mode)</span></span>
  <span data-ttu-id="2ebc0-103">В этом разделе приводится сводка подходов, которые можно использовать для настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ebc0-103">This topic summarizes the approaches that you can use to configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="2ebc0-104">Он также включает список разделов, в которых объясняется, как настраивать конкретные компоненты, функции и возможности сервера.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-104">It also includes a list of topics that explain how to configure specific components, features, or server capabilities.</span></span> <span data-ttu-id="2ebc0-105">Для настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]можно.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-105">To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can:</span></span>  
  
-   <span data-ttu-id="2ebc0-106">Используйте диспетчер конфигурации служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-106">Use the Reporting Services Configuration Manager.</span></span> <span data-ttu-id="2ebc0-107">Многие подразделы этого раздела содержат сведения о том, как настраивать конкретные возможности с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-107">Many of the topics in this section contain information about how to configure specific features through this tool.</span></span>  
  
-   <span data-ttu-id="2ebc0-108">Используйте среду [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , чтобы включить папку "Мои отчеты", включить журналы трассировки и установить значения по умолчанию для уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-108">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to customize server properties, enable My Reports, enable trace logs, and set site-wide defaults.</span></span> <span data-ttu-id="2ebc0-109">Дополнительные сведения о настройках сайта см. в разделе [Сервер отчетов служб Reporting Services (основной режим)](reporting-services-report-server-native-mode.md) для среды Management Studio.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-109">For more information about site settings, see [Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) for Management Studio.</span></span> <span data-ttu-id="2ebc0-110">Обратите внимание, что можно создать и запустить скрипт, который программно задает свойства сервера.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-110">Note that you can create and run script that sets server properties programmatically.</span></span> <span data-ttu-id="2ebc0-111">Дополнительные сведения см. в статьях [Написание скриптов для задач развертывания и администрирования](../tools/script-deployment-and-administrative-tasks.md) и [Системные свойства сервера отчетов](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2ebc0-111">For more information, see [Script Deployment and Administrative Tasks](../tools/script-deployment-and-administrative-tasks.md) and [Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md).</span></span>  
  
-   <span data-ttu-id="2ebc0-112">Использовать диспетчер отчетов, чтобы предоставить разрешения на доступ к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-112">Use Report Manager to grant permissions to access the report server.</span></span> <span data-ttu-id="2ebc0-113">Разрешения предоставляются с помощью назначения ролей для каждой учетной записи пользователя или группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-113">Permissions are conveyed through role assignments that you define for each user or group account.</span></span> <span data-ttu-id="2ebc0-114">Дополнительные сведения см. в статье [Роли и разрешения (службы Reporting Services)](../security/roles-and-permissions-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="2ebc0-114">For more information, see [Roles and Permissions &#40;Reporting Services&#41;](../security/roles-and-permissions-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="2ebc0-115">Дополнительно можно изменить файлы конфигурации для изменения настроек приложений.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-115">Optionally, modify configuration files to change application settings.</span></span> <span data-ttu-id="2ebc0-116">Дополнительные сведения о каждом файле и рекомендации по их изменению см. в разделе [Reporting Services Configuration Files](reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="2ebc0-116">For more information about each file and guidelines for modifying them, see [Reporting Services Configuration Files](reporting-services-configuration-files.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ebc0-117">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2ebc0-117">In This Section</span></span>  
 [<span data-ttu-id="2ebc0-118">Настройка URL-адресов сервера отчетов (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="2ebc0-118">Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
 <span data-ttu-id="2ebc0-119">Описывает способ определения URL-адресов, используемых для доступа к серверу отчетов и диспетчеру отчетов.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-119">Describes how to define the URLs used to access the report server and Report Manager.</span></span>  
  
 [<span data-ttu-id="2ebc0-120">Настройка учетной записи службы сервера отчетов (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="2ebc0-120">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="2ebc0-121">Содержит рекомендации и описывает шаги по изменению учетной записи службы и пароля.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-121">Provides recommendations and steps on how to modify service account and password.</span></span>  
  
 [<span data-ttu-id="2ebc0-122">Создание базы данных сервера отчетов (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="2ebc0-122">Create a Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)  
 <span data-ttu-id="2ebc0-123">Описывает, как создать базу данных сервера отчетов, необходимую для хранения метаданных и объектов сервера.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-123">Describes how to create a report server database, required for storing server metadata and objects.</span></span>  
  
 [<span data-ttu-id="2ebc0-124">Настройка подключения к базе данных сервера отчетов (диспетчер конфигураций служб Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="2ebc0-124">Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md)  
 <span data-ttu-id="2ebc0-125">Описывает, как изменить строку, используемую сервером отчетов для подключения к базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-125">Describes how to modify the connection string used by the report server to connect to the report server database.</span></span>  
  
 [<span data-ttu-id="2ebc0-126">Настройка сервера отчетов для доставки электронной почты &#40;Configuration Manager SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2ebc0-126">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="2ebc0-127">Описывает, как настроить сервер отчетов для поддержки рассылки отчетов по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-127">Describes how to configure a report server to support e-mail report distribution.</span></span>  
  
 [<span data-ttu-id="2ebc0-128">Настройка учетной записи автоматического выполнения (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="2ebc0-128">Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="2ebc0-129">Описывает, как настроить пользовательскую учетную запись для обработки отчетов в автоматическом режиме.</span><span class="sxs-lookup"><span data-stu-id="2ebc0-129">Describes how to configure a user account to process reports in unattended mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ebc0-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="2ebc0-130">See Also</span></span>  
 <span data-ttu-id="2ebc0-131">[Настройка доступа к построитель отчетов](configure-report-builder-access.md) </span><span class="sxs-lookup"><span data-stu-id="2ebc0-131">[Configure Report Builder Access](configure-report-builder-access.md) </span></span>  
 <span data-ttu-id="2ebc0-132">[Файлы конфигурации служб Reporting Services](reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="2ebc0-132">[Reporting Services Configuration Files](reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="2ebc0-133">[Использование диспетчера конфигурации служб Reporting Services (собственный режим)](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="2ebc0-133">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="2ebc0-134">[Reporting Services безопасность и защита](../security/reporting-services-security-and-protection.md) </span><span class="sxs-lookup"><span data-stu-id="2ebc0-134">[Reporting Services Security and Protection](../security/reporting-services-security-and-protection.md) </span></span>  
 [<span data-ttu-id="2ebc0-135">Сервер отчетов служб Reporting Services (основной режим)</span><span class="sxs-lookup"><span data-stu-id="2ebc0-135">Reporting Services Report Server &#40;Native Mode&#41;</span></span>](reporting-services-report-server-native-mode.md)  
  
  
