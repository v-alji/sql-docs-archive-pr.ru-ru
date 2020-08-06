---
title: Просмотр Reporting Services отчетов на устройствах Microsoft Surface и устройствах Apple iOS | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- iPad
- Safari
- SSRS
- Report Viewer [Reporting Services]
- iOS
ms.assetid: 2124bcf5-d60a-475f-a4ae-de6df44d2860
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: db52ed500559969ae52eb9477caa6b410889c1d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666423"
---
# <a name="view-reporting-services-reports-on-microsoft-surface-devices-and--apple-ios-devices"></a><span data-ttu-id="b57a3-102">Просмотр отчетов служб Reporting Services на устройствах с Microsoft Surface и Apple iOS</span><span class="sxs-lookup"><span data-stu-id="b57a3-102">View Reporting Services Reports on Microsoft Surface Devices and  Apple iOS Devices</span></span>
  <span data-ttu-id="b57a3-103">В этой статье описаны функции и рабочие процессы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , поддерживаемые для планшета Microsoft Surface и устройств с Apple iOS 6 и Apple Safari, таких как iPad.</span><span class="sxs-lookup"><span data-stu-id="b57a3-103">This article describes the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features and workflows supported for Microsoft Surface devices, and devices with Apple iOS 6 and Apple Safari such as the iPad.</span></span>

## <a name="view-and-interact-with-reports"></a><span data-ttu-id="b57a3-104">Представление и взаимодействие с помощью отчетов</span><span class="sxs-lookup"><span data-stu-id="b57a3-104">View and Interact With Reports</span></span>
 <span data-ttu-id="b57a3-105">Начиная с версии [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] поддерживает просмотр и базовое взаимодействие с отчетами для планшета Microsoft Surface и устройств с браузерами Apple iOS 6 и Apple Safari, таких как iPad.</span><span class="sxs-lookup"><span data-stu-id="b57a3-105">Starting with [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] supports viewing and basic interactivity with reports on Microsoft Surface devices, and devices with Apple iOS 6 and Apple Safari browser such as the iPad.</span></span> <span data-ttu-id="b57a3-106">Также можно публиковать отчеты с помощью устройств Microsoft Surface.</span><span class="sxs-lookup"><span data-stu-id="b57a3-106">You can also publish reports using Microsoft Surface devices.</span></span>

 <span data-ttu-id="b57a3-107">![IPad Desktop](media/videothumbnail.jpg "Рабочий стол IPad") Посмотрите демонстрацию просмотра отчетов на iPad.</span><span class="sxs-lookup"><span data-stu-id="b57a3-107">![IPad Desktop](media/videothumbnail.jpg "IPad Desktop") Watch a demonstration of viewing reports on an iPad.</span></span>

 <span data-ttu-id="b57a3-108">Можно также просматривать отчеты служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] на устройстве Windows Phone 8.</span><span class="sxs-lookup"><span data-stu-id="b57a3-108">You can also view [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports on a Windows Phone 8 device.</span></span>

 <span data-ttu-id="b57a3-109">Чтобы использовать функции, описанные в этом разделе, установите одно из следующего.</span><span class="sxs-lookup"><span data-stu-id="b57a3-109">To utilize the features described in this topic, install one of the following:</span></span>

-   <span data-ttu-id="b57a3-110">Для использования сервера отчетов с собственным режимом установите [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] или последующую версию.</span><span class="sxs-lookup"><span data-stu-id="b57a3-110">For a native mode report server, install [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] or later.</span></span>

     [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)]<span data-ttu-id="b57a3-111">доступен для загрузки из [центра загрузки Майкрософт](https://www.microsoft.com/download/details.aspx?id=35575).</span><span class="sxs-lookup"><span data-stu-id="b57a3-111">is available for download from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=35575).</span></span>

-   <span data-ttu-id="b57a3-112">Для сервера отчетов в режиме SharePoint установите [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] или более позднюю версию надстройки [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] для продуктов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b57a3-112">For a SharePoint mode report server, install [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] or later of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span>

 <span data-ttu-id="b57a3-113">**Просмотр и взаимодействие с отчетом на устройстве iPad или устройстве Microsoft Surface**</span><span class="sxs-lookup"><span data-stu-id="b57a3-113">**To view and interact with a report on an iPad device or Microsoft Surface device**</span></span>

1.  <span data-ttu-id="b57a3-114">Убедитесь, что можно подключиться к серверу отчетов или сайту SharePoint, где находится отчет.</span><span class="sxs-lookup"><span data-stu-id="b57a3-114">Make sure that you can connect to the report server or SharePoint site where the report resides.</span></span>

2.  <span data-ttu-id="b57a3-115">Откройте отчет, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="b57a3-115">Open the report by doing one of the following.</span></span>

    -   <span data-ttu-id="b57a3-116">**Начните с электронной почты.** В сообщении электронной почты, созданном при помощи подписки [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , выберите URL-адрес отчета.</span><span class="sxs-lookup"><span data-stu-id="b57a3-116">**Start from e-mail:** From an e-mail that is created by a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] subscription, tap the URL of the report.</span></span> <span data-ttu-id="b57a3-117">Отчет откроется в браузере.</span><span class="sxs-lookup"><span data-stu-id="b57a3-117">The report will open in the browser.</span></span>

    -   <span data-ttu-id="b57a3-118">**Запуск с сервера отчетов:** Чтобы запустить отчет, откройте каталог на сервере отчетов [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] и выберите имя отчета.</span><span class="sxs-lookup"><span data-stu-id="b57a3-118">**Start from Report Server:** Browse the directory on the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server, and then tap the report name to open the report.</span></span>

    -   <span data-ttu-id="b57a3-119">**Запуск из библиотеки документов SharePoint:** Откройте библиотеку документов SharePoint, в которой хранятся отчеты [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , и выберите имя отчета.</span><span class="sxs-lookup"><span data-stu-id="b57a3-119">**Start from a SharePoint document library:** Browse to a SharePoint document library that contains [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports, and then tap the report name.</span></span> <span data-ttu-id="b57a3-120">Можно просматривать отчет и работать с ним.</span><span class="sxs-lookup"><span data-stu-id="b57a3-120">You can view and interact with the report.</span></span>

        > [!IMPORTANT]
        >  <span data-ttu-id="b57a3-121"> При использовании iPad свойство **Скрытый просмотр** в Safari должно быть отключено.</span><span class="sxs-lookup"><span data-stu-id="b57a3-121">For the iPad, ensure that the **Private Browsing** property for Safari is turned off.</span></span>

    -   <span data-ttu-id="b57a3-122">**Веб-часть SharePoint:** Если на страницу SharePoint была добавлена веб-часть, то можно просматривать отчеты [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b57a3-122">**SharePoint web part:** If the web part has been added to a SharePoint page, you can view [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports.</span></span>

3.  <span data-ttu-id="b57a3-123">На устройстве Microsoft Surface можно также открыть отчет с использованием диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b57a3-123">On your Microsoft Surface device, you can also open the report by using Report Manager.</span></span> <span data-ttu-id="b57a3-124">Просмотрите каталог в диспетчере отчетов [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] и выберите имя отчета, чтобы открыть его.</span><span class="sxs-lookup"><span data-stu-id="b57a3-124">Browse the directory in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Manager, and then tap the report name to open the report.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="b57a3-125">Просмотр отчетов в диспетчере отчетов не поддерживается на iPad.</span><span class="sxs-lookup"><span data-stu-id="b57a3-125">Viewing reports in Report Manager is not supported on an iPad.</span></span>

4.  <span data-ttu-id="b57a3-126">Прокручивайте и увеличивайте отчет, выполняя следующее.</span><span class="sxs-lookup"><span data-stu-id="b57a3-126">Scroll and zoom by doing the following.</span></span>

    -   <span data-ttu-id="b57a3-127">Для прокрутки отчета проведите пальцем по экрану (вверх, вниз, влево или вправо).</span><span class="sxs-lookup"><span data-stu-id="b57a3-127">To scroll the report, drag your finger across the screen (up, down, left or right).</span></span> <span data-ttu-id="b57a3-128">Это жест «скольжение».</span><span class="sxs-lookup"><span data-stu-id="b57a3-128">This is the swipe gesture.</span></span>

    -   <span data-ttu-id="b57a3-129">Для увеличения установите два пальца на экране и разведите их.</span><span class="sxs-lookup"><span data-stu-id="b57a3-129">To zoom in, place two fingers on the screen and separate the fingers.</span></span> <span data-ttu-id="b57a3-130">Для уменьшения установите два пальца на экране и сведите их.</span><span class="sxs-lookup"><span data-stu-id="b57a3-130">To zoom out, place two fingers on the screen and move the fingers together.</span></span> <span data-ttu-id="b57a3-131">Это жест «щипок».</span><span class="sxs-lookup"><span data-stu-id="b57a3-131">This is the pinch gesture.</span></span>

5.  <span data-ttu-id="b57a3-132">Переходите и взаимодействуйте с отчетом, выполняя следующее.</span><span class="sxs-lookup"><span data-stu-id="b57a3-132">Navigate and interact with the report by doing the following.</span></span>

    -   <span data-ttu-id="b57a3-133">Сворачивать и разворачивать элементы отчета, а также строки и столбцы, связанные с группами, можно, нажимая на значок «плюс» (+) для свертывания и «минус» (-) для развертывания.</span><span class="sxs-lookup"><span data-stu-id="b57a3-133">Collapse and expand report items, and rows and columns that are associated with groups, by taping the plus (+) sign to collapse and the minus (-) sign to expand.</span></span>

    -   <span data-ttu-id="b57a3-134">Переключаться между сортировкой по возрастанию и убыванию для строк в таблице либо строк и столбцов в матрице можно, нажимая кнопку сортировки.</span><span class="sxs-lookup"><span data-stu-id="b57a3-134">Toggle between ascending and descending order for rows in a table or for rows and columns in a matrix, by tapping the sort button.</span></span> <span data-ttu-id="b57a3-135">Кнопка сортировки обычно находится в заголовке столбца.</span><span class="sxs-lookup"><span data-stu-id="b57a3-135">The sort button is usually located in the column header.</span></span>

    -   <span data-ttu-id="b57a3-136">Разворачивать и сворачивать область параметров можно, нажимая кнопку со стрелкой в верхней части отчета.</span><span class="sxs-lookup"><span data-stu-id="b57a3-136">Expand and collapse the parameter pane, by tapping the arrow button near the top of the report.</span></span>

    -   <span data-ttu-id="b57a3-137">Выбрать значение параметра можно, нажав поле или элемент управления рядом с параметром.</span><span class="sxs-lookup"><span data-stu-id="b57a3-137">Select a parameter value by tapping the box or control next to the parameter.</span></span> <span data-ttu-id="b57a3-138">Выберите **Просмотр отчета** , чтобы применить значение параметра к отчету.</span><span class="sxs-lookup"><span data-stu-id="b57a3-138">Tap **View Report** to apply the parameter value to the report.</span></span>

    -   <span data-ttu-id="b57a3-139">Для поиска по содержимому отчета щелкните поле рядом с кнопкой **Найти**, введите термин для поиска, а затем нажмите **Найти**.</span><span class="sxs-lookup"><span data-stu-id="b57a3-139">Search the report content by taping the box next to **Find**, typing a search term, and then taping **Find**.</span></span>

    -   <span data-ttu-id="b57a3-140">Для перехода по страницам отчета используйте кнопки навигации или щелкните текстовое поле рядом с кнопками и введите номер страницы.</span><span class="sxs-lookup"><span data-stu-id="b57a3-140">Navigate the report pages by tapping the navigation buttons, or tapping the text box next to the buttons and typing the page number.</span></span>

    -   <span data-ttu-id="b57a3-141">Для перехода по URL-адресу нажимайте на гиперссылки, добавляемые к таким элементам отчета, как текстовые поля, изображения, диаграммы и датчики.</span><span class="sxs-lookup"><span data-stu-id="b57a3-141">Navigate to URLs by taping hyperlinks that have been added to report items such as text boxes, images, charts, and gauges.</span></span>

    -   <span data-ttu-id="b57a3-142">Для экспорта отчета нажмите значок **раскрывающегося меню экспорта** и выберите формат файла.</span><span class="sxs-lookup"><span data-stu-id="b57a3-142">Export the report by tapping the icon for the **Export drop down menu** and then tapping a file format.</span></span>

        -   <span data-ttu-id="b57a3-143">Если отчет просматривается на устройстве Microsoft Surface, можно экспортировать отчет в один из следующих форматов.</span><span class="sxs-lookup"><span data-stu-id="b57a3-143">If you're viewing the report on a Microsoft Surface device, you can export the report to one of the following formats.</span></span>

            -   <span data-ttu-id="b57a3-144">XML-файл с данными отчета</span><span class="sxs-lookup"><span data-stu-id="b57a3-144">XML file with report data</span></span>

            -   <span data-ttu-id="b57a3-145">CSV (с разделителями-запятыми)</span><span class="sxs-lookup"><span data-stu-id="b57a3-145">CSV (comma delimited)</span></span>

            -   <span data-ttu-id="b57a3-146">PDF</span><span class="sxs-lookup"><span data-stu-id="b57a3-146">PDF</span></span>

            -   <span data-ttu-id="b57a3-147">MHTML (веб-архив)</span><span class="sxs-lookup"><span data-stu-id="b57a3-147">MHTML (web archive)</span></span>

            -   <span data-ttu-id="b57a3-148">Excel</span><span class="sxs-lookup"><span data-stu-id="b57a3-148">Excel</span></span>

            -   <span data-ttu-id="b57a3-149">TIFF</span><span class="sxs-lookup"><span data-stu-id="b57a3-149">TIFF</span></span>

            -   <span data-ttu-id="b57a3-150">Word</span><span class="sxs-lookup"><span data-stu-id="b57a3-150">Word</span></span>

        -   <span data-ttu-id="b57a3-151">Если отчет просматривается на iPad, отчет можно экспортировать в файл TIFF или PDF.</span><span class="sxs-lookup"><span data-stu-id="b57a3-151">If you're viewing the report on an iPad, you can export the report as a TIFF or PDF file.</span></span>

## <a name="authentication"></a><span data-ttu-id="b57a3-152">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="b57a3-152">Authentication</span></span>
 <span data-ttu-id="b57a3-153">Проверка подлинности RSWindowsNTLM и RSWindowsBasic работает с [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] в собственном режиме и iPad.</span><span class="sxs-lookup"><span data-stu-id="b57a3-153">RSWindowsNTLM authentication and RSWindowsBasic authentication work with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in native mode and the iPad.</span></span>

 <span data-ttu-id="b57a3-154">Вообще говоря, рекомендуется использовать RSWindowsBasic в средах, отличных от https, поскольку проверка подлинности этого типа не обеспечивает конфиденциальности при передаче учетных данных.</span><span class="sxs-lookup"><span data-stu-id="b57a3-154">In general, it is recommended that RSWindowsBasic is not used in non-https environments because this type of authentication provides no confidentiality for the transmitted credentials.</span></span>

 <span data-ttu-id="b57a3-155">Дополнительные сведения о проверке подлинности RSWindowsNTLM и RSWindowsBasic см. в разделе [Authentication with the Report Server](security/authentication-with-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="b57a3-155">For more information about RSWindowsNTLM and RSWindowsBasic authentication, see [Authentication with the Report Server](security/authentication-with-the-report-server.md).</span></span>

## <a name="uploading-reports"></a><span data-ttu-id="b57a3-156">Передача отчетов</span><span class="sxs-lookup"><span data-stu-id="b57a3-156">Uploading Reports</span></span>
 <span data-ttu-id="b57a3-157">Отчеты с устройства Microsoft Surface можно публиковать с помощью одного из следующих методов, если у вас есть соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="b57a3-157">You can publish reports from a Microsoft Surface device using one of the following methods, if you have the appropriate permissions.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="b57a3-158">Эти методы не поддерживаются на iPad.</span><span class="sxs-lookup"><span data-stu-id="b57a3-158">These methods are not supported on the iPad.</span></span>

-   <span data-ttu-id="b57a3-159">Передайте файл языка определения отчета (RDL-файл) в библиотеку документов SharePoint. Для этого откройте библиотеку и коснитесь **Передать документ**.</span><span class="sxs-lookup"><span data-stu-id="b57a3-159">Upload a report definition file (.rdl) to a SharePoint document library by opening the library and tapping **Upload Document**.</span></span>

-   <span data-ttu-id="b57a3-160">Передайте файл определения отчета в базу данных сервера отчетов. Для этого откройте диспетчер отчетов и коснитесь **Передать файл**.</span><span class="sxs-lookup"><span data-stu-id="b57a3-160">Upload a report definition file to the report server database by opening Report Manager and tapping **Upload File**.</span></span>

## <a name="additional-information"></a><span data-ttu-id="b57a3-161">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b57a3-161">Additional Information</span></span>
 <span data-ttu-id="b57a3-162">Дополнительные сведения о службах [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] и поддерживаемых браузерах см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="b57a3-162">For more information on [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] and supported browsers, see:</span></span>

-   [<span data-ttu-id="b57a3-163">Планирование поддержки Reporting Services и Power View в браузере &#40;Reporting Services 2014&#41;</span><span class="sxs-lookup"><span data-stu-id="b57a3-163">Planning for Reporting Services and Power View Browser Support &#40;Reporting Services 2014&#41;</span></span>](../../2014/reporting-services/browser-support-for-reporting-services-and-power-view.md)

 <span data-ttu-id="b57a3-164">Дополнительные сведения о бизнес-аналитике Microsoft Business Intelligence и мобильных устройствах см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="b57a3-164">For more information on Microsoft Business Intelligence and Mobile devices, see the following:</span></span>

-   <span data-ttu-id="b57a3-165">[Общие сведения о мобильных устройствах и SharePoint 2013](https://technet.microsoft.com/library/fp161351\(v=office.15\).aspx) ( https://technet.microsoft.com/library/fp161351(v=office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="b57a3-165">[Overview of mobile devices and SharePoint 2013](https://technet.microsoft.com/library/fp161351\(v=office.15\).aspx) (https://technet.microsoft.com/library/fp161351(v=office.15).aspx).</span></span>

-   <span data-ttu-id="b57a3-166">[Поддерживаемые браузеры мобильных устройств в SharePoint 2013](https://technet.microsoft.com/library/fp161353\(v=office.15\).aspx) ( https://technet.microsoft.com/library/fp161353(v=office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="b57a3-166">[Supported mobile device browsers in SharePoint 2013](https://technet.microsoft.com/library/fp161353\(v=office.15\).aspx) (https://technet.microsoft.com/library/fp161353(v=office.15).aspx).</span></span>

-   <span data-ttu-id="b57a3-167">[Просмотр отчетов и показателей на устройствах Apple iPad (SharePoint Server 2010)](https://technet.microsoft.com/library/hh697482.aspx) ( https://technet.microsoft.com/library/hh697482.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b57a3-167">[Viewing reports and scorecards on Apple iPad devices (SharePoint Server 2010)](https://technet.microsoft.com/library/hh697482.aspx) (https://technet.microsoft.com/library/hh697482.aspx).</span></span>

-   <span data-ttu-id="b57a3-168">[Просмотр отчетов Reporting Services на iPad (видео)](https://technet.microsoft.com/sqlserver/jj873792.aspx) ( https://technet.microsoft.com/sqlserver/jj873792.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b57a3-168">[Viewing Reporting Services Reports on an iPad (video)](https://technet.microsoft.com/sqlserver/jj873792.aspx) (https://technet.microsoft.com/sqlserver/jj873792.aspx).</span></span>

-   [<span data-ttu-id="b57a3-169">Просмотр отчетов служб Reporting Services на устройстве Microsoft Surface RT (видео)</span><span class="sxs-lookup"><span data-stu-id="b57a3-169">Viewing Reporting Services Reports on a Microsoft Surface RT Device (video)</span></span>](https://technet.microsoft.com/sqlserver/dn146017)


