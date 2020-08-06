---
title: Удаление заданий | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- delete jobs
ms.assetid: bffb915e-bc84-4417-aa35-183243ca3312
author: stevestein
ms.author: sstein
ms.openlocfilehash: f66387a1334f91c29b8edddad293d76064430b39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737457"
---
# <a name="delete-jobs"></a><span data-ttu-id="cb5c3-102">удаление заданий</span><span class="sxs-lookup"><span data-stu-id="cb5c3-102">Delete Jobs</span></span>
  <span data-ttu-id="cb5c3-103">Задание — это определенная последовательность действий, выполняемых агентом SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cb5c3-103">A job is a specified series of operations performed sequentially by SQL Server Agent.</span></span> <span data-ttu-id="cb5c3-104">По умолчанию после завершения выполнения задания не удаляются.</span><span class="sxs-lookup"><span data-stu-id="cb5c3-104">By default, jobs are not deleted when execution finishes.</span></span> <span data-ttu-id="cb5c3-105">Можно удалить одно или несколько заданий агента [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , независимо от успешности завершения задания.</span><span class="sxs-lookup"><span data-stu-id="cb5c3-105">You can delete one or more [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs regardless of success or failure of the job.</span></span> <span data-ttu-id="cb5c3-106">В агенте [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] также можно настроить автоматическое удаление заданий в случае их успешного выполнения, сбоя или завершения.</span><span class="sxs-lookup"><span data-stu-id="cb5c3-106">You can also configure [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically delete jobs when they succeed, fail, or complete.</span></span>  
  
 <span data-ttu-id="cb5c3-107">По умолчанию члены предопределенной роли сервера **sysadmin** могут выполнять [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) системную хранимую процедуру для удаления задания.</span><span class="sxs-lookup"><span data-stu-id="cb5c3-107">By default, members of the **sysadmin** fixed server role can execute the [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) system stored procedure to delete a job.</span></span> <span data-ttu-id="cb5c3-108">Другим пользователям должна быть предоставлена одна из следующих предопределенных ролей базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в базе данных **msdb** :</span><span class="sxs-lookup"><span data-stu-id="cb5c3-108">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="cb5c3-109">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="cb5c3-109">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="cb5c3-110">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="cb5c3-110">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="cb5c3-111">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="cb5c3-111">**SQLAgentOperatorRole**</span></span>  
  
 <span data-ttu-id="cb5c3-112">Дополнительные сведения о разрешениях этих ролей см. в разделе [Предопределенные роли базы данных агента SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cb5c3-112">For details about the permissions of these roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="cb5c3-113">Члены предопределенной роли сервера **sysadmin** с помощью процедуры **sp_delete_job** могут удалить любое задание.</span><span class="sxs-lookup"><span data-stu-id="cb5c3-113">Members of the **sysadmin** fixed server role can execute **sp_delete_job** to delete any job.</span></span> <span data-ttu-id="cb5c3-114">Пользователь, который не является членом предопределенной роли сервера **sysadmin** , может удалять только задания, принадлежащие этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="cb5c3-114">A user that is not a member of the **sysadmin** fixed server role can only delete jobs owned by that user.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="cb5c3-115">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="cb5c3-115">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb5c3-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="cb5c3-116">**Description**</span></span>|<span data-ttu-id="cb5c3-117">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="cb5c3-117">**Topic**</span></span>|  
|<span data-ttu-id="cb5c3-118">Описывает, как удалить одно или несколько заданий агента [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cb5c3-118">Describes how to delete one or more [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="cb5c3-119">Удаление одного или нескольких заданий</span><span class="sxs-lookup"><span data-stu-id="cb5c3-119">Delete One or More Jobs</span></span>](delete-one-or-more-jobs.md)|  
|<span data-ttu-id="cb5c3-120">Описывает, как настроить автоматическое удаление заданий агента [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в случае их успешного выполнения, сбоя или завершения.</span><span class="sxs-lookup"><span data-stu-id="cb5c3-120">Describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically delete jobs when they succeed, fail, or complete.</span></span>|[<span data-ttu-id="cb5c3-121">Автоматическое удаление задания</span><span class="sxs-lookup"><span data-stu-id="cb5c3-121">Automatically Delete a Job</span></span>](automatically-delete-a-job.md)|  
  
  
