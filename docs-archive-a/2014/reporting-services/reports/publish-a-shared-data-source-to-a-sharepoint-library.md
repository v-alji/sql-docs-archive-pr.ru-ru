---
title: Публикация общего источника данных в библиотеку SharePoint | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], publishing to a SharePoint library
- SharePoint integration [Reporting Services], publishing to a library
- publishing reports [Reporting Services], to a SharePoint library
ms.assetid: 966ed425-3ce2-4e76-8237-3c1c977954ae
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77ee25535ccb98638ae02ca64e3bcbfc88291c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729042"
---
# <a name="publish-a-shared-data-source-to-a-sharepoint-library"></a><span data-ttu-id="931a4-102">опубликовать общий источник данных в библиотеке SharePoint</span><span class="sxs-lookup"><span data-stu-id="931a4-102">Publish a Shared Data Source to a SharePoint Library</span></span>
  <span data-ttu-id="931a4-103">Чтобы опубликовать общий источник данных на сервере отчетов, работающем в режиме интеграции с SharePoint, необходимо задать свойства проекта отчета в конструкторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="931a4-103">To publish a shared data source to a report server that is running in SharePoint integrated mode, you must set the report project properties in Report Designer.</span></span> <span data-ttu-id="931a4-104">В свойствах проекта все ссылки на серверы, отчеты и общие источники данных следует указывать в виде полных URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="931a4-104">In the project properties, all references to servers, reports, and shared data sources must be fully qualified URLs.</span></span>  
  
 <span data-ttu-id="931a4-105">Необходимо иметь разрешение **Член** или **Владелец** на сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="931a4-105">You must have **Member** or **Owner** permission on the SharePoint site.</span></span> <span data-ttu-id="931a4-106">Дополнительные сведения см. в разделе [Примеры URL-адресов для элементов опубликованного отчета на сервере отчетов в режиме SharePoint &#40;службы SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="931a4-106">For more information, see [URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span></span>  
  
### <a name="to-publish-a-shared-data-source-to-a-sharepoint-site"></a><span data-ttu-id="931a4-107">Публикация общего источника данных на сайте SharePoint</span><span class="sxs-lookup"><span data-stu-id="931a4-107">To publish a shared data source to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="931a4-108">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте существующий или создайте новый проект сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="931a4-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open your existing or new Report Server project.</span></span>  
  
2.  <span data-ttu-id="931a4-109">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="931a4-109">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="931a4-110">_\<project>_ Откроется диалоговое окно **страницы свойств** .</span><span class="sxs-lookup"><span data-stu-id="931a4-110">The _\<project>_**Property Pages** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="931a4-111">Выберите **Конфигурацию** для публикации на сайте SharePoint,</span><span class="sxs-lookup"><span data-stu-id="931a4-111">Choose the **Configuration** you use to publish to a SharePoint site.</span></span>  
  
4.  <span data-ttu-id="931a4-112">Если в проекте публикуются общие источники данных и перезаписываются ранее опубликованные общие источники данных, присвойте свойству **OverwriteDataSources** значение **True**.</span><span class="sxs-lookup"><span data-stu-id="931a4-112">If you want to publish the shared data sources in your project and overwrite previously published shared data sources, set **OverwriteDataSources** to **True**.</span></span>  
  
5.  <span data-ttu-id="931a4-113">Для значения свойства **TargetDataSourceFolder**введите URL-адрес библиотеки SharePoint или папки библиотеки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="931a4-113">(Optional) For **TargetDataSourceFolder**, type a URL to a SharePoint library or library folder.</span></span> <span data-ttu-id="931a4-114">Например, *http://TestServer/TestSite/Documents/DataSources* .</span><span class="sxs-lookup"><span data-stu-id="931a4-114">For example, *http://TestServer/TestSite/Documents/DataSources*.</span></span>  
  
     <span data-ttu-id="931a4-115">Если значение не указано, то будет использовано значение свойства **TargetReportFolder** .</span><span class="sxs-lookup"><span data-stu-id="931a4-115">If you do not specify a value, the **TargetReportFolder** value is used.</span></span>  
  
6.  <span data-ttu-id="931a4-116">В качестве значения свойства **TargetReportFolder**введите URL-адрес библиотеки или папки библиотеки.</span><span class="sxs-lookup"><span data-stu-id="931a4-116">For **TargetReportFolder**, type a URL to a library or library folder.</span></span> <span data-ttu-id="931a4-117">Например, http:*//TestServer/TestSite/Documents/Reports*.</span><span class="sxs-lookup"><span data-stu-id="931a4-117">For example, http:*//TestServer/TestSite/Documents/Reports*.</span></span>  
  
7.  <span data-ttu-id="931a4-118">В поле **TargetServerURL**введите URL-адрес сайта SharePoint верхнего уровня или дочернего сайта.</span><span class="sxs-lookup"><span data-stu-id="931a4-118">For **TargetServerURL**, type a URL to a SharePoint top-level site or subsite.</span></span> <span data-ttu-id="931a4-119">Если сайт не указан, то используется сайт верхнего уровня по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="931a4-119">If you do not specify a site, the default top-level site is used.</span></span> <span data-ttu-id="931a4-120">Например:*http://имя_сервера*, http://*имя_сервера*/*сайт*или http://*имя_сервера*/*сайт*/*подсайт*.</span><span class="sxs-lookup"><span data-stu-id="931a4-120">For example, http://*servername*, http://*servername*/*site*, or http://*servername*/*site*/*subsite*.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="931a4-121">В обозревателе решений щелкните правой кнопкой мыши общий источник данных, который необходимо опубликовать, и выберите **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="931a4-121">In Solution Explorer, right-click the shared data source you want to publish, and click **Deploy**.</span></span> <span data-ttu-id="931a4-122">Источник данных будет опубликован в местоположении, которое указывает свойство **TargetDataSourceFolder**.</span><span class="sxs-lookup"><span data-stu-id="931a4-122">The data source is published to the location specified in **TargetDataSourceFolder**.</span></span> <span data-ttu-id="931a4-123">Ошибки развертывания появляются в окне «Вывод».</span><span class="sxs-lookup"><span data-stu-id="931a4-123">Deployment errors appear in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="931a4-124">После публикации общего источника данных на сайте SharePoint, расширение имени файла меняется на RSDS.</span><span class="sxs-lookup"><span data-stu-id="931a4-124">After you publish a shared data source to a SharePoint site, the file name extension is changed to .rsds.</span></span> <span data-ttu-id="931a4-125">Общий источник данных можно изменять и управлять им непосредственно с сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="931a4-125">You can edit and manage a shared data source directly on the SharePoint site.</span></span> <span data-ttu-id="931a4-126">Дополнительные сведения см. в разделе [Создание общих источников данных и управление ими (службы Reporting Services в режиме интеграции с SharePoint)](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="931a4-126">For more information, see [Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="931a4-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="931a4-127">See Also</span></span>  
 <span data-ttu-id="931a4-128">[Публикация отчета в библиотеке SharePoint](publish-a-report-to-a-sharepoint-library.md) </span><span class="sxs-lookup"><span data-stu-id="931a4-128">[Publish a Report to a SharePoint Library](publish-a-report-to-a-sharepoint-library.md) </span></span>  
 <span data-ttu-id="931a4-129">[Примеры URL-адресов для элементов опубликованного отчета на сервере отчетов в режиме интеграции с SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="931a4-129">[URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="931a4-130">[Диалоговое окно "страницы свойств проекта"](../tools/project-property-pages-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="931a4-130">[Project Property Pages Dialog Box](../tools/project-property-pages-dialog-box.md) </span></span>  
 <span data-ttu-id="931a4-131">[Задание свойств развертывания &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="931a4-131">[Set Deployment Properties &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span></span>  
 <span data-ttu-id="931a4-132">[Публикация отчетов на сервере отчетов](publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="931a4-132">[Publishing Reports to a Report Server](publishing-reports-to-a-report-server.md) </span></span>  
 [<span data-ttu-id="931a4-133">Использование ODC-файла подключения к данным Office в отчетах (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="931a4-133">Use an Office Data Connection &#40;.odc&#41; with Reports &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../report-data/use-an-office-data-connection-odc-with-reports.md)  
  
  
