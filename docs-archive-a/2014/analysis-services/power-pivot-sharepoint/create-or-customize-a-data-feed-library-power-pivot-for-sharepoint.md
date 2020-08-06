---
title: Создание или Настройка библиотеки веб-каналов данных (PowerPivot для SharePoint) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data feed library
- data feeds [Analysis Services with SharePoint]
ms.assetid: 699fbeb9-42ab-436b-beba-214db51ea3dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: b86f63c1af094ea9e8a2a1149debeac387bccbf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730929"
---
# <a name="create-or-customize-a-data-feed-library-powerpivot-for-sharepoint"></a><span data-ttu-id="2148f-102">Создание или настройка библиотеки веб-каналов данных (PowerPivot для SharePoint)</span><span class="sxs-lookup"><span data-stu-id="2148f-102">Create or Customize a Data Feed Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="2148f-103">*Библиотека каналов данных* — это специализированная библиотека SharePoint, которая позволяет регистрировать сервисные документы данных Atom (ATOMSVC) и предоставлять к ним общий доступ.</span><span class="sxs-lookup"><span data-stu-id="2148f-103">A *data feed library* is a special-purpose SharePoint library that enables you to register and share Atom data service documents (.atomsvc).</span></span> <span data-ttu-id="2148f-104">Эти документы предоставляют потоки XML-данных для книг [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] или других клиентских приложений, поддерживающих формат веб-каналов данных Atom.</span><span class="sxs-lookup"><span data-stu-id="2148f-104">These documents provide XML data feeds to [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks or other client applications that support the Atom data feed format.</span></span> <span data-ttu-id="2148f-105">Библиотека веб-каналов данных отличается от других библиотек SharePoint, поскольку она позволяет выполнять следующее:</span><span class="sxs-lookup"><span data-stu-id="2148f-105">A data feed library is different from other SharePoint libraries because it gives you the ability to:</span></span>

-   <span data-ttu-id="2148f-106">Создавать и изменять *сервисные документы данных*, используемые для указания HTTP-соединения с определенным каналом.</span><span class="sxs-lookup"><span data-stu-id="2148f-106">Create or edit a *data service document*, used to specify an HTTP connection to a specific feed.</span></span>

-   <span data-ttu-id="2148f-107">Предоставлять общий доступ и управлять сервисными документами данных в централизованном местоположении.</span><span class="sxs-lookup"><span data-stu-id="2148f-107">Share and manage data service documents in a central location.</span></span>

-   <span data-ttu-id="2148f-108">Визуально определить сервисные документы данных по значку, чтобы можно было легко отличать сервисные документы от других документов, хранящихся в той же библиотеке: ![GMNI_IconDataFeed](../media/gmni-icondatafeed.gif "GMNI_IconDataFeed")</span><span class="sxs-lookup"><span data-stu-id="2148f-108">Visually identify data service documents by an icon, so that you can easily distinguish service documents from other documents stored in the same library: ![GMNI_IconDataFeed](../media/gmni-icondatafeed.gif "GMNI_IconDataFeed")</span></span>

 <span data-ttu-id="2148f-109">В библиотеке каналов данных всегда содержатся сервисные документы данных (ATOMSVC), но никогда не содержатся сами каналы данных.</span><span class="sxs-lookup"><span data-stu-id="2148f-109">A data feed library always contains data service document (.atomsvc) files, and never the data feed itself.</span></span> <span data-ttu-id="2148f-110">В отличие от канала данных, состоящего из статических XML-данных, в сервисных документах данных указывается URL-адрес к службам или приложениям, используемым для создания канала по требованию, благодаря чему предоставляются сведения соединения, которые могут использоваться повторно при повторяющихся операциях импорта.</span><span class="sxs-lookup"><span data-stu-id="2148f-110">Unlike a data feed, which consists of static XML data, the data service document specifies a URL to a service or application that generates a feed upon request, providing reusable connection information for repeatable import operations.</span></span>

 <span data-ttu-id="2148f-111">Этот раздел состоит из следующих подразделов.</span><span class="sxs-lookup"><span data-stu-id="2148f-111">This topic contains the following sections:</span></span>

 [<span data-ttu-id="2148f-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2148f-112">Prerequisites</span></span>](#prereq)

 [<span data-ttu-id="2148f-113">Создание новой библиотеки потоков данных</span><span class="sxs-lookup"><span data-stu-id="2148f-113">Create a New Data Feed Library</span></span>](#createlib)

 [<span data-ttu-id="2148f-114">Добавление типа содержимого потока данных в любую библиотеку</span><span class="sxs-lookup"><span data-stu-id="2148f-114">Add the Data Feed Content Type to Any Library</span></span>](#addtolib)

##  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="2148f-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2148f-115">Prerequisites</span></span>
 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] <span data-ttu-id="2148f-116">.</span><span class="sxs-lookup"><span data-stu-id="2148f-116">feature integration must be activated for the sites for which you are creating the data feed library.</span></span> <span data-ttu-id="2148f-117">Если шаблон библиотеки потоков данных недоступен, то это предварительное условие, вероятнее всего, не было выполнено.</span><span class="sxs-lookup"><span data-stu-id="2148f-117">If the data feed library template type is not available, the most likely cause is that this prerequisite has not been met.</span></span> <span data-ttu-id="2148f-118">Дополнительные сведения см. [в разделе Активация интеграции функций PowerPivot для семейств веб-сайтов в центре администрирования](activate-power-pivot-integration-for-site-collections-in-ca.md).</span><span class="sxs-lookup"><span data-stu-id="2148f-118">For more information, see [Activate PowerPivot Feature Integration for Site Collections in Central Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span></span>

 <span data-ttu-id="2148f-119">Создавать библиотеку на сайте может только его владелец.</span><span class="sxs-lookup"><span data-stu-id="2148f-119">You must be a site owner to create the library.</span></span>

##  <a name="create-a-new-data-feed-library"></a><a name="createlib"></a><span data-ttu-id="2148f-120">Создание новой библиотеки веб-каналов данных</span><span class="sxs-lookup"><span data-stu-id="2148f-120">Create a New Data Feed Library</span></span>
 <span data-ttu-id="2148f-121">Создание библиотеки потоков данных является первым этапом включения каналов данных для книг [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2148f-121">Creating a data feed library is the first step to enabling data feeds for [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks.</span></span> <span data-ttu-id="2148f-122">Поскольку библиотека потоков данных обеспечивает страницы приложения и управления для сервисных документов данных, эту библиотеку необходимо установить до создания новых документов.</span><span class="sxs-lookup"><span data-stu-id="2148f-122">Because a data feed library provides application and management pages for data service documents, you must have this library in place before you can create a new document.</span></span>

 <span data-ttu-id="2148f-123">Библиотека каналов данных создается на основе встроенного шаблона стандартного *типа содержимого сервисного документа данных* , определяющего свойства и режимы работы сервисного документа данных.</span><span class="sxs-lookup"><span data-stu-id="2148f-123">A data feed library is based on a built-in template and a preconfigured *data service document content type* that defines properties and behaviors for a data service document.</span></span>

1.  <span data-ttu-id="2148f-124">В левом верхнем углу страницы нажмите кнопку **Действия сайта** .</span><span class="sxs-lookup"><span data-stu-id="2148f-124">Click **Site Actions** at the top left corner of the page.</span></span>

2.  <span data-ttu-id="2148f-125">Щелкните **Дополнительные параметры**...</span><span class="sxs-lookup"><span data-stu-id="2148f-125">Click **More Options**...</span></span>

3.  <span data-ttu-id="2148f-126">В списке «Библиотеки» щелкните элемент **Библиотека потоков данных**.</span><span class="sxs-lookup"><span data-stu-id="2148f-126">Under Libraries, click **Data Feed Library**.</span></span>

4.  <span data-ttu-id="2148f-127">Введите имя, описание, номер версии и параметры запуска.</span><span class="sxs-lookup"><span data-stu-id="2148f-127">Type the name, description, launch, and version preferences.</span></span> <span data-ttu-id="2148f-128">Укажите описательные сведения, которые помогут пользователям определить эту библиотеку в качестве хранилища сервисных документов данных.</span><span class="sxs-lookup"><span data-stu-id="2148f-128">Include descriptive information to help users identify this library as storage for data service documents.</span></span>

5.  <span data-ttu-id="2148f-129">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="2148f-129">Click **Create**.</span></span>

 <span data-ttu-id="2148f-130">Ссылка на библиотеку потоков данных отобразится на панели навигации быстрого запуска для данного сайта.</span><span class="sxs-lookup"><span data-stu-id="2148f-130">A link to the data feed library will appear in the navigation Quick Launch pane for the current site.</span></span>

 <span data-ttu-id="2148f-131">После создания библиотеки с ее помощью можно создавать сервисные документы данных.</span><span class="sxs-lookup"><span data-stu-id="2148f-131">After you create a library, you can use it to create data service documents.</span></span> <span data-ttu-id="2148f-132">Дополнительные сведения см. в статье [Использование веб-каналов данных &#40;PowerPivot для SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="2148f-132">For more information, see [Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span></span>

##  <a name="add-the-data-feed-content-type-to-any-library"></a><a name="addtolib"></a><span data-ttu-id="2148f-133">Добавление типа содержимого потока данных в любую библиотеку</span><span class="sxs-lookup"><span data-stu-id="2148f-133">Add the Data Feed Content Type to Any Library</span></span>
 <span data-ttu-id="2148f-134">Если не требуется создавать специальную библиотеку каналов данных, но желательно создать сервисный документ данных и управлять ими с сайта SharePoint, можно вручную добавить и настроить тип содержимого документа службы данных для любой библиотеки, которая будет использоваться для общего доступа к файлам документов служб данных (ATOMSVC).</span><span class="sxs-lookup"><span data-stu-id="2148f-134">If you do not want to create a dedicated data feed library, but you still want to create and manage data service documents from a SharePoint site, you can manually add and configure the data service document content type for any library that you will use to share data service document (.atomsvc) files.</span></span>

 <span data-ttu-id="2148f-135">Чтобы добавлять и настраивать тип содержимого, необходимо разрешение не ниже «Управление списками».</span><span class="sxs-lookup"><span data-stu-id="2148f-135">You must have at least the Manage Lists permission to add and configure a content type.</span></span> <span data-ttu-id="2148f-136">Это разрешение встроено в разрешения уровня «Создание» и выше.</span><span class="sxs-lookup"><span data-stu-id="2148f-136">This permission is built into the Design permission level and above.</span></span>

 <span data-ttu-id="2148f-137">Для всех библиотек, в которых необходимо создать или изменить документы регистрации каналов данных, необходимо повторить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2148f-137">The following steps must be repeated for each library in which you want to create or edit data feed registration documents.</span></span>

#### <a name="step-1-enable-content-type-management"></a><span data-ttu-id="2148f-138">Шаг 1. Включение управления типами содержимого</span><span class="sxs-lookup"><span data-stu-id="2148f-138">Step 1: Enable Content Type Management</span></span>

1.  <span data-ttu-id="2148f-139">Откройте библиотеку документов, для которой нужно включить несколько типов содержимого.</span><span class="sxs-lookup"><span data-stu-id="2148f-139">Open the document library for which you want to enable multiple content types.</span></span>

2.  <span data-ttu-id="2148f-140">На ленте SharePoint в разделе «Средства библиотеки» выберите пункт **Библиотека**.</span><span class="sxs-lookup"><span data-stu-id="2148f-140">On the SharePoint ribbon, in Library Tools, click **Library**.</span></span>

3.  <span data-ttu-id="2148f-141">Щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="2148f-141">Click **Settings**.</span></span>

4.  <span data-ttu-id="2148f-142">Нажмите кнопку **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="2148f-142">Click **Library Settings**.</span></span>

5.  <span data-ttu-id="2148f-143">В разделе «Общие параметры» нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="2148f-143">In General Settings, click **Advanced settings**.</span></span>

6.  <span data-ttu-id="2148f-144">В группе "Разрешить управление типами содержимого?" раздела "Типы содержимого"</span><span class="sxs-lookup"><span data-stu-id="2148f-144">In Content Types, in the "Allow management of content types?"</span></span> <span data-ttu-id="2148f-145">выберите вариант **Да**.</span><span class="sxs-lookup"><span data-stu-id="2148f-145">section, click **Yes**.</span></span>

7.  <span data-ttu-id="2148f-146">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2148f-146">Click **OK**.</span></span>

#### <a name="step-2-add-the-data-service-document-content-type"></a><span data-ttu-id="2148f-147">Шаг 2. Добавление типа содержимого сервисного документа данных</span><span class="sxs-lookup"><span data-stu-id="2148f-147">Step 2: Add the Data Service Document Content Type</span></span>

1.  <span data-ttu-id="2148f-148">В разделе «Типы содержимого» выберите пункт **Добавить из существующих типов содержимого сайта**.</span><span class="sxs-lookup"><span data-stu-id="2148f-148">In the Content Types section, click **Add from existing site content types**.</span></span> <span data-ttu-id="2148f-149">Если эта страница не отображается, вернитесь на сайт, выберите в средствах библиотеки **Библиотека** , а затем выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="2148f-149">If you do not see this page, go back to the site, click **Library** in Library Tools, and then click **Library Settings**.</span></span>

2.  <span data-ttu-id="2148f-150">В разделе «Типы содержимого» выберите пункт **Добавить из существующих типов содержимого сайта**.</span><span class="sxs-lookup"><span data-stu-id="2148f-150">In Content Types, click **Add from existing site content types**.</span></span>

3.  <span data-ttu-id="2148f-151">В разделе «Выберите типы содержимого сайта из списка» выберите элемент **Бизнес-аналитика**.</span><span class="sxs-lookup"><span data-stu-id="2148f-151">In Select site content types from:, select **Business Intelligence**.</span></span>

4.  <span data-ttu-id="2148f-152">В разделе «Доступные типы содержимого сайта» выберите элемент **Сервисный документ данных**, затем нажмите кнопку **Добавить** , чтобы переместить выбранный тип содержимого в список «Типы содержимого для добавления».</span><span class="sxs-lookup"><span data-stu-id="2148f-152">In Available Site Content Types, click **Data Service Document**, and then click **Add** to move the selected content type to the Content types to add list.</span></span>

5.  <span data-ttu-id="2148f-153">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2148f-153">Click **OK**.</span></span>

#### <a name="step-3-verify-data-service-document-configuration"></a><span data-ttu-id="2148f-154">Шаг 3. Проверка конфигурации сервисного документа данных</span><span class="sxs-lookup"><span data-stu-id="2148f-154">Step 3: Verify Data Service Document Configuration</span></span>

1.  <span data-ttu-id="2148f-155">Откройте домашнюю страницу сайта.</span><span class="sxs-lookup"><span data-stu-id="2148f-155">Open the site home page.</span></span>

2.  <span data-ttu-id="2148f-156">Откройте библиотеку.</span><span class="sxs-lookup"><span data-stu-id="2148f-156">Open the library.</span></span>

3.  <span data-ttu-id="2148f-157">На ленте SharePoint нажмите кнопку **Документы**.</span><span class="sxs-lookup"><span data-stu-id="2148f-157">On the SharePoint ribbon, click **Documents**.</span></span>

4.  <span data-ttu-id="2148f-158">Щелкните стрелку вниз рядом с командой «Создать документ» и выберите пункт **Сервисный документ данных**.</span><span class="sxs-lookup"><span data-stu-id="2148f-158">Click the down arrow on New Document, and select **Data Service Document**.</span></span> <span data-ttu-id="2148f-159">Откроется страница «Новый сервисный документ данных».</span><span class="sxs-lookup"><span data-stu-id="2148f-159">The New Data Service Document page should appear.</span></span>

## <a name="see-also"></a><span data-ttu-id="2148f-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="2148f-160">See Also</span></span>
 <span data-ttu-id="2148f-161">[Использование веб-каналов данных &#40;PowerPivot для SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md) [удаления библиотеки каналов данных PowerPivot](delete-a-power-pivot-data-feed-library.md) [Администрирование и настройка сервера PowerPivot в](power-pivot-server-administration-and-configuration-in-central-administration.md) [каналах данных PowerPivot](power-pivot-data-feeds.md) в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="2148f-161">[Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md) [Delete a PowerPivot Data Feed Library](delete-a-power-pivot-data-feed-library.md) [PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) [PowerPivot Data Feeds](power-pivot-data-feeds.md)</span></span>


