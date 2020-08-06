---
title: Архивация базы данных, страница "Параметры носителя" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- swb.backupdatabase.mediaoptions.f1
- sql12.swb.backupdatabase.mediaoptions.f1
ms.assetid: eff36228-710c-4ed5-9af5-95859575dc0f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cd09eb091a7f488f891bc2e69d19ad039b65e065
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735381"
---
# <a name="back-up-database-media-options-page"></a><span data-ttu-id="c033a-102">Резервное копирование базы данных (страница «Параметры носителя»)</span><span class="sxs-lookup"><span data-stu-id="c033a-102">Back Up Database (Media Options Page)</span></span>
  <span data-ttu-id="c033a-103">На странице  **Параметры носителя** диалогового окна **Резервное копирование базы данных** можно просмотреть или изменить параметры носителя базы данных.</span><span class="sxs-lookup"><span data-stu-id="c033a-103">Use the  **Media Options** page of the **Back Up Database** dialog box to view or modify database media options.</span></span>  
  
 <span data-ttu-id="c033a-104">**Создание резервной копии с помощью среды SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="c033a-104">**To create a backup by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="c033a-105">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c033a-105">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="c033a-106">Создание разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c033a-106">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c033a-107">Для создания резервных копий базы данных можно составить план обслуживания базы данных.</span><span class="sxs-lookup"><span data-stu-id="c033a-107">You can define a database maintenance plan to create database backups.</span></span> <span data-ttu-id="c033a-108">Дополнительные сведения см. в статьях [Планы обслуживания](../maintenance-plans/maintenance-plans.md) и [Использование мастера планов обслуживания](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c033a-108">For more information, see [Maintenance Plans](../maintenance-plans/maintenance-plans.md) and [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c033a-109">Если задача резервного копирования определяется с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], можно создать соответствующий скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) , нажав кнопку **Скрипт** и выбрав место назначения для этого скрипта.</span><span class="sxs-lookup"><span data-stu-id="c033a-109">When you specify a backup task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and then selecting a destination for the script.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c033a-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="c033a-110">Options</span></span>  
  
### <a name="overwrite-media"></a><span data-ttu-id="c033a-111">Перезаписать носитель</span><span class="sxs-lookup"><span data-stu-id="c033a-111">Overwrite media</span></span>  
 <span data-ttu-id="c033a-112">Параметры панели **Перезаписать носитель** управляют записью резервной копии на носитель.</span><span class="sxs-lookup"><span data-stu-id="c033a-112">The options of the **Overwrite media** panel control how the backup is written to the media.</span></span> <span data-ttu-id="c033a-113">Если выбран URL-адрес (служба хранилища Azure) в качестве назначения резервного копирования на странице "Общие" в диалоговом окне "Резервное копирование базы данных", то параметры в разделе "Перезаписать носитель" будут отключены.</span><span class="sxs-lookup"><span data-stu-id="c033a-113">IF you selected URL (Azure Storage) as the backup destination on the General page of the Back Up Database dialog box, the options under the Overwrite media section are disabled.</span></span> <span data-ttu-id="c033a-114">Можно перезаписать резервную копию с помощью инструкции Transact-SQL `BACKUP TO URL.. WITH FORMAT`.</span><span class="sxs-lookup"><span data-stu-id="c033a-114">You can overwrite a backup using the `BACKUP TO URL.. WITH FORMAT` Transact-SQL statement.</span></span> <span data-ttu-id="c033a-115">Дополнительные сведения см. в разделе [SQL Server Backup to URL](sql-server-backup-to-url.md).</span><span class="sxs-lookup"><span data-stu-id="c033a-115">For more information, see [SQL Server Backup to URL](sql-server-backup-to-url.md).</span></span>  
  
 <span data-ttu-id="c033a-116">Параметр **Создать резервную копию на новом носителе и удалить существующие резервные наборы данных** поддерживается только с применением параметров шифрования.</span><span class="sxs-lookup"><span data-stu-id="c033a-116">Only the option, **Backup to a new media, and erase all existing backup sets** is supported with encryption options.</span></span> <span data-ttu-id="c033a-117">Если выбрать параметры в разделе **Создать резервную копию на существующем носителе** , параметры шифрования на странице **Параметры резервного копирования** будут отключены.</span><span class="sxs-lookup"><span data-stu-id="c033a-117">If you select the options under the **Back up to existing media** section, the encryptions options on the **Backup Options** page will be disabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c033a-118">Сведения о наборах носителей см. в разделе [Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)](media-sets-media-families-and-backup-sets-sql-server.md), подключен ленточный накопитель.</span><span class="sxs-lookup"><span data-stu-id="c033a-118">For information about media sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="c033a-119">**Создать резервную копию в существующем наборе носителей**</span><span class="sxs-lookup"><span data-stu-id="c033a-119">**Back up to the existing media set**</span></span>  
 <span data-ttu-id="c033a-120">Создание резервной копии базы данных на существующем наборе носителей.</span><span class="sxs-lookup"><span data-stu-id="c033a-120">Back up a database to an existing media set.</span></span> <span data-ttu-id="c033a-121">Если выбран этот параметр, становятся доступны еще три параметра.</span><span class="sxs-lookup"><span data-stu-id="c033a-121">Selecting this option button activates three options.</span></span>  
  
 <span data-ttu-id="c033a-122">Выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="c033a-122">Choose one of the following options:</span></span>  
  
 <span data-ttu-id="c033a-123">**Добавить к существующему резервному набору данных**</span><span class="sxs-lookup"><span data-stu-id="c033a-123">**Append to the existing backup set**</span></span>  
 <span data-ttu-id="c033a-124">Добавление резервного набора данных к существующему набору носителей с сохранением всех предыдущих резервных копий.</span><span class="sxs-lookup"><span data-stu-id="c033a-124">Append the backup set to the existing media set, preserving any prior backups.</span></span>  
  
 <span data-ttu-id="c033a-125">**Перезаписать все существующие резервные наборы данных**</span><span class="sxs-lookup"><span data-stu-id="c033a-125">**Overwrite all existing backup sets**</span></span>  
 <span data-ttu-id="c033a-126">Замена всех предыдущих резервных копий на существующем наборе носителей текущей резервной копией.</span><span class="sxs-lookup"><span data-stu-id="c033a-126">Replace any prior backups on the existing media set with the current backup.</span></span>  
  
 <span data-ttu-id="c033a-127">**Проверить имя набора носителей и срок действия резервного набора данных**</span><span class="sxs-lookup"><span data-stu-id="c033a-127">**Check media set name and backup set expiration**</span></span>  
 <span data-ttu-id="c033a-128">Этот необязательный параметр указывает, что при резервном копировании на существующий набор носителей должны проверяться имя и дата окончания срока хранения резервных наборов данных.</span><span class="sxs-lookup"><span data-stu-id="c033a-128">Optionally, if backing up to an existing media set, require the backup operation to verify the name and the expiration date of the backup sets.</span></span>  
  
 <span data-ttu-id="c033a-129">**Имя набора носителей**</span><span class="sxs-lookup"><span data-stu-id="c033a-129">**Media set name**</span></span>  
 <span data-ttu-id="c033a-130">Если выбран параметр **Проверить имя набора носителей и срок действия резервного набора данных** , можно указать имя набора носителей, который будет использоваться для операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="c033a-130">If **Check media set name and backup set expiration** is selected, optionally, specify the name of the media set to be used for this backup operation.</span></span>  
  
 <span data-ttu-id="c033a-131">**Создать резервную копию в новом наборе носителей и удалить все существующие резервные наборы данных**</span><span class="sxs-lookup"><span data-stu-id="c033a-131">**Back up to a new media set, and erase all existing backup sets**</span></span>  
 <span data-ttu-id="c033a-132">Использование нового набора носителей и удаление существующих резервных наборов данных.</span><span class="sxs-lookup"><span data-stu-id="c033a-132">Use a new media set, erasing the previous backup sets.</span></span>  
  
 <span data-ttu-id="c033a-133">Если выбран этот параметр, становятся доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="c033a-133">Clicking this option activates the following options:</span></span>  
  
 <span data-ttu-id="c033a-134">**Имя нового набора носителей**</span><span class="sxs-lookup"><span data-stu-id="c033a-134">**New media set name**</span></span>  
 <span data-ttu-id="c033a-135">Введите имя нового набора носителей (необязательно).</span><span class="sxs-lookup"><span data-stu-id="c033a-135">Optionally, enter a new name for the media set.</span></span>  
  
 <span data-ttu-id="c033a-136">**Описание нового набора носителей**</span><span class="sxs-lookup"><span data-stu-id="c033a-136">**New media set description**</span></span>  
 <span data-ttu-id="c033a-137">Введите значимое описание нового набора носителей (необязательно).</span><span class="sxs-lookup"><span data-stu-id="c033a-137">Optionally, enter a meaningful description of the new media set.</span></span> <span data-ttu-id="c033a-138">Описание должно быть достаточно точным, чтобы правильно передавать содержание.</span><span class="sxs-lookup"><span data-stu-id="c033a-138">This description should be specific enough to communicate the contents accurately.</span></span>  
  
### <a name="reliability"></a><span data-ttu-id="c033a-139">Надежность</span><span class="sxs-lookup"><span data-stu-id="c033a-139">Reliability</span></span>  
 <span data-ttu-id="c033a-140">Параметры панели **Журнал транзакций** управляют обработкой ошибок во время операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="c033a-140">The options of the **Transaction log** panel control error management by the backup operation.</span></span>  
  
 <span data-ttu-id="c033a-141">**Проверять резервную копию после завершения**</span><span class="sxs-lookup"><span data-stu-id="c033a-141">**Verify backup when finished**</span></span>  
 <span data-ttu-id="c033a-142">Проверка полноты резервного набора данных и читаемости всех томов.</span><span class="sxs-lookup"><span data-stu-id="c033a-142">Verify that the backup set is complete and that all volumes are readable.</span></span>  
  
 <span data-ttu-id="c033a-143">**Выполняйте контрольную сумму перед записью на носитель**</span><span class="sxs-lookup"><span data-stu-id="c033a-143">**Perform checksum before writing to media**</span></span>  
 <span data-ttu-id="c033a-144">Проверка контрольных сумм перед записью на резервный носитель.</span><span class="sxs-lookup"><span data-stu-id="c033a-144">Verify the checksums before writing to the backup media.</span></span> <span data-ttu-id="c033a-145">Выбор этого параметра эквивалентен использованию параметра CHECKSUM в инструкции BACKUP языка [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c033a-145">Selecting this option is equivalent to specifying the CHECKSUM option in the BACKUP statement of [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c033a-146">Выбор этого параметра может привести к увеличению рабочей нагрузки и замедлению операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="c033a-146">Selecting this option may increase the workload, and decrease the backup throughput of the backup operation.</span></span> <span data-ttu-id="c033a-147">Дополнительные сведения о резервных контрольных суммах см. в разделе [Возможные ошибки носителей во время резервного копирования и восстановления (SQL Server)](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c033a-147">For information about backup checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
 <span data-ttu-id="c033a-148">**Продолжить при ошибке**</span><span class="sxs-lookup"><span data-stu-id="c033a-148">**Continue on error**</span></span>  
 <span data-ttu-id="c033a-149">Операция резервного копирования будет продолжаться даже в случае возникновения одной или нескольких ошибок.</span><span class="sxs-lookup"><span data-stu-id="c033a-149">The backup operation is to continue even after encountering one or more errors.</span></span>  
  
### <a name="transaction-log"></a><span data-ttu-id="c033a-150">Журнал транзакций</span><span class="sxs-lookup"><span data-stu-id="c033a-150">Transaction log</span></span>  
 <span data-ttu-id="c033a-151">Параметры панели **Журнал транзакций** управляют поведением резервной копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="c033a-151">The options of the **Transaction log** panel control the behavior of a transaction log backup.</span></span> <span data-ttu-id="c033a-152">Эти параметры важны только в случае использования модели полного восстановления и модели восстановления с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="c033a-152">These options are relevant only under the full recovery model or bulk-logged recovery model.</span></span> <span data-ttu-id="c033a-153">Они активируются, только если в поле **Тип резервной копии** на странице **Общие** диалогового окна [Резервное копирование базы данных](../../integration-services/general-page-of-integration-services-designers-options.md) выбран **Журнал транзакций** .</span><span class="sxs-lookup"><span data-stu-id="c033a-153">They are activated only if **Transaction log** has been selected in the **Backup type** field on the [General](../../integration-services/general-page-of-integration-services-designers-options.md) page of the **Back Up Database** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c033a-154">Сведения о том, как создавать резервные копии журналов, см. в разделе [Резервные копии журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c033a-154">For information about transaction log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="c033a-155">**Усечь журнал транзакций**</span><span class="sxs-lookup"><span data-stu-id="c033a-155">**Truncate the transaction log**</span></span>  
 <span data-ttu-id="c033a-156">Выполняется резервное копирование журнала транзакций, после чего он усекается для освобождения пространства.</span><span class="sxs-lookup"><span data-stu-id="c033a-156">Back up the transaction log and truncate it to free log space.</span></span> <span data-ttu-id="c033a-157">База данных остается в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="c033a-157">The database remains online.</span></span> <span data-ttu-id="c033a-158">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c033a-158">This is the default option.</span></span>  
  
 <span data-ttu-id="c033a-159">**Создать резервную копию заключительного фрагмента журнала и оставить базу данных в состоянии восстановления**</span><span class="sxs-lookup"><span data-stu-id="c033a-159">**Back up the tail of the log, and leave the database in the restoring state**</span></span>  
 <span data-ttu-id="c033a-160">Создание резервной копии заключительного фрагмента журнала, при этом база данных остается в состоянии восстановления из копии.</span><span class="sxs-lookup"><span data-stu-id="c033a-160">Back up the tail of the log and leave the database in a restoring state.</span></span> <span data-ttu-id="c033a-161">Если выбран этот параметр, создается *резервная копия заключительного фрагмента журнала*и выполняется резервное копирование журналов, которые еще не были скопированы (активный журнал). Как правило, это происходит при подготовке к восстановлению базы данных из копии.</span><span class="sxs-lookup"><span data-stu-id="c033a-161">This option creates a *tail-log backup*, which backs up logs that have not yet been backed up (the active log), typically, in preparation for restoring a database.</span></span> <span data-ttu-id="c033a-162">База данных будет недоступна для пользователей до полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="c033a-162">The database will be unavailable to users until it is completely restored.</span></span>  
  
 <span data-ttu-id="c033a-163">Выбор этого параметра равнозначен использованию параметра WITH NO_TRUNCATE, NORECOVERY в инструкции [BACKUP](/sql/t-sql/statements/backup-transact-sql) (язык [!INCLUDE[tsql](../../includes/tsql-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="c033a-163">Selecting this option is equivalent to specifying WITH NO_TRUNCATE, NORECOVERY in a [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement ([!INCLUDE[tsql](../../includes/tsql-md.md)]).</span></span> <span data-ttu-id="c033a-164">Дополнительные сведения см. в статье [Резервные копии заключительного фрагмента журнала (SQL Server)](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c033a-164">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
### <a name="tape-drive"></a><span data-ttu-id="c033a-165">Ленточный накопитель</span><span class="sxs-lookup"><span data-stu-id="c033a-165">Tape drive</span></span>  
 <span data-ttu-id="c033a-166">Параметры панели **Накопитель на магнитной ленте** управляют магнитной лентой во время операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="c033a-166">The options of the **Tape drive** panel control tape management during the backup operation.</span></span> <span data-ttu-id="c033a-167">Эти параметры активируются, только если на панели **Назначение** на странице **Общие** диалогового окна [Резервное копирование базы данных](../../integration-services/general-page-of-integration-services-designers-options.md) выбран накопитель **Лента** .</span><span class="sxs-lookup"><span data-stu-id="c033a-167">These options are activated only if **Tape** has been selected in the **Destination** panel on the [General](../../integration-services/general-page-of-integration-services-designers-options.md) page of the **Back Up Database** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c033a-168">Дополнительные сведения об использовании ленточных устройств см. в статье [Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c033a-168">For information about how to use tape devices, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>  
  
 <span data-ttu-id="c033a-169">**Выгрузить ленту после резервного копирования**</span><span class="sxs-lookup"><span data-stu-id="c033a-169">**Unload the tape after backup**</span></span>  
 <span data-ttu-id="c033a-170">Выгрузка ленты по окончании резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="c033a-170">After the backup is complete, unload the tape.</span></span>  
  
 <span data-ttu-id="c033a-171">**Перемотать ленту перед выгрузкой**</span><span class="sxs-lookup"><span data-stu-id="c033a-171">**Rewind the tape before unloading**</span></span>  
 <span data-ttu-id="c033a-172">Освобождение и перемотка ленты перед выгрузкой.</span><span class="sxs-lookup"><span data-stu-id="c033a-172">Before unloading the tape, release and rewind it.</span></span> <span data-ttu-id="c033a-173">Этот параметр доступен, только если задан параметр **Выгрузить ленту после резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="c033a-173">This is enabled only if **Unload the tape after backup** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c033a-174">См. также:</span><span class="sxs-lookup"><span data-stu-id="c033a-174">See Also</span></span>  
 <span data-ttu-id="c033a-175">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c033a-175">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="c033a-176">[Создание резервной копии журнала транзакций (SQL Server)](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c033a-176">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="c033a-177">[Создание резервных копий файлов и файловых групп (SQL Server)](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c033a-177">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="c033a-178">Создание резервной копии журнала транзакций при повреждении базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c033a-178">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
  
