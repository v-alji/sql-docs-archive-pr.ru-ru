---
title: Настройка сервера отчетов в собственном режиме для локального администрирования (SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- UAC
- installing Reporting Services
- Windows Vista
- Localhost
- windows server 2008
- Vista
ms.assetid: 312c6bb8-b3f7-4142-a55f-c69ee15bbf52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad53f293ef825a382d9e39b58527a36ef291687a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665825"
---
# <a name="configure-a-native-mode-report-server-for-local-administration-ssrs"></a><span data-ttu-id="8d683-102">Настройка сервера отчетов, работающего в собственном режиме, для локального администрирования (SSRS)</span><span class="sxs-lookup"><span data-stu-id="8d683-102">Configure a Native Mode Report Server for Local Administration (SSRS)</span></span>
  <span data-ttu-id="8d683-103">Развертывание сервера отчетов [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в одной из следующих операционных систем требует дополнительных шагов настройки, если вы желаете управлять экземпляром этого сервера локально.</span><span class="sxs-lookup"><span data-stu-id="8d683-103">Deploying a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server on one of the following operating systems requires more configuration steps if you want to administer the report server instance locally.</span></span> <span data-ttu-id="8d683-104">Данная тема объясняет как настроить сервер отчетов для локального администрирования.</span><span class="sxs-lookup"><span data-stu-id="8d683-104">This topic explains how to configure the report server for local administration.</span></span> <span data-ttu-id="8d683-105">Если сервер отчетов еще не установлен или не настроен, см. раздел [Install SQL Server 2014 мастера установки &#40;установки&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) и [управления сервером отчетов Reporting Services, работающем в собственном режиме](manage-a-reporting-services-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="8d683-105">If you have not yet installed or configured the report server, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) and [Manage a Reporting Services Native Mode Report Server](manage-a-reporting-services-native-mode-report-server.md).</span></span>  
  
||  
|-|  
|<span data-ttu-id="8d683-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="8d683-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
-   [!INCLUDE[winblue_server_2](../../includes/winblue-server-2-md.md)]  
  
-   [!INCLUDE[winblue_client_2](../../includes/winblue-client-2-md.md)]  
  
-   [!INCLUDE[win8](../../includes/win8-md.md)]  
  
-   [!INCLUDE[win8srv](../../includes/win8srv-md.md)]  
  
-   [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)]  
  
-   [!INCLUDE[win7](../../includes/win7-md.md)]  
  
-   [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)]  
  
 <span data-ttu-id="8d683-107">Так как указанные ОС ограничивают разрешения, большинство приложений запускаются членами локальной группы «Администраторы» точно таким же образом, как и из стандартной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="8d683-107">Because the noted operating systems limit permissions, members of the local Administrators group run most applications as if they are using the Standard User account.</span></span>  
  
 <span data-ttu-id="8d683-108">Это позволяет повысить общую безопасность системы, предотвращая использование стандартных, встроенных назначений ролей, которые службы Reporting Services создают для локальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="8d683-108">While this practice improves the overall security of your system, it prevents you from using the predefined, built-in role assignments that Reporting Services creates for local administrators.</span></span>  
  
-   [<span data-ttu-id="8d683-109">Обзор изменений в конфигурации</span><span class="sxs-lookup"><span data-stu-id="8d683-109">Overview of Configuration Changes</span></span>](#bkmk_configuraiton_overview)  
  
-   [<span data-ttu-id="8d683-110">Настройка администрирования локального сервера отчетов и диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="8d683-110">To Configure Local Report Server and Report Manager Administration</span></span>](#bkmk_configure_local_server)  
  
-   [<span data-ttu-id="8d683-111">Настройка среды SQL Server Management Studio (SSMS) для локального администрирования сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="8d683-111">To Configure SQL Server Management Studio (SSMS) for local report server administration</span></span>](#bkmk_configure_ssms)  
  
-   [<span data-ttu-id="8d683-112">Настройка среды SQL Server Data Tools BI (SSDT) для публикации в локальном сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="8d683-112">To Configure SQL Server Data Tools BI (SSDT) to Publish to a Local Report Server</span></span>](#bkmk_configure_ssdt)  
  
-   [<span data-ttu-id="8d683-113">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="8d683-113">Additional Information</span></span>](#bkmk_addiitonal_informaiton)  
  
##  <a name="overview-of-configuration-changes"></a><a name="bkmk_configuraiton_overview"></a><span data-ttu-id="8d683-114">Общие сведения об изменениях конфигурации</span><span class="sxs-lookup"><span data-stu-id="8d683-114">Overview of Configuration Changes</span></span>  
 <span data-ttu-id="8d683-115">Следующие изменения в конфигурации настраивают сервер так, что можно использовать разрешения стандартного пользователя при выполнении операций сервера отчетов и управлении его содержимым.</span><span class="sxs-lookup"><span data-stu-id="8d683-115">The following configuration changes configure the server so that you can use standard user permissions to manage report server content and operations:</span></span>  
  
-   <span data-ttu-id="8d683-116">Добавление URL-адресов служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в доверенные сайты.</span><span class="sxs-lookup"><span data-stu-id="8d683-116">Add [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLs to trusted sites.</span></span> <span data-ttu-id="8d683-117">По умолчанию Internet Explorer, запущенный на перечисленных ОС, выполняется в **защищенном режиме**, в котором запросы браузера изолируются от процессов высокого уровня, выполняющихся на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d683-117">By default, Internet Explorer running on the listed operating systems runs in **Protected Mode**, a feature that blocks browser requests from reaching high-level processes that run on the same computer.</span></span> <span data-ttu-id="8d683-118">Защищенный режим для приложений сервера отчетов можно отключить, добавив их в список «Надежные сайты».</span><span class="sxs-lookup"><span data-stu-id="8d683-118">You can disable protected mode for the report server applications by adding them as Trusted Sites.</span></span>  
  
-   <span data-ttu-id="8d683-119">Создание назначений ролей, которые предоставляют права администратора сервера отчетов, разрешение на управление содержимым и процессом работы сервера отчетов без применения функции обозревателя **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="8d683-119">Create role assignments that grant you, the report server administrator, permission to manage content and operations without having to use the **Run as administrator** feature on Internet Explorer.</span></span> <span data-ttu-id="8d683-120">Создав назначение ролей для учетной записи пользователя Windows, можно получить доступ к серверу отчетов с разрешениями «Диспетчер содержимого» и «Системный администратор» через назначения ролей, определенные явным образом и созданные на замену стандартным встроенным назначениям ролей, которые были созданы службами Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8d683-120">By creating role assignments for your Windows user account, you gain access to a report server with Content Manager and System Administrator permissions through explicit role assignments that replace the predefined, built-in role assignments that Reporting Services creates.</span></span>  
  
##  <a name="to-configure-local-report-server-and-report-manager-administration"></a><a name="bkmk_configure_local_server"></a><span data-ttu-id="8d683-121">Настройка локального сервера отчетов и диспетчер отчетов администрирования</span><span class="sxs-lookup"><span data-stu-id="8d683-121">To Configure Local Report Server and Report Manager Administration</span></span>  
 <span data-ttu-id="8d683-122">Выполните действия по настройке этого раздела, если при переходе на локальный сервер отчетов возникают следующие ошибки.</span><span class="sxs-lookup"><span data-stu-id="8d683-122">Complete the configuration steps in this section if you are browsing to a local report server and you see errors similar to the following:</span></span>  
  
-   <span data-ttu-id="8d683-123">У пользователя `'Domain\[user name]`отсутствуют необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="8d683-123">User `'Domain\[user name]`' does not have required permissions.</span></span> <span data-ttu-id="8d683-124">Убедитесь, что предоставлены достаточные разрешения и учтены ограничения контроля учетных записей Windows.</span><span class="sxs-lookup"><span data-stu-id="8d683-124">Verify that sufficient permissions have been granted and Windows User Account Control (UAC) restrictions have been addressed.</span></span>  
  
###  <a name="trusted-site-settings-in-the-browser"></a><a name="bkmk_site_settings"></a><span data-ttu-id="8d683-125">Параметры доверенного сайта в браузере</span><span class="sxs-lookup"><span data-stu-id="8d683-125">Trusted Site Settings in the Browser</span></span>  
  
1.  <span data-ttu-id="8d683-126">Откройте окно браузера с разрешением «Запуск от имени администратора».</span><span class="sxs-lookup"><span data-stu-id="8d683-126">Open a browser window with Run as administrator permissions.</span></span> <span data-ttu-id="8d683-127">В меню **Пуск** укажите **Все программы**, щелкните правой кнопкой мыши пункт **Internet Explorer**и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="8d683-127">From the **Start** menu, click **All Programs**, right-click **Internet Explorer**, and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="8d683-128">Чтобы продолжить, нажмите кнопку **Разрешить** .</span><span class="sxs-lookup"><span data-stu-id="8d683-128">Click **Allow** to continue.</span></span>  
  
3.  <span data-ttu-id="8d683-129">В качестве URL-адреса укажите URL-адрес диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="8d683-129">In the URL address, enter the Report Manager URL.</span></span> <span data-ttu-id="8d683-130">Инструкции см. в разделе [Диспетчер отчетов (службы SSRS в собственном режиме)](../report-manager-ssrs-native-mode.md) электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d683-130">For instructions, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="8d683-131">Выберите меню **Сервис**.</span><span class="sxs-lookup"><span data-stu-id="8d683-131">Click **Tools**.</span></span>  
  
5.  <span data-ttu-id="8d683-132">Выберите пункт **Свойства обозревателя**.</span><span class="sxs-lookup"><span data-stu-id="8d683-132">Click **Internet Options**.</span></span>  
  
6.  <span data-ttu-id="8d683-133">Перейдите на вкладку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="8d683-133">Click **Security**.</span></span>  
  
7.  <span data-ttu-id="8d683-134">Выберите **Надежные сайты**.</span><span class="sxs-lookup"><span data-stu-id="8d683-134">Click **Trusted Sites**.</span></span>  
  
8.  <span data-ttu-id="8d683-135">Нажмите кнопку **Сайты**.</span><span class="sxs-lookup"><span data-stu-id="8d683-135">Click **Sites**.</span></span>  
  
9. <span data-ttu-id="8d683-136">Добавьте `http://<your-server-name>`.</span><span class="sxs-lookup"><span data-stu-id="8d683-136">Add `http://<your-server-name>`.</span></span>  
  
10. <span data-ttu-id="8d683-137">Снимите флажок **Требуется сертификация сервера (https:) для всех сайтов в этой зоне** , если вы не используете HTTPS для сайта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8d683-137">Clear the check box **Require server certification (https:) for all sites in this zone** if you are not using HTTPS for the default site.</span></span>  
  
11. <span data-ttu-id="8d683-138">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8d683-138">Click **Add**.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
###  <a name="report-manager-folder-settings"></a><a name="bkmk_configure_folder_settings"></a> <span data-ttu-id="8d683-139">Параметры каталога диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="8d683-139">Report Manager Folder Settings</span></span>  
  
1.  <span data-ttu-id="8d683-140">На домашней странице диспетчера отчетов щелкните ссылку **Параметры папки**.</span><span class="sxs-lookup"><span data-stu-id="8d683-140">In Report Manager, on the Home page, click **Folder Settings**.</span></span>  
  
2.  <span data-ttu-id="8d683-141">На странице настроек папки щелкните пункт **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="8d683-141">In the Folder Settings page, click **Security**.</span></span>  
  
3.  <span data-ttu-id="8d683-142">Нажмите кнопку **Создать назначения ролей**.</span><span class="sxs-lookup"><span data-stu-id="8d683-142">Click **New Role Assignment**.</span></span>  
  
4.  <span data-ttu-id="8d683-143">В поле **Имя группы или пользователя** введите имя своей учетной записи Windows в следующем формате: `<domain>\<user>`.</span><span class="sxs-lookup"><span data-stu-id="8d683-143">In the **Group or user name** field, type your Windows user account in this format: `<domain>\<user>`.</span></span>  
  
5.  <span data-ttu-id="8d683-144">Выберите **Диспетчер содержимого**.</span><span class="sxs-lookup"><span data-stu-id="8d683-144">Select **Content Manager**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
###  <a name="report-manager-site-settings"></a><a name="bkmk_configure_site_settings"></a> <span data-ttu-id="8d683-145">Параметры сайта диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="8d683-145">Report Manager Site Settings</span></span>  
  
1.  <span data-ttu-id="8d683-146">Откройте браузер с правами администратора и перейдите к диспетчеру отчетов `http://<server name>/reports`.</span><span class="sxs-lookup"><span data-stu-id="8d683-146">Open your browser with administrative privileges and browse to report manager, `http://<server name>/reports`.</span></span>  
  
2.  <span data-ttu-id="8d683-147">В верхнем углу домашней страницы нажмите кнопку **Параметры сайта** .</span><span class="sxs-lookup"><span data-stu-id="8d683-147">Click **Site Settings** in the upper corner of the Home page.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="8d683-148">**Примечание.** Если вариант **Параметры сайта** недоступен, закройте и повторно откройте браузер и перейдите к диспетчеру отчетов с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="8d683-148">**Note:** If you do not see the **Site Settings** option, close and reopen your browser and browse to report manager with administrative privileges.</span></span>  
  
3.  <span data-ttu-id="8d683-149">Щелкните **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="8d683-149">Click **security**.</span></span>  
  
4.  <span data-ttu-id="8d683-150">Нажмите кнопку **Создать назначения ролей**.</span><span class="sxs-lookup"><span data-stu-id="8d683-150">Click **New Role Assignment**.</span></span>  
  
5.  <span data-ttu-id="8d683-151">В поле **Имя группы или пользователя** введите имя своей учетной записи Windows в следующем формате: `<domain>\<user>`.</span><span class="sxs-lookup"><span data-stu-id="8d683-151">In the **Group or user name** field, type your Windows user account in this format: `<domain>\<user>`.</span></span>  
  
6.  <span data-ttu-id="8d683-152">Выберите **Системный администратор**.</span><span class="sxs-lookup"><span data-stu-id="8d683-152">Select **System Administrator**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="8d683-153">Закройте диспетчер отчетов.</span><span class="sxs-lookup"><span data-stu-id="8d683-153">Close Report Manager.</span></span>  
  
9. <span data-ttu-id="8d683-154">Повторно откройте диспетчер отчетов в Internet Explorer без использования функции **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="8d683-154">Re-open Report Manager in Internet Explorer, without using **Run as administrator**.</span></span>  
  
##  <a name="to-configure-sql-server-management-studio-ssms-for-local-report-server-administration"></a><a name="bkmk_configure_ssms"></a><span data-ttu-id="8d683-155">Настройка SQL Server Management Studio (SSMS) для локального администрирования сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="8d683-155">To Configure SQL Server Management Studio (SSMS) for local report server administration</span></span>  
 <span data-ttu-id="8d683-156">По умолчанию доступ ко всем свойствам сервера отчетов, предусмотренным в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , отсутствует, если не выполнен запуск [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="8d683-156">By default, you cannot access all of the report server properties available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] unless you start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
 <span data-ttu-id="8d683-157">**Настройка назначений ролей [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]** и назначений ролей необходимо каждый раз запускать [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] с повышенным уровнем разрешений.</span><span class="sxs-lookup"><span data-stu-id="8d683-157">**To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]** role properties and role assignments so you do not need to start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with elevated permissions each time:</span></span>  
  
-   <span data-ttu-id="8d683-158">Нажмите кнопку **Пуск** , укажите **Все программы**, **SQL Server 2014**, щелкните правой кнопкой мыши **[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**, а затем выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="8d683-158">From the **Start** menu, click **All Programs**, click **SQL Server 2014**, right-click **[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**, and then click **Run as administrator**.</span></span>  
  
-   <span data-ttu-id="8d683-159">Подключение к локальному серверу [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8d683-159">Connect to your local [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] server.</span></span>  
  
-   <span data-ttu-id="8d683-160">На странице **Безопасность** нажмите **Системные роли**.</span><span class="sxs-lookup"><span data-stu-id="8d683-160">In the **Security** node, click **System Roles**.</span></span>  
  
-   <span data-ttu-id="8d683-161">Щелкните правой кнопкой мыши узел **Системный администратор** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8d683-161">Right-click **System Administrator** and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="8d683-162">В диалоговом окне **Свойства системной роли** выберите **Просмотр свойств сервера отчетов**.</span><span class="sxs-lookup"><span data-stu-id="8d683-162">In the **System Role Properties** page, select **View report server properties**.</span></span> <span data-ttu-id="8d683-163">Выберите все нужные свойства, связанные с членами роли системных администраторов.</span><span class="sxs-lookup"><span data-stu-id="8d683-163">Select any other properties you want associated with members of the system administrators role.</span></span>  
  
-   <span data-ttu-id="8d683-164">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8d683-164">Click **OK**.</span></span>  
  
-   <span data-ttu-id="8d683-165">Закрыть [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d683-165">Close [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]</span></span>  
  
-   <span data-ttu-id="8d683-166">Для добавления пользователя системной роли "системный администратор", обратитесь к предыдущему разделу [Параметры сайта диспетчера отчетов](#bkmk_configure_site_settings) данной темы.</span><span class="sxs-lookup"><span data-stu-id="8d683-166">To add a user to the system role "system administrator", see the [Report Manager Site Settings](#bkmk_configure_site_settings) section earlier in this topic.</span></span>  
  
 <span data-ttu-id="8d683-167">Теперь при открытии [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] без запуска **от имени администратора** у вас будет доступ к свойствам сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="8d683-167">Now when you open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and do not explicitly select **Run as administrator** you have access to the report server properties.</span></span>  
  
##  <a name="to-configure-sql-server-data-tools-bi-ssdt-to-publish-to-a-local-report-server"></a><a name="bkmk_configure_ssdt"></a><span data-ttu-id="8d683-168">Настройка SQL Server Data Tools BI (SSDT) для публикации на локальном сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="8d683-168">To Configure SQL Server Data Tools BI (SSDT) to Publish to a Local Report Server</span></span>  
 <span data-ttu-id="8d683-169">Если вы установили [!INCLUDE[SSDTDev11](../../includes/ssdtdev11-md.md)] в одной из операционных систем, приведенных в первом подразделе, и желаете, чтобы SSDT взаимодействовала с локальным сервером отчетов (в собственном режиме) без получения ошибок о допуске пользователя, нужно открывать [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] с повышенными разрешениями или же настроить роли служб отчетности.</span><span class="sxs-lookup"><span data-stu-id="8d683-169">If you installed [!INCLUDE[SSDTDev11](../../includes/ssdtdev11-md.md)] on one of the operating systems listed in the first section of this topic, and you want SSDT to interact with a local Native mode report server, you will experiences permission errors unless you open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] with elevated permissions or configure reporting services roles.</span></span> <span data-ttu-id="8d683-170">Например, при недостатке разрешений могут возникнуть следующие проблемы.</span><span class="sxs-lookup"><span data-stu-id="8d683-170">For example, if you do not have sufficient permissions, you experience issues similar to the following:</span></span>  
  
-   <span data-ttu-id="8d683-171">При попытке развертывания элементов отчета на локальном сервере отчетов отображается сообщение об ошибке, похожее на приведенное в окне **Список ошибок** .</span><span class="sxs-lookup"><span data-stu-id="8d683-171">When you attempt to deploy report items to the local report server, you see an error message similar to the following in the **Error List** window:</span></span>  
  
    -   <span data-ttu-id="8d683-172">Предоставленные пользователю "домен\\<user name\>" разрешения недостаточны для выполнения данной операции.</span><span class="sxs-lookup"><span data-stu-id="8d683-172">The permissions granted to user 'Domain\\<user name\>' are insufficient for performing this operation.</span></span>  
  
 <span data-ttu-id="8d683-173">**Запуск SSDT с повышенным уровнем разрешений**</span><span class="sxs-lookup"><span data-stu-id="8d683-173">**To run with elevated permissions each time you open SSDT:**</span></span>  
  
1.  <span data-ttu-id="8d683-174">На начальном экране введите, `sql server` а затем щелкните правой кнопкой мыши **SQL Server Data Tools для Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="8d683-174">From the start screen, type `sql server` and then right-click **SQL Server Data Tools for Visual Studio**.</span></span> <span data-ttu-id="8d683-175">Нажмите **Запуск от имени администратора**</span><span class="sxs-lookup"><span data-stu-id="8d683-175">Click **Run as administrator**</span></span>  
  
     <span data-ttu-id="8d683-176">**Или**при работе на старых операционных системах выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="8d683-176">**Or**, on older operating systems:</span></span>  
  
     <span data-ttu-id="8d683-177">Нажмите кнопку **Пуск** , нажмите **Все программы**, **SQL Server 2014**, щелкните правой кнопкой мыши **SQL Server Data Tools**, а затем выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="8d683-177">From the **Start** menu, click **All Programs**, click **SQL Server 2014**, right-click **SQL Server Data Tools**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="8d683-178">Нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="8d683-178">Click **Continue**.</span></span>  
  
3.  <span data-ttu-id="8d683-179">Нажмите кнопку **Выполнить программу**.</span><span class="sxs-lookup"><span data-stu-id="8d683-179">Click **Run Program**.</span></span>  
  
 <span data-ttu-id="8d683-180">После этого можно приступать к развертыванию отчетов и других элементов на локальном сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="8d683-180">You should now be able to deploy reports and other items to a local report server.</span></span>  
  
 <span data-ttu-id="8d683-181">**Настройка назначений ролей [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] без необходимости каждый раз запускать SSDT с повышенным уровнем разрешений**</span><span class="sxs-lookup"><span data-stu-id="8d683-181">**To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] role assignments so you do not need to start SSDT with elevated permissions each time:**</span></span>  
  
-   <span data-ttu-id="8d683-182">Смотрите предыдущие разделы [Параметры каталога диспетчера отчетов](#bkmk_configure_folder_settings) и [Параметры сайта диспетчера отчетов](#bkmk_configure_site_settings) данной темы.</span><span class="sxs-lookup"><span data-stu-id="8d683-182">See the [Report Manager Folder Settings](#bkmk_configure_folder_settings) and [Report Manager Site Settings](#bkmk_configure_site_settings) sections earlier in this topic.</span></span>  
  
##  <a name="additional-information"></a><a name="bkmk_addiitonal_informaiton"></a><span data-ttu-id="8d683-183">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="8d683-183">Additional Information</span></span>  
 <span data-ttu-id="8d683-184">Еще одно распространенное действие по настройке администрирования [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] — открытие порта номер 80 в брандмауэре Windows для разрешения доступа к компьютеру с сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="8d683-184">An additional and common configuration step related to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] administration is to open port 80 in Windows Firewall to allow access to the report server computer.</span></span> <span data-ttu-id="8d683-185">Инструкции см. в разделе [Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="8d683-185">For instructions, see [Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d683-186">См. также:</span><span class="sxs-lookup"><span data-stu-id="8d683-186">See Also</span></span>  
 [<span data-ttu-id="8d683-187">Управление сервером отчетов Reporting Services в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="8d683-187">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
