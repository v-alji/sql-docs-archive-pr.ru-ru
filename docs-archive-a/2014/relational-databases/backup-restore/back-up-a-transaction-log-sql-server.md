---
title: Создание резервной копии журнала транзакций (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction log backups [SQL Server], SQL Server Management Studio
- backups [SQL Server], creating
- backing up transaction logs [SQL Server], SQL Server Management Studio
ms.assetid: 3426b5eb-6327-4c7f-88aa-37030be69fbf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b57ca40b08718cda5095249991e0d424e6593a24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658857"
---
# <a name="back-up-a-transaction-log-sql-server"></a><span data-ttu-id="1e59d-102">Создание резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1e59d-102">Back Up a Transaction Log (SQL Server)</span></span>
  <span data-ttu-id="1e59d-103">В этом разделе описано, как создать резервную копию журнала транзакций в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e59d-103">This topic describes how to back up a transaction log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
 <span data-ttu-id="1e59d-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="1e59d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1e59d-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="1e59d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1e59d-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1e59d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1e59d-107">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1e59d-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="1e59d-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1e59d-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1e59d-109">**Создание резервной копии журнала транзакций**</span><span class="sxs-lookup"><span data-stu-id="1e59d-109">**To back up a transaction log, using:**</span></span>  
  
     [<span data-ttu-id="1e59d-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1e59d-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1e59d-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1e59d-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="1e59d-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e59d-112">PowerShell</span></span>](#PowerShellProcedure)  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e59d-113"> Для создания резервных копий также можно воспользоваться[мастером планов обслуживания](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="1e59d-113">Alternatively, you can use the[Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md)to create backups.</span></span>  
  
-   [<span data-ttu-id="1e59d-114">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="1e59d-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1e59d-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1e59d-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1e59d-116">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1e59d-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1e59d-117">Инструкция BACKUP не разрешена в явных и неявных транзакциях.</span><span class="sxs-lookup"><span data-stu-id="1e59d-117">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1e59d-118">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1e59d-118">Recommendations</span></span>  
  
-   <span data-ttu-id="1e59d-119">Если в базе данных используется полная модель восстановления или модель восстановления с неполным протоколированием, то необходимо регулярно создавать резервную копию журнала транзакций, чтобы защитить данные и предотвратить переполнение журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="1e59d-119">If a database uses either the full or bulk-logged recovery model, you must back up the transaction log regularly enough to protect your data and to keep the transaction log from filling.</span></span> <span data-ttu-id="1e59d-120">При этом журнал усекается и поддерживает восстановление базы данных на определенный момент времени.</span><span class="sxs-lookup"><span data-stu-id="1e59d-120">This truncates the log and supports restoring the database to a specific point in time.</span></span>  
  
-   <span data-ttu-id="1e59d-121">По умолчанию каждая успешная операция резервного копирования добавляет запись в журнал ошибок служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и в журнал системных событий.</span><span class="sxs-lookup"><span data-stu-id="1e59d-121">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="1e59d-122">Если создание резервной копии журналов производится очень часто, это приводит к быстрому накоплению сообщений об успешном завершении. Это приводит к увеличению журналов ошибок, затрудняя поиск других сообщений.</span><span class="sxs-lookup"><span data-stu-id="1e59d-122">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="1e59d-123">Если работа существующих скриптов не зависит от этих записей, то их можно отключить с помощью флага трассировки 3226.</span><span class="sxs-lookup"><span data-stu-id="1e59d-123">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="1e59d-124">Дополнительные сведения см. в разделе [Флаги трассировки (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1e59d-124">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1e59d-125">безопасность</span><span class="sxs-lookup"><span data-stu-id="1e59d-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1e59d-126">Permissions</span><span class="sxs-lookup"><span data-stu-id="1e59d-126">Permissions</span></span>  
 <span data-ttu-id="1e59d-127">Разрешения BACKUP DATABASE и BACKUP LOG назначены по умолчанию членам предопределенной роли сервера **sysadmin** и предопределенным ролям базы данных **db_owner** и **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="1e59d-127">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="1e59d-128">Проблемы, связанные с владельцем и разрешениями у физических файлов на устройстве резервного копирования, могут помешать операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="1e59d-128">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1e59d-129">должен иметь возможность считывать и записывать данные на устройстве; учетная запись, от имени которой выполняется служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , должна иметь разрешения на запись.</span><span class="sxs-lookup"><span data-stu-id="1e59d-129">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="1e59d-130">Однако процедура [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), добавляющая запись для устройства резервного копирования в системные таблицы, не проверяет разрешения на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="1e59d-130">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="1e59d-131">Проблемы физического файла устройства резервного копирования могут не проявляться до момента доступа к физическому ресурсу во время операции резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="1e59d-131">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1e59d-132">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1e59d-132">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-back-up-a-transaction-log"></a><span data-ttu-id="1e59d-133">Создание резервной копии журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="1e59d-133">To back up a transaction log</span></span>  
  
1.  <span data-ttu-id="1e59d-134">После подключения к соответствующему экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="1e59d-134">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="1e59d-135">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="1e59d-135">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="1e59d-136">Щелкните правой кнопкой мыши базу данных, выберите пункт **Задачи**, а затем команду **Создать резервную копию**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-136">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="1e59d-137">Откроется диалоговое окно **Резервное копирование базы данных** .</span><span class="sxs-lookup"><span data-stu-id="1e59d-137">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="1e59d-138">В списке **База данных** проверьте имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="1e59d-138">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="1e59d-139">При необходимости можно выбрать другую базу данных из списка.</span><span class="sxs-lookup"><span data-stu-id="1e59d-139">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="1e59d-140">Убедитесь в том, что используется либо модель восстановления **FULL** , либо **BULK_LOGGED**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-140">Verify that the recovery model is either **FULL** or **BULK_LOGGED**.</span></span>  
  
6.  <span data-ttu-id="1e59d-141">Выберите **Журнал транзакций** в списке **Тип резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-141">In the **Backup type** list box, select **Transaction Log**.</span></span>  
  
7.  <span data-ttu-id="1e59d-142">Также можно выбрать вариант **Резервная копия только для копирования** , чтобы создать резервную копию только для копирования.</span><span class="sxs-lookup"><span data-stu-id="1e59d-142">Optionally, you can select **Copy Only Backup** to create a copy-only backup.</span></span> <span data-ttu-id="1e59d-143">*Резервная копия только для копирования* — это резервная копия [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которая не зависит от обычной последовательности создания традиционных резервных копий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e59d-143">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="1e59d-144">Дополнительные сведения см. в разделе [Резервные копии только для копирования (SQL Server)](copy-only-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e59d-144">For more information, see [Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e59d-145">Если выбран параметр **Разностная** , то резервную копию только для копирования создать не удастся.</span><span class="sxs-lookup"><span data-stu-id="1e59d-145">When the **Differential** option is selected, you cannot create a copy-only backup.</span></span>  
  
8.  <span data-ttu-id="1e59d-146">Оставьте имя резервного набора данных, предложенное по умолчанию в текстовом поле **Имя** , или введите другое имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="1e59d-146">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
9. <span data-ttu-id="1e59d-147">При необходимости можно ввести описание резервного набора данных в текстовом поле **Описание** .</span><span class="sxs-lookup"><span data-stu-id="1e59d-147">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
10. <span data-ttu-id="1e59d-148">Укажите, когда истекает срок действия резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="1e59d-148">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="1e59d-149">Чтобы задать срок действия резервного набора данных, выберите пункт **После** (параметр по умолчанию) и введите срок действия набора в днях с момента его создания.</span><span class="sxs-lookup"><span data-stu-id="1e59d-149">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="1e59d-150">Это значение может быть задано в диапазоне от 0 до 99 999 дней. Значение 0 означает, что срок действия резервного набора данных не ограничен.</span><span class="sxs-lookup"><span data-stu-id="1e59d-150">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="1e59d-151">Значение по умолчанию задается в параметре **Срок хранения носителей резервных копий по умолчанию (дней)** диалогового окна **Свойства сервера** (страница**Параметры базы данных** ).</span><span class="sxs-lookup"><span data-stu-id="1e59d-151">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="1e59d-152">Для этого щелкните правой кнопкой мыши имя сервера в обозревателе объектов и выберите его свойства, затем страницу **Параметры базы данных** .</span><span class="sxs-lookup"><span data-stu-id="1e59d-152">To access this dialog box, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="1e59d-153">Чтобы указать дату истечения срока действия резервного набора данных, выберите пункт **На**и введите дату истечения срока действия резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="1e59d-153">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
11. <span data-ttu-id="1e59d-154">Чтобы выбрать тип назначения резервной копии, выберите пункт **Диск**, **URL-адрес** или **Лента**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-154">Choose the type of backup destination by clicking **Disk**, **URL** or **Tape**.</span></span> <span data-ttu-id="1e59d-155">Чтобы выбрать пути к 64 (или менее) дискам или накопителям на магнитной ленте, содержащим один набор носителей, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-155">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="1e59d-156">Выбранные пути отображаются в списке **Создать резервную копию в** .</span><span class="sxs-lookup"><span data-stu-id="1e59d-156">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="1e59d-157">Чтобы удалить носитель резервной копии, выберите его и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-157">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="1e59d-158">Чтобы просмотреть содержимое носителя резервной копии, выберите его и щелкните **Содержимое**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-158">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="1e59d-159">Чтобы просмотреть или выбрать дополнительные параметры, нажмите кнопку **Параметры** на панели **Выбор страницы** .</span><span class="sxs-lookup"><span data-stu-id="1e59d-159">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
13. <span data-ttu-id="1e59d-160">Выберите параметр **Переписать носитель** , указав один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="1e59d-160">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="1e59d-161">**Создать резервную копию в существующем наборе носителей**</span><span class="sxs-lookup"><span data-stu-id="1e59d-161">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="1e59d-162">Для этого параметра выберите вариант **Добавить в существующий резервный набор данных** или **Перезаписать все существующие резервные наборы данных**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-162">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="1e59d-163">Дополнительные сведения см. в разделах [Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e59d-163">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="1e59d-164">При необходимости выберите **Проверить имя набора носителей и срок действия резервного набора данных** , чтобы при выполнении операции резервного копирования производилась проверка срока действия набора носителей и резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="1e59d-164">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="1e59d-165">При необходимости введите имя в текстовое поле **Имя набора носителей** .</span><span class="sxs-lookup"><span data-stu-id="1e59d-165">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="1e59d-166">Если имя не указано, создается набор носителей с пустым именем.</span><span class="sxs-lookup"><span data-stu-id="1e59d-166">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="1e59d-167">Если имя набора носителей указано, то для носителя (ленточного или дискового) проверяется совпадение введенного и существующего имени.</span><span class="sxs-lookup"><span data-stu-id="1e59d-167">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="1e59d-168">Если оставить имя носителя пустым и установить рядом с ним флажок для проверки, имя носителя при успешном завершении также станет пустым.</span><span class="sxs-lookup"><span data-stu-id="1e59d-168">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="1e59d-169">**Создать резервную копию в новом наборе носителей и удалить все существующие резервные наборы данных**</span><span class="sxs-lookup"><span data-stu-id="1e59d-169">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="1e59d-170">Для этого параметра введите имя в текстовом поле **Имя нового набора носителей** и при необходимости введите описание набора носителей в текстовое поле **Описание нового набора носителей** .</span><span class="sxs-lookup"><span data-stu-id="1e59d-170">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span> <span data-ttu-id="1e59d-171">Дополнительные сведения см. в разделах [Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e59d-171">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
14. <span data-ttu-id="1e59d-172">В разделе **Надежность** можно установить следующие флажки.</span><span class="sxs-lookup"><span data-stu-id="1e59d-172">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="1e59d-173">**Проверить резервную копию после завершения**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-173">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="1e59d-174">**Рассчитать контрольную сумму перед записью на носитель**и, при необходимости, **Продолжить при ошибке контрольной суммы**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-174">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="1e59d-175">Дополнительные сведения см. в разделе [Возможные ошибки носителей во время резервного копирования и восстановления (SQL Server)](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e59d-175">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
15. <span data-ttu-id="1e59d-176">В разделе **Журнал транзакций** можно установить следующие флажки.</span><span class="sxs-lookup"><span data-stu-id="1e59d-176">In the **Transaction log** section:</span></span>  
  
    -   <span data-ttu-id="1e59d-177">Для повседневного резервного копирования журналов оставьте вариант по умолчанию **Обрезать журнал транзакций путем удаления неактивных записей**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-177">For routine log backups, keep the default selection, **Truncate the transaction log by removing inactive entries**.</span></span>  
  
    -   <span data-ttu-id="1e59d-178">Для создания резервной копии заключительного фрагмента журнала (т. е. активного журнала) отметьте параметр **Выполнять резервное копирование заключительного фрагмента журнала, оставляя базу данных в состоянии восстановления**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-178">To back up the tail of the log (that is, the active log), check **Back up the tail of the log, and leave database in the restoring state**.</span></span>  
  
         <span data-ttu-id="1e59d-179">Резервное копирование заключительного фрагмента журнала выполняется после сбоя, чтобы предотвратить потерю сделанной работы.</span><span class="sxs-lookup"><span data-stu-id="1e59d-179">A tail-log backup is taken after a failure to back up the tail of the log in order to prevent work loss.</span></span> <span data-ttu-id="1e59d-180">Резервное копирование активного журнала (резервное копирование заключительного фрагмента журнала) следует выполнять как после сбоя, так и перед началом восстановления базы данных, а также при сбое базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="1e59d-180">Back up the active log (a tail-log backup) both after a failure, before beginning to restore the database, or when failing over to a secondary database.</span></span> <span data-ttu-id="1e59d-181">Выбор этого параметра равносилен применению параметра NORECOVERY в инструкции BACKUP LOG языка Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="1e59d-181">Selecting this option is equivalent to specifying the NORECOVERY option in the BACKUP LOG statement of Transact-SQL.</span></span> <span data-ttu-id="1e59d-182">Дополнительные сведения о резервных копиях заключительного фрагмента журнала см. в разделе [Резервные копии заключительного фрагмента журнала (SQL Server)](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e59d-182">For more information about tail-log backups, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
16. <span data-ttu-id="1e59d-183">При резервном копировании на накопитель на магнитной ленте (как указано в разделе **Назначение** страницы **Общие** ) активен параметр **Выгрузить ленту после резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="1e59d-183">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="1e59d-184">Щелкните этот параметр, чтобы активировать параметр **Перемотать ленту перед выгрузкой** .</span><span class="sxs-lookup"><span data-stu-id="1e59d-184">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
17. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="1e59d-185">и более поздние версии поддерживают [сжатие резервных копий](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e59d-185">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="1e59d-186">По умолчанию сжатие резервных копий зависит от значения параметра конфигурации сервера **backup-compression default** .</span><span class="sxs-lookup"><span data-stu-id="1e59d-186">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="1e59d-187">Однако независимо от текущего значения по умолчанию на уровне сервера можно сжать резервные копии, установив параметр **Сжимать резервные копии**, или отказаться от сжатия резервных копий, установив параметр **Не сжимать резервные копии**.</span><span class="sxs-lookup"><span data-stu-id="1e59d-187">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="1e59d-188">**Просмотр текущих значений параметров по умолчанию для сжатия резервных копий**</span><span class="sxs-lookup"><span data-stu-id="1e59d-188">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="1e59d-189">Параметр конфигурации сервера «Просмотр или настройка параметра сжатия резервных копий по умолчанию»</span><span class="sxs-lookup"><span data-stu-id="1e59d-189">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
 <span data-ttu-id="1e59d-190">**Шифрование**</span><span class="sxs-lookup"><span data-stu-id="1e59d-190">**Encryption**</span></span>  
  
 <span data-ttu-id="1e59d-191">Для шифрования файла резервной копии установите флажок **Зашифровать файл резервной копии** .</span><span class="sxs-lookup"><span data-stu-id="1e59d-191">To encrypt the backup file check the **Encrypt backup** check box.</span></span> <span data-ttu-id="1e59d-192">Выберите алгоритм шифрования файла резервной копии и выберите сертификат или асимметричный ключ.</span><span class="sxs-lookup"><span data-stu-id="1e59d-192">Select an encryption algorithm to use for encrypting the backup file and provide a Certificate or Asymmetric key.</span></span> <span data-ttu-id="1e59d-193">Доступны следующие алгоритмы шифрования:</span><span class="sxs-lookup"><span data-stu-id="1e59d-193">The available algorithms for encryption are:</span></span>  
  
-   <span data-ttu-id="1e59d-194">AES 128</span><span class="sxs-lookup"><span data-stu-id="1e59d-194">AES 128</span></span>  
  
-   <span data-ttu-id="1e59d-195">AES 192</span><span class="sxs-lookup"><span data-stu-id="1e59d-195">AES 192</span></span>  
  
-   <span data-ttu-id="1e59d-196">AES 256</span><span class="sxs-lookup"><span data-stu-id="1e59d-196">AES 256</span></span>  
  
-   <span data-ttu-id="1e59d-197">Triple DES</span><span class="sxs-lookup"><span data-stu-id="1e59d-197">Triple DES</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1e59d-198">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1e59d-198">Using Transact-SQL</span></span>  
  
#### <a name="to-back-up-a-transaction-log"></a><span data-ttu-id="1e59d-199">Создание резервной копии журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="1e59d-199">To back up a transaction log</span></span>  
  
1.  <span data-ttu-id="1e59d-200">Выполните инструкцию BACKUP LOG для создания резервной копии журнала транзакций, указав следующее:</span><span class="sxs-lookup"><span data-stu-id="1e59d-200">Execute the BACKUP LOG statement to back up the transaction log, specifying the following:</span></span>  
  
    -   <span data-ttu-id="1e59d-201">имя базы данных, которой принадлежит журнал транзакций, резервную копию которого необходимо создать;</span><span class="sxs-lookup"><span data-stu-id="1e59d-201">The name of the database to which the transaction log that you want to back up belongs.</span></span>  
  
    -   <span data-ttu-id="1e59d-202">Устройство резервного копирования, на которое записывается резервная копия журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="1e59d-202">The backup device where the transaction log backup is written.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="1e59d-203">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1e59d-203">Example (Transact-SQL)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1e59d-204">В этом примере используется база данных [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , которая опирается на простую модель восстановления.</span><span class="sxs-lookup"><span data-stu-id="1e59d-204">This example uses the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database, which uses the simple recovery model.</span></span> <span data-ttu-id="1e59d-205">Чтобы разрешить создание резервных копий журналов, перед созданием полной резервной копии база данных должна быть настроена на использование модели полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="1e59d-205">To permit log backups, before taking a full database backup, the database was set to use the full recovery model.</span></span> <span data-ttu-id="1e59d-206">Дополнительные сведения см. в разделе [Просмотр или изменение модели восстановления базы данных (SQL Server)](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e59d-206">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="1e59d-207">В этом примере создается резервная копия журнала транзакций для базы данных [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] на созданном ранее устройстве резервного копирования, имеющая имя `MyAdvWorks_FullRM_log1`.</span><span class="sxs-lookup"><span data-stu-id="1e59d-207">This example creates a transaction log backup for the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to the previously created named backup device, `MyAdvWorks_FullRM_log1`.</span></span>  
  
```sql  
BACKUP LOG AdventureWorks2012  
   TO MyAdvWorks_FullRM_log1;  
GO  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="1e59d-208">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e59d-208">Using PowerShell</span></span>  
  
<span data-ttu-id="1e59d-209">Используйте командлет `Backup-SqlDatabase` и укажите `Log` в качестве значения параметра `-BackupAction`.</span><span class="sxs-lookup"><span data-stu-id="1e59d-209">Use the `Backup-SqlDatabase` cmdlet and specify `Log` for the value of the `-BackupAction` parameter.</span></span>  
  
<span data-ttu-id="1e59d-210">В следующем примере создается полная резервная копия журналов базы данных `MyDB` в заданном по умолчанию расположении резервного копирования на экземпляре сервера `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="1e59d-210">The following example creates a log backup of the `MyDB` database to the default backup location of the server instance `Computer\Instance`.</span></span>  
  
    ```powershell
    Backup-SqlDatabase -ServerInstance Computer\Instance -Database MyDB -BackupAction Log  
    ```  
  
<span data-ttu-id="1e59d-211">Сведения о настройке и использовании поставщика SQL Server PowerShell см. в разделе [поставщик SQL Server PowerShell](../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="1e59d-211">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../powershell/sql-server-powershell-provider.md).</span></span>
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1e59d-212">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="1e59d-212">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1e59d-213">Восстановление резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1e59d-213">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="1e59d-214">Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="1e59d-214">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="1e59d-215">Устранение неполадок при переполнении журнала транзакций (ошибка SQL Server 9002)</span><span class="sxs-lookup"><span data-stu-id="1e59d-215">Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;</span></span>](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
  
## <a name="see-also"></a><span data-ttu-id="1e59d-216">См. также:</span><span class="sxs-lookup"><span data-stu-id="1e59d-216">See Also</span></span>  
 <span data-ttu-id="1e59d-217">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1e59d-217">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="1e59d-218">[Применение резервных копий журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1e59d-218">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="1e59d-219">[Планы обслуживания](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="1e59d-219">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 [<span data-ttu-id="1e59d-220">Полные резервные копии файлов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1e59d-220">Full File Backups &#40;SQL Server&#41;</span></span>](full-file-backups-sql-server.md)  
