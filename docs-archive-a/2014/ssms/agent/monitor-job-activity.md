---
title: Наблюдение за активностью заданий | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, monitoring
- jobs [SQL Server Agent], monitoring
- monitoring [SQL Server], jobs
- activity monitoring [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- SQL Server Agent Job Activity Monitor
- SQL Server Agent jobs, monitoring
- performance [SQL Server], jobs
- current activity
ms.assetid: 71cb432b-631d-4b8b-9965-e731b3d8266d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5088e029e90b4556c1559f8c948e8a8734762749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658048"
---
# <a name="monitor-job-activity"></a><span data-ttu-id="d71fb-102">Наблюдение за активностью заданий</span><span class="sxs-lookup"><span data-stu-id="d71fb-102">Monitor Job Activity</span></span>
  <span data-ttu-id="d71fb-103">Текущую активность всех определенных заданий экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно контролировать при помощи монитора активности заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d71fb-103">You can monitor the current activity of all defined jobs on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job Activity Monitor.</span></span>  
  
## <a name="sql-server-agent-sessions"></a><span data-ttu-id="d71fb-104">Сеансы агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="d71fb-104">SQL Server Agent Sessions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d71fb-105">Агент создает новый сеанс при каждом запуске службы.</span><span class="sxs-lookup"><span data-stu-id="d71fb-105">Agent creates a new session each time the service starts.</span></span> <span data-ttu-id="d71fb-106">При создании нового сеанса таблица **sysjobactivity** в базе данных **msdb** заполняется всеми существующими определенными заданиями.</span><span class="sxs-lookup"><span data-stu-id="d71fb-106">When a new session is created, the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs.</span></span> <span data-ttu-id="d71fb-107">При перезапуске агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в этой таблице сохраняются данные о последних действиях заданий.</span><span class="sxs-lookup"><span data-stu-id="d71fb-107">This table preserves the last activity for jobs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is restarted.</span></span> <span data-ttu-id="d71fb-108">В каждом сеансе записываются данные об обычных действиях заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , от начала каждого задания до его завершения.</span><span class="sxs-lookup"><span data-stu-id="d71fb-108">Each session records [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent normal job activity from the start of the job to its finish.</span></span> <span data-ttu-id="d71fb-109">Данные об этих сеансах сохраняются в таблице **syssessions** базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="d71fb-109">Information about these sessions is stored in the **syssessions** table of the **msdb** database.</span></span>  
  
## <a name="job-activity-monitor"></a><span data-ttu-id="d71fb-110">Монитор активности заданий</span><span class="sxs-lookup"><span data-stu-id="d71fb-110">Job Activity Monitor</span></span>  
 <span data-ttu-id="d71fb-111">Монитор активности заданий позволяет просмотреть таблицу **sysjobactivity** в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d71fb-111">The Job Activity Monitor allows you to view the **sysjobactivity** table by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d71fb-112">Можно просматривать все задания на сервере или можно определить фильтры, ограничивающие количество отображаемых заданий.</span><span class="sxs-lookup"><span data-stu-id="d71fb-112">You can view all jobs on the server, or you can define filters to limit the number of jobs displayed.</span></span> <span data-ttu-id="d71fb-113">Можно также отсортировать данные о заданиях, щелкнув заголовок столбца в сетке **Активность заданий агента** .</span><span class="sxs-lookup"><span data-stu-id="d71fb-113">You can also sort the job information by clicking on a column heading in the **Agent Job Activity** grid.</span></span> <span data-ttu-id="d71fb-114">Например, при выборе заголовка столбца **Последний запуск** можно просмотреть задания в том порядке, в котором они выполнялись в последний раз.</span><span class="sxs-lookup"><span data-stu-id="d71fb-114">For example, when you select the **Last Run** column heading, you can view the jobs in the order that they were last run.</span></span> <span data-ttu-id="d71fb-115">При повторном щелчке заголовка столбца производится переключение порядка отображения заданий по дате их последнего выполнения: порядок по возрастанию меняется на порядок по убыванию, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="d71fb-115">Clicking the column heading again toggles the jobs in ascending and descending order based on their last run date.</span></span>  
  
 <span data-ttu-id="d71fb-116">Использование монитора активности заданий позволяет выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d71fb-116">Using the Job Activity Monitor you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="d71fb-117">Запускать и останавливать задания.</span><span class="sxs-lookup"><span data-stu-id="d71fb-117">Start and stop jobs.</span></span>  
  
-   <span data-ttu-id="d71fb-118">Просматривать свойства заданий.</span><span class="sxs-lookup"><span data-stu-id="d71fb-118">View job properties.</span></span>  
  
-   <span data-ttu-id="d71fb-119">Просматривать журнал определенного задания.</span><span class="sxs-lookup"><span data-stu-id="d71fb-119">View the history for a specific job.</span></span>  
  
-   <span data-ttu-id="d71fb-120">Обновлять данные в сетке **Активность заданий агента** вручную или задавать интервал автоматического обновления после нажатия кнопки **Просмотреть настройки обновления**.</span><span class="sxs-lookup"><span data-stu-id="d71fb-120">Refresh the information in the **Agent Job Activity** grid manually or set an automatic refresh interval by clicking **View refresh settings**.</span></span>  
  
 <span data-ttu-id="d71fb-121">Монитор активности заданий используется, если необходимо определить, какие задания запланированы на выполнение, результаты последнего выполнения заданий в ходе текущего сеанса, а также для определения того, какие задания в настоящее время выполняются или бездействуют.</span><span class="sxs-lookup"><span data-stu-id="d71fb-121">Use the Job Activity Monitor when you want to find out what jobs are scheduled to run, the last outcome of jobs that have run during the current session, and to find out which jobs are currently running or idle.</span></span> <span data-ttu-id="d71fb-122">При неожиданном неуспешном завершении службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно определить, какие задания были наиболее активны, проанализировав данные предыдущего сеанса в мониторе активности заданий.</span><span class="sxs-lookup"><span data-stu-id="d71fb-122">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service fails unexpectedly, you can determine which jobs were in the middle of being executed by looking at the previous session in the Job Activity Monitor.</span></span>  
  
 <span data-ttu-id="d71fb-123">Чтобы открыть монитор активности заданий, разверните узел **Агент SQL Server** в обозревателе объектов среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , правой кнопкой мыши щелкните **Монитор активности заданий**и выберите **Просмотр активности заданий**.</span><span class="sxs-lookup"><span data-stu-id="d71fb-123">To open the Job Activity Monitor, expand **SQL Server Agent** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Object Explorer, right-click **Job Activity Monitor**, and click **View Job Activity**.</span></span>  
  
 <span data-ttu-id="d71fb-124">Просмотреть активность заданий текущего сеанса также можно с помощью хранимой процедуры **sp_help_jobactivity**.</span><span class="sxs-lookup"><span data-stu-id="d71fb-124">You can also view job activity for the current session by using the stored procedure **sp_help_jobactivity**.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d71fb-125">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="d71fb-125">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d71fb-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d71fb-126">**Description**</span></span>|<span data-ttu-id="d71fb-127">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="d71fb-127">**Topic**</span></span>|  
|<span data-ttu-id="d71fb-128">Описывает, как просмотреть состояние времени выполнения для заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d71fb-128">Describes how to view the runtime state of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="d71fb-129">Просмотр активности заданий</span><span class="sxs-lookup"><span data-stu-id="d71fb-129">View Job Activity</span></span>](view-job-activity.md)|  
  
## <a name="see-also"></a><span data-ttu-id="d71fb-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="d71fb-130">See Also</span></span>  
 <span data-ttu-id="d71fb-131">[Просмотр активности заданий](view-job-activity.md) </span><span class="sxs-lookup"><span data-stu-id="d71fb-131">[View Job Activity](view-job-activity.md) </span></span>  
 <span data-ttu-id="d71fb-132">[dbo.sysжобактивити &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-sysjobactivity-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d71fb-132">[dbo.sysjobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-sysjobactivity-transact-sql) </span></span>  
 <span data-ttu-id="d71fb-133">[dbo.sysсеансы &#40;&#41;Transact-SQL](/sql/relational-databases/system-tables/dbo-syssessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d71fb-133">[dbo.syssessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-syssessions-transact-sql) </span></span>  
 [<span data-ttu-id="d71fb-134">sp_help_jobactivity &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d71fb-134">sp_help_jobactivity &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql)  
  
  
