---
title: Публикация источников данных и отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- publishing data sources [Reporting Services]
- publishing reports [Reporting Services]
- data sources [Reporting Services], managing
ms.assetid: 3a740f8a-1060-4ec3-938b-2305b6887ebd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 941362afde1cfe5dd3d235c9f243fb17875adadc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729037"
---
# <a name="publishing-data-sources-and-reports"></a><span data-ttu-id="559a9-102">Публикация источников данных и отчетов</span><span class="sxs-lookup"><span data-stu-id="559a9-102">Publishing Data Sources and Reports</span></span>
  <span data-ttu-id="559a9-103">До публикации отчета его следует просмотреть, чтобы проверить его внешний вид.</span><span class="sxs-lookup"><span data-stu-id="559a9-103">Before publishing your report, you should preview the report to see how it will look when it is run.</span></span> <span data-ttu-id="559a9-104">Макет отчета можно изменять, пока не будут достигнуты нужные результаты.</span><span class="sxs-lookup"><span data-stu-id="559a9-104">You can continue to refine the design until you are satisfied with the results.</span></span>  
  
 <span data-ttu-id="559a9-105">После создания и проверки отчета можно предоставить к нему доступ другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="559a9-105">After you design and test your report, you may want to share it with other individuals.</span></span> <span data-ttu-id="559a9-106">Чтобы предоставить доступ к отчету, его нужно опубликовать, или *развернуть*на сервере отчетов или сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="559a9-106">To share your report, you need to publish, or *deploy*, it to a report server or SharePoint site.</span></span> <span data-ttu-id="559a9-107">После публикации отчета пользователи, имеющие доступ к серверу отчетов или сайту SharePoint, смогут запускать этот отчет.</span><span class="sxs-lookup"><span data-stu-id="559a9-107">After it has been published, individuals who have permissions to the report server or the SharePoint site can run your report.</span></span> <span data-ttu-id="559a9-108">Кроме того, пользователи с разрешениями администратора на сервере отчетов могут создавать подписки на этот отчет, чтобы его можно было обновлять и рассылать пользователям по регулярному расписанию.</span><span class="sxs-lookup"><span data-stu-id="559a9-108">In addition, a person with administrator permissions on the report server can create subscriptions to your report so that the report can be updated and sent to users on a regular schedule.</span></span>  
  
 <span data-ttu-id="559a9-109">Если отчет создавался с использованием общего источника данных, этот источник данных должен быть опубликован на том же сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="559a9-109">If you used a shared data source to create your report, you need to publish it to the same location as the report.</span></span> <span data-ttu-id="559a9-110">Общими источниками данных, как и отчетами, можно управлять на сервере отчетов по отдельности.</span><span class="sxs-lookup"><span data-stu-id="559a9-110">Like reports, shared data sources can be managed separately on the report server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="559a9-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="559a9-111">In This Section</span></span>  
 [<span data-ttu-id="559a9-112">Предварительный просмотр отчетов</span><span class="sxs-lookup"><span data-stu-id="559a9-112">Previewing Reports</span></span>](previewing-reports.md)  
 <span data-ttu-id="559a9-113">Описывает, как просмотреть отчет перед публикацией.</span><span class="sxs-lookup"><span data-stu-id="559a9-113">Describes how to preview a report before you publish it.</span></span>  
  
 [<span data-ttu-id="559a9-114">Публикация отчетов на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="559a9-114">Publishing Reports to a Report Server</span></span>](publishing-reports-to-a-report-server.md)  
 <span data-ttu-id="559a9-115">Описывает процесс публикации отчета на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="559a9-115">Describes how to publish a report to a report server.</span></span>  
  
 [<span data-ttu-id="559a9-116">Примеры URL-адресов для элементов опубликованного отчета на сервере отчетов в режиме SharePoint &#40;службы SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="559a9-116">URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;</span></span>](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md)  
 <span data-ttu-id="559a9-117">Описывает процесс публикации отчета на сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="559a9-117">Describes how to publish a report to a SharePoint site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="559a9-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="559a9-118">See Also</span></span>  
 <span data-ttu-id="559a9-119">[Подключения к данным, источники данных и строки подключения в Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="559a9-119">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="559a9-120">[Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](../report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="559a9-120">[Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="559a9-121">[Макет страницы и подготовка к просмотру &#40;построитель отчетов и SSRS&#41;](../report-design/page-layout-and-rendering-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="559a9-121">[Page Layout and Rendering &#40;Report Builder and SSRS&#41;](../report-design/page-layout-and-rendering-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="559a9-122">[Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](../report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="559a9-122">[Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="559a9-123">[Поиск, просмотр отчетов и управление ими &#40;построитель отчетов и SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="559a9-123">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="559a9-124">[Экспорт отчетов &#40;построитель отчетов и SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="559a9-124">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="559a9-125">Печать отчетов (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="559a9-125">Print Reports &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/print-reports-report-builder-and-ssrs.md)  
  
  
