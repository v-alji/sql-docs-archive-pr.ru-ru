---
title: Добавление типов содержимого сервера отчетов в библиотеку (Reporting Services в режиме интеграции с SharePoint) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ac9136c8-9ef4-484c-8e9d-05008a186db5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9e0ee56c235a54920fba5389a61f300eeaa65329
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739605"
---
# <a name="add-report-server-content-types-to-a-library-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="6ff5d-102">добавить в библиотеку типы содержимого сервера отчетов (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="6ff5d-102">Add Report Server Content Types to a Library (Reporting Services in SharePoint Integrated Mode)</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="6ff5d-103">обеспечивают стандартные типы содержимого SharePoint, предназначенные для управления файлами общих источников данных (RSDS), моделей отчетов (SMDL) и определений отчетов (RDL) построителя отчетов.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-103">provides predefined SharePoint content types that are used to manage shared data source (.rsds) files, report models (.smdl), and Report Builder report definition (.rdl) files.</span></span> <span data-ttu-id="6ff5d-104">После добавления в библиотеку типов содержимого **Отчет построителя отчетов**, **Модель отчета**и **Источник данных отчета** становится доступной команда **Создать** , позволяющая создавать новые документы этих типов.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-104">Adding a **Report Builder Report**, **Report Model**, and **Report Data Source** content type to a library enables the **New** command so that you can create new documents of that type.</span></span>  
  
 <span data-ttu-id="6ff5d-105">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Режим интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="6ff5d-105">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>  
  
 <span data-ttu-id="6ff5d-106">Добавить типы содержимого в библиотеку может администратор веб-сайта или пользователь с разрешениями уровня «Полный доступ».</span><span class="sxs-lookup"><span data-stu-id="6ff5d-106">To add content types to a library, you must be a site administrator or have Full Control level of permission.</span></span>  
  
 <span data-ttu-id="6ff5d-107">Типы содержимого служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] и управление типами содержимого будут автоматически включены во всех библиотеках документов для существующих семейств веб-сайтов, созданных на основе следующего шаблона сайта **Центра-бизнес аналитики** .</span><span class="sxs-lookup"><span data-stu-id="6ff5d-107">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types and content type management will automatically be enabled in all document libraries for existing site collections created from the following **Business Intelligence Center** site template.</span></span>  
  
 <span data-ttu-id="6ff5d-108">Для сайтов, созданных после интеграции служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , типы содержимого служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] включены не будут.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-108">Sites created after the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] integration will not have the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types enabled.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="6ff5d-109">Если вы еще **не** настроили типы содержимого для библиотеки, то сначала включите управление типами содержимого, а затем включите типы содержимого [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ff5d-109">If you have **not** previously configured content types for a library, first enable management of content types, then enable the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types.</span></span> <span data-ttu-id="6ff5d-110">Процедуры включения управления типами содержимого приведены в библиотеке одного документа.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-110">See the procedures on enabling content type management in a single document library.</span></span>  
  
 <span data-ttu-id="6ff5d-111">**Короткий видеоролик** [(SSRS) включение типов содержимого в SharePoint2010.wmv](http://www.youtube.com/watch?v=yqhm3DrtT1w) (http://www.youtube.com/watch?v=yqhm3DrtT1w).</span><span class="sxs-lookup"><span data-stu-id="6ff5d-111">**Short video:** [(SSRS) Enabling Content Types in SharePoint2010.wmv](http://www.youtube.com/watch?v=yqhm3DrtT1w) (http://www.youtube.com/watch?v=yqhm3DrtT1w).</span></span>  
  
 <span data-ttu-id="6ff5d-112">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="6ff5d-112">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="6ff5d-113">Включение типов содержимого во всех библиотеках документов в существующем центре бизнес-аналитики</span><span class="sxs-lookup"><span data-stu-id="6ff5d-113">Enable content types in all document libraries in an existing BI center</span></span>](#bkmk_enable_all)  
  
-   [<span data-ttu-id="6ff5d-114">Активация управления типами содержимого для одной библиотеки документов (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="6ff5d-114">To enable content type management for a single document library (SharePoint 2013)</span></span>](#bkmk_enable_content_management)  
  
-   [<span data-ttu-id="6ff5d-115">Добавление типов содержимого Reporting Services (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="6ff5d-115">To add Reporting Services content types (SharePoint 2013)</span></span>](#bkmk_add_single)  
  
-   [<span data-ttu-id="6ff5d-116">Активация управления типами содержимого для одной библиотеки документов (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="6ff5d-116">To enable content type management for a single document library (SharePoint 2010)</span></span>](#bkmk_enable_content_management_2010)  
  
-   [<span data-ttu-id="6ff5d-117">Добавление типов содержимого сервера отчетов в библиотеку (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="6ff5d-117">To add report server content types (SharePoint 2010)</span></span>](#bkmk_add_single_2010)  
  
-   [<span data-ttu-id="6ff5d-118">Включение типов содержимого и управления содержимым для нескольких сайтов бизнес-аналитики</span><span class="sxs-lookup"><span data-stu-id="6ff5d-118">To enable Content types and content management for multiple BI sites</span></span>](#bkmk_enable_multiple_sites)  
  
##  <a name="enable-content-types-in-all-document-libraries-in-an-existing-bi-center"></a><a name="bkmk_enable_all"></a><span data-ttu-id="6ff5d-119">Включение типов содержимого во всех библиотеках документов в существующем центре бизнес-аналитики</span><span class="sxs-lookup"><span data-stu-id="6ff5d-119">Enable content types in all document libraries in an existing BI center</span></span>  
  
1.  <span data-ttu-id="6ff5d-120">Чтобы включить типы содержимого и управление содержимым во всех библиотеках документов в существующем сайте **центра бизнес-аналитики** , можно переключить компонент интеграции служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ff5d-120">To enable the content types and content management in all document libraries in an existing **Business Intelligence Center** site, you can toggle the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] integration feature.</span></span>  
  
2.  <span data-ttu-id="6ff5d-121">Перейдите в раздел **Параметры сайта**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-121">Go to **Site settings**.</span></span>  
  
    -   <span data-ttu-id="6ff5d-122">В SharePoint 2013 щелкните значок **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="6ff5d-122">In SharePoint 2013, click the **Settings** icon.</span></span> <span data-ttu-id="6ff5d-123">![Параметры SharePoint](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "Параметры SharePoint")</span><span class="sxs-lookup"><span data-stu-id="6ff5d-123">![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings")</span></span>  
  
    -   <span data-ttu-id="6ff5d-124">В SharePoint 2010 щелкните **Действия сайта**и выберите **Параметры сайта**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-124">In SharePoint 2010, click **Site Actions**, then click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="6ff5d-125">Щелкните **Компоненты семейства веб-сайтов**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-125">Click **Site collection features**.</span></span>  
  
4.  <span data-ttu-id="6ff5d-126">Найдите в списке пункт **Компонент интеграции с сервером отчетов** и щелкните **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-126">Find the **Report Server Integration Feature** and click **Deactivate**.</span></span>  
  
     <span data-ttu-id="6ff5d-127">![rs_reportserver_integration_active](media/rs-reportserver-integration-active.gif "rs_reportserver_integration_active")</span><span class="sxs-lookup"><span data-stu-id="6ff5d-127">![rs_reportserver_integration_active](media/rs-reportserver-integration-active.gif "rs_reportserver_integration_active")</span></span>  
  
5.  <span data-ttu-id="6ff5d-128">Обновите браузер, а затем щелкните **Активировать** для пункта **Компонент интеграции с сервером отчетов**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-128">Refresh the browser then click **Activate** for the **Report Server Integration Feature**.</span></span>  
  
    <span data-ttu-id="6ff5d-129">![Отключение](media/rs-reportserver-integration-deactivate.gif "rs_reportserver_integration_deactive")</span><span class="sxs-lookup"><span data-stu-id="6ff5d-129">![Deactivate](media/rs-reportserver-integration-deactivate.gif "rs_reportserver_integration_deactive")</span></span>  
  
##  <a name="to-enable-content-type-management-for-a-single-document-library-sharepoint-2013"></a><a name="bkmk_enable_content_management"></a><span data-ttu-id="6ff5d-130">Включение управления типами содержимого для одной библиотеки документов (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="6ff5d-130">To enable content type management for a single document library (SharePoint 2013)</span></span>  
  
1.  <span data-ttu-id="6ff5d-131">Откройте библиотеку, для которой нужно активировать несколько типов содержимого.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-131">Open the library for which you want to enable multiple content types.</span></span>  
  
2.  <span data-ttu-id="6ff5d-132">На ленте нажмите кнопку **Библиотека** .</span><span class="sxs-lookup"><span data-stu-id="6ff5d-132">Click **Library** in the ribbon.</span></span>  
  
     <span data-ttu-id="6ff5d-133">![rs_SharePoint2013_LibraryRibbon](media/rs-sharepoint2013-libraryribbon.gif "rs_SharePoint2013_LibraryRibbon")</span><span class="sxs-lookup"><span data-stu-id="6ff5d-133">![rs_SharePoint2013_LibraryRibbon](media/rs-sharepoint2013-libraryribbon.gif "rs_SharePoint2013_LibraryRibbon")</span></span>  
  
3.  <span data-ttu-id="6ff5d-134">На ленте **Библиотека** щелкните **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-134">On the **Library** ribbon, click **Library Settings**.</span></span> <span data-ttu-id="6ff5d-135">Если вы не видите кнопки **Параметры библиотеки** или если она неактивна, значит у вас нет разрешения на настройку параметров библиотеки, включая типы содержимого.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-135">If you do not see **Library Settings** or the button is disabled, you do not have permission to configure library settings, including content types.</span></span>  
  
     <span data-ttu-id="6ff5d-136">![rs_SharePoint2013_LibrarySettings](media/rs-sharepoint2013-librarysettings.gif "rs_SharePoint2013_LibrarySettings")</span><span class="sxs-lookup"><span data-stu-id="6ff5d-136">![rs_SharePoint2013_LibrarySettings](media/rs-sharepoint2013-librarysettings.gif "rs_SharePoint2013_LibrarySettings")</span></span>  
  
4.  <span data-ttu-id="6ff5d-137">В разделе **Общие параметры** щелкните **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-137">In the **General Settings** section, click **Advanced settings**.</span></span>  
  
     <span data-ttu-id="6ff5d-138">![rs_SharePoint2013_LibrarySettings_AdvancedSettings](media/rs-sharepoint2013-librarysettings-advancedsettings.gif "rs_SharePoint2013_LibrarySettings_AdvancedSettings")</span><span class="sxs-lookup"><span data-stu-id="6ff5d-138">![rs_SharePoint2013_LibrarySettings_AdvancedSettings](media/rs-sharepoint2013-librarysettings-advancedsettings.gif "rs_SharePoint2013_LibrarySettings_AdvancedSettings")</span></span>  
  
5.  <span data-ttu-id="6ff5d-139">В разделе **Типы содержимого** выберите **Да** , чтобы разрешить управление типами содержимого.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-139">In the **Content Types** section, select **Yes** to allow management of content types.</span></span>  
  
6.  <span data-ttu-id="6ff5d-140">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-140">Click **OK**.</span></span>  
  
##  <a name="to-add-reporting-services-content-types-sharepoint-2013"></a><a name="bkmk_add_single"></a> <span data-ttu-id="6ff5d-141">Добавление типов содержимого служб Reporting Services (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="6ff5d-141">To add Reporting Services content types (SharePoint 2013)</span></span>  
  
1.  <span data-ttu-id="6ff5d-142">Откройте библиотеку, для которой нужно добавить типы содержимого служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-142">Open the library for which you want to add Reporting Services content types.</span></span>  
  
2.  <span data-ttu-id="6ff5d-143">На ленте нажмите кнопку **Библиотека**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-143">On the ribbon, click **Library**.</span></span>  
  
3.  <span data-ttu-id="6ff5d-144">Нажмите кнопку **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-144">Click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="6ff5d-145">В разделе **Типы содержимого**выберите пункт **Добавить из типов содержимого существующего веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-145">Under **Content Types**, click **Add from existing site content types**.</span></span>  
  
5.  <span data-ttu-id="6ff5d-146">В разделе **Выберите типы содержимого сайта из списка**выберите элемент **Типы содержимого служб SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-146">In **Select site content types from**, select **SQL Server Reporting Services Content Types**.</span></span>  
  
6.  <span data-ttu-id="6ff5d-147">В списке **Типы содержимого веб-сайта** щелкните элемент **Построитель отчетов**, а затем нажмите кнопку **Добавить** , чтобы переместить выбранный тип содержимого в список **Добавляемые типы содержимого** .</span><span class="sxs-lookup"><span data-stu-id="6ff5d-147">In the **Available Site Content Types** list, click **Report Builder**, and then click **Add** to move the selected content type to the **Content types to add** list.</span></span>  
  
7.  <span data-ttu-id="6ff5d-148">Чтобы добавить типы содержимого **Модель отчета** и **Источник данных отчета** , повторите предыдущий шаг.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-148">To add **Report Model** and **Report Data Source** content types, repeat the previous step.</span></span>  
  
8.  <span data-ttu-id="6ff5d-149">После завершения добавления типов содержимого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-149">When you finish adding content types, click **OK**.</span></span>  
  
9. > [!NOTE]  
    >  <span data-ttu-id="6ff5d-150"> Если группа типов содержимого [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]**Типы содержимого служб SQL Server Reporting Services** не отображается на странице **Добавление типов содержимого** , одно из нижеследующего будет верно.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-150">If the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content type group **SQL Server Reporting Services Content Types** is not visible on the **Add Content Types** page, one of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="6ff5d-151">Надстройка служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] для продуктов SharePoint еще не установлена.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-151">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products has not been installed.</span></span> <span data-ttu-id="6ff5d-152">Дополнительные сведения см. [в разделе Установка или удаление надстройки Reporting Services для sharepoint &#40;sharepoint 2010 и sharepoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="6ff5d-152">For more information, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span> <span data-ttu-id="6ff5d-153">Раздел включает сведения об установке надстройки и пошаговом выполнении установки файлов надстройки для обхода проблем.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-153">The topic includes information on installing the add-in and stepping through a files only installation of the add-in to work around issues.</span></span>  
  
    -   <span data-ttu-id="6ff5d-154">Надстройка установлена, но компонент коллекции сайтов **Компонент интеграции сервера отчетов** неактивен.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-154">The add-in is installed but the site collection feature **Report Server Integration Feature** is not active.</span></span> <span data-ttu-id="6ff5d-155">Проверьте компонент коллекции сайтов в разделе **Параметр сайта**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-155">Verify the site collection feature in **Site Settings**.</span></span>  
  
    -   <span data-ttu-id="6ff5d-156">Все типы содержимого служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] уже добавлены в библиотеку.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-156">All of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types have already been added to the library.</span></span> <span data-ttu-id="6ff5d-157">Если типы содержимого уже есть в библиотеке, группа удаляется со страницы **Добавление типов содержимого** .</span><span class="sxs-lookup"><span data-stu-id="6ff5d-157">If all the content types are part of a library, then the group is removed from the **Add Content Types** page.</span></span> <span data-ttu-id="6ff5d-158">Если удалить один или несколько типов содержимого служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , группа **Типы содержимого служб SQL Server Reporting Services** снова появится на странице **Добавление типов содержимого** .</span><span class="sxs-lookup"><span data-stu-id="6ff5d-158">If you delete one or more of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types, then the group **SQL Server Reporting Services Content Types** will be visible on the **Add Content Types** page.</span></span>  
  
##  <a name="to-enable-content-type-management-for-a-single-document-library-sharepoint-2010"></a><a name="bkmk_enable_content_management_2010"></a><span data-ttu-id="6ff5d-159">Включение управления типами содержимого для одной библиотеки документов (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="6ff5d-159">To enable content type management for a single document library (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="6ff5d-160">Откройте библиотеку, для которой нужно активировать несколько типов содержимого.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-160">Open the library for which you want to enable multiple content types.</span></span> <span data-ttu-id="6ff5d-161">На панели меню библиотеки должны быть представлены следующие меню: **Создать**, **Передать**, **Действия**и **Настройки**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-161">On the library menu bar, you should see the following menus: **New**, **Upload**, **Actions**, and **Settings**.</span></span> <span data-ttu-id="6ff5d-162">Если меню **Параметры**отсутствует, то пользователь не имеет разрешения на добавление типа содержимого.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-162">If you do not see **Settings**, you do not have permission to add a content type.</span></span>  
  
2.  <span data-ttu-id="6ff5d-163">На ленте **Средства работы с библиотекой** щелкните **Библиотека**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-163">On the **Library Tools** ribbon, click **Library**.</span></span>  
  
     <span data-ttu-id="6ff5d-164">![rs_SharePoint2010_LibraryRibbon](media/rs-sharepoint2010-libraryribbon.gif "rs_SharePoint2010_LibraryRibbon")</span><span class="sxs-lookup"><span data-stu-id="6ff5d-164">![rs_SharePoint2010_LibraryRibbon](media/rs-sharepoint2010-libraryribbon.gif "rs_SharePoint2010_LibraryRibbon")</span></span>  
  
3.  <span data-ttu-id="6ff5d-165">В группе ленты **Параметры** выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-165">On the **Settings** ribbon group, click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="6ff5d-166">В разделе **Общие параметры**выберите **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-166">Under **General Settings**, click **Advanced settings**.</span></span>  
  
5.  <span data-ttu-id="6ff5d-167">В разделе **Типы содержимого** выберите **Да** , чтобы разрешить управление типами содержимого.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-167">In the **Content Types** section, select **Yes** to allow management of content types.</span></span>  
  
6.  <span data-ttu-id="6ff5d-168">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-168">Click **OK**.</span></span>  
  
##  <a name="to-add-report-server-content-types-sharepoint-2010"></a><a name="bkmk_add_single_2010"></a><span data-ttu-id="6ff5d-169">Добавление типов содержимого сервера отчетов (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="6ff5d-169">To add report server content types (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="6ff5d-170">Откройте библиотеку, для которой нужно добавить типы содержимого служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-170">Open the library for which you want to add Reporting Services content types.</span></span>  
  
2.  <span data-ttu-id="6ff5d-171">На вкладках ленты **Средства библиотеки** выберите вкладку **Библиотека**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-171">On the **Library Tools** ribbon tabs, click the **Library tab**.</span></span>  
  
3.  <span data-ttu-id="6ff5d-172">В группе ленты **Параметры** выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-172">On the **Settings** ribbon group, click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="6ff5d-173">В разделе **Типы содержимого**выберите пункт **Добавить из типов содержимого существующего веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-173">Under **Content Types**, click **Add from existing site content types**.</span></span>  
  
5.  <span data-ttu-id="6ff5d-174">В разделе **Выбор типов содержимого** в **Выбрать типы содержимого сайта из списка**нажмите кнопку со стрелкой, чтобы выбрать элемент **Типы содержимого служб SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-174">In the **Select Content Types** section, in **Select site content types from**, click the arrow to select **SQL Server Reporting Services Content Types**.</span></span>  
  
6.  <span data-ttu-id="6ff5d-175">В списке **Типы содержимого веб-сайта** щелкните элемент **Построитель отчетов**, а затем нажмите кнопку **Добавить** , чтобы переместить выбранный тип содержимого в список **Добавляемые типы содержимого** .</span><span class="sxs-lookup"><span data-stu-id="6ff5d-175">In the **Available Site Content Types** list, click **Report Builder**, and then click **Add** to move the selected content type to the **Content types to add** list.</span></span>  
  
7.  <span data-ttu-id="6ff5d-176">Чтобы добавить типы содержимого **Модель отчета** и **Источник данных отчета** , повторите предыдущий шаг.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-176">To add **Report Model** and **Report Data Source** content types, repeat the previous step.</span></span>  
  
8.  <span data-ttu-id="6ff5d-177">После завершения добавления типов содержимого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-177">When you finish adding content types, click **OK**.</span></span>  
  
##  <a name="to-enable-content-types-and-content-management-for-multiple-bi-sites"></a><a name="bkmk_enable_multiple_sites"></a><span data-ttu-id="6ff5d-178">Включение типов содержимого и управления содержимым для нескольких сайтов бизнес-аналитики</span><span class="sxs-lookup"><span data-stu-id="6ff5d-178">To enable Content types and content management for multiple BI sites</span></span>  
  
1.  <span data-ttu-id="6ff5d-179">Для серверов отчетов SQL Server Reporting Services 2008 и 2008 R2 можно включить типы содержимого и управление содержимым для нескольких сайтов центра бизнес-аналитики:</span><span class="sxs-lookup"><span data-stu-id="6ff5d-179">For SQL Server Reporting Services 2008 and 2008 R2 report servers, you can enable content types and content management for multiple Business Intelligence Center sites:</span></span>  
  
2.  <span data-ttu-id="6ff5d-180">В центре администрирования SharePoint выберите **Общие параметры приложения**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-180">In SharePoint Central Administration, click **General Applications settings**.</span></span> <span data-ttu-id="6ff5d-181">В разделе **SQL Server Reporting Services (2008 и 2008 R2)** щелкните **Интеграция со службами Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-181">In the **SQL Server Reporting Services (2008 and 2008 R2)** section, click **Reporting Services Integration**.</span></span>  
  
     <span data-ttu-id="6ff5d-182">![rs_general_app_settings](media/rs-general-app-settings.gif "rs_general_app_settings")</span><span class="sxs-lookup"><span data-stu-id="6ff5d-182">![rs_general_app_settings](media/rs-general-app-settings.gif "rs_general_app_settings")</span></span>  
  
3.  <span data-ttu-id="6ff5d-183">Щелкните **Включить функции во всех имеющихся семействах веб-сайтов**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-183">Click **Activate feature in all exciting site collections**.</span></span>  
  
     <span data-ttu-id="6ff5d-184">![rs_general_app_settings_old_integrations](media/rs-general-app-settings-old-integrations.gif "rs_general_app_settings_old_integrations")</span><span class="sxs-lookup"><span data-stu-id="6ff5d-184">![rs_general_app_settings_old_integrations](media/rs-general-app-settings-old-integrations.gif "rs_general_app_settings_old_integrations")</span></span>  
  
4.  <span data-ttu-id="6ff5d-185">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6ff5d-185">Click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ff5d-186">См. также:</span><span class="sxs-lookup"><span data-stu-id="6ff5d-186">See Also</span></span>  
 <span data-ttu-id="6ff5d-187">[Справочник по разрешениям сайтов и списков SharePoint для элементов сервера отчетов](security/sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="6ff5d-187">[SharePoint Site and List Permission Reference for Report Server Items](security/sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span></span>  
 [<span data-ttu-id="6ff5d-188">Запуск построитель отчетов &#40;построитель отчетов&#41;</span><span class="sxs-lookup"><span data-stu-id="6ff5d-188">Start Report Builder &#40;Report Builder&#41;</span></span>](report-builder/start-report-builder.md)  
  
  
