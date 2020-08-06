---
title: Создание или изменение регистрации сервера (вкладка "Общие") (Reporting Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.reportserver.f1
ms.assetid: 5f899a8e-52ef-46b5-b7a9-f200ccd9f724
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 195756498dcefe4686d4b06e758dba9919c0b304
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667880"
---
# <a name="new-or-edit-server-registration-general-tab-reporting-services"></a><span data-ttu-id="73c20-102">Создание или редактирование регистрации сервера (вкладка «Общие») (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="73c20-102">New or Edit Server Registration (General Tab) (Reporting Services)</span></span>
  <span data-ttu-id="73c20-103">В этой вкладке указываются параметры при регистрации экземпляра служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73c20-103">Use this tab to specify options when registering an instance of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="73c20-104">Чтобы открыть эту страницу, нажмите кнопку **Службы Reporting Services** на панели инструментов **Зарегистрированные серверы** , щелкните правой кнопкой мыши любую зарегистрированную группу серверов, например **Службы Reporting Services**, выберите раздел **Создать**и выберите пункт **Регистрация сервера**.</span><span class="sxs-lookup"><span data-stu-id="73c20-104">To access this page, in Registered Servers, click **Reporting Services** on the **Registered Servers** toolbar, right-click any registered servers group such as **Reporting Services**, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="73c20-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="73c20-105">Options</span></span>  
 <span data-ttu-id="73c20-106">**Тип сервера**</span><span class="sxs-lookup"><span data-stu-id="73c20-106">**Server type**</span></span>  
 <span data-ttu-id="73c20-107">При регистрации сервера из списка «Зарегистрированные серверы» поле **Тип сервера** доступно только для чтения и соответствует типу сервера, отображаемому на панели « **Зарегистрированные серверы** ».</span><span class="sxs-lookup"><span data-stu-id="73c20-107">When a server is registered from Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in the **Registered Servers** pane.</span></span> <span data-ttu-id="73c20-108">Чтобы зарегистрировать другой тип сервера, щелкните нужный сервер на панели инструментов **Зарегистрированные серверы** , прежде чем регистрировать новый сервер.</span><span class="sxs-lookup"><span data-stu-id="73c20-108">To register a different type of server, click the server you want on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="73c20-109">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="73c20-109">**Server name**</span></span>  
 <span data-ttu-id="73c20-110">Укажите экземпляр сервера отчетов, к которому необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="73c20-110">Specify the report server instance to connect to.</span></span> <span data-ttu-id="73c20-111">В среде [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]возможно получить доступ к серверу отчетов, используя имя его экземпляра.</span><span class="sxs-lookup"><span data-stu-id="73c20-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], you can access a report server through its instance name.</span></span> <span data-ttu-id="73c20-112">Может иметься по одному экземпляру сервера отчетов для каждого устанавливаемого экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73c20-112">You can have one report server instance for each SQL Server instance that you install.</span></span> <span data-ttu-id="73c20-113">Если используется экземпляр по умолчанию, введите имя экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73c20-113">If you are using the default instance, type the name of the SQL Server instance.</span></span> <span data-ttu-id="73c20-114">Если используется именованный экземпляр, укажите имя экземпляра в формате MSSQL$имя_экземпляра для подключения к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="73c20-114">If you are using a named instance, specify the named instance to connect to the report server in the format MSSQL$InstanceName.</span></span>  
  
 <span data-ttu-id="73c20-115">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="73c20-115">**Authentication**</span></span>  
 <span data-ttu-id="73c20-116">Проверка подлинности для сервера отчетов производится через службы IIS.</span><span class="sxs-lookup"><span data-stu-id="73c20-116">Authentication to a report server is made through Internet Information Services (IIS).</span></span> <span data-ttu-id="73c20-117">При подключении к службам Reporting Services выберите один из следующих режимов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="73c20-117">Select from one of the following authentication modes when connecting to Reporting Services:</span></span>  
  
 <span data-ttu-id="73c20-118">**Режим проверки подлинности Windows (проверка подлинности Windows)**</span><span class="sxs-lookup"><span data-stu-id="73c20-118">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="73c20-119">Подключитесь к экземпляру сервера отчетов, используя учетные данные [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="73c20-119">Connect to the report server instance using your [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows credentials.</span></span>  
  
 <span data-ttu-id="73c20-120">**Обычная проверка подлинности**</span><span class="sxs-lookup"><span data-stu-id="73c20-120">**Basic Authentication**</span></span>  
 <span data-ttu-id="73c20-121">Установите соединение, используя **Обычную проверку подлинности** , если экземпляр служб Reporting Services настроен на использование обычной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="73c20-121">Connect using **Basic Authentication** if your Reporting Services installation is configured to use Basic Authentication.</span></span>  
  
 <span data-ttu-id="73c20-122">**Проверка подлинности с помощью форм**</span><span class="sxs-lookup"><span data-stu-id="73c20-122">**Forms Authentication**</span></span>  
 <span data-ttu-id="73c20-123">Установите соединение, используя **Проверку подлинности с помощью форм** , если экземпляр служб Reporting Services настроен на использование пользовательского модуля проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="73c20-123">Connect using **Forms Authentication** if your Reporting Services installation is configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="73c20-124">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="73c20-124">**User Name**</span></span>  
 <span data-ttu-id="73c20-125">Введите имя входа, которое будет использоваться при соединении.</span><span class="sxs-lookup"><span data-stu-id="73c20-125">Enter the login name to use for the connection.</span></span> <span data-ttu-id="73c20-126">Этот параметр доступен только в том случае, если выбран режим **Обычная проверка подлинности** или **Проверка подлинности с помощью форм**.</span><span class="sxs-lookup"><span data-stu-id="73c20-126">This option is only available if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="73c20-127">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="73c20-127">**Password**</span></span>  
 <span data-ttu-id="73c20-128">Введите пароль для имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="73c20-128">Enter the password for the user name.</span></span> <span data-ttu-id="73c20-129">Этот параметр может редактироваться только в том случае, если выбран режим **Обычная проверка подлинности** или **Проверка подлинности с помощью форм**.</span><span class="sxs-lookup"><span data-stu-id="73c20-129">This option is only editable if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="73c20-130">**Запоминание пароля**</span><span class="sxs-lookup"><span data-stu-id="73c20-130">**Remember password**</span></span>  
 <span data-ttu-id="73c20-131">Сохранить введенный пароль.</span><span class="sxs-lookup"><span data-stu-id="73c20-131">Store the password you have entered.</span></span> <span data-ttu-id="73c20-132">Этот параметр доступен, только если выбран режим **Обычная проверка подлинности** или **Проверка подлинности с помощью форм**.</span><span class="sxs-lookup"><span data-stu-id="73c20-132">This option is only available if you have clicked **Basic** or **Forms Authentication**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73c20-133"> Чтобы пароль больше не запоминался, снимите этот флажок и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="73c20-133">If you have stored the password and want to stop storing it, clear this check box and then click **Save**.</span></span>  
  
 <span data-ttu-id="73c20-134">**Имя зарегистрированного сервера**</span><span class="sxs-lookup"><span data-stu-id="73c20-134">**Registered server name**</span></span>  
 <span data-ttu-id="73c20-135">Имя, которое будет отображаться на панели «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="73c20-135">The name you want to appear in Registered Servers.</span></span> <span data-ttu-id="73c20-136">Это имя необязательно должно совпадать с именем, указанным в поле **Имя сервера** .</span><span class="sxs-lookup"><span data-stu-id="73c20-136">This name does not have to match the name in the **Server name** box.</span></span>  
  
 <span data-ttu-id="73c20-137">**Описание зарегистрированного сервера**</span><span class="sxs-lookup"><span data-stu-id="73c20-137">**Registered server description**</span></span>  
 <span data-ttu-id="73c20-138">Введите необязательное описание сервера.</span><span class="sxs-lookup"><span data-stu-id="73c20-138">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="73c20-139">**Тест**</span><span class="sxs-lookup"><span data-stu-id="73c20-139">**Test**</span></span>  
 <span data-ttu-id="73c20-140">Нажмите для проверки соединения с сервером, заданным в поле **Имя сервера**.</span><span class="sxs-lookup"><span data-stu-id="73c20-140">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="73c20-141">**Сохранить**</span><span class="sxs-lookup"><span data-stu-id="73c20-141">**Save**</span></span>  
 <span data-ttu-id="73c20-142">Нажмите эту кнопку, чтобы сохранить настройки зарегистрированного сервера.</span><span class="sxs-lookup"><span data-stu-id="73c20-142">Click to save the registered server settings.</span></span>  
  
  
