---
title: Активация компонента Синхронизация файлов сервера отчетов в центре администрирования SharePoint | Документация Майкрософт
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 03/06/2017
ms.openlocfilehash: 55feac69da85c7287ea56f4b8245350dd7e69565
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665883"
---
# <a name="activate-the-report-server-file-sync-feature-in-sharepoint-central-administration"></a><span data-ttu-id="6b0e8-102">активировать функции синхронизации файлов сервера отчетов в центре администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="6b0e8-102">Activate the Report Server File Sync Feature in SharePoint Central Administration</span></span>

<span data-ttu-id="6b0e8-103">Функция синхронизации файлов сервера отчетов служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] использует обработчики событий SharePoint для синхронизации каталога сервера отчетов с элементами в библиотеках документов.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-103">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Server File Sync feature utilizes SharePoint event handlers to synchronize the report server catalog with items in document libraries.</span></span> <span data-ttu-id="6b0e8-104">Эта функция может оказаться полезной в том случае, если пользователи часто передают элементы опубликованных отчетов напрямую в библиотеки документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-104">This feature is beneficial when users frequently upload published report items directly to SharePoint document libraries.</span></span> <span data-ttu-id="6b0e8-105">Если функция синхронизации файлов не активирована, содержимое будет по-прежнему синхронизировано, но не так часто.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-105">If the file Sync feature isn't activated, content will still be synchronized but not as frequently.</span></span>  
  
<span data-ttu-id="6b0e8-106">Функция синхронизации файлов активируется в центре администрирования сайта SharePoint после установки надстройки служб [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] для продуктов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-106">The File Sync feature can be activated in SharePoint Site Administration after you install the [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] Add-in for SharePoint products.</span></span>  
  
<span data-ttu-id="6b0e8-107">Эту функцию можно активировать и деактивировать вручную не на уровне семейства веб-сайтов, а раздельно для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-107">This feature can be manually activated and deactivated per site but not at the site collection level.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6b0e8-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6b0e8-108">Prerequisites</span></span>  
 <span data-ttu-id="6b0e8-109">Надстройка служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] для SharePoint должна быть установлена.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-109">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Add-in for SharePoint must be installed.</span></span> <span data-ttu-id="6b0e8-110">Если надстройка не установлена, функция синхронизации файлов не будет отображаться в списке возможностей сайта.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-110">If the add-in isn't installed, the file sync feature won't be visible in the site feature list.</span></span>  
  
 <span data-ttu-id="6b0e8-111">Чтобы проверить установку, просмотрите список установленных приложений на [!INCLUDE[msCoName](../includes/msconame-md.md)]**панели управления** Windows.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-111">To verify installation, view the list of installed applications in [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows **Control Panel**.</span></span> <span data-ttu-id="6b0e8-112">Если надстройка служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] установлена, следуйте инструкциям в этом разделе для активации функции синхронизации файлов сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-112">If the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Add-in is installed, follow the instructions in this topic to activate the report server file sync feature.</span></span>  
  
### <a name="to-activate-or-deactivate-the-reporting-services-file-sync-feature-on-a-site"></a><span data-ttu-id="6b0e8-113">Активация и деактивация функции синхронизации файлов служб Reporting Services на сайте</span><span class="sxs-lookup"><span data-stu-id="6b0e8-113">To activate or deactivate the Reporting Services File Sync feature on a Site</span></span>  
  
1.  <span data-ttu-id="6b0e8-114">На главной странице сайта щелкните меню **действия сайта** и выберите пункт **Параметры сайта**.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-114">From the main page of your site, click the **Site Actions** menu and click **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="6b0e8-115">В области **действия сайта**щелкните **Управление компонентами сайта**.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-115">In the **Site Actions**, click **Manage Site Features**.</span></span>  
  
3.  <span data-ttu-id="6b0e8-116">Найдите в списке **Синхронизация файлов сервера отчетов** .</span><span class="sxs-lookup"><span data-stu-id="6b0e8-116">Find **Report Server File Sync** in the list.</span></span>  
  
4.  <span data-ttu-id="6b0e8-117">Щелкните **Активировать**.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-117">Click **Activate**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b0e8-118">Деактивировать функцию синхронизации файлов сервера отчетов можно с помощью той же процедуры, но выбрав пункт **Деактивировать**.</span><span class="sxs-lookup"><span data-stu-id="6b0e8-118">To deactivate the Report Server file sync feature, you can use the same procedure but click **Deactivate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b0e8-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="6b0e8-119">See Also</span></span>  
 <span data-ttu-id="6b0e8-120">[Устранение неполадок элементов отчетов &#40;построитель отчетов и SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6b0e8-120">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6b0e8-121">[Активация функций интеграции сервера отчетов и Power View в SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="6b0e8-121">[Activate the Report Server and Power View Integration Features in SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md) </span></span>  
 <span data-ttu-id="6b0e8-122">[Установка или удаление надстройки Reporting Services для SharePoint &#40;SharePoint 2010 и SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="6b0e8-122">[Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="6b0e8-123">Установка или удаление надстройки Reporting Services для SharePoint &#40;SharePoint 2010 и SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="6b0e8-123">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
