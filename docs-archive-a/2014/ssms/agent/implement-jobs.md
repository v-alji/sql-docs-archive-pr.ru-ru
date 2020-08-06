---
title: Реализация заданий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent]
- SQL Server Agent jobs
- SQL Server Agent jobs, about jobs
- jobs [SQL Server Agent], about jobs
ms.assetid: 69e06724-25c7-4fb3-8a5b-3d4596f21756
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1925b3113db8d7c57ac4344958c0247763cfd1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654719"
---
# <a name="implement-jobs"></a><span data-ttu-id="c6b9b-102">Реализация заданий</span><span class="sxs-lookup"><span data-stu-id="c6b9b-102">Implement Jobs</span></span>
  <span data-ttu-id="c6b9b-103">Задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] позволяют автоматизировать задачи администрирования и сделать их выполнение более эффективным.</span><span class="sxs-lookup"><span data-stu-id="c6b9b-103">You can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to automate routine administrative tasks and run them on a recurring basis, making administration more efficient.</span></span>  
  
 <span data-ttu-id="c6b9b-104">Задание — это определенная цепочка действий, последовательно выполняемых агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6b9b-104">A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="c6b9b-105">Задание может выполнять различные действия, включая запуск скриптов [!INCLUDE[tsql](../../includes/tsql-md.md)] , приложений командной строки, скриптов Microsoft ActiveX, пакетов служб Integration Services, запросов и команд служб Analysis Services или задач репликации.</span><span class="sxs-lookup"><span data-stu-id="c6b9b-105">A job can perform a wide range of activities, including running [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, command-line applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks.</span></span> <span data-ttu-id="c6b9b-106">Задание может выполнять повторяющиеся задачи или задачи, запуск которых определяется расписанием; кроме того, оно может автоматически уведомлять пользователей о своем состоянии, значительно упрощая администрирование сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6b9b-106">Jobs can run repetitive tasks or those that can be scheduled, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administration.</span></span>  
  
 <span data-ttu-id="c6b9b-107">Задания можно запускать вручную, по расписанию или в ответ на оповещения.</span><span class="sxs-lookup"><span data-stu-id="c6b9b-107">You can run a job manually, or you can configure it to run according to a schedule or in response to alerts.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c6b9b-108">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="c6b9b-108">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c6b9b-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c6b9b-109">**Description**</span></span>|<span data-ttu-id="c6b9b-110">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="c6b9b-110">**Topic**</span></span>|  
|<span data-ttu-id="c6b9b-111">Содержит сведения о создании заданий и назначении владельца.</span><span class="sxs-lookup"><span data-stu-id="c6b9b-111">Contains information about creating jobs and assigning ownership.</span></span>|[<span data-ttu-id="c6b9b-112">Создание заданий</span><span class="sxs-lookup"><span data-stu-id="c6b9b-112">Create Jobs</span></span>](create-jobs.md)|  
|<span data-ttu-id="c6b9b-113">Содержит сведения об организации заданий по категориям.</span><span class="sxs-lookup"><span data-stu-id="c6b9b-113">Contains information about organizing jobs into categories.</span></span>|[<span data-ttu-id="c6b9b-114">упорядочивание заданий</span><span class="sxs-lookup"><span data-stu-id="c6b9b-114">Organize Jobs</span></span>](organize-jobs.md)|  
|<span data-ttu-id="c6b9b-115">Содержит сведения о различных видах шагов заданий, их создании и управлении ими.</span><span class="sxs-lookup"><span data-stu-id="c6b9b-115">Contains information about the different kinds of job steps you can create and how to manage them.</span></span>|[<span data-ttu-id="c6b9b-116">Управление шагами задания</span><span class="sxs-lookup"><span data-stu-id="c6b9b-116">Manage Job Steps</span></span>](manage-job-steps.md)|  
|<span data-ttu-id="c6b9b-117">Содержит сведения о том, как определить время запуска и частоту выполнения заданий.</span><span class="sxs-lookup"><span data-stu-id="c6b9b-117">Contains information about how to define when jobs start running and how often they should run.</span></span>|[<span data-ttu-id="c6b9b-118">Создание и присоединение расписаний к заданиям</span><span class="sxs-lookup"><span data-stu-id="c6b9b-118">Create and Attach Schedules to Jobs</span></span>](create-and-attach-schedules-to-jobs.md)|  
|<span data-ttu-id="c6b9b-119">Содержит сведения о заданиях, запускаемых вручную (не по расписанию).</span><span class="sxs-lookup"><span data-stu-id="c6b9b-119">Contains information about manually running jobs (without a schedule).</span></span>|[<span data-ttu-id="c6b9b-120">Запуск заданий</span><span class="sxs-lookup"><span data-stu-id="c6b9b-120">Run Jobs</span></span>](run-jobs.md)|  
|<span data-ttu-id="c6b9b-121">Содержит сведения о том, как настроить реакцию агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на задания.</span><span class="sxs-lookup"><span data-stu-id="c6b9b-121">Contains information about how you can configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to respond to jobs.</span></span> <span data-ttu-id="c6b9b-122">Например агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может уведомлять администраторов о завершении заданий.</span><span class="sxs-lookup"><span data-stu-id="c6b9b-122">For example, you can configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to notify administrators when jobs are finished.</span></span>|[<span data-ttu-id="c6b9b-123">Определение ответов заданий</span><span class="sxs-lookup"><span data-stu-id="c6b9b-123">Specify Job Responses</span></span>](specify-job-responses.md)|  
|<span data-ttu-id="c6b9b-124">Содержит сведения о том, как просмотреть или изменить существующие задания и просмотреть историю их выполнения.</span><span class="sxs-lookup"><span data-stu-id="c6b9b-124">Contains information about how to view existing jobs, their history once executes, and how to modify them.</span></span>|[<span data-ttu-id="c6b9b-125">Просмотр или изменение заданий</span><span class="sxs-lookup"><span data-stu-id="c6b9b-125">View or Modify Jobs</span></span>](view-or-modify-jobs.md)|  
|<span data-ttu-id="c6b9b-126">Содержит сведения об удалении заданий.</span><span class="sxs-lookup"><span data-stu-id="c6b9b-126">Contains information about how to delete jobs.</span></span>|[<span data-ttu-id="c6b9b-127">удаление заданий</span><span class="sxs-lookup"><span data-stu-id="c6b9b-127">Delete Jobs</span></span>](delete-jobs.md)|  
  
## <a name="see-also"></a><span data-ttu-id="c6b9b-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="c6b9b-128">See Also</span></span>  
 [<span data-ttu-id="c6b9b-129">Обеспечение безопасности агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6b9b-129">Implement SQL Server Agent Security</span></span>](implement-sql-server-agent-security.md)  
  
  
