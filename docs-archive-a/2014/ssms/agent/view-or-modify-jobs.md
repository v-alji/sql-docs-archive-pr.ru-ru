---
title: Просмотр или изменение заданий | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], modifying
- jobs [SQL Server Agent], viewing
- modifying jobs
- viewing jobs
- SQL Server Agent jobs, viewing
- SQL Server Agent jobs, modifying
- displaying jobs
ms.assetid: 57f649b8-190c-4304-abd7-7ca5297deab7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d0d731d25c20597be3ac84adfacd8973e4a51cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731301"
---
# <a name="view-or-modify-jobs"></a><span data-ttu-id="691ac-102">Просмотр или изменение заданий</span><span class="sxs-lookup"><span data-stu-id="691ac-102">View or Modify Jobs</span></span>
  <span data-ttu-id="691ac-103">Можно просматривать любые созданные задания.</span><span class="sxs-lookup"><span data-stu-id="691ac-103">You can view any job you have created.</span></span> <span data-ttu-id="691ac-104">После запуска задания можно также просматривать его журнал.</span><span class="sxs-lookup"><span data-stu-id="691ac-104">After you have run a job, you can also view its history.</span></span> <span data-ttu-id="691ac-105">Просмотр журнала задания позволяет видеть, где было запущено задание, состояние задания в целом и состояние каждого шага задания.</span><span class="sxs-lookup"><span data-stu-id="691ac-105">Viewing a job's history allows you to see when the job ran, the status of the job as a whole, and the status of each job step in the job.</span></span> <span data-ttu-id="691ac-106">Можно определить, выполнялось ли ранее это задание с ошибками, когда было последнее успешное завершение задания, какой вывод создавался после каждого запуска задания.</span><span class="sxs-lookup"><span data-stu-id="691ac-106">You can see whether the job ever failed in the past, when the job last completed successfully, and what output the job created each time the job ran.</span></span> <span data-ttu-id="691ac-107">Члены предопределенной роли сервера **sysadmin** могут просматривать и изменять любые задания, независимо от того, кто их владелец.</span><span class="sxs-lookup"><span data-stu-id="691ac-107">Members of the **sysadmin** fixed server role can view or modify any job, regardless of the owner.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="691ac-108">Для создания журнала заданий, задание должно быть выполнено хотя бы раз.</span><span class="sxs-lookup"><span data-stu-id="691ac-108">A job must have been executed at least one time for there to be a job history.</span></span> <span data-ttu-id="691ac-109">Можно ограничить общий размер журнала заданий, а также размеры журналов отдельных заданий.</span><span class="sxs-lookup"><span data-stu-id="691ac-109">You can limit the total size of the job history log and the size per job.</span></span>  
  
 <span data-ttu-id="691ac-110">Наконец, можно изменить задание, чтобы оно отвечало новым требованиям.</span><span class="sxs-lookup"><span data-stu-id="691ac-110">Finally, you can modify a job to meet new requirements.</span></span> <span data-ttu-id="691ac-111">Можно менять:</span><span class="sxs-lookup"><span data-stu-id="691ac-111">You can modify:</span></span>  
  
-   <span data-ttu-id="691ac-112">параметры ответа;</span><span class="sxs-lookup"><span data-stu-id="691ac-112">Response options</span></span>  
  
-   <span data-ttu-id="691ac-113">Расписания</span><span class="sxs-lookup"><span data-stu-id="691ac-113">Schedules</span></span>  
  
-   <span data-ttu-id="691ac-114">Шаги задания</span><span class="sxs-lookup"><span data-stu-id="691ac-114">Job steps</span></span>  
  
-   <span data-ttu-id="691ac-115">владельца;</span><span class="sxs-lookup"><span data-stu-id="691ac-115">Ownership</span></span>  
  
-   <span data-ttu-id="691ac-116">категорию задания;</span><span class="sxs-lookup"><span data-stu-id="691ac-116">Job category</span></span>  
  
-   <span data-ttu-id="691ac-117">целевые серверы (только для многосерверных заданий).</span><span class="sxs-lookup"><span data-stu-id="691ac-117">Target servers (multiserver jobs only)</span></span>  
  
 <span data-ttu-id="691ac-118">Чтобы убедиться в том, что изменения многосерверных заданий вступили в силу, отправьте изменения в список загрузки, чтобы целевые серверы могли загрузить обновленное задание.</span><span class="sxs-lookup"><span data-stu-id="691ac-118">To make sure that changes to multiserver jobs take effect, you must post the changes to the download list so that target servers can download the updated job.</span></span> <span data-ttu-id="691ac-119">Чтобы убедиться, что на целевых серверах находятся самые последние определения заданий, отправьте инструкцию INSERT после обновления многосерверного задания:</span><span class="sxs-lookup"><span data-stu-id="691ac-119">To ensure that target servers have the most current job definitions, post an INSERT instruction after you update the multiserver job as follows:</span></span>  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="691ac-120">Дополнительные сведения см. в разделе [sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="691ac-120">For more information, see [sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql).</span></span>  
  
 <span data-ttu-id="691ac-121">Члены предопределенной роли сервера **sysadmin** могут просматривать определение и журнал любого задания, а также изменять любое задание.</span><span class="sxs-lookup"><span data-stu-id="691ac-121">Members of the **sysadmin** fixed server role can view the definition or history of any job, and can modify any job.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="691ac-122">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="691ac-122">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="691ac-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="691ac-123">**Description**</span></span>|<span data-ttu-id="691ac-124">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="691ac-124">**Topic**</span></span>|  
|<span data-ttu-id="691ac-125">Описывает, как просмотреть задания агента [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="691ac-125">Describes how to view [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="691ac-126">View a Job</span><span class="sxs-lookup"><span data-stu-id="691ac-126">View a Job</span></span>](view-a-job.md)|  
|<span data-ttu-id="691ac-127">Описывает, как просматривать журнал заданий агента [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="691ac-127">Describes how to view the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="691ac-128">View the Job History</span><span class="sxs-lookup"><span data-stu-id="691ac-128">View the Job History</span></span>](view-the-job-history.md)|  
|<span data-ttu-id="691ac-129">Описывает, как удалить содержимое журнала заданий агента [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="691ac-129">Describes how to delete the contents of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="691ac-130">Clear the Job History Log</span><span class="sxs-lookup"><span data-stu-id="691ac-130">Clear the Job History Log</span></span>](clear-the-job-history-log.md)|  
|<span data-ttu-id="691ac-131">Описывает установление ограничений на размер журналов заданий агента [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="691ac-131">Describes how to set size limits for [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history logs.</span></span>|[<span data-ttu-id="691ac-132">Resize the Job History Log</span><span class="sxs-lookup"><span data-stu-id="691ac-132">Resize the Job History Log</span></span>](resize-the-job-history-log.md)|  
|<span data-ttu-id="691ac-133">Описывает, как изменить свойства заданий агента [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="691ac-133">Describes how to change the properties of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="691ac-134">Изменение задания</span><span class="sxs-lookup"><span data-stu-id="691ac-134">Modify a Job</span></span>](modify-a-job.md)|  
  
## <a name="see-also"></a><span data-ttu-id="691ac-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="691ac-135">See Also</span></span>  
 [<span data-ttu-id="691ac-136">dbo.sysjobhistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="691ac-136">dbo.sysjobhistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysjobhistory-transact-sql)  
  
  
