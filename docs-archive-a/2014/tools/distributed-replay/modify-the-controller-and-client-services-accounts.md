---
title: Изменение учетных записей служб клиента и контроллера | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 44a73ddb-18ad-415c-bfbe-126ab2e3290b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62a054749f1d53323bde5c9d05a1e7632b1dda85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734821"
---
# <a name="modify-the-controller-and-client-services-accounts"></a><span data-ttu-id="a8699-102">Изменение учетных записей служб клиента и контроллера</span><span class="sxs-lookup"><span data-stu-id="a8699-102">Modify the Controller and Client Services Accounts</span></span>
  <span data-ttu-id="a8699-103">В этом разделе будет рассказано о том, как изменить учетные записи контроллера и клиента распределенного воспроизведения и повторно применить списки управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="a8699-103">In this topic, you will learn how to modify the Distributed Replay controller and client service accounts, and then reapply the access control lists (ACLs).</span></span>  
  
### <a name="to-start-or-stop-the-distributed-replay-services-using-computer-management"></a><span data-ttu-id="a8699-104">Запуск и остановка служб распределенного воспроизведения из оснастки «Управление компьютером»</span><span class="sxs-lookup"><span data-stu-id="a8699-104">To start or stop the Distributed Replay services using Computer Management</span></span>  
  
1.  <span data-ttu-id="a8699-105">На компьютере, на котором установлены службы распределенного воспроизведения, в командной строке введите `dcomcnfg`.</span><span class="sxs-lookup"><span data-stu-id="a8699-105">On the computer on which the Distributed Replay services are installed, from the command prompt, type `dcomcnfg`.</span></span>  
  
2.  <span data-ttu-id="a8699-106">Дважды щелкните **службы**, прокрутите вниз и щелкните правой кнопкой мыши \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] распределенное воспроизведение \<service name> \*\*, а затем выберите **Запуск** или **остановки**.</span><span class="sxs-lookup"><span data-stu-id="a8699-106">Double-click **Services**, scroll down and right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay \<service name>**, and then click **Start** or **Stop**.</span></span>  
  
### <a name="to-modify-the-distributed-replay-controller-service"></a><span data-ttu-id="a8699-107">Изменение службы контроллера распределенного воспроизведения</span><span class="sxs-lookup"><span data-stu-id="a8699-107">To modify the Distributed Replay controller service</span></span>  
  
1.  <span data-ttu-id="a8699-108">На компьютере контроллера остановите службу контроллера распределенного воспроизведения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8699-108">On the controller computer, stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service.</span></span>  
  
2.  <span data-ttu-id="a8699-109">На вкладке **Службы** правой кнопкой мыши щелкните **Контроллер распределенного воспроизведения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a8699-109">Under **Services**, right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller**, and then select **Properties**.</span></span>  
  
3.  <span data-ttu-id="a8699-110">В окне **Свойства контроллера распределенного воспроизведения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** на вкладке **Вход в систему** выберите **Эта учетная запись**, введите имя или нажмите кнопку **Обзор** для выбора новой учетной записи входа и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a8699-110">In the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller Properties** window, on the **Log On** tab, select **This account**, type or click **Browse** to enter the new logon account, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a8699-111">**Важно!** При настройке контроллера распределенного воспроизведения можно указать одну или несколько учетных записей пользователя, которые будут применяться для запуска служб клиента распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="a8699-111">**Important**: When you configure Distributed Replay Controller, you can specify one or more user accounts that will be used to run the Distributed Replay Client services.</span></span> <span data-ttu-id="a8699-112">Далее представлен список поддерживаемых учетных записей.</span><span class="sxs-lookup"><span data-stu-id="a8699-112">The following is the list of supported accounts:</span></span>  
  
    -   <span data-ttu-id="a8699-113">Учетная запись пользователя домена</span><span class="sxs-lookup"><span data-stu-id="a8699-113">Domain user account</span></span>  
  
    -   <span data-ttu-id="a8699-114">Пользователь, который создал учетную запись локального пользователя</span><span class="sxs-lookup"><span data-stu-id="a8699-114">User created local user account</span></span>  
  
    -   <span data-ttu-id="a8699-115">Администратор</span><span class="sxs-lookup"><span data-stu-id="a8699-115">Administrator</span></span>  
  
    -   <span data-ttu-id="a8699-116">Виртуальная учетная запись и управляемая учетная запись службы (MSA)</span><span class="sxs-lookup"><span data-stu-id="a8699-116">Virtual account and MSA (Managed Service Account)</span></span>  
  
    -   <span data-ttu-id="a8699-117">Сетевые службы, локальные службы и система</span><span class="sxs-lookup"><span data-stu-id="a8699-117">Network Services, Local Services, and System</span></span>  
  
     <span data-ttu-id="a8699-118">Учетные записи групп (локальные или доменные) и другие встроенные учетные записи (например, «Все») не принимаются.</span><span class="sxs-lookup"><span data-stu-id="a8699-118">Group accounts (local or domain) and other built-in accounts (like Everyone) are not accepted.</span></span>  
  
4.  <span data-ttu-id="a8699-119">Запустите службу контроллера распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="a8699-119">Start the Distributed Replay controller service.</span></span>  
  
### <a name="to-modify-the-distributed-replay-client-service"></a><span data-ttu-id="a8699-120">Изменение службы клиента распределенного воспроизведения</span><span class="sxs-lookup"><span data-stu-id="a8699-120">To modify the Distributed Replay client service</span></span>  
  
1.  <span data-ttu-id="a8699-121">Прежде чем изменить службу клиента распределенного воспроизведения, убедитесь, что изменяемая учетная запись службы была указана во время настройки (в параметре CTLRUSEERS на компьютере контроллера).</span><span class="sxs-lookup"><span data-stu-id="a8699-121">Before you modify the Distributed Replay client service, make sure the client service account you are changing was specified during setup (in the CTLRUSERS parameter on the controller computer).</span></span> <span data-ttu-id="a8699-122">Если учетная запись изменяемой службы клиента не была указана во время настройки, необходимо сначала выполнить следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="a8699-122">If the client service account you are changing was not specified during setup, you must perform the following steps first:</span></span>  
  
    1.  <span data-ttu-id="a8699-123">Остановите службу контроллера распределенного воспроизведения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8699-123">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service.</span></span>  
  
    2.  <span data-ttu-id="a8699-124">На компьютере контроллера, на котором установлена служба контроллера, в командной строке введите `dcomcnfg`.</span><span class="sxs-lookup"><span data-stu-id="a8699-124">On the controller computer on which the controller service is installed, from the command prompt, type `dcomcnfg`.</span></span>  
  
    3.  <span data-ttu-id="a8699-125">В окне **Службы компонентов** перейдите в папку **Корень консоли -> Службы компонентов -> Компьютеры -> Мой компьютер -> Настройка DCOM -> Контроллер распределенного воспроизведения**.</span><span class="sxs-lookup"><span data-stu-id="a8699-125">In the **Component Services** window, navigate to **Console Root -> Component Services -> Computers -> My Computer -> DCOM Config ->DReplayController**.</span></span>  
  
    4.  <span data-ttu-id="a8699-126">Щелкните **DReplayController**правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a8699-126">Right-click **DReplayController**, and then click **Properties**.</span></span>  
  
    5.  <span data-ttu-id="a8699-127">В окне **Свойства DReplayController** на вкладке **Безопасность** нажмите кнопку **Правка** в разделе **Разрешения запуска и активации** .</span><span class="sxs-lookup"><span data-stu-id="a8699-127">In the **DReplayController Properties** window, on the **Security** tab, click **Edit** in the **Launch and Activation Permissions** section.</span></span>  
  
    6.  <span data-ttu-id="a8699-128">Предоставьте учетной записи входа новой службы клиента разрешения **Локальная и удаленная активация** , затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a8699-128">Grant the new client service logon account **Local and Remote activation** permissions, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="a8699-129">Щелкните **Правка** в разделе **Разрешения доступа** и предоставьте новой учетной записи входа службы клиента разрешения **Локальный и удаленный доступ** , затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a8699-129">Click **Edit** in the **Access Permissions** section, and grant the new client service logon account **Local and Remote access** permissions, and then click **OK**.</span></span>  
  
    8.  <span data-ttu-id="a8699-130">Нажмите кнопку **ОК** , чтобы закрыть окно **Свойства DReplayController** .</span><span class="sxs-lookup"><span data-stu-id="a8699-130">Click **OK** to close the **DReplayController Properties** window.</span></span>  
  
    9. <span data-ttu-id="a8699-131">На компьютере контроллера добавьте измененную учетную запись входа службы клиента в группу **Пользователи DCOM** .</span><span class="sxs-lookup"><span data-stu-id="a8699-131">On the controller computer, add the changed client service logon account to the **Distributed COM Users** group.</span></span>  
  
    10. <span data-ttu-id="a8699-132">Запустите службу контроллера распределенного воспроизведения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8699-132">Start the SQL Server Distributed Replay controller service.</span></span>  
  
2.  <span data-ttu-id="a8699-133">Остановите службу клиента распределенного воспроизведения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8699-133">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay client service.</span></span>  
  
3.  <span data-ttu-id="a8699-134">В окне **Свойства клиента распределенного воспроизведения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** на вкладке **Вход в систему** выберите пункт **Эта учетная запись**, введите имя или нажмите кнопку **Обзор** для выбора новой учетной записи входа и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a8699-134">In the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Client Properties** window, on the **Log On** tab, select **This account**, type or click **Browse** to enter the new logon account, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="a8699-135">Запустите службу клиента распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="a8699-135">Start the Distributed Replay client service.</span></span>  
  
  
