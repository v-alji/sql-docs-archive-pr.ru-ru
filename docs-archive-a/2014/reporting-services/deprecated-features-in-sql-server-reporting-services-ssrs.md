---
title: Устаревшие функции в SQL Server Reporting Services в SQL Server 2014 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, backward compatibility
- deprecated features [Reporting Services]
- HTML OWC rendering extension [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: 3876c01e-f81d-4cce-9104-5106a8c369e6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af858ae94bf5ea3d9f0cfe0b99759442dabd6629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664757"
---
# <a name="deprecated-features-in-sql-server-reporting-services-in-sql-server-2014"></a><span data-ttu-id="4e6b8-102">Устаревшие функции служб SQL Server Reporting Services в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4e6b8-102">Deprecated Features in SQL Server Reporting Services in SQL Server 2014</span></span>
  <span data-ttu-id="4e6b8-103">В этом разделе описываются устаревшие функции служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e6b8-103">This topic describes the deprecated [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features.</span></span> <span data-ttu-id="4e6b8-104">Эти функции по-прежнему доступны в выпуске, где они признаны устаревшими, однако запланировано их удаление в следующем выпуске [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e6b8-104">The features are still available in the release in which they are deprecated; however the features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4e6b8-105">Не следует использовать устаревшие функции в новых приложениях.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-105">Deprecated features should not be used in new applications.</span></span>  
  
 <span data-ttu-id="4e6b8-106">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="4e6b8-106">In this topic:</span></span>  
  
-   [<span data-ttu-id="4e6b8-107">Устаревшие функции служб SQL Server 2014 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="4e6b8-107">SQL Server 2014 Reporting Services Deprecated Features</span></span>](#bkmk_2014)  
  
-   [<span data-ttu-id="4e6b8-108">Устаревшие функции служб SQL Server 2012 SP1 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="4e6b8-108">SQL Server 2012 SP1 Reporting Services Deprecated Features</span></span>](#bkmk_2012sp1)  
  
-   [<span data-ttu-id="4e6b8-109">Устаревшие функции служб SQL Server 2012 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="4e6b8-109">SQL Server 2012 Reporting Services Deprecated Features</span></span>](#bkmk_2012)  
  
-   [<span data-ttu-id="4e6b8-110">Устаревшие функции служб SQL Server 2008 R2 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="4e6b8-110">SQL Server 2008 R2 Reporting Services Deprecated Features</span></span>](#bkmk_kj)  
  
##  <a name="sql-server-2014-reporting-services-deprecated-features"></a><a name="bkmk_2014"></a><span data-ttu-id="4e6b8-111">SQL Server 2014 Reporting Services устаревшие функции</span><span class="sxs-lookup"><span data-stu-id="4e6b8-111">SQL Server 2014 Reporting Services Deprecated Features</span></span>  
  
### <a name="features-not-supported-in-the-next-version-of-sql-server"></a><span data-ttu-id="4e6b8-112">Функции, не поддерживаемые в следующей версии SQL Server</span><span class="sxs-lookup"><span data-stu-id="4e6b8-112">Features Not Supported in the Next Version of SQL Server</span></span>  
 <span data-ttu-id="4e6b8-113">Следующие [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] возможности не будут поддерживаться в **следующей** версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e6b8-113">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features will not be supported in the **next** version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4e6b8-114">Не используйте их при работе над новыми приложениями и как можно скорее измените приложения, в которых они в настоящее время используются.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-114">Do not use these features in new development work, and modify applications that currently use these features as soon as possible.</span></span>  
  
#### <a name="html-rendering-extension-device-information-settings"></a><span data-ttu-id="4e6b8-115">Параметры сведений об устройстве для модуля подготовки отчетов в формате HTML</span><span class="sxs-lookup"><span data-stu-id="4e6b8-115">HTML Rendering Extension Device Information Settings</span></span>  
 <span data-ttu-id="4e6b8-116">Следующие параметры сведений об устройстве для модуля подготовки отчетов в формате HTML являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-116">The following device information settings for the HTML rendering extension are deprecated.</span></span>  
  
-   <span data-ttu-id="4e6b8-117">ActionScript</span><span class="sxs-lookup"><span data-stu-id="4e6b8-117">ActionScript</span></span>  
  
-   <span data-ttu-id="4e6b8-118">ActiveXControls</span><span class="sxs-lookup"><span data-stu-id="4e6b8-118">ActiveXControls</span></span>  
  
-   <span data-ttu-id="4e6b8-119">GetImage</span><span class="sxs-lookup"><span data-stu-id="4e6b8-119">GetImage</span></span>  
  
-   <span data-ttu-id="4e6b8-120">OnlyVisibleStyles</span><span class="sxs-lookup"><span data-stu-id="4e6b8-120">OnlyVisibleStyles</span></span>  
  
-   <span data-ttu-id="4e6b8-121">ReplacementRoot</span><span class="sxs-lookup"><span data-stu-id="4e6b8-121">ReplacementRoot</span></span>  
  
-   <span data-ttu-id="4e6b8-122">ResourceStreamRoot</span><span class="sxs-lookup"><span data-stu-id="4e6b8-122">ResourceStreamRoot</span></span>  
  
-   <span data-ttu-id="4e6b8-123">StreamRoot</span><span class="sxs-lookup"><span data-stu-id="4e6b8-123">StreamRoot</span></span>  
  
-   <span data-ttu-id="4e6b8-124">UsePx</span><span class="sxs-lookup"><span data-stu-id="4e6b8-124">UsePx</span></span>  
  
-   <span data-ttu-id="4e6b8-125">Zoom</span><span class="sxs-lookup"><span data-stu-id="4e6b8-125">Zoom</span></span>  
  
 <span data-ttu-id="4e6b8-126">Дополнительные сведения о модуле подготовки отчетов в формате HTML см. в разделе [HTML Device Information Settings](html-device-information-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4e6b8-126">For more information on the HTML rendering extension, see [HTML Device Information Settings](html-device-information-settings.md)</span></span>  
  
#### <a name="microsoft-word-and-microsoft-excel-1997-2003-rendering"></a><span data-ttu-id="4e6b8-127">Подготовка отчетов в формате Microsoft Word и Microsoft Excel 1997-2003</span><span class="sxs-lookup"><span data-stu-id="4e6b8-127">Microsoft Word and Microsoft Excel 1997-2003 Rendering</span></span>  
 <span data-ttu-id="4e6b8-128">Модули подготовки отчетов BIFF8 передается [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[msCoName](../includes/msconame-md.md)] Формат двоичного файла обмена Word и Excel 1997-2003.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-128">The[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] BIFF8 rendering extensions [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Word and [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003 binary interchange file format.</span></span> [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="4e6b8-129">включает расширения, которые отображаются в [!INCLUDE[msCoName](../includes/msconame-md.md)] формате Open XML для Office 2007-2010.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-129">includes extensions that render in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML format.</span></span>  
  
#### <a name="report-definition-language-rdl-2005-and-earlier"></a><span data-ttu-id="4e6b8-130">Язык определения отчетов 2005 и более ранних версий</span><span class="sxs-lookup"><span data-stu-id="4e6b8-130">Report Definition Language (RDL) 2005 and Earlier</span></span>  
 <span data-ttu-id="4e6b8-131">Язык определения отчетов 2005 и более ранних версий считается устаревшим.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-131">Report Definition Language (RDL) 2005 and earlier is deprecated.</span></span> <span data-ttu-id="4e6b8-132">Дополнительные сведения об RDL см. в разделе [язык определения отчетов &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4e6b8-132">For more information about RDL, see [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span></span>  
  
 <span data-ttu-id="4e6b8-133">Дополнительные сведения об обновлении отчетов см. в разделе [Upgrade Reports](install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="4e6b8-133">For more information on upgrading reports, see [Upgrade Reports](install-windows/upgrade-reports.md).</span></span>  
  
#### <a name="sql-server-2005-and-earlier-custom-report-items"></a><span data-ttu-id="4e6b8-134">Пользовательские элементы отчета SQL Server 2005 и более ранних версий</span><span class="sxs-lookup"><span data-stu-id="4e6b8-134">SQL Server 2005 and earlier Custom Report Items</span></span>  
 <span data-ttu-id="4e6b8-135">Пользовательские элементы отчета (CRI), скомпилированные для [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 и более ранних версий, являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-135">Custom Report Items (CRI) compiled for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
#### <a name="reporting-services-snapshots-2005-and-earlier"></a><span data-ttu-id="4e6b8-136">Моментальные снимки служб Reporting Services 2005 и более ранних версий</span><span class="sxs-lookup"><span data-stu-id="4e6b8-136">Reporting Services Snapshots 2005 and earlier</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="4e6b8-137">моментальные снимки, отображаемые с [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 и более ранних версий, являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-137">snapshots rendered with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
#### <a name="report-models"></a><span data-ttu-id="4e6b8-138">Модели отчетов</span><span class="sxs-lookup"><span data-stu-id="4e6b8-138">Report Models</span></span>  
 <span data-ttu-id="4e6b8-139">Модели отчетов на языке семантического моделирования (SMDL) больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-139">Semantic modeling language (SMDL) report models are deprecated.</span></span> <span data-ttu-id="4e6b8-140">Несмотря на то, что можно продолжать использовать существующие модели отчетов в качестве источников данных в [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] отчетах, рекомендуется обновить отчеты, чтобы удалить зависимость от моделей отчетов.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-140">Although you can you continue to use existing report models as data sources in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports you should consider updating your reports to remove their dependency on report models.</span></span>  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="4e6b8-141">не [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] включает средства для создания или обновления моделей отчетов.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-141">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not include tools for creating or updating report models.</span></span> <span data-ttu-id="4e6b8-142">Дополнительные сведения см. в разделе [критические изменения в SQL Server Reporting Services в SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="4e6b8-142">For more information, see [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span></span>  
  
#### <a name="deprecated-methods-in-the-web-service-endpoint"></a><span data-ttu-id="4e6b8-143">Устаревшие методы в конечной точке веб-службы</span><span class="sxs-lookup"><span data-stu-id="4e6b8-143">Deprecated Methods in the Web Service Endpoint</span></span>  
 <span data-ttu-id="4e6b8-144">В конечной точке веб-службы <xref:ReportService2010.ReportingService2010> устарели следующие операции:</span><span class="sxs-lookup"><span data-stu-id="4e6b8-144">The following operations are deprecated in the <xref:ReportService2010.ReportingService2010> Web service endpoint:</span></span>  
  
-   <xref:ReportService2010.ReportingService2010.GetProperties%2A>  
  
-   <xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>  
  
#### <a name="sharepoint-web-parts"></a><span data-ttu-id="4e6b8-145">Веб-части SharePoint</span><span class="sxs-lookup"><span data-stu-id="4e6b8-145">SharePoint Web Parts</span></span>  
 <span data-ttu-id="4e6b8-146">Установочный CAB-файл **RSWebParts.cab** и веб-части SharePoint, которые можно извлечь из него, являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-146">The installation cabinet file **RSWebParts.cab** and the SharePoint web parts that can be extracted from the cab file, are deprecated.</span></span> <span data-ttu-id="4e6b8-147">Нерекомендуемые веб-части — это Обозреватель отчетов (проверяющий **. dwp**) и средство просмотра отчетов (**рецензент. dwp**).</span><span class="sxs-lookup"><span data-stu-id="4e6b8-147">The deprecated web parts are Report Explorer (**SPExplorer.dwp**) and Report Viewer (**SPViewer.dwp**).</span></span>  
  
 <span data-ttu-id="4e6b8-148">Дополнительные сведения об устаревших веб-частях см. в статье [Просмотр и изучение отчетов в собственном режиме с помощью SharePoint веб-части (службы SSRS)](https://msdn.microsoft.com/library/ms159772.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4e6b8-148">For more information on the deprecated web parts, see [View and Explore Native Mode Reports Using SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span></span>  
  
### <a name="features-not-supported-in-a-future-version-of-sql-server"></a><span data-ttu-id="4e6b8-149">Функции, не поддерживаемые в будущей версии SQL Server</span><span class="sxs-lookup"><span data-stu-id="4e6b8-149">Features Not Supported in a Future Version of SQL Server</span></span>  
 <span data-ttu-id="4e6b8-150">Поддержка приведенных ниже функций компонента [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] в следующей версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]будет сохранена, однако будет удалена в более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-150">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="4e6b8-151">(с какой именно версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , пока не определено).</span><span class="sxs-lookup"><span data-stu-id="4e6b8-151">The specific version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has not been determined.</span></span>  
  
 <span data-ttu-id="4e6b8-152">В [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] отсутствуют устаревшие функции служб [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e6b8-152">No [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features were deprecated in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
##  <a name="sql-server-2012-sp1-reporting-services-deprecated-features"></a><a name="bkmk_2012sp1"></a><span data-ttu-id="4e6b8-153">SQL Server 2012 с пакетом обновления 1 (SP1) Reporting Services устаревшие функции</span><span class="sxs-lookup"><span data-stu-id="4e6b8-153">SQL Server 2012 SP1 Reporting Services Deprecated Features</span></span>  
 <span data-ttu-id="4e6b8-154">В этом разделе описываются функции служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , признанные устаревшими в [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e6b8-154">This section describes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features deprecated in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)].</span></span> <span data-ttu-id="4e6b8-155">Поддержка приведенных ниже функций компонента [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] в следующей версии [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]будет сохранена, однако будет удалена в более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-155">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="4e6b8-156">(с какой именно версии [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , пока не определено).</span><span class="sxs-lookup"><span data-stu-id="4e6b8-156">The specific version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] has not been determined.</span></span>  
  
### <a name="sharepoint-web-parts"></a><span data-ttu-id="4e6b8-157">Веб-части SharePoint</span><span class="sxs-lookup"><span data-stu-id="4e6b8-157">SharePoint Web Parts</span></span>  
 <span data-ttu-id="4e6b8-158">Установочный CAB-файл **RSWebParts.cab** и веб-части SharePoint, которые можно извлечь из него, являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-158">The installation cabinet file **RSWebParts.cab** and the SharePoint web parts that can be extracted from the cab file, are deprecated.</span></span> <span data-ttu-id="4e6b8-159">Нерекомендуемые веб-части — это Обозреватель отчетов (проверяющий **. dwp**) и средство просмотра отчетов (**рецензент. dwp**).</span><span class="sxs-lookup"><span data-stu-id="4e6b8-159">The deprecated web parts are Report Explorer (**SPExplorer.dwp**) and Report Viewer (**SPViewer.dwp**).</span></span>  
  
 <span data-ttu-id="4e6b8-160">Дополнительные сведения об устаревших веб-частях см. в статье [Просмотр и изучение отчетов в собственном режиме с помощью SharePoint веб-части (службы SSRS)](https://msdn.microsoft.com/library/ms159772.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4e6b8-160">For more information on the deprecated web parts, see [View and Explore Native Mode Reports Using SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span></span>  
  
##  <a name="sql-server-2012-reporting-services-deprecated-features"></a><a name="bkmk_2012"></a><span data-ttu-id="4e6b8-161">SQL Server 2012 Reporting Services устаревшие функции</span><span class="sxs-lookup"><span data-stu-id="4e6b8-161">SQL Server 2012 Reporting Services Deprecated Features</span></span>  
 <span data-ttu-id="4e6b8-162">В этом разделе описываются функции служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , признанные устаревшими в [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e6b8-162">This section describes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features deprecated in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
### <a name="html-rendering-extension-device-information-settings"></a><span data-ttu-id="4e6b8-163">Параметры сведений об устройстве для модуля подготовки отчетов в формате HTML</span><span class="sxs-lookup"><span data-stu-id="4e6b8-163">HTML Rendering Extension Device Information Settings</span></span>  
 <span data-ttu-id="4e6b8-164">Следующие параметры сведений об устройстве для модуля подготовки отчетов в формате HTML являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-164">The following device information settings for the HTML rendering extension are deprecated.</span></span>  
  
-   <span data-ttu-id="4e6b8-165">ActionScript</span><span class="sxs-lookup"><span data-stu-id="4e6b8-165">ActionScript</span></span>  
  
-   <span data-ttu-id="4e6b8-166">ActiveXControls</span><span class="sxs-lookup"><span data-stu-id="4e6b8-166">ActiveXControls</span></span>  
  
-   <span data-ttu-id="4e6b8-167">GetImage</span><span class="sxs-lookup"><span data-stu-id="4e6b8-167">GetImage</span></span>  
  
-   <span data-ttu-id="4e6b8-168">OnlyVisibleStyles</span><span class="sxs-lookup"><span data-stu-id="4e6b8-168">OnlyVisibleStyles</span></span>  
  
-   <span data-ttu-id="4e6b8-169">ReplacementRoot</span><span class="sxs-lookup"><span data-stu-id="4e6b8-169">ReplacementRoot</span></span>  
  
-   <span data-ttu-id="4e6b8-170">ResourceStreamRoot</span><span class="sxs-lookup"><span data-stu-id="4e6b8-170">ResourceStreamRoot</span></span>  
  
-   <span data-ttu-id="4e6b8-171">StreamRoot</span><span class="sxs-lookup"><span data-stu-id="4e6b8-171">StreamRoot</span></span>  
  
-   <span data-ttu-id="4e6b8-172">UsePx</span><span class="sxs-lookup"><span data-stu-id="4e6b8-172">UsePx</span></span>  
  
-   <span data-ttu-id="4e6b8-173">Zoom</span><span class="sxs-lookup"><span data-stu-id="4e6b8-173">Zoom</span></span>  
  
 <span data-ttu-id="4e6b8-174">Дополнительные сведения о модуле подготовки отчетов в формате HTML см. в разделе [HTML Device Information Settings](html-device-information-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4e6b8-174">For more information on the HTML rendering extension, see [HTML Device Information Settings](html-device-information-settings.md)</span></span>  
  
### <a name="microsoft-word-and-microsoft-excel-1997-2003-rendering"></a><span data-ttu-id="4e6b8-175">Подготовка отчетов в формате Microsoft Word и Microsoft Excel 1997-2003</span><span class="sxs-lookup"><span data-stu-id="4e6b8-175">Microsoft Word and Microsoft Excel 1997-2003 Rendering</span></span>  
 <span data-ttu-id="4e6b8-176">Модули подготовки отчетов BIFF8 передается [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[msCoName](../includes/msconame-md.md)] Формат двоичного файла обмена Word и Excel 1997-2003.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-176">The[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] BIFF8 rendering extensions [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Word and [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003 binary interchange file format.</span></span> [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="4e6b8-177">включает расширения, которые отображаются в [!INCLUDE[msCoName](../includes/msconame-md.md)] формате Open XML для Office 2007-2010.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-177">includes extensions that render in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML format.</span></span>  
  
### <a name="report-definition-language-rdl-2005-and-earlier"></a><span data-ttu-id="4e6b8-178">Язык определения отчетов 2005 и более ранних версий</span><span class="sxs-lookup"><span data-stu-id="4e6b8-178">Report Definition Language (RDL) 2005 and Earlier</span></span>  
 <span data-ttu-id="4e6b8-179">Язык определения отчетов 2005 и более ранних версий считается устаревшим.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-179">Report Definition Language (RDL) 2005 and earlier is deprecated.</span></span> <span data-ttu-id="4e6b8-180">Дополнительные сведения об RDL см. в разделе [язык определения отчетов &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4e6b8-180">For more information about RDL, see [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span></span>  
  
 <span data-ttu-id="4e6b8-181">Дополнительные сведения об обновлении отчетов см. в разделе [Upgrade Reports](install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="4e6b8-181">For more information on upgrading reports, see [Upgrade Reports](install-windows/upgrade-reports.md).</span></span>  
  
### <a name="sql-server-2005-and-earlier-custom-report-items"></a><span data-ttu-id="4e6b8-182">Пользовательские элементы отчета SQL Server 2005 и более ранних версий</span><span class="sxs-lookup"><span data-stu-id="4e6b8-182">SQL Server 2005 and earlier Custom Report Items</span></span>  
 <span data-ttu-id="4e6b8-183">Пользовательские элементы отчета (CRI), скомпилированные для [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 и более ранних версий, являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-183">Custom Report Items (CRI) compiled for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
### <a name="reporting-services-snapshots-2005-and-earlier"></a><span data-ttu-id="4e6b8-184">Моментальные снимки служб Reporting Services 2005 и более ранних версий</span><span class="sxs-lookup"><span data-stu-id="4e6b8-184">Reporting Services Snapshots 2005 and earlier</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="4e6b8-185">моментальные снимки, отображаемые с [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 и более ранних версий, являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-185">snapshots rendered with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
### <a name="report-models"></a><span data-ttu-id="4e6b8-186">Модели отчетов</span><span class="sxs-lookup"><span data-stu-id="4e6b8-186">Report Models</span></span>  
 <span data-ttu-id="4e6b8-187">Модели отчетов на языке семантического моделирования (SMDL) больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-187">Semantic modeling language (SMDL) report models are deprecated.</span></span> <span data-ttu-id="4e6b8-188">Несмотря на то, что можно продолжать использовать существующие модели отчетов в качестве источников данных в [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] отчетах, рекомендуется обновить отчеты, чтобы удалить зависимость от моделей отчетов.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-188">Although you can you continue to use existing report models as data sources in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports you should consider updating your reports to remove their dependency on report models.</span></span>  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="4e6b8-189">не [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] включает средства для создания или обновления моделей отчетов.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-189">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not include tools for creating or updating report models.</span></span> <span data-ttu-id="4e6b8-190">Дополнительные сведения см. в разделе [критические изменения в SQL Server Reporting Services в SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="4e6b8-190">For more information, see [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span></span>  
  
### <a name="deprecated-methods-in-the-web-service-endpoint"></a><span data-ttu-id="4e6b8-191">Устаревшие методы в конечной точке веб-службы</span><span class="sxs-lookup"><span data-stu-id="4e6b8-191">Deprecated Methods in the Web Service Endpoint</span></span>  
 <span data-ttu-id="4e6b8-192">В конечной точке веб-службы <xref:ReportService2010.ReportingService2010> устарели следующие операции:</span><span class="sxs-lookup"><span data-stu-id="4e6b8-192">The following operations are deprecated in the <xref:ReportService2010.ReportingService2010> Web service endpoint:</span></span>  
  
-   <xref:ReportService2010.ReportingService2010.GetProperties%2A>  
  
-   <xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>  
  
##  <a name="sql-server-2008-r2-reporting-services-deprecated-features"></a><a name="bkmk_kj"></a><span data-ttu-id="4e6b8-193">SQL Server 2008 R2 Reporting Services устаревшие функции</span><span class="sxs-lookup"><span data-stu-id="4e6b8-193">SQL Server 2008 R2 Reporting Services Deprecated Features</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e6b8-194">Поскольку SQL Server 2008 R2 содержит изменения дополнительного номера версии по сравнению с SQL Server 2008, рекомендуется также просмотреть содержимое раздела по SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-194">Because SQL Server 2008 R2 is a minor version upgrade of SQL Server 2008, we recommend that you also review the content in the SQL Server 2008 section.</span></span>  
  
### <a name="report-server-web-service-endpoints"></a><span data-ttu-id="4e6b8-195">Конечные точки веб-службы сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="4e6b8-195">Report Server Web Service Endpoints</span></span>  
 <span data-ttu-id="4e6b8-196">В этом выпуске считаются устаревшими веб-службы <xref:ReportService2005.ReportingService2005> и <xref:ReportService2006.ReportingService2006>.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-196">The Web services <xref:ReportService2005.ReportingService2005> and <xref:ReportService2006.ReportingService2006> have been deprecated in this release.</span></span> <span data-ttu-id="4e6b8-197">Эти конечные точки были заменены новой конечной точкой: <xref:ReportService2010.ReportingService2010>.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-197">These endpoints have been replaced by a new endpoint: <xref:ReportService2010.ReportingService2010>.</span></span>  
  
 <span data-ttu-id="4e6b8-198">Новая конечная точка включает все функциональные возможности, доступные в устаревшей конечной точке, и новые средства, введенные в SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="4e6b8-198">The new endpoint includes all the functionality available in the deprecated endpoints and the new features introduced in SQL Server 2008 R2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e6b8-199">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e6b8-199">See Also</span></span>  
 <span data-ttu-id="4e6b8-200">[Новые возможности &#40;Reporting Services&#41;](what-s-new-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="4e6b8-200">[What's New &#40;Reporting Services&#41;](what-s-new-reporting-services.md) </span></span>  
 <span data-ttu-id="4e6b8-201">[Обратная совместимость](../getting-started/backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="4e6b8-201">[Backward Compatibility](../getting-started/backward-compatibility.md) </span></span>  
 <span data-ttu-id="4e6b8-202">[Изменения в работе SQL Server Reporting Services в SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="4e6b8-202">[Behavior Changes to SQL Server Reporting Services  in SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md) </span></span>  
 [<span data-ttu-id="4e6b8-203">Неподдерживаемые возможности в службах SQL Server Reporting Services в версии SQL Server "2014"</span><span class="sxs-lookup"><span data-stu-id="4e6b8-203">Discontinued Functionality to SQL Server Reporting Services in SQL Server 2014</span></span>](discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)  
  
  
