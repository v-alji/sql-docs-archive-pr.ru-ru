---
title: Публикация отчета в библиотеке SharePoint | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- deploying [Reporting Services], reports in SharePoint integrated mode
- SharePoint integration [Reporting Services], publishing to a library
- publishing reports [Reporting Services], to a SharePoint library
ms.assetid: 3f6dfc28-50d8-4231-bd25-871b5f77cce6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 23b74ffb04bf1e13523dcf6ec5d774089d80f73b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729046"
---
# <a name="publish-a-report-to-a-sharepoint-library"></a><span data-ttu-id="ae5f1-102">опубликовать отчет в библиотеке SharePoint</span><span class="sxs-lookup"><span data-stu-id="ae5f1-102">Publish a Report to a SharePoint Library</span></span>
  <span data-ttu-id="ae5f1-103">Чтобы опубликовать отчет на сайте SharePoint, настроенном для интеграции с SharePoint, необходимо задать свойства проекта в конструкторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="ae5f1-103">To publish a report to a SharePoint site configured for SharePoint integration, you must set the project properties in Report Designer.</span></span> <span data-ttu-id="ae5f1-104">В свойствах проекта все ссылки на серверы, отчеты и общие источники данных следует указывать в виде полных URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="ae5f1-104">In the project properties, all references to servers, reports, and shared data sources must be fully qualified URLs.</span></span> <span data-ttu-id="ae5f1-105">В определении отчета все ссылки на вложенные отчеты, детализированные отчеты и такие ресурсы, как изображения, расположенные в Интернете, должны представлять собой полные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="ae5f1-105">In the report definition, all references to subreports, drillthrough reports, and resources such as Web-based images, must be fully qualified URLS.</span></span>  
  
 <span data-ttu-id="ae5f1-106">Необходимо обладать разрешением **Член** или **Владелец** на сайте SharePoint для задания свойств проекта.</span><span class="sxs-lookup"><span data-stu-id="ae5f1-106">You must have **Member** or **Owner** permission on the SharePoint site to set the properties on the project.</span></span> <span data-ttu-id="ae5f1-107">Дополнительные сведения см. в разделе [Примеры URL-адресов для элементов опубликованного отчета на сервере отчетов в режиме SharePoint &#40;службы SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="ae5f1-107">For more information, see [URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span></span>  
  
### <a name="to-publish-a-report-to-a-sharepoint-site"></a><span data-ttu-id="ae5f1-108">Публикация отчета на сайте SharePoint</span><span class="sxs-lookup"><span data-stu-id="ae5f1-108">To publish a report to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="ae5f1-109">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте существующий или новый проект сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="ae5f1-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open an existing or new Report Server project.</span></span>  
  
2.  <span data-ttu-id="ae5f1-110">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ae5f1-110">From the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="ae5f1-111">_\<project>_ Откроется диалоговое окно **страницы свойств** .</span><span class="sxs-lookup"><span data-stu-id="ae5f1-111">The _\<project>_**Property Pages** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="ae5f1-112">В списке **Конфигурация** выберите имя конфигурации сборки решения, предназначенной для формирования и публикации отчета.</span><span class="sxs-lookup"><span data-stu-id="ae5f1-112">In the **Configuration** list, select the name of a solution build configuration to use to build and publish your report.</span></span> <span data-ttu-id="ae5f1-113">Текущая конфигурация указана как **Активная**( *\<configuration>* ).</span><span class="sxs-lookup"><span data-stu-id="ae5f1-113">The current configuration is listed as **Active**(*\<configuration>*).</span></span>  
  
4.  <span data-ttu-id="ae5f1-114">Если в проекте публикуются общие источники данных и перезаписываются ранее опубликованные общие источники данных, присвойте свойству **OverwriteDataSources** значение **True**.</span><span class="sxs-lookup"><span data-stu-id="ae5f1-114">If you want to publish the shared data sources in your project and overwrite previously published shared data sources, set **OverwriteDataSources** to **True**.</span></span>  
  
5.  <span data-ttu-id="ae5f1-115">Используемых Для **TargetDataSourceFolder**введите URL-адрес библиотеки SharePoint или папки библиотеки (например, *http://TestServer/TestSite/Documents/DataSources)* .</span><span class="sxs-lookup"><span data-stu-id="ae5f1-115">(Optional) For **TargetDataSourceFolder**, type a URL to a SharePoint library or library folder (for example, *http://TestServer/TestSite/Documents/DataSources)*.</span></span>  
  
     <span data-ttu-id="ae5f1-116">Если значение не указано, то будет использовано значение свойства **TargetReportFolder** .</span><span class="sxs-lookup"><span data-stu-id="ae5f1-116">If you do not specify a value, the **TargetReportFolder** value is used.</span></span>  
  
6.  <span data-ttu-id="ae5f1-117">Для **TargetReportFolder**введите URL-адрес библиотеки или папки библиотеки (например, *http://TestServer/TestSite/Documents/Reports)* .</span><span class="sxs-lookup"><span data-stu-id="ae5f1-117">For **TargetReportFolder**, type a URL to a library or library folder (for example, *http://TestServer/TestSite/Documents/Reports)*.</span></span>  
  
7.  <span data-ttu-id="ae5f1-118">В поле **TargetServerURL**введите URL-адрес сайта SharePoint верхнего уровня или дочернего сайта.</span><span class="sxs-lookup"><span data-stu-id="ae5f1-118">For **TargetServerURL**, type a URL to a SharePoint top-level site or subsite.</span></span> <span data-ttu-id="ae5f1-119">Если сайт не указан, используется сайт верхнего уровня по умолчанию (например,, *http://servername* *http://servername/site* или *http://servername/site/subsite* ).</span><span class="sxs-lookup"><span data-stu-id="ae5f1-119">If you do not specify a site, the default top-level site is used (for example, *http://servername*, *http://servername/site*, or *http://servername/site/subsite*).</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="ae5f1-120">В обозревателе решений щелкните правой кнопкой мыши отчет, который необходимо опубликовать, и выберите команду **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="ae5f1-120">In Solution Explorer, right-click the report you want to publish, and click **Deploy**.</span></span> <span data-ttu-id="ae5f1-121">Отчет будет опубликован в местоположении, которое указано в свойстве **TargetReportFolder**.</span><span class="sxs-lookup"><span data-stu-id="ae5f1-121">The report is published to the location specified in **TargetReportFolder**.</span></span> <span data-ttu-id="ae5f1-122">Ошибки развертывания появляются в окне «Вывод».</span><span class="sxs-lookup"><span data-stu-id="ae5f1-122">Deployment errors appear in the Output window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae5f1-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae5f1-123">See Also</span></span>  
 <span data-ttu-id="ae5f1-124">[Диалоговое окно "страницы свойств проекта"](../tools/project-property-pages-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="ae5f1-124">[Project Property Pages Dialog Box](../tools/project-property-pages-dialog-box.md) </span></span>  
 <span data-ttu-id="ae5f1-125">[Задание свойств развертывания &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="ae5f1-125">[Set Deployment Properties &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span></span>  
 <span data-ttu-id="ae5f1-126">[Публикация отчетов на сервере отчетов](publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="ae5f1-126">[Publishing Reports to a Report Server](publishing-reports-to-a-report-server.md) </span></span>  
 <span data-ttu-id="ae5f1-127">[Примеры URL-адресов для элементов опубликованного отчета на сервере отчетов в режиме интеграции с SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="ae5f1-127">[URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span></span>  
 [<span data-ttu-id="ae5f1-128">Использование ODC-файла подключения к данным Office в отчетах (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="ae5f1-128">Use an Office Data Connection &#40;.odc&#41; with Reports &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../report-data/use-an-office-data-connection-odc-with-reports.md)  
  
  
