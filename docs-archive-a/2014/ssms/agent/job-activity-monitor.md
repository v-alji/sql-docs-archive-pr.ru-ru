---
title: Монитор активности заданий | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.ACTIVITYMON.F1
- sql12.ag.jobactivitymonitor.alljobs.f1
ms.assetid: 11f2182c-5f71-46f8-8d2b-74f0fc48f2d6
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6f89d5448f0885c85229c2808ee6f85bf6fa071
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731354"
---
# <a name="job-activity-monitor"></a><span data-ttu-id="2709f-102">Монитор активности заданий</span><span class="sxs-lookup"><span data-stu-id="2709f-102">Job Activity Monitor</span></span>
  <span data-ttu-id="2709f-103">Эта страница позволяет просматривать текущую активность заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2709f-103">Use this page to view the current activity of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span> <span data-ttu-id="2709f-104">Выберите пункт **Фильтр** для отбора выводимых заданий.</span><span class="sxs-lookup"><span data-stu-id="2709f-104">Click **Filter** to limit the jobs displayed.</span></span> <span data-ttu-id="2709f-105">Сетка **Активность заданий агента** доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="2709f-105">The **Agent Job Activity** grid is read-only.</span></span> <span data-ttu-id="2709f-106">Щелкните заголовки столбцов для сортировки этой сетки.</span><span class="sxs-lookup"><span data-stu-id="2709f-106">Click on the column headers to sort the grid.</span></span> <span data-ttu-id="2709f-107">Для изменения задания дважды щелкните его, чтобы открыть диалоговое окно **Свойства задания** .</span><span class="sxs-lookup"><span data-stu-id="2709f-107">To modify a job, double-click the job to open the **Job Properties** dialog box.</span></span> <span data-ttu-id="2709f-108">Щелкните правой кнопкой мыши задание в сетке, чтобы запустить его на выполнение всех его шагов, запуска определенного шага задания, отключения или включения, обновления, удаления задания, просмотра его журнала и просмотра свойств задания.</span><span class="sxs-lookup"><span data-stu-id="2709f-108">Right-click a job in the grid to start it running all job steps, start at a particular job step, disable or enable the job, refresh the job, delete the job, view the history of the job, or view the properties of the job.</span></span> <span data-ttu-id="2709f-109">Нажмите кнопку **Обновить** для обновления сетки с текущими данными.</span><span class="sxs-lookup"><span data-stu-id="2709f-109">Click **Refresh** to update the grid with current information.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2709f-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="2709f-110">Options</span></span>  
 <span data-ttu-id="2709f-111">**имя**;</span><span class="sxs-lookup"><span data-stu-id="2709f-111">**Name**</span></span>  
 <span data-ttu-id="2709f-112">Имя задания.</span><span class="sxs-lookup"><span data-stu-id="2709f-112">Name of the job.</span></span>  
  
 <span data-ttu-id="2709f-113">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="2709f-113">**Enabled**</span></span>  
 <span data-ttu-id="2709f-114">Указывает, включено задание (**да**) или отключено (**нет**).</span><span class="sxs-lookup"><span data-stu-id="2709f-114">Whether the job is enabled (**yes**) or not enabled (**no**).</span></span>  
  
 <span data-ttu-id="2709f-115">**Состояние** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2709f-115">**Status** <sup>1</sup></span></span>  
 <span data-ttu-id="2709f-116">Текущее состояние задания.</span><span class="sxs-lookup"><span data-stu-id="2709f-116">Current status of the job.</span></span>  
  
 <span data-ttu-id="2709f-117">**Результат последнего запуска**</span><span class="sxs-lookup"><span data-stu-id="2709f-117">**Last Run Outcome**</span></span>  
 <span data-ttu-id="2709f-118">Состояние задания при последнем запуске.</span><span class="sxs-lookup"><span data-stu-id="2709f-118">Job status when last run.</span></span>  
  
 <span data-ttu-id="2709f-119">**Последний запуск**</span><span class="sxs-lookup"><span data-stu-id="2709f-119">**Last Run**</span></span>  
 <span data-ttu-id="2709f-120">Дата и время последнего запуска задания с использованием локальной даты и времени сервера.</span><span class="sxs-lookup"><span data-stu-id="2709f-120">Date and time job was last run using the local date and time of the server.</span></span>  
  
 <span data-ttu-id="2709f-121">**Следующий запуск** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2709f-121">**Next Run** <sup>1</sup></span></span>  
 <span data-ttu-id="2709f-122">Дата и время запланированного следующего запуска задания с использованием локальной даты и времени сервера.</span><span class="sxs-lookup"><span data-stu-id="2709f-122">Date and time the job is next scheduled to run using the local date and time of the server.</span></span>  
  
 <span data-ttu-id="2709f-123">**Категория**</span><span class="sxs-lookup"><span data-stu-id="2709f-123">**Category**</span></span>  
 <span data-ttu-id="2709f-124">Категория, присвоенная заданию.</span><span class="sxs-lookup"><span data-stu-id="2709f-124">The job category assigned to the job.</span></span>  
  
 <span data-ttu-id="2709f-125">**Готов к запуску**</span><span class="sxs-lookup"><span data-stu-id="2709f-125">**Runnable**</span></span>  
 <span data-ttu-id="2709f-126">**Да** , если задание можно запустить; **Нет** , если задание запустить нельзя.</span><span class="sxs-lookup"><span data-stu-id="2709f-126">**Yes** if the job can be run; **No** if the job cannot be run.</span></span> <span data-ttu-id="2709f-127">Задание нельзя запустить, если оно не содержит шагов или если в нем не указан целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="2709f-127">A job is not runnable if it has no steps or if it has no target server.</span></span>  
  
 <span data-ttu-id="2709f-128">**Назначенные**</span><span class="sxs-lookup"><span data-stu-id="2709f-128">**Scheduled**</span></span>  
 <span data-ttu-id="2709f-129">**Да** , если заданию назначено расписание; **Нет** , если у задания нет расписания.</span><span class="sxs-lookup"><span data-stu-id="2709f-129">**Yes** if the job is assigned to a job schedule; **No** if the job has no schedule.</span></span>  
  
 <span data-ttu-id="2709f-130"><sup>1</sup> Только члены [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предопределенной роли сервера sysadmin и группы администраторов сервера могут видеть значения в этом столбце.</span><span class="sxs-lookup"><span data-stu-id="2709f-130"><sup>1</sup>Only members of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sysadmin fixed server role and the server administrators group can see values in this column.</span></span> <span data-ttu-id="2709f-131">Члены роли SQLAgentOperatorRole не могут видеть значения в этом столбце.</span><span class="sxs-lookup"><span data-stu-id="2709f-131">Members of the SQLAgentOperatorRole role cannot see values in this column.</span></span>  
  
#### <a name="to-open-the-job-activity-monitor"></a><span data-ttu-id="2709f-132">Как открыть монитор активности заданий</span><span class="sxs-lookup"><span data-stu-id="2709f-132">To open the Job Activity Monitor</span></span>  
  
-   <span data-ttu-id="2709f-133">В **обозревателе объектов**разверните сервер, раскройте узел **Агент SQL Server**, щелкните правой кнопкой мыши **Монитор активности заданий**, затем выберите пункт **Просмотр активности заданий**.</span><span class="sxs-lookup"><span data-stu-id="2709f-133">In **Object Explorer**, expand your server, expand **SQL Server Agent**, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2709f-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="2709f-134">See Also</span></span>  
 [<span data-ttu-id="2709f-135">Наблюдение за активностью заданий</span><span class="sxs-lookup"><span data-stu-id="2709f-135">Monitor Job Activity</span></span>](monitor-job-activity.md)  
  
  
