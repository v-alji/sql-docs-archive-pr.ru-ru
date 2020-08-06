---
title: Диалоговое окно "Выбор источника" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.selectsource.f1
ms.assetid: d664c2e5-dd0c-4da8-b27d-aa4ee4fc0ffd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 535d211d6827477fcf029accc27a9000e8c695c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749752"
---
# <a name="select-source-dialog-box"></a><span data-ttu-id="03817-102">Диалоговое окно «Выбор источника»</span><span class="sxs-lookup"><span data-stu-id="03817-102">Select Source Dialog Box</span></span>
  <span data-ttu-id="03817-103">Это диалоговое окно позволяет выбрать источник политик, которые будут запущены.</span><span class="sxs-lookup"><span data-stu-id="03817-103">Use this dialog box to select the source of the policies to be run.</span></span> <span data-ttu-id="03817-104">Чтобы выбрать один или несколько XML-файлов, содержащих политики, выберите **Файлы**.</span><span class="sxs-lookup"><span data-stu-id="03817-104">To select one or more XML files that contain policies, select **Files**.</span></span> <span data-ttu-id="03817-105">Чтобы запустить политики, найденные в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], выберите **Сервер**.</span><span class="sxs-lookup"><span data-stu-id="03817-105">To run the policies that are found on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], select **Server**.</span></span>  
  
 <span data-ttu-id="03817-106">Это диалоговое окно можно открыть несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="03817-106">You can open this dialog box in several ways.</span></span>  
  
 <span data-ttu-id="03817-107">**Открытие этого окна**</span><span class="sxs-lookup"><span data-stu-id="03817-107">**To open this dialog box**</span></span>  
  
-   <span data-ttu-id="03817-108">В окне "Зарегистрированные серверы" щелкните правой кнопкой мыши элемент **Группы локальных серверов** или любой сервер в области **Группы локальных серверов**или любой сервер в области **Центральные серверы управления**и выберите команду **Оценить политики**.</span><span class="sxs-lookup"><span data-stu-id="03817-108">In Registered Servers, right-click **Local Server Groups** or any server under **Local Server Groups**, or any server under **Central Management Servers**, and then select **Evaluate Policies**.</span></span> <span data-ttu-id="03817-109">На странице **Выбор политик** диалогового окна **Выполнение политик** нажмите кнопку обзора ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="03817-109">In the **Policy Selection** page of the **Evaluate Policies** dialog box, click the Browse (**...**) button.</span></span>  
  
-   <span data-ttu-id="03817-110">В обозревателе объектов раскройте узлы **Управление**и **Управление политиками**, щелкните правой кнопкой мыши **Политики**и выберите пункт **Импортировать политику**.</span><span class="sxs-lookup"><span data-stu-id="03817-110">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Policies**, and select **Import Policy**.</span></span> <span data-ttu-id="03817-111">В диалоговом окне **Импорт** нажмите кнопку "Обзор" ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="03817-111">In the **Import** dialog box, click the Browse (**...**) button.</span></span>  
  
-   <span data-ttu-id="03817-112">В обозревателе объектов щелкните правой кнопкой мыши сервер, базу данных или объект базы данных, выберите **Политики**и команду **Вычислить**.</span><span class="sxs-lookup"><span data-stu-id="03817-112">In Object Explorer, right-click a server, database, or database object, select **Policies**, and then select **Evaluate**.</span></span> <span data-ttu-id="03817-113">На странице **Выбор политик** диалогового окна **Выполнение политик** нажмите кнопку обзора ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="03817-113">In the **Policy Selection** page of the **Evaluate Policies** dialog box, click the Browse (**...**) button.</span></span>  
  
## <a name="options"></a><span data-ttu-id="03817-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="03817-114">Options</span></span>  
 <span data-ttu-id="03817-115">**Файлы**</span><span class="sxs-lookup"><span data-stu-id="03817-115">**Files**</span></span>  
 <span data-ttu-id="03817-116">Выберите один или несколько XML-файлов, содержащих политики.</span><span class="sxs-lookup"><span data-stu-id="03817-116">Select one or more XML files that contain policies.</span></span>  
  
 <span data-ttu-id="03817-117">**Server**</span><span class="sxs-lookup"><span data-stu-id="03817-117">**Server**</span></span>  
 <span data-ttu-id="03817-118">Позволяет выбрать сервер, содержащий политики, которые следует запустить.</span><span class="sxs-lookup"><span data-stu-id="03817-118">Enables you to select a server that contains the policies that you want to run.</span></span>  
  
 <span data-ttu-id="03817-119">**Тип сервера**</span><span class="sxs-lookup"><span data-stu-id="03817-119">**Server type**</span></span>  
 <span data-ttu-id="03817-120">Политики содержатся только на серверах компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03817-120">Only [!INCLUDE[ssDE](../../includes/ssde-md.md)] servers contain policies.</span></span> <span data-ttu-id="03817-121">Поле доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="03817-121">This box is read-only.</span></span>  
  
 <span data-ttu-id="03817-122">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="03817-122">**Server name**</span></span>  
 <span data-ttu-id="03817-123">Выберите экземпляр сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="03817-123">Select the server instance to connect to.</span></span> <span data-ttu-id="03817-124">По умолчанию отображается экземпляр сервера, с которым в последний раз устанавливалось соединение.</span><span class="sxs-lookup"><span data-stu-id="03817-124">By default, the server instance last connected to is displayed.</span></span>  
  
 <span data-ttu-id="03817-125">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="03817-125">**Authentication**</span></span>  
 <span data-ttu-id="03817-126">При подключении к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]доступны два режима проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="03817-126">Two authentication modes are available when you connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="03817-127">**Режим проверки подлинности Windows (проверка подлинности Windows)**</span><span class="sxs-lookup"><span data-stu-id="03817-127">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="03817-128">Режим проверки подлинности Windows позволяет подключаться с пользовательской учетной записью Windows.</span><span class="sxs-lookup"><span data-stu-id="03817-128">Windows Authentication mode allows for a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="03817-129">**Проверка подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="03817-129">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="03817-130">При подключении пользователя с указанным именем входа и паролем из ненадежных соединений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняет проверку подлинности посредством проверки наличия учетной записи входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и проверки совпадения пароля с записанным ранее.</span><span class="sxs-lookup"><span data-stu-id="03817-130">When a user connects with a specified login name and password from a nontrusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication itself by checking whether a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and whether the specified password matches the one previously recorded.</span></span> <span data-ttu-id="03817-131">Если в службе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не задана учетная запись входа, проверка подлинности завершается ошибкой, о которой пользователь получит сообщение.</span><span class="sxs-lookup"><span data-stu-id="03817-131">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="03817-132">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="03817-132">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="03817-133">**User name**</span><span class="sxs-lookup"><span data-stu-id="03817-133">**User name**</span></span>  
 <span data-ttu-id="03817-134">Введите имя пользователя для соединения.</span><span class="sxs-lookup"><span data-stu-id="03817-134">Enter the user name to connect with.</span></span> <span data-ttu-id="03817-135">Этот параметр доступен только при соединении с использованием метода проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="03817-135">This option is available only if you have selected to connect by using Windows Authentication.</span></span>  
  
 <span data-ttu-id="03817-136">**Имя входа**</span><span class="sxs-lookup"><span data-stu-id="03817-136">**Login**</span></span>  
 <span data-ttu-id="03817-137">Введите имя входа для подключения.</span><span class="sxs-lookup"><span data-stu-id="03817-137">Enter the login to connect with.</span></span> <span data-ttu-id="03817-138">Этот параметр доступен только в случае, если выбрано соединение с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03817-138">This option is available only if you have selected to connect by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="03817-139">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="03817-139">**Password**</span></span>  
 <span data-ttu-id="03817-140">Введите пароль для этого имени входа.</span><span class="sxs-lookup"><span data-stu-id="03817-140">Enter the password for the login.</span></span> <span data-ttu-id="03817-141">Этот параметр можно изменить только в случае, если выбрано соединение с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03817-141">This option is editable only if you have selected to connect by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03817-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="03817-142">See Also</span></span>  
 <span data-ttu-id="03817-143">[Узел управления политиками (обозреватель объектов)](../../ssms/object/object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="03817-143">[Policy Management Node &#40;Object Explorer&#41;](../../ssms/object/object-explorer.md) </span></span>  
 [<span data-ttu-id="03817-144">Администрирование серверов с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="03817-144">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
