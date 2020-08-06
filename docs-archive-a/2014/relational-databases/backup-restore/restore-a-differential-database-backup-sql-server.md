---
title: Восстановление разностной резервной копии базы данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full differential backups [SQL Server]
- restoring databases [SQL Server], full differential backups
- database backups [SQL Server], full differential backups
- database restores [SQL Server], full differential backups
- backing up databases [SQL Server], full differential backups
ms.assetid: 0dd971a4-ee38-4dd3-9f30-ef77fc58dd11
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a8eab18d84efc1a990715e0d5488085252f93a7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666683"
---
# <a name="restore-a-differential-database-backup-sql-server"></a><span data-ttu-id="fe3ca-102">Восстановление разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fe3ca-102">Restore a Differential Database Backup (SQL Server)</span></span>
  <span data-ttu-id="fe3ca-103">В этом разделе описано, как восстановить разностную резервную копию базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe3ca-103">This topic describes how to restore a differential database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="fe3ca-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="fe3ca-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fe3ca-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="fe3ca-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fe3ca-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="fe3ca-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="fe3ca-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="fe3ca-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="fe3ca-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="fe3ca-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fe3ca-109">**Восстановление разностной резервной копии базы данных с помощью:**</span><span class="sxs-lookup"><span data-stu-id="fe3ca-109">**To restore a differential database backup, using:**</span></span>  
  
     [<span data-ttu-id="fe3ca-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fe3ca-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fe3ca-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fe3ca-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="fe3ca-112">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="fe3ca-112">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fe3ca-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="fe3ca-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fe3ca-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="fe3ca-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="fe3ca-115">Инструкция RESTORE недопустима в явной или неявной транзакции.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-115">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="fe3ca-116">Резервные копии, созданные более поздними версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , не могут быть восстановлены в более ранних версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe3ca-116">Backups that are created by more recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be restored in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="fe3ca-117">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]можно восстановить пользовательскую базу данных из резервной копии базы данных, созданной с помощью [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-117">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can restore a user database from a database backup that was created by using [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="fe3ca-118">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="fe3ca-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="fe3ca-119">Перед восстановлением базы данных в среде по модели полного восстановления или модели восстановления с неполным протоколированием необходимо выполнить резервное копирование активного журнала транзакций (который называется заключительным фрагментом журнала).</span><span class="sxs-lookup"><span data-stu-id="fe3ca-119">Under the full or bulk-logged recovery model, before you can restore a database, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="fe3ca-120">Дополнительные сведения см. в статье [Создание резервной копии журнала транзакций (SQL Server)](back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="fe3ca-120">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fe3ca-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="fe3ca-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fe3ca-122">Permissions</span><span class="sxs-lookup"><span data-stu-id="fe3ca-122">Permissions</span></span>  
 <span data-ttu-id="fe3ca-123">Если восстанавливаемая база данных не существуют, для выполнения инструкции RESTORE у пользователя должны быть разрешения CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="fe3ca-124">Если база данных существует, разрешения на выполнение инструкции RESTORE по умолчанию предоставлены членам предопределенных ролей сервера **sysadmin** и **dbcreator** , а также владельцу базы данных (**dbo**) (для параметра FROM DATABASE_SNAPSHOT база данных всегда существует).</span><span class="sxs-lookup"><span data-stu-id="fe3ca-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="fe3ca-125">Разрешения на выполнение инструкции RESTORE даются ролям, в которых данные о членстве всегда доступны серверу.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="fe3ca-126">Так как членство в предопределенной роли базы данных может быть проверено только тогда, когда база данных доступна и не повреждена, что не всегда имеет место при выполнении инструкции RESTORE, члены предопределенной роли базы данных **db_owner** не имеют разрешений RESTORE.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fe3ca-127">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fe3ca-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-a-differential-database-backup"></a><span data-ttu-id="fe3ca-128">Восстановление разностной резервной копии базы данных</span><span class="sxs-lookup"><span data-stu-id="fe3ca-128">To restore a differential database backup</span></span>  
  
1.  <span data-ttu-id="fe3ca-129">После подключения к соответствующему экземпляру компонента [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув имя сервера.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-129">After you connect to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="fe3ca-130">Разверните узел **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-130">Expand **Databases**.</span></span> <span data-ttu-id="fe3ca-131">В зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных**и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-131">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="fe3ca-132">Щелкните правой кнопкой мыши базу данных, выберите пункт **Задачи**, затем пункт **Восстановить**и пункт **База данных**.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-132">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span>  
  
4.  <span data-ttu-id="fe3ca-133">Чтобы указать источник и расположение восстанавливаемых резервных наборов данных, используйте страницу **Общие** , раздел **Источник** .</span><span class="sxs-lookup"><span data-stu-id="fe3ca-133">On the **General** page, use the **Source** section to specify the source and location of the backup sets to restore.</span></span> <span data-ttu-id="fe3ca-134">Выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-134">Select one of the following options:</span></span>  
  
    -   <span data-ttu-id="fe3ca-135">**База данных**</span><span class="sxs-lookup"><span data-stu-id="fe3ca-135">**Database**</span></span>  
  
         <span data-ttu-id="fe3ca-136">Выберите из раскрывающегося списка базу данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-136">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="fe3ca-137">Данный список содержит только базы данных, резервное копирование которых было выполнено в соответствии с журналом резервного копирования **msdb** .</span><span class="sxs-lookup"><span data-stu-id="fe3ca-137">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fe3ca-138">Если резервная копия была получена с другого сервера, на целевом сервере не будет журнала резервного копирования для указанной базы данных.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-138">If the backup is taken from a different server, the destination server will not have the backup history information for the specified database.</span></span> <span data-ttu-id="fe3ca-139">В этом случае щелкните пункт **Устройство** , чтобы вручную указать файл или устройство для восстановления.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-139">In this case, select **Device** to manually specify the file or device to restore.</span></span>  
  
    -   <span data-ttu-id="fe3ca-140">**Устройство**</span><span class="sxs-lookup"><span data-stu-id="fe3ca-140">**Device**</span></span>  
  
         <span data-ttu-id="fe3ca-141">Нажмите кнопку обзора ( **...** ), после чего откроется диалоговое окно **Выбор устройств резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="fe3ca-141">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="fe3ca-142">В окне **Тип носителя резервной копии** выберите один из перечисленных типов устройств.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-142">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="fe3ca-143">Чтобы выбрать одно или несколько устройств в окне **Носитель резервной копии** , нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-143">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="fe3ca-144">После добавления нужных устройств в списке **Носитель резервной копии** нажмите кнопку **ОК** для возвращения на страницу **Общие** .</span><span class="sxs-lookup"><span data-stu-id="fe3ca-144">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
         <span data-ttu-id="fe3ca-145">В списке **Источник: Устройство: База данных** выберите имя базы данных, из которой нужно восстановить резервные копии.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-145">In the **Source: Device: Database** list box, select the name of the database which should be restored.</span></span>  
  
         <span data-ttu-id="fe3ca-146">**Примечание.** Этот список доступен, только если выбрано **Устройство** .</span><span class="sxs-lookup"><span data-stu-id="fe3ca-146">**Note** This list is only available when **Device** is selected.</span></span> <span data-ttu-id="fe3ca-147">Будут выбраны только те базы данных, резервные копии которых доступны на выбранном устройстве.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-147">Only databases that have backups on the selected device will be available.</span></span>  
  
5.  <span data-ttu-id="fe3ca-148">В разделе **Назначение** , в поле **База данных** автоматически появится имя базы данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-148">In the **Destination** section, the **Database** box is automatically populated with the name of the database to be restored.</span></span> <span data-ttu-id="fe3ca-149">Для изменения имени базы данных введите новое имя в окно **База данных** .</span><span class="sxs-lookup"><span data-stu-id="fe3ca-149">To change the name of the database, enter the new name in the **Database** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fe3ca-150">Для остановки восстановления на определенный момент времени выберите пункт **Временная шкала** и перейдите в диалоговое окно **Временная шкала резервных копий** .</span><span class="sxs-lookup"><span data-stu-id="fe3ca-150">To stop the restore at a specific point in time, click **Timeline** to access the **Backup Timeline** dialog box.</span></span> <span data-ttu-id="fe3ca-151">Справочные сведения по остановке восстановления базы данных в определенный момент доступны в разделе [Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="fe3ca-151">For help with stopping a database restore at a specific point in time, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
6.  <span data-ttu-id="fe3ca-152">В сетке **Резервные наборы данных для восстановления** выберите резервные копии, которые необходимо восстановить с помощью разностного восстановления.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-152">In the **Backup sets to restore** grid, select the backups through the differential backup that you wish to restore.</span></span>  
  
     <span data-ttu-id="fe3ca-153">Дополнительные сведения о столбцах сетки **Резервные наборы данных для восстановления** см. в статье [Восстановление базы данных (страница "Общие")](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="fe3ca-153">For information about the columns in the **Backup sets to restore** grid, see [Restore Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
7.  <span data-ttu-id="fe3ca-154">На странице **Параметры** используйте панель **Параметры восстановления** для выбора любого из следующих вариантов, если он подходит к данной ситуации.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-154">On the **Options** page, in the **Restore options** panel, you can select any of the following options, if appropriate for your situation:</span></span>  
  
    -   <span data-ttu-id="fe3ca-155">**Перезаписать существующую базу данных (WITH REPLACE)**</span><span class="sxs-lookup"><span data-stu-id="fe3ca-155">**Overwrite the existing database (WITH REPLACE)**</span></span>  
  
    -   <span data-ttu-id="fe3ca-156">**Сохранить параметры репликации (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="fe3ca-156">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
    -   <span data-ttu-id="fe3ca-157">**Выдавать приглашение перед восстановлением каждой резервной копии**</span><span class="sxs-lookup"><span data-stu-id="fe3ca-157">**Prompt before restoring each backup**</span></span>  
  
    -   <span data-ttu-id="fe3ca-158">**Ограничить доступ к восстановленной базе данных (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="fe3ca-158">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
     <span data-ttu-id="fe3ca-159">Дополнительные сведения об этих параметрах см. в статье [Восстановление базы данных (страница "Параметры")](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="fe3ca-159">For more information about these options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
8.  <span data-ttu-id="fe3ca-160">Выберите параметр в поле **Состояние восстановления** .</span><span class="sxs-lookup"><span data-stu-id="fe3ca-160">Select an option for the **Recovery state** box.</span></span> <span data-ttu-id="fe3ca-161">В данном окне определяется состояние базы данных после операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-161">This box determines the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="fe3ca-162">По умолчанию установлена схема**RESTORE WITH RECOVERY** , при этом база данных находится в готовом состоянии для использования путем отката незафиксированных транзакций.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-162">**RESTORE WITH RECOVERY** is the default behavior which leaves the database ready for use by rolling back the uncommitted transactions.</span></span> <span data-ttu-id="fe3ca-163">Невозможно восстановить дополнительные журналы транзакций.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-163">Additional transaction logs cannot be restored.</span></span> <span data-ttu-id="fe3ca-164">Выберите данный параметр, если выполняется восстановление всех необходимых резервных копий.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-164">Select this option if you are restoring all of the necessary backups now.</span></span>  
  
    -   <span data-ttu-id="fe3ca-165">Схема**RESTORE WITH NORECOVERY** оставляет базу данных в нерабочем состоянии и не выполняет откат незафиксированных транзакций.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-165">**RESTORE WITH NORECOVERY** which leaves the database non-operational, and does not roll back the uncommitted transactions.</span></span> <span data-ttu-id="fe3ca-166">Можно восстановить дополнительные журналы транзакций.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-166">Additional transaction logs can be restored.</span></span> <span data-ttu-id="fe3ca-167">База данных не может быть использована, пока не будет восстановлена.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-167">The database cannot be used until it is recovered.</span></span>  
  
    -   <span data-ttu-id="fe3ca-168">Схема**RESTORE WITH STANDBY** оставляет базу данных в режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-168">**RESTORE WITH STANDBY** which leaves the database in read-only mode.</span></span> <span data-ttu-id="fe3ca-169">С помощью данного параметра можно отменить незафиксированные транзакции и сохранить отмененные действия в резервном файле, чтобы результаты восстановления можно было отменить.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-169">It undoes uncommitted transactions, but saves the undo actions in a standby file so that recovery effects can be reverted.</span></span>  
  
     <span data-ttu-id="fe3ca-170">Описание параметров см. в статье [Восстановление базы данных (страница "Параметры")](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="fe3ca-170">For descriptions of the options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
9. <span data-ttu-id="fe3ca-171">Если имеются активные соединения с базой данных, операции восстановления завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-171">Restore operations will fail if there are active connections to the database.</span></span> <span data-ttu-id="fe3ca-172">Проверьте окно **Закрыть существующие соединения** и убедитесь, что все активные соединения между [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] и базой данных закрыты.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-172">Check the **Close existing connections option** to ensure that all active connections between [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and the database are closed.</span></span>  
  
10. <span data-ttu-id="fe3ca-173">Установите флажок **Выдавать запрос перед восстановлением каждой резервной копии** , если хотите отследить каждую операцию восстановления.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-173">Select **Prompt before restoring each backup** if you wish to be prompted between each restore operation.</span></span> <span data-ttu-id="fe3ca-174">Обычно это не требуется, за исключением случаев, если необходимо наблюдать за состоянием операции восстановления базы данных большого объема.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-174">This is not usually necessary unless the database is large and you wish to monitor the status of the restore operation.</span></span>  
  
11. <span data-ttu-id="fe3ca-175">По желанию можно использовать страницу **Файлы** для восстановления базы данных в новом расположении.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-175">Optionally, use the **Files** page to restore the database to a new location.</span></span> <span data-ttu-id="fe3ca-176">Дополнительные сведения см. в разделе [Восстановление базы данных в новом расположении (SQL Server)](restore-a-database-to-a-new-location-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fe3ca-176">For help with moving a database, see [Restore a Database to a New Location &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md).</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fe3ca-177">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fe3ca-177">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-a-differential-database-backup"></a><span data-ttu-id="fe3ca-178">Восстановление разностной резервной копии базы данных</span><span class="sxs-lookup"><span data-stu-id="fe3ca-178">To restore a differential database backup</span></span>  
  
1.  <span data-ttu-id="fe3ca-179">Выполните инструкцию RESTORE DATABASE с предложением NORECOVERY, чтобы восстановить полную резервную копию базы данных, которая предшествует разностной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-179">Execute the RESTORE DATABASE statement, specifying the NORECOVERY clause, to restore the full database backup that comes before the differential database backup.</span></span> <span data-ttu-id="fe3ca-180">Дополнительные сведения см. в разделе [Как восстановить полную резервную копию](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="fe3ca-180">For more information, see [How to: Restore a Full Backup](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="fe3ca-181">Выполните инструкцию RESTORE DATABASE для восстановления разностной резервной копии базы данных, указав:</span><span class="sxs-lookup"><span data-stu-id="fe3ca-181">Execute the RESTORE DATABASE statement to restore the differential database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="fe3ca-182">имя базы данных, к которой будет применена разностная резервная копия;</span><span class="sxs-lookup"><span data-stu-id="fe3ca-182">The name of the database to which the differential database backup is applied.</span></span>  
  
    -   <span data-ttu-id="fe3ca-183">устройство резервного копирования, с которого происходит восстановление разностной резервной копии базы данных;</span><span class="sxs-lookup"><span data-stu-id="fe3ca-183">The backup device where the differential database backup is restored from.</span></span>  
  
    -   <span data-ttu-id="fe3ca-184">предложение NORECOVERY в случае, если нужно применить резервные копии журнала транзакций после восстановления разностной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-184">The NORECOVERY clause if you have transaction log backups to apply after the differential database backup is restored.</span></span> <span data-ttu-id="fe3ca-185">В противном случае укажите предложение RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-185">Otherwise, specify the RECOVERY clause.</span></span>  
  
3.  <span data-ttu-id="fe3ca-186">В модели полного восстановления или модели восстановления с неполным протоколированием разностная резервная копия восстанавливает базу данных на момент выполнения разностного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-186">With the full or bulk-logged recovery model, restoring a differential database backup restores the database to the point at which the differential database backup was completed.</span></span> <span data-ttu-id="fe3ca-187">Чтобы восстановить данные на момент сбоя, следует применить все резервные копии журнала транзакций, созданные после создания последней разностной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-187">To recover to the point of failure, you must apply all transaction log backups created after the last differential database backup was created.</span></span> <span data-ttu-id="fe3ca-188">Дополнительные сведения см. в разделе [Применение резервных копий журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fe3ca-188">For more information, see [Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="fe3ca-189">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fe3ca-189">Examples (Transact-SQL)</span></span>  
  
#### <a name="a-restoring-a-differential-database-backup"></a><span data-ttu-id="fe3ca-190">A.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-190">A.</span></span> <span data-ttu-id="fe3ca-191">Восстановление разностной резервной копии базы данных</span><span class="sxs-lookup"><span data-stu-id="fe3ca-191">Restoring a differential database backup</span></span>  
 <span data-ttu-id="fe3ca-192">В этом примере показано восстановление базы данных и разностной резервной копии базы данных `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="fe3ca-192">This example restores a database and differential database backup of the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Assume the database is lost, and restore full database,   
-- specifying the original full database backup and NORECOVERY,   
-- which allows subsequent restore operations to proceed.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH NORECOVERY;  
GO  
-- Now restore the differential database backup, the second backup on   
-- the MyAdvWorks_1 backup device.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH FILE = 2,  
   RECOVERY;  
GO  
```  
  
#### <a name="b-restoring-a-database-differential-database-and-transaction-log-backup"></a><span data-ttu-id="fe3ca-193">Б.</span><span class="sxs-lookup"><span data-stu-id="fe3ca-193">B.</span></span> <span data-ttu-id="fe3ca-194">Восстановление базы данных, разностной резервной копии базы данных и журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="fe3ca-194">Restoring a database, differential database, and transaction log backup</span></span>  
 <span data-ttu-id="fe3ca-195">В этом примере показано восстановление базы данных, разностной резервной копии базы данных и резервной копии журнала транзакций базы данных `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="fe3ca-195">This example restores a database, differential database, and transaction log backup of the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Assume the database is lost at this point. Now restore the full   
-- database. Specify the original full database backup and NORECOVERY.  
-- NORECOVERY allows subsequent restore operations to proceed.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH NORECOVERY;  
GO  
-- Now restore the differential database backup, the second backup on   
-- the MyAdvWorks_1 backup device.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH FILE = 2,  
   NORECOVERY;  
GO  
-- Now restore each transaction log backup created after  
-- the differential database backup.  
RESTORE LOG MyAdvWorks  
   FROM MyAdvWorks_log1  
   WITH NORECOVERY;  
GO  
RESTORE LOG MyAdvWorks  
   FROM MyAdvWorks_log2  
   WITH RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="fe3ca-196">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="fe3ca-196">Related Tasks</span></span>  
  
-   [<span data-ttu-id="fe3ca-197">Создание разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fe3ca-197">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="fe3ca-198">Восстановление резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fe3ca-198">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="fe3ca-199">См. также:</span><span class="sxs-lookup"><span data-stu-id="fe3ca-199">See Also</span></span>  
 <span data-ttu-id="fe3ca-200">[Разностные резервные копии (SQL Server)](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fe3ca-200">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="fe3ca-201">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fe3ca-201">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
