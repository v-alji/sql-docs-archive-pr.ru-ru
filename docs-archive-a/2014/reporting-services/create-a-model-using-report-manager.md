---
title: Создание модели с помощью диспетчер отчетов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report models [Reporting Services], creating
- Report Manager [Reporting Services], model creation
ms.assetid: 8e5d2bd3-48ec-45f3-afee-6d86797c8f28
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 59ce278a22ec9797b001ca37a0bde576483cf5d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735105"
---
# <a name="create-a-model-using-report-manager"></a><span data-ttu-id="04dc5-102">Создание модели с помощью диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="04dc5-102">Create a Model Using Report Manager</span></span>
  <span data-ttu-id="04dc5-103">С помощью диспетчера отчетов можно создавать модели на основе куба служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , базы данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] или базы данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="04dc5-103">You can generate models from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube, a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, or an Oracle database using Report Manager.</span></span> <span data-ttu-id="04dc5-104">Модели отчета создаются на основе общих источников данных, опубликованных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="04dc5-104">Report models are generated from shared data sources that are published on the report server.</span></span> <span data-ttu-id="04dc5-105">Если еще не создано ни одного общего источника данных, то его необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="04dc5-105">If you do not already have a shared data source, you must create one.</span></span>  
  
 <span data-ttu-id="04dc5-106">Создаваемая модель отчета полностью основана на схеме общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="04dc5-106">The report model that you generate is based entirely on the schema of the shared data source.</span></span> <span data-ttu-id="04dc5-107">Пользователь не может выбирать, какие части источника данных включать в модель, и не может редактировать правила или метаданные создаваемой модели.</span><span class="sxs-lookup"><span data-stu-id="04dc5-107">You cannot choose which parts of the data source are included in the model, nor can you edit the rules or metadata of a generated model.</span></span> <span data-ttu-id="04dc5-108">Тем не менее после создания модели можно установить ее свойства и определить назначения ролей, которые ограничивают доступ к модели или ее частям.</span><span class="sxs-lookup"><span data-stu-id="04dc5-108">However, you can set properties on the model after it is generated and define role assignments that restrict access to all or part of the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04dc5-109">Модель на основе Oracle, созданная с помощью диспетчер отчетов или [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007 [!INCLUDE[SPS2010](../includes/sps2010-md.md)] , будет включать в себя объекты базы данных, которые являются частью схемы для учетной записи пользователя, используемой для подключения к источнику данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="04dc5-109">An Oracle-based model generated using Report Manager or [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007 [!INCLUDE[SPS2010](../includes/sps2010-md.md)] will include database objects that are a part of the schema for the user account used to connect to the Oracle data source.</span></span> <span data-ttu-id="04dc5-110">Имя учетной записи пользователя указывается в учетных данных свойств источника данных.</span><span class="sxs-lookup"><span data-stu-id="04dc5-110">The user account name is specified in the data source properties credentials.</span></span>  
  
### <a name="to-create-a-new-data-source-for-a-report-model-using-report-manager"></a><span data-ttu-id="04dc5-111">Создание нового источника данных для модели отчета с помощью диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="04dc5-111">To create a new data source for a report model using Report Manager</span></span>  
  
1.  <span data-ttu-id="04dc5-112">В веб-браузере введите в адресной строке URL-адрес для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="04dc5-112">In your Web browser, type the URL for your report server in the address bar.</span></span>  
  
2.  <span data-ttu-id="04dc5-113">Нажмите кнопку **Создать источник данных**.</span><span class="sxs-lookup"><span data-stu-id="04dc5-113">Click **New Data Source**.</span></span>  
  
3.  <span data-ttu-id="04dc5-114">В окне **Имя** введите имя источника данных.</span><span class="sxs-lookup"><span data-stu-id="04dc5-114">In the **Name** box, enter a name for the data source.</span></span>  
  
4.  <span data-ttu-id="04dc5-115">При необходимости введите краткое описание модели в текстовом поле **Описание** .</span><span class="sxs-lookup"><span data-stu-id="04dc5-115">Optionally, enter a brief description of the mode in the **Description** text box.</span></span>  
  
5.  <span data-ttu-id="04dc5-116">Убедитесь, что флажок **Включить этот источник данных** установлен.</span><span class="sxs-lookup"><span data-stu-id="04dc5-116">Verify that the **Enable this data source** check box is selected.</span></span>  
  
6.  <span data-ttu-id="04dc5-117">В списке **Тип соединения** выберите нужный тип источника данных.</span><span class="sxs-lookup"><span data-stu-id="04dc5-117">In the **Connection type** list, select the data source type to which you want to connect.</span></span> <span data-ttu-id="04dc5-118">Тип соединения должен быть одним из следующих: **Oracle**, **Microsoft SQL Server** или **Microsoft SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="04dc5-118">The connection type must be one of the following: **Oracle**, **Microsoft SQL Server** or **Microsoft SQL Server Analysis Services**.</span></span>  
  
7.  <span data-ttu-id="04dc5-119">В окне **Строка соединения** введите строку соединения, указывающую на базу данных.</span><span class="sxs-lookup"><span data-stu-id="04dc5-119">In the **Connection string** box, enter the connection string that points to the database.</span></span>  
  
8.  <span data-ttu-id="04dc5-120">Выберите метод подключения, с помощью которого пользователи построителя отчетов будут подключаться к базе данных.</span><span class="sxs-lookup"><span data-stu-id="04dc5-120">Select the connection method that Report Builder users will need to use to connect to the database.</span></span>  
  
    -   <span data-ttu-id="04dc5-121">Проверка подлинности Windows: выберите этот параметр, если проверку подлинности пользователей [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] должна проводить операционная система.</span><span class="sxs-lookup"><span data-stu-id="04dc5-121">Windows Authentication: Select this option when you want the operating system to authenticate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] users.</span></span> <span data-ttu-id="04dc5-122">Этот параметр позволяет [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] применять для проверки подлинности пользователей функции безопасности Windows, такие как шифрование паролей.</span><span class="sxs-lookup"><span data-stu-id="04dc5-122">This option allows [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to use Windows security features, such as password encryption, to authenticate users.</span></span> <span data-ttu-id="04dc5-123">Настоятельно рекомендуется выбрать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="04dc5-123">It is strongly recommended that you select this option.</span></span>  
  
    -   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="04dc5-124">Проверка подлинности. Выберите этот параметр, если вы хотите, чтобы пользователи использовали [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] созданную учетную запись входа.</span><span class="sxs-lookup"><span data-stu-id="04dc5-124">Authentication: Select this option when you want users to use a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login account that you created.</span></span> <span data-ttu-id="04dc5-125">Пользователи должны вводить допустимые имена входа пользователей и пароли [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04dc5-125">Users must supply a valid [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login name and password.</span></span>  
  
        > [!CAUTION]  
        >  <span data-ttu-id="04dc5-126">При возможности используйте проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="04dc5-126">Whenever possible, use Windows Authentication.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-create-a-report-model-using-report-manager"></a><span data-ttu-id="04dc5-127">Создание модели отчета с помощью диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="04dc5-127">To create a report model using Report Manager</span></span>  
  
1.  <span data-ttu-id="04dc5-128">Выберите в диспетчере отчетов источник данных, который необходимо использовать в модели.</span><span class="sxs-lookup"><span data-stu-id="04dc5-128">In Report Manager, select the data source that you want to use for your model.</span></span>  
  
     <span data-ttu-id="04dc5-129">Отобразится страница свойств.</span><span class="sxs-lookup"><span data-stu-id="04dc5-129">The Properties page is displayed.</span></span>  
  
2.  <span data-ttu-id="04dc5-130">Проверьте параметры, заданные для источника данных.</span><span class="sxs-lookup"><span data-stu-id="04dc5-130">Verify that you want to use the options specified for the data source.</span></span>  
  
3.  <span data-ttu-id="04dc5-131">Щелкните **Создать модель**.</span><span class="sxs-lookup"><span data-stu-id="04dc5-131">Click **Generate Model**.</span></span>  
  
     <span data-ttu-id="04dc5-132">Отобразится страница «Общие» источника данных.</span><span class="sxs-lookup"><span data-stu-id="04dc5-132">The General page is displayed for the data source.</span></span>  
  
4.  <span data-ttu-id="04dc5-133">В окне **Имя** введите имя модели отчета.</span><span class="sxs-lookup"><span data-stu-id="04dc5-133">In the **Name** box, enter a name for the report model.</span></span>  
  
5.  <span data-ttu-id="04dc5-134">В поле **Описание** введите краткое описание модели.</span><span class="sxs-lookup"><span data-stu-id="04dc5-134">In the **Description** box, enter a brief description of the model.</span></span>  
  
6.  <span data-ttu-id="04dc5-135">Чтобы задать новое расположение, в котором будет сохранена модель, щелкните **Изменить расположение**.</span><span class="sxs-lookup"><span data-stu-id="04dc5-135">To specify a new location to save the report model to, click **Change Location**.</span></span>  
  
     <span data-ttu-id="04dc5-136">По умолчанию модель отчета сохраняется в корневой папке диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="04dc5-136">By default, the report model is saved to Report Manager Home.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="04dc5-137">Модель будет создана и сохранена в заданном расположении.</span><span class="sxs-lookup"><span data-stu-id="04dc5-137">The report model is created and saved to the location that you specified.</span></span> <span data-ttu-id="04dc5-138">Для назначения разрешений этой модели можно воспользоваться диспетчером отчетов.</span><span class="sxs-lookup"><span data-stu-id="04dc5-138">You can assign permissions to this model by using Report Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04dc5-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="04dc5-139">See Also</span></span>  
 <span data-ttu-id="04dc5-140">[Предоставление разрешений на сервер отчетов в собственном режиме](security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="04dc5-140">[Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 <span data-ttu-id="04dc5-141">[Подключения к данным, источники данных и строки подключения в Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="04dc5-141">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="04dc5-142">Страница "Создание источника данных" (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="04dc5-142">New Data Source Page &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/new-data-source-page-report-manager.md)  
  
  
