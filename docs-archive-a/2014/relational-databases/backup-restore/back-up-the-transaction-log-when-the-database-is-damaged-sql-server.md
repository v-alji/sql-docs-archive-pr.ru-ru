---
title: Создание резервной копии журнала транзакций при повреждении базы данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], damaged
- backing up [SQL Server]. damaged database
- transaction log backups [SQL Server], damaged databases
ms.assetid: 9b8873cc-df54-4336-ab9b-8f525132c2b0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea712e6bc4e73119a4f07a7775f9f25e212f8534
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654366"
---
# <a name="back-up-the-transaction-log-when-the-database-is-damaged-sql-server"></a><span data-ttu-id="e3254-102">Создание резервной копии журнала транзакций при повреждении базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e3254-102">Back Up the Transaction Log When the Database Is Damaged (SQL Server)</span></span>
  <span data-ttu-id="e3254-103">В этой теме описывается резервное копирование журнала транзакций в случае, если база данных повреждена в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] . Для этого используется [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3254-103">This topic describes how to back up a transaction log when the database is damaged in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e3254-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="e3254-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e3254-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="e3254-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e3254-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e3254-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e3254-107">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="e3254-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="e3254-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e3254-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e3254-109">**Создание резервной копии журнала транзакций при повреждении базы данных при помощи:**</span><span class="sxs-lookup"><span data-stu-id="e3254-109">**To back up the transaction log when the database is damaged, using:**</span></span>  
  
     [<span data-ttu-id="e3254-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3254-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e3254-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3254-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e3254-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="e3254-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e3254-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e3254-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e3254-114">Инструкция BACKUP не разрешена в явных и неявных транзакциях.</span><span class="sxs-lookup"><span data-stu-id="e3254-114">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="e3254-115">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="e3254-115">Recommendations</span></span>  
  
-   <span data-ttu-id="e3254-116">В базе данных, использующей модель полного восстановления или модель восстановления с неполным протоколированием, в большинстве случаев требуется, чтобы перед восстановлением базы данных была создана резервная копия заключительного фрагмента журнала.</span><span class="sxs-lookup"><span data-stu-id="e3254-116">For a database that uses either the full or bulk-logged recovery model, you generally need to back up the tail of the log before beginning to restore the database.</span></span> <span data-ttu-id="e3254-117">Также необходимо выполнить резервное копирование заключительного фрагмента журнала базы данных-источника перед переходом на другой ресурс конфигурации доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="e3254-117">You also should back up the tail of the log of the primary database before failing over a log shipping configuration.</span></span> <span data-ttu-id="e3254-118">Восстановление резервной копии заключительного фрагмента журнала в качестве заключительной резервной копии перед восстановлением базы данных позволяет избежать потери работы после сбоя.</span><span class="sxs-lookup"><span data-stu-id="e3254-118">Restoring the tail-log backup as the final log backup before recovering the database avoids work loss after a failure.</span></span> <span data-ttu-id="e3254-119">Дополнительные сведения о резервных копиях заключительного фрагмента журнала см. в разделе [Резервные копии заключительного фрагмента журнала (SQL Server)](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e3254-119">For more information about tail-log backups, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e3254-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="e3254-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e3254-121">Permissions</span><span class="sxs-lookup"><span data-stu-id="e3254-121">Permissions</span></span>  
 <span data-ttu-id="e3254-122">Разрешения BACKUP DATABASE и BACKUP LOG назначены по умолчанию членам предопределенной роли сервера **sysadmin** и предопределенным ролям базы данных **db_owner** и **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="e3254-122">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="e3254-123">Проблемы, связанные с владельцем и разрешениями у физических файлов на устройстве резервного копирования, могут помешать операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="e3254-123">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e3254-124">должен иметь возможность считывать и записывать данные на устройстве; учетная запись, от имени которой выполняется служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , должна иметь разрешения на запись.</span><span class="sxs-lookup"><span data-stu-id="e3254-124">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="e3254-125">Однако процедура [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), добавляющая запись для устройства резервного копирования в системные таблицы, не проверяет разрешения на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="e3254-125">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="e3254-126">Проблемы физического файла устройства резервного копирования могут не проявляться до момента доступа к физическому ресурсу во время операции резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="e3254-126">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e3254-127">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3254-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-back-up-the-tail-of-the-transaction-log"></a><span data-ttu-id="e3254-128">Создание резервной копии заключительного фрагмента журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="e3254-128">To back up the tail of the transaction log</span></span>  
  
1.  <span data-ttu-id="e3254-129">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="e3254-129">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="e3254-130">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="e3254-130">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="e3254-131">Щелкните правой кнопкой мыши базу данных, выберите пункт **Задачи**, а затем команду **Создать резервную копию**.</span><span class="sxs-lookup"><span data-stu-id="e3254-131">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="e3254-132">Откроется диалоговое окно **Резервное копирование базы данных** .</span><span class="sxs-lookup"><span data-stu-id="e3254-132">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="e3254-133">В списке **База данных** проверьте имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="e3254-133">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="e3254-134">При необходимости можно выбрать другую базу данных из списка.</span><span class="sxs-lookup"><span data-stu-id="e3254-134">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="e3254-135">Убедитесь в том, что используется либо модель восстановления **FULL** , либо **BULK_LOGGED**.</span><span class="sxs-lookup"><span data-stu-id="e3254-135">Verify that the recovery model is either **FULL** or **BULK_LOGGED**.</span></span>  
  
6.  <span data-ttu-id="e3254-136">Выберите **Журнал транзакций** в списке **Тип резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="e3254-136">In the **Backup type** list box, select **Transaction Log**.</span></span>  
  
7.  <span data-ttu-id="e3254-137">Оставьте снятым флажок **Резервная копия только для копирования** .</span><span class="sxs-lookup"><span data-stu-id="e3254-137">Leave **Copy Only Backup** deselected.</span></span>  
  
8.  <span data-ttu-id="e3254-138">В области **Набор резервного копирования** оставьте имя резервного набора данных, предложенное по умолчанию в текстовом поле **Имя** , или введите другое имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="e3254-138">In the **Backup set** area, either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
9. <span data-ttu-id="e3254-139">Введите описание резервной копии заключительного фрагмента журнала в текстовом поле **Описание** .</span><span class="sxs-lookup"><span data-stu-id="e3254-139">In the **Description** text box, enter a description for the tail-log backup.</span></span>  
  
10. <span data-ttu-id="e3254-140">Укажите, когда истекает срок действия резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="e3254-140">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="e3254-141">Чтобы задать срок действия резервного набора данных, выберите пункт **После** (параметр по умолчанию) и введите срок действия набора в днях с момента его создания.</span><span class="sxs-lookup"><span data-stu-id="e3254-141">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="e3254-142">Это значение может быть задано в диапазоне от 0 до 99 999 дней. Значение 0 означает, что срок действия резервного набора данных не ограничен.</span><span class="sxs-lookup"><span data-stu-id="e3254-142">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="e3254-143">Значение по умолчанию задается в параметре **Срок хранения носителей резервных копий по умолчанию (дней)** диалогового окна **Свойства сервера** (страница**Параметры базы данных** ).</span><span class="sxs-lookup"><span data-stu-id="e3254-143">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="e3254-144">Для этого щелкните правой кнопкой мыши имя сервера в обозревателе объектов и выберите его свойства, затем страницу **Параметры базы данных** .</span><span class="sxs-lookup"><span data-stu-id="e3254-144">To access this dialog box, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="e3254-145">Чтобы указать дату истечения срока действия резервного набора данных, выберите пункт **На**и введите дату истечения срока действия резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="e3254-145">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
11. <span data-ttu-id="e3254-146">Чтобы выбрать тип назначения резервной копии, выберите пункт **Диск** или **Лента**.</span><span class="sxs-lookup"><span data-stu-id="e3254-146">Choose the type of backup destination by clicking **Disk** or **Tape**.</span></span> <span data-ttu-id="e3254-147">Чтобы выбрать пути к 64 (или менее) дискам или накопителям на магнитной ленте, содержащим один набор носителей, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e3254-147">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="e3254-148">Выбранные пути отображаются в списке **Создать резервную копию в** .</span><span class="sxs-lookup"><span data-stu-id="e3254-148">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="e3254-149">Чтобы удалить носитель резервной копии, выберите его и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e3254-149">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="e3254-150">Чтобы просмотреть содержимое носителя резервной копии, выберите его и щелкните **Содержимое**.</span><span class="sxs-lookup"><span data-stu-id="e3254-150">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="e3254-151">На странице **Параметры** выберите параметр **Переписать носитель** , указав один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="e3254-151">On the **Options** page, select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="e3254-152">**Создать резервную копию в существующем наборе носителей**</span><span class="sxs-lookup"><span data-stu-id="e3254-152">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="e3254-153">Для этого параметра выберите вариант **Добавить в существующий резервный набор данных** или **Перезаписать все существующие резервные наборы данных**.</span><span class="sxs-lookup"><span data-stu-id="e3254-153">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span>  
  
         <span data-ttu-id="e3254-154">При необходимости выберите **Проверить имя набора носителей и срок действия резервного набора данных** , чтобы при выполнении операции резервного копирования производилась проверка срока действия набора носителей и резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="e3254-154">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="e3254-155">При необходимости введите имя в текстовое поле **Имя набора носителей** .</span><span class="sxs-lookup"><span data-stu-id="e3254-155">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="e3254-156">Если имя не указано, создается набор носителей с пустым именем.</span><span class="sxs-lookup"><span data-stu-id="e3254-156">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="e3254-157">Если имя набора носителей указано, то для носителя (ленточного или дискового) проверяется совпадение введенного и существующего имени.</span><span class="sxs-lookup"><span data-stu-id="e3254-157">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="e3254-158">Если оставить имя носителя пустым и установить рядом с ним флажок для проверки, имя носителя при успешном завершении также станет пустым.</span><span class="sxs-lookup"><span data-stu-id="e3254-158">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="e3254-159">**Создать резервную копию в новом наборе носителей и удалить все существующие резервные наборы данных**</span><span class="sxs-lookup"><span data-stu-id="e3254-159">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="e3254-160">Для этого параметра введите имя в текстовом поле **Имя нового набора носителей** и при необходимости введите описание набора носителей в текстовое поле **Описание нового набора носителей** .</span><span class="sxs-lookup"><span data-stu-id="e3254-160">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
     <span data-ttu-id="e3254-161">Сведения о параметрах набора носителей см. в разделе [Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e3254-161">For more information about media set options, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
13. <span data-ttu-id="e3254-162">В разделе **Надежность** можно установить следующие флажки.</span><span class="sxs-lookup"><span data-stu-id="e3254-162">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="e3254-163">**Проверить резервную копию после завершения**.</span><span class="sxs-lookup"><span data-stu-id="e3254-163">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="e3254-164">**Рассчитать контрольную сумму перед записью на носитель**.</span><span class="sxs-lookup"><span data-stu-id="e3254-164">**Perform checksum before writing to media**.</span></span>  
  
    -   <span data-ttu-id="e3254-165">**Продолжить при ошибке контрольной суммы**</span><span class="sxs-lookup"><span data-stu-id="e3254-165">**Continue on checksum error**</span></span>  
  
     <span data-ttu-id="e3254-166">Дополнительные сведения см. в разделе [Возможные ошибки носителей во время резервного копирования и восстановления (SQL Server)](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e3254-166">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
14. <span data-ttu-id="e3254-167">В разделе **Журнал транзакций** установите флажок **Создать резервную копию заключительного фрагмента журнала и оставить базу данных в состоянии восстановления**.</span><span class="sxs-lookup"><span data-stu-id="e3254-167">In the **Transaction log** section, check **Back up the tail of the log, and leave database in the restoring state**.</span></span>  
  
     <span data-ttu-id="e3254-168">Это эквивалентно следующей инструкции [BACKUP](/sql/t-sql/statements/backup-transact-sql) :</span><span class="sxs-lookup"><span data-stu-id="e3254-168">This is equivalent to specifying the following [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement:</span></span>  
  
     `BACKUP LOG <database_name> TO <backup_device> WITH NORECOVERY`  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e3254-169">Во время восстановления в диалоговом окне "Восстановление базы данных" тип резервной копии заключительного фрагмента журнала отображается как **Журнал транзакций (только копия)** .</span><span class="sxs-lookup"><span data-stu-id="e3254-169">At restore time, the Restore Database dialog box displays the type of a tail-log backup as **Transaction Log (Copy Only)**.</span></span>  
  
15. <span data-ttu-id="e3254-170">При резервном копировании на накопитель на магнитной ленте (как указано в разделе **Назначение** страницы **Общие** ) активен параметр **Выгрузить ленту после резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="e3254-170">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="e3254-171">Щелкните этот параметр, чтобы активировать параметр **Перемотать ленту перед выгрузкой** .</span><span class="sxs-lookup"><span data-stu-id="e3254-171">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
16. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="e3254-172">и более поздние версии поддерживают [сжатие резервных копий](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e3254-172">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="e3254-173">По умолчанию сжатие резервных копий зависит от значения параметра конфигурации сервера **backup-compression default** .</span><span class="sxs-lookup"><span data-stu-id="e3254-173">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="e3254-174">Однако независимо от текущего значения по умолчанию на уровне сервера можно сжать резервные копии, установив параметр **Сжимать резервные копии**, или отказаться от сжатия резервных копий, установив параметр **Не сжимать резервные копии**.</span><span class="sxs-lookup"><span data-stu-id="e3254-174">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="e3254-175">**Просмотр текущих значений параметров по умолчанию для сжатия резервных копий**</span><span class="sxs-lookup"><span data-stu-id="e3254-175">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="e3254-176">Параметр конфигурации сервера «Просмотр или настройка параметра сжатия резервных копий по умолчанию»</span><span class="sxs-lookup"><span data-stu-id="e3254-176">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e3254-177">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3254-177">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-backup-of-the-currently-active-transaction-log"></a><span data-ttu-id="e3254-178">Создание резервной копии активного журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="e3254-178">To create a backup of the currently active transaction log</span></span>  
  
1.  <span data-ttu-id="e3254-179">Для создания резервной копии активного журнала транзакций выполните инструкцию BACKUP LOG, указав:</span><span class="sxs-lookup"><span data-stu-id="e3254-179">Execute the BACKUP LOG statement to back up the currently active transaction log, specifying:</span></span>  
  
    -   <span data-ttu-id="e3254-180">имя базы данных, которой принадлежит журнал транзакций для резервного копирования;</span><span class="sxs-lookup"><span data-stu-id="e3254-180">The name of the database to which the transaction log to back up belongs.</span></span>  
  
    -   <span data-ttu-id="e3254-181">устройство резервного копирования, на котором будет создана резервная копия журнала транзакций;</span><span class="sxs-lookup"><span data-stu-id="e3254-181">The backup device where the transaction log backup will be written.</span></span>  
  
    -   <span data-ttu-id="e3254-182">предложение NO_TRUNCATE.</span><span class="sxs-lookup"><span data-stu-id="e3254-182">The NO_TRUNCATE clause.</span></span>  
  
         <span data-ttu-id="e3254-183">Это предложение позволяет выполнить резервное копирование активной части журнала транзакций, даже если база данных недоступна, при условии, что файл журнала транзакций доступен и не поврежден.</span><span class="sxs-lookup"><span data-stu-id="e3254-183">This clause allows the active part of the transaction log to be backed up even if the database is inaccessible, provided that the transaction log file is accessible and undamaged.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="e3254-184">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e3254-184">Example (Transact-SQL)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3254-185">В этом примере используется метод [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], который опирается на простую модель восстановления.</span><span class="sxs-lookup"><span data-stu-id="e3254-185">This example uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], which uses the simple recovery model.</span></span> <span data-ttu-id="e3254-186">Чтобы разрешить создание резервных копий журналов, перед созданием полной резервной копии база данных должна быть настроена на использование модели полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="e3254-186">To permit log backups, before taking a full database backup, the database was set to use the full recovery model.</span></span> <span data-ttu-id="e3254-187">Дополнительные сведения см. в разделе [Просмотр или изменение модели восстановления базы данных (SQL Server)](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e3254-187">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="e3254-188">В этом примере выполняется резервное копирование активного журнала транзакций, когда база данных повреждена и недоступна, однако журнал транзакций не поврежден и доступен.</span><span class="sxs-lookup"><span data-stu-id="e3254-188">This example backs up the currently active transaction log when a database is damaged and inaccessible, if the transaction log is undamaged and accessible.</span></span>  
  
```scr  
BACKUP LOG AdventureWorks2012  
   TO MyAdvWorks_FullRM_log1  
   WITH NO_TRUNCATE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3254-189">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3254-189">See Also</span></span>  
 <span data-ttu-id="e3254-190">[Восстановление резервной копии журнала транзакций (SQL Server)](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e3254-190">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="e3254-191">[Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="e3254-191">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 <span data-ttu-id="e3254-192">[Резервное копирование базы данных (страница "Параметры резервного копирования")](back-up-database-backup-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="e3254-192">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) </span></span>  
 <span data-ttu-id="e3254-193">[Резервное копирование базы данных (страница "Общие")](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="e3254-193">[Back Up Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="e3254-194">[Применение резервных копий журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e3254-194">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="e3254-195">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3254-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="e3254-196">[Восстановление файлов (простая модель восстановления)](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="e3254-196">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="e3254-197">Файлы из резервных копий (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="e3254-197">File Restores &#40;Full Recovery Model&#41;</span></span>](file-restores-full-recovery-model.md)  
  
  
