---
title: Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- STOPAT clause [RESTORE LOG statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
ms.assetid: 3a5daefd-08a8-4565-b54f-28ad01a47d32
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0c71ff6e75cbbf27042c1eac70b1f97076290865
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666682"
---
# <a name="restore-a-sql-server-database-to-a-point-in-time-full-recovery-model"></a><span data-ttu-id="c64d5-102">Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="c64d5-102">Restore a SQL Server Database to a Point in Time (Full Recovery Model)</span></span>
  <span data-ttu-id="c64d5-103">В данном разделе содержатся инструкции по восстановлению базы данных на определенный момент времени в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c64d5-103">This topic describes how to restore a database to a point in time in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c64d5-104">Сведения в этом разделе относятся только к тем базам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые используют полную модель восстановления или модель восстановления с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="c64d5-104">This topic is relevant only for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that use the full or bulk-logged recovery models.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c64d5-105">Если в модели восстановления с неполным протоколированием резервная копия журнала содержит изменения с неполным протоколированием, то в пределах этой резервной копии восстановление до момента времени невозможно.</span><span class="sxs-lookup"><span data-stu-id="c64d5-105">Under the bulk-logged recovery model, if a log backup contains bulk-logged changes, point-in-time recovery is not possible to a point within that backup.</span></span> <span data-ttu-id="c64d5-106">База данных должна быть восстановлена к концу резервной копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="c64d5-106">The database must be recovered to the end of the transaction log backup.</span></span>  
  
-   <span data-ttu-id="c64d5-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c64d5-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c64d5-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="c64d5-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="c64d5-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c64d5-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c64d5-110">**Восстановление базы данных SQL Server на определенный момент времени с помощью:**</span><span class="sxs-lookup"><span data-stu-id="c64d5-110">**To restore a SQL Server database to a point in time, using:**</span></span>  
  
     [<span data-ttu-id="c64d5-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c64d5-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c64d5-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c64d5-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c64d5-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c64d5-113">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c64d5-114">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="c64d5-114">Recommendations</span></span>  
  
-   <span data-ttu-id="c64d5-115">Используйте параметр STANDBY для поиска неизвестного момента времени.</span><span class="sxs-lookup"><span data-stu-id="c64d5-115">Use STANDBY to find unknown point in time.</span></span>  
  
-   <span data-ttu-id="c64d5-116">Задайте момент времени в начале последовательности восстановления</span><span class="sxs-lookup"><span data-stu-id="c64d5-116">Specify the point in time early in a restore sequence</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c64d5-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="c64d5-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c64d5-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="c64d5-118">Permissions</span></span>  
 <span data-ttu-id="c64d5-119">Если восстанавливаемая база данных не существуют, для выполнения инструкции RESTORE у пользователя должны быть разрешения CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="c64d5-119">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="c64d5-120">Если база данных существует, разрешения на выполнение инструкции RESTORE по умолчанию предоставлены членам предопределенных ролей сервера **sysadmin** и **dbcreator** , а также владельцу базы данных (**dbo**) (для параметра FROM DATABASE_SNAPSHOT база данных всегда существует).</span><span class="sxs-lookup"><span data-stu-id="c64d5-120">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="c64d5-121">Разрешения на выполнение инструкции RESTORE даются ролям, в которых данные о членстве всегда доступны серверу.</span><span class="sxs-lookup"><span data-stu-id="c64d5-121">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="c64d5-122">Так как членство в предопределенной роли базы данных может быть проверено только тогда, когда база данных доступна и не повреждена, что не всегда имеет место при выполнении инструкции RESTORE, члены предопределенной роли базы данных **db_owner** не имеют разрешений RESTORE.</span><span class="sxs-lookup"><span data-stu-id="c64d5-122">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c64d5-123">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c64d5-123">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c64d5-124">**Восстановление базы данных на момент времени**</span><span class="sxs-lookup"><span data-stu-id="c64d5-124">**To restore a database to a point in time**</span></span>  
  
1.  <span data-ttu-id="c64d5-125">В обозревателе объектов подключитесь к соответствующему экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="c64d5-125">In Object Explorer, connect to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="c64d5-126">Разверните узел **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="c64d5-126">Expand **Databases**.</span></span> <span data-ttu-id="c64d5-127">В зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных**и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="c64d5-127">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="c64d5-128">Щелкните правой кнопкой мыши базу данных, выберите пункт **Задачи**, затем пункт **Восстановить**и пункт **База данных**.</span><span class="sxs-lookup"><span data-stu-id="c64d5-128">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span>  
  
4.  <span data-ttu-id="c64d5-129">Чтобы указать источник и расположение восстанавливаемых резервных наборов данных, используйте страницу **Общие** , раздел **Источник** .</span><span class="sxs-lookup"><span data-stu-id="c64d5-129">On the **General** page, use the **Source** section to specify the source and location of the backup sets to restore.</span></span> <span data-ttu-id="c64d5-130">Выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="c64d5-130">Select one of the following options:</span></span>  
  
    -   <span data-ttu-id="c64d5-131">**База данных**</span><span class="sxs-lookup"><span data-stu-id="c64d5-131">**Database**</span></span>  
  
         <span data-ttu-id="c64d5-132">Выберите из раскрывающегося списка базу данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="c64d5-132">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="c64d5-133">Данный список содержит только базы данных, резервное копирование которых было выполнено в соответствии с журналом резервного копирования **msdb** .</span><span class="sxs-lookup"><span data-stu-id="c64d5-133">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c64d5-134">Если резервная копия была получена с другого сервера, на целевом сервере не будет журнала резервного копирования для указанной базы данных.</span><span class="sxs-lookup"><span data-stu-id="c64d5-134">If the backup is taken from a different server, the destination server will not have the backup history information for the specified database.</span></span> <span data-ttu-id="c64d5-135">В этом случае щелкните пункт **Устройство** , чтобы вручную указать файл или устройство для восстановления.</span><span class="sxs-lookup"><span data-stu-id="c64d5-135">In this case, select **Device** to manually specify the file or device to restore.</span></span>  
  
    -   <span data-ttu-id="c64d5-136">**Устройство**</span><span class="sxs-lookup"><span data-stu-id="c64d5-136">**Device**</span></span>  
  
         <span data-ttu-id="c64d5-137">Нажмите кнопку обзора ( **...** ), после чего откроется диалоговое окно **Выбор устройств резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="c64d5-137">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="c64d5-138">В окне **Тип носителя резервной копии** выберите один из перечисленных типов устройств.</span><span class="sxs-lookup"><span data-stu-id="c64d5-138">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="c64d5-139">Чтобы выбрать одно или несколько устройств в окне **Носитель резервной копии** , нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c64d5-139">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="c64d5-140">После добавления нужных устройств в списке **Носитель резервной копии** нажмите кнопку **ОК** для возвращения на страницу **Общие** .</span><span class="sxs-lookup"><span data-stu-id="c64d5-140">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
         <span data-ttu-id="c64d5-141">В списке **Источник: Устройство: База данных** выберите имя базы данных, которую нужно восстановить.</span><span class="sxs-lookup"><span data-stu-id="c64d5-141">In the **Source: Device: Database** list box, select the name of the database which should be restored.</span></span>  
  
         <span data-ttu-id="c64d5-142">**Примечание.** Этот список доступен, только если выбрано **Устройство** .</span><span class="sxs-lookup"><span data-stu-id="c64d5-142">**Note** This list is only available when **Device** is selected.</span></span> <span data-ttu-id="c64d5-143">Будут выбраны только те базы данных, резервные копии которых доступны на выбранном устройстве.</span><span class="sxs-lookup"><span data-stu-id="c64d5-143">Only databases that have backups on the selected device will be available.</span></span>  
  
5.  <span data-ttu-id="c64d5-144">В разделе **Назначение** , в поле **База данных** автоматически появится имя базы данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="c64d5-144">In the **Destination** section, the **Database** box is automatically populated with the name of the database to be restored.</span></span> <span data-ttu-id="c64d5-145">Для изменения имени базы данных введите новое имя в окно **База данных** .</span><span class="sxs-lookup"><span data-stu-id="c64d5-145">To change the name of the database, enter the new name in the **Database** box.</span></span>  
  
6.  <span data-ttu-id="c64d5-146">Щелкните **Временная шкала** для получения доступа в диалоговое окно **Временная шкала резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="c64d5-146">Click **Timeline** to access the **Backup Timeline** dialog box.</span></span>  
  
7.  <span data-ttu-id="c64d5-147">В разделе **Восстановить на** щелкните **Конкретные дата и время**.</span><span class="sxs-lookup"><span data-stu-id="c64d5-147">In the **Restore to** section, click **Specific date and time**.</span></span>  
  
8.  <span data-ttu-id="c64d5-148">Вы можете использовать окна **Данные** и **Время** или пользоваться ползунком, чтобы указать конкретные дату и время, при которых процесс восстановления должен закончиться.</span><span class="sxs-lookup"><span data-stu-id="c64d5-148">Use either the **Date** and **Time** boxes or the slider bar to specify a specific date and time to where the restore should stop.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="c64d5-149">Используйте поле **Интервал временной шкалы** для изменения количества времени, отображаемого на временной шкале.</span><span class="sxs-lookup"><span data-stu-id="c64d5-149">Use the **Timeline Interval** box to change the amount of time displayed on the timeline.</span></span>  
  
9. <span data-ttu-id="c64d5-150">После указания определенного момента времени помощник по восстановлению базы данных сделает так, что в столбце **Восстановление** сетки **Резервные наборы данных для восстановления** будут выбраны только необходимые для восстановления к указанному моменту времени резервные копии.</span><span class="sxs-lookup"><span data-stu-id="c64d5-150">After you have specified a specific point in time, the Database Recovery Advisor ensures that only backups that are required for restoring to that point in time are selected in the **Restore** column of the **Backup sets to restore** grid.</span></span> <span data-ttu-id="c64d5-151">Эти выбранные резервные копии составляют рекомендованный план восстановления для данного восстановления на момент времени.</span><span class="sxs-lookup"><span data-stu-id="c64d5-151">These selected backups make up the recommended restore plan for your point-in-time restore.</span></span> <span data-ttu-id="c64d5-152">Следует использовать только выбранные резервные копии для операции восстановления на момент времени.</span><span class="sxs-lookup"><span data-stu-id="c64d5-152">You should use only the selected backups for your point-in-time restore operation.</span></span>  
  
     <span data-ttu-id="c64d5-153">Дополнительные сведения о столбцах сетки **Резервные наборы данных для восстановления** см. в статье [Восстановление базы данных (страница "Общие")](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="c64d5-153">For information about the columns in the **Backup sets to restore** grid, see [Restore Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span> <span data-ttu-id="c64d5-154">Сведения о помощнике по восстановлению базы данных см. в статье [Обзор процессов восстановления (SQL Server)](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c64d5-154">For information about the Database Recovery Advisor, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
10. <span data-ttu-id="c64d5-155">На странице **Параметры** используйте панель **Параметры восстановления** для выбора любого из следующих вариантов, если он подходит к данной ситуации.</span><span class="sxs-lookup"><span data-stu-id="c64d5-155">On the **Options** page, in the **Restore options** panel, you can select any of the following options, if appropriate for your situation:</span></span>  
  
    -   <span data-ttu-id="c64d5-156">**Перезаписать существующую базу данных (WITH REPLACE)**</span><span class="sxs-lookup"><span data-stu-id="c64d5-156">**Overwrite the existing database (WITH REPLACE)**</span></span>  
  
    -   <span data-ttu-id="c64d5-157">**Сохранить параметры репликации (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="c64d5-157">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
    -   <span data-ttu-id="c64d5-158">**Ограничить доступ к восстановленной базе данных (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="c64d5-158">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
     <span data-ttu-id="c64d5-159">Дополнительные сведения об этих параметрах см. в статье [Восстановление базы данных (страница "Параметры")](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="c64d5-159">For more information about these options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
11. <span data-ttu-id="c64d5-160">Выберите параметр в поле **Состояние восстановления** .</span><span class="sxs-lookup"><span data-stu-id="c64d5-160">Select an option for the **Recovery state** box.</span></span> <span data-ttu-id="c64d5-161">В данном окне определяется состояние базы данных после операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="c64d5-161">This box determines the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="c64d5-162">По умолчанию установлена схема**RESTORE WITH RECOVERY** , при этом база данных находится в готовом состоянии для использования путем отката незафиксированных транзакций.</span><span class="sxs-lookup"><span data-stu-id="c64d5-162">**RESTORE WITH RECOVERY** is the default behavior which leaves the database ready for use by rolling back the uncommitted transactions.</span></span> <span data-ttu-id="c64d5-163">Невозможно восстановить дополнительные журналы транзакций.</span><span class="sxs-lookup"><span data-stu-id="c64d5-163">Additional transaction logs cannot be restored.</span></span> <span data-ttu-id="c64d5-164">Выберите данный параметр, если выполняется восстановление всех необходимых резервных копий.</span><span class="sxs-lookup"><span data-stu-id="c64d5-164">Select this option if you are restoring all of the necessary backups now.</span></span>  
  
    -   <span data-ttu-id="c64d5-165">Схема**RESTORE WITH NORECOVERY** оставляет базу данных в нерабочем состоянии и не выполняет откат незафиксированных транзакций.</span><span class="sxs-lookup"><span data-stu-id="c64d5-165">**RESTORE WITH NORECOVERY** which leaves the database non-operational, and does not roll back the uncommitted transactions.</span></span> <span data-ttu-id="c64d5-166">Можно восстановить дополнительные журналы транзакций.</span><span class="sxs-lookup"><span data-stu-id="c64d5-166">Additional transaction logs can be restored.</span></span> <span data-ttu-id="c64d5-167">База данных не может быть использована, пока не будет восстановлена.</span><span class="sxs-lookup"><span data-stu-id="c64d5-167">The database cannot be used until it is recovered.</span></span>  
  
    -   <span data-ttu-id="c64d5-168">Схема**RESTORE WITH STANDBY** оставляет базу данных в режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c64d5-168">**RESTORE WITH STANDBY** which leaves the database in read-only mode.</span></span> <span data-ttu-id="c64d5-169">С помощью данного параметра можно отменить незафиксированные транзакции и сохранить отмененные действия в резервном файле, чтобы результаты восстановления можно было отменить.</span><span class="sxs-lookup"><span data-stu-id="c64d5-169">It undoes uncommitted transactions, but saves the undo actions in a standby file so that recovery effects can be reverted.</span></span>  
  
     <span data-ttu-id="c64d5-170">Описание параметров см. в статье [Восстановление базы данных (страница "Параметры")](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="c64d5-170">For descriptions of the options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
12. <span data-ttu-id="c64d5-171">Настройка **Создать резервную копию заключительного фрагмента журнала перед восстановлением** будет выбрана, если это необходимо для указанного вами момента времени.</span><span class="sxs-lookup"><span data-stu-id="c64d5-171">**Take tail-log backup before restore** will be selected if it is necessary for the point in time that you have selected.</span></span> <span data-ttu-id="c64d5-172">Нет необходимости изменять данную настройку, однако вы можете выбрать резервное копирование заключительного фрагмента журнала, даже если выполнение этого не требуется.</span><span class="sxs-lookup"><span data-stu-id="c64d5-172">You do not need to modify this setting, but you can choose to backup the tail of the log even if it is not required.</span></span>  
  
13. <span data-ttu-id="c64d5-173">Если имеются активные соединения с базой данных, то операция восстановления может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c64d5-173">Restore operations may fail if there are active connections to the database.</span></span> <span data-ttu-id="c64d5-174">Проверьте окно **Закрыть существующие соединения** и убедитесь, что все активные соединения между [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] и базой данных закрыты.</span><span class="sxs-lookup"><span data-stu-id="c64d5-174">Check the **Close existing connections option** to ensure that all active connections between [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and the database are closed.</span></span> <span data-ttu-id="c64d5-175">Этот параметр переводит базу данных в однопользовательский режим перед началом выполнения процедуры восстановления, а затем возвращает в многопользовательский режим после ее завершения.</span><span class="sxs-lookup"><span data-stu-id="c64d5-175">This check box sets the database to single user mode before performing the restore operations, and sets the database to multi-user mode when complete.</span></span>  
  
14. <span data-ttu-id="c64d5-176">Установите флажок **Выдавать запрос перед восстановлением каждой резервной копии** , если хотите отследить каждую операцию восстановления.</span><span class="sxs-lookup"><span data-stu-id="c64d5-176">Select **Prompt before restoring each backup** if you wish to be prompted between each restore operation.</span></span> <span data-ttu-id="c64d5-177">Обычно это не требуется, за исключением случаев, если необходимо наблюдать за состоянием операции восстановления базы данных большого объема.</span><span class="sxs-lookup"><span data-stu-id="c64d5-177">This is not usually necessary unless the database is large and you wish to monitor the status of the restore operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c64d5-178">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c64d5-178">Using Transact-SQL</span></span>  
 <span data-ttu-id="c64d5-179">**Before you begin**</span><span class="sxs-lookup"><span data-stu-id="c64d5-179">**Before you begin**</span></span>  
  
 <span data-ttu-id="c64d5-180">Восстановление на момент времени всегда производится из резервной копии журналов.</span><span class="sxs-lookup"><span data-stu-id="c64d5-180">A specified time is always restored from a log backup.</span></span> <span data-ttu-id="c64d5-181">В каждой инструкции RESTORE LOG последовательности восстановления необходимо указать целевое время или транзакцию в идентичном предложении STOPAT.</span><span class="sxs-lookup"><span data-stu-id="c64d5-181">In every RESTORE LOG statement of the restore sequence, you must specify your target time or transaction in an identical STOPAT clause.</span></span> <span data-ttu-id="c64d5-182">В качестве предварительного условия для восстановления на момент времени необходимо сначала восстановить полную резервную копию базы данных, чья конечная точка предшествует моменту времени восстановления.</span><span class="sxs-lookup"><span data-stu-id="c64d5-182">As a prerequisite to a point-in-time restore, you must first restore a full database backup whose end point is earlier than your target restore time.</span></span> <span data-ttu-id="c64d5-183">Эта полная резервная копия базы данных может быть старше самой последней полной резервной копии базы данных, поскольку затем восстанавливается каждая последующая резервная копия журналов, вплоть до резервной копии журналов, содержащей целевой момент времени.</span><span class="sxs-lookup"><span data-stu-id="c64d5-183">That full database backup can be older than the most recent full database backup as long as you then restore every subsequent log backup, up to and including the log backup that contains your target point in time.</span></span>  
  
 <span data-ttu-id="c64d5-184">Чтобы облегчить выбор резервной копии базы данных для восстановления, можно указать в инструкции RESTORE DATABASE предложение WITH STOPAT, которое вызовет ошибку, если данные резервной копии являются слишком новыми для указанного целевого времени.</span><span class="sxs-lookup"><span data-stu-id="c64d5-184">To help you identify which database backup to restore, you can optionally specify your WITH STOPAT clause in your RESTORE DATABASE statement to raise an error if a data backup is too recent for the specified target time.</span></span> <span data-ttu-id="c64d5-185">Резервная копия базы данных восстанавливается полностью, даже если она содержит целевое время.</span><span class="sxs-lookup"><span data-stu-id="c64d5-185">The complete data backup is always restored, even if it contains the target time.</span></span>  
  
 <span data-ttu-id="c64d5-186">**Основной синтаксис [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="c64d5-186">**Basic [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax**</span></span>  
  
 <span data-ttu-id="c64d5-187">RESTORE LOG *database_name* из <backup_device> с параметром STOPAT \*\* = *`time`* ,\*\* Recovery...</span><span class="sxs-lookup"><span data-stu-id="c64d5-187">RESTORE LOG *database_name* FROM <backup_device> WITH STOPAT **=*`time`*,** RECOVERY...</span></span>  
  
 <span data-ttu-id="c64d5-188">Точка восстановления — это последняя фиксация транзакции, которая произошла в или до `datetime` значения, указанного в параметре *time*.</span><span class="sxs-lookup"><span data-stu-id="c64d5-188">The recovery point is the latest transaction commit that occurred at or before the `datetime` value that is specified by *time*.</span></span>  
  
 <span data-ttu-id="c64d5-189">Чтобы восстановить только изменения до определенного момента времени, для каждой восстанавливаемой резервной копии укажите WITH STOPAT **=** *время*.</span><span class="sxs-lookup"><span data-stu-id="c64d5-189">To restore only the modifications that were made before a specific point in time, specify WITH STOPAT **=** *time* for each backup you restore.</span></span> <span data-ttu-id="c64d5-190">Это гарантирует, что конечное время не будет пропущено.</span><span class="sxs-lookup"><span data-stu-id="c64d5-190">This makes sure that you do not go past the target time.</span></span>  
  
 <span data-ttu-id="c64d5-191">**Восстановление базы данных на момент времени**</span><span class="sxs-lookup"><span data-stu-id="c64d5-191">**To restore a database to a point in time**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c64d5-192">Пример этой процедуры см. в подразделе [Примеры (Transact-SQL)](#TsqlExample)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c64d5-192">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="c64d5-193">Подключитесь к экземпляру сервера, на который необходимо восстановить базу данных.</span><span class="sxs-lookup"><span data-stu-id="c64d5-193">Connect to server instance on which you want to restore the database.</span></span>  
  
2.  <span data-ttu-id="c64d5-194">Выполните инструкцию RESTORE DATABASE с параметром NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="c64d5-194">Execute the RESTORE DATABASE statement using the NORECOVERY option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c64d5-195">Если последовательность частичного восстановления исключает любые файловые группы [FILESTREAM](../blob/filestream-sql-server.md) , восстановление на момент времени не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c64d5-195">If a partial restore sequence excludes any [FILESTREAM](../blob/filestream-sql-server.md) filegroup, point-in-time restore is not supported.</span></span> <span data-ttu-id="c64d5-196">Можно принудительно продолжить последовательность восстановления.</span><span class="sxs-lookup"><span data-stu-id="c64d5-196">You can force the restore sequence to continue.</span></span> <span data-ttu-id="c64d5-197">Тем не менее файловые группы FILESTREAM, не вошедшие в инструкцию RESTORE, больше невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="c64d5-197">However the FILESTREAM filegroups that are omitted from your RESTORE statement can never be restored.</span></span> <span data-ttu-id="c64d5-198">Для принудительного продолжения восстановления на момент времени укажите параметр CONTINUE_AFTER_ERROR вместе с параметром STOPAT, STOPATMARK или STOPBEFOREMARK, который также необходимо указать в своих последующих инструкциях RESTORE LOG.</span><span class="sxs-lookup"><span data-stu-id="c64d5-198">To force a point-in-time restore, specify the CONTINUE_AFTER_ERROR option together with the STOPAT, STOPATMARK, or STOPBEFOREMARK option, which you must also specify in your subsequent RESTORE LOG statements.</span></span> <span data-ttu-id="c64d5-199">Если указать параметр CONTINUE_AFTER_ERROR, выполняется последовательность частичного восстановления, а файловая группа FILESTREAM становится невосстановимой.</span><span class="sxs-lookup"><span data-stu-id="c64d5-199">If you specify CONTINUE_AFTER_ERROR, the partial restore sequence succeeds and the FILESTREAM filegroup becomes unrecoverable.</span></span>  
  
3.  <span data-ttu-id="c64d5-200">Восстановите последнюю разностную резервную копию, если таковая имеется, без восстановления базы данных (RESTORE DATABASE *имя_базы_данных* FROM *устройство_резервного_копирования* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="c64d5-200">Restore the last differential database backup, if any,  without recovering the database (RESTORE DATABASE *database_name* FROM *backup_device* WITH NORECOVERY).</span></span>  
  
4.  <span data-ttu-id="c64d5-201">Примените каждую резервную копию журнала транзакций в той же последовательности, в которой они были созданы, указав время, когда необходимо отключить восстановление журнала (RESTORE DATABASE *database_name* из <backup_device> STOPAT\*\* = *`time`* ,\*\* Recovery).</span><span class="sxs-lookup"><span data-stu-id="c64d5-201">Apply each transaction log backup in the same sequence in which they were created, specifying the time at which you intend to stop restoring log (RESTORE DATABASE *database_name* FROM <backup_device> WITH STOPAT**=*`time`*,** RECOVERY).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c64d5-202">Параметры RECOVERY и STOPAT.</span><span class="sxs-lookup"><span data-stu-id="c64d5-202">The RECOVERY and STOPAT options.</span></span> <span data-ttu-id="c64d5-203">Если в резервной копии журнала транзакций не содержится требуемое время (например, если указанное время выходит за рамки времени, отраженного в журнале транзакций), создается предупреждение и база данных остается невосстановленной.</span><span class="sxs-lookup"><span data-stu-id="c64d5-203">If the transaction log backup does not contain the requested time (for example, if the time specified is beyond the end of the time covered by the transaction log), a warning is generated and the database remains unrecovered.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="c64d5-204">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c64d5-204">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="c64d5-205">В следующем примере база данных восстанавливается в состояние на `12:00 AM``April 15, 2020` и демонстрируется операция восстановления, использующая несколько резервных копий журналов.</span><span class="sxs-lookup"><span data-stu-id="c64d5-205">The following example restores a database to its state as of `12:00 AM` on `April 15, 2020` and shows a restore operation that involves multiple log backups.</span></span> <span data-ttu-id="c64d5-206">На устройстве резервного копирования `AdventureWorksBackups` полная резервная копия базы данных, подлежащей восстановлению, — это третий резервный набор данных на устройстве (`FILE = 3`), резервная копия первого журнала — это четвертый резервный набор (`FILE = 4`), резервная копия второго журнала — это пятый резервный набор (`FILE = 5`).</span><span class="sxs-lookup"><span data-stu-id="c64d5-206">On the backup device, `AdventureWorksBackups`, the full database backup to be restored is the third backup set on the device (`FILE = 3`), the first log backup is the fourth backup set (`FILE = 4`), and the second log backup is the fifth backup set (`FILE = 5`).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c64d5-207">В базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] используется простая модель восстановления.</span><span class="sxs-lookup"><span data-stu-id="c64d5-207">The [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database uses the simple recovery model.</span></span> <span data-ttu-id="c64d5-208">Чтобы разрешить создание резервных копий журналов, перед проведением полного резервного копирования базу данных необходимо настроить на использование модели полного восстановления, выполнив инструкцию `ALTER DATABASE AdventureWorks SET RECOVERY FULL`.</span><span class="sxs-lookup"><span data-stu-id="c64d5-208">To permit log backups, before taking a full database backup, the database was set to use the full recovery model, using `ALTER DATABASE AdventureWorks SET RECOVERY FULL`.</span></span>  
  
```  
RESTORE DATABASE AdventureWorks  
   FROM AdventureWorksBackups  
   WITH FILE=3, NORECOVERY;  
  
RESTORE LOG AdventureWorks  
   FROM AdventureWorksBackups  
   WITH FILE=4, NORECOVERY, STOPAT = 'Apr 15, 2020 12:00 AM';  
  
RESTORE LOG AdventureWorks  
   FROM AdventureWorksBackups  
   WITH FILE=5, NORECOVERY, STOPAT = 'Apr 15, 2020 12:00 AM';  
RESTORE DATABASE AdventureWorks WITH RECOVERY;   
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="c64d5-209">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="c64d5-209">Related Tasks</span></span>  
  
-   [<span data-ttu-id="c64d5-210">Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="c64d5-210">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="c64d5-211">Создание резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c64d5-211">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="c64d5-212">Восстановление базы данных до точки сбоя в модели полного восстановления (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c64d5-212">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="c64d5-213">Восстановление базы данных до помеченной транзакции (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c64d5-213">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="c64d5-214">Восстановление до номера LSN (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c64d5-214">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="c64d5-215">См. также:</span><span class="sxs-lookup"><span data-stu-id="c64d5-215">See Also</span></span>  
 <span data-ttu-id="c64d5-216">[backupset (Transact-SQL)](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c64d5-216">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="c64d5-217">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c64d5-217">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="c64d5-218">RESTORE HEADERONLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c64d5-218">RESTORE HEADERONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
  
