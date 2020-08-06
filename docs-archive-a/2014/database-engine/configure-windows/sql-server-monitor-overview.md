---
title: Обзор монитора SQL Server | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlservermonitor.main.f1
helpviewer_keywords:
- SQL Server Monitor [SQL Server]
ms.assetid: 048ae16d-31c3-489a-9f1e-1400a3bacd39
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab90186ed493e616e672cfacf881fd61be166f88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655347"
---
# <a name="sql-server-monitor-overview"></a><span data-ttu-id="f0e32-102">Обзор монитора SQL Server</span><span class="sxs-lookup"><span data-stu-id="f0e32-102">SQL Server Monitor Overview</span></span>
  <span data-ttu-id="f0e32-103">Монитор SQL Server не выполняет функций наблюдения, но в нем размещены модули, которые выполняют эти функции.</span><span class="sxs-lookup"><span data-stu-id="f0e32-103">SQL Server Monitor does not perform monitoring functions, but it hosts modules that do.</span></span> <span data-ttu-id="f0e32-104">К модулям монитора SQL Server относятся монитор репликации и монитор зеркального отображения баз данных.</span><span class="sxs-lookup"><span data-stu-id="f0e32-104">The SQL Server Monitor modules include Replication Monitor and Database Mirroring Monitor.</span></span>  
  
 <span data-ttu-id="f0e32-105">Чтобы использовать один из этих модулей, необходимо выбрать его в меню **Перейти** .</span><span class="sxs-lookup"><span data-stu-id="f0e32-105">To use one of these modules, select that module on the **Go** menu.</span></span> <span data-ttu-id="f0e32-106">Выбранный модуль управляет содержимым панелей навигации и подробных сведений, взаимодействием с пользователем на панелях подробных сведений, а также запросами содержимого и состояния.</span><span class="sxs-lookup"><span data-stu-id="f0e32-106">The currently selected module owns the content of the navigation and detail panes, user interaction in the detail panes, and the queries for content and status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0e32-107">Дополнительные сведения об этих мониторах см. в разделах [Наблюдение за репликацией](../../relational-databases/replication/monitoring-replication.md) и [Наблюдение за зеркальным отображением базы данных (SQL Server)](../database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f0e32-107">For more information about these monitors, see [Monitoring Replication](../../relational-databases/replication/monitoring-replication.md) and [Monitoring Database Mirroring &#40;SQL Server&#41;](../database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="f0e32-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="f0e32-108">Permissions</span></span>  
  
-   <span data-ttu-id="f0e32-109">монитор репликации</span><span class="sxs-lookup"><span data-stu-id="f0e32-109">Replication Monitor</span></span>  
  
     <span data-ttu-id="f0e32-110">Чтобы наблюдать за репликацией, пользователь должен быть членом предопределенной роли сервера **sysadmin** на распространителе или предопределенной роли базы данных **replmonitor** в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="f0e32-110">To monitor replication, you must be a member of the **sysadmin** fixed server role at the Distributor or a member of the **replmonitor** fixed database role in the distribution database.</span></span> <span data-ttu-id="f0e32-111">Системный администратор может добавить любого пользователя в роль **replmonitor** , которая позволяет пользователю наблюдать операции репликации в мониторе репликации. Однако такой пользователь не может управлять репликацией.</span><span class="sxs-lookup"><span data-stu-id="f0e32-111">A system administrator can add any user to the **replmonitor** role, which allows that user to view replication activity in Replication Monitor; however, the user cannot administer replication.</span></span>  
  
-   <span data-ttu-id="f0e32-112">Монитор зеркального отображения баз данных.</span><span class="sxs-lookup"><span data-stu-id="f0e32-112">Database Mirroring Monitor</span></span>  
  
     <span data-ttu-id="f0e32-113">Чтобы наблюдать за зеркальным отображением базы данных, пользователь должен быть членом предопределенной роли сервера **sysadmin** или предопределенной роли базы данных **dbm_monitor** на экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="f0e32-113">To monitor database mirroring, you must be a member of either the **sysadmin** fixed server role or the **dbm_monitor** fixed database role on the server instance.</span></span> <span data-ttu-id="f0e32-114">Если пользователь является членом **sysadmin** или **dbm_monitor** только на одном экземпляре сервера-участника, то монитор сможет подключиться только к этому участнику; монитор не сможет получить данные от другого участника.</span><span class="sxs-lookup"><span data-stu-id="f0e32-114">If you are a member of **sysadmin** or **dbm_monitor** on only one of the partner server instances, the monitor can connect only to that partner; the monitor cannot retrieve information from the other partner.</span></span> <span data-ttu-id="f0e32-115">Дополнительные сведения см. в статье [Database Mirroring Monitor Overview](../database-mirroring/database-mirroring-monitor-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f0e32-115">For more information, see [Database Mirroring Monitor Overview](../database-mirroring/database-mirroring-monitor-overview.md).</span></span>  
  
## <a name="menu-options"></a><span data-ttu-id="f0e32-116">Параметры меню</span><span class="sxs-lookup"><span data-stu-id="f0e32-116">Menu Options</span></span>  
 <span data-ttu-id="f0e32-117">В меню монитора SQL Server содержатся команды для работы с монитором SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f0e32-117">SQL Server Monitor has a menu that contains commands that pertain to SQL Server Monitor.</span></span> <span data-ttu-id="f0e32-118">Это меню также может содержать команды из выбранного модуля.</span><span class="sxs-lookup"><span data-stu-id="f0e32-118">This menu may also contain commands from the selected module.</span></span>  
  
 <span data-ttu-id="f0e32-119">К монитору SQL Server имеют отношение следующие параметры меню.</span><span class="sxs-lookup"><span data-stu-id="f0e32-119">The following menu options pertain to SQL Server Monitor.</span></span>  
  
 <span data-ttu-id="f0e32-120">**Файл**</span><span class="sxs-lookup"><span data-stu-id="f0e32-120">**File**</span></span>  
 <span data-ttu-id="f0e32-121">Это меню содержит команду **Выход** .</span><span class="sxs-lookup"><span data-stu-id="f0e32-121">This menu contains the **Exit** command.</span></span>  
  
 <span data-ttu-id="f0e32-122">**Действие**</span><span class="sxs-lookup"><span data-stu-id="f0e32-122">**Action**</span></span>  
 <span data-ttu-id="f0e32-123">Содержит контекстное меню узла, выбранного в дереве навигации.</span><span class="sxs-lookup"><span data-stu-id="f0e32-123">Contains the context menu of the node selected in the navigation tree.</span></span>  
  
 <span data-ttu-id="f0e32-124">**GO**</span><span class="sxs-lookup"><span data-stu-id="f0e32-124">**Go**</span></span>  
 <span data-ttu-id="f0e32-125">Содержит перечень компонентов мониторинга:</span><span class="sxs-lookup"><span data-stu-id="f0e32-125">Contains a list of monitoring components:</span></span>  
  
-   <span data-ttu-id="f0e32-126">Зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="f0e32-126">Database Mirroring</span></span>  
  
-   <span data-ttu-id="f0e32-127">Репликация</span><span class="sxs-lookup"><span data-stu-id="f0e32-127">Replication</span></span>  
  
 <span data-ttu-id="f0e32-128">**Наблюдение за зеркальным отображением базы данных с помощью среды SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="f0e32-128">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="f0e32-129">Запуск монитора зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f0e32-129">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="f0e32-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="f0e32-130">See Also</span></span>  
 [<span data-ttu-id="f0e32-131">Наблюдение за зеркальным отображением базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f0e32-131">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](../database-mirroring/database-mirroring-sql-server.md)  
  
  
