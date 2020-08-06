---
title: Добавление веб-части средства просмотра отчетов на веб-страницу (Reporting Services в режиме интеграции с SharePoint) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], viewing reports
- Web Parts [Reporting Services]
- SharePoint integration [Reporting Services], Web Parts
- Report Viewer Web Part [Reporting Services]
ms.assetid: cac75345-2380-467d-a394-0a2140908a5a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d9b933fad8bc566b3cb0ef04303a85c5f034e620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736045"
---
# <a name="add-the-report-viewer-web-part-to-a-web-page-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="2dfa3-102">добавить на веб-страницу веб-часть средства просмотра отчетов (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="2dfa3-102">Add the Report Viewer Web Part to a Web Page (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="2dfa3-103">Веб-часть «Средство просмотра отчетов» может применяться для просмотра отчетов, запускаемых на сервере отчетов, настроенном для работы в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-103">You can use the Report Viewer Web Part to view reports that run on report server that is configured to run in SharePoint integrated mode.</span></span> <span data-ttu-id="2dfa3-104">Она позволяет отображать файлы определения отчетов (RDL), созданные в построителе отчетов или конструкторе отчетов и переданные в библиотеку.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-104">You can use the Web Part to display report definition (.rdl) files that you created in Report Builder or Report Designer and uploaded to a library.</span></span>  
  
 <span data-ttu-id="2dfa3-105">Веб-часть «Средство просмотра отчетов» может быть добавлена на веб-страницу, если на эту страницу нужно внедрить отчет.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-105">You can add the Report Viewer Web Part to a Web page if you want to embed a report on that page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2dfa3-106">Несмотря на одинаковое имя, веб-часть «Средство просмотра отчетов», устанавливаемая как надстройка служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , и веб-часть «Средство просмотра отчетов», которая находится в файле RSWebParts.cab, отличаются.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-106">Although they have identical names, the Report Viewer Web Part that is installed through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Add-in is different from the Report Viewer Web Part that is included in the RSWebParts.cab file.</span></span> <span data-ttu-id="2dfa3-107">Инструкции в этом разделе относятся, в частности, к веб-части «Средство просмотра отчетов», которая устанавливается в составе надстройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2dfa3-107">The instructions in this topic are specifically for the Report Viewer Web Part that is installed through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Add-in.</span></span>  
  
 <span data-ttu-id="2dfa3-108">Чтобы добавить веб-часть на веб-страницу, необходимо иметь разрешение «Добавление и настройка страниц» на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-108">To add a Web Part to a Web page, you must have the Add and Customize Pages permission at the site level.</span></span> <span data-ttu-id="2dfa3-109">При использовании параметров безопасности по умолчанию это разрешение предоставлено членам группы **Владельцы** , имеющим уровень разрешений «Полный доступ».</span><span class="sxs-lookup"><span data-stu-id="2dfa3-109">If you are using default security settings, this permission is granted to members of the **Owners** group who have the Full Control level of permission.</span></span>  
  
### <a name="to-embed-a-report-in-a-web-page"></a><span data-ttu-id="2dfa3-110">Внедрение отчета на веб-страницу</span><span class="sxs-lookup"><span data-stu-id="2dfa3-110">To embed a report in a Web page</span></span>  
  
1.  <span data-ttu-id="2dfa3-111">Открытие и создание страницы веб-части или инструментальной панели.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-111">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="2dfa3-112">В меню **Действия сайта**выберите пункт **Изменить страницу**.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-112">On **Site Actions**, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="2dfa3-113">Нажмите кнопку **Добавить веб-часть**.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-113">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="2dfa3-114">В списке веб-частей выберите категорию **Разное** , а затем **Средство просмотра отчетов служб SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-114">In the list of web part categories, select the **Miscellaneous** category, and then select **SQL Server Reporting Services Report Viewer**.</span></span>  
  
5.  <span data-ttu-id="2dfa3-115">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-115">Click **Add**.</span></span> <span data-ttu-id="2dfa3-116">Веб-часть будет добавлена в верхнюю часть зоны.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-116">The Web Part is added at the top of the zone.</span></span> <span data-ttu-id="2dfa3-117">Ее можно перетащить в другое расположение внутри зоны.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-117">You can drag it to a different location in the zone.</span></span>  
  
6.  <span data-ttu-id="2dfa3-118">В средстве просмотра щелкните надпись **Щелкните здесь, чтобы открыть панель инструментов**.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-118">Within the viewer, click **Click here to open the tool pane**.</span></span>  
  
7.  <span data-ttu-id="2dfa3-119">Выберите отчет из любой библиотеки коллекции текущего веб-сайта, нажав кнопку обзора (**...**).</span><span class="sxs-lookup"><span data-stu-id="2dfa3-119">Select a report from any library in the current site collection by clicking the browse (**...**) button.</span></span> <span data-ttu-id="2dfa3-120">Также можно ввести URL-адрес отчета.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-120">You can also type the report URL.</span></span> <span data-ttu-id="2dfa3-121">Чтобы определить URL-адрес любого отчета, щелкните его правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-121">To determine the URL for any report, right-click the report and select **Properties**.</span></span> <span data-ttu-id="2dfa3-122">Не нажимайте стрелку вниз рядом с отчетом, URL-адрес отчета на странице «Просмотр свойств» элемента не отражается.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-122">Do not click the down arrow next to the report; the report URL is not indicated in the View Properties page of the item.</span></span> <span data-ttu-id="2dfa3-123">При копировании и вставке URL-адреса из диалогового окна **Свойства** замените символы URL-адреса "%20" пробелом (например, "Company%20Sales" на "Company Sales").</span><span class="sxs-lookup"><span data-stu-id="2dfa3-123">If you copy and paste the URL from the **Properties** dialog box, replace the "%20" URL encoding with a space (for example, "Company%20Sales" should be "Company Sales").</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2dfa3-124">Каждая веб-часть «Средство просмотра отчетов» содержит один отчет.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-124">Each Report Viewer Web Part contains a single report.</span></span> <span data-ttu-id="2dfa3-125">URL-адрес должен представлять полный путь к отчету, находящемуся на текущем сайте SharePoint или на сайте того же веб-приложения или фермы.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-125">The URL must be the fully qualified path to a report that is on the current SharePoint site, or on a site within the same Web application or farm.</span></span> <span data-ttu-id="2dfa3-126">URL-адрес должен указывать на библиотеку документа или папку внутри нее, в которой содержится отчет.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-126">The URL must resolve to a document library or to a folder within a document library that contains the report.</span></span> <span data-ttu-id="2dfa3-127">URL-адрес отчета должен включать расширение RDL-файла.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-127">The report URL must include the .rdl file extension.</span></span> <span data-ttu-id="2dfa3-128">Если отчет зависит от модели или файлов общего источника данных, указывать эти файлы в URL-адресе не обязательно.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-128">If the report depends on a model or shared data source files, you do not need to specify those files in the URL.</span></span> <span data-ttu-id="2dfa3-129">Отчет содержит в себе ссылки на все необходимые файлы.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-129">The report contains references to the files it needs.</span></span>  
  
8.  <span data-ttu-id="2dfa3-130">Пока панель средств открыта, можно установить свойства, чтобы изменить внешний вид по умолчанию и макет.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-130">While the tool pane is open, you can set properties to modify the default appearance and layout.</span></span>  
  
9. <span data-ttu-id="2dfa3-131">Нажмите кнопку **Применить** в нижней части панели средств, а затем кнопку **ОК** , чтобы закрыть панель.</span><span class="sxs-lookup"><span data-stu-id="2dfa3-131">Click **Apply** at the bottom of the tool pane, and then click **OK** to close the pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dfa3-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="2dfa3-132">See Also</span></span>  
 <span data-ttu-id="2dfa3-133">[Веб-часть "средство просмотра отчетов" на сайте SharePoint](../report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="2dfa3-133">[Report Viewer Web Part on a SharePoint Site](../report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 <span data-ttu-id="2dfa3-134">[Настройка веб-части «Средство просмотра отчетов»](../customize-the-report-viewer-web-part.md) </span><span class="sxs-lookup"><span data-stu-id="2dfa3-134">[Customize the Report Viewer Web Part](../customize-the-report-viewer-web-part.md) </span></span>  
 <span data-ttu-id="2dfa3-135">[Предоставление разрешений на элементы сервера отчетов на сайте SharePoint](../security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="2dfa3-135">[Granting Permissions on Report Server Items on a SharePoint Site](../security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="2dfa3-136">Установка или удаление надстройки Reporting Services для SharePoint &#40;SharePoint 2010 и SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="2dfa3-136">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](../install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
