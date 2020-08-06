---
title: Ручная подготовка базы данных-получателя для присоединения к группе доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.configsecondarydbs.f1
- sql12.swb.availabilitygroup.preparedbs.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- secondary databases [SQL Server]
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 9f2feb3c-ea9b-4992-8202-2aeed4f9a6dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3da3f7332bdabce65785b2844157dd4639389254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657902"
---
# <a name="manually-prepare-a-secondary-database-for-an-availability-group-sql-server"></a><span data-ttu-id="1df47-102">Ручная подготовка базы данных-получателя для присоединения к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1df47-102">Manually Prepare a Secondary Database for an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="1df47-103">В этом разделе описывается подготовка базы данных-получателя для группы доступности AlwaysOn в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1df47-103">This topic describes how to prepare a secondary database for an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="1df47-104">Подготовка базы данных-получателя выполняется в два этапа: (1) восстановление базы данных из последней резервной копии базы данных-источника и соответствующих резервных копий журнала на каждом экземпляре сервера, где размещена вторичная реплика доступности, с помощью инструкции RESTORE WITH NORECOVERY и (2) присоединение восстановленной базы данных к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="1df47-104">Preparing a secondary database requires two steps: (1) restoring a recent database backup of the primary database and subsequent log backups onto each server instance that hosts the secondary replica, using RESTORE WITH NORECOVERY, and (2) joining the restored database to the availability group.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="1df47-105">Если имеется существующая конфигурация доставки журналов, можно будет преобразовать базу данных-источник доставки журналов вместе с одной или более базой данных-получателем в базу данных-источник AlwaysOn и одну или более баз данных-получателей AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="1df47-105">If you have an existing log shipping configuration, you might be able to convert the log shipping primary database along with one or more of its secondary databases to an AlwaysOn primary database and one or more AlwaysOn secondary databases.</span></span> <span data-ttu-id="1df47-106">Дополнительные сведения см. [в разделе Предварительные требования для миграции из доставки журналов в группы доступности AlwaysOn &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="1df47-106">For more information, see [Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span></span>  
  
-   <span data-ttu-id="1df47-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="1df47-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1df47-108">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="1df47-108">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="1df47-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1df47-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="1df47-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1df47-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1df47-111">**Подготовка базы данных-получателя с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="1df47-111">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="1df47-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1df47-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1df47-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1df47-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="1df47-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1df47-114">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="1df47-115">Связанные задачи резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="1df47-115">Related Backup and Restore Tasks</span></span>](#RelatedTasks)  
  
-   <span data-ttu-id="1df47-116">**Дальнейшие действия.** [После подготовки базы данных-получателя](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="1df47-116">**Follow Up:** [After Preparing a Secondary Database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1df47-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1df47-117">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="1df47-118">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="1df47-118">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="1df47-119">Убедитесь, что в системе, в которой предполагается разместить базу данных, есть жесткий диск, на котором достаточно свободного места для баз данных-получателей.</span><span class="sxs-lookup"><span data-stu-id="1df47-119">Make sure that the system where you plan to place database possesses a disk drive with sufficient space for the secondary databases.</span></span>  
  
-   <span data-ttu-id="1df47-120">Имя базы данных-получателя должно совпадать с именем базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="1df47-120">The name of the secondary database must be the same as the name of the primary database.</span></span>  
  
-   <span data-ttu-id="1df47-121">Для каждой операции восстановления используйте инструкцию RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1df47-121">Use RESTORE WITH NORECOVERY for every restore operation.</span></span>  
  
-   <span data-ttu-id="1df47-122">Если необходимо, чтобы путь к файлам базы данных-получателя отличался от пути к базе данных-источнику (в т. ч. буквой диска), в команду восстановления необходимо добавить параметр WITH MOVE для каждого файла базы данных, чтобы указать для них путь к базе данных-получателю.</span><span class="sxs-lookup"><span data-stu-id="1df47-122">If the secondary database needs to reside on a different file path (including the drive letter) than the primary database, the restore command must also use the WITH MOVE option for each of the database files to specify them to the path of the secondary database.</span></span>  
  
-   <span data-ttu-id="1df47-123">При восстановлении файловой группы базы данных по файловой группе следует восстановить базу данных целиком.</span><span class="sxs-lookup"><span data-stu-id="1df47-123">If you restore the database filegroup by filegroup, be sure to restore the whole database.</span></span>  
  
-   <span data-ttu-id="1df47-124">После восстановления базы данных необходимо восстановить (с параметром WITH NORECOVERY) каждую резервную копию журнала, созданную с момента последнего восстановления данных из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="1df47-124">After restoring the database, you must restore (WITH NORECOVERY) every log backup created since the last restored data backup.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1df47-125">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1df47-125">Recommendations</span></span>  
  
-   <span data-ttu-id="1df47-126">Для автономных экземпляров [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]рекомендуется, чтобы по возможности путь к файлам (в том числе буква диска) базы данных-получателя совпадал с путем к соответствующей базе данных-источнику.</span><span class="sxs-lookup"><span data-stu-id="1df47-126">On stand-alone instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], we recommend that, if possible, the file path (including the drive letter) of a given secondary database be identical to the path of the corresponding primary database.</span></span> <span data-ttu-id="1df47-127">Такой подход рекомендуется, поскольку если при создании базы данных-получателя переместить ее файлы, то последующее добавление в нее файлов может завершиться ошибкой, в результате чего ее работа будет приостановлена.</span><span class="sxs-lookup"><span data-stu-id="1df47-127">This is because if you move the database files when creating a secondary database, a later add-file operation might fail on the secondary database and cause the secondary database to be suspended.</span></span>  
  
-   <span data-ttu-id="1df47-128">Перед подготовкой баз данных-получателей настоятельно рекомендуется приостановить резервное копирование журнала по расписанию для всех баз данных в группе доступности до завершения инициализации вторичных реплик.</span><span class="sxs-lookup"><span data-stu-id="1df47-128">Before preparing your secondary databases, we strongly recommend that you suspend scheduled log backups on the databases in the availability group until the initialization of secondary replicas has completed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1df47-129">безопасность</span><span class="sxs-lookup"><span data-stu-id="1df47-129">Security</span></span>  
 <span data-ttu-id="1df47-130">При резервном копировании базы данных [свойство TRUSTWORTHY](../../../relational-databases/security/trustworthy-database-property.md) устанавливается в значение OFF.</span><span class="sxs-lookup"><span data-stu-id="1df47-130">When a database is backed up, the [TRUSTWORTHY database property](../../../relational-databases/security/trustworthy-database-property.md) is set to OFF.</span></span> <span data-ttu-id="1df47-131">Поэтому свойство TRUSTWORTHY всегда имеет значение OFF во всех только что восстановленных базах данных.</span><span class="sxs-lookup"><span data-stu-id="1df47-131">Therefore, TRUSTWORTHY is always OFF on a newly restored database.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1df47-132">Permissions</span><span class="sxs-lookup"><span data-stu-id="1df47-132">Permissions</span></span>  
 <span data-ttu-id="1df47-133">Разрешения BACKUP DATABASE и BACKUP LOG назначены по умолчанию членам предопределенной роли сервера **sysadmin** и предопределенным ролям базы данных **db_owner** и **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="1df47-133">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span> <span data-ttu-id="1df47-134">Дополнительные сведения см. в разделе [BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1df47-134">For more information, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
 <span data-ttu-id="1df47-135">Если восстанавливаемая база данных не существует на нужном экземпляре сервера, для выполнения инструкции RESTORE требуются разрешения CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="1df47-135">When the database being restored does not exist on the server instance, the RESTORE statement requires CREATE DATABASE permissions.</span></span> <span data-ttu-id="1df47-136">Дополнительные сведения см. в разделе [RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql)невозможно.</span><span class="sxs-lookup"><span data-stu-id="1df47-136">For more information, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1df47-137">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1df47-137">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1df47-138"> Если пути для файлов резервного копирования и восстановления на экземпляре сервера, размещающем первичную реплику, и на каждом экземпляре, на которых размещена вторичная реплика, идентичны, есть возможность создания баз данных-получателей с помощью [Мастера создания группы доступности](use-the-availability-group-wizard-sql-server-management-studio.md), [Мастер добавления реплики в группу доступности](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)или [Мастера добавления базы данных в группу доступности](availability-group-add-database-to-group-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="1df47-138">If the backup and restore file paths are identical between the server instance that hosts the primary replica and every instance that hosts a secondary replica, you should be able create secondary databases by using [New Availability Group Wizard](use-the-availability-group-wizard-sql-server-management-studio.md), [Add Replica to Availability Group Wizard](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md), or [Add Database to Availability Group Wizard](availability-group-add-database-to-group-wizard.md).</span></span>  
  
 <span data-ttu-id="1df47-139">**Подготовка базы данных-получателя**</span><span class="sxs-lookup"><span data-stu-id="1df47-139">**To prepare a secondary database**</span></span>  
  
1.  <span data-ttu-id="1df47-140">Создайте новую полную или разностную резервную копию базы данных, если у вас еще нет недавней резервной копии базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="1df47-140">Unless you already have a recent database backup of the primary database, create a new full or differential database backup.</span></span> <span data-ttu-id="1df47-141">Настоятельно рекомендуется поместить эту резервную копию и все последующие резервные копии журналов в указанную общую сетевую папку.</span><span class="sxs-lookup"><span data-stu-id="1df47-141">As a best practice, place this backup and any subsequent log backups onto the recommended network share.</span></span>  
  
2.  <span data-ttu-id="1df47-142">Создайте минимум одну новую резервную копию журнала базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="1df47-142">Create at least one new log backup of the primary database.</span></span>  
  
3.  <span data-ttu-id="1df47-143">Выполните восстановление из полной резервной копии базы данных-источника на том экземпляре сервера, на котором размещена вторичная реплика (можно также восстановить разностную резервную копию), после чего восстановите все последующие резервные копии журнала.</span><span class="sxs-lookup"><span data-stu-id="1df47-143">On the server instance that hosts the secondary replica, restore the full database backup of the primary database (and optionally a differential backup) followed by any subsequent log backups.</span></span>  
  
     <span data-ttu-id="1df47-144">На странице **Параметры RESTORE DATABASE** выберите параметр **Оставить базу данных в неработающем состоянии и не выполнять откат незафиксированных транзакций. Можно восстановить дополнительные журналы транзакций. (RESTORE WITH NORECOVERY)**.</span><span class="sxs-lookup"><span data-stu-id="1df47-144">On the **RESTORE DATABASEOptions** page, select **Leave the database non-operational, and do not roll back the uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**.</span></span>  
  
     <span data-ttu-id="1df47-145">Если пути к файлам базы данных-источника и базы данных-получателя отличаются, например если соответствующие основные базы данных находятся на диске «F:», но на экземпляре сервера, на котором размещена дополнительная реплика, нет диска «F:», используйте параметр MOVE в предложении WITH.</span><span class="sxs-lookup"><span data-stu-id="1df47-145">If the file paths of the primary database and the secondary database differ, for example, if the primary database is on drive 'F:' but the server instance that hosts the secondary replica lacks an F: drive, include the MOVE option in your WITH clause.</span></span>  
  
4.  <span data-ttu-id="1df47-146">Чтобы завершить настройку базы данных-получателя, необходимо присоединить ее к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="1df47-146">To complete configuration of the secondary database, you need to join the secondary database to the availability group.</span></span> <span data-ttu-id="1df47-147">Дополнительные сведения см. в разделе [Присоединение базы данных-получателя к группе доступности (SQL Server)](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1df47-147">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1df47-148"> Дополнительные сведения о выполнении этих операций резервного копирования и восстановления см. в подразделе [Связанные задачи резервного копирования и восстановления](#RelatedTasks)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1df47-148">For information about how to perform these backup and restore operations, see [Related Backup and Restore Tasks](#RelatedTasks), later in this section.</span></span>  
  
###  <a name="related-backup-and-restore-tasks"></a><a name="RelatedTasks"></a><span data-ttu-id="1df47-149">Связанные задачи резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="1df47-149">Related Backup and Restore Tasks</span></span>  
 <span data-ttu-id="1df47-150">**Создание резервной копии базы данных**</span><span class="sxs-lookup"><span data-stu-id="1df47-150">**To create a database backup**</span></span>  
  
-   [<span data-ttu-id="1df47-151">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1df47-151">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="1df47-152">Создание разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1df47-152">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="1df47-153">**Создание резервной копии журнала**</span><span class="sxs-lookup"><span data-stu-id="1df47-153">**To create a log backup**</span></span>  
  
-   [<span data-ttu-id="1df47-154">Создание резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1df47-154">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)  
  
 <span data-ttu-id="1df47-155">**Восстановление резервных копий**</span><span class="sxs-lookup"><span data-stu-id="1df47-155">**To restore backups**</span></span>  
  
-   [<span data-ttu-id="1df47-156">Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1df47-156">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="1df47-157">Восстановление разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1df47-157">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="1df47-158">Восстановление резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1df47-158">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="1df47-159">Восстановление базы данных в новом расположении (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1df47-159">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1df47-160">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1df47-160">Using Transact-SQL</span></span>  
 <span data-ttu-id="1df47-161">**Подготовка базы данных-получателя**</span><span class="sxs-lookup"><span data-stu-id="1df47-161">**To prepare a secondary database**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1df47-162">Пример этой процедуры см. в подразделе [Пример (Transact-SQL)](#ExampleTsql)ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1df47-162">For an example of this procedure, see [Example (Transact-SQL)](#ExampleTsql), earlier in this topic.</span></span>  
  
1.  <span data-ttu-id="1df47-163">Если у вас нет недавней полной резервной копии базы данных-источника, выполните подключение к экземпляру сервера, на котором размещена первичная реплика, и создайте полную резервную копию базы данных.</span><span class="sxs-lookup"><span data-stu-id="1df47-163">Unless you have a recent full backup of the primary database, connect to the server instance that hosts the primary replica and create a full database backup.</span></span> <span data-ttu-id="1df47-164">Настоятельно рекомендуется поместить эту резервную копию и все последующие резервные копии журналов в указанную общую сетевую папку.</span><span class="sxs-lookup"><span data-stu-id="1df47-164">As a best practice, place this backup and any subsequent log backups onto the recommended network share.</span></span>  
  
2.  <span data-ttu-id="1df47-165">В экземпляре сервера, на котором размещена вторичная реплика доступности, выполните восстановление из полной резервной копии базы данных-источника (также можно восстановить и разностную копию), после чего восстановите последующие копии журнала.</span><span class="sxs-lookup"><span data-stu-id="1df47-165">On the server instance that hosts the secondary replica, restore the full database backup of the primary database (and optionally a differential backup) followed by all subsequent log backups.</span></span> <span data-ttu-id="1df47-166">Для каждой операции восстановления используйте параметр WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1df47-166">Use WITH NORECOVERY for every restore operation.</span></span>  
  
     <span data-ttu-id="1df47-167">Если пути к файлам базы данных-источника и базы данных-получателя отличаются, например если соответствующие основные базы данных находятся на диске «F:», но на экземпляре сервера, на котором размещена дополнительная реплика, нет диска «F:», используйте параметр MOVE в предложении WITH.</span><span class="sxs-lookup"><span data-stu-id="1df47-167">If the file paths of the primary database and the secondary database differ, for example, if the primary database is on drive 'F:' but the server instance that hosts the secondary replica lacks an F: drive, include the MOVE option in your WITH clause.</span></span>  
  
3.  <span data-ttu-id="1df47-168">Если с момента последнего обязательного резервного копирования журнала было выполнено резервное копирование журнала базы данных-источника, эти копии также необходимо скопировать на тот экземпляр сервера, на котором размещена вторичная реплика, и применить все эти резервные копии журнала к базе данных-получателю, начиная с самой ранней. При этом необходимо всегда использовать инструкцию RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1df47-168">If any log backups have been taken on the primary database since the required log backup, you must also copy these to the server instance that hosts the secondary replica and apply each of those log backups to the secondary database, starting with the earliest and always using RESTORE WITH NORECOVERY.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1df47-169">Резервной копии журнала может не быть в том случае, если база данных-источник только что создана и в ней еще не было создано ни одной резервной копии журналов либо если модель восстановления только что изменена с SIMPLE на FULL.</span><span class="sxs-lookup"><span data-stu-id="1df47-169">A log backup would not exist if the primary database has just been created and no log backup has been taken yet or if the recovery model has just been changed from simple to full.</span></span>  
  
4.  <span data-ttu-id="1df47-170">Чтобы завершить настройку базы данных-получателя, необходимо присоединить ее к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="1df47-170">To complete configuration of the secondary database, you need to join the secondary database to the availability group.</span></span> <span data-ttu-id="1df47-171">Дополнительные сведения см. в разделе [Присоединение базы данных-получателя к группе доступности (SQL Server)](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1df47-171">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1df47-172"> Дополнительные сведения о выполнении этих операций резервного копирования и восстановления см. в подразделе [Связанные задачи резервного копирования и восстановления](#RelatedTasks)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1df47-172">For information about how to perform these backup and restore operations, see [Related Backup and Restore Tasks](#RelatedTasks), later in this topic.</span></span>  
  
###  <a name="transact-sql-example"></a><a name="ExampleTsql"></a><span data-ttu-id="1df47-173">Пример Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1df47-173">Transact-SQL Example</span></span>  
 <span data-ttu-id="1df47-174">В следующем примере показана подготовка базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="1df47-174">The following example prepares a secondary database.</span></span> <span data-ttu-id="1df47-175">В этом примере используется образец базы данных [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , в котором по умолчанию применяется простая модель восстановления.</span><span class="sxs-lookup"><span data-stu-id="1df47-175">This example uses the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database, which uses the simple recovery model by default.</span></span>  
  
1.  <span data-ttu-id="1df47-176">Чтобы использовать базу данных [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , следует ее изменить так, чтобы использовалась модель полного восстановления:</span><span class="sxs-lookup"><span data-stu-id="1df47-176">To use the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database, modify it to use the full recovery model:</span></span>  
  
    ```sql
    USE master;  
    GO  
    ALTER DATABASE MyDB1   
    SET RECOVERY FULL;  
    GO  
    ```  
  
2.  <span data-ttu-id="1df47-177">После изменения модели восстановления с SIMPLE на FULL создайте полную резервную копию, с помощью которой затем можно будет создать базу данных-получатель.</span><span class="sxs-lookup"><span data-stu-id="1df47-177">After modifying the recovery model of the database from SIMPLE to FULL, create a full backup, which can be used to create the secondary database.</span></span> <span data-ttu-id="1df47-178">Так как модель восстановления только что была изменена, указывается параметр WITH FORMAT для создания нового набора носителей.</span><span class="sxs-lookup"><span data-stu-id="1df47-178">Because the recovery model has just been changed, the WITH FORMAT option is specified to create a new media set.</span></span> <span data-ttu-id="1df47-179">Это полезно для отделения резервных копий при модели полного восстановления от резервных копий, сделанных при простой модели восстановления.</span><span class="sxs-lookup"><span data-stu-id="1df47-179">This is useful to separate the backups under the full recovery model from any previous backups made under the simple recovery model.</span></span> <span data-ttu-id="1df47-180">В данном примере файл резервной копии (C:\\[!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].bak) создается на том же диске, что и база данных.</span><span class="sxs-lookup"><span data-stu-id="1df47-180">For the purpose of this example, the backup file (C:\\[!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].bak) is created on the same drive as the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1df47-181">Для производственной базы данных необходимо всегда делать резервные копии на разные устройства.</span><span class="sxs-lookup"><span data-stu-id="1df47-181">For a production database, you should always back up to a separate device.</span></span>  
  
     <span data-ttu-id="1df47-182">На экземпляре сервера, на котором размещена основная реплика (`INSTANCE01`), создайте полную резервную копию базы данных-источника, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1df47-182">On the server instance that hosts the primary replica (`INSTANCE01`), create a full backup of the primary database as follows:</span></span>  
  
    ```sql
    BACKUP DATABASE MyDB1   
        TO DISK = 'C:\MyDB1.bak'   
        WITH FORMAT  
    GO  
    ```  
  
3.  <span data-ttu-id="1df47-183">Скопируйте полную резервную копию на экземпляр сервера, на котором размещается вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="1df47-183">Copy the full backup to the server instance that hosts the secondary replica.</span></span>  
  
4.  <span data-ttu-id="1df47-184">На сервере, на котором размещена вторичная реплика, восстановите полную резервную копию с помощью инструкции RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1df47-184">Restore the full backup, using RESTORE WITH NORECOVERY, onto the server instance that hosts the secondary replica.</span></span> <span data-ttu-id="1df47-185">Команда восстановления зависит от того, идентичны ли пути к базе данных-источнику и базе данных-получателю.</span><span class="sxs-lookup"><span data-stu-id="1df47-185">The restore command depends on whether the paths of primary and secondary databases are identical.</span></span>  
  
    -   <span data-ttu-id="1df47-186">**Если пути идентичны:**</span><span class="sxs-lookup"><span data-stu-id="1df47-186">**If the paths are identical:**</span></span>  
  
         <span data-ttu-id="1df47-187">На компьютере, на котором размещена вторичная реплика, выполните восстановление полной резервной копии следующим образом.</span><span class="sxs-lookup"><span data-stu-id="1df47-187">On the computer that hosts the secondary replica, restore the full backup as follows:</span></span>  
  
        ```sql
        RESTORE DATABASE MyDB1   
            FROM DISK = 'C:\MyDB1.bak'   
            WITH NORECOVERY  
        GO  
        ```  
  
    -   <span data-ttu-id="1df47-188">**Если пути отличаются:**</span><span class="sxs-lookup"><span data-stu-id="1df47-188">**If the paths differ:**</span></span>  
  
         <span data-ttu-id="1df47-189">Если путь к базе данных-получателю отличается от пути к базе данных-источнику (например, отличаются имена дисков), то для создания базы данных-получателя в операцию восстановления нужно будет добавить предложение MOVE.</span><span class="sxs-lookup"><span data-stu-id="1df47-189">If the path of the secondary database differs from the path of the primary database (for instance, their drive letters differ), creating the secondary database requires that the restore operation include a MOVE clause.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="1df47-190">Если пути к базе данных-источнику и базе данных-получателю отличаются, то добавлять файлы нельзя.</span><span class="sxs-lookup"><span data-stu-id="1df47-190">If the path names of the primary and secondary databases differ, you cannot add a file.</span></span> <span data-ttu-id="1df47-191">Обусловлено это тем, что при получении журнала для выполнения операции добавления файла экземпляр сервера, на котором размещена вторичная реплика, пытается поместить новый файл в местоположение, указанное для базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="1df47-191">This is because on receiving the log for the add file operation, the server instance of the secondary replica attempts to place the new file in the same path as used by the primary database.</span></span>  
  
         <span data-ttu-id="1df47-192">Например, следующая команда восстанавливает базу данных-источник из резервной копии, размещенной в каталоге данных экземпляра [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]по умолчанию, C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA.</span><span class="sxs-lookup"><span data-stu-id="1df47-192">For example, the following command restores a backup of a primary database that resides in the data directory of the default instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA.</span></span> <span data-ttu-id="1df47-193">Операция восстановления базы данных должна переместить базу данных в каталог данных удаленного экземпляра [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с именем (*AlwaysOn1*), на котором размещается вторичная реплика на другом узле кластера.</span><span class="sxs-lookup"><span data-stu-id="1df47-193">The restore database operation must move the database to the data directory of a remote instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] named  (*AlwaysOn1*), which hosts the secondary replica on another cluster node.</span></span> <span data-ttu-id="1df47-194">Там файлы данных и журналов восстанавливаются в папку *C:\Program FILES\MICROSOFT SQL Server\MSSQL12. Каталог ALWAYSON1\MSSQL\DATA* .</span><span class="sxs-lookup"><span data-stu-id="1df47-194">There, the data and log files are restored to the *C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA* directory .</span></span> <span data-ttu-id="1df47-195">Операция восстановления использует параметр WITH NORECOVERY, чтобы оставить базу данных-получатель в восстанавливающейся базе данных.</span><span class="sxs-lookup"><span data-stu-id="1df47-195">The restore operation uses WITH NORECOVERY, to leave the secondary database in the restoring database.</span></span>  
  
        ```sql
        RESTORE DATABASE MyDB1  
          FROM DISK='C:\MyDB1.bak'  
         WITH NORECOVERY,   
            MOVE 'MyDB1_Data' TO   
             'C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA\MyDB1_Data.mdf',   
            MOVE 'MyDB1_Log' TO  
             'C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA\MyDB1_Data.ldf';  
        GO  
        ```  
  
5.  <span data-ttu-id="1df47-196">После того как полная резервная копия базы данных будет восстановлена, необходимо создать резервную копию журнала базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="1df47-196">After you restore the full backup, you must create a log backup on the primary database.</span></span> <span data-ttu-id="1df47-197">Например, следующая инструкция [!INCLUDE[tsql](../../../includes/tsql-md.md)] выполняет резервное копирование журнала в файл резервной копии с именем *E:\MyDB1_log.bak*:</span><span class="sxs-lookup"><span data-stu-id="1df47-197">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement backs up the log to the a backup file named *E:\MyDB1_log.bak*:</span></span>  
  
    ```sql
    BACKUP LOG MyDB1   
      TO DISK = 'E:\MyDB1_log.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="1df47-198">Перед присоединением базы данных к вторичной реплике необходимо применить эту обязательную резервную копию журнала (и все последующие резервные копии журнала).</span><span class="sxs-lookup"><span data-stu-id="1df47-198">Before you can join the database to the secondary replica, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="1df47-199">Например, следующая инструкция [!INCLUDE[tsql](../../../includes/tsql-md.md)] восстанавливает первый журнал из файла *C:\MyDB1.bak*:</span><span class="sxs-lookup"><span data-stu-id="1df47-199">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement restores the first log from *C:\MyDB1.bak*:</span></span>  
  
    ```sql
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="1df47-200">Если перед присоединением базы данных-получателя будут созданы любые дополнительные резервные копии журнала, необходимо будет последовательно восстановить все эти резервные копии журналов на том экземпляре сервера, на котором размещена вторичная реплика. При этом необходимо использовать инструкцию RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1df47-200">If any additional log backups occur before the database joins the secondary replica, you must also restore all of those log backups, in sequence, to the server instance that hosts the secondary replica using RESTORE WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="1df47-201">Например, следующая инструкция [!INCLUDE[tsql](../../../includes/tsql-md.md)] восстанавливает два дополнительных журнала из файла *E:\MyDB1_log.bak*:</span><span class="sxs-lookup"><span data-stu-id="1df47-201">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement restores two additional logs from *E:\MyDB1_log.bak*:</span></span>  
  
    ```sql
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=2, NORECOVERY  
    GO  
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=3, NORECOVERY  
    GO  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="1df47-202">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="1df47-202">Using PowerShell</span></span>  
 <span data-ttu-id="1df47-203">**Подготовка базы данных-получателя**</span><span class="sxs-lookup"><span data-stu-id="1df47-203">**To prepare a secondary database**</span></span>  
  
1.  <span data-ttu-id="1df47-204">В случае если резервная копия базы данных-источника отсутствует и вы создаете ее самостоятельно, перейдите в каталог (`cd`) экземпляра сервера, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="1df47-204">If you need to create a recent backup of the primary database, change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="1df47-205">Используйте командлет `Backup-SqlDatabase`, чтобы создать каждую их этих резервных копий.</span><span class="sxs-lookup"><span data-stu-id="1df47-205">Use the `Backup-SqlDatabase` cmdlet to create each of the backups.</span></span>  
  
3.  <span data-ttu-id="1df47-206">Перейдите в каталог (`cd`) экземпляра сервера, на котором размещается вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="1df47-206">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
4.  <span data-ttu-id="1df47-207">Чтобы восстановить резервные копии базы данных и журналов для каждой базы данных-источника, используйте командлет `restore-SqlDatabase`, указывая параметр восстановления `NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="1df47-207">To restore the database and log backups of each primary database, use the `restore-SqlDatabase` cmdlet, specifying the `NoRecovery` restore parameter.</span></span> <span data-ttu-id="1df47-208">Если пути к файлам различны на компьютерах, на которых размещена основная реплика и целевая вторичная реплика, также следует использовать параметр восстановления `RelocateFile`.</span><span class="sxs-lookup"><span data-stu-id="1df47-208">If the file paths differ between the computers that host the primary replica and the target secondary replica, also use the `RelocateFile` restore parameter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1df47-209">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1df47-209">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="1df47-210">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1df47-210">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
5.  <span data-ttu-id="1df47-211">Чтобы завершить настройку базы данных-получателя, необходимо присоединить ее к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="1df47-211">To complete configuration of the secondary database, you need to join it to the availability group.</span></span> <span data-ttu-id="1df47-212">Дополнительные сведения см. в разделе [Присоединение базы данных-получателя к группе доступности (SQL Server)](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1df47-212">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="1df47-213">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1df47-213">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="1df47-214">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="1df47-214">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
###  <a name="sample-backup-and-restore-script-and-command"></a><a name="ExamplePSscript"></a><span data-ttu-id="1df47-215">Пример сценария и команды резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="1df47-215">Sample Backup and Restore Script and Command</span></span>  
 <span data-ttu-id="1df47-216">Следующие команды PowerShell создают полную резервную копию базы данных и журнала транзакций в общей сетевой папке и восстанавливают базу данных из этой папки.</span><span class="sxs-lookup"><span data-stu-id="1df47-216">The following PowerShell commands back up a full database backup and transaction log to a network share and restore those backups from that share.</span></span> <span data-ttu-id="1df47-217">В этом примере предполагается, что путь к файлам, в которые выполняется восстановление базы данных, такой же, как и путь к файлам базы данных, резервная копия которых была создана.</span><span class="sxs-lookup"><span data-stu-id="1df47-217">This example assumes that the file path to which the database is restored is the same as the file path on which the database was backed up.</span></span>  
  
```powershell
# Create database backup  
Backup-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.bak" -ServerInstance "SourceMachine\Instance"  
# Create log backup  
Backup-SqlDatabase -Database "MyDB1" -BackupAction "Log" -BackupFile "\\share\backups\MyDB1.trn" -ServerInstance "SourceMachine\Instance"  
# Restore database backup
Restore-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.bak" -NoRecovery -ServerInstance "DestinationMachine\Instance"  
# Restore log backup
Restore-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.trn" -RestoreAction "Log" -NoRecovery -ServerInstance "DestinationMachine\Instance"
```  
  
##  <a name="follow-up-after-preparing-a-secondary-database"></a><a name="FollowUp"></a><span data-ttu-id="1df47-218">Дальнейшие действия. После подготовки базы данных-получателя</span><span class="sxs-lookup"><span data-stu-id="1df47-218">Follow Up: After Preparing a Secondary Database</span></span>  
 <span data-ttu-id="1df47-219">Чтобы завершить настройку базы данных-получателя, необходимо присоединить только что восстановленную базу данных к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="1df47-219">To complete configuration of the secondary database, join the newly restored database to the availability group.</span></span> <span data-ttu-id="1df47-220">Дополнительные сведения см. в статье [Присоединение базы данных-получателя к группе доступности (SQL Server)](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1df47-220">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1df47-221">См. также:</span><span class="sxs-lookup"><span data-stu-id="1df47-221">See Also</span></span>  
 <span data-ttu-id="1df47-222">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1df47-222">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="1df47-223">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1df47-223">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="1df47-224">[Аргументы инструкции RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1df47-224">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="1df47-225">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1df47-225">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="1df47-226">Устранение неполадок при &#40;операции добавления файла группы доступности AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="1df47-226">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
