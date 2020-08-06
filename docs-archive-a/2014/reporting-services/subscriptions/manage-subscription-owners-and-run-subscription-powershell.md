---
title: Использование PowerShell для изменения и перечисления Reporting Services владельцев подписок и запуска подписки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0fa6cb36-68fc-4fb8-b1dc-ae4f12bf6ff0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b274dc190d8830a2cf7b55110f15267a00c581e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664685"
---
# <a name="use-powershell-to-change-and-list-reporting-services-subscription-owners-and-run-a-subscription"></a><span data-ttu-id="508b9-102">Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription</span><span class="sxs-lookup"><span data-stu-id="508b9-102">Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription</span></span>
  <span data-ttu-id="508b9-103">Приступая к работе с [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] , вы можете программно передать владение подпиской [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] от одного пользователя другому.</span><span class="sxs-lookup"><span data-stu-id="508b9-103">Starting with [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] you can programmatically transfer the ownership of a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] subscription from one user to another.</span></span> <span data-ttu-id="508b9-104">В этом разделе содержится несколько скриптов Windows PowerShell, которые можно использовать для смены владельца подписки или простого перечисления владельцев.</span><span class="sxs-lookup"><span data-stu-id="508b9-104">This topic provides several Windows PowerShell scripts you can use to change or simply list subscription ownership.</span></span> <span data-ttu-id="508b9-105">В каждом примере содержится образец синтаксиса для собственного режима и режима SharePoint.</span><span class="sxs-lookup"><span data-stu-id="508b9-105">Each sample includes sample syntax for both Native mode and SharePoint mode.</span></span> <span data-ttu-id="508b9-106">После смены владельца подписки подписка будет выполняться в контексте безопасности нового владельца, а в отчете в поле «User!UserID» будет отображаться значение нового владельца.</span><span class="sxs-lookup"><span data-stu-id="508b9-106">After you change the subscription owner, the subscription will then execute in the security context of the new owner, and the User!UserID field in the report will display the value of new owner.</span></span> <span data-ttu-id="508b9-107">Дополнительные сведения об объектной модели вызовов образцов см. в разделе <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span><span class="sxs-lookup"><span data-stu-id="508b9-107">For more information on the object model the PowerShell samples call, see <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span></span>

 <span data-ttu-id="508b9-108">![Содержимое, связанное с PowerShell](../media/rs-powershellicon.jpg "Содержимое, связанное с PowerShell")</span><span class="sxs-lookup"><span data-stu-id="508b9-108">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

||
|-|
|<span data-ttu-id="508b9-109">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] в собственном режиме | [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] в режиме интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="508b9-109">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|

 <span data-ttu-id="508b9-110">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="508b9-110">**In this topic:**</span></span>

-   [<span data-ttu-id="508b9-111">Использование скриптов</span><span class="sxs-lookup"><span data-stu-id="508b9-111">How to use the scripts</span></span>](#bkmk_how_to)

-   [<span data-ttu-id="508b9-112">Скрипт. Вывод списка владельцев всех подписок</span><span class="sxs-lookup"><span data-stu-id="508b9-112">Script: List the ownership of all subscriptions</span></span>](#bkmk_list_ownership_all)

-   [<span data-ttu-id="508b9-113">Скрипт. Вывод списка подписок, принадлежащих конкретному пользователю</span><span class="sxs-lookup"><span data-stu-id="508b9-113">Script: List all subscriptions owned by a specific user</span></span>](#bkmk_list_all_one_user)

-   [<span data-ttu-id="508b9-114">Скрипт. Смена владельца всех подписок, принадлежащих конкретному пользователю</span><span class="sxs-lookup"><span data-stu-id="508b9-114">Script: Change ownership for all subscriptions owned by a specific user</span></span>](#bkmk_change_all)

-   [<span data-ttu-id="508b9-115">Скрипт. Вывод списка всех подписок, связанных с конкретным отчетом</span><span class="sxs-lookup"><span data-stu-id="508b9-115">Script: List all subscriptions associated with a specific report</span></span>](#bkmk_list_for_1_report)

-   [<span data-ttu-id="508b9-116">Скрипт. Смена владельца конкретной подписки</span><span class="sxs-lookup"><span data-stu-id="508b9-116">Script: Change ownership of a specific subscription</span></span>](#bkmk_change_all_1_subscription)

-   [<span data-ttu-id="508b9-117">Скрипт. Запуск (инициация) одной подписки</span><span class="sxs-lookup"><span data-stu-id="508b9-117">Script: Run (fire) a single subscription</span></span>](#bkmk_run_1_subscription)

##  <a name="how-to-use-the-scripts"></a><a name="bkmk_how_to"></a> <span data-ttu-id="508b9-118">Использование скриптов</span><span class="sxs-lookup"><span data-stu-id="508b9-118">How to use the scripts</span></span>

### <a name="permissions"></a><span data-ttu-id="508b9-119">Разрешения</span><span class="sxs-lookup"><span data-stu-id="508b9-119">Permissions</span></span>
 <span data-ttu-id="508b9-120">В этом разделе приводится сводка по уровням разрешений, необходимым для использования каждого метода в собственном режиме и режиме SharePoint [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="508b9-120">This section summarizes the permission levels required to use each of the methods for both Native and SharePoint mode [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="508b9-121">В скриптах, рассматриваемых в этом разделе, используются следующие методы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="508b9-121">The scripts in this topic use the following [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] methods:</span></span>

-   [<span data-ttu-id="508b9-122">Метод ReportingService2010.ListSubscriptions</span><span class="sxs-lookup"><span data-stu-id="508b9-122">ReportingService2010.ListSubscriptions Method</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listsubscriptions.aspx)

-   [<span data-ttu-id="508b9-123">Метод ReportingService2010.ChangeSubscriptionOwner</span><span class="sxs-lookup"><span data-stu-id="508b9-123">ReportingService2010.ChangeSubscriptionOwner Method</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.changesubscriptionowner.aspx)

-   [<span data-ttu-id="508b9-124">ReportingService2010.ListChildren</span><span class="sxs-lookup"><span data-stu-id="508b9-124">ReportingService2010.ListChildren</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listchildren.aspx)

-   <span data-ttu-id="508b9-125">Метод [ReportingService2010.FireEvent](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.fireevent.aspx) используется только в последнем скрипте для запуска конкретной подписки.</span><span class="sxs-lookup"><span data-stu-id="508b9-125">The method [ReportingService2010.FireEvent](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.fireevent.aspx) is only used in the last script to trigger a specific subscription to run.</span></span> <span data-ttu-id="508b9-126">Если использовать этот скрипт не планируется, можно проигнорировать требования к методу FireEvent.</span><span class="sxs-lookup"><span data-stu-id="508b9-126">If you do not plan to use that script you can ignore the permission requirements for the FireEvent method.</span></span>

 <span data-ttu-id="508b9-127">**Собственный режим.**</span><span class="sxs-lookup"><span data-stu-id="508b9-127">**Native mode:**</span></span>

-   <span data-ttu-id="508b9-128">Список подписок: (HYPERLINK " https://technet.microsoft.com/library/microsoft.reportingservices.interfaces.reportoperation.aspx " ReadSubscription в отчете, и пользователь является владельцем подписки) или ReadAnySubscription</span><span class="sxs-lookup"><span data-stu-id="508b9-128">List Subscriptions: ( HYPERLINK "https://technet.microsoft.com/library/microsoft.reportingservices.interfaces.reportoperation.aspx" ReadSubscription on the report AND the user is the subscription owner) OR ReadAnySubscription</span></span>

-   <span data-ttu-id="508b9-129">Изменение подписок: Пользователь должен входить в группу BUILTIN\Administrators</span><span class="sxs-lookup"><span data-stu-id="508b9-129">Change Subscriptions: The user must be a member of the BUILTIN\Administrators group</span></span>

-   <span data-ttu-id="508b9-130">Вывод списка дочерних элементов: Свойства ReadProperties для элемента</span><span class="sxs-lookup"><span data-stu-id="508b9-130">List Children: ReadProperties on Item</span></span>

-   <span data-ttu-id="508b9-131">Вызов события: GenerateEvents (System)</span><span class="sxs-lookup"><span data-stu-id="508b9-131">Fire Event: GenerateEvents (System)</span></span>

 <span data-ttu-id="508b9-132">**Режим интеграции с SharePoint:**</span><span class="sxs-lookup"><span data-stu-id="508b9-132">**SharePoint mode:**</span></span>

-   <span data-ttu-id="508b9-133">Список подписок: ManageAlerts или (HYPERLINK " https://technet.microsoft.com/library/microsoft.sharepoint.spbasepermissions.aspx " CreateAlerts в отчете, и пользователь является владельцем подписки, а подписка является подпиской по времени).</span><span class="sxs-lookup"><span data-stu-id="508b9-133">List Subscriptions: ManageAlerts OR ( HYPERLINK "https://technet.microsoft.com/library/microsoft.sharepoint.spbasepermissions.aspx" CreateAlerts on the report AND the user is the subscription owner and the subscription is a timed subscription).</span></span>

-   <span data-ttu-id="508b9-134">Изменение подписок: ManageWeb</span><span class="sxs-lookup"><span data-stu-id="508b9-134">Change Subscriptions: ManageWeb</span></span>

-   <span data-ttu-id="508b9-135">Вывод списка дочерних элементов: ViewListItems</span><span class="sxs-lookup"><span data-stu-id="508b9-135">List Children: ViewListItems</span></span>

-   <span data-ttu-id="508b9-136">Вызов события: ManageWeb</span><span class="sxs-lookup"><span data-stu-id="508b9-136">Fire Event: ManageWeb</span></span>

 <span data-ttu-id="508b9-137">Дополнительные сведения см. в разделе [Сравнение ролей и задач служб Reporting Services с группами и разрешениями SharePoint](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="508b9-137">For more information, see [Compare Roles and Tasks in Reporting Services to SharePoint Groups and Permissions](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md).</span></span>

### <a name="script-usage"></a><span data-ttu-id="508b9-138">Использование скрипта</span><span class="sxs-lookup"><span data-stu-id="508b9-138">Script usage</span></span>
 <span data-ttu-id="508b9-139">**Создание файлов скрипта (PS1)**</span><span class="sxs-lookup"><span data-stu-id="508b9-139">**Create Script files (.ps1)**</span></span>

1.  <span data-ttu-id="508b9-140">Создайте папку с именем **c:\scripts**.</span><span class="sxs-lookup"><span data-stu-id="508b9-140">Create a folder named **c:\scripts**.</span></span> <span data-ttu-id="508b9-141">Если выбирается другая папка, измените имя папки, используемое в конструкциях синтаксиса командной строки в примере.</span><span class="sxs-lookup"><span data-stu-id="508b9-141">If you choose a different folder then modify the folder name used in the example command line syntax statements.</span></span>

2.  <span data-ttu-id="508b9-142">Для каждого скрипта создайте текстовый файл и сохраните файлы в папку c:\scripts.</span><span class="sxs-lookup"><span data-stu-id="508b9-142">Create a text file for each script and save the files to the c:\scripts folder.</span></span> <span data-ttu-id="508b9-143">При создании файлов PS1 используйте имена из каждого синтаксиса командной строки в примере.</span><span class="sxs-lookup"><span data-stu-id="508b9-143">When you create the .ps1 files, use the name from each example command line syntax.</span></span>

3.  <span data-ttu-id="508b9-144">Откройте окно командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="508b9-144">Open a command prompt with administrative privileges.</span></span>

4.  <span data-ttu-id="508b9-145">С помощью приведенного в каждом примере синтаксиса командной строки выполните каждый скрипт.</span><span class="sxs-lookup"><span data-stu-id="508b9-145">Run each script file, using the sample command line syntax provided with each example.</span></span>

 <span data-ttu-id="508b9-146">**Тестовые среды**</span><span class="sxs-lookup"><span data-stu-id="508b9-146">**Tested environments**</span></span>

 <span data-ttu-id="508b9-147">Скрипты, приведенные в данном разделе, были протестированы в PowerShell версии 3 и со следующими версиями [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="508b9-147">The scripts in this topic were tested on PowerShell version 3 and with the following versions of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]:</span></span>

-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]

-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]

-   [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)]

##  <a name="script-list-the-ownership-of-all-subscriptions"></a><a name="bkmk_list_ownership_all"></a><span data-ttu-id="508b9-148">Скрипт. Вывод списка владельцев всех подписок</span><span class="sxs-lookup"><span data-stu-id="508b9-148">Script: List the ownership of all subscriptions</span></span>
 <span data-ttu-id="508b9-149">Этот скрипт выводит список всех подписок на одной сайте.</span><span class="sxs-lookup"><span data-stu-id="508b9-149">This script lists all of the subscriptions on a site.</span></span> <span data-ttu-id="508b9-150">С помощью этого скрипта можно проверить подключение или проверить путь к отчету и ИД подписки для использования в других скриптах.</span><span class="sxs-lookup"><span data-stu-id="508b9-150">You can use this script to test your connection or to verify the report path and subscription id for use in the other scripts.</span></span> <span data-ttu-id="508b9-151">Этот скрипт упрощает аудит существующих подписок и их владельцев.</span><span class="sxs-lookup"><span data-stu-id="508b9-151">This is also a useful script to simply audit what subscriptions exist and who owns them.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="508b9-152">Синтаксис в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="508b9-152">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions.ps1 "[server]/reportserver" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="508b9-153">Синтаксис режима интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="508b9-153">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions.ps1 "[server]/_vti_bin/reportserver" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="508b9-154">Скрипт</span><span class="sxs-lookup"><span data-stu-id="508b9-154">Script</span></span>

```powershell
# Parameters
#    server   - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)

Param(
    [string]$server,
    [string]$site
   )

$rs2010 += New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site); # use "/" for default native mode site

Write-Host " "
Write-Host "----- $server's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted, Status
```

> [!TIP]
>  <span data-ttu-id="508b9-155">Чтобы проверить URL-адреса сайтов в режиме SharePoint, воспользуйтесь командлетом SharePoint **Get-SPSite**.</span><span class="sxs-lookup"><span data-stu-id="508b9-155">To verify site URLS in SharePoint mode, use the SharePoint cmdlet **Get-SPSite**.</span></span> <span data-ttu-id="508b9-156">Дополнительные сведения см. в статье [Get-SPSite](https://technet.microsoft.com/library/ff607950\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="508b9-156">For more information, see [Get-SPSite](https://technet.microsoft.com/library/ff607950\(v=office.15\).aspx).</span></span>

##  <a name="script-list-all-subscriptions-owned-by-a-specific-user"></a><a name="bkmk_list_all_one_user"></a> <span data-ttu-id="508b9-157">Скрипт. Вывод списка подписок, принадлежащих конкретному пользователю</span><span class="sxs-lookup"><span data-stu-id="508b9-157">Script: List all subscriptions owned by a specific user</span></span>
 <span data-ttu-id="508b9-158">Этот скрипт перечисляет все подписки, принадлежащие конкретному пользователю.</span><span class="sxs-lookup"><span data-stu-id="508b9-158">This script lists all of the subscriptions owned by a specific user.</span></span> <span data-ttu-id="508b9-159">С помощью этого скрипта можно проверить подключение или проверить путь к отчету и ИД подписки для использования в других скриптах.</span><span class="sxs-lookup"><span data-stu-id="508b9-159">You can use this script to test your connection or to verify the report path and subscription id for use in the other scripts.</span></span> <span data-ttu-id="508b9-160">Этот скрипт полезен в случае, если какой-либо сотрудник увольняется из организации и необходимо проверить принадлежащие ему подписки, чтобы в дальнейшем сменить владельца или удалить подписку.</span><span class="sxs-lookup"><span data-stu-id="508b9-160">This script is useful when someone in your organization leaves and you want to verify what subscriptions they owned so you can change the owner or delete the subscription.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="508b9-161">Синтаксис в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="508b9-161">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions4User.ps1 "[Domain]\[user]" "[server]/reportserver" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="508b9-162">Синтаксис режима интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="508b9-162">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions4User.ps1 "[Domain]\[user]"  "[server]/_vti_bin/reportserver" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="508b9-163">Скрипт</span><span class="sxs-lookup"><span data-stu-id="508b9-163">Script</span></span>

```powershell
# Parameters:
#    currentOwner - DOMAIN\USER that owns the subscriptions you wish to change
#    server        - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site        - use "/" for default native mode site
Param(
    [string]$currentOwner,
    [string]$server,
    [string]$site
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site);

Write-Host " "
Write-Host " "
Write-Host "----- $currentOwner's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status | where {$_.owner -eq $currentOwner}
```

##  <a name="script-change-ownership-for-all-subscriptions-owned-by-a-specific-user"></a><a name="bkmk_change_all"></a> <span data-ttu-id="508b9-164">Скрипт. Смена владельца всех подписок, принадлежащих конкретному пользователю</span><span class="sxs-lookup"><span data-stu-id="508b9-164">Script: Change ownership for all subscriptions owned by a specific user</span></span>
 <span data-ttu-id="508b9-165">Этот скрипт меняет владельца подписок, принадлежащих конкретному пользователю параметр нового владельца.</span><span class="sxs-lookup"><span data-stu-id="508b9-165">This script changes the ownership for all subscriptions owned by a specific user to the new owner parameter.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="508b9-166">Синтаксис в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="508b9-166">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ChangeALL_SSRS_SubscriptionOwner.ps1 "[Domain]\current owner]" "[Domain]\[new owner]" "[server]/reportserver"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="508b9-167">Синтаксис режима интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="508b9-167">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ChangeALL_SSRS_SubscriptionOwner.ps1 "[Domain]\{current owner]" "[Domain]\[new owner]" "[server]/_vti_bin/reportserver"
```

### <a name="script"></a><span data-ttu-id="508b9-168">Скрипт</span><span class="sxs-lookup"><span data-stu-id="508b9-168">Script</span></span>

```powershell
# Parameters:
#    currentOwner - DOMAIN\USER that owns the subscriptions you wish to change
#    newOwner      - DOMAIN\USER that will own the subscriptions you wish to change
#    server        - server and instance name (e.g. myserver/reportserver, myserver/reportserver_db2, myserver/_vti_bin/reportserver)

Param(
    [string]$currentOwner,
    [string]$newOwner,
    [string]$server
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$items = $rs2010.ListChildren("/", $true);

$subscriptions = @();

ForEach ($item in $items)
{
    if ($item.TypeName -eq "Report")
    {
        $curRepSubs = $rs2010.ListSubscriptions($item.Path);
        ForEach ($curRepSub in $curRepSubs)
        {
            if ($curRepSub.Owner -eq $currentOwner)
            {
                $subscriptions += $curRepSub;
            }
        }
    }
}

Write-Host " "
Write-Host " "
Write-Host -foregroundcolor "green" "-----  $currentOwner's Subscriptions changing ownership to $newOwner : "
$subscriptions | select SubscriptionID, Owner, Path, Description,  Status  | format-table -AutoSize

ForEach ($sub in $subscriptions)
{
    $rs2010.ChangeSubscriptionOwner($sub.SubscriptionID, $newOwner);
}

$subs2 = @();

ForEach ($item in $items)
{
    if ($item.TypeName -eq "Report")
    {
        $subs2 += $rs2010.ListSubscriptions($item.Path);
    }
}
```

##  <a name="script-list-all-subscriptions-associated-with-a-specific-report"></a><a name="bkmk_list_for_1_report"></a> <span data-ttu-id="508b9-169">Скрипт. Вывод списка всех подписок, связанных с конкретным отчетом</span><span class="sxs-lookup"><span data-stu-id="508b9-169">Script: List all subscriptions associated with a specific report</span></span>
 <span data-ttu-id="508b9-170">Этот скрипт перечисляет все подписки, связанные с конкретным отчетом.</span><span class="sxs-lookup"><span data-stu-id="508b9-170">This script lists all of the subscriptions associated with a specific report.</span></span> <span data-ttu-id="508b9-171">В синтаксисе пути к отчету требуется использовать полный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="508b9-171">The report path syntax is different SharePoint mode which requires a full URL.</span></span> <span data-ttu-id="508b9-172">В примерах синтаксиса в имени отчета указывается только название, содержащее пробел. Поэтому имя отчета следует заключить в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="508b9-172">In the syntax examples, the report name used is "title only", which contains a space and therefore requires the single quotes around the report name.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="508b9-173">Синтаксис в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="508b9-173">Native mode syntax</span></span>

```cmd
powershell c:\scripts\List_SSRS_One_Reports_Subscriptions.ps1 "[server]/reportserver" "'/reports/title only'" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="508b9-174">Синтаксис режима интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="508b9-174">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\List_SSRS_One_Reports_Subscriptions.ps1 "[server]/_vti_bin/reportserver"  "'http://[server]/shared documents/title only.rdl'" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="508b9-175">Скрипт</span><span class="sxs-lookup"><span data-stu-id="508b9-175">Script</span></span>

```powershell
# Parameters:
#    server      - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    reportpath  - path to report in the report server, including report name e.g. /reports/test report >> pass in  "'/reports/title only'"
#    site        - use "/" for default native mode site
Param
(
      [string]$server,
      [string]$reportpath,
      [string]$site
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site);

Write-Host " "
Write-Host " "
Write-Host "----- $reportpath 's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status | where {$_.path -eq $reportpath}
```

##  <a name="script-change-ownership-of-a-specific-subscription"></a><a name="bkmk_change_all_1_subscription"></a> <span data-ttu-id="508b9-176">Скрипт. Смена владельца конкретной подписки</span><span class="sxs-lookup"><span data-stu-id="508b9-176">Script: Change ownership of a specific subscription</span></span>
 <span data-ttu-id="508b9-177">Этот сценарий меняет владельца конкретной подписки.</span><span class="sxs-lookup"><span data-stu-id="508b9-177">This script changes the ownership for a specific subscription.</span></span> <span data-ttu-id="508b9-178">Подписка идентифицируется по SubscriptionID, указанному в скрипте.</span><span class="sxs-lookup"><span data-stu-id="508b9-178">The subscription is identified by the SubscriptionID that you pass into the script.</span></span> <span data-ttu-id="508b9-179">Чтобы определить правильный SubscriptionID, можно воспользоваться одним из скриптов вывода списка подписок.</span><span class="sxs-lookup"><span data-stu-id="508b9-179">You can use one of the list subscription scripts to determine the correct SubscriptionID.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="508b9-180">Синтаксис в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="508b9-180">Native mode syntax</span></span>

```cmd
powershell c:\scripts\Change_SSRS_Owner_One_Subscription.ps1 "[Domain]\[new owner]" "[server]/reportserver" "/" "ac5637a1-9982-4d89-9d69-a72a9c3b3150"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="508b9-181">Синтаксис режима интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="508b9-181">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\Change_SSRS_Owner_One_Subscription.ps1 "[Domain]\[new owner]" "[server]/_vti_bin/reportserver" "http://[server]" "9660674b-f020-453f-b1e3-d9ba37624519"
```

### <a name="script"></a><span data-ttu-id="508b9-182">Скрипт</span><span class="sxs-lookup"><span data-stu-id="508b9-182">Script</span></span>

```powershell
# Parameters:
#    newOwner       - DOMAIN\USER that will own the subscriptions you wish to change
#    server         - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site        - use "/" for default native mode site
#    subscriptionID - guid for the single subscription to change

Param(
    [string]$newOwner,
    [string]$server,
    [string]$site,
    [string]$subscriptionid
   )
$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential;

$subscription += $rs2010.ListSubscriptions($site) | where {$_.SubscriptionID -eq $subscriptionid};

Write-Host " "
Write-Host "----- $subscriptionid's Subscription properties: "
$subscription | select Path, report, Description, SubscriptionID, Owner, Status

$rs2010.ChangeSubscriptionOwner($subscription.SubscriptionID, $newOwner)

#refresh the list
$subscription = $rs2010.ListSubscriptions($site) | where {$_.SubscriptionID -eq $subscriptionid}; # use "/" for default native mode site
Write-Host "----- $subscriptionid's Subscription properties: "
$subscription | select Path, report, Description, SubscriptionID, Owner, Status
```

##  <a name="script-run-fire-a-single-subscription"></a><a name="bkmk_run_1_subscription"></a> <span data-ttu-id="508b9-183">Скрипт. Запуск (инициация) одной подписки</span><span class="sxs-lookup"><span data-stu-id="508b9-183">Script: Run (fire) a single subscription</span></span>
 <span data-ttu-id="508b9-184">Этот скрипт запускает определенную подписку с помощью метода FireEvent.</span><span class="sxs-lookup"><span data-stu-id="508b9-184">This script will run a specific subscription using the FireEvent method.</span></span> <span data-ttu-id="508b9-185">Независимо от настроенного для подписки расписания скрипт запустит подписку немедленно.</span><span class="sxs-lookup"><span data-stu-id="508b9-185">The script will immediately run the subscription regardless of the schedule configured for the subscription.</span></span> <span data-ttu-id="508b9-186">EventType сопоставляется с известным набором событий, которые определены в файле конфигурации сервера отчетов **rsreportserver.config** . Скрипт использует следующий тип событий для стандартных подписок:</span><span class="sxs-lookup"><span data-stu-id="508b9-186">The EventType is matched against the known set of events that are defined in the report server configuration file **rsreportserver.config** The script uses the following event type for standard subscriptions:</span></span>

 `<Event>`

 `<Type>TimedSubscription</Type>`

 `</Event>`

 <span data-ttu-id="508b9-187">Дополнительные сведения о файле конфигурации см. в разделе [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="508b9-187">For more information on the configuration file, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span>

 <span data-ttu-id="508b9-188">Скрипт содержит логику задержки "`Start-Sleep -s 6`", поэтому после запуска события есть небольшой период времени для ввода обновленного состояния в метод ListSubscription.</span><span class="sxs-lookup"><span data-stu-id="508b9-188">The script includes delay logic "`Start-Sleep -s 6`" so there is time after the event fires, for the updated status to be available with the ListSubscription method.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="508b9-189">Синтаксис в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="508b9-189">Native mode syntax</span></span>

```cmd
powershell c:\scripts\FireSubscription.ps1 "[server]/reportserver" $null "70366e82-2d3c-4edd-a216-b97e51e26de9"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="508b9-190">Синтаксис режима интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="508b9-190">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\FireSubscription.ps1 "[server]/_vti_bin/reportserver" "http://[server]" "c3425c72-580d-423e-805a-41cf9799fd25"
```

### <a name="script"></a><span data-ttu-id="508b9-191">Скрипт</span><span class="sxs-lookup"><span data-stu-id="508b9-191">Script</span></span>

```powershell
# Parameters
#    server         - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site           - use $null for a native mode server
#    subscriptionid - subscription guid

Param(
  [string]$server,
  [string]$site,
  [string]$subscriptionid
  )

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
#event type is case sensative to what is in the rsreportserver.config
$rs2010.FireEvent("TimedSubscription",$subscriptionid,$site)

Write-Host " "
Write-Host "----- Subscription ($subscriptionid) status: "
#get list of subscriptions and filter to the specific ID to see the Status and LastExecuted
Start-Sleep -s 6 # slight delay in processing so ListSubscription returns the updated Status and LastExecuted
$subscriptions = $rs2010.ListSubscriptions($site); 
$subscriptions | select Status, Path, report, Description, Owner, SubscriptionID, EventType, lastexecuted | where {$_.SubscriptionID -eq $subscriptionid}
```

## <a name="see-also"></a><span data-ttu-id="508b9-192">См. также:</span><span class="sxs-lookup"><span data-stu-id="508b9-192">See Also</span></span>
 <span data-ttu-id="508b9-193"><xref:ReportService2010.ReportingService2010.ListSubscriptions%2A> <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span><span class="sxs-lookup"><span data-stu-id="508b9-193"><xref:ReportService2010.ReportingService2010.ListSubscriptions%2A> <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span></span> 
 <xref:ReportService2010.ReportingService2010.ListChildren%2A> 
 <xref:ReportService2010.ReportingService2010.FireEvent%2A>
