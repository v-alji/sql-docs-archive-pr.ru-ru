---
title: Установка или удаление надстройки PowerPivot для SharePoint (SharePoint 2013) | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: fe13ce8b-9369-4126-928a-9426f9119424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7df54d11021163167149e5b0c1edd960fee1a2ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729921"
---
# <a name="install-or-uninstall-the-powerpivot-for-sharepoint-add-in-sharepoint-2013"></a><span data-ttu-id="a28a0-102">Установка или удаление надстройки PowerPivot для SharePoint (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="a28a0-102">Install or Uninstall the PowerPivot for SharePoint Add-in (SharePoint 2013)</span></span>
  [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] <span data-ttu-id="a28a0-103">представляет собой набор компонентов сервера приложений и служб, которые обеспечивают доступ к данным [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] в ферме [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a28a0-103">is a collection of application server components and back-end services that provide [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] data access in a [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] farm.</span></span> <span data-ttu-id="a28a0-104">Надстройка [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] для SharePoint (**spPowerpivot.msi**) — это пакет установщика, используемый для установки компонентов сервера приложений.</span><span class="sxs-lookup"><span data-stu-id="a28a0-104">The [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint add-in (**spPowerpivot.msi**) is an installer package used to install the application server components.</span></span>

-   <span data-ttu-id="a28a0-105">Надстройка не требуется для развертываний SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="a28a0-105">The add-in is not required for SharePoint 2010 deployments.</span></span>

-   <span data-ttu-id="a28a0-106">Надстройка не требуется при развертывании в конфигурации с одиночным сервером, на котором установлено программное обеспечение SharePoint 2013 и [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28a0-106">The add-in is not required on a single server deployment that includes SharePoint 2013 and [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="a28a0-107">Компоненты, которые устанавливаются этой надстройкой, включаются при установке сервера [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28a0-107">The components installed by the add-in are included when you install an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] server in SharePoint mode.</span></span> <span data-ttu-id="a28a0-108">Схемы примеров развертывания с надстройкой см. в разделе [топологии развертывания для SQL Server функций бизнес-аналитики в SharePoint](../../../sql-server/install/deployment-topologies-for-sql-server-bi-features-in-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="a28a0-108">For diagrams of example deployments with the add-in, see [Deployment Topologies for SQL Server BI Features in SharePoint](../../../sql-server/install/deployment-topologies-for-sql-server-bi-features-in-sharepoint.md).</span></span>

 <span data-ttu-id="a28a0-109">**Примечание.** В этой статье описывается установка файлов решений [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] и средства настройки [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] для SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="a28a0-109">**Note:** This topic describes installing the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] solution files and [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint 2013 Configuration tool.</span></span> <span data-ttu-id="a28a0-110">После установки ознакомьтесь со следующим разделом, чтобы получить сведения о средстве настройки и дополнительных компонентах, [настройке PowerPivot и развертывании решений &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span><span class="sxs-lookup"><span data-stu-id="a28a0-110">After the installation, see the following topic for information on the configuration tool and additional features, [Configure PowerPivot and Deploy Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span></span>

 <span data-ttu-id="a28a0-111">Дополнительные сведения о том, как загрузить **spPowerPivot.msi**, см. в документации по [Microsoft® SQL Server® 2014 PowerPivot® для Microsoft SharePoint®](https://go.microsoft.com/fwlink/?LinkID=324854).</span><span class="sxs-lookup"><span data-stu-id="a28a0-111">For information on how to download **spPowerPivot.msi**, see [Microsoft® SQL Server® 2014 PowerPivot® for Microsoft SharePoint®](https://go.microsoft.com/fwlink/?LinkID=324854).</span></span>

 <span data-ttu-id="a28a0-112">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="a28a0-112">**In this topic:**</span></span>

-   [<span data-ttu-id="a28a0-113">Фон</span><span class="sxs-lookup"><span data-stu-id="a28a0-113">Background</span></span>](#bkmk_background)

-   [<span data-ttu-id="a28a0-114">Куда устанавливать spPowerPivot.msi?</span><span class="sxs-lookup"><span data-stu-id="a28a0-114">Where to Install spPowerPivot.msi?</span></span>](#bkmk_where_to_install)

-   [<span data-ttu-id="a28a0-115">Требования и необходимые условия</span><span class="sxs-lookup"><span data-stu-id="a28a0-115">Requirements and Prerequisites</span></span>](#bkmk_prereq)

-   [<span data-ttu-id="a28a0-116">Установка PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="a28a0-116">To Install PowerPivot for SharePoint</span></span>](#bkmk_install)

-   [<span data-ttu-id="a28a0-117">Развертывание файлов решения SharePoint с помощью средства настройки PowerPivot для SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="a28a0-117">Deploy the SharePoint Solution Files with the PowerPivot for SharePoint 2013 Configuration Tool</span></span>](#bkmk_deploy_solution)

-   [<span data-ttu-id="a28a0-118">Удаление или восстановление надстройки</span><span class="sxs-lookup"><span data-stu-id="a28a0-118">Uninstall or repair the add-in</span></span>](#bkmk_remove_addin)

##  <a name="background"></a><a name="bkmk_background"></a> <span data-ttu-id="a28a0-119">Историческая справка</span><span class="sxs-lookup"><span data-stu-id="a28a0-119">Background</span></span>

-   <span data-ttu-id="a28a0-120">**Сервер приложений:** [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] в SharePoint 2013 позволяют применять рабочие книги в качестве источников данных, планово обновлять данные, а также использовать панель управления [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a28a0-120">**Application Server:** [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] functionality in SharePoint 2013 includes using workbooks as a data source, scheduled data refresh, and the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] Management Dashboard.</span></span>

     [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)]<span data-ttu-id="a28a0-121">— Это [!INCLUDE[msCoName](../../../includes/msconame-md.md)] установщик Windows пакет (**spPowerpivot.msi**), который развертывает клиентские библиотеки Analysis Services и [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] копирует файлы установки на компьютер.</span><span class="sxs-lookup"><span data-stu-id="a28a0-121">is a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Installer package (**spPowerpivot.msi**) that deploys Analysis Services client libraries and copies [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] installation files to the computer.</span></span> <span data-ttu-id="a28a0-122">Установщик не разворачивает и не настраивает функции [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28a0-122">The installer does not deploy or configure [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] features in SharePoint.</span></span> <span data-ttu-id="a28a0-123">По умолчанию устанавливаются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="a28a0-123">The following components install by default:</span></span>

    -   [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] <span data-ttu-id="a28a0-124">2013. Этот компонент содержит скрипты PowerShell (PS1-файлы), пакеты решения SharePoint (WSP-файлы) и средство настройки [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] 2013 для развертывания [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] в ферме SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="a28a0-124">2013. This component includes PowerShell scripts (.ps1 files), SharePoint solution packages (.wsp), and the [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] 2013 configuration tool to deploy [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] in a SharePoint 2013 farm.</span></span>

    -   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="a28a0-125">Поставщик OLE DB для служб Analysis Services (MSOLAP).</span><span class="sxs-lookup"><span data-stu-id="a28a0-125">OLE DB Provider for Analysis Services (MSOLAP).</span></span>

    -   <span data-ttu-id="a28a0-126">Поставщик данных ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="a28a0-126">ADOMD.NET data provider.</span></span>

    -   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="a28a0-127">Объекты управления аналитикой (AMO-объекты).</span><span class="sxs-lookup"><span data-stu-id="a28a0-127">Analysis Management Objects.</span></span>

-   <span data-ttu-id="a28a0-128">**Серверные службы.** Если для создания книг, содержащих аналитические данные, используется [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] для Excel, то чтобы получать эти данные в серверной среде, необходимо иметь установленные службы Excel с сервером бизнес-аналитики [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , работающим в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28a0-128">**Backend services:** If you use [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for Excel to create workbooks that contain analytical data, you must have Excel Services configured with a BI server running [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode to access that data in a server environment.</span></span> <span data-ttu-id="a28a0-129">Вы можете запустить программу установки SQL Server на компьютере, где установлен SharePoint Server 2013 или на другом компьютере, где нет ПО SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28a0-129">You can run SQL Server Setup on a computer that has SharePoint Server 2013 installed, or on a different computer that has no SharePoint software.</span></span> <span data-ttu-id="a28a0-130">Службы Analysis services нисколько не зависят от SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28a0-130">Analysis Services does not have any dependencies on SharePoint.</span></span>

     <span data-ttu-id="a28a0-131">Дополнительные сведения об установке, отмене установки и настройке серверных служб см. в следующем документе:</span><span class="sxs-lookup"><span data-stu-id="a28a0-131">For more information on installing, uninstalling, and configuring the backend services, see the following:</span></span>

    -   [<span data-ttu-id="a28a0-132">Установка PowerPivot для SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="a28a0-132">PowerPivot for SharePoint 2013 Installation</span></span>](https://docs.microsoft.com/analysis-services/instances/install-windows/install-analysis-services-in-power-pivot-mode)

    -   [<span data-ttu-id="a28a0-133">Удаление PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="a28a0-133">Uninstall PowerPivot for SharePoint</span></span>](../../../sql-server/install/uninstall-power-pivot-for-sharepoint.md)

##  <a name="where-to-install-sppowerpivotmsi"></a><a name="bkmk_where_to_install"></a><span data-ttu-id="a28a0-134">Где можно установить spPowerPivot.msi?</span><span class="sxs-lookup"><span data-stu-id="a28a0-134">Where to Install spPowerPivot.msi?</span></span>
 <span data-ttu-id="a28a0-135">Рекомендуется устанавливать **spPowerPivot.msi** на всех серверах фермы SharePoint, чтобы обеспечить согласованность конфигурации, в том числе на серверы приложений и серверы веб-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a28a0-135">A recommended best practice is to install **spPowerPivot.msi** on all servers in the SharePoint farm for configuration consistency, including application servers and web-front end servers.</span></span> <span data-ttu-id="a28a0-136">В пакет установщика входят поставщики данных служб Analysis Services, а также средство настройки [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a28a0-136">The installer package includes the Analysis Services data providers as well as the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] configuration tool.</span></span> <span data-ttu-id="a28a0-137">При установке **spPowerPivot.msi** вы можете исключить определенные компоненты.</span><span class="sxs-lookup"><span data-stu-id="a28a0-137">When you install **spPowerPivot.msi** you can customize the installation by excluding individual components.</span></span>

 <span data-ttu-id="a28a0-138">**Поставщики данных.** Некоторые технологии SharePoint и SQL Server используют поставщики данных служб Analysis Services, включая службы Excel и PerformancePoint, а также Power View.</span><span class="sxs-lookup"><span data-stu-id="a28a0-138">**Data providers:** Several SharePoint and SQL Server technologies use the Analysis Services data providers including Excel Services, PerformancePoint Services, and Power View.</span></span> <span data-ttu-id="a28a0-139">Установка **spPowerPivot.msi** на всех серверах SharePoint обеспечивает полный набор поставщиков данных служб Analysis Services, а также имеется постоянная возможность подключения к PowerPivot по всей ферме.</span><span class="sxs-lookup"><span data-stu-id="a28a0-139">Installing **spPowerPivot.msi** on all SharePoint servers ensures the full set of Analysis Services data providers and PowerPivot connectivity is consistently available across the farm.</span></span>

> [!NOTE]
>  <span data-ttu-id="a28a0-140">Необходимо установить поставщики данных служб Analysis services на сервере SharePoint 2013 с помощью **spPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-140">You must install the Analysis Services data providers on a SharePoint 2013 server using **spPowerPivot.msi**.</span></span> <span data-ttu-id="a28a0-141">Другие пакеты установщика, доступные в составе пакета дополнительных компонентов [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] , не поддерживаются, поскольку в такие пакеты не входят файлы поддержки SharePoint 2013, которые требуются поставщикам данных для этой среды.</span><span class="sxs-lookup"><span data-stu-id="a28a0-141">Other installer packages available in the [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] Feature Pack are not supported because these packages do not include the SharePoint 2013 support files that the data providers require in this environment.</span></span>

 <span data-ttu-id="a28a0-142">**Средство настройки.** Средство настройки PowerPivot для SharePoint 2013 требуется только на одном из серверов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28a0-142">**Configuration Tool:** The PowerPivot for SharePoint 2013 configuration tool is required on only one of the SharePoint servers.</span></span> <span data-ttu-id="a28a0-143">Однако в многосерверных фермах рекомендуется устанавливать средство настройки по крайней мере на 2 сервера, чтобы обеспечить доступ к средству настройки, даже если один из двух серверов находится вне сети.</span><span class="sxs-lookup"><span data-stu-id="a28a0-143">However a recommended best practice in multi-server farms is to install the configuration tool on at least two servers so you have access to the configuration tool if one of the two servers is offline.</span></span>

##  <a name="requirements-and-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="a28a0-144">Требования и необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="a28a0-144">Requirements and Prerequisites</span></span>

-   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="a28a0-145">SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a28a0-145">SharePoint Server 2013.</span></span>

-   <span data-ttu-id="a28a0-146">**spPowerPivot.msi** подходит только для 64-разрядной версии в соответствии с требованиями к продуктам и технологиям SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28a0-146">**spPowerPivot.msi** is 64-bit only, in accordance with the requirements of SharePoint products and technologies.</span></span>

-   <span data-ttu-id="a28a0-147">Сервер [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] в режиме PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="a28a0-147">A [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] server in PowerPivot mode.</span></span> <span data-ttu-id="a28a0-148">Службы Excel будут использовать экземпляр служб SQL Server Analysis Services в качестве сервера PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="a28a0-148">Excel Services will use the SQL Server Analysis Services instance as a PowerPivot server.</span></span> <span data-ttu-id="a28a0-149">Службы Analysis services могут работать на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a28a0-149">Analysis Services can run on the local or a remote computer.</span></span>

-   <span data-ttu-id="a28a0-150">**Разрешения.** Чтобы установить [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)], текущий пользователь должен иметь права администратора на этом компьютере и быть членом группы администраторов фермы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28a0-150">**Permissions:** To install [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)], the current user is required to be an administrator on the computer and a SharePoint Farm Administrators group.</span></span>

-   <span data-ttu-id="a28a0-151">Дополнительные сведения о [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] требованиях и необходимых компонентах см. в подразделах [требования к оборудованию и программному обеспечению для Analysis Services Server в режиме интеграции с SharePoint &#40;SQL Server 2014&#41;](../../../sql-server/install/hardware-software-requirements-analysis-services-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a28a0-151">For more information on [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] requirements and pre-requisites, go to [Hardware and Software Requirements for Analysis Services Server in SharePoint Mode &#40;SQL Server 2014&#41;](../../../sql-server/install/hardware-software-requirements-analysis-services-server-sharepoint-mode.md).</span></span>

##  <a name="to-install-powerpivot-for-sharepoint"></a><a name="bkmk_install"></a><span data-ttu-id="a28a0-152">Установка PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="a28a0-152">To Install PowerPivot for SharePoint</span></span>
 <span data-ttu-id="a28a0-153">Пакет установщика **spPowerpivot.msi** поддерживает графический пользовательский интерфейс и режим командной строки.</span><span class="sxs-lookup"><span data-stu-id="a28a0-153">The **spPowerpivot.msi** installer package supports both a graphical user interface and a command-line mode.</span></span> <span data-ttu-id="a28a0-154">При использовании этих методов установки необходимо запустить MSI-файл с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="a28a0-154">Both methods of installation require that you run the .msi with administrator privileges.</span></span> <span data-ttu-id="a28a0-155">После установки ознакомьтесь со следующим разделом, чтобы получить сведения о средстве настройки и дополнительных компонентах, [настройке PowerPivot и развертывании решений &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span><span class="sxs-lookup"><span data-stu-id="a28a0-155">After the installation, see the following topic for information on the configuration tool and additional features, [Configure PowerPivot and Deploy Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span></span>

### <a name="user-interface-installation"></a><span data-ttu-id="a28a0-156">Установка с помощью пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="a28a0-156">User interface installation</span></span>
 <span data-ttu-id="a28a0-157">Чтобы установить [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] с помощью графического пользовательского интерфейса, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="a28a0-157">To install [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] with the graphical user interface, complete the following steps:</span></span>

1.  <span data-ttu-id="a28a0-158">Запустите **SpPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-158">Run **SpPowerPivot.msi**.</span></span>

2.  <span data-ttu-id="a28a0-159">На странице приветствия нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-159">Click **Next** on the Welcome page.</span></span>

3.  <span data-ttu-id="a28a0-160">Прочитайте и примите лицензионное соглашение, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-160">Review and accept the license agreement, then click **Next**.</span></span>

4.  <span data-ttu-id="a28a0-161">На странице **Выбор компонентов** все компоненты выбраны по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a28a0-161">On the **Feature Selection** page, all of the features are selected by default.</span></span>

5.  <span data-ttu-id="a28a0-162">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-162">Click **Next**.</span></span>

6.  <span data-ttu-id="a28a0-163">Нажмите **Установить** , чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="a28a0-163">Click **Install** to install to finish the installation.</span></span>

### <a name="command-line-installation"></a><span data-ttu-id="a28a0-164">Установка из командной строки</span><span class="sxs-lookup"><span data-stu-id="a28a0-164">Command Line Installation</span></span>
 <span data-ttu-id="a28a0-165">Для установки из командной строки откройте командную строку с правами администратора, а затем запустите **spPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-165">For a command-line installation, open a command prompt with administrative permissions, and then run the **spPowerPivot.msi**.</span></span> <span data-ttu-id="a28a0-166">Пример:</span><span class="sxs-lookup"><span data-stu-id="a28a0-166">For example:</span></span>

 <span data-ttu-id="a28a0-167">`Msiexec.exe /i SpPowerPivot.msi`.</span><span class="sxs-lookup"><span data-stu-id="a28a0-167">`Msiexec.exe /i SpPowerPivot.msi`.</span></span>

 <span data-ttu-id="a28a0-168">Чтобы создать журнал установки, можно использовать стандартные переключатели ведения журнала MsiExec.</span><span class="sxs-lookup"><span data-stu-id="a28a0-168">To create an installation log, use the standard MsiExec logging switches.</span></span> <span data-ttu-id="a28a0-169">В следующем примере создается файл журнала "Install_Log.txt" с помощью параметра подробного ведения журнала "v".</span><span class="sxs-lookup"><span data-stu-id="a28a0-169">The following example creates the log file "Install_Log.txt" using the "v" verbose logging switch.</span></span>

```cmd
Msiexec.exe /i SpPowerPivot.msi /L v c:\test\Install_Log.txt
```

### <a name="quiet-command-line-installation-for-scripting"></a><span data-ttu-id="a28a0-170">Автоматическая установка из командной строки для создания скрипта</span><span class="sxs-lookup"><span data-stu-id="a28a0-170">Quiet Command Line Installation for scripting</span></span>
 <span data-ttu-id="a28a0-171">Можно использовать параметры **/q** или **/quiet** для автоматической установки без отображения диалоговых окон и предупреждений.</span><span class="sxs-lookup"><span data-stu-id="a28a0-171">You can use the **/q** or **/quiet** switches for a "quiet" installation that will not display any dialogs or warnings.</span></span> <span data-ttu-id="a28a0-172">Автоматическая установка удобна, если установку надстройки нужно выполнить из скрипта.</span><span class="sxs-lookup"><span data-stu-id="a28a0-172">The quiet installation is useful if you want to script the installation of the add-in.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="a28a0-173">При использовании параметра **/q** для автоматической установки из командной строки условия лицензионного соглашения не отображаются.</span><span class="sxs-lookup"><span data-stu-id="a28a0-173">If you use the **/q** switch for a silent command line installation, the end-user license agreement will not be displayed.</span></span> <span data-ttu-id="a28a0-174">Независимо от метода установки, использование программного обеспечения регулируется лицензионным соглашением и пользователь несет ответственность за его соблюдение.</span><span class="sxs-lookup"><span data-stu-id="a28a0-174">Regardless of the installation method, the use of this software is governed by a license agreement and you are responsible for complying with the license agreement.</span></span>

#### <a name="to-perform-a-quiet-installation"></a><span data-ttu-id="a28a0-175">Выполнение автоматической установки</span><span class="sxs-lookup"><span data-stu-id="a28a0-175">To perform a quiet installation</span></span>

1.  <span data-ttu-id="a28a0-176">Откройте командную строку **с разрешениями администратора**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-176">Open a command prompt **with administrator permissions**.</span></span>

2.  <span data-ttu-id="a28a0-177">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a28a0-177">Run the following command:</span></span>

    ```cmd
    Msiexec.exe /i spPowerPivot.msi /q
    ```

### <a name="command-line-installation-to-include-specific-components"></a><span data-ttu-id="a28a0-178">Установка из командной строки для включения определенных компонентов</span><span class="sxs-lookup"><span data-stu-id="a28a0-178">Command Line Installation to include specific components</span></span>
 <span data-ttu-id="a28a0-179">Нет необходимости в средстве настройки [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] на каждом сервере SharePoint, однако рекомендуется установить этот компонент как минимум на двух серверах, чтобы он был доступен в нужный момент.</span><span class="sxs-lookup"><span data-stu-id="a28a0-179">The [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration tool is not required on every SharePoint server, however it is recommended to install it on at least two servers so the configuration tool is available when you need it.</span></span>

 <span data-ttu-id="a28a0-180">При установке spPowerPivot.msi вы можете использовать командную строку для установки конкретных элементов, например поставщиков данных, и не устанавливать средство настройки [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a28a0-180">When you install the spPowerPivot.msi, you can use the command line options to install specific items, such as the data providers and not the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration tool.</span></span> <span data-ttu-id="a28a0-181">Следующая командная строка представляет собой пример установки всех компонентов, кроме средства настройки.</span><span class="sxs-lookup"><span data-stu-id="a28a0-181">The following command line is an example of installing all components except the configuration tool:</span></span>

```
Msiexec /i spPowerPivot.msi AGREETOLICENSE="yes" ADDLOCAL=" SQL_OLAPDM,SQL_ADOMD,SQL_AMO,SQLAS_SP_Common"
```

|<span data-ttu-id="a28a0-182">Параметр</span><span class="sxs-lookup"><span data-stu-id="a28a0-182">Option</span></span>|<span data-ttu-id="a28a0-183">Описание</span><span class="sxs-lookup"><span data-stu-id="a28a0-183">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="a28a0-184">Analysis_Server_SP_addin</span><span class="sxs-lookup"><span data-stu-id="a28a0-184">Analysis_Server_SP_addin</span></span>|<span data-ttu-id="a28a0-185">Настройка PowerPivot</span><span class="sxs-lookup"><span data-stu-id="a28a0-185">PowerPivot Configuration</span></span>|
|<span data-ttu-id="a28a0-186">SQL_OLAPDM</span><span class="sxs-lookup"><span data-stu-id="a28a0-186">SQL_OLAPDM</span></span>|<span data-ttu-id="a28a0-187">MSOLAP</span><span class="sxs-lookup"><span data-stu-id="a28a0-187">MSOLAP</span></span>|
|<span data-ttu-id="a28a0-188">SQL_ADOMD</span><span class="sxs-lookup"><span data-stu-id="a28a0-188">SQL_ADOMD</span></span>|<span data-ttu-id="a28a0-189">Поставщик ADOMD.net</span><span class="sxs-lookup"><span data-stu-id="a28a0-189">ADOMD.net provider</span></span>|
|<span data-ttu-id="a28a0-190">SQL_AMO</span><span class="sxs-lookup"><span data-stu-id="a28a0-190">SQL_AMO</span></span>|<span data-ttu-id="a28a0-191">Поставщик AMO</span><span class="sxs-lookup"><span data-stu-id="a28a0-191">AMO provider</span></span>|
|<span data-ttu-id="a28a0-192">SQLAS_SP_Common</span><span class="sxs-lookup"><span data-stu-id="a28a0-192">SQLAS_SP_Common</span></span>|<span data-ttu-id="a28a0-193">Общие компоненты служб Analysis Services для SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="a28a0-193">Analysis Services common components for SharePoint 2013</span></span>|

##  <a name="deploy-the-sharepoint-solution-files-with-the-powerpivot-for-sharepoint-2013-configuration-tool"></a><a name="bkmk_deploy_solution"></a><span data-ttu-id="a28a0-194">Развертывание файлов решения SharePoint с помощью средства настройки PowerPivot для SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="a28a0-194">Deploy the SharePoint Solution Files with the PowerPivot for SharePoint 2013 Configuration Tool</span></span>
 <span data-ttu-id="a28a0-195">Три из скопированных на жесткий диск файлов программой spPowerPivot.msi являются файлами решения SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28a0-195">Three of the files copied to the hard drive by spPowerPivot.msi are SharePoint solution files.</span></span> <span data-ttu-id="a28a0-196">Область одного файла решения — уровень фермы, а область другого файла — уровень веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="a28a0-196">The scope of one solution file is the Web application level while the scope of the other files is the farm level.</span></span> <span data-ttu-id="a28a0-197">Это относится к следующим файлам:</span><span class="sxs-lookup"><span data-stu-id="a28a0-197">The files are the following:</span></span>

-   `PowerPivotFarmSolution.wsp`

-   `PowerPivotFarm14Solution.wsp`

-   `PowerPivotWebApplicationSolution.wsp`

 <span data-ttu-id="a28a0-198">Файлы решений копируются в следующую папку:</span><span class="sxs-lookup"><span data-stu-id="a28a0-198">The solution files are copied to the following folder:</span></span>

 `C:\Program Files\Microsoft SQL Server\120\Tools\PowerPivotTools\SPAddinConfiguration\Resources`

 <span data-ttu-id="a28a0-199">После установки MSI-файла запустите средство настройки [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] для настройки и развертывания решений в ферме SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28a0-199">Following the .msi installation, run the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration Tool to configure and deploy the solutions in the SharePoint farm.</span></span>

### <a name="to-start-the-configuration-tool"></a><span data-ttu-id="a28a0-200">Запуск средства настройки</span><span class="sxs-lookup"><span data-stu-id="a28a0-200">To start the configuration tool</span></span> 

 <span data-ttu-id="a28a0-201">На начальном экране Windows введите "Power" и в результатах поиска приложений щелкните **PowerPivot для SharePoint конфигурации 2013**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-201">From the Windows Start screen type "power" and in the Apps search results, click **PowerPivot for SharePoint 2013 Configuration**.</span></span> <span data-ttu-id="a28a0-202">Обратите внимание, что результаты поиска могут включать две ссылки, поскольку программа установки [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] устанавливает отдельное средство настройки служб [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] для SharePoint 2010 и SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="a28a0-202">Note that the search results may include two links because [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] setup installs separate [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] configuration tools for SharePoint 2010 and SharePoint 2013.</span></span> <span data-ttu-id="a28a0-203">Убедитесь, что запущен [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] для средства настройки SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="a28a0-203">Make sure you start the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint 2013 Configuration tool.</span></span>

 <span data-ttu-id="a28a0-204">![два средства настройки PowerPivot](../../media/as-powerpivot-configtools-bothicons.gif "два средства настройки PowerPivot")</span><span class="sxs-lookup"><span data-stu-id="a28a0-204">![two powerpivot configuration tools](../../media/as-powerpivot-configtools-bothicons.gif "two powerpivot configuration tools")</span></span>

 <span data-ttu-id="a28a0-205">**Ни**</span><span class="sxs-lookup"><span data-stu-id="a28a0-205">**Or**</span></span>

1.  <span data-ttu-id="a28a0-206">Откройте меню **Пуск**, **Все программы**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-206">Go to **Start**, **All Programs**.</span></span>

2.  <span data-ttu-id="a28a0-207">Выберите **Microsoft SQL Server 2014**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-207">Click **Microsoft SQL Server 2014**.</span></span>

3.  <span data-ttu-id="a28a0-208">Щелкните **Средства настройки**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-208">Click **Configuration Tools**.</span></span>

4.  <span data-ttu-id="a28a0-209">Нажмите **Настройка PowerPivot для SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-209">Click **PowerPivot for SharePoint 2013 Configuration**.</span></span>

 <span data-ttu-id="a28a0-210">Дополнительные сведения о средстве настройки см. в разделе [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a28a0-210">For more information on the configuration tool, see [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span></span>

##  <a name="uninstall-or-repair-the-add-in"></a><a name="bkmk_remove_addin"></a><span data-ttu-id="a28a0-211">Удаление или восстановление надстройки</span><span class="sxs-lookup"><span data-stu-id="a28a0-211">Uninstall or repair the add-in</span></span>

> [!CAUTION]
>  <span data-ttu-id="a28a0-212">При удалении **spPowerPivot.msi** удаляются поставщики данных и средства настройки.</span><span class="sxs-lookup"><span data-stu-id="a28a0-212">If you uninstall **spPowerPivot.msi** the data providers and the configuration tool are uninstalled.</span></span> <span data-ttu-id="a28a0-213">Удаление поставщиков данных лишает сервер возможности подключения к PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="a28a0-213">Uninstalling the data providers will cause the server to be unable to connect to PowerPivot.</span></span>

 <span data-ttu-id="a28a0-214">Удалить или восстановить [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] вы можете одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="a28a0-214">You can uninstall or repair [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] using one of the following methods:</span></span>

1.  <span data-ttu-id="a28a0-215">**На панели управления Windows.** Выберите **Microsoft SQL Server 2012 PowerPivot для SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-215">**Windows control panel:** Select **Microsoft SQL Server 2012 PowerPivot for SharePoint 2013**.</span></span> <span data-ttu-id="a28a0-216">Нажмите **Удалить** или **Восстановить**.</span><span class="sxs-lookup"><span data-stu-id="a28a0-216">Click either **Uninstall** or **Repair**.</span></span>

2.  <span data-ttu-id="a28a0-217">Запустите spPowerPivot.msi и выберите параметр **Удалить** или **Восстановить** .</span><span class="sxs-lookup"><span data-stu-id="a28a0-217">Run the spPowerPivot.msi and select the **Remove** option or the **Repair** option.</span></span>

 <span data-ttu-id="a28a0-218">**Из командной строки.** Чтобы восстановить или удалить PowerPivot для SharePoint 2013 с помощью командной строки, откройте ее **с правами администратора** и выполните одну из следующих команд.</span><span class="sxs-lookup"><span data-stu-id="a28a0-218">**Command Line:** To repair or uninstall PowerPivot for SharePoint 2013 using the command line, open a command prompt **with administrator permissions** and run one of the following commands:</span></span>

-   <span data-ttu-id="a28a0-219">Для восстановления выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a28a0-219">To Repair, run the following command:</span></span>

    ```cmd
    msiexec.exe /f spPowerPivot.msi
    ```

 <span data-ttu-id="a28a0-220">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="a28a0-220">OR</span></span>

-   <span data-ttu-id="a28a0-221">Для удаления выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a28a0-221">To uninstall, run the following command:</span></span>

    ```cmd
    msiexec.exe /uninstall spPowerPivot.msi
    ```
