---
title: Опрос серверов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- target servers [SQL Server], polling interval
- polling master servers [SQL Server]
- server polling [SQL Server]
- master servers [SQL Server], polling
- polling interval [SQL Server]
ms.assetid: 96f5fd43-3edd-4418-9dd0-4d34e618890e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6370e53083d2cf818e8c8b09752d49e092755a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665755"
---
# <a name="poll-servers"></a><span data-ttu-id="4fccc-102">Опрос серверов</span><span class="sxs-lookup"><span data-stu-id="4fccc-102">Poll Servers</span></span>
  <span data-ttu-id="4fccc-103">При использовании системы многосерверного администрирования целевые серверы периодически связываются с главным сервером для загрузки на него данных о выполненных заданиях и для получения новых заданий.</span><span class="sxs-lookup"><span data-stu-id="4fccc-103">When multiserver administration is implemented, target servers periodically contact the master server to upload information on jobs that have been executed, and download new jobs.</span></span> <span data-ttu-id="4fccc-104">Процесс взаимодействия с главным сервером называется *опросом сервера* и выполняется через равные *интервалы опроса.*</span><span class="sxs-lookup"><span data-stu-id="4fccc-104">The process of contacting the master server is called *server polling,* which takes place at regular *polling intervals.*</span></span>  
  
## <a name="polling-intervals"></a><span data-ttu-id="4fccc-105">Интервалы опроса</span><span class="sxs-lookup"><span data-stu-id="4fccc-105">Polling Intervals</span></span>  
 <span data-ttu-id="4fccc-106">Интервал опроса (равный по умолчанию одной минуте) определяет частоту, с которой целевой сервер будет связываться с главным сервером, чтобы загрузить инструкции и передать на него результаты выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="4fccc-106">The polling interval (one minute by default) controls how frequently the target server connects to the master server to download instructions and upload the results of job execution.</span></span>  
  
 <span data-ttu-id="4fccc-107">Опрашивая главный сервер, целевой сервер считывает назначенные ему операции из таблицы **sysdownloadlist** базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="4fccc-107">When a target server polls the master server, it reads the operations assigned to the target server from the **sysdownloadlist** table in the **msdb** database.</span></span> <span data-ttu-id="4fccc-108">Эти операции контролируют многосерверные задания и различные аспекты работы целевого сервера.</span><span class="sxs-lookup"><span data-stu-id="4fccc-108">These operations control multiserver jobs and various aspects of the behavior of a target server.</span></span> <span data-ttu-id="4fccc-109">Примерами таких операций могут служить удаление задания, вставка задания, запуск задания и обновление интервала опроса, заданного на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="4fccc-109">Examples of operations include deleting a job, inserting a job, starting a job, and updating the polling interval of a target server.</span></span>  
  
 <span data-ttu-id="4fccc-110">Операции можно опубликовать в таблице **sysdownloadlist** двумя способами:</span><span class="sxs-lookup"><span data-stu-id="4fccc-110">Operations are posted to the **sysdownloadlist** table in either of the following ways:</span></span>  
  
-   <span data-ttu-id="4fccc-111">явно, вызвав хранимую процедуру **sp_post_msx_operation** ;</span><span class="sxs-lookup"><span data-stu-id="4fccc-111">Explicitly by using the **sp_post_msx_operation** stored procedure.</span></span>  
  
-   <span data-ttu-id="4fccc-112">неявно, используя другие хранимые процедуры задания.</span><span class="sxs-lookup"><span data-stu-id="4fccc-112">Implicitly by using other job stored procedures.</span></span>  
  
 <span data-ttu-id="4fccc-113">При изменении расписания выполнения многосерверного задания или шагов задания с помощью хранимых процедур задания или при использовании объектов SQL-DMO (SQL Distributed Management Objects) для контроля многосерверных заданий выполните после изменения следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4fccc-113">If you use job stored procedures to modify multiserver job schedules or job steps, or SQL Distributed Management Objects (SQL-DMO) to control multiserver jobs, issue the following command after modifying a multiserver job's steps or schedules:</span></span>  
  
```  
EXECUTE msdb.dbo.sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="4fccc-114">Это обеспечивает синхронизацию целевых серверов с текущим определением задания.</span><span class="sxs-lookup"><span data-stu-id="4fccc-114">Issue this command keeps the target servers synchronized with the current job definition.</span></span>  
  
 <span data-ttu-id="4fccc-115">В следующих ситуациях явно публиковать операции не требуется:</span><span class="sxs-lookup"><span data-stu-id="4fccc-115">You do not have to post operations explicitly if you use the following:</span></span>  
  
-   <span data-ttu-id="4fccc-116">при использовании среды Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для контроля многосерверных заданий;</span><span class="sxs-lookup"><span data-stu-id="4fccc-116">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to control multiserver jobs.</span></span>  
  
-   <span data-ttu-id="4fccc-117">при использовании хранимых процедур заданий, не изменяющих расписания выполнения заданий и шагов заданий.</span><span class="sxs-lookup"><span data-stu-id="4fccc-117">Job stored procedures that do not modify job schedules or job steps.</span></span>  
  
 <span data-ttu-id="4fccc-118">**Принудительный опрос главного сервера целевым сервером**</span><span class="sxs-lookup"><span data-stu-id="4fccc-118">**To force a target server to poll the master server**</span></span>  
  
-   [<span data-ttu-id="4fccc-119">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4fccc-119">SQL Server Management Studio</span></span>](force-a-target-server-to-poll-the-master-server.md)  
  
-   [<span data-ttu-id="4fccc-120">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4fccc-120">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="4fccc-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="4fccc-121">See Also</span></span>  
 [<span data-ttu-id="4fccc-122">Управление событиями</span><span class="sxs-lookup"><span data-stu-id="4fccc-122">Manage Events</span></span>](manage-events.md)  
  
  
