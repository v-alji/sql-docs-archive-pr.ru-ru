---
title: Требования к оборудованию и программному обеспечению для Reporting Services в режиме интеграции с SharePoint | Документация Майкрософт
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ed91877d-4f74-4266-a932-b824b4810c99
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a4fc19b2871d7d5731649c61a8d5231d7e3479dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668069"
---
# <a name="hardware-and-software-requirements-for-reporting-services-in-sharepoint-mode"></a><span data-ttu-id="b1abb-102">Требования к оборудованию и программному обеспечению для служб Reporting Services в режиме интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="b1abb-102">Hardware and Software Requirements for Reporting Services in SharePoint Mode</span></span>

  <span data-ttu-id="b1abb-103">В этом разделе описываются необходимые условия, требования к оборудованию и рекомендации по установке для [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] работы в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b1abb-103">This topic describes prerequisites, hardware requirements, and installation considerations for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] running in SharePoint mode.</span></span> <span data-ttu-id="b1abb-104">Поскольку для служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в режиме интеграции с SharePoint требуется сервер SharePoint, большинство требований основаны на среде SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b1abb-104">Because [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode requires a SharePoint server, most of the requirements are based on the SharePoint environment.</span></span> <span data-ttu-id="b1abb-105">Для серверов отчетов, работающих в собственном режиме, оборудование должно соответствовать минимальным требованиям для работы [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1abb-105">For native mode report servers, your hardware should meet minimum hardware and software requirements for running [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="b1abb-106">Дополнительные сведения см. в разделе [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b1abb-106">For more information, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="b1abb-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b1abb-107">Prerequisites</span></span>](#bkmk_prereq)  
  
-   [<span data-ttu-id="b1abb-108">Требования к базе данных сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="b1abb-108">Report Server Database Requirements</span></span>](#bkmk_report_server_database)  
  
-   [<span data-ttu-id="b1abb-109">Требования Power View</span><span class="sxs-lookup"><span data-stu-id="b1abb-109">Power View Requirements</span></span>](#bkmk_powerview)  
  
-   [<span data-ttu-id="b1abb-110">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b1abb-110">More Information</span></span>](#bkmk_more_information)  
  
##  <a name="prerequisites"></a><a name="bkmk_prereq"></a> <span data-ttu-id="b1abb-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b1abb-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="b1abb-112">Для локальных установок учетная запись, в которую был выполнен вход при установке SharePoint, и службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] должны быть членами группы администраторов локальной операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b1abb-112">For local installations, the account logged in during installation of SharePoint and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] needs to be a member of the administrators group in the local operating system.</span></span> <span data-ttu-id="b1abb-113">Учетной записи установки не обязательно быть членом группы администраторов фермы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b1abb-113">The setup account does not need to be a member of the SharePoint farm administrators group.</span></span>  
  
     <span data-ttu-id="b1abb-114">Дополнительные сведения см. в разделе [Разрешения и параметры безопасности учетной записи в SharePoint 2013](https://technet.microsoft.com/library/cc678863.aspx).</span><span class="sxs-lookup"><span data-stu-id="b1abb-114">For more information, see [Account permissions and security settings in SharePoint 2013](https://technet.microsoft.com/library/cc678863.aspx).</span></span>  
  
-   <span data-ttu-id="b1abb-115">Для работы служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в режиме интеграции SharePoint требуется сервер SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b1abb-115">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] running in SharePoint mode requires SharePoint Server.</span></span> <span data-ttu-id="b1abb-116">Дополнительные сведения о требованиях и конфигурациях SharePoint см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="b1abb-116">For more information about SharePoint requirements and configurations, see the following:</span></span>  
  
    -   <span data-ttu-id="b1abb-117">[Требования к оборудованию и программному обеспечению (SharePoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=256365) (https://go.microsoft.com/fwlink/p/?LinkId=256365)</span><span class="sxs-lookup"><span data-stu-id="b1abb-117">[Hardware and software requirements (SharePoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=256365) (https://go.microsoft.com/fwlink/p/?LinkId=256365)</span></span>  
  
    -   [<span data-ttu-id="b1abb-118">Управление размером и его изменение для SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1abb-118">Capacity management and sizing for SharePoint Server 2013</span></span>](https://technet.microsoft.com/library/cc261700.aspx)  
  
    -   [<span data-ttu-id="b1abb-119">Требования к программному обеспечению для бизнес-аналитики (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="b1abb-119">Software requirements for business intelligence (SharePoint 2013)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=256367)  
  
    -   <span data-ttu-id="b1abb-120">[Требования к оборудованию и программному обеспечению (сервер SharePoint 2010)](https://technet.microsoft.com/library/cc262485\(v=office.14\))</span><span class="sxs-lookup"><span data-stu-id="b1abb-120">[Hardware and software requirements (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262485\(v=office.14\))</span></span>  
  
    -   <span data-ttu-id="b1abb-121">[Управление размером и его изменение для SharePoint Server 2010](https://technet.microsoft.com/library/cc261700.aspx\(v=office.14\))</span><span class="sxs-lookup"><span data-stu-id="b1abb-121">[Capacity management and sizing for SharePoint Server 2010](https://technet.microsoft.com/library/cc261700.aspx\(v=office.14\))</span></span>  
  
-   <span data-ttu-id="b1abb-122">Если требуется обновить существующую установку служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], см. раздел [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="b1abb-122">If you want to upgrade or update existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint installation with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="b1abb-123">Проверьте, запущена ли служба **Администрирование SharePoint 2013** в диспетчере Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b1abb-123">Verify the **SharePoint 2013 Administration** service is started in Windows Server Manager.</span></span>  
  
###  <a name="report-server-database-requirements"></a><a name="bkmk_report_server_database"></a><span data-ttu-id="b1abb-124">Требования к базе данных сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="b1abb-124">Report Server Database Requirements</span></span>  
  
-   <span data-ttu-id="b1abb-125">Как службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , так и продукты и технологии SharePoint используют для хранения данных приложений реляционные базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1abb-125">Both [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and SharePoint products and technologies use SQL Server relational databases to store application data.</span></span>  
  
-   [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)] <span data-ttu-id="b1abb-126">требуется экземпляр [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] с соответствующим выпуском SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1abb-126">requires an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] of a compatible SQL Server edition.</span></span> <span data-ttu-id="b1abb-127">Дополнительные сведения о требованиях к программному и аппаратному обеспечению см. в разделе [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b1abb-127">For more information on hardware and software requirements, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
-   <span data-ttu-id="b1abb-128">Продукты SharePoint могут использовать существующий экземпляр базы данных.</span><span class="sxs-lookup"><span data-stu-id="b1abb-128">SharePoint products can use an existing database instance.</span></span> <span data-ttu-id="b1abb-129">Если экземпляр [!INCLUDE[ssDE](../../includes/ssde-md.md)] не установлен, программа установки продуктов SharePoint устанавливает SQL Server Express Edition для баз данных приложений SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1abb-129">If an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] is not installed, the SharePoint Products Setup program installs SQL Server Express Edition for the SharePoint application databases.</span></span>  
  
-   <span data-ttu-id="b1abb-130">Экземпляр сервера отчетов не может использовать для своей базы данных выпуск SQL Server Express Edition.</span><span class="sxs-lookup"><span data-stu-id="b1abb-130">The report server instance cannot use the SQL Server Express Edition for its database.</span></span> <span data-ttu-id="b1abb-131">Однако экземпляр SQL Server Express Edition, установленный продуктом SharePoint, может существовать параллельно с другими выпусками ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="b1abb-131">However, the SQL Server Express Edition instance installed by the SharePoint product can exist side-by-side with other Database Engine editions.</span></span>  
  
##  <a name="sscrescent-requirements"></a><a name="bkmk_powerview"></a><span data-ttu-id="b1abb-132">[!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]Требования к</span><span class="sxs-lookup"><span data-stu-id="b1abb-132">[!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] Requirements</span></span>

 <span data-ttu-id="b1abb-133">Ознакомьтесь с новейшей [документацией по Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx) на сайте Office.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b1abb-133">Review the most up-to-date [Power View documentation](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx) on Office.Microsoft.com.</span></span> [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] <span data-ttu-id="b1abb-134">входит в состав Microsoft Excel 2013 и является частью надстройки служб Reporting Services [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] для выпусков Microsoft SharePoint Server 2010 и 2013 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b1abb-134">is a feature of Microsoft Excel 2013, and is part of the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Reporting Services add-in for Microsoft SharePoint Server 2010 and 2013 Enterprise Editions.</span></span>  
  
##  <a name="more-information"></a><a name="bkmk_more_information"></a> <span data-ttu-id="b1abb-135">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b1abb-135">More Information</span></span>

 <span data-ttu-id="b1abb-136">Сведения об изменениях SharePoint см. в статье [изменения из sharepoint 2010 в sharepoint 2013](https://technet.microsoft.com/library/ff607742\(office.15\).aspx) ( https://technet.microsoft.com/library/ff607742(office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="b1abb-136">For information on SharePoint changes, see [Changes from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/ff607742\(office.15\).aspx) (https://technet.microsoft.com/library/ff607742(office.15).aspx).</span></span>  
  
 <span data-ttu-id="b1abb-137">[Заметки о Выпуске SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="b1abb-137">[SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
