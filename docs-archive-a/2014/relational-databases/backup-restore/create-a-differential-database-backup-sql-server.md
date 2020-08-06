---
title: Создание разностной резервной копии базы данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full differential backups [SQL Server]
- database backups [SQL Server], full differential backups
- backing up databases [SQL Server], full differential backups
- backups [SQL Server], creating
ms.assetid: 70f49794-b217-4519-9f2a-76ed61fa9f99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c3fb53d90ce633498bc518282d1ff03ce0b926e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668929"
---
# <a name="create-a-differential-database-backup-sql-server"></a><span data-ttu-id="ad6a2-102">Создание разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ad6a2-102">Create a Differential Database Backup (SQL Server)</span></span>
  <span data-ttu-id="ad6a2-103">В этом разделе описано, как создать разностную резервную копию базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad6a2-103">This topic describes how to create a differential database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ad6a2-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="ad6a2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ad6a2-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="ad6a2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ad6a2-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ad6a2-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ad6a2-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ad6a2-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="ad6a2-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="ad6a2-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="ad6a2-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ad6a2-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ad6a2-110">**Создание разностной резервной копии**</span><span class="sxs-lookup"><span data-stu-id="ad6a2-110">**To create a differential database backup, using:**</span></span>  
  
     [<span data-ttu-id="ad6a2-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad6a2-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ad6a2-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad6a2-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ad6a2-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ad6a2-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ad6a2-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ad6a2-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ad6a2-115">Инструкция BACKUP не разрешена в явных и неявных транзакциях.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-115">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="ad6a2-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ad6a2-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="ad6a2-117">Для создания разностной резервной копии базы данных необходимо наличие ранее созданной полной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-117">Creating a differential database backup requires that a previous full database backup exist.</span></span> <span data-ttu-id="ad6a2-118">Если для выбранной базы данных резервное копирование еще не производилось, то перед созданием разностной резервной копии выполните полное резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-118">If the selected database has never been backed up, run a full database backup before creating any differential backups.</span></span> <span data-ttu-id="ad6a2-119">Дополнительные сведения см. в разделе [Создание полной резервной копии базы данных (SQL Server)](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ad6a2-119">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="ad6a2-120">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="ad6a2-120">Recommendations</span></span>  
  
-   <span data-ttu-id="ad6a2-121">Поскольку разностные резервные копии увеличиваются в размере, восстановление разностной резервной копии может значительно увеличить время, которое необходимо для восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-121">As the differential backups increase in size, restoring a differential backup can significantly increase the time that is required to restore a database.</span></span> <span data-ttu-id="ad6a2-122">Поэтому рекомендуется через некоторое время выполнить создание новой полной резервной копии, чтобы получить новую базовую копию для разностного копирования.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-122">Therefore, we recommend that you take a new full backup at set intervals to establish a new differential base for the data.</span></span> <span data-ttu-id="ad6a2-123">Например, можно выполнять полное резервное копирование всей базы данных один раз в неделю, а затем в течение недели регулярно создавать разностные резервные копии.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-123">For example, you might take a weekly full backup of the whole database (that is, a full database backup) followed by a regular series of differential database backups during the week.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ad6a2-124">безопасность</span><span class="sxs-lookup"><span data-stu-id="ad6a2-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ad6a2-125">Permissions</span><span class="sxs-lookup"><span data-stu-id="ad6a2-125">Permissions</span></span>  
 <span data-ttu-id="ad6a2-126">Разрешения BACKUP DATABASE и BACKUP LOG назначены по умолчанию членам предопределенной роли сервера **sysadmin** и предопределенным ролям базы данных **db_owner** и **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="ad6a2-126">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="ad6a2-127">Проблемы, связанные с владельцем и разрешениями у физических файлов на устройстве резервного копирования, могут помешать операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-127">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ad6a2-128">должен иметь возможность считывать и записывать данные на устройстве; учетная запись, от имени которой выполняется служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , должна иметь разрешения на запись.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-128">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="ad6a2-129">Однако процедура [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), добавляющая запись для устройства резервного копирования в системные таблицы, не проверяет разрешения на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-129">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="ad6a2-130">Проблемы физического файла устройства резервного копирования могут не проявляться до момента доступа к физическому ресурсу во время операции резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-130">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ad6a2-131">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad6a2-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-differential-database-backup"></a><span data-ttu-id="ad6a2-132">Создание разностной резервной копии</span><span class="sxs-lookup"><span data-stu-id="ad6a2-132">To create a differential database backup</span></span>  
  
1.  <span data-ttu-id="ad6a2-133">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-133">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ad6a2-134">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-134">Expand **Databases**, and depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="ad6a2-135">Щелкните правой кнопкой мыши базу данных, выберите пункт **Задачи**, а затем команду **Создать резервную копию**.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-135">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="ad6a2-136">Откроется диалоговое окно **Резервное копирование базы данных** .</span><span class="sxs-lookup"><span data-stu-id="ad6a2-136">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="ad6a2-137">В списке **База данных** проверьте имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-137">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="ad6a2-138">При необходимости можно выбрать другую базу данных из списка.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-138">You can optionally select a different database from the list.</span></span>  
  
     <span data-ttu-id="ad6a2-139">Разностное резервное копирование можно выполнить для любой модели восстановления (полная, с неполным протоколированием или простая).</span><span class="sxs-lookup"><span data-stu-id="ad6a2-139">You can perform a differential backup for any recovery model (full, bulk-logged, or simple).</span></span>  
  
5.  <span data-ttu-id="ad6a2-140">В списке **Тип резервной копии** выберите **Разностная**.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-140">In the **Backup type** list box, select **Differential**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ad6a2-141"> При выборе **Разностная** убедитесь в том, что флажок **Резервная копия только для копирования** снят.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-141">When **Differential** is selected, verify that the **Copy Only Backup** check box is cleared.</span></span>  
  
6.  <span data-ttu-id="ad6a2-142">В разделе **Компонент резервного копирования**выберите **База данных**.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-142">For **Backup component**, click **Database**.</span></span>  
  
7.  <span data-ttu-id="ad6a2-143">Оставьте имя резервного набора данных, предложенное по умолчанию в текстовом поле **Имя** , или введите другое имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-143">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
8.  <span data-ttu-id="ad6a2-144">При необходимости можно ввести описание резервного набора данных в текстовом поле **Описание** .</span><span class="sxs-lookup"><span data-stu-id="ad6a2-144">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
9. <span data-ttu-id="ad6a2-145">Укажите, когда истекает срок действия резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-145">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="ad6a2-146">Чтобы задать срок действия резервного набора данных, выберите пункт **После** (параметр по умолчанию) и введите срок действия набора в днях с момента его создания.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-146">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="ad6a2-147">Это значение может быть задано в диапазоне от 0 до 99 999 дней. Значение 0 означает, что срок действия резервного набора данных не ограничен.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-147">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="ad6a2-148">Значение по умолчанию задается в параметре **Срок хранения носителей резервных копий по умолчанию (дней)** диалогового окна **Свойства сервера** (страница**Параметры базы данных** ).</span><span class="sxs-lookup"><span data-stu-id="ad6a2-148">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="ad6a2-149">Чтобы получить доступ к этому параметру, щелкните правой кнопкой мыши имя сервера в обозревателе объектов и выберите пункт "Свойства", а затем выберите страницу **Настройки базы данных** .</span><span class="sxs-lookup"><span data-stu-id="ad6a2-149">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="ad6a2-150">Чтобы указать дату истечения срока действия резервного набора данных, выберите пункт **На**и введите дату истечения срока действия резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-150">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
10. <span data-ttu-id="ad6a2-151">Чтобы выбрать тип назначения резервной копии, выберите пункт **Диск** или **Лента**.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-151">Choose the type of backup destination by clicking **Disk** or **Tape**.</span></span> <span data-ttu-id="ad6a2-152">Чтобы выбрать путь к 64 (или менее) дискам или накопителям на магнитной ленте, содержащим один набор носителей, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-152">To select the path of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="ad6a2-153">Выбранные пути отображаются в списке **Создать резервную копию в** .</span><span class="sxs-lookup"><span data-stu-id="ad6a2-153">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="ad6a2-154">Чтобы удалить носитель резервной копии, выберите его и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-154">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="ad6a2-155">Чтобы просмотреть содержимое носителя резервной копии, выберите его и щелкните **Содержимое**.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-155">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
11. <span data-ttu-id="ad6a2-156">Чтобы просмотреть или выбрать дополнительные параметры, нажмите кнопку **Параметры** на панели **Выбор страницы** .</span><span class="sxs-lookup"><span data-stu-id="ad6a2-156">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
12. <span data-ttu-id="ad6a2-157">Выберите параметр **Переписать носитель** , указав один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="ad6a2-157">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="ad6a2-158">**Создать резервную копию в существующем наборе носителей**</span><span class="sxs-lookup"><span data-stu-id="ad6a2-158">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="ad6a2-159">Для этого параметра выберите вариант **Добавить в существующий резервный набор данных** или **Перезаписать все существующие резервные наборы данных**.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-159">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="ad6a2-160">При необходимости установите флажок **Проверить имя набора носителей и срок действия резервного набора данных** и, при необходимости, введите имя в текстовое поле **Имя набора носителей** .</span><span class="sxs-lookup"><span data-stu-id="ad6a2-160">Optionally, check the **Check media set name and backup set expiration** check box and, optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="ad6a2-161">Если имя не указано, создается набор носителей с пустым именем.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-161">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="ad6a2-162">Если указать имя набора носителей, носитель (ленточный или дисковый) проверяется на совпадение введенного и существующего имени.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-162">If you specify a media set name, the media (tape or disk) is checked to see if the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="ad6a2-163">Если оставить имя носителя пустым и установить рядом с ним флажок для проверки, имя носителя при успешном завершении также станет пустым.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-163">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="ad6a2-164">**Создать резервную копию в новом наборе носителей и удалить все существующие резервные наборы данных**</span><span class="sxs-lookup"><span data-stu-id="ad6a2-164">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="ad6a2-165">Для этого параметра введите имя в текстовом поле **Имя нового набора носителей** и при необходимости введите описание набора носителей в текстовое поле **Описание нового набора носителей** .</span><span class="sxs-lookup"><span data-stu-id="ad6a2-165">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
13. <span data-ttu-id="ad6a2-166">В разделе **Надежность** можно установить следующие флажки.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-166">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="ad6a2-167">**Проверить резервную копию после завершения**.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-167">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="ad6a2-168">**Рассчитать контрольную сумму перед записью на носитель**и, при необходимости, **Продолжить при ошибке контрольной суммы**.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-168">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="ad6a2-169">Дополнительные сведения о контрольных суммах см. в разделе [Возможные ошибки носителей во время резервного копирования и восстановления (SQL Server)](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ad6a2-169">For information about checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
14. <span data-ttu-id="ad6a2-170">При резервном копировании на накопитель на магнитной ленте (как указано в разделе **Назначение** страницы **Общие** ) активен параметр **Выгрузить ленту после резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="ad6a2-170">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="ad6a2-171">Щелкните этот параметр, чтобы активировать параметр **Перемотать ленту перед выгрузкой** .</span><span class="sxs-lookup"><span data-stu-id="ad6a2-171">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ad6a2-172">Параметры в разделе **Журнал транзакций** доступны, только если создается резервная копия журнала транзакций (это можно указать в разделе **Тип резервной копии** вкладки **Общие** ).</span><span class="sxs-lookup"><span data-stu-id="ad6a2-172">The options in the **Transaction log** section are inactive unless you are backing up a transaction log (as specified in the **Backup type** section of the **General** page).</span></span>  
  
15. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="ad6a2-173">и более поздние версии поддерживают [сжатие резервных копий](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ad6a2-173">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="ad6a2-174">По умолчанию сжатие резервных копий зависит от значения параметра конфигурации сервера **backup-compression default** .</span><span class="sxs-lookup"><span data-stu-id="ad6a2-174">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="ad6a2-175">Однако независимо от текущего значения по умолчанию на уровне сервера можно сжать резервные копии, установив параметр **Сжимать резервные копии**, или отказаться от сжатия резервных копий, установив параметр **Не сжимать резервные копии**.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-175">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="ad6a2-176">**Просмотр текущих значений параметров по умолчанию для сжатия резервных копий**</span><span class="sxs-lookup"><span data-stu-id="ad6a2-176">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="ad6a2-177">Параметр конфигурации сервера «Просмотр или настройка параметра сжатия резервных копий по умолчанию»</span><span class="sxs-lookup"><span data-stu-id="ad6a2-177">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
    > [!NOTE]  
    >  <span data-ttu-id="ad6a2-178">Для создания разностных резервных копий баз данных можно также воспользоваться мастером планов обслуживания базы данных.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-178">Alternatively, you can use the Maintenance Plan Wizard to create differential database backups.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ad6a2-179">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad6a2-179">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-differential-database-backup"></a><span data-ttu-id="ad6a2-180">Создание разностной резервной копии</span><span class="sxs-lookup"><span data-stu-id="ad6a2-180">To create a differential database backup</span></span>  
  
1.  <span data-ttu-id="ad6a2-181">Выполните инструкцию BACKUP DATABASE для создания разностной резервной копии базы данных, указав следующее:</span><span class="sxs-lookup"><span data-stu-id="ad6a2-181">Execute the BACKUP DATABASE statement to create the differential database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="ad6a2-182">имя базы данных для создания резервной копии;</span><span class="sxs-lookup"><span data-stu-id="ad6a2-182">The name of the database to back up.</span></span>  
  
    -   <span data-ttu-id="ad6a2-183">устройство резервного копирования, на которое записывается полная резервная копия базы данных.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-183">The backup device where the full database backup is written.</span></span>  
  
    -   <span data-ttu-id="ad6a2-184">предложение DIFFERENTIAL. Оно обозначает, что копируются только части базы данных, измененные с момента последнего полного резервного копирования базы данных.</span><span class="sxs-lookup"><span data-stu-id="ad6a2-184">The DIFFERENTIAL clause, to specify that only the parts of the database that have changed after the last full database backup was created are backed up.</span></span>  
  
     <span data-ttu-id="ad6a2-185">Необходимый синтаксис выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ad6a2-185">The required syntax is:</span></span>  
  
     <span data-ttu-id="ad6a2-186">BACKUP DATABASE *имя_базы_данных* TO <устройство_резервного_копирования> WITH DIFFERENTIAL</span><span class="sxs-lookup"><span data-stu-id="ad6a2-186">BACKUP DATABASE *database_name* TO <backup_device> WITH DIFFERENTIAL</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="ad6a2-187">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ad6a2-187">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="ad6a2-188">В этом примере показано создание полной и разностной резервной копии базы данных `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="ad6a2-188">This example creates a full and a differential database backup for the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Create a full database backup first.  
BACKUP DATABASE MyAdvWorks   
   TO MyAdvWorks_1   
   WITH INIT;  
GO  
-- Time elapses.  
-- Create a differential database backup, appending the backup  
-- to the backup device containing the full database backup.  
BACKUP DATABASE MyAdvWorks  
   TO MyAdvWorks_1  
   WITH DIFFERENTIAL;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad6a2-189">См. также:</span><span class="sxs-lookup"><span data-stu-id="ad6a2-189">See Also</span></span>  
 <span data-ttu-id="ad6a2-190">[Разностные резервные копии (SQL Server)](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ad6a2-190">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="ad6a2-191">[Создание полной резервной копии базы данных (SQL Server)](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ad6a2-191">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="ad6a2-192">[Создание резервных копий файлов и файловых групп (SQL Server)](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ad6a2-192">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="ad6a2-193">[Восстановление разностной резервной копии базы данных (SQL Server)](restore-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ad6a2-193">[Restore a Differential Database Backup &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="ad6a2-194">[Восстановление резервной копии журнала транзакций (SQL Server)](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ad6a2-194">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="ad6a2-195">[Планы обслуживания](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="ad6a2-195">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 [<span data-ttu-id="ad6a2-196">Полные резервные копии файлов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ad6a2-196">Full File Backups &#40;SQL Server&#41;</span></span>](full-file-backups-sql-server.md)  
  
  
