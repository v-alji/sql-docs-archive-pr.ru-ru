---
title: Командлеты PowerShell для Reporting Services в режиме интеграции с SharePoint | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7835bc97-2827-4215-b0dd-52f692ce5e02
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b20ad870fd8a9cd7f220eebb2b954d7a88a10c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751795"
---
# <a name="powershell-cmdlets-for-reporting-services-sharepoint-mode"></a><span data-ttu-id="98632-102">PowerShell cmdlets для режима SharePoint службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="98632-102">PowerShell cmdlets for Reporting Services SharePoint Mode</span></span>
  <span data-ttu-id="98632-103">При установке [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] служб в режиме интеграции с SharePoint устанавливаются командлеты PowerShell для поддержки серверов отчетов в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98632-103">When you install [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode, PowerShell cmdlets are installed to support report Servers in SharePoint mode.</span></span> <span data-ttu-id="98632-104">Командлеты охватывают три категории функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="98632-104">The cmdlets cover three categories of functionality.</span></span>  
  
-   <span data-ttu-id="98632-105">Установка общей службы и прокси-сервера SharePoint службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-105">Installation of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint shared service and proxy.</span></span>  
  
-   <span data-ttu-id="98632-106">Провизионирование и управление приложениями служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] и связанными с ними прокси-серверами.</span><span class="sxs-lookup"><span data-stu-id="98632-106">Provisioning and management of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications and associated proxies.</span></span>  
  
-   <span data-ttu-id="98632-107">Управление функциями служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , например расширениями и ключами шифрования.</span><span class="sxs-lookup"><span data-stu-id="98632-107">Management of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features, for example extensions and encryption keys.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../includes/applies-md.md)]<span data-ttu-id="98632-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Режим интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="98632-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint Mode</span></span>|  
  
 <span data-ttu-id="98632-109">**В этом разделе обсуждается следующее.**</span><span class="sxs-lookup"><span data-stu-id="98632-109">**This topic contains the following:**</span></span>  
  
-   [<span data-ttu-id="98632-110">Обзор командлетов</span><span class="sxs-lookup"><span data-stu-id="98632-110">Cmdlet Summary</span></span>](#bkmk_cmdlet_sum)  
  
-   [<span data-ttu-id="98632-111">Командлеты общей службы и прокси-серверов</span><span class="sxs-lookup"><span data-stu-id="98632-111">Shared Service and Proxy Cmdlets</span></span>](#bkmk_sharedservice_cmdlets)  
  
-   [<span data-ttu-id="98632-112">Командлеты приложения службы и прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="98632-112">Service Application and Proxy Cmdlets</span></span>](#bkmk_serviceapp_cmdlets)  
  
-   [<span data-ttu-id="98632-113">Reporting Services командлетов пользовательской функциональности</span><span class="sxs-lookup"><span data-stu-id="98632-113">Reporting Services Custom Functionality Cmdlets</span></span>](#bkmk_ssrsfeatures_cmdlets)  
  
-   [<span data-ttu-id="98632-114">Простые примеры</span><span class="sxs-lookup"><span data-stu-id="98632-114">Basic Samples</span></span>](#bkmk_basic_samples)  
  
-   [<span data-ttu-id="98632-115">Подробные примеры</span><span class="sxs-lookup"><span data-stu-id="98632-115">Detailed Samples</span></span>](#bkmk_detailedsamples)  
  
    -   [<span data-ttu-id="98632-116">Создание приложения службы Reporting Services и прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="98632-116">Create a Reporting Services service application and proxy</span></span>](#bkmk_example_create_service_application)  
  
    -   [<span data-ttu-id="98632-117">Проверка и обновление модуля доставки Reporting Services</span><span class="sxs-lookup"><span data-stu-id="98632-117">Review and update a Reporting Services delivery extension</span></span>](#bkmk_example_delivery_extension)  
  
    -   [<span data-ttu-id="98632-118">Получение и задание свойств базы данных приложения Reporting Services, например времени ожидания базы данных</span><span class="sxs-lookup"><span data-stu-id="98632-118">Get and set properties of the Reporting Servicea application database, for example database timeout</span></span>](#bkmk_example_db_properties)  
  
    -   [<span data-ttu-id="98632-119">Список расширений данных служб Reporting Services — режим интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="98632-119">List reporting services data extensions - SharePoint mode</span></span>](#bkmk_example_list_data_extensions)  
  
    -   [<span data-ttu-id="98632-120">Изменение и вывод списка владельцев подписки</span><span class="sxs-lookup"><span data-stu-id="98632-120">Change and list subscription owners</span></span>](#bkmk_change_subscription_owner)  
  
##  <a name="cmdlet-summary"></a><a name="bkmk_cmdlet_sum"></a><span data-ttu-id="98632-121">Сводка по командлетам</span><span class="sxs-lookup"><span data-stu-id="98632-121">Cmdlet Summary</span></span>  

 <span data-ttu-id="98632-122">Для выполнения командлетов необходимо открыть консоль управления SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98632-122">To run the cmdlets you need to open the SharePoint Management Shell.</span></span> <span data-ttu-id="98632-123">Можно также использовать редактор графического пользовательского интерфейса, который включен в Microsoft Windows, **интегрированная среда скриптов Windows PowerShell (ISE)**.</span><span class="sxs-lookup"><span data-stu-id="98632-123">You can also use the graphical user interface editor that is included with Microsoft Windows, **Windows PowerShell Integrated Scripting Environment (ISE)**.</span></span> <span data-ttu-id="98632-124">Дополнительные сведения см. в разделе [Запуск Windows PowerShell на Windows Server](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="98632-124">For more information, see [Starting Windows PowerShell on Windows Server](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell).</span></span> <span data-ttu-id="98632-125">В следующих сводках командлетов ссылки на приложение службы "базы данных" относятся ко всем базам данных, созданным и используемым [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] приложением службы.</span><span class="sxs-lookup"><span data-stu-id="98632-125">In the following cmdlet summaries, the references to service application 'databases', refer to all of the databases created and used by a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="98632-126">Это включает базы данных конфигурации, предупреждений и временные базы данных.</span><span class="sxs-lookup"><span data-stu-id="98632-126">This includes the configuration, alerting, and temp databases.</span></span>  

  
 <span data-ttu-id="98632-127">Если при вводе примеров PowerShell отображается сообщение об ошибке следующего вида:</span><span class="sxs-lookup"><span data-stu-id="98632-127">If you see an error message similar to the following when you type the PowerShell examples:</span></span>  
  
-   <span data-ttu-id="98632-128">термин "Install-SPRSService" не опознан как</span><span class="sxs-lookup"><span data-stu-id="98632-128">Install-SPRSService : The term 'Install-SPRSService' is not recognized as the</span></span>  
    <span data-ttu-id="98632-129">имя командлета, функции, файла скрипта или действующей программы.</span><span class="sxs-lookup"><span data-stu-id="98632-129">name of a cmdlet, function, script file, or operable program.</span></span> <span data-ttu-id="98632-130">Проверьте правильность написания имени, а если включен путь, то проверьте правильность пути и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="98632-130">Check the spelling of the name, or if a path was included, verify that the path is correct and try again.</span></span>  
  
 <span data-ttu-id="98632-131">Возникает одна из следующих проблем.</span><span class="sxs-lookup"><span data-stu-id="98632-131">One of the following issues is occurring:</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="98632-132">Режим SharePoint не установлен, поэтому не установлены командлеты [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-132">SharePoint mode is not installed and therefore the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] cmdlets are not installed.</span></span>  
  
-   <span data-ttu-id="98632-133">Команда PowerShell была выполнена в Windows PowerShell или Windows PowerShell ISE, а не в оболочке управления SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98632-133">You ran the PowerShell command in Windows PowerShell or Windows PowerShell ISE instead of the SharePoint Management Shell.</span></span> <span data-ttu-id="98632-134">Используйте оболочку управления SharePoint или добавьте оснастку SharePoint к окну Windows PowerShell с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="98632-134">Use the SharePoint Management shell or add the SharePoint Snap-in to the Windows PowerShell window with the following command:</span></span>  
  
    ```powershell
    Add-PSSnapin Microsoft.SharePoint.PowerShell  
    ```  
  
 <span data-ttu-id="98632-135">Дополнительные сведения см. [в статье Использование Windows PowerShell для администрирования SharePoint 2013](https://technet.microsoft.com/library/ee806878.aspx) ( https://technet.microsoft.com/library/ee806878.aspx) .</span><span class="sxs-lookup"><span data-stu-id="98632-135">For more information see [Use Windows PowerShell to administer SharePoint 2013](https://technet.microsoft.com/library/ee806878.aspx) (https://technet.microsoft.com/library/ee806878.aspx).</span></span>  
  
#### <a name="to-open-the-sharepoint-management-shell-and-run-cmdlets"></a><span data-ttu-id="98632-136">Открытие оболочки управления SharePoint и выполнение командлетов</span><span class="sxs-lookup"><span data-stu-id="98632-136">To Open the SharePoint Management Shell and run cmdlets</span></span>  
  
1.  <span data-ttu-id="98632-137">Нажмите кнопку **Пуск** .</span><span class="sxs-lookup"><span data-stu-id="98632-137">Click the **Start** button</span></span>  
  
2.  <span data-ttu-id="98632-138">Щелкните группу **Продукты Microsoft SharePoint** .</span><span class="sxs-lookup"><span data-stu-id="98632-138">Click the **Microsoft SharePoint Products** group.</span></span>  
  
3.  <span data-ttu-id="98632-139">Щелкните **Консоль управления SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="98632-139">Click the **SharePoint Management Shell**.</span></span>  
  
 <span data-ttu-id="98632-140">Чтобы просмотреть справку командной строки для командлета, используйте команду Get-Help среды PowerShell в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98632-140">To view command line help for a cmdlet use the PowerShell 'Get-Help' command at the PowerShell command prompt.</span></span> <span data-ttu-id="98632-141">Пример:</span><span class="sxs-lookup"><span data-stu-id="98632-141">For example:</span></span>  
  
 `Get-Help Get-SPRSServiceApplicationServers`  
  
###  <a name="shared-service-and-proxy-cmdlets"></a><a name="bkmk_sharedservice_cmdlets"></a><span data-ttu-id="98632-142">Командлеты общей службы и прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="98632-142">Shared Service and Proxy Cmdlets</span></span>  
 <span data-ttu-id="98632-143">В следующей таблице содержатся командлеты PowerShell для общей службы SharePoint [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-143">The following table contains the PowerShell cmdlets for the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint shared service.</span></span>  
  
|<span data-ttu-id="98632-144">Командлет</span><span class="sxs-lookup"><span data-stu-id="98632-144">Cmdlet</span></span>|<span data-ttu-id="98632-145">Описание</span><span class="sxs-lookup"><span data-stu-id="98632-145">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="98632-146">Install-SPRSService</span><span class="sxs-lookup"><span data-stu-id="98632-146">Install-SPRSService</span></span>|<span data-ttu-id="98632-147">Устанавливает и регистрирует, либо удаляет общую службу [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-147">Installs and registers, or uninstalls, the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] shared service.</span></span> <span data-ttu-id="98632-148">Это можно сделать только на компьютере, где имеется установка служб SQL Server [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98632-148">This can be done only on the machine that has an installation of SQL Server [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="98632-149">При установке выполняются две операции.</span><span class="sxs-lookup"><span data-stu-id="98632-149">For installation, two operations occur:</span></span><br /><br /> <span data-ttu-id="98632-150">1) [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] служба установлена в ферме.</span><span class="sxs-lookup"><span data-stu-id="98632-150">1) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is installed in the farm.</span></span><br /><br /> <span data-ttu-id="98632-151">2 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] . экземпляр службы устанавливается на текущий компьютер.</span><span class="sxs-lookup"><span data-stu-id="98632-151">2) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service instance is installed to the current machine.</span></span><br /><br /> <span data-ttu-id="98632-152">При удалении выполняются две операции.</span><span class="sxs-lookup"><span data-stu-id="98632-152">For Uninstallation, two operations occur:</span></span><br /><span data-ttu-id="98632-153">1) [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] служба удалена с текущего компьютера.</span><span class="sxs-lookup"><span data-stu-id="98632-153">1) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is uninstalled from the current machine.</span></span><br /><span data-ttu-id="98632-154">2 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] . служба удалена из фермы.</span><span class="sxs-lookup"><span data-stu-id="98632-154">2) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is uninstalled from the farm.</span></span><br /><br /> <br /><br /> <span data-ttu-id="98632-155">Примечание. Если в ферме присутствуют другие компьютеры, на которых установлена служба [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , или если в ферме все еще выполняются приложения службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , будет отображено предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="98632-155">NOTE: If there are any other machines in the farm that have the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service installed, or if there are still [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications running in the farm, a warning message is displayed.</span></span>|  
|<span data-ttu-id="98632-156">Install-SPRSServiceProxy</span><span class="sxs-lookup"><span data-stu-id="98632-156">Install-SPRSServiceProxy</span></span>|<span data-ttu-id="98632-157">Устанавливает и регистрирует или удаляет прокси-сервер службы Reporting Services на ферме SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98632-157">Installs and registers, or uninstalls, the Reporting Services service proxy in the SharePoint farm.</span></span>|  
|<span data-ttu-id="98632-158">Get-SPRSProxyUrl</span><span class="sxs-lookup"><span data-stu-id="98632-158">Get-SPRSProxyUrl</span></span>|<span data-ttu-id="98632-159">Возвращает URL-адреса для доступа к службе [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-159">Gets the URL(s) for accessing the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="98632-160">Get-SPRSServiceApplicationServers</span><span class="sxs-lookup"><span data-stu-id="98632-160">Get-SPRSServiceApplicationServers</span></span>|<span data-ttu-id="98632-161">Возвращает все серверы в локальной ферме SharePoint, на которых имеется установка общей службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-161">Gets all servers in the local SharePoint farm that contain an installation of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] shared service.</span></span> <span data-ttu-id="98632-162">Этот командлет полезен при обновлении служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , чтобы определить, на каких серверах выполняется общая служба, в связи с чем требуется обновление.</span><span class="sxs-lookup"><span data-stu-id="98632-162">This cmdlet is useful for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] upgrades, to determine which servers run the shared service and therefore need to be upgraded.</span></span>|  
  
###  <a name="service-application-and-proxy-cmdlets"></a><a name="bkmk_serviceapp_cmdlets"></a> <span data-ttu-id="98632-163">Командлеты приложения службы и прокси-серверов</span><span class="sxs-lookup"><span data-stu-id="98632-163">Service Application and Proxy Cmdlets</span></span>  
 <span data-ttu-id="98632-164">В следующей таблице содержатся командлеты PowerShell для приложений служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] и связанные с ними прокси-серверы.</span><span class="sxs-lookup"><span data-stu-id="98632-164">The following table contains the PowerShell cmdlets for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications and their associated proxies.</span></span>  
  
|<span data-ttu-id="98632-165">командлет</span><span class="sxs-lookup"><span data-stu-id="98632-165">cmdlet</span></span>|<span data-ttu-id="98632-166">Описание</span><span class="sxs-lookup"><span data-stu-id="98632-166">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="98632-167">Get-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="98632-167">Get-SPRSServiceApplication</span></span>|<span data-ttu-id="98632-168">Возвращает один или больше объектов служебного приложения [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-168">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application objects.</span></span>|  
|<span data-ttu-id="98632-169">New-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="98632-169">New-SPRSServiceApplication</span></span>|<span data-ttu-id="98632-170">Создание нового приложения службы Reporting Services и связанных баз данных.</span><span class="sxs-lookup"><span data-stu-id="98632-170">Create a new Reporting Services service application and associated databases.</span></span><br /><br /> <span data-ttu-id="98632-171">Параметр LogonType указывает, использует ли сервер отчетов учетную запись пула приложений служб SSRS или имя входа SQL Server для доступа к базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="98632-171">LogonType Parameter: Specifies if the report server uses the SSRS Application Pool account or a SQL Server login to access the report server database.</span></span> <span data-ttu-id="98632-172">Может принимать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="98632-172">It can be one of the following:</span></span><br /><br /> <span data-ttu-id="98632-173">0 Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="98632-173">0 Windows Authentication</span></span><br /><br /> <span data-ttu-id="98632-174">1 SQL Server</span><span class="sxs-lookup"><span data-stu-id="98632-174">1 SQL Server</span></span><br /><br /> <span data-ttu-id="98632-175">2 Учетная запись пула приложений (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="98632-175">2 Application Pool Account (default)</span></span>|  
|<span data-ttu-id="98632-176">Remove-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="98632-176">Remove-SPRSServiceApplication</span></span>|<span data-ttu-id="98632-177">Удаляет указанное приложение службы Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="98632-177">Removes the specified Reporting Services service application.</span></span> <span data-ttu-id="98632-178">Также будут удалены связанные базы данных.</span><span class="sxs-lookup"><span data-stu-id="98632-178">This will also remove the associated databases.</span></span>|  
|<span data-ttu-id="98632-179">Set-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="98632-179">Set-SPRSServiceApplication</span></span>|<span data-ttu-id="98632-180">Изменяет свойства существующего приложения службы Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="98632-180">Edits the properties of an existing Reporting Services service application.</span></span>|  
|<span data-ttu-id="98632-181">New-SPRSServiceApplicationProxy</span><span class="sxs-lookup"><span data-stu-id="98632-181">New-SPRSServiceApplicationProxy</span></span>|<span data-ttu-id="98632-182">Создание прокси-сервера приложения службы Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="98632-182">Creates a new Reporting Services service application proxy.</span></span>|  
|<span data-ttu-id="98632-183">Get-SPRSServiceApplicationProxy</span><span class="sxs-lookup"><span data-stu-id="98632-183">Get-SPRSServiceApplicationProxy</span></span>|<span data-ttu-id="98632-184">Получает один или несколько прокси-серверов приложений службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-184">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application proxies.</span></span>|  
|<span data-ttu-id="98632-185">Dismount-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="98632-185">Dismount-SPRSDatabase</span></span>|<span data-ttu-id="98632-186">Выполняет размонтирование баз данных приложения службы для приложения службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-186">Dismounts the service application databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="98632-187">Remove-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="98632-187">Remove-SPRSDatabase</span></span>|<span data-ttu-id="98632-188">Выполняет удаление баз данных приложения службы для приложения службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-188">Remove the service application databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="98632-189">Set-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="98632-189">Set-SPRSDatabase</span></span>|<span data-ttu-id="98632-190">Задает свойства баз данных, связанных с приложением службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-190">Sets the properties of the databases associated to a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="98632-191">Mount-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="98632-191">Mount-SPRSDatabase</span></span>|<span data-ttu-id="98632-192">Присоединяет базы данных для приложения службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-192">Mounts databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="98632-193">New-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="98632-193">New-SPRSDatabase</span></span>|<span data-ttu-id="98632-194">Создает новые базы данных приложения службы для заданного приложения службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-194">Create new service application databases for the specified [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="98632-195">Get-SPRSDatabaseCreationScript</span><span class="sxs-lookup"><span data-stu-id="98632-195">Get-SPRSDatabaseCreationScript</span></span>|<span data-ttu-id="98632-196">Выводит на экран скрипт создания базы данных для приложения службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-196">Outputs the database creation script to the screen for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="98632-197">Затем скрипт можно запустить в среде SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="98632-197">You can then run the script in SQL Server Management Studio.</span></span>|  
|<span data-ttu-id="98632-198">Get-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="98632-198">Get-SPRSDatabase</span></span>|<span data-ttu-id="98632-199">Получает одну или несколько баз данных приложения службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-199">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application databases.</span></span> <span data-ttu-id="98632-200">Используйте команду для получения идентификатора базы данных служебного приложения, чтобы вы могли использовать Set-SPRSDatabase comdlet для изменения параметров, например `querytimeout`.</span><span class="sxs-lookup"><span data-stu-id="98632-200">Use the command to get the ID of service application database so you can use the Set-SPRSDatabase comdlet to modify properties, for example the `querytimeout`.</span></span> <span data-ttu-id="98632-201">Смотрите примеры в данной теме, [Получение и задание свойств базы данных приложения Reporting Services, например времени ожидания базы данных](#bkmk_example_db_properties).</span><span class="sxs-lookup"><span data-stu-id="98632-201">See the example in this topic, [Get and set properties of the Reporting Servicea application database, for example database timeout](#bkmk_example_db_properties).</span></span>|  
|<span data-ttu-id="98632-202">Get-SPRSDatabaseRightsScript</span><span class="sxs-lookup"><span data-stu-id="98632-202">Get-SPRSDatabaseRightsScript</span></span>|<span data-ttu-id="98632-203">Выводит на экран скрипт определения прав базы данных для базы данных приложения службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-203">Outputs the database rights script to the screen for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="98632-204">Запрашивает необходимые сведения о пользователе и базе данных, а затем возвращает код Transact-SQL, который можно выполнить для изменения разрешений.</span><span class="sxs-lookup"><span data-stu-id="98632-204">It will prompt for desired user and database then returns transact SQL you can run to modify permissions.</span></span> <span data-ttu-id="98632-205">Затем этот скрипт можно запустить в среде SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="98632-205">You can then run this script in SQL Server Management Studio.</span></span>|  
|<span data-ttu-id="98632-206">Get-SPRSDatabaseUpgradeScript</span><span class="sxs-lookup"><span data-stu-id="98632-206">Get-SPRSDatabaseUpgradeScript</span></span>|<span data-ttu-id="98632-207">Выводит скрипт обновления базы данных на экран.</span><span class="sxs-lookup"><span data-stu-id="98632-207">Outputs a database upgrade script to the screen.</span></span> <span data-ttu-id="98632-208">Скрипт произведет обновление баз данных приложения службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] до версии баз данных текущей установки служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-208">The script will upgrade [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application databases to the database version of the current [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] installation.</span></span>|  
  
###  <a name="reporting-services-custom-functionality-cmdlets"></a><a name="bkmk_ssrsfeatures_cmdlets"></a><span data-ttu-id="98632-209">Reporting Services командлетов пользовательской функциональности</span><span class="sxs-lookup"><span data-stu-id="98632-209">Reporting Services Custom Functionality Cmdlets</span></span>  
  
|<span data-ttu-id="98632-210">Командлет</span><span class="sxs-lookup"><span data-stu-id="98632-210">Cmdlet</span></span>|<span data-ttu-id="98632-211">Описание</span><span class="sxs-lookup"><span data-stu-id="98632-211">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="98632-212">Update-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="98632-212">Update-SPRSEncryptionKey</span></span>|<span data-ttu-id="98632-213">Обновляет ключ шифрования для указанного приложения службы Reporting Services и повторно шифрует его данные.</span><span class="sxs-lookup"><span data-stu-id="98632-213">Updates the encryption key for the specified Reporting Services service application and re-encrypts its data.</span></span>|  
|<span data-ttu-id="98632-214">Restore-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="98632-214">Restore-SPRSEncryptionKey</span></span>|<span data-ttu-id="98632-215">Восстанавливает созданную ранее резервную копию ключа шифрования для приложения службы Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="98632-215">Restores a previously backed up encryption key for a Reporting Services service application.</span></span>|  
|<span data-ttu-id="98632-216">Remove-SPRSEncryptedData</span><span class="sxs-lookup"><span data-stu-id="98632-216">Remove-SPRSEncryptedData</span></span>|<span data-ttu-id="98632-217">Удаляет зашифрованные данные для указанного приложения службы Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="98632-217">Delete the encrypted data for the specified Reporting Services service application.</span></span>|  
|<span data-ttu-id="98632-218">Backup-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="98632-218">Backup-SPRSEncryptionKey</span></span>|<span data-ttu-id="98632-219">Создает резервную копию ключа шифрования для указанного приложения службы Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="98632-219">Backs up the encryption key for the specified Reporting Services service application.</span></span>|  
|<span data-ttu-id="98632-220">New-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="98632-220">New-SPRSExtension</span></span>|<span data-ttu-id="98632-221">Регистрирует новый модуль для работы с приложением службы Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="98632-221">Registers a new extension with a Reporting Services service application.</span></span>|  
|<span data-ttu-id="98632-222">Set-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="98632-222">Set-SPRSExtension</span></span>|<span data-ttu-id="98632-223">Задает свойства существующего модуля служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="98632-223">Sets the properties of an existing Reporting Services extension.</span></span>|  
|<span data-ttu-id="98632-224">Remove-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="98632-224">Remove-SPRSExtension</span></span>|<span data-ttu-id="98632-225">Удаляет модуль из приложения службы Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="98632-225">Removes an extension from a Reporting Services service application.</span></span>|  
|<span data-ttu-id="98632-226">Get-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="98632-226">Get-SPRSExtension</span></span>|<span data-ttu-id="98632-227">Возвращает одно или несколько расширений служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] для приложения службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98632-227">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] extensions for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span><br /><br /> <span data-ttu-id="98632-228">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="98632-228">Valid values are:</span></span><br /><br /> <span data-ttu-id="98632-229">**Доставка**</span><span class="sxs-lookup"><span data-stu-id="98632-229">**Delivery**</span></span><br /><br /> <span data-ttu-id="98632-230">**DeliveryUI**</span><span class="sxs-lookup"><span data-stu-id="98632-230">**DeliveryUI**</span></span><br /><br /> <span data-ttu-id="98632-231">**Прорисовка**</span><span class="sxs-lookup"><span data-stu-id="98632-231">**Render**</span></span><br /><br /> <span data-ttu-id="98632-232">**Data**</span><span class="sxs-lookup"><span data-stu-id="98632-232">**Data**</span></span><br /><br /> <span data-ttu-id="98632-233">**Безопасность**</span><span class="sxs-lookup"><span data-stu-id="98632-233">**Security**</span></span><br /><br /> <span data-ttu-id="98632-234">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="98632-234">**Authentication**</span></span><br /><br /> <span data-ttu-id="98632-235">**EventProcessing**</span><span class="sxs-lookup"><span data-stu-id="98632-235">**EventProcessing**</span></span><br /><br /> <span data-ttu-id="98632-236">**ReportItems**</span><span class="sxs-lookup"><span data-stu-id="98632-236">**ReportItems**</span></span><br /><br /> <span data-ttu-id="98632-237">**Designer**</span><span class="sxs-lookup"><span data-stu-id="98632-237">**Designer**</span></span><br /><br /> <span data-ttu-id="98632-238">**ReportItemDesigner**</span><span class="sxs-lookup"><span data-stu-id="98632-238">**ReportItemDesigner**</span></span><br /><br /> <span data-ttu-id="98632-239">**ReportItemConverter**</span><span class="sxs-lookup"><span data-stu-id="98632-239">**ReportItemConverter**</span></span><br /><br /> <span data-ttu-id="98632-240">**ReportDefinitionCustomization**</span><span class="sxs-lookup"><span data-stu-id="98632-240">**ReportDefinitionCustomization**</span></span>|  
|<span data-ttu-id="98632-241">Get-SPRSSite</span><span class="sxs-lookup"><span data-stu-id="98632-241">Get-SPRSSite</span></span>|<span data-ttu-id="98632-242">Возвращает сайты SharePoint с учетом того, включена ли на них функция «ReportingService».</span><span class="sxs-lookup"><span data-stu-id="98632-242">Gets the SharePoint sites based on whether the "ReportingService" feature is enabled.</span></span> <span data-ttu-id="98632-243">По умолчанию возвращаются сайты, на которых включена функция «ReportingService».</span><span class="sxs-lookup"><span data-stu-id="98632-243">By default, sites that enable the "ReportingService" feature are returned.</span></span>|  
  
##  <a name="basic-samples"></a><a name="bkmk_basic_samples"></a><span data-ttu-id="98632-244">Основные примеры</span><span class="sxs-lookup"><span data-stu-id="98632-244">Basic Samples</span></span>  
 <span data-ttu-id="98632-245">Возвращает список командлетов, содержащих в названии строку "SPRS".</span><span class="sxs-lookup"><span data-stu-id="98632-245">Return a list of cmdlets that contain 'SPRS' in the name.</span></span> <span data-ttu-id="98632-246">Это будет полный список [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] командлетов.</span><span class="sxs-lookup"><span data-stu-id="98632-246">This will be the full list of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] cmdlets.</span></span>  
  
```powershell
Get-command -noun *SPRS*  
```  
  
 <span data-ttu-id="98632-247">Или (немного более подробно) перенаправлены в текстовый файл с именем commandlist.txt</span><span class="sxs-lookup"><span data-stu-id="98632-247">Or with a little more detail, piped to a text file named commandlist.txt</span></span>  
  
```powershell
Get-Command -Noun *SPRS* | Select name, definition | Format-List | Out-File c:\commandlist.txt  
```  
  
 <span data-ttu-id="98632-248">Установка службы SharePoint [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] и прокси-сервера службы.</span><span class="sxs-lookup"><span data-stu-id="98632-248">Install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint service and service proxy.</span></span>  
  
```powershell
Install-SPRSService  
```  
  
```powershell
Install-SPRSServiceProxy  
```  
  
 <span data-ttu-id="98632-249">Запуск служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98632-249">Start the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service</span></span>  
  
```powershell
Get-SPServiceInstance -all | where {$_.TypeName -like "SQL Server Reporting*"} | Start-SPServiceInstance  
```  
  
 <span data-ttu-id="98632-250">Введите следующую команду в консоли управления SharePoint, чтобы получить из файла журнала отфильтрованный список строк.</span><span class="sxs-lookup"><span data-stu-id="98632-250">Type the following command from the SharePoint Management Shell to return a filtered list of rows from the a log file.</span></span> <span data-ttu-id="98632-251">Команда отфильтрует строки, содержащие подстроку "ssrscustomactionerror".</span><span class="sxs-lookup"><span data-stu-id="98632-251">The command will filter for lines that contain "ssrscustomactionerror".</span></span> <span data-ttu-id="98632-252">В этом примере рассматривается файл журнала, созданный при установке rssharepoint.msi.</span><span class="sxs-lookup"><span data-stu-id="98632-252">This example is looking at the log file created when the rssharepoint.msi was installed.</span></span>  
  
```powershell
Get-Content -Path C:\Users\testuser\AppData\Local\Temp\rs_sp_0.log | Select-String "ssrscustomactionerror"  
```  
  
##  <a name="detailed-samples"></a><a name="bkmk_detailedsamples"></a><span data-ttu-id="98632-253">Подробные примеры</span><span class="sxs-lookup"><span data-stu-id="98632-253">Detailed Samples</span></span>  
 <span data-ttu-id="98632-254">В дополнение к следующим примерам см. раздел «сценарий Windows PowerShell» в разделе [сценарий Windows PowerShell для шагов 1-4](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md#bkmk_full_script).</span><span class="sxs-lookup"><span data-stu-id="98632-254">In addition to the following samples, see the section "Windows PowerShell Script" in the topic [Windows PowerShell script for Steps 1-4](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md#bkmk_full_script).</span></span>  
  
###  <a name="create-a-reporting-services-service-application-and-proxy"></a><a name="bkmk_example_create_service_application"></a><span data-ttu-id="98632-255">Создание приложения службы Reporting Services и прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="98632-255">Create a Reporting Services service application and proxy</span></span>  
 <span data-ttu-id="98632-256">Этот пример скрипта выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="98632-256">This sample script completes the following tasks:</span></span>  
  
1.  <span data-ttu-id="98632-257">Создайте приложение службы Reporting Services и прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="98632-257">Create a Reporting Services service application and proxy.</span></span> <span data-ttu-id="98632-258">В скрипте предполагается, что пул приложений "My App Pool" уже существует.</span><span class="sxs-lookup"><span data-stu-id="98632-258">The script assumes the application pool "My App Pool" already exists.</span></span>  
  
2.  <span data-ttu-id="98632-259">Добавьте прокси-сервер в группу прокси-серверов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="98632-259">Add the proxy to the default proxy group</span></span>  
  
3.  <span data-ttu-id="98632-260">Предоставьте приложению службы доступ к порту 80 базы данных содержимого веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="98632-260">Grant the service app access to the port 80 web app's content database.</span></span> <span data-ttu-id="98632-261">В скрипте предполагается, что сайт " http://sitename " уже существует.</span><span class="sxs-lookup"><span data-stu-id="98632-261">The script assumes site "http://sitename" already exists.</span></span>  
  
```powershell
# Create service application and service application proxy  
$appPool = Get-SPServiceApplicationPool "My App Pool"  
$serviceApp = New-SPRSServiceApplication "My RS Service App" -ApplicationPool $appPool  
$serviceAppProxy = New-SPRSServiceApplicationProxy -Name "My RS Service App Proxy" -ServiceApplication $serviceApp  
  
# Add service application proxy to default proxy group.  Any web application that uses the default proxy group will now be able to use this service application.  
Get-SPServiceApplicationProxyGroup -default | Add-SPServiceApplicationProxyGroupMember -Member $serviceAppProxy  
  
# Grant application pool account access to the port 80 web application's content database.  
$webApp = Get-SPWebApplication "http://sitename"  
$appPoolAccountName = $appPool.ProcessAccount.LookupName()  
$webApp.GrantAccessToProcessIdentity($appPoolAccountName)
```  
  
###  <a name="review-and-update-a-reporting-services-delivery-extension"></a><a name="bkmk_example_delivery_extension"></a><span data-ttu-id="98632-262">Проверка и обновление модуля доставки Reporting Services</span><span class="sxs-lookup"><span data-stu-id="98632-262">Review and update a Reporting Services delivery extension</span></span>  
 <span data-ttu-id="98632-263">Следующий пример скрипта PowerShell показывает обновление конфигурации модуля доставки электронной почты сервера отчетов для приложения службы с именем `My RS Service App`.</span><span class="sxs-lookup"><span data-stu-id="98632-263">The following PowerShell script example, updates the configuration for the report server e-mail delivery extension for the service application named `My RS Service App`.</span></span> <span data-ttu-id="98632-264">Измените значения для SMTP-сервера (`<email server name>`) и псевдонима FROM электронной почты (`<your FROM email address>`).</span><span class="sxs-lookup"><span data-stu-id="98632-264">Update the values for the SMTP server (`<email server name>`) and the FROM email alias (`<your FROM email address>`).</span></span>  
  
```powershell
$app = Get-SPRSServiceApplication -Name "My RS Service App"  
$emailCfg = Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml
$emailXml = [xml]$emailCfg
$emailXml.SelectSingleNode("//SMTPServer").InnerText = "<email server name>"  
$emailXml.SelectSingleNode("//SendUsing").InnerText = "2"  
$emailXml.SelectSingleNode("//SMTPAuthenticate").InnerText = "2"  
$emailXml.SelectSingleNode("//From").InnerText = '<your FROM email address>'  
Set-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" -ExtensionConfiguration $emailXml.OuterXml  
```  
  
 <span data-ttu-id="98632-265">В приведенном выше примере, если точное имя приложения службы не известно, можно было изменить первую инструкцию таким образом, чтобы имя приложения службы возвращалось на основе поиска фрагмента имени.</span><span class="sxs-lookup"><span data-stu-id="98632-265">In the above example if you did not know the exact name of the service application, you could rewrite the first statement to get the service application based on a search of the partial name.</span></span> <span data-ttu-id="98632-266">Пример:</span><span class="sxs-lookup"><span data-stu-id="98632-266">For example:</span></span>  
  
```powershell
$app = Get-SPRSServiceApplication | Where {$_.name -like " ssrs_testapp *"}  
```  
  
 <span data-ttu-id="98632-267">Следующий сценарий вернет текущие значения настройки модулю доставки электронной почты сервера отчетов для служебного приложения под именем "Приложения служб Reporting Services".</span><span class="sxs-lookup"><span data-stu-id="98632-267">The following script will return the current configuration values for the report server e-mail delivery extension for the service application named "Reporting Services Application".</span></span> <span data-ttu-id="98632-268">В ходе первого шага производится задание для переменной $app значения, равного объекту приложения службы с именем «Мое приложение служб RS».</span><span class="sxs-lookup"><span data-stu-id="98632-268">The first step sets the value of the variable $app to the object of the service application that has a name of " My RS Service App "</span></span>  
  
 <span data-ttu-id="98632-269">Во второй инструкции запрашивается значение модуля доставки "электронная почта сервера отчетов" для объекта приложения службы в переменной $app и выбрано configurationXML (XML-файлы конфигурации).</span><span class="sxs-lookup"><span data-stu-id="98632-269">The second statement will Get the 'Report Server Email' delivery extension for the service application object in variable $app, and select the configurationXML</span></span>  
  
```powershell
$app = Get-SPRSServiceapplication -Name "Reporting Services Application"  
Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
```  
  
 <span data-ttu-id="98632-270">Вы также можете переписать указанные выше два выражения в одно:</span><span class="sxs-lookup"><span data-stu-id="98632-270">You can also rewrite the above two statements as one:</span></span>  
  
```powershell
Get-SPRSServiceApplication -Name "Reporting Services Application" | Get-SPRSExtension -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
```  
  
###  <a name="get-and-set-properties-of-the-reporting-servicea-application-database-for-example-database-timeout"></a><a name="bkmk_example_db_properties"></a><span data-ttu-id="98632-271">Получение и задание свойств базы данных приложения Reporting Service, например времени ожидания базы данных</span><span class="sxs-lookup"><span data-stu-id="98632-271">Get and set properties of the Reporting Servicea application database, for example database timeout</span></span>  
 <span data-ttu-id="98632-272">Следующий пример сначала возвращает список баз данных и параметров, чтобы вы могли определить guid базы данных (идентификатор), который вы затем предоставите для настройки команды.</span><span class="sxs-lookup"><span data-stu-id="98632-272">The following example first returns a list of the databases and properties so you can determine the database guid (ID) that you then supply to the set command.</span></span> <span data-ttu-id="98632-273">Полный список параметров смотрите в `Get-SPRSDatabase | format-list`.</span><span class="sxs-lookup"><span data-stu-id="98632-273">For a full list of the properties, use `Get-SPRSDatabase | format-list`.</span></span>  
  
```powershell
Get-SPRSDatabase | Select id, querytimeout,connectiontimeout, status, server, ServiceInstance
```  
  
 <span data-ttu-id="98632-274">Следующий пример является примеров вывода.</span><span class="sxs-lookup"><span data-stu-id="98632-274">The following is an example of the output.</span></span> <span data-ttu-id="98632-275">Определите идентификатор для базы данных, которую вы хотите изменить и используйте идентификатор в SET cmdlet.</span><span class="sxs-lookup"><span data-stu-id="98632-275">Determine the ID for the database you want to modify and use the ID in the SET cmdlet.</span></span>  
  
-   `Id                : 56f8d1bc-cb04-44cf-bd41-a873643c5a14`  
  
     `QueryTimeout      : 120`  
  
     `ConnectionTimeout : 15`  
  
     `Status            : Online`  
  
     `Server            : SPServer Name=uetestb01`  
  
     `ServiceInstance   : SPDatabaseServiceInstance`  
  
```powershell
Set-SPRSDatabase -Identity 56f8d1bc-cb04-44cf-bd41-a873643c5a14 -QueryTimeout 300  
```  
  
 <span data-ttu-id="98632-276">Чтобы убедиться в том, что значение установлено, снова запустите GET cmdlet.</span><span class="sxs-lookup"><span data-stu-id="98632-276">To verify the value is set, run the GET cmdlet again.</span></span>  
  
```powershell
Get-SPRSDatabase -Identity 56f8d1bc-cb04-44cf-bd41-a873643c5a14 | Select id, querytimeout,connectiontimeout, status, server, ServiceInstance  
```  
  
###  <a name="list-reporting-services-data-extensions---sharepoint-mode"></a><a name="bkmk_example_list_data_extensions"></a><span data-ttu-id="98632-277">Список расширений данных служб Reporting Services — режим интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="98632-277">List reporting services data extensions - SharePoint mode</span></span>  
 <span data-ttu-id="98632-278">В примере ниже циклически опрашивается каждое приложение службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , выводится список текущих данных модулей обработки для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="98632-278">The following example loops through each [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application and lists the current data extensions for each.</span></span>  
  
```powershell
$apps = Get-SPRSServiceApplication  
foreach ($app in $apps)
{  
Write-host -ForegroundColor "yellow" Service App Name $app.Name  
Get-SPRSExtension -identity $app -ExtensionType "Data" | select name, extensiontype | Format-Table -AutoSize  
}  
```  
  
 <span data-ttu-id="98632-279">**Выходные данные примера:**</span><span class="sxs-lookup"><span data-stu-id="98632-279">**Example output:**</span></span>  
  
-   `Name           ExtensionType`  
  
     `----           -------------`  
  
     `SQL                     Data`  
  
     `SQLAZURE                Data`  
  
     `SQLPDW                  Data`  
  
     `OLEDB                   Data`  
  
     `OLEDB-MD                Data`  
  
     `ORACLE                  Data`  
  
     `ODBC                    Data`  
  
     `XML                     Data`  
  
     `SHAREPOINTLIST          Data`  
  
###  <a name="change-and-list-subscription-owners"></a><a name="bkmk_change_subscription_owner"></a><span data-ttu-id="98632-280">Изменение и перечисление владельцев подписок</span><span class="sxs-lookup"><span data-stu-id="98632-280">Change and list subscription owners</span></span>  
 <span data-ttu-id="98632-281">См. статью [Использование PowerShell для изменения и перечисления Reporting Services владельцев подписок и запуска подписки](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="98632-281">See [Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98632-282">См. также:</span><span class="sxs-lookup"><span data-stu-id="98632-282">See Also</span></span>  
 <span data-ttu-id="98632-283">[Использование PowerShell для изменения и перечисления Reporting Services владельцев подписок и запуска подписки](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="98632-283">[Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md) </span></span>  
 <span data-ttu-id="98632-284">[Контрольный список: использование PowerShell для проверки PowerPivot для SharePoint](https://docs.microsoft.com/analysis-services/instances/install-windows/checklist-use-powershell-to-verify-power-pivot-for-sharepoint) </span><span class="sxs-lookup"><span data-stu-id="98632-284">[CheckList: Use PowerShell to Verify PowerPivot for SharePoint](https://docs.microsoft.com/analysis-services/instances/install-windows/checklist-use-powershell-to-verify-power-pivot-for-sharepoint) </span></span>  
 [<span data-ttu-id="98632-285">Скрипты PowerShell для управления SharePoint CodePlex</span><span class="sxs-lookup"><span data-stu-id="98632-285">CodePlex SharePoint Management PowerShell scripts</span></span>](https://sharepointpsscripts.codeplex.com/)   
