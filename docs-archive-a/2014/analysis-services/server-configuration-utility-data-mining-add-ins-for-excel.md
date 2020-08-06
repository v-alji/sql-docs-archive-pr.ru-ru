---
title: Служебная программа настройки сервера (надстройки интеллектуального анализа данных для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 28435f86-5cec-4a1e-9b7d-b2069c1ddddb
author: minewiskan
ms.author: owend
ms.openlocfilehash: f985338e44bf0f4b591fcb70a4e093901626149f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752408"
---
# <a name="server-configuration-utility-data-mining-add-ins-for-excel"></a><span data-ttu-id="359da-102">Средство настройки сервера (надстройки интеллектуального анализа данных для Excel)</span><span class="sxs-lookup"><span data-stu-id="359da-102">Server Configuration Utility (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="359da-103">При установке надстроек интеллектуального анализа данных для Excel также устанавливается служебная программа настройки сервера, которая будет запускаться при первом открытии надстроек. В этом разделе описывается, как использовать программу для подключения к экземпляру [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и настройки базы данных для работы с моделями интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="359da-103">When you install the Data Mining Add-ins for Excel, a Server Configuration Utility is also installed, and will run the first time you open the add-ins. This topic describes how to use the utility to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and set up a database for working with data mining models.</span></span>  
  

  
##  <a name="step-1-connect-to-analysis-services"></a><a name="bkmk_step1"></a><span data-ttu-id="359da-104">Шаг 1. подключение к Analysis Services</span><span class="sxs-lookup"><span data-stu-id="359da-104">Step 1: Connect to Analysis Services</span></span>  
 <span data-ttu-id="359da-105">Выберите сервер служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], который будет предоставлять алгоритмы и сохранять модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="359da-105">Choose the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that provides the data mining algorithms and stores your data mining models.</span></span>  
  
 <span data-ttu-id="359da-106">При создании соединения для интеллектуального анализа данных необходимо выбрать сервер, где можно поэкспериментировать с моделями интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="359da-106">When you create a connection to enable data mining, you should choose a server where you can experiment with data mining models.</span></span> <span data-ttu-id="359da-107">Рекомендуется создать новую базу данных на сервере и выделить ее для интеллектуального анализа данных либо попросить администратора подготовить сервер интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="359da-107">We recommend that you create a new database on the server and dedicate the new database to data mining, or ask your administrator to prepare a data mining server for you.</span></span> <span data-ttu-id="359da-108">Это позволит строить модели, не оказывая влияния на производительность других служб.</span><span class="sxs-lookup"><span data-stu-id="359da-108">That way you can build models without affecting the performance of other services.</span></span>  
  
 <span data-ttu-id="359da-109">Обратите внимание, что сервер служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], используемый для интеллектуального анализа данных, не должен обязательно находиться на одном сервере с исходными данными.</span><span class="sxs-lookup"><span data-stu-id="359da-109">Note that the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that you use for data mining does not need to be on the same server as your source data.</span></span>  
  
 <span data-ttu-id="359da-110">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="359da-110">**Server name**</span></span>  
 <span data-ttu-id="359da-111">Введите имя сервера с установленным экземпляром служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], который будет использоваться для интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="359da-111">Type the name of the server that contains the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you will use for data mining.</span></span>  
  
 <span data-ttu-id="359da-112">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="359da-112">**Authentication**</span></span>  
 <span data-ttu-id="359da-113">Укажите методы проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="359da-113">Specify the authentication methods.</span></span> <span data-ttu-id="359da-114">Если администратор еще не настроил доступ к серверу с помощью HTTPPump, то для соединения со службами [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] требуется проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="359da-114">Windows Authentication is required for connections to [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], unless your administrator has configured access to the server via the HTTPPump.</span></span>  
  
##  <a name="step-2-allow-temporary-models"></a><a name="bkmk_step2"></a><span data-ttu-id="359da-115">Шаг 2. Разрешение временных моделей</span><span class="sxs-lookup"><span data-stu-id="359da-115">Step 2: Allow Temporary Models</span></span>  
 <span data-ttu-id="359da-116">Перед использованием надстроек необходимо изменить свойство сервера служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] так, чтобы оно разрешало создание временных моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="359da-116">Before you can use the add-ins, an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server property must be changed to permit the creation of temporary mining models.</span></span>  
  
 <span data-ttu-id="359da-117">Временные модели интеллектуального анализа данных также называются *моделями сеансов*.</span><span class="sxs-lookup"><span data-stu-id="359da-117">Temporary mining models are also called *session models*.</span></span> <span data-ttu-id="359da-118">Это связано с тем, что эти модели сохраняются, только пока открыт текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="359da-118">This is because the models are stored only as long as your current session is open.</span></span> <span data-ttu-id="359da-119">Как только соединение с сервером закрывается, сеанс заканчивается и все модели, использовавшиеся во время сеанса, удаляются.</span><span class="sxs-lookup"><span data-stu-id="359da-119">When you close your connection to the server, the session is ended and any models used during the session are deleted.</span></span>  
  
 <span data-ttu-id="359da-120">Использование моделей интеллектуального анализа данных сеанса не влияет на объем памяти на сервере, но нагрузка, вызванная созданием моделей, может повлиять на производительность сервера.</span><span class="sxs-lookup"><span data-stu-id="359da-120">The use of session mining models does not affect storage space on the server, but the overhead involved in creating data mining models may affect the performance of the server.</span></span>  
  
 <span data-ttu-id="359da-121">Вначале мастер определяет заданные на сервере параметры.</span><span class="sxs-lookup"><span data-stu-id="359da-121">The wizard first detects the settings on the server that you specified.</span></span> <span data-ttu-id="359da-122">Если сервер уже допускает временные модели интеллектуального анализа данных, можно нажать кнопку **Далее** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="359da-122">If the server already allows temporary mining models, you can click **Next** to continue.</span></span> <span data-ttu-id="359da-123">Мастер также показывает инструкции для включения временных моделей интеллектуального анализа данных на указанном сервере служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или для выполнения запроса системному администратору служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="359da-123">The wizard also provides instructions for how to enable temporary mining models on the specified [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server, or how to make a request to your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] administrator.</span></span>  
  
##  <a name="step-3-create-database-for-add-in-users"></a><a name="bkmk_step3"></a><span data-ttu-id="359da-124">Шаг 3. Создание базы данных для пользователей надстроек</span><span class="sxs-lookup"><span data-stu-id="359da-124">Step 3: Create Database for Add-in Users</span></span>  
 <span data-ttu-id="359da-125">На этой странице мастера установки и настройки можно создать новую базу данных, которая будет предназначена для интеллектуального анализа данных, или выбрать существующую базу данных [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="359da-125">On this page of the setup and configuration wizard, you can create a new database that is dedicated to data mining, or select an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="359da-126">Для интеллектуального анализа данных требуется экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], работающий в многомерном режиме.</span><span class="sxs-lookup"><span data-stu-id="359da-126">Data mining requires an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that is running in multidimensional mode.</span></span> <span data-ttu-id="359da-127">Табличный режим не поддерживает интеллектуальный анализ данных.</span><span class="sxs-lookup"><span data-stu-id="359da-127">Tabular mode does not support data mining.</span></span>  
  
 <span data-ttu-id="359da-128">Рекомендуется создать отдельную базу данных, специально предназначенную для интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="359da-128">We recommend that you create a separate database dedicated to data mining.</span></span> <span data-ttu-id="359da-129">Это позволит экспериментировать с моделями интеллектуального анализа данных, не оказывая влияния на другие объекты решения.</span><span class="sxs-lookup"><span data-stu-id="359da-129">This lets you experiment with data mining models without affecting other solution objects.</span></span>  
  
 <span data-ttu-id="359da-130">Если выбрана существующая база данных на экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], убедитесь, что можно перезаписать существующие модели, если окажется, что при создании модели с помощью надстроек модель с таким именем уже существует.</span><span class="sxs-lookup"><span data-stu-id="359da-130">If you choose an existing database on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], note that it is possible to overwrite existing models if you use the add-ins to create a model and a model of that name already exists.</span></span>  
  
 <span data-ttu-id="359da-131">**Создание базы данных**</span><span class="sxs-lookup"><span data-stu-id="359da-131">**Create new database**</span></span>  
 <span data-ttu-id="359da-132">Выберите этот параметр для создания новой базы данных на заданном сервере.</span><span class="sxs-lookup"><span data-stu-id="359da-132">Select this option to create a new database on the selected server.</span></span> <span data-ttu-id="359da-133">В базе данных интеллектуального анализа данных будут храниться источники данных, структуры и модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="359da-133">A data mining database will store your data sources, mining structures, and mining models.</span></span>  
  
 <span data-ttu-id="359da-134">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="359da-134">**Database name**</span></span>  
 <span data-ttu-id="359da-135">Введите имя новой базы данных.</span><span class="sxs-lookup"><span data-stu-id="359da-135">Type the name of the new database.</span></span> <span data-ttu-id="359da-136">Если имя не используется, оно будет создано.</span><span class="sxs-lookup"><span data-stu-id="359da-136">If the name is not already in use, it will be created for you.</span></span>  
  
 <span data-ttu-id="359da-137">**Использовать существующую базу данных**</span><span class="sxs-lookup"><span data-stu-id="359da-137">**Use existing database**</span></span>  
 <span data-ttu-id="359da-138">Выберите этот параметр для использования существующей базы данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="359da-138">Select this option to use an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="359da-139">**База данных**</span><span class="sxs-lookup"><span data-stu-id="359da-139">**Database**</span></span>  
 <span data-ttu-id="359da-140">Если используется существующая база данных, следует выбрать ее имя из списка.</span><span class="sxs-lookup"><span data-stu-id="359da-140">If you chose the option to use an existing database, you must select the database name from the list.</span></span>  
  
##  <a name="step-4-give-add-in-users-appropriate-permissions"></a><a name="bkmk_step4"></a><span data-ttu-id="359da-141">Шаг 4. предоставление пользователям соответствующих разрешений на доступ к надстройкам</span><span class="sxs-lookup"><span data-stu-id="359da-141">Step 4: Give Add-in Users Appropriate Permissions</span></span>  
 <span data-ttu-id="359da-142">Следует убедиться, что все пользователи, включая пользователей надстроек, имеют необходимые разрешения на просмотр, изменение, обработку или создание структур и моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="359da-142">You must ensure that you (and any other users of the add-ins) have the necessary permissions to browse, edit, process, or create data mining structures and models.</span></span>  
  
 <span data-ttu-id="359da-143">По умолчанию для использования надстроек требуется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="359da-143">By default, integrated Windows Authentication is required to use the add-ins.</span></span>  
  
 <span data-ttu-id="359da-144">**Предоставить пользователям надстроек административные разрешения**</span><span class="sxs-lookup"><span data-stu-id="359da-144">**Give add-in users database administration permissions**</span></span>  
 <span data-ttu-id="359da-145">Выберите этот параметр для предоставления заданным пользователям административного доступа к базе данных.</span><span class="sxs-lookup"><span data-stu-id="359da-145">Select this option to give the listed users administrative access to the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="359da-146">Эти разрешения применяются только к базе данных, указанной в поле **имя базы данных** .</span><span class="sxs-lookup"><span data-stu-id="359da-146">These permissions apply only to the database listed in the **Database name** box.</span></span>  
  
 <span data-ttu-id="359da-147">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="359da-147">**Database name**</span></span>  
 <span data-ttu-id="359da-148">Отображает имя выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="359da-148">Displays the name of the selected database.</span></span>  
  
 <span data-ttu-id="359da-149">**Пользователи или группы для добавления**</span><span class="sxs-lookup"><span data-stu-id="359da-149">**Specify users or groups to add**</span></span>  
 <span data-ttu-id="359da-150">Выберите имена входа, которые будут иметь доступ к базе данных, используемой для интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="359da-150">Select the logins that will have access to the database used for data mining.</span></span>  
  
 <span data-ttu-id="359da-151">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="359da-151">**Add**</span></span>  
 <span data-ttu-id="359da-152">Нажмите, чтобы открыть диалоговое окно и добавить пользователей или группы.</span><span class="sxs-lookup"><span data-stu-id="359da-152">Click to open a dialog box and add users or groups.</span></span>  
  
 <span data-ttu-id="359da-153">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="359da-153">**Remove**</span></span>  
 <span data-ttu-id="359da-154">Нажмите, чтобы удалить выбранного пользователя или выбранную группу из списка пользователей с административными разрешениями.</span><span class="sxs-lookup"><span data-stu-id="359da-154">Click to remove the selected user or group from the list of users with administration permissions.</span></span>  
  
  
