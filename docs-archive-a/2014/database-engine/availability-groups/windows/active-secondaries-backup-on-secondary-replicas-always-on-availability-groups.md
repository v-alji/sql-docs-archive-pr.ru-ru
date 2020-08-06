---
title: 'Активные вторичные реплики: резервное копирование во вторичных копиях (Always On групп доступности) | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- backup priority
- backup on secondary replicas
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], backup on secondary replicas
- active secondary replicas [SQL Server], backup on
- automated backup preference
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: 82afe51b-71d1-4d5b-b20a-b57afc002405
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0cf899cdbeb1ae4ede6c9196b8eb93a9d9e54f05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733169"
---
# <a name="active-secondaries-backup-on-secondary-replicas-always-on-availability-groups"></a><span data-ttu-id="7679a-102">Активные вторичные реплики, резервное копирование во вторичных репликах (группы доступности AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="7679a-102">Active Secondaries: Backup on Secondary Replicas (Always On Availability Groups)</span></span>
  <span data-ttu-id="7679a-103">Функции [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] по поддержке вторичных реплик обеспечивают выполнение операций резервного копирования для вторичных реплик.</span><span class="sxs-lookup"><span data-stu-id="7679a-103">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] active secondary capabilities include support for performing backup operations on secondary replicas.</span></span> <span data-ttu-id="7679a-104">Операции резервного копирования могут оказывать значительную нагрузку на систему ввода-вывода и ЦП (при использовании сжатия резервных копий).</span><span class="sxs-lookup"><span data-stu-id="7679a-104">Backup operations can put significant strain on I/O and CPU (with backup compression).</span></span> <span data-ttu-id="7679a-105">Перенос резервного копирования в синхронизированную или синхронизирующуюся вторичную реплику позволяет использовать ресурсы на экземпляре сервера, где размещается первичная реплика, для рабочей нагрузки первого уровня.</span><span class="sxs-lookup"><span data-stu-id="7679a-105">Offloading backups to a synchronized or synchronizing secondary replica allows you to use the resources on server instance that hosts the primary replica for your tier-1 workloads.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7679a-106">Инструкция RESTORE недопустима для базы данных-источника или базы данных-получателя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="7679a-106">RESTORE statements are not allowed on either the primary or secondary databases of an availability group.</span></span>  
  
  
  
##  <a name="backup-types-supported-on-secondary-replicas"></a><a name="SupportedBuTypes"></a><span data-ttu-id="7679a-107">Типы резервных копий, поддерживаемые на вторичных репликах</span><span class="sxs-lookup"><span data-stu-id="7679a-107">Backup Types Supported on Secondary Replicas</span></span>  
  
-   <span data-ttu-id="7679a-108">`BACKUP DATABASE` поддерживает только полные, доступные только для копирования резервные копии баз данных, файлов и файловых групп, которые выполняются во вторичных репликах.</span><span class="sxs-lookup"><span data-stu-id="7679a-108">`BACKUP DATABASE` supports only copy-only full backups of databases, files, or filegroups when it is executed on secondary replicas.</span></span> <span data-ttu-id="7679a-109">Обратите внимание, что резервные копии, доступные только для копирования, не влияют на цепочку журналов и не очищают битовую карту разностного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7679a-109">Note that copy-only backups do not impact the log chain or clear the differential bitmap.</span></span>  
  
-   <span data-ttu-id="7679a-110">Разностные резервные копии не поддерживаются во вторичных репликах.</span><span class="sxs-lookup"><span data-stu-id="7679a-110">Differential backups are not supported on secondary replicas.</span></span>  
  
-   <span data-ttu-id="7679a-111">**BACKUP LOG** поддерживает только обычное резервное копирование журналов (параметр COPY_ONLY не поддерживается для резервных копий журналов во вторичных репликах).</span><span class="sxs-lookup"><span data-stu-id="7679a-111">**BACKUP LOG** supports only regular log backups (the COPY_ONLY option is not supported for log backups on secondary replicas).</span></span>  
  
     <span data-ttu-id="7679a-112">Обеспечивается последовательная цепочка журналов по всем резервным копиям журналов в любой реплике (первичной или вторичной) независимо от их режима доступности (синхронной или асинхронной фиксации).</span><span class="sxs-lookup"><span data-stu-id="7679a-112">A consistent log chain is ensured across log backups taken on any of the replicas (primary or secondary), irrespective of their availability mode (synchronous-commit or asynchronous-commit).</span></span>  
  
-   <span data-ttu-id="7679a-113">Для выполнения резервного копирования базы данных-получателя вторичная реплика должна быть способна обмениваться данными с первичной репликой и находиться в состоянии `SYNCHRONIZED` или `SYNCHRONIZING`.</span><span class="sxs-lookup"><span data-stu-id="7679a-113">To back up a secondary database, a secondary replica must be able to communicate with the primary replica and must be `SYNCHRONIZED` or `SYNCHRONIZING`.</span></span>  
  
##  <a name="configuring-where-backup-jobs-run"></a><a name="WhereBuJobsRun"></a><span data-ttu-id="7679a-114">Настройка места запуска заданий резервного копирования</span><span class="sxs-lookup"><span data-stu-id="7679a-114">Configuring Where Backup Jobs Run</span></span>  
 <span data-ttu-id="7679a-115">Выполнение резервного копирования во вторичной реплике для снятия рабочей нагрузки резервного копирования с основного рабочего сервера обеспечивает значительные преимущества.</span><span class="sxs-lookup"><span data-stu-id="7679a-115">Performing backups on a secondary replica to offload the backup workload from the primary production server is a great benefit.</span></span> <span data-ttu-id="7679a-116">Однако выполнение резервного копирования на вторичных репликах создает значительные сложности в процессе определения, где должны запускаться задания резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7679a-116">However, performing backups on secondary replicas introduce significant complexity to the process of determining where backup jobs should run.</span></span> <span data-ttu-id="7679a-117">Для решения этой проблемы настройте расположение запуска заданий резервного копирования, как описано далее.</span><span class="sxs-lookup"><span data-stu-id="7679a-117">To address this, configure where backup jobs run as follows:</span></span>  
  
1.  <span data-ttu-id="7679a-118">Настройте группу доступности, чтобы указать, на каких репликах доступности предпочтительно проведение резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7679a-118">Configure the availability group to specify which availability replicas where you would prefer backups to be performed.</span></span> <span data-ttu-id="7679a-119">Дополнительные сведения см. в описании параметров *AUTOMATED_BACKUP_PREFERENCE* и *BACKUP_PRIORITY* в разделе [CREATE AVAILABILITY GROUP (Transact-SQL)](/sql/t-sql/statements/create-availability-group-transact-sql) или [ALTER AVAILABILITY GROUP (Transact-SQL)](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7679a-119">For more information, see *AUTOMATED_BACKUP_PREFERENCE* and *BACKUP_PRIORITY* parameters in [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) or [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
2.  <span data-ttu-id="7679a-120">Создайте скрипты заданий резервного копирования для каждой из баз данных доступности на каждом экземпляре сервера, на котором размещается реплика доступности, потенциально используемая для выполнения резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7679a-120">Create scripted backup jobs for every availability database on every server instance that hosts an availability replica that is a candidate for performing backups.</span></span> <span data-ttu-id="7679a-121">Дополнительные сведения см. в подразделе "Дальнейшие действия. После настройки резервного копирования во вторичных репликах" раздела [Настройка резервного копирования в репликах доступности (SQL Server)](configure-backup-on-availability-replicas-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7679a-121">For more information, see the "Follow Up: After Configuring Backup on Secondary Replicas" section of [Configure Backup on Availability Replicas &#40;SQL Server&#41;](configure-backup-on-availability-replicas-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7679a-122">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="7679a-122">Related Tasks</span></span>  
 <span data-ttu-id="7679a-123">**Настройка резервного копирования во вторичных репликах**</span><span class="sxs-lookup"><span data-stu-id="7679a-123">**To configure backup on secondary replicas**</span></span>  
  
-   [<span data-ttu-id="7679a-124">Настройка резервного копирования в репликах доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7679a-124">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
 <span data-ttu-id="7679a-125">**Определение, является ли текущая реплика предпочитаемой репликой резервного копирования**</span><span class="sxs-lookup"><span data-stu-id="7679a-125">**To determine whether the current replica is the preferred backup replica**</span></span>  
  
-   [<span data-ttu-id="7679a-126">sys.fn_hadr_backup_is_preferred_replica</span><span class="sxs-lookup"><span data-stu-id="7679a-126">sys.fn_hadr_backup_is_preferred_replica</span></span>](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql)  
  
 <span data-ttu-id="7679a-127">**Создание задания резервного копирования**</span><span class="sxs-lookup"><span data-stu-id="7679a-127">**To create a backup job**</span></span>  
  
-   [<span data-ttu-id="7679a-128">Использование мастера планов обслуживания</span><span class="sxs-lookup"><span data-stu-id="7679a-128">Use the Maintenance Plan Wizard</span></span>](../../../relational-databases/maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
-   [<span data-ttu-id="7679a-129">Реализация заданий</span><span class="sxs-lookup"><span data-stu-id="7679a-129">Implement Jobs</span></span>](../../../ssms/agent/implement-jobs.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="7679a-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="7679a-130">See Also</span></span>  
 <span data-ttu-id="7679a-131">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7679a-131">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="7679a-132">[Резервные копии только для копирования (SQL Server)](../../../relational-databases/backup-restore/copy-only-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7679a-132">[Copy-Only Backups &#40;SQL Server&#41;](../../../relational-databases/backup-restore/copy-only-backups-sql-server.md) </span></span>  
 <span data-ttu-id="7679a-133">[CREATE AVAILABILITY GROUP (Transact-SQL)](/sql/t-sql/statements/create-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7679a-133">[CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) </span></span>  
 [<span data-ttu-id="7679a-134">ALTER AVAILABILITY GROUP (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7679a-134">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-availability-group-transact-sql)  
  
  
