---
title: Создание заданий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], creating
- SQL Server Agent jobs, creating
ms.assetid: 465fb7fc-7622-4252-a178-ea51691c935b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 706b9348eed5b190f99543a74e7019dc1bde5978
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731369"
---
# <a name="create-jobs"></a><span data-ttu-id="800e7-102">Создание заданий</span><span class="sxs-lookup"><span data-stu-id="800e7-102">Create Jobs</span></span>
  <span data-ttu-id="800e7-103">Задание — это определенная цепочка действий, последовательно выполняемых агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="800e7-103">A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="800e7-104">Задание может выполнять широкий диапазон действий, например запуск скриптов [!INCLUDE[tsql](../../includes/tsql-md.md)] , приложений командной строки, скриптов Microsoft ActiveX, пакетов Integration Services, команд и запросов Analysis Services и задач репликации.</span><span class="sxs-lookup"><span data-stu-id="800e7-104">A job can perform a wide range of activities, including running [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, command prompt applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks.</span></span> <span data-ttu-id="800e7-105">Задания могут запускать повторяющиеся или запланированные задачи, они могут автоматически уведомлять пользователей о состоянии задания, формируя предупреждения и тем самым значительно упрощают администрирование [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="800e7-105">Jobs can run repetitive or schedulable tasks, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administration.</span></span>  
  
 <span data-ttu-id="800e7-106">Чтобы создать задание, пользователь должен быть членом одной из предопределенных ролей базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="800e7-106">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="800e7-107">Задание может быть изменено его владельцем или членом роли **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="800e7-107">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="800e7-108">Члены роли **sysadmin** могут предоставлять права владения заданием другим пользователям, а также запускать любое задание, независимо от того, кто является его владельцем.</span><span class="sxs-lookup"><span data-stu-id="800e7-108">Members of the **sysadmin** role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span> <span data-ttu-id="800e7-109">Дополнительные сведения о предопределенных ролях базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Предопределенные роли базы данных агента SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="800e7-109">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="800e7-110">Задания могут выполняться на локальном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или быть распределены по нескольким экземплярам, работающим на предприятии.</span><span class="sxs-lookup"><span data-stu-id="800e7-110">Jobs can be written to run on the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or on multiple instances across an enterprise.</span></span> <span data-ttu-id="800e7-111">Для запуска заданий на нескольких серверах необходимо установить, по крайней мере, один главный сервер и один или несколько целевых.</span><span class="sxs-lookup"><span data-stu-id="800e7-111">To run jobs on multiple servers, you must set up at least one master server and one or more target servers.</span></span> <span data-ttu-id="800e7-112">Дополнительные сведения о главных и целевых серверах см. в статье [Автоматизация администрирования в масштабах предприятия](automated-administration-across-an-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="800e7-112">For more information about master and target servers, see [Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md)</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="800e7-113">Агент записывает сведения о задании и шагах задания в журнал заданий.</span><span class="sxs-lookup"><span data-stu-id="800e7-113">Agent records job and job step information in the job history.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="800e7-114">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="800e7-114">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="800e7-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="800e7-115">**Description**</span></span>|<span data-ttu-id="800e7-116">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="800e7-116">**Topic**</span></span>|  
|<span data-ttu-id="800e7-117">Описывает создание задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="800e7-117">Describes how to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="800e7-118">Создание задания</span><span class="sxs-lookup"><span data-stu-id="800e7-118">Create a Job</span></span>](create-a-job.md)|  
|<span data-ttu-id="800e7-119">Описывает переназначение владения заданиями агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="800e7-119">Describes how to reassign ownership of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to another user.</span></span>|[<span data-ttu-id="800e7-120">Give Others Ownership of a Job</span><span class="sxs-lookup"><span data-stu-id="800e7-120">Give Others Ownership of a Job</span></span>](give-others-ownership-of-a-job.md)|  
|<span data-ttu-id="800e7-121">Описывает настройку журнала заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="800e7-121">Describes how to set up the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="800e7-122">Set Up the Job History Log</span><span class="sxs-lookup"><span data-stu-id="800e7-122">Set Up the Job History Log</span></span>](set-up-the-job-history-log.md)|  
  
## <a name="see-also"></a><span data-ttu-id="800e7-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="800e7-123">See Also</span></span>  
 <span data-ttu-id="800e7-124">[Управление шагами задания](manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="800e7-124">[Manage Job Steps](manage-job-steps.md) </span></span>  
 <span data-ttu-id="800e7-125">[Автоматизация администрирования в масштабах предприятия](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="800e7-125">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 <span data-ttu-id="800e7-126">[Создание и присоединение расписаний к заданиям](create-and-attach-schedules-to-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="800e7-126">[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md) </span></span>  
 <span data-ttu-id="800e7-127">[Запуск заданий](run-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="800e7-127">[Run Jobs](run-jobs.md) </span></span>  
 [<span data-ttu-id="800e7-128">Просмотр или изменение заданий</span><span class="sxs-lookup"><span data-stu-id="800e7-128">View or Modify Jobs</span></span>](view-or-modify-jobs.md)  
  
  
