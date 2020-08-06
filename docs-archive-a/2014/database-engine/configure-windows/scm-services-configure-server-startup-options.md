---
title: Настройка параметров запуска сервера (диспетчер конфигурации SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 01/07/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- parameters [SQL Server], startup options
- SQL Server, startup options
- single-user mode [SQL Server], starting in
- startup options [SQL Server]
- SQL Server services, setting startup options
ms.assetid: 7a94643c-6460-4baf-bb31-0cb99eaf970d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 405a96208c774a6326a69cf9826a14ca3552eae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729797"
---
# <a name="configure-server-startup-options-sql-server-configuration-manager"></a><span data-ttu-id="a98bc-102">Настройка параметров запуска сервера (диспетчер конфигурации SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a98bc-102">Configure Server Startup Options (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="a98bc-103">В этом разделе описано, как настроить параметры запуска, которые будут использоваться при каждом запуске компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], с помощью Configuration Manager [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a98bc-103">This topic describes how to configure startup options that will be used every time the [!INCLUDE[ssDE](../../includes/ssde-md.md)] starts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="a98bc-104">Список параметров запуска см. в разделе [Параметры запуска службы Database Engine](database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="a98bc-104">For a list of startup options, see [Database Engine Service Startup Options](database-engine-service-startup-options.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a98bc-105">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a98bc-105">Before You Begin</span></span>  
  
### <a name="limitations-and-restrictions"></a><span data-ttu-id="a98bc-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a98bc-106">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a98bc-107">записывает параметры запуска в реестр.</span><span class="sxs-lookup"><span data-stu-id="a98bc-107">Configuration Manager writes startup parameters to the registry.</span></span> <span data-ttu-id="a98bc-108">Они вступают в силу при следующем запуске компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a98bc-108">They take effect upon the next startup of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="a98bc-109">В кластере изменения должны вноситься на активном сервере, пока [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] находится в режиме «в сети», и вступают в силу при перезапуске компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a98bc-109">On a cluster, changes must be made on the active server when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is online, and will take effect when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is restarted.</span></span> <span data-ttu-id="a98bc-110">При следующей отработке отказа произойдет обновление реестра другого узла.</span><span class="sxs-lookup"><span data-stu-id="a98bc-110">The registry update of the startup options on the other node will occur upon the next failover.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a98bc-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="a98bc-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a98bc-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="a98bc-112">Permissions</span></span>  
 <span data-ttu-id="a98bc-113">Настраивать параметры запуска сервера могут только пользователи, уполномоченные изменять соответствующие записи в реестре.</span><span class="sxs-lookup"><span data-stu-id="a98bc-113">Configuring server startup options is restricted to users who can change the related entries in the registry.</span></span> <span data-ttu-id="a98bc-114">Это следующие пользователи.</span><span class="sxs-lookup"><span data-stu-id="a98bc-114">This includes the following users.</span></span>  
  
-   <span data-ttu-id="a98bc-115">Члены локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="a98bc-115">Members of the local administrators group.</span></span>  
  
-   <span data-ttu-id="a98bc-116">Учетная запись домена, используемая [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], если компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] настроен для работы под определенной учетной записью домена.</span><span class="sxs-lookup"><span data-stu-id="a98bc-116">The domain account that is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is configured to run under a domain account.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a98bc-117">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="a98bc-117">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-configure-startup-options"></a><span data-ttu-id="a98bc-118">Настройка параметров запуска</span><span class="sxs-lookup"><span data-stu-id="a98bc-118">To configure startup options</span></span>  
  
1.  <span data-ttu-id="a98bc-119">В диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выберите пункт **Службы SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a98bc-119">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, click **SQL Server Services**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a98bc-120">Поскольку диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] является оснасткой консоли управления ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ), а не изолированной программой, при работе в более новых версиях Windows диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не отображается как приложение.</span><span class="sxs-lookup"><span data-stu-id="a98bc-120">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager does not appear as an application in newer versions of Windows.</span></span>  
    >   
    >  -   <span data-ttu-id="a98bc-121">**Windows 10**:</span><span class="sxs-lookup"><span data-stu-id="a98bc-121">**Windows 10**:</span></span>  
    >          <span data-ttu-id="a98bc-122">Чтобы открыть [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, на **начальной странице**введите SQLServerManager12. msc (для [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="a98bc-122">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, on the **Start Page**, type SQLServerManager12.msc (for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="a98bc-123">Для предыдущих версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] замените 12 на меньшее число.</span><span class="sxs-lookup"><span data-stu-id="a98bc-123">For previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replace 12 with a smaller number.</span></span> <span data-ttu-id="a98bc-124">Если щелкнуть SQLServerManager12.msc, откроется диспетчер конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a98bc-124">Clicking SQLServerManager12.msc opens the Configuration Manager.</span></span> <span data-ttu-id="a98bc-125">Чтобы закрепить Configuration Manager на начальной странице или на панели задач, щелкните правой кнопкой мыши SQLServerManager12. msc и выберите **открыть расположение файла**.</span><span class="sxs-lookup"><span data-stu-id="a98bc-125">To pin the Configuration Manager to the Start Page or Task Bar, right-click SQLServerManager12.msc, and then click **Open file location**.</span></span> <span data-ttu-id="a98bc-126">В проводнике Windows щелкните правой кнопкой мыши файл SQLServerManager12. msc и выберите пункт **закрепить на** **панели задач или закрепить на**ней.</span><span class="sxs-lookup"><span data-stu-id="a98bc-126">In the Windows File Explorer, right-click SQLServerManager12.msc, and then click **Pin to Start** or **Pin to taskbar**.</span></span>  
    > -   <span data-ttu-id="a98bc-127">**Windows 8**:</span><span class="sxs-lookup"><span data-stu-id="a98bc-127">**Windows 8**:</span></span>  
    >          <span data-ttu-id="a98bc-128">Чтобы открыть [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, во вложенном поле **Поиск** в разделе **приложения**введите **SQLServerManager \<version> . msc** , например `SQLServerManager12.msc` , и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="a98bc-128">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager\<version>.msc** such as `SQLServerManager12.msc`, and then press **Enter**.</span></span>  
  
2.  <span data-ttu-id="a98bc-129">На правой панели щелкните правой кнопкой мыши **SQL Server (***<instance_name>***)** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a98bc-129">In the right pane, right-click **SQL Server (***<instance_name>***)**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="a98bc-130">На вкладке **Параметры запуска** в поле **Укажите параметр запуска** введите параметр и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a98bc-130">On the **Startup Parameters** tab, in the **Specify a startup parameter** box, type the parameter, and then click **Add**.</span></span>  
  
     <span data-ttu-id="a98bc-131">Например, чтобы запустить в однопользовательском режиме, введите `-m` в поле **укажите параметр запуска** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="a98bc-131">For example, to start in single-user mode, type `-m` in the **Specify a startup parameter** box and then click **Add**.</span></span> <span data-ttu-id="a98bc-132">(Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] перезапускается в однопользовательском режиме, остановите агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a98bc-132">(When you restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in single-user mode, stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="a98bc-133">В противном случае агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может установить соединение первым, что не позволит подключиться второму пользователю.</span><span class="sxs-lookup"><span data-stu-id="a98bc-133">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent might connect first and prevent you from connecting as a second user.)</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="a98bc-134">Перезапустите компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a98bc-134">Restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="a98bc-135">Завершив работу в однопользовательском режиме, в поле Параметры запуска выберите `-m` параметр в поле **существующие параметры** , а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a98bc-135">After you are finished using single-user mode, in the Startup Parameters box, select the `-m` parameter in the **Existing Parameters** box, and then click **Remove**.</span></span> <span data-ttu-id="a98bc-136">Чтобы вернуться к обычному многопользовательскому режиму [!INCLUDE[ssDE](../../includes/ssde-md.md)] , перезапустите компонент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a98bc-136">Restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to restore [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to the typical multi-user mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a98bc-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="a98bc-137">See Also</span></span>  
 <span data-ttu-id="a98bc-138">[Запуск SQL Server в однопользовательском режиме](start-sql-server-in-single-user-mode.md) </span><span class="sxs-lookup"><span data-stu-id="a98bc-138">[Start SQL Server in Single-User Mode](start-sql-server-in-single-user-mode.md) </span></span>  
 <span data-ttu-id="a98bc-139">[Подключение к SQL Server в случае, если доступ системных администраторов заблокирован](connect-to-sql-server-when-system-administrators-are-locked-out.md) </span><span class="sxs-lookup"><span data-stu-id="a98bc-139">[Connect to SQL Server When System Administrators Are Locked Out](connect-to-sql-server-when-system-administrators-are-locked-out.md) </span></span>  
 [<span data-ttu-id="a98bc-140">Запуск, остановка или приостановка службы агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="a98bc-140">Start, Stop, or Pause the SQL Server Agent Service</span></span>](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
