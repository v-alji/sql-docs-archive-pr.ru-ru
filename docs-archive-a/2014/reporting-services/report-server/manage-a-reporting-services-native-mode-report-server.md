---
title: Управление сервером отчетов служб Reporting Services в собственном режиме | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- configuration options [Reporting Services]
- report servers [Reporting Services], configuring
ms.assetid: 6ca03a09-d6a8-4c93-ba12-1c99dcbfb618
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d44a9329074a20c04f878c055674ea563b297f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665796"
---
# <a name="manage-a-reporting-services-native-mode-report-server"></a><span data-ttu-id="2cab4-102">Управление сервером отчетов служб Reporting Services в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="2cab4-102">Manage a Reporting Services Native Mode Report Server</span></span>
  <span data-ttu-id="2cab4-103">Этот раздел содержит описание процедур по настройке экземпляра сервера отчетов в собственном режиме с использованием диспетчера конфигурации служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2cab4-103">This section contains procedures for configuring a native mode report server instance using the Reporting Services Configuration Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cab4-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2cab4-104">In This Section</span></span>  
 <span data-ttu-id="2cab4-105">Подразделы в этом разделе организованы по категориям, что упрощает поиск необходимых инструкций.</span><span class="sxs-lookup"><span data-stu-id="2cab4-105">The topics in this section are organized into categories so that you can more easily find the instructions you want.</span></span> <span data-ttu-id="2cab4-106">Подразделы первого раздела содержат описания основных задач по настройке конфигурации сервера отчетов, работающего в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="2cab4-106">The first section contains topics for basic configuration tasks for a native mode report server.</span></span> <span data-ttu-id="2cab4-107">Подразделы второго раздела посвящены дополнительным параметрам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2cab4-107">The second section contains advanced configuration topics.</span></span> <span data-ttu-id="2cab4-108">Подразделы третьего раздела помогут выполнить настройку конфигурации сервера отчетов для работы в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cab4-108">The third section contains topics for configuring a report server to run in SharePoint integrated mode.</span></span>  
  
### <a name="basic-configuration"></a><span data-ttu-id="2cab4-109">Основная конфигурация</span><span class="sxs-lookup"><span data-stu-id="2cab4-109">Basic Configuration</span></span>  
 [<span data-ttu-id="2cab4-110">Использование диспетчера конфигурации служб Reporting Services (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="2cab4-110">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
 <span data-ttu-id="2cab4-111">Представляет шаги запуска программы настройки служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2cab4-111">Provides steps for starting the Reporting Services Configuration tool.</span></span>  
  
 [<span data-ttu-id="2cab4-112">Настройка учетной записи службы (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="2cab4-112">Configure a Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="2cab4-113">Объясняет, как задать учетную запись и пароль службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2cab4-113">Explains how to specify account and password information for the Report Server service.</span></span>  
  
 [<span data-ttu-id="2cab4-114">Регистрация имени участника-службы для сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="2cab4-114">Register a Service Principal Name &#40;SPN&#41; for a Report Server</span></span>](register-a-service-principal-name-spn-for-a-report-server.md)  
 <span data-ttu-id="2cab4-115">Показывает, как вручную зарегистрировать имя участника-службы для сервера отчетов, который запускается от учетной записи пользователя домена в сети, где используется проверка подлинности по протоколу Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2cab4-115">Explains how to manually register an SPN for a report server that runs under a domain user account on a network that uses Kerberos authentication.</span></span>  
  
 [<span data-ttu-id="2cab4-116">Настройка URL-адреса (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="2cab4-116">Configure a URL  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-a-url-ssrs-configuration-manager.md)  
 <span data-ttu-id="2cab4-117">Описывает, как назначить один или несколько URL-адресов для получения доступа к веб-службе сервера отчетов и к диспетчеру отчетов.</span><span class="sxs-lookup"><span data-stu-id="2cab4-117">Explains how to establish one or more URLs used to access the Report Server Web service and Report Manager.</span></span>  
  
 [<span data-ttu-id="2cab4-118">Создание базы данных сервера отчетов, работающего в собственном режиме (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="2cab4-118">Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md)  
 <span data-ttu-id="2cab4-119">Представляет шаги создания базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2cab4-119">Provides steps for creating a report server database.</span></span> <span data-ttu-id="2cab4-120">Этот шаг требуется для развертывания установки служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2cab4-120">This step is required for deploying a Reporting Services installation.</span></span>  
  
### <a name="advanced-or-optional-configuration"></a><span data-ttu-id="2cab4-121">Дополнительные или необязательные параметры настройки</span><span class="sxs-lookup"><span data-stu-id="2cab4-121">Advanced or Optional Configuration</span></span>  
 [<span data-ttu-id="2cab4-122">Настройка масштабного развертывания сервера отчетов в основном режиме (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="2cab4-122">Configure a Native Mode Report Server Scale-Out Deployment &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md)  
 <span data-ttu-id="2cab4-123">Представляет шаги настройки нескольких серверов отчетов для совместного использования базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2cab4-123">Provides steps for configuring multiple report servers to share a report server database.</span></span>  
  
 [<span data-ttu-id="2cab4-124">Настройка сервера отчетов для доставки электронной почты &#40;Configuration Manager SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2cab4-124">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="2cab4-125">Содержит шаги настройки сервера отчетов для доставки по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="2cab4-125">Provides steps for configuring a report server for e-mail distribution.</span></span>  
  
 [<span data-ttu-id="2cab4-126">настроить брандмауэр для доступа к серверу отчетов</span><span class="sxs-lookup"><span data-stu-id="2cab4-126">Configure a Firewall for Report Server Access</span></span>](configure-a-firewall-for-report-server-access.md)  
 <span data-ttu-id="2cab4-127">Описывает, как открыть порты для передачи входящих запросов и ответов от сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2cab4-127">Explains how to open ports used for inbound requests and outbound responses from a report server.</span></span>  
  
 [<span data-ttu-id="2cab4-128">Настройка сервера отчетов, работающего в основном режиме, для локального администрирования (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="2cab4-128">Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;</span></span>](configure-a-native-mode-report-server-for-local-administration-ssrs.md)  
 <span data-ttu-id="2cab4-129">Описывает дополнительные шаги, которые необходимо выполнить для соединения с сервером отчетов или диспетчером отчетов с помощью http://localhost.</span><span class="sxs-lookup"><span data-stu-id="2cab4-129">Describes additional steps required to connect to Report Manager or a report server using http://localhost.</span></span>  
  
 [<span data-ttu-id="2cab4-130">настроить сервер отчетов для удаленного администрирования</span><span class="sxs-lookup"><span data-stu-id="2cab4-130">Configure a Report Server for Remote Administration</span></span>](configure-a-report-server-for-remote-administration.md)  
 <span data-ttu-id="2cab4-131">Описывает, как настроить экземпляр удаленного сервера отчетов для удаленного соединения и настройки с другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="2cab4-131">Explains how to configure a remote report server instance so that you can connect to and configure it from a different computer.</span></span>  
  
 [<span data-ttu-id="2cab4-132">Включение и отключение компонентов Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2cab4-132">Turn Reporting Services Features On or Off</span></span>](turn-reporting-services-features-on-or-off.md)  
 <span data-ttu-id="2cab4-133">Объясняет, как удалить неиспользуемые компоненты после установки служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2cab4-133">Explains how to remove unused features in a Reporting Services installation.</span></span>  
  
 [<span data-ttu-id="2cab4-134">Включение отслеживания удаленных ошибок (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="2cab4-134">Enable Remote Errors &#40;Reporting Services&#41;</span></span>](enable-remote-errors-reporting-services.md)  
 <span data-ttu-id="2cab4-135">Поясняет, как задать свойства сервера на сервере отчетов для возвращения дополнительных сведений об условиях возникновения ошибок на удаленных серверах.</span><span class="sxs-lookup"><span data-stu-id="2cab4-135">Explains how to set server properties on a report server to return additional information about error conditions that occur on remote servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cab4-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="2cab4-136">See Also</span></span>  
 <span data-ttu-id="2cab4-137">[Настройка и администрирование сервера отчетов (службы Reporting Services в собственном режиме)](configure-and-administer-a-report-server-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="2cab4-137">[Configure and Administer a Report Server &#40;SSRS Native Mode&#41;](configure-and-administer-a-report-server-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="2cab4-138">Настройка и администрирование сервера отчетов (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="2cab4-138">Configuration and Administration of a Report Server &#40;Reporting Services SharePoint Mode&#41;</span></span>](../configure-administer-report-server-reporting-services-sharepoint-mode.md)  
  
  
