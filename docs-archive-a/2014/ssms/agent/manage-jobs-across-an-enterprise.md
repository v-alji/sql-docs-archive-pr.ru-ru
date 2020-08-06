---
title: Управление заданиями в масштабе предприятия | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiserver job management [SQL Server]
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
- target servers [SQL Server], job changes
ms.assetid: 4fe7f6c6-f89b-4430-979c-4994a5dcf7a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 385435302b2e987c86afb17eaebf90e91bc93e56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658063"
---
# <a name="manage-jobs-across-an-enterprise"></a><span data-ttu-id="4b428-102">Управление заданиями в масштабе предприятия</span><span class="sxs-lookup"><span data-stu-id="4b428-102">Manage Jobs Across an Enterprise</span></span>
  <span data-ttu-id="4b428-103">При внесении изменений в определения многосерверных заданий вне [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , необходимо опубликовать изменения в списке загрузки, чтобы целевые серверы могли скачать обновленное задание еще раз.</span><span class="sxs-lookup"><span data-stu-id="4b428-103">If you make changes to multiserver job definitions outside [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must post the changes to the download list so that target servers can download the updated job again.</span></span> <span data-ttu-id="4b428-104">Чтобы убедиться в том, что целевые серверы получили текущие определения заданий, после обновления многосерверной задачи разместите инструкцию INSERT следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4b428-104">To ensure that target servers have current job definitions, post an INSERT instruction after you update the multiserver job, as follows:</span></span>  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="4b428-105">Чтобы уведомить целевой сервер об изменении многосерверной задачи, необходимо выполнить указанную выше команду после использования одной из этих процедур:</span><span class="sxs-lookup"><span data-stu-id="4b428-105">To notify target servers that a multiserver job has been modified, you must invoke the preceding command after using any of the following procedures:</span></span>  
  
-   [<span data-ttu-id="4b428-106">sp_add_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4b428-106">sp_add_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="4b428-107">sp_update_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4b428-107">sp_update_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql)  
  
-   [<span data-ttu-id="4b428-108">sp_delete_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4b428-108">sp_delete_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql)  
  
-   [<span data-ttu-id="4b428-109">sp_attach_schedule (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4b428-109">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="4b428-110">sp_detach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4b428-110">sp_detach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-schedule-transact-sql)  
  
    > [!NOTE]  
    >  <span data-ttu-id="4b428-111">Необязательно вызывать процедуру **sp_post_msx_operation** после вызова **sp_update_job** или **sp_delete_job**, поскольку эти хранимые процедуры автоматически размещают необходимые изменения в списке скачивания.</span><span class="sxs-lookup"><span data-stu-id="4b428-111">It is not necessary to call **sp_post_msx_operation** after you call **sp_update_job** or **sp_delete_job**, because these stored procedures post the required changes to the download list automatically.</span></span>  
  
 <span data-ttu-id="4b428-112">Типичные задачи для управления задачами в масштабах предприятия:</span><span class="sxs-lookup"><span data-stu-id="4b428-112">The following are common tasks for managing jobs across an enterprise:</span></span>  
  
 <span data-ttu-id="4b428-113">**Проверка состояния целевого сервера**</span><span class="sxs-lookup"><span data-stu-id="4b428-113">**To check the status of a target server**</span></span>  
  
-   [<span data-ttu-id="4b428-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b428-114">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-targetserver-transact-sql)  
  
-   [<span data-ttu-id="4b428-115">Управляющие объекты SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="4b428-115">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="4b428-116">**Изменение целевого сервера для задания**</span><span class="sxs-lookup"><span data-stu-id="4b428-116">**To change the target servers for a job**</span></span>  
  
-   [<span data-ttu-id="4b428-117">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b428-117">SQL Server Management Studio</span></span>](modify-the-target-servers-for-a-job.md)  
  
-   [<span data-ttu-id="4b428-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b428-118">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
-   [<span data-ttu-id="4b428-119">Управляющие объекты SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="4b428-119">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="4b428-120">**Изменение местоположения целевого сервера**</span><span class="sxs-lookup"><span data-stu-id="4b428-120">**To change the location of a target server**</span></span>  
  
-   [<span data-ttu-id="4b428-121">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b428-121">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="4b428-122">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b428-122">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)  
  
-   [<span data-ttu-id="4b428-123">Управляющие объекты SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="4b428-123">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="4b428-124">**Синхронизация часов целевых серверов**</span><span class="sxs-lookup"><span data-stu-id="4b428-124">**To synchronize target server clocks**</span></span>  
  
-   [<span data-ttu-id="4b428-125">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b428-125">SQL Server Management Studio</span></span>](synchronize-target-server-clocks-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="4b428-126">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b428-126">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql)  
  
 <span data-ttu-id="4b428-127">**Принудительный опрос главного сервера целевым сервером**</span><span class="sxs-lookup"><span data-stu-id="4b428-127">**To force a target server to poll the master server**</span></span>  
  
-   [<span data-ttu-id="4b428-128">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4b428-128">SQL Server Management Studio</span></span>](force-a-target-server-to-poll-the-master-server.md)  
  
-   [<span data-ttu-id="4b428-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4b428-129">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="4b428-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b428-130">See Also</span></span>  
 [<span data-ttu-id="4b428-131">Управление событиями</span><span class="sxs-lookup"><span data-stu-id="4b428-131">Manage Events</span></span>](manage-events.md)  
  
  
