---
title: Подготовка зеркальной базы данных к зеркальному отображению (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], preparing for mirroring
- logins [SQL Server], database mirroring
- mirror database [SQL Server]
ms.assetid: 8676f9d8-c451-419b-b934-786997d46c2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf46b4f6fd8e7af55e1930ef6063c4754673fa79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733105"
---
# <a name="prepare-a-mirror-database-for-mirroring-sql-server"></a><span data-ttu-id="1bea7-102">Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1bea7-102">Prepare a Mirror Database for Mirroring (SQL Server)</span></span>
  <span data-ttu-id="1bea7-103">Перед началом сеанса зеркального отображения базы данных ее владелец или системный администратор должен убедиться, что зеркальная база данных создана и готова к работе.</span><span class="sxs-lookup"><span data-stu-id="1bea7-103">Before a database mirroring session can start, the database owner or system administrator must make sure that the mirror database has been created and is ready for mirroring.</span></span> <span data-ttu-id="1bea7-104">Чтобы создать новую зеркальную базу данных, требуется как минимум наличие полной резервной копии основной базы данных и последующих резервных копий журналов. Они восстанавливаются на экземпляре зеркального сервера с параметром WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1bea7-104">Creating a new mirror database minimally requires taking a full backup of the principal database and a subsequent log backup and restoring them both onto the mirror server instance, using WITH NORECOVERY.</span></span>  
  
 <span data-ttu-id="1bea7-105">В этом разделе описано, как подготовить зеркальную базу данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bea7-105">This topic describes how to prepare a mirror database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1bea7-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1bea7-106">Before You Begin</span></span>  
  
###  <a name="requirements"></a><a name="Requirements"></a> <span data-ttu-id="1bea7-107">Требования</span><span class="sxs-lookup"><span data-stu-id="1bea7-107">Requirements</span></span>  
  
-   <span data-ttu-id="1bea7-108">На основном сервере и на экземплярах зеркального сервера должна работать одна и та же версия [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bea7-108">The principal and mirror server instances must be running on the same version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1bea7-109">Для зеркального сервера возможна более поздняя версия SQL Server, но эта конфигурация рекомендуется только во время процесса тщательно спланированного обновления.</span><span class="sxs-lookup"><span data-stu-id="1bea7-109">While it is possible for the mirror server to have a higher version of SQL Server, this configuration is only recommended during a carefully planned upgrade process.</span></span> <span data-ttu-id="1bea7-110">В такой конфигурации есть риск автоматического перехода на другой ресурс, в котором движение данных автоматически приостанавливается, так как данные нельзя переместить на более раннюю версию SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1bea7-110">In such a configuration, you run the risk of an automatic failover, in which data movement is automatically suspended because data cannot move to a lower version of SQL Server.</span></span> <span data-ttu-id="1bea7-111">Дополнительные сведения см. в разделе [Minimize Downtime for Mirrored Databases When Upgrading Server Instances](upgrading-mirrored-instances.md).</span><span class="sxs-lookup"><span data-stu-id="1bea7-111">For more information, see [Minimize Downtime for Mirrored Databases When Upgrading Server Instances](upgrading-mirrored-instances.md).</span></span>  
  
-   <span data-ttu-id="1bea7-112">На основном сервере и на экземплярах зеркального сервера должен работать один и тот же выпуск [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bea7-112">The principal and mirror server instances must be running on the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1bea7-113">Дополнительные сведения о зеркальном отображении базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] см. в разделе [Функции, поддерживаемые различными выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="1bea7-113">For information about support for database mirroring in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="1bea7-114">База данных должна использовать модель полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="1bea7-114">The database must use the full recovery model.</span></span>  
  
     <span data-ttu-id="1bea7-115">Дополнительные сведения см. в статьях [Просмотр или изменение модели восстановления базы данных (SQL Server)](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md) или [sys.databases (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) и [ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1bea7-115">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md) or [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) and [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
-   <span data-ttu-id="1bea7-116">Имя зеркальной базы данных должно совпадать с именем основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-116">The name of the mirror database must be the same as the name of the principal database.</span></span>  
  
-   <span data-ttu-id="1bea7-117">Для работы зеркального отображения необходимо, чтобы зеркальная база данных находилась в состоянии RESTORING.</span><span class="sxs-lookup"><span data-stu-id="1bea7-117">The mirror database must be in the RESTORING state for mirroring to work.</span></span> <span data-ttu-id="1bea7-118">При подготовке зеркальной базы данных необходимо использовать инструкцию RESTORE WITH NORECOVERY для каждой операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="1bea7-118">When preparing a mirror database, you must use RESTORE WITH NORECOVERY for every restore operation.</span></span> <span data-ttu-id="1bea7-119">Как минимум необходимо восстановить с параметром WITH NORECOVERY полную резервную копию основной базы данных, а затем все последующие резервные копии журналов.</span><span class="sxs-lookup"><span data-stu-id="1bea7-119">Minimally, you will need to restore WITH NORECOVERY a full backup of the principal database, followed by all subsequent log backups.</span></span>  
  
-   <span data-ttu-id="1bea7-120">В системе, где предполагается создать зеркальную базу данных, должен быть жесткий диск, на котором достаточно свободного места.</span><span class="sxs-lookup"><span data-stu-id="1bea7-120">The system where you plan to create the mirror database must possesses a disk drive with sufficient space to hold the mirror database.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1bea7-121">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1bea7-121">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1bea7-122">Зеркальное отображение системных баз данных **master**, **msdb**, **temp**и **model** невозможно.</span><span class="sxs-lookup"><span data-stu-id="1bea7-122">You cannot mirror the **master**, **msdb**, **temp**, or **model** system databases.</span></span>  
  
-   <span data-ttu-id="1bea7-123">Нельзя создать зеркальную копию базы данных, которая принадлежит [группы доступности AlwaysOn (SQL Server)](../availability-groups/windows/always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1bea7-123">You cannot mirror a database that belongs to an [AlwaysOn Availability Groups (SQL Server)](../availability-groups/windows/always-on-availability-groups-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1bea7-124">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1bea7-124">Recommendations</span></span>  
  
-   <span data-ttu-id="1bea7-125">Используйте либо самую последнюю полную копию базы данных, либо разностную резервную копию основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-125">Use a very recent full database backup or a recent differential database backup of the principal database.</span></span>  
  
-   <span data-ttu-id="1bea7-126">Если запланировано частое выполнение задания резервного копирования журналов основной базы данных, то, возможно, его придется отключить до запуска зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="1bea7-126">If a log backup job is scheduled to run very frequently on the principal database, you might have to disable the backup job until mirroring has started.</span></span>  
  
-   <span data-ttu-id="1bea7-127">Желательно, чтобы путь зеркальной базы данных (включая имя диска) был идентичен пути основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-127">If possible, the path (including the drive letter) of the mirror database should be identical to the path of the principal database.</span></span>  
  
     <span data-ttu-id="1bea7-128">Если пути к файлам должны различаться, например если основная база данных расположена на диске «F:», а в зеркальной системе нет диска «F:», необходимо включить в инструкцию RESTORE параметр MOVE.</span><span class="sxs-lookup"><span data-stu-id="1bea7-128">If the file paths must differ, for example, if the principal database is on drive 'F:' but the mirror system lacks an F: drive, you must include the MOVE option in the RESTORE STATEMENT.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1bea7-129">Добавление файлов во время сеанса зеркального отображения без влияния на сеанс требует, чтобы путь к файлам существовал на обоих серверах.</span><span class="sxs-lookup"><span data-stu-id="1bea7-129">Adding a file during a mirroring session without impacting the session requires that the path of the file exists on both servers.</span></span> <span data-ttu-id="1bea7-130">Поэтому перемещение файлов базы данных во время создания зеркального отображения может привести к его ошибке или остановке при выполнении операции добавления файла.</span><span class="sxs-lookup"><span data-stu-id="1bea7-130">Therefore, if you move the database files when creating the mirror database, a later add-file operation might fail on the mirror database and cause mirroring to be suspended.</span></span> <span data-ttu-id="1bea7-131">Дополнительные сведения об обработке ошибок операции создания файла см. в статье [Диагностика конфигурации зеркального отображения базы данных (SQL Server)](troubleshoot-database-mirroring-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1bea7-131">For information about dealing with a failed create-file operation, see [Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md).</span></span>  
  
-   <span data-ttu-id="1bea7-132">Если основная база данных содержит любые полнотекстовые каталоги, см. статью [Зеркальное отображение баз данных и полнотекстовые каталоги (SQL Server)](database-mirroring-and-full-text-catalogs-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1bea7-132">If the principal database has any full-text catalogs, we recommend that you see [Database Mirroring and Full-Text Catalogs &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md).</span></span>  
  
-   <span data-ttu-id="1bea7-133">Для производственной базы данных необходимо всегда создавать резервные копии на разных устройствах.</span><span class="sxs-lookup"><span data-stu-id="1bea7-133">For a production database, always back up to a separate device.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1bea7-134">безопасность</span><span class="sxs-lookup"><span data-stu-id="1bea7-134">Security</span></span>  
 <span data-ttu-id="1bea7-135">Параметр TRUSTWORTHY устанавливается в значение OFF каждый раз при создании резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-135">TRUSTWORTHY is set to OFF when a database is backed up.</span></span> <span data-ttu-id="1bea7-136">Таким образом, в новой зеркальной базе данных он всегда имеет значение OFF.</span><span class="sxs-lookup"><span data-stu-id="1bea7-136">Therefore, TRUSTWORTHY is always OFF on a new mirror database.</span></span> <span data-ttu-id="1bea7-137">Если после отработки отказа необходимо, чтобы база данных снова стала надежной, следует выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="1bea7-137">If the database needs to be trustworthy after a failover, additional setup steps are necessary.</span></span> <span data-ttu-id="1bea7-138">Дополнительные сведения см. в статье [Настройка зеркальной базы данных на использование свойства TRUSTWORTHY (Transact-SQL)](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1bea7-138">For more information, see [Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span></span>  
  
 <span data-ttu-id="1bea7-139">Сведения о включении автоматической расшифровки главного ключа базы данных в зеркальной базе данных см. в статье [Настройка зашифрованной зеркальной базы данных](set-up-an-encrypted-mirror-database.md).</span><span class="sxs-lookup"><span data-stu-id="1bea7-139">For information about enabling automatic decryption of the database master key of a mirror database, see [Set Up an Encrypted Mirror Database](set-up-an-encrypted-mirror-database.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1bea7-140">Permissions</span><span class="sxs-lookup"><span data-stu-id="1bea7-140">Permissions</span></span>  
 <span data-ttu-id="1bea7-141">Владелец базы данных или системный администратор.</span><span class="sxs-lookup"><span data-stu-id="1bea7-141">Database owner or system administrator.</span></span>  
  
##  <a name="to-prepare-an-existing-mirror-database-to-restart-mirroring"></a><a name="PrepareToRestartMirroring"></a> <span data-ttu-id="1bea7-142">Подготовка существующей зеркальной базы данных к повторному запуску зеркального отображения</span><span class="sxs-lookup"><span data-stu-id="1bea7-142">To Prepare an Existing Mirror Database to Restart Mirroring</span></span>  
 <span data-ttu-id="1bea7-143">Если зеркальное отображение было удалено, а зеркальная база данных остается в состоянии RECOVERING, то зеркальное отображение можно запустить повторно.</span><span class="sxs-lookup"><span data-stu-id="1bea7-143">If mirroring has been removed and the mirror database is still in the RECOVERING state, you can restart mirroring.</span></span>  
  
1.  <span data-ttu-id="1bea7-144">Создайте хотя бы одну резервную копию журналов основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-144">Take at least one log backup on the principal database.</span></span> <span data-ttu-id="1bea7-145">Дополнительные сведения см. в статье [Создание резервной копии журнала транзакций (SQL Server)](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="1bea7-145">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="1bea7-146">В зеркальной базе данных следует восстановить с помощью инструкции RESTORE WITH NORECOVERY все резервные копии журналов, созданные в основной базе данных с момента удаления зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-146">On the mirror database, use RESTORE WITH NORECOVERY to restore all log backups taken on the principal database since mirroring was removed.</span></span> <span data-ttu-id="1bea7-147">Дополнительные сведения см. в статье [Восстановление резервной копии журнала транзакций (SQL Server)](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1bea7-147">For more information, see [Restore a Transaction Log Backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md).</span></span>  
  
##  <a name="to-prepare-a-new-mirror-database"></a><a name="CombinedProcedure"></a> <span data-ttu-id="1bea7-148">Подготовка новой зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="1bea7-148">To Prepare a New Mirror Database</span></span>  
 <span data-ttu-id="1bea7-149">**Подготовка зеркальной базы данных**</span><span class="sxs-lookup"><span data-stu-id="1bea7-149">**To prepare a mirror database**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bea7-150">Пример этой процедуры на языке [!INCLUDE[tsql](../../includes/tsql-md.md)] см. в подразделе [Пример (Transact-SQL)](#TsqlExample)ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1bea7-150">For a [!INCLUDE[tsql](../../includes/tsql-md.md)] example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="1bea7-151">Установите соединение с основным экземпляром на сервере.</span><span class="sxs-lookup"><span data-stu-id="1bea7-151">Connect to principal server instance.</span></span>  
  
2.  <span data-ttu-id="1bea7-152">Создайте либо полную копию базы данных, либо разностную резервную копию основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-152">Create either a full database backup or a differential database backup of the principal database.</span></span>  
  
    -   [<span data-ttu-id="1bea7-153">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1bea7-153">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
    -   <span data-ttu-id="1bea7-154">[Создание разностной резервной копии базы данных (SQL Server)](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="1bea7-154">[Create a Differential Database Backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="1bea7-155">Как правило, необходимо создать хотя бы одну резервную копию журналов основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-155">Typically, you need to take at least one log backup on the principal database.</span></span> <span data-ttu-id="1bea7-156">Однако резервная копия журналов может не понадобиться, если база данных только что создана и в ней еще не было создано ни одной резервной копии журналов либо если модель восстановления только что изменена с SIMPLE на FULL.</span><span class="sxs-lookup"><span data-stu-id="1bea7-156">However, a log backup might be unnecessary, if the database has just been created and no log backup has been taken yet, or if the recovery model has just been changed from SIMPLE to FULL.</span></span>  
  
    -   [<span data-ttu-id="1bea7-157">Создание резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1bea7-157">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)  
  
4.  <span data-ttu-id="1bea7-158">Если резервная копия находится не на сетевом диске, доступном для обеих систем, то скопируйте базу данных и резервные копии журналов на компьютер, где размещен экземпляр зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="1bea7-158">Unless the backups are on a network drive that is accessible from both systems, copy the database and log backups to the system that will host the mirror server instance.</span></span>  
  
5.  <span data-ttu-id="1bea7-159">Установите соединение с зеркальным экземпляром сервера.</span><span class="sxs-lookup"><span data-stu-id="1bea7-159">Connect to mirror server instance.</span></span>  
  
6.  <span data-ttu-id="1bea7-160">С помощью инструкции RESTORE WITH NORECOVERY создайте зеркальную базу, восстановив полную резервную копию и, возможно, последнюю разностную резервную копию базы данных, на экземпляре зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="1bea7-160">Using RESTORE WITH NORECOVERY, create the mirror database by restoring the full database backup and, optionally, the most recent differential database backup, onto the mirror server instance.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1bea7-161">При восстановлении файловой группы базы данных по файловой группе следует восстановить базу данных целиком.</span><span class="sxs-lookup"><span data-stu-id="1bea7-161">If you restore the database filegroup by filegroup, be sure to restore the whole database.</span></span>  
  
    -   [<span data-ttu-id="1bea7-162">Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1bea7-162">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](../../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md)  
  
    -   <span data-ttu-id="1bea7-163">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) и [Аргументы инструкции RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1bea7-163">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) and [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span></span>  
  
7.  <span data-ttu-id="1bea7-164">С помощью инструкции RESTORE WITH NORECOVERY примените все необработанные резервные копии и резервные копии журналов на зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-164">Using RESTORE WITH NORECOVERY, apply any outstanding log backup or backups to the mirror database.</span></span>  
  
    -   [<span data-ttu-id="1bea7-165">Восстановление резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1bea7-165">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="1bea7-166">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1bea7-166">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="1bea7-167">Перед тем как начать сеанс зеркального отображения базы данных, нужно создать зеркальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-167">Before you can start a database mirroring session, you must create the mirror database.</span></span> <span data-ttu-id="1bea7-168">Это нужно сделать непосредственно перед запуском сеанса зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="1bea7-168">You should do this just before starting the mirroring session.</span></span>  
  
 <span data-ttu-id="1bea7-169">В этом примере используется образец базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , в котором по умолчанию применяется простая модель восстановления.</span><span class="sxs-lookup"><span data-stu-id="1bea7-169">This example uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database, which uses the simple recovery model by default.</span></span>  
  
1.  <span data-ttu-id="1bea7-170">Чтобы включить зеркальное отображение базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , переключите базу данных на модель полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="1bea7-170">To use database mirroring with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, modify it to use the full recovery model:</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
    SET RECOVERY FULL;  
    GO  
    ```  
  
2.  <span data-ttu-id="1bea7-171">После изменения модели восстановления с SIMPLE на FULL создайте полную резервную копию, с помощью которой затем можно будет создать зеркальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-171">After modifying the recovery model of the database from SIMPLE to FULL, create a full backup, which can be used to create the mirror database.</span></span> <span data-ttu-id="1bea7-172">Так как модель восстановления только что была изменена, указывается параметр WITH FORMAT для создания нового набора носителей.</span><span class="sxs-lookup"><span data-stu-id="1bea7-172">Because the recovery model has just been changed, the WITH FORMAT option is specified to create a new media set.</span></span> <span data-ttu-id="1bea7-173">Это полезно для отделения резервных копий при модели полного восстановления от резервных копий, сделанных при простой модели восстановления.</span><span class="sxs-lookup"><span data-stu-id="1bea7-173">This is useful to separate the backups under the full recovery model from any previous backups made under the simple recovery model.</span></span> <span data-ttu-id="1bea7-174">В данном примере файл резервной копии (`C:\AdventureWorks.bak`) создается на том же диске, на котором находится база данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-174">For the purpose of this example, the backup file (`C:\AdventureWorks.bak`) is created on the same drive as the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1bea7-175">Для производственной базы данных необходимо всегда делать резервные копии на разные устройства.</span><span class="sxs-lookup"><span data-stu-id="1bea7-175">For a production database, you should always back up to a separate device.</span></span>  
  
     <span data-ttu-id="1bea7-176">На экземпляре основного сервера ( `PARTNERHOST1`) создайте полную резервную копию основной базы данных следующим образом.</span><span class="sxs-lookup"><span data-stu-id="1bea7-176">On the principal server instance (on `PARTNERHOST1`), create a full backup of the principal database as follows:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
        WITH FORMAT  
    GO  
    ```  
  
3.  <span data-ttu-id="1bea7-177">Создайте полную резервную копию на зеркальном сервере.</span><span class="sxs-lookup"><span data-stu-id="1bea7-177">Copy the full backup to the mirror server.</span></span>  
  
4.  <span data-ttu-id="1bea7-178">Восстановите полную резервную копию на экземпляр зеркального сервера с помощью инструкции RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1bea7-178">Using RESTORE WITH NORECOVERY, restore the full backup onto the mirror server instance.</span></span> <span data-ttu-id="1bea7-179">Команда восстановления зависит от того, идентичны ли пути основной и зеркальной баз данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-179">The restore command depends on whether the paths of principal and mirror databases are identical.</span></span>  
  
    -   <span data-ttu-id="1bea7-180">**Если пути идентичны:**</span><span class="sxs-lookup"><span data-stu-id="1bea7-180">**If the paths are identical:**</span></span>  
  
         <span data-ttu-id="1bea7-181">на экземпляре зеркального сервера ( `PARTNERHOST5`) выполните восстановление из полной резервной копии следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1bea7-181">On the mirror server instance (on `PARTNERHOST5`), restore the full backup as follows:</span></span>  
  
        ```  
        RESTORE DATABASE AdventureWorks   
            FROM DISK = 'C:\AdventureWorks.bak'   
            WITH NORECOVERY  
        GO  
        ```  
  
    -   <span data-ttu-id="1bea7-182">**Если пути отличаются:**</span><span class="sxs-lookup"><span data-stu-id="1bea7-182">**If the paths differ:**</span></span>  
  
         <span data-ttu-id="1bea7-183">Если путь зеркальной базы данных отличается от пути основной базы данных (например, отличаются имена дисков), то при создании зеркальной базы данных в операцию восстановления нужно будет добавить предложение MOVE.</span><span class="sxs-lookup"><span data-stu-id="1bea7-183">If the path of the mirror database differs from the path of the principal database (for instance, their drive letters differ), creating the mirror database requires that the restore operation include a MOVE clause.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="1bea7-184">Если отличаются пути основной и зеркальной баз данных, то добавлять файлы нельзя.</span><span class="sxs-lookup"><span data-stu-id="1bea7-184">If the path names of the principal and mirror databases differ, you cannot add a file.</span></span> <span data-ttu-id="1bea7-185">Это происходит потому, что при появлении в журнале записи об операции добавления файла экземпляр зеркального сервера пытается поместить новый файл в местоположение, указанное для основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-185">This is because on receiving the log for the add file operation, the mirror server instance attempts to place the new file in the location used by the principal database.</span></span>  
  
         <span data-ttu-id="1bea7-186">Например, следующая команда восстанавливает резервную копию основной базы данных, которая находится в каталоге "C:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Data\", в другое расположение — "D:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Dat`a\`", где должна находиться зеркальная база данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-186">For example, the following command restores a backup of a principal database residing in C:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Data\ to a different location, D:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Dat`a\`, where the mirror database is to reside.</span></span>  
  
        ```  
        RESTORE DATABASE AdventureWorks  
           FROM DISK='C:\AdventureWorks.bak'  
           WITH NORECOVERY,   
              MOVE 'AdventureWorks_Data' TO   
                 'D:\Program Files\Microsoft SQL Server\MSSQL.n\MSSQL\Data\AdventureWorks_Data.mdf',   
              MOVE 'AdventureWorks_Log' TO  
                 'D:\Program Files\Microsoft SQL Server\MSSQL.n\MSSQL\Data\AdventureWorks_Log.ldf';  
        GO  
        ```  
  
5.  <span data-ttu-id="1bea7-187">После создания полной резервной копии обязательно создается резервная копия журналов для основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="1bea7-187">After you create the full backup, you must create a log backup on the principal database.</span></span> <span data-ttu-id="1bea7-188">В следующем примере с помощью инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] создается резервная копия журналов для того же файла, который использовался в предыдущей полной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="1bea7-188">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement backs up the log to the same file used by the preceding full backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="1bea7-189">Перед тем как приступать к зеркальному отображению, необходимо применить требуемую резервную копию журналов (и все последующие резервные копии журналов).</span><span class="sxs-lookup"><span data-stu-id="1bea7-189">Before you can start mirroring, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="1bea7-190">Например, следующая инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] восстанавливает первый журнал из `C:\AdventureWorks.bak`:</span><span class="sxs-lookup"><span data-stu-id="1bea7-190">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores the first log from `C:\AdventureWorks.bak`:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="1bea7-191">Если перед запуском зеркального отображения создавались дополнительные резервные копии журналов, то необходимо последовательно восстановить их на зеркальном сервере с параметром WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1bea7-191">If any additional log backups occur before you start mirroring, you must also restore all of those log backups, in sequence, to the mirror server using WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="1bea7-192">Например, следующая инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] восстанавливает два дополнительных журнала из `C:\AdventureWorks.bak`:</span><span class="sxs-lookup"><span data-stu-id="1bea7-192">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores two additional logs from `C:\AdventureWorks.bak`:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=2, NORECOVERY  
    GO  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=3, NORECOVERY  
    GO  
    ```  
  
 <span data-ttu-id="1bea7-193">Подробный пример настройки зеркального отображения базы данных, в котором показана настройка защиты, подготовка зеркальной базы данных, настройка партнеров и добавление следящего сервера, см. в статье [Настройка зеркального отображения базы данных (SQL Server)](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1bea7-193">For a complete example of setting up database mirroring, showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-preparing-a-mirror-database"></a><a name="FollowUp"></a> <span data-ttu-id="1bea7-194">Дальнейшие действия. После подготовки зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="1bea7-194">Follow Up: After Preparing a Mirror Database</span></span>  
  
1.  <span data-ttu-id="1bea7-195">Если были сняты какие-либо дополнительные резервные копии журналов с момента самой последней операции RESTORE LOG, то необходимо вручную применить каждую дополнительную резервную копию с параметром RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1bea7-195">If any additional log backups have been taken since your most recent RESTORE LOG operation, you must manually apply every additional log backup, using RESTORE WITH NORECOVERY.</span></span>  
  
2.  <span data-ttu-id="1bea7-196">Запустите сеанс зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="1bea7-196">Start the mirroring session.</span></span> <span data-ttu-id="1bea7-197">Дополнительные сведения см. в статье [Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)](establish-database-mirroring-session-windows-authentication.md) или [Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (Transact-SQL)](database-mirroring-establish-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="1bea7-197">For more information, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) or [Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md).</span></span>  
  
3.  <span data-ttu-id="1bea7-198">Если задание резервного копирования в основной базе данных отключено, то необходимо снова включить его.</span><span class="sxs-lookup"><span data-stu-id="1bea7-198">If you disabled the backup job on the principal database, reenable the job.</span></span>  
  
4.  <span data-ttu-id="1bea7-199">Если для базы данных после отработки отказа с переходом на другой ресурс требуется доверие, это потребует дополнительных действий по настройке после начала зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="1bea7-199">If the database needs to be trustworthy after a failover, extra setup steps are necessary after mirroring begins.</span></span> <span data-ttu-id="1bea7-200">Дополнительные сведения см. в статье [Настройка зеркальной базы данных на использование свойства TRUSTWORTHY (Transact-SQL)](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1bea7-200">For more information, see [Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1bea7-201">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="1bea7-201">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1bea7-202">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1bea7-202">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="1bea7-203">Восстановление резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1bea7-203">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="1bea7-204">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="1bea7-204">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="1bea7-205">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1bea7-205">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="1bea7-206">Настройка зашифрованной зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="1bea7-206">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
-   [<span data-ttu-id="1bea7-207">Настройка зеркальной базы данных на использование свойства TRUSTWORTHY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1bea7-207">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="1bea7-208">См. также:</span><span class="sxs-lookup"><span data-stu-id="1bea7-208">See Also</span></span>  
 <span data-ttu-id="1bea7-209">[Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1bea7-209">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="1bea7-210">[Безопасность транспорта для зеркального отображения базы данных и группы доступности AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="1bea7-210">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="1bea7-211">[Настройка зеркального отображения базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1bea7-211">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="1bea7-212">[Создание резервных копий и восстановление полнотекстовых каталогов и индексов](../../relational-databases/indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="1bea7-212">[Back Up and Restore Full-Text Catalogs and Indexes](../../relational-databases/indexes/indexes.md) </span></span>  
 <span data-ttu-id="1bea7-213">[Зеркальное отображение баз данных и полнотекстовые каталоги (SQL Server)](database-mirroring-and-full-text-catalogs-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1bea7-213">[Database Mirroring and Full-Text Catalogs &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md) </span></span>  
 <span data-ttu-id="1bea7-214">[Зеркальное отображение и репликация баз данных (SQL Server)](database-mirroring-and-replication-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1bea7-214">[Database Mirroring and Replication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span></span>  
 <span data-ttu-id="1bea7-215">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1bea7-215">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="1bea7-216">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1bea7-216">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="1bea7-217">Аргументы инструкции RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1bea7-217">RESTORE Arguments &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-arguments-transact-sql)  
  
  
