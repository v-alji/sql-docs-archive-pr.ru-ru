---
title: Активация функций интеграции сервера отчетов и Power View в SharePoint | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7f64a54-c555-4d31-bf99-3abe57dc8626
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af5f544e959c039b0bdb85d63d0b94917254d78a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667602"
---
# <a name="activate-the-report-server-and-power-view-integration-features-in-sharepoint"></a><span data-ttu-id="df232-102">Активация функций интеграции семейства веб-сайтов с сервером отчетов и Power View в SharePoint</span><span class="sxs-lookup"><span data-stu-id="df232-102">Activate the Report Server and Power View Integration Features in SharePoint</span></span>
  <span data-ttu-id="df232-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Компоненты семейства веб-сайтов обычно активируются по умолчанию после установки [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] надстройки для продуктов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="df232-103">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] site collection features are usually activated by default after you install the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] Add-in for SharePoint products.</span></span> <span data-ttu-id="df232-104">В некоторых ситуациях эти функции требуется активировать вручную.</span><span class="sxs-lookup"><span data-stu-id="df232-104">In some situations you will need to manually activate the features.</span></span>  
  
 <span data-ttu-id="df232-105">При установке надстройки служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] для продуктов SharePoint 2010 после установки продукта SharePoint функции интеграции с сервером отчетов и с Power View будут активированы только для корневых семейств веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="df232-105">If you install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint 2010 Products after the installation of the SharePoint product, then the Report Server integration feature and the Power View integration feature will only be activated for root site collections.</span></span> <span data-ttu-id="df232-106">Для других семейств веб-сайтов потребуется активировать эти функции вручную.</span><span class="sxs-lookup"><span data-stu-id="df232-106">For other site collections, you will need to manually activate the features.</span></span> <span data-ttu-id="df232-107">Например, если имеется семейство веб-сайтов **http://[имя_сервера]/sites/[имя_семейства_веб-сайтов]** , то потребуется вручную активировать функции семейства веб-сайтов служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df232-107">For example if you have a site collection of **http://[my server name]/sites/[site collection name]** you will need to manually activate the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] site collection features.</span></span>  
  
 <span data-ttu-id="df232-108">Когда корневого семейства веб-сайтов нет, надстройка [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] занесет в журнал сообщение, подобное приведенному далее.</span><span class="sxs-lookup"><span data-stu-id="df232-108">When there is no root site collection, the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in will log a message similar to the following.</span></span>  
  
 <span data-ttu-id="df232-109">«Веб-приложение SharePoint 80 не содержит корневого семейства веб-сайтов»</span><span class="sxs-lookup"><span data-stu-id="df232-109">"SharePoint web app 80 does not have root site collection"</span></span>  
  
 <span data-ttu-id="df232-110">Сообщение будет найдено в журнале установки надстройки с именем "RS_SP_ #. log", где # — это увеличивающийся номер.</span><span class="sxs-lookup"><span data-stu-id="df232-110">The message will be found in the add-in installation log, named "RS_SP_#.log" where # is an incrementing number.</span></span> <span data-ttu-id="df232-111">Файл журнала будет находиться в папке Temp текущего пользователя, например C:\Users \\ [имя пользователя] \AppData\Local\Temp. Дополнительные сведения о параметрах ведения журнала в надстройке см. в разделе [Установка или удаление надстройки Reporting Services для sharepoint &#40;sharepoint 2010 и sharepoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="df232-111">The log file will be found in the current users Temp folder, for example C:\Users\\[user name]\AppData\Local\Temp. For more information on logging options with the add-in, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span>  
  
 <span data-ttu-id="df232-112">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="df232-112">In this topic:</span></span>  
  
-   [<span data-ttu-id="df232-113">Активация функций семейства веб-сайтов для интеграции с сервером отчетов и Power View</span><span class="sxs-lookup"><span data-stu-id="df232-113">To Activate the Report Server and Power View Integration Site Collection Features:</span></span>](#bkmk_features)  
  
-   [<span data-ttu-id="df232-114">Активация и деактивация функций семейства веб-сайтов для центра администрирования служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="df232-114">To Activate or Deactivate Reporting Services Central Administration Site Collection Feature:</span></span>](#bkmk_centraladmin)  
  
##  <a name="to-activate-the-report-server-and-power-view-integration-site-collection-features"></a><a name="bkmk_features"></a><span data-ttu-id="df232-115">Чтобы активировать компоненты семейства веб-сайтов интеграции с сервером отчетов и Power View:</span><span class="sxs-lookup"><span data-stu-id="df232-115">To Activate the Report Server and Power View Integration Site Collection Features:</span></span>  
  
1.  <span data-ttu-id="df232-116">Откройте в браузере веб-сайт, где нужно активировать функции служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df232-116">Open your browser to the site where you want the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features active.</span></span>  
  
2.  <span data-ttu-id="df232-117">Щелкните **Действия сайта**.</span><span class="sxs-lookup"><span data-stu-id="df232-117">Click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="df232-118">Щелкните элемент **Настройки сайта**.</span><span class="sxs-lookup"><span data-stu-id="df232-118">Click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="df232-119">Щелкните **Функции семейства веб-сайтов** в группе администраторов семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="df232-119">Click **Site Collection Features** in the Site Collection Administration Group.</span></span>  
  
5.  <span data-ttu-id="df232-120">Найдите в списке **Функцию интеграции сервера отчетов** или **Функцию интеграции средства Power View** .</span><span class="sxs-lookup"><span data-stu-id="df232-120">Find **Report Server Integration Feature** or **Power View Integration Feature** in the list.</span></span>  
  
6.  <span data-ttu-id="df232-121">Щелкните **Активировать**.</span><span class="sxs-lookup"><span data-stu-id="df232-121">Click **Activate**.</span></span>  
  
 <span data-ttu-id="df232-122">Деактивация компонентов выполняется схожим образом, только вместо кнопки **Активировать** нужно нажать кнопку **Деактивировать**.</span><span class="sxs-lookup"><span data-stu-id="df232-122">To deactivate the features, you can use the same procedure, but click **Deactivate** rather than **Activate.**</span></span>  
  
##  <a name="to-activate-or-deactivate-reporting-services-central-administration-site-collection-feature"></a><a name="bkmk_centraladmin"></a><span data-ttu-id="df232-123">Для активации или деактивации Reporting Services компонента семейства веб-сайтов центра администрирования:</span><span class="sxs-lookup"><span data-stu-id="df232-123">To Activate or Deactivate Reporting Services Central Administration Site Collection Feature:</span></span>  
  
1.  <span data-ttu-id="df232-124">Откройте в браузере центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="df232-124">Open your browser to SharePoint Central Administration.</span></span>  
  
2.  <span data-ttu-id="df232-125">Щелкните **Действия сайта**.</span><span class="sxs-lookup"><span data-stu-id="df232-125">Click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="df232-126">Щелкните элемент **Настройки сайта**.</span><span class="sxs-lookup"><span data-stu-id="df232-126">Click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="df232-127">Щелкните **Функции семейства веб-сайтов** в группе администраторов семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="df232-127">Click **Site Collection Features** in the Site Collection Administration Group.</span></span>  
  
5.  <span data-ttu-id="df232-128">Найдите в списке пункт **Функция центра администрирования сервера отчетов** .</span><span class="sxs-lookup"><span data-stu-id="df232-128">Find **Report Server Central Administration Feature** in the list.</span></span>  
  
6.  <span data-ttu-id="df232-129">Щелкните **Активировать**.</span><span class="sxs-lookup"><span data-stu-id="df232-129">Click **Activate**.</span></span>  
  
 <span data-ttu-id="df232-130">Деактивация компонента выполняется схожим образом, только вместо кнопки **Активировать** нужно нажать кнопку **Деактивировать**.</span><span class="sxs-lookup"><span data-stu-id="df232-130">To deactivate the feature, you can use the same procedure, but click **Deactivate** rather than **Activate.**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="df232-131">Next Steps</span><span class="sxs-lookup"><span data-stu-id="df232-131">Next Steps</span></span>  
 <span data-ttu-id="df232-132">После активации компонента можно продолжить интеграцию сервера.</span><span class="sxs-lookup"><span data-stu-id="df232-132">After the feature is activated, you can continue with server integration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df232-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="df232-133">See Also</span></span>  
 [<span data-ttu-id="df232-134">Установка или удаление надстройки Reporting Services для SharePoint &#40;SharePoint 2010 и SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="df232-134">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
