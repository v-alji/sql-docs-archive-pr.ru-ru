---
title: Создание полной резервной копии базы данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [SQL Server], full backups
- backing up databases [SQL Server], SQL Server Management Studio
- backups [SQL Server], creating
- database backups [SQL Server], SQL Server Management Studio
ms.assetid: 586561fc-dfbb-4842-84f8-204a9100a534
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f406464680a1669133dc87bdfb231c644d33fbdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749995"
---
# <a name="create-a-full-database-backup-sql-server"></a><span data-ttu-id="9b74b-102">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9b74b-102">Create a Full Database Backup (SQL Server)</span></span>
  <span data-ttu-id="9b74b-103">В этом разделе описывается создание полной резервной копии базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b74b-103">This topic describes how to create a full database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b74b-104">Сведения о SQL Server резервного копирования в службу хранилища BLOB-объектов Azure см. в статье [SQL Server резервное копирование и восстановление с помощью службы хранилища BLOB-объектов Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="9b74b-104">For information on SQL Server backup to the Azure Blob storage service, see, [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="9b74b-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="9b74b-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9b74b-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="9b74b-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9b74b-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9b74b-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9b74b-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="9b74b-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="9b74b-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="9b74b-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9b74b-110">**Создание полной резервной копии базы данных с помощью:**</span><span class="sxs-lookup"><span data-stu-id="9b74b-110">**To create a full database backup, using:**</span></span>  
  
     [<span data-ttu-id="9b74b-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b74b-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9b74b-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b74b-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="9b74b-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b74b-113">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="9b74b-114">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9b74b-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9b74b-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="9b74b-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9b74b-116">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9b74b-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9b74b-117">Инструкция BACKUP не разрешена в явных и неявных транзакциях.</span><span class="sxs-lookup"><span data-stu-id="9b74b-117">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="9b74b-118">Резервные копии, созданные более поздними версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , не могут быть восстановлены в более ранних версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b74b-118">Backups that are created by more recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be restored in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9b74b-119">Дополнительные сведения см. в разделе [Общие сведения о резервном копировании (SQL Server)](backup-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b74b-119">For more information, see [Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="9b74b-120">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="9b74b-120">Recommendations</span></span>  
  
-   <span data-ttu-id="9b74b-121">Однако по мере увеличения размера базы данных полное резервное копирование занимает больше времени и требует больше пространства для хранения.</span><span class="sxs-lookup"><span data-stu-id="9b74b-121">As a database increases in size full database backups take more time to finish and require more storage space.</span></span> <span data-ttu-id="9b74b-122">Поэтому для больших баз данных может потребоваться, кроме полных резервных копий, создавать также и *разностные резервные копии баз данных*.</span><span class="sxs-lookup"><span data-stu-id="9b74b-122">Therefore, for a large database, you might want to supplement a full database backup with a series of *differential database backups*.</span></span> <span data-ttu-id="9b74b-123">Дополнительные сведения см. в разделе [Разностные резервные копии (SQL Server)](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b74b-123">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="9b74b-124">Размер полной резервной копии базы данных вы можете вычислить с помощью системной хранимой процедуры [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="9b74b-124">You can estimate the size of a full database backup by using the [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) system stored procedure.</span></span>  
  
-   <span data-ttu-id="9b74b-125">По умолчанию каждая успешная операция резервного копирования добавляет запись в журнал ошибок служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и в журнал системных событий.</span><span class="sxs-lookup"><span data-stu-id="9b74b-125">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="9b74b-126">Если создание резервной копии журналов производится очень часто, это приводит к быстрому накоплению сообщений об успешном завершении. Это приводит к увеличению журналов ошибок, затрудняя поиск других сообщений.</span><span class="sxs-lookup"><span data-stu-id="9b74b-126">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="9b74b-127">Если работа существующих скриптов не зависит от этих записей, то их можно отключить с помощью флага трассировки 3226.</span><span class="sxs-lookup"><span data-stu-id="9b74b-127">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="9b74b-128">Дополнительные сведения см. в разделе [Флаги трассировки (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9b74b-128">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9b74b-129">безопасность</span><span class="sxs-lookup"><span data-stu-id="9b74b-129">Security</span></span>  
 <span data-ttu-id="9b74b-130">Для резервной копии базы данных свойству TRUSTWORTHY присваивается значение OFF.</span><span class="sxs-lookup"><span data-stu-id="9b74b-130">TRUSTWORTHY is set to OFF on a database backup.</span></span> <span data-ttu-id="9b74b-131">Дополнительные сведения о том, как задать для параметра TRUSTWORTHY значение ON, см. в разделе [Параметры ALTER DATABASE SET (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="9b74b-131">For information about how to set TRUSTWORTHY to ON, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="9b74b-132">Начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], параметры `PASSWORD` и `MEDIAPASSWORD` не поддерживаются при создании резервных копий.</span><span class="sxs-lookup"><span data-stu-id="9b74b-132">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] the `PASSWORD` and `MEDIAPASSWORD` options are discontinued for creating backups.</span></span> <span data-ttu-id="9b74b-133">Все еще вы можете восстанавливать резервные копии, созданные с паролями.</span><span class="sxs-lookup"><span data-stu-id="9b74b-133">You can still restore backups created with passwords.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9b74b-134">Permissions</span><span class="sxs-lookup"><span data-stu-id="9b74b-134">Permissions</span></span>  
 <span data-ttu-id="9b74b-135">Разрешения BACKUP DATABASE и BACKUP LOG назначены по умолчанию членам предопределенной роли сервера **sysadmin** и предопределенным ролям базы данных **db_owner** и **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-135">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="9b74b-136">Проблемы, связанные с владельцем и разрешениями у физических файлов на устройстве резервного копирования, могут помешать операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="9b74b-136">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9b74b-137">должен иметь возможность считывать и записывать данные на устройстве; учетная запись, от имени которой выполняется служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , должна иметь разрешения на запись.</span><span class="sxs-lookup"><span data-stu-id="9b74b-137">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="9b74b-138">Однако процедура [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), добавляющая запись для устройства резервного копирования в системные таблицы, не проверяет разрешения на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="9b74b-138">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="9b74b-139">Проблемы физического файла устройства резервного копирования могут не проявляться до момента доступа к физическому ресурсу во время операции резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="9b74b-139">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9b74b-140">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b74b-140">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b74b-141"> При создании задания резервного копирования с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]вы можете сформировать соответствующий скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) , нажав кнопку **Скрипт** и выбрав назначение скрипта.</span><span class="sxs-lookup"><span data-stu-id="9b74b-141">When you specify a back up task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and selecting a script destination.</span></span>  
  
#### <a name="to-back-up-a-database"></a><span data-ttu-id="9b74b-142">Создание резервной копии базы данных</span><span class="sxs-lookup"><span data-stu-id="9b74b-142">To back up a database</span></span>  
  
1.  <span data-ttu-id="9b74b-143">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="9b74b-143">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="9b74b-144">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="9b74b-144">Expand **Databases**, and depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="9b74b-145">Щелкните правой кнопкой мыши базу данных, выберите пункт **Задачи**, а затем команду **Создать резервную копию**.</span><span class="sxs-lookup"><span data-stu-id="9b74b-145">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="9b74b-146">Откроется диалоговое окно **Резервное копирование базы данных** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-146">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="9b74b-147">В `Database` списке проверьте имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="9b74b-147">In the `Database` list box, verify the database name.</span></span> <span data-ttu-id="9b74b-148">При необходимости можно выбрать другую базу данных из списка.</span><span class="sxs-lookup"><span data-stu-id="9b74b-148">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="9b74b-149">Резервное копирование базы данных можно выполнять для любой модели восстановления (**FULL**, **BULK_LOGGED**или **SIMPLE**).</span><span class="sxs-lookup"><span data-stu-id="9b74b-149">You can perform a database backup for any recovery model (**FULL**, **BULK_LOGGED**, or **SIMPLE**).</span></span>  
  
6.  <span data-ttu-id="9b74b-150">В списке **Тип резервной копии** выберите **Полная**.</span><span class="sxs-lookup"><span data-stu-id="9b74b-150">In the **Backup type** list box, select **Full**.</span></span>  
  
     <span data-ttu-id="9b74b-151">Обратите внимание на то, что при создании полной резервной копии базы данных можно создавать разностные резервные копии; дополнительные сведения см. в разделе [Создание разностной резервной копии базы данных (SQL Server)](create-a-differential-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b74b-151">Note that after creating a full database backup, you can create a differential database backup; for more information, see [Create a Differential Database Backup &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md).</span></span>  
  
7.  <span data-ttu-id="9b74b-152">Также можно выбрать вариант **Резервная копия только для копирования** , чтобы создать резервную копию только для копирования.</span><span class="sxs-lookup"><span data-stu-id="9b74b-152">Optionally, you can select **Copy Only Backup** to create a copy-only backup.</span></span> <span data-ttu-id="9b74b-153">*Резервная копия только для копирования* — это резервная копия [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которая не зависит от обычной последовательности создания традиционных резервных копий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b74b-153">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="9b74b-154">Дополнительные сведения см. в разделе [Резервные копии только для копирования (SQL Server)](copy-only-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b74b-154">For more information, see [Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b74b-155">Если выбран параметр **Разностная** , то резервную копию только для копирования создать не удастся.</span><span class="sxs-lookup"><span data-stu-id="9b74b-155">When the **Differential** option is selected, you cannot create a copy-only backup.</span></span>  
  
8.  <span data-ttu-id="9b74b-156">Для **компонента резервного копирования**щелкните `Database` .</span><span class="sxs-lookup"><span data-stu-id="9b74b-156">For **Backup component**, click `Database`.</span></span>  
  
9. <span data-ttu-id="9b74b-157">Оставьте имя резервного набора данных, предложенное по умолчанию в текстовом поле **Имя** , или введите другое имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="9b74b-157">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
10. <span data-ttu-id="9b74b-158">При необходимости можно ввести описание резервного набора данных в текстовом поле **Описание** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-158">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
11. <span data-ttu-id="9b74b-159">Выберите тип назначения резервного копирования, щелкнув **Диск**, **Тип** или **URL**.</span><span class="sxs-lookup"><span data-stu-id="9b74b-159">Choose the type of backup destination by clicking **Disk**, **Tape** or **URL**.</span></span> <span data-ttu-id="9b74b-160">Чтобы выбрать пути к 64 (или менее) дискам или накопителям на магнитной ленте, содержащим один набор носителей, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9b74b-160">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="9b74b-161">Выбранные пути отображаются в списке **Создать резервную копию в** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-161">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="9b74b-162">Чтобы удалить носитель резервной копии, выберите его и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="9b74b-162">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="9b74b-163">Чтобы просмотреть содержимое носителя резервной копии, выберите его и щелкните **Содержимое**.</span><span class="sxs-lookup"><span data-stu-id="9b74b-163">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="9b74b-164">Для просмотра или выбора параметров носителя нажмите кнопку **Параметры носителя** на панели **Выбор страницы** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-164">To view or select the media options, click **Media Options** in the **Select a page** pane.</span></span>  
  
13. <span data-ttu-id="9b74b-165">Выберите параметр **Переписать носитель** , указав один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="9b74b-165">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="9b74b-166">**Создать резервную копию в существующем наборе носителей**</span><span class="sxs-lookup"><span data-stu-id="9b74b-166">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="9b74b-167">Для этого параметра выберите вариант **Добавить в существующий резервный набор данных** или **Перезаписать все существующие резервные наборы данных**.</span><span class="sxs-lookup"><span data-stu-id="9b74b-167">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="9b74b-168">Дополнительные сведения см. в разделах [Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b74b-168">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="9b74b-169">При необходимости выберите **Проверить имя набора носителей и срок действия резервного набора данных** , чтобы при выполнении операции резервного копирования производилась проверка срока действия набора носителей и резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="9b74b-169">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="9b74b-170">При необходимости введите имя в текстовое поле **Имя набора носителей** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-170">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="9b74b-171">Если имя не указано, создается набор носителей с пустым именем.</span><span class="sxs-lookup"><span data-stu-id="9b74b-171">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="9b74b-172">Если имя набора носителей указано, то для носителя (ленточного или дискового) проверяется совпадение введенного и существующего имени.</span><span class="sxs-lookup"><span data-stu-id="9b74b-172">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="9b74b-173">Этот параметр будет отключен, если в качества назначения резервного копирования на странице **Общее** выбран параметр **URL** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-173">This option is disabled if you selected **URL** as the backup destination in the **General** page.</span></span> <span data-ttu-id="9b74b-174">Дополнительные сведения см. в разделе [Резервное копирование базы данных (страница "Параметры носителя")](back-up-database-media-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="9b74b-174">For more information, see [Back Up Database &#40;Media Options Page&#41;](back-up-database-media-options-page.md)</span></span>  
        >   
        >  <span data-ttu-id="9b74b-175">Не выбирайте этот параметр, если планируете использовать шифрование.</span><span class="sxs-lookup"><span data-stu-id="9b74b-175">If you plan to use encryption, do not select this option.</span></span> <span data-ttu-id="9b74b-176">Если выбран данный вариант, параметры шифрования на странице **Параметры резервного копирования** будут отключены.</span><span class="sxs-lookup"><span data-stu-id="9b74b-176">If you select this option, the encryption options in the **Backup Options** page will be disabled.</span></span> <span data-ttu-id="9b74b-177">При присоединении к существующему резервному набору данных шифрование не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9b74b-177">Encryption is not supported when appending to the existing backup set.</span></span>  
  
    -   <span data-ttu-id="9b74b-178">**Создать резервную копию в новом наборе носителей и удалить все существующие резервные наборы данных**</span><span class="sxs-lookup"><span data-stu-id="9b74b-178">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="9b74b-179">Для этого параметра введите имя в текстовом поле **Имя нового набора носителей** и при необходимости введите описание набора носителей в текстовое поле **Описание нового набора носителей** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-179">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="9b74b-180">Этот параметр будет отключен, если в качества назначения на странице **Общее** выбран вариант **URL** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-180">This option is disabled if you selected **URL** in the **General** page.</span></span> <span data-ttu-id="9b74b-181">Эти действия не поддерживаются при резервном копировании в службу хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="9b74b-181">These actions are not supported when backing up to Azure storage.</span></span>  
  
14. <span data-ttu-id="9b74b-182">В разделе **надежность** при необходимости установите флажок:</span><span class="sxs-lookup"><span data-stu-id="9b74b-182">In the **Reliability** section, optionally check:</span></span>  
  
    -   <span data-ttu-id="9b74b-183">**Проверить резервную копию после завершения**.</span><span class="sxs-lookup"><span data-stu-id="9b74b-183">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="9b74b-184">**Рассчитать контрольную сумму перед записью на носитель**и, при необходимости, **Продолжить при ошибке контрольной суммы**.</span><span class="sxs-lookup"><span data-stu-id="9b74b-184">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="9b74b-185">Дополнительные сведения см. в разделе [Возможные ошибки носителей во время резервного копирования и восстановления (SQL Server)](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b74b-185">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
15. <span data-ttu-id="9b74b-186">При резервном копировании на накопитель на магнитной ленте (как указано в разделе **Назначение** страницы **Общие** ) активен параметр **Выгрузить ленту после резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-186">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="9b74b-187">Щелкните этот параметр, чтобы активировать параметр **Перемотать ленту перед выгрузкой** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-187">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b74b-188">Параметры в разделе **Журнал транзакций** доступны, только если создается резервная копия журнала транзакций (это можно указать в разделе **Тип резервной копии** вкладки **Общие** ).</span><span class="sxs-lookup"><span data-stu-id="9b74b-188">The options in the **Transaction log** section are inactive unless you are backing up a transaction log (as specified in the **Backup type** section of the **General** page).</span></span>  
  
16. <span data-ttu-id="9b74b-189">Для просмотра или выбора параметров резервного копирования нажмите кнопку **Параметры резервного копирования** на панели **Выбор страницы** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-189">To view or select the backup options, click **Backup Options** in the **Select a page** pane.</span></span>  
  
17. <span data-ttu-id="9b74b-190">Укажите, когда закончится срок действия резервного набора данных и когда этот набор может быть перезаписан без явного пропуска проверки на истечение срока.</span><span class="sxs-lookup"><span data-stu-id="9b74b-190">Specify when the backup set will expire and can be overwritten without explicitly skipping verification of the expiration data:</span></span>  
  
    -   <span data-ttu-id="9b74b-191">Чтобы задать срок действия резервного набора данных, выберите пункт **После** (параметр по умолчанию) и введите срок действия набора в днях с момента его создания.</span><span class="sxs-lookup"><span data-stu-id="9b74b-191">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="9b74b-192">Это значение может быть задано в диапазоне от 0 до 99 999 дней. Значение 0 означает, что срок действия резервного набора данных не ограничен.</span><span class="sxs-lookup"><span data-stu-id="9b74b-192">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="9b74b-193">Значение по умолчанию задается в поле **Срок хранения носителей резервных копий по умолчанию (дней)** в диалоговом окне **Свойства сервера** (страница параметров базы данных).</span><span class="sxs-lookup"><span data-stu-id="9b74b-193">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (Database Settings Page).</span></span> <span data-ttu-id="9b74b-194">Чтобы получить доступ к этому параметру, щелкните правой кнопкой мыши имя сервера в обозревателе объектов и выберите пункт "Свойства", а затем выберите страницу **Настройки базы данных** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-194">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="9b74b-195">Чтобы указать дату истечения срока действия резервного набора данных, выберите пункт **На**и введите дату истечения срока действия резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="9b74b-195">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
         <span data-ttu-id="9b74b-196">Дополнительные сведения о дате истечения срока действия резервных копий см. в разделе [BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9b74b-196">For more information about backup expiration dates, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
18. [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="9b74b-197">и более поздние версии поддерживают [сжатие резервных копий](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b74b-197">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="9b74b-198">По умолчанию сжатие резервных копий зависит от значения параметра конфигурации сервера **backup-compression default** .</span><span class="sxs-lookup"><span data-stu-id="9b74b-198">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="9b74b-199">Однако независимо от текущего значения по умолчанию на уровне сервера можно сжать резервные копии, установив параметр **Сжимать резервные копии**, или отказаться от сжатия резервных копий, установив параметр **Не сжимать резервные копии**.</span><span class="sxs-lookup"><span data-stu-id="9b74b-199">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="9b74b-200">**Просмотр и изменение текущих значений параметров по умолчанию для сжатия резервных копий**</span><span class="sxs-lookup"><span data-stu-id="9b74b-200">**To view or change the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="9b74b-201">Параметр конфигурации сервера «Просмотр или настройка параметра сжатия резервных копий по умолчанию»</span><span class="sxs-lookup"><span data-stu-id="9b74b-201">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
19. <span data-ttu-id="9b74b-202">Укажите, следует ли использовать шифрование для резервных копий.</span><span class="sxs-lookup"><span data-stu-id="9b74b-202">Specify whether to use encryption for the backup.</span></span> <span data-ttu-id="9b74b-203">Выберите алгоритм шифрования для шага шифрования и выберите сертификат или асимметричный ключ из списка существующих сертификатов или асимметричных ключей.</span><span class="sxs-lookup"><span data-stu-id="9b74b-203">Select an encryption algorithm to use for the encryption step, and provide a Certificate or Asymmetric key from a list of existing certificates or asymmetric keys.</span></span> <span data-ttu-id="9b74b-204">Шифрование поддерживается в SQL Server 2014 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="9b74b-204">Encryption is supported in SQL Server 2014 or later.</span></span> <span data-ttu-id="9b74b-205">Дополнительные сведения об этом параметре шифрования см. в разделе [Резервное копирование базы данных (страница "Параметры резервного копирования")](back-up-database-backup-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="9b74b-205">For more details on the Encryption options, see [Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b74b-206">Также для создания резервных копий баз данных можно использовать мастер планов обслуживания базы данных.</span><span class="sxs-lookup"><span data-stu-id="9b74b-206">Alternatively, you can use the Maintenance Plan Wizard to create database backups.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9b74b-207">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b74b-207">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-full-database-backup"></a><span data-ttu-id="9b74b-208">Создание полной резервной копии базы данных</span><span class="sxs-lookup"><span data-stu-id="9b74b-208">To create a full database backup</span></span>  
  
1.  <span data-ttu-id="9b74b-209">Выполните инструкцию BACKUP DATABASE для создания полной резервной копии базы данных, указав следующее:</span><span class="sxs-lookup"><span data-stu-id="9b74b-209">Execute the BACKUP DATABASE statement to create the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="9b74b-210">имя базы данных для создания резервной копии;</span><span class="sxs-lookup"><span data-stu-id="9b74b-210">The name of the database to back up.</span></span>  
  
    -   <span data-ttu-id="9b74b-211">устройство резервного копирования, на которое записывается полная резервная копия базы данных.</span><span class="sxs-lookup"><span data-stu-id="9b74b-211">The backup device where the full database backup is written.</span></span>  
  
     <span data-ttu-id="9b74b-212">Базовая структура синтаксиса [!INCLUDE[tsql](../../includes/tsql-md.md)] для полного резервного копирования базы данных:</span><span class="sxs-lookup"><span data-stu-id="9b74b-212">The basic [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax for a full database backup is:</span></span>  
  
     <span data-ttu-id="9b74b-213">BACKUP DATABASE *database*</span><span class="sxs-lookup"><span data-stu-id="9b74b-213">BACKUP DATABASE *database*</span></span>  
  
     <span data-ttu-id="9b74b-214">TO *backup_device* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="9b74b-214">TO *backup_device* [ **,**...*n* ]</span></span>  
  
     <span data-ttu-id="9b74b-215">[ WITH *with_options* [ **,** ...*o* ] ] ;</span><span class="sxs-lookup"><span data-stu-id="9b74b-215">[ WITH *with_options* [ **,**...*o* ] ] ;</span></span>  
  
    |<span data-ttu-id="9b74b-216">Параметр</span><span class="sxs-lookup"><span data-stu-id="9b74b-216">Option</span></span>|<span data-ttu-id="9b74b-217">Описание</span><span class="sxs-lookup"><span data-stu-id="9b74b-217">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="9b74b-218">*database*</span><span class="sxs-lookup"><span data-stu-id="9b74b-218">*database*</span></span>|<span data-ttu-id="9b74b-219">База данных для резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="9b74b-219">Is the database that is to be backed up.</span></span>|  
    |<span data-ttu-id="9b74b-220">*backup_device* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="9b74b-220">*backup_device* [ **,**...*n* ]</span></span>|<span data-ttu-id="9b74b-221">Указывает список от 1 до 64 устройств резервного копирования, используемых для создания резервной копии.</span><span class="sxs-lookup"><span data-stu-id="9b74b-221">Specifies a list of from 1 to 64 backup devices to use for the backup operation.</span></span> <span data-ttu-id="9b74b-222">Можно указать как физическое устройство резервного копирования, так и соответствующее логическое устройство, если оно уже определено.</span><span class="sxs-lookup"><span data-stu-id="9b74b-222">You can specify a physical backup device, or you can specify a corresponding logical backup device, if already defined.</span></span> <span data-ttu-id="9b74b-223">Для указания физического устройства резервного копирования используйте параметр DISK или TAPE.</span><span class="sxs-lookup"><span data-stu-id="9b74b-223">To specify a physical backup device, use the DISK or TAPE option:</span></span><br /><br /> <span data-ttu-id="9b74b-224">{ DISK &#124; TAPE } **=** _имя_физического_устройства_резервного _копирования_</span><span class="sxs-lookup"><span data-stu-id="9b74b-224">{ DISK &#124; TAPE } **=**_physical_backup_device_name_</span></span><br /><br /> <span data-ttu-id="9b74b-225">Дополнительные сведения см. в разделе [Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b74b-225">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>|  
    |<span data-ttu-id="9b74b-226">WITH *with_options* [ **,** ...*o* ]</span><span class="sxs-lookup"><span data-stu-id="9b74b-226">WITH *with_options* [ **,**...*o* ]</span></span>|<span data-ttu-id="9b74b-227">При необходимости можно указать один или несколько дополнительных параметров, *o*.</span><span class="sxs-lookup"><span data-stu-id="9b74b-227">Optionally, specifies one or more additional options, *o*.</span></span> <span data-ttu-id="9b74b-228">Сведения о некоторых основных параметрах см. в пункте 2.</span><span class="sxs-lookup"><span data-stu-id="9b74b-228">For information about some of the basic with options, see step 2.</span></span>|  
  
2.  <span data-ttu-id="9b74b-229">При необходимости укажите один или несколько параметров WITH.</span><span class="sxs-lookup"><span data-stu-id="9b74b-229">Optionally, specify one or more WITH options.</span></span> <span data-ttu-id="9b74b-230">Здесь описываются некоторые основные параметры WITH.</span><span class="sxs-lookup"><span data-stu-id="9b74b-230">A few basic WITH options are described here.</span></span> <span data-ttu-id="9b74b-231">Сведения о всех параметрах WITH см. в разделе [BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9b74b-231">For information about all the WITH options, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
    -   <span data-ttu-id="9b74b-232">Основные параметры WITH резервного набора данных:</span><span class="sxs-lookup"><span data-stu-id="9b74b-232">Basic backup set WITH options:</span></span>  
  
         <span data-ttu-id="9b74b-233">{ COMPRESSION | NO_COMPRESSION }</span><span class="sxs-lookup"><span data-stu-id="9b74b-233">{ COMPRESSION | NO_COMPRESSION }</span></span>  
         <span data-ttu-id="9b74b-234">Только в версии [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] и выше указано, выполняется ли команда [backup compression](backup-compression-sql-server.md) для этой резервной копии, переопределяя значение по умолчанию на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="9b74b-234">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] and later only, specifies whether [backup compression](backup-compression-sql-server.md) is performed on this backup, overriding the server-level default.</span></span>  
  
         <span data-ttu-id="9b74b-235">ШИФРОВАНИЕ (АЛГОРИТМ, СЕРТИФИКАТ СЕРВЕРА |АСИММЕТРИЧНЫЙ КЛЮЧ)</span><span class="sxs-lookup"><span data-stu-id="9b74b-235">ENCRYPTION (ALGORITHM,  SERVER CERTIFICATE |ASYMMETRIC KEY)</span></span>  
         <span data-ttu-id="9b74b-236">Только для SQL Server 2014 и выше укажите используемый алгоритм шифрования, а также сертификат или асимметричный ключ для шифрования.</span><span class="sxs-lookup"><span data-stu-id="9b74b-236">In SQL Server 2014 or later only, specify the encryption algorithm to use, and the Certificate or Asymmetric key to use to secure the encryption.</span></span>  
  
         <span data-ttu-id="9b74b-237">Описание **=** { **" *`text`* "**  |  **@** _text_variable_ }</span><span class="sxs-lookup"><span data-stu-id="9b74b-237">DESCRIPTION **=** { **'*`text`*'** | **@**_text_variable_ }</span></span>  
         <span data-ttu-id="9b74b-238">Задает произвольное текстовое описание резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="9b74b-238">Specifies the free-form text that describes the backup set.</span></span> <span data-ttu-id="9b74b-239">В этой строке может содержаться до 255 символов.</span><span class="sxs-lookup"><span data-stu-id="9b74b-239">The string can have a maximum of 255 characters.</span></span>  
  
         <span data-ttu-id="9b74b-240">Имя **=** { *backup_set_name*  |  **@** _backup_set_name_var_ }</span><span class="sxs-lookup"><span data-stu-id="9b74b-240">NAME **=** { *backup_set_name* | **@**_backup_set_name_var_ }</span></span>  
         <span data-ttu-id="9b74b-241">Указывает имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="9b74b-241">Specifies the name of the backup set.</span></span> <span data-ttu-id="9b74b-242">Длина имени не может превышать 128 символов.</span><span class="sxs-lookup"><span data-stu-id="9b74b-242">Names can have a maximum of 128 characters.</span></span> <span data-ttu-id="9b74b-243">Если параметр NAME не указан, то имя является пустым.</span><span class="sxs-lookup"><span data-stu-id="9b74b-243">If NAME is not specified, it is blank.</span></span>  
  
    -   <span data-ttu-id="9b74b-244">Основные параметры WITH резервного набора данных:</span><span class="sxs-lookup"><span data-stu-id="9b74b-244">Basic backup set WITH options:</span></span>  
  
         <span data-ttu-id="9b74b-245">По умолчанию команда BACKUP добавляет резервную копию в существующий набор носителей, сохраняя существующие резервные наборы данных.</span><span class="sxs-lookup"><span data-stu-id="9b74b-245">By default, BACKUP appends the backup to an existing media set, preserving existing backup sets.</span></span> <span data-ttu-id="9b74b-246">Чтобы явно указать это, используйте параметр NOINIT.</span><span class="sxs-lookup"><span data-stu-id="9b74b-246">To explicitly specify this, use the NOINIT option.</span></span> <span data-ttu-id="9b74b-247">Сведения о присоединении к существующим резервным наборам данных см. в разделе [Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b74b-247">For information about appending to existing backup sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="9b74b-248">Чтобы отформатировать носитель резервной копии используется параметр FORMAT:</span><span class="sxs-lookup"><span data-stu-id="9b74b-248">Alternatively, to format the backup media, use the FORMAT option:</span></span>  
  
         <span data-ttu-id="9b74b-249">Format [ **,** MEDIANAME **=** { *media_name*  |  **@** _media_name_variable_ }] [ **,** MEDIADESCRIPTION **=** { *Text*  |  **@** _text_variable_ }]</span><span class="sxs-lookup"><span data-stu-id="9b74b-249">FORMAT [ **,** MEDIANAME**=** { *media_name* | **@**_media_name_variable_ } ] [ **,** MEDIADESCRIPTION **=** { *text* | **@**_text_variable_ } ]</span></span>  
         <span data-ttu-id="9b74b-250">Используйте предложение FORMAT при первом использовании носителя или при необходимости перезаписать существующие данные.</span><span class="sxs-lookup"><span data-stu-id="9b74b-250">Use the FORMAT clause when you are using media for the first time or you want to overwrite all existing data.</span></span> <span data-ttu-id="9b74b-251">При необходимости назначьте новому носителю имя и описание.</span><span class="sxs-lookup"><span data-stu-id="9b74b-251">Optionally, assign the new media a media name and description.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="9b74b-252">Будьте предельно осторожны, используя предложение FORMAT инструкции BACKUP, так как оно удаляет все резервные копии, сохраненные ранее на носителе резервных копий.</span><span class="sxs-lookup"><span data-stu-id="9b74b-252">Use extreme caution when you are using the FORMAT clause of the BACKUP statement because this destroys any backups that were previously stored on the backup media.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="9b74b-253">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9b74b-253">Examples (Transact-SQL)</span></span>  
  
#### <a name="a-backing-up-to-a-disk-device"></a><span data-ttu-id="9b74b-254">A.</span><span class="sxs-lookup"><span data-stu-id="9b74b-254">A.</span></span> <span data-ttu-id="9b74b-255">Резервное копирование на дисковое устройство</span><span class="sxs-lookup"><span data-stu-id="9b74b-255">Backing up to a disk device</span></span>  
 <span data-ttu-id="9b74b-256">В следующем примере производится резервное копирование всей базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] на диск и создание нового набора носителей с помощью параметра `FORMAT` .</span><span class="sxs-lookup"><span data-stu-id="9b74b-256">The following example backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to disk, by using `FORMAT` to create a new media set.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
   WITH FORMAT,  
      MEDIANAME = 'Z_SQLServerBackups',  
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
#### <a name="b-backing-up-to-a-tape-device"></a><span data-ttu-id="9b74b-257">Б.</span><span class="sxs-lookup"><span data-stu-id="9b74b-257">B.</span></span> <span data-ttu-id="9b74b-258">Резервное копирование на ленточное устройство</span><span class="sxs-lookup"><span data-stu-id="9b74b-258">Backing up to a tape device</span></span>  
 <span data-ttu-id="9b74b-259">В следующем примере создается полная резервная копия базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]на ленте в дополнение к предыдущим резервными копиям.</span><span class="sxs-lookup"><span data-stu-id="9b74b-259">The following example backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]database to tape, appending the backup to the previous backups.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
   TO TAPE = '\\.\Tape0'  
   WITH NOINIT,  
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
#### <a name="c-backing-up-to-a-logical-tape-device"></a><span data-ttu-id="9b74b-260">В.</span><span class="sxs-lookup"><span data-stu-id="9b74b-260">C.</span></span> <span data-ttu-id="9b74b-261">Резервное копирование на логическое ленточное устройство</span><span class="sxs-lookup"><span data-stu-id="9b74b-261">Backing up to a logical tape device</span></span>  
 <span data-ttu-id="9b74b-262">В следующем примере создается логическое устройство резервного копирования для ленточного накопителя.</span><span class="sxs-lookup"><span data-stu-id="9b74b-262">The following example creates a logical backup device for a tape drive.</span></span> <span data-ttu-id="9b74b-263">Затем показано, как производится полное резервное копирование базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] на этот накопитель.</span><span class="sxs-lookup"><span data-stu-id="9b74b-263">The example then backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to that device.</span></span>  
  
```sql  
-- Create a logical backup device,   
-- AdventureWorks2012_Bak_Tape, for tape device \\.\tape0.  
USE master;  
GO  
EXEC sp_addumpdevice 'tape', 'AdventureWorks2012_Bak_Tape', '\\.\tape0'; USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
   TO AdventureWorks2012_Bak_Tape  
   WITH FORMAT,  
      MEDIANAME = 'AdventureWorks2012_Bak_Tape',  
      MEDIADESCRIPTION = '\\.\tape0',   
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="9b74b-264">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b74b-264">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="9b74b-265">Используйте командлет `Backup-SqlDatabase`.</span><span class="sxs-lookup"><span data-stu-id="9b74b-265">Use the `Backup-SqlDatabase` cmdlet.</span></span> <span data-ttu-id="9b74b-266">Чтобы явно указать, что это полная резервная копия базы данных, укажите параметр **-BackupAction** со значением по умолчанию, `Database` .</span><span class="sxs-lookup"><span data-stu-id="9b74b-266">To explicitly indicate that this is a full database backup, specify the **-BackupAction**  parameter with its default value, `Database`.</span></span> <span data-ttu-id="9b74b-267">Данный параметр является необязательным для полных резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="9b74b-267">This parameter is optional for full database backups.</span></span>  
  
     <span data-ttu-id="9b74b-268">В следующем примере создается полная резервная копия базы данных `MyDB` в заданном по умолчанию расположении резервного копирования на экземпляре сервера `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="9b74b-268">The following example creates a full database backup of the `MyDB` database to the default backup location of the server instance `Computer\Instance`.</span></span> <span data-ttu-id="9b74b-269">Дополнительно в этом примере указывается `-BackupAction Database`.</span><span class="sxs-lookup"><span data-stu-id="9b74b-269">Optionally, this example specifies `-BackupAction Database`.</span></span>  
  
    ```powershell
    Backup-SqlDatabase -ServerInstance Computer\Instance -Database MyDB -BackupAction Database  
    ```  
  
 <span data-ttu-id="9b74b-270">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9b74b-270">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="9b74b-271">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b74b-271">SQL Server PowerShell Provider</span></span>](../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9b74b-272">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9b74b-272">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9b74b-273">Резервное копирование базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9b74b-273">Back Up a Database (SQL Server)</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="9b74b-274">Создание разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9b74b-274">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="9b74b-275">Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9b74b-275">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="9b74b-276">Восстановление резервной копии базы данных в простой модели восстановления (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9b74b-276">Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md)  
  
-   [<span data-ttu-id="9b74b-277">Восстановление базы данных до точки сбоя в модели полного восстановления (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9b74b-277">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="9b74b-278">Восстановление базы данных в новом расположении (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9b74b-278">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="9b74b-279">Использование мастера планов обслуживания</span><span class="sxs-lookup"><span data-stu-id="9b74b-279">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="9b74b-280">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b74b-280">See Also</span></span>  
 <span data-ttu-id="9b74b-281">[Общие сведения о резервном копировании (SQL Server)](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b74b-281">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="9b74b-282">[Резервные копии журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b74b-282">[Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="9b74b-283">[Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)](media-sets-media-families-and-backup-sets-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b74b-283">[Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span></span>  
 <span data-ttu-id="9b74b-284">[sp_addumpdevice (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b74b-284">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="9b74b-285">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b74b-285">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="9b74b-286">[Резервное копирование базы данных (страница "Общие")](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="9b74b-286">[Back Up Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="9b74b-287">[Резервное копирование базы данных (страница "Параметры резервного копирования")](back-up-database-backup-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="9b74b-287">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) </span></span>  
 <span data-ttu-id="9b74b-288">[Разностные резервные копии (SQL Server)](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b74b-288">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="9b74b-289">Полные резервные копии баз данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9b74b-289">Full Database Backups &#40;SQL Server&#41;</span></span>](full-database-backups-sql-server.md)  
