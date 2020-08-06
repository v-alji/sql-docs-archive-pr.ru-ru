---
title: Общие сведения о резервном копировании (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- tables [SQL Server], backing up data
- backups [SQL Server]
- database backups [SQL Server]
- backup types [SQL Server]
- data backups [SQL Server]
- backing up tables [SQL Server]
- database restores [SQL Server], backups
- backing up [SQL Server], about backing up
- restoring [SQL Server], backup types
- backups [SQL Server], about
- backups [SQL Server], table-level backups unsupported
ms.assetid: 09a6e0c2-d8fd-453f-9aac-4ff24a97dc1f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60fbd0341c4e29c6f98cc4d5fe5a2cfabc9b703f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668947"
---
# <a name="backup-overview-sql-server"></a><span data-ttu-id="f112a-102">Backup Overview (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-102">Backup Overview (SQL Server)</span></span>
  <span data-ttu-id="f112a-103">В этом разделе представлены сведения о компоненте резервного копирования [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f112a-103">This topic introduces the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup component.</span></span> <span data-ttu-id="f112a-104">Резервное копирование базы данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеет важное значение для защиты данных.</span><span class="sxs-lookup"><span data-stu-id="f112a-104">Backing up your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is essential for protecting your data.</span></span> <span data-ttu-id="f112a-105">Здесь представлено описание типов резервных копий и ограничений резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f112a-105">This discussion covers backup types, and backup restrictions.</span></span> <span data-ttu-id="f112a-106">В рамках данной темы также рассмотрены устройства резервного копирования и носители данных резервных копий в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f112a-106">The topic also introduces [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup devices and backup media.</span></span>  
  
 <span data-ttu-id="f112a-107">**В этом разделе.**</span><span class="sxs-lookup"><span data-stu-id="f112a-107">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="f112a-108">Компоненты и основные понятия</span><span class="sxs-lookup"><span data-stu-id="f112a-108">Components and Concepts</span></span>](#TermsAndDefinitions)  
  
-   [<span data-ttu-id="f112a-109">Сжатие резервных копий</span><span class="sxs-lookup"><span data-stu-id="f112a-109">Backup Compression</span></span>](#BackupCompression)  
  
-   [<span data-ttu-id="f112a-110">Ограничения на операции резервного копирования в SQL Server</span><span class="sxs-lookup"><span data-stu-id="f112a-110">Restrictions on Backup Operations in SQL Server</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="f112a-111">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f112a-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="components-and-concepts"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="f112a-112">Компоненты и основные понятия</span><span class="sxs-lookup"><span data-stu-id="f112a-112">Components and Concepts</span></span>  
 <span data-ttu-id="f112a-113">создание резервных копий</span><span class="sxs-lookup"><span data-stu-id="f112a-113">back up [verb]</span></span>  
 <span data-ttu-id="f112a-114">Копирование данных или записей журнала из базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или журнала ее транзакций на устройство для резервного копирования, например на диск, на котором создается резервная копия данных или журнала.</span><span class="sxs-lookup"><span data-stu-id="f112a-114">Copies the data or log records from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database or its transaction log to a backup device, such as a disk, to create a data backup or log backup.</span></span>  
  
 <span data-ttu-id="f112a-115">резервная копия</span><span class="sxs-lookup"><span data-stu-id="f112a-115">backup [noun]</span></span>  
 <span data-ttu-id="f112a-116">Копия данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , используемая для восстановления данных после возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="f112a-116">A copy of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data that can be used to restore and recover the data after a failure.</span></span> <span data-ttu-id="f112a-117">Резервная копия данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] создается на уровне базы данных для одного или нескольких файлов или групп файлов.</span><span class="sxs-lookup"><span data-stu-id="f112a-117">A backup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data is created at the level of a database or one or more of its files or filegroups.</span></span> <span data-ttu-id="f112a-118">Нельзя создать резервные копии на уровне таблиц.</span><span class="sxs-lookup"><span data-stu-id="f112a-118">Table-level backups cannot be created.</span></span> <span data-ttu-id="f112a-119">Кроме резервной копии данных модель полного восстановления требует создания резервной копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="f112a-119">In addition to data backups, the full recovery model requires creating backups of the transaction log.</span></span>  
  
 [<span data-ttu-id="f112a-120">модель восстановления</span><span class="sxs-lookup"><span data-stu-id="f112a-120">recovery model</span></span>](recovery-models-sql-server.md)  
 <span data-ttu-id="f112a-121">Свойство базы данных, с помощью которого выполняется управление обслуживанием журналов транзакций в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f112a-121">A database property that controls transaction log maintenance on a database.</span></span> <span data-ttu-id="f112a-122">Существует три модели восстановления: простая модель восстановления, модель полного восстановления и модель восстановления с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="f112a-122">Three recovery models exist: simple, full, and bulk-logged.</span></span> <span data-ttu-id="f112a-123">Модель восстановления базы данных определяет требования к резервному копированию и восстановлению.</span><span class="sxs-lookup"><span data-stu-id="f112a-123">The recovery model of database determines its backup and restore requirements.</span></span>  
  
 [<span data-ttu-id="f112a-124">восстановление</span><span class="sxs-lookup"><span data-stu-id="f112a-124">restore</span></span>](restore-and-recovery-overview-sql-server.md)  
 <span data-ttu-id="f112a-125">Многоэтапный процесс, в ходе которого все данные и страницы журнала копируются из указанной резервной копии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в определенную базу данных, а затем выполняется накат всех фиксированных транзакций, записанных в резервной копии журнала, путем внесения новых данных на основе зарегистрированных изменений.</span><span class="sxs-lookup"><span data-stu-id="f112a-125">A multi-phase process that copies all the data and log pages from a specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup to a specified database, and then rolls forward all the transactions that are logged in the backup by applying logged changes to bring the data forward in time.</span></span>  
  
 <span data-ttu-id="f112a-126">**Типы резервных копий**</span><span class="sxs-lookup"><span data-stu-id="f112a-126">**Types of Backups**</span></span>  
  
 [<span data-ttu-id="f112a-127">резервная копия, предназначенная только для копирования</span><span class="sxs-lookup"><span data-stu-id="f112a-127">copy-only backup</span></span>](copy-only-backups-sql-server.md)  
 <span data-ttu-id="f112a-128">Специальная резервная копия, независимая от обычной последовательности резервных копий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f112a-128">A special-use backup that is independent of the regular sequence of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span>  
  
 <span data-ttu-id="f112a-129">резервное копирование данных</span><span class="sxs-lookup"><span data-stu-id="f112a-129">data backup</span></span>  
 <span data-ttu-id="f112a-130">Резервная копия данных всей базы данных (резервная копия базы данных), части базы данных (частичная резервная копия) или набора файлов данных или файловых групп (резервная копия файлов).</span><span class="sxs-lookup"><span data-stu-id="f112a-130">A backup of data in a complete database (a database backup), a partial database (a partial backup), or a set of data files or filegroups (a file backup).</span></span>  
  
 [<span data-ttu-id="f112a-131">резервное копирование базы данных</span><span class="sxs-lookup"><span data-stu-id="f112a-131">database backup</span></span>](full-database-backups-sql-server.md)  
 <span data-ttu-id="f112a-132">Резервная копия базы данных.</span><span class="sxs-lookup"><span data-stu-id="f112a-132">A backup of a database.</span></span> <span data-ttu-id="f112a-133">Полные резервные копии базы данных отображают состояние всей базы данных на момент завершения резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f112a-133">Full database backups represent the whole database at the time the backup finished.</span></span> <span data-ttu-id="f112a-134">Разностные резервные копии базы данных содержат только изменения базы данных с момента последнего полного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f112a-134">Differential database backups contain only changes made to the database since its most recent full database backup.</span></span>  
  
 [<span data-ttu-id="f112a-135">разностная резервная копия</span><span class="sxs-lookup"><span data-stu-id="f112a-135">differential backup</span></span>](full-database-backups-sql-server.md)  
 <span data-ttu-id="f112a-136">Резервная копия, основанная на последнем полном резервировании частичной базы данных или набора файлов данных или групп файлов ( *базовая копия для разностного копирования*), которая содержит только добавочные данные, измененные по сравнению с базовой копией для разностного копирования.</span><span class="sxs-lookup"><span data-stu-id="f112a-136">A data backup that is based on the latest full backup of a complete or partial database or a set of data files or filegroups (the *differential base*) and that contains only the data extents that have changed since the differential base.</span></span>  
  
 <span data-ttu-id="f112a-137">Частичная разностная резервная копия, включающая только те экстенты данных, которые изменились в файловых группах с момента создания предыдущей частичной резервной копии, называется основой для разностной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="f112a-137">A differential partial backup records only the data extents that have changed in the filegroups since the previous partial backup, known as the base for the differential.</span></span>  
  
 <span data-ttu-id="f112a-138">полная резервная копия</span><span class="sxs-lookup"><span data-stu-id="f112a-138">full backup</span></span>  
 <span data-ttu-id="f112a-139">Резервная копия, которая содержит все данные заданной базы данных или наборов файлов или файловых групп, а также журналов для обеспечения возможности последующего восстановления этих данных.</span><span class="sxs-lookup"><span data-stu-id="f112a-139">A data backup that contains all the data in a specific database or set of filegroups or files, and also enough log to allow for recovering that data.</span></span>  
  
 [<span data-ttu-id="f112a-140">резервная копия журналов</span><span class="sxs-lookup"><span data-stu-id="f112a-140">log backup</span></span>](transaction-log-backups-sql-server.md)  
 <span data-ttu-id="f112a-141">Резервная копия журналов транзакций, включающая все записи журнала, не входившие в предыдущую резервную копию журналов.</span><span class="sxs-lookup"><span data-stu-id="f112a-141">A backup of transaction logs that includes all log records that were not backed up in a previous log backup.</span></span> <span data-ttu-id="f112a-142">(модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="f112a-142">(full recovery model)</span></span>  
  
 [<span data-ttu-id="f112a-143">резервная копия файлов</span><span class="sxs-lookup"><span data-stu-id="f112a-143">file backup</span></span>](full-file-backups-sql-server.md)  
 <span data-ttu-id="f112a-144">Резервная копия одного или нескольких файлов или файловых групп базы данных.</span><span class="sxs-lookup"><span data-stu-id="f112a-144">A backup of one or more database files or filegroups.</span></span>  
  
 [<span data-ttu-id="f112a-145">частичная резервная копия</span><span class="sxs-lookup"><span data-stu-id="f112a-145">partial backup</span></span>](partial-backups-sql-server.md)  
 <span data-ttu-id="f112a-146">Содержит данные только из некоторых файловых групп базы данных, включая данные в первичной файловой группе, все файловые группы, доступные для чтения-записи, а также любые дополнительно указанные файлы, доступные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f112a-146">Contains data from only some of the filegroups in a database, including the data in the primary filegroup, every read/write filegroup, and any optionally-specified read-only files.</span></span>  
  
 <span data-ttu-id="f112a-147">**Условия и определения носителей резервных копий**</span><span class="sxs-lookup"><span data-stu-id="f112a-147">**Backup Media Terms and Definitions**</span></span>  
  
 [<span data-ttu-id="f112a-148">устройство резервного копирования</span><span class="sxs-lookup"><span data-stu-id="f112a-148">backup device</span></span>](backup-devices-sql-server.md)  
 <span data-ttu-id="f112a-149">Диск или ленточное устройство, на которые записываются резервные копии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для последующего восстановления.</span><span class="sxs-lookup"><span data-stu-id="f112a-149">A disk or tape device to which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups are written and from which they can be restored.</span></span> <span data-ttu-id="f112a-150">Резервные копии SQL Server можно также записать в службу хранилища BLOB-объектов Azure, а формат **URL-адреса** используется, чтобы указать назначение и имя файла резервной копии.</span><span class="sxs-lookup"><span data-stu-id="f112a-150">SQL Server backups can also be written to an Azure Blob storage service, and **URL** format is used to specify the destination and the name of the backup file..</span></span> <span data-ttu-id="f112a-151">Дополнительные сведения см. в статье [Резервное копирование и восстановление SQL Server с помощью службы хранилищ больших двоичных объектов Windows Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="f112a-151">For more information, see [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 [<span data-ttu-id="f112a-152">носитель данных резервной копии</span><span class="sxs-lookup"><span data-stu-id="f112a-152">backup media</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="f112a-153">Один или несколько наборов дисков или ленточных устройств, на которые записывается резервная копия.</span><span class="sxs-lookup"><span data-stu-id="f112a-153">One or more tapes or disk files to which one or more backup have been written.</span></span>  
  
 [<span data-ttu-id="f112a-154">резервный набор данных</span><span class="sxs-lookup"><span data-stu-id="f112a-154">backup set</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="f112a-155">Содержимое резервной копии добавляется на набор носителей при успешной операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f112a-155">The backup content that is added to a media set by a successful backup operation.</span></span>  
  
 [<span data-ttu-id="f112a-156">семейство носителей</span><span class="sxs-lookup"><span data-stu-id="f112a-156">media family</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="f112a-157">Резервные копии, созданные на одном устройстве без зеркального отображения или на наборе устройств с зеркальным отображением в наборе носителей</span><span class="sxs-lookup"><span data-stu-id="f112a-157">Backups created on a single nonmirrored device or a set of mirrored devices in a media set</span></span>  
  
 [<span data-ttu-id="f112a-158">набор носителей</span><span class="sxs-lookup"><span data-stu-id="f112a-158">media set</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="f112a-159">Упорядоченный набор носителей данных резервной копии в виде определенного количества ленточных устройств или дисков, на которые может быть записана одна или несколько операций резервного копирования, с использованием фиксированного типа и номера устройств резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f112a-159">An ordered collection of backup media, tapes or disk files, to which one or more backup operations have written using a fixed type and number of backup devices.</span></span>  
  
 [<span data-ttu-id="f112a-160">зеркальный набор носителей</span><span class="sxs-lookup"><span data-stu-id="f112a-160">mirrored media set</span></span>](mirrored-backup-media-sets-sql-server.md)  
 <span data-ttu-id="f112a-161">Составные копии (зеркала) набора носителей данных резервных копий.</span><span class="sxs-lookup"><span data-stu-id="f112a-161">Multiple copies (mirrors) of a media set.</span></span>  
  
##  <a name="backup-compression"></a><a name="BackupCompression"></a><span data-ttu-id="f112a-162">Сжатие резервных копий</span><span class="sxs-lookup"><span data-stu-id="f112a-162">Backup Compression</span></span>  
 [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="f112a-163">и более поздние версии поддерживают сжатие резервных копий, а [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] и более поздние версии позволяют восстановить сжатые резервные копии.</span><span class="sxs-lookup"><span data-stu-id="f112a-163">and later versions support compressing backups, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions can restore a compressed backup.</span></span> <span data-ttu-id="f112a-164">Дополнительные сведения см. в разделе [Сжатие резервных копий (SQL Server)](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f112a-164">For more information, see [Backup Compression &#40;SQL Server&#41;](backup-compression-sql-server.md).</span></span>  
  
##  <a name="restrictions-on-backup-operations-in-sql-server"></a><a name="Restrictions"></a><span data-ttu-id="f112a-165">Ограничения для операций резервного копирования в SQL Server</span><span class="sxs-lookup"><span data-stu-id="f112a-165">Restrictions on Backup Operations in SQL Server</span></span>  
 <span data-ttu-id="f112a-166">Резервное копирование может выполняться, если база данных находится в режиме «в сети» и используется.</span><span class="sxs-lookup"><span data-stu-id="f112a-166">Backup can occur while the database is online and being used.</span></span> <span data-ttu-id="f112a-167">Однако действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="f112a-167">However, the following restrictions exist.</span></span>  
  
### <a name="offline-data-cannot-be-backed-up"></a><span data-ttu-id="f112a-168">Нельзя создать резервную копию данных, находящихся в режиме «вне сети»</span><span class="sxs-lookup"><span data-stu-id="f112a-168">Offline Data Cannot Be Backed Up</span></span>  
 <span data-ttu-id="f112a-169">Любая операция резервного копирования, которая явно или неявно ссылается на данные, находящиеся в режиме «вне сети», завершается неудачей.</span><span class="sxs-lookup"><span data-stu-id="f112a-169">Any backup operation that implicitly or explicitly references data that is offline fails.</span></span> <span data-ttu-id="f112a-170">Ниже следуют некоторые наиболее распространенные примеры этого.</span><span class="sxs-lookup"><span data-stu-id="f112a-170">Some typical examples include the following:</span></span>  
  
-   <span data-ttu-id="f112a-171">Запрашивается создание полной резервной копии, но одна файловая группа в базе данных находится в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="f112a-171">You request a full database backup, but one filegroup of the database is offline.</span></span> <span data-ttu-id="f112a-172">Операция завершается неудачно, так как в полное резервное копирование неявно включены все файловые группы.</span><span class="sxs-lookup"><span data-stu-id="f112a-172">Because all filegroups are implicitly included in a full database backup, this operation fails.</span></span>  
  
     <span data-ttu-id="f112a-173">Чтобы создать резервную копию этой базы данных, можно воспользоваться созданием резервных копий файлов (или файловых групп) и задать только те файловые группы, которые находятся в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="f112a-173">To back up this database, you can use a file backup and specify only the filegroups that are online.</span></span>  
  
-   <span data-ttu-id="f112a-174">Запрашивается частичное резервное копирование, но файловые группы, доступные для чтения и записи, находятся в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="f112a-174">You request a partial backup, but a read/write filegroup is offline.</span></span> <span data-ttu-id="f112a-175">Операция завершается неудачей, потому что для частичного резервного копирования запрашиваются все файловые группы, доступные для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="f112a-175">Because all read/write filegroups are required for a partial backup, the operation fails.</span></span>  
  
-   <span data-ttu-id="f112a-176">Запрашивается резервное копирование заданных файлов, но один из файлов находится в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="f112a-176">You request a file backup of specific files, but one of the files is not online.</span></span> <span data-ttu-id="f112a-177">Операция завершается неудачей.</span><span class="sxs-lookup"><span data-stu-id="f112a-177">The operation fails.</span></span> <span data-ttu-id="f112a-178">Чтобы создать резервную копию файлов, находящихся в режиме «в сети», устраните из списка файлы, находящиеся в режиме «вне сети», и повторите операцию.</span><span class="sxs-lookup"><span data-stu-id="f112a-178">To back up the online files, you can omit the offline file from the file list and repeat the operation.</span></span>  
  
 <span data-ttu-id="f112a-179">Обычно резервное копирование журнала проходит успешно, даже если один или несколько файлов данных недоступны.</span><span class="sxs-lookup"><span data-stu-id="f112a-179">Typically, a log backup succeeds even if one or more data files are unavailable.</span></span> <span data-ttu-id="f112a-180">Однако если какой-нибудь файл содержит массовые изменения, сделанные в модели восстановления с неполным протоколированием, то для успешного резервного копирования необходимо, чтобы все файлы находились в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="f112a-180">However, if any file contains bulk-logged changes made under the bulk-logged recovery model, all the files must be online for the backup to succeed.</span></span>  
  
### <a name="concurrency-restrictions-during-backup"></a><span data-ttu-id="f112a-181">Ограничения параллелизма во время резервного копирования</span><span class="sxs-lookup"><span data-stu-id="f112a-181">Concurrency Restrictions During Backup</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f112a-182">использует процесс резервного копирования в сети, что позволяет создавать резервную копию базы данных во время ее использования.</span><span class="sxs-lookup"><span data-stu-id="f112a-182">uses an online backup process to allow for a database backup while the database is still being used.</span></span> <span data-ttu-id="f112a-183">Во время резервного копирования можно производить большинство операций. Например, во время создания резервной копии разрешены инструкции INSERT, UPDATE и DELETE.</span><span class="sxs-lookup"><span data-stu-id="f112a-183">During a backup, most operations are possible; for example, INSERT, UPDATE, or DELETE statements are allowed during a backup operation.</span></span> <span data-ttu-id="f112a-184">При попытке приступить к выполнению операции резервного копирования во время создания или удаления файла базы данных выполнение операции резервного копирования будет отложено до завершения создания или удаления либо до истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="f112a-184">However, if you try to start a backup operation while a database file is being created or deleted, the backup operation waits until the create or delete operation is finished or the backup times out.</span></span>  
  
 <span data-ttu-id="f112a-185">Следующие операции запрещены во время создания резервной копии базы данных или журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="f112a-185">Operations that cannot run during a database backup or transaction log backup include the following:</span></span>  
  
-   <span data-ttu-id="f112a-186">Операции управления файлами, такие как инструкция ALTER DATABASE с параметром ADD FILE или с параметром REMOVE FILE.</span><span class="sxs-lookup"><span data-stu-id="f112a-186">File-management operations such as the ALTER DATABASE statement with either the ADD FILE or REMOVE FILE options.</span></span>  
  
-   <span data-ttu-id="f112a-187">Операции сжатия базы данных или файла.</span><span class="sxs-lookup"><span data-stu-id="f112a-187">Shrink database or shrink file operations.</span></span> <span data-ttu-id="f112a-188">Сюда же включены операции автоматического сжатия.</span><span class="sxs-lookup"><span data-stu-id="f112a-188">This includes auto-shrink operations.</span></span>  
  
-   <span data-ttu-id="f112a-189">При попытке создать или удалить файл базы данных во время выполнения операции резервного копирования, создание или удаление завершится неудачно.</span><span class="sxs-lookup"><span data-stu-id="f112a-189">If you try to create or delete a database file while a backup operation is in progress, the create or delete operation fails.</span></span>  
  
 <span data-ttu-id="f112a-190">Если операция резервного копирования перекрывается операцией сжатия или управления файлами, то возникает конфликт.</span><span class="sxs-lookup"><span data-stu-id="f112a-190">If a backup operation overlaps with a file-management operation or shrink operation, a conflict occurs.</span></span> <span data-ttu-id="f112a-191">Независимо от того, какая из конфликтующих операций начата первой, вторая операция ждет истечения времени ожидания первой (оно зависит от параметров сеанса). Если разблокировка происходит до истечения времени ожидания, работа второй операции продолжается.</span><span class="sxs-lookup"><span data-stu-id="f112a-191">Regardless of which of the conflicting operation began first, the second operation waits for the lock set by the first operation to time out. (The time-out period is controlled by a session time-out setting.) If the lock is released during the time-out period, the second operation continues.</span></span> <span data-ttu-id="f112a-192">Если разблокировки за этот период не происходит, вторая операция заканчивается неудачно.</span><span class="sxs-lookup"><span data-stu-id="f112a-192">If the lock times out, the second operation fails.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f112a-193">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f112a-193">Related Tasks</span></span>  
 <span data-ttu-id="f112a-194">**Работа с устройствами резервного копирования и носителями резервных копий**</span><span class="sxs-lookup"><span data-stu-id="f112a-194">**To work with backup devices and backup media**</span></span>  
  
-   [<span data-ttu-id="f112a-195">Определение логического устройства резервного копирования для дискового файла (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-195">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="f112a-196">Определение логического устройства резервного копирования для ленточного накопителя (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-196">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="f112a-197">Указание в качестве назначения резервного копирования диска или ленты (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-197">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="f112a-198">Удаление устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-198">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="f112a-199">Назначение срока хранения резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-199">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="f112a-200">Просмотр содержимого ленты или файла резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-200">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="f112a-201">Просмотр файлов данных и журналов в резервном наборе данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-201">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="f112a-202">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-202">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="f112a-203">Восстановление резервной копии с устройства (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-203">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
-   [<span data-ttu-id="f112a-204">Руководство. Резервное копирование и восстановление SQL Server с помощью службы хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="f112a-204">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
 <span data-ttu-id="f112a-205">**Создание задания резервного копирования**</span><span class="sxs-lookup"><span data-stu-id="f112a-205">**To create a backup**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f112a-206">Для создания частичной резервной копии или резервной копии только для копирования используется инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) с параметром PARTIAL или COPY_ONLY.</span><span class="sxs-lookup"><span data-stu-id="f112a-206">For partial or copy-only backups, you must use the [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) statement with the PARTIAL or COPY_ONLY option, respectively.</span></span>  
  
-   [<span data-ttu-id="f112a-207">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-207">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="f112a-208">Создание резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-208">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="f112a-209">Резервное копирование файлов и файловых групп (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-209">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="f112a-210">Создание разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-210">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="f112a-211">Создание резервной копии журнала транзакций при повреждении базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-211">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
-   [<span data-ttu-id="f112a-212">Включение или отключение вычисления контрольных сумм резервных копий во время резервного копирования или восстановления (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-212">Enable or Disable Backup Checksums During Backup or Restore &#40;SQL Server&#41;</span></span>](enable-or-disable-backup-checksums-during-backup-or-restore-sql-server.md)  
  
-   [<span data-ttu-id="f112a-213">Определение, продолжает ли операция резервного копирования или восстановления работу после возникновения ошибки (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-213">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error &#40;SQL Server&#41;</span></span>](specify-if-backup-or-restore-continues-or-stops-after-error.md)  
  
-   [<span data-ttu-id="f112a-214">Использование регулятора ресурсов для ограничения загрузки ЦП при сжатии резервной копии (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f112a-214">Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;</span></span>](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)  
  
-   [<span data-ttu-id="f112a-215">Руководство. Резервное копирование и восстановление SQL Server с помощью службы хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="f112a-215">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="f112a-216">См. также:</span><span class="sxs-lookup"><span data-stu-id="f112a-216">See Also</span></span>  
 <span data-ttu-id="f112a-217">[Резервное копирование и восстановление баз данных SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="f112a-217">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="f112a-218">[Обзор процессов восстановления (SQL Server)](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f112a-218">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="f112a-219">[Планы обслуживания](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="f112a-219">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 <span data-ttu-id="f112a-220">[Журнал транзакций (SQL Server)](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f112a-220">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="f112a-221">Модели восстановления (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f112a-221">Recovery Models &#40;SQL Server&#41;</span></span>](recovery-models-sql-server.md)  
  
  
