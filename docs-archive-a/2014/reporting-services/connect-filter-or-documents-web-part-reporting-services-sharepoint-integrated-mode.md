---
title: Подключить фильтр или веб-часть документов (Reporting Services в режиме интеграции с SharePoint) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Filter Web Part [Reporting Services]
- SharePoint integration [Reporting Services], Web Parts
- Report Viewer Web Part [Reporting Services]
- Documents Web Part [Reporting Services]
ms.assetid: 6a303135-c0ef-44cd-a423-1cea8df3dcf3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5ea7b9f9aba128052ae6ac7f05ef40517eb50e6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657049"
---
# <a name="connect-filter-or-documents-web-part-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="89b3d-102">установить соединение с веб-частью «Фильтр» или с веб-частью «Документы» (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="89b3d-102">Connect Filter or Documents Web Part (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="89b3d-103">Если используется продукт SharePoint, можно создать панель мониторинга или страницу веб-частей, включающую веб-части «Фильтр» или «Документы» и веб-часть средства просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="89b3d-103">If you are using a SharePoint product, you can create a dashboard or Web Part Page that includes a Filter Web Part or Documents Web part and a Report Viewer Web Part.</span></span> <span data-ttu-id="89b3d-104">Поддерживается версия [!INCLUDE[SPF2010](../includes/spf2010-md.md)] или [!INCLUDE[SPS2010](../includes/sps2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89b3d-104">Supported versions are [!INCLUDE[SPF2010](../includes/spf2010-md.md)] or [!INCLUDE[SPS2010](../includes/sps2010-md.md)].</span></span> <span data-ttu-id="89b3d-105">Также поддерживаются версии [!INCLUDE[winSPServ3](../includes/winspserv3-md.md)] и [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007.</span><span class="sxs-lookup"><span data-stu-id="89b3d-105">Also supported are [!INCLUDE[winSPServ3](../includes/winspserv3-md.md)] or [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007.</span></span> <span data-ttu-id="89b3d-106">С помощью соединения с веб-частью «Фильтр» пользователи, которые выбирают значения фильтра в веб-части «Фильтр», могут отправить значение в параметризованный отчет на той же самой странице.</span><span class="sxs-lookup"><span data-stu-id="89b3d-106">By connecting a Filter Web Part, users who select filter values in a Filter Web Part can send the value to a parameterized report on the same page.</span></span> <span data-ttu-id="89b3d-107">С помощью соединения с веб-частью «Документы» пользователи, выбравшие отчет в библиотеке «Документы», могут просмотреть его в веб-части «Средство просмотра отчетов».</span><span class="sxs-lookup"><span data-stu-id="89b3d-107">By connecting a Documents Web Part, users who click on reports in the Documents library can view the report in an adjacent Report Viewer Web Part.</span></span>  
  
 <span data-ttu-id="89b3d-108">Веб-часть «Фильтр» используется для передачи значений в один или более параметров отчета.</span><span class="sxs-lookup"><span data-stu-id="89b3d-108">The Filter Web Part is used to send values to one or more parameters on a report.</span></span> <span data-ttu-id="89b3d-109">Чтобы использовать веб-часть «Фильтр», необходимо, чтобы параметры отчета были совместимы со значениями, типами данных и форматом, посылаемыми в веб-часть.</span><span class="sxs-lookup"><span data-stu-id="89b3d-109">To use a Filter Web Part, the report must have parameters defined for it that are compatible with the values, data type, and format sent by the Web Part.</span></span>  
  
 <span data-ttu-id="89b3d-110">Веб-часть «Документы» связана с библиотекой «Документы» домашнего веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="89b3d-110">The Documents Web Part is associated with the Documents library of the Home site.</span></span> <span data-ttu-id="89b3d-111">Чтобы просмотреть, добавить или удалить элементы библиотеки «Документы», выберите **Просмотреть все содержимое веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-111">To view, add, or remove items from the Documents library, click **View All Site Content**.</span></span> <span data-ttu-id="89b3d-112">В меню «Библиотеки» выберите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-112">In Libraries, click **Documents**.</span></span> <span data-ttu-id="89b3d-113">Для управления элементами библиотеки «Документы» можно использовать меню **Создание**, **Передача**и **Действия** .</span><span class="sxs-lookup"><span data-stu-id="89b3d-113">You can use the **New**, **Upload**, and **Actions** menu to manage the items in the Documents library.</span></span>  
  
### <a name="to-connect-a-filter-web-part"></a><span data-ttu-id="89b3d-114">Соединение с веб-частью «Фильтр»</span><span class="sxs-lookup"><span data-stu-id="89b3d-114">To connect a Filter Web Part</span></span>  
  
1.  <span data-ttu-id="89b3d-115">Открытие и создание страницы веб-части или инструментальной панели.</span><span class="sxs-lookup"><span data-stu-id="89b3d-115">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="89b3d-116">В меню **Действия веб-сайта** выберите команду **Редактировать страницу**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-116">On the **Site Actions** menu, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="89b3d-117">Нажмите кнопку **Добавить веб-часть**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-117">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="89b3d-118">Во **всех веб-части**в категории **разное** выберите **SQL Server Reporting Services средство просмотра отчетов**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-118">In **All Web Parts**, in the **Miscellaneous** category, select **SQL Server Reporting Services Report Viewer**.</span></span>  
  
5.  <span data-ttu-id="89b3d-119">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-119">Click **Add**.</span></span> <span data-ttu-id="89b3d-120">Веб-часть будет добавлена в верхнюю часть зоны.</span><span class="sxs-lookup"><span data-stu-id="89b3d-120">The Web Part is added at the top of the zone.</span></span>  
  
6.  <span data-ttu-id="89b3d-121">В другой зоне на той же странице веб-части или панели мониторинга щелкните **Добавить веб-часть**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-121">On another zone in the same Web Part page or dashboard, click **Add a Web Part**.</span></span>  
  
7.  <span data-ttu-id="89b3d-122">Во **всех веб-части**в разделе **фильтры** выберите веб-часть.</span><span class="sxs-lookup"><span data-stu-id="89b3d-122">In **All Web Parts**, in the **Filters** section, select a Web Part.</span></span>  
  
8.  <span data-ttu-id="89b3d-123">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-123">Click **Add**.</span></span> <span data-ttu-id="89b3d-124">Веб-часть будет добавлена в верхнюю часть зоны.</span><span class="sxs-lookup"><span data-stu-id="89b3d-124">The Web Part is added at the top of the zone.</span></span>  
  
9. <span data-ttu-id="89b3d-125">В области, содержащей веб-часть, в меню **Правка** веб-части последовательно укажите пункты **Соединения**, **Передать значения фильтров**и выберите пункт **Средство просмотра отчетов** - *имя отчета*.</span><span class="sxs-lookup"><span data-stu-id="89b3d-125">In the zone that contains the Web Part, click the Web Part **edit** menu, point to **Connections**, point to **Send Filter Values To**, and then select **Report Viewer** - *report name*.</span></span>  
  
10. <span data-ttu-id="89b3d-126">Проверьте изменения и сохраните страницу.</span><span class="sxs-lookup"><span data-stu-id="89b3d-126">Check in your changes and save the page.</span></span>  
  
### <a name="to-connect-a-documents-web-part"></a><span data-ttu-id="89b3d-127">Соединение с веб-частью «Документы»</span><span class="sxs-lookup"><span data-stu-id="89b3d-127">To connect a Documents Web Part</span></span>  
  
1.  <span data-ttu-id="89b3d-128">Открытие и создание страницы веб-части или инструментальной панели.</span><span class="sxs-lookup"><span data-stu-id="89b3d-128">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="89b3d-129">В меню **Действия веб-сайта** выберите команду **Редактировать страницу**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-129">On the **Site Actions** menu, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="89b3d-130">Нажмите кнопку **Добавить веб-часть**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-130">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="89b3d-131">В меню **Все веб-части**в разделе **Списки и библиотека** выберите пункт **Документы**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-131">In **All Web Parts**, in the **Lists and Library** section, select **Documents.**</span></span>  
  
5.  <span data-ttu-id="89b3d-132">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-132">Click **Add**.</span></span> <span data-ttu-id="89b3d-133">Веб-часть будет добавлена в верхнюю часть зоны.</span><span class="sxs-lookup"><span data-stu-id="89b3d-133">The Web Part is added at the top of the zone.</span></span>  
  
6.  <span data-ttu-id="89b3d-134">Нажмите кнопку **Применить** в нижней части панели средств, а затем кнопку **ОК** , чтобы закрыть панель.</span><span class="sxs-lookup"><span data-stu-id="89b3d-134">Click **Apply** at the bottom of the tool pane, and then click **OK** to close the pane.</span></span>  
  
7.  <span data-ttu-id="89b3d-135">В другой зоне на той же странице веб-части или панели мониторинга щелкните **Добавить веб-часть**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-135">On another zone in the same Web Part page or dashboard, click **Add a Web Part**.</span></span>  
  
8.  <span data-ttu-id="89b3d-136">В окне **Все веб-части**в категории **Разное** выберите элемент **Средство просмотра отчетов служб SQL Server Reporting Services.**</span><span class="sxs-lookup"><span data-stu-id="89b3d-136">In **All Web Parts**, in the **Miscellaneous** category, select **SQL Server Reporting Services Report Viewer.**</span></span>  
  
9. <span data-ttu-id="89b3d-137">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-137">Click **Add**.</span></span> <span data-ttu-id="89b3d-138">Веб-часть будет добавлена в верхнюю часть зоны.</span><span class="sxs-lookup"><span data-stu-id="89b3d-138">The Web Part is added at the top of the zone.</span></span>  
  
10. <span data-ttu-id="89b3d-139">В области, содержащей веб-часть, в меню **Правка** веб-части последовательно укажите курсор на пункты **Соединения**, **Получить определения отчетов из**и выберите пункт **Документы**.</span><span class="sxs-lookup"><span data-stu-id="89b3d-139">In the zone that contains the Web Part, click the Web Part **edit** menu, point to **Connections**, point to **Get report definitions from**, and then select **Documents**.</span></span>  
  
11. <span data-ttu-id="89b3d-140">Проверьте изменения и сохраните страницу.</span><span class="sxs-lookup"><span data-stu-id="89b3d-140">Check in your changes and save the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89b3d-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="89b3d-141">See Also</span></span>  
 <span data-ttu-id="89b3d-142">[Добавление веб-части "средство просмотра отчетов" на веб-страницу &#40;Reporting Services в режиме интеграции с SharePoint&#41;](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md) </span><span class="sxs-lookup"><span data-stu-id="89b3d-142">[Add the Report Viewer Web Part to a Web Page &#40;Reporting Services in SharePoint Integrated Mode&#41;](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md) </span></span>  
 <span data-ttu-id="89b3d-143">[Веб-часть "средство просмотра отчетов" на сайте SharePoint](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="89b3d-143">[Report Viewer Web Part on a SharePoint Site](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="89b3d-144">Настройка веб-части «Средство просмотра отчетов»</span><span class="sxs-lookup"><span data-stu-id="89b3d-144">Customize the Report Viewer Web Part</span></span>](../../2014/reporting-services/customize-the-report-viewer-web-part.md)  
  
  
