---
title: Запуск заданий по обслуживанию репликации (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server replication]
ms.assetid: 0dc485a0-5a50-41eb-a29d-f2b2fb920174
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9dc27c65e96a9f956ffa6d3edf9c72ed52f721a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736257"
---
# <a name="run-replication-maintenance-jobs-sql-server-management-studio"></a><span data-ttu-id="8beed-102">запустить задания по обслуживанию репликаций (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8beed-102">Run Replication Maintenance Jobs (SQL Server Management Studio)</span></span>
  <span data-ttu-id="8beed-103">Репликация использует следующие задания по обслуживанию:</span><span class="sxs-lookup"><span data-stu-id="8beed-103">Replication uses the following maintenance jobs:</span></span>  
  
-   <span data-ttu-id="8beed-104">**Повторная инициализация подписок, имеющих сбои при выполнении проверки данных**</span><span class="sxs-lookup"><span data-stu-id="8beed-104">**Reinitialize subscriptions having data validation failures**</span></span>
-   <span data-ttu-id="8beed-105">**Очистка журнала агента: распределение**</span><span class="sxs-lookup"><span data-stu-id="8beed-105">**Agent history clean up: distribution**</span></span>
-   <span data-ttu-id="8beed-106">**Обновитель монитора репликацией для распространителя**</span><span class="sxs-lookup"><span data-stu-id="8beed-106">**Replication monitoring refresher for distribution.**</span></span>
-   <span data-ttu-id="8beed-107">**Контроль за агентами репликации**</span><span class="sxs-lookup"><span data-stu-id="8beed-107">**Replication agents checkup**</span></span>
-   <span data-ttu-id="8beed-108">**Очистка распространения: распространение**</span><span class="sxs-lookup"><span data-stu-id="8beed-108">**Distribution clean up: distribution**</span></span>
-   <span data-ttu-id="8beed-109">**Очистка истекшей подписки**</span><span class="sxs-lookup"><span data-stu-id="8beed-109">**Expired subscription clean up**</span></span>  
  
 <span data-ttu-id="8beed-110">Запустить и остановить эти задания можно из папки **Задания** в среде [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] и на вкладке **Агенты** монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="8beed-110">Start and stop these jobs from the **Jobs** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from the **Agents** tab in Replication Monitor.</span></span> <span data-ttu-id="8beed-111">Сведения о запуске монитора репликации см. в [этой статье](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="8beed-111">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span> <span data-ttu-id="8beed-112">Просмотр и изменение свойств каждого задания осуществляется в диалоговом окне **Свойства задания — \<Job>** , доступном в той же папке и на той же вкладке.</span><span class="sxs-lookup"><span data-stu-id="8beed-112">View and modify properties for each job in the **Job Properties - \<Job>** dialog box, which is available from the same folder and tab.</span></span>  
  
### <a name="to-start-or-stop-a-replication-maintenance-job-in-management-studio"></a><span data-ttu-id="8beed-113">Запуск или остановка задания по обслуживанию репликации в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="8beed-113">To start or stop a replication maintenance job in Management Studio</span></span>  
  
1.  <span data-ttu-id="8beed-114">Подключитесь к распространителю в [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]и разверните узел сервера.</span><span class="sxs-lookup"><span data-stu-id="8beed-114">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="8beed-115">Раскройте папку **Агент SQL Server** , а затем — папку **Задания** .</span><span class="sxs-lookup"><span data-stu-id="8beed-115">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="8beed-116">Щелкните правой кнопкой мыши задание, а затем щелкните **Запустить задание** или **Остановить задание**.</span><span class="sxs-lookup"><span data-stu-id="8beed-116">Right-click a job, and then click **Start Job** or **Stop Job**.</span></span>  
  
### <a name="to-start-or-stop-a-replication-maintenance-job-in-replication-monitor"></a><span data-ttu-id="8beed-117">Запуск или остановка задания по обслуживанию репликации в мониторе репликации</span><span class="sxs-lookup"><span data-stu-id="8beed-117">To start or stop a replication maintenance job in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="8beed-118">В мониторе репликации раскройте группу издателей и выберите в ней издателя.</span><span class="sxs-lookup"><span data-stu-id="8beed-118">Expand a Publisher group in Replication Monitor, and then select a Publisher.</span></span>  
  
2.  <span data-ttu-id="8beed-119">Перейдите на вкладку **Агенты** .</span><span class="sxs-lookup"><span data-stu-id="8beed-119">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="8beed-120">Щелкните правой кнопкой мыши задание в сетке, а затем щелкните **Запустить задание** или **Остановить задание**.</span><span class="sxs-lookup"><span data-stu-id="8beed-120">Right-click a job in the grid, and then click **Start Job** or **Stop Job**.</span></span>  
  
### <a name="to-view-and-modify-properties-for-a-replication-maintenance-job-in-management-studio"></a><span data-ttu-id="8beed-121">Просмотр и изменение свойств задания по обслуживанию репликации в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="8beed-121">To view and modify properties for a replication maintenance job in Management Studio</span></span>  
  
1.  <span data-ttu-id="8beed-122">Подключитесь к распространителю в [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]и разверните узел сервера.</span><span class="sxs-lookup"><span data-stu-id="8beed-122">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="8beed-123">Раскройте папку **Агент SQL Server** , а затем — папку **Задания** .</span><span class="sxs-lookup"><span data-stu-id="8beed-123">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="8beed-124">Правой кнопкой мыши щелкните задание и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8beed-124">Right-click a job, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8beed-125">В диалоговом окне **Свойства задания — \<Job>** измените любые свойства, если это необходимо, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8beed-125">In the **Job Properties - \<Job>** dialog box, modify any properties if necessary, and then click **OK**.</span></span>  
  
### <a name="to-view-and-modify-properties-for-a-replication-maintenance-job-in-replication-monitor"></a><span data-ttu-id="8beed-126">Просмотр и изменение свойств задания по обслуживанию репликации в мониторе репликации</span><span class="sxs-lookup"><span data-stu-id="8beed-126">To view and modify properties for a replication maintenance job in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="8beed-127">В мониторе репликации раскройте группу издателей и выберите в ней издателя.</span><span class="sxs-lookup"><span data-stu-id="8beed-127">Expand a Publisher group in Replication Monitor, and then select a Publisher.</span></span>  
  
2.  <span data-ttu-id="8beed-128">Перейдите на вкладку **Агенты** .</span><span class="sxs-lookup"><span data-stu-id="8beed-128">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="8beed-129">Щелкните правой кнопкой мыши задание в сетке, а затем щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8beed-129">Right-click a job in the grid, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8beed-130">В диалоговом окне **Свойства задания — \<Job>** измените любые свойства, если это необходимо, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8beed-130">In the **Job Properties - \<Job>** dialog box, modify any properties if necessary, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8beed-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="8beed-131">See Also</span></span>  
 <span data-ttu-id="8beed-132">[Запуск и остановка агента репликации (среда SQL Server Management Studio)](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="8beed-132">[Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="8beed-133">[Просмотр сведений и выполнение задач с помощью монитора репликации](../monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="8beed-133">[View Information and Perform Tasks using Replication Monitor](../monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="8beed-134">Администрирование агента репликации</span><span class="sxs-lookup"><span data-stu-id="8beed-134">Replication Agent Administration</span></span>](../agents/replication-agent-administration.md)  
  
  
