---
title: Установка Reporting Services режиме интеграции с SharePoint и в основном режиме в командной строке | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 048169b3-512c-41e4-895a-0416eff41268
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b2101c40c5136e89d4e30d9551187a2b63672da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728065"
---
# <a name="command-prompt-installation-of-reporting-services-sharepoint-mode-and-native-mode"></a><span data-ttu-id="bab3b-102">Установка режима интеграции с SharePoint и собственного режима для служб Reporting Services из командной строки</span><span class="sxs-lookup"><span data-stu-id="bab3b-102">Command Prompt Installation of Reporting Services SharePoint Mode and Native Mode</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="bab3b-103">поддерживают установку из командной строки с помощью программы установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bab3b-103">supports a command-line installation from the SQL Server setup program.</span></span> <span data-ttu-id="bab3b-104">В этом разделе приведено несколько примеров установки из командной строки, характерных для служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bab3b-104">This topic contains several examples of command-line installations that are specific to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="bab3b-105">Полное описание параметров командной строки, доступных для всех компонентов SQL Server, см. [в разделе Install SQL Server 2014 в командной строке](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="bab3b-105">For a complete description of the command-line options available for all SQL Server components, see [Install SQL Server 2014 from the Command Prompt](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span> <span data-ttu-id="bab3b-106">Параметры командной строки для надстройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] для продуктов SharePoint в этом разделе не описываются.</span><span class="sxs-lookup"><span data-stu-id="bab3b-106">This topic does not describe command-line options for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span> <span data-ttu-id="bab3b-107">Дополнительные сведения об установке этой надстройки из командной строки см. в разделе [Установка надстройки с помощью файла rsSharePoint.msi](install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md#bkmk_install_rssharepoint).</span><span class="sxs-lookup"><span data-stu-id="bab3b-107">For information on command installation of the add-in, see [Install the add-in using the installation file rsSharePoint.msi](install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md#bkmk_install_rssharepoint).</span></span>  
  
 <span data-ttu-id="bab3b-108">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Режим интеграции с SharePoint | [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим</span><span class="sxs-lookup"><span data-stu-id="bab3b-108">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode | [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>  
  
## <a name="rsinstallmode-native-mode"></a><span data-ttu-id="bab3b-109">RSINSTALLMODE (Собственный режим)</span><span class="sxs-lookup"><span data-stu-id="bab3b-109">RSINSTALLMODE (Native Mode)</span></span>  
 <span data-ttu-id="bab3b-110">Главный входной параметр для установки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] — это **/RSINSTALLMODE** .</span><span class="sxs-lookup"><span data-stu-id="bab3b-110">The primary input setting for installing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is the **/RSINSTALLMODE** input setting.</span></span> <span data-ttu-id="bab3b-111">Он имеет два значения: **DefaultNativeMode** и **FilesOnlyMode**</span><span class="sxs-lookup"><span data-stu-id="bab3b-111">The setting has two options: **DefaultNativeMode** and **FilesOnlyMode**</span></span>  
  
 <span data-ttu-id="bab3b-112">Если установка включает компонент SQL Server Database Engine, то по умолчанию RSINSTALLMODE имеет значение DefaultNativeMode. В противном случае параметр RSINSTALLMODE по умолчанию имеет значение FilesOnlyMode. Если выбран режим DefaultNativeMode, но установка не включает компонент SQL Server Database Engine, то параметр RSINSTALLMODE автоматически примет значение FilesOnlyMode.</span><span class="sxs-lookup"><span data-stu-id="bab3b-112">If the installation includes the SQL Server Database engine, the default RSINSTALLMODE is DefaultNativeMode.If the installation does not include the SQL Server Database engine, the default RSINSTALLMODE is FilesOnlyMode.If you choose DefaultNativeMode but the installation does not include the SQL Server Database engine, the installation automatically changes the RSINSTALLMODE to FilesOnlyMode.</span></span> <span data-ttu-id="bab3b-113">Дополнительные сведения о параметрах ввода см. в разделе [Install SQL Server 2014 из командной строки](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="bab3b-113">For more information on the input settings, see [Install SQL Server 2014 from the Command Prompt](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
## <a name="rsshpinstallmode-sharepoint-mode"></a><span data-ttu-id="bab3b-114">RSSHPINSTALLMODE (режим интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="bab3b-114">RSSHPINSTALLMODE (SharePoint Mode)</span></span>  
 <span data-ttu-id="bab3b-115">Входной параметр для установки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в режиме интеграции с SharePoint — это **/RSSHPINSTALLMODE**.</span><span class="sxs-lookup"><span data-stu-id="bab3b-115">The input setting to install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode is **/RSSHPINSTALLMODE**.</span></span> <span data-ttu-id="bab3b-116">Входной параметр имеет одно значение: SharePointFilesOnlyMode.</span><span class="sxs-lookup"><span data-stu-id="bab3b-116">The input setting has one option: SharePointFilesOnlyMode.</span></span> <span data-ttu-id="bab3b-117">Данный параметр дает указание к установке всех файлов, необходимых для режима интеграции с SharePoint, но по завершении процесса установки потребуется настройка.</span><span class="sxs-lookup"><span data-stu-id="bab3b-117">The option installs all the files needed for SharePoint mode but, configuration is required following installation.</span></span> <span data-ttu-id="bab3b-118">Дополнительная настройка осуществляется через центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bab3b-118">The additional configuration steps are completed using SharePoint Central Administration.</span></span> <span data-ttu-id="bab3b-119">Дополнительные сведения см. в статье [Установка служб Reporting Services в режиме SharePoint для SharePoint 2010](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="bab3b-119">For more information, see [Install Reporting Services SharePoint Mode for SharePoint 2010](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span></span>  
  
## <a name="examples-of-sharepoint-mode-installation"></a><span data-ttu-id="bab3b-120">Примеры установки в режиме интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="bab3b-120">Examples of SharePoint Mode Installation</span></span>  
 <span data-ttu-id="bab3b-121">В следующем примере рассматривается установка службы компонента SQL Server Database Engine и служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в режиме интеграции с SharePoint, а также надстройки [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] для SharePoint (RS_SHPWFE).</span><span class="sxs-lookup"><span data-stu-id="bab3b-121">The following example installs SQL Server the database engine service and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode as well as the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint (RS_SHPWFE).</span></span>  
  
```  
setup /q /ACTION=install /FEATURES=SQL, RS_SHP, RS_SHPWFE,TOOLS /INSTANCENAME=MSSQLSERVER /SQLSYSADMINACCOUNTS="BUILTIN\ADMINISTRATORS" /RSSVCACCOUNT="NT AUTHORITY\NETWORK SERVICE" /SQLSVCACCOUNT="NT AUTHORITY\NETWORK SERVICE" /AGTSVCACCOUNT="NT AUTHORITY\NETWORK SERVICE"  
```  
  
 <span data-ttu-id="bab3b-122">В следующем примере рассматривается только установка служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bab3b-122">The following example installs only [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>  
  
```  
Setup.exe /q /ACTION="Install" /IACCEPTSQLSERVERLICENSETERMS /FEATURES="RS_SHP" /INSTANCEDIR="C:\Program Files\Microsoft SQL Server" /INSTALLSHAREDDIR="C:\Program Files\Microsoft SQL Server" /INSTALLSHAREDWOWDIR="C:\Program Files (x86)\Microsoft SQL Server" /INSTALLSQLDATADIR="C:\Program Files\Microsoft SQL Server" /SECURITYMODE="SQL" /SAPWD="*****" /PID="[Your PID Value]" /SQLSYSADMINACCOUNTS="[Account Name]" "AutoSql Admin Group" /ASSYSADMINACCOUNTS="[Account Name]" /UPDATEENABLED="False"  
  
```  
  
 <span data-ttu-id="bab3b-123">В следующем примере рассматривается установка всех компонентов SQL Server, включая службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], как в собственном режиме, так и в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bab3b-123">The following example installs all of the SQL Server features, including both [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode and SharePoint mode.</span></span>  
  
```  
Setup.exe /q /ACTION="Install" /INSTANCENAME="MSSQLSERVER" /FEATURES="SQLEngine,Replication,SNAC,SNAC_SDK,Browser,Writer,AS,IS,MDS,Adv_SSMS,BC,BOL,Conn,SDK,DReplay_CTLR,DReplay_CLT, RS_SHP,RS_SHPWFE,DQC,BIDS,FullText, RS,DQ,SSMS" /INSTANCEDIR="C:\Program Files\Microsoft SQL Server" /INSTALLSHAREDDIR="C:\Program Files\Microsoft SQL Server" /INSTALLSHAREDWOWDIR="C:\Program Files (x86)\Microsoft SQL Server" /INSTALLSQLDATADIR="C:\Program Files\Microsoft SQL Server" /SQLSVCACCOUNT="[Account Name]" /SQLSVCPASSWORD="********" /AGTSVCACCOUNT="[Account Nam]" /AGTSVCPASSWORD="********" /CTLRSVCACCOUNT="[Account Nam]" /CTLRSVCPASSWORD="********" /CLTSVCACCOUNT="[Account Nam]" /CLTSVCPASSWORD="********" /ASSVCACCOUNT="[Account Nam]" /ASSVCPASSWORD="********" /RSSVCACCOUNT="[Account Nam]" /RSSVCPASSWORD="********" /FTSVCACCOUNT="[Account Nam]" /FTSVCPASSWORD="********" /SECURITYMODE="SQL" /SAPWD="********" /PID="[Your PID Value]" /SQLSYSADMINACCOUNTS="[Account Nam]" "AutoSql Admin Group" /ASSYSADMINACCOUNTS="BUILTIN\ADMINISTRATORS" /UPDATEENABLED="False" /IACCEPTSQLSERVERLICENSETERMS /RSSHPINSTALLMODE="SharePointFilesOnlyMode" /RSINSTALLMODE="DefaultNativeMode"  
```  
  
## <a name="examples-of-sharepoint-mode-upgrade"></a><span data-ttu-id="bab3b-124">Примеры обновления режима интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="bab3b-124">Examples of SharePoint Mode Upgrade</span></span>  
 <span data-ttu-id="bab3b-125">В следующем примере выполняется обновление служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bab3b-125">The following example upgrades [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="bab3b-126">**RSUPGRADEPASSWORD** — это пароль существующей учетной записи службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="bab3b-126">**RSUPGRADEPASSWORD** is the password of the existing Report Server service account.</span></span> <span data-ttu-id="bab3b-127">Поле RSUPGRADEPASSWORD является обязательным для обновления, если только учетная запись служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] не является встроенной.</span><span class="sxs-lookup"><span data-stu-id="bab3b-127">RSUPGRADEPASSWORD is a required field in an upgrade scenario unless the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service account is a built-in account.</span></span>  
  
```  
Setup.exe /q /ACTION="Upgrade" /INSTANCENAME="MSSQLSERVER" /PID="[PID value]" /FTSVCACCOUNT="[DOMAIN\ACCOUNT]" /FTSVCPASSWORD="[ACCOUNTPASSSWORD]" /UPDATEENABLED="False" /IACCEPTSQLSERVERLICENSETERMS /RSUPGRADEPASSWORD="******"  
```  
  
 <span data-ttu-id="bab3b-128">Далее приведен пример, с помощью которого можно обновить установку в режиме интеграции с SharePoint, в основе которой лежит архитектура общей службы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bab3b-128">The following example can be used to upgrade a SharePoint Mode installation that is based on the SharePoint shared service architecture.</span></span> <span data-ttu-id="bab3b-129">В этом примере используется параметр ALLOWUPGRADEFORSSRSSHAREPOINTMODE.</span><span class="sxs-lookup"><span data-stu-id="bab3b-129">The example uses switch ALLOWUPGRADEFORSSRSSHAREPOINTMODE.</span></span> <span data-ttu-id="bab3b-130">Этот параметр не требуется для обновления предыдущих версий, не основанных на архитектуре общих служб.</span><span class="sxs-lookup"><span data-stu-id="bab3b-130">The switch is not needed for upgrading older versions that are not based on the shared service architecture:</span></span>  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
```  
Setup.exe /q /ACTION="Upgrade" /INSTANCENAME="MSSQLSERVER" /PID="[Your PID Value]" /FTSVCACCOUNT="[ACCOUNT Name]" /FTSVCPASSWORD="****" /UPDATEENABLED="False" /IACCEPTSQLSERVERLICENSETERMS /ALLOWUPGRADEFORSSRSSHAREPOINTMODE="True"  
```  
  
## <a name="examples-of-native-mode-installation"></a><span data-ttu-id="bab3b-131">Примеры установки в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="bab3b-131">Examples of Native Mode Installation</span></span>  
  
```  
Setup.exe /q /ACTION="Install" /INSTANCENAME="MSSQLSERVER" /FEATURES="SQLEngine,Replication,SNAC,SNAC_SDK,Browser,Writer,AS,IS,MDS,Adv_SSMS,BC,BOL,Conn,SDK,DReplay_CTLR,DReplay_CLT,DQC,BIDS,FullText, RS,DQ,SSMS" /INSTANCEDIR="C:\Program Files\Microsoft SQL Server" /INSTALLSHAREDDIR="C:\Program Files\Microsoft SQL Server" /INSTALLSHAREDWOWDIR="C:\Program Files (x86)\Microsoft SQL Server" /INSTALLSQLDATADIR="C:\Program Files\Microsoft SQL Server" /SQLSVCACCOUNT="[Account Name]" /SQLSVCPASSWORD="********" /AGTSVCACCOUNT="[Account Nam]" /AGTSVCPASSWORD="********" /CTLRSVCACCOUNT="[Account Nam]" /CTLRSVCPASSWORD="********" /CLTSVCACCOUNT="[Account Nam]" /CLTSVCPASSWORD="********" /ASSVCACCOUNT="[Account Nam]" /ASSVCPASSWORD="********" /RSSVCACCOUNT="[Account Nam]" /RSSVCPASSWORD="********" /FTSVCACCOUNT="[Account Nam]" /FTSVCPASSWORD="********" /SECURITYMODE="SQL" /SAPWD="********" /PID="[Your PID Value]" /SQLSYSADMINACCOUNTS="[Account Nam]" "AutoSql Admin Group" /ASSYSADMINACCOUNTS="BUILTIN\ADMINISTRATORS" /UPDATEENABLED="False" /IACCEPTSQLSERVERLICENSETERMS /RSINSTALLMODE="DefaultNativeMode"  
```  
  
## <a name="see-also"></a><span data-ttu-id="bab3b-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="bab3b-132">See Also</span></span>  
 <span data-ttu-id="bab3b-133">[Установка SQL Server 2014 из командной строки](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="bab3b-133">[Install SQL Server 2014 from the Command Prompt](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="bab3b-134">[Параметры SysPrep](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md#SysPrep) </span><span class="sxs-lookup"><span data-stu-id="bab3b-134">[SysPrep Parameters](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md#SysPrep) </span></span>  
 [<span data-ttu-id="bab3b-135">Установка PowerPivot из командной строки</span><span class="sxs-lookup"><span data-stu-id="bab3b-135">Install PowerPivot from the Command Prompt</span></span>](../../sql-server/install/install-powerpivot-from-the-command-prompt.md)  
  
  