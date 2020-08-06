---
title: Установка для SQL Server 2014 | Документация Майкрософт
ms.custom: ''
ms.date: 09/09/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
f1_keywords:
- sql12.portal.Installation.f1
helpviewer_keywords:
- installing SQL Server, initial installation
- installation [SQL Server]
- initial installation [SQL Server]
ms.assetid: edd75f68-dc62-4479-a596-57ce8ad632e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 62630400f276b00de8acfa875244558cdb39e47b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729749"
---
# <a name="installation-for-sql-server-2014"></a><span data-ttu-id="63abe-102">Установка SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="63abe-102">Installation for SQL Server 2014</span></span>
 ## <a name="download-sql-server-2014-express"></a>[<span data-ttu-id="63abe-103">Загрузка SQL Server 2014 Express</span><span class="sxs-lookup"><span data-stu-id="63abe-103">Download SQL Server 2014 Express</span></span>](http://www.hanselman.com/blog/DownloadSQLServerExpress.aspx)
  <span data-ttu-id="63abe-104">**Благодарим вас на [Скотт Hanselman](http://www.hanselman.com/) по сбору всех ссылок на пакеты установщика в одном месте!**</span><span class="sxs-lookup"><span data-stu-id="63abe-104">**Thank you to [Scott Hanselman](http://www.hanselman.com/) for collecting all of the installer package links in one place!**</span></span>
  
  <span data-ttu-id="63abe-105">Мастер установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предоставляет единое дерево компонентов для установки всех компонентов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="63abe-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard provides a single feature tree to install all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
-   [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]  
  
-   [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)]  
  
-   <span data-ttu-id="63abe-106">Средства управления</span><span class="sxs-lookup"><span data-stu-id="63abe-106">Management tools</span></span>  
  
-   <span data-ttu-id="63abe-107">Компоненты соединения</span><span class="sxs-lookup"><span data-stu-id="63abe-107">Connectivity components</span></span>  
  
 <span data-ttu-id="63abe-108">Каждый компонент можно установить отдельно или выбрать сочетания перечисленных выше компонентов.</span><span class="sxs-lookup"><span data-stu-id="63abe-108">You can install each component individually or select a combination of the components listed above.</span></span> <span data-ttu-id="63abe-109">Чтобы оптимально выбрать выпуски и компоненты, доступные в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , см. раздел [выпуски и компоненты SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) и [функции, поддерживаемые различными выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="63abe-109">To make the best choice among the editions and components available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Editions and Components of SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) and [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="63abe-110">Доступны 32-разрядный и 64-разрядный выпуски [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63abe-110">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is available in 32-bit and 64-bit editions.</span></span>
 
 <span data-ttu-id="63abe-111">**Попробуйте:**</span><span class="sxs-lookup"><span data-stu-id="63abe-111">**Try it out:**</span></span>  
  
-   <span data-ttu-id="63abe-112">Есть учетная запись Azure?</span><span class="sxs-lookup"><span data-stu-id="63abe-112">Have an Azure account?</span></span>  <span data-ttu-id="63abe-113">Затем перейдите **[сюда](https://ms.portal.azure.com/?flight=1#create/Microsoft.SQLServer2016RTMEnterpriseWindowsServer2012R2)** , чтобы запустить виртуальную машину с уже установленным SQL Server 2014 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="63abe-113">Then go **[Here](https://ms.portal.azure.com/?flight=1#create/Microsoft.SQLServer2016RTMEnterpriseWindowsServer2012R2)** to spin up a Virtual Machine with SQL Server 2014 Service Pack 1 (SP1) already installed.</span></span> <span data-ttu-id="63abe-114">Дополнительные сведения о SQL Server 2014 (с пакетом обновления 1 (SP1)) см. в разделе [сведения о выпуске SQL Server 2014 SP1](https://support.microsoft.com/kb/3058865).</span><span class="sxs-lookup"><span data-stu-id="63abe-114">For more information on SQL Server 2014 (SP1), see [SQL Server 2014 Service Pack 1 release information](https://support.microsoft.com/kb/3058865).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="63abe-115">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="63abe-115">In This Section</span></span>  
 <span data-ttu-id="63abe-116">Независимо от способа установки служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (с помощью мастера установки или командной строки) программа установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]выполнят следующие три шага:</span><span class="sxs-lookup"><span data-stu-id="63abe-116">Regardless of whether you use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard or the command prompt to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Setup involves the following steps:</span></span>  
  
 [<span data-ttu-id="63abe-117">Планирование установки SQL Server</span><span class="sxs-lookup"><span data-stu-id="63abe-117">Planning a SQL Server Installation</span></span>](../../sql-server/install/planning-a-sql-server-installation.md)  
 <span data-ttu-id="63abe-118">Описывает подготовку компьютера к установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63abe-118">Describes how to prepare your computer for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="63abe-119">Требования к оборудованию и программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="63abe-119">Hardware and software requirements.</span></span>  
  
-   <span data-ttu-id="63abe-120">Требования средства проверки конфигурации и критические препятствия.</span><span class="sxs-lookup"><span data-stu-id="63abe-120">System Configuration Checker requirements and blocking issues.</span></span>  
  
-   <span data-ttu-id="63abe-121">Соображения безопасности.</span><span class="sxs-lookup"><span data-stu-id="63abe-121">Security considerations.</span></span>  
  
 [<span data-ttu-id="63abe-122">Установка SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="63abe-122">Install SQL Server 2014</span></span>](install-sql-server.md)  
 <span data-ttu-id="63abe-123">Описывает параметры установки для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63abe-123">Describes installation options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="63abe-124">Обновление до SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="63abe-124">Upgrade to SQL Server 2014</span></span>](upgrade-sql-server.md)  
 <span data-ttu-id="63abe-125">Описывает параметры обновления для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63abe-125">Describes options for upgrading to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="63abe-126">Удаление SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="63abe-126">Uninstall SQL Server 2014</span></span>](../../sql-server/install/uninstall-sql-server.md)  
 <span data-ttu-id="63abe-127">Описывает процедуры установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63abe-127">Describes procedures to uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span></span>  
  
 [<span data-ttu-id="63abe-128">Установка отказоустойчивого кластера SQL Server</span><span class="sxs-lookup"><span data-stu-id="63abe-128">SQL Server Failover Cluster Installation</span></span>](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md)  
 <span data-ttu-id="63abe-129">В этом разделе документации по программе установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] описывается процедура установки и настройки кластера отработки отказа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63abe-129">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install, and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
 [<span data-ttu-id="63abe-130">Install SQL Server 2014 BI Features</span><span class="sxs-lookup"><span data-stu-id="63abe-130">Install SQL Server 2014 BI Features</span></span>](../../sql-server/install/install-sql-server-business-intelligence-features.md)  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="63abe-131">компоненты, которые являются частью платформы бизнес-аналитики Майкрософт, включают службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]и несколько клиентских приложений, используемых для создания аналитических данных или работы с ними.</span><span class="sxs-lookup"><span data-stu-id="63abe-131">features that are part of the Microsoft BI platform include [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and several client applications used for creating or working with analytical data.</span></span> <span data-ttu-id="63abe-132">В этом разделе документации по программе установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] описывается, как установить службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63abe-132">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="63abe-133">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="63abe-133">Related Sections</span></span>  
 [<span data-ttu-id="63abe-134">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="63abe-134">Installation How-to Topics</span></span>](../../sql-server/install/installation-how-to-topics.md)  
 <span data-ttu-id="63abe-135">В этом разделе приведены ссылки на методические разделы по установке [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью мастера установки, из командной строки, с помощью файлов конфигурации и с помощью программы SysPrep.</span><span class="sxs-lookup"><span data-stu-id="63abe-135">Provides links to procedural topics for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] from the installation wizard, from the command prompt, by using configuration files, and by using SysPrep.</span></span>  
  
 [<span data-ttu-id="63abe-136">Установка SQL Server компонентов бизнес-аналитики с помощью SharePoint &#40;PowerPivot и Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="63abe-136">Install SQL Server BI Features with SharePoint &#40;PowerPivot and Reporting Services&#41;</span></span>](../../sql-server/install/install-sql-server-bi-features-sharepoint-powerpivot-reporting-services.md)  
 <span data-ttu-id="63abe-137">В этом разделе описывается установка компонентов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в среде SharePoint.</span><span class="sxs-lookup"><span data-stu-id="63abe-137">This section explains how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features in a SharePoint environment.</span></span> <span data-ttu-id="63abe-138">В нем указано, какие компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно установить при использовании той или иной версии и выпуска SharePoint.</span><span class="sxs-lookup"><span data-stu-id="63abe-138">It identifies which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features are available given a specific version and edition of SharePoint.</span></span> <span data-ttu-id="63abe-139">В нем также описаны процедуры установки PowerPivot для SharePoint и служб Reporting Services в режиме SharePoint.</span><span class="sxs-lookup"><span data-stu-id="63abe-139">It also includes installation procedures for PowerPivot for SharePoint and Reporting Services in SharePoint mode.</span></span>  
  
 [<span data-ttu-id="63abe-140">Установка образцов кода и образцов баз данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="63abe-140">Installing SQL Server Samples and Sample Databases</span></span>](https://sqlserversamples.codeplex.com/)  
 <span data-ttu-id="63abe-141">Описывает установку и настройку образцов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а также образцов баз данных.</span><span class="sxs-lookup"><span data-stu-id="63abe-141">Describes how to install and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples and sample databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63abe-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="63abe-142">See Also</span></span>  
 <span data-ttu-id="63abe-143">[Новые возможности SQL Server установки](../../sql-server/install/what-s-new-in-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="63abe-143">[What's New in SQL Server Installation](../../sql-server/install/what-s-new-in-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="63abe-144">Требования к аппаратному и программному обеспечению для установки SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="63abe-144">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
