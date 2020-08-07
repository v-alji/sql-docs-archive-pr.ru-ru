---
title: Использование советника по переходу для подготовки к обновлениям | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server]
- upgrading SQL Server, Upgrade Advisor
- upgrading SQL Server, preparing to upgrade
- SQL Server Upgrade Advisor
- analyzing installations for upgrading [SQL Server]
ms.assetid: d85b0833-ddeb-42e3-9397-97ea60d521b7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e53d895cb19a172d0810ae9d6c2bda3406732da1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732258"
---
# <a name="use-upgrade-advisor-to-prepare-for-upgrades"></a><span data-ttu-id="cee01-102">Использование помощника по обновлению для подготовки к обновлениям</span><span class="sxs-lookup"><span data-stu-id="cee01-102">Use Upgrade Advisor to Prepare for Upgrades</span></span>
  <span data-ttu-id="cee01-103">Помощник по обновлению [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] помогает произвести подготовку к обновлениям [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cee01-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor helps you prepare for upgrades to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="cee01-104">Помощник по обновлению анализирует установленные компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и создает отчет, содержащий список проблем, которые должны быть решены перед началом обновления.</span><span class="sxs-lookup"><span data-stu-id="cee01-104">Upgrade Advisor analyzes installed components from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then generates a report that identifies issues to fix either before or after you upgrade.</span></span>  
  
## <a name="how-upgrade-advisor-works"></a><span data-ttu-id="cee01-105">Как работает помощник по обновлению</span><span class="sxs-lookup"><span data-stu-id="cee01-105">How Upgrade Advisor Works</span></span>  
 <span data-ttu-id="cee01-106">После запуска помощника по обновлению появляется его домашняя страница.</span><span class="sxs-lookup"><span data-stu-id="cee01-106">When you run Upgrade Advisor, the Upgrade Advisor Home page appears.</span></span> <span data-ttu-id="cee01-107">С домашней страницы можно запустить следующие средства:</span><span class="sxs-lookup"><span data-stu-id="cee01-107">From the Home page, you can run the following tools:</span></span>  
  
-   <span data-ttu-id="cee01-108">мастер анализа помощника по обновлению;</span><span class="sxs-lookup"><span data-stu-id="cee01-108">Upgrade Advisor Analysis Wizard</span></span>  
  
-   <span data-ttu-id="cee01-109">Средство просмотра отчетов помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="cee01-109">Upgrade Advisor Report Viewer</span></span>  
  
-   <span data-ttu-id="cee01-110">справка помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="cee01-110">Upgrade Advisor Help</span></span>  
  
 <span data-ttu-id="cee01-111">При первом запуске помощника по обновлению следует запустить мастер анализа помощника по обновлению, чтобы проанализировать компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cee01-111">The first time that you use Upgrade Advisor, run the Upgrade Advisor Analysis Wizard to analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="cee01-112">После того как мастер закончит анализ, итоговый отчет можно просмотреть с помощью средства просмотра отчетов помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="cee01-112">When the wizard finishes the analysis, view the resulting reports in the Upgrade Advisor Report Viewer.</span></span> <span data-ttu-id="cee01-113">Каждый отчет предоставляет ссылки на сведения из справки помощника по обновлению, которые помогут исправить или обойти возникшие проблемы.</span><span class="sxs-lookup"><span data-stu-id="cee01-113">Each report provides links to information in Upgrade Advisor Help that will help you fix or reduce the effect of the known issues.</span></span>  
  
## <a name="upgrade-advisor-analysis"></a><span data-ttu-id="cee01-114">Анализ помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="cee01-114">Upgrade Advisor Analysis</span></span>  
 <span data-ttu-id="cee01-115">Помощник по обновлению анализирует следующие компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cee01-115">Upgrade Advisor analyzes the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
 <span data-ttu-id="cee01-116">В ходе анализа проверяются все доступные объекты: скрипты, хранимые процедуры, триггеры и файлы трассировки.</span><span class="sxs-lookup"><span data-stu-id="cee01-116">The analysis examines objects that can be accessed, such as scripts, stored procedures, triggers, and trace files.</span></span> <span data-ttu-id="cee01-117">Помощник по обновлению не производит анализ настольных приложений и зашифрованных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="cee01-117">Upgrade Advisor cannot analyze desktop applications or encrypted stored procedures.</span></span>  
  
 <span data-ttu-id="cee01-118">Результат формируется в виде XML-отчета.</span><span class="sxs-lookup"><span data-stu-id="cee01-118">Output is in the form of an XML report.</span></span> <span data-ttu-id="cee01-119">Просмотреть отчет в формате XML можно с помощью средства просмотра отчетов помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="cee01-119">View the XML report by using the Upgrade Advisor report viewer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cee01-120">Отчеты могут содержать элемент «другие проблемы обновления».</span><span class="sxs-lookup"><span data-stu-id="cee01-120">Reports might contain an "other upgrade issues" item.</span></span> <span data-ttu-id="cee01-121">Этот элемент содержит ссылку на список проблем, которые не были обнаружены помощником по обновлению, но могут присутствовать на сервере или в приложениях.</span><span class="sxs-lookup"><span data-stu-id="cee01-121">This item links to a list of issues that are not detected by Upgrade Advisor, but might exist on your server or in your applications.</span></span> <span data-ttu-id="cee01-122">Необходимо просмотреть этот список и определиться с изменениями, которые необходимо произвести на сервере или в приложениях для исправления этих ошибок.</span><span class="sxs-lookup"><span data-stu-id="cee01-122">You should review the list of undetectable issues and determine whether you must change your server or applications because of the undetectable issues.</span></span>  
  
## <a name="how-to-install-and-run-upgrade-advisor"></a><span data-ttu-id="cee01-123">Установка и запуск помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="cee01-123">How to Install and Run Upgrade Advisor</span></span>  
 <span data-ttu-id="cee01-124">Место установки помощника по обновлению [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] зависит от того, что именно необходимо проанализировать.</span><span class="sxs-lookup"><span data-stu-id="cee01-124">The location where you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor depends on what you will be analyzing.</span></span> <span data-ttu-id="cee01-125">Помощник по обновлению поддерживает удаленный анализ всех поддерживаемых компонентов, за исключением служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cee01-125">Upgrade Advisor supports remote analysis of all supported components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="cee01-126">Если просмотр экземпляров служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] не производится, помощник по обновлению может быть установлен на любой компьютер, который способен подключаться к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и удовлетворяет требованиям к установке помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="cee01-126">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and that meets the Upgrade Advisor prerequisites.</span></span> <span data-ttu-id="cee01-127">Дополнительные сведения см. в статье [Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="cee01-127">For more information, see [Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span></span> <span data-ttu-id="cee01-128">Для просмотра экземпляров служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]следует установить помощник по обновлению на сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="cee01-128">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="cee01-129">Советник по переходу доступен в пакете дополнительных компонентов.</span><span class="sxs-lookup"><span data-stu-id="cee01-129">Upgrade Advisor is available in a feature pack.</span></span>  
  
 <span data-ttu-id="cee01-130">Ниже перечислены предварительные условия для установки и запуска помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="cee01-130">Prerequisites for installing and running Upgrade Advisor are as follows:</span></span>  
  
-   [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] <span data-ttu-id="cee01-131">с пакетом обновления 2 (SP2), Windows 7 с пакетом обновления 1 (SP1) и [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="cee01-131">SP2, Windows 7 SP1, and [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span></span>  
  
-   <span data-ttu-id="cee01-132">Установщик Windows Installer, начиная с версии 4.5.</span><span class="sxs-lookup"><span data-stu-id="cee01-132">Windows Installer beginning with version 4.5.</span></span> <span data-ttu-id="cee01-133">Установщик Windows можно установить с [веб-сайта установщик Windows](https://www.microsoft.com/download/details.aspx?id=8483).</span><span class="sxs-lookup"><span data-stu-id="cee01-133">You can install Windows Installer from the [Windows Installer Web site](https://www.microsoft.com/download/details.aspx?id=8483).</span></span>  
  
-   <span data-ttu-id="cee01-134">Microsoft .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="cee01-134">Microsoft .NET Framework 4.</span></span> <span data-ttu-id="cee01-135">.NET Framework 4 доступно на [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] носителе продукта и на [странице загрузки .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=209895).</span><span class="sxs-lookup"><span data-stu-id="cee01-135">.NET Framework 4 is available on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] product media, and from the [.NET Framework 4 download page](https://go.microsoft.com/fwlink/?LinkId=209895).</span></span>  
  
    -   <span data-ttu-id="cee01-136">Чтобы установить платформу .NET Framework 4 с установочного диска [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], перейдите в корневой каталог диска.</span><span class="sxs-lookup"><span data-stu-id="cee01-136">To install the .NET Framework 4 from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] media, locate the root of the disk drive.</span></span> <span data-ttu-id="cee01-137">Откройте папку «\redist», а затем папку «DotNetFrameworks», после чего запустите файл dotNetFx40_Full_x86_x64.exe (для 32- и 64-разрядных версий операционных систем).</span><span class="sxs-lookup"><span data-stu-id="cee01-137">Then, double-click the \redist folder, double-click the DotNetFrameworks folder, and run dotNetFx40_Full_x86_x64.exe (for 32-bit operating systems or for 64-bit operating systems).</span></span>  
  
 <span data-ttu-id="cee01-138">Чтобы установить помощник по обновлению из веб-узла, нажмите кнопку загрузки на странице загрузки.</span><span class="sxs-lookup"><span data-stu-id="cee01-138">To install Upgrade Advisor from the Web, click the download button on the download page.</span></span> <span data-ttu-id="cee01-139">Затем можно либо сразу начать установку, либо сохранить файл SQLUA.msi для последующего запуска.</span><span class="sxs-lookup"><span data-stu-id="cee01-139">You can then run installation immediately, or save the SQLUA.msi file to run later.</span></span> <span data-ttu-id="cee01-140">При установке с диска продукта запустите SQLUA.msi непосредственно с диска.</span><span class="sxs-lookup"><span data-stu-id="cee01-140">If you are installing from the product disc, run SQLUA.msi directly from the product disk.</span></span>  
  
 <span data-ttu-id="cee01-141">После установки помощника по обновлению его можно открыть из меню " **Пуск** ":</span><span class="sxs-lookup"><span data-stu-id="cee01-141">After you install Upgrade Advisor, you can open it from the **Start** menu:</span></span>  
  
-   <span data-ttu-id="cee01-142">Нажмите кнопку **Пуск**, укажите пункт **все программы**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)] а затем выберите \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] советник по переходу\*\*.</span><span class="sxs-lookup"><span data-stu-id="cee01-142">Click **Start**, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], and then click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor**.</span></span>  
  
 <span data-ttu-id="cee01-143">Дополнительные сведения см. в документации помощника по обновлению, включенной в пакет загрузки, и в заметках о выпуске [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cee01-143">For more information, see the Upgrade Advisor documentation included in the Upgrade Advisor download and the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Release Notes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cee01-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="cee01-144">See Also</span></span>  
 <span data-ttu-id="cee01-145">[Работа с несколькими версиями и экземплярами SQL Server](../../../2014/sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cee01-145">[Work with Multiple Versions and Instances of SQL Server](../../../2014/sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md) </span></span>  
 <span data-ttu-id="cee01-146">[Поддерживаемые обновления версий и выпусков](../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span><span class="sxs-lookup"><span data-stu-id="cee01-146">[Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span></span>  
 [<span data-ttu-id="cee01-147">Обратная совместимость</span><span class="sxs-lookup"><span data-stu-id="cee01-147">Backward Compatibility</span></span>](../../../2014/getting-started/backward-compatibility.md)  
  
  
