---
title: Мастер преобразования Integration Services проектов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.migrationwizard.f1
ms.assetid: a192b094-4d0f-4c21-b911-460ec844a49f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c47dc8ed1d0485a62128be732cc34de1dca35740
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664391"
---
# <a name="integration-services-project-conversion-wizard"></a><span data-ttu-id="6d492-102">Мастером преобразования проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="6d492-102">Integration Services Project Conversion Wizard</span></span>
  <span data-ttu-id="6d492-103">**Мастер преобразования проекта служб Integration Services** преобразует проект в модель развертывания проекта.</span><span class="sxs-lookup"><span data-stu-id="6d492-103">The **Integration Services Project Conversion Wizard** converts a project to the project deployment model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d492-104">Если проект содержит один или более источников данных, то они будут удалены после завершения преобразования проекта.</span><span class="sxs-lookup"><span data-stu-id="6d492-104">If the project contains one or more datasources, the datasources are removed when the project conversion is completed.</span></span> <span data-ttu-id="6d492-105">Для создания соединения с источником данных, который может совместно использоваться пакетами в проекте, добавьте диспетчер соединений на уровне проекта.</span><span class="sxs-lookup"><span data-stu-id="6d492-105">To create a connection to a data source that can be shared by the packages in the project, add a connection manager at the project level.</span></span> <span data-ttu-id="6d492-106">Дополнительные сведения см. в статье [Добавление, удаление или совместное использование диспетчера соединений в пакете](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="6d492-106">For more information, see [Add, Delete, or Share a Connection Manager in a Package](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md).</span></span>  
  
 <span data-ttu-id="6d492-107">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="6d492-107">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="6d492-108">Открытие мастера преобразования проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="6d492-108">Open the Integration Services Project Conversion Wizard</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="6d492-109">Задание параметров на странице «Поиск пакетов»</span><span class="sxs-lookup"><span data-stu-id="6d492-109">Set Options on the Locate Packages Page</span></span>](#locate)  
  
-   [<span data-ttu-id="6d492-110">Задание параметров на странице «Выбор пакетов»</span><span class="sxs-lookup"><span data-stu-id="6d492-110">Set Options on the Select Packages Page</span></span>](#selectPackages)  
  
-   [<span data-ttu-id="6d492-111">Задание параметров на странице «Выбор назначения»</span><span class="sxs-lookup"><span data-stu-id="6d492-111">Set Options on the Select Destination Page</span></span>](#destination)  
  
-   [<span data-ttu-id="6d492-112">Задание параметров на странице «Задание свойств проекта»</span><span class="sxs-lookup"><span data-stu-id="6d492-112">Set Options on the Specify Project Properties Page</span></span>](#projectProperties)  
  
-   [<span data-ttu-id="6d492-113">Задание параметров на странице «Обновление задачи выполнения пакета»</span><span class="sxs-lookup"><span data-stu-id="6d492-113">Set Options on the Update Execute Package Task Page</span></span>](#executePackage)  
  
-   [<span data-ttu-id="6d492-114">Задание параметров на странице «Выбор конфигурации»</span><span class="sxs-lookup"><span data-stu-id="6d492-114">Set Options on the Select Configurations Page</span></span>](#configurations)  
  
-   [<span data-ttu-id="6d492-115">Задание параметров на странице «Создание параметров»</span><span class="sxs-lookup"><span data-stu-id="6d492-115">Set Options on the Create Parameters Page</span></span>](#createParameters)  
  
-   [<span data-ttu-id="6d492-116">Задание параметров на странице «Настройка параметров»</span><span class="sxs-lookup"><span data-stu-id="6d492-116">Set Options on the Configure Parameters Page</span></span>](#configureParameters)  
  
-   [<span data-ttu-id="6d492-117">Задание параметров на странице «Просмотр»</span><span class="sxs-lookup"><span data-stu-id="6d492-117">Set the Options on the Review page</span></span>](#review)  
  
-   [<span data-ttu-id="6d492-118">Задание параметров на странице «Выполнение преобразования»</span><span class="sxs-lookup"><span data-stu-id="6d492-118">Set the Options on the Perform Conversion</span></span>](#conversion)  
  
##  <a name="open-the-integration-services-project-conversion-wizard"></a><a name="open_dialog"></a><span data-ttu-id="6d492-119">Открытие мастера преобразования Integration Services проектов</span><span class="sxs-lookup"><span data-stu-id="6d492-119">Open the Integration Services Project Conversion Wizard</span></span>  
 <span data-ttu-id="6d492-120">Выполните одно из следующих действий, чтобы открыть мастер **преобразования проекта служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="6d492-120">Do one of the following to open the **Integration Services Project Conversion** Wizard.</span></span>  
  
-   <span data-ttu-id="6d492-121">Откройте проект в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], а затем в обозревателе решений щелкните его правой кнопкой мыши и выберите команду **Преобразовать в модель развертывания проекта**.</span><span class="sxs-lookup"><span data-stu-id="6d492-121">Open the project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], and then in Solution Explorer, right-click the project and click **Convert to Project Deployment Model**.</span></span>  
  
-   <span data-ttu-id="6d492-122">В среде [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]в обозревателе объектов щелкните правой кнопкой мыши узел **Проекты** и выберите команду **Импорт пакетов**.</span><span class="sxs-lookup"><span data-stu-id="6d492-122">From Object Explorer in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], right-click the **Projects** node and select **Import Packages**.</span></span>  
  
 <span data-ttu-id="6d492-123">В зависимости от того, запускается ли **Мастер преобразования проекта служб Integration Services** из [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] или из среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], он выполняет разные задачи по преобразованию.</span><span class="sxs-lookup"><span data-stu-id="6d492-123">Depending on whether you run the **Integration Services Project Conversion Wizard** from [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] or from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], the wizard performs different conversion tasks.</span></span> <span data-ttu-id="6d492-124">Дополнительные сведения см. в разделе [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="6d492-124">For more information, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
##  <a name="set-options-on-the-locate-packages-page"></a><a name="locate"></a><span data-ttu-id="6d492-125">Задание параметров на странице «Размещение пакетов»</span><span class="sxs-lookup"><span data-stu-id="6d492-125">Set Options on the Locate Packages Page</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d492-126">Страница **Поиск пакетов** доступна только при запуске мастера из среды [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d492-126">The **Locate Packages** page is available only when you run the wizard from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="6d492-127">При выборе пункта **Файловая система** в раскрывающемся списке **Источник** на странице отображается следующий параметр.</span><span class="sxs-lookup"><span data-stu-id="6d492-127">The following option displays on the page when you select **File system** in the **Source** drop-down list.</span></span> <span data-ttu-id="6d492-128">Выберите этот параметр, если пакет размещен в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="6d492-128">Select this option when the package is resides in the file system.</span></span>  
  
 <span data-ttu-id="6d492-129">**Папка**</span><span class="sxs-lookup"><span data-stu-id="6d492-129">**Folder**</span></span>  
 <span data-ttu-id="6d492-130">Введите путь к пакету или перейдите к пакету, нажав кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="6d492-130">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="6d492-131">При выборе пункта **Хранилище пакетов служб SSIS** в раскрывающемся списке **Источник** на странице отображаются следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="6d492-131">The following options display on the page when you select **SSIS Package Store** in the **Source** drop-down list.</span></span> <span data-ttu-id="6d492-132">Дополнительные сведения о хранилище пакетов см. в разделе [Управление пакетами (службы SSIS)](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="6d492-132">For more information about the package store, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span>  
  
 <span data-ttu-id="6d492-133">**Server**</span><span class="sxs-lookup"><span data-stu-id="6d492-133">**Server**</span></span>  
 <span data-ttu-id="6d492-134">Введите имя сервера или выберите сервер.</span><span class="sxs-lookup"><span data-stu-id="6d492-134">Type the server name or select the server.</span></span>  
  
 <span data-ttu-id="6d492-135">**Папка**</span><span class="sxs-lookup"><span data-stu-id="6d492-135">**Folder**</span></span>  
 <span data-ttu-id="6d492-136">Введите путь к пакету или перейдите к пакету, нажав кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="6d492-136">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="6d492-137">При выборе пункта **Microsoft SQL Server** в раскрывающемся списке **Источник** на странице отображаются следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="6d492-137">The following options display on the page when you select **Microsoft SQL Server** in the **Source** drop-down list.</span></span> <span data-ttu-id="6d492-138">Выберите этот параметр, если пакет находится в Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d492-138">Select this option when the package resides in Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6d492-139">**Server**</span><span class="sxs-lookup"><span data-stu-id="6d492-139">**Server**</span></span>  
 <span data-ttu-id="6d492-140">Введите имя сервера или выберите сервер.</span><span class="sxs-lookup"><span data-stu-id="6d492-140">Type the server name or select the server.</span></span>  
  
 <span data-ttu-id="6d492-141">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="6d492-141">**Use Windows authentication**</span></span>  
 <span data-ttu-id="6d492-142">Режим проверки подлинности Microsoft Windows позволяет подключаться с учетной записью пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="6d492-142">Microsoft Windows Authentication mode allows a user to connect through a Windows user account.</span></span> <span data-ttu-id="6d492-143">При использовании проверки подлинности Windows не требуется ввод имени пользователя или пароля.</span><span class="sxs-lookup"><span data-stu-id="6d492-143">If you use Windows Authentication, you do not need to provide a user name or password.</span></span>  
  
 <span data-ttu-id="6d492-144">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="6d492-144">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="6d492-145">При соединении пользователя с указанным именем и паролем из ненадежных соединений [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] выполняет проверку подлинности подключения посредством проверки настройки учетной записи входа [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и проверки совпадения указанного пароля с ранее сохраненным.</span><span class="sxs-lookup"><span data-stu-id="6d492-145">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authenticates the connection by checking to see if a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="6d492-146">Если в службе [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] не задана учетная запись входа, проверка подлинности завершается ошибкой, о которой пользователь получит сообщение.</span><span class="sxs-lookup"><span data-stu-id="6d492-146">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
 <span data-ttu-id="6d492-147">**User name**</span><span class="sxs-lookup"><span data-stu-id="6d492-147">**User name**</span></span>  
 <span data-ttu-id="6d492-148">При использовании проверки подлинности SQL Server укажите имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="6d492-148">Specify a user name when you are using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="6d492-149">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="6d492-149">**Password**</span></span>  
 <span data-ttu-id="6d492-150">Укажите пароль, если используется проверка подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6d492-150">Provide the password when you are using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="6d492-151">**Папка**</span><span class="sxs-lookup"><span data-stu-id="6d492-151">**Folder**</span></span>  
 <span data-ttu-id="6d492-152">Введите путь к пакету или перейдите к пакету, нажав кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="6d492-152">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
##  <a name="set-options-on-the-select-packages-page"></a><a name="selectPackages"></a><span data-ttu-id="6d492-153">Задание параметров на странице «Выбор пакетов»</span><span class="sxs-lookup"><span data-stu-id="6d492-153">Set Options on the Select Packages Page</span></span>  
 <span data-ttu-id="6d492-154">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="6d492-154">**Package Name**</span></span>  
 <span data-ttu-id="6d492-155">Выводит список файлов пакета.</span><span class="sxs-lookup"><span data-stu-id="6d492-155">Lists the package file.</span></span>  
  
 <span data-ttu-id="6d492-156">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="6d492-156">**Status**</span></span>  
 <span data-ttu-id="6d492-157">Указывает, готов ли пакет к преобразованию в модель развертывания проекта.</span><span class="sxs-lookup"><span data-stu-id="6d492-157">Indicates whether a package is ready to convert to the project deployment model.</span></span>  
  
 <span data-ttu-id="6d492-158">**Message**</span><span class="sxs-lookup"><span data-stu-id="6d492-158">**Message**</span></span>  
 <span data-ttu-id="6d492-159">Отображает сообщение, связанное с пакетом.</span><span class="sxs-lookup"><span data-stu-id="6d492-159">Displays a message associated with the package.</span></span>  
  
 <span data-ttu-id="6d492-160">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="6d492-160">**Password**</span></span>  
 <span data-ttu-id="6d492-161">Отображает пароль, связанный с пакетом.</span><span class="sxs-lookup"><span data-stu-id="6d492-161">Displays a password associated with the package.</span></span> <span data-ttu-id="6d492-162">Текст пароля скрыт.</span><span class="sxs-lookup"><span data-stu-id="6d492-162">The password text is hidden.</span></span>  
  
 <span data-ttu-id="6d492-163">**Применить к выбранным объектам**</span><span class="sxs-lookup"><span data-stu-id="6d492-163">**Apply to selection**</span></span>  
 <span data-ttu-id="6d492-164">Нажмите эту кнопку для установки пароля в текстовом поле **Пароль** для выбранного пакета или пакетов.</span><span class="sxs-lookup"><span data-stu-id="6d492-164">Click to apply the password in the **Password** text box, to the selected package or packages.</span></span>  
  
 <span data-ttu-id="6d492-165">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="6d492-165">**Refresh**</span></span>  
 <span data-ttu-id="6d492-166">Обновляет список пакетов.</span><span class="sxs-lookup"><span data-stu-id="6d492-166">Refreshes the list of packages.</span></span>  
  
##  <a name="set-options-on-the-select-destination-page"></a><a name="destination"></a><span data-ttu-id="6d492-167">Задание параметров на странице «Выбор назначения»</span><span class="sxs-lookup"><span data-stu-id="6d492-167">Set Options on the Select Destination Page</span></span>  
 <span data-ttu-id="6d492-168">На этой странице укажите имя и путь к новому файлу развертывания проекта (ISPAC) или выберите существующий файл.</span><span class="sxs-lookup"><span data-stu-id="6d492-168">On this page, specify the name and path for a new project deployment file (.ispac) or select an existing file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d492-169">Страница **Выбор назначения** доступна только при запуске мастера из среды [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d492-169">The **Select Destination** page is available only when you run the wizard from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="6d492-170">**Путь для создаваемых файлов**</span><span class="sxs-lookup"><span data-stu-id="6d492-170">**Output path**</span></span>  
 <span data-ttu-id="6d492-171">Введите путь к файлу развертывания или перейдите к файлу, нажав кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="6d492-171">Type the path for the deployment file or navigate to the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="6d492-172">**Имя проекта**</span><span class="sxs-lookup"><span data-stu-id="6d492-172">**Project name**</span></span>  
 <span data-ttu-id="6d492-173">Введите имя проекта.</span><span class="sxs-lookup"><span data-stu-id="6d492-173">Type the project name.</span></span>  
  
 <span data-ttu-id="6d492-174">**Уровень защиты**</span><span class="sxs-lookup"><span data-stu-id="6d492-174">**Protection level**</span></span>  
 <span data-ttu-id="6d492-175">Выберите уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="6d492-175">Select the protection level.</span></span> <span data-ttu-id="6d492-176">Дополнительные сведения см. в разделе [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="6d492-176">For more information, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
 <span data-ttu-id="6d492-177">**Описание проекта**</span><span class="sxs-lookup"><span data-stu-id="6d492-177">**Project description**</span></span>  
 <span data-ttu-id="6d492-178">Введите необязательное описание для проекта.</span><span class="sxs-lookup"><span data-stu-id="6d492-178">Type an optional description for the project.</span></span>  
  
##  <a name="set-options-on-the-specify-project-properties-page"></a><a name="projectProperties"></a><span data-ttu-id="6d492-179">Задание параметров на странице «Задание свойств проекта»</span><span class="sxs-lookup"><span data-stu-id="6d492-179">Set Options on the Specify Project Properties Page</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d492-180">Страница **Задание свойств проекта** доступна только при запуске мастера из среды [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d492-180">The **Specify Project Properties** page is available only when you run the wizard from [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="6d492-181">**Имя проекта**</span><span class="sxs-lookup"><span data-stu-id="6d492-181">**Project name**</span></span>  
 <span data-ttu-id="6d492-182">Выводит список имен проекта.</span><span class="sxs-lookup"><span data-stu-id="6d492-182">Lists the project name.</span></span>  
  
 <span data-ttu-id="6d492-183">**Уровень защиты**</span><span class="sxs-lookup"><span data-stu-id="6d492-183">**Protection level**</span></span>  
 <span data-ttu-id="6d492-184">Выбор уровня защиты для пакетов, содержащихся в проекте.</span><span class="sxs-lookup"><span data-stu-id="6d492-184">Select a protection level for the packages contained in the project.</span></span> <span data-ttu-id="6d492-185">Дополнительные сведения об уровнях защиты см. в разделе [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="6d492-185">For more information about protection levels, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
 <span data-ttu-id="6d492-186">**Описание проекта**</span><span class="sxs-lookup"><span data-stu-id="6d492-186">**Project description**</span></span>  
 <span data-ttu-id="6d492-187">Введите необязательное описание проекта.</span><span class="sxs-lookup"><span data-stu-id="6d492-187">Type an optional project description.</span></span>  
  
##  <a name="set-options-on-the-update-execute-package-task-page"></a><a name="executePackage"></a><span data-ttu-id="6d492-188">Задание параметров на странице «Обновление задачи выполнения пакета»</span><span class="sxs-lookup"><span data-stu-id="6d492-188">Set Options on the Update Execute Package Task Page</span></span>  
 <span data-ttu-id="6d492-189">Обновление задачи «Выполнение пакета» содержится в пакетах для использования ссылки на основе проектов.</span><span class="sxs-lookup"><span data-stu-id="6d492-189">Update Execute Package Tasks contain in the packages, to use a project-based reference.</span></span> <span data-ttu-id="6d492-190">Дополнительные сведения см. в разделе [Execute Package Task Editor](../../2014/integration-services/execute-package-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="6d492-190">For more information, see [Execute Package Task Editor](../../2014/integration-services/execute-package-task-editor.md).</span></span>  
  
 <span data-ttu-id="6d492-191">**Родительский пакет**</span><span class="sxs-lookup"><span data-stu-id="6d492-191">**Parent Package**</span></span>  
 <span data-ttu-id="6d492-192">Выводит список имен пакета, который выполняет дочерний пакет с помощью задачи «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="6d492-192">Lists the name of the package that executes the child package using the Execute Package task.</span></span>  
  
 <span data-ttu-id="6d492-193">**Имя задачи**</span><span class="sxs-lookup"><span data-stu-id="6d492-193">**Task name**</span></span>  
 <span data-ttu-id="6d492-194">Выводит список имен задачи «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="6d492-194">Lists the name of the Execute Package task.</span></span>  
  
 <span data-ttu-id="6d492-195">**Исходная ссылка**</span><span class="sxs-lookup"><span data-stu-id="6d492-195">**Original reference**</span></span>  
 <span data-ttu-id="6d492-196">Отображает текущий путь к дочернему пакету.</span><span class="sxs-lookup"><span data-stu-id="6d492-196">Lists the current path of the child package.</span></span>  
  
 <span data-ttu-id="6d492-197">**Назначение ссылки**</span><span class="sxs-lookup"><span data-stu-id="6d492-197">**Assign reference**</span></span>  
 <span data-ttu-id="6d492-198">Выбор дочернего пакета, хранящегося в этом проекте.</span><span class="sxs-lookup"><span data-stu-id="6d492-198">Select a child package stored in the project.</span></span>  
  
##  <a name="set-options-on-the-select-configurations-page"></a><a name="configurations"></a><span data-ttu-id="6d492-199">Задание параметров на странице «Выбор конфигураций»</span><span class="sxs-lookup"><span data-stu-id="6d492-199">Set Options on the Select Configurations Page</span></span>  
 <span data-ttu-id="6d492-200">Выберите конфигурации пакетов, которые требуется заменить параметрами.</span><span class="sxs-lookup"><span data-stu-id="6d492-200">Select the package configurations that you want to replace with parameters.</span></span>  
  
 <span data-ttu-id="6d492-201">**Пакет**</span><span class="sxs-lookup"><span data-stu-id="6d492-201">**Package**</span></span>  
 <span data-ttu-id="6d492-202">Выводит список файлов пакета.</span><span class="sxs-lookup"><span data-stu-id="6d492-202">Lists the package file.</span></span>  
  
 <span data-ttu-id="6d492-203">**Тип**</span><span class="sxs-lookup"><span data-stu-id="6d492-203">**Type**</span></span>  
 <span data-ttu-id="6d492-204">Выводит список типов конфигурации, например XML-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6d492-204">Lists the type of configuration, such as an XML configuration file.</span></span>  
  
 <span data-ttu-id="6d492-205">**Строка конфигурации**</span><span class="sxs-lookup"><span data-stu-id="6d492-205">**Configuration String**</span></span>  
 <span data-ttu-id="6d492-206">Отображает путь к файлу конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6d492-206">Lists the path of the configuration file.</span></span>  
  
 <span data-ttu-id="6d492-207">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="6d492-207">**Status**</span></span>  
 <span data-ttu-id="6d492-208">Отображает сообщение о состоянии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6d492-208">Displays a status message for the configuration.</span></span> <span data-ttu-id="6d492-209">Щелкните это сообщение для просмотра его содержимого.</span><span class="sxs-lookup"><span data-stu-id="6d492-209">Click the message to view the entire message text.</span></span>  
  
 <span data-ttu-id="6d492-210">**Добавление конфигураций**</span><span class="sxs-lookup"><span data-stu-id="6d492-210">**Add Configurations**</span></span>  
 <span data-ttu-id="6d492-211">Добавление конфигурации пакета, содержащейся в других проектах, в список доступных конфигураций, которые необходимо заменить параметрами.</span><span class="sxs-lookup"><span data-stu-id="6d492-211">Add package configurations contained in other projects to the list of available configurations that you want to replace with parameters.</span></span> <span data-ttu-id="6d492-212">Вы можете выбрать конфигурации, которые хранятся в файловой системе или в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6d492-212">You can select configurations stored in a file system or stored in SQL Server.</span></span>  
  
 <span data-ttu-id="6d492-213">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="6d492-213">**Refresh**</span></span>  
 <span data-ttu-id="6d492-214">Нажмите эту кнопку для обновления списка конфигураций.</span><span class="sxs-lookup"><span data-stu-id="6d492-214">Click to refresh the list of configurations.</span></span>  
  
 <span data-ttu-id="6d492-215">**Удаление конфигураций из всех пакетов после преобразования**</span><span class="sxs-lookup"><span data-stu-id="6d492-215">**Remove configurations from all packages after conversion**</span></span>  
 <span data-ttu-id="6d492-216">Рекомендуется удалить все конфигурации из проекта, выбрав этот параметр.</span><span class="sxs-lookup"><span data-stu-id="6d492-216">It is recommended that you remove all configurations from the project by selecting this option.</span></span>  
  
 <span data-ttu-id="6d492-217">Если не выбрать этот параметр, будут удалены только те конфигурации, которые требуется заменить параметрами.</span><span class="sxs-lookup"><span data-stu-id="6d492-217">If you don't select this option, only the configurations that you selected to replace with parameters are removed.</span></span>  
  
##  <a name="set-options-on-the-create-parameters-page"></a><a name="createParameters"></a><span data-ttu-id="6d492-218">Задание параметров на странице «Создание параметров»</span><span class="sxs-lookup"><span data-stu-id="6d492-218">Set Options on the Create Parameters Page</span></span>  
 <span data-ttu-id="6d492-219">Выбор имени параметра и области каждого свойства конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6d492-219">Select the parameter name and scope for each configuration property.</span></span>  
  
 <span data-ttu-id="6d492-220">**Пакет**</span><span class="sxs-lookup"><span data-stu-id="6d492-220">**Package**</span></span>  
 <span data-ttu-id="6d492-221">Выводит список файлов пакета.</span><span class="sxs-lookup"><span data-stu-id="6d492-221">Lists the package file.</span></span>  
  
 <span data-ttu-id="6d492-222">**Имя параметра**</span><span class="sxs-lookup"><span data-stu-id="6d492-222">**Parameter Name**</span></span>  
 <span data-ttu-id="6d492-223">Выводит список имен параметра.</span><span class="sxs-lookup"><span data-stu-id="6d492-223">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="6d492-224">**Область**</span><span class="sxs-lookup"><span data-stu-id="6d492-224">**Scope**</span></span>  
 <span data-ttu-id="6d492-225">Выбор области параметра, пакета или проекта.</span><span class="sxs-lookup"><span data-stu-id="6d492-225">Select the scope of the parameter, either package or project.</span></span>  
  
##  <a name="set-options-on-the-configure-parameters-page"></a><a name="configureParameters"></a><span data-ttu-id="6d492-226">Задание параметров на странице «Настройка параметров»</span><span class="sxs-lookup"><span data-stu-id="6d492-226">Set Options on the Configure Parameters Page</span></span>  
 <span data-ttu-id="6d492-227">**имя**;</span><span class="sxs-lookup"><span data-stu-id="6d492-227">**Name**</span></span>  
 <span data-ttu-id="6d492-228">Выводит список имен параметра.</span><span class="sxs-lookup"><span data-stu-id="6d492-228">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="6d492-229">**Область**</span><span class="sxs-lookup"><span data-stu-id="6d492-229">**Scope**</span></span>  
 <span data-ttu-id="6d492-230">Отображает область действия параметров.</span><span class="sxs-lookup"><span data-stu-id="6d492-230">Lists the scope of the parameter.</span></span>  
  
 <span data-ttu-id="6d492-231">**Значение**</span><span class="sxs-lookup"><span data-stu-id="6d492-231">**Value**</span></span>  
 <span data-ttu-id="6d492-232">Выводит список значений параметра.</span><span class="sxs-lookup"><span data-stu-id="6d492-232">Lists the parameter value.</span></span>  
  
 <span data-ttu-id="6d492-233">Для настройки свойства параметра нажмите кнопку с многоточием рядом с полем значения.</span><span class="sxs-lookup"><span data-stu-id="6d492-233">Click the ellipsis button next to the value field to configure the parameter properties.</span></span>  
  
 <span data-ttu-id="6d492-234">В диалоговом окне **Задание сведений о параметре** вы можете изменить значение параметра.</span><span class="sxs-lookup"><span data-stu-id="6d492-234">In the **Set Parameter Details** dialog box, you can edit the parameter value.</span></span> <span data-ttu-id="6d492-235">Вы можете также указать, необходимо ли при запуске пакета указывать значение параметра.</span><span class="sxs-lookup"><span data-stu-id="6d492-235">You can also specify whether the parameter value must be provided when you run the package.</span></span>  
  
 <span data-ttu-id="6d492-236">Изменить значение вы можете на странице **Параметры** диалогового окна **Настройка** в среде [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], нажав кнопку обзора рядом с параметром.</span><span class="sxs-lookup"><span data-stu-id="6d492-236">You can modify value in the **Parameters** page of the **Configure** dialog box in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], by clicking the browse button next to the parameter.</span></span> <span data-ttu-id="6d492-237">Отобразится диалоговое окно **Задание значения параметра** .</span><span class="sxs-lookup"><span data-stu-id="6d492-237">The **Set Parameter Value** dialog box appears.</span></span>  
  
 <span data-ttu-id="6d492-238">В диалоговом окне **Задание сведений о параметре** перечислены также типы данных значения параметра и его начальное значение.</span><span class="sxs-lookup"><span data-stu-id="6d492-238">The **Set Parameter Details** dialog box also lists the data type of the parameter value and the origin of the parameter.</span></span>  
  
##  <a name="set-the-options-on-the-review-page"></a><a name="review"></a><span data-ttu-id="6d492-239">Задание параметров на странице «Проверка»</span><span class="sxs-lookup"><span data-stu-id="6d492-239">Set the Options on the Review page</span></span>  
 <span data-ttu-id="6d492-240">Подтвердить параметры, которые выбраны для преобразования проекта, можно на странице **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="6d492-240">Use the **Review** page to confirm the options that you've selected for the conversion of the project.</span></span>  
  
 <span data-ttu-id="6d492-241">**Назад**</span><span class="sxs-lookup"><span data-stu-id="6d492-241">**Previous**</span></span>  
 <span data-ttu-id="6d492-242">Нажмите эту кнопку для изменения параметра.</span><span class="sxs-lookup"><span data-stu-id="6d492-242">Click to change an option.</span></span>  
  
 <span data-ttu-id="6d492-243">**Преобразовать**</span><span class="sxs-lookup"><span data-stu-id="6d492-243">**Convert**</span></span>  
 <span data-ttu-id="6d492-244">Нажмите эту кнопу для преобразования проекта в модель развертывания проекта.</span><span class="sxs-lookup"><span data-stu-id="6d492-244">Click to convert the project to the project deployment model.</span></span>  
  
##  <a name="set-the-options-on-the-perform-conversion"></a><a name="conversion"></a><span data-ttu-id="6d492-245">Задание параметров для выполнения преобразования</span><span class="sxs-lookup"><span data-stu-id="6d492-245">Set the Options on the Perform Conversion</span></span>  
 <span data-ttu-id="6d492-246">На странице «Выполнение преобразования» отображается состояние преобразования проекта.</span><span class="sxs-lookup"><span data-stu-id="6d492-246">The Perform Conversion page shows status of the project conversion.</span></span>  
  
 <span data-ttu-id="6d492-247">**Действие**</span><span class="sxs-lookup"><span data-stu-id="6d492-247">**Action**</span></span>  
 <span data-ttu-id="6d492-248">Выводит список заданных шагов преобразования.</span><span class="sxs-lookup"><span data-stu-id="6d492-248">Lists a specific conversion step.</span></span>  
  
 <span data-ttu-id="6d492-249">**Результат**</span><span class="sxs-lookup"><span data-stu-id="6d492-249">**Result**</span></span>  
 <span data-ttu-id="6d492-250">Отображает состояние каждого шага преобразования.</span><span class="sxs-lookup"><span data-stu-id="6d492-250">Lists the status of each conversion step.</span></span> <span data-ttu-id="6d492-251">Щелкните сообщение о состоянии для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="6d492-251">Click the status message for more information.</span></span>  
  
 <span data-ttu-id="6d492-252">Преобразование проекта не сохраняется до тех пор, пока проект сохранен в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d492-252">The project conversion is not saved until the project is saved in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="6d492-253">**Сохранить отчет**</span><span class="sxs-lookup"><span data-stu-id="6d492-253">**Save report**</span></span>  
 <span data-ttu-id="6d492-254">Нажмите эту кнопку, чтобы сохранить сводку по преобразованию проекта в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="6d492-254">Click to save a summary of the project conversion in an .xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d492-255">См. также:</span><span class="sxs-lookup"><span data-stu-id="6d492-255">See Also</span></span>  
 [<span data-ttu-id="6d492-256">Развертывание проектов на сервере служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="6d492-256">Deploy Projects to Integration Services Server</span></span>](../../2014/integration-services/deploy-projects-to-integration-services-server.md)  
  
  
