---
title: Опубликовать отчеты | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], publishing
- publishing reports [Reporting Services]
ms.assetid: ef5a514e-e818-4041-a8b0-15835f9a046b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb54308a6b15260d4c336950f231d0ee40836430
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654879"
---
# <a name="publish-reports"></a><span data-ttu-id="754bd-102">Публикация отчетов</span><span class="sxs-lookup"><span data-stu-id="754bd-102">Publish Reports</span></span>
  <span data-ttu-id="754bd-103">Среда[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]позволяет опубликовать либо все отчеты и общие источники данных проекта "Сервер отчетов" на сервере отчетов в процессе развертывания проекта, либо один отчет.</span><span class="sxs-lookup"><span data-stu-id="754bd-103">From[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], you can publish either all the reports and shared data sources in a Report Server project to a report server by deploying the project, or you can publish a single report.</span></span> <span data-ttu-id="754bd-104">Перед публикацией отчета необходимо указать URL-адрес целевого сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="754bd-104">Before you can publish a report you must specify the URL of the target report server.</span></span> <span data-ttu-id="754bd-105">Дополнительные сведения см. в разделе [Задание свойства развертывания (службы Reporting Services)](tools/set-deployment-properties-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="754bd-105">For more information, see [Set Deployment Properties &#40;Reporting Services&#41;](tools/set-deployment-properties-reporting-services.md).</span></span>  
  
 <span data-ttu-id="754bd-106">Можно использовать версию [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для открытия, изменения, предварительного просмотра, сохранения и публикации отчетов как [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] , так и [!INCLUDE[ssRSversion10](../includes/ssrsversion10-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="754bd-106">You can use the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] version of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to open, modify, preview, save, and publish both [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] and [!INCLUDE[ssRSversion10](../includes/ssrsversion10-md.md)] reports.</span></span> <span data-ttu-id="754bd-107">Дополнительные сведения см. в разделе [Развертывание и поддержка версий в SQL Server Data Tools (службы SSRS)](tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="754bd-107">For more information, see [Deployment and Version Support in SQL Server Data Tools &#40;SSRS&#41;](tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span></span>  
  
### <a name="to-publish-all-reports-in-a-project"></a><span data-ttu-id="754bd-108">Публикация всех отчетов в проекте</span><span class="sxs-lookup"><span data-stu-id="754bd-108">To publish all reports in a project</span></span>  
  
-   <span data-ttu-id="754bd-109">В меню **Сборка** выберите пункт \*\*Развернуть \<report project name> \*\*.</span><span class="sxs-lookup"><span data-stu-id="754bd-109">On the **Build** menu, click **Deploy \<report project name>**.</span></span> <span data-ttu-id="754bd-110">Или в обозревателе решений щелкните правой кнопкой мыши проект отчета и выберите команду **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="754bd-110">Alternatively, in Solution Explorer, right-click the report project and then click **Deploy**.</span></span> <span data-ttu-id="754bd-111">Можно просмотреть состояние процесса публикации в окне вывода.</span><span class="sxs-lookup"><span data-stu-id="754bd-111">You can view the status of the publishing process in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="754bd-112">При развертывании проекта «Сервер отчетов» будут развернуты и общие источники данных проекта отчета.</span><span class="sxs-lookup"><span data-stu-id="754bd-112">When you deploy a Report Server project, the shared data sources in the report project are also deployed.</span></span>  
  
### <a name="to-publish-a-single-report"></a><span data-ttu-id="754bd-113">Публикация одного отчета</span><span class="sxs-lookup"><span data-stu-id="754bd-113">To publish a single report</span></span>  
  
-   <span data-ttu-id="754bd-114">В обозревателе решений щелкните правой кнопкой мыши отчет, а затем выберите пункт **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="754bd-114">In Solution Explorer, right-click the report and then click **Deploy**.</span></span> <span data-ttu-id="754bd-115">Можно просмотреть состояние процесса публикации в окне вывода.</span><span class="sxs-lookup"><span data-stu-id="754bd-115">You can view the status of the publishing process in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="754bd-116">При публикации отчета необходимо также выполнить развертывание общих источников данных, которые в нем используются.</span><span class="sxs-lookup"><span data-stu-id="754bd-116">When you publish a report, you must also deploy the shared data sources that the report uses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754bd-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="754bd-117">See Also</span></span>  
 <span data-ttu-id="754bd-118">[Публикация источников данных и отчетов](reports/publishing-data-sources-and-reports.md) </span><span class="sxs-lookup"><span data-stu-id="754bd-118">[Publishing Data Sources and Reports](reports/publishing-data-sources-and-reports.md) </span></span>  
 <span data-ttu-id="754bd-119">[Предварительный просмотр отчетов](reports/previewing-reports.md) </span><span class="sxs-lookup"><span data-stu-id="754bd-119">[Previewing Reports](reports/previewing-reports.md) </span></span>  
 <span data-ttu-id="754bd-120">[Публикация отчетов на сервере отчетов](reports/publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="754bd-120">[Publishing Reports to a Report Server](reports/publishing-reports-to-a-report-server.md) </span></span>  
 <span data-ttu-id="754bd-121">[Поиск, просмотр отчетов и управление ими &#40;построитель отчетов и SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="754bd-121">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="754bd-122">Экспорт отчетов &#40;построитель отчетов и SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="754bd-122">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](report-builder/export-reports-report-builder-and-ssrs.md)  
  
  
