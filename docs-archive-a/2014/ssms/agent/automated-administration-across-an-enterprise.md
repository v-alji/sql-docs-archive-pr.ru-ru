---
title: Автоматизированное администрирование в организации | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- enterprise automatic administration [SQL Server]
- multiserver administration [SQL Server]
- SQL Server Agent jobs, multiserver administration
- jobs [SQL Server Agent], multiserver administration
- master servers [SQL Server], about master servers
- target servers [SQL Server], about target servers
- master servers [SQL Server]
- multiple instances of SQL Server
- target servers [SQL Server]
ms.assetid: 44d8365b-42bd-4955-b5b2-74a8a9f4a75f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8df3e34c2c70c81f9710ade0d6855446b930fb50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665769"
---
# <a name="automated-administration-across-an-enterprise"></a><span data-ttu-id="534ca-102">Автоматизация администрирования в масштабах предприятия</span><span class="sxs-lookup"><span data-stu-id="534ca-102">Automated Administration Across an Enterprise</span></span>
  <span data-ttu-id="534ca-103"> Автоматическое администрирование нескольких экземпляров [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] называется *администрированием нескольких серверов*.</span><span class="sxs-lookup"><span data-stu-id="534ca-103">Automating administration across multiple instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is called *multiserver administration*.</span></span> <span data-ttu-id="534ca-104">Оно предназначено для выполнения следующих задач.</span><span class="sxs-lookup"><span data-stu-id="534ca-104">Use multiserver administration to do the following:</span></span>  
  
-   <span data-ttu-id="534ca-105">Управления двумя или несколькими серверами.</span><span class="sxs-lookup"><span data-stu-id="534ca-105">Manage two or more servers.</span></span>  
  
-   <span data-ttu-id="534ca-106">Планирования потоков данных между серверами предприятия для организации хранилищ данных.</span><span class="sxs-lookup"><span data-stu-id="534ca-106">Schedule information flows between enterprise servers for data warehousing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="534ca-107">В рамках [!INCLUDE[msCoName](../../includes/msconame-md.md)] текущих усилий по уменьшению совокупной стоимости владения [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] появились две функции: метод управления серверами, называемый управлением на основе политик, и многосерверные запросы, использующие серверы конфигурации и группы серверов.</span><span class="sxs-lookup"><span data-stu-id="534ca-107">As part of [!INCLUDE[msCoName](../../includes/msconame-md.md)] ongoing efforts to reduce the total cost of ownership, [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduced two features:  a method of managing servers that is called Policy-Based Management, and multiserver queries that use configuration servers and server groups.</span></span> <span data-ttu-id="534ca-108">Эти функции могут использоваться вместо или совместно с некоторыми функциями, описанными в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="534ca-108">These features can be used with, or instead of, some of the features that are described in this topic.</span></span> <span data-ttu-id="534ca-109">Дополнительные сведения см. в статьях [Администрирование серверов с помощью управления на основе политик](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) и [Администрирование нескольких серверов с помощью центральных серверов управления](../../relational-databases/administer-multiple-servers-using-central-management-servers.md).</span><span class="sxs-lookup"><span data-stu-id="534ca-109">For more information, see [Administer Servers by Using Policy-Based Management](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) and [Administer Multiple Servers Using Central Management Servers](../../relational-databases/administer-multiple-servers-using-central-management-servers.md).</span></span>  
  
 <span data-ttu-id="534ca-110">Чтобы воспользоваться преимуществами администрирования нескольких серверов, необходимо иметь, по меньшей мере, один главный сервер и один целевой.</span><span class="sxs-lookup"><span data-stu-id="534ca-110">To take advantage of multiserver administration, you must have at least one master server and at least one target server.</span></span> <span data-ttu-id="534ca-111">Главный сервер распределяет задания целевым серверам и получает от них события.</span><span class="sxs-lookup"><span data-stu-id="534ca-111">A master server distributes jobs to, and receives events from, target servers.</span></span> <span data-ttu-id="534ca-112">На главном сервере также хранится центральная копия определений заданий, выполняющихся на целевых серверах.</span><span class="sxs-lookup"><span data-stu-id="534ca-112">A master server also stores the central copy of job definitions for jobs that are run on target servers.</span></span> <span data-ttu-id="534ca-113">Целевые серверы периодически подключаются к главному серверу для обновления расписаний своих заданий.</span><span class="sxs-lookup"><span data-stu-id="534ca-113">Target servers connect periodically to the master server to update their schedule of jobs.</span></span> <span data-ttu-id="534ca-114">Если на главном сервере имеется новое задание, то целевой сервер получает его.</span><span class="sxs-lookup"><span data-stu-id="534ca-114">If a new job exists on the master server, the target server downloads the job.</span></span> <span data-ttu-id="534ca-115">После завершения задания целевой сервер подключается к главному серверу и сообщает о состоянии его завершения.</span><span class="sxs-lookup"><span data-stu-id="534ca-115">After the target server completes the job, it reconnects to the master server and reports the status of the job.</span></span>  
  
 <span data-ttu-id="534ca-116">На следующем рисунке показана связь между главным и целевыми серверами.</span><span class="sxs-lookup"><span data-stu-id="534ca-116">The following illustration shows the relationship between master and target servers:</span></span>  
  
 <span data-ttu-id="534ca-117">![Настройка администрирования нескольких серверов](../../database-engine/media/multisvr.gif "Настройка администрирования нескольких серверов")</span><span class="sxs-lookup"><span data-stu-id="534ca-117">![Multiserver administration configuration](../../database-engine/media/multisvr.gif "Multiserver administration configuration")</span></span>  
  
 <span data-ttu-id="534ca-118">При администрировании серверов подразделений крупного предприятия можно определить:</span><span class="sxs-lookup"><span data-stu-id="534ca-118">If you administer departmental servers across a large corporation, you can define the following:</span></span>  
  
-   <span data-ttu-id="534ca-119">единое задание резервного копирования, разбитое на шаги;</span><span class="sxs-lookup"><span data-stu-id="534ca-119">One backup job with job steps.</span></span>  
  
-   <span data-ttu-id="534ca-120">операторов, которые будут уведомлены в случае сбоя при резервном копировании;</span><span class="sxs-lookup"><span data-stu-id="534ca-120">Operators to notify in case of backup failure.</span></span>  
  
-   <span data-ttu-id="534ca-121">расписание выполнения для этого задания.</span><span class="sxs-lookup"><span data-stu-id="534ca-121">An execution schedule for the backup job.</span></span>  
  
 <span data-ttu-id="534ca-122">Один раз сохраните это задание резервного копирования на сервере, а затем прикрепите серверы подразделений как целевые.</span><span class="sxs-lookup"><span data-stu-id="534ca-122">Write this backup job one time on the master server and then enlist each departmental server as a target server.</span></span> <span data-ttu-id="534ca-123">С этого момента все серверы подразделений выполняют одно и то же задание, хотя оно было определено всего один раз.</span><span class="sxs-lookup"><span data-stu-id="534ca-123">From the time of their enlistment, all the departmental servers run the same backup job, yet you defined the job only once.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="534ca-124">Функции администрирования нескольких серверов предназначены для членов роли sysadmin.</span><span class="sxs-lookup"><span data-stu-id="534ca-124">Multiserver administration features are intended for members of the sysadmin role.</span></span> <span data-ttu-id="534ca-125">Тем не менее член роли sysadmin на целевом сервере не может изменить операции, которые главный сервер выполняет на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="534ca-125">However, a member of the sysadmin role on the target server cannot edit the operations that are performed on the target server by the master server.</span></span> <span data-ttu-id="534ca-126">Такая мера предосторожности предохраняет шаги задания от случайного удаления, а операции на целевом сервере — от постороннего вмешательства.</span><span class="sxs-lookup"><span data-stu-id="534ca-126">This security measure prevents job steps from being accidentally deleted and operations on the target server from being interrupted.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="534ca-127">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="534ca-127">In This Section</span></span>  
 [<span data-ttu-id="534ca-128">Создание многосерверной среды</span><span class="sxs-lookup"><span data-stu-id="534ca-128">Create a Multiserver Environment</span></span>](create-a-multiserver-environment.md)  
 <span data-ttu-id="534ca-129">Содержит сведения о создании главного и целевых серверов и управлении ими.</span><span class="sxs-lookup"><span data-stu-id="534ca-129">Contains information about how to create and manage master and target servers.</span></span>  
  
 [<span data-ttu-id="534ca-130">Выбор правильной учетной записи службы агента SQL Server для многосерверной среды</span><span class="sxs-lookup"><span data-stu-id="534ca-130">Choose the Right SQL Server Agent Service Account for Multiserver Environments</span></span>](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md)  
 <span data-ttu-id="534ca-131">Содержит сведения о влиянии использования неадминистративных учетных записей Windows или учетной записи Local System службы агента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] на многосерверное окружение.</span><span class="sxs-lookup"><span data-stu-id="534ca-131">Contains information about how using nonadministrative Windows accounts or the Local System account for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service can affect multiserver environments.</span></span>  
  
 [<span data-ttu-id="534ca-132">Установка параметров шифрования на целевых серверах</span><span class="sxs-lookup"><span data-stu-id="534ca-132">Set Encryption Options on Target Servers</span></span>](set-encryption-options-on-target-servers.md)  
 <span data-ttu-id="534ca-133">Содержит сведения о настройке подраздела реестра MsxEncryptChannelOptions агента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] на целевых серверах.</span><span class="sxs-lookup"><span data-stu-id="534ca-133">Contains information about setting the MsxEncryptChannelOptions [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent registry subkey on target servers.</span></span>  
  
 [<span data-ttu-id="534ca-134">Управление заданиями в масштабе предприятия</span><span class="sxs-lookup"><span data-stu-id="534ca-134">Manage Jobs Across an Enterprise</span></span>](manage-jobs-across-an-enterprise.md)  
 <span data-ttu-id="534ca-135">Содержит сведения о проверке состояния задания, изменения для него целевых серверов, синхронизации времени на целевых серверах и опросе главных серверов о состоянии текущих заданий.</span><span class="sxs-lookup"><span data-stu-id="534ca-135">Contains information about checking job status, changing target servers for jobs, synchronizing target server clocks, and polling master servers for their current job status.</span></span>  
  
 [<span data-ttu-id="534ca-136">Устранение неполадок, связанных с многосерверными заданиями, использующими учетные записи-посредники</span><span class="sxs-lookup"><span data-stu-id="534ca-136">Troubleshoot Multiserver Jobs That Use Proxies</span></span>](troubleshoot-multiserver-jobs-that-use-proxies.md)  
 <span data-ttu-id="534ca-137">Содержит сведения об устранении неполадок многосерверных заданий, которые используют неверные учетные записи-посредники.</span><span class="sxs-lookup"><span data-stu-id="534ca-137">Contains information about troubleshooting multiserver jobs that use proxies which fail.</span></span>  
  
 [<span data-ttu-id="534ca-138">Опрос серверов</span><span class="sxs-lookup"><span data-stu-id="534ca-138">Poll Servers</span></span>](poll-servers.md)  
 <span data-ttu-id="534ca-139">Содержит сведения о том, как явно или неявно заставить целевые серверы синхронизировать сведения о заданиях с главным сервером.</span><span class="sxs-lookup"><span data-stu-id="534ca-139">Contains information about how to implicitly and explicitly make target servers poll master servers to synchronize jobs information.</span></span>  
  
 [<span data-ttu-id="534ca-140">Управление событиями</span><span class="sxs-lookup"><span data-stu-id="534ca-140">Manage Events</span></span>](manage-events.md)  
 <span data-ttu-id="534ca-141">Содержит сведения о пересылке событий от целевых серверов к главному.</span><span class="sxs-lookup"><span data-stu-id="534ca-141">Contains information about event forwarding from target servers to master servers.</span></span>  
  
 [<span data-ttu-id="534ca-142">Настройка автоматизированного администрирования в организации</span><span class="sxs-lookup"><span data-stu-id="534ca-142">Tune Automated Administration Across an Enterprise</span></span>](tune-automated-administration-across-an-enterprise.md)  
 <span data-ttu-id="534ca-143">Содержит сведения о том, как автоматизированное администрирование в многосерверном окружении использует функции самонастройки [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="534ca-143">Contains information about how automated administration in a multiserver environment takes advantage of the self-tuning features of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534ca-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="534ca-144">See Also</span></span>  
 <span data-ttu-id="534ca-145">[Обратная совместимость компонента ядра СУБД SQL Server](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="534ca-145">[SQL Server Database Engine Backward Compatibility](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span></span>  
 <span data-ttu-id="534ca-146">[Регистрация серверов](../register-servers/register-servers.md) </span><span class="sxs-lookup"><span data-stu-id="534ca-146">[Register Servers](../register-servers/register-servers.md) </span></span>  
 <span data-ttu-id="534ca-147">[sp_add_targetservergroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-targetservergroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="534ca-147">[sp_add_targetservergroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-targetservergroup-transact-sql) </span></span>  
 <span data-ttu-id="534ca-148">[sp_delete_targetserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-targetserver-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="534ca-148">[sp_delete_targetserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-targetserver-transact-sql) </span></span>  
 <span data-ttu-id="534ca-149">[sp_delete_targetservergroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-targetservergroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="534ca-149">[sp_delete_targetservergroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-targetservergroup-transact-sql) </span></span>  
 <span data-ttu-id="534ca-150">[sp_help_downloadlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-downloadlist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="534ca-150">[sp_help_downloadlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-downloadlist-transact-sql) </span></span>  
 <span data-ttu-id="534ca-151">[sp_help_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobserver-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="534ca-151">[sp_help_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobserver-transact-sql) </span></span>  
 <span data-ttu-id="534ca-152">[sp_help_targetservergroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-targetservergroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="534ca-152">[sp_help_targetservergroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-targetservergroup-transact-sql) </span></span>  
 <span data-ttu-id="534ca-153">[sp_resync_targetserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="534ca-153">[sp_resync_targetserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql) </span></span>  
 <span data-ttu-id="534ca-154">[sp_update_targetservergroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-targetservergroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="534ca-154">[sp_update_targetservergroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-targetservergroup-transact-sql) </span></span>  
 <span data-ttu-id="534ca-155">[dbo.sysжобсерверс &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-sysjobservers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="534ca-155">[dbo.sysjobservers &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-sysjobservers-transact-sql) </span></span>  
 <span data-ttu-id="534ca-156">[sys.sysимена входа &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslogins-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="534ca-156">[sys.syslogins &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslogins-transact-sql) </span></span>  
 [<span data-ttu-id="534ca-157">dbo.sysтаржетсерверс &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="534ca-157">dbo.systargetservers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-systargetservers-transact-sql)  
  
  
