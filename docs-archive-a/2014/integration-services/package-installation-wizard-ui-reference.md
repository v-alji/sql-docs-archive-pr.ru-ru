---
title: Справочник по пользовательскому интерфейсу мастера установки пакетов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.deploymentwizard.confirminstallation.f1
- sql12.dts.deploymentwizard.deploydtspackages.f1
- sql12.dts.deploymentwizard.selectinstfolder.f1
- sql12.dts.deploymentwizard.specifytargetsqlserver.f1
- sql12.dts.deploymentwizard.welcome.f1
- sql12.dts.deploymentwizard.finish.f1
- sql12.dts.deploymentwizard.configurepackages.f1
- sql12.dts.deploymentwizard.packagevalidation.f1
helpviewer_keywords:
- Package Installer Wizard
ms.assetid: 6fca44d9-5001-4644-bcf3-c2d10a674b97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c15b423c66891e799f7f8dcd27682036dce6d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729601"
---
# <a name="package-installation-wizard-ui-reference"></a><span data-ttu-id="65d5d-102">Мастер установки пакета справочника по пользовательскому интерфейсу</span><span class="sxs-lookup"><span data-stu-id="65d5d-102">Package Installation Wizard UI Reference</span></span>
  <span data-ttu-id="65d5d-103">Используйте **Мастер установки пакета** , чтобы развернуть проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , включая пакеты и другие файлы, которые в нем содержатся, а также любые зависимости пакетов.</span><span class="sxs-lookup"><span data-stu-id="65d5d-103">Use the **Package Installation Wizard** to deploy a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, including the packages and miscellaneous files it contains and any package dependencies.</span></span>  
  
 <span data-ttu-id="65d5d-104">Прежде чем выполнять развертывание пакетов, можно создать конфигурации, затем выполнить их развертывание вместе с пакетами.</span><span class="sxs-lookup"><span data-stu-id="65d5d-104">Before you deploy packages, you can create configurations and then deploy them with the packages.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="65d5d-105">конфигурации используются для динамического обновления свойств и объектов пакетов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="65d5d-105">uses configurations to dynamically update properties of packages and package objects at run time.</span></span> <span data-ttu-id="65d5d-106">Например, строка соединения OLE DB может быть задана динамически во время выполнения с помощью конфигурации, которая сопоставляет значение и свойство, содержащее строку соединения.</span><span class="sxs-lookup"><span data-stu-id="65d5d-106">For example, the connection string of an OLE DB connection can be set dynamically at run time by providing a configuration that maps a value to the property that contains the connection string.</span></span>  
  
 <span data-ttu-id="65d5d-107">Нельзя запустить мастер установки пакета до тех пор, пока не собран проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и не создана программа развертывания.</span><span class="sxs-lookup"><span data-stu-id="65d5d-107">You cannot run the Package Installation Wizard until you build an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and create a deployment utility.</span></span> <span data-ttu-id="65d5d-108">Дополнительные сведения см. в статье [Deploy Packages by Using the Deployment Utility](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="65d5d-108">For more information, see [Deploy Packages by Using the Deployment Utility](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="65d5d-109">В следующих разделах описаны страницы мастера.</span><span class="sxs-lookup"><span data-stu-id="65d5d-109">The following sections describe pages of the wizard.</span></span>  
  
## <a name="welcome-to-the-package-installation-wizard-page"></a><span data-ttu-id="65d5d-110">Страница приветствия мастера установки пакета</span><span class="sxs-lookup"><span data-stu-id="65d5d-110">Welcome to the Package Installation Wizard Page</span></span>  
 <span data-ttu-id="65d5d-111">**Мастер установки пакета** используется для развертывания проекта служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , для которого создается программа развертывания пакета.</span><span class="sxs-lookup"><span data-stu-id="65d5d-111">Use the **Package Installation Wizard** to deploy an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project for which you built a package deployment utility.</span></span>  
  
 <span data-ttu-id="65d5d-112">**Больше не показывать это окно**</span><span class="sxs-lookup"><span data-stu-id="65d5d-112">**Do not show this starting page again**</span></span>  
 <span data-ttu-id="65d5d-113">Выберите этот параметр, чтобы пропустить начальную страницу при повторном запуске мастера.</span><span class="sxs-lookup"><span data-stu-id="65d5d-113">Select to skip the starting page when you run the wizard again.</span></span>  
  
 <span data-ttu-id="65d5d-114">**Дальше**</span><span class="sxs-lookup"><span data-stu-id="65d5d-114">**Next**</span></span>  
 <span data-ttu-id="65d5d-115">Перейдите на следующую страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="65d5d-115">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="65d5d-116">**Готово**</span><span class="sxs-lookup"><span data-stu-id="65d5d-116">**Finish**</span></span>  
 <span data-ttu-id="65d5d-117">Переход на страницу завершения работы мастера установки пакета.</span><span class="sxs-lookup"><span data-stu-id="65d5d-117">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="65d5d-118">Этот параметр используется после возврата на предыдущие страницы мастера для просмотра выбранных позиций, если все нужные параметры заданы.</span><span class="sxs-lookup"><span data-stu-id="65d5d-118">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="configure-packages-page"></a><span data-ttu-id="65d5d-119">Страница настройки пакетов</span><span class="sxs-lookup"><span data-stu-id="65d5d-119">Configure Packages Page</span></span>  
 <span data-ttu-id="65d5d-120">Используйте страницу **Настройка пакетов** , чтобы отредактировать конфигурации пакета.</span><span class="sxs-lookup"><span data-stu-id="65d5d-120">Use the **Configure Packages** page to edit package configurations.</span></span>  
  
### <a name="options"></a><span data-ttu-id="65d5d-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="65d5d-121">Options</span></span>  
 <span data-ttu-id="65d5d-122">**Файл конфигурации**</span><span class="sxs-lookup"><span data-stu-id="65d5d-122">**Configuration file**</span></span>  
 <span data-ttu-id="65d5d-123">Редактируйте содержимое файла конфигурации путем выбора файла из списка.</span><span class="sxs-lookup"><span data-stu-id="65d5d-123">Edit the contents of a configuration file by selecting the file from the list.</span></span>  
  
 <span data-ttu-id="65d5d-124">**См. также:** [Создание конфигурации пакетов](../../2014/integration-services/create-package-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="65d5d-124">**Related Topics:** [Create Package Configurations](../../2014/integration-services/create-package-configurations.md)</span></span>  
  
 <span data-ttu-id="65d5d-125">**Путь**</span><span class="sxs-lookup"><span data-stu-id="65d5d-125">**Path**</span></span>  
 <span data-ttu-id="65d5d-126">Просмотр пути к настраиваемому свойству.</span><span class="sxs-lookup"><span data-stu-id="65d5d-126">View the path of the property to be configured.</span></span>  
  
 <span data-ttu-id="65d5d-127">**Тип**</span><span class="sxs-lookup"><span data-stu-id="65d5d-127">**Type**</span></span>  
 <span data-ttu-id="65d5d-128">Просмотр типа данных указанного свойства.</span><span class="sxs-lookup"><span data-stu-id="65d5d-128">View the data type of the property.</span></span>  
  
 <span data-ttu-id="65d5d-129">**Значение**</span><span class="sxs-lookup"><span data-stu-id="65d5d-129">**Value**</span></span>  
 <span data-ttu-id="65d5d-130">Задание значения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="65d5d-130">Specify the value of the configuration.</span></span>  
  
 <span data-ttu-id="65d5d-131">**Дальше**</span><span class="sxs-lookup"><span data-stu-id="65d5d-131">**Next**</span></span>  
 <span data-ttu-id="65d5d-132">Перейдите на следующую страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="65d5d-132">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="65d5d-133">**Готово**</span><span class="sxs-lookup"><span data-stu-id="65d5d-133">**Finish**</span></span>  
 <span data-ttu-id="65d5d-134">Переход на страницу завершения работы мастера установки пакета.</span><span class="sxs-lookup"><span data-stu-id="65d5d-134">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="65d5d-135">Этот параметр используется после возврата на предыдущие страницы мастера для просмотра выбранных позиций, если все нужные параметры заданы.</span><span class="sxs-lookup"><span data-stu-id="65d5d-135">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="confirm-installation-page"></a><span data-ttu-id="65d5d-136">Страница подтверждения установки</span><span class="sxs-lookup"><span data-stu-id="65d5d-136">Confirm Installation Page</span></span>  
 <span data-ttu-id="65d5d-137">Страница **Подтверждение установки** используется для запуска установки пакетов, для просмотра состояния, а также для просмотра данных, которые мастер будет использовать для установки файлов из указанного проекта.</span><span class="sxs-lookup"><span data-stu-id="65d5d-137">Use the **Confirm Installation** page to start the installation of packages, to view the status, and to view the information that the wizard will use to install files from the specified project.</span></span>  
  
 <span data-ttu-id="65d5d-138">**Дальше**</span><span class="sxs-lookup"><span data-stu-id="65d5d-138">**Next**</span></span>  
 <span data-ttu-id="65d5d-139">Установите пакеты и их зависимости, затем, по окончании установки, перейдите на следующую страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="65d5d-139">Install the packages and their dependencies and go to the next wizard page when installation is completed.</span></span>  
  
 <span data-ttu-id="65d5d-140">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="65d5d-140">**Status**</span></span>  
 <span data-ttu-id="65d5d-141">Отображается ход установки пакета.</span><span class="sxs-lookup"><span data-stu-id="65d5d-141">Shows the progress of the package installation.</span></span>  
  
 <span data-ttu-id="65d5d-142">**Готово**</span><span class="sxs-lookup"><span data-stu-id="65d5d-142">**Finish**</span></span>  
 <span data-ttu-id="65d5d-143">Перейдите на страницу завершения работы мастера установки пакета.</span><span class="sxs-lookup"><span data-stu-id="65d5d-143">Go to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="65d5d-144">Этот параметр можно использовать после возврата на предыдущие страницы мастера, чтобы просмотреть свой выбор после указания всех необходимых параметров.</span><span class="sxs-lookup"><span data-stu-id="65d5d-144">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all the required options.</span></span>  
  
## <a name="deploy-ssis-packages-page"></a><span data-ttu-id="65d5d-145">Страница развертывания пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="65d5d-145">Deploy SSIS Packages Page</span></span>  
 <span data-ttu-id="65d5d-146">Страница **Установка пакетов служб SSIS** используется для задания места установки пакетов служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и их зависимостей.</span><span class="sxs-lookup"><span data-stu-id="65d5d-146">Use the **Deploy SSIS Packages** page to specify where to install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages and their dependencies.</span></span>  
  
### <a name="options"></a><span data-ttu-id="65d5d-147">Параметры</span><span class="sxs-lookup"><span data-stu-id="65d5d-147">Options</span></span>  
 <span data-ttu-id="65d5d-148">**Установить в файловую систему**</span><span class="sxs-lookup"><span data-stu-id="65d5d-148">**File system deployment**</span></span>  
 <span data-ttu-id="65d5d-149">Установить пакеты и зависимости в заданную папку в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="65d5d-149">Deploy packages and dependencies in a specified folder in the file system.</span></span>  
  
 <span data-ttu-id="65d5d-150">**Установить на SQL Server**</span><span class="sxs-lookup"><span data-stu-id="65d5d-150">**SQL Server deployment**</span></span>  
 <span data-ttu-id="65d5d-151">Установить пакеты и зависимости в экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65d5d-151">Deploy packages and dependencies in an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="65d5d-152">Используйте данный параметр, если [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] совместно использует пакеты между несколькими серверами.</span><span class="sxs-lookup"><span data-stu-id="65d5d-152">Use this option if [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shares packages between servers.</span></span> <span data-ttu-id="65d5d-153">Все зависимости пакетов устанавливаются в заданную папку файловой системы.</span><span class="sxs-lookup"><span data-stu-id="65d5d-153">Any package dependencies are installed in the specified folder in the file system.</span></span>  
  
 <span data-ttu-id="65d5d-154">**Проверить пакеты после установки**</span><span class="sxs-lookup"><span data-stu-id="65d5d-154">**Validate packages after installation**</span></span>  
 <span data-ttu-id="65d5d-155">Укажите, необходимо ли проверить пакеты после установки.</span><span class="sxs-lookup"><span data-stu-id="65d5d-155">Indicate whether to validate packages after installation.</span></span>  
  
 <span data-ttu-id="65d5d-156">**Дальше**</span><span class="sxs-lookup"><span data-stu-id="65d5d-156">**Next**</span></span>  
 <span data-ttu-id="65d5d-157">Перейдите на следующую страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="65d5d-157">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="65d5d-158">**Готово**</span><span class="sxs-lookup"><span data-stu-id="65d5d-158">**Finish**</span></span>  
 <span data-ttu-id="65d5d-159">Переход на страницу завершения работы мастера установки пакета.</span><span class="sxs-lookup"><span data-stu-id="65d5d-159">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="65d5d-160">Этот параметр используется после возврата на предыдущие страницы мастера для просмотра выбранных позиций, если все нужные параметры заданы.</span><span class="sxs-lookup"><span data-stu-id="65d5d-160">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="packages-validation-page"></a><span data-ttu-id="65d5d-161">Страница проверки пакетов</span><span class="sxs-lookup"><span data-stu-id="65d5d-161">Packages Validation Page</span></span>  
 <span data-ttu-id="65d5d-162">Используйте страницу **Проверка пакетов** для просмотра хода выполнения и результатов проверки пакета.</span><span class="sxs-lookup"><span data-stu-id="65d5d-162">Use the **Packages Validation** page to view the progress and results of the package validation.</span></span>  
  
 <span data-ttu-id="65d5d-163">**Дальше**</span><span class="sxs-lookup"><span data-stu-id="65d5d-163">**Next**</span></span>  
 <span data-ttu-id="65d5d-164">Перейдите на следующую страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="65d5d-164">Go to the next page in the wizard.</span></span>  
  
## <a name="select-installation-folder-page"></a><span data-ttu-id="65d5d-165">Страница выбора папки установки</span><span class="sxs-lookup"><span data-stu-id="65d5d-165">Select Installation Folder Page</span></span>  
 <span data-ttu-id="65d5d-166">Страница **Выбор папки для установки** используется для указания папки в файловой системе, в которую будут установлены пакеты и их зависимости.</span><span class="sxs-lookup"><span data-stu-id="65d5d-166">Use the **Select Installation Folder** page to specify the file system folder in which to install the packages and their dependencies.</span></span>  
  
### <a name="options"></a><span data-ttu-id="65d5d-167">Параметры</span><span class="sxs-lookup"><span data-stu-id="65d5d-167">Options</span></span>  
 <span data-ttu-id="65d5d-168">**Папка**</span><span class="sxs-lookup"><span data-stu-id="65d5d-168">**Folder**</span></span>  
 <span data-ttu-id="65d5d-169">Позволяет указать путь к папке, в которую будет скопирован пакет и его зависимости.</span><span class="sxs-lookup"><span data-stu-id="65d5d-169">Specify the path and folder in which to copy the package and its dependencies.</span></span>  
  
 <span data-ttu-id="65d5d-170">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="65d5d-170">**Browse**</span></span>  
 <span data-ttu-id="65d5d-171">Служит для выбора целевой папки в диалоговом окне **Обзор папки** .</span><span class="sxs-lookup"><span data-stu-id="65d5d-171">Browse to the target folder by using the **Browse For Folder** dialog box.</span></span>  
  
 <span data-ttu-id="65d5d-172">**Дальше**</span><span class="sxs-lookup"><span data-stu-id="65d5d-172">**Next**</span></span>  
 <span data-ttu-id="65d5d-173">Перейдите на следующую страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="65d5d-173">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="65d5d-174">**Готово**</span><span class="sxs-lookup"><span data-stu-id="65d5d-174">**Finish**</span></span>  
 <span data-ttu-id="65d5d-175">Переход на страницу завершения работы мастера установки пакета.</span><span class="sxs-lookup"><span data-stu-id="65d5d-175">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="65d5d-176">Этот параметр следует использовать в случае попадания на данную страницу путем возвращения с последующих страниц мастера для проверки выбранных параметров, если все необходимые параметры были заданы.</span><span class="sxs-lookup"><span data-stu-id="65d5d-176">Use this option if you have backtracked through the wizard pages to revise your choices and if have specified all of the required options.</span></span>  
  
## <a name="specify-target-sql-server-page"></a><span data-ttu-id="65d5d-177">Страница выбора целевого сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="65d5d-177">Specify Target SQL Server Page</span></span>  
 <span data-ttu-id="65d5d-178">Используйте страницу **Выбор целевого сервера SQL Server** для указания параметров развертывания пакета на экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65d5d-178">Use the **Specify Target SQL Server** page to specify options for deploying the package to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="options"></a><span data-ttu-id="65d5d-179">Параметры</span><span class="sxs-lookup"><span data-stu-id="65d5d-179">Options</span></span>  
 <span data-ttu-id="65d5d-180">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="65d5d-180">**Server name**</span></span>  
 <span data-ttu-id="65d5d-181">Укажите имя сервера, на котором надо осуществлять развертывание пакетов.</span><span class="sxs-lookup"><span data-stu-id="65d5d-181">Specify the name of the server to deploy the packages to.</span></span>  
  
 <span data-ttu-id="65d5d-182">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="65d5d-182">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="65d5d-183">Укажите, использовать ли проверку подлинности Windows при входе на сервер.</span><span class="sxs-lookup"><span data-stu-id="65d5d-183">Specify whether to use Windows Authentication to log on to the server.</span></span> <span data-ttu-id="65d5d-184">Для лучшей защиты рекомендуется использовать проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="65d5d-184">Windows Authentication is recommended for better security.</span></span>  
  
 <span data-ttu-id="65d5d-185">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="65d5d-185">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="65d5d-186">Укажите, должен ли пакет использовать проверку подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] при входе на сервер.</span><span class="sxs-lookup"><span data-stu-id="65d5d-186">Specify whether the package should use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to log on to the server.</span></span> <span data-ttu-id="65d5d-187">Если используется проверка подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , необходимо ввести имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="65d5d-187">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="65d5d-188">**User name**</span><span class="sxs-lookup"><span data-stu-id="65d5d-188">**User name**</span></span>  
 <span data-ttu-id="65d5d-189">Укажите имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="65d5d-189">Specify a user name.</span></span>  
  
 <span data-ttu-id="65d5d-190">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="65d5d-190">**Password**</span></span>  
 <span data-ttu-id="65d5d-191">Укажите пароль.</span><span class="sxs-lookup"><span data-stu-id="65d5d-191">Specify a password.</span></span>  
  
 <span data-ttu-id="65d5d-192">**Путь пакета**</span><span class="sxs-lookup"><span data-stu-id="65d5d-192">**Package path**</span></span>  
 <span data-ttu-id="65d5d-193">Укажите имя логической папки или введите «/» в качестве папки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65d5d-193">Specify the name of the logical folder, or enter "/" for the default folder.</span></span>  
  
 <span data-ttu-id="65d5d-194">Чтобы выбрать папку в диалоговом окне **Пакет служб SSIS** , нажмите кнопку Обзор (...). Однако в диалоговом окне отсутствует возможность задать папку по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65d5d-194">To select the folder in the **SSIS Package** dialog box, click browse (...). However, the dialog box does not provide a means to select the default folder.</span></span> <span data-ttu-id="65d5d-195">Если необходимо использовать папку по умолчанию, то следует ввести в текстовое поле «/».</span><span class="sxs-lookup"><span data-stu-id="65d5d-195">If you want to use the default folder, you have to enter "/" in the text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65d5d-196">Если не ввести допустимый путь пакета, появится следующее сообщение об ошибке: "Один или несколько аргументов являются недопустимыми".</span><span class="sxs-lookup"><span data-stu-id="65d5d-196">If you do not enter a valid package path, the following error message appears: "One or more arguments are invalid."</span></span>  
  
 <span data-ttu-id="65d5d-197">**Шифрование обеспечивается хранением на сервере**</span><span class="sxs-lookup"><span data-stu-id="65d5d-197">**Rely on server storage for encryption**</span></span>  
 <span data-ttu-id="65d5d-198">Выберите, чтобы использовать средства безопасности компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] для защиты пакетов.</span><span class="sxs-lookup"><span data-stu-id="65d5d-198">Select to use security features of the [!INCLUDE[ssDE](../includes/ssde-md.md)] to help secure the packages.</span></span>  
  
 <span data-ttu-id="65d5d-199">**Дальше**</span><span class="sxs-lookup"><span data-stu-id="65d5d-199">**Next**</span></span>  
 <span data-ttu-id="65d5d-200">Перейдите на следующую страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="65d5d-200">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="65d5d-201">**Готово**</span><span class="sxs-lookup"><span data-stu-id="65d5d-201">**Finish**</span></span>  
 <span data-ttu-id="65d5d-202">Переход на страницу завершения работы мастера установки пакета.</span><span class="sxs-lookup"><span data-stu-id="65d5d-202">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="65d5d-203">Этот параметр используется после возврата на предыдущие страницы мастера для просмотра выбранных позиций, если все нужные параметры заданы.</span><span class="sxs-lookup"><span data-stu-id="65d5d-203">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="finish-the-package-installation-page"></a><span data-ttu-id="65d5d-204">Страница завершения установки пакета</span><span class="sxs-lookup"><span data-stu-id="65d5d-204">Finish the Package Installation Page</span></span>  
 <span data-ttu-id="65d5d-205">Страница **Завершение работы мастера установки пакета** используется для просмотра сводки о результатах установки пакетов.</span><span class="sxs-lookup"><span data-stu-id="65d5d-205">Use the **Finish the Package Installation Wizard** page to view a summary of the package installation results.</span></span> <span data-ttu-id="65d5d-206">На этой странице представлены такие сведения, как имя развертываемого проекта служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , список инсталлированных пакетов, файлы конфигурации и пути размещения компонентов.</span><span class="sxs-lookup"><span data-stu-id="65d5d-206">This page provides details such as the name of the deployed [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, the packages that were installed, the configuration files, and the installation location.</span></span>  
  
 <span data-ttu-id="65d5d-207">**Готово**</span><span class="sxs-lookup"><span data-stu-id="65d5d-207">**Finish**</span></span>  
 <span data-ttu-id="65d5d-208">Для завершения работы мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="65d5d-208">Exit the wizard by clicking **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d5d-209">См. также:</span><span class="sxs-lookup"><span data-stu-id="65d5d-209">See Also</span></span>  
 [<span data-ttu-id="65d5d-210">Развертывание пакетов &#40;&#41;SSIS</span><span class="sxs-lookup"><span data-stu-id="65d5d-210">Package Deployment &#40;SSIS&#41;</span></span>](packages/legacy-package-deployment-ssis.md)  
  
  
