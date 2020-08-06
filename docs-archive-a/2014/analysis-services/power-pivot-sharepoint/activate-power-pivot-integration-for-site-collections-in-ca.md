---
title: Активация интеграции функций PowerPivot для семейств веб-сайтов в центре администрирования | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 62a27e53-446a-42d7-b5db-c009e02d4904
author: minewiskan
ms.author: owend
ms.openlocfilehash: b565434cba197d04327e833d4ac6eab3caf96646
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730926"
---
# <a name="activate-powerpivot-feature-integration-for-site-collections-in-central-administration"></a><span data-ttu-id="fed6f-102">Активация интеграции функций PowerPivot для семейств веб-сайтов в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="fed6f-102">Activate PowerPivot Feature Integration for Site Collections in Central Administration</span></span>
  <span data-ttu-id="fed6f-103">При использовании параметра установки существующей фермы для установки SQL Server PowerPivot для SharePoint необходимо активировать интеграцию компонента PowerPivot для определенных семейств веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="fed6f-103">Activating PowerPivot feature integration for specific site collections is required if you used the Existing Farm installation option to install SQL Server PowerPivot for SharePoint.</span></span> <span data-ttu-id="fed6f-104">Если надстройка PowerPivot для SharePoint была установлена с параметром «Новый сервер», эту задачу можно пропустить, поскольку программа установки SQL Server уже активировала интеграцию компонента PowerPivot для корневого семейства веб-сайтов при настройке системы.</span><span class="sxs-lookup"><span data-stu-id="fed6f-104">If you installed PowerPivot for SharePoint using the New Server option, you can skip this task because SQL Server Setup already activated PowerPivot feature integration for the root site collection when it configured your deployment.</span></span>  
  
 <span data-ttu-id="fed6f-105">Активация компонента на уровне семейств веб-сайтов необходима, чтобы сделать страницы и шаблоны приложения доступными для веб-сайтов, в том числе страницы конфигурации для планового обновления данных страницы приложений для библиотеки PowerPivot Gallery и библиотек потоков данных.</span><span class="sxs-lookup"><span data-stu-id="fed6f-105">Feature activation at the site collection level is necessary to make application pages and templates available to your sites, including configuration pages for scheduled data refresh and application pages for PowerPivot Gallery and Data Feed libraries.</span></span>  
  
 <span data-ttu-id="fed6f-106">Необходимо активировать интеграцию PowerPivot для всех семейств веб-сайтов, поддерживающих обработку запросов PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fed6f-106">You must activate PowerPivot integration for each site collection that supports PowerPivot query processing.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fed6f-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="fed6f-107">Prerequisites</span></span>  
 <span data-ttu-id="fed6f-108">Пользователь должен быть администратором семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="fed6f-108">You must be a site collection administrator.</span></span>  
  
## <a name="activate-powerpivot-features"></a><span data-ttu-id="fed6f-109">Активация функций PowerPivot</span><span class="sxs-lookup"><span data-stu-id="fed6f-109">Activate PowerPivot Features</span></span>  
  
1.  <span data-ttu-id="fed6f-110">На сайте SharePoint нажмите кнопку **Действия сайта**.</span><span class="sxs-lookup"><span data-stu-id="fed6f-110">On a SharePoint site, click **Site Actions**.</span></span>  
  
     <span data-ttu-id="fed6f-111">По умолчанию доступ к веб-приложениям SharePoint осуществляется через порт 80.</span><span class="sxs-lookup"><span data-stu-id="fed6f-111">By default, SharePoint web applications are accessed through port 80.</span></span> <span data-ttu-id="fed6f-112">Это означает, что часто к сайту SharePoint можно получить доступ, введя http://\<computer name>, чтобы открыть корневое семейство веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="fed6f-112">This means that you can often access a SharePoint site by entering http://\<computer name> to open the root site collection.</span></span>  
  
2.  <span data-ttu-id="fed6f-113">Щелкните элемент **Настройки сайта**.</span><span class="sxs-lookup"><span data-stu-id="fed6f-113">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="fed6f-114">В области "Администрирование семейства веб-сайтов" щелкните ссылку **Возможности семейства узлов**.</span><span class="sxs-lookup"><span data-stu-id="fed6f-114">In Site Collection Administration, click **Site collection features**.</span></span>  
  
4.  <span data-ttu-id="fed6f-115">Прокрутите страницу вниз, пока не найдете **компонент коллекция веб-сайтов интеграции с PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="fed6f-115">Scroll down the page until you find **PowerPivot Integration Site Collection Feature**.</span></span>  
  
5.  <span data-ttu-id="fed6f-116">Щелкните **Активировать**.</span><span class="sxs-lookup"><span data-stu-id="fed6f-116">Click **Activate**.</span></span>  
  
6.  <span data-ttu-id="fed6f-117">Повторите эти действия для дополнительных семейств веб-сайтов, открыв каждый из сайтов и щелкнув **Действия сайта**.</span><span class="sxs-lookup"><span data-stu-id="fed6f-117">Repeat for additional site collections by opening each site and clicking **Site Actions**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed6f-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="fed6f-118">See Also</span></span>  
 <span data-ttu-id="fed6f-119">[Администрирование и настройка сервера PowerPivot в центре администрирования](power-pivot-server-administration-and-configuration-in-central-administration.md) </span><span class="sxs-lookup"><span data-stu-id="fed6f-119">[PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span></span>  
 <span data-ttu-id="fed6f-120">[PowerPivot для SharePoint &#40;начальной конфигурации&#41;](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="fed6f-120">[Initial Configuration &#40;PowerPivot for SharePoint&#41;](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="fed6f-121">Установка PowerPivot для SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="fed6f-121">PowerPivot for SharePoint 2010 Installation</span></span>](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
