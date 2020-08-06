---
title: Службы Reporting Services (SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services]
- SSRS
- reports [Reporting Services], about reports
- Reporting Services
- SQL Server Reporting Services
ms.assetid: b8d18d3d-9db0-43e7-8286-7b46cc3a37ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0418acaab54032148f4bc6d42d06c97070b89e1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728085"
---
# <a name="reporting-services-ssrs"></a><span data-ttu-id="f29ab-102">Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="f29ab-102">Reporting Services (SSRS)</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="f29ab-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]предоставляет полный спектр готовых к использованию средств и служб для создания, развертывания и управления отчетами в Организации.</span><span class="sxs-lookup"><span data-stu-id="f29ab-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides a full range of ready-to-use tools and services to help you create, deploy, and manage reports for your organization.</span></span> <span data-ttu-id="f29ab-104">Службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] включают возможности программирования, которые позволяют расширять и настраивать функциональные возможности по работе с отчетами.</span><span class="sxs-lookup"><span data-stu-id="f29ab-104">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] includes programming features that enable you to extend and customize your reporting functionality.</span></span>

 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="f29ab-105">— это Серверная платформа для создания отчетов, обеспечивающая комплексные функции создания отчетов для различных источников данных.</span><span class="sxs-lookup"><span data-stu-id="f29ab-105">is a server-based reporting platform that provides comprehensive reporting functionality for a variety of data sources.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="f29ab-106">содержит полный набор средств для создания, управления и доставки отчетов, а также интерфейсы API, позволяющие разработчикам интегрировать или расширять обработку данных и отчетов в пользовательских приложениях.</span><span class="sxs-lookup"><span data-stu-id="f29ab-106">includes a complete set of tools for you to create, manage, and deliver reports, and APIs that enable developers to integrate or extend data and report processing in custom applications.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="f29ab-107">средства работают в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] среде и полностью интегрированы с [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] инструментами и компонентами.</span><span class="sxs-lookup"><span data-stu-id="f29ab-107">tools work within the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] environment and are fully integrated with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tools and components.</span></span>

 <span data-ttu-id="f29ab-108">С помощью служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]можно создать интерактивные, табличные, графические отчеты и отчеты свободной формы из реляционных, многомерных и XML-источников данных.</span><span class="sxs-lookup"><span data-stu-id="f29ab-108">With [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], you can create interactive, tabular, graphical, or free-form reports from relational, multidimensional, or XML-based data sources.</span></span> <span data-ttu-id="f29ab-109">Отчеты могут включать визуализацию сложных данных, в том числе диаграммы, карты и спарклайны.</span><span class="sxs-lookup"><span data-stu-id="f29ab-109">Reports can include rich data visualization, including charts, maps, and sparklines.</span></span> <span data-ttu-id="f29ab-110">Можно публиковать отчеты, планировать их обработку или осуществлять доступ к отчетам по требованию.</span><span class="sxs-lookup"><span data-stu-id="f29ab-110">You can publish reports, schedule report processing, or access reports on-demand.</span></span> <span data-ttu-id="f29ab-111">Имеется большой выбор форматов просмотра. Можно экспортировать отчеты в другие приложения, например [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)]. Также можно подписаться на публикуемые отчеты.</span><span class="sxs-lookup"><span data-stu-id="f29ab-111">You can select from a variety of viewing formats, export reports to other applications such as [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], and subscribe to published reports.</span></span> <span data-ttu-id="f29ab-112">Созданные отчеты можно просматривать с помощью веб-соединения или как часть приложения [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows или сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f29ab-112">The reports that you create can be viewed over a Web-based connection or as part of a [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows application or SharePoint site.</span></span> <span data-ttu-id="f29ab-113">Также возможно создавать предупреждения об изменении данных в отчетах, опубликованных на сайте SharePoint, и получать электронные сообщения при изменении данных в отчете.</span><span class="sxs-lookup"><span data-stu-id="f29ab-113">You can also create data alerts on reports published to a SharePoint site and receive email messages when report data changes.</span></span>

 <span data-ttu-id="f29ab-114">Дополнительные сведения о новых возможностях [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] см. в разделе [новые возможности &#40;Reporting Services&#41;](../../2014/reporting-services/what-s-new-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="f29ab-114">For more information about features new in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [What's New &#40;Reporting Services&#41;](../../2014/reporting-services/what-s-new-reporting-services.md).</span></span>

 <span data-ttu-id="f29ab-115">Дополнительные сведения о других компонентах, средствах и ресурсах [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] см. в [электронной документации по SQL Server](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="f29ab-115">For information about other [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components, tools, and resources, see [SQL Server Books Online](../index.yml).</span></span>

 <span data-ttu-id="f29ab-116">**Просмотр содержимого по** ![значку папки](media/hlp-16folder.gif "Значок папки") [Reporting Services сервере отчетов](../../2014/reporting-services/reporting-services-report-server.md)</span><span class="sxs-lookup"><span data-stu-id="f29ab-116">**Browse Content by Area** ![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Report Server](../../2014/reporting-services/reporting-services-report-server.md)</span></span>

 <span data-ttu-id="f29ab-117">![Значок папки](media/hlp-16folder.gif "Значок папки") [Reporting Services отчеты &#40;SSRS&#41;](reports/reporting-services-reports-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="f29ab-117">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Reports &#40;SSRS&#41;](reports/reporting-services-reports-ssrs.md)</span></span>

 <span data-ttu-id="f29ab-118">![Значок папки](media/hlp-16folder.gif "Значок папки") [данные отчета &#40;SSRS&#41;](report-data/report-data-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="f29ab-118">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Data &#40;SSRS&#41;](report-data/report-data-ssrs.md)</span></span>

 <span data-ttu-id="f29ab-119">![Значок папки](media/hlp-16folder.gif "Значок папки") [параметры отчета &#40;построитель отчетов и конструктор отчетов&#41;](report-design/report-parameters-report-builder-and-report-designer.md)</span><span class="sxs-lookup"><span data-stu-id="f29ab-119">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md)</span></span>

 <span data-ttu-id="f29ab-120">![Значок папки](media/hlp-16folder.gif "Значок папки") [элементы отчета в конструктор отчетов &#40;SSRS&#41;](report-design/report-parts-in-report-designer-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="f29ab-120">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Parts in Report Designer &#40;SSRS&#41;](report-design/report-parts-in-report-designer-ssrs.md)</span></span>

 <span data-ttu-id="f29ab-121">[Расписания](subscriptions/schedules.md) ![значков папок](media/hlp-16folder.gif "Значок папки")</span><span class="sxs-lookup"><span data-stu-id="f29ab-121">![Folder icon](media/hlp-16folder.gif "Folder icon") [Schedules](subscriptions/schedules.md)</span></span>

 <span data-ttu-id="f29ab-122">![Значок папки](media/hlp-16folder.gif "Значок папки") [подписки и &#40;доставки Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="f29ab-122">![Folder icon](media/hlp-16folder.gif "Folder icon") [Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)</span></span>

 <span data-ttu-id="f29ab-123">![Значок папки](media/hlp-16folder.gif "Значок папки") [Reporting Services предупреждения](../ssms/agent/alerts.md) об изменении данных</span><span class="sxs-lookup"><span data-stu-id="f29ab-123">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>

 <span data-ttu-id="f29ab-124">![Значок папки](media/hlp-16folder.gif "Значок папки") [Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx)</span><span class="sxs-lookup"><span data-stu-id="f29ab-124">![Folder icon](media/hlp-16folder.gif "Folder icon") [Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx)</span></span>

 <span data-ttu-id="f29ab-125">![Значок папки](media/hlp-16folder.gif "Значок папки") [Reporting Services безопасность и защита](security/reporting-services-security-and-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f29ab-125">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Security and Protection](security/reporting-services-security-and-protection.md)</span></span>

 <span data-ttu-id="f29ab-126">![Значок папки](media/hlp-16folder.gif "Значок папки") [доступ к URL-адресу &#40;SSRS&#41;](url-access-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="f29ab-126">![Folder icon](media/hlp-16folder.gif "Folder icon") [URL Access &#40;SSRS&#41;](url-access-ssrs.md)</span></span>

 <span data-ttu-id="f29ab-127">Расширения ![значков папок](media/hlp-16folder.gif "Значок папки") [&#40;SSRS&#41;](extensions-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="f29ab-127">![Folder icon](media/hlp-16folder.gif "Folder icon") [Extensions &#40;SSRS&#41;](extensions-ssrs.md)</span></span>

 <span data-ttu-id="f29ab-128">![Значок папки](media/hlp-16folder.gif "Значок папки") [Reporting Services средства](tools/reporting-services-tools.md)</span><span class="sxs-lookup"><span data-stu-id="f29ab-128">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Tools](tools/reporting-services-tools.md)</span></span>

 <span data-ttu-id="f29ab-129">![Значок папки](media/hlp-16folder.gif "Значок папки") [ошибки и события справочник &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="f29ab-129">![Folder icon](media/hlp-16folder.gif "Folder icon") [Errors and Events Reference &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md)</span></span>

 <span data-ttu-id="f29ab-130">![Значок папки](media/hlp-16folder.gif "Значок папки") [ссылка на компонент &#40;Reporting Services&#41;](feature-reference-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="f29ab-130">![Folder icon](media/hlp-16folder.gif "Folder icon") [Feature Reference &#40;Reporting Services&#41;](feature-reference-reporting-services.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="f29ab-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="f29ab-131">See Also</span></span>
 [<span data-ttu-id="f29ab-132">Центр ресурсов SQL Server</span><span class="sxs-lookup"><span data-stu-id="f29ab-132">SQL Server Resource Center</span></span>](https://go.microsoft.com/fwlink/?linkID=219676)


